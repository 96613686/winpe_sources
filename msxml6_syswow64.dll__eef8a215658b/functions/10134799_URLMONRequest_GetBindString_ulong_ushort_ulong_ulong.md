# URLMONRequest::GetBindString(ulong,ushort * *,ulong,ulong *)

- ea: `0x10134799`
- end: `0x101349ca`
- name: `?GetBindString@URLMONRequest@@IAEJKPAPAGKPAK@Z`
- size: `561`
- prototype: `HRESULT __thiscall(URLMONRequest *this, const _GUID *ulStringType, wchar_t **ppwzStr, unsigned int cEl, unsigned int *pcElFetched)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x101349d0`

## callees

- `0x100410fe`
- `0x1004fbae`
- `0x10067b20`
- `0x10134799`
- `0x10135a56`
- `0x1016be87`
- `0x10180006`
- `0x10181365`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013497d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013497d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013485b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013485b`

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
  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[16 * (v6 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xD1u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10134799  mov     edi, edi
0x1013479b  push    ebp
0x1013479c  mov     ebp, esp
0x1013479e  sub     esp, 0Ch
0x101347a1  push    ebx
0x101347a2  push    esi; TraceGuid
0x101347a3  push    edi; id
0x101347a4  mov     ebx, this
0x101347a6  mov     [ebp+var_8], 0
0x101347ad  mov     [ebp+cch], 0
0x101347b4  test    byte_10185760, 8; __annotation("TMF:",
0x101347bb  mov     edi, [ebp+ulStringType]
0x101347be  mov     esi, [ebp+ppwzStr]
0x101347c1  jz      short loc_101347D2
0x101347c3  push    [ebp+pcElFetched]; LevelKeyword
0x101347c6  push    [ebp+cEl]; _a5
0x101347c9  push    esi; _a4
0x101347ca  push    edi; _a3
0x101347cb  push    ebx; _a2
0x101347cc  push    this; _a1
0x101347cd  call    _WPP_SF_qdqdq@32; WPP_SF_qdqdq(x,x,x,x,x,x,x,x)
0x101347d2  mov     dword ptr [esi], 0
0x101347d8  mov     eax, [ebx]
0x101347da  mov     esi, [eax+7Ch]
0x101347dd  mov     this, esi; this
0x101347df  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101347e5  mov     this, ebx
0x101347e7  call    esi
0x101347e9  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x101347ef  mov     this, esi; this
0x101347f1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101347f7  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x101347f9  test    eax, eax
0x101347fb  jnz     short loc_10134807
0x101347fd  mov     edi, 80004005h
0x10134802  jmp     CleanUp_467
0x10134807  cmp     edi, 0Eh
0x1013480a  jnz     loc_101348A1
0x10134810  cmp     [ebp+cEl], 1
0x10134814  jb      loc_10134941
0x1013481a  mov     this, [ebx+38h]; psz
0x1013481d  test    this, this
0x1013481f  jz      loc_10134941
0x10134825  mov     esi, 7FFFFFFFh
0x1013482a  mov     edx, esi; cchMax
0x1013482c  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x10134831  mov     [ebp+cch], eax
0x10134834  lea     this, [eax+1]
0x10134837  cmp     this, eax
0x10134839  jb      short loc_10134897
0x1013483b  push    2
0x1013483d  mov     eax, this
0x1013483f  mov     [ebp+cb], this
0x10134842  pop     this
0x10134843  mul     this
0x10134845  lea     this, [ebp+cb]; puResult
0x10134848  push    edx
0x10134849  push    eax; ullOperand
0x1013484a  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1013484f  test    eax, eax
0x10134851  js      short loc_10134897
0x10134853  cmp     [ebp+cb], esi
0x10134856  ja      short loc_10134897
0x10134858  push    [ebp+cb]; cb
0x1013485b  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10134861  mov     this, eax; pszDest
0x10134863  mov     eax, [ebp+ppwzStr]
0x10134866  mov     [eax], this
0x10134868  test    this, this
0x1013486a  jnz     short loc_10134876
0x1013486c  mov     edi, 8007000Eh
0x10134871  jmp     CleanUp_467
0x10134876  push    dword ptr [ebx+38h]; pszSrc
0x10134879  mov     edx, [ebp+cb]; cbDest
0x1013487c  call    ?StringCbCopyW@@YGJPAGIPBG@Z; StringCbCopyW(ushort *,uint,ushort const *)
0x10134881  mov     edi, eax
0x10134883  test    edi, edi
0x10134885  js      CleanUp_467
0x1013488b  mov     [ebp+var_8], 1
0x10134892  jmp     CleanUp_467
0x10134897  mov     edi, 80070216h
0x1013489c  jmp     CleanUp_467
0x101348a1  cmp     edi, 5
0x101348a4  jnz     short loc_101348D4
0x101348a6  cmp     [ebp+cEl], 1
0x101348aa  jb      loc_10134941
0x101348b0  cmp     byte ptr [ebx+1Ch], 0
0x101348b4  jz      loc_10134941
0x101348ba  cmp     dword ptr [ebx+0DCh], 0
0x101348c1  jnz     short loc_10134941
0x101348c3  lea     this, [ebx+20h]; this
0x101348c6  lea     eax, [ebp+cch]
0x101348c9  push    eax; pcch
0x101348ca  push    [ebp+ppwzStr]; ppwsz
0x101348cd  call    ?toString_CoTaskMemAlloc@SecureString@@QAEJPAPAGPAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x101348d2  jmp     short loc_10134881
0x101348d4  cmp     edi, 6
0x101348d7  jnz     short loc_101348F3
0x101348d9  cmp     [ebp+cEl], 1
0x101348dd  jb      short loc_10134941
0x101348df  cmp     byte ptr [ebx+1Ch], 0
0x101348e3  jz      short loc_10134941
0x101348e5  cmp     dword ptr [ebx+0DCh], 0
0x101348ec  jnz     short loc_10134941
0x101348ee  lea     this, [ebx+2Ch]
0x101348f1  jmp     short loc_101348C6
0x101348f3  cmp     edi, 16h
0x101348f6  jnz     short loc_1013490F
0x101348f8  cmp     [ebp+cEl], 1
0x101348fc  jb      short loc_10134941
0x101348fe  cmp     byte ptr [ebx+0E8h], 0
0x10134905  jz      short loc_10134941
0x10134907  lea     this, [ebx+0ECh]
0x1013490d  jmp     short loc_101348C6
0x1013490f  cmp     edi, 17h
0x10134912  jnz     short loc_1013492B
0x10134914  cmp     [ebp+cEl], 1
0x10134918  jb      short loc_10134941
0x1013491a  cmp     byte ptr [ebx+0E8h], 0
0x10134921  jz      short loc_10134941
0x10134923  lea     this, [ebx+0F8h]
0x10134929  jmp     short loc_101348C6
0x1013492b  cmp     edi, 18h
0x1013492e  jnz     short loc_10134941
0x10134930  cmp     [ebp+cEl], 1
0x10134934  jb      short loc_10134941
0x10134936  lea     this, [ebx+190h]
0x1013493c  cmp     dword ptr [this], 0
0x1013493f  jnz     short loc_101348C6
0x10134941  mov     edi, 800C0012h
0x10134946  mov     eax, [ebx]
0x10134948  mov     esi, [eax+80h]
0x1013494e  mov     this, esi; this
0x10134950  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134956  mov     this, ebx
0x10134958  call    esi
0x1013495a  test    edi, edi
0x1013495c  jns     short loc_10134989
0x1013495e  mov     ebx, [ebp+ppwzStr]
0x10134961  mov     this, [ebx]
0x10134963  test    this, this
0x10134965  jz      short loc_10134989
0x10134967  mov     eax, [ebp+cch]
0x1013496a  lea     edx, [eax+eax]
0x1013496d  mov     eax, this
0x1013496f  test    edx, edx
0x10134971  jz      short loc_1013497C
0x10134973  mov     byte ptr [eax], 0
0x10134976  inc     eax
0x10134977  sub     edx, 1
0x1013497a  jnz     short loc_10134973
0x1013497c  push    this; pv
0x1013497d  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10134983  mov     dword ptr [ebx], 0
0x10134989  mov     this, [ebp+pcElFetched]
0x1013498c  test    this, this
0x1013498e  jz      short loc_10134995
0x10134990  mov     eax, [ebp+var_8]
0x10134993  mov     [this], eax
0x10134995  mov     this, edi; __annotation("TMF:",
0x10134997  sar     this, 1Fh
0x1013499a  mov     eax, this
0x1013499c  shl     eax, 4
0x1013499f  test    byte_10185760[eax], 8
0x101349a6  jz      short loc_101349C1
0x101349a8  add     this, 2
0x101349ab  mov     edx, 0D1h; id
0x101349b0  push    edi; _a1
0x101349b1  shl     this, 9
0x101349b4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101349b9  or      this, 3; LevelKeyword
0x101349bc  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101349c1  mov     eax, edi
0x101349c3  pop     edi
0x101349c4  pop     esi
0x101349c5  pop     ebx
0x101349c6  leave
0x101349c7  retn    10h
```
