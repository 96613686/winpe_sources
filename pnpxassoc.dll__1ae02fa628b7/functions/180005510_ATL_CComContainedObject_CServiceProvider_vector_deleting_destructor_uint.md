# ATL::CComContainedObject<CServiceProvider>::`vector deleting destructor'(uint)

- ea: `0x180005510`
- end: `0x18000553f`
- name: `??_E?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800019b0`
- `0x180005510`
- `0x180009990`

## pseudocode

```c
CServiceProvider *__fastcall ATL::CComContainedObject<CServiceProvider>::`vector deleting destructor'(
        CServiceProvider *Block,
        char a2)
{
  CServiceProvider::~CServiceProvider(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005510  mov     [rsp+arg_0], rbx
0x180005515  push    rdi
0x180005516  sub     rsp, 20h
0x18000551a  mov     ebx, edx
0x18000551c  mov     rdi, rcx
0x18000551f  call    ??1CServiceProvider@@UEAA@XZ; CServiceProvider::~CServiceProvider(void)
0x180005524  test    bl, 1
0x180005527  jz      short loc_180005531
0x180005529  mov     rcx, rdi; Block
0x18000552c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005531  mov     rbx, [rsp+28h+arg_0]
0x180005536  mov     rax, rdi
0x180005539  add     rsp, 20h
0x18000553d  pop     rdi
0x18000553e  retn
```
