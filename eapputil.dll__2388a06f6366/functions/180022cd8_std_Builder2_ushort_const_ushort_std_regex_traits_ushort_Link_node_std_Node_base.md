# std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Link_node(std::_Node_base *)

- ea: `0x180022cd8`
- end: `0x180022d0d`
- name: `?_Link_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@PEAV32@@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18001fcc0`
- `0x18002010c`
- `0x180020388`
- `0x180020644`
- `0x1800207d4`
- `0x180020828`
- `0x180021764`
- `0x1800223f8`
- `0x18002344c`

## callees

- `0x180022cd8`

## pseudocode

```c
__int64 __fastcall std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Link_node(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 8);
  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
  if ( v2 )
  {
    *(_QWORD *)(a2 + 16) = v2;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) + 24LL) = a2;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = a2;
  result = a2;
  *(_QWORD *)(a1 + 8) = a2;
  return result;
}

```

## disassembly

```asm
0x180022cd8  mov     rax, [rcx+8]
0x180022cdc  mov     [rdx+18h], rax
0x180022ce0  mov     rax, [rcx+8]
0x180022ce4  mov     r8, [rax+10h]
0x180022ce8  test    r8, r8
0x180022ceb  jz      short loc_180022CFD
0x180022ced  mov     [rdx+10h], r8
0x180022cf1  mov     rax, [rcx+8]
0x180022cf5  mov     r8, [rax+10h]
0x180022cf9  mov     [r8+18h], rdx
0x180022cfd  mov     rax, [rcx+8]
0x180022d01  mov     [rax+10h], rdx
0x180022d05  mov     rax, rdx
0x180022d08  mov     [rcx+8], rdx
0x180022d0c  retn
```
