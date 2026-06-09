# UtcThrottle::Initialize(ushort const *)

- ea: `0x180027bc8`
- end: `0x180027f64`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `924`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ce04`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x1800152d0`
- `0x180027bc8`
- `0x180028100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027d55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027d55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c51`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180027e5a`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180027e5a`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180027eff`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180027eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ec5`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180027da1`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180027de4`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180027da1`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180027de4`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180027e28`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180027eb3`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180027e28`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180027eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f30`

## string_xrefs

- `0x180027d1c`: `Failed to initialize security descriptor [%d]`
- `0x180027d6f`: `Failed to create event [%d]`
- `0x180027dbd`: `Failed to create named semaphore [%d]`
- `0x180027dfe`: `Failed to create semaphore [%d]`
- `0x180027e84`: `Failed to create named timer [%d]`
- `0x180027e72`: `Failed to open named timer [%d]`
- `0x180027ecd`: `Failed to create timer [%d]`

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
  EnterCriticalSection(&stru_1800FF0B8);
  DueTime.QuadPart = (LONGLONG)&stru_1800FF0B8;
  if ( byte_1800FF0E0 )
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
  if ( !qword_1800FF0B0 )
  {
    qword_1800FF0B0 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_1800FF0B0 )
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
  byte_1800FF0E0 = 1;
LABEL_40:
  v10 = 0;
LABEL_41:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  LeaveCriticalSection(&stru_1800FF0B8);
  return v10;
}

