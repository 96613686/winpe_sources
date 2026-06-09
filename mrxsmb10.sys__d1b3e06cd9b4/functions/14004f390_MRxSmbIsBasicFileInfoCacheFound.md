# MRxSmbIsBasicFileInfoCacheFound

- ea: `0x14004f390`
- end: `0x14004f5ce`
- name: `MRxSmbIsBasicFileInfoCacheFound`
- size: `574`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140039ee0`
- `0x140043f30`
- `0x140048b30`

## callees

- `0x14004f390`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004f469`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004f469`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004f3f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004f3f2`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f529`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f5bd`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f529`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f5bd`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f510`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f5a6`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f510`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f5a6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004f44a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004f4c4`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004f44a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004f4c4`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f4de`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f548`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f4de`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f548`

## pseudocode

```c
__int64 __fastcall MRxSmbIsBasicFileInfoCacheFound(__int64 a1, struct _LIST_ENTRY *a2, _DWORD *a3, __int16 *a4)
{
  __int64 v4; // rax
  unsigned __int8 v5; // si
  char v6; // r12
  unsigned int v7; // r14d
  int Blink; // r13d
  __int16 *v9; // rbx
  _DWORD *v10; // rdi
  __int64 v12; // rax
  struct _NAME_CACHE_CONTROL_ *v13; // rbp
  __int16 v14; // r9
  unsigned __int16 i; // ax
  struct _NAME_CACHE *v16; // rax
  struct _NAME_CACHE *v17; // rbx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v20; // rdi
  int v21; // eax
  struct _LIST_ENTRY *Flink; // rax
  __int128 v23; // [rsp+20h] [rbp-58h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  v6 = 0;
  v7 = 0;
  Blink = 0;
  v9 = a4;
  v10 = a3;
  v23 = 0;
  if ( !a4 )
    v9 = (__int16 *)(v4 + 360);
  if ( *(_BYTE *)(a1 + 32) )
    v12 = *(_QWORD *)(v4 + 120);
  else
    v12 = *(_QWORD *)(a1 + 648);
  v13 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v12 + 40) + 288LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  v14 = *v9;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int16)((unsigned __int16)*v9 >> 1) )
    {
      WORD1(v23) = *v9;
      LOWORD(v23) = v14;
      *((_QWORD *)&v23 + 1) = *((_QWORD *)v9 + 1);
      goto LABEL_10;
    }
    if ( *(_WORD *)(*((_QWORD *)v9 + 1) + 2LL * i) == 58 )
      break;
  }
  WORD1(v23) = 2 * i;
  LOWORD(v23) = 2 * i;
  *((_QWORD *)&v23 + 1) = *((_QWORD *)v9 + 1);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v13, &v23, 0, 0);
  v20 = Entry;
  if ( !Entry )
    goto LABEL_16;
  if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) == RX_NC_SUCCESS )
  {
    Blink = (int)v20->Link.Blink;
    v6 = 1;
    v7 = (__int64)v20->Link.Flink[2].Flink & 0xFFFFF5EF;
    RxNameCacheActivateEntry(v13, v20, 0, 0);
LABEL_16:
    v10 = a3;
    goto LABEL_10;
  }
  RxNameCacheExpireEntry(v13, v20);
  v10 = a3;
LABEL_10:
  v16 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v13, v9, 0, 0);
  v17 = v16;
  if ( v16 )
  {
    if ( RxNameCacheCheckEntry(v16, v16->ExpireTime.LowPart)
      || v6 && (*v10 != Blink || ((__int64)a2[2].Flink & 0xFFFFF5EF) != v7) )
    {
      RxNameCacheExpireEntry(v13, v17);
    }
    else
    {
      v21 = (int)v17->Link.Blink;
      ++v13->Spare[0];
      *v10 = v21;
      Flink = v17->Link.Flink;
      v5 = 1;
      *a2 = *Flink;
      a2[1] = Flink[1];
      a2[2].Flink = Flink[2].Flink;
      RxNameCacheActivateEntry(v13, v17, 0, 0);
    }
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  return v5;
}

