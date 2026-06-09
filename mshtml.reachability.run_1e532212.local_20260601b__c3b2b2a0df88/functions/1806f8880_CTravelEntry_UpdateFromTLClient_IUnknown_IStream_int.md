# CTravelEntry::_UpdateFromTLClient(IUnknown *,IStream * *,int)

- ea: `0x1806f8880`
- end: `0x1806f8ca1`
- name: `?_UpdateFromTLClient@CTravelEntry@@IEAAJPEAUIUnknown@@PEAPEAUIStream@@H@Z`
- size: `1057`
- prototype: `__int64 __fastcall(CTravelEntry *__hidden this, struct IUnknown *, struct IStream **, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x181073a40`

## callees

- `0x180012dac`
- `0x180013efc`
- `0x18005d080`
- `0x1800c5000`
- `0x18040ac58`
- `0x1804e4c1c`
- `0x18053c270`
- `0x18053d04c`
- `0x1805e77e0`
- `0x1806a32e0`
- `0x1806f8880`
- `0x181094ae4`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1806f8c29`
- `KERNEL32!GlobalFree` at `0x1806f8c29`
- `KERNEL32!LocalFree` at `0x1806f8b1e`
- `KERNEL32!LocalFree` at `0x1806f8b1e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1806f8b38`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1806f8b38`
- `iertutil!CreateUri` at `0x1806f8b03`
- `iertutil!CreateUri` at `0x1806f8b03`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1806f8c14`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1806f8c14`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1806f89bd`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1806f89bd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f8b9b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f8bac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f8bbd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f8b9b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f8bac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806f8bbd`
- `SHELL32!__imp_ILFree` at `0x1806f8b8a`
- `SHELL32!__imp_ILFree` at `0x1806f8b8a`

## string_xrefs

