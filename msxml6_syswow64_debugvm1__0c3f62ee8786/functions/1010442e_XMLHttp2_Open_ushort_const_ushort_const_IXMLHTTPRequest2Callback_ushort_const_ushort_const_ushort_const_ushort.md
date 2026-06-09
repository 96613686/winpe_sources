# XMLHttp2::_Open(ushort const *,ushort const *,IXMLHTTPRequest2Callback *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1010442e`
- end: `0x1010464f`
- name: `?_Open@XMLHttp2@@AAGJPBG0PAUIXMLHTTPRequest2Callback@@0000@Z`
- size: `545`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, const wchar_t *pwszMethod@<edx>, const wchar_t *pwszUrl, IXMLHTTPRequest2Callback *pStatusCallback, const wchar_t *pwszUserName, const wchar_t *pwszPassword, const wchar_t *pwszProxyUserName, const wchar_t *pwszProxyPassword)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10102bf0`

## callees

- `0x10067bc0`
- `0x1010442e`
- `0x10106ee2`
- `0x101071b8`
- `0x10180006`
- `0x101803ae`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101044c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101044c1`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104513`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010452e`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104548`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010456a`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104513`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010452e`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104548`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010456a`
- `OLEAUT32!__imp__SysFreeString@4` at `0x101045f4`
- `OLEAUT32!__imp__SysFreeString@4` at `0x101045fe`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104608`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104612`
- `OLEAUT32!__imp__SysFreeString@4` at `0x101045f4`
- `OLEAUT32!__imp__SysFreeString@4` at `0x101045fe`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104608`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104612`

## pseudocode

