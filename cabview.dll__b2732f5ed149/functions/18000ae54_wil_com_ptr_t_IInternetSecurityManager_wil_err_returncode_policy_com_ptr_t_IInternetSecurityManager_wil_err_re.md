# wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(void)

- ea: `0x18000ae54`
- end: `0x18000ae71`
- name: `??1?$com_ptr_t@UIInternetSecurityManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ca90`

## callees

- `0x18000ae54`
- `0x180013010`

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
0x18000ae54  sub     rsp, 28h
0x18000ae58  mov     rcx, [rcx]
0x18000ae5b  test    rcx, rcx
0x18000ae5e  jz      short loc_18000AE6C
0x18000ae60  mov     rax, [rcx]
0x18000ae63  mov     rax, [rax+10h]
0x18000ae67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae6c  add     rsp, 28h
0x18000ae70  retn
```
