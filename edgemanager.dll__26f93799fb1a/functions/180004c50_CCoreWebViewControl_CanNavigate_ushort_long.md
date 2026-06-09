# CCoreWebViewControl::CanNavigate(ushort *,long &)

- ea: `0x180004c50`
- end: `0x180004e95`
- name: `?CanNavigate@CCoreWebViewControl@@AEAA_NPEAGAEAJ@Z`
- size: `581`
- prototype: `bool(CCoreWebViewControl *__hidden this, unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014e28`
- `0x18003b524`
- `0x18003b724`

## callees

- `0x180004c50`
- `0x18000b0ec`
- `0x1800154cc`
- `0x18001d850`
- `0x180085010`

## import_xrefs

- `iertutil!CreateUri` at `0x180004c9b`
- `iertutil!CreateUri` at `0x180004c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d10`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d10`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d60`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BOOL8 __fastcall CCoreWebViewControl::CanNavigate(CCoreWebViewControl *this, unsigned __int16 *a2, int *a3)
{
  bool v5; // di
  HRESULT v6; // eax
  int v7; // esi
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  HRESULT (__stdcall *GetSchemeName)(IUri *, BSTR *); // rax
  int v11; // eax
  OLECHAR *v12; // r15
  int v13; // eax
  OLECHAR *v14; // r15
  int v15; // eax
  IUri *v16; // rcx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-60h]
  IUri *v20; // [rsp+30h] [rbp-50h]
  BSTR bstrString; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v22[4]; // [rsp+40h] [rbp-40h] BYREF
  int v23; // [rsp+60h] [rbp-20h]
  __int64 v24; // [rsp+64h] [rbp-1Ch]
  int v25; // [rsp+6Ch] [rbp-14h]
  __int64 v26; // [rsp+70h] [rbp-10h]
  __int64 v27; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v29; // [rsp+C8h] [rbp+48h] BYREF
  int v30; // [rsp+D0h] [rbp+50h] BYREF
  IUri *ppURI; // [rsp+D8h] [rbp+58h] BYREF

  *a3 = 0;
  v30 = 0;
  v5 = 0;
  v20 = 0;
  if ( a2 )
  {
    ppURI = 0;
    v6 = CreateUri(a2, 0x3002B80u, 0, &ppURI);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = (unsigned int)v6;
      v9 = 693;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)v8,
        v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
      goto LABEL_32;
    }
    bstrString = 0;
    GetSchemeName = ppURI->lpVtbl->GetSchemeName;
    if ( *((_BYTE *)this + 145) )
    {
      v11 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(ppURI, &bstrString);
      v12 = bstrString;
      if ( v11 )
      {
        v7 = -2147418113;
      }
      else
      {
        v7 = -2147467260;
        if ( (unsigned int)CUriUtils::_IsAsciiStringInList(
                             bstrString,
                             (const unsigned __int16 *const *const)&off_1800B61A0,
                             9u) )
          v7 = 0;
      }
      if ( v12 )
        SysFreeString(v12);
      if ( v7 < 0 )
      {
        v9 = 696;
LABEL_30:
        v8 = (unsigned int)v7;
        goto LABEL_31;
      }
    }
    else
    {
      v13 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(ppURI, &bstrString);
      v14 = bstrString;
      if ( v13 )
      {
        v7 = -2147418113;
      }
      else
      {
        v7 = -2147467260;
        if ( (unsigned int)CUriUtils::_IsAsciiStringInList(
                             bstrString,
                             (const unsigned __int16 *const *const)&off_1800B6160,
                             8u) )
          v7 = 0;
      }
      if ( v14 )
        SysFreeString(v14);
      if ( v7 < 0 )
      {
        v9 = 700;
        goto LABEL_30;
      }
    }
    v29 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, IUri *, int *))(**((_QWORD **)this + 6) + 520LL))(
            *((_QWORD *)this + 6),
            ppURI,
            &v29);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v15,
        v19);
      v16 = ppURI;
      if ( ppURI )
      {
        ppURI = 0;
        ((void (__fastcall *)(IUri *))v16->lpVtbl->Release)(v16);
      }
LABEL_32:
      *a3 = v7;
      if ( v7 < 0 )
        goto LABEL_35;
      goto LABEL_33;
    }
    if ( v29 )
    {
      v20 = ppURI;
      v7 = 0;
      goto LABEL_32;
    }
    v7 = -2147024809;
    v9 = 712;
    goto LABEL_30;
  }
