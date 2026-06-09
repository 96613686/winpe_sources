# MRxSmbUpdateFileInfoCacheFileSize

- ea: `0x140044568`
- end: `0x14004461e`
- name: `MRxSmbUpdateFileInfoCacheFileSize`
- size: `182`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002b980`
- `0x14003a494`
- `0x140044c70`
- `0x140048b30`

## callees

- `0x140044568`
- `0x14004b1b0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400445fe`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400445fe`
- `ntoskrnl!ExAcquireFastMutex` at `0x140044599`
- `ntoskrnl!ExAcquireFastMutex` at `0x140044599`
- `rdbss!RxNameCacheActivateEntry` at `0x1400445eb`
- `rdbss!RxNameCacheActivateEntry` at `0x1400445eb`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400445b9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400445b9`

## pseudocode

```c
void __fastcall MRxSmbUpdateFileInfoCacheFileSize(__int64 a1, struct _LIST_ENTRY **a2)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  __int64 v6; // rbp
  struct _NAME_CACHE *Entry; // rax
  struct _LIST_ENTRY *Flink; // r8

  v3 = *(_QWORD *)(a1 + 56);
  if ( *(_BYTE *)(a1 + 32) )
    v5 = *(_QWORD *)(v3 + 120);
  else
    v5 = *(_QWORD *)(a1 + 648);
  v6 = *(_QWORD *)(v5 + 40);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v6 + 472, v3 + 360, 0, 0);
  if ( Entry )
  {
    Flink = Entry->Link.Flink;
    Flink->Flink = *a2;
    Flink->Blink = *a2;
    RxNameCacheActivateEntry((PNAME_CACHE_CONTROL)(v6 + 472), Entry, 0, 0);
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  MRxSmbInvalidateFullDirectoryCacheParent(a1, 1);
}

```

## disassembly

```asm
0x140044568  push    rbx
0x14004456a  push    rbp
0x14004456b  push    rsi
0x14004456c  push    rdi
0x14004456d  sub     rsp, 28h
0x140044571  cmp     byte ptr [rcx+20h], 0
0x140044575  mov     rsi, rdx
0x140044578  mov     rdi, [rcx+38h]
0x14004457c  mov     rbx, rcx
0x14004457f  jnz     short loc_14004458A
0x140044581  mov     rax, [rcx+288h]
0x140044588  jmp     short loc_14004458E
0x14004458a  mov     rax, [rdi+78h]
0x14004458e  mov     rbp, [rax+28h]
0x140044592  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140044599  call    cs:__imp_ExAcquireFastMutex
0x1400445a0  nop     dword ptr [rax+rax+00h]
0x1400445a5  lea     rdx, [rdi+168h]
0x1400445ac  xor     r9d, r9d
0x1400445af  xor     r8d, r8d
0x1400445b2  lea     rcx, [rbp+1D8h]
0x1400445b9  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400445c0  nop     dword ptr [rax+rax+00h]
0x1400445c5  test    rax, rax
0x1400445c8  jz      short loc_1400445F7
0x1400445ca  mov     r8, [rax+28h]
0x1400445ce  lea     rcx, [rbp+1D8h]; NameCacheCtl
0x1400445d5  mov     rdx, [rsi]
0x1400445d8  xor     r9d, r9d; MRxContext
0x1400445db  mov     [r8], rdx
0x1400445de  mov     rdx, [rsi]
0x1400445e1  mov     [r8+8], rdx
0x1400445e5  xor     r8d, r8d; LifeTime
0x1400445e8  mov     rdx, rax; NameCache
0x1400445eb  call    cs:__imp_RxNameCacheActivateEntry
0x1400445f2  nop     dword ptr [rax+rax+00h]
0x1400445f7  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400445fe  call    cs:__imp_ExReleaseFastMutex
0x140044605  nop     dword ptr [rax+rax+00h]
0x14004460a  mov     dl, 1
0x14004460c  mov     rcx, rbx
0x14004460f  call    MRxSmbInvalidateFullDirectoryCacheParent
0x140044614  add     rsp, 28h
0x140044618  pop     rdi
0x140044619  pop     rsi
0x14004461a  pop     rbp
0x14004461b  pop     rbx
0x14004461c  retn
```
