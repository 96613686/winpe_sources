# TOKEN_CACHE::Terminate(void)

- ea: `0x180020138`
- end: `0x180020203`
- name: `?Terminate@TOKEN_CACHE@@QEAAXXZ`
- size: `203`
- prototype: `void __fastcall(TOKEN_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180004a18`
- `0x18001fc30`

## callees

- `0x180001250`
- `0x180020138`
- `0x18002225c`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800201a8`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800201a8`
- `KERNEL32!UnregisterWaitEx` at `0x18002015d`
- `KERNEL32!UnregisterWaitEx` at `0x18002015d`
- `KERNEL32!CloseHandle` at `0x180020174`
- `KERNEL32!CloseHandle` at `0x180020174`
- `ADVAPI32!RegCloseKey` at `0x18002018b`
- `ADVAPI32!RegCloseKey` at `0x18002018b`
- `ADVAPI32!CryptReleaseContext` at `0x1800201ec`
- `ADVAPI32!CryptReleaseContext` at `0x1800201ec`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800201c5`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800201c5`

## pseudocode

```c
void __fastcall TOKEN_CACHE::Terminate(TOKEN_CACHE *this)
{
  void *v2; // rcx
  void *v3; // rcx
  HKEY v4; // rcx
  void *v5; // rdx
  void *v6; // rbx

  if ( (*((_BYTE *)this + 104) & 1) != 0 )
  {
    ThreadPoolTerminate();
    *((_DWORD *)this + 26) &= ~1u;
  }
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    UnregisterWaitEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 11) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v4 = (HKEY)*((_QWORD *)this + 9);
  if ( v4 )
  {
    RegCloseKey(v4);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    DeleteTimerQueueTimer(0, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 12) = 0;
  }
  v6 = TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry;
  if ( TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry);
    operator delete(v6);
    TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry = 0;
  }
  if ( TOKEN_CACHE_ENTRY::sm_hCryptProv )
  {
    CryptReleaseContext(TOKEN_CACHE_ENTRY::sm_hCryptProv, 0);
    TOKEN_CACHE_ENTRY::sm_hCryptProv = 0;
  }
}

```

## disassembly

```asm
0x180020138  push    rbx
0x18002013a  sub     rsp, 20h
0x18002013e  test    byte ptr [rcx+68h], 1
0x180020142  mov     rbx, rcx
0x180020145  jz      short loc_180020150
0x180020147  call    ?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x18002014c  and     dword ptr [rbx+68h], 0FFFFFFFEh
0x180020150  mov     rcx, [rbx+58h]; WaitHandle
0x180020154  test    rcx, rcx
0x180020157  jz      short loc_18002016B
0x180020159  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002015d  call    cs:__imp_UnregisterWaitEx
0x180020163  mov     qword ptr [rbx+58h], 0
0x18002016b  mov     rcx, [rbx+50h]; hObject
0x18002016f  test    rcx, rcx
0x180020172  jz      short loc_180020182
0x180020174  call    cs:__imp_CloseHandle
0x18002017a  mov     qword ptr [rbx+50h], 0
0x180020182  mov     rcx, [rbx+48h]; hKey
0x180020186  test    rcx, rcx
0x180020189  jz      short loc_180020199
0x18002018b  call    cs:__imp_RegCloseKey
0x180020191  mov     qword ptr [rbx+48h], 0
0x180020199  mov     rdx, [rbx+60h]; Timer
0x18002019d  test    rdx, rdx
0x1800201a0  jz      short loc_1800201B6
0x1800201a2  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800201a6  xor     ecx, ecx; TimerQueue
0x1800201a8  call    cs:__imp_DeleteTimerQueueTimer
0x1800201ae  mov     qword ptr [rbx+60h], 0
0x1800201b6  mov     rbx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x1800201bd  test    rbx, rbx
0x1800201c0  jz      short loc_1800201DE
0x1800201c2  mov     rcx, rbx
0x1800201c5  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x1800201cb  mov     rcx, rbx; Block
0x1800201ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800201d3  mov     cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x1800201de  mov     rcx, cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; hProv
0x1800201e5  test    rcx, rcx
0x1800201e8  jz      short loc_1800201FD
0x1800201ea  xor     edx, edx; dwFlags
0x1800201ec  call    cs:__imp_CryptReleaseContext
0x1800201f2  mov     cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA, 0; unsigned __int64 TOKEN_CACHE_ENTRY::sm_hCryptProv
0x1800201fd  add     rsp, 20h
0x180020201  pop     rbx
0x180020202  retn
```
