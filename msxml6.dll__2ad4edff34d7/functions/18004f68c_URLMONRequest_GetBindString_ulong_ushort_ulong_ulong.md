# URLMONRequest::GetBindString(ulong,ushort * *,ulong,ulong *)

- ea: `0x18004f68c`
- end: `0x18004f96c`
- name: `?GetBindString@URLMONRequest@@IEAAJKPEAPEAGKPEAK@Z`
- size: `736`
- prototype: `__int64 __fastcall(URLMONRequest *this, int ulStringType, wchar_t **ppwzStr, int cEl, unsigned int *pcElFetched)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180156060`

## callees

- `0x18004f68c`
- `0x1800502b0`
- `0x18005ac64`
- `0x1800a0708`
- `0x180156c74`
- `0x180185008`
- `0x180186d58`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f7b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f7b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f815`

## pseudocode

```c
__int64 __fastcall URLMONRequest::GetBindString(
        URLMONRequest *this,
        int ulStringType,
        wchar_t **ppwzStr,
        int cEl,
        unsigned int *pcElFetched)
{
  int v5; // ebp
  unsigned int *v10; // r15
  wchar_t *pwszTargetUrl; // rcx
  int v12; // ebx
  unsigned int v14; // eax
  unsigned __int64 v15; // rcx
  _BYTE *v16; // rdx
  __int64 i; // rax
  unsigned __int64 v18; // r9
  unsigned int *v19; // rbx
  wchar_t *v20; // rax
  int v21; // eax
  SecureString *p_username; // rcx
  void *v23; // rcx
  unsigned int cch; // [rsp+70h] [rbp+8h] BYREF

  v5 = 0;
  cch = 0;
  v10 = pcElFetched;
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_qdqdq(
      (unsigned __int16)this,
      ulStringType,
      (const _GUID *)ppwzStr,
      this,
      ulStringType,
      ppwzStr,
      cEl,
      pcElFetched);
  *ppwzStr = 0;
  this->Lock(this);
  if ( !(__int64)g_pfnEntry() )
  {
    v12 = -2147467259;
    goto $CleanUp_31;
  }
  if ( ulStringType == 14 )
  {
    if ( !cEl || (pwszTargetUrl = this->_pwszTargetUrl) == 0 )
    {
LABEL_7:
      v12 = -2146697198;
      goto $CleanUp_31;
    }
    v14 = xstrlenw(pwszTargetUrl, 0x7FFFFFFFu);
    cch = v14;
    v15 = v14 + 1LL;
    if ( v15 < v14
      || (pcElFetched = (unsigned int *)(v14 + 1LL), ULongLongMult(v15, 2u, (unsigned __int64 *)&pcElFetched) < 0)
      || (v19 = pcElFetched, (unsigned __int64)pcElFetched > v18) )
    {
      v12 = -2147024362;
      goto $CleanUp_31;
    }
    v20 = (wchar_t *)CoTaskMemAlloc((SIZE_T)pcElFetched);
    *ppwzStr = v20;
    if ( !v20 )
    {
      v12 = -2147024882;
      goto $CleanUp_31;
    }
    v21 = StringCbCopyW(v20, (unsigned __int64)v19, this->_pwszTargetUrl);
  }
  else
  {
    switch ( ulStringType )
    {
      case 5:
        if ( !cEl || !this->_fUseridAndPassword || this->_dwAuth )
          goto LABEL_7;
        p_username = &this->_username;
        break;
      case 6:
        if ( !cEl || !this->_fUseridAndPassword || this->_dwAuth )
          goto LABEL_7;
        p_username = &this->_password;
        break;
      case 22:
        if ( !cEl || !this->_fProxyCredsSet )
          goto LABEL_7;
        p_username = &this->_ssProxyUserName;
        break;
      case 23:
        if ( !cEl || !this->_fProxyCredsSet )
          goto LABEL_7;
        p_username = &this->_ssProxyPassword;
        break;
      case 24:
        if ( !cEl )
          goto LABEL_7;
        p_username = &this->_ssEDPClaim;
        if ( !this->_ssEDPClaim._cch )
          goto LABEL_7;
        break;
      default:
        goto LABEL_7;
    }
    v21 = SecureString::toString_CoTaskMemAlloc(p_username, ppwzStr, &cch);
  }
  v12 = v21;
  if ( v21 >= 0 )
    v5 = 1;
$CleanUp_31:
  this->Unlock(this);
  if ( v12 < 0 )
  {
    v23 = *ppwzStr;
    if ( *ppwzStr )
    {
      v16 = *ppwzStr;
      for ( i = 2LL * cch; i; --i )
        *v16++ = 0;
      CoTaskMemFree(v23);
      *ppwzStr = 0;
    }
  }
  if ( v10 )
    *v10 = v5;
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v12 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(v12 >> 31) + 2) << 9) | 3,
      0xD1u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004f68c  mov     [rsp+arg_8], rbx
