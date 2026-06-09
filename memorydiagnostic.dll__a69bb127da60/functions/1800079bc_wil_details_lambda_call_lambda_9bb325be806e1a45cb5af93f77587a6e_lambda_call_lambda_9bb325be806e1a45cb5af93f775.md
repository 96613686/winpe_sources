# wil::details::lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___::_lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___

- ea: `0x1800079bc`
- end: `0x180007a97`
- name: `wil::details::lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___::_lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___`
- size: `219`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015010`
- `0x180021501`

## callees

- `0x1800079bc`
- `0x180015648`
- `0x1800158a0`
- `0x180015a4c`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800079e7`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800079e7`
- `KERNEL32!LeaveCriticalSection` at `0x180007a57`
- `KERNEL32!LeaveCriticalSection` at `0x180007a57`
- `KERNEL32!EnterCriticalSection` at `0x180007a2b`
- `KERNEL32!EnterCriticalSection` at `0x180007a2b`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___::_lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___(
        __int64 a1)
{
  _QWORD **v1; // rbx
  void *v2; // rdx
  const char *v3; // r9
  char *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  const char *v6; // rax
  const char *v7; // r8
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (_QWORD **)a1;
  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    v2 = **(void ***)a1;
    if ( v2 )
    {
      if ( !DeleteTimerQueueTimer(0, v2, 0) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x55B,
          (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
          v3);
      **v1 = 0;
    }
    if ( g_reliabilityTipTest )
    {
      v4 = (char *)g_reliabilityTipTest + 8;
      v5 = (struct _RTL_CRITICAL_SECTION *)((char *)g_reliabilityTipTest + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)g_reliabilityTipTest + 5);
      *((_DWORD *)v4 + 16) |= 0x300u;
      if ( *((_QWORD *)v4 + 30) )
        tip2::details::shared_data<0,0,0>::complete_helper((__int64)v4, 2u);
      if ( v5 )
        LeaveCriticalSection(v5);
    }
    if ( !g_aomdPromptResult )
    {
      v6 = "AOMDPromptResult::None";
      LOBYTE(a1) = 65;
      v7 = "AOMDPromptResult::None";
      do
      {
        ++v6;
        if ( (_BYTE)a1 == 58 )
          v7 = v6;
        LOBYTE(a1) = *v6;
      }
      while ( *v6 );
      tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
        a1,
        0,
        (__int64)v7);
    }
  }
}

```

## disassembly

```asm
0x1800079bc  mov     [rsp+arg_0], rbx
0x1800079c1  push    rdi
0x1800079c2  sub     rsp, 20h
0x1800079c6  cmp     byte ptr [rcx+8], 0
0x1800079ca  mov     rbx, rcx
0x1800079cd  jz      loc_180007A8C
0x1800079d3  mov     byte ptr [rcx+8], 0
0x1800079d7  mov     rax, [rcx]
0x1800079da  mov     rdx, [rax]; Timer
0x1800079dd  test    rdx, rdx
0x1800079e0  jz      short loc_180007A11
0x1800079e2  xor     r8d, r8d; CompletionEvent
0x1800079e5  xor     ecx, ecx; TimerQueue
0x1800079e7  call    cs:__imp_DeleteTimerQueueTimer
0x1800079ed  test    eax, eax
0x1800079ef  jnz     short loc_180007A07
0x1800079f1  mov     rcx, [rsp+28h]; this
0x1800079f6  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800079fd  mov     edx, 55Bh; void *
0x180007a02  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180007a07  mov     rax, [rbx]
0x180007a0a  mov     qword ptr [rax], 0
0x180007a11  mov     rax, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180007a18  test    rax, rax
0x180007a1b  jz      short loc_180007A5D
0x180007a1d  lea     rbx, [rax+8]
0x180007a21  lea     rdi, [rbx+0C0h]
0x180007a28  mov     rcx, rdi; lpCriticalSection
0x180007a2b  call    cs:__imp_EnterCriticalSection
0x180007a31  or      dword ptr [rbx+40h], 300h
0x180007a38  cmp     qword ptr [rbx+0F0h], 0
0x180007a40  jz      short loc_180007A4F
0x180007a42  mov     edx, 2
0x180007a47  mov     rcx, rbx
0x180007a4a  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180007a4f  test    rdi, rdi
0x180007a52  jz      short loc_180007A5D
0x180007a54  mov     rcx, rdi; lpCriticalSection
0x180007a57  call    cs:__imp_LeaveCriticalSection
0x180007a5d  mov     eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180007a63  nop
0x180007a64  test    eax, eax
0x180007a66  jnz     short loc_180007A8C
0x180007a68  lea     rax, aAomdpromptresu_9; "AOMDPromptResult::None"
0x180007a6f  mov     cl, 41h ; 'A'
0x180007a71  mov     r8, rax
0x180007a74  inc     rax
0x180007a77  cmp     cl, 3Ah ; ':'
0x180007a7a  jnz     short loc_180007A7F
0x180007a7c  mov     r8, rax
0x180007a7f  mov     cl, [rax]
0x180007a81  test    cl, cl
0x180007a83  jnz     short loc_180007A74
0x180007a85  xor     edx, edx
0x180007a87  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180007a8c  mov     rbx, [rsp+28h+arg_0]
0x180007a91  add     rsp, 20h
0x180007a95  pop     rdi
0x180007a96  retn
```
