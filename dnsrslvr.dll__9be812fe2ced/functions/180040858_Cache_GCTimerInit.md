# Cache_GCTimerInit

- ea: `0x180040858`
- end: `0x180040921`
- name: `Cache_GCTimerInit`
- size: `201`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800495c0`

## callees

- `0x180040858`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800408c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800408c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800408fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800408fc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040882`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040882`

## pseudocode

```c
__int64 Cache_GCTimerInit()
{
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  DWORD v1; // eax
  DWORD v2; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax

  pftDueTime.dwHighDateTime = -3;
  pftDueTime.dwLowDateTime = 884901888;
  ThreadpoolTimer = CreateThreadpoolTimer(Cache_GarbageCollectCb, 0, 0);
  if ( ThreadpoolTimer )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      v2 = 0;
      pti = ThreadpoolTimer;
      g_hCacheGCEvent = EventW;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 90, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, LastError);
      CloseThreadpoolTimer(ThreadpoolTimer);
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 89, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, v1);
  }
  return v2;
}

```

## disassembly

```asm
0x180040858  mov     [rsp+arg_0], rbx
0x18004085d  push    rdi
0x18004085e  sub     rsp, 20h
0x180040862  xor     r8d, r8d; pcbe
0x180040865  mov     cs:pftDueTime.dwHighDateTime, 0FFFFFFFDh
0x18004086f  xor     edx, edx; pv
0x180040871  mov     cs:pftDueTime.dwLowDateTime, 34BE8800h
0x18004087b  lea     rcx, Cache_GarbageCollectCb; pfnti
0x180040882  call    cs:__imp_CreateThreadpoolTimer
0x180040888  mov     rdi, rax
0x18004088b  test    rax, rax
0x18004088e  jnz     short loc_1800408BA
0x180040890  call    cs:__imp_GetLastError
0x180040896  mov     ebx, eax
0x180040898  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004089f  jz      short loc_180040914
0x1800408a1  lea     edx, [rdi+59h]
0x1800408a4  mov     ecx, 40Bh
0x1800408a9  mov     r9d, eax
0x1800408ac  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x1800408b3  call    WPP_SF_d
0x1800408b8  jmp     short loc_180040914
0x1800408ba  xor     r9d, r9d; lpName
0x1800408bd  xor     r8d, r8d; bInitialState
0x1800408c0  xor     edx, edx; bManualReset
0x1800408c2  xor     ecx, ecx; lpEventAttributes
0x1800408c4  call    cs:__imp_CreateEventW
0x1800408ca  test    rax, rax
0x1800408cd  jnz     short loc_180040904
0x1800408cf  call    cs:__imp_GetLastError
0x1800408d5  mov     ebx, eax
0x1800408d7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800408de  jz      short loc_1800408F9
0x1800408e0  mov     edx, 5Ah ; 'Z'
0x1800408e5  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x1800408ec  mov     ecx, 40Bh
0x1800408f1  mov     r9d, eax
0x1800408f4  call    WPP_SF_d
0x1800408f9  mov     rcx, rdi; pti
0x1800408fc  call    cs:__imp_CloseThreadpoolTimer
0x180040902  jmp     short loc_180040914
0x180040904  xor     ebx, ebx
0x180040906  mov     cs:pti, rdi
0x18004090d  mov     cs:g_hCacheGCEvent, rax
0x180040914  mov     eax, ebx
0x180040916  mov     rbx, [rsp+28h+arg_0]
0x18004091b  add     rsp, 20h
0x18004091f  pop     rdi
0x180040920  retn
```
