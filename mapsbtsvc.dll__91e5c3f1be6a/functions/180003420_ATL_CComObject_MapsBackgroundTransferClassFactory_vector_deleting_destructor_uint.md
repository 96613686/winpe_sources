# ATL::CComObject<MapsBackgroundTransferClassFactory>::`vector deleting destructor'(uint)

- ea: `0x180003420`
- end: `0x18000344f`
- name: `??_E?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e54`
- `0x180003370`
- `0x180003420`

## pseudocode

```c
void *__fastcall ATL::CComObject<MapsBackgroundTransferClassFactory>::`vector deleting destructor'(
        void *Block,
        char a2)
{
  ATL::CComObject<MapsBackgroundTransferClassFactory>::~CComObject<MapsBackgroundTransferClassFactory>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003420  mov     [rsp+arg_0], rbx
0x180003425  push    rdi
0x180003426  sub     rsp, 20h
0x18000342a  mov     ebx, edx
0x18000342c  mov     rdi, rcx
0x18000342f  call    ??1?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@UEAA@XZ; ATL::CComObject<MapsBackgroundTransferClassFactory>::~CComObject<MapsBackgroundTransferClassFactory>(void)
0x180003434  test    bl, 1
0x180003437  jz      short loc_180003441
0x180003439  mov     rcx, rdi; Block
0x18000343c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003441  mov     rbx, [rsp+28h+arg_0]
0x180003446  mov     rax, rdi
0x180003449  add     rsp, 20h
0x18000344d  pop     rdi
0x18000344e  retn
```
