# SleepstudyJsonReporter::WriteReport(ushort const *,SleepStudyReportData &)

- ea: `0x18004a180`
- end: `0x18004a357`
- name: `?WriteReport@SleepstudyJsonReporter@@UEAAJPEBGAEAUSleepStudyReportData@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(SleepstudyJsonReporter *__hidden this, const unsigned __int16 *, struct SleepStudyReportData *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800256d0`
- `0x18002574c`
- `0x18004a180`
- `0x18004a360`
- `0x18004a420`
- `0x180072c1c`
- `0x180072ef8`
- `0x180073d60`
- `0x180075610`
- `0x18007acd8`
- `0x18007b230`
- `0x18007b258`
- `0x18007e940`
- `0x18007ea68`
- `0x1800907f0`

## import_xrefs

- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x18004a1fb`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x18004a1fb`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18004a30b`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18004a30b`
- `msvcp_win!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x18004a2b3`
- `msvcp_win!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x18004a2b3`

## string_xrefs

- `0x18004a2b9`: `Attempted to complete JSON stream with unclosed values.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SleepstudyJsonReporter::WriteReport(
        SleepstudyJsonReporter *this,
        const unsigned __int16 *a2,
        struct SleepStudyReportData *a3)
{
  const struct SessionModel::SystemPowerReport **v6; // rax
  const struct SessionModel::SystemPowerReport *v7; // rbx
  char v8; // al
  unsigned int v9; // ebx
  const struct SessionModel::SystemPowerReport *v11; // [rsp+20h] [rbp-1B8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-1B0h] BYREF
  _BYTE v13[64]; // [rsp+40h] [rbp-198h] BYREF
  _QWORD v14[2]; // [rsp+80h] [rbp-158h] BYREF
  _BYTE v15[8]; // [rsp+90h] [rbp-148h] BYREF
  _BYTE v16[256]; // [rsp+98h] [rbp-140h] BYREF
  __int64 v17; // [rsp+198h] [rbp-40h]
  __int128 v18; // [rsp+1A0h] [rbp-38h]
  __int16 v19; // [rsp+1B0h] [rbp-28h]
  const std::exception *v20; // [rsp+1C0h] [rbp-18h] BYREF
  int v21; // [rsp+1F8h] [rbp+20h] BYREF

  SessionModel::SystemPowerReportBuilder::SystemPowerReportBuilder((SessionModel::SystemPowerReportBuilder *)v13);
  v11 = 0;
  std::basic_fstream<unsigned short>::basic_fstream<unsigned short>(v14);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  std::ios_base::exceptions((std::ios_base *)((char *)v14 + *(int *)(v14[0] + 4LL)), 6);
  std::basic_fstream<unsigned short>::open(v14, a2);
  try
  {
    SessionModel::SystemPowerReportBuilder::ParseFromLegacySessionData(
      (SessionModel::SystemPowerReportBuilder *)v13,
      a3);
    v6 = (const struct SessionModel::SystemPowerReport **)SessionModel::SystemPowerReportBuilder::BuildSystemPowerReport(
                                                            v13,
                                                            &v21);
    v7 = *v6;
    *v6 = 0;
    v11 = v7;
    std::unique_ptr<SessionModel::SystemPowerReport>::~unique_ptr<SessionModel::SystemPowerReport>(&v21);
    v8 = v19;
    if ( *((_BYTE *)this + 8) )
      v8 = 1;
    LOBYTE(v19) = v8;
    SleepstudyJsonWriter::StartObject((SleepstudyJsonWriter *)v14, 0);
    v9 = SleepstudyJsonReporter::WriteReport(this, v7, (struct SleepstudyJsonWriter *)v14);
    SleepstudyJsonWriter::EndObject((SleepstudyJsonWriter *)v14);
    if ( v17 != (_QWORD)v18 )
    {
      std::basic_ostream<unsigned short>::flush(v15);
      std::logic_error::logic_error(
        (std::logic_error *)pExceptionObject,
        "Attempted to complete JSON stream with unclosed values.");
      throw (std::logic_error *)pExceptionObject;
    }
    if ( !std::basic_filebuf<unsigned short>::close(v16) )
      std::basic_ios<unsigned short>::setstate((char *)v14 + *(int *)(v14[0] + 4LL), 2, 0);
  }
  catch ( const std::exception *v20 )
  {
    v21 = -2147467259;
    v9 = v21;
  }
  catch ( ... )
  {
    v21 = -2147467259;
    v9 = v21;
  }
  SleepstudyJsonWriter::~SleepstudyJsonWriter((SleepstudyJsonWriter *)v14);
  std::unique_ptr<SessionModel::SystemPowerReport>::~unique_ptr<SessionModel::SystemPowerReport>(&v11);
  SessionModel::SystemPowerReportBuilder::~SystemPowerReportBuilder((SessionModel::SystemPowerReportBuilder *)v13);
  return v9;
}

```

