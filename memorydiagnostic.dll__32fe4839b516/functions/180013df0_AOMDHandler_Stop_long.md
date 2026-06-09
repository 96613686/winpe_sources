# AOMDHandler::Stop(long *)

- ea: `0x180013df0`
- end: `0x180013f26`
- name: `?Stop@AOMDHandler@@MEAAJPEAJ@Z`
- size: `310`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001178`
- `0x18000f144`
- `0x180013df0`
- `0x1800162e8`
- `0x1800165dc`
- `0x180024010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180013ede`
- `KERNEL32!SetEvent` at `0x180013ede`

## string_xrefs

- `0x180013e24`: `Stop_StoppingTask`
- `0x180013e57`: `AOMDPromptResult::TaskStop`
- `0x180013ea3`: `Stop_SkippedOverwritePromptResult`

## pseudocode

```c
__int64 __fastcall AOMDHandler::Stop(AOMDHandler *this, int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  int v5; // r8d
  int v6; // r9d
  signed __int32 v7; // edi
  const char *v8; // rcx
  const char *v9; // r8
  char v10; // dl
  const char *v11; // rax
  const struct _tlgProvider_t *v12; // rax
  int v13; // r8d
  int v14; // r9d
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 result; // rax
  const char *v19; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  const wchar_t *v21; // [rsp+60h] [rbp+18h] BYREF
  const wchar_t *v22; // [rsp+68h] [rbp+20h] BYREF

  v4 = TlgHelper::Provider();
  if ( *(_DWORD *)v4 > 4u && (*((_BYTE *)v4 + 16) & 1) != 0 && (*((_QWORD *)v4 + 3) & 1LL) == *((_QWORD *)v4 + 3) )
  {
    v21 = L"Stop_StoppingTask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)&unk_18002AF12,
      v5,
      v6,
      (__int64)&v21);
  }
  v7 = _InterlockedCompareExchange(&g_aomdPromptResult, 1, 0);
  if ( v7 )
  {
    v12 = TlgHelper::Provider();
    if ( *(_DWORD *)v12 > 4u && (*((_BYTE *)v12 + 16) & 2) != 0 && (*((_QWORD *)v12 + 3) & 2LL) == *((_QWORD *)v12 + 3) )
    {
      LODWORD(v21) = v7;
      v22 = L"Stop_SkippedOverwritePromptResult";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)&unk_18002AB49,
        v13,
        v14,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  else
  {
    v8 = "AOMDPromptResult::TaskStop";
    v9 = "AOMDPromptResult::TaskStop";
    v10 = 65;
    do
    {
      v11 = ++v8;
      if ( v10 != 58 )
        v11 = v9;
      v9 = v11;
      v10 = *v8;
    }
    while ( *v8 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v8,
      1,
      v11);
  }
  if ( g_exitEvent )
  {
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v16, v17);
  }
  try
  {
    result = (*(__int64 (__fastcall **)(AOMDHandler *, int *))(*(_QWORD *)this + 80LL))(this, a2);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCC,
                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180013df0  mov     [rsp+arg_0], rbx
0x180013df5  push    rsi
0x180013df6  push    rdi
0x180013df7  push    r14
0x180013df9  sub     rsp, 30h
0x180013dfd  mov     r14, rdx
0x180013e00  mov     rsi, rcx
0x180013e03  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180013e08  mov     ebx, 1
0x180013e0d  cmp     dword ptr [rax], 4
0x180013e10  jbe     short loc_180013E49
0x180013e12  test    [rax+10h], bl
0x180013e15  jz      short loc_180013E49
0x180013e17  mov     rcx, [rax+18h]
0x180013e1b  and     rcx, rbx
0x180013e1e  cmp     rcx, [rax+18h]
0x180013e22  jnz     short loc_180013E49
0x180013e24  lea     rcx, aStopStoppingta; "Stop_StoppingTask"
0x180013e2b  mov     [rsp+48h+arg_10], rcx
0x180013e30  lea     rcx, [rsp+48h+arg_10]
0x180013e35  mov     [rsp+48h+var_28], rcx
0x180013e3a  lea     rdx, byte_18002AF12
0x180013e41  mov     rcx, rax
0x180013e44  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180013e49  xor     eax, eax
0x180013e4b  lock cmpxchg cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A, ebx; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180013e53  mov     edi, eax
0x180013e55  jnz     short loc_180013E82
0x180013e57  lea     rcx, aAomdpromptresu_11; "AOMDPromptResult::TaskStop"
0x180013e5e  mov     r8, rcx
0x180013e61  mov     dl, 41h ; 'A'
0x180013e63  add     rcx, rbx
0x180013e66  mov     rax, rcx
0x180013e69  cmp     dl, 3Ah ; ':'
0x180013e6c  cmovnz  rax, r8
0x180013e70  mov     r8, rax
0x180013e73  mov     dl, [rcx]
0x180013e75  test    dl, dl
0x180013e77  jnz     short loc_180013E63
0x180013e79  mov     edx, ebx
0x180013e7b  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180013e80  jmp     short loc_180013ED2
0x180013e82  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180013e87  cmp     dword ptr [rax], 4
0x180013e8a  jbe     short loc_180013ED2
0x180013e8c  test    byte ptr [rax+10h], 2
0x180013e90  jz      short loc_180013ED2
0x180013e92  mov     rcx, [rax+18h]
0x180013e96  and     ecx, 2
0x180013e99  cmp     rcx, [rax+18h]
0x180013e9d  jnz     short loc_180013ED2
0x180013e9f  mov     dword ptr [rsp+48h+arg_10], edi
0x180013ea3  lea     rcx, aStopSkippedove; "Stop_SkippedOverwritePromptResult"
0x180013eaa  mov     [rsp+48h+arg_18], rcx
0x180013eaf  lea     rcx, [rsp+48h+arg_10]
0x180013eb4  mov     [rsp+48h+var_20], rcx
0x180013eb9  lea     rcx, [rsp+48h+arg_18]
0x180013ebe  mov     [rsp+48h+var_28], rcx
0x180013ec3  lea     rdx, unk_18002AB49
0x180013eca  mov     rcx, rax
0x180013ecd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013ed2  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180013ed9  test    rcx, rcx
0x180013edc  jz      short loc_180013EF3
0x180013ede  call    cs:__imp_SetEvent
0x180013ee5  nop     dword ptr [rax+rax+00h]
0x180013eea  mov     rcx, [rsp+48h]; this
0x180013eef  test    eax, eax
0x180013ef1  jz      short loc_180013F1A
0x180013ef3  mov     rax, [rsi]
0x180013ef6  mov     rdx, r14
0x180013ef9  mov     rcx, rsi
0x180013efc  mov     rax, [rax+50h]
0x180013f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f05  jmp     short loc_180013F0B
0x180013f07  mov     eax, dword ptr [rsp+48h+arg_10]
0x180013f0b  mov     rbx, [rsp+48h+arg_0]
0x180013f10  add     rsp, 30h
0x180013f14  pop     r14
0x180013f16  pop     rdi
0x180013f17  pop     rsi
0x180013f18  retn
0x180013f1a  mov     edx, 9D3h; void *
0x180013f1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
