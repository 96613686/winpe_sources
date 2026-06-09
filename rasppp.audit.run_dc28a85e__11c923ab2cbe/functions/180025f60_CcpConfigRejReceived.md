# CcpConfigRejReceived

- ea: `0x180025f60`
- end: `0x180026040`
- name: `CcpConfigRejReceived`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180025f60`
- `0x1800264e8`
- `0x180033a74`

## pseudocode

```c
__int64 __fastcall CcpConfigRejReceived(__int64 a1, unsigned __int8 *a2)
{
  _BYTE *v2; // rbx
  int v4; // esi
  unsigned int *v5; // rdi
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  _BYTE Buf1[512]; // [rsp+20h] [rbp-238h] BYREF

  v2 = a2 + 4;
  v4 = (a2[2] << 8) + a2[3] - 4;
  while ( (unsigned int)v4 >= 2 )
  {
    if ( v2[1] < 2u )
      return 722;
    v4 -= (unsigned __int8)v2[1];
    if ( v4 < 0 )
      return 722;
    v5 = (unsigned int *)(a1 + 404);
    result = CcpMakeOption(a1 + 404, (unsigned __int8)*v2, Buf1, 500);
    if ( (_DWORD)result )
      return result;
    if ( memcmp_0(Buf1, v2, (unsigned __int8)v2[1]) )
      return 722;
    if ( *v2 != 0xFF )
    {
      v7 = *v5;
      if ( *v2 )
      {
        if ( *v2 == 18 )
          v8 = v7 & 0xFFFFFFFE;
        else
          v8 = v7 & 0xFFFFFFFB;
      }
      else
      {
        v8 = v7 & 0xFFFFFFFD;
      }
      *v5 = v8;
    }
    v2 += (unsigned __int8)v2[1];
  }
  return *(_DWORD *)(a1 + 404) == 0 ? 0x2DC : 0;
}

```

## disassembly

```asm
0x180025f60  push    rbx
0x180025f62  push    rbp
0x180025f63  push    rsi
0x180025f64  push    rdi
0x180025f65  sub     rsp, 238h
0x180025f6c  mov     rax, cs:__security_cookie
0x180025f73  xor     rax, rsp
0x180025f76  mov     [rsp+258h+var_38], rax
0x180025f7e  movzx   r8d, byte ptr [rdx+2]
0x180025f83  lea     rbx, [rdx+4]
0x180025f87  movzx   esi, byte ptr [rdx+3]
0x180025f8b  mov     rbp, rcx
0x180025f8e  shl     r8d, 8
0x180025f92  add     esi, 0FFFFFFFCh
0x180025f95  add     esi, r8d
0x180025f98  cmp     esi, 2
0x180025f9b  jb      short loc_180026012
0x180025f9d  cmp     byte ptr [rbx+1], 2
0x180025fa1  jb      short loc_18002600B
0x180025fa3  movzx   eax, byte ptr [rbx+1]
0x180025fa7  sub     esi, eax
0x180025fa9  js      short loc_18002600B
0x180025fab  movzx   edx, byte ptr [rbx]
0x180025fae  lea     rdi, [rbp+194h]
0x180025fb5  mov     rcx, rdi
0x180025fb8  lea     r8, [rsp+258h+Buf1]
0x180025fbd  mov     r9d, 1F4h
0x180025fc3  call    CcpMakeOption
0x180025fc8  test    eax, eax
0x180025fca  jnz     short loc_180026023
0x180025fcc  movzx   r8d, byte ptr [rbx+1]; Size
0x180025fd1  lea     rcx, [rsp+258h+Buf1]; Buf1
0x180025fd6  mov     rdx, rbx; Buf2
0x180025fd9  call    memcmp_0
0x180025fde  test    eax, eax
0x180025fe0  jnz     short loc_18002600B
0x180025fe2  cmp     byte ptr [rbx], 0FEh
0x180025fe5  ja      short loc_180026002
0x180025fe7  cmp     byte ptr [rbx], 0
0x180025fea  mov     eax, [rdi]
0x180025fec  jz      short loc_180025FFD
0x180025fee  cmp     byte ptr [rbx], 12h
0x180025ff1  jz      short loc_180025FF8
0x180025ff3  and     eax, 0FFFFFFFBh
0x180025ff6  jmp     short loc_180026000
0x180025ff8  and     eax, 0FFFFFFFEh
0x180025ffb  jmp     short loc_180026000
0x180025ffd  and     eax, 0FFFFFFFDh
0x180026000  mov     [rdi], eax
0x180026002  movzx   eax, byte ptr [rbx+1]
0x180026006  add     rbx, rax
0x180026009  jmp     short loc_180025F98
0x18002600b  mov     eax, 2D2h
0x180026010  jmp     short loc_180026023
0x180026012  mov     eax, [rbp+194h]
0x180026018  neg     eax
0x18002601a  sbb     eax, eax
0x18002601c  not     eax
0x18002601e  and     eax, 2DCh
0x180026023  mov     rcx, [rsp+258h+var_38]
0x18002602b  xor     rcx, rsp; StackCookie
0x18002602e  call    __security_check_cookie
0x180026033  add     rsp, 238h
0x18002603a  pop     rdi
0x18002603b  pop     rsi
0x18002603c  pop     rbp
0x18002603d  pop     rbx
0x18002603e  retn
```
