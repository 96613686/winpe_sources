# MRxSmbUpdateStandardFileInfoCache

- ea: `0x140044624`
- end: `0x1400446ef`
- name: `MRxSmbUpdateStandardFileInfoCache`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002b980`
- `0x14003b4c8`

## callees

- `0x140044624`
- `0x14004b1b0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400446cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400446cd`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004465a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004465a`
- `rdbss!RxNameCacheActivateEntry` at `0x1400446ba`
- `rdbss!RxNameCacheActivateEntry` at `0x1400446ba`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004467a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004467a`

## pseudocode

```c
void __fastcall MRxSmbUpdateStandardFileInfoCache(__int64 a1, struct _LIST_ENTRY *a2, char a3)
{
  __int64 v4; // rsi
  __int64 v7; // rax
  __int64 v8; // r14
  struct _NAME_CACHE *Entry; // rax
  struct _LIST_ENTRY *Flink; // rcx

  v4 = *(_QWORD *)(a1 + 56);
  if ( *(_BYTE *)(a1 + 32) )
    v7 = *(_QWORD *)(v4 + 120);
  else
    v7 = *(_QWORD *)(a1 + 648);
  v8 = *(_QWORD *)(v7 + 40);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v8 + 472, v4 + 360, 0, 0);
  if ( Entry )
  {
    Flink = Entry->Link.Flink;
    if ( a2 )
    {
      *Flink = *a2;
      Flink[1].Flink = a2[1].Flink;
    }
    else
    {
      BYTE5(Flink[1].Flink) = a3;
    }
    RxNameCacheActivateEntry((PNAME_CACHE_CONTROL)(v8 + 472), Entry, 0, 0);
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  MRxSmbInvalidateFullDirectoryCacheParent(a1, 1);
}

```

## disassembly

```asm
0x140044624  push    rbx
0x140044626  push    rbp
0x140044627  push    rsi
0x140044628  push    rdi
0x140044629  push    r14
0x14004462b  sub     rsp, 20h
0x14004462f  cmp     byte ptr [rcx+20h], 0
0x140044633  mov     bpl, r8b
0x140044636  mov     rsi, [rcx+38h]
0x14004463a  mov     rdi, rdx
0x14004463d  mov     rbx, rcx
0x140044640  jnz     short loc_14004464B
0x140044642  mov     rax, [rcx+288h]
0x140044649  jmp     short loc_14004464F
0x14004464b  mov     rax, [rsi+78h]
0x14004464f  mov     r14, [rax+28h]
0x140044653  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004465a  call    cs:__imp_ExAcquireFastMutex
0x140044661  nop     dword ptr [rax+rax+00h]
0x140044666  lea     rdx, [rsi+168h]
0x14004466d  xor     r9d, r9d
0x140044670  xor     r8d, r8d
0x140044673  lea     rcx, [r14+1D8h]
0x14004467a  call    cs:__imp_RxNameCacheFetchEntryEx
0x140044681  nop     dword ptr [rax+rax+00h]
0x140044686  test    rax, rax
0x140044689  jz      short loc_1400446C6
0x14004468b  mov     rcx, [rax+28h]
0x14004468f  test    rdi, rdi
0x140044692  jz      short loc_1400446A6
0x140044694  movups  xmm0, xmmword ptr [rdi]
0x140044697  movups  xmmword ptr [rcx], xmm0
0x14004469a  movsd   xmm1, qword ptr [rdi+10h]
0x14004469f  movsd   qword ptr [rcx+10h], xmm1
0x1400446a4  jmp     short loc_1400446AA
0x1400446a6  mov     [rcx+15h], bpl
0x1400446aa  xor     r9d, r9d; MRxContext
0x1400446ad  lea     rcx, [r14+1D8h]; NameCacheCtl
0x1400446b4  xor     r8d, r8d; LifeTime
0x1400446b7  mov     rdx, rax; NameCache
0x1400446ba  call    cs:__imp_RxNameCacheActivateEntry
0x1400446c1  nop     dword ptr [rax+rax+00h]
0x1400446c6  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400446cd  call    cs:__imp_ExReleaseFastMutex
0x1400446d4  nop     dword ptr [rax+rax+00h]
0x1400446d9  mov     dl, 1
0x1400446db  mov     rcx, rbx
0x1400446de  call    MRxSmbInvalidateFullDirectoryCacheParent
0x1400446e3  add     rsp, 20h
0x1400446e7  pop     r14
0x1400446e9  pop     rdi
0x1400446ea  pop     rsi
0x1400446eb  pop     rbp
0x1400446ec  pop     rbx
0x1400446ed  retn
```
