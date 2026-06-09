# std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>::~vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(void)

- ea: `0x18000a76c`
- end: `0x18000a7b6`
- name: `??1?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `74`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028a24`
- `0x1800295d3`
- `0x1800298e8`
- `0x1800298fa`
- `0x18002990c`

## callees

- `0x1800049b8`
- `0x180009a78`
- `0x18000a76c`

## pseudocode

```c
__int64 __fastcall std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::~vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(
        __int64 **a1)
{
  __int64 *v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(v2, a1[1]);
    result = std::_Deallocate<16>(*a1, ((char *)a1[2] - (char *)*a1) & 0xFFFFFFFFFFFFFFF8uLL);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a76c  push    rbx
0x18000a76e  sub     rsp, 20h
0x18000a772  mov     rbx, rcx
0x18000a775  mov     rcx, [rcx]
0x18000a778  test    rcx, rcx
0x18000a77b  jz      short loc_18000A7B0
0x18000a77d  mov     rdx, [rbx+8]
0x18000a781  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x18000a786  mov     rdx, [rbx+10h]
0x18000a78a  sub     rdx, [rbx]
0x18000a78d  mov     rcx, [rbx]
0x18000a790  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000a794  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a799  mov     qword ptr [rbx], 0
0x18000a7a0  mov     qword ptr [rbx+8], 0
0x18000a7a8  mov     qword ptr [rbx+10h], 0
0x18000a7b0  add     rsp, 20h
0x18000a7b4  pop     rbx
0x18000a7b5  retn
```
