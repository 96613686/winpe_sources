# MRxDAVCacheFileNotFoundWithName

- ea: `0x1400252f8`
- end: `0x1400253d7`
- name: `MRxDAVCacheFileNotFoundWithName`
- size: `223`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400128a0`
- `0x1400130e0`
- `0x14001f6c0`
- `0x140022a80`

## callees

- `0x1400027ac`
- `0x1400252f8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140025317`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025317`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002538b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002538b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14002532f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14002532f`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14002534c`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14002534c`
- `rdbss!RxNameCacheActivateEntry` at `0x140025378`
- `rdbss!RxNameCacheActivateEntry` at `0x140025378`

## pseudocode

```c
_UNKNOWN **__fastcall MRxDAVCacheFileNotFoundWithName(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 Entry; // rax
  __int64 v5; // r9
  struct _NAME_CACHE_CONTROL_ *v6; // rcx
  ULONG v7; // r9d
  _UNKNOWN **result; // rax

  v3 = *(_QWORD *)(a2 + 40) + 384LL;
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = RxNameCacheFetchEntryEx(v3, a1, 0, 0);
  v6 = (struct _NAME_CACHE_CONTROL_ *)v3;
  if ( !Entry )
  {
    LOBYTE(v5) = 1;
    Entry = RxNameCacheCreateEntryEx(v3, a1, 0, v5);
    if ( !Entry )
      goto LABEL_5;
    v6 = (struct _NAME_CACHE_CONTROL_ *)v3;
  }
  v7 = MRxContext;
  *(_DWORD *)(Entry + 48) = -1073741772;
  RxNameCacheActivateEntry(v6, (PNAME_CACHE)Entry, FileNotFoundCacheLifeTimeInSec, v7);
LABEL_5:
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    return (_UNKNOWN **)WPP_SF_Z(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          30,
                          WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
                          a1);
  return result;
}

```

## disassembly

```asm
0x1400252f8  mov     [rsp+arg_0], rbx
0x1400252fd  push    rdi
0x1400252fe  sub     rsp, 20h
0x140025302  mov     rbx, [rdx+28h]
0x140025306  mov     rdi, rcx
0x140025309  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025310  add     rbx, 180h
0x140025317  call    cs:__imp_ExAcquireFastMutex
0x14002531e  nop     dword ptr [rax+rax+00h]
0x140025323  xor     r9d, r9d
0x140025326  xor     r8d, r8d
0x140025329  mov     rdx, rdi
0x14002532c  mov     rcx, rbx
0x14002532f  call    cs:__imp_RxNameCacheFetchEntryEx
0x140025336  nop     dword ptr [rax+rax+00h]
0x14002533b  mov     rcx, rbx
0x14002533e  test    rax, rax
0x140025341  jnz     short loc_140025360
0x140025343  mov     r9b, 1
0x140025346  xor     r8d, r8d
0x140025349  mov     rdx, rdi
0x14002534c  call    cs:__imp_RxNameCacheCreateEntryEx
0x140025353  nop     dword ptr [rax+rax+00h]
0x140025358  test    rax, rax
0x14002535b  jz      short loc_140025384
0x14002535d  mov     rcx, rbx; NameCacheCtl
0x140025360  mov     r9d, cs:MRxContext; MRxContext
0x140025367  mov     rdx, rax; NameCache
0x14002536a  mov     dword ptr [rax+30h], 0C0000034h
0x140025371  mov     r8d, cs:FileNotFoundCacheLifeTimeInSec; LifeTime
0x140025378  call    cs:__imp_RxNameCacheActivateEntry
0x14002537f  nop     dword ptr [rax+rax+00h]
0x140025384  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x14002538b  call    cs:__imp_ExReleaseFastMutex
0x140025392  nop     dword ptr [rax+rax+00h]
0x140025397  mov     rcx, cs:WPP_GLOBAL_Control
0x14002539e  lea     rax, WPP_GLOBAL_Control
0x1400253a5  cmp     rcx, rax
0x1400253a8  jz      short loc_1400253CB
0x1400253aa  test    dword ptr [rcx+2Ch], 2000h
0x1400253b1  jz      short loc_1400253CB
0x1400253b3  mov     rcx, [rcx+18h]
0x1400253b7  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x1400253be  mov     edx, 1Eh
0x1400253c3  mov     r9, rdi
0x1400253c6  call    WPP_SF_Z
0x1400253cb  mov     rbx, [rsp+28h+arg_0]
0x1400253d0  add     rsp, 20h
0x1400253d4  pop     rdi
0x1400253d5  retn
```
