# tip2::test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>(void)

- ea: `0x180007d5c`
- end: `0x180007da6`
- name: `??1?$test_watcher@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800214ef`

## callees

- `0x180007c18`
- `0x180007d5c`
- `0x18000872c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180007d8d`
- `ole32!CoTaskMemFree` at `0x180007d8d`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 56);
  if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 272), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
    CoTaskMemFree((LPVOID)v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x180007d5c  mov     [rsp+arg_8], rbx
0x180007d61  push    rdi
0x180007d62  sub     rsp, 20h
0x180007d66  mov     rbx, [rcx+38h]
0x180007d6a  mov     rdi, rcx
0x180007d6d  test    rbx, rbx
0x180007d70  jz      short loc_180007D93
0x180007d72  or      eax, 0FFFFFFFFh
0x180007d75  lock xadd [rbx+110h], eax
0x180007d7d  cmp     eax, 1
0x180007d80  jnz     short loc_180007D93
0x180007d82  mov     rcx, rbx
0x180007d85  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x180007d8a  mov     rcx, rbx; pv
0x180007d8d  call    cs:__imp_CoTaskMemFree
0x180007d93  lea     rcx, [rdi+8]; this
0x180007d97  mov     rbx, [rsp+28h+arg_8]
0x180007d9c  add     rsp, 20h
0x180007da0  pop     rdi
0x180007da1  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
