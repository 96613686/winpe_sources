# GetLinkTarget(ushort const *,ulong,ushort * *,ulong *)

- ea: `0x180004b80`
- end: `0x180004ef5`
- name: `?GetLinkTarget@@YAJPEBGKPEAPEAGPEAK@Z`
- size: `885`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016cbc`
- `0x1800202a0`
- `0x18002c910`
- `0x180032064`
- `0x18003d4c0`

## callees

- `0x180004b80`
- `0x180006430`
- `0x180006bf0`
- `0x180007398`
- `0x180008034`
- `0x180011654`
- `0x1800119c4`
- `0x180011c24`
- `0x180011de8`
- `0x180032a88`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x180004c92`
- `SHELL32!SHBindToParent` at `0x180004c92`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180004bdf`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180004bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ea8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004d04`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004d04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d5d`

## pseudocode

```c
__int64 __fastcall GetLinkTarget(const unsigned __int16 *a1, char a2, unsigned __int16 **a3, unsigned int *a4)
{
  HRESULT Instance; // ebx
  unsigned int v8; // r8d
  const struct _GUID *v9; // r9
  int RemotePath; // edi
  const ITEMIDLIST *v11; // rbx
  unsigned int v12; // r14d
  int v13; // esi
  HRESULT v14; // ebx
  struct IBindCtx *v15; // r8
  int v16; // esi
  HRESULT v17; // ebx
  int HasRoot; // eax
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *ppv; // [rsp+40h] [rbp-C0h] BYREF
  int v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  void *v26; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v27[264]; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  v26 = 0;
  ppidlLast = 0;
  Instance = SHCoCreateInstance(0, &CLSID_ShellLink, 0, &GUID_000214f9_0000_0000_c000_000000000046, (void **)&ppidlLast);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  Instance = _AndLoadFromFile((struct IUnknown *)ppidlLast, a1, v8, v9, &v26);
  (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&ppidlLast->mkid.cb + 16LL))(ppidlLast);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  pidl = 0;
  RemotePath = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST *))(*(_QWORD *)v26 + 32LL))(v26, &pidl);
  if ( RemotePath >= 0 )
  {
    v11 = pidl;
    RemotePath = 1;
    v12 = 0x20000000;
    v27[0] = 0;
    v13 = SHCoInitialize();
    ppv = 0;
    ppidlLast = 0;
    v14 = SHBindToParent(v11, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&ppv, &ppidlLast);
    if ( v14 >= 0 )
    {
      v14 = DisplayNameOfW(ppv, ppidlLast, 0x8000, v27, 260);
      if ( v14 >= 0 )
      {
        v20 = 0;
        _GetAttributesFromFolderAndIDList(
          (struct IShellFolder *)ppv,
          (const struct _ITEMIDLIST_RELATIVE *)ppidlLast,
          v15,
          0x20000000u,
          &v20);
        v12 = v20;
      }
      ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
    }
    if ( !v13 )
      CoUninitialize();
    if ( v14 >= 0 )
    {
      if ( (v12 & 0x20000000) == 0 || (a2 & 1) == 0 )
        goto LABEL_37;
      v16 = 0;
      v20 = 0;
      ppidlLast = 0;
      v24 = 0;
      *(_QWORD *)v23 = 0;
      ppv = 0;
      v17 = CoCreateInstance(
              &CLSID_KnownFolderManager,
              0,
              1u,
              &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
              (LPVOID *)&ppv);
      if ( v17 >= 0 )
      {
        if ( (int)MarshalToGIT(ppv, &IID_IKnownFolderManager, &v20) < 0 )
          v20 = 0;
        v17 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, int *))ppv->lpVtbl->QueryInterface)(
                ppv,
                &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
                v23);
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
        if ( v17 >= 0 )
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, __int64 *))(**(_QWORD **)v23 + 48LL))(
                  *(_QWORD *)v23,
                  &FOLDERID_NetHood,
                  &v24);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
          if ( v17 >= 0 )
          {
            v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCITEMIDLIST *))(*(_QWORD *)v24 + 48LL))(
                    v24,
                    0,
                    &ppidlLast);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            if ( v17 >= 0 )
            {
              v23[0] = 0;
              LODWORD(ppv) = 0;
              HasRoot = CscPath_HasRoot(a1, &ppidlLast->mkid.cb, (int *)&ppv, v23);
              v17 = HasRoot;
              if ( HasRoot >= 0 )
              {
                if ( !HasRoot && v23[0] )
                  v16 = 1;
                v17 = 0;
              }
              CoTaskMemFree((LPVOID)ppidlLast);
              ppidlLast = 0;
            }
          }
        }
      }
      if ( v20 )
        RevokeFromGIT(v20);
      RemotePath = v17;
      if ( v17 >= 0 )
      {
        if ( v16 )
        {
LABEL_37:
          if ( (a2 & 2) == 0 || (unsigned int)ShareIsCacheable(v27) )
            RemotePath = GetRemotePath(v27, a3);
        }
      }
    }
    CoTaskMemFree((LPVOID)pidl);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
  return (unsigned int)RemotePath;
}

