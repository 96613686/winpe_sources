# GestureServices::GetDCompStatisticsAndLogTelemetry(tagPOINT,unsigned __int64,GestureHandler *)

- ea: `0x18016058c`
- end: `0x180160b03`
- name: `?GetDCompStatisticsAndLogTelemetry@GestureServices@@AEAAXUtagPOINT@@_KPEAVGestureHandler@@@Z`
- size: `1399`
- prototype: `void(GestureServices *__hidden this, struct tagPOINT, unsigned __int64, struct GestureHandler *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007dc94`

## callees

- `0x1800065f8`
- `0x180006754`
- `0x180080190`
- `0x180083d00`
- `0x1800899c8`
- `0x18008ee44`
- `0x1800ac1f0`
- `0x1800af59c`
- `0x1800f08d8`
- `0x1800f0990`
- `0x18015fa58`
- `0x18015fe08`
- `0x180160460`
- `0x18016058c`

## import_xrefs

- `dcomp!__imp_DCompositionGetFrameId` at `0x1801607da`
- `dcomp!__imp_DCompositionGetFrameId` at `0x1801607da`
- `win32u!NtDCompositionGetStatistics` at `0x18016062a`
- `win32u!NtDCompositionGetStatistics` at `0x18016073f`
- `win32u!NtDCompositionGetStatistics` at `0x18016062a`
- `win32u!NtDCompositionGetStatistics` at `0x18016073f`
- `win32u!NtDCompositionGetTargetStatistics` at `0x180160803`
- `win32u!NtDCompositionGetTargetStatistics` at `0x180160878`
- `win32u!NtDCompositionGetTargetStatistics` at `0x180160803`
- `win32u!NtDCompositionGetTargetStatistics` at `0x180160878`

## string_xrefs

