# URLMONRequest::GetBindString(ulong,ushort * *,ulong,ulong *)

- ea: `0x10134689`
- end: `0x101348ba`
- name: `?GetBindString@URLMONRequest@@IAEJKPAPAGKPAK@Z`
- size: `561`
- prototype: `HRESULT __thiscall(URLMONRequest *this, unsigned int ulStringType, wchar_t **ppwzStr, unsigned int cEl, unsigned int *pcElFetched)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x101348c0`

## callees

- `0x1004118e`
- `0x1004fc3e`
- `0x10067bc0`
- `0x10134689`
- `0x10135946`
- `0x1016bd97`
- `0x10180006`
- `0x10181365`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013486d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013486d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013474b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013474b`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::GetBindString(
        URLMONRequest *this,
        const _GUID *ulStringType,
        wchar_t **ppwzStr,
        unsigned int cEl,
        unsigned int *pcElFetched)
{
  int v6; // edi
  wchar_t *pwszTargetUrl; // ecx
  unsigned int v8; // eax
  wchar_t *v9; // ecx
  int v10; // eax
  SecureString *p_username; // ecx
  _BYTE *v12; // ecx
  unsigned int v13; // edx
  _BYTE *i; // eax
  int v16; // [esp+0h] [ebp-18h]
  const void *v17; // [esp+4h] [ebp-14h]
  unsigned int cb; // [esp+Ch] [ebp-Ch] BYREF
  unsigned int v19; // [esp+10h] [ebp-8h]
  unsigned int cch; // [esp+14h] [ebp-4h] BYREF

  v19 = 0;
  cch = 0;
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_qdqdq((unsigned __int16)this, (unsigned __int16)this, ulStringType, ppwzStr, cEl, pcElFetched, v16, v17);
  *ppwzStr = 0;
  this->Lock(this);
  if ( !((struct TLSDATA *(__stdcall *)())g_pfnEntry)() )
  {
    v6 = -2147467259;
    goto CleanUp_467;
  }
  if ( ulStringType == (const _GUID *)14 )
  {
    if ( cEl )
    {
      pwszTargetUrl = this->_pwszTargetUrl;
      if ( pwszTargetUrl )
      {
        v8 = xstrlenw(pwszTargetUrl, 0x7FFFFFFFu);
        cch = v8;
        if ( v8 + 1 < v8 || (cb = v8 + 1, ULongLongToUInt(2LL * (v8 + 1), &cb) < 0) || cb > 0x7FFFFFFF )
        {
          v6 = -2147024362;
          goto CleanUp_467;
        }
        v9 = (wchar_t *)CoTaskMemAlloc(cb);
        *ppwzStr = v9;
        if ( !v9 )
        {
          v6 = -2147024882;
          goto CleanUp_467;
        }
        v10 = StringCbCopyW(v9, cb, this->_pwszTargetUrl);
        goto LABEL_14;
      }
    }
LABEL_39:
    v6 = -2146697198;
    goto CleanUp_467;
  }
  if ( ulStringType == (const _GUID *)5 )
  {
    if ( !cEl || !this->_fUseridAndPassword || this->_dwAuth )
      goto LABEL_39;
    p_username = &this->_username;
  }
  else if ( ulStringType == (const _GUID *)6 )
  {
    if ( !cEl || !this->_fUseridAndPassword || this->_dwAuth )
      goto LABEL_39;
    p_username = &this->_password;
  }
  else if ( ulStringType == (const _GUID *)22 )
  {
    if ( !cEl || !this->_fProxyCredsSet )
      goto LABEL_39;
    p_username = &this->_ssProxyUserName;
  }
  else if ( ulStringType == (const _GUID *)23 )
  {
    if ( !cEl || !this->_fProxyCredsSet )
      goto LABEL_39;
    p_username = &this->_ssProxyPassword;
  }
  else
  {
    if ( ulStringType != (const _GUID *)24 )
      goto LABEL_39;
    if ( !cEl )
      goto LABEL_39;
    p_username = &this->_ssEDPClaim;
    if ( !this->_ssEDPClaim._cch )
      goto LABEL_39;
  }
  v10 = SecureString::toString_CoTaskMemAlloc(p_username, ppwzStr, &cch);
LABEL_14:
  v6 = v10;
  if ( v10 >= 0 )
    v19 = 1;
CleanUp_467:
  this->Unlock(this);
  if ( v6 < 0 )
  {
    v12 = *ppwzStr;
    if ( *ppwzStr )
    {
      v13 = 2 * cch;
      for ( i = *ppwzStr; v13; --v13 )
        *i++ = 0;
      CoTaskMemFree(v12);
      *ppwzStr = 0;
    }
  }
  if ( pcElFetched )
    *pcElFetched = v19;
  if ( (byte_101857A0[16 * (v6 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xD1u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10134689  mov     edi, edi
0x1013468b  push    ebp
0x1013468c  mov     ebp, esp
0x1013468e  sub     esp, 0Ch
0x10134691  push    ebx
0x10134692  push    esi; TraceGuid
0x10134693  push    edi; id
0x10134694  mov     ebx, this
0x10134696  mov     [ebp+var_8], 0
0x1013469d  mov     [ebp+cch], 0
0x101346a4  test    byte_101857A0, 8; __annotation("TMF:",
0x101346ab  mov     edi, [ebp+ulStringType]
0x101346ae  mov     esi, [ebp+ppwzStr]
0x101346b1  jz      short loc_101346C2
0x101346b3  push    [ebp+pcElFetched]; LevelKeyword
0x101346b6  push    [ebp+cEl]; _a5
0x101346b9  push    esi; _a4
0x101346ba  push    edi; _a3
0x101346bb  push    ebx; _a2
0x101346bc  push    this; _a1
0x101346bd  call    _WPP_SF_qdqdq@32; WPP_SF_qdqdq(x,x,x,x,x,x,x,x)
0x101346c2  mov     dword ptr [esi], 0
0x101346c8  mov     eax, [ebx]
0x101346ca  mov     esi, [eax+7Ch]
0x101346cd  mov     this, esi; this
0x101346cf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101346d5  mov     this, ebx
0x101346d7  call    esi
0x101346d9  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x101346df  mov     this, esi; this
0x101346e1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101346e7  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x101346e9  test    eax, eax
0x101346eb  jnz     short loc_101346F7
0x101346ed  mov     edi, 80004005h
0x101346f2  jmp     CleanUp_467
0x101346f7  cmp     edi, 0Eh
0x101346fa  jnz     loc_10134791
0x10134700  cmp     [ebp+cEl], 1
0x10134704  jb      loc_10134831
0x1013470a  mov     this, [ebx+38h]; psz
0x1013470d  test    this, this
0x1013470f  jz      loc_10134831
0x10134715  mov     esi, 7FFFFFFFh
0x1013471a  mov     edx, esi; cchMax
0x1013471c  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x10134721  mov     [ebp+cch], eax
0x10134724  lea     this, [eax+1]
0x10134727  cmp     this, eax
0x10134729  jb      short loc_10134787
0x1013472b  push    2
0x1013472d  mov     eax, this
0x1013472f  mov     [ebp+cb], this
0x10134732  pop     this
0x10134733  mul     this
0x10134735  lea     this, [ebp+cb]; puResult
0x10134738  push    edx
0x10134739  push    eax; ullOperand
0x1013473a  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1013473f  test    eax, eax
0x10134741  js      short loc_10134787
0x10134743  cmp     [ebp+cb], esi
0x10134746  ja      short loc_10134787
0x10134748  push    [ebp+cb]; cb
0x1013474b  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10134751  mov     this, eax; pszDest
0x10134753  mov     eax, [ebp+ppwzStr]
0x10134756  mov     [eax], this
0x10134758  test    this, this
0x1013475a  jnz     short loc_10134766
0x1013475c  mov     edi, 8007000Eh
0x10134761  jmp     CleanUp_467
0x10134766  push    dword ptr [ebx+38h]; pszSrc
0x10134769  mov     edx, [ebp+cb]; cbDest
0x1013476c  call    ?StringCbCopyW@@YGJPAGIPBG@Z; StringCbCopyW(ushort *,uint,ushort const *)
0x10134771  mov     edi, eax
0x10134773  test    edi, edi
0x10134775  js      CleanUp_467
0x1013477b  mov     [ebp+var_8], 1
0x10134782  jmp     CleanUp_467
0x10134787  mov     edi, 80070216h
0x1013478c  jmp     CleanUp_467
0x10134791  cmp     edi, 5
0x10134794  jnz     short loc_101347C4
0x10134796  cmp     [ebp+cEl], 1
0x1013479a  jb      loc_10134831
0x101347a0  cmp     byte ptr [ebx+1Ch], 0
0x101347a4  jz      loc_10134831
0x101347aa  cmp     dword ptr [ebx+0DCh], 0
0x101347b1  jnz     short loc_10134831
0x101347b3  lea     this, [ebx+20h]; this
0x101347b6  lea     eax, [ebp+cch]
0x101347b9  push    eax; pcch
0x101347ba  push    [ebp+ppwzStr]; ppwsz
0x101347bd  call    ?toString_CoTaskMemAlloc@SecureString@@QAEJPAPAGPAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x101347c2  jmp     short loc_10134771
0x101347c4  cmp     edi, 6
0x101347c7  jnz     short loc_101347E3
0x101347c9  cmp     [ebp+cEl], 1
0x101347cd  jb      short loc_10134831
0x101347cf  cmp     byte ptr [ebx+1Ch], 0
0x101347d3  jz      short loc_10134831
0x101347d5  cmp     dword ptr [ebx+0DCh], 0
0x101347dc  jnz     short loc_10134831
0x101347de  lea     this, [ebx+2Ch]
0x101347e1  jmp     short loc_101347B6
0x101347e3  cmp     edi, 16h
0x101347e6  jnz     short loc_101347FF
0x101347e8  cmp     [ebp+cEl], 1
0x101347ec  jb      short loc_10134831
0x101347ee  cmp     byte ptr [ebx+0E8h], 0
0x101347f5  jz      short loc_10134831
0x101347f7  lea     this, [ebx+0ECh]
0x101347fd  jmp     short loc_101347B6
0x101347ff  cmp     edi, 17h
0x10134802  jnz     short loc_1013481B
0x10134804  cmp     [ebp+cEl], 1
0x10134808  jb      short loc_10134831
0x1013480a  cmp     byte ptr [ebx+0E8h], 0
0x10134811  jz      short loc_10134831
0x10134813  lea     this, [ebx+0F8h]
0x10134819  jmp     short loc_101347B6
0x1013481b  cmp     edi, 18h
0x1013481e  jnz     short loc_10134831
0x10134820  cmp     [ebp+cEl], 1
0x10134824  jb      short loc_10134831
0x10134826  lea     this, [ebx+190h]
0x1013482c  cmp     dword ptr [this], 0
0x1013482f  jnz     short loc_101347B6
0x10134831  mov     edi, 800C0012h
0x10134836  mov     eax, [ebx]
0x10134838  mov     esi, [eax+80h]
0x1013483e  mov     this, esi; this
0x10134840  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134846  mov     this, ebx
0x10134848  call    esi
0x1013484a  test    edi, edi
0x1013484c  jns     short loc_10134879
0x1013484e  mov     ebx, [ebp+ppwzStr]
0x10134851  mov     this, [ebx]
0x10134853  test    this, this
0x10134855  jz      short loc_10134879
0x10134857  mov     eax, [ebp+cch]
0x1013485a  lea     edx, [eax+eax]
0x1013485d  mov     eax, this
0x1013485f  test    edx, edx
0x10134861  jz      short loc_1013486C
0x10134863  mov     byte ptr [eax], 0
0x10134866  inc     eax
0x10134867  sub     edx, 1
0x1013486a  jnz     short loc_10134863
0x1013486c  push    this; pv
0x1013486d  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10134873  mov     dword ptr [ebx], 0
0x10134879  mov     this, [ebp+pcElFetched]
0x1013487c  test    this, this
0x1013487e  jz      short loc_10134885
0x10134880  mov     eax, [ebp+var_8]
0x10134883  mov     [this], eax
0x10134885  mov     this, edi; __annotation("TMF:",
0x10134887  sar     this, 1Fh
0x1013488a  mov     eax, this
0x1013488c  shl     eax, 4
0x1013488f  test    byte_101857A0[eax], 8
0x10134896  jz      short loc_101348B1
0x10134898  add     this, 2
0x1013489b  mov     edx, 0D1h; id
0x101348a0  push    edi; _a1
0x101348a1  shl     this, 9
0x101348a4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101348a9  or      this, 3; LevelKeyword
0x101348ac  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101348b1  mov     eax, edi
0x101348b3  pop     edi
0x101348b4  pop     esi
0x101348b5  pop     ebx
0x101348b6  leave
0x101348b7  retn    10h
```
