# Fill_ushort_ELUT_from_CurveTag

- ea: `0x1800079d4`
- end: `0x180007bae`
- name: `Fill_ushort_ELUT_from_CurveTag`
- size: `474`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180007418`
- `0x180007994`

## callees

- `0x1800079d4`
- `0x180007bb4`
- `0x1800219e4`
- `0x18003d040`

## pseudocode

```c
__int64 __fastcall Fill_ushort_ELUT_from_CurveTag(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  char v5; // r10
  __int64 v6; // rsi
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  char v10; // bl
  int v11; // r15d
  int v12; // edx
  int v13; // r11d
  int i; // r10d
  __int64 v15; // r9
  unsigned __int64 v16; // rcx
  int v17; // r12d
  int v18; // edx
  int v19; // eax
  char v20; // cl
  int v21; // edx
  unsigned int v24; // [rsp+30h] [rbp-88h]
  double v25[7]; // [rsp+38h] [rbp-80h] BYREF

  v5 = a3;
  v6 = a2;
  if ( a4 > 8 )
  {
    v8 = *(_DWORD *)(a1 + 8);
    if ( v8 )
    {
      if ( v8 != 1 )
      {
        if ( (unsigned __int8)(a3 - 1) > 0xEu || v8 >= 0x2000 )
        {
          return 87;
        }
        else
        {
          v9 = 0;
          v10 = 22;
          v11 = 1 << v5;
          v12 = 1 << a4;
          v13 = 0x1FFFFF;
          v24 = ((v8 - 1) << 18) / ((1 << v5) - 1);
          for ( i = (int)((double)(v12 - 1) / 65535.0 * 4194304.0); (i & 0xFFF8000) != 0; i >>= 1 )
          {
            v13 >>= 1;
            --v10;
          }
          v15 = 0;
          if ( v11 > 0 )
          {
            do
            {
              v16 = (unsigned __int64)(unsigned int)((int)(v15 * v24 + 4) >> 3) >> 15;
              v17 = *(unsigned __int16 *)(a1 + 2 * v16 + 12);
              v18 = i * v17;
              if ( (((int)(v15 * v24 + 4) >> 3) & 0x7FFF) != 0 )
              {
                v19 = *(unsigned __int16 *)(a1 + 2 * v16 + 14);
                v20 = v10 - 1;
                v21 = (v13 >> 1)
                    + (((((int)(v15 * v24 + 4) >> 3) & 0x7FFF) * ((i * (v19 - v17)) >> 15)) >> 1)
                    + (v18 >> 1);
              }
              else
              {
                v21 = v13 + v18;
                v20 = v10;
              }
              *(_WORD *)(v6 + 2 * v15) = v21 >> v20;
              v15 = (unsigned int)(v15 + 1);
            }
            while ( (int)v15 < v11 );
            return 0;
          }
        }
        return v9;
      }
      LOBYTE(a3) = a4;
      LOBYTE(a2) = v5;
      v25[0] = (double)*(unsigned __int16 *)(a1 + 12) * 0.00390625;
      return (unsigned int)Fill_ushort_ELUT_from_ParameterizedCurveFunc(
                             v6,
                             a2,
                             a3,
                             (unsigned int)ParameterizedCurveGamma,
                             (__int64)v25);
    }
    else
    {
      LOBYTE(a3) = a4;
      LOBYTE(a2) = v5;
      return (unsigned int)Fill_ushort_ELUT_identical(v6, a2, a3);
    }
  }
  return 87;
}

