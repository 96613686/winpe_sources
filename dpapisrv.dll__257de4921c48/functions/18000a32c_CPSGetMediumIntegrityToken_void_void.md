# CPSGetMediumIntegrityToken(void *,void * *)

- ea: `0x18000a32c`
- end: `0x18000a5c0`
- name: `?CPSGetMediumIntegrityToken@@YAKPEAXPEAPEAX@Z`
- size: `660`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800097f0`

## callees

- `0x180007f10`
- `0x18000a32c`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a3ba`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a3ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a3ee`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a3ee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a48b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a48b`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000a40b`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000a40b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a4b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a4b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a548`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a55e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a55e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a470`

## string_xrefs

- `0x18000a4f3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a599`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSGetMediumIntegrityToken(HANDLE hExistingToken, void **a2)
{
  _DWORD *v4; // rdi
  char *p_pSid; // rsi
  DWORD v6; // ebx
  DWORD LengthSid; // eax
  int v9; // edx
  DWORD LastError; // eax
  char *v11; // rax
  __int64 v12; // r9
  __int64 v13; // rcx
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE TokenInformation[16]; // [rsp+50h] [rbp-B0h] BYREF
  char pSid; // [rsp+60h] [rbp-A0h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x2A0u);
  cbSid = 68;
  v4 = TokenInformation;
  if ( hExistingToken && a2 )
  {
    if ( DuplicateTokenEx(hExistingToken, 0x8Eu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
    {
      p_pSid = &pSid;
      v6 = 122;
      while ( v6 == 122 )
      {
        if ( CreateWellKnownSid(WinMediumLabelSid, 0, p_pSid, &cbSid) )
        {
          v6 = 0;
        }
        else
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError != 122 )
          {
            v12 = 236;
            goto LABEL_28;
          }
          if ( v4 && v4 != (_DWORD *)TokenInformation )
            LocalFree(v4);
          v11 = (char *)LocalAlloc(0, cbSid + 16LL);
          v4 = v11;
          if ( !v11 )
          {
            v6 = 14;
            v12 = 228;
            v13 = 14;
            goto LABEL_29;
          }
          p_pSid = v11 + 16;
        }
      }
      v4[2] = 96;
      *(_QWORD *)v4 = p_pSid;
      LengthSid = GetLengthSid(p_pSid);
      if ( SetTokenInformation(TokenHandle, TokenIntegrityLevel, v4, LengthSid + 16) )
      {
        v6 = 0;
        *a2 = TokenHandle;
        TokenHandle = 0;
        goto LABEL_8;
      }
      LastError = GetLastError();
      v6 = LastError;
      v12 = 257;
LABEL_28:
      v13 = LastError;
LABEL_29:
      DebugTraceError(v13, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v12);
    }
    else
    {
      v6 = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v9,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwError",
          v6,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          199);
    }
  }
  else
  {
    v6 = 87;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
LABEL_8:
  if ( v4 && v4 != (_DWORD *)TokenInformation )
    LocalFree(v4);
  return v6;
}

```

## disassembly

