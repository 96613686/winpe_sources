# ATL::CComObject<CEraseEvent>::`vector deleting destructor'(uint)

- ea: `0x140003d50`
- end: `0x140003d84`
- name: `??_E?$CComObject@VCEraseEvent@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001c54`
- `0x140003818`
- `0x140003d50`

## pseudocode

```c
void *__fastcall ATL::CComObject<CEraseEvent>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CEraseEvent>::~CComObject<CEraseEvent>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140003d50  mov     [rsp+arg_0], rbx
0x140003d55  push    rdi
0x140003d56  sub     rsp, 20h
0x140003d5a  mov     ebx, edx
0x140003d5c  mov     rdi, rcx
0x140003d5f  call    ??1?$CComObject@VCEraseEvent@@@ATL@@UEAA@XZ; ATL::CComObject<CEraseEvent>::~CComObject<CEraseEvent>(void)
0x140003d64  test    bl, 1
0x140003d67  jz      short loc_140003D76
0x140003d69  mov     edx, 78h ; 'x'
0x140003d6e  mov     rcx, rdi; Block
0x140003d71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d76  mov     rbx, [rsp+28h+arg_0]
0x140003d7b  mov     rax, rdi
0x140003d7e  add     rsp, 20h
0x140003d82  pop     rdi
0x140003d83  retn
```
