# URLMONRequest::AuthenticateEx(HWND__ * *,ushort * *,ushort * *,_tagAUTHENTICATEINFO *)

- ea: `0x101337d6`
- end: `0x10133a04`
- name: `?AuthenticateEx@URLMONRequest@@IAEJPAPAUHWND__@@PAPAG1PAU_tagAUTHENTICATEINFO@@@Z`
- size: `558`
- prototype: `HRESULT __thiscall(URLMONRequest *this, HWND__ **phwnd, wchar_t **ppwszUsername, wchar_t **ppwszPassword, _tagAUTHENTICATEINFO *pAuthinfo)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x101336fc`
- `0x10133a10`

## callees

- `0x10067bc0`
- `0x101337d6`
- `0x10134d03`
- `0x1016bd97`
- `0x10180006`
- `0x10180cb4`
- `0x10180cee`
- `0x101814bd`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101339a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101339c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101339a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101339c6`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::AuthenticateEx(
        URLMONRequest *this,
        HWND__ **phwnd,
        wchar_t **ppwszUsername,
        wchar_t **ppwszPassword,
        _tagAUTHENTICATEINFO *pAuthinfo)
{
  const void *dwFlags; // ecx
  wchar_t *v7; // ebx
  wchar_t **v8; // esi
  SecureString *p_ssProxyUserName; // ecx
  unsigned int v10; // esi
  bool fProxyUserNameAndPassword; // al
  SecureString *p_ssProxyPassword; // esi
  int v13; // eax
  wchar_t *v14; // esi
  wchar_t *v15; // eax
  unsigned int v16; // ecx
  wchar_t *i; // eax
  void *v18; // ecx
  unsigned int v19; // edx
  _BYTE *j; // eax
  int v21; // ebx
  const void *v23; // [esp+0h] [ebp-30h]
  const void *v24; // [esp+4h] [ebp-2Ch]
  unsigned int cchPassword; // [esp+10h] [ebp-20h] BYREF
  unsigned int cchUserName; // [esp+14h] [ebp-1Ch] BYREF
  unsigned int v27; // [esp+18h] [ebp-18h]
  wchar_t *pwszPassword; // [esp+1Ch] [ebp-14h] BYREF
  wchar_t *pwszUserName; // [esp+20h] [ebp-10h] BYREF
  int _a1; // [esp+24h] [ebp-Ch]
  LPVOID pv; // [esp+28h] [ebp-8h]
  HWND__ *hwnd; // [esp+2Ch] [ebp-4h] BYREF

  dwFlags = 0;
  _a1 = 0;
  v7 = 0;
  pv = 0;
  pwszUserName = 0;
  pwszPassword = 0;
  cchUserName = 0;
  cchPassword = 0;
  hwnd = 0;
  if ( (byte_101857A0[0] & 8) != 0 )
  {
    if ( pAuthinfo )
      dwFlags = (const void *)pAuthinfo->dwFlags;
    v8 = ppwszPassword;
    WPP_SF_qqqqqD(
      (unsigned __int16)phwnd,
      (unsigned __int16)this,
      (const _GUID *)phwnd,
      ppwszUsername,
      ppwszPassword,
      pAuthinfo,
      dwFlags,
      v23,
      (unsigned int)v24);
  }
  else
  {
    v8 = ppwszPassword;
  }
  *phwnd = 0;
  *ppwszUsername = 0;
  *v8 = 0;
  this->Lock(this);
  if ( !((struct TLSDATA *(__stdcall *)())g_pfnEntry)() )
  {
    _a1 = -2147467259;
    goto CleanUp_464;
  }
  v10 = pAuthinfo->dwFlags;
  v27 = pAuthinfo->dwFlags;
  if ( (v27 & 1) != 0 )
  {
    fProxyUserNameAndPassword = this->_fProxyUserNameAndPassword;
    p_ssProxyUserName = &this->_ssProxyUserName;
    if ( !fProxyUserNameAndPassword )
      p_ssProxyUserName = 0;
    p_ssProxyPassword = &this->_ssProxyPassword;
    if ( !fProxyUserNameAndPassword )
      p_ssProxyPassword = 0;
  }
  else
  {
    if ( !this->_fUseridAndPassword || this->_dwAuth )
      goto LABEL_25;
    p_ssProxyUserName = &this->_username;
    p_ssProxyPassword = &this->_password;
  }
  if ( !p_ssProxyUserName || !p_ssProxyPassword )
  {
    LOWORD(v10) = v27;
LABEL_25:
    LOBYTE(p_ssProxyUserName) = this->_fDisableUI;
    if ( !(_BYTE)p_ssProxyUserName || (v27 & 1) != 0 && this->_fProxyPrompt )
    {
      _a1 = URLMONRequest::GetWindow(this, &IID_IAuthenticate, &hwnd);
    }
    else
    {
      if ( (byte_10185798 & 2) != 0 )
        WPP_SF_Dll(
          (unsigned __int16)p_ssProxyUserName,
          v10,
          (const _GUID *)(unsigned __int8)p_ssProxyUserName,
          this->_fProxyPrompt,
          (int)v23,
          (int)v24);
      hwnd = (HWND__ *)-1;
    }
    v14 = 0;
    goto LABEL_33;
  }
  _a1 = SecureString::toString_CoTaskMemAlloc(p_ssProxyUserName, &pwszUserName, &cchUserName);
  if ( _a1 < 0 )
  {
    v7 = pwszUserName;
    goto CleanUp_464;
  }
  v13 = SecureString::toString_CoTaskMemAlloc(p_ssProxyPassword, &pwszPassword, &cchPassword);
  v7 = pwszUserName;
  _a1 = v13;
  if ( v13 >= 0 )
  {
    v14 = pwszPassword;
LABEL_33:
    if ( (byte_101857A0[0] & 8) != 0 )
      WPP_SF_SSq(
        (unsigned __int16)p_ssProxyUserName,
        (unsigned __int16)v7,
        (const _GUID *)v14,
        (const wchar_t *)hwnd,
        (const wchar_t *)v23,
        v24);
    *phwnd = hwnd;
    *ppwszUsername = v7;
    v7 = 0;
    *ppwszPassword = v14;
    v15 = 0;
    hwnd = 0;
    goto LABEL_36;
  }
  v15 = pwszPassword;
LABEL_36:
  pv = v15;
CleanUp_464:
  this->Unlock(this);
  if ( v7 )
  {
    v16 = 2 * cchUserName;
    for ( i = v7; v16; --v16 )
    {
      *(_BYTE *)i = 0;
      i = (wchar_t *)((char *)i + 1);
    }
    CoTaskMemFree(v7);
  }
  v18 = pv;
  if ( pv )
  {
    v19 = 2 * cchPassword;
    for ( j = pv; v19; --v19 )
      *j++ = 0;
    CoTaskMemFree(v18);
  }
  v21 = _a1;
  if ( (byte_101857A0[16 * (_a1 >> 31)] & 8) != 0 )
    WPP_SF_q(
      (((unsigned __int16)(_a1 >> 31) + 2) << 9) | 3,
      0xD7u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      _a1);
  return v21;
}

```

