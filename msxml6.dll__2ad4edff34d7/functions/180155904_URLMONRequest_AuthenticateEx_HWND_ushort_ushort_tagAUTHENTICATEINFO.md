# URLMONRequest::AuthenticateEx(HWND__ * *,ushort * *,ushort * *,_tagAUTHENTICATEINFO *)

- ea: `0x180155904`
- end: `0x180155b9b`
- name: `?AuthenticateEx@URLMONRequest@@IEAAJPEAPEAUHWND__@@PEAPEAG1PEAU_tagAUTHENTICATEINFO@@@Z`
- size: `663`
- prototype: `HRESULT __fastcall(URLMONRequest *this, HWND__ **phwnd, wchar_t **ppwszUsername, wchar_t **ppwszPassword, _tagAUTHENTICATEINFO *pAuthinfo)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801557fc`
- `0x180155bb0`

## callees

- `0x1800a0708`
- `0x180155904`
- `0x180185008`
- `0x18018641c`
- `0x18018647c`
- `0x1801870b4`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180155b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180155b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180155b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180155b3a`

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
  if ( (xmmword_1801F6C20 & 8) != 0 )
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
        if ( (BYTE8(xmmword_1801F6C10) & 2) != 0 )
          WPP_SF_Dll(fDisableUI, v13, v16, dwFlags, fDisableUI, *p_fProxyPrompt);
        hwnd = (HWND__ *)-1LL;
      }
LABEL_26:
      if ( (xmmword_1801F6C20 & 8) != 0 )
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
0x180155904  mov     [rsp-40h+arg_8], phwnd
0x180155909  push    rbp
0x18015590a  push    rbx
0x18015590b  push    rsi
0x18015590c  push    rdi
0x18015590d  push    r12
0x18015590f  push    r13
0x180155911  push    r14
0x180155913  push    r15
0x180155915  mov     rbp, rsp
0x180155918  sub     rsp, 68h
0x18015591c  xor     edi, edi
0x18015591e  mov     r12, ppwszPassword
0x180155921  xor     r14d, r14d
0x180155924  mov     [rbp+pwszUserName], rdi
0x180155928  mov     [rbp+pwszPassword], r14
0x18015592c  mov     r13, ppwszUsername
0x18015592f  mov     r15, phwnd
0x180155932  mov     [rbp+cchUserName], edi
0x180155935  mov     rbx, this
0x180155938  mov     [rbp+cchPassword], edi
0x18015593b  mov     [rbp+hwnd], rdi
0x18015593f  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180155946  mov     rsi, [rbp+arg_20]
0x18015594a  jz      short loc_180155977
0x18015594c  test    rsi, rsi
0x18015594f  jz      short loc_180155955
0x180155951  mov     eax, [rsi]
0x180155953  jmp     short loc_180155957
0x180155955  xor     eax, eax
0x180155957  mov     [rsp+68h+TraceGuid], eax; TraceGuid
0x18015595b  mov     ppwszPassword, rbx; _a4
0x18015595e  mov     [rsp+68h+id], rsi; id
0x180155963  mov     [rsp+68h+LevelKeyword], r12; LevelKeyword
0x180155968  mov     [rsp+68h+_a6], r13; _a6
0x18015596d  mov     [rsp+68h+_a5], r15; _a5
0x180155972  call    WPP_SF_qqqqqD
0x180155977  mov     [r15], rdi
0x18015597a  mov     this, rbx
0x18015597d  mov     [r13+0], rdi
0x180155981  mov     [r12], rdi
0x180155985  mov     rax, [rbx]
0x180155988  mov     rax, [rax+0F8h]
0x18015598f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155994  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18015599b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801559a0  test    rax, rax
0x1801559a3  jnz     short loc_1801559AF
0x1801559a5  mov     esi, 80004005h
0x1801559aa  jmp     $CleanUp_516
0x1801559af  mov     r10d, [rsi]
0x1801559b2  mov     r8d, r10d
0x1801559b5  and     r8d, 1; _a3
0x1801559b9  jz      short loc_1801559E3
0x1801559bb  mov     dl, [rbx+19Bh]
0x1801559c1  lea     this, [rbx+1A0h]
0x1801559c8  mov     al, dl
0x1801559ca  neg     al
0x1801559cc  lea     rax, [rbx+1B8h]
0x1801559d3  sbb     ppwszPassword, ppwszPassword
0x1801559d6  and     ppwszPassword, this
0x1801559d9  neg     dl
0x1801559db  sbb     r15, r15
0x1801559de  and     r15, rax
0x1801559e1  jmp     short loc_1801559F9
0x1801559e3  cmp     [rbx+28h], dil
0x1801559e7  jz      short loc_180155A45
0x1801559e9  cmp     [rbx+190h], edi
0x1801559ef  jnz     short loc_180155A45
0x1801559f1  lea     ppwszPassword, [rbx+30h]
0x1801559f5  lea     r15, [rbx+48h]
0x1801559f9  test    ppwszPassword, ppwszPassword
0x1801559fc  jz      short loc_180155A45
0x1801559fe  test    r15, r15
0x180155a01  jz      short loc_180155A45
0x180155a03  lea     ppwszUsername, [rbp+cchUserName]; pcch
0x180155a07  mov     this, ppwszPassword; this
0x180155a0a  lea     phwnd, [rbp+pwszUserName]; ppwsz
0x180155a0e  call    ?toString_CoTaskMemAlloc@SecureString@@QEAAJPEAPEAGPEAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x180155a13  mov     esi, eax
0x180155a15  test    eax, eax
0x180155a17  js      short loc_180155A3C
0x180155a19  lea     ppwszUsername, [rbp+cchPassword]; pcch
0x180155a1d  mov     this, r15; this
0x180155a20  lea     phwnd, [rbp+pwszPassword]; ppwsz
0x180155a24  call    ?toString_CoTaskMemAlloc@SecureString@@QEAAJPEAPEAGPEAK@Z; SecureString::toString_CoTaskMemAlloc(ushort * *,ulong *)
0x180155a29  mov     rdi, [rbp+pwszUserName]
0x180155a2d  mov     esi, eax
0x180155a2f  mov     r14, [rbp+pwszPassword]
0x180155a33  test    eax, eax
0x180155a35  jns     short loc_180155AA9
0x180155a37  jmp     $CleanUp_516
0x180155a3c  mov     rdi, [rbp+pwszUserName]
0x180155a40  jmp     $CleanUp_516
0x180155a45  movzx   ecx, byte ptr [rbx+195h]; _a1
0x180155a4c  test    cl, cl
0x180155a4e  jz      short loc_180155A89
0x180155a50  lea     rax, [rbx+196h]
0x180155a57  test    r8d, r8d
0x180155a5a  jz      short loc_180155A61
0x180155a5c  cmp     [rax], dil
0x180155a5f  jnz     short loc_180155A89
0x180155a61  xor     esi, esi; __annotation("TMF:",
0x180155a63  test    byte ptr cs:xmmword_1801F6C10+8, 2
0x180155a6a  jz      short loc_180155A7F
0x180155a6c  movzx   eax, byte ptr [rax]
0x180155a6f  mov     r9d, r10d; LevelKeyword
0x180155a72  mov     dword ptr [rsp+68h+_a6], eax; TraceGuid
0x180155a76  mov     dword ptr [rsp+68h+_a5], ecx; id
0x180155a7a  call    WPP_SF_Dll
0x180155a7f  mov     [rbp+hwnd], 0FFFFFFFFFFFFFFFFh
0x180155a87  jmp     short loc_180155AA9
0x180155a89  mov     this, [rbx+0A0h]
0x180155a90  lea     ppwszUsername, [rbp+hwnd]
0x180155a94  lea     phwnd, IID_IAuthenticate
0x180155a9b  mov     rax, [this]
0x180155a9e  mov     rax, [rax+28h]
0x180155aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155aa7  mov     esi, eax
0x180155aa9  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180155ab0  jz      short loc_180155AC8
0x180155ab2  mov     rax, [rbp+hwnd]
0x180155ab6  mov     ppwszPassword, rdi; LevelKeyword
0x180155ab9  mov     [rsp+68h+_a6], rax; TraceGuid
0x180155abe  mov     [rsp+68h+_a5], r14; id
0x180155ac3  call    WPP_SF_SSq
0x180155ac8  mov     rax, [rbp+hwnd]
0x180155acc  mov     this, [rbp+arg_8]
0x180155ad0  mov     [this], rax
0x180155ad3  mov     [r13+0], rdi
0x180155ad7  xor     edi, edi
0x180155ad9  mov     [r12], r14
0x180155add  xor     r14d, r14d
0x180155ae0  mov     [rbp+hwnd], rdi
0x180155ae4  mov     rax, [rbx]
0x180155ae7  mov     this, rbx
0x180155aea  mov     rax, [rax+100h]
0x180155af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155af6  test    rdi, rdi
0x180155af9  jz      short loc_180155B1B
0x180155afb  mov     eax, [rbp+cchUserName]
0x180155afe  mov     this, rdi
0x180155b01  add     rax, rax
0x180155b04  jz      short loc_180155B12
0x180155b06  mov     byte ptr [this], 0
0x180155b09  inc     this
0x180155b0c  sub     rax, 1
0x180155b10  jnz     short loc_180155B06
0x180155b12  mov     this, rdi; pv
0x180155b15  call    cs:__imp_CoTaskMemFree
0x180155b1b  test    r14, r14
0x180155b1e  jz      short loc_180155B40
0x180155b20  mov     eax, [rbp+cchPassword]
0x180155b23  mov     this, r14
0x180155b26  add     rax, rax
0x180155b29  jz      short loc_180155B37
0x180155b2b  mov     byte ptr [this], 0
0x180155b2e  inc     this
0x180155b31  sub     rax, 1
0x180155b35  jnz     short loc_180155B2B
0x180155b37  mov     this, r14; pv
0x180155b3a  call    cs:__imp_CoTaskMemFree
0x180155b40  mov     r8d, esi; __annotation("TMF:",
0x180155b43  sar     r8d, 1Fh
0x180155b47  lea     eax, ds:4[ppwszUsername*2]
0x180155b4f  movsxd  this, eax
0x180155b52  lea     rax, g_rgFastWppLevelEnabledFlags
0x180155b59  test    byte ptr [rax+this*8], 8
0x180155b5d  jz      short loc_180155B88
0x180155b5f  add     r8w, 2
0x180155b64  mov     eax, 200h
0x180155b69  movzx   ecx, r8w
0x180155b6d  mov     edx, 0D7h; id
0x180155b72  imul    ecx, eax
0x180155b75  lea     ppwszUsername, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180155b7c  mov     r9d, esi; _a1
0x180155b7f  or      cx, 3; LevelKeyword
0x180155b83  call    WPP_SF_d
0x180155b88  mov     eax, esi
0x180155b8a  add     rsp, 68h
0x180155b8e  pop     r15
0x180155b90  pop     r14
0x180155b92  pop     r13
0x180155b94  pop     r12
0x180155b96  pop     rdi
0x180155b97  pop     rsi
0x180155b98  pop     rbx
0x180155b99  pop     rbp
0x180155b9a  retn
```
