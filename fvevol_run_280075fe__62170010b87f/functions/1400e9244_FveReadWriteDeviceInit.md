# FveReadWriteDeviceInit

- ea: `0x1400e9244`
- end: `0x1400e971c`
- name: `FveReadWriteDeviceInit`
- size: `1240`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14002f430`
- `0x14009ec2c`
- `0x1400aa9c4`
- `0x1400c9248`

## callees

- `0x14000b870`
- `0x14000fb78`
- `0x14000fc0c`
- `0x140091688`
- `0x1400bb39c`
- `0x1400cfa10`
- `0x1400e9050`
- `0x1400e9244`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400e9657`
- `ntoskrnl!KeInitializeEvent` at `0x1400e9657`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e94bd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e9524`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e96cd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e94bd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e9524`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400e96cd`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400e9569`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400e9569`
- `ntoskrnl!KeReleaseMutex` at `0x1400e96fd`
- `ntoskrnl!KeReleaseMutex` at `0x1400e96fd`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e9489`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e9489`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e9453`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e9453`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400e9675`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400e9675`
- `ntoskrnl!IoAllocateMdl` at `0x1400e9697`
- `ntoskrnl!IoAllocateMdl` at `0x1400e9697`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e9278`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e9278`
- `ntoskrnl!ExAllocatePool2` at `0x1400e941b`
- `ntoskrnl!ExAllocatePool2` at `0x1400e94d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400e9584`
- `ntoskrnl!ExAllocatePool2` at `0x1400e95b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400e95f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400e941b`
- `ntoskrnl!ExAllocatePool2` at `0x1400e94d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400e9584`
- `ntoskrnl!ExAllocatePool2` at `0x1400e95b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400e95f9`

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
  __int64 v21; // rax
  unsigned int v22; // edi
  unsigned int v23; // ebx
  PMDL Mdl; // rax

  v1 = *(_QWORD *)(a1 + 8);
  v3 = 0;
  v4 = (struct _KMUTANT *)(v1 + 9608);
  KeWaitForSingleObject((PVOID)(v1 + 9608), Executive, 0, 0, 0);
  if ( *(_DWORD *)(a1 + 4712) == 1 )
    goto LABEL_31;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4712));
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
    *(_QWORD *)(a1 + 2016) = *(_QWORD *)(v1 + 9008);
    v11 = *(_QWORD *)(v1 + 9016);
  }
  else
  {
    Pool2 = ExAllocatePool2(64, 128, 809850438);
    *(_QWORD *)(a1 + 2016) = Pool2;
    if ( !Pool2 )
    {
LABEL_29:
      v3 = -1073741670;
LABEL_30:
      LOBYTE(v8) = 1;
      FveReadWriteDeviceCleanup(a1, v8);
      goto LABEL_31;
    }
    v9 = *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v1 + 884) + 1592);
    v10 = MmSizeOfMdl(0, v9);
    ExInitializeNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016), 0, 0, 0x200u, v10 + v9 + 64, 0x70455646u, 0);
    v11 = 0;
  }
  *(_QWORD *)(a1 + 2024) = v11;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 2032));
  v12 = ExAllocatePool2(64, 5928, 2017809990);
  *(_QWORD *)(a1 + 2040) = v12;
  *(_BYTE *)(a1 + 2048) = 0;
  if ( !v12 )
    goto LABEL_29;
  for ( i = 0; i != 32; KeInitializeSpinLock((PKSPIN_LOCK)(v14 + 448 + 176 * i++)) )
  {
    v14 = *(_QWORD *)(a1 + 2040);
    v15 = 176 * i;
    *(_QWORD *)(v15 + v14 + 456) = 0;
    *(_QWORD *)(v15 + v14 + 464) = 0;
  }
  v16 = AcquireSubIrp(a1, a1 + 1592, *(unsigned int *)(v1 + 884), 0);
  *(_QWORD *)(a1 + 2056) = v16;
  *(_BYTE *)(a1 + 2064) = 0;
  if ( !v16 )
    goto LABEL_29;
  v17 = IoSizeofWorkItem();
  v18 = ExAllocatePool2(64, v17 + 184, 2001032774);
  *(_QWORD *)(a1 + 2072) = v18;
  *(_BYTE *)(a1 + 2080) = 0;
  if ( !v18 )
    goto LABEL_29;
  v19 = ExAllocatePool2(64, 4096, 1883592262);
  *(_QWORD *)(a1 + 2088) = v19;
  *(_BYTE *)(a1 + 2096) = 0;
  if ( !v19 )
    goto LABEL_29;
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( *(_QWORD *)(a1 + 5128) )
    {
      v20 = ExAllocatePool2(64, *(unsigned int *)(v1 + 10480), 809850438);
      *(_QWORD *)(a1 + 2176) = v20;
      *(_BYTE *)(a1 + 2184) = 0;
      if ( !v20 )
        goto LABEL_29;
    }
  }
  v21 = *(unsigned int *)(v1 + 884);
  v22 = 33 * *(_DWORD *)(a1 + 4 * v21 + 1604);
  v23 = *(_DWORD *)(a1 + 4 * v21 + 1592);
  *(_DWORD *)(a1 + 2120) = 1;
  *(_QWORD *)(a1 + 2128) = 0;
  *(_DWORD *)(a1 + 2136) = 0;
  KeInitializeEvent((PRKEVENT)(a1 + 2144), SynchronizationEvent, 0);
  if ( v22 <= v23 )
    v22 = v23;
  *(_QWORD *)(a1 + 2104) = MmAllocateMappingAddress(v22 + 4096, 0x72455646u);
  Mdl = IoAllocateMdl(0, v22 + 4096, 0, 0, 0);
  *(_QWORD *)(a1 + 2112) = Mdl;
  if ( !*(_QWORD *)(a1 + 2104) || !Mdl )
    goto LABEL_29;
  *(_QWORD *)(a1 + 2200) = a1 + 2192;
  *(_QWORD *)(a1 + 2192) = a1 + 2192;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 2208));
  v3 = FveWorkerInit(a1);
  if ( v3 < 0 )
    goto LABEL_30;
LABEL_31:
  KeReleaseMutex(v4, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400e9244  push    rbx
0x1400e9246  push    rbp
0x1400e9247  push    rsi
0x1400e9248  push    rdi
0x1400e9249  push    r14
0x1400e924b  push    r15
0x1400e924d  sub     rsp, 98h
0x1400e9254  mov     rdi, [rcx+8]
0x1400e9258  mov     rsi, rcx
0x1400e925b  xor     r14d, r14d
0x1400e925e  xor     r9d, r9d; Alertable
0x1400e9261  xor     r8d, r8d; WaitMode
0x1400e9264  mov     [rsp+0C8h+Timeout], r14; Timeout
0x1400e9269  xor     edx, edx; WaitReason
0x1400e926b  mov     ebx, r14d
0x1400e926e  lea     rbp, [rdi+2588h]
0x1400e9275  mov     rcx, rbp; Object
0x1400e9278  call    cs:__imp_KeWaitForSingleObject
0x1400e927f  nop     dword ptr [rax+rax+00h]
0x1400e9284  cmp     dword ptr [rsi+1268h], 1
0x1400e928b  jz      loc_1400E96F8
0x1400e9291  lock inc dword ptr [rsi+1268h]
0x1400e9298  xor     r9d, r9d
0x1400e929b  mov     [rsp+0C8h+Timeout], r14
0x1400e92a0  mov     r8, rsi
0x1400e92a3  xor     edx, edx
0x1400e92a5  mov     rcx, rdi
0x1400e92a8  call    FveLoadIoCryptoConfig
0x1400e92ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e92b4  lea     rbx, WPP_GLOBAL_Control
0x1400e92bb  cmp     rcx, rbx
0x1400e92be  jz      loc_1400E93EE
0x1400e92c4  mov     eax, [rcx+2Ch]
0x1400e92c7  test    al, al
0x1400e92c9  jns     loc_1400E9388
0x1400e92cf  cmp     byte ptr [rcx+29h], 4
0x1400e92d3  jb      loc_1400E9388
0x1400e92d9  mov     r8d, [rdi+374h]
0x1400e92e0  lea     edx, [r14+3Ah]
0x1400e92e4  mov     rcx, [rcx+18h]
0x1400e92e8  mov     r9, rsi
0x1400e92eb  mov     eax, [rsi+r8*4+6D4h]
0x1400e92f3  mov     [rsp+0C8h+var_48], eax
0x1400e92fa  mov     eax, [rsi+r8*4+6C8h]
0x1400e9302  mov     [rsp+0C8h+var_50], eax
0x1400e9306  mov     eax, [rsi+r8*4+6BCh]
0x1400e930e  mov     [rsp+0C8h+var_58], eax
0x1400e9312  mov     eax, [rsi+r8*4+6B0h]
0x1400e931a  mov     [rsp+0C8h+var_60], eax
0x1400e931e  mov     eax, [rsi+r8*4+6A4h]
0x1400e9326  mov     [rsp+0C8h+var_68], eax
0x1400e932a  mov     eax, [rsi+r8*4+698h]
0x1400e9332  mov     [rsp+0C8h+var_70], eax
0x1400e9336  mov     eax, [rsi+r8*4+68Ch]
0x1400e933e  mov     [rsp+0C8h+var_78], eax
0x1400e9342  mov     eax, [rsi+r8*4+674h]
0x1400e934a  mov     [rsp+0C8h+var_80], eax
0x1400e934e  mov     eax, [rsi+r8*4+668h]
0x1400e9356  mov     [rsp+0C8h+var_88], eax
0x1400e935a  mov     eax, [rsi+r8*4+650h]
0x1400e9362  mov     [rsp+0C8h+var_90], eax
0x1400e9366  mov     eax, [rsi+r8*4+644h]
0x1400e936e  mov     dword ptr [rsp+0C8h+Depth], eax
0x1400e9372  mov     eax, [rsi+r8*4+638h]
0x1400e937a  mov     [rsp+0C8h+Tag], eax
0x1400e937e  mov     dword ptr [rsp+0C8h+Timeout], r8d
0x1400e9383  call    WPP_SF_qLDDDDDDDDDDDD
0x1400e9388  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e938f  cmp     rcx, rbx
0x1400e9392  jz      short loc_1400E93EE
0x1400e9394  mov     eax, [rcx+2Ch]
0x1400e9397  test    al, al
0x1400e9399  jns     short loc_1400E93EE
0x1400e939b  cmp     byte ptr [rcx+29h], 4
0x1400e939f  jb      short loc_1400E93EE
0x1400e93a1  mov     r8d, [rdi+374h]
0x1400e93a8  mov     edx, 3Bh ; ';'
0x1400e93ad  mov     rcx, [rcx+18h]
0x1400e93b1  mov     r9, rsi
0x1400e93b4  mov     eax, [rdi+r8*4+3F0h]
0x1400e93bc  mov     [rsp+0C8h+var_88], eax
0x1400e93c0  mov     eax, [rdi+r8*4+3CCh]
0x1400e93c8  mov     [rsp+0C8h+var_90], eax
0x1400e93cc  mov     eax, [rsi+r8*4+6ECh]
0x1400e93d4  mov     dword ptr [rsp+0C8h+Depth], eax
0x1400e93d8  mov     eax, [rsi+r8*4+6E0h]
0x1400e93e0  mov     [rsp+0C8h+Tag], eax
0x1400e93e4  mov     dword ptr [rsp+0C8h+Timeout], r8d
0x1400e93e9  call    WPP_SF_qLDDDD
0x1400e93ee  mov     ecx, [rdi+374h]
0x1400e93f4  mov     r15d, 40h ; '@'
0x1400e93fa  mov     eax, [rdi+rcx*4+3A8h]
0x1400e9401  cmp     [rsi+rcx*4+638h], eax
0x1400e9408  jz      loc_1400E949A
0x1400e940e  lea     edx, [r15+40h]
0x1400e9412  mov     r8d, 30455646h
0x1400e9418  mov     ecx, r15d
0x1400e941b  call    cs:__imp_ExAllocatePool2
0x1400e9422  nop     dword ptr [rax+rax+00h]
0x1400e9427  mov     [rsi+7E0h], rax
0x1400e942e  test    rax, rax
0x1400e9431  jz      loc_1400E96E9
0x1400e9437  mov     eax, [rdi+374h]
0x1400e943d  xor     ecx, ecx; Base
0x1400e943f  mov     ebx, [rsi+rax*4+638h]
0x1400e9446  mov     eax, [rdi+374h]
0x1400e944c  mov     edx, [rsi+rax*4+638h]; Length
0x1400e9453  call    cs:__imp_MmSizeOfMdl
0x1400e945a  nop     dword ptr [rax+rax+00h]
0x1400e945f  mov     rcx, [rsi+7E0h]; Lookaside
0x1400e9466  lea     edx, [rbx+40h]
0x1400e9469  add     edx, eax
0x1400e946b  mov     [rsp+0C8h+Depth], r14w; Depth
0x1400e9471  mov     [rsp+0C8h+Tag], 70455646h; Tag
0x1400e9479  mov     r9d, 200h; Flags
0x1400e947f  mov     [rsp+0C8h+Timeout], rdx; Size
0x1400e9484  xor     r8d, r8d; Free
0x1400e9487  xor     edx, edx; Allocate
0x1400e9489  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400e9490  nop     dword ptr [rax+rax+00h]
0x1400e9495  mov     rax, r14
0x1400e9498  jmp     short loc_1400E94AF
0x1400e949a  mov     rax, [rdi+2330h]
0x1400e94a1  mov     [rsi+7E0h], rax
0x1400e94a8  mov     rax, [rdi+2338h]
0x1400e94af  lea     rcx, [rsi+7F0h]; SpinLock
0x1400e94b6  mov     [rsi+7E8h], rax
0x1400e94bd  call    cs:__imp_KeInitializeSpinLock
0x1400e94c4  nop     dword ptr [rax+rax+00h]
0x1400e94c9  mov     edx, 1728h
0x1400e94ce  mov     r8d, 78455646h
0x1400e94d4  mov     rcx, r15
0x1400e94d7  call    cs:__imp_ExAllocatePool2
0x1400e94de  nop     dword ptr [rax+rax+00h]
0x1400e94e3  mov     [rsi+7F8h], rax
0x1400e94ea  mov     [rsi+800h], r14b
0x1400e94f1  test    rax, rax
0x1400e94f4  jz      loc_1400E96E9
0x1400e94fa  mov     rbx, r14
0x1400e94fd  mov     rax, [rsi+7F8h]
0x1400e9504  imul    rcx, rbx, 0B0h
0x1400e950b  mov     [rcx+rax+1C8h], r14
0x1400e9513  mov     [rcx+rax+1D0h], r14
0x1400e951b  add     rax, 1C0h
0x1400e9521  add     rcx, rax; SpinLock
0x1400e9524  call    cs:__imp_KeInitializeSpinLock
0x1400e952b  nop     dword ptr [rax+rax+00h]
0x1400e9530  inc     rbx
0x1400e9533  cmp     rbx, 20h ; ' '
0x1400e9537  jnz     short loc_1400E94FD
0x1400e9539  mov     r8d, [rdi+374h]
0x1400e9540  lea     rdx, [rsi+638h]
0x1400e9547  xor     r9d, r9d
0x1400e954a  mov     rcx, rsi
0x1400e954d  call    AcquireSubIrp
0x1400e9552  mov     [rsi+808h], rax
0x1400e9559  mov     [rsi+810h], r14b
0x1400e9560  test    rax, rax
0x1400e9563  jz      loc_1400E96E9
0x1400e9569  call    cs:__imp_IoSizeofWorkItem
0x1400e9570  nop     dword ptr [rax+rax+00h]
0x1400e9575  mov     r8d, 77455646h
0x1400e957b  mov     rcx, r15
0x1400e957e  lea     edx, [rax+0B8h]
0x1400e9584  call    cs:__imp_ExAllocatePool2
0x1400e958b  nop     dword ptr [rax+rax+00h]
0x1400e9590  mov     [rsi+818h], rax
0x1400e9597  mov     [rsi+820h], r14b
0x1400e959e  test    rax, rax
0x1400e95a1  jz      loc_1400E96E9
0x1400e95a7  mov     edx, 1000h
0x1400e95ac  mov     r8d, 70455646h
0x1400e95b2  mov     rcx, r15
0x1400e95b5  call    cs:__imp_ExAllocatePool2
0x1400e95bc  nop     dword ptr [rax+rax+00h]
0x1400e95c1  mov     [rsi+828h], rax
0x1400e95c8  mov     [rsi+830h], r14b
0x1400e95cf  test    rax, rax
0x1400e95d2  jz      loc_1400E96E9
0x1400e95d8  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400e95dd  test    eax, eax
0x1400e95df  jz      short loc_1400E961C
0x1400e95e1  cmp     [rsi+1408h], r14
0x1400e95e8  jz      short loc_1400E961C
0x1400e95ea  mov     edx, [rdi+28F0h]
0x1400e95f0  mov     r8d, 30455646h
0x1400e95f6  mov     rcx, r15
0x1400e95f9  call    cs:__imp_ExAllocatePool2
0x1400e9600  nop     dword ptr [rax+rax+00h]
0x1400e9605  mov     [rsi+880h], rax
0x1400e960c  mov     [rsi+888h], r14b
0x1400e9613  test    rax, rax
0x1400e9616  jz      loc_1400E96E9
0x1400e961c  mov     eax, [rdi+374h]
0x1400e9622  lea     rcx, [rsi+860h]; Event
0x1400e9629  xor     r8d, r8d; State
0x1400e962c  imul    edi, [rsi+rax*4+644h], 21h ; '!'
0x1400e9634  mov     ebx, [rsi+rax*4+638h]
0x1400e963b  lea     edx, [r8+1]; Type
0x1400e963f  mov     dword ptr [rsi+848h], 1
0x1400e9649  mov     [rsi+850h], r14
0x1400e9650  mov     [rsi+858h], r14d
0x1400e9657  call    cs:__imp_KeInitializeEvent
0x1400e965e  nop     dword ptr [rax+rax+00h]
0x1400e9663  cmp     edi, ebx
0x1400e9665  mov     edx, 72455646h; PoolTag
0x1400e966a  cmovbe  edi, ebx
0x1400e966d  lea     ebx, [rdi+1000h]
0x1400e9673  mov     ecx, ebx; NumberOfBytes
0x1400e9675  call    cs:__imp_MmAllocateMappingAddress
0x1400e967c  nop     dword ptr [rax+rax+00h]
0x1400e9681  xor     r9d, r9d; ChargeQuota
0x1400e9684  mov     [rsp+0C8h+Timeout], r14; Irp
0x1400e9689  xor     r8d, r8d; SecondaryBuffer
0x1400e968c  mov     [rsi+838h], rax
0x1400e9693  mov     edx, ebx; Length
0x1400e9695  xor     ecx, ecx; VirtualAddress
0x1400e9697  call    cs:__imp_IoAllocateMdl
0x1400e969e  nop     dword ptr [rax+rax+00h]
0x1400e96a3  mov     [rsi+840h], rax
0x1400e96aa  cmp     [rsi+838h], r14
0x1400e96b1  jz      short loc_1400E96E9
0x1400e96b3  test    rax, rax
0x1400e96b6  jz      short loc_1400E96E9
0x1400e96b8  lea     rax, [rsi+890h]
0x1400e96bf  lea     rcx, [rsi+8A0h]; SpinLock
0x1400e96c6  mov     [rax+8], rax
0x1400e96ca  mov     [rax], rax
0x1400e96cd  call    cs:__imp_KeInitializeSpinLock
0x1400e96d4  nop     dword ptr [rax+rax+00h]
0x1400e96d9  mov     rcx, rsi
0x1400e96dc  call    FveWorkerInit
0x1400e96e1  mov     ebx, eax
0x1400e96e3  test    eax, eax
0x1400e96e5  jns     short loc_1400E96F8
0x1400e96e7  jmp     short loc_1400E96EE
0x1400e96e9  mov     ebx, 0C000009Ah
0x1400e96ee  mov     dl, 1
0x1400e96f0  mov     rcx, rsi
0x1400e96f3  call    FveReadWriteDeviceCleanup
0x1400e96f8  xor     edx, edx; Wait
0x1400e96fa  mov     rcx, rbp; Mutex
0x1400e96fd  call    cs:__imp_KeReleaseMutex
0x1400e9704  nop     dword ptr [rax+rax+00h]
0x1400e9709  mov     eax, ebx
0x1400e970b  add     rsp, 98h
0x1400e9712  pop     r15
0x1400e9714  pop     r14
0x1400e9716  pop     rdi
0x1400e9717  pop     rsi
0x1400e9718  pop     rbp
0x1400e9719  pop     rbx
0x1400e971a  retn
```
