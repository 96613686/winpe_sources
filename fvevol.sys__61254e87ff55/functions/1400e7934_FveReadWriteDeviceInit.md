# FveReadWriteDeviceInit

- ea: `0x1400e7934`
- end: `0x1400e7dc9`
- name: `FveReadWriteDeviceInit`
- size: `1173`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140030430`
- `0x14009fb70`
- `0x1400ab924`
- `0x1400ccd18`

## callees

- `0x14000ff74`
- `0x140010008`
- `0x140093738`
- `0x1400beb8c`
- `0x1400db0d0`
- `0x1400e62f8`
- `0x1400e7934`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400e7d04`
- `ntoskrnl!KeInitializeEvent` at `0x1400e7d04`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e7bad`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e7c15`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e7d7a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e7bad`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e7c15`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e7d7a`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400e7c5a`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400e7c5a`
- `ntoskrnl!KeReleaseMutex` at `0x1400e7daa`
- `ntoskrnl!KeReleaseMutex` at `0x1400e7daa`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e7b79`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e7b79`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e7b43`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e7b43`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400e7d22`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400e7d22`
- `ntoskrnl!IoAllocateMdl` at `0x1400e7d44`
- `ntoskrnl!IoAllocateMdl` at `0x1400e7d44`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e7968`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e7968`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7b0b`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7bc7`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7c75`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7ca6`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7b0b`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7bc7`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7c75`
- `ntoskrnl!ExAllocatePool2` at `0x1400e7ca6`

## pseudocode

