# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vector deleting destructor'(uint)

- ea: `0x180004be0`
- end: `0x180004c0b`
- name: `??_EReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001a74`
- `0x180004be0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004be0  push    rbx
0x180004be2  sub     rsp, 20h
0x180004be6  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable'
0x180004bed  mov     rbx, rcx
0x180004bf0  mov     [rcx], rax
0x180004bf3  test    dl, 1
0x180004bf6  jz      short loc_180004C02
0x180004bf8  mov     edx, 10h; unsigned __int64
0x180004bfd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004c02  mov     rax, rbx
0x180004c05  add     rsp, 20h
0x180004c09  pop     rbx
0x180004c0a  retn
```
