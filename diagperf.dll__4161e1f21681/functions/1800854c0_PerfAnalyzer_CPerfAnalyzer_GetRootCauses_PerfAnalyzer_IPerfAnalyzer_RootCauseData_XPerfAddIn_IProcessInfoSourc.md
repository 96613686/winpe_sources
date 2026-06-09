# PerfAnalyzer::CPerfAnalyzer::GetRootCauses(PerfAnalyzer::IPerfAnalyzer::RootCauseData * *,XPerfAddIn::IProcessInfoSource::ThreadData const * * const,unsigned __int64,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong)

- ea: `0x1800854c0`
- end: `0x1800859c4`
- name: `?GetRootCauses@CPerfAnalyzer@PerfAnalyzer@@UEBAJPEAPEAURootCauseData@IPerfAnalyzer@2@QEAPEBUThreadData@IProcessInfoSource@XPerfAddIn@@_KAEBVTimeStamp@XPerfCore@@3K@Z`
- size: `1284`
- prototype: `__int64 __usercall@<rax>(PerfAnalyzer::CPerfAnalyzer *__hidden this@<rcx>, struct PerfAnalyzer::IPerfAnalyzer::RootCauseData **@<rdx>, const struct XPerfAddIn::IProcessInfoSource::ThreadData **const@<r8>, unsigned __int64@<r9>, const struct TimeStamp *, const struct TimeStamp *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180056bc8`
- `0x180084ff0`
- `0x18008506c`
- `0x1800854c0`
- `0x1800859cc`
- `0x180085a50`
- `0x1800864b0`
- `0x1800872b4`
- `0x180088e2c`
- `0x18008a0cc`
- `0x18008b280`
- `0x1800cf032`
- `0x1800d6010`

## import_xrefs

