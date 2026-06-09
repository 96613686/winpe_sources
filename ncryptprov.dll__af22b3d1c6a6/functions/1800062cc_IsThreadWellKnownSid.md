# IsThreadWellKnownSid

- ea: `0x1800062cc`
- end: `0x18000669d`
- name: `IsThreadWellKnownSid`
- size: `977`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800060e0`
- `0x18000dab0`
- `0x18000ed10`
- `0x180050eb8`

## callees

- `0x1800062cc`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180062310`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18000644e`
- `ntdll!RtlFreeSid` at `0x18000644e`
- `ntdll!RtlNtStatusToDosError` at `0x18000642d`
- `ntdll!RtlNtStatusToDosError` at `0x18000642d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800063f8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800063f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006504`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006504`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006341`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006341`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006320`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000651d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000651d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800063a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006653`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800063a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006653`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000649c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000649c`

## string_xrefs

- `0x1800064c3`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180006567`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180006619`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180006675`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x1800065b6`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall IsThreadWellKnownSid(__int64 a1, _DWORD *a2)
{
  HANDLE CurrentThread; // rax
  int v4; // edx
  int v5; // r8d
  void *v6; // r14
  DWORD LastError; // ebx
  PVOID *v8; // rcx
  void *v9; // rdi
  PSID *v10; // rbx
  int v11; // edx
  int v12; // esi
  int v13; // r8d
  HANDLE CurrentProcess; // rax
  DWORD v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  DWORD TokenInformationLength; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid1; // [rsp+70h] [rbp-90h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  _BYTE TokenInformation[1024]; // [rsp+80h] [rbp-80h] BYREF

  TokenInformationLength = 1024;
  pSid1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *a2 = 0;
  TokenHandle = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  v6 = 0;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_2:
      v6 = TokenHandle;
      LastError = 0;
      TokenHandle = 0;
LABEL_3:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_4;
    }
    LastError = GetLastError();
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v5,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        45);
      goto LABEL_3;
    }
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v5,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        37);
      goto LABEL_3;
    }
  }
LABEL_4:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !LastError )
  {
    if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    {
      v9 = 0;
      v10 = (PSID *)TokenInformation;
      goto LABEL_9;
    }
    v16 = GetLastError();
    LastError = v16;
    if ( v16 == 122 )
    {
      v9 = (void *)SafeAllocaAllocateFromHeap(TokenInformationLength);
      if ( v9 )
      {
        if ( !GetTokenInformation(v6, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
        {
          LastError = GetLastError();
          DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 107);
          goto LABEL_41;
        }
        v10 = (PSID *)v9;
LABEL_9:
        v12 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1);
        if ( v12 >= 0 )
        {
          if ( EqualSid(pSid1, *v10) )
            *a2 = 1;
          LastError = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v11,
              v13,
              (unsigned int)"Status",
              v12,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
              119);
          LastError = RtlNtStatusToDosError(v12);
        }
        if ( !v9 )
          goto LABEL_15;
LABEL_41:
        MSCryptFree(v9);
        goto LABEL_15;
      }
      v18 = 8;
      LastError = 8;
      v17 = 97;
    }
    else
    {
      v17 = 89;
      v18 = v16;
    }
    DebugTraceError(v18, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v17);
    goto LABEL_15;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      (unsigned int)v8[2],
      v4,
      v5,
      (unsigned int)"dwReturn",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
      71);
LABEL_15:
  if ( pSid1 )
    RtlFreeSid(pSid1);
  if ( v6 )
    CloseHandle(v6);
  return LastError;
}

