# CINDFHelperClassImpl::GetRepairsForRootCause(_GUID,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *)

- ea: `0x180007950`
- end: `0x180007986`
- name: `?GetRepairsForRootCause@CINDFHelperClassImpl@@UEAAJU_GUID@@PEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAK@Z`
- size: `54`
- prototype: `__int64 __fastcall(CINDFHelperClassImpl *__hidden this, struct _GUID *__struct_ptr, struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180007950`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CINDFHelperClassImpl::GetRepairsForRootCause(
        CINDFHelperClassImpl *this,
        struct _GUID *a2,
        struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **a3,
        unsigned int *a4)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *((_QWORD *)this + 8);
  try
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 112LL))(v4);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( exception )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007950  sub     rsp, 48h
0x180007954  mov     rcx, [rcx+40h]
0x180007958  movups  xmm0, xmmword ptr [rdx]
0x18000795b  movdqu  [rsp+48h+var_18], xmm0
0x180007961  mov     rax, [rcx]
0x180007964  lea     rdx, [rsp+48h+var_18]
0x180007969  mov     rax, [rax+70h]
0x18000796d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007972  jmp     short loc_180007980
0x180007974  mov     eax, 8007000Eh
0x180007979  jmp     short loc_180007980
0x18000797b  mov     eax, 80004005h
0x180007980  add     rsp, 48h
0x180007984  retn
```
