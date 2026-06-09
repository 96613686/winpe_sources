# wil::com_query<Rdp::Avenc::IGpuFence,wil::com_ptr_t<IUnknown,wil::err_exception_policy> &>(wil::com_ptr_t<IUnknown,wil::err_exception_policy> &)

- ea: `0x18001fd18`
- end: `0x18001fd67`
- name: `??$com_query@UIGpuFence@Avenc@Rdp@@AEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIGpuFence@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@0@@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021580`

## callees

- `0x18000d590`
- `0x18001fd18`
- `0x18002a010`

## string_xrefs

- `0x18001fd49`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<Rdp::Avenc::IGpuFence,wil::com_ptr_t<IUnknown,wil::err_exception_policy> &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_3f7b3958_53d6_46f9_8675_c8a2d187fef9, a1);
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
0x18001fd18  push    rbx
0x18001fd1a  sub     rsp, 30h
0x18001fd1e  mov     rbx, rcx
0x18001fd21  mov     rcx, [rdx]
0x18001fd24  mov     r8, rbx
0x18001fd27  lea     rdx, _GUID_3f7b3958_53d6_46f9_8675_c8a2d187fef9
0x18001fd2e  mov     qword ptr [rbx], 0
0x18001fd35  mov     rax, [rcx]
0x18001fd38  mov     rax, [rax]
0x18001fd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd40  test    eax, eax
0x18001fd42  jns     short loc_18001FD5E
0x18001fd44  mov     rcx, [rsp+38h]; this
0x18001fd49  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fd50  mov     r9d, eax; char *
0x18001fd53  mov     edx, 1CBEh; void *
0x18001fd58  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fd5e  mov     rax, rbx
0x18001fd61  add     rsp, 30h
0x18001fd65  pop     rbx
0x18001fd66  retn
```
