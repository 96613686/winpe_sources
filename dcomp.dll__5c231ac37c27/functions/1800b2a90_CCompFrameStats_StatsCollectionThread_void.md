# CCompFrameStats::StatsCollectionThread(void)

- ea: `0x1800b2a90`
- end: `0x1800b2bcd`
- name: `?StatsCollectionThread@CCompFrameStats@@IEAAXXZ`
- size: `317`
- prototype: `void __fastcall(CCompFrameStats *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b2a80`

## callees

- `0x1800b2a90`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800b2bb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800b2bb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2ab4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2ab4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2ae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2b46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2b82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2ae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2b46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2b82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2ac5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2b2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2b5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2ac5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2b2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2b5d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b2af6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b2af6`

## pseudocode

```c
void __fastcall __noreturn CCompFrameStats::StatsCollectionThread(CCompFrameStats *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  HMODULE v5; // rbx
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  if ( *((_BYTE *)this + 13) )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
LABEL_9:
    EnterCriticalSection(v4);
    if ( *((_BYTE *)this + 12) )
      (*(void (__fastcall **)(CCompFrameStats *, _QWORD))(*(_QWORD *)this + 208LL))(this, *((_QWORD *)this + 15));
    LeaveCriticalSection(v4);
    if ( *((_BYTE *)this + 12) )
      (*(void (__fastcall **)(CCompFrameStats *))(*(_QWORD *)this + 232LL))(this);
    v5 = (HMODULE)*((_QWORD *)this + 6);
    (*(void (__fastcall **)(CCompFrameStats *))(*(_QWORD *)this + 16LL))(this);
    FreeLibraryAndExitThread(v5, 0);
  }
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  while ( 1 )
  {
    if ( !WaitForSingleObject(*((HANDLE *)this + 8), 0xFFFFFFFF) )
    {
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
      (*(void (__fastcall **)(CCompFrameStats *, _QWORD))(*(_QWORD *)this + 208LL))(this, 0);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    }
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    if ( PerformanceCount.QuadPart <= *((_QWORD *)this + 4) )
      break;
    v4 = v3;
    if ( (unsigned int)((unsigned __int64)(1000 * (PerformanceCount.QuadPart - *((_QWORD *)this + 4)))
                      / *((_QWORD *)this + 2)) <= *((_DWORD *)this + 10) )
      goto LABEL_16;
    EnterCriticalSection(v3);
    (*(void (__fastcall **)(CCompFrameStats *))(*(_QWORD *)this + 224LL))(this);
    LeaveCriticalSection(v3);
    *((_BYTE *)this + 13) = 1;
LABEL_8:
    if ( *((_BYTE *)this + 13) )
      goto LABEL_9;
  }
  v4 = v1;
LABEL_16:
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  goto LABEL_8;
}

```

## disassembly

```asm
0x1800b2a90  push    rbx
0x1800b2a92  push    rbp
0x1800b2a93  push    rsi
0x1800b2a94  push    rdi
0x1800b2a95  sub     rsp, 28h
0x1800b2a99  cmp     byte ptr [rcx+0Dh], 0
0x1800b2a9d  lea     rbp, [rcx+48h]
0x1800b2aa1  mov     rdi, rcx
0x1800b2aa4  jnz     loc_1800B2BBF
0x1800b2aaa  mov     rbx, rbp
0x1800b2aad  mov     rcx, [rdi+40h]; hHandle
0x1800b2ab1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2ab4  call    cs:__imp_WaitForSingleObject
0x1800b2aba  test    eax, eax
0x1800b2abc  jnz     short loc_1800B2AE8
0x1800b2abe  lea     rbx, [rdi+48h]
0x1800b2ac2  mov     rcx, rbx; lpCriticalSection
0x1800b2ac5  call    cs:__imp_EnterCriticalSection
0x1800b2acb  mov     rax, [rdi]
0x1800b2ace  xor     edx, edx
0x1800b2ad0  mov     rcx, rdi
0x1800b2ad3  mov     rax, [rax+0D0h]
0x1800b2ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2adf  mov     rcx, rbx; lpCriticalSection
0x1800b2ae2  call    cs:__imp_LeaveCriticalSection
0x1800b2ae8  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x1800b2aed  mov     qword ptr [rsp+48h+PerformanceCount], 0
0x1800b2af6  call    cs:__imp_QueryPerformanceCounter
0x1800b2afc  mov     rax, qword ptr [rsp+48h+PerformanceCount]
0x1800b2b01  cmp     rax, [rdi+20h]
0x1800b2b05  jle     loc_1800B2BC4
0x1800b2b0b  sub     rax, [rdi+20h]
0x1800b2b0f  xor     edx, edx
0x1800b2b11  imul    rax, 3E8h
0x1800b2b18  mov     rsi, rbx
0x1800b2b1b  div     qword ptr [rdi+10h]
0x1800b2b1f  cmp     eax, [rdi+28h]
0x1800b2b22  jbe     loc_1800B2BC7
0x1800b2b28  mov     rcx, rbx; lpCriticalSection
0x1800b2b2b  call    cs:__imp_EnterCriticalSection
0x1800b2b31  mov     rax, [rdi]
0x1800b2b34  mov     rcx, rdi
0x1800b2b37  mov     rax, [rax+0E0h]
0x1800b2b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b43  mov     rcx, rbx; lpCriticalSection
0x1800b2b46  call    cs:__imp_LeaveCriticalSection
0x1800b2b4c  mov     byte ptr [rdi+0Dh], 1
0x1800b2b50  cmp     byte ptr [rdi+0Dh], 0
0x1800b2b54  jz      loc_1800B2AAD
0x1800b2b5a  mov     rcx, rsi; lpCriticalSection
0x1800b2b5d  call    cs:__imp_EnterCriticalSection
0x1800b2b63  cmp     byte ptr [rdi+0Ch], 0
0x1800b2b67  jz      short loc_1800B2B7F
0x1800b2b69  mov     rax, [rdi]
0x1800b2b6c  mov     rcx, rdi
0x1800b2b6f  mov     rdx, [rdi+78h]
0x1800b2b73  mov     rax, [rax+0D0h]
0x1800b2b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b7f  mov     rcx, rsi; lpCriticalSection
0x1800b2b82  call    cs:__imp_LeaveCriticalSection
0x1800b2b88  cmp     byte ptr [rdi+0Ch], 0
0x1800b2b8c  jz      short loc_1800B2BA0
0x1800b2b8e  mov     rax, [rdi]
0x1800b2b91  mov     rcx, rdi
0x1800b2b94  mov     rax, [rax+0E8h]
0x1800b2b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ba0  mov     rax, [rdi]
0x1800b2ba3  mov     rcx, rdi
0x1800b2ba6  mov     rbx, [rdi+30h]
0x1800b2baa  mov     rax, [rax+10h]
0x1800b2bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2bb3  xor     edx, edx; dwExitCode
0x1800b2bb5  mov     rcx, rbx; hLibModule
0x1800b2bb8  call    cs:__imp_FreeLibraryAndExitThread
0x1800b2bbe  int     3; Trap to Debugger
0x1800b2bbf  mov     rsi, rbp
0x1800b2bc2  jmp     short loc_1800B2B5A
0x1800b2bc4  mov     rsi, rbp
0x1800b2bc7  lea     rbx, [rdi+48h]
0x1800b2bcb  jmp     short loc_1800B2B50
```
