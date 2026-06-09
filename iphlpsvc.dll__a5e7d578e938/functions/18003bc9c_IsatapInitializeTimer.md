# IsatapInitializeTimer

- ea: `0x18003bc9c`
- end: `0x18003be71`
- name: `IsatapInitializeTimer`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032e70`

## callees

- `0x180004f60`
- `0x18000d7c0`
- `0x180015a00`
- `0x1800338f4`
- `0x1800340d0`
- `0x18003bc9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bd0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bd0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bde0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bde0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003be2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003be2c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bd8c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bd8c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003bd3b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003bd3b`

## string_xrefs

- `0x18003bdae`: `%s has been created: timer memory pointer = %p`
- `0x18003bccb`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18003bcb3`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`

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
0x18003bc9c  mov     rax, rsp
0x18003bc9f  mov     [rax+10h], rbx
0x18003bca3  mov     [rax+18h], rsi
0x18003bca7  push    rdi
0x18003bca8  sub     rsp, 30h
0x18003bcac  mov     r8d, cs:g_Reference
0x18003bcb3  lea     rsi, aOnecoreuapNetN_39; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003bcba  shr     r8d, 1
0x18003bcbd  lea     r9, aIsatapinitiali_1; "IsatapInitializeTimer"
0x18003bcc4  mov     dword ptr [rax-10h], 0AD6h
0x18003bccb  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18003bcd2  and     r8d, 3FFFFFFFh
0x18003bcd9  mov     [rax-18h], rsi
0x18003bcdd  mov     ecx, 40000h
0x18003bce2  call    EventWrite0
0x18003bce7  mov     eax, cs:g_Reference
0x18003bced  test    al, 1
0x18003bcef  jnz     loc_18003BDF7
0x18003bcf5  lea     ecx, [rax+2]
0x18003bcf8  lock cmpxchg cs:g_Reference, ecx
0x18003bd00  jnz     short loc_18003BCE7
0x18003bd02  xor     r9d, r9d; lpName
0x18003bd05  xor     r8d, r8d; bInitialState
0x18003bd08  xor     edx, edx; bManualReset
0x18003bd0a  xor     ecx, ecx; lpEventAttributes
0x18003bd0c  call    cs:__imp_CreateEventW
0x18003bd13  nop     dword ptr [rax+rax+00h]
0x18003bd18  mov     cs:qword_1800CA940, rax
0x18003bd1f  mov     rbx, rax
0x18003bd22  test    rax, rax
0x18003bd25  jz      loc_18003BDE0
0x18003bd2b  lea     r8, CallbackEnvironment; pcbe
0x18003bd32  xor     edx, edx; pv
0x18003bd34  lea     rcx, IsatapTimerCleanup; pfnwa
0x18003bd3b  call    cs:__imp_CreateThreadpoolWait
0x18003bd42  nop     dword ptr [rax+rax+00h]
0x18003bd47  mov     cs:pwa, rax
0x18003bd4e  test    rax, rax
0x18003bd51  jz      loc_18003BDE0
0x18003bd57  mov     rdx, rbx
0x18003bd5a  mov     rcx, rax
0x18003bd5d  call    TpclSetThreadpoolWait
0x18003bd62  cmp     cs:dword_1800CA124, 2
0x18003bd69  jnz     short loc_18003BD77
0x18003bd6b  imul    ebx, cs:dword_1800CA128, 0EA60h
0x18003bd75  jmp     short loc_18003BD7C
0x18003bd77  mov     ebx, 7FFFFFFFh
0x18003bd7c  lea     r8, CallbackEnvironment; pcbe
0x18003bd83  xor     edx, edx; pv
0x18003bd85  lea     rcx, IsatapTimerCallback; pfnti
0x18003bd8c  call    cs:__imp_CreateThreadpoolTimer
0x18003bd93  nop     dword ptr [rax+rax+00h]
0x18003bd98  mov     cs:qword_1800CA938, rax
0x18003bd9f  test    rax, rax
0x18003bda2  jz      short loc_18003BDE0
0x18003bda4  mov     r9, rax
0x18003bda7  lea     r8, aIsatapTimer; "Isatap Timer"
0x18003bdae  lea     rdx, aSHasBeenCreate; "%s has been created: timer memory point"...
0x18003bdb5  mov     ecx, 8000000h
0x18003bdba  call    EventWrite0
0x18003bdbf  mov     rdx, cs:qword_1800CA938
0x18003bdc6  lea     rcx, aIsatapTimer; "Isatap Timer"
0x18003bdcd  mov     r9d, ebx
0x18003bdd0  xor     r8d, r8d
0x18003bdd3  call    TpclSetTimer
0x18003bdd8  test    eax, eax
0x18003bdda  jz      short loc_18003BDE0
0x18003bddc  xor     ebx, ebx
0x18003bdde  jmp     short loc_18003BE5E
0x18003bde0  call    cs:__imp_GetLastError
0x18003bde7  nop     dword ptr [rax+rax+00h]
0x18003bdec  mov     ebx, eax
0x18003bdee  mov     dil, 1
0x18003bdf1  test    eax, eax
0x18003bdf3  jnz     short loc_18003BDFF
0x18003bdf5  jmp     short loc_18003BE5E
0x18003bdf7  xor     dil, dil
0x18003bdfa  mov     ebx, 15h
0x18003bdff  mov     rcx, cs:pwa; pwa
0x18003be06  test    rcx, rcx
0x18003be09  jz      short loc_18003BE20
0x18003be0b  xor     r8d, r8d
0x18003be0e  xor     edx, edx
0x18003be10  call    TpclUnregisterWait
0x18003be15  mov     cs:pwa, 0
0x18003be20  mov     rcx, cs:qword_1800CA940; hObject
0x18003be27  test    rcx, rcx
0x18003be2a  jz      short loc_18003BE43
0x18003be2c  call    cs:__imp_CloseHandle
0x18003be33  nop     dword ptr [rax+rax+00h]
0x18003be38  mov     cs:qword_1800CA940, 0
0x18003be43  cmp     dil, 1
0x18003be47  jnz     short loc_18003BE5E
0x18003be49  mov     r8d, 0B0Ch
0x18003be4f  lea     rcx, aIsataptimercle; "IsatapTimerCleanup"
0x18003be56  mov     rdx, rsi
0x18003be59  call    DereferenceServiceEx
0x18003be5e  mov     rsi, [rsp+38h+arg_10]
0x18003be63  mov     eax, ebx
0x18003be65  mov     rbx, [rsp+38h+arg_8]
0x18003be6a  add     rsp, 30h
0x18003be6e  pop     rdi
0x18003be6f  retn
```
