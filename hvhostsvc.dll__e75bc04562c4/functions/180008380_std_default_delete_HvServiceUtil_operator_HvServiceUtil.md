# std::default_delete<HvServiceUtil>::operator()(HvServiceUtil *)

- ea: `0x180008380`
- end: `0x1800083a8`
- name: `??R?$default_delete@VHvServiceUtil@@@std@@QEBAXPEAVHvServiceUtil@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180008234`
- `0x1800084f4`

## callees

- `0x1800024d0`
- `0x180007064`
- `0x180008380`

## pseudocode

```c
void __fastcall std::default_delete<HvServiceUtil>::operator()(__int64 a1, void **a2)
{
  if ( a2 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
    operator delete(a2, (const struct std::nothrow_t *)8);
  }
}

```

## disassembly

```asm
0x180008380  test    rdx, rdx
0x180008383  jz      short locret_1800083A7
0x180008385  push    rbx
0x180008386  sub     rsp, 20h
0x18000838a  mov     rcx, rdx
0x18000838d  mov     rbx, rdx
0x180008390  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008395  mov     edx, 8; struct std::nothrow_t *
0x18000839a  mov     rcx, rbx; void *
0x18000839d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800083a2  add     rsp, 20h
0x1800083a6  pop     rbx
0x1800083a7  retn
```
