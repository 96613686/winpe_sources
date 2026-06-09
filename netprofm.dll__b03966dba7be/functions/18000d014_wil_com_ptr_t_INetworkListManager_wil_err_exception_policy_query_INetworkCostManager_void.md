# wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::query<INetworkCostManager>(void)

- ea: `0x18000d014`
- end: `0x18000d063`
- name: `??$query@UINetworkCostManager@@@?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINetworkCostManager@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x18000d014`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000d045`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::query<INetworkCostManager>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, a2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  return a2;
}

```

## disassembly

```asm
0x18000d014  push    rbx
0x18000d016  sub     rsp, 30h
0x18000d01a  mov     rcx, [rcx]
0x18000d01d  mov     rbx, rdx
0x18000d020  mov     qword ptr [rdx], 0
0x18000d027  mov     r8, rdx
0x18000d02a  lea     rdx, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b
0x18000d031  mov     rax, [rcx]
0x18000d034  mov     rax, [rax]
0x18000d037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d03c  test    eax, eax
0x18000d03e  jns     short loc_18000D05A
0x18000d040  mov     rcx, [rsp+38h]; this
0x18000d045  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d04c  mov     r9d, eax; char *
0x18000d04f  mov     edx, 1CBEh; void *
0x18000d054  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d05a  mov     rax, rbx
0x18000d05d  add     rsp, 30h
0x18000d061  pop     rbx
0x18000d062  retn
```
