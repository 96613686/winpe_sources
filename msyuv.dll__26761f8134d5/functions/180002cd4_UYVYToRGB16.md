# UYVYToRGB16

- ea: `0x180002cd4`
- end: `0x1800030df`
- name: `UYVYToRGB16`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000208c`

## callees

- `0x180002cd4`
- `0x180004789`

## pseudocode

```c
__int64 __fastcall UYVYToRGB16(__int64 a1, __int64 a2, char *a3, int *a4, char *a5)
{
  int v8; // r11d
  int v9; // r10d
  char *v10; // rdi
  char *v11; // r14
  __int64 result; // rax
  unsigned __int64 v13; // r13
  char *v14; // r9
  unsigned int v15; // esi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  int v18; // r12d
  unsigned int v19; // ecx
  unsigned int v20; // eax
  __int64 v21; // rdx
  int v22; // ecx
  unsigned int v23; // esi
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  int v26; // r12d
  unsigned int v27; // r8d
  unsigned int v28; // edx
  __int64 v29; // rdx
  unsigned int v30; // esi
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  int v33; // r12d
  int v34; // edx
  int v35; // eax
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  __int64 v38; // rdx
  __int64 v39; // [rsp+70h] [rbp+8h]

  v8 = *(_DWORD *)(a2 + 4);
  v9 = -*(_DWORD *)(a2 + 8);
  if ( *(int *)(a2 + 8) > 0 )
    v9 = *(_DWORD *)(a2 + 8);
  if ( a4[4] == 1498831189 || a4[4] == 844715353 || a4[4] == 1431918169 )
  {
    result = (unsigned int)(v9 * v8 * *(unsigned __int16 *)(a2 + 14) / 8);
    if ( *(_DWORD *)(a2 + 20) >= (unsigned int)result && a4[5] >= (unsigned int)result )
      return (__int64)memcpy_0(a5, a3, (unsigned int)result);
  }
  else
  {
    v10 = a5;
    v11 = a3;
    v39 = *(_QWORD *)(a1 + 8);
    result = (unsigned int)(4 * v8);
    v13 = (unsigned __int64)(int)result >> 2;
    if ( a4[2] < 0 )
    {
      v14 = a5;
    }
    else
    {
      result = (unsigned int)(2 * v8 * (v9 - 1));
      v14 = &a5[(int)result];
    }
    if ( *(_DWORD *)(a1 + 4) == 1498831189 )
    {
      if ( v9 > 0 )
      {
        result = (unsigned int)(v8 / 2);
        v15 = 4 * (v8 / 2);
        do
        {
          if ( a3 > v11 )
            break;
          result = *(unsigned int *)(a2 + 20);
          if ( (unsigned int)result < v15 )
            break;
          v16 = (unsigned int)result - v15;
          result = v11 - a3;
          if ( v11 - a3 > v16 )
            break;
          if ( v10 > v14 )
            break;
          result = (unsigned int)a4[5];
          if ( (unsigned int)result < v15 )
            break;
          v17 = (unsigned int)result - v15;
          result = v14 - v10;
          if ( v14 - v10 > v17 )
            break;
          v18 = v8;
          if ( v8 > 1 )
          {
            do
            {
              v19 = *(_DWORD *)v11;
              v18 -= 2;
              v20 = *(_DWORD *)v11;
              v11 += 4;
              v21 = (((v19 & 0xFFFF00FF) << 8) & 0xF800 | ((((v19 & 0xFFFF00FF) << 8) | (v20 >> 8) & 0xFF00FF) >> 21)) >> 6;
              v22 = *(unsigned __int16 *)(v39
                                        + 2
                                        * (v21 | ((((v19 & 0xFFFF00FF) << 8) | (v20 >> 8) & 0xFF00FF) >> 9) & 0x7C00)) << 16;
              result = *(unsigned __int16 *)(v39 + 2 * (v21 | (((v20 >> 8) & 0xF8) << 7)));
              *(_DWORD *)v14 = result | v22;
              v14 += 4;
            }
            while ( v18 > 1 );
            v10 = a5;
          }
          if ( a4[2] >= 0 )
          {
            result = -(__int64)(int)v13;
            v14 -= 4 * (int)v13;
          }
          --v9;
        }
        while ( v9 > 0 );
      }
    }
    else if ( *(_DWORD *)(a1 + 4) == 844715353 )
    {
      if ( v9 > 0 )
      {
        result = (unsigned int)(v8 / 2);
        v23 = 4 * (v8 / 2);
        do
        {
          if ( a3 > v11 )
            break;
          result = *(unsigned int *)(a2 + 20);
          if ( (unsigned int)result < v23 )
            break;
          v24 = (unsigned int)result - v23;
          result = v11 - a3;
          if ( v11 - a3 > v24 )
            break;
          if ( v10 > v14 )
            break;
          result = (unsigned int)a4[5];
          if ( (unsigned int)result < v23 )
            break;
          v25 = (unsigned int)result - v23;
          result = v14 - v10;
          if ( v14 - v10 > v25 )
            break;
          v26 = v8;
          if ( v8 > 1 )
          {
            do
            {
              v27 = *(_DWORD *)v11;
              v26 -= 2;
              v28 = *(_DWORD *)v11 & 0xF800 | (*(_DWORD *)v11 >> 21);
              v11 += 4;
              v29 = v28 >> 6;
              result = *(unsigned __int16 *)(v39 + 2 * (v29 | ((unsigned __int8)(v27 & 0xF8) << 7)));
              *(_DWORD *)v14 = result | (*(unsigned __int16 *)(v39 + 2 * (v29 | (v27 >> 9) & 0x7C00)) << 16);
              v14 += 4;
            }
            while ( v26 > 1 );
            v10 = a5;
          }
          if ( a4[2] >= 0 )
          {
            result = -(__int64)(int)v13;
            v14 -= 4 * (int)v13;
          }
          --v9;
        }
        while ( v9 > 0 );
      }
    }
    else if ( *(_DWORD *)(a1 + 4) == 1431918169 && v9 > 0 )
    {
      result = (unsigned int)(v8 / 2);
      v30 = 4 * (v8 / 2);
      do
      {
        if ( a3 > v11 )
          break;
        result = *(unsigned int *)(a2 + 20);
        if ( (unsigned int)result < v30 )
          break;
        v31 = (unsigned int)result - v30;
        result = v11 - a3;
        if ( v11 - a3 > v31 )
          break;
        if ( v10 > v14 )
          break;
        result = (unsigned int)a4[5];
        if ( (unsigned int)result < v30 )
          break;
        v32 = (unsigned int)result - v30;
        result = v14 - v10;
        if ( v14 - v10 > v32 )
          break;
        v33 = v8;
        if ( v8 > 1 )
        {
          do
          {
            v33 -= 2;
            v34 = *(_DWORD *)v11 & 0xFF00FF;
            v35 = HIWORD(*(_DWORD *)v11) & 0xFF00;
            v36 = (*(_DWORD *)v11 & 0xFFFFFF00) << 16;
            v11 += 4;
            v37 = v34 | v35 | v36;
            v38 = (v37 & 0xF800 | (v37 >> 21)) >> 6;
            result = *(unsigned __int16 *)(v39 + 2 * (v38 | ((unsigned __int8)(v37 & 0xF8) << 7)));
            *(_DWORD *)v14 = result | (*(unsigned __int16 *)(v39 + 2 * (v38 | (v37 >> 9) & 0x7C00)) << 16);
            v14 += 4;
          }
          while ( v33 > 1 );
          v10 = a5;
        }
        if ( a4[2] >= 0 )
        {
          result = -(__int64)(int)v13;
          v14 -= 4 * (int)v13;
        }
        --v9;
      }
      while ( v9 > 0 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002cd4  push    rbx
0x180002cd6  push    rbp
0x180002cd7  push    rsi
0x180002cd8  push    rdi
0x180002cd9  push    r12
0x180002cdb  push    r13
0x180002cdd  push    r14
0x180002cdf  push    r15
0x180002ce1  sub     rsp, 28h
0x180002ce5  mov     r15, rdx
0x180002ce8  mov     r12d, 59565955h
0x180002cee  mov     rbx, r9
0x180002cf1  mov     rbp, r8
0x180002cf4  mov     rdx, rcx
0x180002cf7  mov     r10d, [r15+8]
0x180002cfb  mov     r11d, [r15+4]
0x180002cff  neg     r10d
0x180002d02  cmovs   r10d, [r15+8]
0x180002d07  cmp     [r9+10h], r12d
0x180002d0b  jz      loc_180003099
0x180002d11  mov     r8d, 32595559h
0x180002d17  cmp     [r9+10h], r8d
0x180002d1b  jz      loc_180003099
0x180002d21  mov     esi, 55595659h
0x180002d26  cmp     [r9+10h], esi
0x180002d2a  jz      loc_180003099
0x180002d30  mov     rax, [rdx+8]
0x180002d34  lea     ecx, [r11+r11]
0x180002d38  mov     rdi, [rsp+68h+arg_20]
0x180002d40  mov     r14, rbp
0x180002d43  mov     [rsp+68h+arg_0], rax
0x180002d48  lea     eax, [rcx+rcx]
0x180002d4b  movsxd  r13, eax
0x180002d4e  shr     r13, 2
0x180002d52  cmp     dword ptr [r9+8], 0
0x180002d57  jl      short loc_180002D68
0x180002d59  lea     eax, [r10-1]
0x180002d5d  imul    eax, ecx
0x180002d60  movsxd  r9, eax
0x180002d63  add     r9, rdi
0x180002d66  jmp     short loc_180002D6B
0x180002d68  mov     r9, rdi
0x180002d6b  cmp     [rdx+4], r12d
0x180002d6f  jnz     loc_180002E7D
0x180002d75  test    r10d, r10d
0x180002d78  jle     loc_1800030CE
0x180002d7e  mov     eax, r11d
0x180002d81  cdq
0x180002d82  sub     eax, edx
0x180002d84  sar     eax, 1
0x180002d86  mov     esi, eax
0x180002d88  shl     esi, 2
0x180002d8b  cmp     rbp, r14
0x180002d8e  ja      loc_1800030CE
0x180002d94  mov     eax, [r15+14h]
0x180002d98  cmp     eax, esi
0x180002d9a  jb      loc_1800030CE
0x180002da0  sub     eax, esi
0x180002da2  mov     ecx, eax
0x180002da4  mov     rax, r14
0x180002da7  sub     rax, rbp
0x180002daa  cmp     rax, rcx
0x180002dad  ja      loc_1800030CE
0x180002db3  cmp     rdi, r9
0x180002db6  ja      loc_1800030CE
0x180002dbc  mov     eax, [rbx+14h]
0x180002dbf  cmp     eax, esi
0x180002dc1  jb      loc_1800030CE
0x180002dc7  sub     eax, esi
0x180002dc9  mov     ecx, eax
0x180002dcb  mov     rax, r9
0x180002dce  sub     rax, rdi
0x180002dd1  cmp     rax, rcx
0x180002dd4  ja      loc_1800030CE
0x180002dda  mov     r12d, r11d
0x180002ddd  cmp     r11d, 1
0x180002de1  jle     short loc_180002E5C
0x180002de3  mov     rdi, [rsp+68h+arg_0]
0x180002de8  mov     ecx, [r14]
0x180002deb  sub     r12d, 2
0x180002def  mov     eax, ecx
0x180002df1  add     r14, 4
0x180002df5  shr     eax, 8
0x180002df8  and     ecx, 0FFFF00FFh
0x180002dfe  and     eax, 0FF00FFh
0x180002e03  shl     ecx, 8
0x180002e06  or      eax, ecx
0x180002e08  mov     edx, eax
0x180002e0a  mov     r8d, eax
0x180002e0d  and     eax, 0F800h
0x180002e12  shr     edx, 15h
0x180002e15  or      edx, eax
0x180002e17  mov     eax, r8d
0x180002e1a  shr     rax, 9
0x180002e1e  and     r8d, 0F8h
0x180002e25  and     eax, 7C00h
0x180002e2a  shr     edx, 6
0x180002e2d  or      rax, rdx
0x180002e30  shl     r8d, 7
0x180002e34  movzx   ecx, word ptr [rdi+rax*2]
0x180002e38  shl     ecx, 10h
0x180002e3b  mov     eax, r8d
0x180002e3e  or      rax, rdx
0x180002e41  movzx   eax, word ptr [rdi+rax*2]
0x180002e45  or      ecx, eax
0x180002e47  mov     [r9], ecx
0x180002e4a  add     r9, 4
0x180002e4e  cmp     r12d, 1
0x180002e52  jg      short loc_180002DE8
0x180002e54  mov     rdi, [rsp+68h+arg_20]
0x180002e5c  cmp     dword ptr [rbx+8], 0
0x180002e60  jl      short loc_180002E6C
0x180002e62  movsxd  rax, r13d
0x180002e65  neg     rax
0x180002e68  lea     r9, [r9+rax*4]
0x180002e6c  dec     r10d
0x180002e6f  test    r10d, r10d
0x180002e72  jg      loc_180002D8B
0x180002e78  jmp     loc_1800030CE
0x180002e7d  cmp     [rdx+4], r8d
0x180002e81  jnz     loc_180002F7B
0x180002e87  test    r10d, r10d
0x180002e8a  jle     loc_1800030CE
0x180002e90  mov     eax, r11d
0x180002e93  cdq
0x180002e94  sub     eax, edx
0x180002e96  sar     eax, 1
0x180002e98  mov     esi, eax
0x180002e9a  shl     esi, 2
0x180002e9d  cmp     rbp, r14
0x180002ea0  ja      loc_1800030CE
0x180002ea6  mov     eax, [r15+14h]
0x180002eaa  cmp     eax, esi
0x180002eac  jb      loc_1800030CE
0x180002eb2  sub     eax, esi
0x180002eb4  mov     ecx, eax
0x180002eb6  mov     rax, r14
0x180002eb9  sub     rax, rbp
0x180002ebc  cmp     rax, rcx
0x180002ebf  ja      loc_1800030CE
0x180002ec5  cmp     rdi, r9
0x180002ec8  ja      loc_1800030CE
0x180002ece  mov     eax, [rbx+14h]
0x180002ed1  cmp     eax, esi
0x180002ed3  jb      loc_1800030CE
0x180002ed9  sub     eax, esi
0x180002edb  mov     ecx, eax
0x180002edd  mov     rax, r9
0x180002ee0  sub     rax, rdi
0x180002ee3  cmp     rax, rcx
0x180002ee6  ja      loc_1800030CE
0x180002eec  mov     r12d, r11d
0x180002eef  cmp     r11d, 1
0x180002ef3  jle     short loc_180002F5A
0x180002ef5  mov     rdi, [rsp+68h+arg_0]
0x180002efa  mov     r8d, [r14]
0x180002efd  sub     r12d, 2
0x180002f01  mov     edx, r8d
0x180002f04  mov     eax, r8d
0x180002f07  and     eax, 0F800h
0x180002f0c  shr     edx, 15h
0x180002f0f  or      edx, eax
0x180002f11  add     r14, 4
0x180002f15  mov     eax, r8d
0x180002f18  shr     edx, 6
0x180002f1b  shr     rax, 9
0x180002f1f  and     r8d, 0F8h
0x180002f26  and     eax, 7C00h
0x180002f2b  shl     r8d, 7
0x180002f2f  or      rax, rdx
0x180002f32  movzx   ecx, word ptr [rdi+rax*2]
0x180002f36  shl     ecx, 10h
0x180002f39  mov     eax, r8d
0x180002f3c  or      rax, rdx
0x180002f3f  movzx   eax, word ptr [rdi+rax*2]
0x180002f43  or      ecx, eax
0x180002f45  mov     [r9], ecx
0x180002f48  add     r9, 4
0x180002f4c  cmp     r12d, 1
0x180002f50  jg      short loc_180002EFA
0x180002f52  mov     rdi, [rsp+68h+arg_20]
0x180002f5a  cmp     dword ptr [rbx+8], 0
0x180002f5e  jl      short loc_180002F6A
0x180002f60  movsxd  rax, r13d
0x180002f63  neg     rax
0x180002f66  lea     r9, [r9+rax*4]
0x180002f6a  dec     r10d
0x180002f6d  test    r10d, r10d
0x180002f70  jg      loc_180002E9D
0x180002f76  jmp     loc_1800030CE
0x180002f7b  cmp     [rdx+4], esi
0x180002f7e  jnz     loc_1800030CE
0x180002f84  test    r10d, r10d
0x180002f87  jle     loc_1800030CE
0x180002f8d  mov     eax, r11d
0x180002f90  cdq
0x180002f91  sub     eax, edx
0x180002f93  sar     eax, 1
0x180002f95  mov     esi, eax
0x180002f97  shl     esi, 2
0x180002f9a  cmp     rbp, r14
0x180002f9d  ja      loc_1800030CE
0x180002fa3  mov     eax, [r15+14h]
0x180002fa7  cmp     eax, esi
0x180002fa9  jb      loc_1800030CE
0x180002faf  sub     eax, esi
0x180002fb1  mov     ecx, eax
0x180002fb3  mov     rax, r14
0x180002fb6  sub     rax, rbp
0x180002fb9  cmp     rax, rcx
0x180002fbc  ja      loc_1800030CE
0x180002fc2  cmp     rdi, r9
0x180002fc5  ja      loc_1800030CE
0x180002fcb  mov     eax, [rbx+14h]
0x180002fce  cmp     eax, esi
0x180002fd0  jb      loc_1800030CE
0x180002fd6  sub     eax, esi
0x180002fd8  mov     ecx, eax
0x180002fda  mov     rax, r9
0x180002fdd  sub     rax, rdi
0x180002fe0  cmp     rax, rcx
0x180002fe3  ja      loc_1800030CE
0x180002fe9  mov     r12d, r11d
0x180002fec  cmp     r11d, 1
0x180002ff0  jle     loc_18000307B
0x180002ff6  mov     rdi, [rsp+68h+arg_0]
0x180002ffb  mov     edx, [r14]
0x180002ffe  sub     r12d, 2
0x180003002  mov     eax, edx
0x180003004  mov     ecx, edx
0x180003006  shr     eax, 10h
0x180003009  and     edx, 0FF00FFh
0x18000300f  and     eax, 0FF00h
0x180003014  and     ecx, 0FFFFFF00h
0x18000301a  shl     ecx, 10h
0x18000301d  add     r14, 4
0x180003021  or      ecx, eax
0x180003023  or      ecx, edx
0x180003025  mov     edx, ecx
0x180003027  mov     eax, ecx
0x180003029  and     eax, 0F800h
0x18000302e  shr     edx, 15h
0x180003031  or      edx, eax
0x180003033  mov     r8d, ecx
0x180003036  mov     eax, r8d
0x180003039  shr     edx, 6
0x18000303c  shr     rax, 9
0x180003040  and     r8d, 0F8h
0x180003047  and     eax, 7C00h
0x18000304c  shl     r8d, 7
0x180003050  or      rax, rdx
0x180003053  movzx   ecx, word ptr [rdi+rax*2]
0x180003057  shl     ecx, 10h
0x18000305a  mov     eax, r8d
0x18000305d  or      rax, rdx
0x180003060  movzx   eax, word ptr [rdi+rax*2]
0x180003064  or      ecx, eax
0x180003066  mov     [r9], ecx
0x180003069  add     r9, 4
0x18000306d  cmp     r12d, 1
0x180003071  jg      short loc_180002FFB
0x180003073  mov     rdi, [rsp+68h+arg_20]
0x18000307b  cmp     dword ptr [rbx+8], 0
0x18000307f  jl      short loc_18000308B
0x180003081  movsxd  rax, r13d
0x180003084  neg     rax
0x180003087  lea     r9, [r9+rax*4]
0x18000308b  dec     r10d
0x18000308e  test    r10d, r10d
0x180003091  jg      loc_180002F9A
0x180003097  jmp     short loc_1800030CE
0x180003099  movzx   eax, word ptr [r15+0Eh]
0x18000309e  imul    eax, r11d
0x1800030a2  imul    eax, r10d
0x1800030a6  cdq
0x1800030a7  and     edx, 7
0x1800030aa  add     eax, edx
0x1800030ac  sar     eax, 3
0x1800030af  cmp     [r15+14h], eax
0x1800030b3  jb      short loc_1800030CE
0x1800030b5  cmp     [r9+14h], eax
0x1800030b9  jb      short loc_1800030CE
0x1800030bb  mov     rcx, [rsp+68h+arg_20]; void *
0x1800030c3  mov     rdx, rbp; Src
0x1800030c6  mov     r8d, eax; Size
0x1800030c9  call    memcpy_0
0x1800030ce  add     rsp, 28h
0x1800030d2  pop     r15
0x1800030d4  pop     r14
0x1800030d6  pop     r13
0x1800030d8  pop     r12
0x1800030da  pop     rdi
0x1800030db  pop     rsi
0x1800030dc  pop     rbp
0x1800030dd  pop     rbx
0x1800030de  retn
```