```

## disassembly

```asm
0x180004b80  push    rbp
0x180004b82  push    rbx
0x180004b83  push    rsi
0x180004b84  push    r12
0x180004b86  push    r13
0x180004b88  push    r15
0x180004b8a  lea     rbp, [rsp-198h]
0x180004b92  sub     rsp, 298h
0x180004b99  mov     rax, cs:__security_cookie
0x180004ba0  xor     rax, rsp
0x180004ba3  mov     [rbp+1C0h+var_40], rax
0x180004baa  xor     esi, esi
0x180004bac  lea     rax, [rsp+2C0h+ppidlLast]
0x180004bb1  mov     [r8], rsi
0x180004bb4  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x180004bbb  mov     r13, r8
0x180004bbe  mov     [rsp+2C0h+var_260], rsi
0x180004bc3  mov     r12d, edx
0x180004bc6  mov     [rsp+2C0h+ppidlLast], rsi
0x180004bcb  mov     r15, rcx
0x180004bce  mov     [rsp+2C0h+ppv], rax; ppv
0x180004bd3  xor     r8d, r8d; pUnkOuter
0x180004bd6  lea     rdx, CLSID_ShellLink; pclsid
0x180004bdd  xor     ecx, ecx; pszCLSID
0x180004bdf  call    cs:__imp_SHCoCreateInstance
0x180004be5  mov     ebx, eax
0x180004be7  test    eax, eax
0x180004be9  js      loc_180004ED3
0x180004bef  mov     rcx, [rsp+2C0h+ppidlLast]; struct IUnknown *
0x180004bf4  lea     rax, [rsp+2C0h+var_260]
0x180004bf9  mov     rdx, r15; unsigned __int16 *
0x180004bfc  mov     [rsp+2C0h+ppv], rax; void **
0x180004c01  call    ?_AndLoadFromFile@@YAJPEAUIUnknown@@PEBGKAEBU_GUID@@PEAPEAX@Z; _AndLoadFromFile(IUnknown *,ushort const *,ulong,_GUID const &,void * *)
0x180004c06  mov     rcx, [rsp+2C0h+ppidlLast]
0x180004c0b  mov     ebx, eax
0x180004c0d  mov     rax, [rcx]
0x180004c10  mov     rax, [rax+10h]
0x180004c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c19  test    ebx, ebx
0x180004c1b  js      loc_180004ED3
0x180004c21  mov     rcx, [rsp+2C0h+var_260]
0x180004c26  lea     rdx, [rsp+2C0h+pidl]
0x180004c2b  mov     [rsp+2C0h+pidl], rsi
0x180004c30  mov     [rsp+2C0h+arg_8], rdi
0x180004c38  mov     rax, [rcx]
0x180004c3b  mov     rax, [rax+20h]
0x180004c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c44  mov     edi, eax
0x180004c46  test    eax, eax
0x180004c48  js      loc_180004EB6
0x180004c4e  mov     rbx, [rsp+2C0h+pidl]
0x180004c53  mov     edi, 1
0x180004c58  mov     [rsp+2C0h+var_30], r14
0x180004c60  mov     r14d, 20000000h
0x180004c66  mov     [rsp+2C0h+var_250], si
0x180004c6b  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180004c70  mov     esi, eax
0x180004c72  lea     r9, [rsp+2C0h+ppidlLast]; ppidlLast
0x180004c77  xor     eax, eax
0x180004c79  lea     r8, [rsp+2C0h+var_280]; ppv
0x180004c7e  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180004c85  mov     [rsp+2C0h+var_280], rax
0x180004c8a  mov     rcx, rbx; pidl
0x180004c8d  mov     [rsp+2C0h+ppidlLast], rax
0x180004c92  call    cs:__imp_SHBindToParent
0x180004c98  mov     ebx, eax
0x180004c9a  test    eax, eax
0x180004c9c  js      short loc_180004D00
0x180004c9e  mov     rdx, [rsp+2C0h+ppidlLast]
0x180004ca3  lea     r9, [rsp+2C0h+var_250]
0x180004ca8  mov     rcx, [rsp+2C0h+var_280]
0x180004cad  mov     r8d, 8000h
0x180004cb3  mov     dword ptr [rsp+2C0h+ppv], 104h
0x180004cbb  call    DisplayNameOfW
0x180004cc0  mov     ebx, eax
0x180004cc2  test    eax, eax
0x180004cc4  js      short loc_180004CEF
0x180004cc6  mov     rdx, [rsp+2C0h+ppidlLast]; struct _ITEMIDLIST_RELATIVE *
0x180004ccb  lea     rax, [rsp+2C0h+var_290]
0x180004cd0  mov     rcx, [rsp+2C0h+var_280]; struct IShellFolder *
0x180004cd5  mov     r9d, r14d; unsigned int
0x180004cd8  mov     [rsp+2C0h+ppv], rax; unsigned int *
0x180004cdd  mov     [rsp+2C0h+var_290], 0
0x180004ce5  call    ?_GetAttributesFromFolderAndIDList@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@KPEAK@Z; _GetAttributesFromFolderAndIDList(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong,ulong *)
0x180004cea  mov     r14d, [rsp+2C0h+var_290]
0x180004cef  mov     rcx, [rsp+2C0h+var_280]
0x180004cf4  mov     rax, [rcx]
0x180004cf7  mov     rax, [rax+10h]
0x180004cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d00  test    esi, esi
0x180004d02  jnz     short loc_180004D0A
0x180004d04  call    cs:__imp_CoUninitialize
0x180004d0a  test    ebx, ebx
0x180004d0c  js      loc_180004EA3
0x180004d12  bt      r14d, 1Dh
0x180004d17  jnb     loc_180004E80
0x180004d1d  test    dil, r12b
0x180004d20  jz      loc_180004E80
0x180004d26  xor     esi, esi
0x180004d28  lea     rax, [rsp+2C0h+var_280]
0x180004d2d  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180004d34  mov     [rsp+2C0h+var_290], esi
0x180004d38  mov     r8d, edi; dwClsContext
0x180004d3b  mov     [rsp+2C0h+ppidlLast], rsi
0x180004d40  xor     edx, edx; pUnkOuter
0x180004d42  mov     [rsp+2C0h+var_270], rsi
0x180004d47  lea     rcx, CLSID_KnownFolderManager; rclsid
0x180004d4e  mov     qword ptr [rsp+2C0h+var_278], rsi
0x180004d53  mov     [rsp+2C0h+var_280], rsi
0x180004d58  mov     [rsp+2C0h+ppv], rax; ppv
0x180004d5d  call    cs:__imp_CoCreateInstance
0x180004d63  mov     ebx, eax
0x180004d65  test    eax, eax
0x180004d67  js      loc_180004E69
0x180004d6d  mov     rcx, [rsp+2C0h+var_280]; struct IUnknown *
0x180004d72  lea     r8, [rsp+2C0h+var_290]; unsigned int *
0x180004d77  lea     rdx, IID_IKnownFolderManager; struct _GUID *
0x180004d7e  call    ?MarshalToGIT@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; MarshalToGIT(IUnknown *,_GUID const &,ulong *)
0x180004d83  test    eax, eax
0x180004d85  jns     short loc_180004D8B
0x180004d87  mov     [rsp+2C0h+var_290], esi
0x180004d8b  mov     rcx, [rsp+2C0h+var_280]
0x180004d90  lea     r8, [rsp+2C0h+var_278]
0x180004d95  lea     rdx, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018
0x180004d9c  mov     rax, [rcx]
0x180004d9f  mov     rax, [rax]
0x180004da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da7  mov     rcx, [rsp+2C0h+var_280]
0x180004dac  mov     ebx, eax
0x180004dae  mov     rax, [rcx]
0x180004db1  mov     rax, [rax+10h]
0x180004db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dba  test    ebx, ebx
0x180004dbc  js      loc_180004E69
0x180004dc2  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x180004dc7  lea     r8, [rsp+2C0h+var_270]
0x180004dcc  lea     rdx, FOLDERID_NetHood
0x180004dd3  mov     rax, [rcx]
0x180004dd6  mov     rax, [rax+30h]
0x180004dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ddf  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x180004de4  mov     ebx, eax
0x180004de6  mov     rax, [rcx]
0x180004de9  mov     rax, [rax+10h]
0x180004ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df2  test    ebx, ebx
0x180004df4  js      short loc_180004E69
0x180004df6  mov     rcx, [rsp+2C0h+var_270]
0x180004dfb  lea     r8, [rsp+2C0h+ppidlLast]
0x180004e00  xor     edx, edx
0x180004e02  mov     rax, [rcx]
0x180004e05  mov     rax, [rax+30h]
0x180004e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e0e  mov     rcx, [rsp+2C0h+var_270]
0x180004e13  mov     ebx, eax
0x180004e15  mov     rax, [rcx]
0x180004e18  mov     rax, [rax+10h]
0x180004e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e21  test    ebx, ebx
0x180004e23  js      short loc_180004E69
0x180004e25  mov     rdx, [rsp+2C0h+ppidlLast]; unsigned __int16 *
0x180004e2a  lea     r9, [rsp+2C0h+var_278]; int *
0x180004e2f  lea     r8, [rsp+2C0h+var_280]; int *
0x180004e34  mov     [rsp+2C0h+var_278], esi
0x180004e38  mov     rcx, r15; unsigned __int16 *
0x180004e3b  mov     dword ptr [rsp+2C0h+var_280], esi
0x180004e3f  call    ?CscPath_HasRoot@@YAJPEBG0PEAH1@Z; CscPath_HasRoot(ushort const *,ushort const *,int *,int *)
0x180004e44  mov     ebx, eax
0x180004e46  test    eax, eax
0x180004e48  js      short loc_180004E55
0x180004e4a  jnz     short loc_180004E53
0x180004e4c  cmp     [rsp+2C0h+var_278], esi
0x180004e50  cmovnz  esi, edi
0x180004e53  xor     ebx, ebx
0x180004e55  mov     rcx, [rsp+2C0h+ppidlLast]; pv
0x180004e5a  call    cs:__imp_CoTaskMemFree
0x180004e60  mov     [rsp+2C0h+ppidlLast], 0
0x180004e69  mov     ecx, [rsp+2C0h+var_290]; unsigned int
0x180004e6d  test    ecx, ecx
0x180004e6f  jz      short loc_180004E76
0x180004e71  call    ?RevokeFromGIT@@YAXK@Z; RevokeFromGIT(ulong)
0x180004e76  mov     edi, ebx
0x180004e78  test    ebx, ebx
0x180004e7a  js      short loc_180004EA3
0x180004e7c  test    esi, esi
0x180004e7e  jz      short loc_180004EA3
0x180004e80  test    r12b, 2
0x180004e84  jz      short loc_180004E94
0x180004e86  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180004e8b  call    ?ShareIsCacheable@@YAHPEBG@Z; ShareIsCacheable(ushort const *)
0x180004e90  test    eax, eax
0x180004e92  jz      short loc_180004EA3
0x180004e94  mov     rdx, r13; unsigned __int16 **
0x180004e97  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180004e9c  call    ?GetRemotePath@@YAJPEBGPEAPEAG@Z; GetRemotePath(ushort const *,ushort * *)
0x180004ea1  mov     edi, eax
0x180004ea3  mov     rcx, [rsp+2C0h+pidl]; pv
0x180004ea8  call    cs:__imp_CoTaskMemFree
0x180004eae  mov     r14, [rsp+2C0h+var_30]
0x180004eb6  mov     rcx, [rsp+2C0h+var_260]
0x180004ebb  mov     rax, [rcx]
0x180004ebe  mov     rax, [rax+10h]
0x180004ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec7  mov     eax, edi
0x180004ec9  mov     rdi, [rsp+2C0h+arg_8]
0x180004ed1  jmp     short loc_180004ED5
0x180004ed3  mov     eax, ebx
0x180004ed5  mov     rcx, [rbp+1C0h+var_40]
0x180004edc  xor     rcx, rsp; StackCookie
0x180004edf  call    __security_check_cookie
0x180004ee4  add     rsp, 298h
0x180004eeb  pop     r15
0x180004eed  pop     r13
0x180004eef  pop     r12
0x180004ef1  pop     rsi
0x180004ef2  pop     rbx
0x180004ef3  pop     rbp
0x180004ef4  retn
```
