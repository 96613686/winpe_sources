# GetMatrixFromProfile

- ea: `0x18002167c`
- end: `0x1800217d1`
- name: `GetMatrixFromProfile`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c308`
- `0x18001de14`
- `0x180020ae4`

## callees

- `0x180006008`
- `0x18000604c`
- `0x180018b68`
- `0x18002167c`
- `0x180021b38`
- `0x18003d040`

## pseudocode

```c
__int64 __fastcall GetMatrixFromProfile(__int64 a1, HPROFILE *a2, TAGTYPE a3, double a4)
{
  __int64 v5; // rdx
  unsigned int v6; // r10d
  __int64 i; // rax
  _OWORD *v8; // rax
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  _WORD v13[2]; // [rsp+38h] [rbp-49h] BYREF
  DWORD pcbElement[3]; // [rsp+3Ch] [rbp-45h] BYREF
  _OWORD v15[4]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v16; // [rsp+88h] [rbp+7h]
  _DWORD v17[10]; // [rsp+98h] [rbp+17h] BYREF

  pcbElement[0] = 36;
  v13[0] = 0;
  CMGetPartialProfileElement(*a2, a3, 0xCu, pcbElement, v17);
  SwapLongOffset((__int64)v17, 0, pcbElement[0]);
  if ( !v6 )
  {
    if ( pcbElement[0] == 36 )
    {
      do
      {
        for ( i = 0; i != 3; ++i )
          *((double *)v15 + 3 * v5 + i) = (double)(int)v17[3 * v5 + i] * 0.0000152587890625 * a4;
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (int)v5 < 3 );
      if ( (unsigned __int8)MatrixIsCloseToIdentity(v15) )
      {
        *(_QWORD *)(a1 + 80) = 0;
      }
      else
      {
        v8 = SmartNewPtr(72, v13);
        v6 = v13[0];
        *(_QWORD *)(a1 + 80) = v8;
        if ( !v6 )
        {
          v9 = v15[1];
          *v8 = v15[0];
          v10 = v15[2];
          v8[1] = v9;
          v11 = v15[3];
          v8[2] = v10;
          *(_QWORD *)&v10 = v16;
          v8[3] = v11;
          *((_QWORD *)v8 + 8) = v10;
        }
      }
    }
    else
    {
      return 2011;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002167c  mov     rax, rsp
0x18002167f  mov     [rax+20h], rbx
0x180021683  push    rbp
0x180021684  lea     rbp, [rax-5Fh]
0x180021688  sub     rsp, 0D0h
0x18002168f  movaps  xmmword ptr [rax-18h], xmm6
0x180021693  mov     rax, cs:__security_cookie
0x18002169a  xor     rax, rsp
0x18002169d  mov     [rbp+57h+var_18], rax
0x1800216a1  mov     r10, rdx
0x1800216a4  mov     [rbp+57h+pcbElement], 24h ; '$'
0x1800216ab  xor     eax, eax
0x1800216ad  lea     r9, [rbp+57h+pcbElement]; pcbElement
0x1800216b1  mov     r11d, r8d
0x1800216b4  mov     [rbp+57h+var_A0], ax
0x1800216b8  mov     rbx, rcx
0x1800216bb  lea     rax, [rbp+57h+var_40]
0x1800216bf  mov     rcx, [r10]; hProfile
0x1800216c2  mov     r8d, 0Ch; dwOffset
0x1800216c8  mov     edx, r11d; tag
0x1800216cb  mov     [rsp+0D0h+var_B0], rax; PVOID
0x1800216d0  movaps  xmm6, xmm3
0x1800216d3  call    CMGetPartialProfileElement
0x1800216d8  mov     r8d, [rbp+57h+pcbElement]
0x1800216dc  lea     rcx, [rbp+57h+var_40]
0x1800216e0  xor     edx, edx
0x1800216e2  mov     r10d, eax
0x1800216e5  call    SwapLongOffset
0x1800216ea  test    r10d, r10d
0x1800216ed  jnz     loc_1800217AC
0x1800216f3  cmp     [rbp+57h+pcbElement], 24h ; '$'
0x1800216f7  jz      short loc_180021704
0x1800216f9  mov     r10d, 7DBh
0x1800216ff  jmp     loc_1800217AC
0x180021704  lea     rax, [rdx+rdx*2]
0x180021708  lea     r8, [rbp+57h+var_40]
0x18002170c  lea     r8, [r8+rax*4]
0x180021710  lea     rax, [rdx+rdx*2]
0x180021714  lea     rcx, [rbp+57h+var_90]
0x180021718  lea     rcx, [rcx+rax*8]
0x18002171c  xor     eax, eax
0x18002171e  movd    xmm0, dword ptr [r8+rax*4]
0x180021724  cvtdq2pd xmm0, xmm0
0x180021728  mulsd   xmm0, cs:__real@3ef0000000000000
0x180021730  mulsd   xmm0, xmm6
0x180021734  movsd   qword ptr [rcx+rax*8], xmm0
0x180021739  inc     rax
0x18002173c  cmp     rax, 3
0x180021740  jnz     short loc_18002171E
0x180021742  inc     edx
0x180021744  cmp     edx, eax
0x180021746  jl      short loc_180021704
0x180021748  movss   xmm1, cs:__real@358637bd
0x180021750  lea     rcx, [rbp+57h+var_90]
0x180021754  call    MatrixIsCloseToIdentity
0x180021759  test    al, al
0x18002175b  jnz     short loc_1800217A4
0x18002175d  lea     rdx, [rbp+57h+var_A0]
0x180021761  mov     ecx, 48h ; 'H'
0x180021766  call    SmartNewPtr
0x18002176b  movsx   r10d, [rbp+57h+var_A0]
0x180021770  mov     [rbx+50h], rax
0x180021774  test    r10d, r10d
0x180021777  jnz     short loc_1800217AC
0x180021779  movaps  xmm0, [rbp+57h+var_90]
0x18002177d  movaps  xmm1, [rbp+57h+var_80]
0x180021781  movups  xmmword ptr [rax], xmm0
0x180021784  movaps  xmm0, [rbp+57h+var_70]
0x180021788  movups  xmmword ptr [rax+10h], xmm1
0x18002178c  movaps  xmm1, [rbp+57h+var_60]
0x180021790  movups  xmmword ptr [rax+20h], xmm0
0x180021794  movsd   xmm0, [rbp+57h+var_50]
0x180021799  movups  xmmword ptr [rax+30h], xmm1
0x18002179d  movsd   qword ptr [rax+40h], xmm0
0x1800217a2  jmp     short loc_1800217AC
0x1800217a4  mov     qword ptr [rbx+50h], 0
0x1800217ac  mov     eax, r10d
0x1800217af  mov     rcx, [rbp+57h+var_18]
0x1800217b3  xor     rcx, rsp; StackCookie
0x1800217b6  call    __security_check_cookie
0x1800217bb  lea     r11, [rsp+0D0h+var_s0]
0x1800217c3  mov     rbx, [r11+28h]
0x1800217c7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800217cc  mov     rsp, r11
0x1800217cf  pop     rbp
0x1800217d0  retn
```
