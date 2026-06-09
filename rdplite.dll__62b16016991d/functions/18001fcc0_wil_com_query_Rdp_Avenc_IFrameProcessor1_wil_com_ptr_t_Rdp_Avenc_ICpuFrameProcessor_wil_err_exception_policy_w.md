# wil::com_query<Rdp::Avenc::IFrameProcessor1,wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &>(wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &)

- ea: `0x18001fcc0`
- end: `0x18001fd0f`
- name: `??$com_query@UIFrameProcessor1@Avenc@Rdp@@AEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800210ec`
- `0x1800211dc`

## callees

- `0x18000d590`
- `0x18001fcc0`
- `0x18002a010`

## string_xrefs

- `0x18001fcf1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<Rdp::Avenc::IFrameProcessor1,wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_4854b3c6_4466_4f32_a2b6_58874b5ed926, a1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  return a1;
}

```

## disassembly

```asm
0x18001fcc0  push    rbx
0x18001fcc2  sub     rsp, 30h
0x18001fcc6  mov     rbx, rcx
0x18001fcc9  mov     rcx, [rdx]
0x18001fccc  mov     r8, rbx
0x18001fccf  lea     rdx, _GUID_4854b3c6_4466_4f32_a2b6_58874b5ed926
0x18001fcd6  mov     qword ptr [rbx], 0
0x18001fcdd  mov     rax, [rcx]
0x18001fce0  mov     rax, [rax]
0x18001fce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce8  test    eax, eax
0x18001fcea  jns     short loc_18001FD06
0x18001fcec  mov     rcx, [rsp+38h]; this
0x18001fcf1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fcf8  mov     r9d, eax; char *
0x18001fcfb  mov     edx, 1CBEh; void *
0x18001fd00  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fd06  mov     rax, rbx
0x18001fd09  add     rsp, 30h
0x18001fd0d  pop     rbx
0x18001fd0e  retn
```
