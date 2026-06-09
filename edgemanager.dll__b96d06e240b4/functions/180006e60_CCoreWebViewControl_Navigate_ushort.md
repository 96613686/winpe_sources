# CCoreWebViewControl::Navigate(ushort *)

- ea: `0x180006e60`
- end: `0x18000721e`
- name: `?Navigate@CCoreWebViewControl@@UEAAJPEAG@Z`
- size: `958`
- prototype: `int(CCoreWebViewControl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180006e60`
- `0x18000b0ec`
- `0x18000deac`
- `0x180014e28`
- `0x1800154cc`
- `0x18001d850`
- `0x180085010`

## import_xrefs

- `iertutil!CreateUri` at `0x180006f25`
- `iertutil!CreateUri` at `0x180006f25`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006fea`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006fea`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180006ea6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180006edf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180006ea6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180006edf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCoreWebViewControl::Navigate(CCoreWebViewControl *this, unsigned __int16 *a2)
{
  char *v3; // r14
  int v4; // eax
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r9
  char v8; // si
  HRESULT v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  HRESULT (__stdcall *GetSchemeName)(IUri *, BSTR *); // rax
  int v13; // eax
  OLECHAR *v14; // r15
  int v15; // eax
  OLECHAR *v16; // r15
  int v17; // eax
  IUri *v18; // rcx
  int v19; // eax
  _QWORD *v20; // rdi
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // [rsp+20h] [rbp-60h]
  int v25; // [rsp+20h] [rbp-60h]
  IUri *v26; // [rsp+30h] [rbp-50h]
  BSTR bstrString; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v28[4]; // [rsp+40h] [rbp-40h] BYREF
  int v29; // [rsp+60h] [rbp-20h]
  __int64 v30; // [rsp+64h] [rbp-1Ch]
  int v31; // [rsp+6Ch] [rbp-14h]
  __int64 v32; // [rsp+70h] [rbp-10h]
  __int64 v33; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v35; // [rsp+C0h] [rbp+40h] BYREF
  int v36; // [rsp+D0h] [rbp+50h] BYREF
  IUri *ppURI; // [rsp+D8h] [rbp+58h] BYREF

  v3 = (char *)this - 8;
  if ( (unsigned __int64)(*((_QWORD *)this + 14) - 1LL) <= 0x60003FFFFFFFELL )
  {
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 6) + 184LL))(*((_QWORD *)v3 + 6));
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v22,
        v24);
      return v23;
    }
    return 0;
  }
  if ( !StrCmpNICW(a2, L"ms-appdata://", 13) )
  {
    v4 = CCoreWebViewControl::NavigateToAppDataUri((CCoreWebViewControl *)v3, a2);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 287;
LABEL_51:
      v7 = (unsigned int)v4;
      goto LABEL_52;
    }
    return 0;
  }
  if ( !StrCmpNICW(a2, L"ms-local-stream", 15) )
  {
    v5 = -2147467260;
    v7 = 2147500036LL;
    v6 = 292;
    goto LABEL_52;
  }
  v36 = 0;
  v8 = 0;
  v26 = 0;
  if ( !a2 )
    goto LABEL_39;
  ppURI = 0;
  v9 = CreateUri(a2, 0x3002B80u, 0, &ppURI);
  v5 = v9;
  if ( v9 < 0 )
  {
    v10 = (unsigned int)v9;
    v11 = 693;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)v10,
      v24);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
    goto LABEL_38;
  }
  bstrString = 0;
  GetSchemeName = ppURI->lpVtbl->GetSchemeName;
  if ( v3[145] )
  {
    v13 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(ppURI, &bstrString);
    v14 = bstrString;
    if ( v13 )
    {
      v5 = -2147418113;
    }
    else
    {
      v5 = -2147467260;
      if ( (unsigned int)CUriUtils::_IsAsciiStringInList(
                           bstrString,
                           (const unsigned __int16 *const *const)&off_1800B61A0,
                           9u) )
        v5 = 0;
    }
    if ( v14 )
      SysFreeString(v14);
    if ( v5 < 0 )
    {
      v11 = 696;
LABEL_36:
      v10 = (unsigned int)v5;
      goto LABEL_37;
    }
  }
  else
  {
    v15 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(ppURI, &bstrString);
    v16 = bstrString;
    if ( v15 )
    {
      v5 = -2147418113;
    }
    else
    {
      v5 = -2147467260;
      if ( (unsigned int)CUriUtils::_IsAsciiStringInList(
                           bstrString,
                           (const unsigned __int16 *const *const)&off_1800B6160,
                           8u) )
        v5 = 0;
    }
    if ( v16 )
      SysFreeString(v16);
    if ( v5 < 0 )
    {
      v11 = 700;
      goto LABEL_36;
    }
  }
  v35 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, IUri *, int *))(**((_QWORD **)v3 + 6) + 520LL))(
          *((_QWORD *)v3 + 6),
          ppURI,
          &v35);
  v5 = v17;
  if ( v17 >= 0 )
  {
    if ( v35 )
    {
      v26 = ppURI;
      v5 = 0;
      goto LABEL_38;
    }
    v5 = -2147024809;
    v11 = 712;
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C0,
    (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
    (const char *)(unsigned int)v17,
    v24);
  v18 = ppURI;
  if ( ppURI )
  {
    ppURI = 0;
    ((void (__fastcall *)(IUri *))v18->lpVtbl->Release)(v18);
  }
LABEL_38:
  if ( v5 >= 0 )
  {
LABEL_39:
    memset(&v28[1], 0, 24);
    v30 = 0;
    v31 = 0;
    v33 = 0;
    v28[0] = v26;
    v29 = 0;
    v32 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, int *))(**((_QWORD **)v3 + 7) + 24LL))(
           *((_QWORD *)v3 + 7),
           *((_QWORD *)v3 + 6),
           v28,
           &v36);
    if ( v5 >= 0 && !v36 )
      v8 = 1;
  }
  if ( v26 )
    ((void (__fastcall *)(IUri *))v26->lpVtbl->Release)(v26);
  if ( v8 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 6) + 472LL))(*((_QWORD *)v3 + 6));
    v5 = v19;
    if ( v19 >= 0 )
    {
      v20 = (_QWORD *)*((_QWORD *)v3 + 16);
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CoreWebviewPermissionContextEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CoreWebviewPermissionContextEntry>>,void *>>>(
        v3 + 128,
        v3 + 128,
        v20[1]);
      v20[1] = v20;
      *v20 = v20;
      v20[2] = v20;
      *((_QWORD *)v3 + 17) = 0;
      v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)v3 + 6) + 184LL))(
             *((_QWORD *)v3 + 6),
             a2);
      v5 = v4;
      if ( v4 < 0 )
      {
        v6 = 301;
        goto LABEL_51;
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v19,
      v24);
    v7 = (unsigned int)v5;
    v6 = 299;
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)v7,
      v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v5,
      v25);
    return (unsigned int)v5;
  }
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v6 = 297;
    goto LABEL_52;
  }
  return 0;
}

