# wil::com_ptr_t<INetwork,wil::err_exception_policy>::query<IPropertyBag>(void)

- ea: `0x18000eeb0`
- end: `0x18000eeff`
- name: `??$query@UIPropertyBag@@@?$com_ptr_t@UINetwork@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPropertyBag@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e33c`

## callees

- `0x18000eeb0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000eee1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<INetwork,wil::err_exception_policy>::query<IPropertyBag>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, a2);
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
0x18000eeb0  push    rbx
0x18000eeb2  sub     rsp, 30h
0x18000eeb6  mov     rcx, [rcx]
0x18000eeb9  mov     rbx, rdx
0x18000eebc  mov     qword ptr [rdx], 0
0x18000eec3  mov     r8, rdx
0x18000eec6  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18000eecd  mov     rax, [rcx]
0x18000eed0  mov     rax, [rax]
0x18000eed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed8  test    eax, eax
0x18000eeda  jns     short loc_18000EEF6
0x18000eedc  mov     rcx, [rsp+38h]; this
0x18000eee1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000eee8  mov     r9d, eax; char *
0x18000eeeb  mov     edx, 1CBEh; void *
0x18000eef0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000eef6  mov     rax, rbx
0x18000eef9  add     rsp, 30h
0x18000eefd  pop     rbx
0x18000eefe  retn
```
