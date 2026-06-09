# AOMDHandler::ShouldExitEarly(void)

- ea: `0x180012024`
- end: `0x180012199`
- name: `?ShouldExitEarly@AOMDHandler@@AEAA_NXZ`
- size: `373`
- prototype: `bool __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a7e4`

## callees

- `0x180001008`
- `0x180003fbc`
- `0x1800062b4`
- `0x18000e964`
- `0x18000f144`
- `0x180012024`
- `0x1800165dc`
- `0x180021954`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180012114`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180012114`

## string_xrefs

- `0x180012079`: `AOMDUsageTipTestCompletionReason::AdminProtectionDetected`
- `0x1800120d1`: `ShouldExitEarly_FailedToReadSelfThrottleEndTime`
- `0x180012160`: `AOMDUsageTipTestCompletionReason::SelfThrottleActive`

## pseudocode

```c
char __fastcall AOMDHandler::ShouldExitEarly(AOMDHandler *this)
{
  int v1; // eax
  const char *v2; // r9
  const struct _tlgProvider_t *v3; // rax
  int v4; // r8d
  int v5; // r9d
  const char *v6; // rax
  const char *v7; // r8
  char v8; // dl
  const char *v9; // rcx
  unsigned int value_qword; // eax
  struct _FILETIME v12; // rbx
  __int64 v13; // rcx
  const char *v14; // rcx
  const char *v15; // r8
  char v16; // dl
  const char *v17; // rax
  _QWORD v18[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 v22; // [rsp+60h] [rbp+18h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)this;
  try
  {
    v1 = LUAIsShadowAdminEnabled();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6AF,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      v2);
    return 0;
  }
  if ( v1 )
  {
    v3 = TlgHelper::Provider();
    if ( *(_DWORD *)v3 > 4u && (*((_BYTE *)v3 + 16) & 2) != 0 && (*((_QWORD *)v3 + 3) & 2LL) == *((_QWORD *)v3 + 3) )
    {
      SystemTimeAsFileTime = (struct _FILETIME)L"ShouldExitEarly_ShadowAdminEnabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v3,
        (unsigned int)&unk_18002AB01,
        v4,
        v5,
        (__int64)&SystemTimeAsFileTime);
    }
    v6 = "AOMDUsageTipTestCompletionReason::AdminProtectionDetected";
    v7 = "AOMDUsageTipTestCompletionReason::AdminProtectionDetected";
    v8 = 65;
    do
    {
      v9 = ++v6;
      if ( v8 != 58 )
        v9 = v7;
      v7 = v9;
      v8 = *v6;
    }
    while ( *v6 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v9,
      101,
      v9);
    return 1;
  }
  else
  {
    v21 = 0;
    value_qword = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
                    -2147483647,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
                    L"AOMDSelfThrottleEndTime",
                    &v21);
    v18[0] = L"ShouldExitEarly_FailedToReadSelfThrottleEndTime";
    v18[1] = 47;
    TlgHelper::LogIfFailedExpected(v18, value_qword);
    if ( v21
      && (SystemTimeAsFileTime = 0,
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
          v12 = SystemTimeAsFileTime,
          v22 = v21,
          TlgHelper::LogInfoFiletime<unsigned short const (&)[36],_FILETIME &,_FILETIME>(
            v13,
            &SystemTimeAsFileTime,
            &v22),
          *(_QWORD *)&v12 < v21) )
    {
      v14 = "AOMDUsageTipTestCompletionReason::SelfThrottleActive";
      v15 = "AOMDUsageTipTestCompletionReason::SelfThrottleActive";
      v16 = 65;
      do
      {
        v17 = ++v14;
        if ( v16 != 58 )
          v17 = v15;
        v15 = v17;
        v16 = *v14;
      }
      while ( *v14 );
      tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
        v14,
        102,
        v17);
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
0x180012024  mov     qword ptr [rsp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180012029  push    rbx
0x18001202a  sub     rsp, 40h
0x18001202e  call    LUAIsShadowAdminEnabled
0x180012033  test    eax, eax
0x180012035  jz      short loc_1800120AC
0x180012037  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001203c  cmp     dword ptr [rax], 4
0x18001203f  jbe     short loc_180012079
0x180012041  test    byte ptr [rax+10h], 2
0x180012045  jz      short loc_180012079
0x180012047  mov     rcx, [rax+18h]
0x18001204b  and     ecx, 2
0x18001204e  cmp     rcx, [rax+18h]
0x180012052  jnz     short loc_180012079
0x180012054  lea     rcx, aShouldexitearl; "ShouldExitEarly_ShadowAdminEnabled"
0x18001205b  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180012060  lea     rcx, [rsp+48h+SystemTimeAsFileTime]
0x180012065  mov     [rsp+48h+var_28], rcx
0x18001206a  lea     rdx, byte_18002AB01
0x180012071  mov     rcx, rax
0x180012074  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180012079  lea     rax, aAomdusagetipte_2; "AOMDUsageTipTestCompletionReason::Admin"...
0x180012080  mov     r8, rax
0x180012083  mov     dl, 41h ; 'A'
0x180012085  inc     rax
0x180012088  mov     rcx, rax
0x18001208b  cmp     dl, 3Ah ; ':'
0x18001208e  cmovnz  rcx, r8
0x180012092  mov     r8, rcx
0x180012095  mov     dl, [rax]
0x180012097  test    dl, dl
0x180012099  jnz     short loc_180012085
0x18001209b  mov     edx, 65h ; 'e'
0x1800120a0  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x1800120a5  mov     al, 1
0x1800120a7  jmp     loc_180012192
0x1800120ac  and     [rsp+48h+arg_8], 0
0x1800120b2  lea     r9, [rsp+48h+arg_8]
0x1800120b7  lea     r8, aAomdselfthrott_0; "AOMDSelfThrottleEndTime"
0x1800120be  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800120c5  mov     rcx, 0FFFFFFFF80000001h
0x1800120cc  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x1800120d1  lea     rcx, aShouldexitearl_1; "ShouldExitEarly_FailedToReadSelfThrottl"...
0x1800120d8  mov     [rsp+48h+var_18], rcx
0x1800120dd  mov     [rsp+48h+var_18+8], 2Fh ; '/'
0x1800120e6  movaps  xmm0, xmmword ptr [rsp+48h+var_18]
0x1800120eb  movdqa  xmmword ptr [rsp+48h+var_18], xmm0
0x1800120f1  mov     edx, eax
0x1800120f3  lea     rcx, [rsp+48h+var_18]
0x1800120f8  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x1800120fd  cmp     [rsp+48h+arg_8], 0
0x180012103  jz      loc_180012190
0x180012109  and     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001210f  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012114  call    cs:__imp_GetSystemTimeAsFileTime
0x18001211b  nop     dword ptr [rax+rax+00h]
0x180012120  mov     ebx, [rsp+48h+SystemTimeAsFileTime.dwHighDateTime]
0x180012124  shl     rbx, 20h
0x180012128  mov     eax, [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18001212c  or      rbx, rax
0x18001212f  mov     rax, [rsp+48h+arg_8]
0x180012134  mov     dword ptr [rsp+48h+arg_10], eax
0x180012138  shr     rax, 20h
0x18001213c  mov     dword ptr [rsp+48h+arg_10+4], eax
0x180012140  mov     rax, [rsp+48h+arg_10]
0x180012145  mov     [rsp+48h+arg_10], rax
0x18001214a  lea     r8, [rsp+48h+arg_10]
0x18001214f  lea     rdx, [rsp+48h+SystemTimeAsFileTime]
0x180012154  call    ??$LogInfoFiletime@AEAY0CE@$$CBGAEAU_FILETIME@@U1@@TlgHelper@@SAXAEAY0CE@$$CBGAEAU_FILETIME@@$$QEAU1@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[36],_FILETIME &,_FILETIME>(ushort const (&)[36],_FILETIME &,_FILETIME &&)
0x180012159  cmp     rbx, [rsp+48h+arg_8]
0x18001215e  jnb     short loc_180012190
0x180012160  lea     rcx, aAomdusagetipte_0; "AOMDUsageTipTestCompletionReason::SelfT"...
0x180012167  mov     r8, rcx
0x18001216a  mov     dl, 41h ; 'A'
0x18001216c  inc     rcx
0x18001216f  mov     rax, rcx
0x180012172  cmp     dl, 3Ah ; ':'
0x180012175  cmovnz  rax, r8
0x180012179  mov     r8, rax
0x18001217c  mov     dl, [rcx]
0x18001217e  test    dl, dl
0x180012180  jnz     short loc_18001216C
0x180012182  mov     edx, 66h ; 'f'
0x180012187  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x18001218c  mov     al, 1
0x18001218e  jmp     short loc_180012192
0x180012190  xor     al, al
0x180012192  add     rsp, 40h
0x180012196  pop     rbx
0x180012197  retn
```
