# URLMONRequest::AuthenticateEx(HWND__ * *,ushort * *,ushort * *,_tagAUTHENTICATEINFO *)

- ea: `0x101338e6`
- end: `0x10133b14`
- name: `?AuthenticateEx@URLMONRequest@@IAEJPAPAUHWND__@@PAPAG1PAU_tagAUTHENTICATEINFO@@@Z`
- size: `558`
- prototype: `HRESULT __thiscall(URLMONRequest *this, HWND__ **phwnd, wchar_t **ppwszUsername, wchar_t **ppwszPassword, _tagAUTHENTICATEINFO *pAuthinfo)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1013380c`
- `0x10133b20`

## callees

- `0x10067b20`
- `0x101338e6`
- `0x10134e13`
- `0x1016be87`
- `0x10180006`
- `0x10180cb4`
- `0x10180cee`
- `0x101814bd`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133ad6`

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
  if ( (byte_10185760[0] & 8) != 0 )
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
      if ( (byte_10185758 & 2) != 0 )
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
    if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[16 * (_a1 >> 31)] & 8) != 0 )
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
0x101338e6  mov     edi, edi
0x101338e8  push    ebp
0x101338e9  mov     ebp, esp
0x101338eb  sub     esp, 24h
0x101338ee  push    ebx
0x101338ef  push    esi; TraceGuid
0x101338f0  push    edi; id
0x101338f1  mov     edi, this
0x101338f3  xor     this, this
0x101338f5  mov     eax, this
0x101338f7  mov     [ebp+_a1], this
0x101338fa  mov     ebx, this
0x101338fc  mov     [ebp+pv], eax
0x101338ff  mov     [ebp+pwszUserName], ebx
0x10133902  mov     [ebp+pwszPassword], eax
0x10133905  mov     [ebp+cchUserName], this
0x10133908  mov     [ebp+cchPassword], this
0x1013390b  mov     [ebp+hwnd], this
0x1013390e  test    byte_10185760, 8; __annotation("TMF:",
0x10133915  jz      short loc_10133938
0x10133917  mov     eax, [ebp+pAuthinfo]
0x1013391a  test    eax, eax
0x1013391c  jz      short loc_10133920
0x1013391e  mov     this, [eax]
0x10133920  mov     esi, [ebp+ppwszPassword]
0x10133923  push    this; LevelKeyword
0x10133924  mov     this, [ebp+phwnd]
0x10133927  push    eax; _a6
0x10133928  push    esi; _a5
0x10133929  push    [ebp+ppwszUsername]; _a4
0x1013392c  push    this; _a3
0x1013392d  push    edi; _a2
0x1013392e  push    this; _a1
0x1013392f  call    _WPP_SF_qqqqqD@36; WPP_SF_qqqqqD(x,x,x,x,x,x,x,x,x)
0x10133934  xor     this, this
0x10133936  jmp     short loc_1013393B
0x10133938  mov     esi, [ebp+ppwszPassword]
0x1013393b  mov     eax, [ebp+phwnd]
0x1013393e  mov     [eax], this
0x10133940  mov     eax, [ebp+ppwszUsername]
0x10133943  mov     [eax], this
0x10133945  mov     [esi], this
0x10133947  mov     eax, [edi]
0x10133949  mov     esi, [eax+7Ch]
0x1013394c  mov     this, esi; this
0x1013394e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133954  mov     this, edi
0x10133956  call    esi
0x10133958  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x1013395e  mov     this, esi; this
0x10133960  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133966  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x10133968  test    eax, eax
0x1013396a  jnz     short loc_10133978
0x1013396c  mov     [ebp+_a1], 80004005h
0x10133973  jmp     CleanUp_464
0x10133978  mov     eax, [ebp+pAuthinfo]
0x1013397b  mov     esi, [eax]
0x1013397d  mov     edx, esi
0x1013397f  mov     [ebp+var_18], esi
0x10133982  and     edx, 1
0x10133985  jz      short loc_101339A5
0x10133987  mov     al, [edi+0E7h]
0x1013398d  lea     this, [edi+0ECh]
0x10133993  xor     esi, esi
0x10133995  test    al, al
0x10133997  cmovz   this, esi
0x1013399a  lea     esi, [edi+0F8h]
0x101339a0  cmovz   esi, ebx
0x101339a3  jmp     short loc_101339B8
0x101339a5  cmp     [edi+1Ch], bl
0x101339a8  jz      short loc_10133A05
0x101339aa  cmp     [edi+0DCh], ebx
0x101339b0  jnz     short loc_10133A05
0x101339b2  lea     this, [edi+20h]; this
0x101339b5  lea     esi, [edi+2Ch]
0x101339b8  test    this, this
0x101339ba  jz      short loc_10133A02
0x101339bc  test    esi, esi
0x101339be  jz      short loc_10133A02
0x101339c0  lea     eax, [ebp+cchUserName]
0x101339c3  push    eax; pcch
0x101339c4  lea     eax, [ebp+pwszUserName]
0x101339c7  push    eax; ppwsz
0x101339c8  call    ?toString_CoTaskMemAlloc@SecureString@@QAEJPAPAGPAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x101339cd  mov     [ebp+_a1], eax
0x101339d0  test    eax, eax
0x101339d2  js      short loc_101339FA
0x101339d4  lea     eax, [ebp+cchPassword]
0x101339d7  mov     this, esi; this
0x101339d9  push    eax; pcch
0x101339da  lea     eax, [ebp+pwszPassword]
0x101339dd  push    eax; ppwsz
0x101339de  call    ?toString_CoTaskMemAlloc@SecureString@@QAEJPAPAGPAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x101339e3  mov     ebx, [ebp+pwszUserName]
0x101339e6  mov     [ebp+_a1], eax
0x101339e9  test    eax, eax
0x101339eb  js      short loc_101339F2
0x101339ed  mov     esi, [ebp+pwszPassword]
0x101339f0  jmp     short loc_10133A55
0x101339f2  mov     eax, [ebp+pwszPassword]
0x101339f5  jmp     loc_10133A82
0x101339fa  mov     ebx, [ebp+pwszUserName]
0x101339fd  jmp     CleanUp_464
0x10133a02  mov     esi, [ebp+var_18]
0x10133a05  mov     cl, [edi+0E1h]
0x10133a0b  test    cl, cl
0x10133a0d  jz      short loc_10133A40
0x10133a0f  test    edx, edx
0x10133a11  jz      short loc_10133A1B
0x10133a13  cmp     [edi+0E2h], bl
0x10133a19  jnz     short loc_10133A40
0x10133a1b  test    byte_10185758, 2; __annotation("TMF:",
0x10133a22  jz      short loc_10133A37
0x10133a24  movzx   eax, byte ptr [edi+0E2h]
0x10133a2b  push    eax; LevelKeyword
0x10133a2c  movzx   eax, cl
0x10133a2f  push    eax; _a3
0x10133a30  push    esi; _a2
0x10133a31  push    this; _a1
0x10133a32  call    _WPP_SF_Dll@24; WPP_SF_Dll(x,x,x,x,x,x)
0x10133a37  mov     [ebp+hwnd], 0FFFFFFFFh
0x10133a3e  jmp     short loc_10133A53
0x10133a40  lea     eax, [ebp+hwnd]
0x10133a43  mov     this, edi; this
0x10133a45  push    eax; phwnd
0x10133a46  push    offset _IID_IAuthenticate; guidReason
0x10133a4b  call    ?GetWindow@URLMONRequest@@IAEJABU_GUID@@PAPAUHWND__@@@Z; URLMONRequest::GetWindow(_GUID const &,HWND__ * *)
0x10133a50  mov     [ebp+_a1], eax
0x10133a53  mov     esi, ebx
0x10133a55  test    byte_10185760, 8; __annotation("TMF:",
0x10133a5c  jz      short loc_10133A69
0x10133a5e  push    [ebp+hwnd]; LevelKeyword
0x10133a61  push    esi; _a3
0x10133a62  push    ebx; _a2
0x10133a63  push    this; _a1
0x10133a64  call    _WPP_SF_SSq@24; WPP_SF_SSq(x,x,x,x,x,x)
0x10133a69  mov     this, [ebp+phwnd]
0x10133a6c  mov     eax, [ebp+hwnd]
0x10133a6f  mov     [this], eax
0x10133a71  mov     eax, [ebp+ppwszUsername]
0x10133a74  mov     [eax], ebx
0x10133a76  xor     ebx, ebx
0x10133a78  mov     eax, [ebp+ppwszPassword]
0x10133a7b  mov     [eax], esi
0x10133a7d  xor     eax, eax
0x10133a7f  mov     [ebp+hwnd], eax
0x10133a82  mov     [ebp+pv], eax
0x10133a85  mov     eax, [edi]
0x10133a87  mov     esi, [eax+80h]
0x10133a8d  mov     this, esi; this
0x10133a8f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133a95  mov     this, edi
0x10133a97  call    esi
0x10133a99  test    ebx, ebx
0x10133a9b  jz      short loc_10133AB9
0x10133a9d  mov     eax, [ebp+cchUserName]
0x10133aa0  lea     this, [eax+eax]
0x10133aa3  mov     eax, ebx
0x10133aa5  test    this, this
0x10133aa7  jz      short loc_10133AB2
0x10133aa9  mov     byte ptr [eax], 0
0x10133aac  inc     eax
0x10133aad  sub     this, 1
0x10133ab0  jnz     short loc_10133AA9
0x10133ab2  push    ebx; pv
0x10133ab3  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10133ab9  mov     this, [ebp+pv]
0x10133abc  test    this, this
0x10133abe  jz      short loc_10133ADC
0x10133ac0  mov     eax, [ebp+cchPassword]
0x10133ac3  lea     edx, [eax+eax]
0x10133ac6  mov     eax, this
0x10133ac8  test    edx, edx
0x10133aca  jz      short loc_10133AD5
0x10133acc  mov     byte ptr [eax], 0
0x10133acf  inc     eax
0x10133ad0  sub     edx, 1
0x10133ad3  jnz     short loc_10133ACC
0x10133ad5  push    this; pv
0x10133ad6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10133adc  mov     ebx, [ebp+_a1]; __annotation("TMF:",
0x10133adf  mov     this, ebx
0x10133ae1  sar     this, 1Fh
0x10133ae4  mov     eax, this
0x10133ae6  shl     eax, 4
0x10133ae9  test    byte_10185760[eax], 8
0x10133af0  jz      short loc_10133B0B
0x10133af2  add     this, 2
0x10133af5  mov     edx, 0D7h; id
0x10133afa  push    ebx; _a1
0x10133afb  shl     this, 9
0x10133afe  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10133b03  or      this, 3; LevelKeyword
0x10133b06  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10133b0b  pop     edi
0x10133b0c  pop     esi
0x10133b0d  mov     eax, ebx
0x10133b0f  pop     ebx
0x10133b10  leave
0x10133b11  retn    10h
```
