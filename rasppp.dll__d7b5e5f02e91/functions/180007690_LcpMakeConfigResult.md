# LcpMakeConfigResult

- ea: `0x180007690`
- end: `0x1800078fb`
- name: `LcpMakeConfigResult`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006328`
- `0x18000638c`
- `0x180007690`
- `0x180008338`
- `0x1800084e4`
- `0x180033a80`

## pseudocode

```c
__int64 __fastcall LcpMakeConfigResult(__int64 a1, unsigned __int8 *a2, char *a3, int a4, int a5)
{
  unsigned __int8 *v6; // r15
  unsigned __int8 *v8; // rsi
  _DWORD *v9; // r13
  int v10; // r8d
  int v11; // ecx
  __int16 v12; // bp
  int v13; // ebx
  unsigned int v14; // r12d
  unsigned int v15; // ecx
  int v16; // eax
  __int64 result; // rax
  __int64 v18; // rax
  char v19; // al
  unsigned int v20; // esi
  unsigned __int8 *v21; // rcx
  __int16 v22; // bp
  unsigned int v23; // [rsp+70h] [rbp+8h]
  int v24; // [rsp+78h] [rbp+10h]
  unsigned int v25; // [rsp+80h] [rbp+18h]
  int v26; // [rsp+88h] [rbp+20h] BYREF

  v6 = (unsigned __int8 *)(a3 + 4);
  v23 = a4 - 4;
  v8 = a2 + 4;
  v9 = (_DWORD *)(a1 + 1408);
  v10 = a2[2] << 8;
  v11 = a2[3] - 4;
  *v9 = 0;
  v12 = a4;
  v25 = a4 - 4;
  v13 = 2;
  v14 = a4 - 4;
  v15 = v10 + v11;
  while ( 1 )
  {
    v24 = v13;
    v26 = v13;
    if ( v15 < 2 )
      break;
    if ( v8[1] < 2u )
      return 722;
    v26 = v15 - v8[1];
    if ( v26 < 0 )
      return 722;
    v16 = CheckOption((_DWORD *)a1, a1 + 1296, v8, 1);
    if ( v13 == 2 && v16 != 2 )
      goto LABEL_9;
    if ( v13 != 3 )
      goto LABEL_10;
    if ( v16 == 4 )
    {
LABEL_9:
      v14 = v25;
      v6 = (unsigned __int8 *)(a3 + 4);
      v13 = v16;
LABEL_10:
      if ( v16 == 4 )
        goto LABEL_13;
    }
    if ( *v8 <= 0x17u )
      *v9 |= 1 << *v8;
LABEL_13:
    if ( v16 == v13 )
    {
      if ( v14 < v8[1] )
        return 722;
      if ( v16 == 4 || v16 == 3 && a5 )
      {
        memcpy_0(v6, v8, v8[1]);
      }
      else
      {
        result = MakeOption(a1 + 1408, *v8, v6, v14);
        if ( (_DWORD)result )
          return result;
      }
      v18 = v6[1];
      v14 -= v18;
      v6 += v18;
    }
    v15 = v26;
    v8 += v8[1];
  }
  if ( v13 != 3 || (v19 = 4, !a5) )
    v19 = v13;
  *a3 = v19;
  a3[3] = v12 - v14;
  a3[2] = (unsigned __int16)(v12 - v14) >> 8;
  if ( ((unsigned __int8)~*(_BYTE *)v9 & *(_BYTE *)(a1 + 1320) & 8) == 0 || v13 == 4 )
  {
LABEL_37:
    if ( *a3 == 4 )
      *(_DWORD *)(a1 + 1304) = *(_DWORD *)(a1 + 1308);
    else
      *(_DWORD *)(a1 + 1308) = *(_DWORD *)(a1 + 1304);
    if ( v13 == 3 )
      return *(_DWORD *)(a1 + 20) > 3u ? 0x2E1 : 0;
    else
      return 0;
  }
  else
  {
    *(_DWORD *)(a1 + 1304) = ((*(_DWORD *)(a1 + 1300) & 1) == 0) + 1;
    MakeAuthProtocolOption(a1 + 1296);
    v20 = v23;
    v21 = (unsigned __int8 *)(a3 + 4);
    if ( v13 == 2 )
      v13 = 3;
    if ( v26 != 2 )
      v20 = v14;
    v26 = v20;
    if ( v24 != 2 )
      v21 = v6;
    result = BuildOptionList(v21, &v26, a1 + 1408, 8);
    if ( !(_DWORD)result )
    {
      v22 = v26 + v12 - v20;
      *a3 = 3;
      a3[2] = HIBYTE(v22);
      a3[3] = v22;
      goto LABEL_37;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007690  push    rbx
0x180007692  push    rbp
0x180007693  push    rsi
0x180007694  push    rdi
0x180007695  push    r12
0x180007697  push    r13
0x180007699  push    r14
0x18000769b  push    r15
0x18000769d  sub     rsp, 28h
0x1800076a1  mov     rdi, rcx
0x1800076a4  lea     eax, [r9-4]
0x1800076a8  movzx   ecx, byte ptr [rdx+3]
0x1800076ac  lea     r15, [r8+4]
0x1800076b0  mov     r14, r8
0x1800076b3  mov     [rsp+68h+arg_0], eax
0x1800076b7  movzx   r8d, byte ptr [rdx+2]
0x1800076bc  lea     rsi, [rdx+4]
0x1800076c0  lea     r13, [rdi+580h]
0x1800076c7  shl     r8d, 8
0x1800076cb  add     ecx, 0FFFFFFFCh
0x1800076ce  mov     dword ptr [r13+0], 0
0x1800076d6  mov     ebp, r9d
0x1800076d9  mov     [rsp+68h+arg_10], rax
0x1800076e1  mov     ebx, 2
0x1800076e6  mov     r12d, eax
0x1800076e9  add     ecx, r8d
0x1800076ec  mov     [rsp+68h+arg_8], ebx
0x1800076f0  mov     [rsp+68h+arg_18], ebx
0x1800076f7  cmp     ecx, 2
0x1800076fa  jb      loc_1800077E1
0x180007700  cmp     byte ptr [rsi+1], 2
0x180007704  jb      loc_1800077D7
0x18000770a  movzx   eax, byte ptr [rsi+1]
0x18000770e  sub     ecx, eax
0x180007710  mov     [rsp+68h+arg_18], ecx
0x180007717  js      loc_1800077D7
0x18000771d  lea     rdx, [rdi+510h]
0x180007724  mov     r9d, 1
0x18000772a  mov     r8, rsi
0x18000772d  mov     rcx, rdi
0x180007730  call    CheckOption
0x180007735  mov     edx, eax
0x180007737  cmp     ebx, 2
0x18000773a  jnz     short loc_180007740
0x18000773c  cmp     eax, ebx
0x18000773e  jnz     short loc_18000774A
0x180007740  cmp     ebx, 3
0x180007743  jnz     short loc_180007758
0x180007745  cmp     edx, 4
0x180007748  jnz     short loc_18000775D
0x18000774a  mov     r12d, dword ptr [rsp+68h+arg_10]
0x180007752  lea     r15, [r14+4]
0x180007756  mov     ebx, edx
0x180007758  cmp     edx, 4
0x18000775b  jz      short loc_18000776F
0x18000775d  cmp     byte ptr [rsi], 17h
0x180007760  ja      short loc_18000776F
0x180007762  mov     cl, [rsi]
0x180007764  mov     eax, 1
0x180007769  shl     eax, cl
0x18000776b  or      [r13+0], eax
0x18000776f  cmp     edx, ebx
0x180007771  jnz     short loc_1800077C4
0x180007773  movzx   eax, byte ptr [rsi+1]
0x180007777  cmp     r12d, eax
0x18000777a  jb      short loc_1800077D7
0x18000777c  cmp     edx, 4
0x18000777f  jz      short loc_1800077AB
0x180007781  cmp     edx, 3
0x180007784  jnz     short loc_180007790
0x180007786  cmp     [rsp+68h+arg_20], 0
0x18000778e  jnz     short loc_1800077AB
0x180007790  movzx   edx, byte ptr [rsi]
0x180007793  mov     r9d, r12d
0x180007796  mov     r8, r15
0x180007799  mov     rcx, r13
0x18000779c  call    MakeOption
0x1800077a1  test    eax, eax
0x1800077a3  jnz     loc_1800078E9
0x1800077a9  jmp     short loc_1800077B9
0x1800077ab  mov     r8, rax; Size
0x1800077ae  mov     rdx, rsi; Src
0x1800077b1  mov     rcx, r15; void *
0x1800077b4  call    memcpy_0
0x1800077b9  movzx   eax, byte ptr [r15+1]
0x1800077be  sub     r12d, eax
0x1800077c1  add     r15, rax
0x1800077c4  movzx   eax, byte ptr [rsi+1]
0x1800077c8  mov     ecx, [rsp+68h+arg_18]
0x1800077cf  add     rsi, rax
0x1800077d2  jmp     loc_1800076EC
0x1800077d7  mov     eax, 2D2h
0x1800077dc  jmp     loc_1800078E9
0x1800077e1  mov     edx, 3
0x1800077e6  cmp     ebx, edx
0x1800077e8  jnz     short loc_1800077F6
0x1800077ea  cmp     [rsp+68h+arg_20], 0
0x1800077f2  mov     al, 4
0x1800077f4  jnz     short loc_1800077F8
0x1800077f6  mov     al, bl
0x1800077f8  mov     [r14], al
0x1800077fb  movzx   ecx, bp
0x1800077fe  sub     cx, r12w
0x180007802  movzx   eax, cx
0x180007805  mov     [r14+3], cl
0x180007809  shr     ax, 8
0x18000780d  mov     [r14+2], al
0x180007811  mov     eax, [r13+0]
0x180007815  mov     ecx, [rdi+528h]
0x18000781b  not     eax
0x18000781d  and     ecx, eax
0x18000781f  test    cl, 8
0x180007822  jz      loc_1800078B7
0x180007828  cmp     ebx, 4
0x18000782b  jz      loc_1800078B7
0x180007831  mov     eax, [rdi+514h]
0x180007837  lea     rcx, [rdi+510h]
0x18000783e  not     eax
0x180007840  and     eax, 1
0x180007843  inc     eax
0x180007845  mov     [rdi+518h], eax
0x18000784b  call    MakeAuthProtocolOption
0x180007850  mov     esi, [rsp+68h+arg_0]
0x180007854  lea     rcx, [r14+4]
0x180007858  cmp     ebx, 2
0x18000785b  lea     rdx, [rsp+68h+arg_18]
0x180007863  mov     eax, 3
0x180007868  mov     r8, r13
0x18000786b  cmovz   ebx, eax
0x18000786e  cmp     [rsp+68h+arg_18], 2
0x180007876  cmovnz  esi, r12d
0x18000787a  cmp     [rsp+68h+arg_8], 2
0x18000787f  lea     r9d, [rax+5]
0x180007883  mov     [rsp+68h+arg_18], esi
0x18000788a  cmovnz  rcx, r15
0x18000788e  call    BuildOptionList
0x180007893  test    eax, eax
0x180007895  jnz     short loc_1800078E9
0x180007897  lea     edx, [rax+3]
0x18000789a  sub     bp, si
0x18000789d  add     bp, word ptr [rsp+68h+arg_18]
0x1800078a5  mov     [r14], dl
0x1800078a8  movzx   eax, bp
0x1800078ab  shr     ax, 8
0x1800078af  mov     [r14+2], al
0x1800078b3  mov     [r14+3], bpl
0x1800078b7  cmp     byte ptr [r14], 4
0x1800078bb  jnz     short loc_1800078CB
0x1800078bd  mov     eax, [rdi+51Ch]
0x1800078c3  mov     [rdi+518h], eax
0x1800078c9  jmp     short loc_1800078D7
0x1800078cb  mov     eax, [rdi+518h]
0x1800078d1  mov     [rdi+51Ch], eax
0x1800078d7  cmp     ebx, edx
0x1800078d9  jnz     short loc_1800078E7
0x1800078db  cmp     edx, [rdi+14h]
0x1800078de  sbb     eax, eax
0x1800078e0  and     eax, 2E1h
0x1800078e5  jmp     short loc_1800078E9
0x1800078e7  xor     eax, eax
0x1800078e9  add     rsp, 28h
0x1800078ed  pop     r15
0x1800078ef  pop     r14
0x1800078f1  pop     r13
0x1800078f3  pop     r12
0x1800078f5  pop     rdi
0x1800078f6  pop     rsi
0x1800078f7  pop     rbp
0x1800078f8  pop     rbx
0x1800078f9  retn
```