0x18004f691  mov     [rsp+arg_10], rbp
0x18004f696  push    rsi
0x18004f697  push    rdi
0x18004f698  push    r13
0x18004f69a  push    r14
0x18004f69c  push    r15
0x18004f69e  sub     rsp, 40h
0x18004f6a2  xor     ebp, ebp
0x18004f6a4  mov     esi, cEl
0x18004f6a7  mov     [rsp+68h+cch], ebp
0x18004f6ab  mov     r14, ppwzStr
0x18004f6ae  mov     ebx, ulStringType
0x18004f6b0  mov     rdi, this
0x18004f6b3  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x18004f6ba  mov     r15, [rsp+68h+cb]
0x18004f6c2  jnz     loc_18004F7C8
0x18004f6c8  mov     [r14], rbp
0x18004f6cb  mov     this, rdi
0x18004f6ce  mov     rax, [rdi]
0x18004f6d1  mov     rax, [rax+0F8h]
0x18004f6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6dd  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18004f6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6e9  mov     r13d, 1
0x18004f6ef  test    rax, rax
0x18004f6f2  jz      short loc_18004F771
0x18004f6f4  cmp     ebx, 0Eh
0x18004f6f7  jnz     loc_18004F861
0x18004f6fd  cmp     esi, r13d
0x18004f700  jb      short loc_18004F70B
0x18004f702  mov     this, [rdi+60h]; psz
0x18004f706  test    this, this
0x18004f709  jnz     short loc_18004F778
0x18004f70b  mov     ebx, 800C0012h
0x18004f710  mov     rax, [rdi]
0x18004f713  mov     this, rdi
0x18004f716  mov     rax, [rax+100h]
0x18004f71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f722  test    ebx, ebx
0x18004f724  js      loc_18004F925
0x18004f72a  test    r15, r15
0x18004f72d  jnz     loc_18004F936
0x18004f733  mov     r8d, ebx; __annotation("TMF:",
0x18004f736  sar     r8d, 1Fh
0x18004f73a  lea     eax, ds:4[ppwzStr*2]
0x18004f742  movsxd  this, eax
0x18004f745  lea     rax, g_rgFastWppLevelEnabledFlags
0x18004f74c  test    byte ptr [rax+this*8], 8
0x18004f750  jnz     loc_18004F93E
0x18004f756  lea     r11, [rsp+68h+var_28]
0x18004f75b  mov     eax, ebx
0x18004f75d  mov     rbx, [r11+38h]
0x18004f761  mov     rbp, [r11+40h]
0x18004f765  mov     rsp, r11
0x18004f768  pop     r15
0x18004f76a  pop     r14
0x18004f76c  pop     r13
0x18004f76e  pop     rdi
0x18004f76f  pop     rsi
0x18004f770  retn
0x18004f771  mov     ebx, 80004005h
0x18004f776  jmp     short $CleanUp_31
0x18004f778  mov     cEl, 7FFFFFFFh
0x18004f77e  mov     ulStringType, cEl; cchMax
0x18004f781  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x18004f786  mov     ulStringType, eax
0x18004f788  mov     [rsp+68h+cch], ulStringType
0x18004f78c  lea     this, [rdx+1]; ullMultiplicand
0x18004f790  cmp     this, rdx
0x18004f793  jnb     short loc_18004F7E7
0x18004f795  mov     ebx, 80070216h
0x18004f79a  jmp     $CleanUp_31
0x18004f79f  mov     eax, [rsp+68h+cch]
0x18004f7a3  mov     rdx, this
0x18004f7a6  add     rax, rax
0x18004f7a9  jz      short loc_18004F7B6
0x18004f7ab  mov     byte ptr [rdx], 0
0x18004f7ae  add     rdx, r13
0x18004f7b1  sub     rax, r13
0x18004f7b4  jnz     short loc_18004F7AB
0x18004f7b6  call    cs:__imp_CoTaskMemFree
0x18004f7bc  mov     qword ptr [r14], 0
0x18004f7c3  jmp     loc_18004F72A
0x18004f7c8  mov     [rsp+68h+TraceGuid], r15; TraceGuid
0x18004f7cd  mov     r9, rdi; _a4
0x18004f7d0  mov     [rsp+68h+id], esi; id
0x18004f7d4  mov     [rsp+68h+LevelKeyword], r14; LevelKeyword
0x18004f7d9  mov     [rsp+68h+_a5], ebx; _a5
0x18004f7dd  call    WPP_SF_qdqdq
0x18004f7e2  jmp     loc_18004F6C8
0x18004f7e7  lea     ppwzStr, [rsp+68h+cb]; pullResult
0x18004f7ef  mov     [rsp+68h+cb], this
0x18004f7f7  mov     ulStringType, 2; ullMultiplier
0x18004f7fc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004f801  test    eax, eax
0x18004f803  js      short loc_18004F795
0x18004f805  mov     rbx, [rsp+68h+cb]
0x18004f80d  cmp     rbx, r9
0x18004f810  ja      short loc_18004F795
0x18004f812  mov     this, rbx; cb
0x18004f815  call    cs:__imp_CoTaskMemAlloc
0x18004f81b  mov     [r14], rax
0x18004f81e  test    rax, rax
0x18004f821  jnz     short loc_18004F82D
0x18004f823  mov     ebx, 8007000Eh
0x18004f828  jmp     $CleanUp_31
0x18004f82d  mov     ppwzStr, [rdi+60h]; pszSrc
0x18004f831  mov     rdx, rbx; cbDest
0x18004f834  mov     this, rax; pszDest
0x18004f837  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f83c  jmp     short loc_18004F84F
0x18004f83e  lea     this, [rdi+30h]; this
0x18004f842  lea     ppwzStr, [rsp+68h+cch]; pcch
0x18004f847  mov     rdx, r14; ppwsz
0x18004f84a  call    ?toString_CoTaskMemAlloc@SecureString@@QEAAJPEAPEAGPEAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x18004f84f  mov     ebx, eax
0x18004f851  test    eax, eax
0x18004f853  js      $CleanUp_31
0x18004f859  mov     ebp, r13d
0x18004f85c  jmp     $CleanUp_31
0x18004f861  cmp     ebx, 5
0x18004f864  jnz     short loc_18004F887
0x18004f866  cmp     esi, r13d
0x18004f869  jb      loc_18004F70B
0x18004f86f  cmp     [rdi+28h], bpl
0x18004f873  jz      loc_18004F70B
0x18004f879  cmp     [rdi+190h], ebp
0x18004f87f  jnz     loc_18004F70B
0x18004f885  jmp     short loc_18004F83E
0x18004f887  cmp     ebx, 6
0x18004f88a  jnz     short loc_18004F8B1
0x18004f88c  cmp     esi, r13d
0x18004f88f  jb      loc_18004F70B
0x18004f895  cmp     [rdi+28h], bpl
0x18004f899  jz      loc_18004F70B
0x18004f89f  cmp     [rdi+190h], ebp
0x18004f8a5  jnz     loc_18004F70B
0x18004f8ab  lea     this, [rdi+48h]
0x18004f8af  jmp     short loc_18004F842
0x18004f8b1  cmp     ebx, 16h
0x18004f8b4  jnz     short loc_18004F8D8
0x18004f8b6  cmp     esi, r13d
0x18004f8b9  jb      loc_18004F70B
0x18004f8bf  cmp     [rdi+19Ch], bpl
0x18004f8c6  jz      loc_18004F70B
0x18004f8cc  lea     this, [rdi+1A0h]
0x18004f8d3  jmp     loc_18004F842
0x18004f8d8  cmp     ebx, 17h
0x18004f8db  jnz     short loc_18004F8FF
0x18004f8dd  cmp     esi, r13d
0x18004f8e0  jb      loc_18004F70B
0x18004f8e6  cmp     [rdi+19Ch], bpl
0x18004f8ed  jz      loc_18004F70B
0x18004f8f3  lea     this, [rdi+1B8h]
0x18004f8fa  jmp     loc_18004F842
0x18004f8ff  cmp     ebx, 18h
0x18004f902  jnz     loc_18004F70B
0x18004f908  cmp     esi, r13d
0x18004f90b  jb      loc_18004F70B
0x18004f911  lea     this, [rdi+288h]
0x18004f918  cmp     [this], ebp
0x18004f91a  jnz     loc_18004F842
0x18004f920  jmp     loc_18004F70B
0x18004f925  mov     this, [r14]; pv
0x18004f928  test    this, this
0x18004f92b  jz      loc_18004F72A
0x18004f931  jmp     loc_18004F79F
0x18004f936  mov     [r15], ebp
0x18004f939  jmp     loc_18004F733
0x18004f93e  add     r8w, 2
0x18004f943  mov     eax, 200h
0x18004f948  movzx   ecx, r8w
0x18004f94c  mov     ulStringType, 0D1h; id
0x18004f951  imul    ecx, eax
0x18004f954  lea     ppwzStr, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18004f95b  mov     cEl, ebx; _a1
0x18004f95e  or      cx, 3; LevelKeyword
0x18004f962  call    WPP_SF_d
0x18004f967  jmp     loc_18004F756
```
