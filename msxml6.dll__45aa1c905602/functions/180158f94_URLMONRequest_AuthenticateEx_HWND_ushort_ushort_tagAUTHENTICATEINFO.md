# URLMONRequest::AuthenticateEx(HWND__ * *,ushort * *,ushort * *,_tagAUTHENTICATEINFO *)

- ea: `0x180158f94`
- end: `0x180159238`
- name: `?AuthenticateEx@URLMONRequest@@IEAAJPEAPEAUHWND__@@PEAPEAG1PEAU_tagAUTHENTICATEINFO@@@Z`
- size: `676`
- prototype: `HRESULT __fastcall(URLMONRequest *this, HWND__ **phwnd, wchar_t **ppwszUsername, wchar_t **ppwszPassword, _tagAUTHENTICATEINFO *pAuthinfo)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180158e8c`
- `0x180159240`

## callees

- `0x1800a0f50`
- `0x180158f94`
- `0x180189008`
- `0x18018a438`
- `0x18018a498`
- `0x18018b0ec`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801591a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801591d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801591a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801591d0`

## pseudocode

```c
__int64 __fastcall URLMONRequest::AuthenticateEx(
        URLMONRequest *this,
        HWND__ **phwnd,
        wchar_t **ppwszUsername,
        wchar_t **ppwszPassword,
        _tagAUTHENTICATEINFO *pAuthinfo)
{
  wchar_t *v5; // rdi
  wchar_t *v7; // r14
  _tagAUTHENTICATEINFO *v11; // rsi
  unsigned int TraceGuid; // eax
  unsigned __int16 v13; // dx
  int v14; // esi
  unsigned int dwFlags; // r10d
  const _GUID *v16; // r8
  SecureString *p_username; // r9
  SecureString *p_password; // r15
  int v19; // eax
  BOOL fDisableUI; // ecx
  bool *p_fProxyPrompt; // rax
  wchar_t *v22; // rcx
  __int64 i; // rax
  wchar_t *v24; // rcx
  __int64 j; // rax
  wchar_t *pwszUserName; // [rsp+50h] [rbp-18h] BYREF
  wchar_t *pwszPassword; // [rsp+58h] [rbp-10h] BYREF
  unsigned int cchUserName; // [rsp+B0h] [rbp+48h] BYREF
  HWND__ **v30; // [rsp+B8h] [rbp+50h]
  unsigned int cchPassword; // [rsp+C0h] [rbp+58h] BYREF
  HWND__ *hwnd; // [rsp+C8h] [rbp+60h] BYREF

  v30 = phwnd;
  v5 = 0;
  v7 = 0;
  pwszUserName = 0;
  pwszPassword = 0;
  cchUserName = 0;
  cchPassword = 0;
  hwnd = 0;
  v11 = pAuthinfo;
  if ( (xmmword_1801FAD20 & 8) != 0 )
  {
    if ( pAuthinfo )
      TraceGuid = pAuthinfo->dwFlags;
    else
      TraceGuid = 0;
    WPP_SF_qqqqqD(
      (unsigned __int16)this,
      (unsigned __int16)phwnd,
      (const _GUID *)ppwszUsername,
      this,
      phwnd,
      ppwszUsername,
      ppwszPassword,
      pAuthinfo,
      TraceGuid);
  }
  *phwnd = 0;
  *ppwszUsername = 0;
  *ppwszPassword = 0;
  this->Lock(this);
  if ( !(__int64)g_pfnEntry() )
  {
    v14 = -2147467259;
    goto $CleanUp_516;
  }
  dwFlags = v11->dwFlags;
  v16 = (const _GUID *)(v11->dwFlags & 1);
  if ( (v11->dwFlags & 1) != 0 )
  {
    p_username = (SecureString *)((unsigned __int64)&this->_ssProxyUserName & -(__int64)this->_fProxyUserNameAndPassword);
    LOBYTE(v13) = -this->_fProxyUserNameAndPassword;
    p_password = (SecureString *)((unsigned __int64)&this->_ssProxyPassword & -(__int64)this->_fProxyUserNameAndPassword);
  }
  else
  {
    if ( !this->_fUseridAndPassword || this->_dwAuth )
    {
LABEL_19:
      fDisableUI = this->_fDisableUI;
      if ( !fDisableUI || (p_fProxyPrompt = &this->_fProxyPrompt, (_DWORD)v16) && *p_fProxyPrompt )
      {
        v14 = this->_pRequestSite->get_window(this->_pRequestSite, &IID_IAuthenticate, &hwnd);
      }
      else
      {
        v14 = 0;
        if ( (BYTE8(xmmword_1801FAD10) & 2) != 0 )
          WPP_SF_Dll(fDisableUI, v13, v16, dwFlags, fDisableUI, *p_fProxyPrompt);
        hwnd = (HWND__ *)-1LL;
      }
LABEL_26:
      if ( (xmmword_1801FAD20 & 8) != 0 )
        WPP_SF_SSq(fDisableUI, v13, v16, v5, v7, hwnd);
      *v30 = hwnd;
      *ppwszUsername = v5;
      v5 = 0;
      *ppwszPassword = v7;
      v7 = 0;
      hwnd = 0;
      goto $CleanUp_516;
    }
    p_username = &this->_username;
    p_password = &this->_password;
  }
  if ( !p_username || !p_password )
    goto LABEL_19;
  v14 = SecureString::toString_CoTaskMemAlloc(p_username, &pwszUserName, &cchUserName);
  if ( v14 < 0 )
  {
    v5 = pwszUserName;
    goto $CleanUp_516;
  }
  v19 = SecureString::toString_CoTaskMemAlloc(p_password, &pwszPassword, &cchPassword);
  v5 = pwszUserName;
  v14 = v19;
  v7 = pwszPassword;
  if ( v19 >= 0 )
    goto LABEL_26;
$CleanUp_516:
  this->Unlock(this);
  if ( v5 )
  {
    v22 = v5;
    for ( i = 2LL * cchUserName; i; --i )
    {
      *(_BYTE *)v22 = 0;
      v22 = (wchar_t *)((char *)v22 + 1);
    }
    CoTaskMemFree(v5);
  }
  if ( v7 )
  {
    v24 = v7;
    for ( j = 2LL * cchPassword; j; --j )
    {
      *(_BYTE *)v24 = 0;
      v24 = (wchar_t *)((char *)v24 + 1);
    }
    CoTaskMemFree(v7);
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v14 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(v14 >> 31) + 2) << 9) | 3,
      0xD7u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180158f94  mov     [rsp-40h+arg_8], phwnd
