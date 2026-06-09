# VIDMM_PROCESS::InitializeProcessAdapterInfo(VIDMM_GLOBAL *)

- ea: `0x140116c04`
- end: `0x140117307`
- name: `?InitializeProcessAdapterInfo@VIDMM_PROCESS@@IEAAPEAUVIDMM_PROCESS_ADAPTER_INFO@@PEAVVIDMM_GLOBAL@@@Z`
- size: `1795`
- prototype: `struct VIDMM_PROCESS_ADAPTER_INFO *__fastcall(VIDMM_PROCESS *__hidden this, struct VIDMM_GLOBAL *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401168a8`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002bcc0`
- `0x14002bddc`
- `0x14002c5d0`
- `0x14002e4a4`
- `0x14002e6c0`
- `0x14002ed58`
- `0x140031304`
- `0x1400330f0`
- `0x140034920`
- `0x1400349c0`
- `0x14003b3a4`
- `0x1400ac0c8`
- `0x1400b8af4`
- `0x140102cf4`
- `0x140103074`
- `0x140104d50`
- `0x14010d940`
- `0x140116c04`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140117080`
- `ntoskrnl!RtlInitUnicodeString` at `0x140117080`
- `ntoskrnl!PcwCreateInstance` at `0x1401170b9`
- `ntoskrnl!PcwCreateInstance` at `0x1401170b9`
- `watchdog!WdLogSingleEntry0` at `0x140116d27`
- `watchdog!WdLogSingleEntry0` at `0x140116dad`
- `watchdog!WdLogSingleEntry0` at `0x140116efb`
- `watchdog!WdLogSingleEntry0` at `0x140116f22`
- `watchdog!WdLogSingleEntry0` at `0x140116f6d`
- `watchdog!WdLogSingleEntry0` at `0x140116fab`
- `watchdog!WdLogSingleEntry0` at `0x1401170f3`
- `watchdog!WdLogSingleEntry0` at `0x14011712f`
- `watchdog!WdLogSingleEntry0` at `0x1401172ad`
- `watchdog!WdLogSingleEntry0` at `0x140116d27`
- `watchdog!WdLogSingleEntry0` at `0x140116dad`
- `watchdog!WdLogSingleEntry0` at `0x140116efb`
- `watchdog!WdLogSingleEntry0` at `0x140116f22`
- `watchdog!WdLogSingleEntry0` at `0x140116f6d`
- `watchdog!WdLogSingleEntry0` at `0x140116fab`
- `watchdog!WdLogSingleEntry0` at `0x1401170f3`
- `watchdog!WdLogSingleEntry0` at `0x14011712f`
- `watchdog!WdLogSingleEntry0` at `0x1401172ad`

## string_xrefs

