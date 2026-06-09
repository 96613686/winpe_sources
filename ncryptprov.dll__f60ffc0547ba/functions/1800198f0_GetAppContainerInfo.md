# GetAppContainerInfo

- ea: `0x1800198f0`
- end: `0x180019d7d`
- name: `GetAppContainerInfo`
- size: `1165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019660`

## callees

- `0x18000b250`
- `0x1800198f0`
- `0x180062310`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800199b6`
- `ntdll!NtQueryInformationToken` at `0x1800199b6`
- `ntdll!RtlFreeSid` at `0x180019ac6`
- `ntdll!RtlFreeSid` at `0x180019ac6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180019a12`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180019a12`
- `ntdll!RtlCheckTokenCapability` at `0x180019a32`
- `ntdll!RtlCheckTokenCapability` at `0x180019a77`
- `ntdll!RtlCheckTokenCapability` at `0x180019a32`
- `ntdll!RtlCheckTokenCapability` at `0x180019a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019b2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019978`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019978`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001995a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001995a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180019b47`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180019b47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019adb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019adb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d56`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019a59`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019a59`

## string_xrefs

- `0x180019bbe`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180019cf4`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180019d2a`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetAppContainerInfo(_DWORD *a1, _DWORD *a2, _DWORD *a3)
{
  HANDLE CurrentThread; // rax
  void *v7; // rbx
  int v8; // edx
  DWORD v9; // edi
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  int v16; // r8d
  int v18; // edx
  int v19; // r8d
  signed int LastError; // r15d
  HANDLE CurrentProcess; // rax
  PVOID *v22; // rcx
  int v23; // edx
  int v24; // r8d
  _BYTE v25[4]; // [rsp+68h] [rbp-19h] BYREF
  int TokenInformation; // [rsp+6Ch] [rbp-15h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-11h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp-9h] BYREF
  PSID Sid; // [rsp+80h] [rbp-1h] BYREF
  PSID hMem; // [rsp+88h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+90h] [rbp+Fh] BYREF

  *a1 = 0;
  *a2 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  Sid = 0;
  hMem = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v25[0] = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
    {
LABEL_2:
      v7 = TokenHandle;
      TokenHandle = 0;
LABEL_3:
      v9 = NtQueryInformationToken(v7, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            v10,
            (unsigned int)"Status",
            v9,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
            86);
      }
      else
      {
        *a1 = TokenInformation != 0;
        v9 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 3u, 9u, 0, 0, 0, 0, 0, 0, &Sid);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v11,
              v12,
              (unsigned int)"Status",
              v9,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
              106);
        }
        else
        {
          v9 = RtlCheckTokenCapability(0, Sid, v25);
          if ( v9 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v13,
                v14,
                (unsigned int)"Status",
                v9,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
                118);
          }
          else
          {
            *a2 = v25[0];
            if ( ConvertStringSidToSidW(
                   L"S-1-15-3-1024-950745478-3562277873-4084666094-894910038-3455483509-2403009927-1209652952-3346094864",
                   &hMem) )
            {
              v9 = RtlCheckTokenCapability(0, hMem, v25);
              if ( v9 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v15,
                    v16,
                    (unsigned int)"Status",
                    v9,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
                    144);
              }
              else
              {
                *a3 = v25[0];
              }
            }
            else
            {
              v9 = GetLastError();
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v23,
                  v24,
                  (unsigned int)"Status",
                  v9,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
                  132);
            }
          }
        }
      }
      goto LABEL_9;
    }
    LastError = GetLastError();
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v19,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        45);
LABEL_47:
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v19,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        37);
      goto LABEL_47;
    }
  }
  v7 = 0;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !LastError )
    goto LABEL_3;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  else
    v9 = LastError;
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      (unsigned int)v22[2],
      v18,
      v19,
      (unsigned int)"dwStatus",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
      72);
LABEL_9:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( hMem )
    LocalFree(hMem);
  if ( v7 )
    CloseHandle(v7);
  return v9;
}

```

## disassembly

