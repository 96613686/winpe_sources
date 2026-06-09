# std::_Tree_buy<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>>::_Buynode0(void)

- ea: `0x18002b080`
- end: `0x18002b0c4`
- name: `?_Buynode0@?$_Tree_buy@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@XZ`
- size: `68`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025c04`
- `0x18002b298`
- `0x18002b394`
- `0x18002b3e8`

## callees

- `0x180002034`
- `0x18002b080`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002b0a0`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002b0a0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode0(
        _QWORD *a1)
{
  _QWORD *v2; // rdx

  v2 = operator new(0x30u);
  if ( !v2 )
    std::_Xbad_alloc();
  *v2 = *a1;
  v2[1] = *a1;
  v2[2] = *a1;
  return v2;
}

```

## disassembly

```asm
0x18002b080  push    rbx
0x18002b082  sub     rsp, 20h
0x18002b086  mov     rbx, rcx
0x18002b089  mov     ecx, 30h ; '0'; Size
0x18002b08e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b093  mov     rdx, rax
0x18002b096  mov     [rsp+28h+arg_8], rax
0x18002b09b  test    rax, rax
0x18002b09e  jnz     short loc_18002B0A7
0x18002b0a0  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002b0a6  nop
0x18002b0a7  mov     rax, [rbx]
0x18002b0aa  mov     [rdx], rax
0x18002b0ad  mov     rax, [rbx]
0x18002b0b0  mov     [rdx+8], rax
0x18002b0b4  mov     rax, [rbx]
0x18002b0b7  mov     [rdx+10h], rax
0x18002b0bb  mov     rax, rdx
0x18002b0be  add     rsp, 20h
0x18002b0c2  pop     rbx
0x18002b0c3  retn
```