0x180158f99  push    rbp
0x180158f9a  push    rbx
0x180158f9b  push    rsi
0x180158f9c  push    rdi
0x180158f9d  push    r12
0x180158f9f  push    r13
0x180158fa1  push    r14
0x180158fa3  push    r15
0x180158fa5  mov     rbp, rsp
0x180158fa8  sub     rsp, 68h
0x180158fac  xor     edi, edi
0x180158fae  mov     r12, ppwszPassword
0x180158fb1  xor     r14d, r14d
0x180158fb4  mov     [rbp+pwszUserName], rdi
0x180158fb8  mov     [rbp+pwszPassword], r14
0x180158fbc  mov     r13, ppwszUsername
0x180158fbf  mov     r15, phwnd
0x180158fc2  mov     [rbp+cchUserName], edi
0x180158fc5  mov     rbx, this
0x180158fc8  mov     [rbp+cchPassword], edi
0x180158fcb  mov     [rbp+hwnd], rdi
0x180158fcf  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180158fd6  mov     rsi, [rbp+arg_20]
0x180158fda  jz      short loc_180159007
0x180158fdc  test    rsi, rsi
0x180158fdf  jz      short loc_180158FE5
0x180158fe1  mov     eax, [rsi]
0x180158fe3  jmp     short loc_180158FE7
0x180158fe5  xor     eax, eax
0x180158fe7  mov     [rsp+68h+TraceGuid], eax; TraceGuid
0x180158feb  mov     ppwszPassword, rbx; _a4
0x180158fee  mov     [rsp+68h+id], rsi; id
0x180158ff3  mov     [rsp+68h+LevelKeyword], r12; LevelKeyword
0x180158ff8  mov     [rsp+68h+_a6], r13; _a6
0x180158ffd  mov     [rsp+68h+_a5], r15; _a5
0x180159002  call    WPP_SF_qqqqqD
0x180159007  mov     [r15], rdi
0x18015900a  mov     this, rbx
0x18015900d  mov     [r13+0], rdi
0x180159011  mov     [r12], rdi
0x180159015  mov     rax, [rbx]
0x180159018  mov     rax, [rax+0F8h]
0x18015901f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159024  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18015902b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159030  test    rax, rax
0x180159033  jnz     short loc_18015903F
0x180159035  mov     esi, 80004005h
0x18015903a  jmp     $CleanUp_516
0x18015903f  mov     r10d, [rsi]
0x180159042  mov     r8d, r10d
0x180159045  and     r8d, 1; _a3
0x180159049  jz      short loc_180159073
0x18015904b  mov     dl, [rbx+19Bh]
0x180159051  lea     this, [rbx+1A0h]
0x180159058  mov     al, dl
0x18015905a  neg     al
0x18015905c  lea     rax, [rbx+1B8h]
0x180159063  sbb     ppwszPassword, ppwszPassword
0x180159066  and     ppwszPassword, this
0x180159069  neg     dl
0x18015906b  sbb     r15, r15
0x18015906e  and     r15, rax
0x180159071  jmp     short loc_180159089
0x180159073  cmp     [rbx+28h], dil
0x180159077  jz      short loc_1801590D5
0x180159079  cmp     [rbx+190h], edi
0x18015907f  jnz     short loc_1801590D5
0x180159081  lea     ppwszPassword, [rbx+30h]
0x180159085  lea     r15, [rbx+48h]
0x180159089  test    ppwszPassword, ppwszPassword
0x18015908c  jz      short loc_1801590D5
0x18015908e  test    r15, r15
0x180159091  jz      short loc_1801590D5
0x180159093  lea     ppwszUsername, [rbp+cchUserName]; pcch
0x180159097  mov     this, ppwszPassword; this
0x18015909a  lea     phwnd, [rbp+pwszUserName]; ppwsz
0x18015909e  call    ?toString_CoTaskMemAlloc@SecureString@@QEAAJPEAPEAGPEAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x1801590a3  mov     esi, eax
0x1801590a5  test    eax, eax
0x1801590a7  js      short loc_1801590CC
0x1801590a9  lea     ppwszUsername, [rbp+cchPassword]; pcch
0x1801590ad  mov     this, r15; this
0x1801590b0  lea     phwnd, [rbp+pwszPassword]; ppwsz
0x1801590b4  call    ?toString_CoTaskMemAlloc@SecureString@@QEAAJPEAPEAGPEAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x1801590b9  mov     rdi, [rbp+pwszUserName]
0x1801590bd  mov     esi, eax
0x1801590bf  mov     r14, [rbp+pwszPassword]
0x1801590c3  test    eax, eax
0x1801590c5  jns     short loc_180159139
0x1801590c7  jmp     $CleanUp_516
0x1801590cc  mov     rdi, [rbp+pwszUserName]
0x1801590d0  jmp     $CleanUp_516
0x1801590d5  movzx   ecx, byte ptr [rbx+195h]; _a1
0x1801590dc  test    cl, cl
0x1801590de  jz      short loc_180159119
0x1801590e0  lea     rax, [rbx+196h]
0x1801590e7  test    r8d, r8d
0x1801590ea  jz      short loc_1801590F1
0x1801590ec  cmp     [rax], dil
0x1801590ef  jnz     short loc_180159119
0x1801590f1  xor     esi, esi; __annotation("TMF:",
0x1801590f3  test    byte ptr cs:xmmword_1801FAD10+8, 2
0x1801590fa  jz      short loc_18015910F
0x1801590fc  movzx   eax, byte ptr [rax]
0x1801590ff  mov     r9d, r10d; LevelKeyword
0x180159102  mov     dword ptr [rsp+68h+_a6], eax; TraceGuid
0x180159106  mov     dword ptr [rsp+68h+_a5], ecx; id
0x18015910a  call    WPP_SF_Dll
0x18015910f  mov     [rbp+hwnd], 0FFFFFFFFFFFFFFFFh
0x180159117  jmp     short loc_180159139
0x180159119  mov     this, [rbx+0A0h]
0x180159120  lea     ppwszUsername, [rbp+hwnd]
0x180159124  lea     phwnd, IID_IAuthenticate
0x18015912b  mov     rax, [this]
0x18015912e  mov     rax, [rax+28h]
0x180159132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159137  mov     esi, eax
0x180159139  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180159140  jz      short loc_180159158
0x180159142  mov     rax, [rbp+hwnd]
0x180159146  mov     ppwszPassword, rdi; LevelKeyword
0x180159149  mov     [rsp+68h+_a6], rax; TraceGuid
0x18015914e  mov     [rsp+68h+_a5], r14; id
0x180159153  call    WPP_SF_SSq
0x180159158  mov     rax, [rbp+hwnd]
0x18015915c  mov     this, [rbp+arg_8]
0x180159160  mov     [this], rax
0x180159163  mov     [r13+0], rdi
0x180159167  xor     edi, edi
0x180159169  mov     [r12], r14
0x18015916d  xor     r14d, r14d
0x180159170  mov     [rbp+hwnd], rdi
0x180159174  mov     rax, [rbx]
0x180159177  mov     this, rbx
0x18015917a  mov     rax, [rax+100h]
0x180159181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159186  test    rdi, rdi
0x180159189  jz      short loc_1801591B1
0x18015918b  mov     eax, [rbp+cchUserName]
0x18015918e  mov     this, rdi
0x180159191  add     rax, rax
0x180159194  jz      short loc_1801591A2
0x180159196  mov     byte ptr [this], 0
0x180159199  inc     this
0x18015919c  sub     rax, 1
0x1801591a0  jnz     short loc_180159196
0x1801591a2  mov     this, rdi; pv
0x1801591a5  call    cs:__imp_CoTaskMemFree
0x1801591ac  nop     dword ptr [rax+rax+00h]
0x1801591b1  test    r14, r14
0x1801591b4  jz      short loc_1801591DC
0x1801591b6  mov     eax, [rbp+cchPassword]
0x1801591b9  mov     this, r14
0x1801591bc  add     rax, rax
0x1801591bf  jz      short loc_1801591CD
0x1801591c1  mov     byte ptr [this], 0
0x1801591c4  inc     this
0x1801591c7  sub     rax, 1
0x1801591cb  jnz     short loc_1801591C1
0x1801591cd  mov     this, r14; pv
0x1801591d0  call    cs:__imp_CoTaskMemFree
0x1801591d7  nop     dword ptr [rax+rax+00h]
0x1801591dc  mov     r8d, esi; __annotation("TMF:",
0x1801591df  sar     r8d, 1Fh
0x1801591e3  lea     eax, ds:4[ppwszUsername*2]
0x1801591eb  movsxd  this, eax
0x1801591ee  lea     rax, g_rgFastWppLevelEnabledFlags
0x1801591f5  test    byte ptr [rax+this*8], 8
0x1801591f9  jz      short loc_180159224
0x1801591fb  add     r8w, 2
0x180159200  mov     eax, 200h
0x180159205  movzx   ecx, r8w
0x180159209  mov     edx, 0D7h; id
0x18015920e  imul    ecx, eax
0x180159211  lea     ppwszUsername, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159218  mov     r9d, esi; _a1
0x18015921b  or      cx, 3; LevelKeyword
0x18015921f  call    WPP_SF_d
0x180159224  mov     eax, esi
0x180159226  add     rsp, 68h
0x18015922a  pop     r15
0x18015922c  pop     r14
0x18015922e  pop     r13
0x180159230  pop     r12
0x180159232  pop     rdi
0x180159233  pop     rsi
0x180159234  pop     rbx
0x180159235  pop     rbp
0x180159236  retn
```
