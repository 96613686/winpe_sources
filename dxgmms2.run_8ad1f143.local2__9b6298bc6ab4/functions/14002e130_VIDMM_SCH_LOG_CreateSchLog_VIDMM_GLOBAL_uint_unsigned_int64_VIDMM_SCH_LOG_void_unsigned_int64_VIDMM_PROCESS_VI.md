# VIDMM_SCH_LOG::CreateSchLog(VIDMM_GLOBAL *,uint,unsigned __int64,VIDMM_SCH_LOG * *,void * *,unsigned __int64 *,VIDMM_PROCESS *,VIDMM_SCH_LOG_TYPE)

- ea: `0x14002e130`
- end: `0x14002e75d`
- name: `?CreateSchLog@VIDMM_SCH_LOG@@SAJPEAVVIDMM_GLOBAL@@I_KPEAPEAV1@PEAPEAXPEA_KPEAVVIDMM_PROCESS@@W4VIDMM_SCH_LOG_TYPE@@@Z`
- size: `1581`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *, int, __int64, __int64 *, _QWORD *, _QWORD *, VIDMM_PROCESS *, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14002deb8`
- `0x140054148`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002e130`
- `0x14002e850`
- `0x14002e950`
- `0x140032d3c`
- `0x140032d60`
- `0x14003ea98`
- `0x140044190`
- `0x14005846c`
- `0x140058ac0`
- `0x1400c3064`
- `0x1400dfe1c`
- `0x1400ea1dc`
- `0x1400edb04`
- `0x1400fa2ac`
- `0x14010aa7c`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x14002e41e`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002e41e`
- `ntoskrnl!MmCreateSection` at `0x14002e2d8`
- `ntoskrnl!MmCreateSection` at `0x14002e2d8`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14002e35f`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14002e35f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002e1e1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002e1e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002e1ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002e1ed`
- `watchdog!WdLogSingleEntry0` at `0x14002e37e`
- `watchdog!WdLogSingleEntry0` at `0x14002e3d4`
- `watchdog!WdLogSingleEntry0` at `0x14002e483`
- `watchdog!WdLogSingleEntry0` at `0x14002e4c1`
- `watchdog!WdLogSingleEntry0` at `0x14002e534`
- `watchdog!WdLogSingleEntry0` at `0x14002e5bd`
- `watchdog!WdLogSingleEntry0` at `0x14002e651`
- `watchdog!WdLogSingleEntry0` at `0x14002e6af`
- `watchdog!WdLogSingleEntry0` at `0x14002e37e`
- `watchdog!WdLogSingleEntry0` at `0x14002e3d4`
- `watchdog!WdLogSingleEntry0` at `0x14002e483`
- `watchdog!WdLogSingleEntry0` at `0x14002e4c1`
- `watchdog!WdLogSingleEntry0` at `0x14002e534`
- `watchdog!WdLogSingleEntry0` at `0x14002e5bd`
- `watchdog!WdLogSingleEntry0` at `0x14002e651`
- `watchdog!WdLogSingleEntry0` at `0x14002e6af`
- `watchdog!WdLogSingleEntry1` at `0x14002e2fa`
- `watchdog!WdLogSingleEntry1` at `0x14002e455`
- `watchdog!WdLogSingleEntry1` at `0x14002e2fa`
- `watchdog!WdLogSingleEntry1` at `0x14002e455`

## string_xrefs

- `0x14002e324`: `Failed to create section for VidMm scheduler log, Status=0x%.8x`

## pseudocode