## disassembly

```asm
0x101337d6  mov     edi, edi
0x101337d8  push    ebp
0x101337d9  mov     ebp, esp
0x101337db  sub     esp, 24h
0x101337de  push    ebx
0x101337df  push    esi; TraceGuid
0x101337e0  push    edi; id
0x101337e1  mov     edi, this
0x101337e3  xor     this, this
0x101337e5  mov     eax, this
0x101337e7  mov     [ebp+_a1], this
0x101337ea  mov     ebx, this
0x101337ec  mov     [ebp+pv], eax
0x101337ef  mov     [ebp+pwszUserName], ebx
0x101337f2  mov     [ebp+pwszPassword], eax
0x101337f5  mov     [ebp+cchUserName], this
0x101337f8  mov     [ebp+cchPassword], this
0x101337fb  mov     [ebp+hwnd], this
0x101337fe  test    byte_101857A0, 8; __annotation("TMF:",
0x10133805  jz      short loc_10133828
0x10133807  mov     eax, [ebp+pAuthinfo]
0x1013380a  test    eax, eax
0x1013380c  jz      short loc_10133810
0x1013380e  mov     this, [eax]
0x10133810  mov     esi, [ebp+ppwszPassword]
0x10133813  push    this; LevelKeyword
0x10133814  mov     this, [ebp+phwnd]
0x10133817  push    eax; _a6
0x10133818  push    esi; _a5
0x10133819  push    [ebp+ppwszUsername]; _a4
0x1013381c  push    this; _a3
0x1013381d  push    edi; _a2
0x1013381e  push    this; _a1
0x1013381f  call    _WPP_SF_qqqqqD@36; WPP_SF_qqqqqD(x,x,x,x,x,x,x,x,x)
0x10133824  xor     this, this
0x10133826  jmp     short loc_1013382B
0x10133828  mov     esi, [ebp+ppwszPassword]
0x1013382b  mov     eax, [ebp+phwnd]
0x1013382e  mov     [eax], this
0x10133830  mov     eax, [ebp+ppwszUsername]
0x10133833  mov     [eax], this
0x10133835  mov     [esi], this
0x10133837  mov     eax, [edi]
0x10133839  mov     esi, [eax+7Ch]
0x1013383c  mov     this, esi; this
0x1013383e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133844  mov     this, edi
0x10133846  call    esi
0x10133848  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x1013384e  mov     this, esi; this
0x10133850  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133856  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x10133858  test    eax, eax
0x1013385a  jnz     short loc_10133868
0x1013385c  mov     [ebp+_a1], 80004005h
0x10133863  jmp     CleanUp_464
0x10133868  mov     eax, [ebp+pAuthinfo]
0x1013386b  mov     esi, [eax]
0x1013386d  mov     edx, esi
0x1013386f  mov     [ebp+var_18], esi
0x10133872  and     edx, 1
0x10133875  jz      short loc_10133895
0x10133877  mov     al, [edi+0E7h]
0x1013387d  lea     this, [edi+0ECh]
0x10133883  xor     esi, esi
0x10133885  test    al, al
0x10133887  cmovz   this, esi
0x1013388a  lea     esi, [edi+0F8h]
0x10133890  cmovz   esi, ebx
0x10133893  jmp     short loc_101338A8
0x10133895  cmp     [edi+1Ch], bl
0x10133898  jz      short loc_101338F5
0x1013389a  cmp     [edi+0DCh], ebx
0x101338a0  jnz     short loc_101338F5
0x101338a2  lea     this, [edi+20h]; this
0x101338a5  lea     esi, [edi+2Ch]
0x101338a8  test    this, this
0x101338aa  jz      short loc_101338F2
0x101338ac  test    esi, esi
0x101338ae  jz      short loc_101338F2
0x101338b0  lea     eax, [ebp+cchUserName]
0x101338b3  push    eax; pcch
0x101338b4  lea     eax, [ebp+pwszUserName]
0x101338b7  push    eax; ppwsz
0x101338b8  call    ?toString_CoTaskMemAlloc@SecureString@@QAEJPAPAGPAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x101338bd  mov     [ebp+_a1], eax
0x101338c0  test    eax, eax
0x101338c2  js      short loc_101338EA
0x101338c4  lea     eax, [ebp+cchPassword]
0x101338c7  mov     this, esi; this
0x101338c9  push    eax; pcch
0x101338ca  lea     eax, [ebp+pwszPassword]
0x101338cd  push    eax; ppwsz
0x101338ce  call    ?toString_CoTaskMemAlloc@SecureString@@QAEJPAPAGPAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x101338d3  mov     ebx, [ebp+pwszUserName]
0x101338d6  mov     [ebp+_a1], eax
0x101338d9  test    eax, eax
0x101338db  js      short loc_101338E2
0x101338dd  mov     esi, [ebp+pwszPassword]
0x101338e0  jmp     short loc_10133945
0x101338e2  mov     eax, [ebp+pwszPassword]
0x101338e5  jmp     loc_10133972
0x101338ea  mov     ebx, [ebp+pwszUserName]
0x101338ed  jmp     CleanUp_464
0x101338f2  mov     esi, [ebp+var_18]
0x101338f5  mov     cl, [edi+0E1h]
0x101338fb  test    cl, cl
0x101338fd  jz      short loc_10133930
0x101338ff  test    edx, edx
0x10133901  jz      short loc_1013390B
0x10133903  cmp     [edi+0E2h], bl
0x10133909  jnz     short loc_10133930
0x1013390b  test    byte_10185798, 2; __annotation("TMF:",
0x10133912  jz      short loc_10133927
0x10133914  movzx   eax, byte ptr [edi+0E2h]
0x1013391b  push    eax; LevelKeyword
0x1013391c  movzx   eax, cl
0x1013391f  push    eax; _a3
0x10133920  push    esi; _a2
0x10133921  push    this; _a1
0x10133922  call    _WPP_SF_Dll@24; WPP_SF_Dll(x,x,x,x,x,x)
0x10133927  mov     [ebp+hwnd], 0FFFFFFFFh
0x1013392e  jmp     short loc_10133943
0x10133930  lea     eax, [ebp+hwnd]
0x10133933  mov     this, edi; this
0x10133935  push    eax; phwnd
0x10133936  push    offset _IID_IAuthenticate; guidReason
0x1013393b  call    ?GetWindow@URLMONRequest@@IAEJABU_GUID@@PAPAUHWND__@@@Z; URLMONRequest::GetWindow(_GUID const &,HWND__ * *)
0x10133940  mov     [ebp+_a1], eax
0x10133943  mov     esi, ebx
0x10133945  test    byte_101857A0, 8; __annotation("TMF:",
0x1013394c  jz      short loc_10133959
0x1013394e  push    [ebp+hwnd]; LevelKeyword
0x10133951  push    esi; _a3
0x10133952  push    ebx; _a2
0x10133953  push    this; _a1
0x10133954  call    _WPP_SF_SSq@24; WPP_SF_SSq(x,x,x,x,x,x)
0x10133959  mov     this, [ebp+phwnd]
0x1013395c  mov     eax, [ebp+hwnd]
0x1013395f  mov     [this], eax
0x10133961  mov     eax, [ebp+ppwszUsername]
0x10133964  mov     [eax], ebx
0x10133966  xor     ebx, ebx
0x10133968  mov     eax, [ebp+ppwszPassword]
0x1013396b  mov     [eax], esi
0x1013396d  xor     eax, eax
0x1013396f  mov     [ebp+hwnd], eax
0x10133972  mov     [ebp+pv], eax
0x10133975  mov     eax, [edi]
0x10133977  mov     esi, [eax+80h]
0x1013397d  mov     this, esi; this
0x1013397f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133985  mov     this, edi
0x10133987  call    esi
0x10133989  test    ebx, ebx
0x1013398b  jz      short loc_101339A9
0x1013398d  mov     eax, [ebp+cchUserName]
0x10133990  lea     this, [eax+eax]
0x10133993  mov     eax, ebx
0x10133995  test    this, this
0x10133997  jz      short loc_101339A2
0x10133999  mov     byte ptr [eax], 0
0x1013399c  inc     eax
0x1013399d  sub     this, 1
0x101339a0  jnz     short loc_10133999
0x101339a2  push    ebx; pv
0x101339a3  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101339a9  mov     this, [ebp+pv]
0x101339ac  test    this, this
0x101339ae  jz      short loc_101339CC
0x101339b0  mov     eax, [ebp+cchPassword]
0x101339b3  lea     edx, [eax+eax]
0x101339b6  mov     eax, this
0x101339b8  test    edx, edx
0x101339ba  jz      short loc_101339C5
0x101339bc  mov     byte ptr [eax], 0
0x101339bf  inc     eax
0x101339c0  sub     edx, 1
0x101339c3  jnz     short loc_101339BC
0x101339c5  push    this; pv
0x101339c6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101339cc  mov     ebx, [ebp+_a1]; __annotation("TMF:",
0x101339cf  mov     this, ebx
0x101339d1  sar     this, 1Fh
0x101339d4  mov     eax, this
0x101339d6  shl     eax, 4
0x101339d9  test    byte_101857A0[eax], 8
0x101339e0  jz      short loc_101339FB
0x101339e2  add     this, 2
0x101339e5  mov     edx, 0D7h; id
0x101339ea  push    ebx; _a1
0x101339eb  shl     this, 9
0x101339ee  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101339f3  or      this, 3; LevelKeyword
0x101339f6  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101339fb  pop     edi
0x101339fc  pop     esi
0x101339fd  mov     eax, ebx
0x101339ff  pop     ebx
0x10133a00  leave
0x10133a01  retn    10h
```