```

## disassembly

```asm
0x1800079d4  mov     [rsp+arg_0], rbx
0x1800079d9  push    rbp
0x1800079da  push    rsi
0x1800079db  push    rdi
0x1800079dc  push    r12
0x1800079de  push    r13
0x1800079e0  push    r14
0x1800079e2  push    r15
0x1800079e4  sub     rsp, 80h
0x1800079eb  mov     rax, cs:__security_cookie
0x1800079f2  xor     rax, rsp
0x1800079f5  mov     [rsp+0B8h+var_48], rax
0x1800079fa  mov     r11b, r9b
0x1800079fd  mov     r10b, r8b
0x180007a00  mov     rsi, rdx
0x180007a03  mov     rdi, rcx
0x180007a06  cmp     r9b, 8
0x180007a0a  jle     loc_180007B47
0x180007a10  mov     r9d, [rcx+8]
0x180007a14  test    r9d, r9d
0x180007a17  jz      loc_180007B93
0x180007a1d  mov     ebp, 1
0x180007a22  cmp     r9d, ebp
0x180007a25  jz      loc_180007B55
0x180007a2b  mov     al, r8b
0x180007a2e  sub     al, bpl
0x180007a31  cmp     al, 0Eh
0x180007a33  ja      loc_180007BA3
0x180007a39  cmp     r9d, 2000h
0x180007a40  jnb     loc_180007BA3
0x180007a46  xor     edx, edx
0x180007a48  lea     eax, [r9-1]
0x180007a4c  mov     cl, r10b
0x180007a4f  shl     eax, 12h
0x180007a52  xor     r8d, r8d
0x180007a55  lea     ebx, [rbp+15h]
0x180007a58  mov     r15d, ebp
0x180007a5b  mov     [rsp+0B8h+var_84], r8d
0x180007a60  shl     r15d, cl
0x180007a63  lea     ecx, [r15-1]
0x180007a67  div     ecx
0x180007a69  mov     cl, r11b
0x180007a6c  mov     edx, ebp
0x180007a6e  shl     edx, cl
0x180007a70  mov     r11d, 1FFFFFh
0x180007a76  sub     edx, ebp
0x180007a78  mov     [rsp+0B8h+var_88], eax
0x180007a7c  mov     eax, 0FFF8000h
0x180007a81  movd    xmm0, edx
0x180007a85  cvtdq2pd xmm0, xmm0
0x180007a89  divsd   xmm0, cs:__real@40efffe000000000
0x180007a91  mulsd   xmm0, cs:__real@4150000000000000
0x180007a99  cvttsd2si r10d, xmm0
0x180007a9e  jmp     short loc_180007AA8
0x180007aa0  sar     r10d, 1
0x180007aa3  sar     r11d, 1
0x180007aa6  sub     ebx, ebp
0x180007aa8  test    eax, r10d
0x180007aab  jnz     short loc_180007AA0
0x180007aad  mov     r14d, r11d
0x180007ab0  xor     r9d, r9d
0x180007ab3  sar     r14d, 1
0x180007ab6  test    r15d, r15d
0x180007ab9  jle     short loc_180007B1C
0x180007abb  mov     r8d, [rsp+0B8h+var_88]
0x180007ac0  mov     eax, r8d
0x180007ac3  imul    eax, r9d
0x180007ac7  add     eax, 4
0x180007aca  sar     eax, 3
0x180007acd  mov     ecx, eax
0x180007acf  mov     ebp, eax
0x180007ad1  shr     rcx, 0Fh
0x180007ad5  movzx   r12d, word ptr [rdi+rcx*2+0Ch]
0x180007adb  mov     edx, r12d
0x180007ade  imul    edx, r10d
0x180007ae2  and     ebp, 7FFFh
0x180007ae8  jz      short loc_180007B4E
0x180007aea  movzx   eax, word ptr [rdi+rcx*2+0Eh]
0x180007aef  lea     ecx, [rbx-1]
0x180007af2  sub     eax, r12d
0x180007af5  sar     edx, 1
0x180007af7  imul    eax, r10d
0x180007afb  sar     eax, 0Fh
0x180007afe  imul    eax, ebp
0x180007b01  sar     eax, 1
0x180007b03  add     eax, r14d
0x180007b06  add     edx, eax
0x180007b08  sar     edx, cl
0x180007b0a  mov     [rsi+r9*2], dx
0x180007b0f  inc     r9d
0x180007b12  cmp     r9d, r15d
0x180007b15  jl      short loc_180007AC0
0x180007b17  mov     r8d, [rsp+0B8h+var_84]
0x180007b1c  mov     eax, r8d
0x180007b1f  mov     rcx, [rsp+0B8h+var_48]
0x180007b24  xor     rcx, rsp; StackCookie
0x180007b27  call    __security_check_cookie
0x180007b2c  mov     rbx, [rsp+0B8h+arg_0]
0x180007b34  add     rsp, 80h
0x180007b3b  pop     r15
0x180007b3d  pop     r14
0x180007b3f  pop     r13
0x180007b41  pop     r12
0x180007b43  pop     rdi
0x180007b44  pop     rsi
0x180007b45  pop     rbp
0x180007b46  retn
0x180007b47  mov     eax, 57h ; 'W'
0x180007b4c  jmp     short loc_180007B1F
0x180007b4e  add     edx, r11d
0x180007b51  mov     ecx, ebx
0x180007b53  jmp     short loc_180007B08
0x180007b55  movzx   eax, word ptr [rcx+0Ch]
0x180007b59  lea     r9, ParameterizedCurveGamma
0x180007b60  mov     r8b, r11b
0x180007b63  mov     dl, r10b
0x180007b66  mov     rcx, rsi
0x180007b69  movd    xmm0, eax
0x180007b6d  lea     rax, [rsp+0B8h+var_80]
0x180007b72  cvtdq2pd xmm0, xmm0
0x180007b76  mov     [rsp+0B8h+var_98], rax
0x180007b7b  mulsd   xmm0, cs:__real@3f70000000000000
0x180007b83  movsd   [rsp+0B8h+var_80], xmm0
0x180007b89  call    Fill_ushort_ELUT_from_ParameterizedCurveFunc
0x180007b8e  mov     r8d, eax
0x180007b91  jmp     short loc_180007B1C
0x180007b93  mov     r8b, r11b
0x180007b96  mov     dl, r10b
0x180007b99  mov     rcx, rsi
0x180007b9c  call    Fill_ushort_ELUT_identical
0x180007ba1  jmp     short loc_180007B8E
0x180007ba3  mov     r8d, 57h ; 'W'
0x180007ba9  jmp     loc_180007B1C
```
