# UtcThrottle::Initialize(ushort const *)

- ea: `0x18001178c`
- end: `0x180011b28`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `924`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001377c`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18001178c`
- `0x180011b30`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011815`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011815`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011919`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011919`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180011a1e`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180011a1e`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180011ac3`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180011ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001192b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001192b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ad4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ad4`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180011965`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800119a8`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180011965`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800119a8`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800119ec`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180011a77`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800119ec`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180011a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011af4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011af4`

## string_xrefs

- `0x1800118e0`: `Failed to initialize security descriptor [%d]`
- `0x180011933`: `Failed to create event [%d]`
- `0x180011981`: `Failed to create named semaphore [%d]`
- `0x1800119c2`: `Failed to create semaphore [%d]`
- `0x180011a36`: `Failed to open named timer [%d]`
- `0x180011a48`: `Failed to create named timer [%d]`
- `0x180011a91`: `Failed to create timer [%d]`

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
  EnterCriticalSection(&stru_180157088);
  DueTime.QuadPart = (LONGLONG)&stru_180157088;
  if ( byte_1801570B0 )
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
  if ( !qword_180157080 )
  {
    qword_180157080 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_180157080 )
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
  byte_1801570B0 = 1;
LABEL_40:
  v10 = 0;
LABEL_41:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  LeaveCriticalSection(&stru_180157088);
  return v10;
}

