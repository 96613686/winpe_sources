# ATL::CComObject<CMSDiscMasterObj>::`vector deleting destructor'(uint)

- ea: `0x180007ff0`
- end: `0x18000801f`
- name: `??_E?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x180007e90`
- `0x180007ff0`

## pseudocode

```c
CMSDiscMasterObj *__fastcall ATL::CComObject<CMSDiscMasterObj>::`vector deleting destructor'(
        CMSDiscMasterObj *Block,
        char a2)
{
  ATL::CComObject<CMSDiscMasterObj>::~CComObject<CMSDiscMasterObj>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007ff0  mov     [rsp+arg_0], rbx
0x180007ff5  push    rdi
0x180007ff6  sub     rsp, 20h
0x180007ffa  mov     ebx, edx
0x180007ffc  mov     rdi, rcx
0x180007fff  call    ??1?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAA@XZ; ATL::CComObject<CMSDiscMasterObj>::~CComObject<CMSDiscMasterObj>(void)
0x180008004  test    bl, 1
0x180008007  jz      short loc_180008011
0x180008009  mov     rcx, rdi; Block
0x18000800c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008011  mov     rbx, [rsp+28h+arg_0]
0x180008016  mov     rax, rdi
0x180008019  add     rsp, 20h
0x18000801d  pop     rdi
0x18000801e  retn
```
