# wil::com_ptr_t<INetworkConnection,wil::err_exception_policy>::query<INetworkConnectionCost>(void)

- ea: `0x18000d58c`
- end: `0x18000d5db`
- name: `??$query@UINetworkConnectionCost@@@?$com_ptr_t@UINetworkConnection@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINetworkConnectionCost@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b9d0`

## callees

- `0x18000d58c`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000d5bd`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<INetworkConnection,wil::err_exception_policy>::query<INetworkConnectionCost>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_dcb0000a_570f_4a9b_8d69_199fdba5723b, a2);
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
0x18000d58c  push    rbx
0x18000d58e  sub     rsp, 30h
0x18000d592  mov     rcx, [rcx]
0x18000d595  mov     rbx, rdx
0x18000d598  mov     qword ptr [rdx], 0
0x18000d59f  mov     r8, rdx
0x18000d5a2  lea     rdx, _GUID_dcb0000a_570f_4a9b_8d69_199fdba5723b
0x18000d5a9  mov     rax, [rcx]
0x18000d5ac  mov     rax, [rax]
0x18000d5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b4  test    eax, eax
0x18000d5b6  jns     short loc_18000D5D2
0x18000d5b8  mov     rcx, [rsp+38h]; this
0x18000d5bd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d5c4  mov     r9d, eax; char *
0x18000d5c7  mov     edx, 1CBEh; void *
0x18000d5cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d5d2  mov     rax, rbx
0x18000d5d5  add     rsp, 30h
0x18000d5d9  pop     rbx
0x18000d5da  retn
```
