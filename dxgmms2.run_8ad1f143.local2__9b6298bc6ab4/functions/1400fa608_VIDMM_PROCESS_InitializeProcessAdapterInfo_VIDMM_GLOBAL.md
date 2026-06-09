# VIDMM_PROCESS::InitializeProcessAdapterInfo(VIDMM_GLOBAL *)

- ea: `0x1400fa608`
- end: `0x1400facea`
- name: `?InitializeProcessAdapterInfo@VIDMM_PROCESS@@IEAAPEAUVIDMM_PROCESS_ADAPTER_INFO@@PEAVVIDMM_GLOBAL@@@Z`
- size: `1762`
- prototype: `struct VIDMM_PROCESS_ADAPTER_INFO *__fastcall(VIDMM_PROCESS *__hidden this, struct VIDMM_GLOBAL *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400fa2ac`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002ec00`
- `0x14002ed1c`
- `0x14002f510`
- `0x1400308bc`
- `0x140030ae0`
- `0x140031178`
- `0x140033494`
- `0x140034800`
- `0x140035b70`
- `0x140035bc8`
- `0x14003c694`
- `0x1400ab080`
- `0x1400e27f0`
- `0x1400ed184`
- `0x1400ed504`
- `0x1400fa608`
- `0x1400fb150`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400faa6c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400faa6c`
- `ntoskrnl!PcwCreateInstance` at `0x1400faaa5`
- `ntoskrnl!PcwCreateInstance` at `0x1400faaa5`
- `watchdog!WdLogSingleEntry0` at `0x1400fa730`
- `watchdog!WdLogSingleEntry0` at `0x1400fa7b5`
- `watchdog!WdLogSingleEntry0` at `0x1400fa8bc`
- `watchdog!WdLogSingleEntry0` at `0x1400fa922`
- `watchdog!WdLogSingleEntry0` at `0x1400fa96d`
- `watchdog!WdLogSingleEntry0` at `0x1400fa9ab`
- `watchdog!WdLogSingleEntry0` at `0x1400faad3`
- `watchdog!WdLogSingleEntry0` at `0x1400fab0f`
- `watchdog!WdLogSingleEntry0` at `0x1400fac90`
- `watchdog!WdLogSingleEntry0` at `0x1400fa730`
- `watchdog!WdLogSingleEntry0` at `0x1400fa7b5`
- `watchdog!WdLogSingleEntry0` at `0x1400fa8bc`
- `watchdog!WdLogSingleEntry0` at `0x1400fa922`
- `watchdog!WdLogSingleEntry0` at `0x1400fa96d`
- `watchdog!WdLogSingleEntry0` at `0x1400fa9ab`
- `watchdog!WdLogSingleEntry0` at `0x1400faad3`
- `watchdog!WdLogSingleEntry0` at `0x1400fab0f`
- `watchdog!WdLogSingleEntry0` at `0x1400fac90`

## string_xrefs

- `0x1400fa741`: `Couldn't allocate memory for commitment info.`
- `0x1400fa9bc`: `Failed to create name string for GpuPerformanceCounterSetProcessMemory`
- `0x1400fab1d`: `Failed to create name string for GpuPerformanceCounterSetProcessMemory`
- `0x1400faae8`: `Failed to create GpuPerformanceCounterSetProcessMemory`

## pseudocode

