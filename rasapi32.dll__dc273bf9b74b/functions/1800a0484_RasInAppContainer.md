# RasInAppContainer

- ea: `0x1800a0484`
- end: `0x1800a05e1`
- name: `RasInAppContainer`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007a750`
- `0x18007c380`
- `0x1800a7f48`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007efdc`
- `0x1800a0484`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a04df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a04df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a04f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a04f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a0555`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a0555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a055f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a055f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a059f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a059f`

## pseudocode

```c
__int64 RasInAppContainer()
{
  unsigned int v0; // ebx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v3; // r9
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int TokenInformation; // [rsp+50h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
  }
  TokenInformation = 0;
  v0 = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 17;
LABEL_11:
        WPP_SF_d(v4[2], v5, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, LastError);
        goto LABEL_19;
      }
      goto LABEL_20;
    }
LABEL_19:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    v0 = TokenInformation;
    goto LABEL_19;
  }
  LastError = GetLastError();
  if ( !LastError )
    goto LABEL_19;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 18;
    goto LABEL_11;
  }
LABEL_20:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    LOBYTE(v3) = v0 != 0;
    WPP_SF_c(v4[2], 19, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v3);
  }
  return v0;
}

```

## disassembly

```asm
0x1800a0484  push    rbx
0x1800a0486  push    rbp
0x1800a0487  push    rsi
0x1800a0488  sub     rsp, 30h
0x1800a048c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0493  lea     rbp, WPP_GLOBAL_Control
0x1800a049a  mov     esi, 800h
0x1800a049f  cmp     rcx, rbp
0x1800a04a2  jz      short loc_1800A04C4
0x1800a04a4  test    [rcx+1Ch], esi
0x1800a04a7  jz      short loc_1800A04C4
0x1800a04a9  cmp     byte ptr [rcx+19h], 6
0x1800a04ad  jb      short loc_1800A04C4
0x1800a04af  mov     rcx, [rcx+10h]
0x1800a04b3  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a04ba  mov     edx, 10h
0x1800a04bf  call    WPP_SF_
0x1800a04c4  mov     [rsp+48h+TokenInformation], 0
0x1800a04cc  xor     ebx, ebx
0x1800a04ce  mov     [rsp+48h+arg_8], 0
0x1800a04d6  mov     [rsp+48h+TokenHandle], 0
0x1800a04df  call    cs:__imp_GetCurrentProcess
0x1800a04e5  mov     rcx, rax; ProcessHandle
0x1800a04e8  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800a04ed  lea     edx, [rbx+8]; DesiredAccess
0x1800a04f0  call    cs:__imp_OpenProcessToken
0x1800a04f6  test    eax, eax
0x1800a04f8  jnz     short loc_1800A0537
0x1800a04fa  call    cs:__imp_GetLastError
0x1800a0500  test    eax, eax
0x1800a0502  jz      loc_1800A058B
0x1800a0508  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a050f  cmp     rcx, rbp
0x1800a0512  jz      short loc_1800A0592
0x1800a0514  test    [rcx+1Ch], esi
0x1800a0517  jz      short loc_1800A0592
0x1800a0519  cmp     byte ptr [rcx+19h], 2
0x1800a051d  jb      short loc_1800A0592
0x1800a051f  lea     edx, [rbx+11h]
0x1800a0522  mov     rcx, [rcx+10h]
0x1800a0526  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a052d  mov     r9d, eax
0x1800a0530  call    WPP_SF_d
0x1800a0535  jmp     short loc_1800A058B
0x1800a0537  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800a053c  lea     rax, [rsp+48h+arg_8]
0x1800a0541  mov     r9d, 4; TokenInformationLength
0x1800a0547  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800a054c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800a0551  lea     edx, [r9+19h]; TokenInformationClass
0x1800a0555  call    cs:__imp_GetTokenInformation
0x1800a055b  test    eax, eax
0x1800a055d  jnz     short loc_1800A0587
0x1800a055f  call    cs:__imp_GetLastError
0x1800a0565  test    eax, eax
0x1800a0567  jz      short loc_1800A058B
0x1800a0569  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0570  cmp     rcx, rbp
0x1800a0573  jz      short loc_1800A0592
0x1800a0575  test    [rcx+1Ch], esi
0x1800a0578  jz      short loc_1800A0592
0x1800a057a  cmp     byte ptr [rcx+19h], 2
0x1800a057e  jb      short loc_1800A0592
0x1800a0580  mov     edx, 12h
0x1800a0585  jmp     short loc_1800A0522
0x1800a0587  mov     ebx, [rsp+48h+TokenInformation]
0x1800a058b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0592  mov     rax, [rsp+48h+TokenHandle]
0x1800a0597  test    rax, rax
0x1800a059a  jz      short loc_1800A05AC
0x1800a059c  mov     rcx, rax; hObject
0x1800a059f  call    cs:__imp_CloseHandle
0x1800a05a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a05ac  cmp     rcx, rbp
0x1800a05af  jz      short loc_1800A05D7
0x1800a05b1  test    [rcx+1Ch], esi
0x1800a05b4  jz      short loc_1800A05D7
0x1800a05b6  cmp     byte ptr [rcx+19h], 6
0x1800a05ba  jb      short loc_1800A05D7
0x1800a05bc  mov     rcx, [rcx+10h]
0x1800a05c0  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a05c7  test    ebx, ebx
0x1800a05c9  mov     edx, 13h
0x1800a05ce  setnz   r9b
0x1800a05d2  call    WPP_SF_c
0x1800a05d7  mov     eax, ebx
0x1800a05d9  add     rsp, 30h
0x1800a05dd  pop     rsi
0x1800a05de  pop     rbp
0x1800a05df  pop     rbx
0x1800a05e0  retn
```