- `0x18016063e`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gestureservices.cpp`
- `0x18016084f`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gestureservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GestureServices::GetDCompStatisticsAndLogTelemetry(
        GestureServices *this,
        struct tagPOINT a2,
        unsigned __int64 a3,
        GestureServices **a4)
{
  int Statistics; // eax
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // r12
  unsigned __int64 v9; // r13
  __int64 v10; // rax
  unsigned __int8 v11; // si
  unsigned int v12; // ebx
  GestureServices *i; // rax
  int TargetStatistics; // eax
  unsigned __int64 v15; // r8
  int v16; // ecx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r9
  struct GestureHandler *v19; // r14
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int64 v23; // r8
  int v24; // r9d
  int v25; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  GestureServices *v27; // [rsp+80h] [rbp-80h] BYREF
  GestureServices **v28; // [rsp+88h] [rbp-78h] BYREF
  GestureServices *v29; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+98h] [rbp-68h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v32; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v33; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v34; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v35; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v36; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v37; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v39; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v41[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v42; // [rsp+118h] [rbp+18h]
  char v43[8]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v44; // [rsp+128h] [rbp+28h]
  unsigned int v45; // [rsp+138h] [rbp+38h]
  unsigned __int64 v46; // [rsp+148h] [rbp+48h]
  unsigned int v47; // [rsp+150h] [rbp+50h]
  unsigned __int64 v48; // [rsp+160h] [rbp+60h]
  _BYTE v49[112]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v28 = a4;
  v27 = this;
  v29 = a4[13];
  BYTE12(v40) = 0;
  v25 = 0;
  if ( !a3 )
  {
    LODWORD(v26) = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgs(this, 0x20000, 609);
  }
  v30 = 0;
  v31 = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  Statistics = NtDCompositionGetStatistics(&v29, v41, 4, v49);
  if ( Statistics >= 0 )
  {
    v7 = 0;
    v8 = 0;
    v9 = v41[0];
    if ( v41[0] <= a3 )
    {
      LODWORD(v26) = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgs(retaddr, 0x20000, 631);
    }
    v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GestureServices::FindDCompTargetIdForPoint)(
            v27,
            v43,
            a2,
            (unsigned int)v25);
    v39 = *(_OWORD *)(v10 + 8);
    v40 = *(_OWORD *)(v10 + 24);
    v38 = *(_QWORD *)v10;
    if ( (_QWORD)v30 )
      std::_Deallocate<16>(v30, 4 * ((v31 - (__int64)v30) >> 2));
    v11 = 1;
    if ( BYTE12(v40) )
    {
      memset_0(v43, 0, 0x48u);
      v26 = 0;
      if ( (int)DCompositionGetFrameId(2, &v26) < 0 )
      {
        if ( !BYTE12(v40) )
          std::_Throw_bad_optional_access();
        if ( (int)NtDCompositionGetTargetStatistics(&v29, &v39, v43) >= 0 )
        {
          v7 = v46;
          v8 = v48;
        }
      }
      else
      {
        v12 = 0;
        for ( i = v29; ; i = (GestureServices *)((char *)v27 + 1) )
        {
          v27 = i;
          if ( (unsigned __int64)i >= v26 )
            break;
          if ( !BYTE12(v40) )
            std::_Throw_bad_optional_access();
          TargetStatistics = NtDCompositionGetTargetStatistics(&v27, &v39, v43);
          if ( TargetStatistics < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2A8,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\s"
                            "ystem\\gestureservices.cpp",
              (const char *)(unsigned int)TargetStatistics,
              (int)v49);
            break;
          }
          if ( !v12 && v44 )
          {
            v7 = v46;
            v12 = v45;
          }
          if ( v48 && v47 >= v12 )
          {
            v8 = v48;
            break;
          }
        }
      }
    }
    if ( v7 <= a3 || v8 <= a3 )
      v11 = 0;
    if ( v9 > a3 )
    {
      v15 = InputETW::CalculateElapsedMicroseconds(a3, v9);
      if ( (unsigned int)dword_180241248 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180241248, 0x400000000000LL, v15, 0x624DD2F1A9FBE77LL) )
      {
        LODWORD(v26) = v11;
        LODWORD(v27) = v25;
        v32 = (unsigned __int64)(((v17 * (unsigned __int128)v18) >> 64)
                               + ((unsigned __int64)(v17 - ((v17 * (unsigned __int128)v18) >> 64)) >> 1)) >> 9;
        v33 = v9;
        v34 = a3;
        v19 = (struct GestureHandler *)v28;
        v28 = (GestureServices **)v28[32];
        v35 = *((unsigned int *)v19 + 34);
        v36 = *((_QWORD *)v19 + 3);
        v37 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&unk_180212C78,
          v32,
          v18,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v28,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v27,
          (__int64)&v26);
      }
      else
      {
        v19 = (struct GestureHandler *)v28;
      }
      if ( v11 )
      {
        v20 = InputETW::CalculateElapsedMicroseconds(a3, v7);
        v21 = InputETW::CalculateElapsedMicroseconds(a3, v8);
        if ( (unsigned int)dword_180241248 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_180241248, 0x400000000000LL, v21, v22) )
          {
            v37 = v23 / 0x3E8;
            v36 = v20 / 0x3E8;
            v35 = v8;
            v34 = v7;
            v33 = a3;
            v32 = *((_QWORD *)v19 + 32);
            v28 = (GestureServices **)*((unsigned int *)v19 + 34);
            v27 = (GestureServices *)*((_QWORD *)v19 + 3);
            v26 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              446676599,
              (unsigned int)&dword_180212D1C,
              v23 / 0x3E8,
              v24,
              (__int64)&v26,
              (__int64)&v27,
              (__int64)&v28,
              (__int64)&v32,
              (__int64)&v33,
              (__int64)&v34,
              (__int64)&v35,
              (__int64)&v36,
              (__int64)&v37,
              (__int64)&v38);
          }
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x274,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\g"
                    "estureservices.cpp",
      (const char *)(unsigned int)Statistics,
      (int)&v25);
    if ( (_QWORD)v30 )
      std::_Deallocate<16>(v30, 4 * ((v31 - (__int64)v30) >> 2));
  }
}

```

## disassembly