```c
struct VIDMM_PROCESS_ADAPTER_INFO *__fastcall VIDMM_PROCESS::InitializeProcessAdapterInfo(
        struct VIDMM_PARTITION **this,
        struct VIDMM_GLOBAL *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  _QWORD *v6; // rax
  unsigned __int64 v7; // r14
  __int64 v8; // rax
  bool v9; // cf
  __int64 v10; // rax
  unsigned __int64 *v11; // rax
  _QWORD *v12; // rbp
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rax
  const wchar_t *v16; // r9
  int v17; // edx
  unsigned int v18; // edx
  VIDMM_PROCESS_ADAPTER_INFO_PAGED *v19; // rax
  VIDMM_PROCESS_ADAPTER_INFO_PAGED *v20; // rax
  _QWORD *v21; // r13
  unsigned __int16 i; // r14
  __int64 v23; // r13
  unsigned __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int64 *v27; // rax
  _QWORD *v28; // rbp
  unsigned int k; // edx
  __int64 v30; // rax
  CVirtualAddressAllocator *v31; // rax
  CVirtualAddressAllocator *v32; // rax
  wchar_t *v33; // r15
  NTSTATUS v34; // r14d
  unsigned int j; // ebp
  __int64 v36; // r13
  __int64 v37; // r14
  __int64 v38; // rcx
  __int64 v39; // r9
  int v40; // ecx
  int v41; // r8d
  const wchar_t *v42; // r9
  __int64 v43; // rax
  int v44; // edx
  CVirtualAddressAllocator *v45; // rcx
  int v46; // eax
  unsigned int v47; // eax
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  DXGPROCESS *v51; // rcx
  struct VIDMM_GLOBAL **v52; // rdx
  int v54; // ecx
  int v55; // r8d
  PPCW_DATA Data; // [rsp+20h] [rbp-98h]
  __int64 v57; // [rsp+28h] [rbp-90h]
  __int64 v58; // [rsp+30h] [rbp-88h]
  __int64 v59; // [rsp+50h] [rbp-68h]
  struct _PCW_DATA v60; // [rsp+58h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-50h] BYREF
  __int64 v62; // [rsp+D8h] [rbp+20h]

  v4 = operator new(192, 858876246, 64);
  v5 = v4;
  if ( !v4 )
  {
    _InterlockedAdd(&dword_14008671C, 1u);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 829;
    DxgkLogInternalTriageEvent(
      v54,
      262145,
      v55,
      (unsigned int)L"Couldn't allocate memory for adapter info.",
      829,
      0,
      0,
      0);
    return 0;
  }
  *(_QWORD *)(v4 + 104) = 0;
  *(_QWORD *)(v4 + 112) = 0;
  *(_QWORD *)(v4 + 120) = 0;
  *(_QWORD *)(v4 + 128) = 0;
  *(_DWORD *)(v4 + 136) = 0;
  *(_QWORD *)(v4 + 144) = 0;
  *(_QWORD *)(v4 + 152) = 0;
  *(_DWORD *)(v4 + 160) = 0;
  *(_DWORD *)(v4 + 164) = 1;
  *(_DWORD *)(v4 + 168) = 54;
  *(_DWORD *)(v4 + 176) = 33685504;
  *(_BYTE *)(v4 + 180) = 0;
  *(_QWORD *)(v4 + 32) = 0;
  v6 = (_QWORD *)(v4 + 88);
  v6[1] = v6;
  *v6 = v6;
  *(_QWORD *)(v5 + 72) = 0;
  *(_QWORD *)(v5 + 80) = 0;
  v7 = *((unsigned int *)a2 + 778);
  v8 = 304 * v7;
  if ( !is_mul_ok(v7, 0x130u) )
    v8 = -1;
  v9 = __CFADD__(v8, 8);
  v10 = v8 + 8;
  if ( v9 )
    v10 = -1;
  v11 = (unsigned __int64 *)operator new[](v10, 1630628182, 256);
  if ( v11 )
  {
    v12 = v11 + 1;
    *v11 = v7;
    `vector constructor iterator'(
      v11 + 1,
      0x130u,
      (unsigned int)v7,
      (void *(*)(void *))VIDMM_PROCESS_PHYSICAL_ADAPTER_INFO::VIDMM_PROCESS_PHYSICAL_ADAPTER_INFO);
  }
  else
  {
    v12 = 0;
  }
  *(_QWORD *)(v5 + 8) = v12;
  if ( !v12 )
  {
    _InterlockedAdd(&dword_140086724, 1u);
    WdLogSingleEntry0(6);
    v15 = 837;
    goto LABEL_11;
  }
  v19 = (VIDMM_PROCESS_ADAPTER_INFO_PAGED *)operator new(1752, 858876246, 256);
  if ( v19 )
    v20 = VIDMM_PROCESS_ADAPTER_INFO_PAGED::VIDMM_PROCESS_ADAPTER_INFO_PAGED(v19);
  else
    v20 = 0;
  v59 = v5 + 184;
  *(_QWORD *)(v5 + 184) = v20;
  if ( !v20 )
  {
    _InterlockedAdd(&dword_140086720, 1u);
    WdLogSingleEntry0(6);
    v15 = 845;
    v16 = L"Couldn't allocate memory for paged adapter info.";
    goto LABEL_12;
  }
  v21 = (_QWORD *)(v5 + 8);
  for ( i = 0; ; ++i )
  {
    if ( (unsigned int)i >= *((_DWORD *)a2 + 778) )
    {
      if ( (*((_BYTE *)a2 + 37224) & 0x10) != 0 && ((_DWORD)this[17] & 2) == 0 )
      {
        v31 = (CVirtualAddressAllocator *)operator new(160, 1265072196, 256);
        if ( v31 )
          v32 = CVirtualAddressAllocator::CVirtualAddressAllocator(v31);
        else
          v32 = 0;
        *(_QWORD *)(v5 + 24) = v32;
        if ( !v32 )
        {
          WdLogSingleEntry0(1);
          v15 = 880;
          v16 = L"Failed to allocate CVirtualAddressAllocator";
LABEL_38:
          v17 = 0x40000;
          goto LABEL_13;
        }
        if ( (int)CVirtualAddressAllocator::InitializeVaAllocator(
                    v32,
                    1LL << *((_DWORD *)a2 + 9304),
                    *((unsigned int *)a2 + 9325),
                    a2,
                    (struct VIDMM_PROCESS *)this) < 0 )
        {
          WdLogSingleEntry0(1);
          v15 = 892;
          v16 = L"Failed to initialize CVirtualAddressAllocator";
          goto LABEL_38;
        }
      }
      v33 = (wchar_t *)operator new[](520, 1265072196, 258);
      if ( !v33 )
      {
        _InterlockedAdd(&dword_14008687C, 1u);
        WdLogSingleEntry0(6);
        v15 = 901;
        v16 = L"Failed to create name string for GpuPerformanceCounterSetProcessMemory";
        goto LABEL_12;
      }
      v34 = 0;
      for ( j = 0; j < *((_DWORD *)a2 + 778); ++j )
      {
        v36 = 304LL * (unsigned __int16)j + *v21 + 8LL;
        v37 = 0;
        *(_QWORD *)(v36 + 16) = v5;
        do
        {
          *(_QWORD *)(v36 + 8 * v37 + 24) = *((_QWORD *)VIDMM_GLOBAL::GetSegmentGroupState(
                                                          a2,
                                                          j,
                                                          (enum _D3DKMT_MEMORY_SEGMENT_GROUP)v37,
                                                          this[42])
                                            + 4);
          v37 = (unsigned int)(v37 + 1);
        }
        while ( (int)v37 < 2 );
        v38 = *((_QWORD *)a2 + 3);
        v39 = *((unsigned int *)this + 6);
        DestinationString = 0;
        LODWORD(v58) = j;
        LODWORD(v57) = *(_DWORD *)(v38 + 412);
        LODWORD(Data) = *(_DWORD *)(v38 + 416);
        v34 = RtlStringCbPrintfW(v33, 0x208u, L"pid_%u_luid_0x%08X_0x%08X_phys_%u", v39, Data, v57, v58);
        if ( v34 < 0 )
        {
          WdLogSingleEntry0(1);
          v40 = 0;
          v42 = L"Failed to create name string for GpuPerformanceCounterSetProcessMemory";
          v43 = 927;
          v44 = 0x40000;
          goto LABEL_52;
        }
        RtlInitUnicodeString(&DestinationString, v33);
        v60.Data = (const void *)v36;
        v60.Size = 296;
        v34 = PcwCreateInstance(
                (PPCW_INSTANCE *)(v36 + 248),
                GpuPerformanceCounterSetProcessMemory,
                &DestinationString,
                1u,
                &v60);
        if ( v34 < 0 )
        {
          _InterlockedAdd(&dword_14008687C, 1u);
          WdLogSingleEntry0(6);
          v42 = L"Failed to create GpuPerformanceCounterSetProcessMemory";
          v43 = 935;
          v44 = 262145;
LABEL_52:
          WdLogGlobalForLineNumber = v43;
          DxgkLogInternalTriageEvent(v40, v44, v41, (_DWORD)v42, v43, 0, 0, 0);
          break;
        }
        v21 = (_QWORD *)(v5 + 8);
      }
      operator delete(v33);
      if ( v34 < 0 )
        goto LABEL_54;
      v46 = *(_DWORD *)(*(_QWORD *)v59 + 24LL);
      if ( dword_1400863B8 )
        v47 = v46 & 0xFFFFFFF8 | 6;
      else
        v47 = v46 | 7;
      *(_DWORD *)(*(_QWORD *)v59 + 24LL) = v47;
      if ( (VIDMM_GLOBAL::_Config & 4) != 0
        && DXGPROCESS::GetCurrent()
        && (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) != 0 )
      {
        *(_DWORD *)(*(_QWORD *)v59 + 36LL) = 1;
      }
      *(_QWORD *)v5 = a2;
      *(_DWORD *)(v5 + 136) = 1;
      *(_QWORD *)(v5 + 16) = this;
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)&DestinationString,
        (struct VIDMM_GLOBAL *)((char *)a2 + 37376));
      v48 = (_QWORD *)((char *)a2 + 37424);
      v49 = *((_QWORD *)a2 + 4678);
      if ( *(struct VIDMM_GLOBAL **)(v49 + 8) == (struct VIDMM_GLOBAL *)((char *)a2 + 37424) )
      {
        *(_QWORD *)(v5 + 40) = v49;
        *(_QWORD *)(v5 + 48) = v48;
        *(_QWORD *)(v49 + 8) = v5 + 40;
        *v48 = v5 + 40;
        v50 = *((_QWORD *)a2 + 5172);
        *((_QWORD *)a2 + 5172) = v50 + 1;
        *(_QWORD *)(v5 + 104) = v50;
        if ( !(unsigned int)Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_70;
        v51 = *(DXGPROCESS **)(*(_QWORD *)(v5 + 16) + 72LL);
        if ( !v51 || !DXGPROCESS::UmdManagesResidency(v51) )
          goto LABEL_70;
        v52 = (struct VIDMM_GLOBAL **)*((_QWORD *)a2 + 4542);
        if ( *v52 == (struct VIDMM_GLOBAL *)((char *)a2 + 36328) )
        {
          *(_QWORD *)(v5 + 56) = (char *)a2 + 36328;
          *(_QWORD *)(v5 + 64) = v52;
          *v52 = (struct VIDMM_GLOBAL *)(v5 + 56);
          *((_QWORD *)a2 + 4542) = v5 + 56;
LABEL_70:
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&DestinationString);
          VIDMM_GLOBAL::RequestNewBudget(a2, 1);
          return (struct VIDMM_PROCESS_ADAPTER_INFO *)v5;
        }
      }
      __fastfail(3u);
    }
    v62 = i;
    v23 = *(_QWORD *)(*((_QWORD *)a2 + 4560) + 8LL * i);
    v24 = *(unsigned int *)(v23 + 664);
    v25 = 184 * v24;
    if ( !is_mul_ok(v24, 0xB8u) )
      v25 = -1;
    v9 = __CFADD__(v25, 8);
    v26 = v25 + 8;
    if ( v9 )
      v26 = -1;
    v27 = (unsigned __int64 *)operator new[](v26, 875653462, 256);
    if ( !v27 )
      break;
    v28 = v27 + 1;
    *v27 = v24;
    `vector constructor iterator'(
      v27 + 1,
      0xB8u,
      (unsigned int)v24,
      (void *(*)(void *))VIDMM_PROCESS_COMMITMENT_INFO::VIDMM_PROCESS_COMMITMENT_INFO);
    if ( !v28 )
      break;
    for ( k = 0; k < *(_DWORD *)(v23 + 664); v28[23 * v30] = this )
      v30 = k++;
    v21 = (_QWORD *)(v5 + 8);
    *(_QWORD *)(304 * v62 + *(_QWORD *)(v5 + 8)) = v28;
  }
  _InterlockedAdd(&dword_140086724, 1u);
  WdLogSingleEntry0(6);
  v15 = 859;
LABEL_11:
  v16 = L"Couldn't allocate memory for commitment info.";
LABEL_12:
  v17 = 262145;
LABEL_13:
  WdLogGlobalForLineNumber = v15;
  DxgkLogInternalTriageEvent(v13, v17, v14, (_DWORD)v16, v15, 0, 0, 0);
LABEL_54:
  v45 = *(CVirtualAddressAllocator **)(v5 + 24);
  if ( v45 )
    CVirtualAddressAllocator::DestroyVaAllocator(v45, 0);
  VIDMM_PROCESS_ADAPTER_INFO::`scalar deleting destructor'((VIDMM_PROCESS_ADAPTER_INFO *)v5, v18);
  return 0;
}