```asm
0x18000a32c  mov     [rsp-8+arg_10], rbx
0x18000a331  mov     [rsp-8+arg_18], rsi
0x18000a336  push    rbp
0x18000a337  push    rdi
0x18000a338  push    r14
0x18000a33a  lea     rbp, [rsp-200h]
0x18000a342  sub     rsp, 300h
0x18000a349  mov     rax, cs:__security_cookie
0x18000a350  xor     rax, rsp
0x18000a353  mov     [rbp+210h+var_20], rax
0x18000a35a  mov     r14, rdx
0x18000a35d  mov     [rsp+310h+TokenHandle], 0
0x18000a366  mov     rbx, rcx
0x18000a369  xor     edx, edx; Val
0x18000a36b  lea     rcx, [rsp+310h+TokenInformation]; void *
0x18000a370  mov     r8d, 2A0h; Size
0x18000a376  call    memset_0
0x18000a37b  mov     [rsp+310h+cbSid], 44h ; 'D'
0x18000a383  lea     rdi, [rsp+310h+TokenInformation]
0x18000a388  test    rbx, rbx
0x18000a38b  jz      loc_18000A461
0x18000a391  test    r14, r14
0x18000a394  jz      loc_18000A461
0x18000a39a  lea     rax, [rsp+310h+TokenHandle]
0x18000a39f  mov     r9d, 2; ImpersonationLevel
0x18000a3a5  mov     [rsp+310h+phNewToken], rax; phNewToken
0x18000a3aa  xor     r8d, r8d; lpTokenAttributes
0x18000a3ad  mov     edx, 8Eh; dwDesiredAccess
0x18000a3b2  mov     [rsp+310h+TokenType], r9d; TokenType
0x18000a3b7  mov     rcx, rbx; hExistingToken
0x18000a3ba  call    cs:__imp_DuplicateTokenEx
0x18000a3c1  nop     dword ptr [rax+rax+00h]
0x18000a3c6  test    eax, eax
0x18000a3c8  jz      loc_18000A4C4
0x18000a3ce  lea     rsi, [rsp+310h+pSid]
0x18000a3d3  mov     ebx, 7Ah ; 'z'
0x18000a3d8  cmp     ebx, 7Ah ; 'z'
0x18000a3db  jz      loc_18000A47E
0x18000a3e1  mov     rcx, rsi; pSid
0x18000a3e4  mov     dword ptr [rdi+8], 60h ; '`'
0x18000a3eb  mov     [rdi], rsi
0x18000a3ee  call    cs:__imp_GetLengthSid
0x18000a3f5  nop     dword ptr [rax+rax+00h]
0x18000a3fa  mov     rcx, [rsp+310h+TokenHandle]; TokenHandle
0x18000a3ff  mov     r8, rdi; TokenInformation
0x18000a402  mov     edx, 19h; TokenInformationClass
0x18000a407  lea     r9d, [rax+10h]; TokenInformationLength
0x18000a40b  call    cs:__imp_SetTokenInformation
0x18000a412  nop     dword ptr [rax+rax+00h]
0x18000a417  test    eax, eax
0x18000a419  jz      loc_18000A5AA
0x18000a41f  mov     rax, [rsp+310h+TokenHandle]
0x18000a424  xor     ebx, ebx
0x18000a426  mov     [r14], rax
0x18000a429  mov     [rsp+310h+TokenHandle], 0
0x18000a432  test    rdi, rdi
0x18000a435  jnz     short loc_18000A4A6
0x18000a437  mov     eax, ebx
0x18000a439  mov     rcx, [rbp+210h+var_20]
0x18000a440  xor     rcx, rsp; StackCookie
0x18000a443  call    __security_check_cookie
0x18000a448  lea     r11, [rsp+310h+var_10]
0x18000a450  mov     rbx, [r11+30h]
0x18000a454  mov     rsi, [r11+38h]
0x18000a458  mov     rsp, r11
0x18000a45b  pop     r14
0x18000a45d  pop     rdi
0x18000a45e  pop     rbp
0x18000a45f  retn
0x18000a461  mov     ebx, 57h ; 'W'
0x18000a466  mov     rcx, [rsp+310h+TokenHandle]; hObject
0x18000a46b  test    rcx, rcx
0x18000a46e  jz      short loc_18000A432
0x18000a470  call    cs:__imp_CloseHandle
0x18000a477  nop     dword ptr [rax+rax+00h]
0x18000a47c  jmp     short loc_18000A432
0x18000a47e  xor     edx, edx; DomainSid
0x18000a480  lea     r9, [rsp+310h+cbSid]; cbSid
0x18000a485  mov     r8, rsi; pSid
0x18000a488  lea     ecx, [rdx+43h]; WellKnownSidType
0x18000a48b  call    cs:__imp_CreateWellKnownSid
0x18000a492  nop     dword ptr [rax+rax+00h]
0x18000a497  test    eax, eax
0x18000a499  jz      loc_18000A523
0x18000a49f  xor     ebx, ebx
0x18000a4a1  jmp     loc_18000A3D8
0x18000a4a6  lea     rax, [rsp+310h+TokenInformation]
0x18000a4ab  cmp     rdi, rax
0x18000a4ae  jz      short loc_18000A437
0x18000a4b0  mov     rcx, rdi; hMem
0x18000a4b3  call    cs:__imp_LocalFree
0x18000a4ba  nop     dword ptr [rax+rax+00h]
0x18000a4bf  jmp     loc_18000A437
0x18000a4c4  call    cs:__imp_GetLastError
0x18000a4cb  nop     dword ptr [rax+rax+00h]
0x18000a4d0  mov     ebx, eax
0x18000a4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4d9  lea     rax, WPP_GLOBAL_Control
0x18000a4e0  cmp     rcx, rax
0x18000a4e3  jz      short loc_18000A466
0x18000a4e5  test    byte ptr [rcx+1Ch], 1
0x18000a4e9  jz      loc_18000A466
0x18000a4ef  mov     rcx, [rcx+10h]
0x18000a4f3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000a4fa  mov     [rsp+310h+var_2E0], 0C7h
0x18000a502  lea     r9, aDwerror; "dwError"
0x18000a509  mov     [rsp+310h+phNewToken], r8
0x18000a50e  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000a515  mov     [rsp+310h+TokenType], ebx
0x18000a519  call    WPP_SF_sDsd
0x18000a51e  jmp     loc_18000A466
0x18000a523  call    cs:__imp_GetLastError
0x18000a52a  nop     dword ptr [rax+rax+00h]
0x18000a52f  mov     ebx, eax
0x18000a531  cmp     eax, 7Ah ; 'z'
0x18000a534  jnz     short loc_18000A58A
0x18000a536  test    rdi, rdi
0x18000a539  jz      short loc_18000A554
0x18000a53b  lea     rax, [rsp+310h+TokenInformation]
0x18000a540  cmp     rdi, rax
0x18000a543  jz      short loc_18000A554
0x18000a545  mov     rcx, rdi; hMem
0x18000a548  call    cs:__imp_LocalFree
0x18000a54f  nop     dword ptr [rax+rax+00h]
0x18000a554  mov     edx, [rsp+310h+cbSid]
0x18000a558  xor     ecx, ecx; uFlags
0x18000a55a  add     rdx, 10h; uBytes
0x18000a55e  call    cs:__imp_LocalAlloc
0x18000a565  nop     dword ptr [rax+rax+00h]
0x18000a56a  mov     rdi, rax
0x18000a56d  test    rax, rax
0x18000a570  jz      short loc_18000A57B
0x18000a572  lea     rsi, [rax+10h]
0x18000a576  jmp     loc_18000A3D8
0x18000a57b  mov     ebx, 0Eh
0x18000a580  mov     r9d, 0E4h
0x18000a586  mov     ecx, ebx
0x18000a588  jmp     short loc_18000A592
0x18000a58a  mov     r9d, 0ECh
0x18000a590  mov     ecx, eax
0x18000a592  lea     rdx, aDwerror; "dwError"
0x18000a599  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000a5a0  call    DebugTraceError
0x18000a5a5  jmp     loc_18000A466
0x18000a5aa  call    cs:__imp_GetLastError
0x18000a5b1  nop     dword ptr [rax+rax+00h]
0x18000a5b6  mov     ebx, eax
0x18000a5b8  mov     r9d, 101h
0x18000a5be  jmp     short loc_18000A590
```
