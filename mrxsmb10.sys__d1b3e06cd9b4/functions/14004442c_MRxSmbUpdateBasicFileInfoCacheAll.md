# MRxSmbUpdateBasicFileInfoCacheAll

- ea: `0x14004442c`
- end: `0x140044561`
- name: `MRxSmbUpdateBasicFileInfoCacheAll`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002b980`
- `0x14003b4c8`

## callees

- `0x14004442c`
- `0x140044700`
- `0x14004b1b0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140044541`
- `ntoskrnl!ExReleaseFastMutex` at `0x140044541`
- `ntoskrnl!ExAcquireFastMutex` at `0x140044473`
- `ntoskrnl!ExAcquireFastMutex` at `0x140044473`
- `rdbss!RxNameCacheExpireEntry` at `0x14004452e`
- `rdbss!RxNameCacheExpireEntry` at `0x14004452e`
- `rdbss!RxNameCacheActivateEntry` at `0x1400444ec`
- `rdbss!RxNameCacheActivateEntry` at `0x1400444ec`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004448b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140044517`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004448b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140044517`

## pseudocode

```c
void __fastcall MRxSmbUpdateBasicFileInfoCacheAll(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v3; // rax
  __int64 v6; // rbp
  __int64 v7; // rax
  struct _NAME_CACHE_CONTROL_ *v8; // rsi
  __int64 Entry; // rax
  struct _NAME_CACHE *v10; // r10
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // eax
  struct _NAME_CACHE *v16; // rax
  _OWORD v17[3]; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(_BYTE *)(a1 + 32) == 0;
  v3 = *(_QWORD *)(a1 + 56);
  v17[0] = 0;
  v6 = v3 + 360;
  if ( v2 )
    v7 = *(_QWORD *)(a1 + 648);
  else
    v7 = *(_QWORD *)(v3 + 120);
  v8 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v7 + 40) + 288LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = RxNameCacheFetchEntryEx(v8, v6, 0, 0);
  v10 = (struct _NAME_CACHE *)Entry;
  if ( Entry )
  {
    v11 = *(_QWORD *)(Entry + 40);
    if ( *(_QWORD *)a2 )
      *(_QWORD *)v11 = *(_QWORD *)a2;
    v12 = *(_QWORD *)(a2 + 8);
    if ( v12 )
      *(_QWORD *)(v11 + 8) = v12;
    v13 = *(_QWORD *)(a2 + 16);
    if ( v13 )
      *(_QWORD *)(v11 + 16) = v13;
    v14 = *(_DWORD *)(a2 + 32) | *(_DWORD *)(v11 + 32) & 0x4E10;
    *(_DWORD *)(v11 + 32) = v14;
    v15 = v14 & 0xFFFFFF7F;
    if ( v15 )
      *(_DWORD *)(v11 + 32) = v15;
    RxNameCacheActivateEntry(v8, v10, 0, 0);
  }
  if ( (unsigned __int8)MRxSmbIsStreamFile(v6, v17) )
  {
    v16 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v8, v17, 0, 0);
    if ( v16 )
      RxNameCacheExpireEntry(v8, v16);
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  MRxSmbInvalidateFullDirectoryCacheParent(a1, 1);
}

```

## disassembly

```asm
0x14004442c  push    rbx
0x14004442e  push    rbp
0x14004442f  push    rsi
0x140044430  push    rdi
0x140044431  sub     rsp, 38h
0x140044435  cmp     byte ptr [rcx+20h], 0
0x140044439  xorps   xmm0, xmm0
0x14004443c  mov     rax, [rcx+38h]
0x140044440  mov     rdi, rdx
0x140044443  mov     rbx, rcx
0x140044446  movups  [rsp+58h+var_38], xmm0
0x14004444b  lea     rbp, [rax+168h]
0x140044452  jnz     short loc_14004445D
0x140044454  mov     rax, [rcx+288h]
0x14004445b  jmp     short loc_140044461
0x14004445d  mov     rax, [rax+78h]
0x140044461  mov     rsi, [rax+28h]
0x140044465  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004446c  add     rsi, 120h
0x140044473  call    cs:__imp_ExAcquireFastMutex
0x14004447a  nop     dword ptr [rax+rax+00h]
0x14004447f  xor     r9d, r9d
0x140044482  xor     r8d, r8d
0x140044485  mov     rdx, rbp
0x140044488  mov     rcx, rsi
0x14004448b  call    cs:__imp_RxNameCacheFetchEntryEx
0x140044492  nop     dword ptr [rax+rax+00h]
0x140044497  mov     r10, rax
0x14004449a  test    rax, rax
0x14004449d  jz      short loc_1400444F8
0x14004449f  mov     rcx, [rdi]
0x1400444a2  mov     rdx, [rax+28h]
0x1400444a6  test    rcx, rcx
0x1400444a9  jz      short loc_1400444AE
0x1400444ab  mov     [rdx], rcx
0x1400444ae  mov     rcx, [rdi+8]
0x1400444b2  test    rcx, rcx
0x1400444b5  jz      short loc_1400444BB
0x1400444b7  mov     [rdx+8], rcx
0x1400444bb  mov     rax, [rdi+10h]
0x1400444bf  test    rax, rax
0x1400444c2  jz      short loc_1400444C8
0x1400444c4  mov     [rdx+10h], rax
0x1400444c8  mov     eax, [rdx+20h]
0x1400444cb  and     eax, 4E10h
0x1400444d0  or      eax, [rdi+20h]
0x1400444d3  mov     [rdx+20h], eax
0x1400444d6  and     eax, 0FFFFFF7Fh
0x1400444db  jz      short loc_1400444E0
0x1400444dd  mov     [rdx+20h], eax
0x1400444e0  xor     r9d, r9d; MRxContext
0x1400444e3  xor     r8d, r8d; LifeTime
0x1400444e6  mov     rdx, r10; NameCache
0x1400444e9  mov     rcx, rsi; NameCacheCtl
0x1400444ec  call    cs:__imp_RxNameCacheActivateEntry
0x1400444f3  nop     dword ptr [rax+rax+00h]
0x1400444f8  lea     rdx, [rsp+58h+var_38]
0x1400444fd  mov     rcx, rbp
0x140044500  call    MRxSmbIsStreamFile
0x140044505  test    al, al
0x140044507  jz      short loc_14004453A
0x140044509  xor     r9d, r9d
0x14004450c  lea     rdx, [rsp+58h+var_38]
0x140044511  xor     r8d, r8d
0x140044514  mov     rcx, rsi
0x140044517  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004451e  nop     dword ptr [rax+rax+00h]
0x140044523  test    rax, rax
0x140044526  jz      short loc_14004453A
0x140044528  mov     rdx, rax; NameCache
0x14004452b  mov     rcx, rsi; NameCacheCtl
0x14004452e  call    cs:__imp_RxNameCacheExpireEntry
0x140044535  nop     dword ptr [rax+rax+00h]
0x14004453a  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140044541  call    cs:__imp_ExReleaseFastMutex
0x140044548  nop     dword ptr [rax+rax+00h]
0x14004454d  mov     dl, 1
0x14004454f  mov     rcx, rbx
0x140044552  call    MRxSmbInvalidateFullDirectoryCacheParent
0x140044557  add     rsp, 38h
0x14004455b  pop     rdi
0x14004455c  pop     rsi
0x14004455d  pop     rbp
0x14004455e  pop     rbx
0x14004455f  retn
```
