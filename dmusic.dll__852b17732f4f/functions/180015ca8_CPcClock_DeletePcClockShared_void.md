# CPcClock::DeletePcClockShared(void)

- ea: `0x180015ca8`
- end: `0x180015d81`
- name: `?DeletePcClockShared@CPcClock@@AEAAXXZ`
- size: `217`
- prototype: `void __fastcall(CPcClock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180015a1c`

## callees

- `0x180015ca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015d68`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015d68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015cc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015cc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015cd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015cd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015d75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015d75`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180015d33`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180015d33`

## pseudocode

```c
void __fastcall CPcClock::DeletePcClockShared(CPcClock *this)
{
  _QWORD *v1; // rcx
  unsigned int v2; // ebx
  DWORD CurrentProcessId; // eax

  if ( CPcClock::m_hPcClockMutex )
  {
    WaitForSingleObject(CPcClock::m_hPcClockMutex, 0xFFFFFFFF);
    v1 = CPcClock::m_pShared;
    if ( CPcClock::m_pShared )
    {
      v2 = 0;
      while ( 1 )
      {
        CurrentProcessId = GetCurrentProcessId();
        v1 = CPcClock::m_pShared;
        if ( *((_DWORD *)CPcClock::m_pShared + 4 * v2 + 4) == CurrentProcessId )
          break;
        if ( (int)++v2 >= 64 )
          goto LABEL_8;
      }
      *((_DWORD *)CPcClock::m_pShared + 4 * v2 + 4) = 0;
      v1[2 * v2 + 1] = 0;
    }
LABEL_8:
    if ( CPcClock::m_hClock )
    {
      CloseHandle(CPcClock::m_hClock);
      v1 = CPcClock::m_pShared;
      CPcClock::m_hClock = 0;
    }
    if ( v1 )
    {
      UnmapViewOfFile(v1);
      CPcClock::m_pShared = 0;
    }
    if ( CPcClock::m_hFileMapping )
    {
      CloseHandle(CPcClock::m_hFileMapping);
      CPcClock::m_hFileMapping = 0;
    }
    ReleaseMutex(CPcClock::m_hPcClockMutex);
    CloseHandle(CPcClock::m_hPcClockMutex);
  }
}

```

## disassembly

```asm
0x180015ca8  push    rbx
0x180015caa  sub     rsp, 20h
0x180015cae  mov     rcx, cs:?m_hPcClockMutex@CPcClock@@0PEAXEA; hHandle
0x180015cb5  test    rcx, rcx
0x180015cb8  jz      loc_180015D7B
0x180015cbe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015cc1  call    cs:__imp_WaitForSingleObject
0x180015cc7  mov     rcx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015cce  test    rcx, rcx
0x180015cd1  jz      short loc_180015D07
0x180015cd3  xor     ebx, ebx
0x180015cd5  call    cs:__imp_GetCurrentProcessId
0x180015cdb  mov     rcx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015ce2  mov     edx, ebx
0x180015ce4  add     rdx, rdx
0x180015ce7  cmp     [rcx+rdx*8+10h], eax
0x180015ceb  jz      short loc_180015CF6
0x180015ced  inc     ebx
0x180015cef  cmp     ebx, 40h ; '@'
0x180015cf2  jl      short loc_180015CD5
0x180015cf4  jmp     short loc_180015D07
0x180015cf6  mov     dword ptr [rcx+rdx*8+10h], 0
0x180015cfe  mov     qword ptr [rcx+rdx*8+8], 0
0x180015d07  mov     rax, cs:?m_hClock@CPcClock@@0PEAXEA; void * CPcClock::m_hClock
0x180015d0e  test    rax, rax
0x180015d11  jz      short loc_180015D2E
0x180015d13  mov     rcx, rax; hObject
0x180015d16  call    cs:__imp_CloseHandle
0x180015d1c  mov     rcx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; lpBaseAddress
0x180015d23  mov     cs:?m_hClock@CPcClock@@0PEAXEA, 0; void * CPcClock::m_hClock
0x180015d2e  test    rcx, rcx
0x180015d31  jz      short loc_180015D44
0x180015d33  call    cs:__imp_UnmapViewOfFile
0x180015d39  mov     cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA, 0; PCCLOCKSHARE * CPcClock::m_pShared
0x180015d44  mov     rcx, cs:?m_hFileMapping@CPcClock@@0PEAXEA; hObject
0x180015d4b  test    rcx, rcx
0x180015d4e  jz      short loc_180015D61
0x180015d50  call    cs:__imp_CloseHandle
0x180015d56  mov     cs:?m_hFileMapping@CPcClock@@0PEAXEA, 0; void * CPcClock::m_hFileMapping
0x180015d61  mov     rcx, cs:?m_hPcClockMutex@CPcClock@@0PEAXEA; hMutex
0x180015d68  call    cs:__imp_ReleaseMutex
0x180015d6e  mov     rcx, cs:?m_hPcClockMutex@CPcClock@@0PEAXEA; hObject
0x180015d75  call    cs:__imp_CloseHandle
0x180015d7b  add     rsp, 20h
0x180015d7f  pop     rbx
0x180015d80  retn
```
