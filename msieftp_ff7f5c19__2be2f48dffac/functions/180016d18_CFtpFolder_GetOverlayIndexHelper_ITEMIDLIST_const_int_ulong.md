# CFtpFolder::GetOverlayIndexHelper(_ITEMIDLIST const *,int *,ulong)

- ea: `0x180016d18`
- end: `0x180016dca`
- name: `?GetOverlayIndexHelper@CFtpFolder@@QEAAJPEFBU_ITEMIDLIST@@PEAHK@Z`
- size: `178`
- prototype: `int(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016ce0`
- `0x180016d00`

## callees

- `0x180016d18`
- `0x18001c4fc`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d76`

## pseudocode

```c
__int64 __fastcall CFtpFolder::GetOverlayIndexHelper(CFtpFolder *this, const struct _ITEMIDLIST *a2, int *a3, int a4)
{
  unsigned int Instance; // edi
  LPVOID *ppv; // rbx
  LPVOID v10; // r14
  unsigned int (__fastcall *v11)(LPVOID, const WCHAR *, _QWORD, int *, int, int); // rbx
  unsigned int Attributes; // eax

  *a3 = 0;
  Instance = -2147467259;
  if ( a2 && (FtpPidl_GetAttributes(a2) & 0x400) != 0 )
  {
    ppv = (LPVOID *)((char *)this + 152);
    if ( !*ppv )
      Instance = CoCreateInstance(&CLSID_CFSIconOverlayManager, 0, 1u, &IID_IShellIconOverlayManager, ppv);
    v10 = *ppv;
    if ( *ppv )
    {
      v11 = *(unsigned int (__fastcall **)(LPVOID, const WCHAR *, _QWORD, int *, int, int))(*(_QWORD *)v10 + 32LL);
      Attributes = FtpPidl_GetAttributes(a2);
      return v11(v10, &lParam, Attributes, a3, a4, 1);
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x180016d18  push    rbx
0x180016d1a  push    rbp
0x180016d1b  push    rsi
0x180016d1c  push    rdi
0x180016d1d  push    r14
0x180016d1f  push    r15
0x180016d21  sub     rsp, 48h
0x180016d25  mov     dword ptr [r8], 0
0x180016d2c  mov     ebp, r9d
0x180016d2f  mov     r15, r8
0x180016d32  mov     rsi, rdx
0x180016d35  mov     rbx, rcx
0x180016d38  mov     edi, 80004005h
0x180016d3d  test    rdx, rdx
0x180016d40  jz      short loc_180016DBB
0x180016d42  mov     rcx, rdx; struct _ITEMIDLIST *
0x180016d45  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x180016d4a  bt      eax, 0Ah
0x180016d4e  jnb     short loc_180016DBB
0x180016d50  add     rbx, 98h
0x180016d57  cmp     qword ptr [rbx], 0
0x180016d5b  jnz     short loc_180016D7E
0x180016d5d  xor     edx, edx; pUnkOuter
0x180016d5f  mov     [rsp+78h+ppv], rbx; ppv
0x180016d64  lea     r9, IID_IShellIconOverlayManager; riid
0x180016d6b  lea     rcx, CLSID_CFSIconOverlayManager; rclsid
0x180016d72  lea     r8d, [rdx+1]; dwClsContext
0x180016d76  call    cs:__imp_CoCreateInstance
0x180016d7c  mov     edi, eax
0x180016d7e  mov     r14, [rbx]
0x180016d81  test    r14, r14
0x180016d84  jz      short loc_180016DBB
0x180016d86  mov     rax, [r14]
0x180016d89  mov     rcx, rsi; struct _ITEMIDLIST *
0x180016d8c  mov     rbx, [rax+20h]
0x180016d90  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x180016d95  mov     r8d, eax
0x180016d98  mov     [rsp+78h+var_50], 1
0x180016da0  mov     rax, rbx
0x180016da3  mov     dword ptr [rsp+78h+ppv], ebp
0x180016da7  mov     r9, r15
0x180016daa  lea     rdx, lParam
0x180016db1  mov     rcx, r14
0x180016db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db9  mov     edi, eax
0x180016dbb  mov     eax, edi
0x180016dbd  add     rsp, 48h
0x180016dc1  pop     r15
0x180016dc3  pop     r14
0x180016dc5  pop     rdi
0x180016dc6  pop     rsi
0x180016dc7  pop     rbp
0x180016dc8  pop     rbx
0x180016dc9  retn
```
