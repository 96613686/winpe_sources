# PpfEvtLogValidateNextEventAndMoveAhead

- ea: `0x18002923c`
- end: `0x18002945c`
- name: `PpfEvtLogValidateNextEventAndMoveAhead`
- size: `544`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180028d5c`
- `0x18002904c`

## callees

- `0x1800290f4`
- `0x18002919c`
- `0x18002923c`

## string_xrefs

- `0x18002941f`: `PpfEvtLogValidateNextEventAndMoveAhead`

## pseudocode

```c
__int64 __fastcall PpfEvtLogValidateNextEventAndMoveAhead(__int64 *a1, _BYTE *a2)
{
  int v4; // edx
  unsigned int v5; // ebx
  __int64 v6; // rsi
  unsigned int v7; // ecx
  unsigned int *v8; // r14
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // r15d
  unsigned int v12; // edx
  unsigned int v13; // ebp
  unsigned __int16 *v14; // r12
  int Size; // eax
  unsigned int v16; // r15d
  unsigned __int16 v18; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp+18h]

  v18 = 0;
  if ( a1 && *a1 )
  {
    if ( a2 )
    {
      *a2 = 0;
      v5 = 0;
      v6 = *((unsigned int *)a1 + 7);
      v7 = *((_DWORD *)a1 + 2);
      if ( (_DWORD)v6 == v7 )
        return v5;
      if ( (unsigned int)v6 <= v7 )
      {
        if ( (int)v6 + 20 < (unsigned int)v6 )
        {
          Size = -1073741675;
          v4 = 344;
          goto LABEL_41;
        }
        if ( (int)v6 + 20 <= v7 )
        {
          v19 = *a1;
          v8 = (unsigned int *)(v19 + v6);
          if ( v19 + v6 < v19 )
          {
            Size = -1073741675;
            v4 = 357;
            goto LABEL_41;
          }
          v9 = *v8;
          v10 = v9 + v6;
          if ( (int)v9 + (int)v6 < (unsigned int)v6 )
          {
            Size = -1073741675;
            v4 = 362;
            goto LABEL_41;
          }
          if ( v10 <= v7 )
          {
            v11 = v8[4];
            v12 = v11 + v10;
            if ( v11 + v10 < v10 )
            {
              Size = -1073741675;
              v4 = 375;
              goto LABEL_41;
            }
            if ( v12 <= v7 )
            {
              v13 = v12 + v8[3];
              if ( v13 < v12 )
              {
                Size = -1073741675;
                v4 = 387;
                goto LABEL_41;
              }
              if ( v13 <= v7 )
              {
                if ( (unsigned int *)((char *)v8 + v13) < v8 )
                {
                  Size = -1073741675;
                  v4 = 401;
                  goto LABEL_41;
                }
                v14 = (unsigned __int16 *)((char *)v8 + v9);
                if ( !v11 )
                {
LABEL_28:
                  a1[2] = (__int64)v8;
                  *((_DWORD *)a1 + 7) = v13;
                  *((_DWORD *)a1 + 6) = v13 - v6;
                  *a2 = 1;
                  return v5;
                }
                while ( v11 > 2 )
                {
                  Size = PpfEvtLogValidateDigestAlgIDAndGetSize(*v14, &v18);
                  v5 = Size;
                  if ( Size < 0 )
                  {
                    v4 = 423;
                    goto LABEL_42;
                  }
                  if ( (c_PpfAlgorithmIdToBitmapTable[*v14] & *(_DWORD *)(v19 + 22)) == 0 )
                  {
                    v4 = 433;
                    goto LABEL_40;
                  }
                  v16 = v11 - 2;
                  if ( v16 < v18 )
                  {
                    v4 = 437;
                    goto LABEL_40;
                  }
                  v11 = v16 - v18;
                  v14 = (unsigned __int16 *)((char *)v14 + v18 + 2);
                  if ( !v11 )
                    goto LABEL_28;
                }
                v4 = 414;
              }
              else
              {
                v4 = 391;
              }
            }
            else
            {
              v4 = 378;
            }
          }
          else
          {
            v4 = 366;
          }
        }
        else
        {
          v4 = 348;
        }
      }
      else
      {
        v4 = 331;
      }
    }
    else
    {
      v4 = 317;
    }
  }
  else
  {
    v4 = 313;
  }
