# VIDMM_GUEST_SYSTEM_MEMORY_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400d9900`
- end: `0x1400d9c4a`
- name: `?AllocateGlobal@VIDMM_GUEST_SYSTEM_MEMORY_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `842`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, _QWORD *, _BYTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140003490`
- `0x140004268`
- `0x140059030`
- `0x1400d9848`
- `0x1400d9900`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d9ba7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d9ba7`
- `watchdog!WdLogSingleEntry3` at `0x1400d99ca`
- `watchdog!WdLogSingleEntry3` at `0x1400d99ca`
- `watchdog!WdLogSingleEntry2` at `0x1400d9959`
- `watchdog!WdLogSingleEntry2` at `0x1400d9a59`
- `watchdog!WdLogSingleEntry2` at `0x1400d9b11`
- `watchdog!WdLogSingleEntry2` at `0x1400d9959`
- `watchdog!WdLogSingleEntry2` at `0x1400d9a59`
- `watchdog!WdLogSingleEntry2` at `0x1400d9b11`
- `watchdog!WdLogSingleEntry1` at `0x1400d9bef`
- `watchdog!WdLogSingleEntry1` at `0x1400d9bef`

## pseudocode

```c
__int64 __fastcall VIDMM_GUEST_SYSTEM_MEMORY_HEAP::AllocateGlobal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        _QWORD *a9,
        _BYTE *a10)
{
  __int64 v10; // rbp
  __int64 v12; // rcx
  int v15; // eax
  __int64 v16; // rsi
  int v17; // ecx
  int v18; // r8d
  unsigned __int64 v20; // r14
  int v21; // ecx
  int v22; // r8d
  __int64 v23; // rcx
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // rax
  __int64 v27; // rsi
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // r14
  int v31; // ecx
  int v32; // r8d
  unsigned int v33; // edx
  PMDL v34; // r10
  PVOID MappedSystemVa; // rax
  int v36; // ecx
  int v37; // r8d
  PMDL MemoryDescriptorList[2]; // [rsp+50h] [rbp-38h] BYREF
  unsigned int v39; // [rsp+90h] [rbp+8h] BYREF

  v10 = a6;
  v12 = *(_QWORD *)(a1 + 8);
  v39 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v12 + 16LL))(v12, a6, &v39);
  v16 = v15;
  if ( v15 < 0 )
  {
    WdLogSingleEntry2(1, v10, v15);
    WdLogGlobalForLineNumber = 1108;
    DxgkLogInternalTriageEvent(
      v17,
      0x40000,
      v18,
      (unsigned int)L"Failed to get the size of the memory block 0x%I64x, returning 0x%I64x.",
      v10,
      v16,
      0,
      0);
    return (unsigned int)v16;
  }
  v20 = (unsigned __int64)(a3 + 4095) >> 12;
  if ( (_DWORD)v20 << 12 > v39 )
  {
    WdLogSingleEntry3(1, v10, a3, -1073741811);
    WdLogGlobalForLineNumber = 1118;
    DxgkLogInternalTriageEvent(
      v21,
      0x40000,
      v22,
      (unsigned int)L"Memory block  0x%I64x is not large enough for allocation size 0x%I64x, returning 0x%I64x.",
      v10,
      a3,
      -1073741811,
      0);
    return 3221225485LL;
  }
  v23 = *(_QWORD *)(a1 + 8);
  LOBYTE(a6) = 0;
  (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v23 + 32LL))(v23, v10, &a6);
  if ( !(_BYTE)a6 && (**(_DWORD **)(a2 + 392) & 1) != 0 )
  {
    WdLogSingleEntry2(1, v10, -1073741811);
    WdLogGlobalForLineNumber = 1132;
    DxgkLogInternalTriageEvent(
      v24,
      0x40000,
      v25,
      (unsigned int)L"Memory block 0x%I64x is not CPU visible, but the driver requested it to be CPU visible, returning 0x%I64x.",
      v10,
      -1073741811,
      0,
      0);
    return 3221225485LL;
  }
  v26 = operator new(48, 1714579798, 256);
  v27 = v26;
  if ( v26 )
  {
    *(_QWORD *)v26 = a1;
    *(_QWORD *)(v26 + 8) = 0;
    *(_QWORD *)(v26 + 16) = 0;
    *(_BYTE *)(v26 + 24) = 0;
    *(_QWORD *)(v26 + 32) = 0;
    *(_QWORD *)(v26 + 40) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 8LL));
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    v28 = *(_QWORD *)(a1 + 8);
    MemoryDescriptorList[0] = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, PMDL *))(*(_QWORD *)v28 + 24LL))(
            v28,
            v10,
            0,
            (unsigned int)v20,
            1,
            MemoryDescriptorList);
    v30 = v29;
    if ( v29 >= 0 )
    {
      *(_QWORD *)(v27 + 8) = a3;
      *(_QWORD *)(v27 + 16) = v10;
      *(PMDL *)(v27 + 32) = MemoryDescriptorList[0];
      v34 = MemoryDescriptorList[0];
      *(_BYTE *)(v27 + 24) = **(_BYTE **)(a2 + 392) & 1;
      if ( (v34->MdlFlags & 5) != 0 )
        MappedSystemVa = v34->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v34, 0, MmCached, 0, 0, 0x10u);
      *(_QWORD *)(v27 + 40) = MappedSystemVa;
      *a10 = 1;
      *a8 = v27;
      *a9 = *(_QWORD *)(v27 + 40);
      return 0;
    }
    else
    {
      WdLogSingleEntry2(1, v10, v29);
      WdLogGlobalForLineNumber = 1166;
      DxgkLogInternalTriageEvent(
        v31,
        0x40000,
        v32,
        (unsigned int)L"Failed to probe and lock the memory block 0x%I64x, returning 0x%I64x.",
        v10,
        v30,
        0,
        0);
      VIDMM_GUEST_SYSTEM_MEMORY_HEAP_ALLOC::`scalar deleting destructor'(
        (VIDMM_GUEST_SYSTEM_MEMORY_HEAP_ALLOC *)v27,
        v33);
      return (unsigned int)v30;
    }
  }
  else
  {
    _InterlockedIncrement(&dword_1400878B8);
    WdLogSingleEntry1(6, a2);
    WdLogGlobalForLineNumber = 1149;
    DxgkLogInternalTriageEvent(
      v36,
      262145,
      v37,
      (unsigned int)L"Failed to allocate VIDMM_GUEST_SYSTEM_MEMORY_HEAP_ALLOC for global alloc 0x%.16x",
      a2,
      0,
      0,
      0);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x1400d9900  mov     r11, rsp
0x1400d9903  mov     [r11+10h], rbx
0x1400d9907  mov     [r11+18h], rbp
0x1400d990b  push    rsi
0x1400d990c  push    r12
0x1400d990e  push    r13
0x1400d9910  push    r14
0x1400d9912  push    r15
0x1400d9914  sub     rsp, 60h
0x1400d9918  mov     rbp, [rsp+88h+arg_28]
0x1400d9920  mov     r13, rcx
0x1400d9923  mov     rcx, [rcx+8]
0x1400d9927  mov     r15, r8
0x1400d992a  mov     rbx, rdx
0x1400d992d  lea     r8, [r11+8]
0x1400d9931  xor     r12d, r12d
0x1400d9934  mov     rdx, rbp
0x1400d9937  mov     [r11+8], r12d
0x1400d993b  mov     rax, [rcx]
0x1400d993e  mov     rax, [rax+10h]
0x1400d9942  call    _guard_dispatch_icall
0x1400d9947  movsxd  rsi, eax
0x1400d994a  test    eax, eax
0x1400d994c  jns     short loc_1400D999B
0x1400d994e  mov     r8, rsi
0x1400d9951  lea     ecx, [r12+1]
0x1400d9956  mov     rdx, rbp
0x1400d9959  call    cs:__imp_WdLogSingleEntry2
0x1400d9960  nop     dword ptr [rax+rax+00h]
0x1400d9965  mov     [rsp+88h+var_50], r12
0x1400d996a  lea     r9, aFailedToGetThe; "Failed to get the size of the memory bl"...
0x1400d9971  mov     [rsp+88h+var_58], r12
0x1400d9976  mov     edx, 40000h
0x1400d997b  mov     qword ptr [rsp+88h+Priority], rsi
0x1400d9980  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x1400d9985  mov     cs:WdLogGlobalForLineNumber, 454h
0x1400d998f  call    DxgkLogInternalTriageEvent
0x1400d9994  mov     eax, esi
0x1400d9996  jmp     loc_1400D9C2F
0x1400d999b  lea     r14, [r15+0FFFh]
0x1400d99a2  shr     r14, 0Ch
0x1400d99a6  mov     eax, r14d
0x1400d99a9  shl     eax, 0Ch
0x1400d99ac  cmp     eax, [rsp+88h+arg_0]
0x1400d99b3  jbe     short loc_1400D9A0C
0x1400d99b5  mov     rbx, 0FFFFFFFFC000000Dh
0x1400d99bc  mov     r8, r15
0x1400d99bf  mov     r9, rbx
0x1400d99c2  mov     rdx, rbp
0x1400d99c5  mov     ecx, 1
0x1400d99ca  call    cs:__imp_WdLogSingleEntry3
0x1400d99d1  nop     dword ptr [rax+rax+00h]
0x1400d99d6  mov     [rsp+88h+var_50], r12
0x1400d99db  lea     r9, aMemoryBlock0xI; "Memory block  0x%I64x is not large enou"...
0x1400d99e2  mov     [rsp+88h+var_58], rbx
0x1400d99e7  mov     qword ptr [rsp+88h+Priority], r15
0x1400d99ec  mov     cs:WdLogGlobalForLineNumber, 45Eh
0x1400d99f6  mov     edx, 40000h
0x1400d99fb  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x1400d9a00  call    DxgkLogInternalTriageEvent
0x1400d9a05  mov     eax, ebx
0x1400d9a07  jmp     loc_1400D9C2F
0x1400d9a0c  mov     rcx, [r13+8]
0x1400d9a10  lea     r8, [rsp+88h+arg_28]
0x1400d9a18  mov     byte ptr [rsp+88h+arg_28], r12b
0x1400d9a20  mov     rdx, rbp
0x1400d9a23  mov     rax, [rcx]
0x1400d9a26  mov     rax, [rax+20h]
0x1400d9a2a  call    _guard_dispatch_icall
0x1400d9a2f  cmp     byte ptr [rsp+88h+arg_28], r12b
0x1400d9a37  jnz     short loc_1400D9A8A
0x1400d9a39  mov     rax, [rbx+188h]
0x1400d9a40  mov     ecx, [rax]
0x1400d9a42  test    cl, 1
0x1400d9a45  jz      short loc_1400D9A8A
0x1400d9a47  mov     rbx, 0FFFFFFFFC000000Dh
0x1400d9a4e  mov     rdx, rbp
0x1400d9a51  mov     r8, rbx
0x1400d9a54  mov     ecx, 1
0x1400d9a59  call    cs:__imp_WdLogSingleEntry2
0x1400d9a60  nop     dword ptr [rax+rax+00h]
0x1400d9a65  mov     [rsp+88h+var_50], r12
0x1400d9a6a  lea     r9, aMemoryBlock0xI_0; "Memory block 0x%I64x is not CPU visible"...
0x1400d9a71  mov     [rsp+88h+var_58], r12
0x1400d9a76  mov     qword ptr [rsp+88h+Priority], rbx
0x1400d9a7b  mov     cs:WdLogGlobalForLineNumber, 46Ch
0x1400d9a85  jmp     loc_1400D99F6
0x1400d9a8a  mov     edx, 66326956h
0x1400d9a8f  mov     ecx, 30h ; '0'
0x1400d9a94  mov     r8d, 100h
0x1400d9a9a  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400d9a9f  mov     rsi, rax
0x1400d9aa2  test    rax, rax
0x1400d9aa5  jz      loc_1400D9BE0
0x1400d9aab  mov     [rax], r13
0x1400d9aae  mov     [rax+8], r12
0x1400d9ab2  mov     [rax+10h], r12
0x1400d9ab6  mov     [rax+18h], r12b
0x1400d9aba  mov     [rax+20h], r12
0x1400d9abe  mov     [rax+28h], r12
0x1400d9ac2  mov     rcx, [r13+8]
0x1400d9ac6  lock inc dword ptr [rcx+8]
0x1400d9aca  lock inc dword ptr [r13+10h]
0x1400d9acf  mov     rcx, [r13+8]
0x1400d9ad3  lea     rdx, [rsp+88h+MemoryDescriptorList]
0x1400d9ad8  mov     qword ptr [rsp+88h+Priority], rdx
0x1400d9add  mov     r9d, r14d
0x1400d9ae0  mov     [rsp+88h+MemoryDescriptorList], r12
0x1400d9ae5  xor     r8d, r8d
0x1400d9ae8  mov     rdx, rbp
0x1400d9aeb  mov     [rsp+88h+BugCheckOnFailure], 1
0x1400d9af3  mov     rax, [rcx]
0x1400d9af6  mov     rax, [rax+18h]
0x1400d9afa  call    _guard_dispatch_icall
0x1400d9aff  movsxd  r14, eax
0x1400d9b02  test    eax, eax
0x1400d9b04  jns     short loc_1400D9B5C
0x1400d9b06  mov     r8, r14
0x1400d9b09  mov     rdx, rbp
0x1400d9b0c  mov     ecx, 1
0x1400d9b11  call    cs:__imp_WdLogSingleEntry2
0x1400d9b18  nop     dword ptr [rax+rax+00h]
0x1400d9b1d  mov     [rsp+88h+var_50], r12
0x1400d9b22  lea     r9, aFailedToProbeA_2; "Failed to probe and lock the memory blo"...
0x1400d9b29  mov     [rsp+88h+var_58], r12
0x1400d9b2e  mov     edx, 40000h
0x1400d9b33  mov     qword ptr [rsp+88h+Priority], r14
0x1400d9b38  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x1400d9b3d  mov     cs:WdLogGlobalForLineNumber, 48Eh
0x1400d9b47  call    DxgkLogInternalTriageEvent
0x1400d9b4c  mov     rcx, rsi; this
0x1400d9b4f  call    ??_GVIDMM_GUEST_SYSTEM_MEMORY_HEAP_ALLOC@@QEAAPEAXI@Z; VIDMM_GUEST_SYSTEM_MEMORY_HEAP_ALLOC::`scalar deleting destructor'(uint)
0x1400d9b54  mov     eax, r14d
0x1400d9b57  jmp     loc_1400D9C2F
0x1400d9b5c  mov     [rsi+8], r15
0x1400d9b60  mov     [rsi+10h], rbp
0x1400d9b64  mov     rax, [rsp+88h+MemoryDescriptorList]
0x1400d9b69  mov     [rsi+20h], rax
0x1400d9b6d  mov     rax, [rbx+188h]
0x1400d9b74  mov     r10, [rsp+88h+MemoryDescriptorList]
0x1400d9b79  mov     cl, [rax]
0x1400d9b7b  and     cl, 1
0x1400d9b7e  mov     [rsi+18h], cl
0x1400d9b81  test    byte ptr [r10+0Ah], 5
0x1400d9b86  jz      short loc_1400D9B8E
0x1400d9b88  mov     rax, [r10+18h]
0x1400d9b8c  jmp     short loc_1400D9BB3
0x1400d9b8e  xor     r9d, r9d; RequestedAddress
0x1400d9b91  mov     [rsp+88h+Priority], 10h; Priority
0x1400d9b99  xor     edx, edx; AccessMode
0x1400d9b9b  mov     [rsp+88h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x1400d9ba0  mov     rcx, r10; MemoryDescriptorList
0x1400d9ba3  lea     r8d, [r9+1]; CacheType
0x1400d9ba7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d9bae  nop     dword ptr [rax+rax+00h]
0x1400d9bb3  mov     [rsi+28h], rax
0x1400d9bb7  mov     rax, [rsp+88h+arg_48]
0x1400d9bbf  mov     byte ptr [rax], 1
0x1400d9bc2  mov     rax, [rsp+88h+arg_38]
0x1400d9bca  mov     [rax], rsi
0x1400d9bcd  mov     rax, [rsp+88h+arg_40]
0x1400d9bd5  mov     rcx, [rsi+28h]
0x1400d9bd9  mov     [rax], rcx
0x1400d9bdc  xor     eax, eax
0x1400d9bde  jmp     short loc_1400D9C2F
0x1400d9be0  lock inc cs:dword_1400878B8
0x1400d9be7  mov     rdx, rbx
0x1400d9bea  mov     ecx, 6
0x1400d9bef  call    cs:__imp_WdLogSingleEntry1
0x1400d9bf6  nop     dword ptr [rax+rax+00h]
0x1400d9bfb  mov     [rsp+88h+var_50], r12
0x1400d9c00  lea     r9, aFailedToAlloca_25; "Failed to allocate VIDMM_GUEST_SYSTEM_M"...
0x1400d9c07  mov     [rsp+88h+var_58], r12
0x1400d9c0c  mov     edx, 40001h
0x1400d9c11  mov     qword ptr [rsp+88h+Priority], r12
0x1400d9c16  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbx
0x1400d9c1b  mov     cs:WdLogGlobalForLineNumber, 47Dh
0x1400d9c25  call    DxgkLogInternalTriageEvent
0x1400d9c2a  mov     eax, 0C0000017h
0x1400d9c2f  lea     r11, [rsp+88h+var_28]
0x1400d9c34  mov     rbx, [r11+38h]
0x1400d9c38  mov     rbp, [r11+40h]
0x1400d9c3c  mov     rsp, r11
0x1400d9c3f  pop     r15
0x1400d9c41  pop     r14
0x1400d9c43  pop     r13
0x1400d9c45  pop     r12
0x1400d9c47  pop     rsi
0x1400d9c48  retn
```
