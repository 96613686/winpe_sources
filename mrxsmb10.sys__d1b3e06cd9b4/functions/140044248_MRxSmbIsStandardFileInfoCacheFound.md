# MRxSmbIsStandardFileInfoCacheFound

- ea: `0x140044248`
- end: `0x140044425`
- name: `MRxSmbIsStandardFileInfoCacheFound`
- size: `477`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140043f30`
- `0x140048b30`

## callees

- `0x140044248`
- `0x140044700`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140044400`
- `ntoskrnl!ExReleaseFastMutex` at `0x140044400`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400442be`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400442be`
- `rdbss!RxNameCacheExpireEntry` at `0x140044336`
- `rdbss!RxNameCacheExpireEntry` at `0x1400443ed`
- `rdbss!RxNameCacheExpireEntry` at `0x140044336`
- `rdbss!RxNameCacheExpireEntry` at `0x1400443ed`
- `rdbss!RxNameCacheActivateEntry` at `0x140044328`
- `rdbss!RxNameCacheActivateEntry` at `0x1400443d9`
- `rdbss!RxNameCacheActivateEntry` at `0x140044328`
- `rdbss!RxNameCacheActivateEntry` at `0x1400443d9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400442e9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004434e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400442e9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004434e`
- `rdbss!RxNameCacheCheckEntry` at `0x140044303`
- `rdbss!RxNameCacheCheckEntry` at `0x14004436c`
- `rdbss!RxNameCacheCheckEntry` at `0x140044303`
- `rdbss!RxNameCacheCheckEntry` at `0x14004436c`

## pseudocode

```c
char __fastcall MRxSmbIsStandardFileInfoCacheFound(__int64 a1, struct _LIST_ENTRY *a2, _DWORD *a3, __int64 a4)
{
  __int64 v4; // rax
  char v5; // r14
  int Blink; // r12d
  __int64 v7; // rbp
  __int64 v10; // rcx
  __int64 v11; // r13
  struct _NAME_CACHE_CONTROL_ *v12; // rdi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v14; // rbx
  struct _NAME_CACHE *v15; // rax
  struct _NAME_CACHE *v16; // rbx
  int v17; // eax
  struct _LIST_ENTRY *Flink; // rax
  _OWORD v20[4]; // [rsp+20h] [rbp-48h] BYREF
  char v21; // [rsp+70h] [rbp+8h]

  v4 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  Blink = 0;
  v21 = 0;
  v7 = a4;
  v20[0] = 0;
  if ( !a4 )
    v7 = v4 + 360;
  if ( *(_BYTE *)(a1 + 32) )
  {
    v10 = *(_QWORD *)(v4 + 120);
    v11 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL);
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 648);
    v11 = *(_QWORD *)(a1 + 72);
  }
  v12 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v10 + 40) + 472LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  if ( (unsigned __int8)MRxSmbIsStreamFile(v7, v20) )
  {
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v12, v20, 0, 0);
    v14 = Entry;
    if ( Entry )
    {
      if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) )
      {
        RxNameCacheExpireEntry(v12, v14);
      }
      else
      {
        Blink = (int)v14->Link.Blink;
        v21 = 1;
        RxNameCacheActivateEntry(v12, v14, 0, 0);
      }
    }
  }
  v15 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v12, v7, 0, 0);
  v16 = v15;
  if ( v15 )
  {
    if ( RxNameCacheCheckEntry(v15, v15->ExpireTime.LowPart) || v21 && *a3 != Blink )
    {
      RxNameCacheExpireEntry(v12, v16);
    }
    else
    {
      v17 = (int)v16->Link.Blink;
      ++v12->Spare[0];
      *a3 = v17;
      Flink = v16->Link.Flink;
      *a2 = *Flink;
      a2[1].Flink = Flink[1].Flink;
      if ( (*(_DWORD *)(v11 + 72) & 0x300000) == 0x200000 )
        a2->Blink = *(struct _LIST_ENTRY **)(*(_QWORD *)(a1 + 56) + 32LL);
      v5 = 1;
      RxNameCacheActivateEntry(v12, v16, 0, 0);
    }
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  return v5;
}

```

## disassembly