```c
HRESULT __fastcall XMLHttp2::_Open(
        XMLHttp2 *this,
        const _GUID *pwszMethod,
        const wchar_t *pwszUrl,
        IXMLHTTPRequest2Callback *pStatusCallback,
        const wchar_t *pwszUserName,
        const wchar_t *pwszPassword,
        const wchar_t *pwszProxyUserName,
        const wchar_t *pwszProxyPassword)
{
  const OLECHAR *v9; // esi
  int v10; // esi
  unsigned int m_dwStaThreadId; // esi
  BSTR v12; // eax
  BSTR v13; // eax
  const wchar_t *v15; // [esp+2Ch] [ebp-58h]
  const wchar_t *v16; // [esp+30h] [ebp-54h]
  wchar_t *bstrString; // [esp+3Ch] [ebp-48h]
  wchar_t *v18; // [esp+40h] [ebp-44h]
  wchar_t *v19; // [esp+44h] [ebp-40h]
  wchar_t *v20; // [esp+48h] [ebp-3Ch]
  int varPassword; // [esp+54h] [ebp-30h]
  BSTR varPassword_8; // [esp+5Ch] [ebp-28h]
  int varUserName; // [esp+64h] [ebp-20h]
  BSTR varUserName_8; // [esp+6Ch] [ebp-18h]
  int varAsync; // [esp+74h] [ebp-10h]
  int varAsync_8; // [esp+7Ch] [ebp-8h]

  HIWORD(varAsync) = 0;
  v9 = (const OLECHAR *)pwszMethod;
  bstrString = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  HIWORD(varAsync_8) = 0;
  HIWORD(varUserName) = 0;
  varUserName_8 = 0;
  HIWORD(varPassword) = 0;
  varPassword_8 = 0;
  if ( (byte_101857A0[0] & 2) != 0 )
    WPP_SF_qSSqSSSS(
      0,
      (unsigned __int16)this,
      pwszMethod,
      pwszUrl,
      (const wchar_t *)pStatusCallback,
      pwszUserName,
      pwszPassword,
      pwszProxyUserName,
      pwszProxyPassword,
      v15,
      v16);
  if ( !v9 || !pwszUrl || !pStatusCallback )
  {
    v10 = -2147024809;
    goto CleanUp_378;
  }
  if ( this->m_dwStaThreadId )
  {
    m_dwStaThreadId = this->m_dwStaThreadId;
    if ( m_dwStaThreadId != GetCurrentThreadId() )
    {
      v10 = -2147417842;
      goto CleanUp_378;
    }
    v9 = (const OLECHAR *)pwszMethod;
  }
  if ( _InterlockedCompareExchange(&this->m_fOpened, 1, 0) )
  {
    v10 = -2147019873;
    goto CleanUp_378;
  }
  LOWORD(varAsync) = 11;
  LOWORD(varAsync_8) = -1;
  LOWORD(varUserName) = 1;
  LOWORD(varPassword) = 1;
  bstrString = SysAllocString(v9);
  if ( !bstrString )
    goto LABEL_14;
  v18 = SysAllocString(pwszUrl);
  if ( !v18 )
    goto LABEL_14;
  if ( pwszUserName )
  {
    v12 = SysAllocString(pwszUserName);
    v19 = v12;
    if ( !v12 )
      goto LABEL_14;
    LOWORD(varUserName) = 8;
    varUserName_8 = v12;
  }
  if ( pwszPassword )
  {
    v13 = SysAllocString(pwszPassword);
    v20 = v13;
    if ( v13 )
    {
      LOWORD(varPassword) = 8;
      varPassword_8 = v13;
      goto LABEL_22;
    }
LABEL_14:
    v10 = -2147024882;
    goto CleanUp_378;
  }
LABEL_22:
  v10 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLHTTPRequest *, wchar_t *, wchar_t *, tagVARIANT, tagVARIANT, tagVARIANT), XMLHttp *, wchar_t *, wchar_t *, int, _DWORD, int, _DWORD, int, _DWORD, BSTR, _DWORD, int, _DWORD, BSTR, _DWORD))this->m_pXMLHttp->open)(
          this->m_pXMLHttp->open,
          this->m_pXMLHttp,
          bstrString,
          v18,
          varAsync,
          0,
          varAsync_8,
          0,
          varUserName,
          0,
          varUserName_8,
          0,
          varPassword,
          0,
          varPassword_8,
          0);
  if ( v10 >= 0 )
  {
    v10 = XMLHttp::setStatusCallback(this->m_pXMLHttp, this, pStatusCallback);
    if ( v10 >= 0 )
      v10 = XMLHttp::setProxyCredentials(this->m_pXMLHttp, pwszProxyUserName, pwszProxyPassword);
  }
CleanUp_378:
  SysFreeString(bstrString);
  SysFreeString(v18);
  SysFreeString(v19);
  SysFreeString(v20);
  if ( (byte_101857A0[16 * (v10 >> 31)] & 2) != 0 )
    WPP_SF_q(
      (((unsigned __int16)(v10 >> 31) + 2) << 9) | 1,
      0x8Au,
      WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids,
      v10);
  return v10;
}

```

## disassembly

