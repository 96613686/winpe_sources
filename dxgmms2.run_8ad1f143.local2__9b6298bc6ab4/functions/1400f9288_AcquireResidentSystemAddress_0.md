# AcquireResidentSystemAddress_0

- ea: `0x1400f9288`
- end: `0x1400f95ab`
- name: `AcquireResidentSystemAddress_0`
- size: `803`
- prototype: `PVOID __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f9270`

## callees

- `0x1400045ec`
- `0x1400bd6ac`
- `0x1400c9160`
- `0x1400f9288`
- `0x1400f95b4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400f9553`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400f9553`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400f93e5`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400f93e5`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400f9332`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400f9332`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f9479`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f9479`
- `watchdog!WdLogSingleEntry5` at `0x1400f9595`
- `watchdog!WdLogSingleEntry5` at `0x1400f9595`
- `watchdog!WdLogSingleEntry0` at `0x1400f9438`
- `watchdog!WdLogSingleEntry0` at `0x1400f94f1`
- `watchdog!WdLogSingleEntry0` at `0x1400f9438`
- `watchdog!WdLogSingleEntry0` at `0x1400f94f1`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f956d`

## string_xrefs

- `0x1400f9449`: `Failed to create system space mapping for MDL`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
PVOID __fastcall AcquireResidentSystemAddress_0(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r11
  int v7; // eax
  unsigned __int64 v8; // rdx
  PVOID result; // rax
  unsigned __int64 v10; // r8
  const struct _MDL *v11; // rcx
  __int64 v12; // r9
  int v13; // eax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdi
  _QWORD *v16; // r11
  __int64 v17; // r9
  unsigned int v18; // r8d
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // r8d
  __int64 v22; // r9
  unsigned int v23; // r8d
  struct _MDL **v24; // r9
  struct _MDL *v25; // rax
  int v26; // ecx
  int v27; // r8d
  __int64 v28; // [rsp+88h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 136);
  v7 = *(_DWORD *)(v3 + 64);
  if ( (v7 & 0x1000) != 0 )
    return *(PVOID *)(*(_QWORD *)a2 + 224LL);
  if ( (v7 & 0x2000) != 0 )
  {
    v8 = *(_QWORD *)(a2 + 144);
    v28 = 0;
    if ( *(_BYTE *)(a3 + 16) )
      return VIDMM_MEMORY_SEGMENT::GetAddressForPageTableInCpuHostAperture(
               (VIDMM_MEMORY_SEGMENT *)v3,
               v8,
               *(_DWORD *)(a2 + 16));
    if ( (int)AcquireResidentSystemAddressInCpuHostAperture(
                (struct VIDMM_PHYSICAL_ALLOC *)a2,
                v8,
                *(VIDMM_CPU_HOST_APERTURE **)(v3 + 512),
                a3,
                (__int64)&v28) >= 0 )
      return (PVOID)v28;
    return 0;
  }
  if ( (v7 & 4) == 0 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 73);
    WdLogGlobalForLineNumber = 222;
    JUMPOUT(0x1400F95ABLL);
  }
  v10 = *(_QWORD *)(a2 + 144);
  v11 = *(const struct _MDL **)(v3 + 32);
  v12 = (__int64)v11 + v10;
  v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL) + 444LL);
  if ( *(_BYTE *)(a3 + 16) )
  {
    v14 = *(_QWORD *)(a2 + 16);
    v15 = v14 >> 12;
    v16 = (_QWORD *)(*(_QWORD *)(a1 + 2240) + 48LL);
    if ( (v13 & 8) != 0 )
    {
      v22 = (v10 >> 12) + 6;
      v23 = 0;
      v24 = &v11->Next + v22;
      if ( v15 )
      {
        do
        {
          ++v23;
          *v16 = *v24++;
          v14 = *(_QWORD *)(a2 + 16);
          ++v16;
        }
        while ( v23 < v14 >> 12 );
      }
    }
    else
    {
      v17 = v12 >> 12;
      v18 = 0;
      if ( v15 )
      {
        do
        {
          ++v18;
          *v16 = v17++;
          v14 = *(_QWORD *)(a2 + 16);
          ++v16;
        }
        while ( v18 < v14 >> 12 );
      }
    }
    v19 = *(_QWORD *)(a1 + 2240);
    *(_DWORD *)(v19 + 40) = v14;
    *(_WORD *)(v19 + 8) = 8 * (((v14 + 4095) >> 12) + 6);
    *(_QWORD *)v19 = 0;
    *(_WORD *)(v19 + 10) = 0;
    *(_QWORD *)(v19 + 32) = 0;
    *(_DWORD *)(v19 + 44) = 0;
    *(_WORD *)(*(_QWORD *)(a1 + 2240) + 10LL) |= 0x802u;
    return MmMapLockedPagesWithReservedMapping(
             *(PVOID *)(a1 + 2232),
             0x6D4D6956u,
             *(PMDL *)(a1 + 2240),
             MmWriteCombined);
  }
  else
  {
    if ( (v13 & 8) == 0 )
      return (PVOID)MmMapIoSpaceEx(v12, *(_QWORD *)(a2 + 16), 1028);
    v25 = VidMmiBuildMdlFromMdl(*(_QWORD *)(a2 + 16), v11, v10 >> 12);
    *(_QWORD *)a3 = v25;
    if ( !v25 )
    {
      _InterlockedIncrement(&dword_140086794);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1377;
      DxgkLogInternalTriageEvent(
        v26,
        262145,
        v27,
        (unsigned int)L"Failed to build SoftGPU MDL system address",
        1377,
        0,
        0,
        0);
      return 0;
    }
    v25->MdlFlags |= 0x802u;
    result = MmMapLockedPagesSpecifyCache(*(PMDL *)a3, 0, MmCached, 0, 0, 0x40000010u);
    if ( !result )
    {
      _InterlockedIncrement(&dword_1400868C8);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1400;
      DxgkLogInternalTriageEvent(
        v20,
        262145,
        v21,
        (unsigned int)L"Failed to create system space mapping for MDL",
        1400,
        0,
        0,
        0);
      ExFreePoolWithTag(*(PVOID *)a3, 0);
      *(_QWORD *)a3 = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400f9288  push    rbx
0x1400f928a  push    rbp
0x1400f928b  push    rsi
0x1400f928c  push    rdi
0x1400f928d  sub     rsp, 58h
0x1400f9291  mov     r11, [rdx+88h]
0x1400f9298  mov     rdi, r8
0x1400f929b  mov     r10, rdx
0x1400f929e  mov     rsi, rcx
0x1400f92a1  mov     eax, [r11+40h]
0x1400f92a5  bt      eax, 0Ch
0x1400f92a9  jb      short loc_1400F92E2
0x1400f92ab  bt      eax, 0Dh
0x1400f92af  jnb     short loc_1400F92EE
0x1400f92b1  mov     rdx, [rdx+90h]; unsigned __int64
0x1400f92b8  xor     ebx, ebx
0x1400f92ba  mov     [rsp+78h+arg_8], rbx
0x1400f92c2  cmp     [r8+10h], bl
0x1400f92c6  jz      loc_1400F93F6
0x1400f92cc  mov     r8d, [r10+10h]; unsigned int
0x1400f92d0  mov     rcx, r11; this
0x1400f92d3  call    ?GetAddressForPageTableInCpuHostAperture@VIDMM_MEMORY_SEGMENT@@QEAAPEAX_KI@Z; VIDMM_MEMORY_SEGMENT::GetAddressForPageTableInCpuHostAperture(unsigned __int64,uint)
0x1400f92d8  add     rsp, 58h
0x1400f92dc  pop     rdi
0x1400f92dd  pop     rsi
0x1400f92de  pop     rbp
0x1400f92df  pop     rbx
0x1400f92e0  retn
0x1400f92e2  mov     rax, [rdx]
0x1400f92e5  mov     rax, [rax+0E0h]
0x1400f92ec  jmp     short loc_1400F92D8
0x1400f92ee  test    al, 4
0x1400f92f0  jz      loc_1400F956D
0x1400f92f6  mov     rax, [rsi+38h]
0x1400f92fa  xor     ebx, ebx
0x1400f92fc  mov     r8, [rdx+90h]
0x1400f9303  mov     rcx, [r11+20h]
0x1400f9307  mov     rbp, [rax+18h]
0x1400f930b  lea     r9, [rcx+r8]
0x1400f930f  mov     eax, [rbp+1BCh]
0x1400f9315  cmp     [rdi+10h], bl
0x1400f9318  jnz     short loc_1400F9340
0x1400f931a  mov     r11, [rdx+10h]
0x1400f931e  test    al, 8
0x1400f9320  jnz     loc_1400F94D0
0x1400f9326  mov     r8d, 404h
0x1400f932c  mov     rdx, r11
0x1400f932f  mov     rcx, r9
0x1400f9332  call    cs:__imp_MmMapIoSpaceEx
0x1400f9339  nop     dword ptr [rax+rax+00h]
0x1400f933e  jmp     short loc_1400F92D8
0x1400f9340  mov     rdx, [rdx+10h]
0x1400f9344  mov     r11, [rsi+8C0h]
0x1400f934b  mov     rdi, rdx
0x1400f934e  shr     rdi, 0Ch
0x1400f9352  add     r11, 30h ; '0'
0x1400f9356  test    al, 8
0x1400f9358  jnz     loc_1400F948F
0x1400f935e  sar     r9, 0Ch
0x1400f9362  mov     r8d, ebx
0x1400f9365  test    rdi, rdi
0x1400f9368  jz      short loc_1400F938D
0x1400f936a  mov     rax, r9
0x1400f936d  inc     r8d
0x1400f9370  mov     [r11], rax
0x1400f9373  inc     r9
0x1400f9376  mov     rdx, [r10+10h]
0x1400f937a  lea     r11, [r11+8]
0x1400f937e  mov     rcx, rdx
0x1400f9381  mov     eax, r8d
0x1400f9384  shr     rcx, 0Ch
0x1400f9388  cmp     rax, rcx
0x1400f938b  jb      short loc_1400F936A
0x1400f938d  mov     rcx, [rsi+8C0h]
0x1400f9394  lea     rax, [rdx+0FFFh]
0x1400f939b  shr     rax, 0Ch
0x1400f939f  mov     r9d, 2; CacheType
0x1400f93a5  add     ax, 6
0x1400f93a9  shl     ax, 3
0x1400f93ad  mov     [rcx+28h], edx
0x1400f93b0  mov     edx, 6D4D6956h; PoolTag
0x1400f93b5  mov     [rcx+8], ax
0x1400f93b9  mov     [rcx], rbx
0x1400f93bc  mov     [rcx+0Ah], bx
0x1400f93c0  mov     [rcx+20h], rbx
0x1400f93c4  mov     [rcx+2Ch], ebx
0x1400f93c7  mov     ecx, 802h
0x1400f93cc  mov     rax, [rsi+8C0h]
0x1400f93d3  or      [rax+0Ah], cx
0x1400f93d7  mov     r8, [rsi+8C0h]; MemoryDescriptorList
0x1400f93de  mov     rcx, [rsi+8B8h]; MappingAddress
0x1400f93e5  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400f93ec  nop     dword ptr [rax+rax+00h]
0x1400f93f1  jmp     loc_1400F92D8
0x1400f93f6  lea     rax, [rsp+78h+arg_8]
0x1400f93fe  mov     rcx, r10; struct VIDMM_PHYSICAL_ALLOC *
0x1400f9401  lea     r9, [r8+8]
0x1400f9405  mov     qword ptr [rsp+78h+Priority], rax; __int64
0x1400f940a  mov     r8, [r11+200h]; this
0x1400f9411  mov     qword ptr [rsp+78h+BugCheckOnFailure], rdi; __int64
0x1400f9416  call    AcquireResidentSystemAddressInCpuHostAperture
0x1400f941b  test    eax, eax
0x1400f941d  js      short loc_1400F9488
0x1400f941f  mov     rax, [rsp+78h+arg_8]
0x1400f9427  jmp     loc_1400F92D8
0x1400f942c  lock inc cs:dword_1400868C8
0x1400f9433  mov     ecx, 6
0x1400f9438  call    cs:__imp_WdLogSingleEntry0
0x1400f943f  nop     dword ptr [rax+rax+00h]
0x1400f9444  mov     [rsp+78h+var_40], rbx
0x1400f9449  lea     r9, aFailedToCreate_0; "Failed to create system space mapping f"...
0x1400f9450  mov     eax, 578h
0x1400f9455  mov     [rsp+78h+var_48], rbx
0x1400f945a  mov     qword ptr [rsp+78h+Priority], rbx
0x1400f945f  mov     edx, 40001h
0x1400f9464  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f946a  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1400f946f  call    DxgkLogInternalTriageEvent
0x1400f9474  mov     rcx, [rdi]; P
0x1400f9477  xor     edx, edx; Tag
0x1400f9479  call    cs:__imp_ExFreePoolWithTag
0x1400f9480  nop     dword ptr [rax+rax+00h]
0x1400f9485  mov     [rdi], rbx
0x1400f9488  xor     eax, eax
0x1400f948a  jmp     loc_1400F92D8
0x1400f948f  shr     r8, 0Ch
0x1400f9493  lea     r9, [r8+6]
0x1400f9497  mov     r8d, ebx
0x1400f949a  lea     r9, [rcx+r9*8]
0x1400f949e  test    rdi, rdi
0x1400f94a1  jz      loc_1400F938D
0x1400f94a7  mov     rax, [r9]
0x1400f94aa  inc     r8d
0x1400f94ad  mov     [r11], rax
0x1400f94b0  lea     r9, [r9+8]
0x1400f94b4  mov     rdx, [r10+10h]
0x1400f94b8  lea     r11, [r11+8]
0x1400f94bc  mov     rcx, rdx
0x1400f94bf  mov     eax, r8d
0x1400f94c2  shr     rcx, 0Ch
0x1400f94c6  cmp     rax, rcx
0x1400f94c9  jb      short loc_1400F94A7
0x1400f94cb  jmp     loc_1400F938D
0x1400f94d0  mov     rdx, rcx; struct _MDL *
0x1400f94d3  shr     r8, 0Ch; unsigned __int64
0x1400f94d7  mov     rcx, r11; Length
0x1400f94da  call    ?VidMmiBuildMdlFromMdl@@YAPEAU_MDL@@_KPEBU1@0@Z; VidMmiBuildMdlFromMdl(unsigned __int64,_MDL const *,unsigned __int64)
0x1400f94df  mov     [rdi], rax
0x1400f94e2  test    rax, rax
0x1400f94e5  jnz     short loc_1400F9532
0x1400f94e7  lock inc cs:dword_140086794
0x1400f94ee  lea     ecx, [rax+6]
0x1400f94f1  call    cs:__imp_WdLogSingleEntry0
0x1400f94f8  nop     dword ptr [rax+rax+00h]
0x1400f94fd  mov     [rsp+78h+var_40], rbx
0x1400f9502  lea     r9, aFailedToBuildS; "Failed to build SoftGPU MDL system addr"...
0x1400f9509  mov     eax, 561h
0x1400f950e  mov     [rsp+78h+var_48], rbx
0x1400f9513  mov     qword ptr [rsp+78h+Priority], rbx
0x1400f9518  mov     edx, 40001h
0x1400f951d  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f9523  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1400f9528  call    DxgkLogInternalTriageEvent
0x1400f952d  jmp     loc_1400F9488
0x1400f9532  xor     r9d, r9d; RequestedAddress
0x1400f9535  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400f953d  mov     ecx, 802h
0x1400f9542  mov     [rsp+78h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x1400f9546  or      [rax+0Ah], cx
0x1400f954a  xor     edx, edx; AccessMode
0x1400f954c  mov     rcx, [rdi]; MemoryDescriptorList
0x1400f954f  lea     r8d, [r9+1]; CacheType
0x1400f9553  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400f955a  nop     dword ptr [rax+rax+00h]
0x1400f955f  test    rax, rax
0x1400f9562  jnz     loc_1400F92D8
0x1400f9568  jmp     loc_1400F942C
0x1400f956d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f9574  mov     rcx, [rdx]
0x1400f9577  mov     dword ptr [rax], 1
0x1400f957d  mov     qword ptr [rsp+78h+Priority], r11
0x1400f9582  mov     r9, rsi
0x1400f9585  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx
0x1400f958a  mov     edx, 10Eh
0x1400f958f  xor     ecx, ecx
0x1400f9591  lea     r8d, [rcx+49h]
0x1400f9595  call    cs:__imp_WdLogSingleEntry5
0x1400f959c  nop     dword ptr [rax+rax+00h]
0x1400f95a1  mov     cs:WdLogGlobalForLineNumber, 0DEh
```