```asm
0x18016058c  mov     [rsp-8+arg_10], rbx
0x180160591  push    rbp
0x180160592  push    rsi
0x180160593  push    rdi
0x180160594  push    r12
0x180160596  push    r13
0x180160598  push    r14
0x18016059a  push    r15
0x18016059c  lea     rbp, [rsp-0F0h]
0x1801605a4  sub     rsp, 1F0h
0x1801605ab  mov     rax, cs:__security_cookie
0x1801605b2  xor     rax, rsp
0x1801605b5  mov     [rbp+120h+var_40], rax
0x1801605bc  mov     [rbp+120h+var_198], r9
0x1801605c0  mov     rdi, r8
0x1801605c3  mov     rbx, rdx
0x1801605c6  mov     [rbp+120h+var_1A0], rcx
0x1801605ca  mov     rax, [r9+68h]
0x1801605ce  mov     [rbp+120h+var_190], rax
0x1801605d2  xor     esi, esi
0x1801605d4  mov     [rbp+120h+var_11C], sil
0x1801605d8  mov     [rsp+220h+var_1B0], esi
0x1801605dc  test    r8, r8
0x1801605df  jnz     short loc_1801605F8
0x1801605e1  mov     dword ptr [rsp+220h+var_1A8], 20000h
0x1801605e9  mov     r8d, 261h
0x1801605ef  mov     edx, dword ptr [rsp+220h+var_1A8]
0x1801605f3  call    MicrosoftTelemetryAssertTriggeredArgs
0x1801605f8  xorps   xmm0, xmm0
0x1801605fb  movdqu  [rbp+120h+var_188], xmm0
0x180160600  mov     [rbp+120h+var_178], rsi
0x180160604  xor     eax, eax
0x180160606  movups  xmmword ptr [rbp+120h+var_118], xmm0
0x18016060a  mov     [rbp+120h+var_108], rax
0x18016060e  lea     rax, [rsp+220h+var_1B0]
0x180160613  mov     qword ptr [rsp+220h+var_200], rax; int
0x180160618  lea     r9, [rbp+120h+var_B0]
0x18016061c  mov     r8d, 4
0x180160622  lea     rdx, [rbp+120h+var_118]
0x180160626  lea     rcx, [rbp+120h+var_190]
0x18016062a  call    cs:__imp_NtDCompositionGetStatistics
0x180160630  mov     rcx, [rbp+128h]; this
0x180160637  test    eax, eax
0x180160639  jns     short loc_180160684
0x18016063b  mov     r9d, eax; char *
0x18016063e  lea     r8, aOnecoreuapWind_212; "onecoreuap\\windows\\moderncore\\inputv"...
0x180160645  mov     edx, 274h; void *
0x18016064a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18016064f  nop
0x180160650  mov     rcx, qword ptr [rbp+120h+var_188]
0x180160654  test    rcx, rcx
0x180160657  jz      loc_180160ACD
0x18016065d  mov     rax, [rbp+120h+var_178]
0x180160661  sub     rax, rcx
0x180160664  sar     rax, 2
0x180160668  mov     rsi, 6DB6DB6DB6DB6DB7h
0x180160672  imul    rax, rsi
0x180160676  imul    rdx, rax, 1Ch
0x18016067a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18016067f  jmp     loc_180160ACD
0x180160684  mov     r15, rsi
0x180160687  mov     r12, rsi
0x18016068a  lea     r14, [rbp+120h+var_B0]
0x18016068e  mov     r13, [rbp+120h+var_118]
0x180160692  cmp     r13, rdi
0x180160695  ja      short loc_1801606AE
0x180160697  mov     dword ptr [rsp+220h+var_1A8], 20000h
0x18016069f  mov     r8d, 277h
0x1801606a5  mov     edx, dword ptr [rsp+220h+var_1A8]
0x1801606a9  call    MicrosoftTelemetryAssertTriggeredArgs
0x1801606ae  mov     rsi, 6DB6DB6DB6DB6DB7h
0x1801606b8  mov     ecx, [rsp+220h+var_1B0]
0x1801606bc  cmp     ecx, 4
0x1801606bf  jbe     loc_18016075C
0x1801606c5  mov     r8d, ecx
0x1801606c8  mov     r9, qword ptr [rbp+120h+var_188]
0x1801606cc  mov     rdx, qword ptr [rbp+120h+var_188+8]
0x1801606d0  sub     rdx, r9
0x1801606d3  sar     rdx, 2
0x1801606d7  imul    rdx, rsi
0x1801606db  cmp     rcx, rdx
0x1801606de  jnb     short loc_1801606E9
0x1801606e0  imul    rax, r8, 1Ch
0x1801606e4  add     rax, r9
0x1801606e7  jmp     short loc_180160724
0x1801606e9  jbe     short loc_180160728
0x1801606eb  mov     rax, [rbp+120h+var_178]
0x1801606ef  sub     rax, r9
0x1801606f2  sar     rax, 2
0x1801606f6  imul    rax, rsi
0x1801606fa  cmp     r8, rax
0x1801606fd  jbe     short loc_180160711
0x1801606ff  mov     rdx, r8
0x180160702  lea     rcx, [rbp+120h+var_188]
0x180160706  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UtagCOMPOSITION_TARGET_ID@@V?$allocator@UtagCOMPOSITION_TARGET_ID@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tagCOMPOSITION_TARGET_ID>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18016070b  mov     ecx, [rsp+220h+var_1B0]
0x18016070f  jmp     short loc_180160728
0x180160711  sub     r8, rdx
0x180160714  mov     rdx, r8
0x180160717  mov     rcx, qword ptr [rbp+120h+var_188+8]
0x18016071b  call    ??$_Uninitialized_value_construct_n@V?$allocator@UtagCOMPOSITION_TARGET_ID@@@std@@@std@@YAPEAUtagCOMPOSITION_TARGET_ID@@PEAU1@_KAEAV?$allocator@UtagCOMPOSITION_TARGET_ID@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<tagCOMPOSITION_TARGET_ID>>(tagCOMPOSITION_TARGET_ID *,unsigned __int64,std::allocator<tagCOMPOSITION_TARGET_ID> &)
0x180160720  mov     ecx, [rsp+220h+var_1B0]
0x180160724  mov     qword ptr [rbp+120h+var_188+8], rax
0x180160728  mov     r14, qword ptr [rbp+120h+var_188]
0x18016072c  mov     qword ptr [rsp+220h+var_200], r12
0x180160731  mov     r9, r14
0x180160734  mov     r8d, ecx
0x180160737  lea     rdx, [rbp+120h+var_118]
0x18016073b  lea     rcx, [rbp+120h+var_190]
0x18016073f  call    cs:__imp_NtDCompositionGetStatistics
0x180160745  test    eax, eax
0x180160747  jns     short loc_180160758
0x180160749  lea     r14, [rbp+120h+var_B0]
0x18016074d  mov     ecx, 4
0x180160752  mov     [rsp+220h+var_1B0], ecx
0x180160756  jmp     short loc_18016075C
0x180160758  mov     ecx, [rsp+220h+var_1B0]
0x18016075c  mov     qword ptr [rsp+220h+var_200], r14
0x180160761  mov     r9d, ecx
0x180160764  mov     r8, rbx
0x180160767  lea     rdx, [rbp+120h+var_100]
0x18016076b  mov     rcx, [rbp+120h+var_1A0]
0x18016076f  call    ?FindDCompTargetIdForPoint@GestureServices@@AEAA?AV?$tuple@V?$optional@UtagCOMPOSITION_TARGET_ID@@@std@@PEBG@std@@UtagPOINT@@IPEAUtagCOMPOSITION_TARGET_ID@@@Z; GestureServices::FindDCompTargetIdForPoint(tagPOINT,uint,tagCOMPOSITION_TARGET_ID *)
0x180160774  movups  xmm0, xmmword ptr [rax+8]
0x180160778  movups  [rbp+120h+var_138], xmm0
0x18016077c  movups  xmm1, xmmword ptr [rax+18h]
0x180160780  movups  xmmword ptr [rbp-8], xmm1
0x180160784  mov     rax, [rax]
0x180160787  mov     [rbp+120h+var_140], rax
0x18016078b  mov     rcx, qword ptr [rbp+120h+var_188]
0x18016078f  xor     r14d, r14d
0x180160792  test    rcx, rcx
0x180160795  jz      short loc_1801607AF
0x180160797  mov     rax, [rbp+120h+var_178]
0x18016079b  sub     rax, rcx
0x18016079e  sar     rax, 2
0x1801607a2  imul    rax, rsi
0x1801607a6  imul    rdx, rax, 1Ch
0x1801607aa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801607af  mov     esi, 1
0x1801607b4  cmp     [rbp+120h+var_11C], r14b
0x1801607b8  jz      loc_18016088A
0x1801607be  xor     edx, edx; Val
0x1801607c0  lea     r8d, [rsi+47h]; Size
0x1801607c4  lea     rcx, [rbp+120h+var_100]; void *
0x1801607c8  call    memset_0
0x1801607cd  mov     [rsp+220h+var_1A8], r14
0x1801607d2  lea     rdx, [rsp+220h+var_1A8]
0x1801607d7  lea     ecx, [rsi+1]
0x1801607da  call    cs:__imp_DCompositionGetFrameId
0x1801607e0  test    eax, eax
0x1801607e2  js      short loc_180160862
0x1801607e4  mov     ebx, r14d
0x1801607e7  mov     rax, [rbp+120h+var_190]
0x1801607eb  jmp     short loc_180160833
0x1801607ed  cmp     [rbp+120h+var_11C], r14b
0x1801607f1  jz      loc_180160AFD
0x1801607f7  lea     r8, [rbp+120h+var_100]
0x1801607fb  lea     rdx, [rbp+120h+var_138]
0x1801607ff  lea     rcx, [rbp+120h+var_1A0]
0x180160803  call    cs:__imp_NtDCompositionGetTargetStatistics
0x180160809  test    eax, eax
0x18016080b  js      short loc_180160845
0x18016080d  test    ebx, ebx
0x18016080f  jnz     short loc_18016081E
0x180160811  cmp     [rbp+120h+var_F8], r14
0x180160815  jz      short loc_18016081E
0x180160817  mov     r15, [rbp+120h+var_D8]
0x18016081b  mov     ebx, [rbp+120h+var_E8]
0x18016081e  mov     rax, [rbp+120h+var_C0]
0x180160822  test    rax, rax
0x180160825  jz      short loc_18016082C
0x180160827  cmp     [rbp+120h+var_D0], ebx
0x18016082a  jnb     short loc_180160840
0x18016082c  mov     rax, [rbp+120h+var_1A0]
0x180160830  add     rax, rsi
0x180160833  cmp     rax, [rsp+220h+var_1A8]
0x180160838  mov     [rbp+120h+var_1A0], rax
0x18016083c  jb      short loc_1801607ED
0x18016083e  jmp     short loc_18016088A
0x180160840  mov     r12, rax
0x180160843  jmp     short loc_18016088A
0x180160845  mov     rcx, [rbp+128h]; this
0x18016084c  mov     r9d, eax; char *
0x18016084f  lea     r8, aOnecoreuapWind_212; "onecoreuap\\windows\\moderncore\\inputv"...
0x180160856  mov     edx, 2A8h; void *
0x18016085b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180160860  jmp     short loc_18016088A
0x180160862  cmp     [rbp+120h+var_11C], r14b
0x180160866  jz      loc_180160AF7
0x18016086c  lea     r8, [rbp+120h+var_100]
0x180160870  lea     rdx, [rbp+120h+var_138]
0x180160874  lea     rcx, [rbp+120h+var_190]
0x180160878  call    cs:__imp_NtDCompositionGetTargetStatistics
0x18016087e  test    eax, eax
0x180160880  js      short loc_18016088A
0x180160882  mov     r15, [rbp+120h+var_D8]
0x180160886  mov     r12, [rbp+120h+var_C0]
0x18016088a  cmp     r15, rdi
0x18016088d  jbe     short loc_180160894
0x18016088f  cmp     r12, rdi
0x180160892  ja      short loc_180160897
0x180160894  mov     sil, r14b
0x180160897  cmp     r13, rdi
0x18016089a  jbe     loc_180160ACD
0x1801608a0  mov     rdx, r13; unsigned __int64
0x1801608a3  mov     rcx, rdi; unsigned __int64
0x1801608a6  call    ?CalculateElapsedMicroseconds@InputETW@@SA_K_K0@Z; InputETW::CalculateElapsedMicroseconds(unsigned __int64,unsigned __int64)
0x1801608ab  mov     r8, rax
0x1801608ae  mov     ecx, cs:dword_180241248
0x1801608b4  mov     r9, 624DD2F1A9FBE77h
0x1801608be  cmp     ecx, 5
0x1801608c1  jbe     loc_18016099D
0x1801608c7  mov     rdx, 400000000000h
0x1801608d1  lea     rcx, dword_180241248
0x1801608d8  call    _tlgKeywordOn
0x1801608dd  test    al, al
0x1801608df  jz      loc_18016099D
0x1801608e5  movzx   eax, sil
0x1801608e9  mov     dword ptr [rsp+220h+var_1A8], eax
0x1801608ed  mov     eax, [rsp+220h+var_1B0]
0x1801608f1  mov     dword ptr [rbp+120h+var_1A0], eax
0x1801608f4  mov     rax, r9
0x1801608f7  mul     r8
0x1801608fa  sub     r8, rdx
0x1801608fd  shr     r8, 1
0x180160900  add     r8, rdx
0x180160903  shr     r8, 9
0x180160907  mov     [rbp+120h+var_170], r8
0x18016090b  mov     [rbp+120h+var_168], r13
0x18016090f  mov     [rbp+120h+var_160], rdi
0x180160913  mov     r14, [rbp+120h+var_198]
0x180160917  mov     rax, [r14+100h]
0x18016091e  mov     [rbp+120h+var_198], rax
0x180160922  mov     eax, [r14+88h]
0x180160929  mov     [rbp+120h+var_158], rax
0x18016092d  mov     rax, [r14+18h]
0x180160931  mov     [rbp+120h+var_150], rax
0x180160935  mov     [rbp+120h+var_148], 1000000h
0x18016093d  lea     rax, [rsp+220h+var_1A8]
0x180160942  mov     [rsp+220h+var_1C0], rax
0x180160947  lea     rax, [rbp+120h+var_1A0]
0x18016094b  mov     [rsp+220h+var_1C8], rax
0x180160950  lea     rax, [rbp+120h+var_170]
0x180160954  mov     [rsp+220h+var_1D0], rax
0x180160959  lea     rax, [rbp+120h+var_168]
0x18016095d  mov     [rsp+220h+var_1D8], rax
0x180160962  lea     rax, [rbp+120h+var_160]
0x180160966  mov     [rsp+220h+var_1E0], rax
0x18016096b  lea     rax, [rbp+120h+var_198]
0x18016096f  mov     [rsp+220h+var_1E8], rax
0x180160974  lea     rax, [rbp+120h+var_158]
0x180160978  mov     [rsp+220h+var_1F0], rax
0x18016097d  lea     rax, [rbp+120h+var_150]
0x180160981  mov     [rsp+220h+var_1F8], rax
0x180160986  lea     rax, [rbp+120h+var_148]
0x18016098a  mov     qword ptr [rsp+220h+var_200], rax
0x18016098f  lea     rdx, unk_180212C78
0x180160996  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@33333AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016099b  jmp     short loc_1801609A1
0x18016099d  mov     r14, [rbp+120h+var_198]
0x1801609a1  test    sil, sil
0x1801609a4  jz      loc_180160ACD
0x1801609aa  mov     rdx, r15; unsigned __int64
0x1801609ad  mov     rcx, rdi; unsigned __int64
0x1801609b0  call    ?CalculateElapsedMicroseconds@InputETW@@SA_K_K0@Z; InputETW::CalculateElapsedMicroseconds(unsigned __int64,unsigned __int64)
0x1801609b5  mov     rbx, rax
0x1801609b8  mov     rdx, r12; unsigned __int64
0x1801609bb  mov     rcx, rdi; unsigned __int64
0x1801609be  call    ?CalculateElapsedMicroseconds@InputETW@@SA_K_K0@Z; InputETW::CalculateElapsedMicroseconds(unsigned __int64,unsigned __int64)
0x1801609c3  mov     r8, rax
0x1801609c6  mov     edx, cs:dword_180241248
0x1801609cc  cmp     edx, 5
0x1801609cf  jbe     loc_180160ACD
0x1801609d5  mov     rdx, 400000000000h
0x1801609df  lea     rcx, dword_180241248
0x1801609e6  call    _tlgKeywordOn
0x1801609eb  test    al, al
0x1801609ed  jz      loc_180160ACD
0x1801609f3  mov     rax, [rbp+120h+var_140]
0x1801609f7  mov     [rbp+120h+var_140], rax
0x1801609fb  mov     rcx, 624DD2F1A9FBE77h
0x180160a05  mov     rax, rcx
0x180160a08  mul     r8
0x180160a0b  sub     r8, rdx
0x180160a0e  shr     r8, 1
0x180160a11  add     r8, rdx
0x180160a14  shr     r8, 9
0x180160a18  mov     [rbp+120h+var_148], r8
0x180160a1c  mov     rax, rcx
0x180160a1f  mul     rbx
0x180160a22  sub     rbx, rdx
0x180160a25  shr     rbx, 1
0x180160a28  add     rbx, rdx
0x180160a2b  shr     rbx, 9
0x180160a2f  mov     [rbp+120h+var_150], rbx
0x180160a33  mov     [rbp+120h+var_158], r12
0x180160a37  mov     [rbp+120h+var_160], r15
0x180160a3b  mov     [rbp+120h+var_168], rdi
0x180160a3f  mov     rax, [r14+100h]
  ... truncated ...
```
