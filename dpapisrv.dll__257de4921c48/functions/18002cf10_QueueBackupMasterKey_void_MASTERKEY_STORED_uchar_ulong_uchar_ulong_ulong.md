# QueueBackupMasterKey(void *,MASTERKEY_STORED *,uchar *,ulong,uchar *,ulong,ulong)

- ea: `0x18002cf10`
- end: `0x18002d31b`
- name: `?QueueBackupMasterKey@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEK2KK@Z`
- size: `1035`
- prototype: `__int64 __fastcall(HANDLE *, struct MASTERKEY_STORED *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int Size, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a794`

## callees

- `0x1800048a4`
- `0x180007f10`
- `0x18001e1b4`
- `0x18002beb0`
- `0x18002cf10`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002d008`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002d008`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d2cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d300`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d2cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d300`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d0c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d148`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d0c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d0d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d0e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d15c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d16b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d0d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d0e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d15c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d16b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d273`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cf5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cf5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d287`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d29b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d287`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d29b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002d118`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002d19c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002d118`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002d19c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002d1d1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002d1d1`

## string_xrefs

- `0x18002d04e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002d092`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002d1f7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002d02a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall QueueBackupMasterKey(
        HANDLE *a1,
        struct MASTERKEY_STORED *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int Size,
        DWORD dwMilliseconds)
{
  size_t v8; // rbx
  _DWORD *v9; // rsi
  HANDLE EventW; // r15
  HANDLE v12; // r14
  void *v13; // rcx
  DWORD LastError; // edi
  void *v15; // r12
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  HANDLE v18; // rbx
  HANDLE v19; // rax
  HANDLE TargetHandle; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-18h] BYREF
  void *phNewToken; // [rsp+50h] [rbp-10h] BYREF
  struct MASTERKEY_STORED *v23; // [rsp+58h] [rbp-8h]

  TargetHandle = 0;
  hObject = 0;
  v8 = a4;
  v9 = LocalAlloc(0, a4 + Size + 224LL);
  if ( !v9 )
    return 14;
  v23 = 0;
  EventW = 0;
  v12 = 0;
  memset_0(v9, 0, v8 + Size + 224LL);
  *((_QWORD *)v9 + 22) = v9 + 56;
  *v9 = 224;
  v9[46] = a4;
  memcpy_0(v9 + 56, a3, v8);
  v13 = (void *)(v8 + *((_QWORD *)v9 + 22));
  *((_QWORD *)v9 + 24) = v13;
  v9[50] = Size;
  memcpy_0(v13, a5, Size);
  phNewToken = 0;
  if ( DuplicateTokenEx(a1[3], 0, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
  {
    v15 = phNewToken;
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 1009);
    v15 = 0;
    if ( LastError )
    {
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 5914);
      goto LABEL_20;
    }
  }
  if ( !DuplicateMasterKey(a2, (struct MASTERKEY_STORED *)(v9 + 2)) )
  {
    LastError = 14;
    DebugTraceError(14, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 5925);
LABEL_21:
    if ( v15 )
      CloseHandle(v15);
    if ( TargetHandle )
      CloseHandle(TargetHandle);
    if ( hObject )
      CloseHandle(hObject);
    if ( v23 )
      CloseMasterKey(a1, v23, 0);
    LocalFree(v9);
    goto LABEL_30;
  }
  *((_QWORD *)v9 + 21) = v15;
  v23 = (struct MASTERKEY_STORED *)(v9 + 2);
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    CurrentProcess = GetCurrentProcess();
    v17 = GetCurrentProcess();
    if ( DuplicateHandle(v17, EventW, CurrentProcess, &TargetHandle, 0, 0, 2u) )
      *((_QWORD *)v9 + 26) = TargetHandle;
    else
      TargetHandle = 0;
  }
  v12 = CreateEventW(0, 1, 0, 0);
  if ( v12 )
  {
    v18 = GetCurrentProcess();
    v19 = GetCurrentProcess();
    if ( DuplicateHandle(v19, v12, v18, &hObject, 0, 0, 2u) )
      *((_QWORD *)v9 + 27) = hObject;
    else
      hObject = 0;
  }
  if ( !QueueUserWorkItem(QueueBackupMasterKeyThreadFunc, v9, 0x10u) )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 5990);
    goto LABEL_19;
  }
  if ( EventW && WaitForSingleObject(EventW, dwMilliseconds) )
    LastError = 259;
  if ( !v12 )
  {
LABEL_19:
    if ( !LastError )
      goto LABEL_30;
    goto LABEL_20;
  }
  if ( !LastError )
  {
    if ( WaitForSingleObject(v12, 0) )
      LastError = 259;
    goto LABEL_30;
  }
LABEL_20:
  if ( LastError != 259 )
    goto LABEL_21;
LABEL_30:
  if ( EventW )
    CloseHandle(EventW);
  if ( v12 )
    CloseHandle(v12);
  return LastError;
}

```

