# LmpGetTokens

- ea: `0x14004e60c`
- end: `0x14004e84f`
- name: `LmpGetTokens`
- size: `579`
- prototype: `__int64 __fastcall(void *Buf1, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14004d4b0`
- `0x14004da30`

## callees

- `0x140031440`
- `0x140044180`
- `0x14004e60c`
- `0x14004e858`

## pseudocode

```c
__int64 __fastcall LmpGetTokens(_BYTE *Buf1, _QWORD *a2, int *a3)
{
  int v3; // r13d
  _BYTE *v5; // rsi
  int v6; // r15d
  unsigned int v7; // ebx
  int v8; // edi
  int v9; // ebp
  int v10; // r12d
  __int64 v11; // rdx
  __int64 IsKeyWord; // rax
  int v14; // ecx
  __int64 v15; // rax
  int v16; // eax
  _BYTE *v17; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp+10h]
  int *v19; // [rsp+70h] [rbp+18h]

  v19 = a3;
  v18 = a2;
  v3 = *a3;
  v5 = 0;
  memset(a2, 0, 8LL * *a3);
  v6 = 0;
  v7 = 1;
  v8 = 0;
  v9 = v3;
  v10 = 0;
  while ( 1 )
  {
    v11 = (unsigned __int8)*Buf1;
    v17 = Buf1;
    if ( !(_BYTE)v11 )
      break;
    switch ( (_DWORD)v11 )
    {
      case 9:
        goto LABEL_18;
      case 0xA:
      case 0xD:
        goto LABEL_26;
      case 0x20:
LABEL_18:
        if ( v10 )
          goto LABEL_16;
        if ( v6 == 2 )
        {
          *Buf1 = 0;
          v6 = 1;
          if ( v8 == v9 )
            goto LABEL_28;
        }
        break;
      case 0x22:
        if ( v6 != 2 || !v10 )
        {
          if ( v9 > v3 || v8 >= v9 )
            return v7 & 0xFFFFFFF0 | 6;
          v5 = Buf1 + 1;
          v10 = 1;
          v18[v8] = Buf1 + 1;
LABEL_15:
          v6 = 2;
          ++v8;
          break;
        }
        *Buf1 = 0;
        *v5 = 0;
        if ( v8 == v9 )
          goto LABEL_28;
        v6 = 1;
        v10 = 0;
        break;
      case 0x23:
        if ( v10 )
          goto LABEL_16;
        IsKeyWord = LmpIsKeyWord(Buf1);
        if ( !IsKeyWord )
        {
          if ( !v6 )
          {
            v7 &= 0xFFFFFFF0;
            *Buf1 = 0;
            goto LABEL_28;
          }
LABEL_26:
          *Buf1 = 0;
          if ( v10 )
            *v5 = 0;
          goto LABEL_28;
        }
        v14 = *(_DWORD *)(IsKeyWord + 16);
        v6 = 2;
        v9 = *(_DWORD *)(IsKeyWord + 20);
        if ( v14 == 0x8000 )
        {
          v7 |= 0x10u;
        }
        else if ( v14 == 0x4000 )
        {
          v7 |= 0x20u;
        }
        else
        {
          if ( v9 > v3 || v8 >= v9 )
            return v7 & 0xFFFFFFF0 | 6;
          v15 = v8++;
          v7 = v14 ^ (v14 ^ v7) & 0xFFFFFFF0;
          v18[v15] = Buf1;
        }
        break;
      case 0x5C:
        if ( !v10 )
        {
LABEL_11:
          if ( v6 == 2 )
            break;
          if ( v9 > v3 || v8 >= v9 )
            return v7 & 0xFFFFFFF0 | 6;
          v18[v8] = Buf1;
          goto LABEL_15;
        }
        v16 = HandleSpecial(&v17, v11, Buf1);
        if ( v16 == -1 )
          return v7 & 0xFFFFFFF0 | 6;
        Buf1 = v17;
        *v5++ = v16;
        break;
      default:
        if ( !v10 )
          goto LABEL_11;
LABEL_16:
        *v5++ = v11;
        break;
    }
    ++Buf1;
  }
LABEL_28:
  if ( v8 <= 1 && v8 != v9 )
    v7 = v7 & 0xFFFFFFF0 | 6;
  *v19 = v8;
  return v7;
}

```

