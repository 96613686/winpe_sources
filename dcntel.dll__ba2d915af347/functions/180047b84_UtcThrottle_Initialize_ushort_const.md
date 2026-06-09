# UtcThrottle::Initialize(ushort const *)

- ea: `0x180047b84`
- end: `0x180047f20`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `924`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c04c`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180047b84`
- `0x180047f28`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047c0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047c0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047efa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047efa`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180047e16`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180047e16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047d11`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047d11`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180047ebb`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180047ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047ecc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047ecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047eec`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180047de4`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180047e6f`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180047de4`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180047e6f`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180047d5d`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180047da0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180047d5d`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180047da0`

## string_xrefs

- `0x180047cd8`: `Failed to initialize security descriptor [%d]`
- `0x180047dba`: `Failed to create semaphore [%d]`
- `0x180047d2b`: `Failed to create event [%d]`
- `0x180047d79`: `Failed to create named semaphore [%d]`
- `0x180047e40`: `Failed to create named timer [%d]`
- `0x180047e2e`: `Failed to open named timer [%d]`
- `0x180047e89`: `Failed to create timer [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtcThrottle::Initialize(UtcThrottle *this, const unsigned __int16 *a2)
{
  __int64 v2; // r9
  __int64 v3; // rcx
  const wchar_t *v4; // r10
  __int64 v5; // rdx
  __int64 v6; // r8
  WCHAR *v7; // rax
  wchar_t v8; // r11
  WCHAR *v9; // rcx
  unsigned int v10; // ebx
  const wchar_t *v11; // rcx
  WCHAR *v12; // rax
  wchar_t v13; // r8
  UtcThrottle *v14; // rcx
  DWORD LastError; // eax
  const char *v16; // r9
  __int64 v17; // r8
  DWORD v18; // eax
  HANDLE v19; // rax
  DWORD v20; // eax
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // rcx
  LPVOID lpArgToCompletionRoutine; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  LARGE_INTEGER DueTime; // [rsp+38h] [rbp-C8h] BYREF
  _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _SECURITY_DESCRIPTOR v29; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR TimerName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  memset(&v29, 0, sizeof(v29));
  *(_QWORD *)&SemaphoreAttributes.nLength = 24;
  *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
  hMem = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(TimerName, 0, 0x208u);
  SemaphoreAttributes.lpSecurityDescriptor = &v29;
  EnterCriticalSection(&stru_1801FFC78);
  DueTime.QuadPart = (LONGLONG)&stru_1801FFC78;
  if ( byte_1801FFCA0 )
    goto LABEL_40;
  v2 = 2147483646;
  v3 = 2147483646;
  v4 = L"Global\\AmiUtcThrottlingSemaphore";
  v5 = 260;
  v6 = 260;
  v7 = Name;
  do
  {
    if ( !v3 )
      break;
    v8 = *v4;
    if ( !*v4 )
      break;
    ++v4;
    *v7++ = v8;
    --v3;
    --v6;
  }
  while ( v6 );
  v9 = v7 - 1;
  if ( v6 )
    v9 = v7;
  *v9 = 0;
  if ( !v6 )
    goto LABEL_9;
  v11 = L"Global\\AmiUtcThrottlingTimer2";
  v12 = TimerName;
  do
  {
    if ( !v2 )
      break;
    v13 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v12++ = v13;
    --v2;
    --v5;
  }
  while ( v5 );
  v14 = (UtcThrottle *)(v12 - 1);
  if ( v5 )
    v14 = (UtcThrottle *)v12;
  *(_WORD *)v14 = 0;
  if ( !v5 )
  {
LABEL_9:
    v10 = 14;
    goto LABEL_41;
  }
  LastError = UtcThrottle::InitializeSecurityDesc(v14, &v29, (struct _ACL **)&hMem);
  v10 = LastError;
  if ( LastError )
  {
    v16 = "Failed to initialize security descriptor [%d]";
    v17 = 123;
LABEL_19:
    LODWORD(lpArgToCompletionRoutine) = LastError;
    AslLogCallPrintf(1, "UtcThrottle::Initialize", v17, v16, lpArgToCompletionRoutine);
    goto LABEL_41;
  }
  if ( !qword_1801FFC70 )
  {
    qword_1801FFC70 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_1801FFC70 )
    {
      LastError = GetLastError();
      v10 = LastError;
      v16 = "Failed to create event [%d]";
      v17 = 133;
      goto LABEL_19;
    }
  }
  if ( !InventoryCoreUtcThrottle )
  {
    InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, Name);
    if ( !InventoryCoreUtcThrottle )
    {
      v18 = GetLastError();
      AslLogCallPrintf(3, "UtcThrottle::Initialize", 144, "Failed to create named semaphore [%d]", v18);
      InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, 0);
      if ( !InventoryCoreUtcThrottle )
      {
        LastError = GetLastError();
        v10 = LastError;
        v16 = "Failed to create semaphore [%d]";
        v17 = 150;
        goto LABEL_19;
      }
    }
  }
  if ( hObject )
    goto LABEL_39;
  v19 = CreateWaitableTimerW(&SemaphoreAttributes, 0, TimerName);
  hObject = v19;
  if ( v19 )
  {
LABEL_37:
    DueTime.QuadPart = -10000000;
    if ( !SetWaitableTimer(v19, &DueTime, 0, 0, 0, 0) )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    goto LABEL_39;
  }
  v20 = GetLastError();
  v21 = 183;
  if ( v20 == 183 )
  {
    hObject = OpenWaitableTimerW(0x100000u, 0, TimerName);
    if ( hObject )
      goto LABEL_34;
    v20 = GetLastError();
    v22 = "Failed to open named timer [%d]";
    v21 = 178;
    v23 = 1;
  }
  else
  {
    v22 = "Failed to create named timer [%d]";
    v23 = 3;
  }
  LODWORD(lpArgToCompletionRoutine) = v20;
  AslLogCallPrintf(v23, "UtcThrottle::Initialize", v21, v22, lpArgToCompletionRoutine);
