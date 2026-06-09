# MRxSmbIsFileNotFoundCached

- ea: `0x14004ef00`
- end: `0x14004f053`
- name: `MRxSmbIsFileNotFoundCached`
- size: `339`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14002b980`
- `0x140036d40`
- `0x14003b07c`
- `0x140048b30`

## callees

- `0x14004ef00`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004efc4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004efc4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004ef8f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004ef8f`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f042`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f042`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f02e`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f02e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004efa9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004efa9`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f006`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f006`

## pseudocode

```c
__int64 __fastcall MRxSmbIsFileNotFoundCached(__int64 a1)
{
  __int64 v1; // r9
  unsigned __int8 v2; // di
  __int64 v3; // rax
  __int64 v4; // rsi
  unsigned __int16 v5; // ax
  unsigned __int16 v6; // r10
  struct _NAME_CACHE_CONTROL_ *v7; // rsi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v9; // rbx
  __int128 v11; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v2 = 0;
  v11 = 0;
  if ( *(_BYTE *)(a1 + 32) )
    v3 = *(_QWORD *)(v1 + 120);
  else
    v3 = *(_QWORD *)(a1 + 648);
  v4 = *(_QWORD *)(v3 + 40);
  v5 = 0;
  v6 = *(_WORD *)(v1 + 360);
  v7 = (struct _NAME_CACHE_CONTROL_ *)(v4 + 840);
  while ( 1 )
  {
    if ( v5 >= (unsigned __int16)(v6 >> 1) )
    {
      WORD1(v11) = *(_WORD *)(v1 + 360);
      LOWORD(v11) = v6;
      goto LABEL_8;
    }
    if ( *(_WORD *)(*(_QWORD *)(v1 + 368) + 2LL * v5) == 58 )
      break;
    ++v5;
  }
  WORD1(v11) = 2 * v5;
  LOWORD(v11) = 2 * v5;
LABEL_8:
  *((_QWORD *)&v11 + 1) = *(_QWORD *)(v1 + 368);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v7, &v11, 0, 0);
  v9 = Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) || LODWORD(v9->Link.Blink) != -1073741772 )
    {
      RxNameCacheExpireEntry(v7, v9);
    }
    else
    {
      v2 = 1;
      RxNameCacheActivateEntry(v7, v9, 0, 0);
    }
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  return v2;
}

```

## disassembly

```asm
0x14004ef00  mov     [rsp+arg_0], rbx
0x14004ef05  mov     [rsp+arg_8], rsi
0x14004ef0a  push    rdi
0x14004ef0b  sub     rsp, 30h
0x14004ef0f  mov     r9, [rcx+38h]
0x14004ef13  xor     dil, dil
0x14004ef16  xorps   xmm0, xmm0
0x14004ef19  movups  [rsp+38h+var_18], xmm0
0x14004ef1e  cmp     [rcx+20h], dil
0x14004ef22  jnz     loc_14004EFE5
0x14004ef28  mov     rax, [rcx+288h]
0x14004ef2f  mov     rsi, [rax+28h]
0x14004ef33  xor     eax, eax
0x14004ef35  movzx   r10d, word ptr [r9+168h]
0x14004ef3d  add     rsi, 348h
0x14004ef44  movzx   r8d, r10w
0x14004ef48  shr     r8w, 1
0x14004ef4c  nop     dword ptr [rax+00h]
0x14004ef50  cmp     ax, r8w
0x14004ef54  jnb     short loc_14004EF70
0x14004ef56  mov     rcx, [r9+170h]
0x14004ef5d  movzx   edx, ax
0x14004ef60  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x14004ef65  jz      loc_14004EFEE
0x14004ef6b  inc     ax
0x14004ef6e  jmp     short loc_14004EF50
0x14004ef70  mov     word ptr [rsp+38h+var_18+2], r10w
0x14004ef76  mov     word ptr [rsp+38h+var_18], r10w
0x14004ef7c  mov     rax, [r9+170h]
0x14004ef83  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004ef8a  mov     qword ptr [rsp+38h+var_18+8], rax
0x14004ef8f  call    cs:__imp_ExAcquireFastMutex
0x14004ef96  nop     dword ptr [rax+rax+00h]
0x14004ef9b  xor     r9d, r9d
0x14004ef9e  lea     rdx, [rsp+38h+var_18]
0x14004efa3  xor     r8d, r8d
0x14004efa6  mov     rcx, rsi
0x14004efa9  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004efb0  nop     dword ptr [rax+rax+00h]
0x14004efb5  mov     rbx, rax
0x14004efb8  test    rax, rax
0x14004efbb  jnz     short loc_14004F000
0x14004efbd  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004efc4  call    cs:__imp_ExReleaseFastMutex
0x14004efcb  nop     dword ptr [rax+rax+00h]
0x14004efd0  mov     rbx, [rsp+38h+arg_0]
0x14004efd5  movzx   eax, dil
0x14004efd9  mov     rsi, [rsp+38h+arg_8]
0x14004efde  add     rsp, 30h
0x14004efe2  pop     rdi
0x14004efe3  retn
0x14004efe5  mov     rax, [r9+78h]
0x14004efe9  jmp     loc_14004EF2F
0x14004efee  add     ax, ax
0x14004eff1  mov     word ptr [rsp+38h+var_18+2], ax
0x14004eff6  mov     word ptr [rsp+38h+var_18], ax
0x14004effb  jmp     loc_14004EF7C
0x14004f000  mov     edx, [rax+20h]; MRxContext
0x14004f003  mov     rcx, rbx; NameCache
0x14004f006  call    cs:__imp_RxNameCacheCheckEntry
0x14004f00d  nop     dword ptr [rax+rax+00h]
0x14004f012  test    eax, eax
0x14004f014  jnz     short loc_14004F03C
0x14004f016  cmp     dword ptr [rbx+30h], 0C0000034h
0x14004f01d  jnz     short loc_14004F03C
0x14004f01f  xor     r9d, r9d; MRxContext
0x14004f022  xor     r8d, r8d; LifeTime
0x14004f025  mov     rdx, rbx; NameCache
0x14004f028  mov     rcx, rsi; NameCacheCtl
0x14004f02b  mov     dil, 1
0x14004f02e  call    cs:__imp_RxNameCacheActivateEntry
0x14004f035  nop     dword ptr [rax+rax+00h]
0x14004f03a  jmp     short loc_14004EFBD
0x14004f03c  mov     rdx, rbx; NameCache
0x14004f03f  mov     rcx, rsi; NameCacheCtl
0x14004f042  call    cs:__imp_RxNameCacheExpireEntry
0x14004f049  nop     dword ptr [rax+rax+00h]
0x14004f04e  jmp     loc_14004EFBD
```