```

## disassembly

```asm
0x18001178c  push    rbp
0x18001178e  push    rbx
0x18001178f  push    rsi
0x180011790  push    r12
0x180011792  push    r14
0x180011794  lea     rbp, [rsp-3B0h]
0x18001179c  sub     rsp, 4B0h
0x1800117a3  mov     rax, cs:__security_cookie
0x1800117aa  xor     rax, rsp
0x1800117ad  mov     [rbp+3D0h+var_30], rax
0x1800117b4  xorps   xmm0, xmm0
0x1800117b7  xor     eax, eax
0x1800117b9  movups  xmmword ptr [rsp+4D0h+var_478.Revision], xmm0
0x1800117be  movups  xmmword ptr [rsp+4D0h+var_478.Group], xmm0
0x1800117c3  mov     [rsp+4D0h+var_478.Dacl], rax
0x1800117c8  xor     esi, esi
0x1800117ca  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.nLength], 18h
0x1800117d3  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.bInheritHandle], rsi
0x1800117d8  mov     [rsp+4D0h+hMem], rsi
0x1800117dd  mov     ebx, 208h
0x1800117e2  mov     r8d, ebx; Size
0x1800117e5  xor     edx, edx; Val
0x1800117e7  lea     rcx, [rbp+3D0h+Name]; void *
0x1800117ee  call    memset_0
0x1800117f3  mov     r8d, ebx; Size
0x1800117f6  xor     edx, edx; Val
0x1800117f8  lea     rcx, [rbp+3D0h+TimerName]; void *
0x1800117fc  call    memset_0
0x180011801  lea     rax, [rsp+4D0h+var_478]
0x180011806  mov     [rsp+4D0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x18001180b  lea     r12, stru_180157088
0x180011812  mov     rcx, r12; lpCriticalSection
0x180011815  call    cs:__imp_EnterCriticalSection
0x18001181b  mov     qword ptr [rsp+4D0h+DueTime], r12
0x180011820  cmp     cs:byte_1801570B0, sil
0x180011827  jnz     loc_180011AE8
0x18001182d  mov     r9d, 7FFFFFFEh
0x180011833  mov     ecx, r9d
0x180011836  lea     r10, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x18001183d  mov     edx, 104h
0x180011842  mov     r8d, edx
0x180011845  lea     rax, [rbp+3D0h+Name]
0x18001184c  lea     r14d, [rsi+1]
0x180011850  test    rcx, rcx
0x180011853  jz      short loc_180011873
0x180011855  movzx   r11d, word ptr [r10]
0x180011859  test    r11w, r11w
0x18001185d  jz      short loc_180011873
0x18001185f  add     r10, 2
0x180011863  mov     [rax], r11w
0x180011867  add     rax, 2
0x18001186b  sub     rcx, r14
0x18001186e  sub     r8, r14
0x180011871  jnz     short loc_180011850
0x180011873  lea     rcx, [rax-2]
0x180011877  test    r8, r8
0x18001187a  cmovnz  rcx, rax
0x18001187e  mov     [rcx], si
0x180011881  jnz     short loc_18001188D
0x180011883  mov     ebx, 0Eh
0x180011888  jmp     loc_180011AEA
0x18001188d  lea     rcx, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x180011894  lea     rax, [rbp+3D0h+TimerName]
0x180011898  test    r9, r9
0x18001189b  jz      short loc_1800118BB
0x18001189d  movzx   r8d, word ptr [rcx]
0x1800118a1  test    r8w, r8w
0x1800118a5  jz      short loc_1800118BB
0x1800118a7  add     rcx, 2
0x1800118ab  mov     [rax], r8w
0x1800118af  add     rax, 2
0x1800118b3  sub     r9, r14
0x1800118b6  sub     rdx, r14
0x1800118b9  jnz     short loc_180011898
0x1800118bb  lea     rcx, [rax-2]
0x1800118bf  test    rdx, rdx
0x1800118c2  cmovnz  rcx, rax; this
0x1800118c6  mov     [rcx], si
0x1800118c9  jz      short loc_180011883
0x1800118cb  lea     r8, [rsp+4D0h+hMem]; struct _ACL **
0x1800118d0  lea     rdx, [rsp+4D0h+var_478]; struct _SECURITY_DESCRIPTOR *
0x1800118d5  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x1800118da  mov     ebx, eax
0x1800118dc  test    eax, eax
0x1800118de  jz      short loc_180011905
0x1800118e0  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x1800118e7  mov     r8d, 7Bh ; '{'
0x1800118ed  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x1800118f1  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x1800118f8  mov     ecx, r14d
0x1800118fb  call    AslLogCallPrintf
0x180011900  jmp     loc_180011AEA
0x180011905  cmp     cs:qword_180157080, rsi
0x18001190c  jnz     short loc_180011942
0x18001190e  xor     r9d, r9d; lpName
0x180011911  xor     r8d, r8d; bInitialState
0x180011914  mov     edx, r14d; bManualReset
0x180011917  xor     ecx, ecx; lpEventAttributes
0x180011919  call    cs:__imp_CreateEventW
0x18001191f  mov     cs:qword_180157080, rax
0x180011926  test    rax, rax
0x180011929  jnz     short loc_180011942
0x18001192b  call    cs:__imp_GetLastError
0x180011931  mov     ebx, eax
0x180011933  lea     r9, aFailedToCreate_4; "Failed to create event [%d]"
0x18001193a  mov     r8d, 85h
0x180011940  jmp     short loc_1800118ED
0x180011942  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rsi; UtcThrottle InventoryCoreUtcThrottle
0x180011949  jnz     loc_1800119D4
0x18001194f  lea     r9, [rbp+3D0h+Name]; lpName
0x180011956  mov     ebx, 14h
0x18001195b  mov     r8d, ebx; lMaximumCount
0x18001195e  mov     edx, ebx; lInitialCount
0x180011960  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180011965  call    cs:__imp_CreateSemaphoreW
0x18001196b  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x180011972  test    rax, rax
0x180011975  jnz     short loc_1800119D4
0x180011977  call    cs:__imp_GetLastError
0x18001197d  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180011981  lea     r9, aFailedToCreate_6; "Failed to create named semaphore [%d]"
0x180011988  lea     r8d, [rbx+7Ch]
0x18001198c  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180011993  lea     ecx, [rbx-11h]
0x180011996  call    AslLogCallPrintf
0x18001199b  xor     r9d, r9d; lpName
0x18001199e  mov     r8d, ebx; lMaximumCount
0x1800119a1  mov     edx, ebx; lInitialCount
0x1800119a3  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x1800119a8  call    cs:__imp_CreateSemaphoreW
0x1800119ae  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x1800119b5  test    rax, rax
0x1800119b8  jnz     short loc_1800119D4
0x1800119ba  call    cs:__imp_GetLastError
0x1800119c0  mov     ebx, eax
0x1800119c2  lea     r9, aFailedToCreate_5; "Failed to create semaphore [%d]"
0x1800119c9  mov     r8d, 96h
0x1800119cf  jmp     loc_1800118ED
0x1800119d4  cmp     cs:hObject, rsi
0x1800119db  jnz     loc_180011AE1
0x1800119e1  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x1800119e5  xor     edx, edx; bManualReset
0x1800119e7  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x1800119ec  call    cs:__imp_CreateWaitableTimerW
0x1800119f2  mov     cs:hObject, rax
0x1800119f9  test    rax, rax
0x1800119fc  jnz     loc_180011AA3
0x180011a02  call    cs:__imp_GetLastError
0x180011a08  mov     r8d, 0B7h
0x180011a0e  cmp     eax, r8d
0x180011a11  jnz     short loc_180011A48
0x180011a13  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x180011a17  xor     edx, edx; bInheritHandle
0x180011a19  mov     ecx, 100000h; dwDesiredAccess
0x180011a1e  call    cs:__imp_OpenWaitableTimerW
0x180011a24  mov     cs:hObject, rax
0x180011a2b  test    rax, rax
0x180011a2e  jnz     short loc_180011A64
0x180011a30  call    cs:__imp_GetLastError
0x180011a36  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x180011a3d  mov     r8d, 0B2h
0x180011a43  mov     ecx, r14d
0x180011a46  jmp     short loc_180011A54
0x180011a48  lea     r9, aFailedToCreate_7; "Failed to create named timer [%d]"
0x180011a4f  mov     ecx, 3
0x180011a54  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x180011a58  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180011a5f  call    AslLogCallPrintf
0x180011a64  cmp     cs:hObject, rsi
0x180011a6b  jnz     short loc_180011AE1
0x180011a6d  xor     r8d, r8d; lpTimerName
0x180011a70  xor     edx, edx; bManualReset
0x180011a72  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x180011a77  call    cs:__imp_CreateWaitableTimerW
0x180011a7d  mov     cs:hObject, rax
0x180011a84  test    rax, rax
0x180011a87  jnz     short loc_180011AA3
0x180011a89  call    cs:__imp_GetLastError
0x180011a8f  mov     ebx, eax
0x180011a91  lea     r9, aFailedToCreate_3; "Failed to create timer [%d]"
0x180011a98  mov     r8d, 0C5h
0x180011a9e  jmp     loc_1800118ED
0x180011aa3  mov     qword ptr [rsp+4D0h+DueTime], 0FFFFFFFFFF676980h
0x180011aac  mov     [rsp+4D0h+fResume], esi; fResume
0x180011ab0  mov     [rsp+4D0h+lpArgToCompletionRoutine], rsi; lpArgToCompletionRoutine
0x180011ab5  xor     r9d, r9d; pfnCompletionRoutine
0x180011ab8  xor     r8d, r8d; lPeriod
0x180011abb  lea     rdx, [rsp+4D0h+DueTime]; lpDueTime
0x180011ac0  mov     rcx, rax; hTimer
0x180011ac3  call    cs:__imp_SetWaitableTimer
0x180011ac9  test    eax, eax
0x180011acb  jnz     short loc_180011AE1
0x180011acd  mov     rcx, cs:hObject; hObject
0x180011ad4  call    cs:__imp_CloseHandle
0x180011ada  mov     cs:hObject, rsi
0x180011ae1  mov     cs:byte_1801570B0, r14b
0x180011ae8  mov     ebx, esi
0x180011aea  mov     rcx, [rsp+4D0h+hMem]; hMem
0x180011aef  test    rcx, rcx
0x180011af2  jz      short loc_180011AFF
0x180011af4  call    cs:__imp_LocalFree
0x180011afa  mov     [rsp+4D0h+hMem], rsi
0x180011aff  mov     rcx, r12; lpCriticalSection
0x180011b02  call    cs:__imp_LeaveCriticalSection
0x180011b08  mov     eax, ebx
0x180011b0a  mov     rcx, [rbp+3D0h+var_30]
0x180011b11  xor     rcx, rsp; StackCookie
0x180011b14  call    __security_check_cookie
0x180011b19  add     rsp, 4B0h
0x180011b20  pop     r14
0x180011b22  pop     r12
0x180011b24  pop     rsi
0x180011b25  pop     rbx
0x180011b26  pop     rbp
0x180011b27  retn
```
