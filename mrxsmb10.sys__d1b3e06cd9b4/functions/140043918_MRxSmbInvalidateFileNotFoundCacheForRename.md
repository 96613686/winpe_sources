# MRxSmbInvalidateFileNotFoundCacheForRename

- ea: `0x140043918`
- end: `0x1400439d7`
- name: `MRxSmbInvalidateFileNotFoundCacheForRename`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b980`
- `0x14003c3f8`

## callees

- `0x140043918`
- `0x140044700`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400439c4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400439c4`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043978`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043978`
- `rdbss!RxNameCacheExpireEntry` at `0x1400439b1`
- `rdbss!RxNameCacheExpireEntry` at `0x1400439b1`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043996`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043996`

## pseudocode

```c
void __fastcall MRxSmbInvalidateFileNotFoundCacheForRename(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // rdx
  __int64 v3; // rax
  __int64 v4; // rbx
  struct _NAME_CACHE *Entry; // rax
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v1 = *(_BYTE *)(a1 + 32) == 0;
  v2 = *(_QWORD *)(a1 + 456);
  v6[0] = 0;
  v7 = 0;
  v6[1] = v2 + 20;
  LOWORD(v6[0]) = *(_WORD *)(v2 + 16);
  if ( v1 )
    v3 = *(_QWORD *)(a1 + 648);
  else
    v3 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL);
  v4 = *(_QWORD *)(v3 + 40);
  MRxSmbIsStreamFile(v6, &v7);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v4 + 840, &v7, 0, 0);
  if ( Entry )
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v4 + 840), Entry);
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
}

```

## disassembly

```asm
0x140043918  push    rbx
0x14004391a  sub     rsp, 40h
0x14004391e  cmp     byte ptr [rcx+20h], 0
0x140043922  xorps   xmm0, xmm0
0x140043925  mov     rdx, [rcx+1C8h]
0x14004392c  xorps   xmm1, xmm1
0x14004392f  movups  [rsp+48h+var_28], xmm0
0x140043934  movups  [rsp+48h+var_18], xmm1
0x140043939  lea     rax, [rdx+14h]
0x14004393d  mov     qword ptr [rsp+48h+var_28+8], rax
0x140043942  movzx   eax, word ptr [rdx+10h]
0x140043946  mov     word ptr [rsp+48h+var_28], ax
0x14004394b  jnz     short loc_140043956
0x14004394d  mov     rax, [rcx+288h]
0x140043954  jmp     short loc_14004395E
0x140043956  mov     rax, [rcx+38h]
0x14004395a  mov     rax, [rax+78h]
0x14004395e  mov     rbx, [rax+28h]
0x140043962  lea     rdx, [rsp+48h+var_18]
0x140043967  lea     rcx, [rsp+48h+var_28]
0x14004396c  call    MRxSmbIsStreamFile
0x140043971  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043978  call    cs:__imp_ExAcquireFastMutex
0x14004397f  nop     dword ptr [rax+rax+00h]
0x140043984  xor     r9d, r9d
0x140043987  lea     rdx, [rsp+48h+var_18]
0x14004398c  xor     r8d, r8d
0x14004398f  lea     rcx, [rbx+348h]
0x140043996  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004399d  nop     dword ptr [rax+rax+00h]
0x1400439a2  test    rax, rax
0x1400439a5  jz      short loc_1400439BD
0x1400439a7  mov     rdx, rax; NameCache
0x1400439aa  lea     rcx, [rbx+348h]; NameCacheCtl
0x1400439b1  call    cs:__imp_RxNameCacheExpireEntry
0x1400439b8  nop     dword ptr [rax+rax+00h]
0x1400439bd  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400439c4  call    cs:__imp_ExReleaseFastMutex
0x1400439cb  nop     dword ptr [rax+rax+00h]
0x1400439d0  add     rsp, 40h
0x1400439d4  pop     rbx
0x1400439d5  retn
```
