# ATL::CComObject<CEnhancedStorageActEnumerator>::`vector deleting destructor'(uint)

- ea: `0x180008d80`
- end: `0x180008daf`
- name: `??_E?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001240`
- `0x180008c70`
- `0x180008d80`

## pseudocode

```c
CEnhancedStorageActEnumerator *__fastcall ATL::CComObject<CEnhancedStorageActEnumerator>::`vector deleting destructor'(
        CEnhancedStorageActEnumerator *Block,
        char a2)
{
  ATL::CComObject<CEnhancedStorageActEnumerator>::~CComObject<CEnhancedStorageActEnumerator>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008d80  mov     [rsp+arg_0], rbx
0x180008d85  push    rdi
0x180008d86  sub     rsp, 20h
0x180008d8a  mov     ebx, edx
0x180008d8c  mov     rdi, rcx
0x180008d8f  call    ??1?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@UEAA@XZ; ATL::CComObject<CEnhancedStorageActEnumerator>::~CComObject<CEnhancedStorageActEnumerator>(void)
0x180008d94  test    bl, 1
0x180008d97  jz      short loc_180008DA1
0x180008d99  mov     rcx, rdi; Block
0x180008d9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008da1  mov     rbx, [rsp+28h+arg_0]
0x180008da6  mov     rax, rdi
0x180008da9  add     rsp, 20h
0x180008dad  pop     rdi
0x180008dae  retn
```
