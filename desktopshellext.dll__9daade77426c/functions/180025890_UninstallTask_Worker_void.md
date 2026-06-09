# UninstallTask::Worker(void)

- ea: `0x180025890`
- end: `0x1800259e5`
- name: `?Worker@UninstallTask@@EEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(UninstallTask *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001612c`
- `0x180023e40`
- `0x180025890`
- `0x1800259ec`
- `0x18002661c`
- `0x180026ae4`
- `0x180026b20`
- `0x180026bcc`
- `0x180026c04`
- `0x18003b568`
- `0x18003b5c4`
- `0x18003c0c4`
- `0x18003c62c`
- `0x18003c960`
- `0x18003d128`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800258df`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800258df`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800258d2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800258d2`

## string_xrefs

- `0x1800259d3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180025915`: `OneCopilotRemediationReason::uninstall_task_triggered`
- `0x18002595a`: `OneCopilotRemediationReason::uninstallation_completed`
- `0x180025984`: `OneCopilotRemediationReason::failed_uninstall`

## pseudocode

```c
__int64 __fastcall UninstallTask::Worker(UninstallTask *this, const unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  int CurrentProcessExecutionOptionNoThrow; // eax
  int v6; // ebx
  _QWORD *v7; // rax
  char *v8; // rdi
  const char *v9; // rdx
  const char *v10; // rax
  _QWORD *v11; // r9
  OneCopilot *v12; // rcx
  unsigned int v13; // ebx
  const char *v14; // rdx
  const char *v15; // rax
  _QWORD *v16; // r9
  const char *v17; // rax
  _QWORD *v18; // r9
  UninstallTask *v19; // rcx
  int v21; // [rsp+20h] [rbp-8h]
  wil::details *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v23; // [rsp+38h] [rbp+10h] BYREF

  while ( 1 )
  {
    LODWORD(v23) = 1;
    CurrentProcessExecutionOptionNoThrow = wil::details::GetCurrentProcessExecutionOptionNoThrow(
                                             this,
                                             a2,
                                             (unsigned int)&v23,
                                             a4);
    if ( CurrentProcessExecutionOptionNoThrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)CurrentProcessExecutionOptionNoThrow,
        v21);
    v6 = v23;
    if ( !(_DWORD)v23 )
      break;
    if ( wil::details::IsDebuggerPresent(retaddr) )
    {
      if ( v6 == 2 )
        DebugBreak();
      break;
    }
    Sleep(0x1F4u);
  }
  v7 = tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>>(&v23);
  v8 = (char *)this + 56;
  wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::operator=(
    v8,
    v7);
  wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v23);
  tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
    v8,
    &v23);
  v10 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::uninstall_task_triggered", v9);
  tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(*v11 + 8LL, 12, v10);
  tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(&v23);
  v13 = OneCopilot::TryUninstallMAI(v12);
  tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
    v8,
    &v23);
  if ( (v13 & 0x80000000) != 0 )
  {
    v17 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::failed_uninstall", v14);
    tip2::details::shared_data<1,0,1>::set_flag_value<long>(*v18 + 8LL, 1, v17, v13);
  }
  else
  {
    v15 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::uninstallation_completed", v14);
    tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(*v16 + 8LL, 13, v15);
  }
  tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(&v23);
  tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::complete(v8);
  UninstallTask::StoreUninstallResultInRegistry(v19, v13);
  return v13;
}

