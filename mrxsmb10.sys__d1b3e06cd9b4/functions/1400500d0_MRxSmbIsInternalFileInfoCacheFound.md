# MRxSmbIsInternalFileInfoCacheFound

- ea: `0x1400500d0`
- end: `0x1400501bb`
- name: `MRxSmbIsInternalFileInfoCacheFound`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140048b30`

## callees

- `0x1400500d0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14005013d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005013d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005010a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005010a`
- `rdbss!RxNameCacheExpireEntry` at `0x1400501aa`
- `rdbss!RxNameCacheExpireEntry` at `0x1400501aa`
- `rdbss!RxNameCacheActivateEntry` at `0x140050199`
- `rdbss!RxNameCacheActivateEntry` at `0x140050199`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140050122`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140050122`
- `rdbss!RxNameCacheCheckEntry` at `0x140050168`
- `rdbss!RxNameCacheCheckEntry` at `0x140050168`

## pseudocode

```c
__int64 __fastcall MRxSmbIsInternalFileInfoCacheFound(__int64 a1, struct _LIST_ENTRY **a2, _DWORD *a3)
{
  __int64 v3; // rax
  unsigned __int8 v4; // bl
  __int64 v7; // rdi
  __int64 v8; // rax
  struct _NAME_CACHE_CONTROL_ *v9; // rsi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v11; // rdi
  int Blink; // eax

  v3 = *(_QWORD *)(a1 + 56);
  v4 = 0;
  v7 = v3 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v8 = *(_QWORD *)(v3 + 120);
  else
    v8 = *(_QWORD *)(a1 + 648);
  v9 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v8 + 40) + 656LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v9, v7, 0, 0);
  v11 = Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) )
    {
      RxNameCacheExpireEntry(v9, v11);
    }
    else
    {
      Blink = (int)v11->Link.Blink;
      ++v9->Spare[0];
      *a3 = Blink;
      v4 = 1;
      *a2 = v11->Link.Flink->Flink;
      RxNameCacheActivateEntry(v9, v11, 0, 0);
    }
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  return v4;
}

```

## disassembly

```asm
0x1400500d0  push    rbx
0x1400500d2  push    rsi
0x1400500d3  push    rdi
0x1400500d4  push    r14
0x1400500d6  push    r15
0x1400500d8  sub     rsp, 20h
0x1400500dc  mov     rax, [rcx+38h]
0x1400500e0  xor     bl, bl
0x1400500e2  mov     r14, r8
0x1400500e5  mov     r15, rdx
0x1400500e8  lea     rdi, [rax+168h]
0x1400500ef  cmp     [rcx+20h], bl
0x1400500f2  jz      short loc_140050159
0x1400500f4  mov     rax, [rax+78h]
0x1400500f8  mov     rsi, [rax+28h]
0x1400500fc  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140050103  add     rsi, 290h
0x14005010a  call    cs:__imp_ExAcquireFastMutex
0x140050111  nop     dword ptr [rax+rax+00h]
0x140050116  xor     r9d, r9d
0x140050119  xor     r8d, r8d
0x14005011c  mov     rdx, rdi
0x14005011f  mov     rcx, rsi
0x140050122  call    cs:__imp_RxNameCacheFetchEntryEx
0x140050129  nop     dword ptr [rax+rax+00h]
0x14005012e  mov     rdi, rax
0x140050131  test    rax, rax
0x140050134  jnz     short loc_140050162
0x140050136  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14005013d  call    cs:__imp_ExReleaseFastMutex
0x140050144  nop     dword ptr [rax+rax+00h]
0x140050149  movzx   eax, bl
0x14005014c  add     rsp, 20h
0x140050150  pop     r15
0x140050152  pop     r14
0x140050154  pop     rdi
0x140050155  pop     rsi
0x140050156  pop     rbx
0x140050157  retn
0x140050159  mov     rax, [rcx+288h]
0x140050160  jmp     short loc_1400500F8
0x140050162  mov     edx, [rax+20h]; MRxContext
0x140050165  mov     rcx, rdi; NameCache
0x140050168  call    cs:__imp_RxNameCacheCheckEntry
0x14005016f  nop     dword ptr [rax+rax+00h]
0x140050174  mov     rcx, rsi; NameCacheCtl
0x140050177  test    eax, eax
0x140050179  jnz     short loc_1400501A7
0x14005017b  mov     eax, [rdi+30h]
0x14005017e  xor     r9d, r9d; MRxContext
0x140050181  inc     dword ptr [rsi+74h]
0x140050184  xor     r8d, r8d; LifeTime
0x140050187  mov     [r14], eax
0x14005018a  mov     bl, 1
0x14005018c  mov     rax, [rdi+28h]
0x140050190  mov     rdx, [rax]
0x140050193  mov     [r15], rdx
0x140050196  mov     rdx, rdi; NameCache
0x140050199  call    cs:__imp_RxNameCacheActivateEntry
0x1400501a0  nop     dword ptr [rax+rax+00h]
0x1400501a5  jmp     short loc_140050136
0x1400501a7  mov     rdx, rdi; NameCache
0x1400501aa  call    cs:__imp_RxNameCacheExpireEntry
0x1400501b1  nop     dword ptr [rax+rax+00h]
0x1400501b6  jmp     loc_140050136
```
