# ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`scalar deleting destructor'(uint)

- ea: `0x18000da70`
- end: `0x18000daa0`
- name: `??_G?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `IASTL::IASComponent *__fastcall(IASTL::IASComponent *Block, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d6a0`
- `0x18000da70`

## import_xrefs

- `msvcrt!free` at `0x18000da8c`
- `msvcrt!free` at `0x18000da8c`

## pseudocode

```c
IASTL::IASComponent *__fastcall ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`scalar deleting destructor'(
        IASTL::IASComponent *Block,
        char a2)
{
  ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::~CComObject<IASTL::IASComponentObject<NTEventLog>>(Block);
  if ( (a2 & 1) != 0 )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000da70  mov     [rsp+arg_0], rbx
0x18000da75  push    rdi
0x18000da76  sub     rsp, 20h
0x18000da7a  mov     ebx, edx
0x18000da7c  mov     rdi, rcx
0x18000da7f  call    ??1?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@UEAA@XZ; ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::~CComObject<IASTL::IASComponentObject<NTEventLog>>(void)
0x18000da84  test    bl, 1
0x18000da87  jz      short loc_18000DA92
0x18000da89  mov     rcx, rdi; Block
0x18000da8c  call    cs:__imp_free
0x18000da92  mov     rbx, [rsp+28h+arg_0]
0x18000da97  mov     rax, rdi
0x18000da9a  add     rsp, 20h
0x18000da9e  pop     rdi
0x18000da9f  retn
```
