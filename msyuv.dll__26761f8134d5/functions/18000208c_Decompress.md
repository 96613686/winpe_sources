# Decompress

- ea: `0x18000208c`
- end: `0x1800021c2`
- name: `Decompress`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x18000208c`
- `0x180002cd4`
- `0x1800030e8`
- `0x1800037a4`
- `0x180003e88`

## pseudocode

```c
__int64 __fastcall Decompress(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r10
  int v3; // r8d
  int v4; // eax
  __int64 v5; // r9
  int v6; // r8d
  int v7; // eax
  __int16 v8; // ax

  if ( a1 && a2 )
  {
    v2 = a2[1];
    if ( *(_DWORD *)(v2 + 4) > 0x4E20u )
      return 4294967289LL;
    v3 = *(_DWORD *)(v2 + 8);
    if ( !v3 )
      return 4294967289LL;
    v4 = -v3;
    if ( v3 > 0 )
      v4 = *(_DWORD *)(v2 + 8);
    if ( v4 > 20000 )
      return 4294967289LL;
    v5 = a2[3];
    if ( *(_DWORD *)(v5 + 4) > 0x4E20u )
      return 4294967289LL;
    v6 = *(_DWORD *)(v5 + 8);
    if ( !v6 )
      return 4294967289LL;
    v7 = -v6;
    if ( v6 > 0 )
      v7 = *(_DWORD *)(v5 + 8);
    if ( v7 > 20000 )
      return 4294967289LL;
    if ( *(_DWORD *)(a1 + 4) != 1498831189 && *(_DWORD *)(a1 + 4) != 844715353 && *(_DWORD *)(a1 + 4) != 1431918169 )
      return 0;
    v8 = *(_WORD *)(v5 + 14);
    switch ( v8 )
    {
      case 8:
        UYVYToRGB8(a1, a2[1], a2[2], v5, a2[4]);
        return 0;
      case 16:
        if ( *(_QWORD *)(a1 + 8) )
        {
          UYVYToRGB16(a1, a2[1], a2[2]);
          return 0;
        }
        break;
      case 24:
        if ( *(_QWORD *)(a1 + 8) )
        {
          UYVYToRGB24(a1, a2[1], a2[2]);
          return 0;
        }
        break;
      case 32:
        if ( *(_QWORD *)(a1 + 8) )
        {
          UYVYToRGB32(a1, a2[1], a2[2]);
          return 0;
        }
        break;
      default:
        return 0;
    }
  }
  return 4294967196LL;
}

```

## disassembly

```asm
0x18000208c  push    rbx
0x18000208e  sub     rsp, 30h
0x180002092  xor     r11d, r11d
0x180002095  test    rcx, rcx
0x180002098  jz      loc_1800021B7
0x18000209e  test    rdx, rdx
0x1800020a1  jz      loc_1800021B7
0x1800020a7  mov     r10, [rdx+8]
0x1800020ab  mov     ebx, 4E20h
0x1800020b0  cmp     [r10+4], ebx
0x1800020b4  ja      loc_1800021B0
0x1800020ba  mov     r8d, [r10+8]
0x1800020be  test    r8d, r8d
0x1800020c1  jz      loc_1800021B0
0x1800020c7  mov     eax, r8d
0x1800020ca  neg     eax
0x1800020cc  cmovs   eax, r8d
0x1800020d0  cmp     eax, ebx
0x1800020d2  jg      loc_1800021B0
0x1800020d8  mov     r9, [rdx+18h]
0x1800020dc  cmp     [r9+4], ebx
0x1800020e0  ja      loc_1800021B0
0x1800020e6  mov     r8d, [r9+8]
0x1800020ea  test    r8d, r8d
0x1800020ed  jz      loc_1800021B0
0x1800020f3  mov     eax, r8d
0x1800020f6  neg     eax
0x1800020f8  cmovs   eax, r8d
0x1800020fc  cmp     eax, ebx
0x1800020fe  jg      loc_1800021B0
0x180002104  cmp     dword ptr [rcx+4], 59565955h
0x18000210b  jz      short loc_180002123
0x18000210d  cmp     dword ptr [rcx+4], 32595559h
0x180002114  jz      short loc_180002123
0x180002116  cmp     dword ptr [rcx+4], 55595659h
0x18000211d  jnz     loc_1800021AC
0x180002123  movzx   eax, word ptr [r9+0Eh]
0x180002128  cmp     ax, 8
0x18000212c  jz      short loc_180002197
0x18000212e  cmp     ax, 10h
0x180002132  jz      short loc_18000217A
0x180002134  cmp     ax, 18h
0x180002138  jz      short loc_18000215D
0x18000213a  cmp     ax, 20h ; ' '
0x18000213e  jnz     short loc_1800021AC
0x180002140  cmp     [rcx+8], r11
0x180002144  jz      short loc_1800021B7
0x180002146  mov     rax, [rdx+20h]
0x18000214a  mov     r8, [rdx+10h]
0x18000214e  mov     rdx, r10
0x180002151  mov     [rsp+38h+var_18], rax
0x180002156  call    UYVYToRGB32
0x18000215b  jmp     short loc_1800021AC
0x18000215d  cmp     [rcx+8], r11
0x180002161  jz      short loc_1800021B7
0x180002163  mov     rax, [rdx+20h]
0x180002167  mov     r8, [rdx+10h]
0x18000216b  mov     rdx, r10
0x18000216e  mov     [rsp+38h+var_18], rax
0x180002173  call    UYVYToRGB24
0x180002178  jmp     short loc_1800021AC
0x18000217a  cmp     [rcx+8], r11
0x18000217e  jz      short loc_1800021B7
0x180002180  mov     rax, [rdx+20h]
0x180002184  mov     r8, [rdx+10h]
0x180002188  mov     rdx, r10
0x18000218b  mov     [rsp+38h+var_18], rax
0x180002190  call    UYVYToRGB16
0x180002195  jmp     short loc_1800021AC
0x180002197  mov     rax, [rdx+20h]
0x18000219b  mov     r8, [rdx+10h]
0x18000219f  mov     rdx, r10
0x1800021a2  mov     [rsp+38h+var_18], rax
0x1800021a7  call    UYVYToRGB8
0x1800021ac  xor     eax, eax
0x1800021ae  jmp     short loc_1800021BC
0x1800021b0  mov     eax, 0FFFFFFF9h
0x1800021b5  jmp     short loc_1800021BC
0x1800021b7  mov     eax, 0FFFFFF9Ch
0x1800021bc  add     rsp, 30h
0x1800021c0  pop     rbx
0x1800021c1  retn
```