```

## disassembly

```asm
0x180006e60  push    rbp
0x180006e62  push    rbx
0x180006e63  push    rsi
0x180006e64  push    rdi
0x180006e65  push    r12
0x180006e67  push    r14
0x180006e69  push    r15
0x180006e6b  mov     rbp, rsp
0x180006e6e  sub     rsp, 80h
0x180006e75  mov     rbx, rdx
0x180006e78  lea     r14, [rcx-8]
0x180006e7c  mov     rax, [r14+78h]
0x180006e80  dec     rax
0x180006e83  mov     rcx, 60003FFFFFFFEh
0x180006e8d  cmp     rax, rcx
0x180006e90  jbe     loc_1800071D5
0x180006e96  mov     r8d, 0Dh; nChar
0x180006e9c  lea     rdx, pszStr2; "ms-appdata://"
0x180006ea3  mov     rcx, rbx; pszStr1
0x180006ea6  call    cs:__imp_StrCmpNICW
0x180006eac  test    eax, eax
0x180006eae  jnz     short loc_180006ECF
0x180006eb0  mov     rdx, rbx; unsigned __int16 *
0x180006eb3  mov     rcx, r14; this
0x180006eb6  call    ?NavigateToAppDataUri@CCoreWebViewControl@@AEAAJPEAG@Z; CCoreWebViewControl::NavigateToAppDataUri(ushort *)
0x180006ebb  mov     edi, eax
0x180006ebd  test    eax, eax
0x180006ebf  jns     loc_18000720A
0x180006ec5  mov     edx, 11Fh
0x180006eca  jmp     loc_1800071A6
0x180006ecf  mov     r8d, 0Fh; nChar
0x180006ed5  lea     rdx, aMsLocalStream_0; "ms-local-stream"
0x180006edc  mov     rcx, rbx; pszStr1
0x180006edf  call    cs:__imp_StrCmpNICW
0x180006ee5  test    eax, eax
0x180006ee7  jnz     short loc_180006EFB
0x180006ee9  mov     edi, 80004004h
0x180006eee  mov     r9d, edi
0x180006ef1  mov     edx, 124h
0x180006ef6  jmp     loc_1800071A9
0x180006efb  xor     r12d, r12d
0x180006efe  mov     [rbp+arg_10], r12d
0x180006f02  xor     sil, sil
0x180006f05  mov     [rbp+var_50], r12
0x180006f09  test    rbx, rbx
0x180006f0c  jz      loc_180007093
0x180006f12  mov     [rbp+ppURI], r12
0x180006f16  lea     r9, [rbp+ppURI]; ppURI
0x180006f1a  xor     r8d, r8d; dwReserved
0x180006f1d  mov     edx, 3002B80h; dwFlags
0x180006f22  mov     rcx, rbx; pwzURI
0x180006f25  call    cs:__imp_CreateUri
0x180006f2b  mov     edi, eax
0x180006f2d  test    eax, eax
0x180006f2f  jns     short loc_180006F3E
0x180006f31  mov     r9d, eax
0x180006f34  mov     edx, 2B5h
0x180006f39  jmp     loc_180007075
0x180006f3e  mov     rcx, [rbp+ppURI]
0x180006f42  mov     [rbp+bstrString], r12
0x180006f46  lea     rdx, [rbp+bstrString]
0x180006f4a  mov     rax, [rcx]
0x180006f4d  mov     rax, [rax+98h]
0x180006f54  cmp     byte ptr [r14+91h], 0
0x180006f5c  jz      short loc_180006FAE
0x180006f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f63  mov     r15, [rbp+bstrString]
0x180006f67  test    eax, eax
0x180006f69  jnz     short loc_180006F8D
0x180006f6b  mov     r8d, 9; unsigned __int64
0x180006f71  lea     rdx, off_1800B61A0; unsigned __int16 **
0x180006f78  mov     rcx, r15; unsigned __int16 *
0x180006f7b  call    ?_IsAsciiStringInList@CUriUtils@@CAHPEBGQEBQEBG_K@Z; CUriUtils::_IsAsciiStringInList(ushort const *,ushort const * const * const,unsigned __int64)
0x180006f80  mov     edi, 80004004h
0x180006f85  test    eax, eax
0x180006f87  cmovnz  edi, r12d
0x180006f8b  jmp     short loc_180006F92
0x180006f8d  mov     edi, 8000FFFFh
0x180006f92  test    r15, r15
0x180006f95  jz      short loc_180006FA0
0x180006f97  mov     rcx, r15; bstrString
0x180006f9a  call    cs:__imp_SysFreeString
0x180006fa0  test    edi, edi
0x180006fa2  jns     short loc_180006FFB
0x180006fa4  mov     edx, 2B8h
0x180006fa9  jmp     loc_180007072
0x180006fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fb3  mov     r15, [rbp+bstrString]
0x180006fb7  test    eax, eax
0x180006fb9  jnz     short loc_180006FDD
0x180006fbb  mov     r8d, 8; unsigned __int64
0x180006fc1  lea     rdx, off_1800B6160; unsigned __int16 **
0x180006fc8  mov     rcx, r15; unsigned __int16 *
0x180006fcb  call    ?_IsAsciiStringInList@CUriUtils@@CAHPEBGQEBQEBG_K@Z; CUriUtils::_IsAsciiStringInList(ushort const *,ushort const * const * const,unsigned __int64)
0x180006fd0  mov     edi, 80004004h
0x180006fd5  test    eax, eax
0x180006fd7  cmovnz  edi, r12d
0x180006fdb  jmp     short loc_180006FE2
0x180006fdd  mov     edi, 8000FFFFh
0x180006fe2  test    r15, r15
0x180006fe5  jz      short loc_180006FF0
0x180006fe7  mov     rcx, r15; bstrString
0x180006fea  call    cs:__imp_SysFreeString
0x180006ff0  test    edi, edi
0x180006ff2  jns     short loc_180006FFB
0x180006ff4  mov     edx, 2BCh
0x180006ff9  jmp     short loc_180007072
0x180006ffb  mov     [rbp+arg_0], r12d
0x180006fff  mov     rcx, [r14+30h]
0x180007003  mov     rax, [rcx]
0x180007006  lea     r8, [rbp+arg_0]
0x18000700a  mov     rdx, [rbp+ppURI]
0x18000700e  mov     rax, [rax+208h]
0x180007015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701a  mov     edi, eax
0x18000701c  test    eax, eax
0x18000701e  jns     short loc_180007055
0x180007020  mov     rcx, [rbp+38h]; this
0x180007024  mov     r9d, eax; char *
0x180007027  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000702e  mov     edx, 2C0h; void *
0x180007033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007038  nop
0x180007039  mov     rcx, [rbp+ppURI]
0x18000703d  test    rcx, rcx
0x180007040  jz      short loc_180007053
0x180007042  mov     [rbp+ppURI], r12
0x180007046  mov     rax, [rcx]
0x180007049  mov     rax, [rax+10h]
0x18000704d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007052  nop
0x180007053  jmp     short loc_18000708F
0x180007055  cmp     [rbp+arg_0], 0
0x180007059  jz      short loc_180007068
0x18000705b  mov     rax, [rbp+ppURI]
0x18000705f  mov     [rbp+var_50], rax
0x180007063  mov     edi, r12d
0x180007066  jmp     short loc_18000708F
0x180007068  mov     edi, 80070057h
0x18000706d  mov     edx, 2C8h; void *
0x180007072  mov     r9d, edi; char *
0x180007075  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000707c  mov     rcx, [rbp+38h]; this
0x180007080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007085  nop
0x180007086  lea     rcx, [rbp+ppURI]
0x18000708a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000708f  test    edi, edi
0x180007091  js      short loc_1800070E6
0x180007093  mov     [rbp+var_38], r12
0x180007097  mov     [rbp+var_30], r12
0x18000709b  mov     [rbp+var_28], r12
0x18000709f  mov     [rbp+var_1C], r12
0x1800070a3  mov     [rbp+var_14], r12d
0x1800070a7  mov     [rbp+var_8], r12
0x1800070ab  mov     rax, [rbp+var_50]
0x1800070af  mov     [rbp+var_40], rax
0x1800070b3  mov     [rbp+var_20], r12d
0x1800070b7  mov     [rbp+var_10], r12
0x1800070bb  mov     rcx, [r14+38h]
0x1800070bf  mov     rax, [rcx]
0x1800070c2  lea     r9, [rbp+arg_10]
0x1800070c6  lea     r8, [rbp+var_40]
0x1800070ca  mov     rdx, [r14+30h]
0x1800070ce  mov     rax, [rax+18h]
0x1800070d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070d7  mov     edi, eax
0x1800070d9  test    eax, eax
0x1800070db  js      short loc_1800070E6
0x1800070dd  cmp     [rbp+arg_10], 0
0x1800070e1  jnz     short loc_1800070E6
0x1800070e3  mov     sil, 1
0x1800070e6  mov     rcx, [rbp+var_50]
0x1800070ea  test    rcx, rcx
0x1800070ed  jz      short loc_180007100
0x1800070ef  mov     [rbp+var_50], r12
0x1800070f3  mov     rax, [rcx]
0x1800070f6  mov     rax, [rax+10h]
0x1800070fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ff  nop
0x180007100  test    sil, sil
0x180007103  jnz     short loc_18000711A
0x180007105  test    edi, edi
0x180007107  jns     loc_18000720A
0x18000710d  mov     r9d, edi
0x180007110  mov     edx, 129h
0x180007115  jmp     loc_1800071A9
0x18000711a  mov     rcx, [r14+30h]
0x18000711e  mov     rax, [rcx]
0x180007121  mov     rax, [rax+1D8h]
0x180007128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000712d  mov     edi, eax
0x18000712f  test    eax, eax
0x180007131  jns     short loc_180007155
0x180007133  mov     rcx, [rbp+38h]; this
0x180007137  mov     r9d, eax; char *
0x18000713a  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180007141  mov     edx, 2D7h; void *
0x180007146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000714b  mov     r9d, edi
0x18000714e  mov     edx, 12Bh
0x180007153  jmp     short loc_1800071A9
0x180007155  mov     rdi, [r14+80h]
0x18000715c  mov     r8, [rdi+8]
0x180007160  lea     rdx, [r14+80h]
0x180007167  lea     rcx, [r14+80h]
0x18000716e  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCoreWebviewPermissionContextEntry@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCoreWebviewPermissionContextEntry@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCoreWebviewPermissionContextEntry@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCoreWebviewPermissionContextEntry@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CoreWebviewPermissionContextEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CoreWebviewPermissionContextEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CoreWebviewPermissionContextEntry>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<CoreWebviewPermissionContextEntry>>,void *> *)
0x180007173  mov     [rdi+8], rdi
0x180007177  mov     [rdi], rdi
0x18000717a  mov     [rdi+10h], rdi
0x18000717e  mov     [r14+88h], r12
0x180007185  mov     rcx, [r14+30h]
0x180007189  mov     rax, [rcx]
0x18000718c  mov     rdx, rbx
0x18000718f  mov     rax, [rax+0B8h]
0x180007196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000719b  mov     edi, eax
0x18000719d  test    eax, eax
0x18000719f  jns     short loc_18000720A
0x1800071a1  mov     edx, 12Dh; void *
0x1800071a6  mov     r9d, eax; char *
0x1800071a9  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800071b0  mov     rcx, [rbp+38h]; this
0x1800071b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071b9  mov     rcx, [rbp+38h]; this
0x1800071bd  mov     r9d, edi; char *
0x1800071c0  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800071c7  mov     edx, 10Fh; void *
0x1800071cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071d1  mov     eax, edi
0x1800071d3  jmp     short loc_18000720C
0x1800071d5  mov     rcx, [r14+30h]
0x1800071d9  mov     rax, [rcx]
0x1800071dc  mov     rax, [rax+0B8h]
0x1800071e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e8  mov     ebx, eax
0x1800071ea  test    eax, eax
0x1800071ec  jns     short loc_18000720A
0x1800071ee  mov     rcx, [rbp+38h]; this
0x1800071f2  mov     r9d, eax; char *
0x1800071f5  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800071fc  mov     edx, 113h; void *
0x180007201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007206  mov     eax, ebx
0x180007208  jmp     short loc_18000720C
0x18000720a  xor     eax, eax
0x18000720c  add     rsp, 80h
0x180007213  pop     r15
0x180007215  pop     r14
0x180007217  pop     r12
0x180007219  pop     rdi
0x18000721a  pop     rsi
0x18000721b  pop     rbx
0x18000721c  pop     rbp
0x18000721d  retn
```
