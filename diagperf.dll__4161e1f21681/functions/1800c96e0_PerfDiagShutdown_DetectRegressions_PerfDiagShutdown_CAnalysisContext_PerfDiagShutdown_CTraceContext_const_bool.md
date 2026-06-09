# PerfDiagShutdown::DetectRegressions(PerfDiagShutdown::CAnalysisContext &,PerfDiagShutdown::CTraceContext const &,bool)

- ea: `0x1800c96e0`
- end: `0x1800c9a73`
- name: `?DetectRegressions@PerfDiagShutdown@@YAJAEAUCAnalysisContext@1@AEBVCTraceContext@1@_N@Z`
- size: `915`
- prototype: `__int64 __fastcall(PerfDiagShutdown *__hidden this, struct PerfDiagShutdown::CAnalysisContext *, const struct PerfDiagShutdown::CTraceContext *, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1800b67d8`

## callees

- `0x18001890c`
- `0x180019370`
- `0x18001d648`
- `0x180026254`
- `0x180027064`
- `0x1800282a4`
- `0x1800361c0`
- `0x180036520`
- `0x180072ab8`
- `0x1800ae71c`
- `0x1800b5fe0`
- `0x1800b60e0`
- `0x1800c1314`
- `0x1800c150c`
- `0x1800c1840`
- `0x1800c1908`
- `0x1800c9558`
- `0x1800c96e0`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800c97b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800c97cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800c97b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800c97cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PerfDiagShutdown::DetectRegressions(
        PerfDiagShutdown *this,
        struct PerfDiagShutdown::CAnalysisContext *a2,
        const struct PerfDiagShutdown::CTraceContext *a3)
{
  __int64 result; // rax
  LPCWSTR *v6; // r12
  UINT SystemDirectoryW; // ebx
  WCHAR *BufferSetLength; // rax
  char *v9; // rbx
  const unsigned __int16 *v10; // r9
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned int v13; // esi
  __int64 v14; // r9
  char v15; // cl
  char v16; // dl
  char v17; // cl
  char v18; // dl
  _OWORD *v19; // r9
  _OWORD *v20; // rax
  __int64 v21; // rcx
  char v22; // r14
  PerfDiagShared::RegressionAnalysis::CActivityNode *v23; // r15
  char v24; // di
  __int64 v25; // [rsp+30h] [rbp-3C8h] BYREF
  _BYTE v26[152]; // [rsp+38h] [rbp-3C0h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-328h]
  __int128 v28; // [rsp+E0h] [rbp-318h]
  __m128i v29; // [rsp+F0h] [rbp-308h]
  __int64 v30; // [rsp+100h] [rbp-2F8h]
  __int64 v31; // [rsp+108h] [rbp-2F0h]
  _BYTE v32[688]; // [rsp+110h] [rbp-2E8h] BYREF

  v25 = 0;
  XPerfAddIn::IShutdownInfoSource::ShutdownInformation::ShutdownInformation((XPerfAddIn::IShutdownInfoSource::ShutdownInformation *)v26);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v28 = 0;
  v29 = _mm_load_si128((const __m128i *)&_xmm);
  v30 = XPerfCore::TimeStamp::Min;
  v31 = XPerfCore::TimeStamp::Max;
  result = PerfDiagShutdown::Impl::CScenarioBuilder::BuildScenario(
             (PerfDiagShutdown::Impl::CScenarioBuilder *)&v25,
             this,
             a2);
  if ( !(_DWORD)result )
  {
    if ( PerfDiagShared::RegressionAnalysis::CActivityNode::IsInvalid((PerfDiagShutdown *)((char *)this + 568)) )
      return 2147942413LL;
    v6 = (LPCWSTR *)((char *)this + 616);
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    BufferSetLength = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(
                                 (char *)this + 616,
                                 SystemDirectoryW);
    if ( SystemDirectoryW - 1 != GetSystemDirectoryW(BufferSetLength, SystemDirectoryW) )
      return 2147549183LL;
    ATL::CSimpleStringT<unsigned short,0>::SetLength((char *)this + 616, SystemDirectoryW - 1);
    ATL::CSimpleStringT<unsigned short,0>::Append(
      (char *)this + 616,
      L"\\WDI\\ShutdownPerformanceDiagnostics_SystemData.bin");
    v9 = (char *)this + 624;
    result = PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(*v6, this, (char *)this + 624);
    if ( (int)result < 0 )
    {
      if ( (_DWORD)result != -2147024894 )
      {
        if ( (_DWORD)result != -2147024362
          && (_DWORD)result != -2147023504
          && (_DWORD)result != -2058088447
          && (_DWORD)result != -2058088446
          && (_DWORD)result != -805306333 )
        {
          return result;
        }
        PerfDiagOutput::StatusLog::Write(
          (PerfDiagOutput::StatusLog *)PDEvt_Shutdown_ArchiveCorrupt_Info,
          (const struct _EVENT_DESCRIPTOR *)(unsigned int)result,
          0,
          v10);
      }
      v12 = PerfDiagShutdown::CScenarioArchive::CScenarioArchive((PerfDiagShutdown::CScenarioArchive *)v32);
      PerfDiagShutdown::CScenarioArchive::operator=((char *)this + 624, v12);
      PerfDiagShutdown::CScenarioArchive::~CScenarioArchive((PerfDiagShutdown::CScenarioArchive *)v32);
    }
    else
    {
      PerfDiagShutdown::CFlatThresholdingConfig::CreateConfigNode(
        (PerfDiagShutdown *)((char *)this + 632),
        this,
        (PerfDiagShutdown *)((char *)this + 1112));
    }
    v13 = 1;
    if ( ++*((_DWORD *)this + 157) <= *((_DWORD *)this + 24) )
    {
      v22 = 0;
      v24 = 0;
    }
    else
    {
      LOBYTE(v11) = 1;
      PerfDiagShutdown::CScenarioArchive::AnalyzeChange((char *)this + 624, 0, 0, v11);
      LOBYTE(v14) = 1;
      PerfDiagShutdown::CScenarioArchive::AnalyzeChange((char *)this + 624, 1, 0, v14);
      PerfDiagShared::RegressionAnalysis::CActivityNodeHistory::Trim(
        (PerfDiagShutdown *)((char *)this + 1200),
        (PerfDiagShutdown *)((char *)this + 1100));
      v15 = *((_BYTE *)this + 72);
      v16 = *((_BYTE *)this + 76);
      *((_BYTE *)this + 1100) = *((_BYTE *)this + 80);
      *((_BYTE *)this + 1101) = v15;
      *((_BYTE *)this + 1102) = v16;
      v17 = *((_BYTE *)this + 84);
      v18 = *((_BYTE *)this + 88);
      *((_BYTE *)this + 1103) = *((_BYTE *)this + 92);
      *((_BYTE *)this + 1104) = v17;
      *((_BYTE *)this + 1105) = v18;
      v19 = (_OWORD *)((char *)this + 632);
      v20 = (_OWORD *)((char *)this + 100);
      v21 = 3;
      do
      {
        *v19 = *v20;
        v19[1] = v20[1];
        v19[2] = v20[2];
        v19[3] = v20[3];
        v19[4] = v20[4];
        v19[5] = v20[5];
        v19[6] = v20[6];
        v19[7] = v20[7];
        v19 += 8;
        v20 += 8;
        --v21;
      }
      while ( v21 );
      *v19 = *v20;
      v19[1] = v20[1];
      v19[2] = v20[2];
      v19[3] = v20[3];
      v19[4] = v20[4];
      *((_DWORD *)v19 + 20) = *((_DWORD *)v20 + 20);
      PerfDiagShutdown::CFlatThresholdingConfig::CreateConfigNode(
        (PerfDiagShutdown *)((char *)this + 632),
        this,
        (PerfDiagShutdown *)((char *)this + 1112));
      PerfDiagShared::RegressionAnalysis::CActivityNodeHistory::Merge(
        (PerfDiagShutdown *)((char *)this + 1200),
        (PerfDiagShutdown *)((char *)this + 568),
        (PerfDiagShutdown *)((char *)this + 1100),
        *((_DWORD *)this + 302) + 1);
      v22 = PerfDiagShutdown::CScenarioArchive::AnalyzeChange((char *)this + 624, 0, (char *)this + 1312, 0);
      if ( v22 )
        PerfDiagShared::RegressionAnalysis::CActivityNode::Sort((PerfDiagShutdown *)((char *)this + 1312));
      v23 = (PerfDiagShutdown *)((char *)this + 1360);
      v24 = PerfDiagShutdown::CScenarioArchive::AnalyzeChange((char *)this + 624, 1, (char *)this + 1360, 0);
      if ( v24 )
        PerfDiagShared::RegressionAnalysis::CActivityNode::Sort(v23);
    }
    result = PerfDiagShared::Serializer::WriteToFile<PerfDiagShutdown::CScenarioArchive>(*v6, (__int64)v9);
    if ( (int)result >= 0 )
    {
      if ( v22 || v24 )
        return 0;
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c96e0  mov     [rsp+arg_10], rbx
0x1800c96e5  mov     [rsp+arg_18], rsi
0x1800c96ea  push    rdi
0x1800c96eb  push    r12
0x1800c96ed  push    r13
0x1800c96ef  push    r14
0x1800c96f1  push    r15
0x1800c96f3  sub     rsp, 3D0h
0x1800c96fa  mov     rax, cs:__security_cookie
0x1800c9701  xor     rax, rsp
0x1800c9704  mov     [rsp+3F8h+var_38], rax
0x1800c970c  mov     rbx, rdx
0x1800c970f  mov     rdi, rcx
0x1800c9712  mov     [rsp+3F8h+var_3C8], 0
0x1800c971b  lea     rcx, [rsp+3F8h+var_3C0]; this
0x1800c9720  call    ??0ShutdownInformation@IShutdownInfoSource@XPerfAddIn@@QEAA@XZ; XPerfAddIn::IShutdownInfoSource::ShutdownInformation::ShutdownInformation(void)
0x1800c9725  movdqa  xmm0, cs:__xmm@00000000000000380000000000000000
0x1800c972d  movdqa  [rsp+3F8h+var_328], xmm0
0x1800c9736  xorps   xmm0, xmm0
0x1800c9739  movdqa  [rsp+3F8h+var_318], xmm0
0x1800c9742  movdqa  xmm1, cs:__xmm@00000000000000000000000000000038
0x1800c974a  movdqa  [rsp+3F8h+var_308], xmm1
0x1800c9753  mov     rax, cs:?Min@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Min
0x1800c975a  mov     [rsp+3F8h+var_2F8], rax
0x1800c9762  mov     rax, cs:?Max@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Max
0x1800c9769  mov     [rsp+3F8h+var_2F0], rax
0x1800c9771  mov     r8, rbx; struct PerfDiagShutdown::CTraceContext *
0x1800c9774  mov     rdx, rdi; struct PerfDiagShutdown::CAnalysisContext *
0x1800c9777  lea     rcx, [rsp+3F8h+var_3C8]; this
0x1800c977c  call    ?BuildScenario@CScenarioBuilder@Impl@PerfDiagShutdown@@QEAAJAEAUCAnalysisContext@3@AEBVCTraceContext@3@@Z; PerfDiagShutdown::Impl::CScenarioBuilder::BuildScenario(PerfDiagShutdown::CAnalysisContext &,PerfDiagShutdown::CTraceContext const &)
0x1800c9781  test    eax, eax
0x1800c9783  jnz     loc_1800C9A45
0x1800c9789  lea     r13, [rdi+238h]
0x1800c9790  mov     rcx, r13; this
0x1800c9793  call    ?IsInvalid@CActivityNode@RegressionAnalysis@PerfDiagShared@@QEBA_NXZ; PerfDiagShared::RegressionAnalysis::CActivityNode::IsInvalid(void)
0x1800c9798  test    al, al
0x1800c979a  jz      short loc_1800C97A6
0x1800c979c  mov     eax, 8007000Dh
0x1800c97a1  jmp     loc_1800C9A45
0x1800c97a6  lea     r12, [rdi+268h]
0x1800c97ad  xor     edx, edx; uSize
0x1800c97af  xor     ecx, ecx; lpBuffer
0x1800c97b1  call    cs:__imp_GetSystemDirectoryW
0x1800c97b7  mov     ebx, eax
0x1800c97b9  mov     edx, eax
0x1800c97bb  mov     rcx, r12
0x1800c97be  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x1800c97c3  lea     esi, [rbx-1]
0x1800c97c6  mov     edx, ebx; uSize
0x1800c97c8  mov     rcx, rax; lpBuffer
0x1800c97cb  call    cs:__imp_GetSystemDirectoryW
0x1800c97d1  cmp     esi, eax
0x1800c97d3  jnz     loc_1800C9A33
0x1800c97d9  mov     edx, esi
0x1800c97db  mov     rcx, r12
0x1800c97de  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800c97e3  lea     rdx, aWdiShutdownper; "\\WDI\\ShutdownPerformanceDiagnostics_S"...
0x1800c97ea  mov     rcx, r12
0x1800c97ed  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800c97f2  lea     rbx, [rdi+270h]
0x1800c97f9  mov     r8, rbx
0x1800c97fc  mov     rdx, rdi
0x1800c97ff  mov     rcx, [r12]
0x1800c9803  call    ??$ReadFromFile@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagShutdown@@@Z; PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagShutdown::CScenarioArchive &)
0x1800c9808  test    eax, eax
0x1800c980a  js      short loc_1800C9821
0x1800c980c  lea     r8, [rbx+1E8h]; struct PerfDiagShared::RegressionAnalysis::CConfigNode *
0x1800c9813  lea     rcx, [rbx+8]; this
0x1800c9817  mov     rdx, rdi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800c981a  call    ?CreateConfigNode@CFlatThresholdingConfig@PerfDiagShutdown@@QEBAXAEAVCStringInterner@Serializer@PerfDiagShared@@AEAUCConfigNode@RegressionAnalysis@5@@Z; PerfDiagShutdown::CFlatThresholdingConfig::CreateConfigNode(PerfDiagShared::Serializer::CStringInterner &,PerfDiagShared::RegressionAnalysis::CConfigNode &)
0x1800c981f  jmp     short loc_1800C9887
0x1800c9821  cmp     eax, 80070002h
0x1800c9826  jz      short loc_1800C9860
0x1800c9828  cmp     eax, 80070216h
0x1800c982d  jz      short loc_1800C984F
0x1800c982f  cmp     eax, 80070570h
0x1800c9834  jz      short loc_1800C984F
0x1800c9836  cmp     eax, 85541001h
0x1800c983b  jz      short loc_1800C984F
0x1800c983d  cmp     eax, 85541002h
0x1800c9842  jz      short loc_1800C984F
0x1800c9844  cmp     eax, 0D0000023h
0x1800c9849  jnz     loc_1800C9A45
0x1800c984f  xor     r8d, r8d; unsigned int
0x1800c9852  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x1800c9854  lea     rcx, PDEvt_Shutdown_ArchiveCorrupt_Info; this
0x1800c985b  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800c9860  lea     rcx, [rsp+3F8h+var_2E8]; this
0x1800c9868  call    ??0CScenarioArchive@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CScenarioArchive::CScenarioArchive(void)
0x1800c986d  nop
0x1800c986e  mov     rdx, rax
0x1800c9871  mov     rcx, rbx
0x1800c9874  call    ??4CScenarioArchive@PerfDiagShutdown@@QEAAAEAU01@$$QEAU01@@Z; PerfDiagShutdown::CScenarioArchive::operator=(PerfDiagShutdown::CScenarioArchive &&)
0x1800c9879  nop
0x1800c987a  lea     rcx, [rsp+3F8h+var_2E8]; this
0x1800c9882  call    ??1CScenarioArchive@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CScenarioArchive::~CScenarioArchive(void)
0x1800c9887  mov     esi, 1
0x1800c988c  add     [rbx+4], esi
0x1800c988f  mov     eax, [rbx+4]
0x1800c9892  cmp     eax, [rdi+60h]
0x1800c9895  jbe     loc_1800C9A0D
0x1800c989b  mov     r9b, sil
0x1800c989e  xor     r8d, r8d
0x1800c98a1  xor     edx, edx
0x1800c98a3  mov     rcx, rbx
0x1800c98a6  call    ?AnalyzeChange@CScenarioArchive@PerfDiagShutdown@@QEAA_NW4CBaselineType@RegressionAnalysis@PerfDiagShared@@PEAUCActivityNode@45@_N@Z; PerfDiagShutdown::CScenarioArchive::AnalyzeChange(PerfDiagShared::RegressionAnalysis::CBaselineType,PerfDiagShared::RegressionAnalysis::CActivityNode *,bool)
0x1800c98ab  mov     r9b, sil
0x1800c98ae  xor     r8d, r8d
0x1800c98b1  mov     edx, esi
0x1800c98b3  mov     rcx, rbx
0x1800c98b6  call    ?AnalyzeChange@CScenarioArchive@PerfDiagShutdown@@QEAA_NW4CBaselineType@RegressionAnalysis@PerfDiagShared@@PEAUCActivityNode@45@_N@Z; PerfDiagShutdown::CScenarioArchive::AnalyzeChange(PerfDiagShared::RegressionAnalysis::CBaselineType,PerfDiagShared::RegressionAnalysis::CActivityNode *,bool)
0x1800c98bb  lea     r15, [rbx+240h]
0x1800c98c2  lea     r14, [rbx+1DCh]
0x1800c98c9  mov     rdx, r14; struct PerfDiagShared::RegressionAnalysis::CHistoryConfig *
0x1800c98cc  mov     rcx, r15; this
0x1800c98cf  call    ?Trim@CActivityNodeHistory@RegressionAnalysis@PerfDiagShared@@QEAAXAEBUCHistoryConfig@23@@Z; PerfDiagShared::RegressionAnalysis::CActivityNodeHistory::Trim(PerfDiagShared::RegressionAnalysis::CHistoryConfig const &)
0x1800c98d4  mov     cl, [rdi+48h]
0x1800c98d7  mov     dl, [rdi+4Ch]
0x1800c98da  mov     al, [rdi+50h]
0x1800c98dd  mov     [r14], al
0x1800c98e0  mov     [r14+1], cl
0x1800c98e4  mov     [r14+2], dl
0x1800c98e8  mov     cl, [rdi+54h]
0x1800c98eb  mov     dl, [rdi+58h]
0x1800c98ee  mov     al, [rdi+5Ch]
0x1800c98f1  mov     [rbx+1DFh], al
0x1800c98f7  mov     [rbx+1E0h], cl
0x1800c98fd  mov     [rbx+1E1h], dl
0x1800c9903  lea     r9, [rbx+8]
0x1800c9907  lea     rax, [rdi+64h]
0x1800c990b  lea     ecx, [rsi+2]
0x1800c990e  lea     edx, [rsi+7Fh]
0x1800c9911  movups  xmm0, xmmword ptr [rax]
0x1800c9914  movups  xmmword ptr [r9], xmm0
0x1800c9918  movups  xmm1, xmmword ptr [rax+10h]
0x1800c991c  movups  xmmword ptr [r9+10h], xmm1
0x1800c9921  movups  xmm0, xmmword ptr [rax+20h]
0x1800c9925  movups  xmmword ptr [r9+20h], xmm0
0x1800c992a  movups  xmm1, xmmword ptr [rax+30h]
0x1800c992e  movups  xmmword ptr [r9+30h], xmm1
0x1800c9933  movups  xmm0, xmmword ptr [rax+40h]
0x1800c9937  movups  xmmword ptr [r9+40h], xmm0
0x1800c993c  movups  xmm1, xmmword ptr [rax+50h]
0x1800c9940  movups  xmmword ptr [r9+50h], xmm1
0x1800c9945  movups  xmm0, xmmword ptr [rax+60h]
0x1800c9949  movups  xmmword ptr [r9+60h], xmm0
0x1800c994e  movups  xmm1, xmmword ptr [rax+70h]
0x1800c9952  movups  xmmword ptr [r9+70h], xmm1
0x1800c9957  add     r9, rdx
0x1800c995a  add     rax, rdx
0x1800c995d  sub     rcx, rsi
0x1800c9960  jnz     short loc_1800C9911
0x1800c9962  movups  xmm0, xmmword ptr [rax]
0x1800c9965  movups  xmmword ptr [r9], xmm0
0x1800c9969  movups  xmm1, xmmword ptr [rax+10h]
0x1800c996d  movups  xmmword ptr [r9+10h], xmm1
0x1800c9972  movups  xmm0, xmmword ptr [rax+20h]
0x1800c9976  movups  xmmword ptr [r9+20h], xmm0
0x1800c997b  movups  xmm1, xmmword ptr [rax+30h]
0x1800c997f  movups  xmmword ptr [r9+30h], xmm1
0x1800c9984  movups  xmm0, xmmword ptr [rax+40h]
0x1800c9988  movups  xmmword ptr [r9+40h], xmm0
0x1800c998d  mov     eax, [rax+50h]
0x1800c9990  mov     [r9+50h], eax
0x1800c9994  lea     r8, [rbx+1E8h]; struct PerfDiagShared::RegressionAnalysis::CConfigNode *
0x1800c999b  mov     rdx, rdi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800c999e  lea     rcx, [rbx+8]; this
0x1800c99a2  call    ?CreateConfigNode@CFlatThresholdingConfig@PerfDiagShutdown@@QEBAXAEAVCStringInterner@Serializer@PerfDiagShared@@AEAUCConfigNode@RegressionAnalysis@5@@Z; PerfDiagShutdown::CFlatThresholdingConfig::CreateConfigNode(PerfDiagShared::Serializer::CStringInterner &,PerfDiagShared::RegressionAnalysis::CConfigNode &)
0x1800c99a7  mov     r9d, [rbx+248h]
0x1800c99ae  add     r9d, esi; unsigned int
0x1800c99b1  mov     r8, r14; struct PerfDiagShared::RegressionAnalysis::CHistoryConfig *
0x1800c99b4  mov     rdx, r13; struct PerfDiagShared::RegressionAnalysis::CActivityNode *
0x1800c99b7  mov     rcx, r15; this
0x1800c99ba  call    ?Merge@CActivityNodeHistory@RegressionAnalysis@PerfDiagShared@@QEAAXAEBUCActivityNode@23@AEBUCHistoryConfig@23@K@Z; PerfDiagShared::RegressionAnalysis::CActivityNodeHistory::Merge(PerfDiagShared::RegressionAnalysis::CActivityNode const &,PerfDiagShared::RegressionAnalysis::CHistoryConfig const &,ulong)
0x1800c99bf  lea     r15, [rdi+520h]
0x1800c99c6  xor     r9d, r9d
0x1800c99c9  mov     r8, r15
0x1800c99cc  xor     edx, edx
0x1800c99ce  mov     rcx, rbx
0x1800c99d1  call    ?AnalyzeChange@CScenarioArchive@PerfDiagShutdown@@QEAA_NW4CBaselineType@RegressionAnalysis@PerfDiagShared@@PEAUCActivityNode@45@_N@Z; PerfDiagShutdown::CScenarioArchive::AnalyzeChange(PerfDiagShared::RegressionAnalysis::CBaselineType,PerfDiagShared::RegressionAnalysis::CActivityNode *,bool)
0x1800c99d6  mov     r14b, al
0x1800c99d9  test    al, al
0x1800c99db  jz      short loc_1800C99E5
0x1800c99dd  mov     rcx, r15; this
0x1800c99e0  call    ?Sort@CActivityNode@RegressionAnalysis@PerfDiagShared@@QEAAXXZ; PerfDiagShared::RegressionAnalysis::CActivityNode::Sort(void)
0x1800c99e5  lea     r15, [rdi+550h]
0x1800c99ec  xor     r9d, r9d
0x1800c99ef  mov     r8, r15
0x1800c99f2  mov     edx, esi
0x1800c99f4  mov     rcx, rbx
0x1800c99f7  call    ?AnalyzeChange@CScenarioArchive@PerfDiagShutdown@@QEAA_NW4CBaselineType@RegressionAnalysis@PerfDiagShared@@PEAUCActivityNode@45@_N@Z; PerfDiagShutdown::CScenarioArchive::AnalyzeChange(PerfDiagShared::RegressionAnalysis::CBaselineType,PerfDiagShared::RegressionAnalysis::CActivityNode *,bool)
0x1800c99fc  mov     dil, al
0x1800c99ff  test    al, al
0x1800c9a01  jz      short loc_1800C9A13
0x1800c9a03  mov     rcx, r15; this
0x1800c9a06  call    ?Sort@CActivityNode@RegressionAnalysis@PerfDiagShared@@QEAAXXZ; PerfDiagShared::RegressionAnalysis::CActivityNode::Sort(void)
0x1800c9a0b  jmp     short loc_1800C9A13
0x1800c9a0d  xor     r14b, r14b
0x1800c9a10  xor     dil, dil
0x1800c9a13  mov     rdx, rbx
0x1800c9a16  mov     rcx, [r12]; lpFileName
0x1800c9a1a  call    ??$WriteToFile@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEBGAEBUCScenarioArchive@PerfDiagShutdown@@@Z; PerfDiagShared::Serializer::WriteToFile<PerfDiagShutdown::CScenarioArchive>(ushort const *,PerfDiagShutdown::CScenarioArchive const &)
0x1800c9a1f  test    eax, eax
0x1800c9a21  js      short loc_1800C9A45
0x1800c9a23  test    r14b, r14b
0x1800c9a26  jnz     short loc_1800C9A2D
0x1800c9a28  test    dil, dil
0x1800c9a2b  jz      short loc_1800C9A2F
0x1800c9a2d  xor     esi, esi
0x1800c9a2f  mov     eax, esi
0x1800c9a31  jmp     short loc_1800C9A45
0x1800c9a33  mov     eax, 8000FFFFh
0x1800c9a38  jmp     short loc_1800C9A45
0x1800c9a3a  mov     eax, 8007000Eh
0x1800c9a3f  jmp     short loc_1800C9A45
0x1800c9a41  mov     eax, [rsp+3F8h+var_3D8]
0x1800c9a45  mov     rcx, [rsp+3F8h+var_38]
0x1800c9a4d  xor     rcx, rsp; StackCookie
0x1800c9a50  call    __security_check_cookie
0x1800c9a55  lea     r11, [rsp+3F8h+var_28]
0x1800c9a5d  mov     rbx, [r11+40h]
0x1800c9a61  mov     rsi, [r11+48h]
0x1800c9a65  mov     rsp, r11
0x1800c9a68  pop     r15
0x1800c9a6a  pop     r14
0x1800c9a6c  pop     r13
0x1800c9a6e  pop     r12
0x1800c9a70  pop     rdi
0x1800c9a71  retn
```