LABEL_33:
  memset(&v22[1], 0, 24);
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v22[0] = v20;
  v23 = 0;
  v26 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, int *))(**((_QWORD **)this + 7) + 24LL))(
          *((_QWORD *)this + 7),
          *((_QWORD *)this + 6),
          v22,
          &v30);
  *a3 = v17;
  if ( v17 >= 0 )
    v5 = v30 == 0;
LABEL_35:
  if ( v20 )
    ((void (__fastcall *)(IUri *))v20->lpVtbl->Release)(v20);
  return v5;
}

```

## disassembly

```asm
0x180004c50  push    rbp
0x180004c52  push    rbx
0x180004c53  push    rsi
0x180004c54  push    rdi
0x180004c55  push    r12
0x180004c57  push    r14
0x180004c59  push    r15
0x180004c5b  mov     rbp, rsp
0x180004c5e  sub     rsp, 80h
0x180004c65  mov     rbx, r8
0x180004c68  mov     rax, rdx
0x180004c6b  mov     r14, rcx
0x180004c6e  xor     r12d, r12d
0x180004c71  mov     [r8], r12d
0x180004c74  mov     [rbp+arg_10], r12d
0x180004c78  xor     dil, dil
0x180004c7b  mov     [rbp+var_50], r12
0x180004c7f  test    rdx, rdx
0x180004c82  jz      loc_180004E0B
0x180004c88  mov     [rbp+ppURI], r12
0x180004c8c  lea     r9, [rbp+ppURI]; ppURI
0x180004c90  xor     r8d, r8d; dwReserved
0x180004c93  mov     edx, 3002B80h; dwFlags
0x180004c98  mov     rcx, rax; pwzURI
0x180004c9b  call    cs:__imp_CreateUri
0x180004ca1  mov     esi, eax
0x180004ca3  test    eax, eax
0x180004ca5  jns     short loc_180004CB4
0x180004ca7  mov     r9d, eax
0x180004caa  mov     edx, 2B5h
0x180004caf  jmp     loc_180004DEB
0x180004cb4  mov     rcx, [rbp+ppURI]
0x180004cb8  mov     [rbp+bstrString], r12
0x180004cbc  lea     rdx, [rbp+bstrString]
0x180004cc0  mov     rax, [rcx]
0x180004cc3  mov     rax, [rax+98h]
0x180004cca  cmp     byte ptr [r14+91h], 0
0x180004cd2  jz      short loc_180004D24
0x180004cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd9  mov     r15, [rbp+bstrString]
0x180004cdd  test    eax, eax
0x180004cdf  jnz     short loc_180004D03
0x180004ce1  mov     r8d, 9; unsigned __int64
0x180004ce7  lea     rdx, off_1800B61A0; unsigned __int16 **
0x180004cee  mov     rcx, r15; unsigned __int16 *
0x180004cf1  call    ?_IsAsciiStringInList@CUriUtils@@CAHPEBGQEBQEBG_K@Z; CUriUtils::_IsAsciiStringInList(ushort const *,ushort const * const * const,unsigned __int64)
0x180004cf6  mov     esi, 80004004h
0x180004cfb  test    eax, eax
0x180004cfd  cmovnz  esi, r12d
0x180004d01  jmp     short loc_180004D08
0x180004d03  mov     esi, 8000FFFFh
0x180004d08  test    r15, r15
0x180004d0b  jz      short loc_180004D16
0x180004d0d  mov     rcx, r15; bstrString
0x180004d10  call    cs:__imp_SysFreeString
0x180004d16  test    esi, esi
0x180004d18  jns     short loc_180004D71
0x180004d1a  mov     edx, 2B8h
0x180004d1f  jmp     loc_180004DE8
0x180004d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d29  mov     r15, [rbp+bstrString]
0x180004d2d  test    eax, eax
0x180004d2f  jnz     short loc_180004D53
0x180004d31  mov     r8d, 8; unsigned __int64
0x180004d37  lea     rdx, off_1800B6160; unsigned __int16 **
0x180004d3e  mov     rcx, r15; unsigned __int16 *
0x180004d41  call    ?_IsAsciiStringInList@CUriUtils@@CAHPEBGQEBQEBG_K@Z; CUriUtils::_IsAsciiStringInList(ushort const *,ushort const * const * const,unsigned __int64)
0x180004d46  mov     esi, 80004004h
0x180004d4b  test    eax, eax
0x180004d4d  cmovnz  esi, r12d
0x180004d51  jmp     short loc_180004D58
0x180004d53  mov     esi, 8000FFFFh
0x180004d58  test    r15, r15
0x180004d5b  jz      short loc_180004D66
0x180004d5d  mov     rcx, r15; bstrString
0x180004d60  call    cs:__imp_SysFreeString
0x180004d66  test    esi, esi
0x180004d68  jns     short loc_180004D71
0x180004d6a  mov     edx, 2BCh
0x180004d6f  jmp     short loc_180004DE8
0x180004d71  mov     [rbp+arg_8], r12d
0x180004d75  mov     rcx, [r14+30h]
0x180004d79  mov     rax, [rcx]
0x180004d7c  lea     r8, [rbp+arg_8]
0x180004d80  mov     rdx, [rbp+ppURI]
0x180004d84  mov     rax, [rax+208h]
0x180004d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d90  mov     esi, eax
0x180004d92  test    eax, eax
0x180004d94  jns     short loc_180004DCB
0x180004d96  mov     rcx, [rbp+38h]; this
0x180004d9a  mov     r9d, eax; char *
0x180004d9d  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180004da4  mov     edx, 2C0h; void *
0x180004da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dae  nop
0x180004daf  mov     rcx, [rbp+ppURI]
0x180004db3  test    rcx, rcx
0x180004db6  jz      short loc_180004DC9
0x180004db8  mov     [rbp+ppURI], r12
0x180004dbc  mov     rax, [rcx]
0x180004dbf  mov     rax, [rax+10h]
0x180004dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc8  nop
0x180004dc9  jmp     short loc_180004E05
0x180004dcb  cmp     [rbp+arg_8], 0
0x180004dcf  jz      short loc_180004DDE
0x180004dd1  mov     rax, [rbp+ppURI]
0x180004dd5  mov     [rbp+var_50], rax
0x180004dd9  mov     esi, r12d
0x180004ddc  jmp     short loc_180004E05
0x180004dde  mov     esi, 80070057h
0x180004de3  mov     edx, 2C8h; void *
0x180004de8  mov     r9d, esi; char *
0x180004deb  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180004df2  mov     rcx, [rbp+38h]; this
0x180004df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dfb  nop
0x180004dfc  lea     rcx, [rbp+ppURI]
0x180004e00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180004e05  mov     [rbx], esi
0x180004e07  test    esi, esi
0x180004e09  js      short loc_180004E65
0x180004e0b  mov     [rbp+var_38], r12
0x180004e0f  mov     [rbp+var_30], r12
0x180004e13  mov     [rbp+var_28], r12
0x180004e17  mov     [rbp+var_1C], r12
0x180004e1b  mov     [rbp+var_14], r12d
0x180004e1f  mov     [rbp+var_8], r12
0x180004e23  mov     rax, [rbp+var_50]
0x180004e27  mov     [rbp+var_40], rax
0x180004e2b  mov     [rbp+var_20], r12d
0x180004e2f  mov     [rbp+var_10], r12
0x180004e33  mov     rcx, [r14+38h]
0x180004e37  mov     rax, [rcx]
0x180004e3a  lea     r9, [rbp+arg_10]
0x180004e3e  lea     r8, [rbp+var_40]
0x180004e42  mov     rdx, [r14+30h]
0x180004e46  mov     rax, [rax+18h]
0x180004e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4f  mov     [rbx], eax
0x180004e51  test    eax, eax
0x180004e53  js      short loc_180004E65
0x180004e55  movzx   edi, dil
0x180004e59  mov     eax, 1
0x180004e5e  cmp     [rbp+arg_10], 0
0x180004e62  cmovz   edi, eax
0x180004e65  mov     rcx, [rbp+var_50]
0x180004e69  test    rcx, rcx
0x180004e6c  jz      short loc_180004E7F
0x180004e6e  mov     [rbp+var_50], r12
0x180004e72  mov     rdx, [rcx]
0x180004e75  mov     rax, [rdx+10h]
0x180004e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e7e  nop
0x180004e7f  movzx   eax, dil
0x180004e83  add     rsp, 80h
0x180004e8a  pop     r15
0x180004e8c  pop     r14
0x180004e8e  pop     r12
0x180004e90  pop     rdi
0x180004e91  pop     rsi
0x180004e92  pop     rbx
0x180004e93  pop     rbp
0x180004e94  retn
```