```asm
0x140044248  mov     [rsp+arg_8], rbx
0x14004424d  mov     [rsp+arg_10], r8
0x140044252  push    rbp
0x140044253  push    rsi
0x140044254  push    rdi
0x140044255  push    r12
0x140044257  push    r13
0x140044259  push    r14
0x14004425b  push    r15
0x14004425d  sub     rsp, 30h
0x140044261  mov     rax, [rcx+38h]
0x140044265  xor     r14b, r14b
0x140044268  xor     r12d, r12d
0x14004426b  mov     [rsp+68h+arg_0], r14b
0x140044270  xorps   xmm0, xmm0
0x140044273  mov     rbp, r9
0x140044276  mov     r15, rdx
0x140044279  mov     rsi, rcx
0x14004427c  movups  [rsp+68h+var_48], xmm0
0x140044281  test    r9, r9
0x140044284  jnz     short loc_14004428D
0x140044286  lea     rbp, [rax+168h]
0x14004428d  cmp     [rcx+20h], r12b
0x140044291  jnz     short loc_1400442A0
0x140044293  mov     rcx, [rcx+288h]
0x14004429a  mov     r13, [rsi+48h]
0x14004429e  jmp     short loc_1400442AC
0x1400442a0  mov     rcx, [rax+78h]
0x1400442a4  mov     rax, [rsi+40h]
0x1400442a8  mov     r13, [rax+20h]
0x1400442ac  mov     rdi, [rcx+28h]
0x1400442b0  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400442b7  add     rdi, 1D8h
0x1400442be  call    cs:__imp_ExAcquireFastMutex
0x1400442c5  nop     dword ptr [rax+rax+00h]
0x1400442ca  lea     rdx, [rsp+68h+var_48]
0x1400442cf  mov     rcx, rbp
0x1400442d2  call    MRxSmbIsStreamFile
0x1400442d7  test    al, al
0x1400442d9  jz      short loc_140044342
0x1400442db  xor     r9d, r9d
0x1400442de  lea     rdx, [rsp+68h+var_48]
0x1400442e3  xor     r8d, r8d
0x1400442e6  mov     rcx, rdi
0x1400442e9  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400442f0  nop     dword ptr [rax+rax+00h]
0x1400442f5  mov     rbx, rax
0x1400442f8  test    rax, rax
0x1400442fb  jz      short loc_140044342
0x1400442fd  mov     edx, [rax+20h]; MRxContext
0x140044300  mov     rcx, rax; NameCache
0x140044303  call    cs:__imp_RxNameCacheCheckEntry
0x14004430a  nop     dword ptr [rax+rax+00h]
0x14004430f  mov     rdx, rbx; NameCache
0x140044312  mov     rcx, rdi; NameCacheCtl
0x140044315  test    eax, eax
0x140044317  jnz     short loc_140044336
0x140044319  mov     r12d, [rbx+30h]
0x14004431d  xor     r9d, r9d; MRxContext
0x140044320  xor     r8d, r8d; LifeTime
0x140044323  mov     [rsp+68h+arg_0], 1
0x140044328  call    cs:__imp_RxNameCacheActivateEntry
0x14004432f  nop     dword ptr [rax+rax+00h]
0x140044334  jmp     short loc_140044342
0x140044336  call    cs:__imp_RxNameCacheExpireEntry
0x14004433d  nop     dword ptr [rax+rax+00h]
0x140044342  xor     r9d, r9d
0x140044345  xor     r8d, r8d
0x140044348  mov     rdx, rbp
0x14004434b  mov     rcx, rdi
0x14004434e  call    cs:__imp_RxNameCacheFetchEntryEx
0x140044355  nop     dword ptr [rax+rax+00h]
0x14004435a  mov     rbx, rax
0x14004435d  test    rax, rax
0x140044360  jz      loc_1400443F9
0x140044366  mov     edx, [rax+20h]; MRxContext
0x140044369  mov     rcx, rax; NameCache
0x14004436c  call    cs:__imp_RxNameCacheCheckEntry
0x140044373  nop     dword ptr [rax+rax+00h]
0x140044378  test    eax, eax
0x14004437a  jnz     short loc_1400443E7
0x14004437c  mov     rcx, [rsp+68h+arg_10]
0x140044384  cmp     [rsp+68h+arg_0], r14b
0x140044389  jz      short loc_140044390
0x14004438b  cmp     [rcx], r12d
0x14004438e  jnz     short loc_1400443E7
0x140044390  mov     eax, [rbx+30h]
0x140044393  inc     dword ptr [rdi+74h]
0x140044396  mov     [rcx], eax
0x140044398  mov     rax, [rbx+28h]
0x14004439c  movups  xmm0, xmmword ptr [rax]
0x14004439f  movups  xmmword ptr [r15], xmm0
0x1400443a3  movsd   xmm1, qword ptr [rax+10h]
0x1400443a8  movsd   qword ptr [r15+10h], xmm1
0x1400443ae  mov     eax, [r13+48h]
0x1400443b2  and     eax, 300000h
0x1400443b7  cmp     eax, 200000h
0x1400443bc  jnz     short loc_1400443CA
0x1400443be  mov     rax, [rsi+38h]
0x1400443c2  mov     rdx, [rax+20h]
0x1400443c6  mov     [r15+8], rdx
0x1400443ca  xor     r9d, r9d; MRxContext
0x1400443cd  xor     r8d, r8d; LifeTime
0x1400443d0  mov     rdx, rbx; NameCache
0x1400443d3  mov     rcx, rdi; NameCacheCtl
0x1400443d6  mov     r14b, 1
0x1400443d9  call    cs:__imp_RxNameCacheActivateEntry
0x1400443e0  nop     dword ptr [rax+rax+00h]
0x1400443e5  jmp     short loc_1400443F9
0x1400443e7  mov     rdx, rbx; NameCache
0x1400443ea  mov     rcx, rdi; NameCacheCtl
0x1400443ed  call    cs:__imp_RxNameCacheExpireEntry
0x1400443f4  nop     dword ptr [rax+rax+00h]
0x1400443f9  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140044400  call    cs:__imp_ExReleaseFastMutex
0x140044407  nop     dword ptr [rax+rax+00h]
0x14004440c  mov     rbx, [rsp+68h+arg_8]
0x140044411  mov     al, r14b
0x140044414  add     rsp, 30h
0x140044418  pop     r15
0x14004441a  pop     r14
0x14004441c  pop     r13
0x14004441e  pop     r12
0x140044420  pop     rdi
0x140044421  pop     rsi
0x140044422  pop     rbp
0x140044423  retn
```