```asm
0x1010442e  mov     edi, edi
0x10104430  push    ebp
0x10104431  mov     ebp, esp
0x10104433  and     esp, 0FFFFFFF8h
0x10104436  sub     esp, 4Ch
0x10104439  xor     eax, eax
0x1010443b  push    ebx
0x1010443c  push    esi; TraceGuid
0x1010443d  push    edi; id
0x1010443e  lea     edi, [esp+58h+varAsync]
0x10104442  mov     ebx, this
0x10104444  stosd
0x10104445  xor     this, this
0x10104447  mov     esi, pwszMethod
0x10104449  mov     [esp+58h+pXhr], ebx
0x1010444d  mov     [esp+58h+var_38], esi
0x10104451  mov     [esp+58h+bstrString], this
0x10104455  stosd
0x10104456  mov     [esp+58h+var_44], this
0x1010445a  mov     [esp+58h+var_40], this
0x1010445e  mov     [esp+58h+var_3C], this
0x10104462  stosd
0x10104463  stosd
0x10104464  xor     eax, eax
0x10104466  lea     edi, [esp+58h+varUserName]
0x1010446a  stosd
0x1010446b  stosd
0x1010446c  stosd
0x1010446d  stosd
0x1010446e  xor     eax, eax
0x10104470  lea     edi, [esp+58h+varPassword]
0x10104474  stosd
0x10104475  stosd
0x10104476  stosd
0x10104477  stosd
0x10104478  test    byte_101857A0, 2; __annotation("TMF:",
0x1010447f  mov     edi, [ebp+pwszUrl]
0x10104482  jz      short loc_1010449E
0x10104484  push    [ebp+pwszProxyPassword]; LevelKeyword
0x10104487  push    [ebp+pwszProxyUserName]; _a8
0x1010448a  push    [ebp+pwszPassword]; _a7
0x1010448d  push    [ebp+pwszUserName]; _a6
0x10104490  push    [ebp+pStatusCallback]; _a5
0x10104493  push    edi; _a4
0x10104494  push    esi; _a3
0x10104495  push    ebx; _a2
0x10104496  push    this; _a1
0x10104497  call    _WPP_SF_qSSqSSSS@44; WPP_SF_qSSqSSSS(x,x,x,x,x,x,x,x,x,x,x)
0x1010449c  xor     this, this
0x1010449e  xor     eax, eax
0x101044a0  inc     eax
0x101044a1  test    esi, esi
0x101044a3  jnz     short loc_101044AF
0x101044a5  mov     esi, 80070057h
0x101044aa  jmp     CleanUp_378
0x101044af  test    edi, edi
0x101044b1  jz      short loc_101044A5
0x101044b3  cmp     [ebp+pStatusCallback], 0
0x101044b7  jz      short loc_101044A5
0x101044b9  cmp     [ebx+1Ch], this
0x101044bc  jz      short loc_101044DC
0x101044be  mov     esi, [ebx+1Ch]
0x101044c1  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x101044c7  cmp     esi, eax
0x101044c9  jz      short loc_101044D5
0x101044cb  mov     esi, 8001010Eh
0x101044d0  jmp     CleanUp_378
0x101044d5  mov     esi, [esp+58h+var_38]
0x101044d9  xor     eax, eax
0x101044db  inc     eax
0x101044dc  mov     pwszMethod, eax
0x101044de  lea     this, [ebx+14h]
0x101044e1  xor     eax, eax
0x101044e3  lock cmpxchg [this], pwszMethod
0x101044e7  test    eax, eax
0x101044e9  jz      short loc_101044F5
0x101044eb  mov     esi, 8007139Fh
0x101044f0  jmp     CleanUp_378
0x101044f5  push    0Bh
0x101044f7  pop     eax
0x101044f8  mov     word ptr [esp+58h+varAsync.___u0], ax
0x101044fd  or      eax, 0FFFFFFFFh
0x10104500  mov     word ptr [esp+58h+varAsync.___u0+8], ax
0x10104505  xor     eax, eax
0x10104507  inc     eax
0x10104508  push    esi; psz
0x10104509  mov     word ptr [esp+5Ch+varUserName.___u0], ax
0x1010450e  mov     word ptr [esp+5Ch+varPassword.___u0], ax
0x10104513  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104519  mov     esi, eax
0x1010451b  mov     [esp+58h+bstrString], esi
0x1010451f  test    esi, esi
0x10104521  jnz     short loc_1010452D
0x10104523  mov     esi, 8007000Eh
0x10104528  jmp     CleanUp_378
0x1010452d  push    edi; psz
0x1010452e  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104534  mov     [esp+58h+var_44], eax
0x10104538  test    eax, eax
0x1010453a  jz      short loc_10104523
0x1010453c  cmp     [ebp+pwszUserName], 0
0x10104540  push    8
0x10104542  pop     edi
0x10104543  jz      short loc_10104561
0x10104545  push    [ebp+pwszUserName]; psz
0x10104548  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1010454e  mov     esi, eax
0x10104550  mov     [esp+58h+var_40], esi
0x10104554  test    esi, esi
0x10104556  jz      short loc_10104523
0x10104558  mov     word ptr [esp+58h+varUserName.___u0], di
0x1010455d  mov     dword ptr [esp+58h+varUserName.___u0+8], esi
0x10104561  cmp     [ebp+pwszPassword], 0
0x10104565  jz      short loc_10104581
0x10104567  push    [ebp+pwszPassword]; psz
0x1010456a  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104570  mov     [esp+58h+var_3C], eax
0x10104574  test    eax, eax
0x10104576  jz      short loc_10104523
0x10104578  mov     word ptr [esp+58h+varPassword.___u0], di
0x1010457d  mov     dword ptr [esp+58h+varPassword.___u0+8], eax
0x10104581  sub     esp, 10h
0x10104584  mov     this, [ebx+18h]
0x10104587  mov     edi, esp
0x10104589  lea     esi, [esp+68h+varPassword]
0x1010458d  sub     esp, 10h
0x10104590  mov     eax, [this]
0x10104592  movsd
0x10104593  mov     ebx, [eax+1Ch]
0x10104596  movsd
0x10104597  movsd
0x10104598  movsd
0x10104599  mov     edi, esp
0x1010459b  lea     esi, [esp+78h+varUserName]
0x1010459f  sub     esp, 10h
0x101045a2  movsd
0x101045a3  movsd
0x101045a4  movsd
0x101045a5  movsd
0x101045a6  mov     edi, esp
0x101045a8  lea     esi, [esp+88h+varAsync]
0x101045ac  push    [esp+88h+var_44]
0x101045b0  push    [esp+8Ch+bstrString]
0x101045b4  movsd
0x101045b5  push    this
0x101045b6  mov     this, ebx; this
0x101045b8  movsd
0x101045b9  movsd
0x101045ba  movsd
0x101045bb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101045c1  call    ebx
0x101045c3  mov     esi, eax
0x101045c5  test    esi, esi
0x101045c7  js      short CleanUp_378
0x101045c9  mov     edi, [esp+58h+pXhr]
0x101045cd  mov     pwszMethod, edi; pXhr
0x101045cf  push    [ebp+pStatusCallback]; pStatusCallback
0x101045d2  mov     this, [edi+18h]; this
0x101045d5  call    ?setStatusCallback@XMLHttp@@QAGJPAUIXMLHTTPRequest2@@PAUIXMLHTTPRequest2Callback@@@Z; XMLHttp::setStatusCallback(IXMLHTTPRequest2 *,IXMLHTTPRequest2Callback *)
0x101045da  mov     esi, eax
0x101045dc  test    esi, esi
0x101045de  js      short CleanUp_378
0x101045e0  push    [ebp+pwszProxyPassword]; pcwszProxyPassword
0x101045e3  mov     pwszMethod, [ebp+pwszProxyUserName]; pcwszProxyUserName
0x101045e6  mov     this, [edi+18h]; this
0x101045e9  call    ?setProxyCredentials@XMLHttp@@QAGJPBG0@Z; XMLHttp::setProxyCredentials(ushort const *,ushort const *)
0x101045ee  mov     esi, eax
0x101045f0  push    [esp+58h+bstrString]; bstrString
0x101045f4  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x101045fa  push    [esp+58h+var_44]; bstrString
0x101045fe  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104604  push    [esp+58h+var_40]; bstrString
0x10104608  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1010460e  push    [esp+58h+var_3C]; bstrString
0x10104612  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104618  mov     this, esi; __annotation("TMF:",
0x1010461a  sar     this, 1Fh
0x1010461d  mov     eax, this
0x1010461f  shl     eax, 4
0x10104622  test    byte_101857A0[eax], 2
0x10104629  jz      short loc_10104644
0x1010462b  add     this, 2
0x1010462e  mov     pwszMethod, 8Ah; id
0x10104633  push    esi; _a1
0x10104634  shl     this, 9
0x10104637  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1010463c  or      this, 1; LevelKeyword
0x1010463f  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104644  pop     edi
0x10104645  mov     eax, esi
0x10104647  pop     esi
0x10104648  pop     ebx
0x10104649  mov     esp, ebp
0x1010464b  pop     ebp
0x1010464c  retn    18h
```
