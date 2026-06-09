# Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582___::_scalar_deleting_destructor_

- ea: `0x180009870`
- end: `0x18000989b`
- name: `Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582___::_scalar_deleting_destructor_`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180009870`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582___::_scalar_deleting_destructor_(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009870  push    rbx
0x180009872  sub     rsp, 20h
0x180009876  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::ReleaseNotifier::`vftable'
0x18000987d  mov     rbx, rcx
0x180009880  mov     [rcx], rax
0x180009883  test    dl, 1
0x180009886  jz      short loc_180009892
0x180009888  mov     edx, 18h
0x18000988d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009892  mov     rax, rbx
0x180009895  add     rsp, 20h
0x180009899  pop     rbx
0x18000989a  retn
```