- `msvcrt!malloc` at `0x1800858bc`
- `msvcrt!malloc` at `0x1800858bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PerfAnalyzer::CPerfAnalyzer::GetRootCauses(
        struct XPerfAddIn::IDiskIOInfoSource **this,
        struct PerfAnalyzer::IPerfAnalyzer::RootCauseData **a2,
        const struct XPerfAddIn::IProcessInfoSource::ThreadData **const a3,
        unsigned __int64 a4,
        const struct TimeStamp *a5,
        const struct TimeStamp *a6,
        unsigned int a7)
{
  unsigned __int64 i; // rcx
  unsigned __int64 v11; // rdi
  int IsValidTrace; // eax
  int v13; // esi
  __int64 v14; // rdi
  const struct XPerfAddIn::IDpcIsrInfoSource2 *v15; // rdi
  const struct XPerfAddIn::IDiskIOInfoSource *v16; // r14
  PerfAnalyzer::RCAProc *v17; // rax
  const struct TimeStamp *v18; // r9
  unsigned int v19; // r14d
  const struct XPerfAddIn::IDiskIOInfoSource *v20; // rdi
  PerfAnalyzer::RCADisk *v21; // rax
  bool v22; // zf
  struct XPerfAddIn::IHardFaultInfoSource **v23; // r14
  const struct XPerfAddIn::IProcessInfoSource *v24; // r13
  PerfAnalyzer::RCAFrag *v25; // rax
  const struct XPerfAddIn::IProcessInfoSource *v26; // r13
  const struct XPerfAddIn::IPerfCounters *v27; // r15
  const struct XPerfAddIn::IHardFaultInfoSource *v28; // r14
  PerfAnalyzer::RCAMemory *v29; // rax
  unsigned __int64 j; // r14
  size_t v31; // rdx
  size_t v32; // r14
  struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *v33; // rax
  struct PerfAnalyzer::IPerfAnalyzer::RootCauseData **v34; // r15
  unsigned __int64 k; // r14
  unsigned __int64 m; // r14
  void (__fastcall ***v37)(_QWORD, __int64); // rcx
  __int64 v38; // [rsp+50h] [rbp-C8h] BYREF
  struct XPerfAddIn::IProcessInfoSource::ThreadData **v39; // [rsp+58h] [rbp-C0h]
  __int64 v40; // [rsp+60h] [rbp-B8h] BYREF
  size_t v41; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-A8h]
  unsigned __int64 v43; // [rsp+78h] [rbp-A0h]
  struct XPerfAddIn::IDiskIOInfoSource *v44; // [rsp+80h] [rbp-98h]
  struct XPerfAddIn::IHardFaultInfoSource *v45; // [rsp+88h] [rbp-90h]
  PerfAnalyzer::RCAProc *v46; // [rsp+90h] [rbp-88h]
  __int64 v47; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v48[16]; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-68h]
  _QWORD v50[4]; // [rsp+B8h] [rbp-60h] BYREF
  struct PerfAnalyzer::IPerfAnalyzer::RootCauseData **v51; // [rsp+D8h] [rbp-40h]
  __int64 v52[7]; // [rsp+E0h] [rbp-38h] BYREF

  v43 = a4;
  v39 = a3;
  v51 = a2;
  memset(v50, 0, sizeof(v50));
  v38 = 0;
  v40 = 0;
  v47 = 0;
  v41 = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( *(_QWORD *)a5 >= *(_QWORD *)a6 || !a3 || !a4 )
    return 2147942487LL;
  for ( i = 0; i < a4; ++i )
  {
    if ( !*((_DWORD *)a3[i] + 21) )
      return 2147942487LL;
  }
  if ( !PerfAnalyzer::CPerfAnalyzer::InitOptions((PerfAnalyzer::CPerfAnalyzer *)i) )
    return 2147942414LL;
  v11 = 0;
  v42 = 0;
  IsValidTrace = PerfAnalyzer::CPerfAnalyzer::IsValidTrace(
                   (PerfAnalyzer::CPerfAnalyzer *)this,
                   (struct TimeStamp *)&v38,
                   (struct TimeStamp *)&v40,
                   a5,
                   a6);
  v13 = IsValidTrace;
  if ( IsValidTrace >= 0 )
  {
    if ( IsValidTrace )
      return 3489660990LL;
    try
    {
      v14 = (*(__int64 (__fastcall **)(struct XPerfAddIn::IDiskIOInfoSource *))(*(_QWORD *)this[6] + 104LL))(this[6]);
      std::map<XPerfAddIn::IProcessInfoSource::ImageData const *,XPerfAddIn::IDpcIsrInfoSource::TimeByModule>::map<XPerfAddIn::IProcessInfoSource::ImageData const *,XPerfAddIn::IDpcIsrInfoSource::TimeByModule>(v48);
      v49 = v14;
      v15 = this[3];
      v16 = this[2];
      v44 = this[1];
      v45 = this[8];
      v17 = (PerfAnalyzer::RCAProc *)operator new(0x100u);
      v46 = v17;
      if ( v17 )
        v17 = (PerfAnalyzer::RCAProc *)PerfAnalyzer::RCAProc::RCAProc(
                                         v17,
                                         v39,
                                         a4,
                                         (const struct TimeStamp *)&v38,
                                         (const struct TimeStamp *)&v40,
                                         a7,
                                         (unsigned __int64)v45,
                                         v44,
                                         v16,
                                         v15);
      v50[0] = v17;
      v11 = 1;
      v42 = 1;
      if ( (a7 & 4) != 0 )
      {
        v19 = a7 & 0x10;
      }
      else
      {
        v19 = a7 & 0x10;
        if ( (a7 & 0x10) == 0 )
          goto LABEL_24;
      }
      PerfAnalyzer::CReadAheadDB::Construct(
        (PerfAnalyzer::CReadAheadDB *)v48,
        this[2],
        (const struct TimeStamp *)&v38,
        v18);
      if ( (a7 & 4) != 0 )
      {
        v20 = this[2];
        v21 = (PerfAnalyzer::RCADisk *)operator new(0xA0u);
        v46 = v21;
        if ( v21 )
          v21 = (PerfAnalyzer::RCADisk *)PerfAnalyzer::RCADisk::RCADisk(
                                           v21,
                                           v39,
                                           v43,
                                           (const struct TimeStamp *)&v38,
                                           (const struct TimeStamp *)&v40,
                                           a7,
                                           v20,
                                           (const struct PerfAnalyzer::CReadAheadDB *)v48);
        v50[1] = v21;
        v11 = 2;
        v42 = 2;
      }
LABEL_24:
      v22 = v19 == 0;
      v23 = this + 4;
      if ( !v22 )
      {
        v24 = this[6];
        v45 = *v23;
        v44 = this[2];
        v25 = (PerfAnalyzer::RCAFrag *)operator new(0x100u);
        v46 = v25;
        if ( v25 )
          v25 = (PerfAnalyzer::RCAFrag *)PerfAnalyzer::RCAFrag::RCAFrag(
                                           v25,
                                           v39,
                                           v43,
                                           (const struct TimeStamp *)&v38,
                                           (const struct TimeStamp *)&v40,
                                           a7,
                                           v44,
                                           v45,
                                           v24,
                                           (const struct PerfAnalyzer::CReadAheadDB *)v48);
        v50[v11++] = v25;
        v42 = v11;
      }
      if ( (a7 & 0x100) != 0 )
      {
        v26 = this[6];
        v27 = this[5];
        v28 = *v23;
        v29 = (PerfAnalyzer::RCAMemory *)operator new(0x70u);
        v46 = v29;
        if ( v29 )
          v29 = (PerfAnalyzer::RCAMemory *)PerfAnalyzer::RCAMemory::RCAMemory(
                                             v29,
                                             v39,
                                             v43,
                                             (const struct TimeStamp *)&v38,
                                             (const struct TimeStamp *)&v40,
                                             a7,
                                             v28,
                                             v27,
                                             v26);
        v50[v11++] = v29;
        v42 = v11;
      }
      for ( j = 0; j < v11; ++j )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, size_t *))(*(_QWORD *)v50[j] + 8LL))(v50[j], &v47, &v41);
        if ( v13 < 0 )
          goto LABEL_35;
      }
      v52[0] = 16 * (v47 - 1) + 376;
      v31 = v52[0] + v41;
      v41 += v52[0];
      if ( !v47 )
      {
        v31 += 16LL;
        v41 = v31;
      }
      v32 = v31;
      v33 = (struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *)malloc(v31);
      v34 = v51;
      *v51 = v33;
      if ( v33 )
      {
        memset_0(v33, 0, v32);
        *(_QWORD *)*v34 = v41;
        *((_QWORD *)*v34 + 2) = v38;
        *((_QWORD *)*v34 + 3) = v40;
        for ( k = 0; k < v11; ++k )
        {
          v13 = (*(__int64 (__fastcall **)(_QWORD, struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *, __int64 *))(*(_QWORD *)v50[k] + 16LL))(
                  v50[k],
                  *v34,
                  v52);
          if ( v13 < 0 )
            break;
        }
LABEL_35:
        std::_Tree<std::_Tmap_traits<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>(v48);
        goto LABEL_45;
      }
      v13 = -2147024882;
      std::_Tree<std::_Tmap_traits<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>(v48);
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v39) = -2147024882;
      v13 = -2147024882;
      v11 = v42;
    }
  }
LABEL_45:
  for ( m = 0; m < v11; ++m )
  {
    v37 = (void (__fastcall ***)(_QWORD, __int64))v50[m];
    if ( v37 )
      (**v37)(v37, 1);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800854c0  mov     rax, rsp
0x1800854c3  mov     [rax+20h], rsi
0x1800854c7  push    rdi
0x1800854c8  push    r12
0x1800854ca  push    r13
0x1800854cc  push    r14
0x1800854ce  push    r15
0x1800854d0  sub     rsp, 0F0h
0x1800854d7  mov     r13, r9
0x1800854da  mov     [rsp+118h+var_A0], r9
0x1800854df  mov     [rsp+118h+var_C0], r8
0x1800854e4  mov     [rsp+118h+var_40], rdx
0x1800854ec  mov     r15, rcx
0x1800854ef  xorps   xmm0, xmm0
0x1800854f2  movups  xmmword ptr [rax-60h], xmm0
0x1800854f6  movups  xmmword ptr [rax-50h], xmm0
0x1800854fa  mov     [rsp+118h+var_C8], 0
0x180085503  mov     [rsp+118h+var_B8], 0
0x18008550c  mov     qword ptr [rax-80h], 0
0x180085514  mov     [rsp+118h+var_B0], 0
0x18008551d  test    rdx, rdx
0x180085520  jnz     short loc_18008552C
0x180085522  mov     eax, 80004003h
0x180085527  jmp     loc_1800859AB
0x18008552c  mov     qword ptr [rdx], 0
0x180085533  mov     rsi, [rsp+118h+arg_28]
0x18008553b  mov     rax, [rsi]
0x18008553e  mov     r14, [rsp+118h+arg_20]
0x180085546  cmp     [r14], rax
0x180085549  jge     loc_1800859A6
0x18008554f  test    r8, r8
0x180085552  jz      loc_1800859A6
0x180085558  test    r13, r13
0x18008555b  jz      loc_1800859A6
0x180085561  xor     ecx, ecx; this
0x180085563  cmp     rcx, r13
0x180085566  jnb     short loc_18008557B
0x180085568  mov     rax, [r8+rcx*8]
0x18008556c  cmp     dword ptr [rax+54h], 0
0x180085570  jz      loc_1800859A6
0x180085576  inc     rcx
0x180085579  jmp     short loc_180085563
0x18008557b  call    ?InitOptions@CPerfAnalyzer@PerfAnalyzer@@AEBAPEAUOptions@IPerfAnalyzer@2@XZ; PerfAnalyzer::CPerfAnalyzer::InitOptions(void)
0x180085580  test    rax, rax
0x180085583  jnz     short loc_18008558F
0x180085585  mov     eax, 8007000Eh
0x18008558a  jmp     loc_1800859AB
0x18008558f  xor     edi, edi
0x180085591  mov     [rsp+118h+var_A8], rdi
0x180085596  mov     [rsp+118h+var_F8], rsi; struct TimeStamp *
0x18008559b  mov     r9, r14; struct TimeStamp *
0x18008559e  lea     r8, [rsp+118h+var_B8]; struct TimeStamp *
0x1800855a3  lea     rdx, [rsp+118h+var_C8]; struct TimeStamp *
0x1800855a8  mov     rcx, r15; this
0x1800855ab  call    ?IsValidTrace@CPerfAnalyzer@PerfAnalyzer@@UEBAJAEAVTimeStamp@XPerfCore@@0AEBV34@1@Z; PerfAnalyzer::CPerfAnalyzer::IsValidTrace(XPerfCore::TimeStamp &,XPerfCore::TimeStamp &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &)
0x1800855b0  mov     esi, eax
0x1800855b2  test    eax, eax
0x1800855b4  js      loc_180085975
0x1800855ba  mov     r12d, [rsp+118h+arg_30]
0x1800855c2  jz      short loc_1800855CE
0x1800855c4  mov     eax, 0D000003Eh
0x1800855c9  jmp     loc_1800859AB
0x1800855ce  mov     rcx, [r15+30h]
0x1800855d2  mov     rax, [rcx]
0x1800855d5  mov     rax, [rax+68h]
0x1800855d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855de  mov     rdi, rax
0x1800855e1  lea     rcx, [rsp+118h+var_78]
0x1800855e9  call    ??0?$map@PEBUImageData@IProcessInfoSource@XPerfAddIn@@UTimeByModule@IDpcIsrInfoSource@3@U?$less@PEBUImageData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUImageData@IProcessInfoSource@XPerfAddIn@@UTimeByModule@IDpcIsrInfoSource@3@@std@@@7@@std@@QEAA@XZ; std::map<XPerfAddIn::IProcessInfoSource::ImageData const *,XPerfAddIn::IDpcIsrInfoSource::TimeByModule>::map<XPerfAddIn::IProcessInfoSource::ImageData const *,XPerfAddIn::IDpcIsrInfoSource::TimeByModule>(void)
0x1800855ee  mov     [rsp+118h+var_68], rdi
0x1800855f6  mov     rdi, [r15+18h]
0x1800855fa  mov     r14, [r15+10h]
0x1800855fe  mov     rax, [r15+8]
0x180085602  mov     [rsp+118h+var_98], rax
0x18008560a  mov     rax, [r15+40h]
0x18008560e  mov     [rsp+118h+var_90], rax
0x180085616  mov     ecx, 100h; Size
0x18008561b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180085620  mov     [rsp+118h+var_88], rax
0x180085628  test    rax, rax
0x18008562b  jz      short loc_180085676
0x18008562d  mov     [rsp+118h+var_D0], rdi; struct XPerfAddIn::IDpcIsrInfoSource2 *
0x180085632  mov     [rsp+118h+var_D8], r14; struct XPerfAddIn::IDiskIOInfoSource *
0x180085637  mov     rcx, [rsp+118h+var_98]
0x18008563f  mov     [rsp+118h+var_E0], rcx; struct XPerfAddIn::ICSwitchInfoSource *
0x180085644  mov     rcx, [rsp+118h+var_90]
0x18008564c  mov     [rsp+118h+var_E8], rcx; unsigned __int64
0x180085651  mov     [rsp+118h+var_F0], r12d; unsigned int
0x180085656  lea     rcx, [rsp+118h+var_B8]
0x18008565b  mov     [rsp+118h+var_F8], rcx; struct TimeStamp *
0x180085660  lea     r9, [rsp+118h+var_C8]; struct TimeStamp *
0x180085665  mov     r8, r13; unsigned __int64
0x180085668  mov     rdx, [rsp+118h+var_C0]; struct XPerfAddIn::IProcessInfoSource::ThreadData **
0x18008566d  mov     rcx, rax; this
0x180085670  call    ??0RCAProc@PerfAnalyzer@@QEAA@QEAPEBUThreadData@IProcessInfoSource@XPerfAddIn@@_KAEBVTimeStamp@XPerfCore@@2K1PEBUICSwitchInfoSource@4@PEBUIDiskIOInfoSource@4@PEBUIDpcIsrInfoSource2@4@@Z; PerfAnalyzer::RCAProc::RCAProc(XPerfAddIn::IProcessInfoSource::ThreadData const * * const,unsigned __int64,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong,unsigned __int64,XPerfAddIn::ICSwitchInfoSource const *,XPerfAddIn::IDiskIOInfoSource const *,XPerfAddIn::IDpcIsrInfoSource2 const *)
0x180085675  nop
0x180085676  mov     [rsp+118h+var_60], rax
0x18008567e  mov     edi, 1
0x180085683  mov     [rsp+118h+var_A8], rdi
0x180085688  mov     r13d, r12d
0x18008568b  and     r13d, 4
0x18008568f  mov     r14d, r12d
0x180085692  jz      short loc_18008569A
0x180085694  and     r14d, 10h
0x180085698  jmp     short loc_1800856A4
0x18008569a  and     r14d, 10h
0x18008569e  jz      loc_180085725
0x1800856a4  lea     r8, [rsp+118h+var_C8]; struct TimeStamp *
0x1800856a9  mov     rdx, [r15+10h]; struct XPerfAddIn::IDiskIOInfoSource *
0x1800856ad  lea     rcx, [rsp+118h+var_78]; this
0x1800856b5  call    ?Construct@CReadAheadDB@PerfAnalyzer@@QEAAJPEBUIDiskIOInfoSource@XPerfAddIn@@AEBVTimeStamp@XPerfCore@@1@Z; PerfAnalyzer::CReadAheadDB::Construct(XPerfAddIn::IDiskIOInfoSource const *,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &)
0x1800856ba  test    r13d, r13d
0x1800856bd  jz      short loc_180085725
0x1800856bf  mov     rdi, [r15+10h]
0x1800856c3  mov     ecx, 0A0h; Size
0x1800856c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800856cd  mov     [rsp+118h+var_88], rax
0x1800856d5  test    rax, rax
0x1800856d8  jz      short loc_180085713
0x1800856da  lea     rcx, [rsp+118h+var_78]
0x1800856e2  mov     [rsp+118h+var_E0], rcx; struct PerfAnalyzer::CReadAheadDB *
0x1800856e7  mov     [rsp+118h+var_E8], rdi; struct XPerfAddIn::IDiskIOInfoSource *
0x1800856ec  mov     [rsp+118h+var_F0], r12d; unsigned int
0x1800856f1  lea     rcx, [rsp+118h+var_B8]
0x1800856f6  mov     [rsp+118h+var_F8], rcx; struct TimeStamp *
0x1800856fb  lea     r9, [rsp+118h+var_C8]; struct TimeStamp *
0x180085700  mov     r8, [rsp+118h+var_A0]; unsigned __int64
0x180085705  mov     rdx, [rsp+118h+var_C0]; struct XPerfAddIn::IProcessInfoSource::ThreadData **
0x18008570a  mov     rcx, rax; this
0x18008570d  call    ??0RCADisk@PerfAnalyzer@@QEAA@QEAPEBUThreadData@IProcessInfoSource@XPerfAddIn@@_KAEBVTimeStamp@XPerfCore@@2KPEBUIDiskIOInfoSource@4@AEBVCReadAheadDB@1@@Z; PerfAnalyzer::RCADisk::RCADisk(XPerfAddIn::IProcessInfoSource::ThreadData const * * const,unsigned __int64,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong,XPerfAddIn::IDiskIOInfoSource const *,PerfAnalyzer::CReadAheadDB const &)
0x180085712  nop
0x180085713  mov     [rsp+118h+var_58], rax
0x18008571b  mov     edi, 2
0x180085720  mov     [rsp+118h+var_A8], rdi
0x180085725  test    r14d, r14d
0x180085728  lea     r14, [r15+20h]
0x18008572c  jz      loc_1800857C7
0x180085732  mov     r13, [r15+30h]
0x180085736  mov     rax, [r14]
0x180085739  mov     [rsp+118h+var_90], rax
0x180085741  mov     rax, [r15+10h]
0x180085745  mov     [rsp+118h+var_98], rax
0x18008574d  mov     ecx, 100h; Size
0x180085752  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180085757  mov     [rsp+118h+var_88], rax
0x18008575f  test    rax, rax
0x180085762  jz      short loc_1800857B7
0x180085764  lea     rcx, [rsp+118h+var_78]
0x18008576c  mov     [rsp+118h+var_D0], rcx; struct PerfAnalyzer::CReadAheadDB *
0x180085771  mov     [rsp+118h+var_D8], r13; struct XPerfAddIn::IProcessInfoSource *
0x180085776  mov     rcx, [rsp+118h+var_90]
0x18008577e  mov     [rsp+118h+var_E0], rcx; struct XPerfAddIn::IHardFaultInfoSource *
0x180085783  mov     rcx, [rsp+118h+var_98]
0x18008578b  mov     [rsp+118h+var_E8], rcx; struct XPerfAddIn::IDiskIOInfoSource *
0x180085790  mov     [rsp+118h+var_F0], r12d; unsigned int
0x180085795  lea     rcx, [rsp+118h+var_B8]
0x18008579a  mov     [rsp+118h+var_F8], rcx; struct TimeStamp *
0x18008579f  lea     r9, [rsp+118h+var_C8]; struct TimeStamp *
0x1800857a4  mov     r8, [rsp+118h+var_A0]; unsigned __int64
0x1800857a9  mov     rdx, [rsp+118h+var_C0]; struct XPerfAddIn::IProcessInfoSource::ThreadData **
0x1800857ae  mov     rcx, rax; this
0x1800857b1  call    ??0RCAFrag@PerfAnalyzer@@QEAA@QEAPEBUThreadData@IProcessInfoSource@XPerfAddIn@@_KAEBVTimeStamp@XPerfCore@@2KPEBUIDiskIOInfoSource@4@PEBUIHardFaultInfoSource@4@PEBU34@AEBVCReadAheadDB@1@@Z; PerfAnalyzer::RCAFrag::RCAFrag(XPerfAddIn::IProcessInfoSource::ThreadData const * * const,unsigned __int64,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong,XPerfAddIn::IDiskIOInfoSource const *,XPerfAddIn::IHardFaultInfoSource const *,XPerfAddIn::IProcessInfoSource const *,PerfAnalyzer::CReadAheadDB const &)
0x1800857b6  nop
0x1800857b7  mov     [rsp+rdi*8+118h+var_60], rax
0x1800857bf  inc     rdi
0x1800857c2  mov     [rsp+118h+var_A8], rdi
0x1800857c7  bt      r12d, 8
0x1800857cc  jnb     short loc_180085836
0x1800857ce  mov     r13, [r15+30h]
0x1800857d2  mov     r15, [r15+28h]
0x1800857d6  mov     r14, [r14]
0x1800857d9  mov     ecx, 70h ; 'p'; Size
0x1800857de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800857e3  mov     [rsp+118h+var_88], rax
0x1800857eb  test    rax, rax
0x1800857ee  jz      short loc_180085826
0x1800857f0  mov     [rsp+118h+var_D8], r13; struct XPerfAddIn::IProcessInfoSource *
0x1800857f5  mov     [rsp+118h+var_E0], r15; struct XPerfAddIn::IPerfCounters *
0x1800857fa  mov     [rsp+118h+var_E8], r14; struct XPerfAddIn::IHardFaultInfoSource *
0x1800857ff  mov     [rsp+118h+var_F0], r12d; unsigned int
0x180085804  lea     rcx, [rsp+118h+var_B8]
0x180085809  mov     [rsp+118h+var_F8], rcx; struct TimeStamp *
0x18008580e  lea     r9, [rsp+118h+var_C8]; struct TimeStamp *
0x180085813  mov     r8, [rsp+118h+var_A0]; unsigned __int64
0x180085818  mov     rdx, [rsp+118h+var_C0]; struct XPerfAddIn::IProcessInfoSource::ThreadData **
0x18008581d  mov     rcx, rax; this
0x180085820  call    ??0RCAMemory@PerfAnalyzer@@QEAA@QEAPEBUThreadData@IProcessInfoSource@XPerfAddIn@@_KAEBVTimeStamp@XPerfCore@@2KPEBUIHardFaultInfoSource@4@PEBUIPerfCounters@4@PEBU34@@Z; PerfAnalyzer::RCAMemory::RCAMemory(XPerfAddIn::IProcessInfoSource::ThreadData const * * const,unsigned __int64,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong,XPerfAddIn::IHardFaultInfoSource const *,XPerfAddIn::IPerfCounters const *,XPerfAddIn::IProcessInfoSource const *)
0x180085825  nop
0x180085826  mov     [rsp+rdi*8+118h+var_60], rax
0x18008582e  inc     rdi
0x180085831  mov     [rsp+118h+var_A8], rdi
0x180085836  xor     r14d, r14d
0x180085839  cmp     r14, rdi
0x18008583c  jnb     short loc_18008587D
0x18008583e  mov     rcx, [rsp+r14*8+118h+var_60]
0x180085846  mov     rax, [rcx]
0x180085849  lea     r8, [rsp+118h+var_B0]
0x18008584e  lea     rdx, [rsp+118h+var_80]
0x180085856  mov     rax, [rax+8]
0x18008585a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008585f  mov     esi, eax
0x180085861  test    eax, eax
0x180085863  jns     short loc_180085878
0x180085865  lea     rcx, [rsp+118h+var_78]
0x18008586d  call    ??1?$_Tree@V?$_Tmap_traits@KV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>(void)
0x180085872  nop
0x180085873  jmp     loc_180085975
0x180085878  inc     r14
0x18008587b  jmp     short loc_180085839
0x18008587d  mov     rcx, [rsp+118h+var_80]
0x180085885  lea     rax, [rcx-1]
0x180085889  shl     rax, 4
0x18008588d  add     rax, 178h
0x180085893  mov     [rsp+118h+var_38], rax
0x18008589b  mov     rdx, [rsp+118h+var_B0]
0x1800858a0  add     rdx, rax
0x1800858a3  mov     [rsp+118h+var_B0], rdx
0x1800858a8  test    rcx, rcx
0x1800858ab  jnz     short loc_1800858B6
0x1800858ad  add     rdx, 10h
0x1800858b1  mov     [rsp+118h+var_B0], rdx
0x1800858b6  mov     r14, rdx
0x1800858b9  mov     rcx, rdx; Size
0x1800858bc  call    cs:__imp_malloc
0x1800858c2  mov     r15, [rsp+118h+var_40]
0x1800858ca  mov     [r15], rax
0x1800858cd  test    rax, rax
0x1800858d0  jnz     short loc_1800858EA
0x1800858d2  mov     esi, 8007000Eh
0x1800858d7  lea     rcx, [rsp+118h+var_78]
0x1800858df  call    ??1?$_Tree@V?$_Tmap_traits@KV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>(void)
0x1800858e4  nop
0x1800858e5  jmp     loc_180085975
0x1800858ea  mov     r8, r14; Size
0x1800858ed  xor     edx, edx; Val
0x1800858ef  mov     rcx, rax; void *
0x1800858f2  call    memset_0
0x1800858f7  mov     rcx, [r15]
0x1800858fa  mov     rax, [rsp+118h+var_B0]
0x1800858ff  mov     [rcx], rax
0x180085902  mov     rcx, [r15]
0x180085905  mov     rax, [rsp+118h+var_C8]
0x18008590a  mov     [rcx+10h], rax
0x18008590e  mov     rcx, [r15]
0x180085911  mov     rax, [rsp+118h+var_B8]
0x180085916  mov     [rcx+18h], rax
0x18008591a  xor     r14d, r14d
0x18008591d  cmp     r14, rdi
0x180085920  jnb     short loc_18008595C
0x180085922  mov     rcx, [rsp+r14*8+118h+var_60]
0x18008592a  mov     rax, [rcx]
0x18008592d  lea     r8, [rsp+118h+var_38]
0x180085935  mov     rdx, [r15]
0x180085938  mov     rax, [rax+10h]
0x18008593c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085941  mov     esi, eax
0x180085943  test    eax, eax
0x180085945  jns     short loc_180085957
0x180085947  lea     rcx, [rsp+118h+var_78]
0x18008594f  call    ??1?$_Tree@V?$_Tmap_traits@KV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>(void)
0x180085954  nop
0x180085955  jmp     short loc_180085975
0x180085957  inc     r14
0x18008595a  jmp     short loc_18008591D
0x18008595c  lea     rcx, [rsp+118h+var_78]
0x180085964  call    ??1?$_Tree@V?$_Tmap_traits@KV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$vector@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@V?$allocator@USegmentPreference@IAllocationInfoSource@DX@XPerfAddIn@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<ulong>,std::allocator<std::pair<ulong const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>(void)
0x180085969  nop
0x18008596a  jmp     short loc_180085975
0x18008596c  mov     esi, dword ptr [rsp+118h+var_C0]
0x180085970  mov     rdi, [rsp+118h+var_A8]
0x180085975  xor     r14d, r14d
0x180085978  test    rdi, rdi
0x18008597b  jz      short loc_1800859A2
0x18008597d  mov     rcx, [rsp+r14*8+118h+var_60]
0x180085985  test    rcx, rcx
0x180085988  jz      short loc_18008599A
0x18008598a  mov     rax, [rcx]
0x18008598d  mov     edx, 1
0x180085992  mov     rax, [rax]
0x180085995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008599a  inc     r14
0x18008599d  cmp     r14, rdi
0x1800859a0  jb      short loc_18008597D
0x1800859a2  mov     eax, esi
0x1800859a4  jmp     short loc_1800859AB
0x1800859a6  mov     eax, 80070057h
0x1800859ab  mov     rsi, [rsp+118h+arg_18]
0x1800859b3  add     rsp, 0F0h
0x1800859ba  pop     r15
0x1800859bc  pop     r14
0x1800859be  pop     r13
0x1800859c0  pop     r12
0x1800859c2  pop     rdi
0x1800859c3  retn
```