## disassembly

```asm
0x18002cf10  mov     rax, rsp
0x18002cf13  mov     [rax+20h], rbx
0x18002cf17  mov     [rax+18h], r8
0x18002cf1b  mov     [rax+10h], rdx
0x18002cf1f  mov     [rax+8], rcx
0x18002cf23  push    rbp
0x18002cf24  push    rsi
0x18002cf25  push    rdi
0x18002cf26  push    r12
0x18002cf28  push    r13
0x18002cf2a  push    r14
0x18002cf2c  push    r15
0x18002cf2e  mov     rbp, rsp
0x18002cf31  sub     rsp, 60h
0x18002cf35  mov     r12d, dword ptr [rbp+Size]
0x18002cf39  xor     ecx, ecx; uFlags
0x18002cf3b  mov     edi, r9d
0x18002cf3e  mov     [rbp+TargetHandle], 0
0x18002cf46  mov     [rbp+hObject], 0
0x18002cf4e  lea     rdx, [r12+0E0h]
0x18002cf56  mov     ebx, r9d
0x18002cf59  add     rdx, rdi; uBytes
0x18002cf5c  call    cs:__imp_LocalAlloc
0x18002cf63  nop     dword ptr [rax+rax+00h]
0x18002cf68  mov     rsi, rax
0x18002cf6b  test    rax, rax
0x18002cf6e  jnz     short loc_18002CF78
0x18002cf70  lea     eax, [rsi+0Eh]
0x18002cf73  jmp     loc_18002D2A9
0x18002cf78  xor     eax, eax
0x18002cf7a  lea     r8, [r12+0E0h]
0x18002cf82  add     r8, rbx; Size
0x18002cf85  mov     [rbp+var_8], rax
0x18002cf89  xor     edx, edx; Val
0x18002cf8b  mov     rcx, rsi; void *
0x18002cf8e  xor     r15d, r15d
0x18002cf91  xor     r14d, r14d
0x18002cf94  call    memset_0
0x18002cf99  mov     rdx, [rbp+Src]; Src
0x18002cf9d  lea     rcx, [rsi+0E0h]; void *
0x18002cfa4  mov     r8, rbx; Size
0x18002cfa7  mov     [rsi+0B0h], rcx
0x18002cfae  mov     dword ptr [rsi], 0E0h
0x18002cfb4  mov     [rsi+0B8h], edi
0x18002cfba  call    memcpy_0
0x18002cfbf  mov     rcx, [rsi+0B0h]
0x18002cfc6  mov     r8, r12; Size
0x18002cfc9  mov     rdx, [rbp+arg_20]; Src
0x18002cfcd  add     rcx, rbx; void *
0x18002cfd0  mov     [rsi+0C0h], rcx
0x18002cfd7  mov     [rsi+0C8h], r12d
0x18002cfde  call    memcpy_0
0x18002cfe3  mov     r13, [rbp+arg_0]
0x18002cfe7  lea     rax, [rbp+var_10]
0x18002cfeb  mov     [rsp+60h+phNewToken], rax; phNewToken
0x18002cff0  xor     r8d, r8d; lpTokenAttributes
0x18002cff3  lea     eax, [r15+2]
0x18002cff7  mov     [rbp+var_10], r14
0x18002cffb  mov     r9d, eax; ImpersonationLevel
0x18002cffe  mov     [rsp+60h+TokenType], eax; TokenType
0x18002d002  mov     rcx, [r13+18h]; hExistingToken
0x18002d006  xor     edx, edx; dwDesiredAccess
0x18002d008  call    cs:__imp_DuplicateTokenEx
0x18002d00f  nop     dword ptr [rax+rax+00h]
0x18002d014  test    eax, eax
0x18002d016  jnz     short loc_18002D06D
0x18002d018  call    cs:__imp_GetLastError
0x18002d01f  nop     dword ptr [rax+rax+00h]
0x18002d024  mov     r9d, 3F1h
0x18002d02a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d031  mov     ecx, eax
0x18002d033  lea     rdx, aDwlasterror; "dwLastError"
0x18002d03a  mov     edi, eax
0x18002d03c  call    DebugTraceError
0x18002d041  xor     r12d, r12d
0x18002d044  test    edi, edi
0x18002d046  jz      short loc_18002D073
0x18002d048  mov     r9d, 171Ah
0x18002d04e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d055  lea     rdx, aDwlasterror; "dwLastError"
0x18002d05c  mov     ecx, edi
0x18002d05e  call    DebugTraceError
0x18002d063  mov     ebx, 103h
0x18002d068  jmp     loc_18002D217
0x18002d06d  mov     r12, [rbp+var_10]
0x18002d071  xor     edi, edi
0x18002d073  mov     rcx, [rbp+arg_8]; struct MASTERKEY_STORED *
0x18002d077  lea     rbx, [rsi+8]
0x18002d07b  mov     rdx, rbx; struct MASTERKEY_STORED *
0x18002d07e  call    ?DuplicateMasterKey@@YAHPEAUMASTERKEY_STORED@@0@Z; DuplicateMasterKey(MASTERKEY_STORED *,MASTERKEY_STORED *)
0x18002d083  test    eax, eax
0x18002d085  jnz     short loc_18002D0AA
0x18002d087  lea     edi, [rax+0Eh]
0x18002d08a  mov     r9d, 1725h
0x18002d090  mov     ecx, edi
0x18002d092  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d099  lea     rdx, aDwlasterror; "dwLastError"
0x18002d0a0  call    DebugTraceError
0x18002d0a5  jmp     loc_18002D21B
0x18002d0aa  xor     r9d, r9d; lpName
0x18002d0ad  mov     [rsi+0A8h], r12
0x18002d0b4  xor     r8d, r8d; bInitialState
0x18002d0b7  mov     [rbp+var_8], rbx
0x18002d0bb  xor     ecx, ecx; lpEventAttributes
0x18002d0bd  lea     r14d, [r9+1]
0x18002d0c1  mov     edx, r14d; bManualReset
0x18002d0c4  call    cs:__imp_CreateEventW
0x18002d0cb  nop     dword ptr [rax+rax+00h]
0x18002d0d0  mov     r15, rax
0x18002d0d3  test    rax, rax
0x18002d0d6  jz      short loc_18002D13D
0x18002d0d8  call    cs:__imp_GetCurrentProcess
0x18002d0df  nop     dword ptr [rax+rax+00h]
0x18002d0e4  mov     rbx, rax
0x18002d0e7  call    cs:__imp_GetCurrentProcess
0x18002d0ee  nop     dword ptr [rax+rax+00h]
0x18002d0f3  mov     [rsp+60h+dwOptions], 2; dwOptions
0x18002d0fb  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18002d0ff  mov     rcx, rax; hSourceProcessHandle
0x18002d102  mov     dword ptr [rsp+60h+phNewToken], 0; bInheritHandle
0x18002d10a  mov     r8, rbx; hTargetProcessHandle
0x18002d10d  mov     [rsp+60h+TokenType], 0; dwDesiredAccess
0x18002d115  mov     rdx, r15; hSourceHandle
0x18002d118  call    cs:__imp_DuplicateHandle
0x18002d11f  nop     dword ptr [rax+rax+00h]
0x18002d124  test    eax, eax
0x18002d126  jz      short loc_18002D135
0x18002d128  mov     rax, [rbp+TargetHandle]
0x18002d12c  mov     [rsi+0D0h], rax
0x18002d133  jmp     short loc_18002D13D
0x18002d135  mov     [rbp+TargetHandle], 0
0x18002d13d  xor     r9d, r9d; lpName
0x18002d140  xor     r8d, r8d; bInitialState
0x18002d143  mov     edx, r14d; bManualReset
0x18002d146  xor     ecx, ecx; lpEventAttributes
0x18002d148  call    cs:__imp_CreateEventW
0x18002d14f  nop     dword ptr [rax+rax+00h]
0x18002d154  mov     r14, rax
0x18002d157  test    rax, rax
0x18002d15a  jz      short loc_18002D1C1
0x18002d15c  call    cs:__imp_GetCurrentProcess
0x18002d163  nop     dword ptr [rax+rax+00h]
0x18002d168  mov     rbx, rax
0x18002d16b  call    cs:__imp_GetCurrentProcess
0x18002d172  nop     dword ptr [rax+rax+00h]
0x18002d177  mov     [rsp+60h+dwOptions], 2; dwOptions
0x18002d17f  lea     r9, [rbp+hObject]; lpTargetHandle
0x18002d183  mov     rcx, rax; hSourceProcessHandle
0x18002d186  mov     dword ptr [rsp+60h+phNewToken], 0; bInheritHandle
0x18002d18e  mov     r8, rbx; hTargetProcessHandle
0x18002d191  mov     [rsp+60h+TokenType], 0; dwDesiredAccess
0x18002d199  mov     rdx, r14; hSourceHandle
0x18002d19c  call    cs:__imp_DuplicateHandle
0x18002d1a3  nop     dword ptr [rax+rax+00h]
0x18002d1a8  test    eax, eax
0x18002d1aa  jz      short loc_18002D1B9
0x18002d1ac  mov     rax, [rbp+hObject]
0x18002d1b0  mov     [rsi+0D8h], rax
0x18002d1b7  jmp     short loc_18002D1C1
0x18002d1b9  mov     [rbp+hObject], 0
0x18002d1c1  mov     r8d, 10h; Flags
0x18002d1c7  lea     rcx, ?QueueBackupMasterKeyThreadFunc@@YAKPEAX@Z; Function
0x18002d1ce  mov     rdx, rsi; Context
0x18002d1d1  call    cs:__imp_QueueUserWorkItem
0x18002d1d8  nop     dword ptr [rax+rax+00h]
0x18002d1dd  test    eax, eax
0x18002d1df  jnz     loc_18002D2C2
0x18002d1e5  call    cs:__imp_GetLastError
0x18002d1ec  nop     dword ptr [rax+rax+00h]
0x18002d1f1  mov     r9d, 1766h
0x18002d1f7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d1fe  mov     ecx, eax
0x18002d200  lea     rdx, aDwlasterror; "dwLastError"
0x18002d207  mov     edi, eax
0x18002d209  call    DebugTraceError
0x18002d20e  mov     ebx, 103h
0x18002d213  test    edi, edi
0x18002d215  jz      short loc_18002D27F
0x18002d217  cmp     edi, ebx
0x18002d219  jz      short loc_18002D27F
0x18002d21b  test    r12, r12
0x18002d21e  jz      short loc_18002D22F
0x18002d220  mov     rcx, r12; hObject
0x18002d223  call    cs:__imp_CloseHandle
0x18002d22a  nop     dword ptr [rax+rax+00h]
0x18002d22f  mov     rcx, [rbp+TargetHandle]; hObject
0x18002d233  test    rcx, rcx
0x18002d236  jz      short loc_18002D244
0x18002d238  call    cs:__imp_CloseHandle
0x18002d23f  nop     dword ptr [rax+rax+00h]
0x18002d244  mov     rcx, [rbp+hObject]; hObject
0x18002d248  test    rcx, rcx
0x18002d24b  jz      short loc_18002D259
0x18002d24d  call    cs:__imp_CloseHandle
0x18002d254  nop     dword ptr [rax+rax+00h]
0x18002d259  mov     rax, [rbp+var_8]
0x18002d25d  test    rax, rax
0x18002d260  jz      short loc_18002D270
0x18002d262  xor     r8d, r8d; int
0x18002d265  mov     rdx, rax; struct MASTERKEY_STORED *
0x18002d268  mov     rcx, r13; void *
0x18002d26b  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002d270  mov     rcx, rsi; hMem
0x18002d273  call    cs:__imp_LocalFree
0x18002d27a  nop     dword ptr [rax+rax+00h]
0x18002d27f  test    r15, r15
0x18002d282  jz      short loc_18002D293
0x18002d284  mov     rcx, r15; hObject
0x18002d287  call    cs:__imp_CloseHandle
0x18002d28e  nop     dword ptr [rax+rax+00h]
0x18002d293  test    r14, r14
0x18002d296  jz      short loc_18002D2A7
0x18002d298  mov     rcx, r14; hObject
0x18002d29b  call    cs:__imp_CloseHandle
0x18002d2a2  nop     dword ptr [rax+rax+00h]
0x18002d2a7  mov     eax, edi
0x18002d2a9  mov     rbx, [rsp+60h+arg_18]
0x18002d2b1  add     rsp, 60h
0x18002d2b5  pop     r15
0x18002d2b7  pop     r14
0x18002d2b9  pop     r13
0x18002d2bb  pop     r12
0x18002d2bd  pop     rdi
0x18002d2be  pop     rsi
0x18002d2bf  pop     rbp
0x18002d2c0  retn
0x18002d2c2  test    r15, r15
0x18002d2c5  jz      short loc_18002D2E5
0x18002d2c7  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x18002d2ca  mov     rcx, r15; hHandle
0x18002d2cd  call    cs:__imp_WaitForSingleObject
0x18002d2d4  nop     dword ptr [rax+rax+00h]
0x18002d2d9  test    eax, eax
0x18002d2db  mov     ebx, 103h
0x18002d2e0  cmovnz  edi, ebx
0x18002d2e3  jmp     short loc_18002D2EA
0x18002d2e5  mov     ebx, 103h
0x18002d2ea  test    r14, r14
0x18002d2ed  jz      loc_18002D213
0x18002d2f3  test    edi, edi
0x18002d2f5  jnz     loc_18002D217
0x18002d2fb  xor     edx, edx; dwMilliseconds
0x18002d2fd  mov     rcx, r14; hHandle
0x18002d300  call    cs:__imp_WaitForSingleObject
0x18002d307  nop     dword ptr [rax+rax+00h]
0x18002d30c  test    eax, eax
0x18002d30e  jz      loc_18002D27F
0x18002d314  mov     edi, ebx
0x18002d316  jmp     loc_18002D27F
```
