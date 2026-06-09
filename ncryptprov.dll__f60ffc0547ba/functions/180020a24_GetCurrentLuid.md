# _GetCurrentLuid

- ea: `0x180020a24`
- end: `0x180020b95`
- name: `_GetCurrentLuid`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d3f4`

## callees

- `0x18000b250`
- `0x180020a24`
- `0x180020b9c`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ac3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020a9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020a9a`

## string_xrefs

- `0x180020b1e`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`

## pseudocode

```c
__int64 __fastcall GetCurrentLuid(_QWORD *a1)
{
  int v2; // eax
  int v3; // edx
  int v4; // r8d
  unsigned int v5; // ebx
  signed int LastError; // eax
  int v8; // edx
  int v9; // r8d
  HANDLE TokenHandle; // [rsp+40h] [rbp-58h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp-50h] BYREF
  _OWORD TokenInformation[3]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v13; // [rsp+80h] [rbp-18h]

  TokenHandle = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v13 = 0;
  v2 = OpenCallerToken((__int64)a1, &TokenHandle);
  v5 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v5 = (unsigned __int16)v2 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v3,
        v4,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
        34);
  }
  else if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    *a1 = *((_QWORD *)&TokenInformation[0] + 1);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v9,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
        42);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x180020a24  mov     r11, rsp
0x180020a27  mov     [r11+10h], rbx
0x180020a2b  push    rsi
0x180020a2c  sub     rsp, 90h
0x180020a33  mov     rax, cs:__security_cookie
0x180020a3a  xor     rax, rsp
0x180020a3d  mov     [rsp+98h+var_10], rax
0x180020a45  xorps   xmm0, xmm0
0x180020a48  mov     qword ptr [r11-58h], 0
0x180020a50  xor     eax, eax
0x180020a52  mov     [rsp+98h+var_50], 0
0x180020a5a  movups  [rsp+98h+TokenInformation], xmm0
0x180020a5f  lea     rdx, [r11-58h]
0x180020a63  mov     rsi, rcx
0x180020a66  movups  [rsp+98h+var_38], xmm0
0x180020a6b  movups  [rsp+98h+var_28], xmm0
0x180020a70  mov     [r11-18h], rax
0x180020a74  call    _OpenCallerToken
0x180020a79  mov     ebx, eax
0x180020a7b  test    eax, eax
0x180020a7d  jnz     short loc_180020AF3
0x180020a7f  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x180020a84  lea     rax, [rsp+98h+var_50]
0x180020a89  lea     r9d, [rbx+38h]; TokenInformationLength
0x180020a8d  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180020a92  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180020a97  lea     edx, [rbx+0Ah]; TokenInformationClass
0x180020a9a  call    cs:__imp_GetTokenInformation
0x180020aa1  nop     dword ptr [rax+rax+00h]
0x180020aa6  test    eax, eax
0x180020aa8  jz      loc_180020B3F
0x180020aae  mov     rax, qword ptr [rsp+98h+TokenInformation+8]
0x180020ab3  mov     [rsi], rax
0x180020ab6  cmp     [rsp+98h+TokenHandle], 0
0x180020abc  jz      short loc_180020ACF
0x180020abe  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x180020ac3  call    cs:__imp_CloseHandle
0x180020aca  nop     dword ptr [rax+rax+00h]
0x180020acf  mov     eax, ebx
0x180020ad1  mov     rcx, [rsp+98h+var_10]
0x180020ad9  xor     rcx, rsp; StackCookie
0x180020adc  call    __security_check_cookie
0x180020ae1  mov     rbx, [rsp+98h+arg_8]
0x180020ae9  add     rsp, 90h
0x180020af0  pop     rsi
0x180020af1  retn
0x180020af3  jg      loc_180020B7C
0x180020af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b00  lea     rax, WPP_GLOBAL_Control
0x180020b07  cmp     rcx, rax
0x180020b0a  jz      short loc_180020AB6
0x180020b0c  test    byte ptr [rcx+1Ch], 1
0x180020b10  jz      short loc_180020AB6
0x180020b12  mov     [rsp+98h+var_68], 122h
0x180020b1a  mov     rcx, [rcx+10h]
0x180020b1e  lea     rax, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020b25  mov     [rsp+98h+var_70], rax
0x180020b2a  lea     r9, aStatus; "Status"
0x180020b31  mov     dword ptr [rsp+98h+ReturnLength], ebx
0x180020b35  call    WPP_SF_sDsd
0x180020b3a  jmp     loc_180020AB6
0x180020b3f  call    cs:__imp_GetLastError
0x180020b46  nop     dword ptr [rax+rax+00h]
0x180020b4b  mov     ebx, eax
0x180020b4d  test    eax, eax
0x180020b4f  jg      short loc_180020B8A
0x180020b51  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b58  lea     rax, WPP_GLOBAL_Control
0x180020b5f  cmp     rcx, rax
0x180020b62  jz      loc_180020AB6
0x180020b68  test    byte ptr [rcx+1Ch], 1
0x180020b6c  jz      loc_180020AB6
0x180020b72  mov     [rsp+98h+var_68], 12Ah
0x180020b7a  jmp     short loc_180020B1A
0x180020b7c  movzx   ebx, ax
0x180020b7f  or      ebx, 80070000h
0x180020b85  jmp     loc_180020AF9
0x180020b8a  movzx   ebx, ax
0x180020b8d  or      ebx, 80070000h
0x180020b93  jmp     short loc_180020B51
```