LABEL_34:
  if ( !hObject )
  {
    v19 = CreateWaitableTimerW(&SemaphoreAttributes, 0, 0);
    hObject = v19;
    if ( !v19 )
    {
      LastError = GetLastError();
      v10 = LastError;
      v16 = "Failed to create timer [%d]";
      v17 = 197;
      goto LABEL_19;
    }
    goto LABEL_37;
  }
LABEL_39:
  byte_1801FFCA0 = 1;
LABEL_40:
  v10 = 0;
LABEL_41:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  LeaveCriticalSection(&stru_1801FFC78);
  return v10;
}

```

## disassembly

```asm
0x180047b84  push    rbp
0x180047b86  push    rbx
0x180047b87  push    rsi
0x180047b88  push    r12
0x180047b8a  push    r14
0x180047b8c  lea     rbp, [rsp-3B0h]
0x180047b94  sub     rsp, 4B0h
0x180047b9b  mov     rax, cs:__security_cookie
0x180047ba2  xor     rax, rsp
0x180047ba5  mov     [rbp+3D0h+var_30], rax
0x180047bac  xorps   xmm0, xmm0
0x180047baf  xor     eax, eax
0x180047bb1  movups  xmmword ptr [rsp+4D0h+var_478.Revision], xmm0
0x180047bb6  movups  xmmword ptr [rsp+4D0h+var_478.Group], xmm0
0x180047bbb  mov     [rsp+4D0h+var_478.Dacl], rax
0x180047bc0  xor     esi, esi
0x180047bc2  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.nLength], 18h
0x180047bcb  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.bInheritHandle], rsi
0x180047bd0  mov     [rsp+4D0h+hMem], rsi
0x180047bd5  mov     ebx, 208h
0x180047bda  mov     r8d, ebx; Size
0x180047bdd  xor     edx, edx; Val
0x180047bdf  lea     rcx, [rbp+3D0h+Name]; void *
0x180047be6  call    memset_0
0x180047beb  mov     r8d, ebx; Size
0x180047bee  xor     edx, edx; Val
0x180047bf0  lea     rcx, [rbp+3D0h+TimerName]; void *
0x180047bf4  call    memset_0
0x180047bf9  lea     rax, [rsp+4D0h+var_478]
0x180047bfe  mov     [rsp+4D0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x180047c03  lea     r12, stru_1801FFC78
0x180047c0a  mov     rcx, r12; lpCriticalSection
0x180047c0d  call    cs:__imp_EnterCriticalSection
0x180047c13  mov     qword ptr [rsp+4D0h+DueTime], r12
0x180047c18  cmp     cs:byte_1801FFCA0, sil
0x180047c1f  jnz     loc_180047EE0
0x180047c25  mov     r9d, 7FFFFFFEh
0x180047c2b  mov     ecx, r9d
0x180047c2e  lea     r10, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x180047c35  mov     edx, 104h
0x180047c3a  mov     r8d, edx
0x180047c3d  lea     rax, [rbp+3D0h+Name]
0x180047c44  lea     r14d, [rsi+1]
0x180047c48  test    rcx, rcx
0x180047c4b  jz      short loc_180047C6B
0x180047c4d  movzx   r11d, word ptr [r10]
0x180047c51  test    r11w, r11w
0x180047c55  jz      short loc_180047C6B
0x180047c57  add     r10, 2
0x180047c5b  mov     [rax], r11w
0x180047c5f  add     rax, 2
0x180047c63  sub     rcx, r14
0x180047c66  sub     r8, r14
0x180047c69  jnz     short loc_180047C48
0x180047c6b  lea     rcx, [rax-2]
0x180047c6f  test    r8, r8
0x180047c72  cmovnz  rcx, rax
0x180047c76  mov     [rcx], si
0x180047c79  jnz     short loc_180047C85
0x180047c7b  mov     ebx, 0Eh
0x180047c80  jmp     loc_180047EE2
0x180047c85  lea     rcx, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x180047c8c  lea     rax, [rbp+3D0h+TimerName]
0x180047c90  test    r9, r9
0x180047c93  jz      short loc_180047CB3
0x180047c95  movzx   r8d, word ptr [rcx]
0x180047c99  test    r8w, r8w
0x180047c9d  jz      short loc_180047CB3
0x180047c9f  add     rcx, 2
0x180047ca3  mov     [rax], r8w
0x180047ca7  add     rax, 2
0x180047cab  sub     r9, r14
0x180047cae  sub     rdx, r14
0x180047cb1  jnz     short loc_180047C90
0x180047cb3  lea     rcx, [rax-2]
0x180047cb7  test    rdx, rdx
0x180047cba  cmovnz  rcx, rax; this
0x180047cbe  mov     [rcx], si
0x180047cc1  jz      short loc_180047C7B
0x180047cc3  lea     r8, [rsp+4D0h+hMem]; struct _ACL **
0x180047cc8  lea     rdx, [rsp+4D0h+var_478]; struct _SECURITY_DESCRIPTOR *
0x180047ccd  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x180047cd2  mov     ebx, eax
0x180047cd4  test    eax, eax
0x180047cd6  jz      short loc_180047CFD
0x180047cd8  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x180047cdf  mov     r8d, 7Bh ; '{'
0x180047ce5  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180047ce9  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180047cf0  mov     ecx, r14d
0x180047cf3  call    AslLogCallPrintf
0x180047cf8  jmp     loc_180047EE2
0x180047cfd  cmp     cs:qword_1801FFC70, rsi
0x180047d04  jnz     short loc_180047D3A
0x180047d06  xor     r9d, r9d; lpName
0x180047d09  xor     r8d, r8d; bInitialState
0x180047d0c  mov     edx, r14d; bManualReset
0x180047d0f  xor     ecx, ecx; lpEventAttributes
0x180047d11  call    cs:__imp_CreateEventW
0x180047d17  mov     cs:qword_1801FFC70, rax
0x180047d1e  test    rax, rax
0x180047d21  jnz     short loc_180047D3A
0x180047d23  call    cs:__imp_GetLastError
0x180047d29  mov     ebx, eax
0x180047d2b  lea     r9, aFailedToCreate_1; "Failed to create event [%d]"
0x180047d32  mov     r8d, 85h
0x180047d38  jmp     short loc_180047CE5
0x180047d3a  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rsi; UtcThrottle InventoryCoreUtcThrottle
0x180047d41  jnz     loc_180047DCC
0x180047d47  lea     r9, [rbp+3D0h+Name]; lpName
0x180047d4e  mov     ebx, 14h
0x180047d53  mov     r8d, ebx; lMaximumCount
0x180047d56  mov     edx, ebx; lInitialCount
0x180047d58  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180047d5d  call    cs:__imp_CreateSemaphoreW
0x180047d63  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x180047d6a  test    rax, rax
0x180047d6d  jnz     short loc_180047DCC
0x180047d6f  call    cs:__imp_GetLastError
0x180047d75  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180047d79  lea     r9, aFailedToCreate_3; "Failed to create named semaphore [%d]"
0x180047d80  lea     r8d, [rbx+7Ch]
0x180047d84  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180047d8b  lea     ecx, [rbx-11h]
0x180047d8e  call    AslLogCallPrintf
0x180047d93  xor     r9d, r9d; lpName
0x180047d96  mov     r8d, ebx; lMaximumCount
0x180047d99  mov     edx, ebx; lInitialCount
0x180047d9b  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180047da0  call    cs:__imp_CreateSemaphoreW
0x180047da6  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x180047dad  test    rax, rax
0x180047db0  jnz     short loc_180047DCC
0x180047db2  call    cs:__imp_GetLastError
0x180047db8  mov     ebx, eax
0x180047dba  lea     r9, aFailedToCreate_2; "Failed to create semaphore [%d]"
0x180047dc1  mov     r8d, 96h
0x180047dc7  jmp     loc_180047CE5
0x180047dcc  cmp     cs:hObject, rsi
0x180047dd3  jnz     loc_180047ED9
0x180047dd9  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x180047ddd  xor     edx, edx; bManualReset
0x180047ddf  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x180047de4  call    cs:__imp_CreateWaitableTimerW
0x180047dea  mov     cs:hObject, rax
0x180047df1  test    rax, rax
0x180047df4  jnz     loc_180047E9B
0x180047dfa  call    cs:__imp_GetLastError
0x180047e00  mov     r8d, 0B7h
0x180047e06  cmp     eax, r8d
0x180047e09  jnz     short loc_180047E40
0x180047e0b  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x180047e0f  xor     edx, edx; bInheritHandle
0x180047e11  mov     ecx, 100000h; dwDesiredAccess
0x180047e16  call    cs:__imp_OpenWaitableTimerW
0x180047e1c  mov     cs:hObject, rax
0x180047e23  test    rax, rax
0x180047e26  jnz     short loc_180047E5C
0x180047e28  call    cs:__imp_GetLastError
0x180047e2e  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x180047e35  mov     r8d, 0B2h
0x180047e3b  mov     ecx, r14d
0x180047e3e  jmp     short loc_180047E4C
0x180047e40  lea     r9, aFailedToCreate_4; "Failed to create named timer [%d]"
0x180047e47  mov     ecx, 3
0x180047e4c  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180047e50  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180047e57  call    AslLogCallPrintf
0x180047e5c  cmp     cs:hObject, rsi
0x180047e63  jnz     short loc_180047ED9
0x180047e65  xor     r8d, r8d; lpTimerName
0x180047e68  xor     edx, edx; bManualReset
0x180047e6a  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x180047e6f  call    cs:__imp_CreateWaitableTimerW
0x180047e75  mov     cs:hObject, rax
0x180047e7c  test    rax, rax
0x180047e7f  jnz     short loc_180047E9B
0x180047e81  call    cs:__imp_GetLastError
0x180047e87  mov     ebx, eax
0x180047e89  lea     r9, aFailedToCreate_0; "Failed to create timer [%d]"
0x180047e90  mov     r8d, 0C5h
0x180047e96  jmp     loc_180047CE5
0x180047e9b  mov     qword ptr [rsp+4D0h+DueTime], 0FFFFFFFFFF676980h
0x180047ea4  mov     [rsp+4D0h+fResume], esi; fResume
0x180047ea8  mov     [rsp+4D0h+lpArgToCompletionRoutine], rsi; lpArgToCompletionRoutine
0x180047ead  xor     r9d, r9d; pfnCompletionRoutine
0x180047eb0  xor     r8d, r8d; lPeriod
0x180047eb3  lea     rdx, [rsp+4D0h+DueTime]; lpDueTime
0x180047eb8  mov     rcx, rax; hTimer
0x180047ebb  call    cs:__imp_SetWaitableTimer
0x180047ec1  test    eax, eax
0x180047ec3  jnz     short loc_180047ED9
0x180047ec5  mov     rcx, cs:hObject; hObject
0x180047ecc  call    cs:__imp_CloseHandle
0x180047ed2  mov     cs:hObject, rsi
0x180047ed9  mov     cs:byte_1801FFCA0, r14b
0x180047ee0  mov     ebx, esi
0x180047ee2  mov     rcx, [rsp+4D0h+hMem]; hMem
0x180047ee7  test    rcx, rcx
0x180047eea  jz      short loc_180047EF7
0x180047eec  call    cs:__imp_LocalFree
0x180047ef2  mov     [rsp+4D0h+hMem], rsi
0x180047ef7  mov     rcx, r12; lpCriticalSection
0x180047efa  call    cs:__imp_LeaveCriticalSection
0x180047f00  mov     eax, ebx
0x180047f02  mov     rcx, [rbp+3D0h+var_30]
0x180047f09  xor     rcx, rsp; StackCookie
0x180047f0c  call    __security_check_cookie
0x180047f11  add     rsp, 4B0h
0x180047f18  pop     r14
0x180047f1a  pop     r12
0x180047f1c  pop     rsi
0x180047f1d  pop     rbx
0x180047f1e  pop     rbp
0x180047f1f  retn
```