- `0x1806f8b6d`: `CTravelEntry::_UpdateFromTLClient - TravelEntry=0x%08lX ptlc=0x%08lX _bid=0x%08lX UrlWithFragment=%S Title=%S ppStream=0x%08lX`

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
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  int IsSearchUrl; // eax
  __int64 v16; // r8
  char *v17; // rcx
  __int64 v18; // rax
  const unsigned __int16 *v19; // r8
  IUri **v20; // rax
  void *v21; // rcx
  const wchar_t *v22; // rcx
  LPSTREAM v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B8h] BYREF
  HGLOBAL phglobal; // [rsp+58h] [rbp-B0h] BYREF
  HGLOBAL phglobal_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  LPITEMIDLIST pidl_8[2]; // [rsp+70h] [rbp-98h]
  WCHAR *v32; // [rsp+80h] [rbp-88h]
  __int128 v33; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v34[16]; // [rsp+98h] [rbp-70h] BYREF
  int v35; // [rsp+A8h] [rbp-60h]
  wchar_t pwzURI[2088]; // [rsp+E8h] [rbp-20h] BYREF

  v32 = 0;
  lpVtbl = a2->lpVtbl;
  v27 = 0;
  *(_OWORD *)phglobal_8 = 0;
  v28 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)pidl_8 = 0;
  pwzURI[0] = 0;
  v33 = 0;
  StreamOnHGlobal = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
                      a2,
                      &GUID_241c033e_e659_43da_aa4d_4086dbc4758d,
                      &v27);
  if ( StreamOnHGlobal )
    goto LABEL_37;
  if ( a4 )
  {
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                        a2,
                        &GUID_0000010c_0000_0000_c000_000000000046,
                        &v28);
    if ( StreamOnHGlobal )
      goto LABEL_37;
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v28 + 24LL))(v28, &v33);
    if ( StreamOnHGlobal )
      goto LABEL_37;
    v10 = (_OWORD *)*((_QWORD *)this + 5);
    if ( v10 )
    {
      *v10 = v33;
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
      *v11 = v33;
      *((_QWORD *)this + 5) = v11;
    }
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 0, a3);
  if ( StreamOnHGlobal )
    goto LABEL_37;
  StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, HGLOBAL *))(*(_QWORD *)v27 + 32LL))(
                      v27,
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
  if ( (unsigned int)IsSpecialUrl(pwzURI, v12)
    && !UrlUtils::IsAboutTabs((UrlUtils *)pwzURI, v13)
    && !UrlUtils::IsAboutNewsFeed((UrlUtils *)pwzURI, v14) )
  {
    goto LABEL_36;
  }
  IsSearchUrl = CTravelEntry::_IsSearchUrl(pwzURI);
  v16 = *((_QWORD *)this + 1);
  v17 = (char *)this + 8;
  if ( IsSearchUrl )
    (*(void (__fastcall **)(char *, __int64))(v16 + 24))(v17, 4);
  else
    (*(void (__fastcall **)(char *, __int64))(v16 + 32))(v17, 4);
  if ( !pidl_8[1] || !pidl_8[1]->mkid.cb )
    goto LABEL_29;
  v18 = -1;
  do
    ++v18;
  while ( pwzURI[v18] );
  v19 = L"%s";
  if ( pidl_8[1]->mkid.cb != 35 )
    v19 = L"#%s";
  StreamOnHGlobal = StringCchPrintfW(&pwzURI[(unsigned int)v18], 2084LL - (unsigned int)v18, v19);
  if ( StreamOnHGlobal >= 0 )
  {
LABEL_29:
    v20 = (IUri **)TSmartPointer<ID3D11Device>::operator&((char *)this + 56);
    StreamOnHGlobal = CreateUri(pwzURI, 0x3002B84u, 0, v20);
    if ( StreamOnHGlobal >= 0 )
    {
      v21 = (void *)*((_QWORD *)this + 11);
      if ( v21 )
      {
        LocalFree(v21);
        *((_QWORD *)this + 11) = 0;
      }
      if ( v32 )
      {
        v22 = StrDupW(v32);
        *((_QWORD *)this + 11) = v22;
      }
      else
      {
        v22 = 0;
      }
      Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
        "CTravelEntry::_UpdateFromTLClient - TravelEntry=0x%08lX ptlc=0x%08lX _bid=0x%08lX UrlWithFragment=%S Title=%S ppStream=0x%08lX",
        (_DWORD)this,
        v27,
        *((_DWORD *)this + 18),
        pwzURI,
        v22,
        (unsigned int)*a3);
    }
  }
LABEL_37:
  ILFree((LPITEMIDLIST)phglobal_8[1]);
  CoTaskMemFree(pidl_8[0]);
  CoTaskMemFree(pidl_8[1]);
  CoTaskMemFree(v32);
  v23 = *a3;
  if ( *a3 )
  {
    memset_0(v34, 0, 0x50u);
    phglobal = 0;
    if ( StreamOnHGlobal < 0
      || (*(int (__fastcall **)(LPSTREAM, _BYTE *, __int64))(*(_QWORD *)v23 + 96LL))(v23, v34, 1) >= 0 && !v35 )
    {
      if ( GetHGlobalFromStream(*a3, &phglobal) >= 0 )
        GlobalFree(phglobal);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
      *a3 = 0;
    }
  }
  v24 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1806f8880  mov     rax, rsp
