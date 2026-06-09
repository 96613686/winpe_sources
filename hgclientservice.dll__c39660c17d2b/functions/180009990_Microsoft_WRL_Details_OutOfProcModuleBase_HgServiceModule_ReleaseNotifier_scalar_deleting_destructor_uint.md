# Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::ReleaseNotifier::`scalar deleting destructor'(uint)

- ea: `0x180009990`
- end: `0x1800099bb`
- name: `??_GReleaseNotifier@?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180009990`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::ReleaseNotifier::`scalar deleting destructor'(
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
0x180009990  push    rbx
0x180009992  sub     rsp, 20h
0x180009996  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::ReleaseNotifier::`vftable'
0x18000999d  mov     rbx, rcx
0x1800099a0  mov     [rcx], rax
0x1800099a3  test    dl, 1
0x1800099a6  jz      short loc_1800099B2
0x1800099a8  mov     edx, 10h
0x1800099ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800099b2  mov     rax, rbx
0x1800099b5  add     rsp, 20h
0x1800099b9  pop     rbx
0x1800099ba  retn
```