```

## disassembly

```asm
0x1400fa608  mov     [rsp+arg_0], rbx
0x1400fa60d  push    rbp
0x1400fa60e  push    rsi
0x1400fa60f  push    rdi
0x1400fa610  push    r12
0x1400fa612  push    r13
0x1400fa614  push    r14
0x1400fa616  push    r15
0x1400fa618  sub     rsp, 80h
0x1400fa61f  mov     rsi, rdx
0x1400fa622  mov     r12, rcx
0x1400fa625  mov     r13d, 33316956h
0x1400fa62b  mov     r8d, 40h ; '@'
0x1400fa631  mov     edx, r13d
0x1400fa634  mov     ecx, 0C0h
0x1400fa639  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fa63e  xor     r15d, r15d
0x1400fa641  mov     rbx, rax
0x1400fa644  lea     edi, [r15+1]
0x1400fa648  test    rax, rax
0x1400fa64b  jz      loc_1400FAC84
0x1400fa651  mov     [rax+68h], r15
0x1400fa655  lea     rcx, [rdi-2]
0x1400fa659  mov     [rax+70h], r15
0x1400fa65d  mov     r8d, 100h
0x1400fa663  mov     [rax+78h], r15
0x1400fa667  mov     [rax+80h], r15
0x1400fa66e  mov     [rax+88h], r15d
0x1400fa675  mov     [rax+90h], r15
0x1400fa67c  mov     [rax+98h], r15
0x1400fa683  mov     [rax+0A0h], r15d
0x1400fa68a  mov     [rax+0A4h], edi
0x1400fa690  mov     dword ptr [rax+0A8h], 36h ; '6'
0x1400fa69a  mov     dword ptr [rax+0B0h], 2020000h
0x1400fa6a4  mov     [rax+0B4h], r15b
0x1400fa6ab  mov     [rax+20h], r15
0x1400fa6af  add     rax, 58h ; 'X'
0x1400fa6b3  mov     [rax+8], rax
0x1400fa6b7  mov     [rax], rax
0x1400fa6ba  mov     eax, 130h
0x1400fa6bf  mov     [rbx+48h], r15
0x1400fa6c3  mov     [rbx+50h], r15
0x1400fa6c7  mov     r14d, [rsi+0C28h]
0x1400fa6ce  mul     r14
0x1400fa6d1  mov     edx, 61316956h
0x1400fa6d6  cmovb   rax, rcx
0x1400fa6da  add     rax, 8
0x1400fa6de  cmovb   rax, rcx
0x1400fa6e2  mov     rcx, rax
0x1400fa6e5  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fa6ea  test    rax, rax
0x1400fa6ed  jz      short loc_1400FA70F
0x1400fa6ef  lea     rbp, [rax+8]
0x1400fa6f3  mov     [rax], r14
0x1400fa6f6  mov     rcx, rbp; void *
0x1400fa6f9  lea     r9, ??0VIDMM_PROCESS_PHYSICAL_ADAPTER_INFO@@QEAA@XZ; void *(*)(void *)
0x1400fa700  mov     r8d, r14d; unsigned __int64
0x1400fa703  mov     edx, 130h; unsigned __int64
0x1400fa708  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400fa70d  jmp     short loc_1400FA712
0x1400fa70f  mov     rbp, r15
0x1400fa712  lea     rax, [rbx+8]
0x1400fa716  mov     [rsp+0B8h+arg_10], rax
0x1400fa71e  mov     [rax], rbp
0x1400fa721  test    rbp, rbp
0x1400fa724  jnz     short loc_1400FA771
0x1400fa726  lock add cs:dword_140086724, edi
0x1400fa72d  lea     ecx, [rbp+6]
0x1400fa730  call    cs:__imp_WdLogSingleEntry0
0x1400fa737  nop     dword ptr [rax+rax+00h]
0x1400fa73c  mov     eax, 345h
0x1400fa741  lea     r9, aCouldnTAllocat_48; "Couldn't allocate memory for commitment"...
0x1400fa748  mov     edx, 40001h
0x1400fa74d  mov     [rsp+0B8h+var_80], r15
0x1400fa752  mov     [rsp+0B8h+var_88], r15
0x1400fa757  mov     [rsp+0B8h+var_90], r15
0x1400fa75c  mov     [rsp+0B8h+Data], rax
0x1400fa761  mov     cs:WdLogGlobalForLineNumber, eax
0x1400fa767  call    DxgkLogInternalTriageEvent
0x1400fa76c  jmp     loc_1400FAB5D
0x1400fa771  mov     r8d, 100h
0x1400fa777  mov     edx, r13d
0x1400fa77a  mov     ecx, 6D8h
0x1400fa77f  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fa784  test    rax, rax
0x1400fa787  jz      short loc_1400FA793
0x1400fa789  mov     rcx, rax; this
0x1400fa78c  call    ??0VIDMM_PROCESS_ADAPTER_INFO_PAGED@@QEAA@XZ; VIDMM_PROCESS_ADAPTER_INFO_PAGED::VIDMM_PROCESS_ADAPTER_INFO_PAGED(void)
0x1400fa791  jmp     short loc_1400FA796
0x1400fa793  mov     rax, r15
0x1400fa796  lea     r13, [rbx+0B8h]
0x1400fa79d  mov     [rsp+0B8h+var_68], r13
0x1400fa7a2  mov     [r13+0], rax
0x1400fa7a6  test    rax, rax
0x1400fa7a9  jnz     short loc_1400FA7D2
0x1400fa7ab  lock add cs:dword_140086720, edi
0x1400fa7b2  lea     ecx, [rax+6]
0x1400fa7b5  call    cs:__imp_WdLogSingleEntry0
0x1400fa7bc  nop     dword ptr [rax+rax+00h]
0x1400fa7c1  mov     eax, 34Dh
0x1400fa7c6  lea     r9, aCouldnTAllocat_11; "Couldn't allocate memory for paged adap"...
0x1400fa7cd  jmp     loc_1400FA748
0x1400fa7d2  mov     r13, [rsp+0B8h+arg_10]
0x1400fa7da  mov     r14d, r15d
0x1400fa7dd  movzx   eax, r14w
0x1400fa7e1  cmp     eax, [rsi+0C28h]
0x1400fa7e7  jnb     loc_1400FA8D2
0x1400fa7ed  mov     rax, [rsi+8E80h]
0x1400fa7f4  mov     r8d, 100h
0x1400fa7fa  movzx   ecx, r14w
0x1400fa7fe  mov     [rsp+0B8h+arg_18], rcx
0x1400fa806  mov     r13, [rax+rcx*8]
0x1400fa80a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400fa811  mov     eax, 0B8h
0x1400fa816  mov     r15d, [r13+298h]
0x1400fa81d  mul     r15
0x1400fa820  mov     edx, 34316956h
0x1400fa825  cmovb   rax, rcx
0x1400fa829  add     rax, 8
0x1400fa82d  cmovb   rax, rcx
0x1400fa831  mov     rcx, rax
0x1400fa834  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fa839  test    rax, rax
0x1400fa83c  jz      short loc_1400FA8AD
0x1400fa83e  lea     rbp, [rax+8]
0x1400fa842  mov     [rax], r15
0x1400fa845  mov     rcx, rbp; void *
0x1400fa848  lea     r9, ??0VIDMM_PROCESS_COMMITMENT_INFO@@QEAA@XZ; void *(*)(void *)
0x1400fa84f  mov     r8d, r15d; unsigned __int64
0x1400fa852  mov     edx, 0B8h; unsigned __int64
0x1400fa857  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400fa85c  xor     r15d, r15d
0x1400fa85f  test    rbp, rbp
0x1400fa862  jz      short loc_1400FA8B0
0x1400fa864  mov     edx, r15d
0x1400fa867  cmp     [r13+298h], r15d
0x1400fa86e  jbe     short loc_1400FA888
0x1400fa870  mov     eax, edx
0x1400fa872  add     edx, edi
0x1400fa874  imul    rcx, rax, 0B8h
0x1400fa87b  mov     [rcx+rbp], r12
0x1400fa87f  cmp     edx, [r13+298h]
0x1400fa886  jb      short loc_1400FA870
0x1400fa888  imul    rcx, [rsp+0B8h+arg_18], 130h
0x1400fa894  mov     r13, [rsp+0B8h+arg_10]
0x1400fa89c  add     r14w, di
0x1400fa8a0  mov     rax, [r13+0]
0x1400fa8a4  mov     [rcx+rax], rbp
0x1400fa8a8  jmp     loc_1400FA7DD
0x1400fa8ad  xor     r15d, r15d
0x1400fa8b0  lock add cs:dword_140086724, edi
0x1400fa8b7  mov     ecx, 6
0x1400fa8bc  call    cs:__imp_WdLogSingleEntry0
0x1400fa8c3  nop     dword ptr [rax+rax+00h]
0x1400fa8c8  mov     eax, 35Bh
0x1400fa8cd  jmp     loc_1400FA741
0x1400fa8d2  test    byte ptr [rsi+9168h], 10h
0x1400fa8d9  mov     ebp, 4B677844h
0x1400fa8de  jz      loc_1400FA987
0x1400fa8e4  mov     eax, [r12+88h]
0x1400fa8ec  test    al, 2
0x1400fa8ee  jnz     loc_1400FA987
0x1400fa8f4  mov     r8d, 100h
0x1400fa8fa  mov     edx, ebp
0x1400fa8fc  lea     ecx, [r8-60h]
0x1400fa900  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fa905  test    rax, rax
0x1400fa908  jz      short loc_1400FA914
0x1400fa90a  mov     rcx, rax; this
0x1400fa90d  call    ??0CVirtualAddressAllocator@@QEAA@XZ; CVirtualAddressAllocator::CVirtualAddressAllocator(void)
0x1400fa912  jmp     short loc_1400FA917
0x1400fa914  mov     rax, r15
0x1400fa917  mov     [rbx+18h], rax
0x1400fa91b  test    rax, rax
0x1400fa91e  jnz     short loc_1400FA944
0x1400fa920  mov     ecx, edi
0x1400fa922  call    cs:__imp_WdLogSingleEntry0
0x1400fa929  nop     dword ptr [rax+rax+00h]
0x1400fa92e  mov     eax, 370h
0x1400fa933  lea     r9, aFailedToAlloca_31; "Failed to allocate CVirtualAddressAlloc"...
0x1400fa93a  mov     edx, 40000h
0x1400fa93f  jmp     loc_1400FA74D
0x1400fa944  mov     ecx, [rsi+9160h]
0x1400fa94a  mov     rdx, rdi
0x1400fa94d  mov     r8d, [rsi+91B4h]; unsigned __int64
0x1400fa954  mov     r9, rsi; struct VIDMM_GLOBAL *
0x1400fa957  shl     rdx, cl; unsigned __int64
0x1400fa95a  mov     rcx, rax; this
0x1400fa95d  mov     [rsp+0B8h+Data], r12; struct VIDMM_PROCESS *
0x1400fa962  call    ?InitializeVaAllocator@CVirtualAddressAllocator@@QEAAJ_K0PEAVVIDMM_GLOBAL@@PEAVVIDMM_PROCESS@@@Z; CVirtualAddressAllocator::InitializeVaAllocator(unsigned __int64,unsigned __int64,VIDMM_GLOBAL *,VIDMM_PROCESS *)
0x1400fa967  test    eax, eax
0x1400fa969  jns     short loc_1400FA987
0x1400fa96b  mov     ecx, edi
0x1400fa96d  call    cs:__imp_WdLogSingleEntry0
0x1400fa974  nop     dword ptr [rax+rax+00h]
0x1400fa979  mov     eax, 37Ch
0x1400fa97e  lea     r9, aFailedToInitia_22; "Failed to initialize CVirtualAddressAll"...
0x1400fa985  jmp     short loc_1400FA93A
0x1400fa987  mov     r8d, 102h
0x1400fa98d  mov     edx, ebp
0x1400fa98f  mov     ecx, 208h
0x1400fa994  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fa999  mov     r15, rax
0x1400fa99c  test    rax, rax
0x1400fa99f  jnz     short loc_1400FA9C8
0x1400fa9a1  lock add cs:dword_14008687C, edi
0x1400fa9a8  lea     ecx, [rax+6]
0x1400fa9ab  call    cs:__imp_WdLogSingleEntry0
0x1400fa9b2  nop     dword ptr [rax+rax+00h]
0x1400fa9b7  mov     eax, 385h
0x1400fa9bc  lea     r9, aFailedToCreate_26; "Failed to create name string for GpuPer"...
0x1400fa9c3  jmp     loc_1400FA748
0x1400fa9c8  xor     r14d, r14d
0x1400fa9cb  xor     ebp, ebp
0x1400fa9cd  cmp     ebp, [rsi+0C28h]
0x1400fa9d3  jnb     loc_1400FAB4D
0x1400fa9d9  mov     r13, [r13+0]
0x1400fa9dd  add     r13, 8
0x1400fa9e1  movzx   eax, bp
0x1400fa9e4  imul    rcx, rax, 130h
0x1400fa9eb  add     r13, rcx
0x1400fa9ee  xor     r14d, r14d
0x1400fa9f1  mov     [r13+10h], rbx
0x1400fa9f5  mov     r9, [r12+150h]; struct VIDMM_PARTITION *
0x1400fa9fd  mov     r8d, r14d; enum _D3DKMT_MEMORY_SEGMENT_GROUP
0x1400faa00  mov     edx, ebp; unsigned int
0x1400faa02  mov     rcx, rsi; this
0x1400faa05  call    ?GetSegmentGroupState@VIDMM_GLOBAL@@QEBAPEBUVIDMM_SEGMENT_GROUP_STATE@@KW4_D3DKMT_MEMORY_SEGMENT_GROUP@@PEAUVIDMM_PARTITION@@@Z; VIDMM_GLOBAL::GetSegmentGroupState(ulong,_D3DKMT_MEMORY_SEGMENT_GROUP,VIDMM_PARTITION *)
0x1400faa0a  mov     rax, [rax+20h]
0x1400faa0e  mov     [r13+r14*8+18h], rax
0x1400faa13  add     r14d, edi
0x1400faa16  cmp     r14d, 2
0x1400faa1a  jl      short loc_1400FA9F5
0x1400faa1c  mov     rcx, [rsi+18h]
0x1400faa20  lea     r8, aPidULuid0x08x0; "pid_%u_luid_0x%08X_0x%08X_phys_%u"
0x1400faa27  mov     r9d, [r12+18h]
0x1400faa2c  xorps   xmm0, xmm0
0x1400faa2f  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x1400faa34  mov     dword ptr [rsp+0B8h+var_88], ebp
0x1400faa38  mov     edx, 208h; cbDest
0x1400faa3d  mov     eax, [rcx+19Ch]
0x1400faa43  mov     dword ptr [rsp+0B8h+var_90], eax
0x1400faa47  mov     eax, [rcx+1A0h]
0x1400faa4d  mov     rcx, r15; pszDest
0x1400faa50  mov     dword ptr [rsp+0B8h+Data], eax
0x1400faa54  call    RtlStringCbPrintfW
0x1400faa59  mov     r14d, eax
0x1400faa5c  test    eax, eax
0x1400faa5e  js      loc_1400FAB0D
0x1400faa64  mov     rdx, r15; SourceString
0x1400faa67  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1400faa6c  call    cs:__imp_RtlInitUnicodeString
0x1400faa73  nop     dword ptr [rax+rax+00h]
0x1400faa78  mov     rdx, cs:GpuPerformanceCounterSetProcessMemory; Registration
0x1400faa7f  lea     rax, [rsp+0B8h+var_60]
0x1400faa84  lea     rcx, [r13+0F8h]; Instance
0x1400faa8b  mov     [rsp+0B8h+Data], rax; Data
0x1400faa90  mov     r9d, edi; Count
0x1400faa93  mov     [rsp+0B8h+var_60.Data], r13
0x1400faa98  lea     r8, [rsp+0B8h+DestinationString]; Name
0x1400faa9d  mov     [rsp+0B8h+var_60.Size], 128h
0x1400faaa5  call    cs:__imp_PcwCreateInstance
0x1400faaac  nop     dword ptr [rax+rax+00h]
0x1400faab1  mov     r14d, eax
0x1400faab4  test    eax, eax
0x1400faab6  js      short loc_1400FAAC7
0x1400faab8  mov     r13, [rsp+0B8h+arg_10]
0x1400faac0  add     ebp, edi
0x1400faac2  jmp     loc_1400FA9CD
0x1400faac7  lock add cs:dword_14008687C, edi
0x1400faace  mov     ecx, 6
0x1400faad3  call    cs:__imp_WdLogSingleEntry0
0x1400faada  nop     dword ptr [rax+rax+00h]
0x1400faadf  mov     [rsp+0B8h+var_80], 0
0x1400faae8  lea     r9, aFailedToCreate_18; "Failed to create GpuPerformanceCounterS"...
0x1400faaef  mov     [rsp+0B8h+var_88], 0
0x1400faaf8  mov     eax, 3A7h
0x1400faafd  mov     [rsp+0B8h+var_90], 0
0x1400fab06  mov     edx, 40001h
0x1400fab0b  jmp     short loc_1400FAB3D
0x1400fab0d  mov     ecx, edi
0x1400fab0f  call    cs:__imp_WdLogSingleEntry0
0x1400fab16  nop     dword ptr [rax+rax+00h]
0x1400fab1b  xor     ecx, ecx
0x1400fab1d  lea     r9, aFailedToCreate_26; "Failed to create name string for GpuPer"...
0x1400fab24  mov     [rsp+0B8h+var_80], rcx
0x1400fab29  mov     eax, 39Fh
0x1400fab2e  mov     [rsp+0B8h+var_88], rcx
0x1400fab33  mov     edx, 40000h
0x1400fab38  mov     [rsp+0B8h+var_90], rcx
0x1400fab3d  mov     [rsp+0B8h+Data], rax
0x1400fab42  mov     cs:WdLogGlobalForLineNumber, eax
0x1400fab48  call    DxgkLogInternalTriageEvent
0x1400fab4d  mov     rcx, r15; void *
0x1400fab50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fab55  xor     r15d, r15d
0x1400fab58  test    r14d, r14d
0x1400fab5b  jns     short loc_1400FAB7A
0x1400fab5d  mov     rcx, [rbx+18h]; this
0x1400fab61  test    rcx, rcx
  ... truncated ...
```
