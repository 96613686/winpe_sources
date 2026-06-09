# CTravelEntry::_UpdateFromTLClient(IUnknown *,IStream * *,int)

- ea: `0x1806f3a8c`
- end: `0x1806f3e70`
- name: `?_UpdateFromTLClient@CTravelEntry@@IEAAJPEAUIUnknown@@PEAPEAUIStream@@H@Z`
- size: `996`
- prototype: `__int64 __fastcall(CTravelEntry *__hidden this, struct IUnknown *, struct IStream **, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x181044ce0`

## callees

- `0x1801af6e0`
- `0x1801b0510`
- `0x1801bf528`
- `0x18028ecdc`
- `0x1802cca88`
- `0x1802e5024`
- `0x180552000`
- `0x1805523c8`
- `0x1805ec7d8`
- `0x1806a4e8c`
- `0x1806f3a8c`
- `0x1810643ac`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1806f3dff`
- `KERNEL32!GlobalFree` at `0x1806f3dff`
- `KERNEL32!LocalFree` at `0x1806f3d1e`
- `KERNEL32!LocalFree` at `0x1806f3d1e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1806f3d32`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1806f3d32`
- `iertutil!CreateUri` at `0x1806f3d09`
- `iertutil!CreateUri` at `0x1806f3d09`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1806f3df0`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1806f3df0`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1806f3bc9`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1806f3bc9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f3d89`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f3d94`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f3d9f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f3d89`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f3d94`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f3d9f`
- `SHELL32!__imp_ILFree` at `0x1806f3d7e`
- `SHELL32!__imp_ILFree` at `0x1806f3d7e`

## string_xrefs

- `0x1806f3d61`: `CTravelEntry::_UpdateFromTLClient - TravelEntry=0x%08lX ptlc=0x%08lX _bid=0x%08lX UrlWithFragment=%S Title=%S ppStream=0x%08lX`

## pseudocode

