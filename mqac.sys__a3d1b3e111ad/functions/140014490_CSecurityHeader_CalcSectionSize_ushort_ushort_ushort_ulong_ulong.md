# CSecurityHeader::CalcSectionSize(ushort,ushort,ushort,ulong,ulong)

- ea: `0x140014490`
- end: `0x140014532`
- name: `?CalcSectionSize@CSecurityHeader@@SAKGGGKK@Z`
- size: `162`
- prototype: `unsigned int __fastcall(unsigned __int16, unsigned __int16, unsigned __int16, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013b94`

## callees

- `0x140014490`

## pseudocode

```c
unsigned __int64 __fastcall CSecurityHeader::CalcSectionSize(
        unsigned __int16 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned __int64 result; // rax

  result = 0;
  if ( a1 || a2 || a3 || a4 || a5 )
  {
    if ( ((a1 + 3) & 0xFFFFFFFC) < a1 )
      return 0xFFFFFFFFLL;
    if ( ((a2 + 3) & 0xFFFFFFFC) < a2 )
      return 0xFFFFFFFFLL;
    if ( ((a3 + 3) & 0xFFFFFFFC) < a3 )
      return 0xFFFFFFFFLL;
    if ( ((a4 + 3) & 0xFFFFFFFC) < a4 )
      return 0xFFFFFFFFLL;
    if ( ((a5 + 3) & 0xFFFFFFFC) < a5 )
      return 0xFFFFFFFFLL;
    result = ((a5 + 3) & 0xFFFFFFFC)
           + ((a1 + 3) & 0xFFFFFFFC)
           + ((a2 + 3) & 0xFFFFFFFC)
           + (unsigned __int64)((a3 + 3) & 0xFFFFFFFC)
           + ((a4 + 3) & 0xFFFFFFFC)
           + 16LL;
    if ( result >= 0xFFFFFFFF )
      return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x140014490  push    rbx
0x140014492  push    rsi
0x140014493  push    rdi
0x140014494  mov     r10d, [rsp+18h+arg_20]
0x140014499  xor     eax, eax
0x14001449b  test    cx, cx
0x14001449e  jnz     short loc_1400144B5
0x1400144a0  test    dx, dx
0x1400144a3  jnz     short loc_1400144B5
0x1400144a5  test    r8w, r8w
0x1400144a9  jnz     short loc_1400144B5
0x1400144ab  test    r9d, r9d
0x1400144ae  jnz     short loc_1400144B5
0x1400144b0  test    r10d, r10d
0x1400144b3  jz      short loc_14001452D
0x1400144b5  movzx   ecx, cx
0x1400144b8  mov     edi, 0FFFFFFFCh
0x1400144bd  mov     esi, 0FFFFFFFFh
0x1400144c2  lea     ebx, [rcx+3]
0x1400144c5  mov     eax, ebx
0x1400144c7  and     eax, edi
0x1400144c9  cmp     eax, ecx
0x1400144cb  jb      short loc_14001452B
0x1400144cd  movzx   ecx, dx
0x1400144d0  lea     r11d, [rcx+3]
0x1400144d4  mov     eax, r11d
0x1400144d7  and     eax, edi
0x1400144d9  cmp     eax, ecx
0x1400144db  jb      short loc_14001452B
0x1400144dd  movzx   ecx, r8w
0x1400144e1  lea     edx, [rcx+3]
0x1400144e4  mov     eax, edx
0x1400144e6  and     eax, edi
0x1400144e8  cmp     eax, ecx
0x1400144ea  jb      short loc_14001452B
0x1400144ec  lea     r8d, [r9+3]
0x1400144f0  mov     eax, r8d
0x1400144f3  and     eax, edi
0x1400144f5  cmp     eax, r9d
0x1400144f8  jb      short loc_14001452B
0x1400144fa  lea     ecx, [r10+3]
0x1400144fe  mov     eax, ecx
0x140014500  and     eax, edi
0x140014502  cmp     eax, r10d
0x140014505  jb      short loc_14001452B
0x140014507  and     rdx, rdi
0x14001450a  and     r11, rdi
0x14001450d  add     rdx, r11
0x140014510  and     r8, rdi
0x140014513  and     rbx, rdi
0x140014516  and     rcx, rdi
0x140014519  add     rdx, rbx
0x14001451c  add     rdx, rcx
0x14001451f  lea     rax, [r8+10h]
0x140014523  add     rax, rdx
0x140014526  cmp     rax, rsi
0x140014529  jb      short loc_14001452D
0x14001452b  mov     eax, esi
0x14001452d  pop     rdi
0x14001452e  pop     rsi
0x14001452f  pop     rbx
0x140014530  retn
```
