# XMLHttp2::_Open(ushort const *,ushort const *,IXMLHTTPRequest2Callback *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1010454e`
- end: `0x1010476f`
- name: `?_Open@XMLHttp2@@AAGJPBG0PAUIXMLHTTPRequest2Callback@@0000@Z`
- size: `545`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, const wchar_t *pwszMethod@<edx>, const wchar_t *pwszUrl, IXMLHTTPRequest2Callback *pStatusCallback, const wchar_t *pwszUserName, const wchar_t *pwszPassword, const wchar_t *pwszProxyUserName, const wchar_t *pwszProxyPassword)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10102d00`

## callees

- `0x10067b20`
- `0x1010454e`
- `0x10107002`
- `0x101072d8`
- `0x10180006`
- `0x101803ae`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101045e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101045e1`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104633`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010464e`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104668`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010468a`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104633`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010464e`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104668`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1010468a`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104714`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1010471e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104728`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104732`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104714`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1010471e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104728`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104732`

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
  if ( (byte_10185760[0] & 2) != 0 )
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
  if ( (byte_10185760[16 * (v10 >> 31)] & 2) != 0 )
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
0x1010454e  mov     edi, edi
0x10104550  push    ebp
0x10104551  mov     ebp, esp
0x10104553  and     esp, 0FFFFFFF8h
0x10104556  sub     esp, 4Ch
0x10104559  xor     eax, eax
0x1010455b  push    ebx
0x1010455c  push    esi; TraceGuid
0x1010455d  push    edi; id
0x1010455e  lea     edi, [esp+58h+varAsync]
0x10104562  mov     ebx, this
0x10104564  stosd
0x10104565  xor     this, this
0x10104567  mov     esi, pwszMethod
0x10104569  mov     [esp+58h+pXhr], ebx
0x1010456d  mov     [esp+58h+var_38], esi
0x10104571  mov     [esp+58h+bstrString], this
0x10104575  stosd
0x10104576  mov     [esp+58h+var_44], this
0x1010457a  mov     [esp+58h+var_40], this
0x1010457e  mov     [esp+58h+var_3C], this
0x10104582  stosd
0x10104583  stosd
0x10104584  xor     eax, eax
0x10104586  lea     edi, [esp+58h+varUserName]
0x1010458a  stosd
0x1010458b  stosd
0x1010458c  stosd
0x1010458d  stosd
0x1010458e  xor     eax, eax
0x10104590  lea     edi, [esp+58h+varPassword]
0x10104594  stosd
0x10104595  stosd
0x10104596  stosd
0x10104597  stosd
0x10104598  test    byte_10185760, 2; __annotation("TMF:",
0x1010459f  mov     edi, [ebp+pwszUrl]
0x101045a2  jz      short loc_101045BE
0x101045a4  push    [ebp+pwszProxyPassword]; LevelKeyword
0x101045a7  push    [ebp+pwszProxyUserName]; _a8
0x101045aa  push    [ebp+pwszPassword]; _a7
0x101045ad  push    [ebp+pwszUserName]; _a6
0x101045b0  push    [ebp+pStatusCallback]; _a5
0x101045b3  push    edi; _a4
0x101045b4  push    esi; _a3
0x101045b5  push    ebx; _a2
0x101045b6  push    this; _a1
0x101045b7  call    _WPP_SF_qSSqSSSS@44; WPP_SF_qSSqSSSS(x,x,x,x,x,x,x,x,x,x,x)
0x101045bc  xor     this, this
0x101045be  xor     eax, eax
0x101045c0  inc     eax
0x101045c1  test    esi, esi
0x101045c3  jnz     short loc_101045CF
0x101045c5  mov     esi, 80070057h
0x101045ca  jmp     CleanUp_378
0x101045cf  test    edi, edi
0x101045d1  jz      short loc_101045C5
0x101045d3  cmp     [ebp+pStatusCallback], 0
0x101045d7  jz      short loc_101045C5
0x101045d9  cmp     [ebx+1Ch], this
0x101045dc  jz      short loc_101045FC
0x101045de  mov     esi, [ebx+1Ch]
0x101045e1  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x101045e7  cmp     esi, eax
0x101045e9  jz      short loc_101045F5
0x101045eb  mov     esi, 8001010Eh
0x101045f0  jmp     CleanUp_378
0x101045f5  mov     esi, [esp+58h+var_38]
0x101045f9  xor     eax, eax
0x101045fb  inc     eax
0x101045fc  mov     pwszMethod, eax
0x101045fe  lea     this, [ebx+14h]
0x10104601  xor     eax, eax
0x10104603  lock cmpxchg [this], pwszMethod
0x10104607  test    eax, eax
0x10104609  jz      short loc_10104615
0x1010460b  mov     esi, 8007139Fh
0x10104610  jmp     CleanUp_378
0x10104615  push    0Bh
0x10104617  pop     eax
0x10104618  mov     word ptr [esp+58h+varAsync.___u0], ax
0x1010461d  or      eax, 0FFFFFFFFh
0x10104620  mov     word ptr [esp+58h+varAsync.___u0+8], ax
0x10104625  xor     eax, eax
0x10104627  inc     eax
0x10104628  push    esi; psz
0x10104629  mov     word ptr [esp+5Ch+varUserName.___u0], ax
0x1010462e  mov     word ptr [esp+5Ch+varPassword.___u0], ax
0x10104633  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104639  mov     esi, eax
0x1010463b  mov     [esp+58h+bstrString], esi
0x1010463f  test    esi, esi
0x10104641  jnz     short loc_1010464D
0x10104643  mov     esi, 8007000Eh
0x10104648  jmp     CleanUp_378
0x1010464d  push    edi; psz
0x1010464e  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104654  mov     [esp+58h+var_44], eax
0x10104658  test    eax, eax
0x1010465a  jz      short loc_10104643
0x1010465c  cmp     [ebp+pwszUserName], 0
0x10104660  push    8
0x10104662  pop     edi
0x10104663  jz      short loc_10104681
0x10104665  push    [ebp+pwszUserName]; psz
0x10104668  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1010466e  mov     esi, eax
0x10104670  mov     [esp+58h+var_40], esi
0x10104674  test    esi, esi
0x10104676  jz      short loc_10104643
0x10104678  mov     word ptr [esp+58h+varUserName.___u0], di
0x1010467d  mov     dword ptr [esp+58h+varUserName.___u0+8], esi
0x10104681  cmp     [ebp+pwszPassword], 0
0x10104685  jz      short loc_101046A1
0x10104687  push    [ebp+pwszPassword]; psz
0x1010468a  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104690  mov     [esp+58h+var_3C], eax
0x10104694  test    eax, eax
0x10104696  jz      short loc_10104643
0x10104698  mov     word ptr [esp+58h+varPassword.___u0], di
0x1010469d  mov     dword ptr [esp+58h+varPassword.___u0+8], eax
0x101046a1  sub     esp, 10h
0x101046a4  mov     this, [ebx+18h]
0x101046a7  mov     edi, esp
0x101046a9  lea     esi, [esp+68h+varPassword]
0x101046ad  sub     esp, 10h
0x101046b0  mov     eax, [this]
0x101046b2  movsd
0x101046b3  mov     ebx, [eax+1Ch]
0x101046b6  movsd
0x101046b7  movsd
0x101046b8  movsd
0x101046b9  mov     edi, esp
0x101046bb  lea     esi, [esp+78h+varUserName]
0x101046bf  sub     esp, 10h
0x101046c2  movsd
0x101046c3  movsd
0x101046c4  movsd
0x101046c5  movsd
0x101046c6  mov     edi, esp
0x101046c8  lea     esi, [esp+88h+varAsync]
0x101046cc  push    [esp+88h+var_44]
0x101046d0  push    [esp+8Ch+bstrString]
0x101046d4  movsd
0x101046d5  push    this
0x101046d6  mov     this, ebx; this
0x101046d8  movsd
0x101046d9  movsd
0x101046da  movsd
0x101046db  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101046e1  call    ebx
0x101046e3  mov     esi, eax
0x101046e5  test    esi, esi
0x101046e7  js      short CleanUp_378
0x101046e9  mov     edi, [esp+58h+pXhr]
0x101046ed  mov     pwszMethod, edi; pXhr
0x101046ef  push    [ebp+pStatusCallback]; pStatusCallback
0x101046f2  mov     this, [edi+18h]; this
0x101046f5  call    ?setStatusCallback@XMLHttp@@QAGJPAUIXMLHTTPRequest2@@PAUIXMLHTTPRequest2Callback@@@Z; XMLHttp::setStatusCallback(IXMLHTTPRequest2 *,IXMLHTTPRequest2Callback *)
0x101046fa  mov     esi, eax
0x101046fc  test    esi, esi
0x101046fe  js      short CleanUp_378
0x10104700  push    [ebp+pwszProxyPassword]; pcwszProxyPassword
0x10104703  mov     pwszMethod, [ebp+pwszProxyUserName]; pcwszProxyUserName
0x10104706  mov     this, [edi+18h]; this
0x10104709  call    ?setProxyCredentials@XMLHttp@@QAGJPBG0@Z; XMLHttp::setProxyCredentials(ushort const *,ushort const *)
0x1010470e  mov     esi, eax
0x10104710  push    [esp+58h+bstrString]; bstrString
0x10104714  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1010471a  push    [esp+58h+var_44]; bstrString
0x1010471e  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104724  push    [esp+58h+var_40]; bstrString
0x10104728  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1010472e  push    [esp+58h+var_3C]; bstrString
0x10104732  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104738  mov     this, esi; __annotation("TMF:",
0x1010473a  sar     this, 1Fh
0x1010473d  mov     eax, this
0x1010473f  shl     eax, 4
0x10104742  test    byte_10185760[eax], 2
0x10104749  jz      short loc_10104764
0x1010474b  add     this, 2
0x1010474e  mov     pwszMethod, 8Ah; id
0x10104753  push    esi; _a1
0x10104754  shl     this, 9
0x10104757  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1010475c  or      this, 1; LevelKeyword
0x1010475f  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104764  pop     edi
0x10104765  mov     eax, esi
0x10104767  pop     esi
0x10104768  pop     ebx
0x10104769  mov     esp, ebp
0x1010476b  pop     ebp
0x1010476c  retn    18h
```