```

## disassembly

```asm
0x1800062cc  push    rbp
0x1800062ce  push    rbx
0x1800062cf  push    rsi
0x1800062d0  push    rdi
0x1800062d1  push    r12
0x1800062d3  push    r13
0x1800062d5  push    r14
0x1800062d7  push    r15
0x1800062d9  lea     rbp, [rsp-398h]
0x1800062e1  sub     rsp, 498h
0x1800062e8  mov     rax, cs:__security_cookie
0x1800062ef  xor     rax, rsp
0x1800062f2  mov     [rbp+3D0h+var_50], rax
0x1800062f9  xor     r12d, r12d
0x1800062fc  mov     [rsp+4D0h+TokenInformationLength], 400h
0x180006304  mov     [rsp+4D0h+pSid1], r12
0x180006309  mov     r15, rdx
0x18000630c  mov     dword ptr [rsp+4D0h+IdentifierAuthority.Value], r12d
0x180006311  mov     [rdx], r12d
0x180006314  mov     [rsp+4D0h+TokenHandle], r12
0x180006319  mov     word ptr [rsp+4D0h+IdentifierAuthority.Value+4], 500h
0x180006320  call    cs:__imp_GetCurrentThread
0x180006327  nop     dword ptr [rax+rax+00h]
0x18000632c  lea     r13d, [r12+1]
0x180006331  mov     rcx, rax; ThreadHandle
0x180006334  mov     r8d, r13d; OpenAsSelf
0x180006337  lea     r9, [rsp+4D0h+TokenHandle]; TokenHandle
0x18000633c  lea     edx, [r12+8]; DesiredAccess
0x180006341  call    cs:__imp_OpenThreadToken
0x180006348  nop     dword ptr [rax+rax+00h]
0x18000634d  lea     rsi, aDwreturn; "dwReturn"
0x180006354  lea     rdi, WPP_GLOBAL_Control
0x18000635b  test    eax, eax
0x18000635d  jz      loc_1800064E8
0x180006363  mov     r14, [rsp+4D0h+TokenHandle]
0x180006368  mov     ebx, r12d
0x18000636b  mov     [rsp+4D0h+TokenHandle], r12
0x180006370  mov     rcx, cs:WPP_GLOBAL_Control
0x180006377  mov     rax, [rsp+4D0h+TokenHandle]
0x18000637c  test    rax, rax
0x18000637f  jnz     loc_1800065D3
0x180006385  test    ebx, ebx
0x180006387  jnz     loc_1800064B4
0x18000638d  mov     r9d, [rsp+4D0h+TokenInformationLength]; TokenInformationLength
0x180006392  lea     rax, [rsp+4D0h+TokenInformationLength]
0x180006397  lea     r8, [rbp+3D0h+TokenInformation]; TokenInformation
0x18000639b  mov     [rsp+4D0h+ReturnLength], rax; ReturnLength
0x1800063a0  mov     edx, r13d; TokenInformationClass
0x1800063a3  mov     rcx, r14; TokenHandle
0x1800063a6  call    cs:__imp_GetTokenInformation
0x1800063ad  nop     dword ptr [rax+rax+00h]
0x1800063b2  test    eax, eax
0x1800063b4  jz      loc_1800065EE
0x1800063ba  mov     rdi, r12
0x1800063bd  lea     rbx, [rbp+3D0h+TokenInformation]
0x1800063c1  lea     rax, [rsp+4D0h+pSid1]
0x1800063c6  xor     r9d, r9d; SubAuthority1
0x1800063c9  mov     [rsp+4D0h+Sid], rax; Sid
0x1800063ce  lea     rcx, [rsp+4D0h+IdentifierAuthority]; IdentifierAuthority
0x1800063d3  mov     [rsp+4D0h+SubAuthority7], r12d; SubAuthority7
0x1800063d8  mov     dl, r13b; SubAuthorityCount
0x1800063db  mov     [rsp+4D0h+SubAuthority6], r12d; SubAuthority6
0x1800063e0  mov     [rsp+4D0h+SubAuthority5], r12d; SubAuthority5
0x1800063e5  lea     r8d, [r9+12h]; SubAuthority0
0x1800063e9  mov     [rsp+4D0h+SubAuthority4], r12d; SubAuthority4
0x1800063ee  mov     [rsp+4D0h+SubAuthority3], r12d; SubAuthority3
0x1800063f3  mov     dword ptr [rsp+4D0h+ReturnLength], r12d; SubAuthority2
0x1800063f8  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800063ff  nop     dword ptr [rax+rax+00h]
0x180006404  mov     esi, eax
0x180006406  test    eax, eax
0x180006408  jns     loc_180006494
0x18000640e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006415  lea     rax, WPP_GLOBAL_Control
0x18000641c  cmp     rcx, rax
0x18000641f  jz      short loc_18000642B
0x180006421  test    [rcx+1Ch], r13b
0x180006425  jnz     loc_180006563
0x18000642b  mov     ecx, esi; Status
0x18000642d  call    cs:__imp_RtlNtStatusToDosError
0x180006434  nop     dword ptr [rax+rax+00h]
0x180006439  mov     ebx, eax
0x18000643b  test    rdi, rdi
0x18000643e  jnz     loc_180006688
0x180006444  mov     rcx, [rsp+4D0h+pSid1]; Sid
0x180006449  test    rcx, rcx
0x18000644c  jz      short loc_18000645A
0x18000644e  call    cs:__imp_RtlFreeSid
0x180006455  nop     dword ptr [rax+rax+00h]
0x18000645a  test    r14, r14
0x18000645d  jz      short loc_18000646E
0x18000645f  mov     rcx, r14; hObject
0x180006462  call    cs:__imp_CloseHandle
0x180006469  nop     dword ptr [rax+rax+00h]
0x18000646e  mov     eax, ebx
0x180006470  mov     rcx, [rbp+3D0h+var_50]
0x180006477  xor     rcx, rsp; StackCookie
0x18000647a  call    __security_check_cookie
0x18000647f  add     rsp, 498h
0x180006486  pop     r15
0x180006488  pop     r14
0x18000648a  pop     r13
0x18000648c  pop     r12
0x18000648e  pop     rdi
0x18000648f  pop     rsi
0x180006490  pop     rbx
0x180006491  pop     rbp
0x180006492  retn
0x180006494  mov     rdx, [rbx]; pSid2
0x180006497  mov     rcx, [rsp+4D0h+pSid1]; pSid1
0x18000649c  call    cs:__imp_EqualSid
0x1800064a3  nop     dword ptr [rax+rax+00h]
0x1800064a8  test    eax, eax
0x1800064aa  jz      short loc_1800064AF
0x1800064ac  mov     [r15], r13d
0x1800064af  mov     ebx, r12d
0x1800064b2  jmp     short loc_18000643B
0x1800064b4  cmp     rcx, rdi
0x1800064b7  jz      short loc_180006444
0x1800064b9  test    [rcx+1Ch], r13b
0x1800064bd  jz      short loc_180006444
0x1800064bf  mov     rcx, [rcx+10h]
0x1800064c3  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800064ca  mov     [rsp+4D0h+SubAuthority4], 47h ; 'G'
0x1800064d2  mov     r9, rsi
0x1800064d5  mov     qword ptr [rsp+4D0h+SubAuthority3], rax
0x1800064da  mov     dword ptr [rsp+4D0h+ReturnLength], ebx
0x1800064de  call    WPP_SF_sDsd
0x1800064e3  jmp     loc_180006444
0x1800064e8  mov     r14, r12
0x1800064eb  call    cs:__imp_GetLastError
0x1800064f2  nop     dword ptr [rax+rax+00h]
0x1800064f7  mov     ebx, eax
0x1800064f9  cmp     eax, 3F0h
0x1800064fe  jnz     loc_180006590
0x180006504  call    cs:__imp_GetCurrentProcess
0x18000650b  nop     dword ptr [rax+rax+00h]
0x180006510  lea     r8, [rsp+4D0h+TokenHandle]; TokenHandle
0x180006515  mov     edx, 8; DesiredAccess
0x18000651a  mov     rcx, rax; ProcessHandle
0x18000651d  call    cs:__imp_OpenProcessToken
0x180006524  nop     dword ptr [rax+rax+00h]
0x180006529  test    eax, eax
0x18000652b  jnz     loc_180006363
0x180006531  call    cs:__imp_GetLastError
0x180006538  nop     dword ptr [rax+rax+00h]
0x18000653d  mov     ebx, eax
0x18000653f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006546  cmp     rcx, rdi
0x180006549  jz      loc_180006377
0x18000654f  test    [rcx+1Ch], r13b
0x180006553  jz      loc_180006377
0x180006559  mov     [rsp+4D0h+SubAuthority4], 12Dh
0x180006561  jmp     short loc_1800065B2
0x180006563  mov     rcx, [rcx+10h]
0x180006567  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000656e  mov     [rsp+4D0h+SubAuthority4], 77h ; 'w'
0x180006576  lea     r9, aStatus; "Status"
0x18000657d  mov     qword ptr [rsp+4D0h+SubAuthority3], rax
0x180006582  mov     dword ptr [rsp+4D0h+ReturnLength], esi
0x180006586  call    WPP_SF_sDsd
0x18000658b  jmp     loc_18000642B
0x180006590  mov     rcx, cs:WPP_GLOBAL_Control
0x180006597  cmp     rcx, rdi
0x18000659a  jz      loc_180006377
0x1800065a0  test    [rcx+1Ch], r13b
0x1800065a4  jz      loc_180006377
0x1800065aa  mov     [rsp+4D0h+SubAuthority4], 125h
0x1800065b2  mov     rcx, [rcx+10h]
0x1800065b6  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800065bd  mov     qword ptr [rsp+4D0h+SubAuthority3], rax
0x1800065c2  mov     r9, rsi
0x1800065c5  mov     dword ptr [rsp+4D0h+ReturnLength], ebx
0x1800065c9  call    WPP_SF_sDsd
0x1800065ce  jmp     loc_180006370
0x1800065d3  mov     rcx, rax; hObject
0x1800065d6  call    cs:__imp_CloseHandle
0x1800065dd  nop     dword ptr [rax+rax+00h]
0x1800065e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065e9  jmp     loc_180006385
0x1800065ee  call    cs:__imp_GetLastError
0x1800065f5  nop     dword ptr [rax+rax+00h]
0x1800065fa  mov     ebx, eax
0x1800065fc  cmp     eax, 7Ah ; 'z'
0x1800065ff  jz      short loc_18000662A
0x180006601  mov     r9d, 59h ; 'Y'
0x180006607  mov     ecx, eax
0x180006609  jmp     short loc_180006616
0x18000660b  mov     ecx, 8
0x180006610  mov     ebx, ecx
0x180006612  lea     r9d, [rcx+59h]
0x180006616  mov     rdx, rsi
0x180006619  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006620  call    DebugTraceError
0x180006625  jmp     loc_180006444
0x18000662a  mov     ecx, [rsp+4D0h+TokenInformationLength]
0x18000662e  call    SafeAllocaAllocateFromHeap
0x180006633  mov     rdi, rax
0x180006636  test    rax, rax
0x180006639  jz      short loc_18000660B
0x18000663b  mov     r9d, [rsp+4D0h+TokenInformationLength]; TokenInformationLength
0x180006640  lea     rax, [rsp+4D0h+TokenInformationLength]
0x180006645  mov     r8, rdi; TokenInformation
0x180006648  mov     [rsp+4D0h+ReturnLength], rax; ReturnLength
0x18000664d  mov     edx, r13d; TokenInformationClass
0x180006650  mov     rcx, r14; TokenHandle
0x180006653  call    cs:__imp_GetTokenInformation
0x18000665a  nop     dword ptr [rax+rax+00h]
0x18000665f  test    eax, eax
0x180006661  jnz     short loc_180006695
0x180006663  call    cs:__imp_GetLastError
0x18000666a  nop     dword ptr [rax+rax+00h]
0x18000666f  mov     r9d, 6Bh ; 'k'
0x180006675  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000667c  mov     ecx, eax
0x18000667e  mov     rdx, rsi
0x180006681  mov     ebx, eax
0x180006683  call    DebugTraceError
0x180006688  mov     rcx, rdi
0x18000668b  call    MSCryptFree
0x180006690  jmp     loc_180006444
0x180006695  mov     rbx, rdi
0x180006698  jmp     loc_1800063C1
```
