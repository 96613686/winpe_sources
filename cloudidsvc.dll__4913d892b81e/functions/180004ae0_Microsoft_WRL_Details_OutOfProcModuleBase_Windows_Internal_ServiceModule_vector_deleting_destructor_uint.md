# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vector deleting destructor'(uint)

- ea: `0x180004ae0`
- end: `0x180004b14`
- name: `??_E?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *, __int64, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001a74`
- `0x180004194`
- `0x180004ae0`

## pseudocode

```c
Microsoft::WRL::Details *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vector deleting destructor'(
        Microsoft::WRL::Details *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  char v4; // bl

  v4 = a2;
  Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(
    a1,
    a2,
    a3,
    a4);
  if ( (v4 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004ae0  mov     [rsp+arg_0], rbx
0x180004ae5  push    rdi
0x180004ae6  sub     rsp, 20h
0x180004aea  mov     ebx, edx
0x180004aec  mov     rdi, rcx
0x180004aef  call    ??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)
0x180004af4  test    bl, 1
0x180004af7  jz      short loc_180004B06
0x180004af9  mov     edx, 10h; unsigned __int64
0x180004afe  mov     rcx, rdi; void *
0x180004b01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004b06  mov     rbx, [rsp+28h+arg_0]
0x180004b0b  mov     rax, rdi
0x180004b0e  add     rsp, 20h
0x180004b12  pop     rdi
0x180004b13  retn
```
