# mDns_CreateResponderThread

- ea: `0x1800340bc`
- end: `0x180034135`
- name: `mDns_CreateResponderThread`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bf58`

## callees

- `0x1800340bc`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034109`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800340cb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800340cb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800340ef`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800340ef`

## pseudocode

```c
__int64 mDns_CreateResponderThread()
{
  DWORD v0; // ebx
  DWORD LastError; // eax

  v0 = 0;
  ResetEvent(g_mdnsResponderStop);
  g_hMdnsThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)MDns_ResponderThread, 0, 0, &g_mdnsThreadId);
  if ( !g_hMdnsThread )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 10, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, LastError);
  }
  return v0;
}

```

## disassembly

```asm
0x1800340bc  push    rbx
0x1800340be  sub     rsp, 30h
0x1800340c2  mov     rcx, cs:?g_mdnsResponderStop@@3PEAXEA; hEvent
0x1800340c9  xor     ebx, ebx
0x1800340cb  call    cs:__imp_ResetEvent
0x1800340d1  lea     rax, ?g_mdnsThreadId@@3KA; ulong g_mdnsThreadId
0x1800340d8  xor     r9d, r9d; lpParameter
0x1800340db  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800340e0  lea     r8, ?MDns_ResponderThread@@YAJPEAX@Z; lpStartAddress
0x1800340e7  xor     edx, edx; dwStackSize
0x1800340e9  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1800340ed  xor     ecx, ecx; lpThreadAttributes
0x1800340ef  call    cs:__imp_CreateThread
0x1800340f5  mov     cs:?g_hMdnsThread@@3PEAXEA, rax; void * g_hMdnsThread
0x1800340fc  test    rax, rax
0x1800340ff  jz      short loc_180034109
0x180034101  mov     eax, ebx
0x180034103  add     rsp, 30h
0x180034107  pop     rbx
0x180034108  retn
0x180034109  call    cs:__imp_GetLastError
0x18003410f  mov     ebx, eax
0x180034111  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180034118  jz      short loc_180034101
0x18003411a  mov     edx, 0Ah
0x18003411f  lea     r8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x180034126  mov     ecx, 40Bh
0x18003412b  mov     r9d, eax
0x18003412e  call    WPP_SF_d
0x180034133  jmp     short loc_180034101
```
