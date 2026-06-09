# MRxSmbInvalidateStandardFileInfoCache

- ea: `0x14004ac50`
- end: `0x14004ad7d`
- name: `MRxSmbInvalidateStandardFileInfoCache`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14004ab38`

## callees

- `0x14004ac50`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004acf9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004acf9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004ac8d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004ac8d`
- `rdbss!RxNameCacheExpireEntry` at `0x14004ad23`
- `rdbss!RxNameCacheExpireEntry` at `0x14004ad6c`
- `rdbss!RxNameCacheExpireEntry` at `0x14004ad23`
- `rdbss!RxNameCacheExpireEntry` at `0x14004ad6c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004aca5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004ad55`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004aca5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004ad55`

## pseudocode

```c
void __fastcall MRxSmbInvalidateStandardFileInfoCache(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // rax
  __int16 *v3; // rbx
  __int64 v4; // rax
  struct _NAME_CACHE_CONTROL_ *v5; // rdi
  struct _NAME_CACHE *Entry; // rax
  __int16 v7; // r9
  unsigned __int16 i; // ax
  struct _NAME_CACHE *v9; // rax
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_BYTE *)(a1 + 32) == 0;
  v2 = *(_QWORD *)(a1 + 56);
  v10 = 0;
  v3 = (__int16 *)(v2 + 360);
  if ( v1 )
    v4 = *(_QWORD *)(a1 + 648);
  else
    v4 = *(_QWORD *)(v2 + 120);
  v5 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 40) + 472LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, v3, 0, 0);
  if ( Entry )
    RxNameCacheExpireEntry(v5, Entry);
  v7 = *v3;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int16)((unsigned __int16)*v3 >> 1) )
    {
      WORD1(v10) = *v3;
      LOWORD(v10) = v7;
      *((_QWORD *)&v10 + 1) = *((_QWORD *)v3 + 1);
      goto LABEL_10;
    }
    if ( *(_WORD *)(*((_QWORD *)v3 + 1) + 2LL * i) == 58 )
      break;
  }
  WORD1(v10) = 2 * i;
  LOWORD(v10) = 2 * i;
  *((_QWORD *)&v10 + 1) = *((_QWORD *)v3 + 1);
  v9 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, &v10, 0, 0);
  if ( v9 )
    RxNameCacheExpireEntry(v5, v9);
LABEL_10:
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
}

```

## disassembly

```asm
0x14004ac50  mov     [rsp+arg_0], rbx
0x14004ac55  push    rdi
0x14004ac56  sub     rsp, 30h
0x14004ac5a  cmp     byte ptr [rcx+20h], 0
0x14004ac5e  xorps   xmm0, xmm0
0x14004ac61  mov     rax, [rcx+38h]
0x14004ac65  movups  [rsp+38h+var_18], xmm0
0x14004ac6a  lea     rbx, [rax+168h]
0x14004ac71  jz      loc_14004AD11
0x14004ac77  mov     rax, [rax+78h]
0x14004ac7b  mov     rdi, [rax+28h]
0x14004ac7f  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004ac86  add     rdi, 1D8h
0x14004ac8d  call    cs:__imp_ExAcquireFastMutex
0x14004ac94  nop     dword ptr [rax+rax+00h]
0x14004ac99  xor     r9d, r9d
0x14004ac9c  xor     r8d, r8d
0x14004ac9f  mov     rdx, rbx
0x14004aca2  mov     rcx, rdi
0x14004aca5  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004acac  nop     dword ptr [rax+rax+00h]
0x14004acb1  test    rax, rax
0x14004acb4  jnz     short loc_14004AD1D
0x14004acb6  movzx   r9d, word ptr [rbx]
0x14004acba  xor     eax, eax
0x14004acbc  movzx   r8d, r9w
0x14004acc0  shr     r8w, 1
0x14004acc4  cmp     ax, r8w
0x14004acc8  jnb     short loc_14004ACDD
0x14004acca  mov     rcx, [rbx+8]
0x14004acce  movzx   edx, ax
0x14004acd1  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x14004acd6  jz      short loc_14004AD31
0x14004acd8  inc     ax
0x14004acdb  jmp     short loc_14004ACC4
0x14004acdd  mov     word ptr [rsp+38h+var_18+2], r9w
0x14004ace3  mov     word ptr [rsp+38h+var_18], r9w
0x14004ace9  mov     rax, [rbx+8]
0x14004aced  mov     qword ptr [rsp+38h+var_18+8], rax
0x14004acf2  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004acf9  call    cs:__imp_ExReleaseFastMutex
0x14004ad00  nop     dword ptr [rax+rax+00h]
0x14004ad05  mov     rbx, [rsp+38h+arg_0]
0x14004ad0a  add     rsp, 30h
0x14004ad0e  pop     rdi
0x14004ad0f  retn
0x14004ad11  mov     rax, [rcx+288h]
0x14004ad18  jmp     loc_14004AC7B
0x14004ad1d  mov     rdx, rax; NameCache
0x14004ad20  mov     rcx, rdi; NameCacheCtl
0x14004ad23  call    cs:__imp_RxNameCacheExpireEntry
0x14004ad2a  nop     dword ptr [rax+rax+00h]
0x14004ad2f  jmp     short loc_14004ACB6
0x14004ad31  add     ax, ax
0x14004ad34  lea     rdx, [rsp+38h+var_18]
0x14004ad39  mov     word ptr [rsp+38h+var_18+2], ax
0x14004ad3e  xor     r9d, r9d
0x14004ad41  mov     word ptr [rsp+38h+var_18], ax
0x14004ad46  xor     r8d, r8d
0x14004ad49  mov     rax, [rbx+8]
0x14004ad4d  mov     rcx, rdi
0x14004ad50  mov     qword ptr [rsp+38h+var_18+8], rax
0x14004ad55  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004ad5c  nop     dword ptr [rax+rax+00h]
0x14004ad61  test    rax, rax
0x14004ad64  jz      short loc_14004ACF2
0x14004ad66  mov     rdx, rax; NameCache
0x14004ad69  mov     rcx, rdi; NameCacheCtl
0x14004ad6c  call    cs:__imp_RxNameCacheExpireEntry
0x14004ad73  nop     dword ptr [rax+rax+00h]
0x14004ad78  jmp     loc_14004ACF2
```
