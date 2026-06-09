# XMLHttp2::_Open(ushort const *,ushort const *,IXMLHTTPRequest2Callback *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180095b10`
- end: `0x180095dea`
- name: `?_Open@XMLHttp2@@AEAAJPEBG0PEAUIXMLHTTPRequest2Callback@@0000@Z`
- size: `730`
- prototype: `HRESULT __fastcall(XMLHttp2 *this, const wchar_t *pwszMethod, const wchar_t *pwszUrl, IXMLHTTPRequest2Callback *pStatusCallback, const wchar_t *pwszUserName, const wchar_t *pwszPassword, const wchar_t *pwszProxyUserName, const wchar_t *pwszProxyPassword)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180095a20`

## callees

- `0x180095b10`
- `0x1800a3d34`
- `0x180141458`
- `0x180189008`
- `0x1801895d8`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095bdb`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c23`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c44`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c65`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c98`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c23`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c44`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c65`
- `OLEAUT32!__imp_SysAllocString` at `0x180095c98`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d49`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d69`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d78`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d49`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d69`
- `OLEAUT32!__imp_SysFreeString` at `0x180095d78`

## pseudocode

```c
__int64 __fastcall XMLHttp2::_Open(
        XMLHttp2 *this,
        const wchar_t *pwszMethod,
        const _GUID *pwszUrl,
        IXMLHTTPRequest2Callback *pStatusCallback,
        wchar_t *pwszUserName,
        wchar_t *pwszPassword,
        wchar_t *pwszProxyUserName,
        wchar_t *pwszProxyPassword)
{
  wchar_t *v8; // r13
  wchar_t *v9; // r15
  IXMLHTTPRequest2Callback *v11; // rax
  int v14; // ebx
  wchar_t *v15; // rsi
  BSTR v16; // rax
  BSTR v17; // rax
  XMLHttp *m_pXMLHttp; // rcx
  XMLHttp_vtbl *v19; // rax
  HRESULT (__fastcall *open)(IXMLHTTPRequest *, wchar_t *, wchar_t *, tagVARIANT, tagVARIANT, tagVARIANT); // rax
  wchar_t *bstrString; // [rsp+68h] [rbp-81h]
  tagVARIANT varPassword; // [rsp+70h] [rbp-79h] BYREF
  tagVARIANT varUserName; // [rsp+90h] [rbp-59h] BYREF
  tagVARIANT varAsync; // [rsp+B0h] [rbp-39h] BYREF
  IRecordInfo *v26; // [rsp+D0h] [rbp-19h]
  IRecordInfo *v27; // [rsp+D8h] [rbp-11h]
  IRecordInfo *v28; // [rsp+E0h] [rbp-9h]

  bstrString = 0;
  v8 = 0;
  v9 = 0;
  v11 = pStatusCallback;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  varAsync.0 = 0;
  varUserName.0 = 0;
  varPassword.0 = 0;
  if ( (xmmword_1801FAD20 & 2) != 0 )
  {
    WPP_SF_qSSqSSSS(
      (unsigned __int16)pwszProxyUserName,
      (unsigned __int16)pwszMethod,
      pwszUrl,
      this,
      pwszMethod,
      (const wchar_t *)pwszUrl,
      pStatusCallback,
      pwszUserName,
      pwszPassword,
      pwszProxyUserName,
      pwszProxyPassword);
    v11 = pStatusCallback;
  }
  if ( !pwszMethod || !pwszUrl || !v11 )
  {
    v14 = -2147024809;
LABEL_5:
    v15 = 0;
    goto $CleanUp_114;
  }
  if ( this->m_dwStaThreadId && this->m_dwStaThreadId != GetCurrentThreadId() )
  {
    v14 = -2147417842;
    goto LABEL_5;
  }
  if ( _InterlockedCompareExchange(&this->m_fOpened, 1, 0) )
  {
    v14 = -2147019873;
    goto LABEL_5;
  }
  varUserName.vt = 1;
  varAsync.vt = 11;
  varPassword.vt = 1;
  varAsync.iVal = -1;
  v15 = SysAllocString(pwszMethod);
  if ( !v15 )
    goto LABEL_14;
  bstrString = SysAllocString((const OLECHAR *)pwszUrl);
  if ( !bstrString )
    goto LABEL_14;
  if ( pwszUserName )
  {
    v16 = SysAllocString(pwszUserName);
    v8 = v16;
    if ( !v16 )
      goto LABEL_14;
    varUserName.llVal = (__int64)v16;
    varUserName.vt = 8;
  }
  if ( pwszPassword )
  {
    v17 = SysAllocString(pwszPassword);
    v9 = v17;
    if ( v17 )
    {
      varPassword.vt = 8;
      varPassword.llVal = (__int64)v17;
      goto LABEL_22;
    }
LABEL_14:
    v14 = -2147024882;
    goto $CleanUp_114;
  }
LABEL_22:
  m_pXMLHttp = this->m_pXMLHttp;
  v19 = m_pXMLHttp->_dispatchEx<IServerXMLHTTPRequest2,&LIBID_MSXML2,&IID_IServerXMLHTTPRequest2,0,0>::_dispatch<IServerXMLHTTPRequest2,&LIBID_MSXML2,&IID_IServerXMLHTTPRequest2,0>::IServerXMLHTTPRequest2::IServerXMLHTTPRequest::IXMLHTTPRequest::IDispatch::IUnknown::__vftable;
  varPassword.pRecInfo = v26;
  open = v19->open;
  varUserName.pRecInfo = v27;
  varAsync.pRecInfo = v28;
  v14 = ((__int64 (__fastcall *)(XMLHttp *, wchar_t *, wchar_t *, tagVARIANT *, tagVARIANT *, tagVARIANT *))open)(
          m_pXMLHttp,
          v15,
          bstrString,
          &varAsync,
          &varUserName,
          &varPassword);
  if ( v14 >= 0 )
  {
    v14 = XMLHttp::setStatusCallback(this->m_pXMLHttp, this, pStatusCallback);
    if ( v14 >= 0 )
      v14 = XMLHttp::setProxyCredentials(this->m_pXMLHttp, pwszProxyUserName, pwszProxyPassword);
  }
$CleanUp_114:
  SysFreeString(v15);
  SysFreeString(bstrString);
  SysFreeString(v8);
  SysFreeString(v9);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v14 >> 31) + 4].rgbFlags[0] & 2) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(v14 >> 31) + 2) << 9) | 1,
      0x8Au,
      WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids,
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180095b10  mov     [rsp-8+arg_0], rbx
0x180095b15  mov     [rsp-8+arg_18], pStatusCallback
0x180095b1a  push    rbp
0x180095b1b  push    rsi
0x180095b1c  push    rdi
0x180095b1d  push    r12
0x180095b1f  push    r13
0x180095b21  push    r14
0x180095b23  push    r15
0x180095b25  lea     rbp, [rsp-7]
0x180095b2a  sub     rsp, 0F0h
0x180095b31  xorps   xmm0, xmm0
0x180095b34  mov     [rsp+120h+bstrString], 0
0x180095b3d  xor     r13d, r13d
0x180095b40  xor     r15d, r15d
0x180095b43  mov     rdi, this
0x180095b46  xorps   xmm1, xmm1
0x180095b49  xor     ecx, ecx
0x180095b4b  mov     rax, pStatusCallback
0x180095b4e  mov     [rbp+37h+var_40], this
0x180095b52  mov     rbx, pwszUrl
0x180095b55  mov     [rbp+37h+var_48], this
0x180095b59  mov     rsi, pwszMethod
0x180095b5c  mov     [rbp+37h+var_50], this
0x180095b60  movups  xmmword ptr [rbp+37h+varAsync.___u0], xmm0
0x180095b64  movups  xmmword ptr [rbp+37h+varUserName.___u0], xmm1
0x180095b68  movups  xmmword ptr [rbp+37h+varPassword.___u0], xmm0
0x180095b6c  test    byte ptr cs:xmmword_1801FAD20, 2; __annotation("TMF:",
0x180095b73  mov     r12, [rbp+37h+arg_28]
0x180095b77  mov     r14, [rbp+37h+psz]
0x180095b7b  jz      short loc_180095BB4
0x180095b7d  mov     this, [rbp+37h+pcwszProxyPassword]
0x180095b81  mov     pStatusCallback, rdi; _a4
0x180095b84  mov     [rsp+120h+TraceGuid], this; TraceGuid
0x180095b89  mov     this, [rbp+37h+pcwszProxyUserName]; _a1
0x180095b8d  mov     [rsp+120h+id], this; id
0x180095b92  mov     [rsp+120h+LevelKeyword], r12; LevelKeyword
0x180095b97  mov     [rsp+120h+_a8], r14; _a8
0x180095b9c  mov     [rsp+120h+_a7], rax; _a7
0x180095ba1  mov     [rsp+120h+_a6], rbx; _a6
0x180095ba6  mov     [rsp+120h+_a5], pwszMethod; _a5
0x180095bab  call    WPP_SF_qSSqSSSS
0x180095bb0  mov     rax, [rbp+37h+arg_18]
0x180095bb4  mov     ecx, 1
0x180095bb9  test    rsi, rsi
0x180095bbc  jnz     short loc_180095BCB
0x180095bbe  mov     ebx, 80070057h
0x180095bc3  mov     rsi, r13
0x180095bc6  jmp     $CleanUp_114
0x180095bcb  test    rbx, rbx
0x180095bce  jz      short loc_180095BBE
0x180095bd0  test    rax, rax
0x180095bd3  jz      short loc_180095BBE
0x180095bd5  cmp     [rdi+30h], r13d
0x180095bd9  jz      short loc_180095BF8
0x180095bdb  call    cs:__imp_GetCurrentThreadId
0x180095be2  nop     dword ptr [rax+rax+00h]
0x180095be7  cmp     [rdi+30h], eax
0x180095bea  jz      short loc_180095BF3
0x180095bec  mov     ebx, 8001010Eh
0x180095bf1  jmp     short loc_180095BC3
0x180095bf3  mov     ecx, 1
0x180095bf8  xor     eax, eax
0x180095bfa  lock cmpxchg [rdi+24h], ecx
0x180095bff  jz      short loc_180095C08
0x180095c01  mov     ebx, 8007139Fh
0x180095c06  jmp     short loc_180095BC3
0x180095c08  mov     eax, 0Bh
0x180095c0d  mov     word ptr [rbp+37h+varUserName.___u0], cx
0x180095c11  mov     word ptr [rbp+37h+varAsync.___u0], ax
0x180095c15  or      eax, 0FFFFFFFFh
0x180095c18  mov     word ptr [rbp+37h+varPassword.___u0], cx
0x180095c1c  mov     this, rsi; psz
0x180095c1f  mov     word ptr [rbp+37h+varAsync.___u0+8], ax
0x180095c23  call    cs:__imp_SysAllocString
0x180095c2a  nop     dword ptr [rax+rax+00h]
0x180095c2f  mov     rsi, rax
0x180095c32  test    rax, rax
0x180095c35  jnz     short loc_180095C41
0x180095c37  mov     ebx, 8007000Eh
0x180095c3c  jmp     $CleanUp_114
0x180095c41  mov     this, rbx; psz
0x180095c44  call    cs:__imp_SysAllocString
0x180095c4b  nop     dword ptr [rax+rax+00h]
0x180095c50  mov     [rsp+120h+bstrString], rax
0x180095c55  mov     rbx, rax
0x180095c58  test    rax, rax
0x180095c5b  jz      short loc_180095C37
0x180095c5d  test    r14, r14
0x180095c60  jz      short loc_180095C8A
0x180095c62  mov     this, r14; psz
0x180095c65  call    cs:__imp_SysAllocString
0x180095c6c  nop     dword ptr [rax+rax+00h]
0x180095c71  mov     r13, rax
0x180095c74  test    rax, rax
0x180095c77  jz      short loc_180095C37
0x180095c79  mov     r14d, 8
0x180095c7f  mov     qword ptr [rbp+37h+varUserName.___u0+8], rax
0x180095c83  mov     word ptr [rbp+37h+varUserName.___u0], r14w
0x180095c88  jmp     short loc_180095C90
0x180095c8a  mov     r14d, 8
0x180095c90  test    r12, r12
0x180095c93  jz      short loc_180095CB5
0x180095c95  mov     this, r12; psz
0x180095c98  call    cs:__imp_SysAllocString
0x180095c9f  nop     dword ptr [rax+rax+00h]
0x180095ca4  mov     r15, rax
0x180095ca7  test    rax, rax
0x180095caa  jz      short loc_180095C37
0x180095cac  mov     word ptr [rbp+37h+varPassword.___u0], r14w
0x180095cb1  mov     qword ptr [rbp+37h+varPassword.___u0+8], rax
0x180095cb5  movups  xmm0, xmmword ptr [rbp+37h+varPassword.___u0]
0x180095cb9  lea     pwszMethod, [rbp+37h+varPassword]
0x180095cbd  mov     this, [rdi+28h]
0x180095cc1  movsd   xmm1, [rbp+37h+var_50]
0x180095cc6  lea     pStatusCallback, [rbp+37h+varAsync]
0x180095cca  mov     [rsp+120h+_a6], pwszMethod
0x180095ccf  mov     pwszUrl, rbx
0x180095cd2  movaps  xmmword ptr [rbp+37h+varPassword.___u0], xmm0
0x180095cd6  lea     pwszMethod, [rbp+37h+varUserName]
0x180095cda  movups  xmm0, xmmword ptr [rbp+37h+varUserName.___u0]
0x180095cde  mov     rax, [this]
0x180095ce1  movsd   [rbp+37h+varPassword.pRecInfo], xmm1
0x180095ce6  movsd   xmm1, [rbp+37h+var_48]
0x180095ceb  movaps  xmmword ptr [rbp+37h+varUserName.___u0], xmm0
0x180095cef  movups  xmm0, xmmword ptr [rbp+37h+varAsync.___u0]
0x180095cf3  mov     rax, [rax+38h]
0x180095cf7  movsd   [rbp+37h+varUserName.pRecInfo], xmm1
0x180095cfc  movsd   xmm1, [rbp+37h+var_40]
0x180095d01  mov     [rsp+120h+_a5], pwszMethod
0x180095d06  mov     pwszMethod, rsi
0x180095d09  movaps  xmmword ptr [rbp+37h+varAsync.___u0], xmm0
0x180095d0d  movsd   [rbp+37h+varAsync.pRecInfo], xmm1
0x180095d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095d17  mov     ebx, eax
0x180095d19  test    eax, eax
0x180095d1b  js      short $CleanUp_114
0x180095d1d  mov     pwszUrl, [rbp+37h+arg_18]; pStatusCallback
0x180095d21  mov     pwszMethod, rdi; pXhr
0x180095d24  mov     this, [rdi+28h]; this
0x180095d28  call    ?setStatusCallback@XMLHttp@@QEAAJPEAUIXMLHTTPRequest2@@PEAUIXMLHTTPRequest2Callback@@@Z; XMLHttp::setStatusCallback(IXMLHTTPRequest2 *,IXMLHTTPRequest2Callback *)
0x180095d2d  mov     ebx, eax
0x180095d2f  test    eax, eax
0x180095d31  js      short $CleanUp_114
0x180095d33  mov     pwszUrl, [rbp+37h+pcwszProxyPassword]; pcwszProxyPassword
0x180095d37  mov     pwszMethod, [rbp+37h+pcwszProxyUserName]; pcwszProxyUserName
0x180095d3b  mov     this, [rdi+28h]; this
0x180095d3f  call    ?setProxyCredentials@XMLHttp@@QEAAJPEBG0@Z; XMLHttp::setProxyCredentials(ushort const *,ushort const *)
0x180095d44  mov     ebx, eax
0x180095d46  mov     this, rsi; bstrString
0x180095d49  call    cs:__imp_SysFreeString
0x180095d50  nop     dword ptr [rax+rax+00h]
0x180095d55  mov     this, [rsp+120h+bstrString]; bstrString
0x180095d5a  call    cs:__imp_SysFreeString
0x180095d61  nop     dword ptr [rax+rax+00h]
0x180095d66  mov     this, r13; bstrString
0x180095d69  call    cs:__imp_SysFreeString
0x180095d70  nop     dword ptr [rax+rax+00h]
0x180095d75  mov     this, r15; bstrString
0x180095d78  call    cs:__imp_SysFreeString
0x180095d7f  nop     dword ptr [rax+rax+00h]
0x180095d84  mov     r8d, ebx; __annotation("TMF:",
0x180095d87  sar     r8d, 1Fh
0x180095d8b  lea     eax, ds:4[pwszUrl*2]
0x180095d93  movsxd  this, eax
0x180095d96  lea     rax, g_rgFastWppLevelEnabledFlags
0x180095d9d  test    byte ptr [rax+this*8], 2
0x180095da1  jz      short loc_180095DCC
0x180095da3  add     r8w, 2
0x180095da8  mov     eax, 200h
0x180095dad  movzx   ecx, r8w
0x180095db1  mov     edx, 8Ah; id
0x180095db6  imul    ecx, eax
0x180095db9  lea     pwszUrl, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x180095dc0  mov     r9d, ebx; _a1
0x180095dc3  or      cx, 1; LevelKeyword
0x180095dc7  call    WPP_SF_d
0x180095dcc  mov     eax, ebx
0x180095dce  mov     rbx, [rsp+120h+arg_0]
0x180095dd6  add     rsp, 0F0h
0x180095ddd  pop     r15
0x180095ddf  pop     r14
0x180095de1  pop     r13
0x180095de3  pop     r12
0x180095de5  pop     rdi
0x180095de6  pop     rsi
0x180095de7  pop     rbp
0x180095de8  retn
```
