# SleepStudyReportData::CpuActiveTimeLocalAnalysis(void)

- ea: `0x180039b1c`
- end: `0x18003a1c3`
- name: `?CpuActiveTimeLocalAnalysis@SleepStudyReportData@@QEBAJXZ`
- size: `1703`
- prototype: `__int64 __fastcall(SleepStudyReportData *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800778f0`

## callees

- `0x180003738`
- `0x180004298`
- `0x18000474c`
- `0x180004a0c`
- `0x180008740`
- `0x180011990`
- `0x18001292c`
- `0x1800146cc`
- `0x180014e08`
- `0x180014e34`
- `0x18001e218`
- `0x180029118`
- `0x1800321ec`
- `0x180035680`
- `0x18003742c`
- `0x180039b1c`
- `0x18003bb60`
- `0x18004682c`
- `0x1800468dc`
- `0x18004ca90`
- `0x18004ce98`
- `0x18004cf68`
- `0x18007fc50`
- `0x1800804cc`
- `0x1800808d0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180039c86`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180039c86`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SleepStudyReportData::CpuActiveTimeLocalAnalysis(SleepStudyReportData *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  char v5; // r12
  __int64 *i; // rdi
  __int64 v7; // r14
  unsigned __int16 *v8; // r15
  unsigned __int64 v9; // rsi
  void (__fastcall *v10)(__int64, unsigned __int64, unsigned __int64); // rbx
  unsigned __int64 TotalDuration; // rax
  unsigned __int64 v12; // rax
  const unsigned __int16 *v13; // rbx
  __int64 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rsi
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rsi
  __int64 v21; // r14
  __int64 v22; // rax
  const unsigned __int16 *v23; // rsi
  const unsigned __int16 *v24; // rax
  unsigned __int8 v25; // bl
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // r14
  const unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  const unsigned __int16 *v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  unsigned __int8 IsPowerSourceAc; // [rsp+70h] [rbp-90h] BYREF
  char v45; // [rsp+71h] [rbp-8Fh] BYREF
  char v46; // [rsp+72h] [rbp-8Eh] BYREF
  char v47; // [rsp+73h] [rbp-8Dh] BYREF
  char v48[4]; // [rsp+74h] [rbp-8Ch] BYREF
  const unsigned __int16 *v49; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *BitpackedStartTime; // [rsp+80h] [rbp-80h] BYREF
  EnergyEstimationSortedRecords *v51[2]; // [rsp+88h] [rbp-78h] BYREF
  EnergyEstimationSortedRecords *v52; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v53; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v54; // [rsp+A8h] [rbp-58h] BYREF
  const unsigned __int16 *v55; // [rsp+B0h] [rbp-50h] BYREF
  __int64 DurationMinutes; // [rsp+B8h] [rbp-48h]
  double ScenarioActiveTimePercent; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int16 *v59; // [rsp+D0h] [rbp-30h] BYREF
  double v60; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v61; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v62; // [rsp+E8h] [rbp-18h] BYREF
  double v63; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-8h] BYREF
  const unsigned __int16 *v65; // [rsp+100h] [rbp+0h] BYREF
  __int128 v66; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v67; // [rsp+118h] [rbp+18h]
  _BYTE v68[8]; // [rsp+120h] [rbp+20h] BYREF
  volatile signed __int32 *v69; // [rsp+128h] [rbp+28h]
  __int64 v70; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v71[32]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v72; // [rsp+158h] [rbp+58h]
  __int64 v73; // [rsp+160h] [rbp+60h]
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v75[4]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v76[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v77[4]; // [rsp+1C0h] [rbp+C0h] BYREF

  `eh vector constructor iterator'(
    v75,
    0x20u,
    3u,
    (void (*)(void *))std::wstring::wstring,
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>);
  v66 = 0;
  v67 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  SrumKey::SrumKey((SrumKey *)v71);
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 3) > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2, v4);
  v5 = 0;
  for ( i = (__int64 *)*((_QWORD *)this + 41); i != *((__int64 **)this + 42); ++i )
  {
    v7 = *i;
    v53 = *(const unsigned __int16 **)(*i + 16);
    v8 = (unsigned __int16 *)(v7 + 632);
    BlockerData::SetSegment(v7 + 632, 1);
    v9 = 10 * SegmentData::GetDurationInUs((SegmentData *)(v7 + 1576));
    v10 = *(void (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(*(_QWORD *)(v7 + 632) + 16LL);
    TotalDuration = ScenarioInstanceData::GetTotalDuration((ScenarioInstanceData *)v7);
    v10(v7 + 632, v9, TotalDuration);
    if ( BlockerData::GetScenarioActiveTimePercent((BlockerData *)(v7 + 632)) >= 90.0 && *(_QWORD *)(v7 + 1232) )
    {
      BitpackedStartTime = (const unsigned __int16 *)SleepStudyReportData::GetBitpackedStartTime(
                                                       *(_QWORD *)(v7 + 32),
                                                       1u);
      v12 = ScenarioInstanceData::GetTotalDuration((ScenarioInstanceData *)v7);
      DurationMinutes = SleepStudyReportData::GetDurationMinutes(v12);
      IsPowerSourceAc = ScenarioInstanceData::IsPowerSourceAc((ScenarioInstanceData *)v7);
      if ( !IsPowerSourceAc
        && GetSystemPowerStatus(&SystemPowerStatus)
        && ((SystemPowerStatus.SystemStatusFlag & 1) != 0 || *(_BYTE *)(v7 + 129)) )
      {
        v5 = 1;
      }
      v13 = **(const unsigned __int16 ***)(v7 + 1224);
      v49 = v13;
      while ( v13 != *(const unsigned __int16 **)(v7 + 1224) )
      {
        std::wstring::operator=(v71, v13 + 16);
        v14 = (__int64 *)std::shared_ptr<SrumKeyData>::shared_ptr<SrumKeyData>(v68, v13 + 32);
        v15 = *v14;
        *v14 = v72;
        v72 = v15;
        v16 = v14[1];
        v14[1] = v73;
        v73 = v16;
        v17 = v69;
        if ( v69 )
        {
          if ( _InterlockedExchangeAdd(v69 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          }
        }
        v70 = *((_QWORD *)v13 + 10);
        if ( v51[1] == v52 )
        {
          std::vector<EnergyEstimationSortedRecords>::_Emplace_reallocate<EnergyEstimationSortedRecords const &>(
            v51,
            v51[1],
            &v70);
        }
        else
        {
          EnergyEstimationSortedRecords::EnergyEstimationSortedRecords(
            v51[1],
            (const struct EnergyEstimationSortedRecords *)&v70);
          v51[1] = (EnergyEstimationSortedRecords *)((char *)v51[1] + 56);
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SrumKey const,EnergyEstimationInfo *>>>,std::_Iterator_base0>::operator++(&v49);
        v13 = v49;
      }
      std::_Sort_unchecked<EnergyEstimationSortedRecords *,unsigned char (*)(EnergyEstimationSortedRecords,EnergyEstimationSortedRecords)>(
        v51[0],
        v51[1],
        0x6DB6DB6DB6DB6DB7LL * ((v51[1] - v51[0]) >> 3),
        &SleepStudyReportData::EnergyEstimationCpuBasedComparator);
      v20 = 0x6DB6DB6DB6DB6DB7LL * ((v51[1] - v51[0]) >> 3);
      v21 = 0;
      do
      {
        if ( (unsigned int)v21 == v20 )
          break;
        v22 = std::vector<EnergyEstimationSortedRecords>::at(v51, (unsigned int)v21);
        std::wstring::operator=(&v75[4 * (unsigned int)v21], v22 + 8);
        *((_QWORD *)&v66 + v21) = *(_QWORD *)(*(_QWORD *)std::vector<EnergyEstimationSortedRecords>::at(
                                                           v51,
                                                           (unsigned int)v21)
                                            + 24LL);
        v21 = (unsigned int)(v21 + 1);
      }
      while ( (unsigned int)v21 < 3 );
      if ( v51[0] != v51[1] )
      {
        std::_Destroy_range<std::allocator<EnergyEstimationSortedRecords>>(v51[0], v51[1], v18, v19);
        v51[1] = v51[0];
      }
      if ( CallbackContext > 5u && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x400000000000LL) )
      {
        v23 = v53;
        v49 = v53;
        v53 = (const unsigned __int16 *)v66;
        v24 = (const unsigned __int16 *)v75;
        if ( v75[3] > 7u )
          v24 = (const unsigned __int16 *)v75[0];
        v54 = v24;
        v45 = v5;
        v25 = IsPowerSourceAc;
        ScenarioActiveTimePercent = BlockerData::GetScenarioActiveTimePercent((BlockerData *)v8);
        v29 = v8 + 4;
        if ( *((_QWORD *)v8 + 4) > 7u )
          v29 = *(const unsigned __int16 **)v29;
        v55 = v29;
        v58 = DurationMinutes;
        v30 = BitpackedStartTime;
        v59 = BitpackedStartTime;
        v46 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v26,
          (__int64)&word_1800B547E,
          v27,
          v28,
          (__int64)&v46,
          (__int64)&v59,
          (__int64)&v58,
          &v55,
          (__int64)&ScenarioActiveTimePercent,
          (__int64)&IsPowerSourceAc,
          (__int64)&v45,
          &v54,
          (__int64)&v53,
          (__int64)&v49);
      }
      else
      {
        v30 = BitpackedStartTime;
        v23 = v53;
        v25 = IsPowerSourceAc;
      }
      if ( CallbackContext > 5u && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x400000000000LL) )
      {
        v55 = v23;
        v54 = (const unsigned __int16 *)*((_QWORD *)&v66 + 1);
        v31 = (const unsigned __int16 *)v76;
        if ( v76[3] > 7u )
          v31 = (const unsigned __int16 *)v76[0];
        v49 = v31;
        v45 = v5;
        IsPowerSourceAc = v25;
        v60 = BlockerData::GetScenarioActiveTimePercent((BlockerData *)v8);
        v35 = v8 + 4;
        if ( *((_QWORD *)v8 + 4) > 7u )
          v35 = *(const unsigned __int16 **)v35;
        BitpackedStartTime = v35;
        v61 = DurationMinutes;
        v62 = v30;
        v47 = 2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v32,
          (__int64)byte_1800B5669,
          v33,
          v34,
          (__int64)&v47,
          (__int64)&v62,
          (__int64)&v61,
          &BitpackedStartTime,
          (__int64)&v60,
          (__int64)&IsPowerSourceAc,
          (__int64)&v45,
          &v49,
          (__int64)&v54,
          (__int64)&v55);
      }
      if ( CallbackContext > 5u && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x400000000000LL) )
      {
        v55 = v23;
        v54 = v67;
        v36 = (const unsigned __int16 *)v77;
        if ( v77[3] > 7u )
          v36 = (const unsigned __int16 *)v77[0];
        v49 = v36;
        v45 = v5;
        IsPowerSourceAc = v25;
        v63 = BlockerData::GetScenarioActiveTimePercent((BlockerData *)v8);
        v40 = v8 + 4;
        if ( *((_QWORD *)v8 + 4) > 7u )
          v40 = *(const unsigned __int16 **)v40;
        BitpackedStartTime = v40;
        v64 = DurationMinutes;
        v65 = v30;
        v48[0] = 3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v37,
          (__int64)byte_1800B5585,
          v38,
          v39,
          (__int64)v48,
          (__int64)&v65,
          (__int64)&v64,
          &BitpackedStartTime,
          (__int64)&v63,
          (__int64)&IsPowerSourceAc,
          (__int64)&v45,
          &v49,
          (__int64)&v54,
          (__int64)&v55);
      }
    }
  }
  SrumKey::~SrumKey((SrumKey *)v71);
  if ( v51[0] )
  {
    std::_Destroy_range<std::allocator<EnergyEstimationSortedRecords>>(v51[0], v51[1], v41, v42);
    std::_Deallocate<16>(v51[0], 8 * ((v52 - v51[0]) >> 3));
    *(_OWORD *)v51 = 0;
    v52 = 0;
  }
  `eh vector destructor iterator'(
    v75,
    0x20u,
    3u,
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>);
  return 0;
}

```

