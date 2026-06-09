# EapHost::HostPeerApis::EapHostPeerGetEncryptedPassword(ulong,wchar_t *,wchar_t * *)

- ea: `0x1800062f0`
- end: `0x18000656f`
- name: `?EapHostPeerGetEncryptedPassword@HostPeerApis@EapHost@@UEAAJKPEA_WPEAPEA_W@Z`
- size: `639`
- prototype: `int(EapHost::HostPeerApis *__hidden this, unsigned int, wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800062f0`
- `0x18000a21c`
- `0x18000a24c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000643a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000643a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800063c7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800063c7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000652e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000652e`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18000642a`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x1800064e7`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18000642a`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x1800064e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006553`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180006366`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180006366`

## pseudocode

```c
__int64 __fastcall EapHost::HostPeerApis::EapHostPeerGetEncryptedPassword(
        EapHost::HostPeerApis *this,
        __int64 a2,
        wchar_t *a3,
        wchar_t **a4)
{
  __int64 v4; // rsi
  wchar_t *v8; // rdi
  signed int LastError; // ebx
  EapHost::Peer::Host *v10; // rcx
  __int64 v11; // rdx
  EapHost::Peer::Host *v12; // rcx
  __int64 v13; // rdx
  bool v14; // sf
  HANDLE hToken[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD pcchMaxChars; // [rsp+98h] [rbp+20h] BYREF

  v4 = -1;
  hToken[0] = (HANDLE)-1LL;
  pcchMaxChars = 0;
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids);
    }
    return 87;
  }
  v8 = 0;
  *a4 = 0;
  do
    ++v4;
  while ( a3[v4] );
  if ( !(unsigned int)QueryUserToken(0, hToken) )
  {
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_33;
    }
    v11 = 54;
    goto LABEL_12;
  }
  if ( ImpersonateLoggedOnUser(hToken[0]) )
  {
    if ( CredProtectW(0, a3, v4, 0, &pcchMaxChars, 0) || (LastError = GetLastError(), LastError == 122) )
    {
      v8 = (wchar_t *)CoTaskMemAlloc(2LL * pcchMaxChars);
      if ( v8 )
      {
        if ( CredProtectW(0, a3, v4, v8, &pcchMaxChars, 0) )
        {
          *a4 = v8;
          LastError = 0;
          goto LABEL_32;
        }
        LastError = GetLastError();
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_32;
        }
        v13 = 58;
      }
      else
      {
        LastError = 8;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_32;
        }
        v13 = 57;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_32;
      }
      v13 = 56;
    }
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, (unsigned int)LastError);
LABEL_32:
    RevertToSelf();
    goto LABEL_33;
  }
  LastError = GetLastError();
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
  {
    goto LABEL_33;
  }
  v11 = 55;
LABEL_12:
  WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, (unsigned int)LastError);
LABEL_33:
  v14 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = LastError < 0;
  }
  if ( v14 && v8 )
    CoTaskMemFree(v8);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800062f0  mov     rax, rsp
0x1800062f3  push    rbx
0x1800062f4  push    rbp
0x1800062f5  push    rsi
0x1800062f6  push    rdi
0x1800062f7  push    r14
0x1800062f9  push    r15
0x1800062fb  sub     rsp, 48h
0x1800062ff  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006303  xor     r15d, r15d
0x180006306  mov     [rax-48h], rsi
0x18000630a  mov     r14, r9
0x18000630d  mov     [rax+20h], r15d
0x180006311  mov     rbp, r8
0x180006314  test    r9, r9
0x180006317  jnz     short loc_18000634F
0x180006319  mov     rcx, cs:WPP_GLOBAL_Control
0x180006320  lea     rax, WPP_GLOBAL_Control
0x180006327  cmp     rcx, rax
0x18000632a  jz      short loc_180006345
0x18000632c  test    byte ptr [rcx+1Ch], 1
0x180006330  jz      short loc_180006345
0x180006332  mov     rcx, [rcx+10h]
0x180006336  lea     edx, [rsi+36h]
0x180006339  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006340  call    WPP_SF_
0x180006345  mov     eax, 57h ; 'W'
0x18000634a  jmp     loc_180006561
0x18000634f  mov     rdi, r15
0x180006352  mov     [r9], r15
0x180006355  inc     rsi
0x180006358  cmp     [r8+rsi*2], r15w
0x18000635d  jnz     short loc_180006355
0x18000635f  lea     rdx, [rsp+78h+hToken]
0x180006364  xor     ecx, ecx
0x180006366  call    cs:__imp_QueryUserToken
0x18000636d  nop     dword ptr [rax+rax+00h]
0x180006372  test    eax, eax
0x180006374  jnz     short loc_1800063C2
0x180006376  call    cs:__imp_GetLastError
0x18000637d  nop     dword ptr [rax+rax+00h]
0x180006382  mov     ebx, eax
0x180006384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000638b  lea     rax, WPP_GLOBAL_Control
0x180006392  cmp     rcx, rax
0x180006395  jz      loc_18000653A
0x18000639b  test    byte ptr [rcx+1Ch], 4
0x18000639f  jz      loc_18000653A
0x1800063a5  mov     edx, 36h ; '6'
0x1800063aa  mov     rcx, [rcx+10h]
0x1800063ae  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800063b5  mov     r9d, ebx
0x1800063b8  call    WPP_SF_d
0x1800063bd  jmp     loc_18000653A
0x1800063c2  mov     rcx, [rsp+78h+hToken]; hToken
0x1800063c7  call    cs:__imp_ImpersonateLoggedOnUser
0x1800063ce  nop     dword ptr [rax+rax+00h]
0x1800063d3  test    eax, eax
0x1800063d5  jnz     short loc_18000640D
0x1800063d7  call    cs:__imp_GetLastError
0x1800063de  nop     dword ptr [rax+rax+00h]
0x1800063e3  mov     ebx, eax
0x1800063e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063ec  lea     rax, WPP_GLOBAL_Control
0x1800063f3  cmp     rcx, rax
0x1800063f6  jz      loc_18000653A
0x1800063fc  test    byte ptr [rcx+1Ch], 4
0x180006400  jz      loc_18000653A
0x180006406  mov     edx, 37h ; '7'
0x18000640b  jmp     short loc_1800063AA
0x18000640d  lea     rax, [rsp+78h+arg_18]
0x180006415  mov     [rsp+78h+ProtectionType], r15; ProtectionType
0x18000641a  xor     r9d, r9d; pszProtectedCredentials
0x18000641d  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x180006422  mov     r8d, esi; cchCredentials
0x180006425  mov     rdx, rbp; pszCredentials
0x180006428  xor     ecx, ecx; fAsSelf
0x18000642a  call    cs:__imp_CredProtectW
0x180006431  nop     dword ptr [rax+rax+00h]
0x180006436  test    eax, eax
0x180006438  jnz     short loc_18000648B
0x18000643a  call    cs:__imp_GetLastError
0x180006441  nop     dword ptr [rax+rax+00h]
0x180006446  mov     ebx, eax
0x180006448  cmp     eax, 7Ah ; 'z'
0x18000644b  jz      short loc_18000648B
0x18000644d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006454  lea     rax, WPP_GLOBAL_Control
0x18000645b  cmp     rcx, rax
0x18000645e  jz      loc_18000652E
0x180006464  test    byte ptr [rcx+1Ch], 4
0x180006468  jz      loc_18000652E
0x18000646e  mov     edx, 38h ; '8'
0x180006473  mov     rcx, [rcx+10h]
0x180006477  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000647e  mov     r9d, ebx
0x180006481  call    WPP_SF_d
0x180006486  jmp     loc_18000652E
0x18000648b  mov     ecx, [rsp+78h+arg_18]
0x180006492  add     rcx, rcx; cb
0x180006495  call    cs:__imp_CoTaskMemAlloc
0x18000649c  nop     dword ptr [rax+rax+00h]
0x1800064a1  mov     rdi, rax
0x1800064a4  test    rax, rax
0x1800064a7  jnz     short loc_1800064CA
0x1800064a9  lea     ebx, [rax+8]
0x1800064ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064b3  lea     rax, WPP_GLOBAL_Control
0x1800064ba  cmp     rcx, rax
0x1800064bd  jz      short loc_18000652E
0x1800064bf  test    byte ptr [rcx+1Ch], 4
0x1800064c3  jz      short loc_18000652E
0x1800064c5  lea     edx, [rdi+39h]
0x1800064c8  jmp     short loc_180006473
0x1800064ca  lea     rax, [rsp+78h+arg_18]
0x1800064d2  mov     [rsp+78h+ProtectionType], r15; ProtectionType
0x1800064d7  mov     r9, rdi; pszProtectedCredentials
0x1800064da  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x1800064df  mov     r8d, esi; cchCredentials
0x1800064e2  mov     rdx, rbp; pszCredentials
0x1800064e5  xor     ecx, ecx; fAsSelf
0x1800064e7  call    cs:__imp_CredProtectW
0x1800064ee  nop     dword ptr [rax+rax+00h]
0x1800064f3  test    eax, eax
0x1800064f5  jnz     short loc_180006528
0x1800064f7  call    cs:__imp_GetLastError
0x1800064fe  nop     dword ptr [rax+rax+00h]
0x180006503  mov     ebx, eax
0x180006505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000650c  lea     rax, WPP_GLOBAL_Control
0x180006513  cmp     rcx, rax
0x180006516  jz      short loc_18000652E
0x180006518  test    byte ptr [rcx+1Ch], 4
0x18000651c  jz      short loc_18000652E
0x18000651e  mov     edx, 3Ah ; ':'
0x180006523  jmp     loc_180006473
0x180006528  mov     [r14], rdi
0x18000652b  mov     ebx, r15d
0x18000652e  call    cs:__imp_RevertToSelf
0x180006535  nop     dword ptr [rax+rax+00h]
0x18000653a  test    ebx, ebx
0x18000653c  jle     short loc_180006549
0x18000653e  movzx   ebx, bx
0x180006541  or      ebx, 80070000h
0x180006547  test    ebx, ebx
0x180006549  jns     short loc_18000655F
0x18000654b  test    rdi, rdi
0x18000654e  jz      short loc_18000655F
0x180006550  mov     rcx, rdi; pv
0x180006553  call    cs:__imp_CoTaskMemFree
0x18000655a  nop     dword ptr [rax+rax+00h]
0x18000655f  mov     eax, ebx
0x180006561  add     rsp, 48h
0x180006565  pop     r15
0x180006567  pop     r14
0x180006569  pop     rdi
0x18000656a  pop     rsi
0x18000656b  pop     rbp
0x18000656c  pop     rbx
0x18000656d  retn
```
