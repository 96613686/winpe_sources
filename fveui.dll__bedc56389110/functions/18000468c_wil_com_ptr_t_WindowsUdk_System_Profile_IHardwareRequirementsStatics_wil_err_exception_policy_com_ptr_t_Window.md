# wil::com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>::~com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>(void)

- ea: `0x18000468c`
- end: `0x1800046aa`
- name: `??1?$com_ptr_t@UIHardwareRequirementsStatics@Profile@System@WindowsUdk@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009768`
- `0x18002c599`

## callees

- `0x18000468c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>::~com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000468c  sub     rsp, 28h
0x180004690  mov     rcx, [rcx]
0x180004693  test    rcx, rcx
0x180004696  jz      short loc_1800046A5
0x180004698  mov     rax, [rcx]
0x18000469b  mov     rax, [rax+10h]
0x18000469f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a4  nop
0x1800046a5  add     rsp, 28h
0x1800046a9  retn
```
