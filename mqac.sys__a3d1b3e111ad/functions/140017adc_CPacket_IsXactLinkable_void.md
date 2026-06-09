# CPacket::IsXactLinkable(void)

- ea: `0x140017adc`
- end: `0x140017afa`
- name: `?IsXactLinkable@CPacket@@QEBAHXZ`
- size: `30`
- prototype: `__int64 __fastcall(CPacket *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d69c`
- `0x14001e4c8`

## callees

- `0x140017adc`

## pseudocode

```c
_BOOL8 __fastcall CPacket::IsXactLinkable(CPacket *this)
{
  return (*((_DWORD *)this + 13) & 0x30000000) == 0x30000000 && *((_DWORD *)this + 4) != -1;
}

```

## disassembly

```asm
0x140017adc  mov     eax, [rcx+34h]
0x140017adf  mov     edx, 30000000h
0x140017ae4  and     eax, edx
0x140017ae6  cmp     eax, edx
0x140017ae8  jnz     short loc_140017AF7
0x140017aea  cmp     dword ptr [rcx+10h], 0FFFFFFFFh
0x140017aee  jz      short loc_140017AF7
0x140017af0  mov     eax, 1
0x140017af5  retn
0x140017af7  xor     eax, eax
0x140017af9  retn
```
