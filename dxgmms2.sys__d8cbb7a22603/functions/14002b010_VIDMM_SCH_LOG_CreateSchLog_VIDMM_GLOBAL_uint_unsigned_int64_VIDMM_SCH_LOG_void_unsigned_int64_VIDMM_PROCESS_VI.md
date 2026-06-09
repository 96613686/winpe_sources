# VIDMM_SCH_LOG::CreateSchLog(VIDMM_GLOBAL *,uint,unsigned __int64,VIDMM_SCH_LOG * *,void * *,unsigned __int64 *,VIDMM_PROCESS *,VIDMM_SCH_LOG_TYPE)

- ea: `0x14002b010`
- end: `0x14002b63d`
- name: `?CreateSchLog@VIDMM_SCH_LOG@@SAJPEAVVIDMM_GLOBAL@@I_KPEAPEAV1@PEAPEAXPEA_KPEAVVIDMM_PROCESS@@W4VIDMM_SCH_LOG_TYPE@@@Z`
- size: `1581`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *, int, __int64, __int64 *, _QWORD *, _QWORD *, VIDMM_PROCESS *, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14002ad98`
- `0x140054a20`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002b010`
- `0x14002b730`
- `0x14002b830`
- `0x140030bac`
- `0x140030bd0`
- `0x14003d458`
- `0x140044394`
- `0x140058d3c`
- `0x140059380`
- `0x1400c7210`
- `0x1400e827c`
- `0x1400ffd4c`
- `0x14010e82c`
- `0x140110c04`
- `0x1401168a8`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x14002b2fe`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002b2fe`
- `ntoskrnl!MmCreateSection` at `0x14002b1b8`
- `ntoskrnl!MmCreateSection` at `0x14002b1b8`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14002b23f`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14002b23f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002b0c1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002b0c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002b0cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002b0cd`
- `watchdog!WdLogSingleEntry0` at `0x14002b25e`
- `watchdog!WdLogSingleEntry0` at `0x14002b2b4`
- `watchdog!WdLogSingleEntry0` at `0x14002b363`
- `watchdog!WdLogSingleEntry0` at `0x14002b3a1`
- `watchdog!WdLogSingleEntry0` at `0x14002b414`
- `watchdog!WdLogSingleEntry0` at `0x14002b49d`
- `watchdog!WdLogSingleEntry0` at `0x14002b531`
- `watchdog!WdLogSingleEntry0` at `0x14002b58f`
- `watchdog!WdLogSingleEntry0` at `0x14002b25e`
- `watchdog!WdLogSingleEntry0` at `0x14002b2b4`
- `watchdog!WdLogSingleEntry0` at `0x14002b363`
- `watchdog!WdLogSingleEntry0` at `0x14002b3a1`
- `watchdog!WdLogSingleEntry0` at `0x14002b414`
- `watchdog!WdLogSingleEntry0` at `0x14002b49d`
- `watchdog!WdLogSingleEntry0` at `0x14002b531`
- `watchdog!WdLogSingleEntry0` at `0x14002b58f`
- `watchdog!WdLogSingleEntry1` at `0x14002b1da`
- `watchdog!WdLogSingleEntry1` at `0x14002b335`
- `watchdog!WdLogSingleEntry1` at `0x14002b1da`
- `watchdog!WdLogSingleEntry1` at `0x14002b335`

## string_xrefs

