# LcpConfigRejReceived

- ea: `0x1800071f0`
- end: `0x1800072ff`
- name: `LcpConfigRejReceived`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x1800071f0`
- `0x1800084e4`
- `0x180033a74`

## pseudocode

```c
__int64 __fastcall LcpConfigRejReceived(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rbx
  unsigned int v4; // ecx
  int v5; // ebp
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  __int64 result; // rax
  _BYTE Buf1[1504]; // [rsp+20h] [rbp-608h] BYREF

  v2 = a2 + 4;
  v4 = 0;
  v5 = (a2[2] << 8) + a2[3] - 4;
  while ( (unsigned int)v5 >= 2 )
  {
    v6 = v2[1];
    if ( !(_BYTE)v6 )
      return 722;
    v5 -= v6;
    if ( v5 < 0 )
      return 722;
    v7 = *v2;
    if ( (unsigned __int8)v7 <= 0x17u )
    {
      if ( (unsigned int)v7 < v4 )
        return 722;
      v8 = *(_DWORD *)(a1 + 1208);
      if ( !_bittest(&v8, v7) )
        return 722;
    }
    if ( (*(_BYTE *)(a1 + 1120) & 8) != 0 && (_BYTE)v7 == 3 && (*(_DWORD *)(a1 + 24) & 0x4000) == 0 )
      return 919;
    result = MakeOption(a1 + 1208, v7, Buf1, 1500);
    if ( (_DWORD)result )
      return result;
    if ( memcmp_0(Buf1, v2, v2[1]) )
      return 722;
    v4 = *v2;
    if ( (unsigned __int8)v4 <= 0x17u )
      *(_DWORD *)(a1 + 1208) &= ~(1 << v4);
    v2 += v2[1];
  }
  return 0;
}

```

## disassembly

```asm
0x1800071f0  mov     [rsp+arg_10], rbx
0x1800071f5  push    rbp
0x1800071f6  push    rsi
0x1800071f7  push    rdi
0x1800071f8  sub     rsp, 610h
0x1800071ff  mov     rax, cs:__security_cookie
0x180007206  xor     rax, rsp
0x180007209  mov     [rsp+628h+var_28], rax
0x180007211  movzx   r8d, byte ptr [rdx+2]
0x180007216  lea     rbx, [rdx+4]
0x18000721a  movzx   ebp, byte ptr [rdx+3]
0x18000721e  mov     rsi, rcx
0x180007221  xor     ecx, ecx
0x180007223  shl     r8d, 8
0x180007227  add     ebp, 0FFFFFFFCh
0x18000722a  add     ebp, r8d
0x18000722d  lea     rdi, [rsi+4B8h]
0x180007234  cmp     ebp, 2
0x180007237  jb      loc_1800072D9
0x18000723d  movzx   eax, byte ptr [rbx+1]
0x180007241  test    al, al
0x180007243  jz      loc_1800072D2
0x180007249  sub     ebp, eax
0x18000724b  js      loc_1800072D2
0x180007251  movzx   edx, byte ptr [rbx]
0x180007254  cmp     dl, 17h
0x180007257  ja      short loc_180007268
0x180007259  cmp     edx, ecx
0x18000725b  jb      short loc_1800072D2
0x18000725d  mov     eax, [rsi+4B8h]
0x180007263  bt      eax, edx
0x180007266  jnb     short loc_1800072D2
0x180007268  test    byte ptr [rsi+460h], 8
0x18000726f  jz      short loc_18000727F
0x180007271  cmp     dl, 3
0x180007274  jnz     short loc_18000727F
0x180007276  test    dword ptr [rsi+18h], 4000h
0x18000727d  jz      short loc_1800072CB
0x18000727f  mov     r9d, 5DCh
0x180007285  lea     r8, [rsp+628h+Buf1]
0x18000728a  mov     rcx, rdi
0x18000728d  call    MakeOption
0x180007292  test    eax, eax
0x180007294  jnz     short loc_1800072DB
0x180007296  movzx   r8d, byte ptr [rbx+1]; Size
0x18000729b  lea     rcx, [rsp+628h+Buf1]; Buf1
0x1800072a0  mov     rdx, rbx; Buf2
0x1800072a3  call    memcmp_0
0x1800072a8  test    eax, eax
0x1800072aa  jnz     short loc_1800072D2
0x1800072ac  movzx   ecx, byte ptr [rbx]
0x1800072af  cmp     cl, 17h
0x1800072b2  ja      short loc_1800072BF
0x1800072b4  mov     eax, 1
0x1800072b9  shl     eax, cl
0x1800072bb  not     eax
0x1800072bd  and     [rdi], eax
0x1800072bf  movzx   eax, byte ptr [rbx+1]
0x1800072c3  add     rbx, rax
0x1800072c6  jmp     loc_180007234
0x1800072cb  mov     eax, 397h
0x1800072d0  jmp     short loc_1800072DB
0x1800072d2  mov     eax, 2D2h
0x1800072d7  jmp     short loc_1800072DB
0x1800072d9  xor     eax, eax
0x1800072db  mov     rcx, [rsp+628h+var_28]
0x1800072e3  xor     rcx, rsp; StackCookie
0x1800072e6  call    __security_check_cookie
0x1800072eb  mov     rbx, [rsp+628h+arg_10]
0x1800072f3  add     rsp, 610h
0x1800072fa  pop     rdi
0x1800072fb  pop     rsi
0x1800072fc  pop     rbp
0x1800072fd  retn
```
