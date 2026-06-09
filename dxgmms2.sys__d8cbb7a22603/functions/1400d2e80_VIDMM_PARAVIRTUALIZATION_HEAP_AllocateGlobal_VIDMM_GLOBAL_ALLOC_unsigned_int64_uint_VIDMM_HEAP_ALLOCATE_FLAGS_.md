# VIDMM_PARAVIRTUALIZATION_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400d2e80`
- end: `0x1400d30f0`
- name: `?AllocateGlobal@VIDMM_PARAVIRTUALIZATION_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `624`
- prototype: `__int64 __fastcall(VIDMM_PROCESS **, __int64, SIZE_T, __int64, __int64, __int64, __int64, __int64 *, _QWORD *, _BYTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140003490`
- `0x140004268`
- `0x140059030`
- `0x1400c58e4`
- `0x1400d2e80`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d2fa9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d2fa9`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400d2f27`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400d2f27`
- `watchdog!WdLogSingleEntry0` at `0x1400d2f41`
- `watchdog!WdLogSingleEntry0` at `0x1400d2fc0`
- `watchdog!WdLogSingleEntry0` at `0x1400d2f41`
- `watchdog!WdLogSingleEntry0` at `0x1400d2fc0`
- `watchdog!WdLogSingleEntry1` at `0x1400d3008`
- `watchdog!WdLogSingleEntry1` at `0x1400d309f`
- `watchdog!WdLogSingleEntry1` at `0x1400d3008`
- `watchdog!WdLogSingleEntry1` at `0x1400d309f`

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
    _InterlockedIncrement(&dword_140087888);
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
                  (MEMORY_CACHING_TYPE)(2 - ((**(_DWORD **)(a2 + 392) & 4) != 0)),
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
0x1400d2e80  push    rbx
0x1400d2e82  push    rbp
0x1400d2e83  push    rdi
0x1400d2e84  push    r12
0x1400d2e86  push    r14
0x1400d2e88  push    r15
0x1400d2e8a  sub     rsp, 58h
0x1400d2e8e  mov     rdi, r8
0x1400d2e91  mov     rbx, rdx
0x1400d2e94  mov     r15, rcx
0x1400d2e97  mov     edx, 62326956h
0x1400d2e9c  mov     ecx, 28h ; '('
0x1400d2ea1  mov     r8d, 100h
0x1400d2ea7  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400d2eac  xor     r12d, r12d
0x1400d2eaf  mov     r14, rax
0x1400d2eb2  test    rax, rax
0x1400d2eb5  jz      loc_1400D3090
0x1400d2ebb  mov     edx, [rax+20h]
0x1400d2ebe  mov     ebp, r12d
0x1400d2ec1  mov     [rax+8], rdi
0x1400d2ec5  mov     r8d, [rbx+1Ch]
0x1400d2ec9  mov     ecx, r8d
0x1400d2ecc  shr     ecx, 4
0x1400d2ecf  xor     ecx, edx
0x1400d2ed1  and     ecx, 1
0x1400d2ed4  xor     ecx, edx
0x1400d2ed6  mov     [rax+20h], ecx
0x1400d2ed9  mov     eax, [rbx+1Ch]
0x1400d2edc  shr     eax, 5
0x1400d2edf  xor     eax, ecx
0x1400d2ee1  and     eax, 2
0x1400d2ee4  xor     eax, ecx
0x1400d2ee6  mov     [r14+20h], eax
0x1400d2eea  test    r8b, 10h
0x1400d2eee  jz      loc_1400D3045
0x1400d2ef4  mov     rax, [rbx+188h]
0x1400d2efb  mov     r9, rdi; TotalBytes
0x1400d2efe  mov     rdx, qword ptr cs:HighAddress; HighAddress
0x1400d2f05  mov     [rsp+88h+Flags], 4; Flags
0x1400d2f0d  mov     ecx, [rax]
0x1400d2f0f  and     cl, 4
0x1400d2f12  neg     cl
0x1400d2f14  mov     rcx, qword ptr cs:LowAddress; LowAddress
0x1400d2f1b  sbb     eax, eax
0x1400d2f1d  mov     r8, rcx; SkipBytes
0x1400d2f20  add     eax, 2
0x1400d2f23  mov     [rsp+88h+CacheType], eax; CacheType
0x1400d2f27  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400d2f2e  nop     dword ptr [rax+rax+00h]
0x1400d2f33  mov     [r14], rax
0x1400d2f36  mov     rcx, rax; MemoryDescriptorList
0x1400d2f39  test    rax, rax
0x1400d2f3c  jnz     short loc_1400D2F87
0x1400d2f3e  lea     ecx, [rax+1]
0x1400d2f41  call    cs:__imp_WdLogSingleEntry0
0x1400d2f48  nop     dword ptr [rax+rax+00h]
0x1400d2f4d  mov     eax, 1F3h
0x1400d2f52  lea     r9, aFailedToAlloca_23; "Failed to allocate pages for the backin"...
0x1400d2f59  mov     [rsp+88h+var_50], r12
0x1400d2f5e  mov     edx, 40000h
0x1400d2f63  mov     [rsp+88h+var_58], r12
0x1400d2f68  mov     qword ptr [rsp+88h+Flags], r12
0x1400d2f6d  mov     qword ptr [rsp+88h+CacheType], rax
0x1400d2f72  mov     cs:WdLogGlobalForLineNumber, eax
0x1400d2f78  call    DxgkLogInternalTriageEvent
0x1400d2f7d  mov     edi, 0C0000017h
0x1400d2f82  jmp     loc_1400D3073
0x1400d2f87  test    byte ptr [rax+0Ah], 5
0x1400d2f8b  jz      short loc_1400D2F93
0x1400d2f8d  mov     rbp, [rax+18h]
0x1400d2f91  jmp     short loc_1400D2FB8
0x1400d2f93  xor     r9d, r9d; RequestedAddress
0x1400d2f96  mov     [rsp+88h+Flags], 40000010h; Priority
0x1400d2f9e  xor     edx, edx; AccessMode
0x1400d2fa0  mov     [rsp+88h+CacheType], r12d; BugCheckOnFailure
0x1400d2fa5  lea     r8d, [r9+1]; CacheType
0x1400d2fa9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d2fb0  nop     dword ptr [rax+rax+00h]
0x1400d2fb5  mov     rbp, rax
0x1400d2fb8  test    rbp, rbp
0x1400d2fbb  jnz     short loc_1400D2FDD
0x1400d2fbd  lea     ecx, [rbp+1]
0x1400d2fc0  call    cs:__imp_WdLogSingleEntry0
0x1400d2fc7  nop     dword ptr [rax+rax+00h]
0x1400d2fcc  mov     eax, 1FBh
0x1400d2fd1  lea     r9, aFailedToGetSys_0; "Failed to get system view for backing s"...
0x1400d2fd8  jmp     loc_1400D2F59
0x1400d2fdd  mov     rdx, [r14]; struct _MDL *
0x1400d2fe0  lea     r9, [r14+10h]; void **
0x1400d2fe4  mov     rcx, [r15+8]; this
0x1400d2fe8  lea     rax, [r9+8]
0x1400d2fec  mov     r8, rdi; unsigned __int64
0x1400d2fef  mov     qword ptr [rsp+88h+CacheType], rax; unsigned __int64 *
0x1400d2ff4  call    ?MapHostAddressesToGuest@VIDMM_PROCESS@@QEAAJPEAU_MDL@@_KPEAPEAXPEA_K@Z; VIDMM_PROCESS::MapHostAddressesToGuest(_MDL *,unsigned __int64,void * *,unsigned __int64 *)
0x1400d2ff9  movsxd  rdi, eax
0x1400d2ffc  test    eax, eax
0x1400d2ffe  jns     short loc_1400D3049
0x1400d3000  mov     rdx, rdi
0x1400d3003  mov     ecx, 1
0x1400d3008  call    cs:__imp_WdLogSingleEntry1
0x1400d300f  nop     dword ptr [rax+rax+00h]
0x1400d3014  mov     [rsp+88h+var_50], r12
0x1400d3019  lea     r9, aFailedToMapHpa; "Failed to map HPA to GPA: 0x%I64x"
0x1400d3020  mov     [rsp+88h+var_58], r12
0x1400d3025  mov     edx, 40000h
0x1400d302a  mov     qword ptr [rsp+88h+Flags], r12
0x1400d302f  mov     qword ptr [rsp+88h+CacheType], rdi
0x1400d3034  mov     cs:WdLogGlobalForLineNumber, 207h
0x1400d303e  call    DxgkLogInternalTriageEvent
0x1400d3043  jmp     short loc_1400D3073
0x1400d3045  test    al, 2
0x1400d3047  jz      short loc_1400D306E
0x1400d3049  mov     rax, [rsp+88h+arg_38]
0x1400d3051  mov     [rax], r14
0x1400d3054  mov     rax, [rsp+88h+arg_40]
0x1400d305c  mov     [rax], rbp
0x1400d305f  mov     rax, [rsp+88h+arg_48]
0x1400d3067  mov     byte ptr [rax], 1
0x1400d306a  xor     eax, eax
0x1400d306c  jmp     short loc_1400D30E1
0x1400d306e  mov     edi, 0C0000002h
0x1400d3073  mov     rax, [r15]
0x1400d3076  xor     r9d, r9d
0x1400d3079  mov     r8, rbp
0x1400d307c  mov     rdx, r14
0x1400d307f  mov     rcx, r15
0x1400d3082  mov     rax, [rax+88h]
0x1400d3089  call    _guard_dispatch_icall
0x1400d308e  jmp     short loc_1400D30DF
0x1400d3090  lock inc cs:dword_140087888
0x1400d3097  mov     rdx, rbx
0x1400d309a  mov     ecx, 6
0x1400d309f  call    cs:__imp_WdLogSingleEntry1
0x1400d30a6  nop     dword ptr [rax+rax+00h]
0x1400d30ab  mov     [rsp+88h+var_50], r12
0x1400d30b0  lea     r9, aFailedToAlloca_73; "Failed to allocate VIDMM_PARAVIRTUALIZA"...
0x1400d30b7  mov     [rsp+88h+var_58], r12
0x1400d30bc  mov     edx, 40001h
0x1400d30c1  mov     qword ptr [rsp+88h+Flags], r12
0x1400d30c6  mov     qword ptr [rsp+88h+CacheType], rbx
0x1400d30cb  mov     cs:WdLogGlobalForLineNumber, 1DFh
0x1400d30d5  call    DxgkLogInternalTriageEvent
0x1400d30da  mov     edi, 0C0000017h
0x1400d30df  mov     eax, edi
0x1400d30e1  add     rsp, 58h
0x1400d30e5  pop     r15
0x1400d30e7  pop     r14
0x1400d30e9  pop     r12
0x1400d30eb  pop     rdi
0x1400d30ec  pop     rbp
0x1400d30ed  pop     rbx
0x1400d30ee  retn
```