```c
__int64 __fastcall VIDMM_SCH_LOG::CreateSchLog(
        VIDMM_GLOBAL *a1,
        int a2,
        __int64 a3,
        __int64 *a4,
        _QWORD *a5,
        _QWORD *a6,
        VIDMM_PROCESS *a7,
        int a8)
{
  bool v12; // r8
  VIDMM_PROCESS *v13; // r14
  unsigned int v14; // edx
  __int64 v15; // rsi
  __int64 v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rax
  SIZE_T v19; // r15
  int v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // ecx
  int v24; // r8d
  struct _MDL *Mdl; // rax
  int v26; // ecx
  int v27; // r8d
  int LogicalMemory; // eax
  unsigned __int64 v29; // r8
  CVirtualAddressAllocator *VaAllocator; // r12
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // r9
  __int64 v33; // rax
  unsigned __int64 v34; // rax
  int v35; // r14d
  __int64 v36; // rax
  unsigned __int64 LogicalAddress; // rax
  __int64 v39; // [rsp+80h] [rbp-B8h] BYREF
  char v40; // [rsp+88h] [rbp-B0h]
  unsigned __int64 v41; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+98h] [rbp-A0h] BYREF
  _QWORD v43[19]; // [rsp+A0h] [rbp-98h] BYREF
  SIZE_T v44; // [rsp+140h] [rbp+8h] BYREF
  int v45; // [rsp+148h] [rbp+10h]
  SIZE_T v46; // [rsp+150h] [rbp+18h] BYREF
  __int64 *v47; // [rsp+158h] [rbp+20h]

  v47 = a4;
  v45 = a2;
  v42 = 0;
  v44 = 0;
  memset(v43, 0, 0x58u);
  v41 = 0;
  v46 = 0;
  v13 = a7;
  if ( !a7 )
    v13 = g_pVidMmSystemProcess;
  DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(
    (DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&v39,
    (struct DXGPUSHLOCKFAST *)(*(_QWORD *)a1 + 152LL),
    v12);
  if ( *(_BYTE *)(*(_QWORD *)a1 + 228LL) != 1 )
  {
    v15 = 0;
    LODWORD(v16) = -1073741801;
    if ( v40 )
    {
      v17 = v39;
      *(_QWORD *)(v39 + 8) = 0;
      ExReleasePushLockExclusiveEx(v17, 0);
      KeLeaveCriticalRegion();
    }
    goto LABEL_35;
  }
  v18 = operator new(104, 1697999190, 256);
  v15 = v18;
  if ( v18 )
  {
    *(_QWORD *)v18 = 0;
    *(_OWORD *)(v18 + 8) = 0;
    *(_DWORD *)(v18 + 24) = 0;
    *(_QWORD *)(v18 + 32) = 0;
    *(_QWORD *)(v18 + 40) = 0;
    *(_QWORD *)(v18 + 48) = 0;
    *(_QWORD *)(v18 + 56) = 0;
    *(_QWORD *)(v18 + 64) = 0;
    *(_QWORD *)(v18 + 72) = 0;
    *(_QWORD *)(v18 + 80) = 0;
    *(_BYTE *)(v18 + 88) = 0;
    *(_DWORD *)(v18 + 92) = 0;
    *(_QWORD *)(v18 + 96) = 0;
  }
  else
  {
    v15 = 0;
  }
  a7 = (VIDMM_PROCESS *)v15;
  if ( !v15 )
    goto LABEL_10;
  v19 = a3 - (((_WORD)a3 - 1) & 0xFFF) + 4095;
  *(_QWORD *)v15 = a1;
  *(_DWORD *)(v15 + 24) = a2;
  *(_QWORD *)(v15 + 32) = v19;
  *(_DWORD *)(v15 + 92) = a8;
  *(_QWORD *)(v15 + 96) = v13;
  v44 = v19;
  v20 = MmCreateSection(v15 + 40, 0, 0, &v44, 4, 0x8000000, 0, 0);
  v16 = v20;
  if ( v20 < 0 )
  {
    _InterlockedIncrement(&dword_14008683C);
    WdLogSingleEntry1(6, v20);
    WdLogGlobalForLineNumber = 142;
    DxgkLogInternalTriageEvent(
      v21,
      262145,
      v22,
      (unsigned int)L"Failed to create section for VidMm scheduler log, Status=0x%.8x",
      v16,
      0,
      0,
      0);
    goto LABEL_11;
  }
  v46 = v19;
  LODWORD(v16) = MmMapViewInSystemSpaceEx(*(_QWORD *)(v15 + 40), v15 + 48, &v46, &v42, 0);
  if ( (int)v16 < 0 )
  {
    _InterlockedIncrement(&dword_1400867CC);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 158;
    DxgkLogInternalTriageEvent(
      v23,
      262145,
      v24,
      (unsigned int)L"Failed to map view of section for VidMm scheduler log",
      158,
      0,
      0,
      0);
    goto LABEL_11;
  }
  Mdl = VidMmiAllocateMdl(*(PVOID *)(v15 + 48), v19);
  *(_QWORD *)(v15 + 72) = Mdl;
  if ( !Mdl )
  {
    _InterlockedIncrement(&dword_140086840);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 171;
    DxgkLogInternalTriageEvent(
      v26,
      262145,
      v27,
      (unsigned int)L"Failed to allocate Mdl for VidMm scheduler log",
      171,
      0,
      0,
      0);
LABEL_10:
    LODWORD(v16) = -1073741801;
LABEL_11:
    DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release((DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&v39);
    goto LABEL_35;
  }
  MmProbeAndLockPages(Mdl, 0, IoModifyAccess);
  LogicalMemory = SysMmAllocateLogicalMemory(
                    *(struct SYSMM_ADAPTER **)(*((_QWORD *)a1 + 3) + 224LL),
                    *(_QWORD *)(v15 + 32),
                    (const void *)v15,
                    (void **)(v15 + 80));
  LODWORD(v16) = LogicalMemory;
  if ( LogicalMemory < 0 )
  {
    WdLogSingleEntry1(3, LogicalMemory);
    WdLogGlobalForLineNumber = 202;
    goto LABEL_11;
  }
  VaAllocator = VIDMM_SCH_LOG::GetVaAllocator((VIDMM_SCH_LOG *)v15);
  if ( VaAllocator )
  {
    if ( a8 )
    {
      v33 = *((_QWORD *)a1 + 3);
      v32 = *(_QWORD *)(v33 + 3064);
      v31 = *(_QWORD *)(v33 + 3072);
    }
    else
    {
      v31 = 0;
      v32 = *((_QWORD *)a1 + 4660);
    }
    LODWORD(v16) = CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(
                     VaAllocator,
                     v19,
                     v29,
                     v32,
                     v31,
                     0x1000u,
                     &v41);
    if ( (int)v16 < 0 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 239;
      goto LABEL_11;
    }
    v34 = v41;
    *(_QWORD *)(v15 + 56) = v41;
    v35 = v45;
    v36 = CVirtualAddressAllocator::MapVirtualAddressRange(
            VaAllocator,
            v15,
            0,
            7,
            v19,
            v34,
            0,
            0,
            4096,
            17,
            0,
            v45,
            0,
            0,
            0);
    if ( !v36 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 260;
      LODWORD(v16) = -1073741823;
      goto LABEL_11;
    }
    *(_QWORD *)(v15 + 64) = v36;
    LODWORD(v43[0]) = 113;
    v43[6] = v36;
    v43[5] = VaAllocator;
    HIDWORD(v43[0]) = v35;
    LogicalAddress = SysMmGetLogicalAddress(*(void *const *)(v15 + 80));
    VidMmiInitializeAdlForPfnArray(
      (struct _DXGK_ADL *)&v43[7],
      (const unsigned __int64 *)(*(_QWORD *)(v15 + 72) + 48LL),
      *(_DWORD *)(*(_QWORD *)(v15 + 72) + 40LL) >> 12,
      LogicalAddress);
    LODWORD(v16) = VIDMM_GLOBAL::QueueSystemCommandAndWait(a1, (struct VIDMM_SYSTEM_COMMAND *)v43, 1);
    if ( (int)v16 < 0 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 283;
      goto LABEL_11;
    }
  }
  else
  {
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 211;
  }
  DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release((DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&v39);
  LODWORD(v16) = VIDMM_GLOBAL::RegisterSchLog(a1, (struct VIDMM_SCH_LOG *)v15);
  if ( (int)v16 >= 0 )
  {
    VIDMM_PROCESS::OpenAdapter(*(VIDMM_PROCESS **)(v15 + 96), a1);
    *(_BYTE *)(v15 + 88) = 1;
    *a4 = v15;
    *a5 = *(_QWORD *)(v15 + 48);
    *a6 = *(_QWORD *)(v15 + 56);
    return (unsigned int)v16;
  }
  WdLogSingleEntry0(3);
  WdLogGlobalForLineNumber = 298;
LABEL_35:
  if ( v15 )
    VIDMM_SCH_LOG::`scalar deleting destructor'((VIDMM_SCH_LOG *)v15, v14);
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14002e130  mov     rax, rsp
0x14002e133  mov     [rax+20h], r9
0x14002e137  mov     [rax+10h], edx
0x14002e13a  push    rbx
0x14002e13b  push    rsi
0x14002e13c  push    rdi
0x14002e13d  push    r12
0x14002e13f  push    r13
0x14002e141  push    r14
0x14002e143  push    r15
0x14002e145  sub     rsp, 100h
0x14002e14c  mov     r13, r9
0x14002e14f  mov     r15, r8
0x14002e152  mov     r12d, edx
0x14002e155  mov     rbx, rcx
0x14002e158  xor     edi, edi
0x14002e15a  mov     [rax-0A0h], rdi
0x14002e161  mov     [rax+8], rdi
0x14002e165  xor     edx, edx; Val
0x14002e167  lea     r8d, [rdi+58h]; Size
0x14002e16b  lea     rcx, [rax-98h]; void *
0x14002e172  call    memset
0x14002e177  mov     [rsp+138h+var_A8], rdi
0x14002e17f  mov     [rsp+138h+arg_10], rdi
0x14002e187  mov     r14, [rsp+138h+arg_30]
0x14002e18f  test    r14, r14
0x14002e192  cmovz   r14, cs:?g_pVidMmSystemProcess@@3PEAVVIDMM_PROCESS@@EA; VIDMM_PROCESS * g_pVidMmSystemProcess
0x14002e19a  mov     rdx, [rbx]
0x14002e19d  add     rdx, 98h; struct DXGPUSHLOCKFAST *
0x14002e1a4  lea     rcx, [rsp+138h+var_B8]; this
0x14002e1ac  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x14002e1b1  mov     rax, [rbx]
0x14002e1b4  cmp     byte ptr [rax+0E4h], 1
0x14002e1bb  jz      short loc_14002E1FE
0x14002e1bd  mov     esi, edi
0x14002e1bf  mov     r14d, 0C0000017h
0x14002e1c5  cmp     [rsp+138h+var_B0], dil
0x14002e1cd  jz      loc_14002E71F
0x14002e1d3  mov     rcx, [rsp+138h+var_B8]
0x14002e1db  mov     [rcx+8], rdi
0x14002e1df  xor     edx, edx
0x14002e1e1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002e1e8  nop     dword ptr [rax+rax+00h]
0x14002e1ed  call    cs:__imp_KeLeaveCriticalRegion
0x14002e1f4  nop     dword ptr [rax+rax+00h]
0x14002e1f9  jmp     loc_14002E71F
0x14002e1fe  mov     edx, 65356956h
0x14002e203  mov     ecx, 68h ; 'h'
0x14002e208  mov     r8d, 100h
0x14002e20e  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14002e213  mov     rsi, rax
0x14002e216  test    rax, rax
0x14002e219  jz      short loc_14002E251
0x14002e21b  mov     [rax], rdi
0x14002e21e  xorps   xmm0, xmm0
0x14002e221  movups  xmmword ptr [rax+8], xmm0
0x14002e225  mov     [rax+18h], edi
0x14002e228  mov     [rax+20h], rdi
0x14002e22c  mov     [rax+28h], rdi
0x14002e230  mov     [rax+30h], rdi
0x14002e234  mov     [rax+38h], rdi
0x14002e238  mov     [rax+40h], rdi
0x14002e23c  mov     [rax+48h], rdi
0x14002e240  mov     [rax+50h], rdi
0x14002e244  mov     [rax+58h], dil
0x14002e248  mov     [rax+5Ch], edi
0x14002e24b  mov     [rax+60h], rdi
0x14002e24f  jmp     short loc_14002E254
0x14002e251  mov     rsi, rdi
0x14002e254  mov     [rsp+138h+arg_30], rsi
0x14002e25c  test    rsi, rsi
0x14002e25f  jnz     short loc_14002E279
0x14002e261  mov     r14d, 0C0000017h
0x14002e267  lea     rcx, [rsp+138h+var_B8]; this
0x14002e26f  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x14002e274  jmp     loc_14002E71F
0x14002e279  lea     rax, [r15-1]
0x14002e27d  and     eax, 0FFFh
0x14002e282  sub     r15, rax
0x14002e285  add     r15, 0FFFh
0x14002e28c  mov     [rsi], rbx
0x14002e28f  mov     [rsi+18h], r12d
0x14002e293  mov     [rsi+20h], r15
0x14002e297  mov     eax, [rsp+138h+arg_38]
0x14002e29e  mov     [rsi+5Ch], eax
0x14002e2a1  mov     [rsi+60h], r14
0x14002e2a5  mov     [rsp+138h+arg_0], r15
0x14002e2ad  mov     [rsp+138h+var_100], rdi
0x14002e2b2  mov     [rsp+138h+var_108], rdi
0x14002e2b7  mov     [rsp+138h+var_110], 8000000h
0x14002e2bf  mov     dword ptr [rsp+138h+var_118], 4
0x14002e2c7  lea     r9, [rsp+138h+arg_0]
0x14002e2cf  xor     r8d, r8d
0x14002e2d2  xor     edx, edx
0x14002e2d4  lea     rcx, [rsi+28h]
0x14002e2d8  call    cs:__imp_MmCreateSection
0x14002e2df  nop     dword ptr [rax+rax+00h]
0x14002e2e4  movsxd  r14, eax
0x14002e2e7  test    eax, eax
0x14002e2e9  jns     short loc_14002E33A
0x14002e2eb  lock inc cs:dword_14008683C
0x14002e2f2  mov     rdx, r14
0x14002e2f5  mov     ecx, 6
0x14002e2fa  call    cs:__imp_WdLogSingleEntry1
0x14002e301  nop     dword ptr [rax+rax+00h]
0x14002e306  mov     cs:WdLogGlobalForLineNumber, 8Eh
0x14002e310  mov     [rsp+138h+var_100], rdi
0x14002e315  mov     [rsp+138h+var_108], rdi
0x14002e31a  mov     qword ptr [rsp+138h+var_110], rdi
0x14002e31f  mov     [rsp+138h+var_118], r14
0x14002e324  lea     r9, aFailedToCreate_1; "Failed to create section for VidMm sche"...
0x14002e32b  mov     edx, 40001h
0x14002e330  call    DxgkLogInternalTriageEvent
0x14002e335  jmp     loc_14002E267
0x14002e33a  mov     [rsp+138h+arg_10], r15
0x14002e342  lea     rdx, [rsi+30h]
0x14002e346  mov     [rsp+138h+var_118], rdi
0x14002e34b  lea     r9, [rsp+138h+var_A0]
0x14002e353  lea     r8, [rsp+138h+arg_10]
0x14002e35b  mov     rcx, [rsi+28h]
0x14002e35f  call    cs:__imp_MmMapViewInSystemSpaceEx
0x14002e366  nop     dword ptr [rax+rax+00h]
0x14002e36b  mov     r14d, eax
0x14002e36e  test    eax, eax
0x14002e370  jns     short loc_14002E3B5
0x14002e372  lock inc cs:dword_1400867CC
0x14002e379  mov     ecx, 6
0x14002e37e  call    cs:__imp_WdLogSingleEntry0
0x14002e385  nop     dword ptr [rax+rax+00h]
0x14002e38a  mov     eax, 9Eh
0x14002e38f  mov     cs:WdLogGlobalForLineNumber, eax
0x14002e395  mov     [rsp+138h+var_100], rdi
0x14002e39a  mov     [rsp+138h+var_108], rdi
0x14002e39f  mov     qword ptr [rsp+138h+var_110], rdi
0x14002e3a4  mov     [rsp+138h+var_118], rax
0x14002e3a9  lea     r9, aFailedToMapVie; "Failed to map view of section for VidMm"...
0x14002e3b0  jmp     loc_14002E32B
0x14002e3b5  mov     rdx, r15; Length
0x14002e3b8  mov     rcx, [rsi+30h]; Base
0x14002e3bc  call    ?VidMmiAllocateMdl@@YAPEAU_MDL@@PEAX_K@Z; VidMmiAllocateMdl(void *,unsigned __int64)
0x14002e3c1  mov     [rsi+48h], rax
0x14002e3c5  test    rax, rax
0x14002e3c8  jnz     short loc_14002E415
0x14002e3ca  lock inc cs:dword_140086840
0x14002e3d1  lea     ecx, [rax+6]
0x14002e3d4  call    cs:__imp_WdLogSingleEntry0
0x14002e3db  nop     dword ptr [rax+rax+00h]
0x14002e3e0  mov     eax, 0ABh
0x14002e3e5  mov     cs:WdLogGlobalForLineNumber, eax
0x14002e3eb  mov     [rsp+138h+var_100], rdi
0x14002e3f0  mov     [rsp+138h+var_108], rdi
0x14002e3f5  mov     qword ptr [rsp+138h+var_110], rdi
0x14002e3fa  mov     [rsp+138h+var_118], rax
0x14002e3ff  lea     r9, aFailedToAlloca_86; "Failed to allocate Mdl for VidMm schedu"...
0x14002e406  mov     edx, 40001h
0x14002e40b  call    DxgkLogInternalTriageEvent
0x14002e410  jmp     loc_14002E261
0x14002e415  xor     edx, edx; AccessMode
0x14002e417  lea     r8d, [rdx+2]; Operation
0x14002e41b  mov     rcx, rax; MemoryDescriptorList
0x14002e41e  call    cs:__imp_MmProbeAndLockPages
0x14002e425  nop     dword ptr [rax+rax+00h]
0x14002e42a  nop
0x14002e42b  lea     r9, [rsi+50h]; void **
0x14002e42f  mov     rcx, [rbx+18h]
0x14002e433  mov     r8, rsi; void *
0x14002e436  mov     rdx, [rsi+20h]; unsigned __int64
0x14002e43a  mov     rcx, [rcx+0E0h]; struct SYSMM_ADAPTER *
0x14002e441  call    ?SysMmAllocateLogicalMemory@@YAJPEAUSYSMM_ADAPTER@@_KPEBXPEAPEAX@Z; SysMmAllocateLogicalMemory(SYSMM_ADAPTER *,unsigned __int64,void const *,void * *)
0x14002e446  movsxd  r14, eax
0x14002e449  test    eax, eax
0x14002e44b  jns     short loc_14002E470
0x14002e44d  mov     rdx, r14
0x14002e450  mov     ecx, 3
0x14002e455  call    cs:__imp_WdLogSingleEntry1
0x14002e45c  nop     dword ptr [rax+rax+00h]
0x14002e461  mov     cs:WdLogGlobalForLineNumber, 0CAh
0x14002e46b  jmp     loc_14002E267
0x14002e470  mov     rcx, rsi; this
0x14002e473  call    ?GetVaAllocator@VIDMM_SCH_LOG@@QEAAPEAVCVirtualAddressAllocator@@XZ; VIDMM_SCH_LOG::GetVaAllocator(void)
0x14002e478  mov     r12, rax
0x14002e47b  test    rax, rax
0x14002e47e  jnz     short loc_14002E4DC
0x14002e480  lea     ecx, [rax+4]
0x14002e483  call    cs:__imp_WdLogSingleEntry0
0x14002e48a  nop     dword ptr [rax+rax+00h]
0x14002e48f  mov     cs:WdLogGlobalForLineNumber, 0D3h
0x14002e499  lea     rcx, [rsp+138h+var_B8]; this
0x14002e4a1  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x14002e4a6  mov     rdx, rsi; struct VIDMM_SCH_LOG *
0x14002e4a9  mov     rcx, rbx; this
0x14002e4ac  call    ?RegisterSchLog@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_SCH_LOG@@@Z; VIDMM_GLOBAL::RegisterSchLog(VIDMM_SCH_LOG *)
0x14002e4b1  mov     r14d, eax
0x14002e4b4  test    eax, eax
0x14002e4b6  jns     loc_14002E66C
0x14002e4bc  mov     ecx, 3
0x14002e4c1  call    cs:__imp_WdLogSingleEntry0
0x14002e4c8  nop     dword ptr [rax+rax+00h]
0x14002e4cd  mov     cs:WdLogGlobalForLineNumber, 12Ah
0x14002e4d7  jmp     loc_14002E71F
0x14002e4dc  cmp     [rsp+138h+arg_38], edi
0x14002e4e3  jnz     short loc_14002E4F1
0x14002e4e5  mov     rax, rdi
0x14002e4e8  mov     r9, [rbx+91A0h]
0x14002e4ef  jmp     short loc_14002E503
0x14002e4f1  mov     rax, [rbx+18h]
0x14002e4f5  mov     r9, [rax+0BF8h]; unsigned __int64
0x14002e4fc  mov     rax, [rax+0C00h]
0x14002e503  lea     rcx, [rsp+138h+var_A8]
0x14002e50b  mov     [rsp+138h+var_108], rcx; unsigned __int64 *
0x14002e510  mov     [rsp+138h+var_110], 1000h; unsigned int
0x14002e518  mov     [rsp+138h+var_118], rax; unsigned __int64
0x14002e51d  mov     rdx, r15; unsigned __int64
0x14002e520  mov     rcx, r12; this
0x14002e523  call    ?ReserveVirtualAddressRangeNoAccess@CVirtualAddressAllocator@@QEAAJ_K000IPEA_K@Z; CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,unsigned __int64 *)
0x14002e528  mov     r14d, eax
0x14002e52b  test    eax, eax
0x14002e52d  jns     short loc_14002E54F
0x14002e52f  mov     ecx, 3
0x14002e534  call    cs:__imp_WdLogSingleEntry0
0x14002e53b  nop     dword ptr [rax+rax+00h]
0x14002e540  mov     cs:WdLogGlobalForLineNumber, 0EFh
0x14002e54a  jmp     loc_14002E267
0x14002e54f  mov     rax, [rsp+138h+var_A8]
0x14002e557  mov     [rsi+38h], rax
0x14002e55b  mov     [rsp+138h+var_C8], dil
0x14002e560  mov     [rsp+138h+var_D0], dil
0x14002e565  mov     [rsp+138h+var_D8], rdi
0x14002e56a  mov     r14d, [rsp+138h+arg_8]
0x14002e572  mov     [rsp+138h+var_E0], r14d
0x14002e577  mov     [rsp+138h+var_E8], rdi
0x14002e57c  mov     [rsp+138h+var_F0], 11h
0x14002e585  mov     [rsp+138h+var_F8], 1000h
0x14002e58d  mov     [rsp+138h+var_100], rdi
0x14002e592  mov     [rsp+138h+var_108], rdi
0x14002e597  mov     qword ptr [rsp+138h+var_110], rax
0x14002e59c  mov     [rsp+138h+var_118], r15
0x14002e5a1  mov     r9d, 7
0x14002e5a7  xor     r8d, r8d
0x14002e5aa  mov     rdx, rsi
0x14002e5ad  mov     rcx, r12
0x14002e5b0  call    ?MapVirtualAddressRange@CVirtualAddressAllocator@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAX_KW4VIDMM_VAD_OWNER_TYPE@@_K333IU_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@1IPEAPEAUVIDMM_VAD_PENDING_OPERATION@@_N6@Z; CVirtualAddressAllocator::MapVirtualAddressRange(void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,uint,VIDMM_VAD_PENDING_OPERATION * *,bool,bool)
0x14002e5b5  test    rax, rax
0x14002e5b8  jnz     short loc_14002E5DE
0x14002e5ba  lea     ecx, [rax+3]
0x14002e5bd  call    cs:__imp_WdLogSingleEntry0
0x14002e5c4  nop     dword ptr [rax+rax+00h]
0x14002e5c9  mov     cs:WdLogGlobalForLineNumber, 104h
0x14002e5d3  mov     r14d, 0C0000001h
0x14002e5d9  jmp     loc_14002E267
0x14002e5de  mov     [rsi+40h], rax
0x14002e5e2  mov     [rsp+138h+var_98], 71h ; 'q'
0x14002e5ed  mov     [rsp+138h+var_68], rax
0x14002e5f5  mov     [rsp+138h+var_70], r12
0x14002e5fd  mov     [rsp+138h+var_94], r14d
0x14002e605  mov     rcx, [rsi+50h]; void *
0x14002e609  call    ?SysMmGetLogicalAddress@@YA_KQEAX@Z; SysMmGetLogicalAddress(void * const)
0x14002e60e  mov     rdx, [rsi+48h]
0x14002e612  mov     r8d, [rdx+28h]
0x14002e616  shr     r8d, 0Ch; unsigned int
0x14002e61a  add     rdx, 30h ; '0'; unsigned __int64 *
0x14002e61e  mov     r9, rax; unsigned __int64
0x14002e621  lea     rcx, [rsp+138h+var_60]; struct _DXGK_ADL *
0x14002e629  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x14002e62e  mov     r8b, 1; bool
0x14002e631  lea     rdx, [rsp+138h+var_98]; struct VIDMM_SYSTEM_COMMAND *
0x14002e639  mov     rcx, rbx; this
0x14002e63c  call    ?QueueSystemCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x14002e641  mov     r14d, eax
0x14002e644  test    eax, eax
0x14002e646  jns     loc_14002E499
0x14002e64c  mov     ecx, 3
0x14002e651  call    cs:__imp_WdLogSingleEntry0
0x14002e658  nop     dword ptr [rax+rax+00h]
0x14002e65d  mov     cs:WdLogGlobalForLineNumber, 11Bh
0x14002e667  jmp     loc_14002E267
0x14002e66c  mov     rdx, rbx; struct VIDMM_GLOBAL *
0x14002e66f  mov     rcx, [rsi+60h]; this
0x14002e673  call    ?OpenAdapter@VIDMM_PROCESS@@QEAAJPEAVVIDMM_GLOBAL@@@Z; VIDMM_PROCESS::OpenAdapter(VIDMM_GLOBAL *)
0x14002e678  mov     byte ptr [rsi+58h], 1
0x14002e67c  mov     [r13+0], rsi
0x14002e680  mov     rcx, [rsi+30h]
0x14002e684  mov     rax, [rsp+138h+arg_20]
0x14002e68c  mov     [rax], rcx
0x14002e68f  mov     rcx, [rsi+38h]
0x14002e693  mov     rax, [rsp+138h+arg_28]
0x14002e69b  mov     [rax], rcx
0x14002e69e  jmp     loc_14002E746
0x14002e6a3  lock inc cs:dword_1400866A4
0x14002e6aa  mov     ecx, 6
0x14002e6af  call    cs:__imp_WdLogSingleEntry0
0x14002e6b6  nop     dword ptr [rax+rax+00h]
0x14002e6bb  mov     cs:WdLogGlobalForLineNumber, 0BBh
0x14002e6c5  mov     [rsp+138h+var_100], 0
0x14002e6ce  mov     [rsp+138h+var_108], 0
0x14002e6d7  mov     qword ptr [rsp+138h+var_110], 0
0x14002e6e0  mov     [rsp+138h+var_118], 0BBh
0x14002e6e9  lea     r9, aFailedToProbeA; "Failed to probe and lock pages for sche"...
0x14002e6f0  mov     edx, 40001h
0x14002e6f5  call    DxgkLogInternalTriageEvent
  ... truncated ...
```
