# GetOTFCompatCmap

- ea: `0x1400348e0`
- end: `0x140034b9b`
- name: `GetOTFCompatCmap`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400350dc`

## callees

- `0x1400348e0`
- `0x140038670`
- `0x1400392ac`

## pseudocode

```c
__int64 __fastcall GetOTFCompatCmap(__int64 *a1, _DWORD *a2, unsigned __int64 a3, unsigned int a4)
{
  char *v7; // rbx
  unsigned int v8; // r14d
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rdx
  int v12; // r13d
  __int64 v13; // rax
  __int16 v14; // ax
  unsigned __int16 k; // r8
  unsigned __int16 v16; // ax
  unsigned __int16 v17; // r10
  unsigned __int16 v18; // cx
  __int64 v19; // rdx
  char *v20; // rcx
  unsigned __int16 i; // r9
  unsigned int j; // eax

  v7 = 0;
  v8 = 0;
  v9 = a4 + a3;
  if ( v9 >= a3 )
  {
    v10 = a3 + 4;
    v11 = v10 + 8 * (*(unsigned __int8 *)(a3 + 3) | (unsigned __int64)(unsigned __int16)(*(_WORD *)(a3 + 2) << 8));
    if ( v11 <= v9 )
    {
      if ( a1 )
      {
        *a1 = 0;
        while ( 1 )
        {
          v12 = 0;
          if ( v10 >= v11 )
            break;
          if ( __ROR2__(*(_WORD *)v10, 8) == 4 && !*(_BYTE *)(v10 + 2) )
          {
            _mm_lfence();
            v7 = (char *)(a3
                        + (*(unsigned __int8 *)(v10 + 7)
                         | ((unsigned __int64)*(unsigned __int8 *)(v10 + 6) << 8)
                         | ((*(unsigned __int8 *)(v10 + 5) | (unsigned int)(unsigned __int16)(*(_WORD *)(v10 + 4) << 8)) << 16)));
            if ( (unsigned __int64)v7 < a3 )
              goto LABEL_38;
            v12 = *(unsigned __int8 *)(v10 + 3);
            break;
          }
          v10 += 8LL;
        }
        if ( !v7 )
          goto LABEL_37;
        if ( v7 + 10 >= v7 && (unsigned __int64)(v7 + 10) <= v9 )
        {
          LOBYTE(v10) = 1;
          v13 = ATMallocExt(512, v11, v10);
          *a1 = v13;
          if ( v13 )
          {
            v14 = __ROR2__(*(_WORD *)v7, 8);
            if ( v14 )
            {
              if ( v14 == 6 )
              {
                v16 = __ROR2__(*((_WORD *)v7 + 3), 8);
                v17 = __ROR2__(*((_WORD *)v7 + 4), 8);
                v18 = __ROR2__(*((_WORD *)v7 + 1), 8);
                if ( v16 <= 0xFFu && v16 + (unsigned int)v17 <= 0x100 )
                {
                  v19 = v18;
                  v20 = &v7[v18];
                  if ( v20 >= v7 && v19 == 2LL * v17 + 10 && (unsigned __int64)v20 <= v9 )
                  {
                    for ( i = 0; i < v17; ++i )
                      *(_WORD *)(*a1 + 2LL * (v16 + (unsigned int)i)) = __ROR2__(*(_WORD *)&v7[2 * i + 10], 8);
LABEL_31:
                    if ( a2 )
                    {
                      *a2 = 1;
                      for ( j = 0; j < 0x11; ++j )
                      {
                        if ( v12 == charSetMap[2 * j + 1] )
                        {
                          *a2 = charSetMap[2 * j];
                          break;
                        }
                      }
                    }
LABEL_37:
                    v8 = 1;
                  }
                }
              }
            }
            else if ( *((_WORD *)v7 + 1) == 1537 && v7 + 262 >= v7 && (unsigned __int64)(v7 + 262) <= v9 )
            {
              for ( k = 0; k < 0x100u; ++k )
                *(_WORD *)(*a1 + 2LL * k) = (unsigned __int8)v7[k + 6];
              goto LABEL_31;
            }
          }
        }
      }
    }
  }
LABEL_38:
  if ( v8 != 1 && a1 )
    EnhancedFree(a1);
  return v8;
}

