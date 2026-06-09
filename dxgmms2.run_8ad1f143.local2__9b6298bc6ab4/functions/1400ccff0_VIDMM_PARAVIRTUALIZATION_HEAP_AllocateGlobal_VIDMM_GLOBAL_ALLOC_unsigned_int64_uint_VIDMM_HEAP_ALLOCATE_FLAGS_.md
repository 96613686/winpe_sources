# VIDMM_PARAVIRTUALIZATION_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400ccff0`
- end: `0x1400cd260`
- name: `?AllocateGlobal@VIDMM_PARAVIRTUALIZATION_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `624`
- prototype: `int __high(struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned int, enum VIDMM_HEAP_ALLOCATE_FLAGS, void *, enum VIDMM_PROCESS_HEAP_MAPPING, struct VIDMM_HEAP_ALLOC **, void **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140058760`
- `0x1400c1738`
- `0x1400ccff0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cd119`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cd119`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400cd097`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400cd097`
- `watchdog!WdLogSingleEntry0` at `0x1400cd0b1`
- `watchdog!WdLogSingleEntry0` at `0x1400cd130`
- `watchdog!WdLogSingleEntry0` at `0x1400cd0b1`
- `watchdog!WdLogSingleEntry0` at `0x1400cd130`
- `watchdog!WdLogSingleEntry1` at `0x1400cd178`
- `watchdog!WdLogSingleEntry1` at `0x1400cd20f`
- `watchdog!WdLogSingleEntry1` at `0x1400cd178`
- `watchdog!WdLogSingleEntry1` at `0x1400cd20f`

## pseudocode

```c
__int64 __fastcall VIDMM_PARAVIRTUALIZATION_HEAP::AllocateGlobal(
        VIDMM_PROCESS **a1,
        __int64 a2,
        SIZE_T a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        _QWORD *a9,
        _BYTE *a10)
{
  __int64 v13; // rax
  __int64 v14; // r14
  int v15; // edx
  PVOID MappedSystemVa; // rbp
  unsigned int v17; // r8d
  int v18; // ecx
  int v19; // eax
  PMDL PagesForMdl; // rax
  int v21; // ecx
  int v22; // r8d
  __int64 v23; // rax
  const wchar_t *v24; // r9
  __int64 v25; // rdi
  int v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v30; // ecx
  int v31; // r8d

  v13 = operator new(40, 1647470934, 256);
  v14 = v13;
  if ( !v13 )
  {
    _InterlockedIncrement(&dword_1400868A8);
    WdLogSingleEntry1(6, a2);
    WdLogGlobalForLineNumber = 479;
    DxgkLogInternalTriageEvent(
      v30,
      262145,
      v31,
      (unsigned int)L"Failed to allocate VIDMM_PARAVIRTUALIZATION_HEAP_ALLOC for global alloc 0x%.16x",
      a2,
      0,
      0,
      0);
    LODWORD(v25) = -1073741801;
    return (unsigned int)v25;
  }
  v15 = *(_DWORD *)(v13 + 32);
  MappedSystemVa = 0;
  *(_QWORD *)(v13 + 8) = a3;
  v17 = *(_DWORD *)(a2 + 28);
  v18 = v15 ^ ((unsigned __int8)v15 ^ (unsigned __int8)(v17 >> 4)) & 1;
  *(_DWORD *)(v13 + 32) = v18;
  v19 = v18 ^ ((unsigned __int8)v18 ^ (unsigned __int8)(*(_DWORD *)(a2 + 28) >> 5)) & 2;
  *(_DWORD *)(v14 + 32) = v19;
  if ( (v17 & 0x10) == 0 )
  {
    if ( (v19 & 2) == 0 )
    {
      LODWORD(v25) = -1073741822;
      goto LABEL_16;
    }
    goto LABEL_14;
  }
  PagesForMdl = MmAllocatePagesForMdlEx(
                  0,
                  (PHYSICAL_ADDRESS)-1LL,
                  0,
                  a3,
                  (MEMORY_CACHING_TYPE)(2 - ((**(_DWORD **)(a2 + 384) & 4) != 0)),
                  4u);
  *(_QWORD *)v14 = PagesForMdl;
  if ( PagesForMdl )
  {
    if ( (PagesForMdl->MdlFlags & 5) != 0 )
      MappedSystemVa = PagesForMdl->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(PagesForMdl, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
    {
      WdLogSingleEntry0(1);
      v23 = 507;
      v24 = L"Failed to get system view for backing store";
      goto LABEL_5;
    }
    v26 = VIDMM_PROCESS::MapHostAddressesToGuest(
            a1[1],
            *(struct _MDL **)v14,
            a3,
            (void **)(v14 + 16),
            (unsigned __int64 *)(v14 + 24));
    v25 = v26;
    if ( v26 < 0 )
    {
      WdLogSingleEntry1(1, v26);
      WdLogGlobalForLineNumber = 519;
      DxgkLogInternalTriageEvent(v27, 0x40000, v28, (unsigned int)L"Failed to map HPA to GPA: 0x%I64x", v25, 0, 0, 0);
      goto LABEL_16;
    }
LABEL_14:
    *a8 = v14;
    *a9 = MappedSystemVa;
    *a10 = 1;
    return 0;
  }
  WdLogSingleEntry0(1);
  v23 = 499;
  v24 = L"Failed to allocate pages for the backing store";
LABEL_5:
  WdLogGlobalForLineNumber = v23;
  DxgkLogInternalTriageEvent(v21, 0x40000, v22, (_DWORD)v24, v23, 0, 0, 0);
  LODWORD(v25) = -1073741801;
LABEL_16:
  (*((void (__fastcall **)(VIDMM_PROCESS **, __int64, PVOID, _QWORD))*a1 + 17))(a1, v14, MappedSystemVa, 0);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1400ccff0  push    rbx
0x1400ccff2  push    rbp
0x1400ccff3  push    rdi
0x1400ccff4  push    r12
0x1400ccff6  push    r14
0x1400ccff8  push    r15
0x1400ccffa  sub     rsp, 58h
0x1400ccffe  mov     rdi, r8
0x1400cd001  mov     rbx, rdx
0x1400cd004  mov     r15, rcx
0x1400cd007  mov     edx, 62326956h
0x1400cd00c  mov     ecx, 28h ; '('
0x1400cd011  mov     r8d, 100h
0x1400cd017  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400cd01c  xor     r12d, r12d
0x1400cd01f  mov     r14, rax
0x1400cd022  test    rax, rax
0x1400cd025  jz      loc_1400CD200
0x1400cd02b  mov     edx, [rax+20h]
0x1400cd02e  mov     ebp, r12d
0x1400cd031  mov     [rax+8], rdi
0x1400cd035  mov     r8d, [rbx+1Ch]
0x1400cd039  mov     ecx, r8d
0x1400cd03c  shr     ecx, 4
0x1400cd03f  xor     ecx, edx
0x1400cd041  and     ecx, 1
0x1400cd044  xor     ecx, edx
0x1400cd046  mov     [rax+20h], ecx
0x1400cd049  mov     eax, [rbx+1Ch]
0x1400cd04c  shr     eax, 5
0x1400cd04f  xor     eax, ecx
0x1400cd051  and     eax, 2
0x1400cd054  xor     eax, ecx
0x1400cd056  mov     [r14+20h], eax
0x1400cd05a  test    r8b, 10h
0x1400cd05e  jz      loc_1400CD1B5
0x1400cd064  mov     rax, [rbx+180h]
0x1400cd06b  mov     r9, rdi; TotalBytes
0x1400cd06e  mov     rdx, qword ptr cs:HighAddress; HighAddress
0x1400cd075  mov     [rsp+88h+Flags], 4; Flags
0x1400cd07d  mov     ecx, [rax]
0x1400cd07f  and     cl, 4
0x1400cd082  neg     cl
0x1400cd084  mov     rcx, qword ptr cs:LowAddress; LowAddress
0x1400cd08b  sbb     eax, eax
0x1400cd08d  mov     r8, rcx; SkipBytes
0x1400cd090  add     eax, 2
0x1400cd093  mov     [rsp+88h+CacheType], eax; CacheType
0x1400cd097  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400cd09e  nop     dword ptr [rax+rax+00h]
0x1400cd0a3  mov     [r14], rax
0x1400cd0a6  mov     rcx, rax; MemoryDescriptorList
0x1400cd0a9  test    rax, rax
0x1400cd0ac  jnz     short loc_1400CD0F7
0x1400cd0ae  lea     ecx, [rax+1]
0x1400cd0b1  call    cs:__imp_WdLogSingleEntry0
0x1400cd0b8  nop     dword ptr [rax+rax+00h]
0x1400cd0bd  mov     eax, 1F3h
0x1400cd0c2  lea     r9, aFailedToAlloca_20; "Failed to allocate pages for the backin"...
0x1400cd0c9  mov     [rsp+88h+var_50], r12
0x1400cd0ce  mov     edx, 40000h
0x1400cd0d3  mov     [rsp+88h+var_58], r12
0x1400cd0d8  mov     qword ptr [rsp+88h+Flags], r12
0x1400cd0dd  mov     qword ptr [rsp+88h+CacheType], rax
0x1400cd0e2  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cd0e8  call    DxgkLogInternalTriageEvent
0x1400cd0ed  mov     edi, 0C0000017h
0x1400cd0f2  jmp     loc_1400CD1E3
0x1400cd0f7  test    byte ptr [rax+0Ah], 5
0x1400cd0fb  jz      short loc_1400CD103
0x1400cd0fd  mov     rbp, [rax+18h]
0x1400cd101  jmp     short loc_1400CD128
0x1400cd103  xor     r9d, r9d; RequestedAddress
0x1400cd106  mov     [rsp+88h+Flags], 40000010h; Priority
0x1400cd10e  xor     edx, edx; AccessMode
0x1400cd110  mov     [rsp+88h+CacheType], r12d; BugCheckOnFailure
0x1400cd115  lea     r8d, [r9+1]; CacheType
0x1400cd119  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400cd120  nop     dword ptr [rax+rax+00h]
0x1400cd125  mov     rbp, rax
0x1400cd128  test    rbp, rbp
0x1400cd12b  jnz     short loc_1400CD14D
0x1400cd12d  lea     ecx, [rbp+1]
0x1400cd130  call    cs:__imp_WdLogSingleEntry0
0x1400cd137  nop     dword ptr [rax+rax+00h]
0x1400cd13c  mov     eax, 1FBh
0x1400cd141  lea     r9, aFailedToGetSys_0; "Failed to get system view for backing s"...
0x1400cd148  jmp     loc_1400CD0C9
0x1400cd14d  mov     rdx, [r14]; struct _MDL *
0x1400cd150  lea     r9, [r14+10h]; void **
0x1400cd154  mov     rcx, [r15+8]; this
0x1400cd158  lea     rax, [r9+8]
0x1400cd15c  mov     r8, rdi; unsigned __int64
0x1400cd15f  mov     qword ptr [rsp+88h+CacheType], rax; unsigned __int64 *
0x1400cd164  call    ?MapHostAddressesToGuest@VIDMM_PROCESS@@QEAAJPEAU_MDL@@_KPEAPEAXPEA_K@Z; VIDMM_PROCESS::MapHostAddressesToGuest(_MDL *,unsigned __int64,void * *,unsigned __int64 *)
0x1400cd169  movsxd  rdi, eax
0x1400cd16c  test    eax, eax
0x1400cd16e  jns     short loc_1400CD1B9
0x1400cd170  mov     rdx, rdi
0x1400cd173  mov     ecx, 1
0x1400cd178  call    cs:__imp_WdLogSingleEntry1
0x1400cd17f  nop     dword ptr [rax+rax+00h]
0x1400cd184  mov     [rsp+88h+var_50], r12
0x1400cd189  lea     r9, aFailedToMapHpa; "Failed to map HPA to GPA: 0x%I64x"
0x1400cd190  mov     [rsp+88h+var_58], r12
0x1400cd195  mov     edx, 40000h
0x1400cd19a  mov     qword ptr [rsp+88h+Flags], r12
0x1400cd19f  mov     qword ptr [rsp+88h+CacheType], rdi
0x1400cd1a4  mov     cs:WdLogGlobalForLineNumber, 207h
0x1400cd1ae  call    DxgkLogInternalTriageEvent
0x1400cd1b3  jmp     short loc_1400CD1E3
0x1400cd1b5  test    al, 2
0x1400cd1b7  jz      short loc_1400CD1DE
0x1400cd1b9  mov     rax, [rsp+88h+arg_38]
0x1400cd1c1  mov     [rax], r14
0x1400cd1c4  mov     rax, [rsp+88h+arg_40]
0x1400cd1cc  mov     [rax], rbp
0x1400cd1cf  mov     rax, [rsp+88h+arg_48]
0x1400cd1d7  mov     byte ptr [rax], 1
0x1400cd1da  xor     eax, eax
0x1400cd1dc  jmp     short loc_1400CD251
0x1400cd1de  mov     edi, 0C0000002h
0x1400cd1e3  mov     rax, [r15]
0x1400cd1e6  xor     r9d, r9d
0x1400cd1e9  mov     r8, rbp
0x1400cd1ec  mov     rdx, r14
0x1400cd1ef  mov     rcx, r15
0x1400cd1f2  mov     rax, [rax+88h]
0x1400cd1f9  call    _guard_dispatch_icall
0x1400cd1fe  jmp     short loc_1400CD24F
0x1400cd200  lock inc cs:dword_1400868A8
0x1400cd207  mov     rdx, rbx
0x1400cd20a  mov     ecx, 6
0x1400cd20f  call    cs:__imp_WdLogSingleEntry1
0x1400cd216  nop     dword ptr [rax+rax+00h]
0x1400cd21b  mov     [rsp+88h+var_50], r12
0x1400cd220  lea     r9, aFailedToAlloca_69; "Failed to allocate VIDMM_PARAVIRTUALIZA"...
0x1400cd227  mov     [rsp+88h+var_58], r12
0x1400cd22c  mov     edx, 40001h
0x1400cd231  mov     qword ptr [rsp+88h+Flags], r12
0x1400cd236  mov     qword ptr [rsp+88h+CacheType], rbx
0x1400cd23b  mov     cs:WdLogGlobalForLineNumber, 1DFh
0x1400cd245  call    DxgkLogInternalTriageEvent
0x1400cd24a  mov     edi, 0C0000017h
0x1400cd24f  mov     eax, edi
0x1400cd251  add     rsp, 58h
0x1400cd255  pop     r15
0x1400cd257  pop     r14
0x1400cd259  pop     r12
0x1400cd25b  pop     rdi
0x1400cd25c  pop     rbp
0x1400cd25d  pop     rbx
0x1400cd25e  retn
```