```c
__int64 __fastcall FveReadWriteDeviceInit(__int64 a1)
{
  __int64 v1; // rdi
  int v3; // ebx
  struct _KMUTANT *v4; // rbp
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 Pool2; // rax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 i; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  ULONG v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int v21; // edi
  unsigned int v22; // ebx
  PMDL Mdl; // rax

  v1 = *(_QWORD *)(a1 + 8);
  v3 = 0;
  v4 = (struct _KMUTANT *)(v1 + 9856);
  KeWaitForSingleObject((PVOID)(v1 + 9856), Executive, 0, 0, 0);
  if ( *(_DWORD *)(a1 + 4728) != 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 4728));
    FveLoadIoCryptoConfig(v1, 0, a1, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v5 = *(unsigned int *)(v1 + 884);
        WPP_SF_qLDDDDDDDDDDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          58,
          v5,
          a1,
          *(_DWORD *)(v1 + 884),
          *(_DWORD *)(a1 + 4 * v5 + 1592),
          *(_DWORD *)(a1 + 4 * v5 + 1604),
          *(_DWORD *)(a1 + 4 * v5 + 1616),
          *(_DWORD *)(a1 + 4 * v5 + 1640),
          *(_DWORD *)(a1 + 4 * v5 + 1652),
          *(_DWORD *)(a1 + 4 * v5 + 1676),
          *(_DWORD *)(a1 + 4 * v5 + 1688),
          *(_DWORD *)(a1 + 4 * v5 + 1700),
          *(_DWORD *)(a1 + 4 * v5 + 1712),
          *(_DWORD *)(a1 + 4 * v5 + 1724),
          *(_DWORD *)(a1 + 4 * v5 + 1736),
          *(_DWORD *)(a1 + 4 * v5 + 1748));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v6 = *(unsigned int *)(v1 + 884);
        WPP_SF_qLDDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          59,
          v6,
          a1,
          *(_DWORD *)(v1 + 884),
          *(_DWORD *)(a1 + 4 * v6 + 1760),
          *(_DWORD *)(a1 + 4 * v6 + 1772),
          *(_DWORD *)(v1 + 4 * v6 + 972),
          *(_DWORD *)(v1 + 4 * v6 + 1008));
      }
    }
    if ( *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v1 + 884) + 1592) == *(_DWORD *)(v1
                                                                                 + 4LL * *(unsigned int *)(v1 + 884)
                                                                                 + 936) )
    {
      *(_QWORD *)(a1 + 2016) = *(_QWORD *)(v1 + 9256);
      v11 = *(_QWORD *)(v1 + 9264);
    }
    else
    {
      Pool2 = ExAllocatePool2(64, 128, 809850438);
      *(_QWORD *)(a1 + 2016) = Pool2;
      if ( !Pool2 )
        goto LABEL_26;
      v9 = *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v1 + 884) + 1592);
      v10 = MmSizeOfMdl(0, v9);
      ExInitializeNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016),
        0,
        0,
        0x200u,
        v10 + v9 + 64,
        0x70455646u,
        0);
      v11 = 0;
    }
    *(_QWORD *)(a1 + 2024) = v11;
    KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 2032));
    v12 = ExAllocatePool2(64, 6456, 2017809990);
    *(_QWORD *)(a1 + 2040) = v12;
    *(_BYTE *)(a1 + 2048) = 0;
    if ( v12 )
    {
      for ( i = 0; i != 32; KeInitializeSpinLock((PKSPIN_LOCK)(v14 + 464 + 192 * i++)) )
      {
        v14 = *(_QWORD *)(a1 + 2040);
        v15 = 192 * i;
        *(_QWORD *)(v15 + v14 + 488) = 0;
        *(_QWORD *)(v15 + v14 + 496) = 0;
      }
      v16 = AcquireSubIrp(a1, a1 + 1592, *(unsigned int *)(v1 + 884), 0);
      *(_QWORD *)(a1 + 2056) = v16;
      *(_BYTE *)(a1 + 2064) = 0;
      if ( v16 )
      {
        v17 = IoSizeofWorkItem();
        v18 = ExAllocatePool2(64, v17 + 184, 2001032774);
        *(_QWORD *)(a1 + 2072) = v18;
        *(_BYTE *)(a1 + 2080) = 0;
        if ( v18 )
        {
          v19 = ExAllocatePool2(64, 4096, 1883592262);
          *(_QWORD *)(a1 + 2088) = v19;
          *(_BYTE *)(a1 + 2096) = 0;
          if ( v19 )
          {
            v20 = *(unsigned int *)(v1 + 884);
            v21 = 33 * *(_DWORD *)(a1 + 4 * v20 + 1604);
            v22 = *(_DWORD *)(a1 + 4 * v20 + 1592);
            *(_DWORD *)(a1 + 2120) = 1;
            *(_QWORD *)(a1 + 2128) = 0;
            *(_DWORD *)(a1 + 2136) = 0;
            KeInitializeEvent((PRKEVENT)(a1 + 2144), SynchronizationEvent, 0);
            if ( v21 <= v22 )
              v21 = v22;
            *(_QWORD *)(a1 + 2104) = MmAllocateMappingAddress(v21 + 4096, 0x72455646u);
            Mdl = IoAllocateMdl(0, v21 + 4096, 0, 0, 0);
            *(_QWORD *)(a1 + 2112) = Mdl;
            if ( *(_QWORD *)(a1 + 2104) )
            {
              if ( Mdl )
              {
                *(_QWORD *)(a1 + 2216) = a1 + 2208;
                *(_QWORD *)(a1 + 2208) = a1 + 2208;
                KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 2224));
                v3 = FveWorkerInit(a1);
                if ( v3 >= 0 )
                  goto LABEL_28;
                goto LABEL_27;
              }
            }
          }
        }
      }
    }
LABEL_26:
    v3 = -1073741670;
LABEL_27:
    LOBYTE(v8) = 1;
    FveReadWriteDeviceCleanup(a1, v8);
  }
LABEL_28:
  KeReleaseMutex(v4, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400e7934  push    rbx
0x1400e7936  push    rbp
0x1400e7937  push    rsi
0x1400e7938  push    rdi
0x1400e7939  push    r14
0x1400e793b  push    r15
0x1400e793d  sub     rsp, 98h
0x1400e7944  mov     rdi, [rcx+8]
0x1400e7948  mov     rsi, rcx
0x1400e794b  xor     r14d, r14d
0x1400e794e  xor     r9d, r9d; Alertable
0x1400e7951  xor     r8d, r8d; WaitMode
0x1400e7954  mov     [rsp+0C8h+Timeout], r14; Timeout
0x1400e7959  xor     edx, edx; WaitReason
0x1400e795b  mov     ebx, r14d
0x1400e795e  lea     rbp, [rdi+2680h]
0x1400e7965  mov     rcx, rbp; Object
0x1400e7968  call    cs:__imp_KeWaitForSingleObject
0x1400e796f  nop     dword ptr [rax+rax+00h]
0x1400e7974  cmp     dword ptr [rsi+1278h], 1
0x1400e797b  jz      loc_1400E7DA5
0x1400e7981  lock inc dword ptr [rsi+1278h]
0x1400e7988  xor     r9d, r9d
0x1400e798b  mov     [rsp+0C8h+Timeout], r14
0x1400e7990  mov     r8, rsi
0x1400e7993  xor     edx, edx
0x1400e7995  mov     rcx, rdi
0x1400e7998  call    FveLoadIoCryptoConfig
0x1400e799d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e79a4  lea     rbx, WPP_GLOBAL_Control
0x1400e79ab  cmp     rcx, rbx
0x1400e79ae  jz      loc_1400E7ADE
0x1400e79b4  mov     eax, [rcx+2Ch]
0x1400e79b7  test    al, al
0x1400e79b9  jns     loc_1400E7A78
0x1400e79bf  cmp     byte ptr [rcx+29h], 4
0x1400e79c3  jb      loc_1400E7A78
0x1400e79c9  mov     r8d, [rdi+374h]
0x1400e79d0  lea     edx, [r14+3Ah]
0x1400e79d4  mov     rcx, [rcx+18h]
0x1400e79d8  mov     r9, rsi
0x1400e79db  mov     eax, [rsi+r8*4+6D4h]
0x1400e79e3  mov     [rsp+0C8h+var_48], eax
0x1400e79ea  mov     eax, [rsi+r8*4+6C8h]
0x1400e79f2  mov     [rsp+0C8h+var_50], eax
0x1400e79f6  mov     eax, [rsi+r8*4+6BCh]
0x1400e79fe  mov     [rsp+0C8h+var_58], eax
0x1400e7a02  mov     eax, [rsi+r8*4+6B0h]
0x1400e7a0a  mov     [rsp+0C8h+var_60], eax
0x1400e7a0e  mov     eax, [rsi+r8*4+6A4h]
0x1400e7a16  mov     [rsp+0C8h+var_68], eax
0x1400e7a1a  mov     eax, [rsi+r8*4+698h]
0x1400e7a22  mov     [rsp+0C8h+var_70], eax
0x1400e7a26  mov     eax, [rsi+r8*4+68Ch]
0x1400e7a2e  mov     [rsp+0C8h+var_78], eax
0x1400e7a32  mov     eax, [rsi+r8*4+674h]
0x1400e7a3a  mov     [rsp+0C8h+var_80], eax
0x1400e7a3e  mov     eax, [rsi+r8*4+668h]
0x1400e7a46  mov     [rsp+0C8h+var_88], eax
0x1400e7a4a  mov     eax, [rsi+r8*4+650h]
0x1400e7a52  mov     [rsp+0C8h+var_90], eax
0x1400e7a56  mov     eax, [rsi+r8*4+644h]
0x1400e7a5e  mov     dword ptr [rsp+0C8h+Depth], eax
0x1400e7a62  mov     eax, [rsi+r8*4+638h]
0x1400e7a6a  mov     [rsp+0C8h+Tag], eax
0x1400e7a6e  mov     dword ptr [rsp+0C8h+Timeout], r8d
0x1400e7a73  call    WPP_SF_qLDDDDDDDDDDDD
0x1400e7a78  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7a7f  cmp     rcx, rbx
0x1400e7a82  jz      short loc_1400E7ADE
0x1400e7a84  mov     eax, [rcx+2Ch]
0x1400e7a87  test    al, al
0x1400e7a89  jns     short loc_1400E7ADE
0x1400e7a8b  cmp     byte ptr [rcx+29h], 4
0x1400e7a8f  jb      short loc_1400E7ADE
0x1400e7a91  mov     r8d, [rdi+374h]
0x1400e7a98  mov     edx, 3Bh ; ';'
0x1400e7a9d  mov     rcx, [rcx+18h]
0x1400e7aa1  mov     r9, rsi
0x1400e7aa4  mov     eax, [rdi+r8*4+3F0h]
0x1400e7aac  mov     [rsp+0C8h+var_88], eax
0x1400e7ab0  mov     eax, [rdi+r8*4+3CCh]
0x1400e7ab8  mov     [rsp+0C8h+var_90], eax
0x1400e7abc  mov     eax, [rsi+r8*4+6ECh]
0x1400e7ac4  mov     dword ptr [rsp+0C8h+Depth], eax
0x1400e7ac8  mov     eax, [rsi+r8*4+6E0h]
0x1400e7ad0  mov     [rsp+0C8h+Tag], eax
0x1400e7ad4  mov     dword ptr [rsp+0C8h+Timeout], r8d
0x1400e7ad9  call    WPP_SF_qLDDDD
0x1400e7ade  mov     ecx, [rdi+374h]
0x1400e7ae4  mov     r15d, 40h ; '@'
0x1400e7aea  mov     eax, [rdi+rcx*4+3A8h]
0x1400e7af1  cmp     [rsi+rcx*4+638h], eax
0x1400e7af8  jz      loc_1400E7B8A
0x1400e7afe  lea     edx, [r15+40h]
0x1400e7b02  mov     r8d, 30455646h
0x1400e7b08  mov     ecx, r15d
0x1400e7b0b  call    cs:__imp_ExAllocatePool2
0x1400e7b12  nop     dword ptr [rax+rax+00h]
0x1400e7b17  mov     [rsi+7E0h], rax
0x1400e7b1e  test    rax, rax
0x1400e7b21  jz      loc_1400E7D96
0x1400e7b27  mov     eax, [rdi+374h]
0x1400e7b2d  xor     ecx, ecx; Base
0x1400e7b2f  mov     ebx, [rsi+rax*4+638h]
0x1400e7b36  mov     eax, [rdi+374h]
0x1400e7b3c  mov     edx, [rsi+rax*4+638h]; Length
0x1400e7b43  call    cs:__imp_MmSizeOfMdl
0x1400e7b4a  nop     dword ptr [rax+rax+00h]
0x1400e7b4f  mov     rcx, [rsi+7E0h]; Lookaside
0x1400e7b56  lea     edx, [rbx+40h]
0x1400e7b59  add     edx, eax
0x1400e7b5b  mov     [rsp+0C8h+Depth], r14w; Depth
0x1400e7b61  mov     [rsp+0C8h+Tag], 70455646h; Tag
0x1400e7b69  mov     r9d, 200h; Flags
0x1400e7b6f  mov     [rsp+0C8h+Timeout], rdx; Size
0x1400e7b74  xor     r8d, r8d; Free
0x1400e7b77  xor     edx, edx; Allocate
0x1400e7b79  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400e7b80  nop     dword ptr [rax+rax+00h]
0x1400e7b85  mov     rax, r14
0x1400e7b88  jmp     short loc_1400E7B9F
0x1400e7b8a  mov     rax, [rdi+2428h]
0x1400e7b91  mov     [rsi+7E0h], rax
0x1400e7b98  mov     rax, [rdi+2430h]
0x1400e7b9f  lea     rcx, [rsi+7F0h]; SpinLock
0x1400e7ba6  mov     [rsi+7E8h], rax
0x1400e7bad  call    cs:__imp_KeInitializeSpinLock
0x1400e7bb4  nop     dword ptr [rax+rax+00h]
0x1400e7bb9  mov     edx, 1938h
0x1400e7bbe  mov     r8d, 78455646h
0x1400e7bc4  mov     rcx, r15
0x1400e7bc7  call    cs:__imp_ExAllocatePool2
0x1400e7bce  nop     dword ptr [rax+rax+00h]
0x1400e7bd3  mov     [rsi+7F8h], rax
0x1400e7bda  mov     [rsi+800h], r14b
0x1400e7be1  test    rax, rax
0x1400e7be4  jz      loc_1400E7D96
0x1400e7bea  mov     rbx, r14
0x1400e7bed  mov     rax, [rsi+7F8h]
0x1400e7bf4  lea     rcx, [rbx+rbx*2]
0x1400e7bf8  shl     rcx, 6
0x1400e7bfc  mov     [rcx+rax+1E8h], r14
0x1400e7c04  mov     [rcx+rax+1F0h], r14
0x1400e7c0c  add     rax, 1D0h
0x1400e7c12  add     rcx, rax; SpinLock
0x1400e7c15  call    cs:__imp_KeInitializeSpinLock
0x1400e7c1c  nop     dword ptr [rax+rax+00h]
0x1400e7c21  inc     rbx
0x1400e7c24  cmp     rbx, 20h ; ' '
0x1400e7c28  jnz     short loc_1400E7BED
0x1400e7c2a  mov     r8d, [rdi+374h]
0x1400e7c31  lea     rdx, [rsi+638h]
0x1400e7c38  xor     r9d, r9d
0x1400e7c3b  mov     rcx, rsi
0x1400e7c3e  call    AcquireSubIrp
0x1400e7c43  mov     [rsi+808h], rax
0x1400e7c4a  mov     [rsi+810h], r14b
0x1400e7c51  test    rax, rax
0x1400e7c54  jz      loc_1400E7D96
0x1400e7c5a  call    cs:__imp_IoSizeofWorkItem
0x1400e7c61  nop     dword ptr [rax+rax+00h]
0x1400e7c66  mov     r8d, 77455646h
0x1400e7c6c  mov     rcx, r15
0x1400e7c6f  lea     edx, [rax+0B8h]
0x1400e7c75  call    cs:__imp_ExAllocatePool2
0x1400e7c7c  nop     dword ptr [rax+rax+00h]
0x1400e7c81  mov     [rsi+818h], rax
0x1400e7c88  mov     [rsi+820h], r14b
0x1400e7c8f  test    rax, rax
0x1400e7c92  jz      loc_1400E7D96
0x1400e7c98  mov     edx, 1000h
0x1400e7c9d  mov     r8d, 70455646h
0x1400e7ca3  mov     rcx, r15
0x1400e7ca6  call    cs:__imp_ExAllocatePool2
0x1400e7cad  nop     dword ptr [rax+rax+00h]
0x1400e7cb2  mov     [rsi+828h], rax
0x1400e7cb9  mov     [rsi+830h], r14b
0x1400e7cc0  test    rax, rax
0x1400e7cc3  jz      loc_1400E7D96
0x1400e7cc9  mov     eax, [rdi+374h]
0x1400e7ccf  lea     rcx, [rsi+860h]; Event
0x1400e7cd6  xor     r8d, r8d; State
0x1400e7cd9  imul    edi, [rsi+rax*4+644h], 21h ; '!'
0x1400e7ce1  mov     ebx, [rsi+rax*4+638h]
0x1400e7ce8  lea     edx, [r8+1]; Type
0x1400e7cec  mov     dword ptr [rsi+848h], 1
0x1400e7cf6  mov     [rsi+850h], r14
0x1400e7cfd  mov     [rsi+858h], r14d
0x1400e7d04  call    cs:__imp_KeInitializeEvent
0x1400e7d0b  nop     dword ptr [rax+rax+00h]
0x1400e7d10  cmp     edi, ebx
0x1400e7d12  mov     edx, 72455646h; PoolTag
0x1400e7d17  cmovbe  edi, ebx
0x1400e7d1a  lea     ebx, [rdi+1000h]
0x1400e7d20  mov     ecx, ebx; NumberOfBytes
0x1400e7d22  call    cs:__imp_MmAllocateMappingAddress
0x1400e7d29  nop     dword ptr [rax+rax+00h]
0x1400e7d2e  xor     r9d, r9d; ChargeQuota
0x1400e7d31  mov     [rsp+0C8h+Timeout], r14; Irp
0x1400e7d36  xor     r8d, r8d; SecondaryBuffer
0x1400e7d39  mov     [rsi+838h], rax
0x1400e7d40  mov     edx, ebx; Length
0x1400e7d42  xor     ecx, ecx; VirtualAddress
0x1400e7d44  call    cs:__imp_IoAllocateMdl
0x1400e7d4b  nop     dword ptr [rax+rax+00h]
0x1400e7d50  mov     [rsi+840h], rax
0x1400e7d57  cmp     [rsi+838h], r14
0x1400e7d5e  jz      short loc_1400E7D96
0x1400e7d60  test    rax, rax
0x1400e7d63  jz      short loc_1400E7D96
0x1400e7d65  lea     rax, [rsi+8A0h]
0x1400e7d6c  lea     rcx, [rsi+8B0h]; SpinLock
0x1400e7d73  mov     [rax+8], rax
0x1400e7d77  mov     [rax], rax
0x1400e7d7a  call    cs:__imp_KeInitializeSpinLock
0x1400e7d81  nop     dword ptr [rax+rax+00h]
0x1400e7d86  mov     rcx, rsi
0x1400e7d89  call    FveWorkerInit
0x1400e7d8e  mov     ebx, eax
0x1400e7d90  test    eax, eax
0x1400e7d92  js      short loc_1400E7D9B
0x1400e7d94  jmp     short loc_1400E7DA5
0x1400e7d96  mov     ebx, 0C000009Ah
0x1400e7d9b  mov     dl, 1
0x1400e7d9d  mov     rcx, rsi
0x1400e7da0  call    FveReadWriteDeviceCleanup
0x1400e7da5  xor     edx, edx; Wait
0x1400e7da7  mov     rcx, rbp; Mutex
0x1400e7daa  call    cs:__imp_KeReleaseMutex
0x1400e7db1  nop     dword ptr [rax+rax+00h]
0x1400e7db6  mov     eax, ebx
0x1400e7db8  add     rsp, 98h
0x1400e7dbf  pop     r15
0x1400e7dc1  pop     r14
0x1400e7dc3  pop     rdi
0x1400e7dc4  pop     rsi
0x1400e7dc5  pop     rbp
0x1400e7dc6  pop     rbx
0x1400e7dc7  retn
```
