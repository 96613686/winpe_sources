# wil::details::lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___::_lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___

- ea: `0x180007aa0`
- end: `0x180007b0a`
- name: `wil::details::lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___::_lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___`
- size: `106`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011760`
- `0x18002116a`

## callees

- `0x180007aa0`
- `0x18001488c`
- `0x180015604`
- `0x1800158a0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180007aeb`
- `KERNEL32!SetEvent` at `0x180007aeb`

## string_xrefs

- `0x180007ac3`: `AOMDPromptResult::MainToastCreateFailed`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___::_lambda_call__lambda_ab797f41c250a1d929997cbddbc485b0___(
        __int64 a1)
{
  const char *v1; // rcx
  const char *v2; // r8
  char v3; // al
  __int64 v4; // r8
  const char *v5; // r9
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
      ++v1;
      if ( v3 == 58 )
        v2 = v1;
      v3 = *v1;
    }
    while ( *v1 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      (__int64)v1,
      2,
      (__int64)v2);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v4, v5);
  }
}

```

## disassembly

```asm
0x180007aa0  sub     rsp, 28h
0x180007aa4  cmp     byte ptr [rcx+8], 0
0x180007aa8  jz      short loc_180007AFA
0x180007aaa  mov     byte ptr [rcx+8], 0
0x180007aae  mov     rcx, [rcx]; this
0x180007ab1  call    ?UnsubscribeFromToastEventCallbacks@AOMDHandler@@AEAAXXZ; AOMDHandler::UnsubscribeFromToastEventCallbacks(void)
0x180007ab6  mov     edx, 2
0x180007abb  mov     eax, edx
0x180007abd  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180007ac3  lea     rcx, aAomdpromptresu_3; "AOMDPromptResult::MainToastCreateFailed"
0x180007aca  mov     r8, rcx
0x180007acd  mov     al, 41h ; 'A'
0x180007acf  inc     rcx
0x180007ad2  cmp     al, 3Ah ; ':'
0x180007ad4  jnz     short loc_180007AD9
0x180007ad6  mov     r8, rcx
0x180007ad9  mov     al, [rcx]
0x180007adb  test    al, al
0x180007add  jnz     short loc_180007ACF
0x180007adf  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180007ae4  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180007aeb  call    cs:__imp_SetEvent
0x180007af1  mov     rcx, [rsp+28h]; this
0x180007af6  test    eax, eax
0x180007af8  jz      short loc_180007AFF
0x180007afa  add     rsp, 28h
0x180007afe  retn
0x180007aff  mov     edx, 0A01h; void *
0x180007b04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
