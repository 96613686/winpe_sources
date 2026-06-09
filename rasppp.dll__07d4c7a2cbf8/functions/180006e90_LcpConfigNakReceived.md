# LcpConfigNakReceived

- ea: `0x180006e90`
- end: `0x180006f37`
- name: `LcpConfigNakReceived`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180006118`
- `0x180006e90`

## pseudocode

```c
__int64 __fastcall LcpConfigNakReceived(__int64 a1, unsigned __int8 *a2)
{
  _BYTE *v2; // rbx
  _DWORD *v3; // rbp
  int v4; // esi
  int v6; // eax
  int v7; // eax
  int v8; // ecx

  v2 = a2 + 4;
  v3 = (_DWORD *)(a1 + 1096);
  v4 = (a2[2] << 8) + a2[3] - 4;
  while ( (unsigned int)v4 >= 2 )
  {
    v6 = (unsigned __int8)v2[1];
    if ( !(_BYTE)v6 )
      return 722;
    v4 -= v6;
    if ( v4 < 0 )
      return 722;
    if ( *v2 <= 0x17u )
    {
      v7 = 1 << *v2;
      if ( (v7 & *v3) != 0 )
      {
        v8 = *(_DWORD *)(a1 + 1208);
        if ( (v8 & v7) == 0 )
          *(_DWORD *)(a1 + 1208) = v7 | v8;
      }
    }
    if ( (unsigned int)CheckOption(a1, v3, v2, 0) == 4 && *v2 <= 0x17u )
      *(_DWORD *)(a1 + 1208) &= ~(1 << *v2);
    v2 += (unsigned __int8)v2[1];
  }
  return 0;
}

```

## disassembly

```asm
0x180006e90  push    rbx
0x180006e92  push    rbp
0x180006e93  push    rsi
0x180006e94  push    rdi
0x180006e95  sub     rsp, 28h
0x180006e99  movzx   r8d, byte ptr [rdx+2]
0x180006e9e  lea     rbx, [rdx+4]
0x180006ea2  movzx   esi, byte ptr [rdx+3]
0x180006ea6  lea     rbp, [rcx+448h]
0x180006ead  shl     r8d, 8
0x180006eb1  add     esi, 0FFFFFFFCh
0x180006eb4  add     esi, r8d
0x180006eb7  mov     rdi, rcx
0x180006eba  cmp     esi, 2
0x180006ebd  jb      short loc_180006F2C
0x180006ebf  movzx   eax, byte ptr [rbx+1]
0x180006ec3  test    al, al
0x180006ec5  jz      short loc_180006F25
0x180006ec7  sub     esi, eax
0x180006ec9  js      short loc_180006F25
0x180006ecb  cmp     byte ptr [rbx], 17h
0x180006ece  ja      short loc_180006EF0
0x180006ed0  mov     cl, [rbx]
0x180006ed2  mov     eax, 1
0x180006ed7  shl     eax, cl
0x180006ed9  test    [rbp+0], eax
0x180006edc  jz      short loc_180006EF0
0x180006ede  mov     ecx, [rdi+4B8h]
0x180006ee4  test    eax, ecx
0x180006ee6  jnz     short loc_180006EF0
0x180006ee8  or      ecx, eax
0x180006eea  mov     [rdi+4B8h], ecx
0x180006ef0  xor     r9d, r9d
0x180006ef3  mov     r8, rbx
0x180006ef6  mov     rdx, rbp
0x180006ef9  mov     rcx, rdi
0x180006efc  call    CheckOption
0x180006f01  cmp     eax, 4
0x180006f04  jnz     short loc_180006F1C
0x180006f06  cmp     byte ptr [rbx], 17h
0x180006f09  ja      short loc_180006F1C
0x180006f0b  mov     cl, [rbx]
0x180006f0d  mov     eax, 1
0x180006f12  shl     eax, cl
0x180006f14  not     eax
0x180006f16  and     [rdi+4B8h], eax
0x180006f1c  movzx   eax, byte ptr [rbx+1]
0x180006f20  add     rbx, rax
0x180006f23  jmp     short loc_180006EBA
0x180006f25  mov     eax, 2D2h
0x180006f2a  jmp     short loc_180006F2E
0x180006f2c  xor     eax, eax
0x180006f2e  add     rsp, 28h
0x180006f32  pop     rdi
0x180006f33  pop     rsi
0x180006f34  pop     rbp
0x180006f35  pop     rbx
0x180006f36  retn
```
