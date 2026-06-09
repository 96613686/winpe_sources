# AOMDHandler::Stop(long *)

- ea: `0x1800132f0`
- end: `0x1800133e4`
- name: `?Stop@AOMDHandler@@MEAAJPEAJ@Z`
- size: `244`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800044e8`
- `0x18000e7ec`
- `0x1800132f0`
- `0x180015604`
- `0x1800158a0`
- `0x180023010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800133a1`
- `KERNEL32!SetEvent` at `0x1800133a1`

## string_xrefs

- `0x180013330`: `Stop_StoppingTask`
- `0x180013361`: `AOMDPromptResult::TaskStop`

## pseudocode

```c
__int64 __fastcall AOMDHandler::Stop(AOMDHandler *this, int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  signed __int32 v8; // eax
  const char *v9; // rax
  const char *v10; // r8
  __int64 v12; // r8
  const char *v13; // r9
  __int64 result; // rax
  const char *v15; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const wchar_t *v17; // [rsp+50h] [rbp+18h] BYREF

  v4 = TlgHelper::Provider();
  if ( *(_DWORD *)v4 > 4u )
  {
    v6 = *((_QWORD *)v4 + 3);
    v7 = *((_QWORD *)v4 + 2);
    if ( (v7 & 1) != 0 )
    {
      v5 = *((_QWORD *)v4 + 3) & 1LL;
      if ( v5 == *((_QWORD *)v4 + 3) )
      {
        v17 = L"Stop_StoppingTask";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v4,
          (__int64)byte_180029F11,
          v7,
          v6,
          (int **)&v17);
      }
    }
  }
  v8 = _InterlockedCompareExchange(&g_aomdPromptResult, 1, 0);
  if ( v8 )
  {
    LODWORD(v17) = v8;
    TlgHelper::LogInfo<unsigned short const (&)[34],unsigned int>(v5, &v17);
  }
  else
  {
    v9 = "AOMDPromptResult::TaskStop";
    v10 = "AOMDPromptResult::TaskStop";
    LOBYTE(v5) = 65;
    do
    {
      ++v9;
      if ( (_BYTE)v5 == 58 )
        v10 = v9;
      LOBYTE(v5) = *v9;
    }
    while ( *v9 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v5,
      1,
      (__int64)v10);
  }
  if ( g_exitEvent )
  {
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v12, v13);
  }
  try
  {
    result = (*(__int64 (__fastcall **)(AOMDHandler *, int *))(*(_QWORD *)this + 80LL))(this, a2);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBB,
                           (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800132f0  mov     [rsp+arg_0], rbx
0x1800132f5  mov     [rsp+arg_8], rsi
0x1800132fa  push    rdi
0x1800132fb  sub     rsp, 30h
0x1800132ff  mov     rsi, rdx
0x180013302  mov     rdi, rcx
0x180013305  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001330a  mov     r8d, [rax]
0x18001330d  mov     ebx, 1
0x180013312  cmp     r8d, 4
0x180013316  jbe     short loc_180013355
0x180013318  mov     r9, [rax+18h]
0x18001331c  mov     r8, [rax+10h]
0x180013320  test    bl, r8b
0x180013323  jz      short loc_180013355
0x180013325  mov     rcx, r9
0x180013328  and     rcx, rbx
0x18001332b  cmp     rcx, r9
0x18001332e  jnz     short loc_180013355
0x180013330  lea     rcx, aStopStoppingta; "Stop_StoppingTask"
0x180013337  mov     [rsp+38h+arg_10], rcx
0x18001333c  lea     rcx, [rsp+38h+arg_10]
0x180013341  mov     [rsp+38h+var_18], rcx
0x180013346  lea     rdx, byte_180029F11
0x18001334d  mov     rcx, rax
0x180013350  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180013355  xor     eax, eax
0x180013357  lock cmpxchg cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A, ebx; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x18001335f  jnz     short loc_180013387
0x180013361  lea     rax, aAomdpromptresu_10; "AOMDPromptResult::TaskStop"
0x180013368  mov     r8, rax
0x18001336b  mov     cl, 41h ; 'A'
0x18001336d  add     rax, rbx
0x180013370  cmp     cl, 3Ah ; ':'
0x180013373  jnz     short loc_180013378
0x180013375  mov     r8, rax
0x180013378  mov     cl, [rax]
0x18001337a  test    cl, cl
0x18001337c  jnz     short loc_18001336D
0x18001337e  mov     edx, ebx
0x180013380  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180013385  jmp     short loc_180013395
0x180013387  mov     dword ptr [rsp+38h+arg_10], eax
0x18001338b  lea     rdx, [rsp+38h+arg_10]
0x180013390  call    ??$LogInfo@AEAY0CC@$$CBGI@TlgHelper@@SAXAEAY0CC@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[34],uint>(ushort const (&)[34],uint &&)
0x180013395  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x18001339c  test    rcx, rcx
0x18001339f  jz      short loc_1800133B0
0x1800133a1  call    cs:__imp_SetEvent
0x1800133a7  mov     rcx, [rsp+38h]; this
0x1800133ac  test    eax, eax
0x1800133ae  jz      short loc_1800133D8
0x1800133b0  mov     rax, [rdi]
0x1800133b3  mov     rdx, rsi
0x1800133b6  mov     rcx, rdi
0x1800133b9  mov     rax, [rax+50h]
0x1800133bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c2  jmp     short loc_1800133C8
0x1800133c4  mov     eax, dword ptr [rsp+38h+arg_10]
0x1800133c8  mov     rbx, [rsp+38h+arg_0]
0x1800133cd  mov     rsi, [rsp+38h+arg_8]
0x1800133d2  add     rsp, 30h
0x1800133d6  pop     rdi
0x1800133d7  retn
0x1800133d8  mov     edx, 0A01h; void *
0x1800133dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