```c
__int64 __fastcall CTravelEntry::_UpdateFromTLClient(
        CTravelEntry *this,
        struct IUnknown *a2,
        struct IStream **a3,
        int a4)
{
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  HRESULT StreamOnHGlobal; // ebx
  _OWORD *v10; // rax
  _OWORD *v11; // rax
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  int IsSearchUrl; // eax
  __int64 v15; // r8
  char *v16; // rcx
  __int64 v17; // rax
  const unsigned __int16 *v18; // r8
  IUri **v19; // rax
  void *v20; // rcx
  const wchar_t *v21; // rcx
  LPSTREAM v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v26; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B8h] BYREF
  HGLOBAL phglobal; // [rsp+58h] [rbp-B0h] BYREF
  HGLOBAL phglobal_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  LPITEMIDLIST pidl_8[2]; // [rsp+70h] [rbp-98h]
  WCHAR *v31; // [rsp+80h] [rbp-88h]
  __int128 v32; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v33[16]; // [rsp+98h] [rbp-70h] BYREF
  int v34; // [rsp+A8h] [rbp-60h]
  wchar_t pwzURI[2088]; // [rsp+E8h] [rbp-20h] BYREF

  v31 = 0;
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  *(_OWORD *)phglobal_8 = 0;
  v27 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)pidl_8 = 0;
  pwzURI[0] = 0;
  v32 = 0;
  StreamOnHGlobal = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
                      a2,
                      &GUID_241c033e_e659_43da_aa4d_4086dbc4758d,
                      &v26);
  if ( StreamOnHGlobal )
    goto LABEL_37;
  if ( a4 )
  {
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                        a2,
                        &GUID_0000010c_0000_0000_c000_000000000046,
                        &v27);
    if ( StreamOnHGlobal )
      goto LABEL_37;
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v27 + 24LL))(v27, &v32);
    if ( StreamOnHGlobal )
      goto LABEL_37;
    v10 = (_OWORD *)*((_QWORD *)this + 5);
    if ( v10 )
    {
      *v10 = v32;
    }
    else
    {
      v11 = (_OWORD *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, (unsigned int)(StreamOnHGlobal + 16));
      if ( !v11 )
      {
        *((_QWORD *)this + 5) = 0;
        StreamOnHGlobal = -2147024882;
        goto LABEL_37;
      }
      *v11 = v32;
      *((_QWORD *)this + 5) = v11;
    }
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 0, a3);
  if ( StreamOnHGlobal )
    goto LABEL_37;
  StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, HGLOBAL *))(*(_QWORD *)v26 + 32LL))(
                      v26,
                      *a3,
                      phglobal_8);
  if ( StreamOnHGlobal )
    goto LABEL_37;
  *((_DWORD *)this + 18) = phglobal_8[0];
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((char *)this + 56);
  if ( phglobal_8[1] )
  {
    IEGetNameAndFlagsEx((struct _ITEMIDLIST_RELATIVE *)phglobal_8[1]);
  }
  else
  {
    if ( !pidl_8[0] )
    {
LABEL_36:
      StreamOnHGlobal = -2146697202;
      goto LABEL_37;
    }
    StringCchCopyW(pwzURI, 0x824u, &pidl_8[0]->mkid.cb);
  }
  if ( (unsigned int)IsSpecialUrl(pwzURI)
    && !UrlUtils::IsAboutTabs((UrlUtils *)pwzURI, v12)
    && !UrlUtils::IsAboutNewsFeed((UrlUtils *)pwzURI, v13) )
  {
    goto LABEL_36;
  }
  IsSearchUrl = CTravelEntry::_IsSearchUrl(pwzURI);
  v15 = *((_QWORD *)this + 1);
  v16 = (char *)this + 8;
  if ( IsSearchUrl )
    (*(void (__fastcall **)(char *, __int64))(v15 + 24))(v16, 4);
  else
    (*(void (__fastcall **)(char *, __int64))(v15 + 32))(v16, 4);
  if ( !pidl_8[1] || !pidl_8[1]->mkid.cb )
    goto LABEL_29;
  v17 = -1;
  do
    ++v17;
  while ( pwzURI[v17] );
  v18 = L"%s";
  if ( pidl_8[1]->mkid.cb != 35 )
    v18 = L"#%s";
  StreamOnHGlobal = StringCchPrintfW(&pwzURI[(unsigned int)v17], 2084LL - (unsigned int)v17, v18);
  if ( StreamOnHGlobal >= 0 )
  {
LABEL_29:
    v19 = (IUri **)TSmartPointer<ID3D11Device>::operator&((char *)this + 56);
    StreamOnHGlobal = CreateUri(pwzURI, 0x3002B84u, 0, v19);
    if ( StreamOnHGlobal >= 0 )
    {
      v20 = (void *)*((_QWORD *)this + 11);
      if ( v20 )
      {
        LocalFree(v20);
        *((_QWORD *)this + 11) = 0;
      }
      if ( v31 )
      {
        v21 = StrDupW(v31);
        *((_QWORD *)this + 11) = v21;
      }
      else
      {
        v21 = 0;
      }
      Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
        "CTravelEntry::_UpdateFromTLClient - TravelEntry=0x%08lX ptlc=0x%08lX _bid=0x%08lX UrlWithFragment=%S Title=%S ppStream=0x%08lX",
        (_DWORD)this,
        v26,
        *((_DWORD *)this + 18),
        pwzURI,
        v21,
        (unsigned int)*a3);
    }
  }
LABEL_37:
  ILFree((LPITEMIDLIST)phglobal_8[1]);
  CoTaskMemFree(pidl_8[0]);
  CoTaskMemFree(pidl_8[1]);
  CoTaskMemFree(v31);
  v22 = *a3;
  if ( *a3 )
  {
    memset_0(v33, 0, 0x50u);
    phglobal = 0;
    if ( StreamOnHGlobal < 0
      || (*(int (__fastcall **)(LPSTREAM, _BYTE *, __int64))(*(_QWORD *)v22 + 96LL))(v22, v33, 1) >= 0 && !v34 )
    {
      if ( GetHGlobalFromStream(*a3, &phglobal) >= 0 )
        GlobalFree(phglobal);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
      *a3 = 0;
    }
  }
  v23 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1806f3a8c  mov     rax, rsp
0x1806f3a8f  mov     [rax+20h], r9d
0x1806f3a93  mov     [rax+18h], r8
0x1806f3a97  mov     [rax+10h], rdx
0x1806f3a9b  mov     [rax+8], rcx
0x1806f3a9f  push    rbp
0x1806f3aa0  push    rbx
0x1806f3aa1  push    rsi
0x1806f3aa2  push    rdi
0x1806f3aa3  push    r12
0x1806f3aa5  push    r14
0x1806f3aa7  push    r15
0x1806f3aa9  lea     rbp, [rax-1078h]
0x1806f3ab0  mov     eax, 1140h
0x1806f3ab5  call    _alloca_probe
0x1806f3aba  sub     rsp, rax
0x1806f3abd  mov     rax, cs:__security_cookie
0x1806f3ac4  xor     rax, rsp
0x1806f3ac7  mov     [rbp+1070h+var_40], rax
0x1806f3ace  mov     r14, [rbp+1070h+arg_8]
0x1806f3ad5  lea     r8, [rsp+1170h+var_1130]
0x1806f3ada  mov     rdi, [rbp+1070h+arg_0]
0x1806f3ae1  lea     rdx, _GUID_241c033e_e659_43da_aa4d_4086dbc4758d
0x1806f3ae8  mov     rsi, [rbp+1070h+ppstm]
0x1806f3aef  xor     eax, eax
0x1806f3af1  xorps   xmm0, xmm0
0x1806f3af4  mov     [rsp+1170h+var_10F8], rax
0x1806f3af9  mov     rax, [r14]
0x1806f3afc  xor     r12d, r12d
0x1806f3aff  mov     rcx, r14
0x1806f3b02  mov     [rsp+1170h+var_1130], r12
0x1806f3b07  movups  xmmword ptr [rsp+1170h+phglobal+8], xmm0
0x1806f3b0c  mov     [rsp+1170h+var_1128], r12
0x1806f3b11  mov     rax, [rax]
0x1806f3b14  movups  xmmword ptr [rsp+1170h+pidl+8], xmm0
0x1806f3b19  mov     [rbp+1070h+pwzURI], r12w
0x1806f3b1e  movups  [rbp+1070h+var_10F0], xmm0
0x1806f3b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3b27  mov     ebx, eax
0x1806f3b29  test    eax, eax
0x1806f3b2b  jnz     loc_1806F3D79
0x1806f3b31  cmp     [rbp+1070h+arg_18], r12d
0x1806f3b38  jz      loc_1806F3BC2
0x1806f3b3e  mov     rax, [r14]
0x1806f3b41  lea     r8, [rsp+1170h+var_1128]
0x1806f3b46  lea     rdx, _GUID_0000010c_0000_0000_c000_000000000046
0x1806f3b4d  mov     rcx, r14
0x1806f3b50  mov     rax, [rax]
0x1806f3b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3b58  mov     ebx, eax
0x1806f3b5a  test    eax, eax
0x1806f3b5c  jnz     loc_1806F3D79
0x1806f3b62  mov     rcx, [rsp+1170h+var_1128]
0x1806f3b67  lea     rdx, [rbp+1070h+var_10F0]
0x1806f3b6b  mov     rax, [rcx]
0x1806f3b6e  mov     rax, [rax+18h]
0x1806f3b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3b77  mov     ebx, eax
0x1806f3b79  test    eax, eax
0x1806f3b7b  jnz     loc_1806F3D79
0x1806f3b81  mov     rax, [rdi+28h]
0x1806f3b85  test    rax, rax
0x1806f3b88  jnz     short loc_1806F3BBA
0x1806f3b8a  mov     rcx, cs:g_hProcessHeap
0x1806f3b91  lea     edx, [rbx+10h]
0x1806f3b94  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1806f3b99  test    rax, rax
0x1806f3b9c  jz      short loc_1806F3BAC
0x1806f3b9e  movups  xmm0, [rbp+1070h+var_10F0]
0x1806f3ba2  movdqu  xmmword ptr [rax], xmm0
0x1806f3ba6  mov     [rdi+28h], rax
0x1806f3baa  jmp     short loc_1806F3BC2
0x1806f3bac  mov     [rdi+28h], r12
0x1806f3bb0  mov     ebx, 8007000Eh
0x1806f3bb5  jmp     loc_1806F3D79
0x1806f3bba  movups  xmm0, [rbp+1070h+var_10F0]
0x1806f3bbe  movdqu  xmmword ptr [rax], xmm0
0x1806f3bc2  mov     r8, rsi; ppstm
0x1806f3bc5  xor     edx, edx; fDeleteOnRelease
0x1806f3bc7  xor     ecx, ecx; hGlobal
0x1806f3bc9  call    cs:__imp_CreateStreamOnHGlobal
0x1806f3bcf  mov     ebx, eax
0x1806f3bd1  test    eax, eax
0x1806f3bd3  jnz     loc_1806F3D79
0x1806f3bd9  mov     rcx, [rsp+1170h+var_1130]
0x1806f3bde  lea     r8, [rsp+1170h+phglobal+8]
0x1806f3be3  mov     rdx, [rsi]
0x1806f3be6  mov     rax, [rcx]
0x1806f3be9  mov     rax, [rax+20h]
0x1806f3bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3bf2  mov     ebx, eax
0x1806f3bf4  test    eax, eax
0x1806f3bf6  jnz     loc_1806F3D79
0x1806f3bfc  mov     eax, dword ptr [rsp+1170h+phglobal+8]
0x1806f3c00  lea     rcx, [rdi+38h]; void *
0x1806f3c04  mov     [rdi+48h], eax
0x1806f3c07  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1806f3c0c  mov     rcx, [rsp+1170h+pidl]; struct _ITEMIDLIST_RELATIVE *
0x1806f3c11  mov     r14d, 824h
0x1806f3c17  test    rcx, rcx
0x1806f3c1a  jz      short loc_1806F3C27
0x1806f3c1c  lea     r9, [rbp+1070h+pwzURI]
0x1806f3c20  call    IEGetNameAndFlagsEx
0x1806f3c25  jmp     short loc_1806F3C41
0x1806f3c27  mov     r8, [rsp+1170h+pidl+8]; unsigned __int16 *
0x1806f3c2c  test    r8, r8
0x1806f3c2f  jz      loc_1806F3D74
0x1806f3c35  mov     rdx, r14; unsigned __int64
0x1806f3c38  lea     rcx, [rbp+1070h+pwzURI]; unsigned __int16 *
0x1806f3c3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1806f3c41  lea     rcx, [rbp+1070h+pwzURI]
0x1806f3c45  call    IsSpecialUrl
0x1806f3c4a  test    eax, eax
0x1806f3c4c  jz      short loc_1806F3C6C
0x1806f3c4e  lea     rcx, [rbp+1070h+pwzURI]; this
0x1806f3c52  call    ?IsAboutTabs@UrlUtils@@YA_NPEBG@Z; UrlUtils::IsAboutTabs(ushort const *)
0x1806f3c57  test    al, al
0x1806f3c59  jnz     short loc_1806F3C6C
0x1806f3c5b  lea     rcx, [rbp+1070h+pwzURI]; this
0x1806f3c5f  call    ?IsAboutNewsFeed@UrlUtils@@YA_NPEBG@Z; UrlUtils::IsAboutNewsFeed(ushort const *)
0x1806f3c64  test    al, al
0x1806f3c66  jz      loc_1806F3D74
0x1806f3c6c  lea     rcx, [rbp+1070h+pwzURI]; unsigned __int16 *
0x1806f3c70  lea     rbx, [rdi+8]
0x1806f3c74  call    ?_IsSearchUrl@CTravelEntry@@KAHPEBG@Z; CTravelEntry::_IsSearchUrl(ushort const *)
0x1806f3c79  mov     r8, [rbx]
0x1806f3c7c  mov     edx, 4
0x1806f3c81  mov     rcx, rbx
0x1806f3c84  test    eax, eax
0x1806f3c86  jz      short loc_1806F3C8E
0x1806f3c88  mov     rax, [r8+18h]
0x1806f3c8c  jmp     short loc_1806F3C92
0x1806f3c8e  mov     rax, [r8+20h]
0x1806f3c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3c97  mov     r9, [rsp+1170h+pv]
0x1806f3c9c  test    r9, r9
0x1806f3c9f  jz      short loc_1806F3CF1
0x1806f3ca1  cmp     [r9], r12w
0x1806f3ca5  jz      short loc_1806F3CF1
0x1806f3ca7  lea     rcx, [rbp+1070h+pwzURI]
0x1806f3cab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1806f3caf  inc     rax
0x1806f3cb2  cmp     [rcx+rax*2], r12w
0x1806f3cb7  jnz     short loc_1806F3CAF
0x1806f3cb9  mov     eax, eax
0x1806f3cbb  lea     rcx, [rbp+1070h+pwzURI]
0x1806f3cbf  sub     r14, rax
0x1806f3cc2  lea     r8, aS_11; "%s"
0x1806f3cc9  mov     rdx, r14; unsigned __int64
0x1806f3ccc  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1806f3cd0  mov     eax, 23h ; '#'
0x1806f3cd5  cmp     ax, [r9]
0x1806f3cd9  jz      short loc_1806F3CE2
0x1806f3cdb  lea     r8, aS_14; "#%s"
0x1806f3ce2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1806f3ce7  mov     ebx, eax
0x1806f3ce9  test    eax, eax
0x1806f3ceb  js      loc_1806F3D79
0x1806f3cf1  lea     rcx, [rdi+38h]
0x1806f3cf5  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1806f3cfa  mov     r9, rax; ppURI
0x1806f3cfd  lea     rcx, [rbp+1070h+pwzURI]; pwzURI
0x1806f3d01  xor     r8d, r8d; dwReserved
0x1806f3d04  mov     edx, 3002B84h; dwFlags
0x1806f3d09  call    cs:__imp_CreateUri
0x1806f3d0f  mov     ebx, eax
0x1806f3d11  test    eax, eax
0x1806f3d13  js      short loc_1806F3D79
0x1806f3d15  mov     rcx, [rdi+58h]; hMem
0x1806f3d19  test    rcx, rcx
0x1806f3d1c  jz      short loc_1806F3D28
0x1806f3d1e  call    cs:__imp_LocalFree
0x1806f3d24  mov     [rdi+58h], r12
0x1806f3d28  mov     rcx, [rsp+1170h+var_10F8]; pszSrch
0x1806f3d2d  test    rcx, rcx
0x1806f3d30  jz      short loc_1806F3D41
0x1806f3d32  call    cs:__imp_StrDupW
0x1806f3d38  mov     rcx, rax
0x1806f3d3b  mov     [rdi+58h], rax
0x1806f3d3f  jmp     short loc_1806F3D44
0x1806f3d41  mov     rcx, r12
0x1806f3d44  mov     rax, [rsi]
0x1806f3d47  mov     rdx, rdi
0x1806f3d4a  mov     r8, [rsp+1170h+var_1130]
0x1806f3d4f  mov     r9d, [rdi+48h]
0x1806f3d53  mov     [rsp+30h], rax
0x1806f3d58  lea     rax, [rbp+1070h+pwzURI]
0x1806f3d5c  mov     [rsp+1170h+var_1148], rcx
0x1806f3d61  lea     rcx, aCtravelentryUp; "CTravelEntry::_UpdateFromTLClient - Tra"...
0x1806f3d68  mov     [rsp+1170h+var_1150], rax
0x1806f3d6d  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(...)
0x1806f3d72  jmp     short loc_1806F3D79
0x1806f3d74  mov     ebx, 800C000Eh
0x1806f3d79  mov     rcx, [rsp+1170h+pidl]; pidl
0x1806f3d7e  call    cs:__imp_ILFree
0x1806f3d84  mov     rcx, [rsp+1170h+pidl+8]; pv
0x1806f3d89  call    cs:__imp_CoTaskMemFree
0x1806f3d8f  mov     rcx, [rsp+1170h+pv]; pv
0x1806f3d94  call    cs:__imp_CoTaskMemFree
0x1806f3d9a  mov     rcx, [rsp+1170h+var_10F8]; pv
0x1806f3d9f  call    cs:__imp_CoTaskMemFree
0x1806f3da5  mov     rdi, [rsi]
0x1806f3da8  test    rdi, rdi
0x1806f3dab  jz      short loc_1806F3E17
0x1806f3dad  xor     edx, edx; Val
0x1806f3daf  lea     rcx, [rbp+1070h+var_10E0]; void *
0x1806f3db3  lea     r8d, [rdx+50h]; Size
0x1806f3db7  call    memset_0
0x1806f3dbc  mov     [rsp+1170h+phglobal], r12
0x1806f3dc1  test    ebx, ebx
0x1806f3dc3  js      short loc_1806F3DE8
0x1806f3dc5  mov     rax, [rdi]
0x1806f3dc8  lea     rdx, [rbp+1070h+var_10E0]
0x1806f3dcc  mov     r8d, 1
0x1806f3dd2  mov     rcx, rdi
0x1806f3dd5  mov     rax, [rax+60h]
0x1806f3dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3dde  test    eax, eax
0x1806f3de0  js      short loc_1806F3E17
0x1806f3de2  cmp     [rbp+1070h+var_10D0], r12d
0x1806f3de6  jnz     short loc_1806F3E17
0x1806f3de8  mov     rcx, [rsi]; pstm
0x1806f3deb  lea     rdx, [rsp+1170h+phglobal]; phglobal
0x1806f3df0  call    cs:__imp_GetHGlobalFromStream
0x1806f3df6  test    eax, eax
0x1806f3df8  js      short loc_1806F3E05
0x1806f3dfa  mov     rcx, [rsp+1170h+phglobal]; hMem
0x1806f3dff  call    cs:__imp_GlobalFree
0x1806f3e05  mov     rcx, [rsi]
0x1806f3e08  mov     rax, [rcx]
0x1806f3e0b  mov     rax, [rax+10h]
0x1806f3e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3e14  mov     [rsi], r12
0x1806f3e17  mov     rcx, [rsp+1170h+var_1130]
0x1806f3e1c  test    rcx, rcx
0x1806f3e1f  jz      short loc_1806F3E32
0x1806f3e21  mov     [rsp+1170h+var_1130], r12
0x1806f3e26  mov     rax, [rcx]
0x1806f3e29  mov     rax, [rax+10h]
0x1806f3e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3e32  mov     rcx, [rsp+1170h+var_1128]
0x1806f3e37  test    rcx, rcx
0x1806f3e3a  jz      short loc_1806F3E4D
0x1806f3e3c  mov     [rsp+1170h+var_1128], r12
0x1806f3e41  mov     rax, [rcx]
0x1806f3e44  mov     rax, [rax+10h]
0x1806f3e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f3e4d  mov     eax, ebx
0x1806f3e4f  mov     rcx, [rbp+1070h+var_40]
0x1806f3e56  xor     rcx, rsp; StackCookie
0x1806f3e59  call    __security_check_cookie
0x1806f3e5e  add     rsp, 1140h
0x1806f3e65  pop     r15
0x1806f3e67  pop     r14
0x1806f3e69  pop     r12
0x1806f3e6b  pop     rdi
0x1806f3e6c  pop     rsi
0x1806f3e6d  pop     rbx
0x1806f3e6e  pop     rbp
0x1806f3e6f  retn
```
