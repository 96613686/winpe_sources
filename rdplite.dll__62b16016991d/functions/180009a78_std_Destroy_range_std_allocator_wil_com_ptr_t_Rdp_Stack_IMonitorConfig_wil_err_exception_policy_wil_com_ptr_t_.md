# std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)

- ea: `0x180009a78`
- end: `0x180009aa9`
- name: `??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009dc4`
- `0x18000a76c`
- `0x18000aa58`
- `0x18000c0f0`
- `0x18000d2a8`
- `0x180016304`
- `0x180019894`

## callees

- `0x180007b28`
- `0x180009a78`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
      result = wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v3++);
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180009a78  cmp     rcx, rdx
0x180009a7b  jz      short locret_180009AA8
0x180009a7d  mov     [rsp+arg_0], rbx
0x180009a82  push    rdi
0x180009a83  sub     rsp, 20h
0x180009a87  mov     rdi, rdx
0x180009a8a  mov     rbx, rcx
0x180009a8d  mov     rcx, rbx
0x180009a90  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180009a95  add     rbx, 8
0x180009a99  cmp     rbx, rdi
0x180009a9c  jnz     short loc_180009A8D
0x180009a9e  mov     rbx, [rsp+28h+arg_0]
0x180009aa3  add     rsp, 20h
0x180009aa7  pop     rdi
0x180009aa8  retn
```
