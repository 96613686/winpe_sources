# HgServiceModule::`vector deleting destructor'(uint)

- ea: `0x180009950`
- end: `0x180009984`
- name: `??_EHgServiceModule@@UEAAPEAXI@Z`
- size: `52`
- prototype: `HgServiceModule *__fastcall(HgServiceModule *this, struct Microsoft::WRL::Details::ModuleBase *, const wchar_t *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180009564`
- `0x180009950`

## pseudocode

```c
HgServiceModule *__fastcall HgServiceModule::`vector deleting destructor'(
        HgServiceModule *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const wchar_t *a3,
        bool a4)
{
  char v4; // bl

  v4 = (char)a2;
  Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(this, a2, a3, a4);
  if ( (v4 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009950  mov     [rsp+arg_0], rbx
0x180009955  push    rdi
0x180009956  sub     rsp, 20h
0x18000995a  mov     ebx, edx
0x18000995c  mov     rdi, rcx
0x18000995f  call    ??1?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(void)
0x180009964  test    bl, 1
0x180009967  jz      short loc_180009976
0x180009969  mov     edx, 18h
0x18000996e  mov     rcx, rdi; Block
0x180009971  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009976  mov     rbx, [rsp+28h+arg_0]
0x18000997b  mov     rax, rdi
0x18000997e  add     rsp, 20h
0x180009982  pop     rdi
0x180009983  retn
```
