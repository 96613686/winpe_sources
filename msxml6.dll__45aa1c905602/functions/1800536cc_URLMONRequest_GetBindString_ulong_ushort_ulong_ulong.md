# URLMONRequest::GetBindString(ulong,ushort * *,ulong,ulong *)

- ea: `0x1800536cc`
- end: `0x1800539bd`
- name: `?GetBindString@URLMONRequest@@IEAAJKPEAPEAGKPEAK@Z`
- size: `753`
- prototype: `HRESULT __fastcall(URLMONRequest *this, unsigned int ulStringType, wchar_t **ppwzStr, unsigned int cEl, unsigned int *pcElFetched)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801596f0`

## callees

- `0x1800536cc`
- `0x180054310`
- `0x18005d2c4`
- `0x1800a0f50`
- `0x18015a324`
- `0x180189008`
- `0x18018ad88`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053860`

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
  if ( (xmmword_1801FAD20 & 8) != 0 )
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
    goto $CleanUp_34;
  }
  if ( ulStringType == 14 )
  {
    if ( !cEl || (pwszTargetUrl = this->_pwszTargetUrl) == 0 )
    {
LABEL_7:
      v12 = -2146697198;
      goto $CleanUp_34;
    }
    v14 = xstrlenw(pwszTargetUrl, 0x7FFFFFFFu);
    cch = v14;
    v15 = v14 + 1LL;
    if ( v15 < v14
      || (pcElFetched = (unsigned int *)(v14 + 1LL), ULongLongMult(v15, 2u, (unsigned __int64 *)&pcElFetched) < 0)
      || (v19 = pcElFetched, (unsigned __int64)pcElFetched > v18) )
    {
      v12 = -2147024362;
      goto $CleanUp_34;
    }
    v20 = (wchar_t *)CoTaskMemAlloc((SIZE_T)pcElFetched);
    *ppwzStr = v20;
    if ( !v20 )
    {
      v12 = -2147024882;
      goto $CleanUp_34;
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
$CleanUp_34:
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
0x1800536cc  mov     [rsp+arg_8], rbx
0x1800536d1  mov     [rsp+arg_10], rbp
0x1800536d6  push    rsi
0x1800536d7  push    rdi
0x1800536d8  push    r13
0x1800536da  push    r14
0x1800536dc  push    r15
0x1800536de  sub     rsp, 40h
0x1800536e2  xor     ebp, ebp
0x1800536e4  mov     esi, cEl
0x1800536e7  mov     [rsp+68h+cch], ebp
0x1800536eb  mov     r14, ppwzStr
0x1800536ee  mov     ebx, ulStringType
0x1800536f0  mov     rdi, this
0x1800536f3  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x1800536fa  mov     r15, [rsp+68h+cb]
0x180053702  jnz     loc_18005380F
0x180053708  mov     [r14], rbp
0x18005370b  mov     this, rdi
0x18005370e  mov     rax, [rdi]
0x180053711  mov     rax, [rax+0F8h]
0x180053718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005371d  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180053724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053729  mov     r13d, 1
0x18005372f  test    rax, rax
0x180053732  jz      short loc_1800537B2
0x180053734  cmp     ebx, 0Eh
0x180053737  jnz     loc_1800538B2
0x18005373d  cmp     esi, r13d
0x180053740  jb      short loc_18005374B
0x180053742  mov     this, [rdi+60h]; psz
0x180053746  test    this, this
0x180053749  jnz     short loc_1800537B9
0x18005374b  mov     ebx, 800C0012h
0x180053750  mov     rax, [rdi]
0x180053753  mov     this, rdi
0x180053756  mov     rax, [rax+100h]
0x18005375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053762  test    ebx, ebx
0x180053764  js      loc_180053976
0x18005376a  test    r15, r15
0x18005376d  jnz     loc_180053987
0x180053773  mov     r8d, ebx; __annotation("TMF:",
0x180053776  sar     r8d, 1Fh
0x18005377a  lea     eax, ds:4[ppwzStr*2]
0x180053782  movsxd  this, eax
0x180053785  lea     rax, g_rgFastWppLevelEnabledFlags
0x18005378c  test    byte ptr [rax+this*8], 8
0x180053790  jnz     loc_18005398F
0x180053796  lea     r11, [rsp+68h+var_28]
0x18005379b  mov     eax, ebx
0x18005379d  mov     rbx, [r11+38h]
0x1800537a1  mov     rbp, [r11+40h]
0x1800537a5  mov     rsp, r11
0x1800537a8  pop     r15
0x1800537aa  pop     r14
0x1800537ac  pop     r13
0x1800537ae  pop     rdi
0x1800537af  pop     rsi
0x1800537b0  retn
0x1800537b2  mov     ebx, 80004005h
0x1800537b7  jmp     short $CleanUp_34
0x1800537b9  mov     cEl, 7FFFFFFFh
0x1800537bf  mov     ulStringType, cEl; cchMax
0x1800537c2  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800537c7  mov     ulStringType, eax
0x1800537c9  mov     [rsp+68h+cch], ulStringType
0x1800537cd  lea     this, [rdx+1]; ullMultiplicand
0x1800537d1  cmp     this, rdx
0x1800537d4  jnb     short loc_18005382E
0x1800537d6  mov     ebx, 80070216h
0x1800537db  jmp     $CleanUp_34
0x1800537e0  mov     eax, [rsp+68h+cch]
0x1800537e4  mov     rdx, this
0x1800537e7  add     rax, rax
0x1800537ea  jz      short loc_1800537F7
0x1800537ec  mov     byte ptr [rdx], 0
0x1800537ef  add     rdx, r13
0x1800537f2  sub     rax, r13
0x1800537f5  jnz     short loc_1800537EC
0x1800537f7  call    cs:__imp_CoTaskMemFree
0x1800537fe  nop     dword ptr [rax+rax+00h]
0x180053803  mov     qword ptr [r14], 0
0x18005380a  jmp     loc_18005376A
0x18005380f  mov     [rsp+68h+TraceGuid], r15; TraceGuid
0x180053814  mov     r9, rdi; _a4
0x180053817  mov     [rsp+68h+id], esi; id
0x18005381b  mov     [rsp+68h+LevelKeyword], r14; LevelKeyword
0x180053820  mov     [rsp+68h+_a5], ebx; _a5
0x180053824  call    WPP_SF_qdqdq
0x180053829  jmp     loc_180053708
0x18005382e  lea     ppwzStr, [rsp+68h+cb]; pullResult
0x180053836  mov     [rsp+68h+cb], this
0x18005383e  mov     ulStringType, 2; ullMultiplier
0x180053843  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180053848  test    eax, eax
0x18005384a  js      short loc_1800537D6
0x18005384c  mov     rbx, [rsp+68h+cb]
0x180053854  cmp     rbx, r9
0x180053857  ja      loc_1800537D6
0x18005385d  mov     this, rbx; cb
0x180053860  call    cs:__imp_CoTaskMemAlloc
0x180053867  nop     dword ptr [rax+rax+00h]
0x18005386c  mov     [r14], rax
0x18005386f  test    rax, rax
0x180053872  jnz     short loc_18005387E
0x180053874  mov     ebx, 8007000Eh
0x180053879  jmp     $CleanUp_34
0x18005387e  mov     ppwzStr, [rdi+60h]; pszSrc
0x180053882  mov     rdx, rbx; cbDest
0x180053885  mov     this, rax; pszDest
0x180053888  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18005388d  jmp     short loc_1800538A0
0x18005388f  lea     this, [rdi+30h]; this
0x180053893  lea     ppwzStr, [rsp+68h+cch]; pcch
0x180053898  mov     rdx, r14; ppwsz
0x18005389b  call    ?toString_CoTaskMemAlloc@SecureString@@QEAAJPEAPEAGPEAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x1800538a0  mov     ebx, eax
0x1800538a2  test    eax, eax
0x1800538a4  js      $CleanUp_34
0x1800538aa  mov     ebp, r13d
0x1800538ad  jmp     $CleanUp_34
0x1800538b2  cmp     ebx, 5
0x1800538b5  jnz     short loc_1800538D8
0x1800538b7  cmp     esi, r13d
0x1800538ba  jb      loc_18005374B
0x1800538c0  cmp     [rdi+28h], bpl
0x1800538c4  jz      loc_18005374B
0x1800538ca  cmp     [rdi+190h], ebp
0x1800538d0  jnz     loc_18005374B
0x1800538d6  jmp     short loc_18005388F
0x1800538d8  cmp     ebx, 6
0x1800538db  jnz     short loc_180053902
0x1800538dd  cmp     esi, r13d
0x1800538e0  jb      loc_18005374B
0x1800538e6  cmp     [rdi+28h], bpl
0x1800538ea  jz      loc_18005374B
0x1800538f0  cmp     [rdi+190h], ebp
0x1800538f6  jnz     loc_18005374B
0x1800538fc  lea     this, [rdi+48h]
0x180053900  jmp     short loc_180053893
0x180053902  cmp     ebx, 16h
0x180053905  jnz     short loc_180053929
0x180053907  cmp     esi, r13d
0x18005390a  jb      loc_18005374B
0x180053910  cmp     [rdi+19Ch], bpl
0x180053917  jz      loc_18005374B
0x18005391d  lea     this, [rdi+1A0h]
0x180053924  jmp     loc_180053893
0x180053929  cmp     ebx, 17h
0x18005392c  jnz     short loc_180053950
0x18005392e  cmp     esi, r13d
0x180053931  jb      loc_18005374B
0x180053937  cmp     [rdi+19Ch], bpl
0x18005393e  jz      loc_18005374B
0x180053944  lea     this, [rdi+1B8h]
0x18005394b  jmp     loc_180053893
0x180053950  cmp     ebx, 18h
0x180053953  jnz     loc_18005374B
0x180053959  cmp     esi, r13d
0x18005395c  jb      loc_18005374B
0x180053962  lea     this, [rdi+288h]
0x180053969  cmp     [this], ebp
0x18005396b  jnz     loc_180053893
0x180053971  jmp     loc_18005374B
0x180053976  mov     this, [r14]; pv
0x180053979  test    this, this
0x18005397c  jz      loc_18005376A
0x180053982  jmp     loc_1800537E0
0x180053987  mov     [r15], ebp
0x18005398a  jmp     loc_180053773
0x18005398f  add     r8w, 2
0x180053994  mov     eax, 200h
0x180053999  movzx   ecx, r8w
0x18005399d  mov     ulStringType, 0D1h; id
0x1800539a2  imul    ecx, eax
0x1800539a5  lea     ppwzStr, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800539ac  mov     cEl, ebx; _a1
0x1800539af  or      cx, 3; LevelKeyword
0x1800539b3  call    WPP_SF_d
0x1800539b8  jmp     loc_180053796
```
