# CPcClock::CreatePcClockShared(void)

- ea: `0x180015b50`
- end: `0x180015ca2`
- name: `?CreatePcClockShared@CPcClock@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(CPcClock *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180015a60`

## callees

- `0x1800021a8`
- `0x180015b50`
- `0x180015d88`
- `0x180015f2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180015b65`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180015b65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015bd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015c8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015bd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015c8f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015b87`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015c6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015c6d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015c05`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015c05`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180015bae`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180015bae`

## pseudocode

```c
__int64 __fastcall CPcClock::CreatePcClockShared(CPcClock *this)
{
  HANDLE MutexA; // rax
  signed int LastError; // ebx
  _DWORD *v4; // rax
  CPcClock *v5; // rcx
  _DWORD *v6; // rdi

  MutexA = CreateMutexA(0, 0, "DirectMusiCPcClockMutex");
  CPcClock::m_hPcClockMutex = MutexA;
  if ( !MutexA )
    return 2147942414LL;
  WaitForSingleObject(MutexA, 0xFFFFFFFF);
  CPcClock::m_hFileMapping = CreateFileMappingA((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x408u, "DirectMusiCPcClock");
  LastError = GetLastError();
  if ( CPcClock::m_hFileMapping )
  {
    v4 = MapViewOfFile(CPcClock::m_hFileMapping, 2u, 0, 0, 0);
    CPcClock::m_pShared = v4;
    v6 = v4;
    if ( v4 )
    {
      if ( LastError != 183 )
      {
        *v4 = 0;
        memset_0(v4 + 2, 0, 0x400u);
      }
      LastError = 1;
      if ( ++*v6 == 1 )
      {
        if ( (unsigned int)LookForPortClock(&CPcClock::m_hClock) )
        {
          *((_QWORD *)CPcClock::m_pShared + 1) = CPcClock::m_hClock;
          LastError = 0;
          *((_DWORD *)CPcClock::m_pShared + 4) = GetCurrentProcessId();
        }
      }
      else
      {
        LastError = CPcClock::DuplicatePcClockHandle(v5);
      }
    }
    else
    {
      LastError = -2147024882;
    }
    ReleaseMutex(CPcClock::m_hPcClockMutex);
  }
  else
  {
    ReleaseMutex(CPcClock::m_hPcClockMutex);
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180015b50  mov     [rsp+arg_0], rbx
0x180015b55  push    rdi
0x180015b56  sub     rsp, 30h
0x180015b5a  lea     r8, ?m_cszPcClockMutex@CPcClock@@0QBDB; "DirectMusiCPcClockMutex"
0x180015b61  xor     edx, edx; bInitialOwner
0x180015b63  xor     ecx, ecx; lpMutexAttributes
0x180015b65  call    cs:__imp_CreateMutexA
0x180015b6b  mov     cs:?m_hPcClockMutex@CPcClock@@0PEAXEA, rax; void * CPcClock::m_hPcClockMutex
0x180015b72  test    rax, rax
0x180015b75  jnz     short loc_180015B81
0x180015b77  mov     eax, 8007000Eh
0x180015b7c  jmp     loc_180015C97
0x180015b81  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015b84  mov     rcx, rax; hHandle
0x180015b87  call    cs:__imp_WaitForSingleObject
0x180015b8d  xor     r9d, r9d; dwMaximumSizeHigh
0x180015b90  lea     rax, ?m_cszPcClockMemory@CPcClock@@0QBDB; "DirectMusiCPcClock"
0x180015b97  mov     [rsp+38h+lpName], rax; lpName
0x180015b9c  xor     edx, edx; lpFileMappingAttributes
0x180015b9e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180015ba2  mov     [rsp+38h+dwMaximumSizeLow], 408h; dwMaximumSizeLow
0x180015baa  lea     r8d, [r9+4]; flProtect
0x180015bae  call    cs:__imp_CreateFileMappingA
0x180015bb4  mov     cs:?m_hFileMapping@CPcClock@@0PEAXEA, rax; void * CPcClock::m_hFileMapping
0x180015bbb  call    cs:__imp_GetLastError
0x180015bc1  mov     rcx, cs:?m_hFileMapping@CPcClock@@0PEAXEA; hFileMappingObject
0x180015bc8  mov     ebx, eax
0x180015bca  test    rcx, rcx
0x180015bcd  jnz     short loc_180015BF2
0x180015bcf  mov     rcx, cs:?m_hPcClockMutex@CPcClock@@0PEAXEA; hMutex
0x180015bd6  call    cs:__imp_ReleaseMutex
0x180015bdc  test    ebx, ebx
0x180015bde  jle     loc_180015C95
0x180015be4  movzx   ebx, bx
0x180015be7  or      ebx, 80070000h
0x180015bed  jmp     loc_180015C95
0x180015bf2  xor     r9d, r9d; dwFileOffsetLow
0x180015bf5  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180015bfe  xor     r8d, r8d; dwFileOffsetHigh
0x180015c01  lea     edx, [r9+2]; dwDesiredAccess
0x180015c05  call    cs:__imp_MapViewOfFile
0x180015c0b  mov     cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA, rax; PCCLOCKSHARE * CPcClock::m_pShared
0x180015c12  mov     rdi, rax
0x180015c15  test    rax, rax
0x180015c18  jnz     short loc_180015C21
0x180015c1a  mov     ebx, 8007000Eh
0x180015c1f  jmp     short loc_180015C88
0x180015c21  cmp     ebx, 0B7h
0x180015c27  jz      short loc_180015C40
0x180015c29  lea     rcx, [rax+8]; void *
0x180015c2d  mov     dword ptr [rax], 0
0x180015c33  xor     edx, edx; Val
0x180015c35  mov     r8d, 400h; Size
0x180015c3b  call    memset_0
0x180015c40  mov     ebx, 1
0x180015c45  add     [rdi], ebx
0x180015c47  cmp     [rdi], ebx
0x180015c49  jnz     short loc_180015C81
0x180015c4b  lea     rcx, ?m_hClock@CPcClock@@0PEAXEA; void * CPcClock::m_hClock
0x180015c52  call    LookForPortClock
0x180015c57  test    eax, eax
0x180015c59  jz      short loc_180015C88
0x180015c5b  mov     rcx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015c62  mov     rax, cs:?m_hClock@CPcClock@@0PEAXEA; void * CPcClock::m_hClock
0x180015c69  mov     [rcx+8], rax
0x180015c6d  call    cs:__imp_GetCurrentProcessId
0x180015c73  mov     rcx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015c7a  xor     ebx, ebx
0x180015c7c  mov     [rcx+10h], eax
0x180015c7f  jmp     short loc_180015C88
0x180015c81  call    ?DuplicatePcClockHandle@CPcClock@@AEAAJXZ; CPcClock::DuplicatePcClockHandle(void)
0x180015c86  mov     ebx, eax
0x180015c88  mov     rcx, cs:?m_hPcClockMutex@CPcClock@@0PEAXEA; hMutex
0x180015c8f  call    cs:__imp_ReleaseMutex
0x180015c95  mov     eax, ebx
0x180015c97  mov     rbx, [rsp+38h+arg_0]
0x180015c9c  add     rsp, 30h
0x180015ca0  pop     rdi
0x180015ca1  retn
```