## disassembly

```asm
0x14004e60c  mov     [rsp+arg_18], rbx
0x14004e611  mov     [rsp+arg_10], r8
0x14004e616  mov     [rsp+arg_8], rdx
0x14004e61b  push    rbp
0x14004e61c  push    rsi
0x14004e61d  push    rdi
0x14004e61e  push    r12
0x14004e620  push    r13
0x14004e622  push    r14
0x14004e624  push    r15
0x14004e626  sub     rsp, 20h
0x14004e62a  movsxd  r13, dword ptr [r8]
0x14004e62d  mov     rax, rdx
0x14004e630  mov     r14, rcx
0x14004e633  mov     r8, r13
0x14004e636  shl     r8, 3; Size
0x14004e63a  xor     edx, edx; Val
0x14004e63c  mov     rcx, rax; void *
0x14004e63f  xor     esi, esi
0x14004e641  call    memset
0x14004e646  xor     r15d, r15d
0x14004e649  lea     ebx, [rsi+1]
0x14004e64c  xor     edi, edi
0x14004e64e  mov     ebp, r13d
0x14004e651  xor     r12d, r12d
0x14004e654  movzx   edx, byte ptr [r14]
0x14004e658  mov     r8, r14
0x14004e65b  mov     [rsp+58h+arg_0], r14
0x14004e660  test    dl, dl
0x14004e662  jz      loc_14004E736
0x14004e668  mov     ecx, edx
0x14004e66a  sub     ecx, 9
0x14004e66d  jz      short loc_14004E6DC
0x14004e66f  sub     ecx, 1
0x14004e672  jz      loc_14004E729
0x14004e678  sub     ecx, 3
0x14004e67b  jz      loc_14004E729
0x14004e681  sub     ecx, 13h
0x14004e684  jz      short loc_14004E6DC
0x14004e686  sub     ecx, 2
0x14004e689  jz      loc_14004E792
0x14004e68f  sub     ecx, 1
0x14004e692  jz      short loc_14004E6F5
0x14004e694  cmp     ecx, 39h ; '9'
0x14004e697  jz      loc_14004E7F6
0x14004e69d  test    r12d, r12d
0x14004e6a0  jnz     short loc_14004E6CF
0x14004e6a2  cmp     r15d, 2
0x14004e6a6  jz      short loc_14004E6D4
0x14004e6a8  cmp     ebp, r13d
0x14004e6ab  jg      loc_14004E75E
0x14004e6b1  cmp     edi, ebp
0x14004e6b3  jge     loc_14004E75E
0x14004e6b9  mov     rcx, [rsp+58h+arg_8]
0x14004e6be  movsxd  rax, edi
0x14004e6c1  mov     [rcx+rax*8], r14
0x14004e6c5  mov     r15d, 2
0x14004e6cb  inc     edi
0x14004e6cd  jmp     short loc_14004E6D4
0x14004e6cf  mov     [rsi], dl
0x14004e6d1  inc     rsi
0x14004e6d4  inc     r14
0x14004e6d7  jmp     loc_14004E654
0x14004e6dc  test    r12d, r12d
0x14004e6df  jnz     short loc_14004E6CF
0x14004e6e1  cmp     r15d, 2
0x14004e6e5  jnz     short loc_14004E6D4
0x14004e6e7  mov     [r14], r12b
0x14004e6ea  lea     r15d, [r12+1]
0x14004e6ef  cmp     edi, ebp
0x14004e6f1  jnz     short loc_14004E6D4
0x14004e6f3  jmp     short loc_14004E736
0x14004e6f5  test    r12d, r12d
0x14004e6f8  jnz     short loc_14004E6CF
0x14004e6fa  lea     rax, Decoration
0x14004e701  test    r15d, r15d
0x14004e704  lea     rdx, Directive
0x14004e70b  mov     rcx, r8; Buf1
0x14004e70e  cmovnz  rdx, rax
0x14004e712  call    LmpIsKeyWord
0x14004e717  test    rax, rax
0x14004e71a  jnz     short loc_14004E766
0x14004e71c  test    r15d, r15d
0x14004e71f  jnz     short loc_14004E729
0x14004e721  and     ebx, 0FFFFFFF0h
0x14004e724  mov     [r14], r15b
0x14004e727  jmp     short loc_14004E736
0x14004e729  mov     byte ptr [r14], 0
0x14004e72d  test    r12d, r12d
0x14004e730  jnz     loc_14004E847
0x14004e736  cmp     edi, 1
0x14004e739  jle     loc_14004E7C0
0x14004e73f  mov     rax, [rsp+58h+arg_10]
0x14004e744  mov     [rax], edi
0x14004e746  mov     eax, ebx
0x14004e748  mov     rbx, [rsp+58h+arg_18]
0x14004e74d  add     rsp, 20h
0x14004e751  pop     r15
0x14004e753  pop     r14
0x14004e755  pop     r13
0x14004e757  pop     r12
0x14004e759  pop     rdi
0x14004e75a  pop     rsi
0x14004e75b  pop     rbp
0x14004e75c  retn
0x14004e75e  and     ebx, 0FFFFFFF6h
0x14004e761  or      ebx, 6
0x14004e764  jmp     short loc_14004E746
0x14004e766  mov     ecx, [rax+10h]
0x14004e769  mov     r15d, 2
0x14004e76f  mov     ebp, [rax+14h]
0x14004e772  cmp     ecx, 8000h
0x14004e778  jz      short loc_14004E78A
0x14004e77a  cmp     ecx, 4000h
0x14004e780  jnz     short loc_14004E7D3
0x14004e782  or      ebx, 20h
0x14004e785  jmp     loc_14004E6D4
0x14004e78a  or      ebx, 10h
0x14004e78d  jmp     loc_14004E6D4
0x14004e792  cmp     r15d, 2
0x14004e796  jz      loc_14004E821
0x14004e79c  cmp     ebp, r13d
0x14004e79f  jg      short loc_14004E75E
0x14004e7a1  cmp     edi, ebp
0x14004e7a3  jge     short loc_14004E75E
0x14004e7a5  mov     rcx, [rsp+58h+arg_8]
0x14004e7aa  lea     rsi, [r8+1]
0x14004e7ae  movsxd  rax, edi
0x14004e7b1  mov     r12d, 1
0x14004e7b7  mov     [rcx+rax*8], rsi
0x14004e7bb  jmp     loc_14004E6C5
0x14004e7c0  cmp     edi, ebp
0x14004e7c2  jz      loc_14004E73F
0x14004e7c8  and     ebx, 0FFFFFFF6h
0x14004e7cb  or      ebx, 6
0x14004e7ce  jmp     loc_14004E73F
0x14004e7d3  cmp     ebp, r13d
0x14004e7d6  jg      short loc_14004E75E
0x14004e7d8  cmp     edi, ebp
0x14004e7da  jge     short loc_14004E75E
0x14004e7dc  mov     rdx, [rsp+58h+arg_8]
0x14004e7e1  xor     ebx, ecx
0x14004e7e3  movsxd  rax, edi
0x14004e7e6  and     ebx, 0FFFFFFF0h
0x14004e7e9  inc     edi
0x14004e7eb  xor     ebx, ecx
0x14004e7ed  mov     [rdx+rax*8], r14
0x14004e7f1  jmp     loc_14004E6D4
0x14004e7f6  test    r12d, r12d
0x14004e7f9  jz      loc_14004E6A2
0x14004e7ff  lea     rcx, [rsp+58h+arg_0]
0x14004e804  call    HandleSpecial
0x14004e809  cmp     eax, 0FFFFFFFFh
0x14004e80c  jz      loc_14004E75E
0x14004e812  mov     r14, [rsp+58h+arg_0]
0x14004e817  mov     [rsi], al
0x14004e819  inc     rsi
0x14004e81c  jmp     loc_14004E6D4
0x14004e821  test    r12d, r12d
0x14004e824  jz      loc_14004E79C
0x14004e82a  mov     byte ptr [r14], 0
0x14004e82e  mov     byte ptr [rsi], 0
0x14004e831  cmp     edi, ebp
0x14004e833  jz      loc_14004E736
0x14004e839  mov     r15d, 1
0x14004e83f  xor     r12d, r12d
0x14004e842  jmp     loc_14004E6D4
0x14004e847  mov     byte ptr [rsi], 0
0x14004e84a  jmp     loc_14004E736
```