```

## disassembly

```asm
0x1400348e0  mov     rax, rsp
0x1400348e3  mov     [rax+10h], rbx
0x1400348e7  mov     [rax+18h], rsi
0x1400348eb  mov     [rax+8], rcx
0x1400348ef  push    rdi
0x1400348f0  push    r12
0x1400348f2  push    r13
0x1400348f4  push    r14
0x1400348f6  push    r15
0x1400348f8  sub     rsp, 50h
0x1400348fc  mov     r10, r8
0x1400348ff  mov     r12, rdx
0x140034902  mov     rsi, rcx
0x140034905  xor     r11d, r11d
0x140034908  mov     ebx, r11d
0x14003490b  mov     r14d, r11d
0x14003490e  mov     [rax-40h], r11d
0x140034912  mov     eax, r9d
0x140034915  lea     r15, [rax+r8]
0x140034919  cmp     r15, r8
0x14003491c  jb      loc_140034B67
0x140034922  add     r8, 4
0x140034926  mov     [rsp+78h+var_38], r8
0x14003492b  movzx   eax, word ptr [r10+2]
0x140034930  shl     ax, 8
0x140034934  movzx   ecx, ax
0x140034937  movzx   eax, byte ptr [r10+3]
0x14003493c  or      rcx, rax
0x14003493f  lea     rdx, [r8+rcx*8]
0x140034943  cmp     rdx, r15
0x140034946  ja      loc_140034B67
0x14003494c  test    rsi, rsi
0x14003494f  jz      loc_140034B67
0x140034955  mov     [rsi], r11
0x140034958  mov     [rsp+78h+var_38], r8
0x14003495d  mov     r13d, r11d
0x140034960  cmp     r8, rdx
0x140034963  jnb     short loc_1400349BF
0x140034965  movzx   eax, word ptr [r8]
0x140034969  ror     ax, 8
0x14003496d  cmp     ax, 4
0x140034971  jnz     loc_140034A6B
0x140034977  cmp     [r8+2], r11b
0x14003497b  jnz     loc_140034A6B
0x140034981  lfence
0x140034984  movzx   eax, word ptr [r8+4]
0x140034989  shl     ax, 8
0x14003498d  movzx   ebx, ax
0x140034990  movzx   eax, byte ptr [r8+5]
0x140034995  or      ebx, eax
0x140034997  shl     ebx, 10h
0x14003499a  movzx   eax, byte ptr [r8+6]
0x14003499f  shl     rax, 8
0x1400349a3  or      rbx, rax
0x1400349a6  movzx   eax, byte ptr [r8+7]
0x1400349ab  or      rbx, rax
0x1400349ae  add     rbx, r10
0x1400349b1  cmp     rbx, r10
0x1400349b4  jb      loc_140034B67
0x1400349ba  movzx   r13d, byte ptr [r8+3]
0x1400349bf  test    rbx, rbx
0x1400349c2  jz      loc_140034B59
0x1400349c8  lea     rax, [rbx+0Ah]
0x1400349cc  cmp     rax, rbx
0x1400349cf  jb      loc_140034B67
0x1400349d5  cmp     rax, r15
0x1400349d8  ja      loc_140034B67
0x1400349de  mov     edi, 1
0x1400349e3  mov     r9b, dil
0x1400349e6  mov     r8b, dil
0x1400349e9  mov     ecx, 200h
0x1400349ee  call    ATMallocExt
0x1400349f3  mov     [rsi], rax
0x1400349f6  xor     r11d, r11d
0x1400349f9  test    rax, rax
0x1400349fc  jz      loc_140034B6C
0x140034a02  movzx   eax, word ptr [rbx]
0x140034a05  ror     ax, 8
0x140034a09  test    ax, ax
0x140034a0c  jnz     short loc_140034A74
0x140034a0e  mov     eax, 601h
0x140034a13  cmp     [rbx+2], ax
0x140034a17  jnz     loc_140034B6C
0x140034a1d  lea     rax, [rbx+106h]
0x140034a24  cmp     rax, rbx
0x140034a27  jb      loc_140034B6C
0x140034a2d  cmp     rax, r15
0x140034a30  ja      loc_140034B6C
0x140034a36  mov     r8d, r11d
0x140034a39  mov     [rsp+78h+var_48], r11w
0x140034a3f  mov     r9d, 100h
0x140034a45  cmp     r8w, r9w
0x140034a49  jnb     loc_140034B22
0x140034a4f  movzx   edx, r8w
0x140034a53  movzx   ecx, byte ptr [rdx+rbx+6]
0x140034a58  mov     rax, [rsi]
0x140034a5b  mov     [rax+rdx*2], cx
0x140034a5f  add     r8w, di
0x140034a63  mov     [rsp+78h+var_48], r8w
0x140034a69  jmp     short loc_140034A45
0x140034a6b  add     r8, 8
0x140034a6f  jmp     loc_140034958
0x140034a74  cmp     ax, 6
0x140034a78  jnz     loc_140034B6C
0x140034a7e  movzx   eax, word ptr [rbx+6]
0x140034a82  ror     ax, 8
0x140034a86  movzx   r10d, word ptr [rbx+8]
0x140034a8b  ror     r10w, 8
0x140034a90  movzx   ecx, word ptr [rbx+2]
0x140034a94  ror     cx, 8
0x140034a98  mov     edx, 0FFh
0x140034a9d  cmp     ax, dx
0x140034aa0  ja      loc_140034B6C
0x140034aa6  movzx   r11d, ax
0x140034aaa  movzx   eax, r10w
0x140034aae  add     eax, r11d
0x140034ab1  lea     r9d, [rdx+1]
0x140034ab5  cmp     eax, r9d
0x140034ab8  ja      loc_140034B6C
0x140034abe  movzx   edx, cx
0x140034ac1  lea     rcx, [rdx+rbx]
0x140034ac5  cmp     rcx, rbx
0x140034ac8  jb      loc_140034B6C
0x140034ace  movzx   eax, r10w
0x140034ad2  lea     rax, ds:0Ah[rax*2]
0x140034ada  cmp     rdx, rax
0x140034add  jnz     loc_140034B6C
0x140034ae3  cmp     rcx, r15
0x140034ae6  ja      loc_140034B6C
0x140034aec  xor     r9d, r9d
0x140034aef  mov     [rsp+78h+var_48], r9w
0x140034af5  cmp     r9w, r10w
0x140034af9  jnb     short loc_140034B1F
0x140034afb  movzx   eax, r9w
0x140034aff  movzx   r8d, word ptr [rbx+rax*2+0Ah]
0x140034b05  ror     r8w, 8
0x140034b0a  movzx   ecx, r9w
0x140034b0e  add     ecx, r11d
0x140034b11  mov     rax, [rsi]
0x140034b14  mov     [rax+rcx*2], r8w
0x140034b19  add     r9w, di
0x140034b1d  jmp     short loc_140034AEF
0x140034b1f  xor     r11d, r11d
0x140034b22  test    r12, r12
0x140034b25  jz      short loc_140034B5E
0x140034b27  mov     [rsp+78h+var_44], r11d
0x140034b2c  mov     [r12], edi
0x140034b30  mov     eax, r11d
0x140034b33  lea     rdx, charSetMap
0x140034b3a  mov     [rsp+78h+var_44], eax
0x140034b3e  cmp     eax, 11h
0x140034b41  jnb     short loc_140034B5E
0x140034b43  mov     ecx, eax
0x140034b45  cmp     r13d, [rdx+rcx*8+4]
0x140034b4a  jnz     short loc_140034B55
0x140034b4c  mov     eax, [rdx+rcx*8]
0x140034b4f  mov     [r12], eax
0x140034b53  jmp     short loc_140034B5E
0x140034b55  add     eax, edi
0x140034b57  jmp     short loc_140034B3A
0x140034b59  mov     edi, 1
0x140034b5e  mov     r14d, edi
0x140034b61  mov     [rsp+78h+var_40], edi
0x140034b65  jmp     short loc_140034B6C
0x140034b67  mov     edi, 1
0x140034b6c  cmp     r14d, edi
0x140034b6f  jz      short loc_140034B7E
0x140034b71  test    rsi, rsi
0x140034b74  jz      short loc_140034B7E
0x140034b76  mov     rcx, rsi
0x140034b79  call    EnhancedFree
0x140034b7e  mov     eax, r14d
0x140034b81  lea     r11, [rsp+78h+var_28]
0x140034b86  mov     rbx, [r11+38h]
0x140034b8a  mov     rsi, [r11+40h]
0x140034b8e  mov     rsp, r11
0x140034b91  pop     r15
0x140034b93  pop     r14
0x140034b95  pop     r13
0x140034b97  pop     r12
0x140034b99  pop     rdi
0x140034b9a  retn
0x14009682b  push    rbp
0x14009682d  sub     rsp, 30h
0x140096831  mov     rbp, rdx
0x140096834  cmp     dword ptr [rbp+38h], 1
0x140096838  jz      short loc_14009684C
0x14009683a  mov     rcx, [rbp+80h]
0x140096841  test    rcx, rcx
0x140096844  jz      short loc_14009684C
0x140096846  call    EnhancedFree
0x14009684b  nop
0x14009684c  add     rsp, 30h
0x140096850  pop     rbp
0x140096851  retn
```