- `0x14002b204`: `Failed to create section for VidMm scheduler log, Status=0x%.8x`

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
    _InterlockedIncrement(&dword_14008781C);
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
    _InterlockedIncrement(&dword_1400877AC);
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
    _InterlockedIncrement(&dword_140087820);
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
      v32 = *(_QWORD *)(v33 + 3080);
      v31 = *(_QWORD *)(v33 + 3088);
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
0x14002b010  mov     rax, rsp
0x14002b013  mov     [rax+20h], r9
0x14002b017  mov     [rax+10h], edx
0x14002b01a  push    rbx
0x14002b01b  push    rsi
0x14002b01c  push    rdi
0x14002b01d  push    r12
0x14002b01f  push    r13
0x14002b021  push    r14
0x14002b023  push    r15
0x14002b025  sub     rsp, 100h
0x14002b02c  mov     r13, r9
0x14002b02f  mov     r15, r8
0x14002b032  mov     r12d, edx
0x14002b035  mov     rbx, rcx
0x14002b038  xor     edi, edi
0x14002b03a  mov     [rax-0A0h], rdi
0x14002b041  mov     [rax+8], rdi
0x14002b045  xor     edx, edx; Val
0x14002b047  lea     r8d, [rdi+58h]; Size
0x14002b04b  lea     rcx, [rax-98h]; void *
0x14002b052  call    memset
0x14002b057  mov     [rsp+138h+var_A8], rdi
0x14002b05f  mov     [rsp+138h+arg_10], rdi
0x14002b067  mov     r14, [rsp+138h+arg_30]
0x14002b06f  test    r14, r14
0x14002b072  cmovz   r14, cs:?g_pVidMmSystemProcess@@3PEAVVIDMM_PROCESS@@EA; VIDMM_PROCESS * g_pVidMmSystemProcess
0x14002b07a  mov     rdx, [rbx]
0x14002b07d  add     rdx, 98h; struct DXGPUSHLOCKFAST *
0x14002b084  lea     rcx, [rsp+138h+var_B8]; this
0x14002b08c  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x14002b091  mov     rax, [rbx]
0x14002b094  cmp     byte ptr [rax+0E4h], 1
0x14002b09b  jz      short loc_14002B0DE
0x14002b09d  mov     esi, edi
0x14002b09f  mov     r14d, 0C0000017h
0x14002b0a5  cmp     [rsp+138h+var_B0], dil
0x14002b0ad  jz      loc_14002B5FF
0x14002b0b3  mov     rcx, [rsp+138h+var_B8]
0x14002b0bb  mov     [rcx+8], rdi
0x14002b0bf  xor     edx, edx
0x14002b0c1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002b0c8  nop     dword ptr [rax+rax+00h]
0x14002b0cd  call    cs:__imp_KeLeaveCriticalRegion
0x14002b0d4  nop     dword ptr [rax+rax+00h]
0x14002b0d9  jmp     loc_14002B5FF
0x14002b0de  mov     edx, 65356956h
0x14002b0e3  mov     ecx, 68h ; 'h'
0x14002b0e8  mov     r8d, 100h
0x14002b0ee  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14002b0f3  mov     rsi, rax
0x14002b0f6  test    rax, rax
0x14002b0f9  jz      short loc_14002B131
0x14002b0fb  mov     [rax], rdi
0x14002b0fe  xorps   xmm0, xmm0
0x14002b101  movups  xmmword ptr [rax+8], xmm0
0x14002b105  mov     [rax+18h], edi
0x14002b108  mov     [rax+20h], rdi
0x14002b10c  mov     [rax+28h], rdi
0x14002b110  mov     [rax+30h], rdi
0x14002b114  mov     [rax+38h], rdi
0x14002b118  mov     [rax+40h], rdi
0x14002b11c  mov     [rax+48h], rdi
0x14002b120  mov     [rax+50h], rdi
0x14002b124  mov     [rax+58h], dil
0x14002b128  mov     [rax+5Ch], edi
0x14002b12b  mov     [rax+60h], rdi
0x14002b12f  jmp     short loc_14002B134
0x14002b131  mov     rsi, rdi
0x14002b134  mov     [rsp+138h+arg_30], rsi
0x14002b13c  test    rsi, rsi
0x14002b13f  jnz     short loc_14002B159
0x14002b141  mov     r14d, 0C0000017h
0x14002b147  lea     rcx, [rsp+138h+var_B8]; this
0x14002b14f  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x14002b154  jmp     loc_14002B5FF
0x14002b159  lea     rax, [r15-1]
0x14002b15d  and     eax, 0FFFh
0x14002b162  sub     r15, rax
0x14002b165  add     r15, 0FFFh
0x14002b16c  mov     [rsi], rbx
0x14002b16f  mov     [rsi+18h], r12d
0x14002b173  mov     [rsi+20h], r15
0x14002b177  mov     eax, [rsp+138h+arg_38]
0x14002b17e  mov     [rsi+5Ch], eax
0x14002b181  mov     [rsi+60h], r14
0x14002b185  mov     [rsp+138h+arg_0], r15
0x14002b18d  mov     [rsp+138h+var_100], rdi
0x14002b192  mov     [rsp+138h+var_108], rdi
0x14002b197  mov     [rsp+138h+var_110], 8000000h
0x14002b19f  mov     dword ptr [rsp+138h+var_118], 4
0x14002b1a7  lea     r9, [rsp+138h+arg_0]
0x14002b1af  xor     r8d, r8d
0x14002b1b2  xor     edx, edx
0x14002b1b4  lea     rcx, [rsi+28h]
0x14002b1b8  call    cs:__imp_MmCreateSection
0x14002b1bf  nop     dword ptr [rax+rax+00h]
0x14002b1c4  movsxd  r14, eax
0x14002b1c7  test    eax, eax
0x14002b1c9  jns     short loc_14002B21A
0x14002b1cb  lock inc cs:dword_14008781C
0x14002b1d2  mov     rdx, r14
0x14002b1d5  mov     ecx, 6
0x14002b1da  call    cs:__imp_WdLogSingleEntry1
0x14002b1e1  nop     dword ptr [rax+rax+00h]
0x14002b1e6  mov     cs:WdLogGlobalForLineNumber, 8Eh
0x14002b1f0  mov     [rsp+138h+var_100], rdi
0x14002b1f5  mov     [rsp+138h+var_108], rdi
0x14002b1fa  mov     qword ptr [rsp+138h+var_110], rdi
0x14002b1ff  mov     [rsp+138h+var_118], r14
0x14002b204  lea     r9, aFailedToCreate_1; "Failed to create section for VidMm sche"...
0x14002b20b  mov     edx, 40001h
0x14002b210  call    DxgkLogInternalTriageEvent
0x14002b215  jmp     loc_14002B147
0x14002b21a  mov     [rsp+138h+arg_10], r15
0x14002b222  lea     rdx, [rsi+30h]
0x14002b226  mov     [rsp+138h+var_118], rdi
0x14002b22b  lea     r9, [rsp+138h+var_A0]
0x14002b233  lea     r8, [rsp+138h+arg_10]
0x14002b23b  mov     rcx, [rsi+28h]
0x14002b23f  call    cs:__imp_MmMapViewInSystemSpaceEx
0x14002b246  nop     dword ptr [rax+rax+00h]
0x14002b24b  mov     r14d, eax
0x14002b24e  test    eax, eax
0x14002b250  jns     short loc_14002B295
0x14002b252  lock inc cs:dword_1400877AC
0x14002b259  mov     ecx, 6
0x14002b25e  call    cs:__imp_WdLogSingleEntry0
0x14002b265  nop     dword ptr [rax+rax+00h]
0x14002b26a  mov     eax, 9Eh
0x14002b26f  mov     cs:WdLogGlobalForLineNumber, eax
0x14002b275  mov     [rsp+138h+var_100], rdi
0x14002b27a  mov     [rsp+138h+var_108], rdi
0x14002b27f  mov     qword ptr [rsp+138h+var_110], rdi
0x14002b284  mov     [rsp+138h+var_118], rax
0x14002b289  lea     r9, aFailedToMapVie; "Failed to map view of section for VidMm"...
0x14002b290  jmp     loc_14002B20B
0x14002b295  mov     rdx, r15; Length
0x14002b298  mov     rcx, [rsi+30h]; Base
0x14002b29c  call    ?VidMmiAllocateMdl@@YAPEAU_MDL@@PEAX_K@Z; VidMmiAllocateMdl(void *,unsigned __int64)
0x14002b2a1  mov     [rsi+48h], rax
0x14002b2a5  test    rax, rax
0x14002b2a8  jnz     short loc_14002B2F5
0x14002b2aa  lock inc cs:dword_140087820
0x14002b2b1  lea     ecx, [rax+6]
0x14002b2b4  call    cs:__imp_WdLogSingleEntry0
0x14002b2bb  nop     dword ptr [rax+rax+00h]
0x14002b2c0  mov     eax, 0ABh
0x14002b2c5  mov     cs:WdLogGlobalForLineNumber, eax
0x14002b2cb  mov     [rsp+138h+var_100], rdi
0x14002b2d0  mov     [rsp+138h+var_108], rdi
0x14002b2d5  mov     qword ptr [rsp+138h+var_110], rdi
0x14002b2da  mov     [rsp+138h+var_118], rax
0x14002b2df  lea     r9, aFailedToAlloca_90; "Failed to allocate Mdl for VidMm schedu"...
0x14002b2e6  mov     edx, 40001h
0x14002b2eb  call    DxgkLogInternalTriageEvent
0x14002b2f0  jmp     loc_14002B141
0x14002b2f5  xor     edx, edx; AccessMode
0x14002b2f7  lea     r8d, [rdx+2]; Operation
0x14002b2fb  mov     rcx, rax; MemoryDescriptorList
0x14002b2fe  call    cs:__imp_MmProbeAndLockPages
0x14002b305  nop     dword ptr [rax+rax+00h]
0x14002b30a  nop
0x14002b30b  lea     r9, [rsi+50h]; void **
0x14002b30f  mov     rcx, [rbx+18h]
0x14002b313  mov     r8, rsi; void *
0x14002b316  mov     rdx, [rsi+20h]; unsigned __int64
0x14002b31a  mov     rcx, [rcx+0E0h]; struct SYSMM_ADAPTER *
0x14002b321  call    ?SysMmAllocateLogicalMemory@@YAJPEAUSYSMM_ADAPTER@@_KPEBXPEAPEAX@Z; SysMmAllocateLogicalMemory(SYSMM_ADAPTER *,unsigned __int64,void const *,void * *)
0x14002b326  movsxd  r14, eax
0x14002b329  test    eax, eax
0x14002b32b  jns     short loc_14002B350
0x14002b32d  mov     rdx, r14
0x14002b330  mov     ecx, 3
0x14002b335  call    cs:__imp_WdLogSingleEntry1
0x14002b33c  nop     dword ptr [rax+rax+00h]
0x14002b341  mov     cs:WdLogGlobalForLineNumber, 0CAh
0x14002b34b  jmp     loc_14002B147
0x14002b350  mov     rcx, rsi; this
0x14002b353  call    ?GetVaAllocator@VIDMM_SCH_LOG@@QEAAPEAVCVirtualAddressAllocator@@XZ; VIDMM_SCH_LOG::GetVaAllocator(void)
0x14002b358  mov     r12, rax
0x14002b35b  test    rax, rax
0x14002b35e  jnz     short loc_14002B3BC
0x14002b360  lea     ecx, [rax+4]
0x14002b363  call    cs:__imp_WdLogSingleEntry0
0x14002b36a  nop     dword ptr [rax+rax+00h]
0x14002b36f  mov     cs:WdLogGlobalForLineNumber, 0D3h
0x14002b379  lea     rcx, [rsp+138h+var_B8]; this
0x14002b381  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x14002b386  mov     rdx, rsi; struct VIDMM_SCH_LOG *
0x14002b389  mov     rcx, rbx; this
0x14002b38c  call    ?RegisterSchLog@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_SCH_LOG@@@Z; VIDMM_GLOBAL::RegisterSchLog(VIDMM_SCH_LOG *)
0x14002b391  mov     r14d, eax
0x14002b394  test    eax, eax
0x14002b396  jns     loc_14002B54C
0x14002b39c  mov     ecx, 3
0x14002b3a1  call    cs:__imp_WdLogSingleEntry0
0x14002b3a8  nop     dword ptr [rax+rax+00h]
0x14002b3ad  mov     cs:WdLogGlobalForLineNumber, 12Ah
0x14002b3b7  jmp     loc_14002B5FF
0x14002b3bc  cmp     [rsp+138h+arg_38], edi
0x14002b3c3  jnz     short loc_14002B3D1
0x14002b3c5  mov     rax, rdi
0x14002b3c8  mov     r9, [rbx+91A0h]
0x14002b3cf  jmp     short loc_14002B3E3
0x14002b3d1  mov     rax, [rbx+18h]
0x14002b3d5  mov     r9, [rax+0C08h]; unsigned __int64
0x14002b3dc  mov     rax, [rax+0C10h]
0x14002b3e3  lea     rcx, [rsp+138h+var_A8]
0x14002b3eb  mov     [rsp+138h+var_108], rcx; unsigned __int64 *
0x14002b3f0  mov     [rsp+138h+var_110], 1000h; unsigned int
0x14002b3f8  mov     [rsp+138h+var_118], rax; unsigned __int64
0x14002b3fd  mov     rdx, r15; unsigned __int64
0x14002b400  mov     rcx, r12; this
0x14002b403  call    ?ReserveVirtualAddressRangeNoAccess@CVirtualAddressAllocator@@QEAAJ_K000IPEA_K@Z; CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,unsigned __int64 *)
0x14002b408  mov     r14d, eax
0x14002b40b  test    eax, eax
0x14002b40d  jns     short loc_14002B42F
0x14002b40f  mov     ecx, 3
0x14002b414  call    cs:__imp_WdLogSingleEntry0
0x14002b41b  nop     dword ptr [rax+rax+00h]
0x14002b420  mov     cs:WdLogGlobalForLineNumber, 0EFh
0x14002b42a  jmp     loc_14002B147
0x14002b42f  mov     rax, [rsp+138h+var_A8]
0x14002b437  mov     [rsi+38h], rax
0x14002b43b  mov     [rsp+138h+var_C8], dil
0x14002b440  mov     [rsp+138h+var_D0], dil
0x14002b445  mov     [rsp+138h+var_D8], rdi
0x14002b44a  mov     r14d, [rsp+138h+arg_8]
0x14002b452  mov     [rsp+138h+var_E0], r14d
0x14002b457  mov     [rsp+138h+var_E8], rdi
0x14002b45c  mov     [rsp+138h+var_F0], 11h
0x14002b465  mov     [rsp+138h+var_F8], 1000h
0x14002b46d  mov     [rsp+138h+var_100], rdi
0x14002b472  mov     [rsp+138h+var_108], rdi
0x14002b477  mov     qword ptr [rsp+138h+var_110], rax
0x14002b47c  mov     [rsp+138h+var_118], r15
0x14002b481  mov     r9d, 7
0x14002b487  xor     r8d, r8d
0x14002b48a  mov     rdx, rsi
0x14002b48d  mov     rcx, r12
0x14002b490  call    ?MapVirtualAddressRange@CVirtualAddressAllocator@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAX_KW4VIDMM_VAD_OWNER_TYPE@@_K333IU_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@1IPEAPEAUVIDMM_VAD_PENDING_OPERATION@@_N6@Z; CVirtualAddressAllocator::MapVirtualAddressRange(void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,uint,VIDMM_VAD_PENDING_OPERATION * *,bool,bool)
0x14002b495  test    rax, rax
0x14002b498  jnz     short loc_14002B4BE
0x14002b49a  lea     ecx, [rax+3]
0x14002b49d  call    cs:__imp_WdLogSingleEntry0
0x14002b4a4  nop     dword ptr [rax+rax+00h]
0x14002b4a9  mov     cs:WdLogGlobalForLineNumber, 104h
0x14002b4b3  mov     r14d, 0C0000001h
0x14002b4b9  jmp     loc_14002B147
0x14002b4be  mov     [rsi+40h], rax
0x14002b4c2  mov     [rsp+138h+var_98], 71h ; 'q'
0x14002b4cd  mov     [rsp+138h+var_68], rax
0x14002b4d5  mov     [rsp+138h+var_70], r12
0x14002b4dd  mov     [rsp+138h+var_94], r14d
0x14002b4e5  mov     rcx, [rsi+50h]; void *
0x14002b4e9  call    ?SysMmGetLogicalAddress@@YA_KQEAX@Z; SysMmGetLogicalAddress(void * const)
0x14002b4ee  mov     rdx, [rsi+48h]
0x14002b4f2  mov     r8d, [rdx+28h]
0x14002b4f6  shr     r8d, 0Ch; unsigned int
0x14002b4fa  add     rdx, 30h ; '0'; unsigned __int64 *
0x14002b4fe  mov     r9, rax; unsigned __int64
0x14002b501  lea     rcx, [rsp+138h+var_60]; struct _DXGK_ADL *
0x14002b509  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x14002b50e  mov     r8b, 1; bool
0x14002b511  lea     rdx, [rsp+138h+var_98]; struct VIDMM_SYSTEM_COMMAND *
0x14002b519  mov     rcx, rbx; this
0x14002b51c  call    ?QueueSystemCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x14002b521  mov     r14d, eax
0x14002b524  test    eax, eax
0x14002b526  jns     loc_14002B379
0x14002b52c  mov     ecx, 3
0x14002b531  call    cs:__imp_WdLogSingleEntry0
0x14002b538  nop     dword ptr [rax+rax+00h]
0x14002b53d  mov     cs:WdLogGlobalForLineNumber, 11Bh
0x14002b547  jmp     loc_14002B147
0x14002b54c  mov     rdx, rbx; struct VIDMM_GLOBAL *
0x14002b54f  mov     rcx, [rsi+60h]; this
0x14002b553  call    ?OpenAdapter@VIDMM_PROCESS@@QEAAJPEAVVIDMM_GLOBAL@@@Z; VIDMM_PROCESS::OpenAdapter(VIDMM_GLOBAL *)
0x14002b558  mov     byte ptr [rsi+58h], 1
0x14002b55c  mov     [r13+0], rsi
0x14002b560  mov     rcx, [rsi+30h]
0x14002b564  mov     rax, [rsp+138h+arg_20]
0x14002b56c  mov     [rax], rcx
0x14002b56f  mov     rcx, [rsi+38h]
0x14002b573  mov     rax, [rsp+138h+arg_28]
0x14002b57b  mov     [rax], rcx
0x14002b57e  jmp     loc_14002B626
0x14002b583  lock inc cs:dword_140087684
0x14002b58a  mov     ecx, 6
0x14002b58f  call    cs:__imp_WdLogSingleEntry0
0x14002b596  nop     dword ptr [rax+rax+00h]
0x14002b59b  mov     cs:WdLogGlobalForLineNumber, 0BBh
0x14002b5a5  mov     [rsp+138h+var_100], 0
0x14002b5ae  mov     [rsp+138h+var_108], 0
0x14002b5b7  mov     qword ptr [rsp+138h+var_110], 0
0x14002b5c0  mov     [rsp+138h+var_118], 0BBh
0x14002b5c9  lea     r9, aFailedToProbeA; "Failed to probe and lock pages for sche"...
0x14002b5d0  mov     edx, 40001h
0x14002b5d5  call    DxgkLogInternalTriageEvent
  ... truncated ...
```