```

## disassembly

```asm
0x14004f390  mov     [rsp+arg_10], r8
0x14004f395  push    rbx
0x14004f396  push    rbp
0x14004f397  push    rsi
0x14004f398  push    rdi
0x14004f399  push    r12
0x14004f39b  push    r13
0x14004f39d  push    r14
0x14004f39f  push    r15
0x14004f3a1  sub     rsp, 38h
0x14004f3a5  mov     rax, [rcx+38h]
0x14004f3a9  xor     sil, sil
0x14004f3ac  xor     r12b, r12b
0x14004f3af  xor     r14d, r14d
0x14004f3b2  xor     r13d, r13d
0x14004f3b5  xorps   xmm0, xmm0
0x14004f3b8  mov     rbx, r9
0x14004f3bb  mov     rdi, r8
0x14004f3be  mov     r15, rdx
0x14004f3c1  movups  [rsp+78h+var_58], xmm0
0x14004f3c6  test    r9, r9
0x14004f3c9  jz      loc_14004F494
0x14004f3cf  cmp     [rcx+20h], sil
0x14004f3d3  jnz     loc_14004F48B
0x14004f3d9  mov     rax, [rcx+288h]
0x14004f3e0  mov     rbp, [rax+28h]
0x14004f3e4  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004f3eb  add     rbp, 120h
0x14004f3f2  call    cs:__imp_ExAcquireFastMutex
0x14004f3f9  nop     dword ptr [rax+rax+00h]
0x14004f3fe  movzx   r9d, word ptr [rbx]
0x14004f402  xor     eax, eax
0x14004f404  movzx   r8d, r9w
0x14004f408  shr     r8w, 1
0x14004f40c  nop     dword ptr [rax+00h]
0x14004f410  cmp     ax, r8w
0x14004f414  jnb     short loc_14004F429
0x14004f416  mov     rcx, [rbx+8]
0x14004f41a  movzx   edx, ax
0x14004f41d  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x14004f422  jz      short loc_14004F4A0
0x14004f424  inc     ax
0x14004f427  jmp     short loc_14004F410
0x14004f429  mov     word ptr [rsp+78h+var_58+2], r9w
0x14004f42f  mov     word ptr [rsp+78h+var_58], r9w
0x14004f435  mov     rax, [rbx+8]
0x14004f439  mov     qword ptr [rsp+78h+var_58+8], rax
0x14004f43e  xor     r9d, r9d
0x14004f441  xor     r8d, r8d
0x14004f444  mov     rdx, rbx
0x14004f447  mov     rcx, rbp
0x14004f44a  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004f451  nop     dword ptr [rax+rax+00h]
0x14004f456  mov     rbx, rax
0x14004f459  test    rax, rax
0x14004f45c  jnz     loc_14004F542
0x14004f462  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004f469  call    cs:__imp_ExReleaseFastMutex
0x14004f470  nop     dword ptr [rax+rax+00h]
0x14004f475  movzx   eax, sil
0x14004f479  add     rsp, 38h
0x14004f47d  pop     r15
0x14004f47f  pop     r14
0x14004f481  pop     r13
0x14004f483  pop     r12
0x14004f485  pop     rdi
0x14004f486  pop     rsi
0x14004f487  pop     rbp
0x14004f488  pop     rbx
0x14004f489  retn
0x14004f48b  mov     rax, [rax+78h]
0x14004f48f  jmp     loc_14004F3E0
0x14004f494  lea     rbx, [rax+168h]
0x14004f49b  jmp     loc_14004F3CF
0x14004f4a0  add     ax, ax
0x14004f4a3  lea     rdx, [rsp+78h+var_58]
0x14004f4a8  mov     word ptr [rsp+78h+var_58+2], ax
0x14004f4ad  xor     r9d, r9d
0x14004f4b0  mov     word ptr [rsp+78h+var_58], ax
0x14004f4b5  xor     r8d, r8d
0x14004f4b8  mov     rax, [rbx+8]
0x14004f4bc  mov     rcx, rbp
0x14004f4bf  mov     qword ptr [rsp+78h+var_58+8], rax
0x14004f4c4  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004f4cb  nop     dword ptr [rax+rax+00h]
0x14004f4d0  mov     rdi, rax
0x14004f4d3  test    rax, rax
0x14004f4d6  jz      short loc_14004F51C
0x14004f4d8  mov     edx, [rax+20h]; MRxContext
0x14004f4db  mov     rcx, rax; NameCache
0x14004f4de  call    cs:__imp_RxNameCacheCheckEntry
0x14004f4e5  nop     dword ptr [rax+rax+00h]
0x14004f4ea  mov     rdx, rdi; NameCache
0x14004f4ed  mov     rcx, rbp; NameCacheCtl
0x14004f4f0  test    eax, eax
0x14004f4f2  jnz     short loc_14004F529
0x14004f4f4  mov     rax, [rdi+28h]
0x14004f4f8  xor     r9d, r9d; MRxContext
0x14004f4fb  mov     r13d, [rdi+30h]
0x14004f4ff  xor     r8d, r8d; LifeTime
0x14004f502  mov     r12b, 1
0x14004f505  mov     r14d, [rax+20h]
0x14004f509  and     r14d, 0FFFFF5EFh
0x14004f510  call    cs:__imp_RxNameCacheActivateEntry
0x14004f517  nop     dword ptr [rax+rax+00h]
0x14004f51c  mov     rdi, [rsp+78h+arg_10]
0x14004f524  jmp     loc_14004F43E
0x14004f529  call    cs:__imp_RxNameCacheExpireEntry
0x14004f530  nop     dword ptr [rax+rax+00h]
0x14004f535  mov     rdi, [rsp+78h+arg_10]
0x14004f53d  jmp     loc_14004F43E
0x14004f542  mov     edx, [rax+20h]; MRxContext
0x14004f545  mov     rcx, rbx; NameCache
0x14004f548  call    cs:__imp_RxNameCacheCheckEntry
0x14004f54f  nop     dword ptr [rax+rax+00h]
0x14004f554  test    eax, eax
0x14004f556  jnz     short loc_14004F5B7
0x14004f558  test    r12b, r12b
0x14004f55b  jz      short loc_14004F570
0x14004f55d  cmp     [rdi], r13d
0x14004f560  jnz     short loc_14004F5B7
0x14004f562  mov     eax, [r15+20h]
0x14004f566  and     eax, 0FFFFF5EFh
0x14004f56b  cmp     eax, r14d
0x14004f56e  jnz     short loc_14004F5B7
0x14004f570  mov     eax, [rbx+30h]
0x14004f573  xor     r9d, r9d; MRxContext
0x14004f576  inc     dword ptr [rbp+74h]
0x14004f579  xor     r8d, r8d; LifeTime
0x14004f57c  mov     [rdi], eax
0x14004f57e  mov     rdx, rbx; NameCache
0x14004f581  mov     rax, [rbx+28h]
0x14004f585  mov     rcx, rbp; NameCacheCtl
0x14004f588  mov     sil, 1
0x14004f58b  movups  xmm0, xmmword ptr [rax]
0x14004f58e  movups  xmmword ptr [r15], xmm0
0x14004f592  movups  xmm1, xmmword ptr [rax+10h]
0x14004f596  movups  xmmword ptr [r15+10h], xmm1
0x14004f59b  movsd   xmm0, qword ptr [rax+20h]
0x14004f5a0  movsd   qword ptr [r15+20h], xmm0
0x14004f5a6  call    cs:__imp_RxNameCacheActivateEntry
0x14004f5ad  nop     dword ptr [rax+rax+00h]
0x14004f5b2  jmp     loc_14004F462
0x14004f5b7  mov     rdx, rbx; NameCache
0x14004f5ba  mov     rcx, rbp; NameCacheCtl
0x14004f5bd  call    cs:__imp_RxNameCacheExpireEntry
0x14004f5c4  nop     dword ptr [rax+rax+00h]
0x14004f5c9  jmp     loc_14004F462
```
