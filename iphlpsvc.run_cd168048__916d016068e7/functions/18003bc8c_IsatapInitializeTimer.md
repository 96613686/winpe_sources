# IsatapInitializeTimer

- ea: `0x18003bc8c`
- end: `0x18003be61`
- name: `IsatapInitializeTimer`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032e60`

## callees

- `0x180004f50`
- `0x18000d7b0`
- `0x1800159f0`
- `0x1800338e4`
- `0x1800340c0`
- `0x18003bc8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bcfc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bcfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003be1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003be1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bd7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bd7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003bd2b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003bd2b`

## string_xrefs

- `0x18003bd9e`: `%s has been created: timer memory pointer = %p`
- `0x18003bcbb`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18003bca3`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`

## pseudocode

```c
__int64 IsatapInitializeTimer()
{
  int v0; // eax
  HANDLE v1; // rbx
  struct _TP_WAIT *ThreadpoolWait; // rax
  unsigned int v3; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  DWORD LastError; // ebx
  char v6; // di

  EventWrite0(
    0x40000,
    L"ReferenceService: ++%u (%hs) @ %ls:%u",
    ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
    "IsatapInitializeTimer",
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
    2774);
  do
  {
    v0 = g_Reference;
    if ( (g_Reference & 1) != 0 )
    {
      v6 = 0;
      LastError = 21;
LABEL_15:
      if ( pwa )
      {
        TpclUnregisterWait(pwa);
        pwa = 0;
      }
      if ( qword_1800CA940 )
      {
        CloseHandle(qword_1800CA940);
        qword_1800CA940 = 0;
      }
      if ( v6 == 1 )
        DereferenceServiceEx("IsatapTimerCleanup", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c", 2828);
      return LastError;
    }
  }
  while ( v0 != _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) );
  qword_1800CA940 = CreateEventW(0, 0, 0, 0);
  v1 = qword_1800CA940;
  if ( qword_1800CA940 )
  {
    ThreadpoolWait = CreateThreadpoolWait(IsatapTimerCleanup, 0, &CallbackEnvironment);
    pwa = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      TpclSetThreadpoolWait(ThreadpoolWait, v1);
      v3 = dword_1800CA124 == 2 ? 60000 * dword_1800CA128 : 0x7FFFFFFF;
      ThreadpoolTimer = CreateThreadpoolTimer(IsatapTimerCallback, 0, &CallbackEnvironment);
      qword_1800CA938 = (__int64)ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        EventWrite0(0x8000000, L"%s has been created: timer memory pointer = %p", L"Isatap Timer", ThreadpoolTimer);
        if ( (unsigned int)TpclSetTimer(L"Isatap Timer", qword_1800CA938, 0, v3) )
          return 0;
      }
    }
  }
  LastError = GetLastError();
  v6 = 1;
  if ( LastError )
    goto LABEL_15;
  return LastError;
}