## disassembly

```asm
0x18004a180  mov     [rsp+arg_0], rbx
0x18004a185  mov     [rsp+arg_8], rsi
0x18004a18a  push    rdi
0x18004a18b  sub     rsp, 1D0h
0x18004a192  mov     rsi, r8
0x18004a195  mov     rbx, rdx
0x18004a198  mov     rdi, rcx
0x18004a19b  lea     rcx, [rsp+1D8h+var_198]; this
0x18004a1a0  call    ??0SystemPowerReportBuilder@SessionModel@@QEAA@XZ; SessionModel::SystemPowerReportBuilder::SystemPowerReportBuilder(void)
0x18004a1a5  nop
0x18004a1a6  mov     [rsp+1D8h+var_1B8], 0
0x18004a1af  lea     rcx, [rsp+1D8h+var_158]
0x18004a1b7  call    ??0?$basic_fstream@GU?$char_traits@G@std@@@std@@QEAA@XZ; std::basic_fstream<ushort>::basic_fstream<ushort>(void)
0x18004a1bc  nop
0x18004a1bd  mov     [rsp+1D8h+var_40], 0
0x18004a1c9  xorps   xmm0, xmm0
0x18004a1cc  movdqa  [rsp+1D8h+var_38], xmm0
0x18004a1d5  mov     [rsp+1D8h+var_28], 0
0x18004a1df  mov     rax, [rsp+1D8h+var_158]
0x18004a1e7  movsxd  rcx, dword ptr [rax+4]
0x18004a1eb  lea     rax, [rsp+1D8h+var_158]
0x18004a1f3  add     rcx, rax
0x18004a1f6  mov     edx, 6
0x18004a1fb  call    cs:__imp_?exceptions@ios_base@std@@QEAAXH@Z; std::ios_base::exceptions(int)
0x18004a201  mov     rdx, rbx
0x18004a204  lea     rcx, [rsp+1D8h+var_158]
0x18004a20c  call    ?open@?$basic_fstream@GU?$char_traits@G@std@@@std@@QEAAXPEBGHH@Z; std::basic_fstream<ushort>::open(ushort const *,int,int)
0x18004a211  nop
0x18004a212  mov     rdx, rsi; struct SleepStudyReportData *
0x18004a215  lea     rcx, [rsp+1D8h+var_198]; this
0x18004a21a  call    ?ParseFromLegacySessionData@SystemPowerReportBuilder@SessionModel@@QEAAXAEBUSleepStudyReportData@@@Z; SessionModel::SystemPowerReportBuilder::ParseFromLegacySessionData(SleepStudyReportData const &)
0x18004a21f  lea     rdx, [rsp+1D8h+arg_18]
0x18004a227  lea     rcx, [rsp+1D8h+var_198]
0x18004a22c  call    ?BuildSystemPowerReport@SystemPowerReportBuilder@SessionModel@@QEAA?AV?$unique_ptr@VSystemPowerReport@SessionModel@@U?$default_delete@VSystemPowerReport@SessionModel@@@std@@@std@@XZ; SessionModel::SystemPowerReportBuilder::BuildSystemPowerReport(void)
0x18004a231  mov     rbx, [rax]
0x18004a234  mov     qword ptr [rax], 0
0x18004a23b  mov     [rsp+1D8h+var_1B8], rbx
0x18004a240  lea     rcx, [rsp+1D8h+arg_18]
0x18004a248  call    ??1?$unique_ptr@VSystemPowerReport@SessionModel@@U?$default_delete@VSystemPowerReport@SessionModel@@@std@@@std@@QEAA@XZ; std::unique_ptr<SessionModel::SystemPowerReport>::~unique_ptr<SessionModel::SystemPowerReport>(void)
0x18004a24d  movzx   eax, byte ptr [rsp+1D8h+var_28]
0x18004a255  mov     ecx, 1
0x18004a25a  cmp     byte ptr [rdi+8], 0
0x18004a25e  cmovnz  eax, ecx
0x18004a261  mov     byte ptr [rsp+1D8h+var_28], al
0x18004a268  xor     edx, edx; unsigned __int16 *
0x18004a26a  lea     rcx, [rsp+1D8h+var_158]; this
0x18004a272  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18004a277  lea     r8, [rsp+1D8h+var_158]; struct SleepstudyJsonWriter *
0x18004a27f  mov     rdx, rbx; struct SessionModel::SystemPowerReport *
0x18004a282  mov     rcx, rdi; this
0x18004a285  call    ?WriteReport@SleepstudyJsonReporter@@AEAAJAEBVSystemPowerReport@SessionModel@@AEAVSleepstudyJsonWriter@@@Z; SleepstudyJsonReporter::WriteReport(SessionModel::SystemPowerReport const &,SleepstudyJsonWriter &)
0x18004a28a  mov     ebx, eax
0x18004a28c  lea     rcx, [rsp+1D8h+var_158]; this
0x18004a294  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18004a299  mov     rax, qword ptr [rsp+1D8h+var_38]
0x18004a2a1  cmp     [rsp+1D8h+var_40], rax
0x18004a2a9  jz      short loc_18004A2DB
0x18004a2ab  lea     rcx, [rsp+1D8h+var_148]
0x18004a2b3  call    cs:__imp_?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x18004a2b9  lea     rdx, aAttemptedToCom; "Attempted to complete JSON stream with "...
0x18004a2c0  lea     rcx, [rsp+1D8h+pExceptionObject]; this
0x18004a2c5  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18004a2ca  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18004a2d1  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x18004a2d6  call    _CxxThrowException_0
0x18004a2db  lea     rcx, [rsp+1D8h+var_140]
0x18004a2e3  call    ?close@?$basic_filebuf@GU?$char_traits@G@std@@@std@@QEAAPEAV12@XZ; std::basic_filebuf<ushort>::close(void)
0x18004a2e8  test    rax, rax
0x18004a2eb  jnz     short loc_18004A312
0x18004a2ed  mov     rax, [rsp+1D8h+var_158]
0x18004a2f5  movsxd  rcx, dword ptr [rax+4]
0x18004a2f9  lea     rax, [rsp+1D8h+var_158]
0x18004a301  add     rcx, rax
0x18004a304  xor     r8d, r8d
0x18004a307  lea     edx, [r8+2]
0x18004a30b  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18004a311  nop
0x18004a312  jmp     short loc_18004A31D
0x18004a314  jmp     short $+2
0x18004a316  mov     ebx, [rsp+1D8h+arg_18]
0x18004a31d  lea     rcx, [rsp+1D8h+var_158]; this
0x18004a325  call    ??1SleepstudyJsonWriter@@QEAA@XZ; SleepstudyJsonWriter::~SleepstudyJsonWriter(void)
0x18004a32a  nop
0x18004a32b  lea     rcx, [rsp+1D8h+var_1B8]
0x18004a330  call    ??1?$unique_ptr@VSystemPowerReport@SessionModel@@U?$default_delete@VSystemPowerReport@SessionModel@@@std@@@std@@QEAA@XZ; std::unique_ptr<SessionModel::SystemPowerReport>::~unique_ptr<SessionModel::SystemPowerReport>(void)
0x18004a335  nop
0x18004a336  lea     rcx, [rsp+1D8h+var_198]; this
0x18004a33b  call    ??1SystemPowerReportBuilder@SessionModel@@QEAA@XZ; SessionModel::SystemPowerReportBuilder::~SystemPowerReportBuilder(void)
0x18004a340  mov     eax, ebx
0x18004a342  lea     r11, [rsp+1D8h+var_8]
0x18004a34a  mov     rbx, [r11+10h]
0x18004a34e  mov     rsi, [r11+18h]
0x18004a352  mov     rsp, r11
0x18004a355  pop     rdi
0x18004a356  retn
```
