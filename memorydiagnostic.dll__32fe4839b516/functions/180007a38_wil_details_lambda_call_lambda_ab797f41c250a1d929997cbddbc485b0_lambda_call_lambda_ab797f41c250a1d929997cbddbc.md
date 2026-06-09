# wil::details::lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___::_lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___

- ea: `0x180007a38`
- end: `0x180007ab3`
- name: `wil::details::lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___::_lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800121a0`
- `0x180022aa0`

## callees

- `0x180007a38`
- `0x1800156b4`
- `0x1800162e8`
- `0x1800165dc`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180007a8d`
- `KERNEL32!SetEvent` at `0x180007a8d`

## string_xrefs

- `0x180007a5b`: `AOMDPromptResult::MainToastCreateFailed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___::_lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___(
        __int64 a1)
{
  const char *v1; // rcx
  const char *v2; // r8
  char v3; // r9
  const char *v4; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    AOMDHandler::UnsubscribeFromToastEventCallbacks(*(AOMDHandler **)a1);
    _InterlockedExchange(&g_aomdPromptResult, 2);
    v1 = "AOMDPromptResult::MainToastCreateFailed";
    v2 = "AOMDPromptResult::MainToastCreateFailed";
    v3 = 65;
    do
    {
      v4 = ++v1;
      if ( v3 != 58 )
        v4 = v2;
      v2 = v4;
      v3 = *v1;
    }
    while ( *v1 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v1,
      2,
      v4);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v5, v6);
  }
}

```

## disassembly

```asm
0x180007a38  sub     rsp, 28h
0x180007a3c  cmp     byte ptr [rcx+8], 0
0x180007a40  jz      short loc_180007AA2
0x180007a42  mov     byte ptr [rcx+8], 0
0x180007a46  mov     rcx, [rcx]; this
0x180007a49  call    ?UnsubscribeFromToastEventCallbacks@AOMDHandler@@AEAAXXZ; AOMDHandler::UnsubscribeFromToastEventCallbacks(void)
0x180007a4e  mov     edx, 2
0x180007a53  mov     eax, edx
0x180007a55  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180007a5b  lea     rcx, aAomdpromptresu_2; "AOMDPromptResult::MainToastCreateFailed"
0x180007a62  mov     r8, rcx
0x180007a65  mov     r9b, 41h ; 'A'
0x180007a68  inc     rcx
0x180007a6b  mov     rax, rcx
0x180007a6e  cmp     r9b, 3Ah ; ':'
0x180007a72  cmovnz  rax, r8
0x180007a76  mov     r8, rax
0x180007a79  mov     r9b, [rcx]
0x180007a7c  test    r9b, r9b
0x180007a7f  jnz     short loc_180007A68
0x180007a81  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180007a86  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180007a8d  call    cs:__imp_SetEvent
0x180007a94  nop     dword ptr [rax+rax+00h]
0x180007a99  mov     rcx, [rsp+28h]; this
0x180007a9e  test    eax, eax
0x180007aa0  jz      short loc_180007AA8
0x180007aa2  add     rsp, 28h
0x180007aa6  retn
0x180007aa8  mov     edx, 9D3h; void *
0x180007aad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