- `0x140116d38`: `Couldn't allocate memory for commitment info.`
- `0x140116fbc`: `Failed to create name string for GpuPerformanceCounterSetProcessMemory`
- `0x14011713d`: `Failed to create name string for GpuPerformanceCounterSetProcessMemory`
- `0x140117108`: `Failed to create GpuPerformanceCounterSetProcessMemory`

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
  _QWORD *v13; // r15
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // rax
  const wchar_t *v17; // r9
  int v18; // edx
  unsigned int v19; // edx
  VIDMM_PROCESS_ADAPTER_INFO_PAGED *v20; // rax
  VIDMM_PROCESS_ADAPTER_INFO_PAGED *v21; // rax
  unsigned __int16 v22; // r14
  __int64 v23; // r12
  unsigned __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int64 *v27; // rax
  _QWORD *v28; // rbp
  unsigned int i; // edx
  __int64 v30; // rax
  CVirtualAddressAllocator *v31; // rax
  CVirtualAddressAllocator *v32; // rax
  wchar_t *v33; // r12
  NTSTATUS v34; // r14d
  unsigned int v35; // ebp
  __int64 v36; // r15
  __int64 v37; // r14
  const struct VIDMM_SEGMENT_GROUP_STATE *SegmentGroupState; // rax
  __int64 v39; // rcx
  __int64 v40; // r9
  int v41; // ecx
  int v42; // r8d
  const wchar_t *v43; // r9
  __int64 v44; // rax
  int v45; // edx
  CVirtualAddressAllocator *v46; // rcx
  int v47; // eax
  unsigned int v48; // eax
  _QWORD *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  DXGPROCESS *v52; // rcx
  struct VIDMM_GLOBAL **v53; // rdx
  int v55; // ecx
  int v56; // r8d
  PPCW_DATA Data; // [rsp+20h] [rbp-98h]
  __int64 v58; // [rsp+28h] [rbp-90h]
  __int64 v59; // [rsp+30h] [rbp-88h]
  __int64 v60; // [rsp+50h] [rbp-68h]
  struct _PCW_DATA v61; // [rsp+58h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-50h] BYREF
  __int64 v63; // [rsp+D8h] [rbp+20h]

  v4 = operator new(192, 858876246, 64);
  v5 = v4;
  if ( v4 )
  {
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
    *(_QWORD *)(v5 + 72) = 0;
    *(_QWORD *)(v5 + 80) = 0;
    v6[1] = v6;
    *v6 = v6;
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
    v13 = (_QWORD *)(v5 + 8);
    *(_QWORD *)(v5 + 8) = v12;
    if ( !v12 )
    {
      _InterlockedAdd(&dword_140087704, 1u);
      WdLogSingleEntry0(6);
      v16 = 891;
LABEL_11:
      v17 = L"Couldn't allocate memory for commitment info.";
LABEL_12:
      v18 = 262145;
LABEL_13:
      WdLogGlobalForLineNumber = v16;
      DxgkLogInternalTriageEvent(v14, v18, v15, (_DWORD)v17, v16, 0, 0, 0);
LABEL_56:
      v46 = *(CVirtualAddressAllocator **)(v5 + 24);
      if ( v46 )
        CVirtualAddressAllocator::DestroyVaAllocator(v46, 0);
      VIDMM_PROCESS_ADAPTER_INFO::`scalar deleting destructor'((VIDMM_PROCESS_ADAPTER_INFO *)v5, v19);
      return 0;
    }
    v20 = (VIDMM_PROCESS_ADAPTER_INFO_PAGED *)operator new(1752, 858876246, 256);
    if ( v20 )
      v21 = VIDMM_PROCESS_ADAPTER_INFO_PAGED::VIDMM_PROCESS_ADAPTER_INFO_PAGED(v20);
    else
      v21 = 0;
    v60 = v5 + 184;
    *(_QWORD *)(v5 + 184) = v21;
    if ( !v21 )
    {
      _InterlockedAdd(&dword_140087700, 1u);
      WdLogSingleEntry0(6);
      v16 = 899;
      v17 = L"Couldn't allocate memory for paged adapter info.";
      goto LABEL_12;
    }
    v22 = 0;
    if ( *((_DWORD *)a2 + 778) )
    {
      while ( 1 )
      {
        v63 = v22;
        v23 = *(_QWORD *)(*((_QWORD *)a2 + 4560) + 8LL * v22);
        v24 = *(unsigned int *)(v23 + 928);
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
        for ( i = 0; i < *(_DWORD *)(v23 + 928); v28[23 * v30] = this )
          v30 = i++;
        v13 = (_QWORD *)(v5 + 8);
        ++v22;
        *(_QWORD *)(304 * v63 + *(_QWORD *)(v5 + 8)) = v28;
        if ( (unsigned int)v22 >= *((_DWORD *)a2 + 778) )
          goto LABEL_29;
      }
      _InterlockedAdd(&dword_140087704, 1u);
      WdLogSingleEntry0(6);
      v16 = 913;
      goto LABEL_11;
    }
LABEL_29:
    if ( (*((_BYTE *)a2 + 37224) & 0x10) != 0 && ((_DWORD)this[18] & 2) == 0 )
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
        v16 = 934;
        v17 = L"Failed to allocate CVirtualAddressAllocator";
LABEL_37:
        v18 = 0x40000;
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
        v16 = 946;
        v17 = L"Failed to initialize CVirtualAddressAllocator";
        goto LABEL_37;
      }
    }
    v33 = (wchar_t *)operator new[](520, 1265072196, 258);
    if ( !v33 )
    {
      _InterlockedAdd(&dword_14008785C, 1u);
      WdLogSingleEntry0(6);
      v16 = 955;
      v17 = L"Failed to create name string for GpuPerformanceCounterSetProcessMemory";
      goto LABEL_12;
    }
    v34 = 0;
    v35 = 0;
    if ( *((_DWORD *)a2 + 778) )
    {
      while ( 1 )
      {
        v36 = 304LL * (unsigned __int16)v35 + *v13 + 8LL;
        v37 = 0;
        *(_QWORD *)(v36 + 16) = v5;
        do
        {
          if ( g_Feature_ResourcePoolManagement )
            SegmentGroupState = VIDMM_GLOBAL::GetSegmentGroupState(
                                  a2,
                                  v35,
                                  (enum _D3DKMT_MEMORY_SEGMENT_GROUP)v37,
                                  this[46]);
          else
            SegmentGroupState = VIDMM_GLOBAL::GetSegmentGroupState(
                                  a2,
                                  v35,
                                  (enum _D3DKMT_MEMORY_SEGMENT_GROUP)v37,
                                  this[43]);
          *(_QWORD *)(v36 + 8 * v37 + 24) = *((_QWORD *)SegmentGroupState + 4);
          v37 = (unsigned int)(v37 + 1);
        }
        while ( (int)v37 < 2 );
        v39 = *((_QWORD *)a2 + 3);
        v40 = *((unsigned int *)this + 6);
        DestinationString = 0;
        LODWORD(v59) = v35;
        LODWORD(v58) = *(_DWORD *)(v39 + 412);
        LODWORD(Data) = *(_DWORD *)(v39 + 416);
        v34 = RtlStringCbPrintfW(v33, 0x208u, L"pid_%u_luid_0x%08X_0x%08X_phys_%u", v40, Data, v58, v59);
        if ( v34 < 0 )
          break;
        RtlInitUnicodeString(&DestinationString, v33);
        v61.Data = (const void *)v36;
        v61.Size = 296;
        v34 = PcwCreateInstance(
                (PPCW_INSTANCE *)(v36 + 248),
                GpuPerformanceCounterSetProcessMemory,
                &DestinationString,
                1u,
                &v61);
        if ( v34 < 0 )
        {
          _InterlockedAdd(&dword_14008785C, 1u);
          WdLogSingleEntry0(6);
          v43 = L"Failed to create GpuPerformanceCounterSetProcessMemory";
          v44 = 997;
          v45 = 262145;
          goto LABEL_54;
        }
        v13 = (_QWORD *)(v5 + 8);
        if ( ++v35 >= *((_DWORD *)a2 + 778) )
          goto LABEL_55;
      }
      WdLogSingleEntry0(1);
      v41 = 0;
      v43 = L"Failed to create name string for GpuPerformanceCounterSetProcessMemory";
      v44 = 989;
      v45 = 0x40000;
LABEL_54:
      WdLogGlobalForLineNumber = v44;
      DxgkLogInternalTriageEvent(v41, v45, v42, (_DWORD)v43, v44, 0, 0, 0);
    }
LABEL_55:
    operator delete(v33);
    if ( v34 < 0 )
      goto LABEL_56;
    v47 = *(_DWORD *)(*(_QWORD *)v60 + 24LL);
    if ( dword_140087388 )
      v48 = v47 & 0xFFFFFFFE;
    else
      v48 = v47 | 1;
    *(_DWORD *)(*(_QWORD *)v60 + 24LL) = v48 | 6;
    if ( (VIDMM_GLOBAL::_Config & 4) != 0
      && DXGPROCESS::GetCurrent()
      && (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)v60 + 36LL) = 1;
    }
    *(_QWORD *)v5 = a2;
    *(_DWORD *)(v5 + 136) = 1;
    *(_QWORD *)(v5 + 16) = this;
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)&DestinationString,
      (struct VIDMM_GLOBAL *)((char *)a2 + 37376));
    v49 = (_QWORD *)((char *)a2 + 37424);
    v50 = *((_QWORD *)a2 + 4678);
    if ( *(struct VIDMM_GLOBAL **)(v50 + 8) == (struct VIDMM_GLOBAL *)((char *)a2 + 37424) )
    {
      *(_QWORD *)(v5 + 40) = v50;
      *(_QWORD *)(v5 + 48) = v49;
      *(_QWORD *)(v50 + 8) = v5 + 40;
      *v49 = v5 + 40;
      v51 = *((_QWORD *)a2 + 5172);
      *((_QWORD *)a2 + 5172) = v51 + 1;
      *(_QWORD *)(v5 + 104) = v51;
      if ( !(unsigned int)Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_72;
      v52 = *(DXGPROCESS **)(*(_QWORD *)(v5 + 16) + 80LL);
      if ( !v52 || !DXGPROCESS::UmdManagesResidency(v52) )
        goto LABEL_72;
      v53 = (struct VIDMM_GLOBAL **)*((_QWORD *)a2 + 4542);
      if ( *v53 == (struct VIDMM_GLOBAL *)((char *)a2 + 36328) )
      {
        *(_QWORD *)(v5 + 56) = (char *)a2 + 36328;
        *(_QWORD *)(v5 + 64) = v53;
        *v53 = (struct VIDMM_GLOBAL *)(v5 + 56);
        *((_QWORD *)a2 + 4542) = v5 + 56;
LABEL_72:
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&DestinationString);
        VIDMM_GLOBAL::RequestNewBudget(a2, 1);
        return (struct VIDMM_PROCESS_ADAPTER_INFO *)v5;
      }
    }
    __fastfail(3u);
  }
  _InterlockedAdd(&dword_1400876FC, 1u);
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 883;
  DxgkLogInternalTriageEvent(
    v55,
    262145,
    v56,
    (unsigned int)L"Couldn't allocate memory for adapter info.",
    883,
    0,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x140116c04  mov     [rsp+arg_0], rbx
0x140116c09  push    rbp
0x140116c0a  push    rsi
0x140116c0b  push    rdi
0x140116c0c  push    r12
0x140116c0e  push    r13
0x140116c10  push    r14
0x140116c12  push    r15
0x140116c14  sub     rsp, 80h
0x140116c1b  mov     r13, rcx
0x140116c1e  mov     rsi, rdx
0x140116c21  mov     ecx, 0C0h
0x140116c26  mov     edx, 33316956h
0x140116c2b  lea     r8d, [rcx-80h]
0x140116c2f  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140116c34  xor     r12d, r12d
0x140116c37  mov     rbx, rax
0x140116c3a  lea     edi, [r12+1]
0x140116c3f  test    rax, rax
0x140116c42  jz      loc_1401172A1
0x140116c48  mov     [rax+68h], r12
0x140116c4c  lea     rcx, [rdi-2]
0x140116c50  mov     [rax+70h], r12
0x140116c54  mov     r15d, 130h
0x140116c5a  mov     [rax+78h], r12
0x140116c5e  mov     [rax+80h], r12
0x140116c65  mov     [rax+88h], r12d
0x140116c6c  mov     [rax+90h], r12
0x140116c73  lea     r8d, [r15-30h]
0x140116c77  mov     [rax+98h], r12
0x140116c7e  mov     [rax+0A0h], r12d
0x140116c85  mov     [rax+0A4h], edi
0x140116c8b  mov     dword ptr [rax+0A8h], 36h ; '6'
0x140116c95  mov     dword ptr [rax+0B0h], 2020000h
0x140116c9f  mov     [rax+0B4h], r12b
0x140116ca6  mov     [rax+20h], r12
0x140116caa  add     rax, 58h ; 'X'
0x140116cae  mov     [rbx+48h], r12
0x140116cb2  mov     [rbx+50h], r12
0x140116cb6  mov     [rax+8], rax
0x140116cba  mov     [rax], rax
0x140116cbd  mov     eax, r15d
0x140116cc0  mov     r14d, [rsi+0C28h]
0x140116cc7  mul     r14
0x140116cca  mov     edx, 61316956h
0x140116ccf  cmovb   rax, rcx
0x140116cd3  add     rax, 8
0x140116cd7  cmovb   rax, rcx
0x140116cdb  mov     rcx, rax
0x140116cde  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140116ce3  test    rax, rax
0x140116ce6  jz      short loc_140116D06
0x140116ce8  lea     rbp, [rax+8]
0x140116cec  mov     [rax], r14
0x140116cef  mov     rcx, rbp; void *
0x140116cf2  lea     r9, ??0VIDMM_PROCESS_PHYSICAL_ADAPTER_INFO@@QEAA@XZ; void *(*)(void *)
0x140116cf9  mov     r8d, r14d; unsigned __int64
0x140116cfc  mov     edx, r15d; unsigned __int64
0x140116cff  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x140116d04  jmp     short loc_140116D09
0x140116d06  mov     rbp, r12
0x140116d09  lea     r15, [rbx+8]
0x140116d0d  mov     [rsp+0B8h+arg_10], r15
0x140116d15  mov     [r15], rbp
0x140116d18  test    rbp, rbp
0x140116d1b  jnz     short loc_140116D68
0x140116d1d  lock add cs:dword_140087704, edi
0x140116d24  lea     ecx, [rbp+6]
0x140116d27  call    cs:__imp_WdLogSingleEntry0
0x140116d2e  nop     dword ptr [rax+rax+00h]
0x140116d33  mov     eax, 37Bh
0x140116d38  lea     r9, aCouldnTAllocat_52; "Couldn't allocate memory for commitment"...
0x140116d3f  mov     edx, 40001h
0x140116d44  mov     [rsp+0B8h+var_80], r12
0x140116d49  mov     [rsp+0B8h+var_88], r12
0x140116d4e  mov     [rsp+0B8h+var_90], r12
0x140116d53  mov     [rsp+0B8h+Data], rax
0x140116d58  mov     cs:WdLogGlobalForLineNumber, eax
0x140116d5e  call    DxgkLogInternalTriageEvent
0x140116d63  jmp     loc_14011717D
0x140116d68  mov     edx, 33316956h
0x140116d6d  mov     ecx, 6D8h
0x140116d72  mov     r8d, 100h
0x140116d78  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140116d7d  test    rax, rax
0x140116d80  jz      short loc_140116D8C
0x140116d82  mov     rcx, rax; this
0x140116d85  call    ??0VIDMM_PROCESS_ADAPTER_INFO_PAGED@@QEAA@XZ; VIDMM_PROCESS_ADAPTER_INFO_PAGED::VIDMM_PROCESS_ADAPTER_INFO_PAGED(void)
0x140116d8a  jmp     short loc_140116D8F
0x140116d8c  mov     rax, r12
0x140116d8f  lea     rcx, [rbx+0B8h]
0x140116d96  mov     [rsp+0B8h+var_68], rcx
0x140116d9b  mov     [rcx], rax
0x140116d9e  test    rax, rax
0x140116da1  jnz     short loc_140116DCA
0x140116da3  lock add cs:dword_140087700, edi
0x140116daa  lea     ecx, [rax+6]
0x140116dad  call    cs:__imp_WdLogSingleEntry0
0x140116db4  nop     dword ptr [rax+rax+00h]
0x140116db9  mov     eax, 383h
0x140116dbe  lea     r9, aCouldnTAllocat_11; "Couldn't allocate memory for paged adap"...
0x140116dc5  jmp     loc_140116D3F
0x140116dca  mov     r14d, r12d
0x140116dcd  cmp     [rsi+0C28h], r12d
0x140116dd4  jbe     loc_140116EAE
0x140116dda  mov     rax, [rsi+8E80h]
0x140116de1  mov     r8d, 100h
0x140116de7  movzx   ecx, r14w
0x140116deb  mov     [rsp+0B8h+arg_18], rcx
0x140116df3  mov     r12, [rax+rcx*8]
0x140116df7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140116dfe  mov     eax, 0B8h
0x140116e03  mov     r15d, [r12+3A0h]
0x140116e0b  mul     r15
0x140116e0e  mov     edx, 34316956h
0x140116e13  cmovb   rax, rcx
0x140116e17  add     rax, 8
0x140116e1b  cmovb   rax, rcx
0x140116e1f  mov     rcx, rax
0x140116e22  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140116e27  test    rax, rax
0x140116e2a  jz      loc_140116EEF
0x140116e30  lea     rbp, [rax+8]
0x140116e34  mov     [rax], r15
0x140116e37  mov     rcx, rbp; void *
0x140116e3a  lea     r9, ??0VIDMM_PROCESS_COMMITMENT_INFO@@QEAA@XZ; void *(*)(void *)
0x140116e41  mov     r8d, r15d; unsigned __int64
0x140116e44  mov     edx, 0B8h; unsigned __int64
0x140116e49  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x140116e4e  test    rbp, rbp
0x140116e51  jz      loc_140116EEF
0x140116e57  xor     edx, edx
0x140116e59  cmp     [r12+3A0h], edx
0x140116e61  jbe     short loc_140116E7C
0x140116e63  mov     eax, edx
0x140116e65  add     edx, edi
0x140116e67  imul    rcx, rax, 0B8h
0x140116e6e  mov     [rcx+rbp], r13
0x140116e72  cmp     edx, [r12+3A0h]
0x140116e7a  jb      short loc_140116E63
0x140116e7c  imul    rcx, [rsp+0B8h+arg_18], 130h
0x140116e88  mov     r15, [rsp+0B8h+arg_10]
0x140116e90  add     r14w, di
0x140116e94  mov     rax, [r15]
0x140116e97  mov     [rcx+rax], rbp
0x140116e9b  movzx   eax, r14w
0x140116e9f  cmp     eax, [rsi+0C28h]
0x140116ea5  jb      loc_140116DDA
0x140116eab  xor     r12d, r12d
0x140116eae  test    byte ptr [rsi+9168h], 10h
0x140116eb5  mov     ebp, 4B677844h
0x140116eba  jz      loc_140116F87
0x140116ec0  mov     eax, [r13+90h]
0x140116ec7  test    al, 2
0x140116ec9  jnz     loc_140116F87
0x140116ecf  mov     r8d, 100h
0x140116ed5  mov     edx, ebp
0x140116ed7  lea     ecx, [r8-60h]
0x140116edb  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140116ee0  test    rax, rax
0x140116ee3  jz      short loc_140116F14
0x140116ee5  mov     rcx, rax; this
0x140116ee8  call    ??0CVirtualAddressAllocator@@QEAA@XZ; CVirtualAddressAllocator::CVirtualAddressAllocator(void)
0x140116eed  jmp     short loc_140116F17
0x140116eef  lock add cs:dword_140087704, edi
0x140116ef6  mov     ecx, 6
0x140116efb  call    cs:__imp_WdLogSingleEntry0
0x140116f02  nop     dword ptr [rax+rax+00h]
0x140116f07  mov     eax, 391h
0x140116f0c  xor     r12d, r12d
0x140116f0f  jmp     loc_140116D38
0x140116f14  mov     rax, r12
0x140116f17  mov     [rbx+18h], rax
0x140116f1b  test    rax, rax
0x140116f1e  jnz     short loc_140116F44
0x140116f20  mov     ecx, edi
0x140116f22  call    cs:__imp_WdLogSingleEntry0
0x140116f29  nop     dword ptr [rax+rax+00h]
0x140116f2e  mov     eax, 3A6h
0x140116f33  lea     r9, aFailedToAlloca_35; "Failed to allocate CVirtualAddressAlloc"...
0x140116f3a  mov     edx, 40000h
0x140116f3f  jmp     loc_140116D44
0x140116f44  mov     ecx, [rsi+9160h]
0x140116f4a  mov     rdx, rdi
0x140116f4d  mov     r8d, [rsi+91B4h]; unsigned __int64
0x140116f54  mov     r9, rsi; struct VIDMM_GLOBAL *
0x140116f57  shl     rdx, cl; unsigned __int64
0x140116f5a  mov     rcx, rax; this
0x140116f5d  mov     [rsp+0B8h+Data], r13; struct VIDMM_PROCESS *
0x140116f62  call    ?InitializeVaAllocator@CVirtualAddressAllocator@@QEAAJ_K0PEAVVIDMM_GLOBAL@@PEAVVIDMM_PROCESS@@@Z; CVirtualAddressAllocator::InitializeVaAllocator(unsigned __int64,unsigned __int64,VIDMM_GLOBAL *,VIDMM_PROCESS *)
0x140116f67  test    eax, eax
0x140116f69  jns     short loc_140116F87
0x140116f6b  mov     ecx, edi
0x140116f6d  call    cs:__imp_WdLogSingleEntry0
0x140116f74  nop     dword ptr [rax+rax+00h]
0x140116f79  mov     eax, 3B2h
0x140116f7e  lea     r9, aFailedToInitia_27; "Failed to initialize CVirtualAddressAll"...
0x140116f85  jmp     short loc_140116F3A
0x140116f87  mov     r8d, 102h
0x140116f8d  mov     edx, ebp
0x140116f8f  mov     ecx, 208h
0x140116f94  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140116f99  mov     r12, rax
0x140116f9c  test    rax, rax
0x140116f9f  jnz     short loc_140116FC8
0x140116fa1  lock add cs:dword_14008785C, edi
0x140116fa8  lea     ecx, [rax+6]
0x140116fab  call    cs:__imp_WdLogSingleEntry0
0x140116fb2  nop     dword ptr [rax+rax+00h]
0x140116fb7  mov     eax, 3BBh
0x140116fbc  lea     r9, aFailedToCreate_26; "Failed to create name string for GpuPer"...
0x140116fc3  jmp     loc_140116D3F
0x140116fc8  xor     r14d, r14d
0x140116fcb  xor     ebp, ebp
0x140116fcd  cmp     [rsi+0C28h], ebp
0x140116fd3  jbe     loc_14011716D
0x140116fd9  mov     r15, [r15]
0x140116fdc  add     r15, 8
0x140116fe0  movzx   eax, bp
0x140116fe3  imul    rcx, rax, 130h
0x140116fea  add     r15, rcx
0x140116fed  xor     r14d, r14d
0x140116ff0  mov     [r15+10h], rbx
0x140116ff4  cmp     cs:?g_Feature_ResourcePoolManagement@@3_NA, 0; bool g_Feature_ResourcePoolManagement
0x140116ffb  mov     r8d, r14d; enum _D3DKMT_MEMORY_SEGMENT_GROUP
0x140116ffe  mov     edx, ebp; unsigned int
0x140117000  mov     rcx, rsi; this
0x140117003  jz      short loc_140117013
0x140117005  mov     r9, [r13+170h]; struct VIDMM_RESOURCE_POOL *
0x14011700c  call    ?GetSegmentGroupState@VIDMM_GLOBAL@@QEBAPEBUVIDMM_SEGMENT_GROUP_STATE@@KW4_D3DKMT_MEMORY_SEGMENT_GROUP@@PEAUVIDMM_RESOURCE_POOL@@@Z; VIDMM_GLOBAL::GetSegmentGroupState(ulong,_D3DKMT_MEMORY_SEGMENT_GROUP,VIDMM_RESOURCE_POOL *)
0x140117011  jmp     short loc_14011701F
0x140117013  mov     r9, [r13+158h]; struct VIDMM_PARTITION *
0x14011701a  call    ?GetSegmentGroupState@VIDMM_GLOBAL@@QEBAPEBUVIDMM_SEGMENT_GROUP_STATE@@KW4_D3DKMT_MEMORY_SEGMENT_GROUP@@PEAUVIDMM_PARTITION@@@Z; VIDMM_GLOBAL::GetSegmentGroupState(ulong,_D3DKMT_MEMORY_SEGMENT_GROUP,VIDMM_PARTITION *)
0x14011701f  mov     rcx, [rax+20h]
0x140117023  mov     [r15+r14*8+18h], rcx
0x140117028  add     r14d, edi
0x14011702b  cmp     r14d, 2
0x14011702f  jl      short loc_140116FF4
0x140117031  mov     rcx, [rsi+18h]
0x140117035  lea     r8, aPidULuid0x08x0; "pid_%u_luid_0x%08X_0x%08X_phys_%u"
0x14011703c  mov     r9d, [r13+18h]
0x140117040  xorps   xmm0, xmm0
0x140117043  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x140117048  mov     dword ptr [rsp+0B8h+var_88], ebp
0x14011704c  mov     edx, 208h; cbDest
0x140117051  mov     eax, [rcx+19Ch]
0x140117057  mov     dword ptr [rsp+0B8h+var_90], eax
0x14011705b  mov     eax, [rcx+1A0h]
0x140117061  mov     rcx, r12; pszDest
0x140117064  mov     dword ptr [rsp+0B8h+Data], eax
0x140117068  call    RtlStringCbPrintfW
0x14011706d  mov     r14d, eax
0x140117070  test    eax, eax
0x140117072  js      loc_14011712D
0x140117078  mov     rdx, r12; SourceString
0x14011707b  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x140117080  call    cs:__imp_RtlInitUnicodeString
0x140117087  nop     dword ptr [rax+rax+00h]
0x14011708c  mov     rdx, cs:GpuPerformanceCounterSetProcessMemory; Registration
0x140117093  lea     rax, [rsp+0B8h+var_60]
0x140117098  lea     rcx, [r15+0F8h]; Instance
0x14011709f  mov     [rsp+0B8h+Data], rax; Data
0x1401170a4  mov     r9d, edi; Count
0x1401170a7  mov     [rsp+0B8h+var_60.Data], r15
0x1401170ac  lea     r8, [rsp+0B8h+DestinationString]; Name
0x1401170b1  mov     [rsp+0B8h+var_60.Size], 128h
0x1401170b9  call    cs:__imp_PcwCreateInstance
0x1401170c0  nop     dword ptr [rax+rax+00h]
0x1401170c5  mov     r14d, eax
0x1401170c8  test    eax, eax
0x1401170ca  js      short loc_1401170E7
0x1401170cc  mov     r15, [rsp+0B8h+arg_10]
0x1401170d4  add     ebp, edi
0x1401170d6  cmp     ebp, [rsi+0C28h]
0x1401170dc  jb      loc_140116FD9
0x1401170e2  jmp     loc_14011716D
0x1401170e7  lock add cs:dword_14008785C, edi
0x1401170ee  mov     ecx, 6
0x1401170f3  call    cs:__imp_WdLogSingleEntry0
0x1401170fa  nop     dword ptr [rax+rax+00h]
0x1401170ff  mov     [rsp+0B8h+var_80], 0
0x140117108  lea     r9, aFailedToCreate_18; "Failed to create GpuPerformanceCounterS"...
0x14011710f  mov     [rsp+0B8h+var_88], 0
0x140117118  mov     eax, 3E5h
0x14011711d  mov     [rsp+0B8h+var_90], 0
0x140117126  mov     edx, 40001h
0x14011712b  jmp     short loc_14011715D
0x14011712d  mov     ecx, edi
0x14011712f  call    cs:__imp_WdLogSingleEntry0
0x140117136  nop     dword ptr [rax+rax+00h]
0x14011713b  xor     ecx, ecx
0x14011713d  lea     r9, aFailedToCreate_26; "Failed to create name string for GpuPer"...
0x140117144  mov     [rsp+0B8h+var_80], rcx
0x140117149  mov     eax, 3DDh
0x14011714e  mov     [rsp+0B8h+var_88], rcx
0x140117153  mov     edx, 40000h
0x140117158  mov     [rsp+0B8h+var_90], rcx
0x14011715d  mov     [rsp+0B8h+Data], rax
0x140117162  mov     cs:WdLogGlobalForLineNumber, eax
0x140117168  call    DxgkLogInternalTriageEvent
  ... truncated ...
```