## disassembly

```asm
0x180039b1c  push    rbp
0x180039b1e  push    rbx
0x180039b1f  push    rsi
0x180039b20  push    rdi
0x180039b21  push    r12
0x180039b23  push    r13
0x180039b25  push    r14
0x180039b27  push    r15
0x180039b29  lea     rbp, [rsp-0F8h]
0x180039b31  sub     rsp, 1F8h
0x180039b38  mov     rax, cs:__security_cookie
0x180039b3f  xor     rax, rsp
0x180039b42  mov     [rbp+130h+var_50], rax
0x180039b49  mov     r13, rcx
0x180039b4c  lea     rbx, ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180039b53  mov     [rsp+230h+var_210], rbx; void (*)(void *)
0x180039b58  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180039b5f  mov     edx, 20h ; ' '; unsigned __int64
0x180039b64  lea     r8d, [rdx-1Dh]; unsigned __int64
0x180039b68  lea     rcx, [rbp+130h+var_B0]; void *
0x180039b6f  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180039b74  nop
0x180039b75  xorps   xmm0, xmm0
0x180039b78  xor     eax, eax
0x180039b7a  movups  [rbp+130h+var_128], xmm0
0x180039b7e  mov     [rbp+130h+var_118], rax
0x180039b82  xorps   xmm1, xmm1
0x180039b85  movdqu  xmmword ptr [rbp+130h+var_1A8], xmm1
0x180039b8a  mov     [rbp+130h+var_198], rax
0x180039b8e  lea     rcx, [rbp+130h+var_F8]; this
0x180039b92  call    ??0SrumKey@@QEAA@XZ; SrumKey::SrumKey(void)
0x180039b97  nop
0x180039b98  xor     eax, eax
0x180039b9a  mov     qword ptr [rbp+130h+SystemPowerStatus.ACLineStatus], rax
0x180039b9e  mov     [rbp+130h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180039ba1  mov     rax, [r13+150h]
0x180039ba8  sub     rax, [r13+148h]
0x180039baf  sar     rax, 3
0x180039bb3  cmp     rax, 1
0x180039bb7  jbe     short loc_180039BBE
0x180039bb9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039bbe  xor     r12b, r12b
0x180039bc1  mov     rdi, [r13+148h]
0x180039bc8  cmp     rdi, [r13+150h]
0x180039bcf  jz      loc_18003A130
0x180039bd5  mov     r14, [rdi]
0x180039bd8  mov     rax, [r14+10h]
0x180039bdc  mov     [rbp+130h+var_190], rax
0x180039be0  lea     r15, [r14+278h]
0x180039be7  mov     edx, 1
0x180039bec  mov     rcx, r15
0x180039bef  call    ?SetSegment@BlockerData@@QEAAXW4ScenarioSegment@@@Z; BlockerData::SetSegment(ScenarioSegment)
0x180039bf4  lea     rcx, [r14+628h]; this
0x180039bfb  call    ?GetDurationInUs@SegmentData@@QEBA_KXZ; SegmentData::GetDurationInUs(void)
0x180039c00  lea     rsi, [rax+rax*4]
0x180039c04  add     rsi, rsi
0x180039c07  mov     rax, [r15]
0x180039c0a  mov     rbx, [rax+10h]
0x180039c0e  mov     rcx, r14; this
0x180039c11  call    ?GetTotalDuration@ScenarioInstanceData@@QEBA_KXZ; ScenarioInstanceData::GetTotalDuration(void)
0x180039c16  mov     r8, rax
0x180039c19  mov     rdx, rsi
0x180039c1c  mov     rcx, r15
0x180039c1f  mov     rax, rbx
0x180039c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c27  mov     rcx, r15; this
0x180039c2a  call    ?GetScenarioActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetScenarioActiveTimePercent(void)
0x180039c2f  comisd  xmm0, cs:__real@4056800000000000
0x180039c37  jb      loc_18003A127
0x180039c3d  cmp     qword ptr [r14+4D0h], 0
0x180039c45  jbe     loc_18003A127
0x180039c4b  mov     dl, 1; unsigned __int8
0x180039c4d  mov     rcx, [r14+20h]; unsigned __int64
0x180039c51  call    ?GetBitpackedStartTime@SleepStudyReportData@@SAK_KE@Z; SleepStudyReportData::GetBitpackedStartTime(unsigned __int64,uchar)
0x180039c56  mov     eax, eax
0x180039c58  mov     [rbp+130h+var_1B0], rax
0x180039c5c  mov     rcx, r14; this
0x180039c5f  call    ?GetTotalDuration@ScenarioInstanceData@@QEBA_KXZ; ScenarioInstanceData::GetTotalDuration(void)
0x180039c64  mov     rcx, rax; unsigned __int64
0x180039c67  call    ?GetDurationMinutes@SleepStudyReportData@@SAK_K@Z; SleepStudyReportData::GetDurationMinutes(unsigned __int64)
0x180039c6c  mov     eax, eax
0x180039c6e  mov     [rbp+130h+var_178], rax
0x180039c72  mov     rcx, r14; this
0x180039c75  call    ?IsPowerSourceAc@ScenarioInstanceData@@QEBAEXZ; ScenarioInstanceData::IsPowerSourceAc(void)
0x180039c7a  mov     [rsp+230h+var_1C0], al
0x180039c7e  test    al, al
0x180039c80  jnz     short loc_180039CA3
0x180039c82  lea     rcx, [rbp+130h+SystemPowerStatus]; lpSystemPowerStatus
0x180039c86  call    cs:__imp_GetSystemPowerStatus
0x180039c8c  test    eax, eax
0x180039c8e  jz      short loc_180039CA3
0x180039c90  test    [rbp+130h+SystemPowerStatus.SystemStatusFlag], 1
0x180039c94  jnz     short loc_180039CA0
0x180039c96  cmp     byte ptr [r14+81h], 0
0x180039c9e  jz      short loc_180039CA3
0x180039ca0  mov     r12b, 1
0x180039ca3  mov     rbx, [r14+4C8h]
0x180039caa  mov     rbx, [rbx]
0x180039cad  mov     [rsp+230h+var_1B8], rbx
0x180039cb2  cmp     rbx, [r14+4C8h]
0x180039cb9  jz      loc_180039D80
0x180039cbf  lea     rdx, [rbx+20h]
0x180039cc3  lea     rcx, [rbp+130h+var_F8]
0x180039cc7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180039ccc  lea     rdx, [rbx+40h]
0x180039cd0  lea     rcx, [rbp+130h+var_110]
0x180039cd4  call    ??0?$shared_ptr@USrumKeyData@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SrumKeyData>::shared_ptr<SrumKeyData>(std::shared_ptr<SrumKeyData> const &)
0x180039cd9  mov     rdx, [rax]
0x180039cdc  mov     rcx, [rbp+130h+var_D8]
0x180039ce0  mov     [rax], rcx
0x180039ce3  mov     [rbp+130h+var_D8], rdx
0x180039ce7  mov     rdx, [rax+8]
0x180039ceb  mov     rcx, [rbp+130h+var_D0]
0x180039cef  mov     [rax+8], rcx
0x180039cf3  mov     [rbp+130h+var_D0], rdx
0x180039cf7  mov     rsi, [rbp+130h+var_108]
0x180039cfb  test    rsi, rsi
0x180039cfe  jz      short loc_180039D37
0x180039d00  or      eax, 0FFFFFFFFh
0x180039d03  lock xadd [rsi+8], eax
0x180039d08  cmp     eax, 1
0x180039d0b  jnz     short loc_180039D37
0x180039d0d  mov     rax, [rsi]
0x180039d10  mov     rcx, rsi
0x180039d13  mov     rax, [rax]
0x180039d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d1b  or      eax, 0FFFFFFFFh
0x180039d1e  lock xadd [rsi+0Ch], eax
0x180039d23  cmp     eax, 1
0x180039d26  jnz     short loc_180039D37
0x180039d28  mov     rax, [rsi]
0x180039d2b  mov     rcx, rsi
0x180039d2e  mov     rax, [rax+8]
0x180039d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d37  mov     rax, [rbx+50h]
0x180039d3b  mov     [rbp+130h+var_100], rax
0x180039d3f  mov     rax, [rbp+130h+var_1A8+8]
0x180039d43  cmp     rax, [rbp+130h+var_198]
0x180039d47  jz      short loc_180039D5C
0x180039d49  lea     rdx, [rbp+130h+var_100]; struct EnergyEstimationSortedRecords *
0x180039d4d  mov     rcx, rax; this
0x180039d50  call    ??0EnergyEstimationSortedRecords@@QEAA@AEBU0@@Z; EnergyEstimationSortedRecords::EnergyEstimationSortedRecords(EnergyEstimationSortedRecords const &)
0x180039d55  add     [rbp+130h+var_1A8+8], 38h ; '8'
0x180039d5a  jmp     short loc_180039D6C
0x180039d5c  lea     r8, [rbp+130h+var_100]
0x180039d60  mov     rdx, rax
0x180039d63  lea     rcx, [rbp+130h+var_1A8]
0x180039d67  call    ??$_Emplace_reallocate@AEBUEnergyEstimationSortedRecords@@@?$vector@UEnergyEstimationSortedRecords@@V?$allocator@UEnergyEstimationSortedRecords@@@std@@@std@@AEAAPEAUEnergyEstimationSortedRecords@@QEAU2@AEBU2@@Z; std::vector<EnergyEstimationSortedRecords>::_Emplace_reallocate<EnergyEstimationSortedRecords const &>(EnergyEstimationSortedRecords * const,EnergyEstimationSortedRecords const &)
0x180039d6c  lea     rcx, [rsp+230h+var_1B8]
0x180039d71  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUSrumKey@@PEAUEnergyEstimationInfo@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SrumKey const,EnergyEstimationInfo *>>>,std::_Iterator_base0>::operator++(void)
0x180039d76  mov     rbx, [rsp+230h+var_1B8]
0x180039d7b  jmp     loc_180039CB2
0x180039d80  mov     rdx, [rbp+130h+var_1A8+8]
0x180039d84  mov     rcx, [rbp+130h+var_1A8]
0x180039d88  mov     r8, rdx
0x180039d8b  sub     r8, rcx
0x180039d8e  sar     r8, 3
0x180039d92  mov     rbx, 6DB6DB6DB6DB6DB7h
0x180039d9c  imul    r8, rbx
0x180039da0  lea     r9, ?EnergyEstimationCpuBasedComparator@SleepStudyReportData@@SAEUEnergyEstimationSortedRecords@@0@Z; SleepStudyReportData::EnergyEstimationCpuBasedComparator(EnergyEstimationSortedRecords,EnergyEstimationSortedRecords)
0x180039da7  call    ??$_Sort_unchecked@PEAUEnergyEstimationSortedRecords@@P6AEU1@0@Z@std@@YAXPEAUEnergyEstimationSortedRecords@@0_JP6AEU1@2@Z@Z; std::_Sort_unchecked<EnergyEstimationSortedRecords *,uchar (*)(EnergyEstimationSortedRecords,EnergyEstimationSortedRecords)>(EnergyEstimationSortedRecords *,EnergyEstimationSortedRecords *,__int64,uchar (*)(EnergyEstimationSortedRecords,EnergyEstimationSortedRecords))
0x180039dac  mov     rsi, [rbp+130h+var_1A8+8]
0x180039db0  sub     rsi, [rbp+130h+var_1A8]
0x180039db4  sar     rsi, 3
0x180039db8  imul    rsi, rbx
0x180039dbc  xor     r14d, r14d
0x180039dbf  mov     ebx, r14d
0x180039dc2  cmp     rbx, rsi
0x180039dc5  jz      short loc_180039E0B
0x180039dc7  mov     edx, ebx
0x180039dc9  lea     rcx, [rbp+130h+var_1A8]
0x180039dcd  call    ?at@?$vector@UEnergyEstimationSortedRecords@@V?$allocator@UEnergyEstimationSortedRecords@@@std@@@std@@QEAAAEAUEnergyEstimationSortedRecords@@_K@Z; std::vector<EnergyEstimationSortedRecords>::at(unsigned __int64)
0x180039dd2  lea     rdx, [rax+8]
0x180039dd6  mov     eax, ebx
0x180039dd8  shl     rax, 5
0x180039ddc  lea     rcx, [rbp+130h+var_B0]
0x180039de3  add     rcx, rax
0x180039de6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180039deb  mov     edx, ebx
0x180039ded  lea     rcx, [rbp+130h+var_1A8]
0x180039df1  call    ?at@?$vector@UEnergyEstimationSortedRecords@@V?$allocator@UEnergyEstimationSortedRecords@@@std@@@std@@QEAAAEAUEnergyEstimationSortedRecords@@_K@Z; std::vector<EnergyEstimationSortedRecords>::at(unsigned __int64)
0x180039df6  mov     rcx, [rax]
0x180039df9  mov     rax, [rcx+18h]
0x180039dfd  mov     qword ptr [rbp+r14*8+130h+var_128], rax
0x180039e02  inc     r14d
0x180039e05  cmp     r14d, 3
0x180039e09  jb      short loc_180039DBF
0x180039e0b  mov     rdx, [rbp+130h+var_1A8+8]
0x180039e0f  mov     rcx, [rbp+130h+var_1A8]
0x180039e13  cmp     rcx, rdx
0x180039e16  jz      short loc_180039E25
0x180039e18  call    ??$_Destroy_range@V?$allocator@UEnergyEstimationSortedRecords@@@std@@@std@@YAXPEAUEnergyEstimationSortedRecords@@QEAU1@AEAV?$allocator@UEnergyEstimationSortedRecords@@@0@@Z; std::_Destroy_range<std::allocator<EnergyEstimationSortedRecords>>(EnergyEstimationSortedRecords *,EnergyEstimationSortedRecords * const,std::allocator<EnergyEstimationSortedRecords> &)
0x180039e1d  mov     rax, [rbp+130h+var_1A8]
0x180039e21  mov     [rbp+130h+var_1A8+8], rax
0x180039e25  mov     eax, cs:CallbackContext
0x180039e2b  cmp     eax, 5
0x180039e2e  jbe     loc_180039F2B
0x180039e34  mov     rdx, 400000000000h
0x180039e3e  lea     rcx, CallbackContext
0x180039e45  call    _tlgKeywordOn
0x180039e4a  test    al, al
0x180039e4c  jz      loc_180039F2B
0x180039e52  mov     rsi, [rbp+130h+var_190]
0x180039e56  mov     [rsp+230h+var_1B8], rsi
0x180039e5b  mov     rax, qword ptr [rbp+130h+var_128]
0x180039e5f  mov     [rbp+130h+var_190], rax
0x180039e63  lea     rax, [rbp+130h+var_B0]
0x180039e6a  cmp     [rbp+130h+var_98], 7
0x180039e72  cmova   rax, [rbp+130h+var_B0]
0x180039e7a  mov     [rbp+130h+var_188], rax
0x180039e7e  mov     [rsp+230h+var_1BF], r12b
0x180039e83  mov     bl, [rsp+230h+var_1C0]
0x180039e87  mov     [rsp+230h+var_1C0], bl
0x180039e8b  mov     rcx, r15; this
0x180039e8e  call    ?GetScenarioActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetScenarioActiveTimePercent(void)
0x180039e93  movsd   [rbp+130h+var_170], xmm0
0x180039e98  lea     rax, [r15+8]
0x180039e9c  cmp     qword ptr [r15+20h], 7
0x180039ea1  jbe     short loc_180039EA6
0x180039ea3  mov     rax, [rax]
0x180039ea6  mov     [rbp+130h+var_180], rax
0x180039eaa  mov     rax, [rbp+130h+var_178]
0x180039eae  mov     [rbp+130h+var_168], rax
0x180039eb2  mov     r14, [rbp+130h+var_1B0]
0x180039eb6  mov     [rbp+130h+var_160], r14
0x180039eba  mov     [rsp+230h+var_1BE], 1
0x180039ebf  lea     rax, [rsp+230h+var_1B8]
0x180039ec4  mov     [rsp+230h+var_1C8], rax
0x180039ec9  lea     rax, [rbp+130h+var_190]
0x180039ecd  mov     [rsp+230h+var_1D0], rax
0x180039ed2  lea     rax, [rbp+130h+var_188]
0x180039ed6  mov     [rsp+230h+var_1D8], rax
0x180039edb  lea     rax, [rsp+230h+var_1BF]
0x180039ee0  mov     [rsp+230h+var_1E0], rax
0x180039ee5  lea     rax, [rsp+230h+var_1C0]
0x180039eea  mov     [rsp+230h+var_1E8], rax
0x180039eef  lea     rax, [rbp+130h+var_170]
0x180039ef3  mov     [rsp+230h+var_1F0], rax
0x180039ef8  lea     rax, [rbp+130h+var_180]
0x180039efc  mov     [rsp+230h+var_1F8], rax
0x180039f01  lea     rax, [rbp+130h+var_168]
0x180039f05  mov     [rsp+230h+var_200], rax
0x180039f0a  lea     rax, [rbp+130h+var_160]
0x180039f0e  mov     [rsp+230h+var_208], rax
0x180039f13  lea     rax, [rsp+230h+var_1BE]
0x180039f18  mov     [rsp+230h+var_210], rax
0x180039f1d  lea     rdx, word_1800B547E
0x180039f24  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapSz@G@@U2@U1@U1@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapSz@G@@433544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180039f29  jmp     short loc_180039F37
0x180039f2b  mov     r14, [rbp+130h+var_1B0]
0x180039f2f  mov     rsi, [rbp+130h+var_190]
0x180039f33  mov     bl, [rsp+230h+var_1C0]
0x180039f37  mov     eax, cs:CallbackContext
0x180039f3d  cmp     eax, 5
0x180039f40  jbe     loc_18003A02F
0x180039f46  mov     rdx, 400000000000h
0x180039f50  lea     rcx, CallbackContext
0x180039f57  call    _tlgKeywordOn
0x180039f5c  test    al, al
0x180039f5e  jz      loc_18003A02F
0x180039f64  mov     [rbp+130h+var_180], rsi
0x180039f68  mov     rax, qword ptr [rbp+130h+var_128+8]
0x180039f6c  mov     [rbp+130h+var_188], rax
0x180039f70  lea     rax, [rbp+130h+var_90]
0x180039f77  cmp     [rbp+130h+var_78], 7
0x180039f7f  cmova   rax, [rbp+130h+var_90]
0x180039f87  mov     [rsp+230h+var_1B8], rax
0x180039f8c  mov     [rsp+230h+var_1BF], r12b
0x180039f91  mov     [rsp+230h+var_1C0], bl
0x180039f95  mov     rcx, r15; this
0x180039f98  call    ?GetScenarioActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetScenarioActiveTimePercent(void)
0x180039f9d  movsd   [rbp+130h+var_158], xmm0
0x180039fa2  lea     rax, [r15+8]
0x180039fa6  cmp     qword ptr [r15+20h], 7
0x180039fab  jbe     short loc_180039FB0
0x180039fad  mov     rax, [rax]
0x180039fb0  mov     [rbp+130h+var_1B0], rax
0x180039fb4  mov     rax, [rbp+130h+var_178]
0x180039fb8  mov     [rbp+130h+var_150], rax
0x180039fbc  mov     [rbp+130h+var_148], r14
0x180039fc0  mov     [rsp+230h+var_1BD], 2
0x180039fc5  lea     rax, [rbp+130h+var_180]
0x180039fc9  mov     [rsp+230h+var_1C8], rax
0x180039fce  lea     rax, [rbp+130h+var_188]
0x180039fd2  mov     [rsp+230h+var_1D0], rax
0x180039fd7  lea     rax, [rsp+230h+var_1B8]
0x180039fdc  mov     [rsp+230h+var_1D8], rax
0x180039fe1  lea     rax, [rsp+230h+var_1BF]
0x180039fe6  mov     [rsp+230h+var_1E0], rax
0x180039feb  lea     rax, [rsp+230h+var_1C0]
0x180039ff0  mov     [rsp+230h+var_1E8], rax
0x180039ff5  lea     rax, [rbp+130h+var_158]
0x180039ff9  mov     [rsp+230h+var_1F0], rax
0x180039ffe  lea     rax, [rbp+130h+var_1B0]
0x18003a002  mov     [rsp+230h+var_1F8], rax
0x18003a007  lea     rax, [rbp+130h+var_150]
0x18003a00b  mov     [rsp+230h+var_200], rax
0x18003a010  lea     rax, [rbp+130h+var_148]
0x18003a014  mov     [rsp+230h+var_208], rax
0x18003a019  lea     rax, [rsp+230h+var_1BD]
  ... truncated ...
```