LABEL_40:
  Size = -1073741811;
LABEL_41:
  v5 = Size;
LABEL_42:
  PpfEvtLogTraceHelper(
    (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
    v4,
    (int)"PpfEvtLogValidateNextEventAndMoveAhead",
    1,
    "Error: 0x%x",
    Size);
  return v5;
}

```

## disassembly

```asm
0x18002923c  mov     [rsp+arg_8], rbx
0x180029241  push    rbp
0x180029242  push    rsi
0x180029243  push    rdi
0x180029244  push    r12
0x180029246  push    r13
0x180029248  push    r14
0x18002924a  push    r15
0x18002924c  sub     rsp, 30h
0x180029250  xor     eax, eax
0x180029252  mov     r13, rdx
0x180029255  mov     [rsp+68h+arg_0], ax
0x18002925a  mov     rdi, rcx
0x18002925d  test    rcx, rcx
0x180029260  jz      loc_18002940F
0x180029266  cmp     [rcx], rax
0x180029269  jz      loc_18002940F
0x18002926f  test    rdx, rdx
0x180029272  jnz     short loc_18002927E
0x180029274  mov     edx, 13Dh
0x180029279  jmp     loc_180029414
0x18002927e  mov     [rdx], al
0x180029280  xor     ebx, ebx
0x180029282  mov     esi, [rdi+1Ch]
0x180029285  mov     ecx, [rcx+8]
0x180029288  cmp     esi, ecx
0x18002928a  jz      loc_180029444
0x180029290  jbe     short loc_18002929C
0x180029292  mov     edx, 14Bh
0x180029297  jmp     loc_180029414
0x18002929c  lea     eax, [rsi+14h]
0x18002929f  cmp     eax, esi
0x1800292a1  jb      loc_180029403
0x1800292a7  cmp     eax, ecx
0x1800292a9  jbe     short loc_1800292B5
0x1800292ab  mov     edx, 15Ch
0x1800292b0  jmp     loc_180029414
0x1800292b5  mov     rdx, [rdi]
0x1800292b8  mov     [rsp+68h+arg_10], rdx
0x1800292c0  lea     r14, [rdx+rsi]
0x1800292c4  cmp     r14, rdx
0x1800292c7  jb      loc_1800293F7
0x1800292cd  mov     r8d, [r14]
0x1800292d0  lea     eax, [r8+rsi]
0x1800292d4  cmp     eax, esi
0x1800292d6  jb      loc_1800293EB
0x1800292dc  cmp     eax, ecx
0x1800292de  jbe     short loc_1800292EA
0x1800292e0  mov     edx, 16Eh
0x1800292e5  jmp     loc_180029414
0x1800292ea  mov     r15d, [r14+10h]
0x1800292ee  lea     edx, [r15+rax]
0x1800292f2  cmp     edx, eax
0x1800292f4  jb      loc_1800293DF
0x1800292fa  cmp     edx, ecx
0x1800292fc  jbe     short loc_180029308
0x1800292fe  mov     edx, 17Ah
0x180029303  jmp     loc_180029414
0x180029308  mov     ebp, [r14+0Ch]
0x18002930c  add     ebp, edx
0x18002930e  cmp     ebp, edx
0x180029310  jb      loc_1800293D3
0x180029316  cmp     ebp, ecx
0x180029318  jbe     short loc_180029324
0x18002931a  mov     edx, 187h
0x18002931f  jmp     loc_180029414
0x180029324  mov     eax, ebp
0x180029326  add     rax, r14
0x180029329  cmp     rax, r14
0x18002932c  jb      loc_1800293C7
0x180029332  lea     r12, [r14+r8]
0x180029336  test    r15d, r15d
0x180029339  jz      short loc_180029393
0x18002933b  cmp     r15d, 2
0x18002933f  jbe     short loc_1800293C0
0x180029341  movzx   ecx, word ptr [r12]
0x180029346  lea     rdx, [rsp+68h+arg_0]
0x18002934b  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x180029350  mov     ebx, eax
0x180029352  test    eax, eax
0x180029354  js      short loc_1800293B9
0x180029356  movzx   ecx, word ptr [r12]
0x18002935b  lea     rax, c_PpfAlgorithmIdToBitmapTable
0x180029362  mov     ecx, [rax+rcx*4]
0x180029365  mov     rax, [rsp+68h+arg_10]
0x18002936d  test    [rax+16h], ecx
0x180029370  jz      short loc_1800293B2
0x180029372  movzx   eax, [rsp+68h+arg_0]
0x180029377  add     r15d, 0FFFFFFFEh
0x18002937b  cmp     r15d, eax
0x18002937e  jb      short loc_1800293AB
0x180029380  sub     r15d, eax
0x180029383  lea     r12, [r12+2]
0x180029388  movzx   eax, [rsp+68h+arg_0]
0x18002938d  lea     r12, [r12+rax]
0x180029391  jnz     short loc_18002933B
0x180029393  mov     eax, ebp
0x180029395  mov     [rdi+10h], r14
0x180029399  sub     eax, esi
0x18002939b  mov     [rdi+1Ch], ebp
0x18002939e  mov     [rdi+18h], eax
0x1800293a1  mov     byte ptr [r13+0], 1
0x1800293a6  jmp     loc_180029444
0x1800293ab  mov     edx, 1B5h
0x1800293b0  jmp     short loc_180029414
0x1800293b2  mov     edx, 1B1h
0x1800293b7  jmp     short loc_180029414
0x1800293b9  mov     edx, 1A7h
0x1800293be  jmp     short loc_18002941B
0x1800293c0  mov     edx, 19Eh
0x1800293c5  jmp     short loc_180029414
0x1800293c7  mov     eax, 0C0000095h
0x1800293cc  mov     edx, 191h
0x1800293d1  jmp     short loc_180029419
0x1800293d3  mov     eax, 0C0000095h
0x1800293d8  mov     edx, 183h
0x1800293dd  jmp     short loc_180029419
0x1800293df  mov     eax, 0C0000095h
0x1800293e4  mov     edx, 177h
0x1800293e9  jmp     short loc_180029419
0x1800293eb  mov     eax, 0C0000095h
0x1800293f0  mov     edx, 16Ah
0x1800293f5  jmp     short loc_180029419
0x1800293f7  mov     eax, 0C0000095h
0x1800293fc  mov     edx, 165h
0x180029401  jmp     short loc_180029419
0x180029403  mov     eax, 0C0000095h
0x180029408  mov     edx, 158h
0x18002940d  jmp     short loc_180029419
0x18002940f  mov     edx, 139h; int
0x180029414  mov     eax, 0C000000Dh
0x180029419  mov     ebx, eax
0x18002941b  mov     dword ptr [rsp+68h+var_40], eax; char
0x18002941f  lea     r8, aPpfevtlogvalid_0; "PpfEvtLogValidateNextEventAndMoveAhead"
0x180029426  lea     rax, aError0xX; "Error: 0x%x"
0x18002942d  mov     r9d, 1; int
0x180029433  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x18002943a  mov     [rsp+68h+Format], rax; Format
0x18002943f  call    PpfEvtLogTraceHelper
0x180029444  mov     eax, ebx
0x180029446  mov     rbx, [rsp+68h+arg_8]
0x18002944b  add     rsp, 30h
0x18002944f  pop     r15
0x180029451  pop     r14
0x180029453  pop     r13
0x180029455  pop     r12
0x180029457  pop     rdi
0x180029458  pop     rsi
0x180029459  pop     rbp
0x18002945a  retn
```
