# MRxSmbCacheFileNotFound

- ea: `0x140043228`
- end: `0x140043362`
- name: `MRxSmbCacheFileNotFound`
- size: `314`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002b980`
- `0x140036d40`
- `0x14003a204`
- `0x14003a494`
- `0x14003b07c`
- `0x14003b4c8`
- `0x14003c3f8`
- `0x140048b30`
- `0x140052c00`

## callees

- `0x140043228`
- `0x140044700`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004334c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004334c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004328f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004328f`
- `rdbss!RxNameCacheActivateEntry` at `0x140043339`
- `rdbss!RxNameCacheActivateEntry` at `0x140043339`
- `rdbss!RxNameCacheCreateEntryEx` at `0x1400432f4`
- `rdbss!RxNameCacheCreateEntryEx` at `0x1400432f4`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400432a7`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400432a7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140043251`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400432d0`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004331d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140043251`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400432d0`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004331d`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x1400432bb`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140043308`

## pseudocode

```c
void __fastcall MRxSmbCacheFileNotFound(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  struct _NAME_CACHE_CONTROL_ *v5; // rdi
  __int64 Entry; // rax
  __int64 v7; // r9
  struct _NAME_CACHE *v8; // rbp
  ULONG v9; // ebx
  __int64 ConfigurationBlock; // rax
  struct _NAME_CACHE *v11; // rdx
  __int64 v12; // rax
  struct _NAME_CACHE *v13; // rsi

  v1 = *(_QWORD *)(a1 + 56);
  v3 = v1 + 360;
  if ( !(unsigned __int8)MRxSmbIsStreamFile(v1 + 360, 0) && *(_DWORD *)(MRxSmbGetConfigurationBlock() + 148) )
  {
    if ( *(_BYTE *)(a1 + 32) )
      v4 = *(_QWORD *)(v1 + 120);
    else
      v4 = *(_QWORD *)(a1 + 648);
    v5 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 40) + 840LL);
    ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
    Entry = RxNameCacheFetchEntryEx(v5, v3, 0, 0);
    v8 = (struct _NAME_CACHE *)Entry;
    if ( Entry )
    {
      *(_DWORD *)(Entry + 48) = -1073741772;
      v9 = *(_DWORD *)(MRxSmbLegacyPerfCtrs + 8LL);
      ConfigurationBlock = MRxSmbGetConfigurationBlock();
      v11 = v8;
    }
    else
    {
      if ( (*(_DWORD *)(v4 + 56) & 0x20) == 0 )
        goto LABEL_12;
      LOBYTE(v7) = 1;
      v12 = RxNameCacheCreateEntryEx(v5, v3, 0, v7);
      v13 = (struct _NAME_CACHE *)v12;
      if ( !v12 )
        goto LABEL_12;
      *(_DWORD *)(v12 + 48) = -1073741772;
      v9 = *(_DWORD *)(MRxSmbLegacyPerfCtrs + 8LL);
      ConfigurationBlock = MRxSmbGetConfigurationBlock();
      v11 = v13;
    }
    RxNameCacheActivateEntry(v5, v11, *(_DWORD *)(ConfigurationBlock + 148), v9);
LABEL_12:
    ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  }
}

```

## disassembly

```asm
0x140043228  push    rbx
0x14004322a  push    rbp
0x14004322b  push    rsi
0x14004322c  push    rdi
0x14004322d  sub     rsp, 28h
0x140043231  mov     rdi, [rcx+38h]
0x140043235  mov     rbx, rcx
0x140043238  xor     edx, edx
0x14004323a  lea     rsi, [rdi+168h]
0x140043241  mov     rcx, rsi
0x140043244  call    MRxSmbIsStreamFile
0x140043249  test    al, al
0x14004324b  jnz     loc_140043358
0x140043251  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140043258  nop     dword ptr [rax+rax+00h]
0x14004325d  cmp     dword ptr [rax+94h], 0
0x140043264  jz      loc_140043358
0x14004326a  cmp     byte ptr [rbx+20h], 0
0x14004326e  jnz     short loc_140043279
0x140043270  mov     rbx, [rbx+288h]
0x140043277  jmp     short loc_14004327D
0x140043279  mov     rbx, [rdi+78h]
0x14004327d  mov     rdi, [rbx+28h]
0x140043281  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043288  add     rdi, 348h
0x14004328f  call    cs:__imp_ExAcquireFastMutex
0x140043296  nop     dword ptr [rax+rax+00h]
0x14004329b  xor     r9d, r9d
0x14004329e  xor     r8d, r8d
0x1400432a1  mov     rdx, rsi
0x1400432a4  mov     rcx, rdi
0x1400432a7  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400432ae  nop     dword ptr [rax+rax+00h]
0x1400432b3  mov     rbp, rax
0x1400432b6  test    rax, rax
0x1400432b9  jz      short loc_1400432E1
0x1400432bb  mov     rdx, cs:__imp_MRxSmbLegacyPerfCtrs
0x1400432c2  mov     dword ptr [rax+30h], 0C0000034h
0x1400432c9  mov     r8, [rdx]
0x1400432cc  mov     ebx, [r8+8]
0x1400432d0  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400432d7  nop     dword ptr [rax+rax+00h]
0x1400432dc  mov     rdx, rbp
0x1400432df  jmp     short loc_14004332C
0x1400432e1  mov     eax, [rbx+38h]
0x1400432e4  test    al, 20h
0x1400432e6  jz      short loc_140043345
0x1400432e8  mov     r9b, 1
0x1400432eb  xor     r8d, r8d
0x1400432ee  mov     rdx, rsi
0x1400432f1  mov     rcx, rdi
0x1400432f4  call    cs:__imp_RxNameCacheCreateEntryEx
0x1400432fb  nop     dword ptr [rax+rax+00h]
0x140043300  mov     rsi, rax
0x140043303  test    rax, rax
0x140043306  jz      short loc_140043345
0x140043308  mov     rdx, cs:__imp_MRxSmbLegacyPerfCtrs
0x14004330f  mov     dword ptr [rax+30h], 0C0000034h
0x140043316  mov     r8, [rdx]
0x140043319  mov     ebx, [r8+8]
0x14004331d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140043324  nop     dword ptr [rax+rax+00h]
0x140043329  mov     rdx, rsi; NameCache
0x14004332c  mov     r8d, [rax+94h]; LifeTime
0x140043333  mov     r9d, ebx; MRxContext
0x140043336  mov     rcx, rdi; NameCacheCtl
0x140043339  call    cs:__imp_RxNameCacheActivateEntry
0x140043340  nop     dword ptr [rax+rax+00h]
0x140043345  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004334c  call    cs:__imp_ExReleaseFastMutex
0x140043353  nop     dword ptr [rax+rax+00h]
0x140043358  add     rsp, 28h
0x14004335c  pop     rdi
0x14004335d  pop     rsi
0x14004335e  pop     rbp
0x14004335f  pop     rbx
0x140043360  retn
```
