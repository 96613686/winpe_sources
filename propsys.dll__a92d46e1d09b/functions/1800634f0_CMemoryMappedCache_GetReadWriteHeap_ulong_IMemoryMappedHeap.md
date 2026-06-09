# CMemoryMappedCache::GetReadWriteHeap(ulong,IMemoryMappedHeap * *)

- ea: `0x1800634f0`
- end: `0x1800635e3`
- name: `?GetReadWriteHeap@CMemoryMappedCache@@UEAAJKPEAPEAUIMemoryMappedHeap@@@Z`
- size: `243`
- prototype: `int(CMemoryMappedCache *__hidden this, unsigned int, struct IMemoryMappedHeap **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180059e60`
- `0x1800634f0`
- `0x180066120`
- `0x18006f1fc`
- `0x1800a7954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800635ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800635ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063526`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063526`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800635bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800635bb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180063550`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180063550`

## pseudocode

```c
__int64 __fastcall CMemoryMappedCache::GetReadWriteHeap(void **this, unsigned int a2, struct IMemoryMappedHeap **a3)
{
  HRESULT v6; // esi
  struct _RTL_CRITICAL_SECTION *v7; // rbp
  HANDLE FileMappingW; // rax
  CSimpleHeapOnBytes *v9; // rax
  CSimpleHeapOnBytes *v10; // rbx

  *a3 = 0;
  v6 = -2147467259;
  if ( (*((_BYTE *)this + 12) & 2) != 0 )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)(this + 76);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 76));
    if ( this[9]
      || (FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 0, a2, 0),
          (this[9] = FileMappingW) != 0) )
    {
      v9 = (CSimpleHeapOnBytes *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
      v10 = v9;
      if ( v9 )
      {
        CSimpleHeapOnBytes::CSimpleHeapOnBytes(v9);
        *((_QWORD *)v10 + 10) = 0;
        *(_QWORD *)v10 = &CMemoryMappedHeap::`vftable';
        v6 = CMemoryMappedHeap::Initialize(v10, this[9], a2);
        if ( v6 >= 0 )
          v6 = QISearch(v10, &stru_1800BE6E8, &GUID_8f2b137c_34bb_490d_9cf8_c8c4e8184de6, (void **)a3);
        CSimpleHeapOnBytes::Release(v10);
      }
    }
    LeaveCriticalSection(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800634f0  push    rbx
0x1800634f2  push    rbp
0x1800634f3  push    rsi
0x1800634f4  push    rdi
0x1800634f5  push    r14
0x1800634f7  push    r15
0x1800634f9  sub     rsp, 38h
0x1800634fd  mov     qword ptr [r8], 0
0x180063504  mov     r14, r8
0x180063507  test    byte ptr [rcx+0Ch], 2
0x18006350b  mov     r15d, edx
0x18006350e  mov     rdi, rcx
0x180063511  mov     esi, 80004005h
0x180063516  jz      loc_1800635D4
0x18006351c  lea     rbp, [rcx+260h]
0x180063523  mov     rcx, rbp; lpCriticalSection
0x180063526  call    cs:__imp_EnterCriticalSection
0x18006352c  cmp     qword ptr [rdi+48h], 0
0x180063531  jnz     short loc_18006355F
0x180063533  mov     [rsp+68h+lpName], 0; lpName
0x18006353c  xor     r9d, r9d; dwMaximumSizeHigh
0x18006353f  xor     edx, edx; lpFileMappingAttributes
0x180063541  mov     [rsp+68h+dwMaximumSizeLow], r15d; dwMaximumSizeLow
0x180063546  mov     r8d, 4000004h; flProtect
0x18006354c  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180063550  call    cs:__imp_CreateFileMappingW
0x180063556  mov     [rdi+48h], rax
0x18006355a  test    rax, rax
0x18006355d  jz      short loc_1800635CB
0x18006355f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180063566  mov     ecx, 58h ; 'X'; unsigned __int64
0x18006356b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180063570  mov     rbx, rax
0x180063573  test    rax, rax
0x180063576  jz      short loc_1800635CB
0x180063578  mov     rcx, rax; this
0x18006357b  call    ??0CSimpleHeapOnBytes@@QEAA@XZ; CSimpleHeapOnBytes::CSimpleHeapOnBytes(void)
0x180063580  lea     rax, ??_7CMemoryMappedHeap@@6B@; const CMemoryMappedHeap::`vftable'
0x180063587  mov     qword ptr [rbx+50h], 0
0x18006358f  mov     [rbx], rax
0x180063592  mov     r8d, r15d; unsigned int
0x180063595  mov     rdx, [rdi+48h]; void *
0x180063599  mov     rcx, rbx; this
0x18006359c  call    ?Initialize@CMemoryMappedHeap@@QEAAJPEAXK@Z; CMemoryMappedHeap::Initialize(void *,ulong)
0x1800635a1  mov     esi, eax
0x1800635a3  test    eax, eax
0x1800635a5  js      short loc_1800635C3
0x1800635a7  mov     r9, r14; ppv
0x1800635aa  lea     r8, _GUID_8f2b137c_34bb_490d_9cf8_c8c4e8184de6; riid
0x1800635b1  lea     rdx, stru_1800BE6E8; pqit
0x1800635b8  mov     rcx, rbx; that
0x1800635bb  call    cs:__imp_QISearch
0x1800635c1  mov     esi, eax
0x1800635c3  mov     rcx, rbx; this
0x1800635c6  call    ?Release@CSimpleHeapOnBytes@@UEAAKXZ; CSimpleHeapOnBytes::Release(void)
0x1800635cb  mov     rcx, rbp; lpCriticalSection
0x1800635ce  call    cs:__imp_LeaveCriticalSection
0x1800635d4  mov     eax, esi
0x1800635d6  add     rsp, 38h
0x1800635da  pop     r15
0x1800635dc  pop     r14
0x1800635de  pop     rdi
0x1800635df  pop     rsi
0x1800635e0  pop     rbp
0x1800635e1  pop     rbx
0x1800635e2  retn
```
