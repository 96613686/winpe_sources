# EapHost::HostPeerApis::EapHostPeerGetEncryptedPassword(ulong,wchar_t *,wchar_t * *)

- ea: `0x1800060c0`
- end: `0x1800062fc`
- name: `?EapHostPeerGetEncryptedPassword@HostPeerApis@EapHost@@UEAAJKPEA_WPEAPEA_W@Z`
- size: `572`
- prototype: `int(EapHost::HostPeerApis *__hidden this, unsigned int, wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800060c0`
- `0x180009dc4`
- `0x180009dec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006297`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000618b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000618b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800062c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800062c8`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x1800061e2`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18000628d`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x1800061e2`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18000628d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062e7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180006136`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180006136`

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
0x1800060c0  mov     rax, rsp
0x1800060c3  push    rbx
0x1800060c4  push    rbp
0x1800060c5  push    rsi
0x1800060c6  push    rdi
0x1800060c7  push    r14
0x1800060c9  push    r15
0x1800060cb  sub     rsp, 48h
0x1800060cf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800060d3  xor     r15d, r15d
0x1800060d6  mov     [rax-48h], rsi
0x1800060da  mov     r14, r9
0x1800060dd  mov     [rax+20h], r15d
0x1800060e1  mov     rbp, r8
0x1800060e4  test    r9, r9
0x1800060e7  jnz     short loc_18000611F
0x1800060e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060f0  lea     rax, WPP_GLOBAL_Control
0x1800060f7  cmp     rcx, rax
0x1800060fa  jz      short loc_180006115
0x1800060fc  test    byte ptr [rcx+1Ch], 1
0x180006100  jz      short loc_180006115
0x180006102  mov     rcx, [rcx+10h]
0x180006106  lea     edx, [rsi+36h]
0x180006109  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006110  call    WPP_SF_
0x180006115  mov     eax, 57h ; 'W'
0x18000611a  jmp     loc_1800062EF
0x18000611f  mov     rdi, r15
0x180006122  mov     [r9], r15
0x180006125  inc     rsi
0x180006128  cmp     [r8+rsi*2], r15w
0x18000612d  jnz     short loc_180006125
0x18000612f  lea     rdx, [rsp+78h+hToken]
0x180006134  xor     ecx, ecx
0x180006136  call    cs:__imp_QueryUserToken
0x18000613c  test    eax, eax
0x18000613e  jnz     short loc_180006186
0x180006140  call    cs:__imp_GetLastError
0x180006146  mov     ebx, eax
0x180006148  mov     rcx, cs:WPP_GLOBAL_Control
0x18000614f  lea     rax, WPP_GLOBAL_Control
0x180006156  cmp     rcx, rax
0x180006159  jz      loc_1800062CE
0x18000615f  test    byte ptr [rcx+1Ch], 4
0x180006163  jz      loc_1800062CE
0x180006169  mov     edx, 36h ; '6'
0x18000616e  mov     rcx, [rcx+10h]
0x180006172  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006179  mov     r9d, ebx
0x18000617c  call    WPP_SF_d
0x180006181  jmp     loc_1800062CE
0x180006186  mov     rcx, [rsp+78h+hToken]; hToken
0x18000618b  call    cs:__imp_ImpersonateLoggedOnUser
0x180006191  test    eax, eax
0x180006193  jnz     short loc_1800061C5
0x180006195  call    cs:__imp_GetLastError
0x18000619b  mov     ebx, eax
0x18000619d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061a4  lea     rax, WPP_GLOBAL_Control
0x1800061ab  cmp     rcx, rax
0x1800061ae  jz      loc_1800062CE
0x1800061b4  test    byte ptr [rcx+1Ch], 4
0x1800061b8  jz      loc_1800062CE
0x1800061be  mov     edx, 37h ; '7'
0x1800061c3  jmp     short loc_18000616E
0x1800061c5  lea     rax, [rsp+78h+arg_18]
0x1800061cd  mov     [rsp+78h+ProtectionType], r15; ProtectionType
0x1800061d2  xor     r9d, r9d; pszProtectedCredentials
0x1800061d5  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x1800061da  mov     r8d, esi; cchCredentials
0x1800061dd  mov     rdx, rbp; pszCredentials
0x1800061e0  xor     ecx, ecx; fAsSelf
0x1800061e2  call    cs:__imp_CredProtectW
0x1800061e8  test    eax, eax
0x1800061ea  jnz     short loc_180006237
0x1800061ec  call    cs:__imp_GetLastError
0x1800061f2  mov     ebx, eax
0x1800061f4  cmp     eax, 7Ah ; 'z'
0x1800061f7  jz      short loc_180006237
0x1800061f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006200  lea     rax, WPP_GLOBAL_Control
0x180006207  cmp     rcx, rax
0x18000620a  jz      loc_1800062C8
0x180006210  test    byte ptr [rcx+1Ch], 4
0x180006214  jz      loc_1800062C8
0x18000621a  mov     edx, 38h ; '8'
0x18000621f  mov     rcx, [rcx+10h]
0x180006223  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000622a  mov     r9d, ebx
0x18000622d  call    WPP_SF_d
0x180006232  jmp     loc_1800062C8
0x180006237  mov     ecx, [rsp+78h+arg_18]
0x18000623e  add     rcx, rcx; cb
0x180006241  call    cs:__imp_CoTaskMemAlloc
0x180006247  mov     rdi, rax
0x18000624a  test    rax, rax
0x18000624d  jnz     short loc_180006270
0x18000624f  lea     ebx, [rax+8]
0x180006252  mov     rcx, cs:WPP_GLOBAL_Control
0x180006259  lea     rax, WPP_GLOBAL_Control
0x180006260  cmp     rcx, rax
0x180006263  jz      short loc_1800062C8
0x180006265  test    byte ptr [rcx+1Ch], 4
0x180006269  jz      short loc_1800062C8
0x18000626b  lea     edx, [rdi+39h]
0x18000626e  jmp     short loc_18000621F
0x180006270  lea     rax, [rsp+78h+arg_18]
0x180006278  mov     [rsp+78h+ProtectionType], r15; ProtectionType
0x18000627d  mov     r9, rdi; pszProtectedCredentials
0x180006280  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x180006285  mov     r8d, esi; cchCredentials
0x180006288  mov     rdx, rbp; pszCredentials
0x18000628b  xor     ecx, ecx; fAsSelf
0x18000628d  call    cs:__imp_CredProtectW
0x180006293  test    eax, eax
0x180006295  jnz     short loc_1800062C2
0x180006297  call    cs:__imp_GetLastError
0x18000629d  mov     ebx, eax
0x18000629f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062a6  lea     rax, WPP_GLOBAL_Control
0x1800062ad  cmp     rcx, rax
0x1800062b0  jz      short loc_1800062C8
0x1800062b2  test    byte ptr [rcx+1Ch], 4
0x1800062b6  jz      short loc_1800062C8
0x1800062b8  mov     edx, 3Ah ; ':'
0x1800062bd  jmp     loc_18000621F
0x1800062c2  mov     [r14], rdi
0x1800062c5  mov     ebx, r15d
0x1800062c8  call    cs:__imp_RevertToSelf
0x1800062ce  test    ebx, ebx
0x1800062d0  jle     short loc_1800062DD
0x1800062d2  movzx   ebx, bx
0x1800062d5  or      ebx, 80070000h
0x1800062db  test    ebx, ebx
0x1800062dd  jns     short loc_1800062ED
0x1800062df  test    rdi, rdi
0x1800062e2  jz      short loc_1800062ED
0x1800062e4  mov     rcx, rdi; pv
0x1800062e7  call    cs:__imp_CoTaskMemFree
0x1800062ed  mov     eax, ebx
0x1800062ef  add     rsp, 48h
0x1800062f3  pop     r15
0x1800062f5  pop     r14
0x1800062f7  pop     rdi
0x1800062f8  pop     rsi
0x1800062f9  pop     rbp
0x1800062fa  pop     rbx
0x1800062fb  retn
```
