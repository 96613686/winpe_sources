# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>>>::_Buyheadnode(void)

- ea: `0x18002b040`
- end: `0x18002b07a`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@XZ`
- size: `58`
- prototype: `void()`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026240`
- `0x18002e0a0`
- `0x18002eb90`

## callees

- `0x180002034`
- `0x18002b040`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002b05d`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002b05d`

## pseudocode

```c
void std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>>::_Buyheadnode()
{
  _QWORD *v0; // rax

  v0 = operator new(0x30u);
  if ( !v0 )
    std::_Xbad_alloc();
  *v0 = v0;
  v0[1] = v0;
  v0[2] = v0;
  *((_WORD *)v0 + 12) = 257;
}

```

## disassembly

```asm
0x18002b040  mov     [rsp+arg_0], rcx
0x18002b045  sub     rsp, 28h
0x18002b049  mov     ecx, 30h ; '0'; Size
0x18002b04e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b053  mov     [rsp+28h+arg_0], rax
0x18002b058  test    rax, rax
0x18002b05b  jnz     short loc_18002B064
0x18002b05d  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002b063  nop
0x18002b064  mov     [rax], rax
0x18002b067  mov     [rax+8], rax
0x18002b06b  mov     [rax+10h], rax
0x18002b06f  mov     word ptr [rax+18h], 101h
0x18002b075  add     rsp, 28h
0x18002b079  retn
```
