# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vector deleting destructor'(uint)

- ea: `0x180004a60`
- end: `0x180004a94`
- name: `??_E?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *, __int64, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001a74`
- `0x180004124`
- `0x180004a60`

## pseudocode

```c
Microsoft::WRL::Details *__fastcall Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vector deleting destructor'(
        Microsoft::WRL::Details *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  char v4; // bl

  v4 = a2;
  Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::~Module<1,Windows::Internal::ServiceModule>(
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
0x180004a60  mov     [rsp+arg_0], rbx
0x180004a65  push    rdi
0x180004a66  sub     rsp, 20h
0x180004a6a  mov     ebx, edx
0x180004a6c  mov     rdi, rcx
0x180004a6f  call    ??1?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::~Module<1,Windows::Internal::ServiceModule>(void)
0x180004a74  test    bl, 1
0x180004a77  jz      short loc_180004A86
0x180004a79  mov     edx, 8; unsigned __int64
0x180004a7e  mov     rcx, rdi; void *
0x180004a81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004a86  mov     rbx, [rsp+28h+arg_0]
0x180004a8b  mov     rax, rdi
0x180004a8e  add     rsp, 20h
0x180004a92  pop     rdi
0x180004a93  retn
```
