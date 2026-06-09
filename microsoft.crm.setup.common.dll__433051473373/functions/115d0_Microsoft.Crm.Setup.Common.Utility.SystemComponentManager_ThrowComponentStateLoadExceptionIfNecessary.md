# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::ThrowComponentStateLoadExceptionIfNecessary

- ea: `0x115d0`
- end: `0x115f0`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::ThrowComponentStateLoadExceptionIfNecessary`
- size: `32`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11350`
- `0x11380`
- `0x113e0`

## callees

- `0x115d0`
- `0x11710`
- `0x11730`

## pseudocode

```c

```

## disassembly

```asm
0x115d0  ldarg.0
0x115d1  call     instance class [mscorlib]System.Exception Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_ExceptionThrownDuringComponentLoad()
0x115d6  brfalse.s loc_115DF
0x115d8  ldarg.0
0x115d9  call     instance class [mscorlib]System.Exception Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_ExceptionThrownDuringComponentLoad()
0x115de  throw
0x115df  ldarg.0
0x115e0  call     instance bool Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_ComponentStatesLoaded()
0x115e5  ldstr    aInitializeMust// "Initialize must be called first."
0x115ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x115ef  ret
```
