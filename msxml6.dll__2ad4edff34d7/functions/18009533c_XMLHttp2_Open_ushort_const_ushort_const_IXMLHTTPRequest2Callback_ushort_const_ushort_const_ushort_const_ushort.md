# XMLHttp2::_Open(ushort const *,ushort const *,IXMLHTTPRequest2Callback *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18009533c`
- end: `0x1800955df`
- name: `?_Open@XMLHttp2@@AEAAJPEBG0PEAUIXMLHTTPRequest2Callback@@0000@Z`
- size: `675`
- prototype: `__int64 __fastcall(XMLHttp2 *this, const wchar_t *pwszMethod, const _GUID *pwszUrl, IXMLHTTPRequest2Callback *pStatusCallback, wchar_t *pwszUserName, wchar_t *pwszPassword, wchar_t *pwszProxyUserName, wchar_t *pwszProxyPassword)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180095250`

## callees

- `0x18009533c`
- `0x1800a38b8`
- `0x18013e288`
- `0x180185008`
- `0x1801855cc`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095407`
- `OLEAUT32!__imp_SysAllocString` at `0x180095449`
- `OLEAUT32!__imp_SysAllocString` at `0x180095464`
- `OLEAUT32!__imp_SysAllocString` at `0x18009547f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800954ac`
- `OLEAUT32!__imp_SysAllocString` at `0x180095449`
- `OLEAUT32!__imp_SysAllocString` at `0x180095464`
- `OLEAUT32!__imp_SysAllocString` at `0x18009547f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800954ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180095557`
- `OLEAUT32!__imp_SysFreeString` at `0x180095562`
- `OLEAUT32!__imp_SysFreeString` at `0x18009556b`
- `OLEAUT32!__imp_SysFreeString` at `0x180095574`
- `OLEAUT32!__imp_SysFreeString` at `0x180095557`
- `OLEAUT32!__imp_SysFreeString` at `0x180095562`
- `OLEAUT32!__imp_SysFreeString` at `0x18009556b`
- `OLEAUT32!__imp_SysFreeString` at `0x180095574`

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
  if ( (xmmword_1801F6C20 & 2) != 0 )
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
    goto $CleanUp_115;
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
    goto $CleanUp_115;
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
$CleanUp_115:
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
0x18009533c  mov     [rsp-8+arg_0], rbx
0x180095341  mov     [rsp-8+arg_18], pStatusCallback
0x180095346  push    rbp
0x180095347  push    rsi
0x180095348  push    rdi
0x180095349  push    r12
0x18009534b  push    r13
0x18009534d  push    r14
0x18009534f  push    r15
0x180095351  lea     rbp, [rsp-7]
0x180095356  sub     rsp, 0F0h
0x18009535d  xorps   xmm0, xmm0
0x180095360  mov     [rsp+120h+bstrString], 0
0x180095369  xor     r13d, r13d
0x18009536c  xor     r15d, r15d
0x18009536f  mov     rdi, this
0x180095372  xorps   xmm1, xmm1
0x180095375  xor     ecx, ecx
0x180095377  mov     rax, pStatusCallback
0x18009537a  mov     [rbp+37h+var_40], this
0x18009537e  mov     rbx, pwszUrl
0x180095381  mov     [rbp+37h+var_48], this
0x180095385  mov     rsi, pwszMethod
0x180095388  mov     [rbp+37h+var_50], this
0x18009538c  movups  xmmword ptr [rbp+37h+varAsync.___u0], xmm0
0x180095390  movups  xmmword ptr [rbp+37h+varUserName.___u0], xmm1
0x180095394  movups  xmmword ptr [rbp+37h+varPassword.___u0], xmm0
0x180095398  test    byte ptr cs:xmmword_1801F6C20, 2; __annotation("TMF:",
0x18009539f  mov     r12, [rbp+37h+arg_28]
0x1800953a3  mov     r14, [rbp+37h+psz]
0x1800953a7  jz      short loc_1800953E0
0x1800953a9  mov     this, [rbp+37h+pcwszProxyPassword]
0x1800953ad  mov     pStatusCallback, rdi; _a4
0x1800953b0  mov     [rsp+120h+TraceGuid], this; TraceGuid
0x1800953b5  mov     this, [rbp+37h+pcwszProxyUserName]; _a1
0x1800953b9  mov     [rsp+120h+id], this; id
0x1800953be  mov     [rsp+120h+LevelKeyword], r12; LevelKeyword
0x1800953c3  mov     [rsp+120h+_a8], r14; _a8
0x1800953c8  mov     [rsp+120h+_a7], rax; _a7
0x1800953cd  mov     [rsp+120h+_a6], rbx; _a6
0x1800953d2  mov     [rsp+120h+_a5], pwszMethod; _a5
0x1800953d7  call    WPP_SF_qSSqSSSS
0x1800953dc  mov     rax, [rbp+37h+arg_18]
0x1800953e0  mov     ecx, 1
0x1800953e5  test    rsi, rsi
0x1800953e8  jnz     short loc_1800953F7
0x1800953ea  mov     ebx, 80070057h
0x1800953ef  mov     rsi, r13
0x1800953f2  jmp     $CleanUp_115
0x1800953f7  test    rbx, rbx
0x1800953fa  jz      short loc_1800953EA
0x1800953fc  test    rax, rax
0x1800953ff  jz      short loc_1800953EA
0x180095401  cmp     [rdi+30h], r13d
0x180095405  jz      short loc_18009541E
0x180095407  call    cs:__imp_GetCurrentThreadId
0x18009540d  cmp     [rdi+30h], eax
0x180095410  jz      short loc_180095419
0x180095412  mov     ebx, 8001010Eh
0x180095417  jmp     short loc_1800953EF
0x180095419  mov     ecx, 1
0x18009541e  xor     eax, eax
0x180095420  lock cmpxchg [rdi+24h], ecx
0x180095425  jz      short loc_18009542E
0x180095427  mov     ebx, 8007139Fh
0x18009542c  jmp     short loc_1800953EF
0x18009542e  mov     eax, 0Bh
0x180095433  mov     word ptr [rbp+37h+varUserName.___u0], cx
0x180095437  mov     word ptr [rbp+37h+varAsync.___u0], ax
0x18009543b  or      eax, 0FFFFFFFFh
0x18009543e  mov     word ptr [rbp+37h+varPassword.___u0], cx
0x180095442  mov     this, rsi; psz
0x180095445  mov     word ptr [rbp+37h+varAsync.___u0+8], ax
0x180095449  call    cs:__imp_SysAllocString
0x18009544f  mov     rsi, rax
0x180095452  test    rax, rax
0x180095455  jnz     short loc_180095461
0x180095457  mov     ebx, 8007000Eh
0x18009545c  jmp     $CleanUp_115
0x180095461  mov     this, rbx; psz
0x180095464  call    cs:__imp_SysAllocString
0x18009546a  mov     [rsp+120h+bstrString], rax
0x18009546f  mov     rbx, rax
0x180095472  test    rax, rax
0x180095475  jz      short loc_180095457
0x180095477  test    r14, r14
0x18009547a  jz      short loc_18009549E
0x18009547c  mov     this, r14; psz
0x18009547f  call    cs:__imp_SysAllocString
0x180095485  mov     r13, rax
0x180095488  test    rax, rax
0x18009548b  jz      short loc_180095457
0x18009548d  mov     r14d, 8
0x180095493  mov     qword ptr [rbp+37h+varUserName.___u0+8], rax
0x180095497  mov     word ptr [rbp+37h+varUserName.___u0], r14w
0x18009549c  jmp     short loc_1800954A4
0x18009549e  mov     r14d, 8
0x1800954a4  test    r12, r12
0x1800954a7  jz      short loc_1800954C3
0x1800954a9  mov     this, r12; psz
0x1800954ac  call    cs:__imp_SysAllocString
0x1800954b2  mov     r15, rax
0x1800954b5  test    rax, rax
0x1800954b8  jz      short loc_180095457
0x1800954ba  mov     word ptr [rbp+37h+varPassword.___u0], r14w
0x1800954bf  mov     qword ptr [rbp+37h+varPassword.___u0+8], rax
0x1800954c3  movups  xmm0, xmmword ptr [rbp+37h+varPassword.___u0]
0x1800954c7  lea     pwszMethod, [rbp+37h+varPassword]
0x1800954cb  mov     this, [rdi+28h]
0x1800954cf  movsd   xmm1, [rbp+37h+var_50]
0x1800954d4  lea     pStatusCallback, [rbp+37h+varAsync]
0x1800954d8  mov     [rsp+120h+_a6], pwszMethod
0x1800954dd  mov     pwszUrl, rbx
0x1800954e0  movaps  xmmword ptr [rbp+37h+varPassword.___u0], xmm0
0x1800954e4  lea     pwszMethod, [rbp+37h+varUserName]
0x1800954e8  movups  xmm0, xmmword ptr [rbp+37h+varUserName.___u0]
0x1800954ec  mov     rax, [this]
0x1800954ef  movsd   [rbp+37h+varPassword.pRecInfo], xmm1
0x1800954f4  movsd   xmm1, [rbp+37h+var_48]
0x1800954f9  movaps  xmmword ptr [rbp+37h+varUserName.___u0], xmm0
0x1800954fd  movups  xmm0, xmmword ptr [rbp+37h+varAsync.___u0]
0x180095501  mov     rax, [rax+38h]
0x180095505  movsd   [rbp+37h+varUserName.pRecInfo], xmm1
0x18009550a  movsd   xmm1, [rbp+37h+var_40]
0x18009550f  mov     [rsp+120h+_a5], pwszMethod
0x180095514  mov     pwszMethod, rsi
0x180095517  movaps  xmmword ptr [rbp+37h+varAsync.___u0], xmm0
0x18009551b  movsd   [rbp+37h+varAsync.pRecInfo], xmm1
0x180095520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095525  mov     ebx, eax
0x180095527  test    eax, eax
0x180095529  js      short $CleanUp_115
0x18009552b  mov     pwszUrl, [rbp+37h+arg_18]; pStatusCallback
0x18009552f  mov     pwszMethod, rdi; pXhr
0x180095532  mov     this, [rdi+28h]; this
0x180095536  call    ?setStatusCallback@XMLHttp@@QEAAJPEAUIXMLHTTPRequest2@@PEAUIXMLHTTPRequest2Callback@@@Z; XMLHttp::setStatusCallback(IXMLHTTPRequest2 *,IXMLHTTPRequest2Callback *)
0x18009553b  mov     ebx, eax
0x18009553d  test    eax, eax
0x18009553f  js      short $CleanUp_115
0x180095541  mov     pwszUrl, [rbp+37h+pcwszProxyPassword]; pcwszProxyPassword
0x180095545  mov     pwszMethod, [rbp+37h+pcwszProxyUserName]; pcwszProxyUserName
0x180095549  mov     this, [rdi+28h]; this
0x18009554d  call    ?setProxyCredentials@XMLHttp@@QEAAJPEBG0@Z; XMLHttp::setProxyCredentials(ushort const *,ushort const *)
0x180095552  mov     ebx, eax
0x180095554  mov     this, rsi; bstrString
0x180095557  call    cs:__imp_SysFreeString
0x18009555d  mov     this, [rsp+120h+bstrString]; bstrString
0x180095562  call    cs:__imp_SysFreeString
0x180095568  mov     this, r13; bstrString
0x18009556b  call    cs:__imp_SysFreeString
0x180095571  mov     this, r15; bstrString
0x180095574  call    cs:__imp_SysFreeString
0x18009557a  mov     r8d, ebx; __annotation("TMF:",
0x18009557d  sar     r8d, 1Fh
0x180095581  lea     eax, ds:4[pwszUrl*2]
0x180095589  movsxd  this, eax
0x18009558c  lea     rax, g_rgFastWppLevelEnabledFlags
0x180095593  test    byte ptr [rax+this*8], 2
0x180095597  jz      short loc_1800955C2
0x180095599  add     r8w, 2
0x18009559e  mov     eax, 200h
0x1800955a3  movzx   ecx, r8w
0x1800955a7  mov     edx, 8Ah; id
0x1800955ac  imul    ecx, eax
0x1800955af  lea     pwszUrl, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1800955b6  mov     r9d, ebx; _a1
0x1800955b9  or      cx, 1; LevelKeyword
0x1800955bd  call    WPP_SF_d
0x1800955c2  mov     eax, ebx
0x1800955c4  mov     rbx, [rsp+120h+arg_0]
0x1800955cc  add     rsp, 0F0h
0x1800955d3  pop     r15
0x1800955d5  pop     r14
0x1800955d7  pop     r13
0x1800955d9  pop     r12
0x1800955db  pop     rdi
0x1800955dc  pop     rsi
0x1800955dd  pop     rbp
0x1800955de  retn
```