```

## disassembly

```asm
0x180027bc8  push    rbp
0x180027bca  push    rbx
0x180027bcb  push    rsi
0x180027bcc  push    r12
0x180027bce  push    r14
0x180027bd0  lea     rbp, [rsp-3B0h]
0x180027bd8  sub     rsp, 4B0h
0x180027bdf  mov     rax, cs:__security_cookie
0x180027be6  xor     rax, rsp
0x180027be9  mov     [rbp+3D0h+var_30], rax
0x180027bf0  xorps   xmm0, xmm0
0x180027bf3  xor     eax, eax
0x180027bf5  movups  xmmword ptr [rsp+4D0h+var_478.Revision], xmm0
0x180027bfa  movups  xmmword ptr [rsp+4D0h+var_478.Group], xmm0
0x180027bff  mov     [rsp+4D0h+var_478.Dacl], rax
0x180027c04  xor     esi, esi
0x180027c06  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.nLength], 18h
0x180027c0f  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.bInheritHandle], rsi
0x180027c14  mov     [rsp+4D0h+hMem], rsi
0x180027c19  mov     ebx, 208h
0x180027c1e  mov     r8d, ebx; Size
0x180027c21  xor     edx, edx; Val
0x180027c23  lea     rcx, [rbp+3D0h+Name]; void *
0x180027c2a  call    memset_0
0x180027c2f  mov     r8d, ebx; Size
0x180027c32  xor     edx, edx; Val
0x180027c34  lea     rcx, [rbp+3D0h+TimerName]; void *
0x180027c38  call    memset_0
0x180027c3d  lea     rax, [rsp+4D0h+var_478]
0x180027c42  mov     [rsp+4D0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x180027c47  lea     r12, stru_1800FF0B8
0x180027c4e  mov     rcx, r12; lpCriticalSection
0x180027c51  call    cs:__imp_EnterCriticalSection
0x180027c57  mov     qword ptr [rsp+4D0h+DueTime], r12
0x180027c5c  cmp     cs:byte_1800FF0E0, sil
0x180027c63  jnz     loc_180027F24
0x180027c69  mov     r9d, 7FFFFFFEh
0x180027c6f  mov     ecx, r9d
0x180027c72  lea     r10, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x180027c79  mov     edx, 104h
0x180027c7e  mov     r8d, edx
0x180027c81  lea     rax, [rbp+3D0h+Name]
0x180027c88  lea     r14d, [rsi+1]
0x180027c8c  test    rcx, rcx
0x180027c8f  jz      short loc_180027CAF
0x180027c91  movzx   r11d, word ptr [r10]
0x180027c95  test    r11w, r11w
0x180027c99  jz      short loc_180027CAF
0x180027c9b  add     r10, 2
0x180027c9f  mov     [rax], r11w
0x180027ca3  add     rax, 2
0x180027ca7  sub     rcx, r14
0x180027caa  sub     r8, r14
0x180027cad  jnz     short loc_180027C8C
0x180027caf  lea     rcx, [rax-2]
0x180027cb3  test    r8, r8
0x180027cb6  cmovnz  rcx, rax
0x180027cba  mov     [rcx], si
0x180027cbd  jnz     short loc_180027CC9
0x180027cbf  mov     ebx, 0Eh
0x180027cc4  jmp     loc_180027F26
0x180027cc9  lea     rcx, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x180027cd0  lea     rax, [rbp+3D0h+TimerName]
0x180027cd4  test    r9, r9
0x180027cd7  jz      short loc_180027CF7
0x180027cd9  movzx   r8d, word ptr [rcx]
0x180027cdd  test    r8w, r8w
0x180027ce1  jz      short loc_180027CF7
0x180027ce3  add     rcx, 2
0x180027ce7  mov     [rax], r8w
0x180027ceb  add     rax, 2
0x180027cef  sub     r9, r14
0x180027cf2  sub     rdx, r14
0x180027cf5  jnz     short loc_180027CD4
0x180027cf7  lea     rcx, [rax-2]
0x180027cfb  test    rdx, rdx
0x180027cfe  cmovnz  rcx, rax; this
0x180027d02  mov     [rcx], si
0x180027d05  jz      short loc_180027CBF
0x180027d07  lea     r8, [rsp+4D0h+hMem]; struct _ACL **
0x180027d0c  lea     rdx, [rsp+4D0h+var_478]; struct _SECURITY_DESCRIPTOR *
0x180027d11  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x180027d16  mov     ebx, eax
0x180027d18  test    eax, eax
0x180027d1a  jz      short loc_180027D41
0x180027d1c  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x180027d23  mov     r8d, 7Bh ; '{'
0x180027d29  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180027d2d  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180027d34  mov     ecx, r14d
0x180027d37  call    AslLogCallPrintf
0x180027d3c  jmp     loc_180027F26
0x180027d41  cmp     cs:qword_1800FF0B0, rsi
0x180027d48  jnz     short loc_180027D7E
0x180027d4a  xor     r9d, r9d; lpName
0x180027d4d  xor     r8d, r8d; bInitialState
0x180027d50  mov     edx, r14d; bManualReset
0x180027d53  xor     ecx, ecx; lpEventAttributes
0x180027d55  call    cs:__imp_CreateEventW
0x180027d5b  mov     cs:qword_1800FF0B0, rax
0x180027d62  test    rax, rax
0x180027d65  jnz     short loc_180027D7E
0x180027d67  call    cs:__imp_GetLastError
0x180027d6d  mov     ebx, eax
0x180027d6f  lea     r9, aFailedToCreate_2; "Failed to create event [%d]"
0x180027d76  mov     r8d, 85h
0x180027d7c  jmp     short loc_180027D29
0x180027d7e  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rsi; UtcThrottle InventoryCoreUtcThrottle
0x180027d85  jnz     loc_180027E10
0x180027d8b  lea     r9, [rbp+3D0h+Name]; lpName
0x180027d92  mov     ebx, 14h
0x180027d97  mov     r8d, ebx; lMaximumCount
0x180027d9a  mov     edx, ebx; lInitialCount
0x180027d9c  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180027da1  call    cs:__imp_CreateSemaphoreW
0x180027da7  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x180027dae  test    rax, rax
0x180027db1  jnz     short loc_180027E10
0x180027db3  call    cs:__imp_GetLastError
0x180027db9  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180027dbd  lea     r9, aFailedToCreate_4; "Failed to create named semaphore [%d]"
0x180027dc4  lea     r8d, [rbx+7Ch]
0x180027dc8  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180027dcf  lea     ecx, [rbx-11h]
0x180027dd2  call    AslLogCallPrintf
0x180027dd7  xor     r9d, r9d; lpName
0x180027dda  mov     r8d, ebx; lMaximumCount
0x180027ddd  mov     edx, ebx; lInitialCount
0x180027ddf  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180027de4  call    cs:__imp_CreateSemaphoreW
0x180027dea  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x180027df1  test    rax, rax
0x180027df4  jnz     short loc_180027E10
0x180027df6  call    cs:__imp_GetLastError
0x180027dfc  mov     ebx, eax
0x180027dfe  lea     r9, aFailedToCreate_3; "Failed to create semaphore [%d]"
0x180027e05  mov     r8d, 96h
0x180027e0b  jmp     loc_180027D29
0x180027e10  cmp     cs:hObject, rsi
0x180027e17  jnz     loc_180027F1D
0x180027e1d  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x180027e21  xor     edx, edx; bManualReset
0x180027e23  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x180027e28  call    cs:__imp_CreateWaitableTimerW
0x180027e2e  mov     cs:hObject, rax
0x180027e35  test    rax, rax
0x180027e38  jnz     loc_180027EDF
0x180027e3e  call    cs:__imp_GetLastError
0x180027e44  mov     r8d, 0B7h
0x180027e4a  cmp     eax, r8d
0x180027e4d  jnz     short loc_180027E84
0x180027e4f  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x180027e53  xor     edx, edx; bInheritHandle
0x180027e55  mov     ecx, 100000h; dwDesiredAccess
0x180027e5a  call    cs:__imp_OpenWaitableTimerW
0x180027e60  mov     cs:hObject, rax
0x180027e67  test    rax, rax
0x180027e6a  jnz     short loc_180027EA0
0x180027e6c  call    cs:__imp_GetLastError
0x180027e72  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x180027e79  mov     r8d, 0B2h
0x180027e7f  mov     ecx, r14d
0x180027e82  jmp     short loc_180027E90
0x180027e84  lea     r9, aFailedToCreate_6; "Failed to create named timer [%d]"
0x180027e8b  mov     ecx, 3
0x180027e90  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180027e94  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180027e9b  call    AslLogCallPrintf
0x180027ea0  cmp     cs:hObject, rsi
0x180027ea7  jnz     short loc_180027F1D
0x180027ea9  xor     r8d, r8d; lpTimerName
0x180027eac  xor     edx, edx; bManualReset
0x180027eae  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x180027eb3  call    cs:__imp_CreateWaitableTimerW
0x180027eb9  mov     cs:hObject, rax
0x180027ec0  test    rax, rax
0x180027ec3  jnz     short loc_180027EDF
0x180027ec5  call    cs:__imp_GetLastError
0x180027ecb  mov     ebx, eax
0x180027ecd  lea     r9, aFailedToCreate_1; "Failed to create timer [%d]"
0x180027ed4  mov     r8d, 0C5h
0x180027eda  jmp     loc_180027D29
0x180027edf  mov     qword ptr [rsp+4D0h+DueTime], 0FFFFFFFFFF676980h
0x180027ee8  mov     [rsp+4D0h+fResume], esi; fResume
0x180027eec  mov     [rsp+4D0h+lpArgToCompletionRoutine], rsi; lpArgToCompletionRoutine
0x180027ef1  xor     r9d, r9d; pfnCompletionRoutine
0x180027ef4  xor     r8d, r8d; lPeriod
0x180027ef7  lea     rdx, [rsp+4D0h+DueTime]; lpDueTime
0x180027efc  mov     rcx, rax; hTimer
0x180027eff  call    cs:__imp_SetWaitableTimer
0x180027f05  test    eax, eax
0x180027f07  jnz     short loc_180027F1D
0x180027f09  mov     rcx, cs:hObject; hObject
0x180027f10  call    cs:__imp_CloseHandle
0x180027f16  mov     cs:hObject, rsi
0x180027f1d  mov     cs:byte_1800FF0E0, r14b
0x180027f24  mov     ebx, esi
0x180027f26  mov     rcx, [rsp+4D0h+hMem]; hMem
0x180027f2b  test    rcx, rcx
0x180027f2e  jz      short loc_180027F3B
0x180027f30  call    cs:__imp_LocalFree
0x180027f36  mov     [rsp+4D0h+hMem], rsi
0x180027f3b  mov     rcx, r12; lpCriticalSection
0x180027f3e  call    cs:__imp_LeaveCriticalSection
0x180027f44  mov     eax, ebx
0x180027f46  mov     rcx, [rbp+3D0h+var_30]
0x180027f4d  xor     rcx, rsp; StackCookie
0x180027f50  call    __security_check_cookie
0x180027f55  add     rsp, 4B0h
0x180027f5c  pop     r14
0x180027f5e  pop     r12
0x180027f60  pop     rsi
0x180027f61  pop     rbx
0x180027f62  pop     rbp
0x180027f63  retn
```
