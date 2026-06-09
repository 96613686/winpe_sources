# LcpMakeConfigResult

- ea: `0x1800073d0`
- end: `0x18000763a`
- name: `LcpMakeConfigResult`
- size: `618`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800060b4`
- `0x180006118`
- `0x1800073d0`
- `0x180008048`
- `0x1800081cc`
- `0x180032460`

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
    v16 = CheckOption(a1, a1 + 1296, v8, 1);
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
0x1800073d0  push    rbx
0x1800073d2  push    rbp
0x1800073d3  push    rsi
0x1800073d4  push    rdi
0x1800073d5  push    r12
0x1800073d7  push    r13
0x1800073d9  push    r14
0x1800073db  push    r15
0x1800073dd  sub     rsp, 28h
0x1800073e1  mov     rdi, rcx
0x1800073e4  lea     eax, [r9-4]
0x1800073e8  movzx   ecx, byte ptr [rdx+3]
0x1800073ec  lea     r15, [r8+4]
0x1800073f0  mov     r14, r8
0x1800073f3  mov     [rsp+68h+arg_0], eax
0x1800073f7  movzx   r8d, byte ptr [rdx+2]
0x1800073fc  lea     rsi, [rdx+4]
0x180007400  lea     r13, [rdi+580h]
0x180007407  shl     r8d, 8
0x18000740b  add     ecx, 0FFFFFFFCh
0x18000740e  mov     dword ptr [r13+0], 0
0x180007416  mov     ebp, r9d
0x180007419  mov     [rsp+68h+arg_10], rax
0x180007421  mov     ebx, 2
0x180007426  mov     r12d, eax
0x180007429  add     ecx, r8d
0x18000742c  mov     [rsp+68h+arg_8], ebx
0x180007430  mov     [rsp+68h+arg_18], ebx
0x180007437  cmp     ecx, 2
0x18000743a  jb      loc_180007521
0x180007440  cmp     byte ptr [rsi+1], 2
0x180007444  jb      loc_180007517
0x18000744a  movzx   eax, byte ptr [rsi+1]
0x18000744e  sub     ecx, eax
0x180007450  mov     [rsp+68h+arg_18], ecx
0x180007457  js      loc_180007517
0x18000745d  lea     rdx, [rdi+510h]
0x180007464  mov     r9d, 1
0x18000746a  mov     r8, rsi
0x18000746d  mov     rcx, rdi
0x180007470  call    CheckOption
0x180007475  mov     edx, eax
0x180007477  cmp     ebx, 2
0x18000747a  jnz     short loc_180007480
0x18000747c  cmp     eax, ebx
0x18000747e  jnz     short loc_18000748A
0x180007480  cmp     ebx, 3
0x180007483  jnz     short loc_180007498
0x180007485  cmp     edx, 4
0x180007488  jnz     short loc_18000749D
0x18000748a  mov     r12d, dword ptr [rsp+68h+arg_10]
0x180007492  lea     r15, [r14+4]
0x180007496  mov     ebx, edx
0x180007498  cmp     edx, 4
0x18000749b  jz      short loc_1800074AF
0x18000749d  cmp     byte ptr [rsi], 17h
0x1800074a0  ja      short loc_1800074AF
0x1800074a2  mov     cl, [rsi]
0x1800074a4  mov     eax, 1
0x1800074a9  shl     eax, cl
0x1800074ab  or      [r13+0], eax
0x1800074af  cmp     edx, ebx
0x1800074b1  jnz     short loc_180007504
0x1800074b3  movzx   eax, byte ptr [rsi+1]
0x1800074b7  cmp     r12d, eax
0x1800074ba  jb      short loc_180007517
0x1800074bc  cmp     edx, 4
0x1800074bf  jz      short loc_1800074EB
0x1800074c1  cmp     edx, 3
0x1800074c4  jnz     short loc_1800074D0
0x1800074c6  cmp     [rsp+68h+arg_20], 0
0x1800074ce  jnz     short loc_1800074EB
0x1800074d0  movzx   edx, byte ptr [rsi]
0x1800074d3  mov     r9d, r12d
0x1800074d6  mov     r8, r15
0x1800074d9  mov     rcx, r13
0x1800074dc  call    MakeOption
0x1800074e1  test    eax, eax
0x1800074e3  jnz     loc_180007629
0x1800074e9  jmp     short loc_1800074F9
0x1800074eb  mov     r8, rax; Size
0x1800074ee  mov     rdx, rsi; Src
0x1800074f1  mov     rcx, r15; void *
0x1800074f4  call    memcpy_0
0x1800074f9  movzx   eax, byte ptr [r15+1]
0x1800074fe  sub     r12d, eax
0x180007501  add     r15, rax
0x180007504  movzx   eax, byte ptr [rsi+1]
0x180007508  mov     ecx, [rsp+68h+arg_18]
0x18000750f  add     rsi, rax
0x180007512  jmp     loc_18000742C
0x180007517  mov     eax, 2D2h
0x18000751c  jmp     loc_180007629
0x180007521  mov     edx, 3
0x180007526  cmp     ebx, edx
0x180007528  jnz     short loc_180007536
0x18000752a  cmp     [rsp+68h+arg_20], 0
0x180007532  mov     al, 4
0x180007534  jnz     short loc_180007538
0x180007536  mov     al, bl
0x180007538  mov     [r14], al
0x18000753b  movzx   ecx, bp
0x18000753e  sub     cx, r12w
0x180007542  movzx   eax, cx
0x180007545  mov     [r14+3], cl
0x180007549  shr     ax, 8
0x18000754d  mov     [r14+2], al
0x180007551  mov     eax, [r13+0]
0x180007555  mov     ecx, [rdi+528h]
0x18000755b  not     eax
0x18000755d  and     ecx, eax
0x18000755f  test    cl, 8
0x180007562  jz      loc_1800075F7
0x180007568  cmp     ebx, 4
0x18000756b  jz      loc_1800075F7
0x180007571  mov     eax, [rdi+514h]
0x180007577  lea     rcx, [rdi+510h]
0x18000757e  not     eax
0x180007580  and     eax, 1
0x180007583  inc     eax
0x180007585  mov     [rdi+518h], eax
0x18000758b  call    MakeAuthProtocolOption
0x180007590  mov     esi, [rsp+68h+arg_0]
0x180007594  lea     rcx, [r14+4]
0x180007598  cmp     ebx, 2
0x18000759b  lea     rdx, [rsp+68h+arg_18]
0x1800075a3  mov     eax, 3
0x1800075a8  mov     r8, r13
0x1800075ab  cmovz   ebx, eax
0x1800075ae  cmp     [rsp+68h+arg_18], 2
0x1800075b6  cmovnz  esi, r12d
0x1800075ba  cmp     [rsp+68h+arg_8], 2
0x1800075bf  lea     r9d, [rax+5]
0x1800075c3  mov     [rsp+68h+arg_18], esi
0x1800075ca  cmovnz  rcx, r15
0x1800075ce  call    BuildOptionList
0x1800075d3  test    eax, eax
0x1800075d5  jnz     short loc_180007629
0x1800075d7  lea     edx, [rax+3]
0x1800075da  sub     bp, si
0x1800075dd  add     bp, word ptr [rsp+68h+arg_18]
0x1800075e5  mov     [r14], dl
0x1800075e8  movzx   eax, bp
0x1800075eb  shr     ax, 8
0x1800075ef  mov     [r14+2], al
0x1800075f3  mov     [r14+3], bpl
0x1800075f7  cmp     byte ptr [r14], 4
0x1800075fb  jnz     short loc_18000760B
0x1800075fd  mov     eax, [rdi+51Ch]
0x180007603  mov     [rdi+518h], eax
0x180007609  jmp     short loc_180007617
0x18000760b  mov     eax, [rdi+518h]
0x180007611  mov     [rdi+51Ch], eax
0x180007617  cmp     ebx, edx
0x180007619  jnz     short loc_180007627
0x18000761b  cmp     edx, [rdi+14h]
0x18000761e  sbb     eax, eax
0x180007620  and     eax, 2E1h
0x180007625  jmp     short loc_180007629
0x180007627  xor     eax, eax
0x180007629  add     rsp, 28h
0x18000762d  pop     r15
0x18000762f  pop     r14
0x180007631  pop     r13
0x180007633  pop     r12
0x180007635  pop     rdi
0x180007636  pop     rsi
0x180007637  pop     rbp
0x180007638  pop     rbx
0x180007639  retn
```
