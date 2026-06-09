# AOMDHandler::ShouldExitEarly(void)

- ea: `0x1800115f8`
- end: `0x180011759`
- name: `?ShouldExitEarly@AOMDHandler@@AEAA_NXZ`
- size: `353`
- prototype: `char __fastcall(AOMDHandler *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6d4`

## callees

- `0x180001008`
- `0x180004854`
- `0x180006390`
- `0x18000e168`
- `0x18000e7ec`
- `0x1800115f8`
- `0x1800158a0`
- `0x1800201dc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800116e0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800116e0`

## string_xrefs

- `0x180011654`: `AOMDUsageTipTestCompletionReason::AdminProtectionDetected`
- `0x1800116a9`: `ShouldExitEarly_FailedToReadSelfThrottleEndTime`
- `0x180011726`: `AOMDUsageTipTestCompletionReason::SelfThrottleActive`

## pseudocode

```c
char __fastcall AOMDHandler::ShouldExitEarly(AOMDHandler *this)
{
  int v1; // eax
  const char *v2; // r9
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v6; // rcx
  const char *v7; // r8
  char v8; // al
  unsigned int value_qword; // eax
  struct _FILETIME v11; // rbx
  __int64 v12; // rcx
  const char *v13; // rcx
  const char *v14; // r8
  char v15; // al
  _QWORD v16[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)this;
  try
  {
    v1 = LUAIsShadowAdminEnabled();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x632,
      (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      v2);
    return 0;
  }
  if ( v1 )
  {
    v3 = TlgHelper::Provider();
    if ( *(_DWORD *)v3 > 4u && (*((_QWORD *)v3 + 2) & 2) != 0 && (*((_QWORD *)v3 + 3) & 2LL) == *((_QWORD *)v3 + 3) )
    {
      SystemTimeAsFileTime = (struct _FILETIME)L"ShouldExitEarly_ShadowAdminEnabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v3,
        (__int64)word_18002A342,
        v4,
        v5,
        (int **)&SystemTimeAsFileTime);
    }
    v6 = "AOMDUsageTipTestCompletionReason::AdminProtectionDetected";
    v7 = "AOMDUsageTipTestCompletionReason::AdminProtectionDetected";
    v8 = 65;
    do
    {
      ++v6;
      if ( v8 == 58 )
        v7 = v6;
      v8 = *v6;
    }
    while ( *v6 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      (__int64)v6,
      101,
      (__int64)v7);
    return 1;
  }
  else
  {
    v19 = 0;
    value_qword = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
                    -2147483647,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
                    L"AOMDSelfThrottleEndTime",
                    &v19);
    v16[0] = L"ShouldExitEarly_FailedToReadSelfThrottleEndTime";
    v16[1] = 47;
    TlgHelper::LogIfFailedExpected(v16, value_qword);
    if ( v19
      && (SystemTimeAsFileTime = 0,
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
          v11 = SystemTimeAsFileTime,
          v20 = v19,
          TlgHelper::LogInfoFiletime<unsigned short const (&)[36],_FILETIME &,_FILETIME>(
            v12,
            &SystemTimeAsFileTime,
            &v20),
          *(_QWORD *)&v11 < v19) )
    {
      v13 = "AOMDUsageTipTestCompletionReason::SelfThrottleActive";
      v14 = "AOMDUsageTipTestCompletionReason::SelfThrottleActive";
      v15 = 65;
      do
      {
        ++v13;
        if ( v15 == 58 )
          v14 = v13;
        v15 = *v13;
      }
      while ( *v13 );
      tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
        (__int64)v13,
        102,
        (__int64)v14);
      return 1;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800115f8  mov     qword ptr [rsp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800115fd  push    rbx
0x1800115fe  sub     rsp, 40h
0x180011602  call    LUAIsShadowAdminEnabled
0x180011607  test    eax, eax
0x180011609  jz      short loc_180011681
0x18001160b  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180011610  mov     ecx, [rax]
0x180011612  cmp     ecx, 4
0x180011615  jbe     short loc_180011654
0x180011617  mov     rdx, [rax+18h]
0x18001161b  mov     rcx, [rax+10h]
0x18001161f  test    cl, 2
0x180011622  jz      short loc_180011654
0x180011624  mov     rcx, rdx
0x180011627  and     ecx, 2
0x18001162a  cmp     rcx, rdx
0x18001162d  jnz     short loc_180011654
0x18001162f  lea     rcx, aShouldexitearl; "ShouldExitEarly_ShadowAdminEnabled"
0x180011636  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18001163b  lea     rcx, [rsp+48h+SystemTimeAsFileTime]
0x180011640  mov     [rsp+48h+var_28], rcx
0x180011645  lea     rdx, word_18002A342
0x18001164c  mov     rcx, rax
0x18001164f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180011654  lea     rcx, aAomdusagetipte_2; "AOMDUsageTipTestCompletionReason::Admin"...
0x18001165b  mov     r8, rcx
0x18001165e  mov     al, 41h ; 'A'
0x180011660  inc     rcx
0x180011663  cmp     al, 3Ah ; ':'
0x180011665  jnz     short loc_18001166A
0x180011667  mov     r8, rcx
0x18001166a  mov     al, [rcx]
0x18001166c  test    al, al
0x18001166e  jnz     short loc_180011660
0x180011670  mov     edx, 65h ; 'e'
0x180011675  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x18001167a  mov     al, 1
0x18001167c  jmp     loc_180011752
0x180011681  mov     [rsp+48h+arg_8], 0
0x18001168a  lea     r9, [rsp+48h+arg_8]
0x18001168f  lea     r8, aAomdselfthrott_0; "AOMDSelfThrottleEndTime"
0x180011696  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001169d  mov     rcx, 0FFFFFFFF80000001h
0x1800116a4  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x1800116a9  lea     rcx, aShouldexitearl_1; "ShouldExitEarly_FailedToReadSelfThrottl"...
0x1800116b0  mov     [rsp+48h+var_18], rcx
0x1800116b5  mov     [rsp+48h+var_10], 2Fh ; '/'
0x1800116be  mov     edx, eax
0x1800116c0  lea     rcx, [rsp+48h+var_18]
0x1800116c5  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x1800116ca  cmp     [rsp+48h+arg_8], 0
0x1800116d0  jz      short loc_180011750
0x1800116d2  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800116db  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800116e0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800116e6  mov     ebx, [rsp+48h+SystemTimeAsFileTime.dwHighDateTime]
0x1800116ea  shl     rbx, 20h
0x1800116ee  mov     eax, [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x1800116f2  or      rbx, rax
0x1800116f5  mov     rax, [rsp+48h+arg_8]
0x1800116fa  mov     dword ptr [rsp+48h+arg_10], eax
0x1800116fe  shr     rax, 20h
0x180011702  mov     dword ptr [rsp+48h+arg_10+4], eax
0x180011706  mov     rax, [rsp+48h+arg_10]
0x18001170b  mov     [rsp+48h+arg_10], rax
0x180011710  lea     r8, [rsp+48h+arg_10]
0x180011715  lea     rdx, [rsp+48h+SystemTimeAsFileTime]
0x18001171a  call    ??$LogInfoFiletime@AEAY0CE@$$CBGAEAU_FILETIME@@U1@@TlgHelper@@SAXAEAY0CE@$$CBGAEAU_FILETIME@@$$QEAU1@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[36],_FILETIME &,_FILETIME>(ushort const (&)[36],_FILETIME &,_FILETIME &&)
0x18001171f  cmp     rbx, [rsp+48h+arg_8]
0x180011724  jnb     short loc_180011750
0x180011726  lea     rcx, aAomdusagetipte_0; "AOMDUsageTipTestCompletionReason::SelfT"...
0x18001172d  mov     r8, rcx
0x180011730  mov     al, 41h ; 'A'
0x180011732  inc     rcx
0x180011735  cmp     al, 3Ah ; ':'
0x180011737  jnz     short loc_18001173C
0x180011739  mov     r8, rcx
0x18001173c  mov     al, [rcx]
0x18001173e  test    al, al
0x180011740  jnz     short loc_180011732
0x180011742  mov     edx, 66h ; 'f'
0x180011747  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x18001174c  mov     al, 1
0x18001174e  jmp     short loc_180011752
0x180011750  xor     al, al
0x180011752  add     rsp, 40h
0x180011756  pop     rbx
0x180011757  retn
```
