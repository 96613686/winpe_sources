# I8xVerifyMousePnPID

- ea: `0x14000c8b4`
- end: `0x14000c9f0`
- name: `I8xVerifyMousePnPID`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002610`
- `0x140019cfc`

## callees

- `0x14000c8b4`

## pseudocode

```c
char __fastcall I8xVerifyMousePnPID(__int64 a1, __int64 a2)
{
  unsigned __int16 *v3; // rdx
  unsigned __int16 *v4; // rax
  int v5; // r9d
  int v6; // r8d
  __int64 v7; // rax
  unsigned __int16 *i; // rax
  unsigned __int16 *v9; // rcx
  int v10; // r9d
  int v11; // r8d
  __int64 v12; // rcx
  _OWORD v14[11]; // [rsp+0h] [rbp-69h] BYREF
  int v15; // [rsp+B0h] [rbp+47h]

  v3 = *(unsigned __int16 **)(a1 + 1040);
  v15 = 0;
  v14[0] = *(_OWORD *)L"MSH0002";
  v14[2] = xmmword_1400109F0;
  v14[1] = xmmword_1400109E0;
  v14[4] = xmmword_140010A10;
  v14[3] = xmmword_140010A00;
  v14[6] = xmmword_140010A30;
  v14[5] = xmmword_140010A20;
  v14[8] = xmmword_140010A50;
  v14[7] = xmmword_140010A40;
  v14[10] = xmmword_140010A70;
  v14[9] = xmmword_140010A60;
  if ( v3 )
  {
    while ( *v3 )
    {
      v4 = v3;
      do
      {
        v5 = *(unsigned __int16 *)((char *)v4 + a2 - (_QWORD)v3);
        v6 = *v4 - v5;
        if ( v6 )
          break;
        ++v4;
      }
      while ( v5 );
      if ( !v6 )
        return 1;
      v7 = -1;
      do
        ++v7;
      while ( v3[v7] );
      v3 += v7 + 1;
    }
  }
  for ( i = (unsigned __int16 *)v14; *i; i += v12 + 1 )
  {
    v9 = i;
    do
    {
      v10 = *(unsigned __int16 *)((char *)v9 + a2 - (_QWORD)i);
      v11 = *v9 - v10;
      if ( v11 )
        break;
      ++v9;
    }
    while ( v10 );
    if ( !v11 )
      return 1;
    v12 = -1;
    do
      ++v12;
    while ( i[v12] );
  }
  return 0;
}

```

## disassembly

```asm
0x14000c8b4  push    rbp
0x14000c8b6  lea     rbp, [rsp-57h]
0x14000c8bb  sub     rsp, 0C0h
0x14000c8c2  movaps  xmm0, xmmword ptr cs:aMsh0002; "MSH0002"
0x14000c8c9  mov     r10, rdx
0x14000c8cc  movaps  xmm1, cs:xmmword_1400109E0
0x14000c8d3  xor     r11d, r11d
0x14000c8d6  mov     rdx, [rcx+410h]
0x14000c8dd  mov     eax, cs:dword_140010A80
0x14000c8e3  mov     [rbp+57h+var_10], eax
0x14000c8e6  movups  [rbp+57h+var_C0], xmm0
0x14000c8ea  movaps  xmm0, cs:xmmword_1400109F0
0x14000c8f1  movups  [rbp+57h+var_A0], xmm0
0x14000c8f5  movaps  xmm0, cs:xmmword_140010A10
0x14000c8fc  movups  [rbp+57h+var_B0], xmm1
0x14000c900  movaps  xmm1, cs:xmmword_140010A00
0x14000c907  movups  [rbp+57h+var_80], xmm0
0x14000c90b  movaps  xmm0, cs:xmmword_140010A30
0x14000c912  movups  [rbp+57h+var_90], xmm1
0x14000c916  movaps  xmm1, cs:xmmword_140010A20
0x14000c91d  movups  [rbp+57h+var_60], xmm0
0x14000c921  movaps  xmm0, cs:xmmword_140010A50
0x14000c928  movups  [rbp+57h+var_70], xmm1
0x14000c92c  movaps  xmm1, cs:xmmword_140010A40
0x14000c933  movups  [rbp+57h+var_40], xmm0
0x14000c937  movaps  xmm0, cs:xmmword_140010A70
0x14000c93e  movups  [rbp+57h+var_50], xmm1
0x14000c942  movaps  xmm1, cs:xmmword_140010A60
0x14000c949  movups  [rbp+57h+var_20], xmm0
0x14000c94d  movups  [rbp+57h+var_30], xmm1
0x14000c951  test    rdx, rdx
0x14000c954  jz      short loc_14000C999
0x14000c956  cmp     [rdx], r11w
0x14000c95a  jz      short loc_14000C999
0x14000c95c  mov     rcx, r10
0x14000c95f  mov     rax, rdx
0x14000c962  sub     rcx, rdx
0x14000c965  movzx   r8d, word ptr [rax]
0x14000c969  movzx   r9d, word ptr [rax+rcx]
0x14000c96e  sub     r8d, r9d
0x14000c971  jnz     short loc_14000C97C
0x14000c973  add     rax, 2
0x14000c977  test    r9d, r9d
0x14000c97a  jnz     short loc_14000C965
0x14000c97c  test    r8d, r8d
0x14000c97f  jz      short loc_14000C9E0
0x14000c981  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c985  inc     rax
0x14000c988  cmp     [rdx+rax*2], r11w
0x14000c98d  jnz     short loc_14000C985
0x14000c98f  lea     rdx, [rdx+rax*2]
0x14000c993  add     rdx, 2
0x14000c997  jmp     short loc_14000C956
0x14000c999  lea     rax, [rbp+57h+var_C0]
0x14000c99d  cmp     [rax], r11w
0x14000c9a1  jz      short loc_14000C9E4
0x14000c9a3  mov     rdx, r10
0x14000c9a6  mov     rcx, rax
0x14000c9a9  sub     rdx, rax
0x14000c9ac  movzx   r8d, word ptr [rcx]
0x14000c9b0  movzx   r9d, word ptr [rcx+rdx]
0x14000c9b5  sub     r8d, r9d
0x14000c9b8  jnz     short loc_14000C9C3
0x14000c9ba  add     rcx, 2
0x14000c9be  test    r9d, r9d
0x14000c9c1  jnz     short loc_14000C9AC
0x14000c9c3  test    r8d, r8d
0x14000c9c6  jz      short loc_14000C9E0
0x14000c9c8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000c9cc  inc     rcx
0x14000c9cf  cmp     [rax+rcx*2], r11w
0x14000c9d4  jnz     short loc_14000C9CC
0x14000c9d6  lea     rax, [rax+rcx*2]
0x14000c9da  add     rax, 2
0x14000c9de  jmp     short loc_14000C99D
0x14000c9e0  mov     al, 1
0x14000c9e2  jmp     short loc_14000C9E6
0x14000c9e4  xor     al, al
0x14000c9e6  add     rsp, 0C0h
0x14000c9ed  pop     rbp
0x14000c9ee  retn
```