```

## disassembly

```asm
0x180025890  mov     [rsp+arg_0], rbx
0x180025895  push    rdi; int
0x180025896  sub     rsp, 20h
0x18002589a  mov     rdi, rcx
0x18002589d  lea     r8, [rsp+28h+arg_8]; unsigned int
0x1800258a2  mov     dword ptr [rsp+28h+arg_8], 1
0x1800258aa  call    ?GetCurrentProcessExecutionOptionNoThrow@details@wil@@YAJPEBGKPEAK@Z; wil::details::GetCurrentProcessExecutionOptionNoThrow(ushort const *,ulong,ulong *)
0x1800258af  mov     rcx, [rsp+28h]; this
0x1800258b4  test    eax, eax
0x1800258b6  js      loc_1800259D0
0x1800258bc  mov     ebx, dword ptr [rsp+28h+arg_8]
0x1800258c0  test    ebx, ebx
0x1800258c2  jz      short loc_1800258E5
0x1800258c4  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x1800258c9  test    al, al
0x1800258cb  jnz     short loc_1800258DA
0x1800258cd  mov     ecx, 1F4h; dwMilliseconds
0x1800258d2  call    cs:__imp_Sleep
0x1800258d8  jmp     short loc_18002589D
0x1800258da  cmp     ebx, 2
0x1800258dd  jnz     short loc_1800258E5
0x1800258df  call    cs:__imp_DebugBreak
0x1800258e5  lea     rcx, [rsp+28h+arg_8]
0x1800258ea  call    ??$open@V?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>>(void)
0x1800258ef  add     rdi, 38h ; '8'
0x1800258f3  mov     rdx, rax
0x1800258f6  mov     rcx, rdi
0x1800258f9  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy> &&)
0x1800258fe  lea     rcx, [rsp+28h+arg_8]
0x180025903  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x180025908  lea     rdx, [rsp+28h+arg_8]
0x18002590d  mov     rcx, rdi
0x180025910  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180025915  lea     rcx, aOnecopilotreme_11; "OneCopilotRemediationReason::uninstall_"...
0x18002591c  mov     r9, rax
0x18002591f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180025924  mov     rcx, [r9]
0x180025927  mov     r8, rax
0x18002592a  add     rcx, 8
0x18002592e  mov     edx, 0Ch
0x180025933  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(ushort,char const *)
0x180025938  lea     rcx, [rsp+28h+arg_8]
0x18002593d  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x180025942  call    ?TryUninstallMAI@OneCopilot@@YAJXZ; OneCopilot::TryUninstallMAI(void)
0x180025947  lea     rdx, [rsp+28h+arg_8]
0x18002594c  mov     ebx, eax
0x18002594e  mov     rcx, rdi
0x180025951  test    eax, eax
0x180025953  js      short loc_18002597F
0x180025955  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x18002595a  lea     rcx, aOnecopilotreme_1; "OneCopilotRemediationReason::uninstalla"...
0x180025961  mov     r9, rax
0x180025964  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180025969  mov     rcx, [r9]
0x18002596c  mov     r8, rax
0x18002596f  add     rcx, 8
0x180025973  mov     edx, 0Dh
0x180025978  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(ushort,char const *)
0x18002597d  jmp     short loc_1800259AA
0x18002597f  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180025984  lea     rcx, aOnecopilotreme_10; "OneCopilotRemediationReason::failed_uni"...
0x18002598b  mov     r9, rax
0x18002598e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180025993  mov     rcx, [r9]
0x180025996  mov     r8, rax
0x180025999  add     rcx, 8
0x18002599d  mov     edx, 1
0x1800259a2  mov     r9d, ebx
0x1800259a5  call    ??$set_flag_value@J@?$shared_data@$00$0A@$00@details@tip2@@QEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,1>::set_flag_value<long>(ushort,char const *,long)
0x1800259aa  lea     rcx, [rsp+28h+arg_8]
0x1800259af  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x1800259b4  mov     rcx, rdi
0x1800259b7  call    ?complete@?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::complete(void)
0x1800259bc  mov     edx, ebx; int
0x1800259be  call    ?StoreUninstallResultInRegistry@UninstallTask@@AEAAXJ@Z; UninstallTask::StoreUninstallResultInRegistry(long)
0x1800259c3  mov     eax, ebx
0x1800259c5  mov     rbx, [rsp+28h+arg_0]
0x1800259ca  add     rsp, 20h
0x1800259ce  pop     rdi
0x1800259cf  retn
0x1800259d0  mov     r9d, eax; char *
0x1800259d3  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800259da  mov     edx, 1CBEh; void *
0x1800259df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