```asm
0x1800198f0  mov     r11, rsp
0x1800198f3  push    rbp
0x1800198f4  push    rbx
0x1800198f5  push    rdi
0x1800198f6  lea     rbp, [r11-5Fh]
0x1800198fa  sub     rsp, 0C0h
0x180019901  mov     rax, cs:__security_cookie
0x180019908  xor     rax, rsp
0x18001990b  mov     [rbp+57h+var_40], rax
0x18001990f  mov     [r11+20h], rsi
0x180019913  mov     rsi, rdx
0x180019916  mov     [r11-20h], r12
0x18001991a  mov     r12, r8
0x18001991d  mov     [r11-28h], r13
0x180019921  xor     r13d, r13d
0x180019924  mov     [r11-30h], r14
0x180019928  mov     r14, rcx
0x18001992b  mov     [rcx], r13d
0x18001992e  mov     [rdx], r13d
0x180019931  mov     [r11-38h], r15
0x180019935  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x18001993c  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x180019942  mov     [rbp+57h+Sid], r13
0x180019946  mov     [rbp+57h+hMem], r13
0x18001994a  mov     [rbp+57h+TokenInformation], r13d
0x18001994e  mov     [rbp+57h+var_60], r13d
0x180019952  mov     [rbp+57h+var_70], r13b
0x180019956  mov     [rbp+57h+TokenHandle], r13
0x18001995a  call    cs:__imp_GetCurrentThread
0x180019961  nop     dword ptr [rax+rax+00h]
0x180019966  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001996a  mov     edx, 0Ch; DesiredAccess
0x18001996f  mov     rcx, rax; ThreadHandle
0x180019972  mov     r8d, 1; OpenAsSelf
0x180019978  call    cs:__imp_OpenThreadToken
0x18001997f  nop     dword ptr [rax+rax+00h]
0x180019984  lea     rbx, WPP_GLOBAL_Control
0x18001998b  test    eax, eax
0x18001998d  jz      loc_180019B15
0x180019993  mov     rbx, [rbp+57h+TokenHandle]
0x180019997  mov     [rbp+57h+TokenHandle], r13
0x18001999b  lea     rax, [rbp+57h+var_60]
0x18001999f  mov     r9d, 4; TokenInformationLength
0x1800199a5  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800199a9  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800199ae  mov     edx, 1Dh; TokenInformationClass
0x1800199b3  mov     rcx, rbx; TokenHandle
0x1800199b6  call    cs:__imp_NtQueryInformationToken
0x1800199bd  nop     dword ptr [rax+rax+00h]
0x1800199c2  mov     edi, eax
0x1800199c4  test    eax, eax
0x1800199c6  jnz     loc_180019B91
0x1800199cc  cmp     [rbp+57h+TokenInformation], r13d
0x1800199d0  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800199d4  mov     eax, r13d
0x1800199d7  mov     r9d, 9; SubAuthority1
0x1800199dd  setnz   al
0x1800199e0  mov     r8d, 3; SubAuthority0
0x1800199e6  mov     [r14], eax
0x1800199e9  mov     dl, 2; SubAuthorityCount
0x1800199eb  lea     rax, [rbp+57h+Sid]
0x1800199ef  mov     [rsp+50h], rax; Sid
0x1800199f4  mov     [rsp+0D0h+SubAuthority7], r13d; SubAuthority7
0x1800199f9  mov     [rsp+0D0h+SubAuthority6], r13d; SubAuthority6
0x1800199fe  mov     [rsp+0D0h+SubAuthority5], r13d; SubAuthority5
0x180019a03  mov     [rsp+0D0h+SubAuthority4], r13d; SubAuthority4
0x180019a08  mov     [rsp+0D0h+SubAuthority3], r13d; SubAuthority3
0x180019a0d  mov     dword ptr [rsp+0D0h+ReturnLength], r13d; SubAuthority2
0x180019a12  call    cs:__imp_RtlAllocateAndInitializeSid
0x180019a19  nop     dword ptr [rax+rax+00h]
0x180019a1e  mov     edi, eax
0x180019a20  test    eax, eax
0x180019a22  jnz     loc_180019BDF
0x180019a28  mov     rdx, [rbp+57h+Sid]
0x180019a2c  lea     r8, [rbp+57h+var_70]
0x180019a30  xor     ecx, ecx
0x180019a32  call    cs:__imp_RtlCheckTokenCapability
0x180019a39  nop     dword ptr [rax+rax+00h]
0x180019a3e  mov     edi, eax
0x180019a40  test    eax, eax
0x180019a42  jnz     loc_180019C74
0x180019a48  movzx   eax, [rbp+57h+var_70]
0x180019a4c  lea     rdx, [rbp+57h+hMem]; Sid
0x180019a50  lea     rcx, StringSid; "S-1-15-3-1024-950745478-3562277873-4084"...
0x180019a57  mov     [rsi], eax
0x180019a59  call    cs:__imp_ConvertStringSidToSidW
0x180019a60  nop     dword ptr [rax+rax+00h]
0x180019a65  test    eax, eax
0x180019a67  jz      loc_180019C0A
0x180019a6d  mov     rdx, [rbp+57h+hMem]
0x180019a71  lea     r8, [rbp+57h+var_70]
0x180019a75  xor     ecx, ecx
0x180019a77  call    cs:__imp_RtlCheckTokenCapability
0x180019a7e  nop     dword ptr [rax+rax+00h]
0x180019a83  mov     edi, eax
0x180019a85  test    eax, eax
0x180019a87  jnz     loc_180019C46
0x180019a8d  movzx   eax, [rbp+57h+var_70]
0x180019a91  mov     [r12], eax
0x180019a95  mov     rcx, [rbp+57h+Sid]; Sid
0x180019a99  mov     r15, [rsp+0D0h+var_30]
0x180019aa1  mov     r14, [rsp+0D0h+var_28]
0x180019aa9  mov     r13, [rsp+0D0h+var_20]
0x180019ab1  mov     r12, [rsp+0B8h]
0x180019ab9  mov     rsi, [rsp+0D0h+arg_18]
0x180019ac1  test    rcx, rcx
0x180019ac4  jz      short loc_180019AD2
0x180019ac6  call    cs:__imp_RtlFreeSid
0x180019acd  nop     dword ptr [rax+rax+00h]
0x180019ad2  mov     rcx, [rbp+57h+hMem]; hMem
0x180019ad6  test    rcx, rcx
0x180019ad9  jz      short loc_180019AE7
0x180019adb  call    cs:__imp_LocalFree
0x180019ae2  nop     dword ptr [rax+rax+00h]
0x180019ae7  test    rbx, rbx
0x180019aea  jz      short loc_180019AFB
0x180019aec  mov     rcx, rbx; hObject
0x180019aef  call    cs:__imp_CloseHandle
0x180019af6  nop     dword ptr [rax+rax+00h]
0x180019afb  mov     eax, edi
0x180019afd  mov     rcx, [rbp+57h+var_40]
0x180019b01  xor     rcx, rsp; StackCookie
0x180019b04  call    __security_check_cookie
0x180019b09  add     rsp, 0C0h
0x180019b10  pop     rdi
0x180019b11  pop     rbx
0x180019b12  pop     rbp
0x180019b13  retn
0x180019b15  call    cs:__imp_GetLastError
0x180019b1c  nop     dword ptr [rax+rax+00h]
0x180019b21  mov     r15d, eax
0x180019b24  cmp     eax, 3F0h
0x180019b29  jnz     loc_180019CA2
0x180019b2f  call    cs:__imp_GetCurrentProcess
0x180019b36  nop     dword ptr [rax+rax+00h]
0x180019b3b  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180019b3f  mov     edx, 0Ch; DesiredAccess
0x180019b44  mov     rcx, rax; ProcessHandle
0x180019b47  call    cs:__imp_OpenProcessToken
0x180019b4e  nop     dword ptr [rax+rax+00h]
0x180019b53  test    eax, eax
0x180019b55  jnz     loc_180019993
0x180019b5b  call    cs:__imp_GetLastError
0x180019b62  nop     dword ptr [rax+rax+00h]
0x180019b67  mov     r15d, eax
0x180019b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b71  cmp     rcx, rbx
0x180019b74  jz      loc_180019CB4
0x180019b7a  test    byte ptr [rcx+1Ch], 1
0x180019b7e  jz      loc_180019CB4
0x180019b84  mov     [rsp+0D0h+SubAuthority4], 12Dh
0x180019b8c  jmp     loc_180019D26
0x180019b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b98  lea     rax, WPP_GLOBAL_Control
0x180019b9f  cmp     rcx, rax
0x180019ba2  jz      loc_180019A95
0x180019ba8  test    byte ptr [rcx+1Ch], 1
0x180019bac  jz      loc_180019A95
0x180019bb2  mov     [rsp+0D0h+SubAuthority4], 656h
0x180019bba  mov     rcx, [rcx+10h]
0x180019bbe  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019bc5  mov     qword ptr [rsp+0D0h+SubAuthority3], rax
0x180019bca  lea     r9, aStatus; "Status"
0x180019bd1  mov     dword ptr [rsp+0D0h+ReturnLength], edi
0x180019bd5  call    WPP_SF_sDsd
0x180019bda  jmp     loc_180019A95
0x180019bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180019be6  lea     rax, WPP_GLOBAL_Control
0x180019bed  cmp     rcx, rax
0x180019bf0  jz      loc_180019A95
0x180019bf6  test    byte ptr [rcx+1Ch], 1
0x180019bfa  jz      loc_180019A95
0x180019c00  mov     [rsp+0D0h+SubAuthority4], 66Ah
0x180019c08  jmp     short loc_180019BBA
0x180019c0a  call    cs:__imp_GetLastError
0x180019c11  nop     dword ptr [rax+rax+00h]
0x180019c16  mov     edi, eax
0x180019c18  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c1f  lea     rax, WPP_GLOBAL_Control
0x180019c26  cmp     rcx, rax
0x180019c29  jz      loc_180019A95
0x180019c2f  test    byte ptr [rcx+1Ch], 1
0x180019c33  jz      loc_180019A95
0x180019c39  mov     [rsp+0D0h+SubAuthority4], 684h
0x180019c41  jmp     loc_180019BBA
0x180019c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c4d  lea     rax, WPP_GLOBAL_Control
0x180019c54  cmp     rcx, rax
0x180019c57  jz      loc_180019A95
0x180019c5d  test    byte ptr [rcx+1Ch], 1
0x180019c61  jz      loc_180019A95
0x180019c67  mov     [rsp+0D0h+SubAuthority4], 690h
0x180019c6f  jmp     loc_180019BBA
0x180019c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c7b  lea     rax, WPP_GLOBAL_Control
0x180019c82  cmp     rcx, rax
0x180019c85  jz      loc_180019A95
0x180019c8b  test    byte ptr [rcx+1Ch], 1
0x180019c8f  jz      loc_180019A95
0x180019c95  mov     [rsp+0D0h+SubAuthority4], 676h
0x180019c9d  jmp     loc_180019BBA
0x180019ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ca9  cmp     rcx, rbx
0x180019cac  jz      short loc_180019CB4
0x180019cae  test    byte ptr [rcx+1Ch], 1
0x180019cb2  jnz     short loc_180019D1E
0x180019cb4  mov     rax, [rbp+57h+TokenHandle]
0x180019cb8  mov     rbx, r13
0x180019cbb  test    rax, rax
0x180019cbe  jnz     loc_180019D53
0x180019cc4  test    r15d, r15d
0x180019cc7  jz      loc_18001999B
0x180019ccd  jg      loc_180019D6E
0x180019cd3  mov     edi, r15d
0x180019cd6  lea     rax, WPP_GLOBAL_Control
0x180019cdd  cmp     rcx, rax
0x180019ce0  jz      loc_180019A95
0x180019ce6  test    byte ptr [rcx+1Ch], 1
0x180019cea  jz      loc_180019A95
0x180019cf0  mov     rcx, [rcx+10h]
0x180019cf4  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019cfb  mov     [rsp+0D0h+SubAuthority4], 648h
0x180019d03  lea     r9, aDwstatus; "dwStatus"
0x180019d0a  mov     qword ptr [rsp+0D0h+SubAuthority3], rax
0x180019d0f  mov     dword ptr [rsp+0D0h+ReturnLength], r15d
0x180019d14  call    WPP_SF_sDsd
0x180019d19  jmp     loc_180019A95
0x180019d1e  mov     [rsp+0D0h+SubAuthority4], 125h
0x180019d26  mov     rcx, [rcx+10h]
0x180019d2a  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019d31  mov     qword ptr [rsp+0D0h+SubAuthority3], rax
0x180019d36  lea     r9, aDwreturn; "dwReturn"
0x180019d3d  mov     dword ptr [rsp+0D0h+ReturnLength], r15d
0x180019d42  call    WPP_SF_sDsd
0x180019d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d4e  jmp     loc_180019CB4
0x180019d53  mov     rcx, rax; hObject
0x180019d56  call    cs:__imp_CloseHandle
0x180019d5d  nop     dword ptr [rax+rax+00h]
0x180019d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d69  jmp     loc_180019CC4
0x180019d6e  movzx   edi, r15w
0x180019d72  or      edi, 80070000h
0x180019d78  jmp     loc_180019CD6
```
