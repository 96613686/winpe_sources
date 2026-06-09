# makeCode

- ea: `0x1800040d0`
- end: `0x18000420d`
- name: `makeCode`
- size: `317`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a60`
- `0x180003ff0`

## callees

- `0x1800040d0`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall makeCode(int a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  int v6; // edx
  int v8; // ecx
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  __int64 v24; // r9
  __int64 result; // rax
  __int64 v27; // rdx
  unsigned int v28; // r8d
  unsigned int v29; // eax
  int v30; // ecx
  _DWORD v31[16]; // [rsp+0h] [rbp-68h]
  int v32; // [rsp+40h] [rbp-28h]
  int i; // [rsp+44h] [rbp-24h]

  v5 = 2 * a2[1];
  v6 = v5 + a2[2];
  v31[2] = v5;
  v31[1] = 0;
  v6 *= 2;
  v8 = a2[4];
  v9 = 2 * (v6 + a2[3]);
  v31[3] = v6;
  v10 = a2[15];
  v31[4] = v9;
  v11 = 2 * (v9 + v8);
  v13 = v11 + a2[5];
  v31[5] = v11;
  v13 *= 2;
  v14 = v13 + a2[6];
  v31[6] = v13;
  v14 *= 2;
  v15 = v14 + a2[7];
  v31[7] = v14;
  v15 *= 2;
  v16 = v15 + a2[8];
  v31[8] = v15;
  v16 *= 2;
  v17 = v16 + a2[9];
  v31[9] = v16;
  v17 *= 2;
  v18 = v17 + a2[10];
  v31[10] = v17;
  v18 *= 2;
  v19 = v18 + a2[11];
  v31[11] = v18;
  v19 *= 2;
  v20 = v19 + a2[12];
  v31[12] = v19;
  v20 *= 2;
  v21 = v20 + a2[13];
  v31[13] = v20;
  v21 *= 2;
  v22 = v21 + a2[14];
  v31[14] = v21;
  v23 = a2[16];
  v31[15] = 2 * v22;
  v24 = 0;
  v32 = 2 * (2 * v22 + v10);
  result = (unsigned int)(2 * (v32 + v23));
  for ( i = result; (int)v24 < a1; v24 = (unsigned int)(v24 + 1) )
  {
    v27 = *(unsigned __int8 *)(v24 + a3);
    v28 = v31[v27];
    v31[v27] = v28 + 1;
    v29 = 0;
    do
    {
      LODWORD(v27) = v27 - 1;
      v30 = v28 & 1;
      v28 >>= 1;
      v29 = 2 * (v30 | v29);
    }
    while ( (int)v27 > 0 );
    result = v29 >> 1;
    *(_WORD *)(a4 + 2 * v24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800040d0  mov     [rsp+arg_0], rbx
0x1800040d5  push    rdi
0x1800040d6  sub     rsp, 60h
0x1800040da  mov     rax, cs:__security_cookie
0x1800040e1  xor     rax, rsp
0x1800040e4  mov     [rsp+68h+var_18], rax
0x1800040e9  mov     eax, [rdx+4]
0x1800040ec  mov     r10, rdx
0x1800040ef  mov     edx, [rdx+8]
0x1800040f2  add     eax, eax
0x1800040f4  add     edx, eax
0x1800040f6  mov     [rsp+68h+var_60], eax
0x1800040fa  mov     r11d, ecx
0x1800040fd  mov     [rsp+68h+var_64], 0
0x180004105  mov     eax, [r10+0Ch]
0x180004109  add     edx, edx
0x18000410b  mov     ecx, [r10+10h]
0x18000410f  add     eax, edx
0x180004111  add     eax, eax
0x180004113  mov     [rsp+68h+var_5C], edx
0x180004117  add     ecx, eax
0x180004119  mov     edx, [r10+3Ch]
0x18000411d  mov     [rsp+68h+var_58], eax
0x180004121  add     ecx, ecx
0x180004123  mov     eax, [r10+14h]
0x180004127  mov     rbx, r9
0x18000412a  add     eax, ecx
0x18000412c  mov     [rsp+68h+var_54], ecx
0x180004130  mov     ecx, [r10+18h]
0x180004134  add     eax, eax
0x180004136  add     ecx, eax
0x180004138  mov     [rsp+68h+var_50], eax
0x18000413c  mov     eax, [r10+1Ch]
0x180004140  add     ecx, ecx
0x180004142  add     eax, ecx
0x180004144  mov     [rsp+68h+var_4C], ecx
0x180004148  mov     ecx, [r10+20h]
0x18000414c  add     eax, eax
0x18000414e  add     ecx, eax
0x180004150  mov     [rsp+68h+var_48], eax
0x180004154  mov     eax, [r10+24h]
0x180004158  add     ecx, ecx
0x18000415a  add     eax, ecx
0x18000415c  mov     [rsp+68h+var_44], ecx
0x180004160  mov     ecx, [r10+28h]
0x180004164  add     eax, eax
0x180004166  add     ecx, eax
0x180004168  mov     [rsp+68h+var_40], eax
0x18000416c  mov     eax, [r10+2Ch]
0x180004170  add     ecx, ecx
0x180004172  add     eax, ecx
0x180004174  mov     [rsp+68h+var_3C], ecx
0x180004178  mov     ecx, [r10+30h]
0x18000417c  add     eax, eax
0x18000417e  add     ecx, eax
0x180004180  mov     [rsp+68h+var_38], eax
0x180004184  mov     eax, [r10+34h]
0x180004188  add     ecx, ecx
0x18000418a  add     eax, ecx
0x18000418c  mov     [rsp+68h+var_34], ecx
0x180004190  mov     ecx, [r10+38h]
0x180004194  add     eax, eax
0x180004196  add     ecx, eax
0x180004198  mov     [rsp+68h+var_30], eax
0x18000419c  mov     eax, [r10+40h]
0x1800041a0  add     ecx, ecx
0x1800041a2  add     edx, ecx
0x1800041a4  mov     [rsp+68h+var_2C], ecx
0x1800041a8  add     edx, edx
0x1800041aa  xor     r9d, r9d
0x1800041ad  add     eax, edx
0x1800041af  mov     [rsp+68h+var_28], edx
0x1800041b3  add     eax, eax
0x1800041b5  mov     rdi, r8
0x1800041b8  mov     [rsp+68h+var_24], eax
0x1800041bc  test    r11d, r11d
0x1800041bf  jle     short loc_1800041F5
0x1800041c1  movzx   edx, byte ptr [r9+rdi]
0x1800041c6  mov     r8d, [rsp+rdx*4+68h+var_68]
0x1800041ca  lea     eax, [r8+1]
0x1800041ce  mov     [rsp+rdx*4+68h+var_68], eax
0x1800041d1  xor     eax, eax
0x1800041d3  mov     ecx, r8d
0x1800041d6  dec     edx
0x1800041d8  and     ecx, 1
0x1800041db  shr     r8d, 1
0x1800041de  or      eax, ecx
0x1800041e0  add     eax, eax
0x1800041e2  test    edx, edx
0x1800041e4  jg      short loc_1800041D3
0x1800041e6  shr     eax, 1
0x1800041e8  mov     [rbx+r9*2], ax
0x1800041ed  inc     r9d
0x1800041f0  cmp     r9d, r11d
0x1800041f3  jl      short loc_1800041C1
0x1800041f5  mov     rcx, [rsp+68h+var_18]
0x1800041fa  xor     rcx, rsp; StackCookie
0x1800041fd  call    __security_check_cookie
0x180004202  mov     rbx, [rsp+68h+arg_0]
0x180004207  add     rsp, 60h
0x18000420b  pop     rdi
0x18000420c  retn
```
