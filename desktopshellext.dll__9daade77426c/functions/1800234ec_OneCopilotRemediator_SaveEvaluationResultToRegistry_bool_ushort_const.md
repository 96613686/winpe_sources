# OneCopilotRemediator::SaveEvaluationResultToRegistry(bool,ushort const *)

- ea: `0x1800234ec`
- end: `0x180023662`
- name: `?SaveEvaluationResultToRegistry@OneCopilotRemediator@@AEAAJ_NPEBG@Z`
- size: `374`
- prototype: `int(OneCopilotRemediator *__hidden this, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18002663c`

## callees

- `0x180017988`
- `0x1800234ec`
- `0x180023668`
- `0x180026ae4`
- `0x180026bcc`
- `0x180026c04`
- `0x18003b60c`
- `0x18003d128`
- `0x180051d40`
- `0x180053798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002359b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800235e3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002359b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800235e3`
- `msvcp_win!_Xtime_get_ticks` at `0x180023501`
- `msvcp_win!_Xtime_get_ticks` at `0x180023501`

## string_xrefs

- `0x180023626`: `OneCopilotRemediationReason::write_criteria_to_registry`

## pseudocode

```c
__int64 __fastcall OneCopilotRemediator::SaveEvaluationResultToRegistry(
        HKEY *this,
        unsigned __int8 a2,
        wil::reg::reg_view_details::reg_value_type_info *a3)
{
  int v4; // ebx
  __int64 ticks; // rbp
  HKEY v7; // rcx
  signed int v8; // ebx
  __int64 v9; // rdx
  HKEY v11; // rcx
  LSTATUS v12; // eax
  const unsigned __int16 *v13; // rdx
  DWORD cbData; // eax
  LSTATUS v15; // eax
  HKEY v16; // rcx
  const char *v17; // rdx
  const char *v18; // rax
  _QWORD *v19; // r9
  int lpData; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 Data; // [rsp+50h] [rbp+8h] BYREF
  int v23; // [rsp+58h] [rbp+10h] BYREF

  v4 = a2;
  ticks = _Xtime_get_ticks();
  OneCopilotRemediator::EnsureCopilotRegistryKeyCreated((OneCopilotRemediator *)this);
  v7 = this[5];
  v23 = v4;
  v8 = wil::reg::set_value_nothrow<unsigned int>(v7, 0, L"RemediationNecessary", &v23);
  if ( v8 < 0 )
  {
    v9 = 539;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
      (const char *)(unsigned int)v8,
      lpData);
    return (unsigned int)v8;
  }
  v11 = this[5];
  Data = ticks / 10000000;
  v12 = RegSetKeyValueW(v11, 0, L"EvaluationTimestamp", 0xBu, &Data, 8u);
  v8 = v12;
  if ( v12 > 0 )
    v8 = (unsigned __int16)v12 | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 540;
    goto LABEL_3;
  }
  cbData = wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(a3, v13);
  v15 = RegSetKeyValueW(this[5], 0, L"Criteria", 1u, a3, cbData);
  v8 = v15;
  if ( v15 > 0 )
    v8 = (unsigned __int16)v15 | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 541;
    goto LABEL_3;
  }
  v16 = this[10];
  if ( v16 )
  {
    if ( (unsigned __int8)tip2::details::shared_data<1,0,1>::is_running(v16 + 2) )
    {
      tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
        this + 10,
        &Data);
      v18 = tip2::details::reason_string(
              (tip2::details *)"OneCopilotRemediationReason::write_criteria_to_registry",
              v17);
      tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(*v19 + 8LL, 10, v18);
      tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(&Data);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800234ec  mov     [rsp+arg_10], rbx
0x1800234f1  push    rbp
0x1800234f2  push    rsi
0x1800234f3  push    rdi
0x1800234f4  sub     rsp, 30h
0x1800234f8  mov     rsi, r8
0x1800234fb  movzx   ebx, dl
0x1800234fe  mov     rdi, rcx
0x180023501  call    cs:__imp__Xtime_get_ticks
0x180023507  mov     rcx, rdi; this
0x18002350a  mov     rbp, rax
0x18002350d  call    ?EnsureCopilotRegistryKeyCreated@OneCopilotRemediator@@AEAAXXZ; OneCopilotRemediator::EnsureCopilotRegistryKeyCreated(void)
0x180023512  mov     rcx, [rdi+28h]
0x180023516  lea     r9, [rsp+48h+arg_8]
0x18002351b  lea     r8, aRemediationnec; "RemediationNecessary"
0x180023522  mov     [rsp+48h+arg_8], ebx
0x180023526  xor     edx, edx
0x180023528  call    ??$set_value_nothrow@I@reg@wil@@YAJPEAUHKEY__@@PEBG1AEBI@Z; wil::reg::set_value_nothrow<uint>(HKEY__ *,ushort const *,ushort const *,uint const &)
0x18002352d  mov     ebx, eax
0x18002352f  test    eax, eax
0x180023531  jns     short loc_180023553
0x180023533  mov     edx, 21Bh; void *
0x180023538  mov     rcx, [rsp+48h]; this
0x18002353d  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180023544  mov     r9d, ebx; char *
0x180023547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002354c  mov     eax, ebx
0x18002354e  jmp     loc_180023655
0x180023553  mov     rcx, [rdi+28h]; hKey
0x180023557  lea     r8, aEvaluationtime; "EvaluationTimestamp"
0x18002355e  mov     rax, 0D6BF94D5E57A42BDh
0x180023568  mov     [rsp+48h+cbData], 8; cbData
0x180023570  imul    rbp
0x180023573  mov     r9d, 0Bh; dwType
0x180023579  add     rdx, rbp
0x18002357c  sar     rdx, 17h
0x180023580  mov     rax, rdx
0x180023583  shr     rax, 3Fh
0x180023587  add     rdx, rax
0x18002358a  lea     rax, [rsp+48h+Data]
0x18002358f  mov     [rsp+48h+Data], rdx
0x180023594  xor     edx, edx; lpSubKey
0x180023596  mov     [rsp+48h+lpData], rax; lpData
0x18002359b  call    cs:__imp_RegSetKeyValueW
0x1800235a1  mov     ebx, eax
0x1800235a3  mov     ebp, 80070000h
0x1800235a8  test    eax, eax
0x1800235aa  jle     short loc_1800235B1
0x1800235ac  movzx   ebx, ax
0x1800235af  or      ebx, ebp
0x1800235b1  test    ebx, ebx
0x1800235b3  jns     short loc_1800235BF
0x1800235b5  mov     edx, 21Ch
0x1800235ba  jmp     loc_180023538
0x1800235bf  mov     rcx, rsi; this
0x1800235c2  call    ?get_buffer_size_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAKPEBG@Z; wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(ushort const *)
0x1800235c7  mov     rcx, [rdi+28h]; hKey
0x1800235cb  lea     r8, aCriteria; "Criteria"
0x1800235d2  mov     [rsp+48h+cbData], eax; cbData
0x1800235d6  xor     edx, edx; lpSubKey
0x1800235d8  mov     r9d, 1; dwType
0x1800235de  mov     [rsp+48h+lpData], rsi; lpData
0x1800235e3  call    cs:__imp_RegSetKeyValueW
0x1800235e9  mov     ebx, eax
0x1800235eb  test    eax, eax
0x1800235ed  jle     short loc_1800235F4
0x1800235ef  movzx   ebx, ax
0x1800235f2  or      ebx, ebp
0x1800235f4  test    ebx, ebx
0x1800235f6  jns     short loc_180023602
0x1800235f8  mov     edx, 21Dh
0x1800235fd  jmp     loc_180023538
0x180023602  mov     rcx, [rdi+50h]
0x180023606  test    rcx, rcx
0x180023609  jz      short loc_180023653
0x18002360b  add     rcx, 8
0x18002360f  call    ?is_running@?$shared_data@$00$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,1>::is_running(void)
0x180023614  test    al, al
0x180023616  jz      short loc_180023653
0x180023618  lea     rdx, [rsp+48h+Data]
0x18002361d  lea     rcx, [rdi+50h]
0x180023621  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180023626  lea     rcx, aOnecopilotreme_8; "OneCopilotRemediationReason::write_crit"...
0x18002362d  mov     r9, rax
0x180023630  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180023635  mov     rcx, [r9]
0x180023638  mov     r8, rax
0x18002363b  add     rcx, 8
0x18002363f  mov     edx, 0Ah
0x180023644  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(ushort,char const *)
0x180023649  lea     rcx, [rsp+48h+Data]
0x18002364e  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x180023653  xor     eax, eax
0x180023655  mov     rbx, [rsp+48h+arg_10]
0x18002365a  add     rsp, 30h
0x18002365e  pop     rdi
0x18002365f  pop     rsi
0x180023660  pop     rbp
0x180023661  retn
```
