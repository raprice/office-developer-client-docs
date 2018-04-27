---
title: "Requery Method (ADO)"
 
 
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
  
localization_priority: Normal
ms.assetid: 1062d907-979f-020a-b2ed-94e11c0e7d08

---

# Requery Method (ADO)

Updates the data in a [Recordset](recordset-object-ado.md) object by re-executing the query on which the object is based. 
  
## Syntax

 *recordset*  . **Requery** * Options * 
  
## Parameter

-  *Options* 
    
- Optional. A bitmask that contains [ExecuteOptionEnum](executeoptionenum.md) and [CommandTypeEnum](commandtypeenum.md) values affecting this operation. 
    
> [!NOTE]
> If  *Options*  is set to **adAsyncExecute**, this operation will execute asynchronously and a [RecordsetChangeComplete](willchangerecordset-and-recordsetchangecomplete-events-ado.md) event will be issued when it concludes. 
  
The **ExecuteOpenEnum** values of **adExecuteNoRecords** or **adExecuteStream** should not be used with **Requery**. 
  
## Remarks

Use the **Requery** method to refresh the entire contents of a **Recordset** object from the data source by reissuing the original command and retrieving the data a second time. Calling this method is equivalent to calling the [Close](close-method-ado.md) and [Open](open-method-ado-recordset.md) methods in succession. If you are editing the current record or adding a new record, an error occurs. 
  
While the **Recordset** object is open, the properties that define the nature of the cursor ( [CursorType](cursortype-property-ado.md), [LockType](locktype-property-ado.md), [MaxRecords](maxrecords-property-ado.md), and so forth) are read-only. Thus, the **Requery** method can only refresh the current cursor. To change any of the cursor properties and view the results, you must use the [Close](close-method-ado.md) method so that the properties become read/write again. You can then change the property settings and call the [Open](open-method-ado-recordset.md) method to reopen the cursor. 
  
