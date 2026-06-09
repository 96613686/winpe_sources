# MRxSmbInvalidateFileNotFoundCache

- ea: `0x1400507a0`
- end: `0x140050894`
- name: `MRxSmbInvalidateFileNotFoundCache`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002b980`
- `0x140036d40`
- `0x14003a494`
- `0x14003b07c`
- `0x14003b4c8`
- `0x140047fb0`
- `0x140048b30`

## callees

- `0x1400507a0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140050851`
- `ntoskrnl!ExReleaseFastMutex` at `0x140050851`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005081b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005081b`
- `rdbss!RxNameCacheExpireEntry` at `0x140050886`
- `rdbss!RxNameCacheExpireEntry` at `0x140050886`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140050839`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140050839`

## pseudocode

```c
void __fastcall MRxSmbInvalidateFileNotFoundCache(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // r9
  __int64 v3; // rax
  unsigned __int16 v4; // r10
  __int64 v5; // rbx
  unsigned __int16 i; // ax
  struct _NAME_CACHE *Entry; // rax
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_BYTE *)(a1 + 32) == 0;
  v2 = *(_QWORD *)(a1 + 56);
  v8 = 0;
  if ( v1 )
    v3 = *(_QWORD *)(a1 + 648);
  else
    v3 = *(_QWORD *)(v2 + 120);
  v4 = *(_WORD *)(v2 + 360);
  v5 = *(_QWORD *)(v3 + 40);
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int16)(v4 >> 1) )
    {
      WORD1(v8) = *(_WORD *)(v2 + 360);
      LOWORD(v8) = v4;
      goto LABEL_8;
    }
    if ( *(_WORD *)(*(_QWORD *)(v2 + 368) + 2LL * i) == 58 )
      break;
  }
  WORD1(v8) = 2 * i;
  LOWORD(v8) = 2 * i;
LABEL_8:
  *((_QWORD *)&v8 + 1) = *(_QWORD *)(v2 + 368);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5 + 840, &v8, 0, 0);
  if ( Entry )
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v5 + 840), Entry);
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
}

```

## disassembly

```asm
0x1400507a0  push    rbx
0x1400507a2  sub     rsp, 30h
0x1400507a6  cmp     byte ptr [rcx+20h], 0
0x1400507aa  xorps   xmm0, xmm0
0x1400507ad  mov     r9, [rcx+38h]
0x1400507b1  movups  [rsp+38h+var_18], xmm0
0x1400507b6  jnz     loc_140050864
0x1400507bc  mov     rax, [rcx+288h]
0x1400507c3  movzx   r10d, word ptr [r9+168h]
0x1400507cb  mov     rbx, [rax+28h]
0x1400507cf  movzx   r8d, r10w
0x1400507d3  xor     eax, eax
0x1400507d5  shr     r8w, 1
0x1400507d9  nop     dword ptr [rax+00000000h]
0x1400507e0  cmp     ax, r8w
0x1400507e4  jnb     short loc_1400507FC
0x1400507e6  mov     rcx, [r9+170h]
0x1400507ed  movzx   edx, ax
0x1400507f0  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x1400507f5  jz      short loc_14005086D
0x1400507f7  inc     ax
0x1400507fa  jmp     short loc_1400507E0
0x1400507fc  mov     word ptr [rsp+38h+var_18+2], r10w
0x140050802  mov     word ptr [rsp+38h+var_18], r10w
0x140050808  mov     rax, [r9+170h]
0x14005080f  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140050816  mov     qword ptr [rsp+38h+var_18+8], rax
0x14005081b  call    cs:__imp_ExAcquireFastMutex
0x140050822  nop     dword ptr [rax+rax+00h]
0x140050827  xor     r9d, r9d
0x14005082a  lea     rdx, [rsp+38h+var_18]
0x14005082f  xor     r8d, r8d
0x140050832  lea     rcx, [rbx+348h]
0x140050839  call    cs:__imp_RxNameCacheFetchEntryEx
0x140050840  nop     dword ptr [rax+rax+00h]
0x140050845  test    rax, rax
0x140050848  jnz     short loc_14005087C
0x14005084a  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140050851  call    cs:__imp_ExReleaseFastMutex
0x140050858  nop     dword ptr [rax+rax+00h]
0x14005085d  add     rsp, 30h
0x140050861  pop     rbx
0x140050862  retn
0x140050864  mov     rax, [r9+78h]
0x140050868  jmp     loc_1400507C3
0x14005086d  add     ax, ax
0x140050870  mov     word ptr [rsp+38h+var_18+2], ax
0x140050875  mov     word ptr [rsp+38h+var_18], ax
0x14005087a  jmp     short loc_140050808
0x14005087c  mov     rdx, rax; NameCache
0x14005087f  lea     rcx, [rbx+348h]; NameCacheCtl
0x140050886  call    cs:__imp_RxNameCacheExpireEntry
0x14005088d  nop     dword ptr [rax+rax+00h]
0x140050892  jmp     short loc_14005084A
```
