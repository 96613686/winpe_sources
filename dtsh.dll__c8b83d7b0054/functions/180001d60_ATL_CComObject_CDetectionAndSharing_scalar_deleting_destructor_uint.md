# ATL::CComObject<CDetectionAndSharing>::`scalar deleting destructor'(uint)

- ea: `0x180001d60`
- end: `0x180001d8f`
- name: `??_G?$CComObject@VCDetectionAndSharing@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010e0`
- `0x180001c2c`
- `0x180001d60`

## pseudocode

```c
void *__fastcall ATL::CComObject<CDetectionAndSharing>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CDetectionAndSharing>::~CComObject<CDetectionAndSharing>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180001d60  mov     [rsp+arg_0], rbx
0x180001d65  push    rdi
0x180001d66  sub     rsp, 20h
0x180001d6a  mov     ebx, edx
0x180001d6c  mov     rdi, rcx
0x180001d6f  call    ??1?$CComObject@VCDetectionAndSharing@@@ATL@@UEAA@XZ; ATL::CComObject<CDetectionAndSharing>::~CComObject<CDetectionAndSharing>(void)
0x180001d74  test    bl, 1
0x180001d77  jz      short loc_180001D81
0x180001d79  mov     rcx, rdi; Block
0x180001d7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d81  mov     rbx, [rsp+28h+arg_0]
0x180001d86  mov     rax, rdi
0x180001d89  add     rsp, 20h
0x180001d8d  pop     rdi
0x180001d8e  retn
```
