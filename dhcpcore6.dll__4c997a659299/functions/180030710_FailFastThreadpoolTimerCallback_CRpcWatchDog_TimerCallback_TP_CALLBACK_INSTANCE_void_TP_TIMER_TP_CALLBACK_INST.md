# FailFastThreadpoolTimerCallback<&CRpcWatchDog::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)>(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180030710`
- end: `0x180030742`
- name: `??$FailFastThreadpoolTimerCallback@$1?TimerCallback@CRpcWatchDog@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `50`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, CRpcWatchDog *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800193a0`
- `0x180030550`
- `0x180030594`
- `0x180030710`

## pseudocode

```c
void __fastcall FailFastThreadpoolTimerCallback<&private: static void CRpcWatchDog::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)>(
        PTP_CALLBACK_INSTANCE Instance,
        CRpcWatchDog *Context,
        PTP_TIMER Timer)
{
  CRpcWatchDog::ProcessEntries(Context);
}

```

## disassembly

```asm
0x180030710  push    rbx
0x180030712  sub     rsp, 30h
0x180030716  mov     ebx, 1
0x18003071b  mov     [rsp+38h+var_14], ebx
0x18003071f  mov     rcx, rdx; this
0x180030722  call    ?ProcessEntries@CRpcWatchDog@@AEAAXXZ; CRpcWatchDog::ProcessEntries(void)
0x180030727  jmp     short loc_18003072D
0x180030729  mov     ebx, [rsp+38h+var_14]
0x18003072d  test    ebx, ebx
0x18003072f  jnz     short loc_18003073B
0x180030731  add     rsp, 30h
0x180030735  pop     rbx
0x180030736  jmp     WxReportSwallowedFatalException
0x18003073b  add     rsp, 30h
0x18003073f  pop     rbx
0x180030740  retn
0x180030b06  push    rbp
0x180030b08  sub     rsp, 20h
0x180030b0c  mov     rbp, rdx
0x180030b0f  call    WxSaveExceptionFilter
0x180030b14  mov     [rbp+24h], eax
0x180030b17  mov     eax, [rbp+24h]
0x180030b1a  add     rsp, 20h
0x180030b1e  pop     rbp
0x180030b1f  retn
0x180030b21  push    rbp
0x180030b23  sub     rsp, 20h
0x180030b27  mov     rbp, rdx
0x180030b2a  cmp     dword ptr [rbp+24h], 0
0x180030b2e  jnz     short loc_180030B36
0x180030b30  call    WxReportSwallowedFatalException
0x180030b36  add     rsp, 20h
0x180030b3a  pop     rbp
0x180030b3b  retn
```
