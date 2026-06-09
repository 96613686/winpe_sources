# CINDFHelperClassImpl::GetRepairs(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *)

- ea: `0x180007920`
- end: `0x180007948`
- name: `?GetRepairs@CINDFHelperClassImpl@@UEAAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAK@Z`
- size: `40`
- prototype: `__int64 __fastcall(CINDFHelperClassImpl *__hidden this, struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180007920`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CINDFHelperClassImpl::GetRepairs(
        CINDFHelperClassImpl *this,
        struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **a2,
        unsigned int *a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **, unsigned int *))(**((_QWORD **)this + 8) + 96LL))(
           *((_QWORD *)this + 8),
           a2,
           a3);
}

```

## disassembly

```asm
0x180007920  sub     rsp, 28h
0x180007924  mov     rcx, [rcx+40h]
0x180007928  mov     rax, [rcx]
0x18000792b  mov     rax, [rax+60h]
0x18000792f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007934  jmp     short loc_180007942
0x180007936  mov     eax, 8007000Eh
0x18000793b  jmp     short loc_180007942
0x18000793d  mov     eax, 80004005h
0x180007942  add     rsp, 28h
0x180007946  retn
```
