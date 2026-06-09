# SystemSettings::DataModel::Details::_dynamic_atexit_destructor_for__s_handlersResourceMapCache__

- ea: `0x180013ea0`
- end: `0x180013ec2`
- name: `SystemSettings::DataModel::Details::_dynamic_atexit_destructor_for__s_handlersResourceMapCache__`
- size: `34`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180013ea0`
- `0x180014010`

## pseudocode

```c
__int64 SystemSettings::DataModel::Details::_dynamic_atexit_destructor_for__s_handlersResourceMapCache__()
{
  __int64 result; // rax

  if ( SystemSettings::DataModel::Details::s_handlersResourceMapCache )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)SystemSettings::DataModel::Details::s_handlersResourceMapCache
                                              + 16LL))(SystemSettings::DataModel::Details::s_handlersResourceMapCache);
  return result;
}

```

## disassembly

```asm
0x180013ea0  sub     rsp, 28h
0x180013ea4  mov     rcx, cs:?s_handlersResourceMapCache@Details@DataModel@SystemSettings@@3V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> SystemSettings::DataModel::Details::s_handlersResourceMapCache
0x180013eab  test    rcx, rcx
0x180013eae  jz      short loc_180013EBD
0x180013eb0  mov     rax, [rcx]
0x180013eb3  mov     rax, [rax+10h]
0x180013eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ebc  nop
0x180013ebd  add     rsp, 28h
0x180013ec1  retn
```
