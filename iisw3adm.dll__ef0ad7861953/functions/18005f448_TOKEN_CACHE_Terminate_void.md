# TOKEN_CACHE::Terminate(void)

- ea: `0x18005f448`
- end: `0x18005f514`
- name: `?Terminate@TOKEN_CACHE@@QEAAXXZ`
- size: `204`
- prototype: `void __fastcall(TOKEN_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180006880`
- `0x18005eab0`

## callees

- `0x180001274`
- `0x18005f448`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f49c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f49c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005f4b9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005f4b9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18005f46e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18005f46e`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18005f4d6`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18005f4d6`
- `W3TP!ThreadPoolTerminate` at `0x18005f457`
- `W3TP!ThreadPoolTerminate` at `0x18005f457`
- `CRYPTSP!CryptReleaseContext` at `0x18005f4fd`
- `CRYPTSP!CryptReleaseContext` at `0x18005f4fd`

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
0x18005f448  push    rbx
0x18005f44a  sub     rsp, 20h
0x18005f44e  test    byte ptr [rcx+68h], 1
0x18005f452  mov     rbx, rcx
0x18005f455  jz      short loc_18005F461
0x18005f457  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x18005f45d  and     dword ptr [rbx+68h], 0FFFFFFFEh
0x18005f461  mov     rcx, [rbx+58h]; WaitHandle
0x18005f465  test    rcx, rcx
0x18005f468  jz      short loc_18005F47C
0x18005f46a  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18005f46e  call    cs:__imp_UnregisterWaitEx
0x18005f474  mov     qword ptr [rbx+58h], 0
0x18005f47c  mov     rcx, [rbx+50h]; hObject
0x18005f480  test    rcx, rcx
0x18005f483  jz      short loc_18005F493
0x18005f485  call    cs:__imp_CloseHandle
0x18005f48b  mov     qword ptr [rbx+50h], 0
0x18005f493  mov     rcx, [rbx+48h]; hKey
0x18005f497  test    rcx, rcx
0x18005f49a  jz      short loc_18005F4AA
0x18005f49c  call    cs:__imp_RegCloseKey
0x18005f4a2  mov     qword ptr [rbx+48h], 0
0x18005f4aa  mov     rdx, [rbx+60h]; Timer
0x18005f4ae  test    rdx, rdx
0x18005f4b1  jz      short loc_18005F4C7
0x18005f4b3  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18005f4b7  xor     ecx, ecx; TimerQueue
0x18005f4b9  call    cs:__imp_DeleteTimerQueueTimer
0x18005f4bf  mov     qword ptr [rbx+60h], 0
0x18005f4c7  mov     rbx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18005f4ce  test    rbx, rbx
0x18005f4d1  jz      short loc_18005F4EF
0x18005f4d3  mov     rcx, rbx
0x18005f4d6  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18005f4dc  mov     rcx, rbx; Block
0x18005f4df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005f4e4  mov     cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18005f4ef  mov     rcx, cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; hProv
0x18005f4f6  test    rcx, rcx
0x18005f4f9  jz      short loc_18005F50E
0x18005f4fb  xor     edx, edx; dwFlags
0x18005f4fd  call    cs:__imp_CryptReleaseContext
0x18005f503  mov     cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA, 0; unsigned __int64 TOKEN_CACHE_ENTRY::sm_hCryptProv
0x18005f50e  add     rsp, 20h
0x18005f512  pop     rbx
0x18005f513  retn
```