```

## disassembly

```asm
0x18003bc8c  mov     rax, rsp
0x18003bc8f  mov     [rax+10h], rbx
0x18003bc93  mov     [rax+18h], rsi
0x18003bc97  push    rdi
0x18003bc98  sub     rsp, 30h
0x18003bc9c  mov     r8d, cs:g_Reference
0x18003bca3  lea     rsi, aOnecoreuapNetN_39; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003bcaa  shr     r8d, 1
0x18003bcad  lea     r9, aIsatapinitiali_1; "IsatapInitializeTimer"
0x18003bcb4  mov     dword ptr [rax-10h], 0AD6h
0x18003bcbb  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18003bcc2  and     r8d, 3FFFFFFFh
0x18003bcc9  mov     [rax-18h], rsi
0x18003bccd  mov     ecx, 40000h
0x18003bcd2  call    EventWrite0
0x18003bcd7  mov     eax, cs:g_Reference
0x18003bcdd  test    al, 1
0x18003bcdf  jnz     loc_18003BDE7
0x18003bce5  lea     ecx, [rax+2]
0x18003bce8  lock cmpxchg cs:g_Reference, ecx
0x18003bcf0  jnz     short loc_18003BCD7
0x18003bcf2  xor     r9d, r9d; lpName
0x18003bcf5  xor     r8d, r8d; bInitialState
0x18003bcf8  xor     edx, edx; bManualReset
0x18003bcfa  xor     ecx, ecx; lpEventAttributes
0x18003bcfc  call    cs:__imp_CreateEventW
0x18003bd03  nop     dword ptr [rax+rax+00h]
0x18003bd08  mov     cs:qword_1800CA940, rax
0x18003bd0f  mov     rbx, rax
0x18003bd12  test    rax, rax
0x18003bd15  jz      loc_18003BDD0
0x18003bd1b  lea     r8, CallbackEnvironment; pcbe
0x18003bd22  xor     edx, edx; pv
0x18003bd24  lea     rcx, IsatapTimerCleanup; pfnwa
0x18003bd2b  call    cs:__imp_CreateThreadpoolWait
0x18003bd32  nop     dword ptr [rax+rax+00h]
0x18003bd37  mov     cs:pwa, rax
0x18003bd3e  test    rax, rax
0x18003bd41  jz      loc_18003BDD0
0x18003bd47  mov     rdx, rbx
0x18003bd4a  mov     rcx, rax
0x18003bd4d  call    TpclSetThreadpoolWait
0x18003bd52  cmp     cs:dword_1800CA124, 2
0x18003bd59  jnz     short loc_18003BD67
0x18003bd5b  imul    ebx, cs:dword_1800CA128, 0EA60h
0x18003bd65  jmp     short loc_18003BD6C
0x18003bd67  mov     ebx, 7FFFFFFFh
0x18003bd6c  lea     r8, CallbackEnvironment; pcbe
0x18003bd73  xor     edx, edx; pv
0x18003bd75  lea     rcx, IsatapTimerCallback; pfnti
0x18003bd7c  call    cs:__imp_CreateThreadpoolTimer
0x18003bd83  nop     dword ptr [rax+rax+00h]
0x18003bd88  mov     cs:qword_1800CA938, rax
0x18003bd8f  test    rax, rax
0x18003bd92  jz      short loc_18003BDD0
0x18003bd94  mov     r9, rax
0x18003bd97  lea     r8, aIsatapTimer; "Isatap Timer"
0x18003bd9e  lea     rdx, aSHasBeenCreate; "%s has been created: timer memory point"...
0x18003bda5  mov     ecx, 8000000h
0x18003bdaa  call    EventWrite0
0x18003bdaf  mov     rdx, cs:qword_1800CA938
0x18003bdb6  lea     rcx, aIsatapTimer; "Isatap Timer"
0x18003bdbd  mov     r9d, ebx
0x18003bdc0  xor     r8d, r8d
0x18003bdc3  call    TpclSetTimer
0x18003bdc8  test    eax, eax
0x18003bdca  jz      short loc_18003BDD0
0x18003bdcc  xor     ebx, ebx
0x18003bdce  jmp     short loc_18003BE4E
0x18003bdd0  call    cs:__imp_GetLastError
0x18003bdd7  nop     dword ptr [rax+rax+00h]
0x18003bddc  mov     ebx, eax
0x18003bdde  mov     dil, 1
0x18003bde1  test    eax, eax
0x18003bde3  jnz     short loc_18003BDEF
0x18003bde5  jmp     short loc_18003BE4E
0x18003bde7  xor     dil, dil
0x18003bdea  mov     ebx, 15h
0x18003bdef  mov     rcx, cs:pwa; pwa
0x18003bdf6  test    rcx, rcx
0x18003bdf9  jz      short loc_18003BE10
0x18003bdfb  xor     r8d, r8d
0x18003bdfe  xor     edx, edx
0x18003be00  call    TpclUnregisterWait
0x18003be05  mov     cs:pwa, 0
0x18003be10  mov     rcx, cs:qword_1800CA940; hObject
0x18003be17  test    rcx, rcx
0x18003be1a  jz      short loc_18003BE33
0x18003be1c  call    cs:__imp_CloseHandle
0x18003be23  nop     dword ptr [rax+rax+00h]
0x18003be28  mov     cs:qword_1800CA940, 0
0x18003be33  cmp     dil, 1
0x18003be37  jnz     short loc_18003BE4E
0x18003be39  mov     r8d, 0B0Ch
0x18003be3f  lea     rcx, aIsataptimercle; "IsatapTimerCleanup"
0x18003be46  mov     rdx, rsi
0x18003be49  call    DereferenceServiceEx
0x18003be4e  mov     rsi, [rsp+38h+arg_10]
0x18003be53  mov     eax, ebx
0x18003be55  mov     rbx, [rsp+38h+arg_8]
0x18003be5a  add     rsp, 30h
0x18003be5e  pop     rdi
0x18003be5f  retn
```
