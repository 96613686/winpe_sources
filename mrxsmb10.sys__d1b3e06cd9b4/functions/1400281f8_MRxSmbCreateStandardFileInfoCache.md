# MRxSmbCreateStandardFileInfoCache

- ea: `0x1400281f8`
- end: `0x14002830a`
- name: `MRxSmbCreateStandardFileInfoCache`
- size: `274`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140048b30`
- `0x1400499e0`
- `0x14004a750`

## callees

- `0x1400281f8`
- `0x14004a930`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400282f0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400282f0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002824e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002824e`
- `rdbss!RxNameCacheActivateEntry` at `0x1400282dd`
- `rdbss!RxNameCacheActivateEntry` at `0x1400282dd`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140028286`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140028286`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140028266`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140028266`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400282c1`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400282c1`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x1400282b0`

## pseudocode

```c
void __fastcall MRxSmbCreateStandardFileInfoCache(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  __int64 v8; // rsi
  __int64 v9; // rax
  struct _NAME_CACHE_CONTROL_ *v10; // rbp
  __int64 Entry; // rdi
  __int64 v12; // r9
  __int64 v13; // rax
  ULONG v14; // ebx
  __int64 ConfigurationBlock; // rax

  v4 = *(_QWORD *)(a1 + 56);
  if ( (unsigned __int8)MRxSmbCacheInfo(a1, a3) )
  {
    v8 = v4 + 360;
    if ( *(_BYTE *)(a1 + 32) )
      v9 = *(_QWORD *)(v4 + 120);
    else
      v9 = *(_QWORD *)(a1 + 648);
    v10 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v9 + 40) + 472LL);
    ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
    Entry = RxNameCacheFetchEntryEx(v10, v4 + 360, 0, 0);
    if ( Entry || (LOBYTE(v12) = 1, (Entry = RxNameCacheCreateEntryEx(v10, v8, 0, v12)) != 0) )
    {
      v13 = *(_QWORD *)(Entry + 40);
      *(_OWORD *)v13 = *(_OWORD *)a2;
      *(_QWORD *)(v13 + 16) = *(_QWORD *)(a2 + 16);
      *(_DWORD *)(Entry + 48) = a4;
      v14 = *(_DWORD *)(MRxSmbLegacyPerfCtrs + 8LL);
      ConfigurationBlock = MRxSmbGetConfigurationBlock();
      RxNameCacheActivateEntry(v10, (PNAME_CACHE)Entry, *(_DWORD *)(ConfigurationBlock + 144), v14);
    }
    ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  }
}

```

## disassembly

```asm
0x1400281f8  push    rbx
0x1400281fa  push    rbp
0x1400281fb  push    rsi
0x1400281fc  push    rdi
0x1400281fd  push    r14
0x1400281ff  push    r15
0x140028201  sub     rsp, 28h
0x140028205  mov     rdi, [rcx+38h]
0x140028209  mov     r14, rdx
0x14002820c  mov     rdx, r8
0x14002820f  mov     r15d, r9d
0x140028212  mov     rbx, rcx
0x140028215  call    MRxSmbCacheInfo
0x14002821a  test    al, al
0x14002821c  jz      loc_1400282FC
0x140028222  cmp     byte ptr [rbx+20h], 0
0x140028226  lea     rsi, [rdi+168h]
0x14002822d  jnz     short loc_140028238
0x14002822f  mov     rax, [rbx+288h]
0x140028236  jmp     short loc_14002823C
0x140028238  mov     rax, [rdi+78h]
0x14002823c  mov     rbp, [rax+28h]
0x140028240  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140028247  add     rbp, 1D8h
0x14002824e  call    cs:__imp_ExAcquireFastMutex
0x140028255  nop     dword ptr [rax+rax+00h]
0x14002825a  xor     r9d, r9d
0x14002825d  xor     r8d, r8d
0x140028260  mov     rdx, rsi
0x140028263  mov     rcx, rbp
0x140028266  call    cs:__imp_RxNameCacheFetchEntryEx
0x14002826d  nop     dword ptr [rax+rax+00h]
0x140028272  mov     rdi, rax
0x140028275  test    rax, rax
0x140028278  jnz     short loc_14002829A
0x14002827a  mov     r9b, 1
0x14002827d  xor     r8d, r8d
0x140028280  mov     rdx, rsi
0x140028283  mov     rcx, rbp
0x140028286  call    cs:__imp_RxNameCacheCreateEntryEx
0x14002828d  nop     dword ptr [rax+rax+00h]
0x140028292  mov     rdi, rax
0x140028295  test    rax, rax
0x140028298  jz      short loc_1400282E9
0x14002829a  mov     rax, [rdi+28h]
0x14002829e  movups  xmm0, xmmword ptr [r14]
0x1400282a2  movups  xmmword ptr [rax], xmm0
0x1400282a5  movsd   xmm1, qword ptr [r14+10h]
0x1400282ab  movsd   qword ptr [rax+10h], xmm1
0x1400282b0  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x1400282b7  mov     [rdi+30h], r15d
0x1400282bb  mov     rdx, [rax]
0x1400282be  mov     ebx, [rdx+8]
0x1400282c1  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400282c8  nop     dword ptr [rax+rax+00h]
0x1400282cd  mov     r9d, ebx; MRxContext
0x1400282d0  mov     rdx, rdi; NameCache
0x1400282d3  mov     rcx, rbp; NameCacheCtl
0x1400282d6  mov     r8d, [rax+90h]; LifeTime
0x1400282dd  call    cs:__imp_RxNameCacheActivateEntry
0x1400282e4  nop     dword ptr [rax+rax+00h]
0x1400282e9  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400282f0  call    cs:__imp_ExReleaseFastMutex
0x1400282f7  nop     dword ptr [rax+rax+00h]
0x1400282fc  add     rsp, 28h
0x140028300  pop     r15
0x140028302  pop     r14
0x140028304  pop     rdi
0x140028305  pop     rsi
0x140028306  pop     rbp
0x140028307  pop     rbx
0x140028308  retn
```
