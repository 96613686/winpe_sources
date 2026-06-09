# CCollection<IHCCommandCollection,CCommand>::`vector deleting destructor'(uint)

- ea: `0x1800047e0`
- end: `0x180004810`
- name: `??_E?$CCollection@UIHCCommandCollection@@VCCommand@@@@MEAAPEAXI@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800047e0`
- `0x180004894`
- `0x180004fbc`

## pseudocode

```c
void *__fastcall CCollection<IHCCommandCollection,CCommand>::`vector deleting destructor'(void *Block, char a2)
{
  CCollection<IHCCommandCollection,CCommand>::~CCollection<IHCCommandCollection,CCommand>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800047e0  mov     [rsp+arg_0], rbx
0x1800047e5  push    rdi
0x1800047e6  sub     rsp, 20h
0x1800047ea  mov     ebx, edx
0x1800047ec  mov     rdi, rcx
0x1800047ef  call    ??1?$CCollection@UIHCCommandCollection@@VCCommand@@@@MEAA@XZ; CCollection<IHCCommandCollection,CCommand>::~CCollection<IHCCommandCollection,CCommand>(void)
0x1800047f4  test    bl, 1
0x1800047f7  jz      short loc_180004801
0x1800047f9  mov     rcx, rdi; Block
0x1800047fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004801  mov     rbx, [rsp+28h+arg_0]
0x180004806  mov     rax, rdi
0x180004809  add     rsp, 20h
0x18000480d  pop     rdi
0x18000480e  retn
```
