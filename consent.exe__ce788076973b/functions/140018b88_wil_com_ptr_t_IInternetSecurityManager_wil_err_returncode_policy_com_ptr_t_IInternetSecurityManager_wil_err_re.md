# wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(void)

- ea: `0x140018b88`
- end: `0x140018ba6`
- name: `??1?$com_ptr_t@UIInternetSecurityManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018c68`
- `0x14001e7e6`

## callees

- `0x140018b88`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(
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
0x140018b88  sub     rsp, 28h
0x140018b8c  mov     rcx, [rcx]
0x140018b8f  test    rcx, rcx
0x140018b92  jz      short loc_140018BA1
0x140018b94  mov     rax, [rcx]
0x140018b97  mov     rax, [rax+10h]
0x140018b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ba0  nop
0x140018ba1  add     rsp, 28h
0x140018ba5  retn
```
