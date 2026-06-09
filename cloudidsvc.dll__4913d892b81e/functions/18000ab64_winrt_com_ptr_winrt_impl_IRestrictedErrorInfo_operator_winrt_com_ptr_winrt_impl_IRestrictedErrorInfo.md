# winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)

- ea: `0x18000ab64`
- end: `0x18000ab9f`
- name: `??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z`
- size: `59`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a1f8`
- `0x18000c88c`

## callees

- `0x18000ab64`
- `0x18000ce2c`

## pseudocode

```c
__int64 *__fastcall winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rax

  if ( a1 != a2 )
  {
    if ( *a1 )
      winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(a1);
    v4 = *a2;
    *a2 = 0;
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x18000ab64  mov     [rsp+arg_0], rbx
0x18000ab69  push    rdi
0x18000ab6a  sub     rsp, 20h
0x18000ab6e  mov     rdi, rdx
0x18000ab71  mov     rbx, rcx
0x18000ab74  cmp     rcx, rdx
0x18000ab77  jz      short loc_18000AB91
0x18000ab79  cmp     qword ptr [rcx], 0
0x18000ab7d  jz      short loc_18000AB84
0x18000ab7f  call    ?unconditional_release_ref@?$com_ptr@UILanguageExceptionErrorInfo2@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(void)
0x18000ab84  mov     rax, [rdi]
0x18000ab87  mov     qword ptr [rdi], 0
0x18000ab8e  mov     [rbx], rax
0x18000ab91  mov     rax, rbx
0x18000ab94  mov     rbx, [rsp+28h+arg_0]
0x18000ab99  add     rsp, 20h
0x18000ab9d  pop     rdi
0x18000ab9e  retn
```