0x1806f8883  mov     [rax+20h], r9d
0x1806f8887  mov     [rax+18h], r8
0x1806f888b  mov     [rax+10h], rdx
0x1806f888f  mov     [rax+8], rcx
0x1806f8893  push    rbp
0x1806f8894  push    rbx
0x1806f8895  push    rsi
0x1806f8896  push    rdi
0x1806f8897  push    r12
0x1806f8899  push    r14
0x1806f889b  push    r15
0x1806f889d  lea     rbp, [rax-1078h]
0x1806f88a4  mov     eax, 1140h
0x1806f88a9  call    _alloca_probe
0x1806f88ae  sub     rsp, rax
0x1806f88b1  mov     rax, cs:__security_cookie
0x1806f88b8  xor     rax, rsp
0x1806f88bb  mov     [rbp+1070h+var_40], rax
0x1806f88c2  mov     r14, [rbp+1070h+arg_8]
0x1806f88c9  lea     r8, [rsp+1170h+var_1130]
0x1806f88ce  mov     rdi, [rbp+1070h+arg_0]
0x1806f88d5  lea     rdx, _GUID_241c033e_e659_43da_aa4d_4086dbc4758d
0x1806f88dc  mov     rsi, [rbp+1070h+ppstm]
0x1806f88e3  xor     eax, eax
0x1806f88e5  xorps   xmm0, xmm0
0x1806f88e8  mov     [rsp+1170h+var_10F8], rax
0x1806f88ed  mov     rax, [r14]
0x1806f88f0  xor     r12d, r12d
0x1806f88f3  mov     rcx, r14
0x1806f88f6  mov     [rsp+1170h+var_1130], r12
0x1806f88fb  movups  xmmword ptr [rsp+1170h+phglobal+8], xmm0
0x1806f8900  mov     [rsp+1170h+var_1128], r12
0x1806f8905  mov     rax, [rax]
0x1806f8908  movups  xmmword ptr [rsp+1170h+pidl+8], xmm0
0x1806f890d  mov     [rbp+1070h+pwzURI], r12w
0x1806f8912  movups  [rbp+1070h+var_10F0], xmm0
0x1806f8916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f891b  mov     ebx, eax
0x1806f891d  test    eax, eax
0x1806f891f  jnz     loc_1806F8B85
0x1806f8925  cmp     [rbp+1070h+arg_18], r12d
0x1806f892c  jz      loc_1806F89B6
0x1806f8932  mov     rax, [r14]
0x1806f8935  lea     r8, [rsp+1170h+var_1128]
0x1806f893a  lea     rdx, _GUID_0000010c_0000_0000_c000_000000000046
0x1806f8941  mov     rcx, r14
0x1806f8944  mov     rax, [rax]
0x1806f8947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f894c  mov     ebx, eax
0x1806f894e  test    eax, eax
0x1806f8950  jnz     loc_1806F8B85
0x1806f8956  mov     rcx, [rsp+1170h+var_1128]
0x1806f895b  lea     rdx, [rbp+1070h+var_10F0]
0x1806f895f  mov     rax, [rcx]
0x1806f8962  mov     rax, [rax+18h]
0x1806f8966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f896b  mov     ebx, eax
0x1806f896d  test    eax, eax
0x1806f896f  jnz     loc_1806F8B85
0x1806f8975  mov     rax, [rdi+28h]
0x1806f8979  test    rax, rax
0x1806f897c  jnz     short loc_1806F89AE
0x1806f897e  mov     rcx, cs:g_hProcessHeap
0x1806f8985  lea     edx, [rbx+10h]
0x1806f8988  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1806f898d  test    rax, rax
0x1806f8990  jz      short loc_1806F89A0
0x1806f8992  movups  xmm0, [rbp+1070h+var_10F0]
0x1806f8996  movdqu  xmmword ptr [rax], xmm0
0x1806f899a  mov     [rdi+28h], rax
0x1806f899e  jmp     short loc_1806F89B6
0x1806f89a0  mov     [rdi+28h], r12
0x1806f89a4  mov     ebx, 8007000Eh
0x1806f89a9  jmp     loc_1806F8B85
0x1806f89ae  movups  xmm0, [rbp+1070h+var_10F0]
0x1806f89b2  movdqu  xmmword ptr [rax], xmm0
0x1806f89b6  mov     r8, rsi; ppstm
0x1806f89b9  xor     edx, edx; fDeleteOnRelease
0x1806f89bb  xor     ecx, ecx; hGlobal
0x1806f89bd  call    cs:__imp_CreateStreamOnHGlobal
0x1806f89c4  nop     dword ptr [rax+rax+00h]
0x1806f89c9  mov     ebx, eax
0x1806f89cb  test    eax, eax
0x1806f89cd  jnz     loc_1806F8B85
0x1806f89d3  mov     rcx, [rsp+1170h+var_1130]
0x1806f89d8  lea     r8, [rsp+1170h+phglobal+8]
0x1806f89dd  mov     rdx, [rsi]
0x1806f89e0  mov     rax, [rcx]
0x1806f89e3  mov     rax, [rax+20h]
0x1806f89e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f89ec  mov     ebx, eax
0x1806f89ee  test    eax, eax
0x1806f89f0  jnz     loc_1806F8B85
0x1806f89f6  mov     eax, dword ptr [rsp+1170h+phglobal+8]
0x1806f89fa  lea     rcx, [rdi+38h]; void *
0x1806f89fe  mov     [rdi+48h], eax
0x1806f8a01  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1806f8a06  mov     rcx, [rsp+1170h+pidl]; struct _ITEMIDLIST_RELATIVE *
0x1806f8a0b  mov     r14d, 824h
0x1806f8a11  test    rcx, rcx
0x1806f8a14  jz      short loc_1806F8A21
0x1806f8a16  lea     r9, [rbp+1070h+pwzURI]
0x1806f8a1a  call    IEGetNameAndFlagsEx
0x1806f8a1f  jmp     short loc_1806F8A3B
0x1806f8a21  mov     r8, [rsp+1170h+pidl+8]; unsigned __int16 *
0x1806f8a26  test    r8, r8
0x1806f8a29  jz      loc_1806F8B80
0x1806f8a2f  mov     rdx, r14; unsigned __int64
0x1806f8a32  lea     rcx, [rbp+1070h+pwzURI]; unsigned __int16 *
0x1806f8a36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1806f8a3b  lea     rcx, [rbp+1070h+pwzURI]
0x1806f8a3f  call    IsSpecialUrl
0x1806f8a44  test    eax, eax
0x1806f8a46  jz      short loc_1806F8A66
0x1806f8a48  lea     rcx, [rbp+1070h+pwzURI]; this
0x1806f8a4c  call    ?IsAboutTabs@UrlUtils@@YA_NPEBG@Z; UrlUtils::IsAboutTabs(ushort const *)
0x1806f8a51  test    al, al
0x1806f8a53  jnz     short loc_1806F8A66
0x1806f8a55  lea     rcx, [rbp+1070h+pwzURI]; this
0x1806f8a59  call    ?IsAboutNewsFeed@UrlUtils@@YA_NPEBG@Z; UrlUtils::IsAboutNewsFeed(ushort const *)
0x1806f8a5e  test    al, al
0x1806f8a60  jz      loc_1806F8B80
0x1806f8a66  lea     rcx, [rbp+1070h+pwzURI]; unsigned __int16 *
0x1806f8a6a  lea     rbx, [rdi+8]
0x1806f8a6e  call    ?_IsSearchUrl@CTravelEntry@@KAHPEBG@Z; CTravelEntry::_IsSearchUrl(ushort const *)
0x1806f8a73  mov     r8, [rbx]
0x1806f8a76  mov     edx, 4
0x1806f8a7b  mov     rcx, rbx
0x1806f8a7e  test    eax, eax
0x1806f8a80  jz      short loc_1806F8A88
0x1806f8a82  mov     rax, [r8+18h]
0x1806f8a86  jmp     short loc_1806F8A8C
0x1806f8a88  mov     rax, [r8+20h]
0x1806f8a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f8a91  mov     r9, [rsp+1170h+pv]
0x1806f8a96  test    r9, r9
0x1806f8a99  jz      short loc_1806F8AEB
0x1806f8a9b  cmp     [r9], r12w
0x1806f8a9f  jz      short loc_1806F8AEB
0x1806f8aa1  lea     rcx, [rbp+1070h+pwzURI]
0x1806f8aa5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1806f8aa9  inc     rax
0x1806f8aac  cmp     [rcx+rax*2], r12w
0x1806f8ab1  jnz     short loc_1806F8AA9
0x1806f8ab3  mov     eax, eax
0x1806f8ab5  lea     rcx, [rbp+1070h+pwzURI]
0x1806f8ab9  sub     r14, rax
0x1806f8abc  lea     r8, aS_11; "%s"
0x1806f8ac3  mov     rdx, r14; unsigned __int64
0x1806f8ac6  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1806f8aca  mov     eax, 23h ; '#'
0x1806f8acf  cmp     ax, [r9]
0x1806f8ad3  jz      short loc_1806F8ADC
0x1806f8ad5  lea     r8, aS_14; "#%s"
0x1806f8adc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1806f8ae1  mov     ebx, eax
0x1806f8ae3  test    eax, eax
0x1806f8ae5  js      loc_1806F8B85
0x1806f8aeb  lea     rcx, [rdi+38h]
0x1806f8aef  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1806f8af4  mov     r9, rax; ppURI
0x1806f8af7  lea     rcx, [rbp+1070h+pwzURI]; pwzURI
0x1806f8afb  xor     r8d, r8d; dwReserved
0x1806f8afe  mov     edx, 3002B84h; dwFlags
0x1806f8b03  call    cs:__imp_CreateUri
0x1806f8b0a  nop     dword ptr [rax+rax+00h]
0x1806f8b0f  mov     ebx, eax
0x1806f8b11  test    eax, eax
0x1806f8b13  js      short loc_1806F8B85
0x1806f8b15  mov     rcx, [rdi+58h]; hMem
0x1806f8b19  test    rcx, rcx
0x1806f8b1c  jz      short loc_1806F8B2E
0x1806f8b1e  call    cs:__imp_LocalFree
0x1806f8b25  nop     dword ptr [rax+rax+00h]
0x1806f8b2a  mov     [rdi+58h], r12
0x1806f8b2e  mov     rcx, [rsp+1170h+var_10F8]; pszSrch
0x1806f8b33  test    rcx, rcx
0x1806f8b36  jz      short loc_1806F8B4D
0x1806f8b38  call    cs:__imp_StrDupW
0x1806f8b3f  nop     dword ptr [rax+rax+00h]
0x1806f8b44  mov     rcx, rax
0x1806f8b47  mov     [rdi+58h], rax
0x1806f8b4b  jmp     short loc_1806F8B50
0x1806f8b4d  mov     rcx, r12
0x1806f8b50  mov     rax, [rsi]
0x1806f8b53  mov     rdx, rdi
0x1806f8b56  mov     r8, [rsp+1170h+var_1130]
0x1806f8b5b  mov     r9d, [rdi+48h]
0x1806f8b5f  mov     [rsp+30h], rax
0x1806f8b64  lea     rax, [rbp+1070h+pwzURI]
0x1806f8b68  mov     [rsp+1170h+var_1148], rcx
0x1806f8b6d  lea     rcx, aCtravelentryUp; "CTravelEntry::_UpdateFromTLClient - Tra"...
0x1806f8b74  mov     [rsp+1170h+var_1150], rax
0x1806f8b79  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(...)
0x1806f8b7e  jmp     short loc_1806F8B85
0x1806f8b80  mov     ebx, 800C000Eh
0x1806f8b85  mov     rcx, [rsp+1170h+pidl]; pidl
0x1806f8b8a  call    cs:__imp_ILFree
0x1806f8b91  nop     dword ptr [rax+rax+00h]
0x1806f8b96  mov     rcx, [rsp+1170h+pidl+8]; pv
0x1806f8b9b  call    cs:__imp_CoTaskMemFree
0x1806f8ba2  nop     dword ptr [rax+rax+00h]
0x1806f8ba7  mov     rcx, [rsp+1170h+pv]; pv
0x1806f8bac  call    cs:__imp_CoTaskMemFree
0x1806f8bb3  nop     dword ptr [rax+rax+00h]
0x1806f8bb8  mov     rcx, [rsp+1170h+var_10F8]; pv
0x1806f8bbd  call    cs:__imp_CoTaskMemFree
0x1806f8bc4  nop     dword ptr [rax+rax+00h]
0x1806f8bc9  mov     rdi, [rsi]
0x1806f8bcc  test    rdi, rdi
0x1806f8bcf  jz      short loc_1806F8C47
0x1806f8bd1  xor     edx, edx; Val
0x1806f8bd3  lea     rcx, [rbp+1070h+var_10E0]; void *
0x1806f8bd7  lea     r8d, [rdx+50h]; Size
0x1806f8bdb  call    memset_0
0x1806f8be0  mov     [rsp+1170h+phglobal], r12
0x1806f8be5  test    ebx, ebx
0x1806f8be7  js      short loc_1806F8C0C
0x1806f8be9  mov     rax, [rdi]
0x1806f8bec  lea     rdx, [rbp+1070h+var_10E0]
0x1806f8bf0  mov     r8d, 1
0x1806f8bf6  mov     rcx, rdi
0x1806f8bf9  mov     rax, [rax+60h]
0x1806f8bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f8c02  test    eax, eax
0x1806f8c04  js      short loc_1806F8C47
0x1806f8c06  cmp     [rbp+1070h+var_10D0], r12d
0x1806f8c0a  jnz     short loc_1806F8C47
0x1806f8c0c  mov     rcx, [rsi]; pstm
0x1806f8c0f  lea     rdx, [rsp+1170h+phglobal]; phglobal
0x1806f8c14  call    cs:__imp_GetHGlobalFromStream
0x1806f8c1b  nop     dword ptr [rax+rax+00h]
0x1806f8c20  test    eax, eax
0x1806f8c22  js      short loc_1806F8C35
0x1806f8c24  mov     rcx, [rsp+1170h+phglobal]; hMem
0x1806f8c29  call    cs:__imp_GlobalFree
0x1806f8c30  nop     dword ptr [rax+rax+00h]
0x1806f8c35  mov     rcx, [rsi]
0x1806f8c38  mov     rax, [rcx]
0x1806f8c3b  mov     rax, [rax+10h]
0x1806f8c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f8c44  mov     [rsi], r12
0x1806f8c47  mov     rcx, [rsp+1170h+var_1130]
0x1806f8c4c  test    rcx, rcx
0x1806f8c4f  jz      short loc_1806F8C62
0x1806f8c51  mov     [rsp+1170h+var_1130], r12
0x1806f8c56  mov     rax, [rcx]
0x1806f8c59  mov     rax, [rax+10h]
0x1806f8c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f8c62  mov     rcx, [rsp+1170h+var_1128]
0x1806f8c67  test    rcx, rcx
0x1806f8c6a  jz      short loc_1806F8C7D
0x1806f8c6c  mov     [rsp+1170h+var_1128], r12
0x1806f8c71  mov     rax, [rcx]
0x1806f8c74  mov     rax, [rax+10h]
0x1806f8c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f8c7d  mov     eax, ebx
0x1806f8c7f  mov     rcx, [rbp+1070h+var_40]
0x1806f8c86  xor     rcx, rsp; StackCookie
0x1806f8c89  call    __security_check_cookie
0x1806f8c8e  add     rsp, 1140h
0x1806f8c95  pop     r15
0x1806f8c97  pop     r14
0x1806f8c99  pop     r12
0x1806f8c9b  pop     rdi
0x1806f8c9c  pop     rsi
0x1806f8c9d  pop     rbx
0x1806f8c9e  pop     rbp
0x1806f8c9f  retn
```
