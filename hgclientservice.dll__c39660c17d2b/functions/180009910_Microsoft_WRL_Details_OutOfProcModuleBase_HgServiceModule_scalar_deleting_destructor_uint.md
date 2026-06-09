# Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::`scalar deleting destructor'(uint)

- ea: `0x180009910`
- end: `0x180009944`
- name: `??_G?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *Block, struct Microsoft::WRL::Details::ModuleBase *, const wchar_t *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180009564`
- `0x180009910`

## pseudocode

```c
Microsoft::WRL::Details *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::`scalar deleting destructor'(
        Microsoft::WRL::Details *Block,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const wchar_t *a3,
        bool a4)
{
  char v4; // bl

  v4 = (char)a2;
  Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(
    Block,
    a2,
    a3,
    a4);
  if ( (v4 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009910  mov     [rsp+arg_0], rbx
0x180009915  push    rdi
0x180009916  sub     rsp, 20h
0x18000991a  mov     ebx, edx
0x18000991c  mov     rdi, rcx
0x18000991f  call    ??1?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(void)
0x180009924  test    bl, 1
0x180009927  jz      short loc_180009936
0x180009929  mov     edx, 10h
0x18000992e  mov     rcx, rdi; Block
0x180009931  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009936  mov     rbx, [rsp+28h+arg_0]
0x18000993b  mov     rax, rdi
0x18000993e  add     rsp, 20h
0x180009942  pop     rdi
0x180009943  retn
```
