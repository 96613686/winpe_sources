# LcpConfigNakReceived

- ea: `0x180007140`
- end: `0x1800071e8`
- name: `LcpConfigNakReceived`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000638c`
- `0x180007140`

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
0x180007140  push    rbx
0x180007142  push    rbp
0x180007143  push    rsi
0x180007144  push    rdi
0x180007145  sub     rsp, 28h
0x180007149  movzx   r8d, byte ptr [rdx+2]
0x18000714e  lea     rbx, [rdx+4]
0x180007152  movzx   esi, byte ptr [rdx+3]
0x180007156  lea     rbp, [rcx+448h]
0x18000715d  shl     r8d, 8
0x180007161  add     esi, 0FFFFFFFCh
0x180007164  add     esi, r8d
0x180007167  mov     rdi, rcx
0x18000716a  cmp     esi, 2
0x18000716d  jb      short loc_1800071DC
0x18000716f  movzx   eax, byte ptr [rbx+1]
0x180007173  test    al, al
0x180007175  jz      short loc_1800071D5
0x180007177  sub     esi, eax
0x180007179  js      short loc_1800071D5
0x18000717b  cmp     byte ptr [rbx], 17h
0x18000717e  ja      short loc_1800071A0
0x180007180  mov     cl, [rbx]
0x180007182  mov     eax, 1
0x180007187  shl     eax, cl
0x180007189  test    [rbp+0], eax
0x18000718c  jz      short loc_1800071A0
0x18000718e  mov     ecx, [rdi+4B8h]
0x180007194  test    eax, ecx
0x180007196  jnz     short loc_1800071A0
0x180007198  or      ecx, eax
0x18000719a  mov     [rdi+4B8h], ecx
0x1800071a0  xor     r9d, r9d
0x1800071a3  mov     r8, rbx
0x1800071a6  mov     rdx, rbp
0x1800071a9  mov     rcx, rdi
0x1800071ac  call    CheckOption
0x1800071b1  cmp     eax, 4
0x1800071b4  jnz     short loc_1800071CC
0x1800071b6  cmp     byte ptr [rbx], 17h
0x1800071b9  ja      short loc_1800071CC
0x1800071bb  mov     cl, [rbx]
0x1800071bd  mov     eax, 1
0x1800071c2  shl     eax, cl
0x1800071c4  not     eax
0x1800071c6  and     [rdi+4B8h], eax
0x1800071cc  movzx   eax, byte ptr [rbx+1]
0x1800071d0  add     rbx, rax
0x1800071d3  jmp     short loc_18000716A
0x1800071d5  mov     eax, 2D2h
0x1800071da  jmp     short loc_1800071DE
0x1800071dc  xor     eax, eax
0x1800071de  add     rsp, 28h
0x1800071e2  pop     rdi
0x1800071e3  pop     rsi
0x1800071e4  pop     rbp
0x1800071e5  pop     rbx
0x1800071e6  retn
```
