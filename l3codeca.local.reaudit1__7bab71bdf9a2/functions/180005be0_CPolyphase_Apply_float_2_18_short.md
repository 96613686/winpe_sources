# CPolyphase::Apply(float * (&)[2][18],short *)

- ea: `0x180005be0`
- end: `0x180005eed`
- name: `?Apply@CPolyphase@@QEAAPEAFAEAY11BC@PEAMPEAF@Z`
- size: `781`
- prototype: `__int16 *__fastcall(CPolyphase *__hidden this, float *(*)[2][18], __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004910`
- `0x180004da0`

## callees

- `0x180005be0`
- `0x180005f00`
- `0x180006340`
- `0x180006ed0`
- `0x180007290`

## pseudocode

```c
__int16 *__fastcall CPolyphase::Apply(CPolyphase *this, float *(*a2)[2][18], __int16 *a3, int a4)
{
  int v7; // r15d
  __int64 v8; // rbp
  __int64 v9; // r13
  int v10; // esi
  __int64 v11; // rbx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // rdx
  float *v16; // rax
  float v17; // xmm6_4
  float v18; // xmm5_4
  float v19; // xmm2_4
  float v20; // xmm1_4
  float v21; // xmm6_4
  float v22; // xmm5_4
  float v23; // xmm0_4
  float v24; // xmm1_4
  float v25; // xmm5_4
  float v26; // xmm6_4
  float v27; // xmm4_4
  float v28; // xmm3_4
  float v29; // xmm0_4
  float v30; // xmm5_4
  float v31; // xmm6_4
  float v32; // xmm2_4
  float v33; // xmm4_4
  float v34; // xmm1_4
  float v35; // xmm0_4
  int v36; // edx

  if ( *((_DWORD *)this + 12) )
    v7 = 1;
  else
    v7 = **((_DWORD **)this + 4);
  v8 = 0;
  v9 = 2 * ((__int64)(16 << v7) >> (*((_BYTE *)this + 40) + *((_BYTE *)this + 44)));
  do
  {
    v10 = 0;
    *(_DWORD *)this = ((unsigned __int16)*(_DWORD *)this - 32) & 0x1FF;
    if ( v7 > 0 )
    {
      v11 = 0;
      do
      {
        v12 = *((_DWORD *)this + 10);
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            if ( v13 == 1 )
            {
              v14 = *(int *)this;
              v15 = *((_QWORD *)this + v11 + 1);
              v16 = (*a2)[v11][v8];
              v17 = *v16 + v16[7];
              v18 = v16[1] + v16[6];
              v19 = (float)(v16[3] + v16[4]) + v17;
              v20 = (float)(v16[2] + v16[5]) + v18;
              v21 = (float)(v17 - (float)(v16[3] + v16[4])) * 0.54119611;
              v22 = (float)(v18 - (float)(v16[2] + v16[5])) * 1.306563;
              *(float *)(v15 + 4 * v14) = v20 + v19;
              *(float *)(v15 + 4 * v14 + 64) = (float)(v19 - v20) * 0.70710677;
              v23 = (float)(v21 - v22) * 0.70710677;
              *(float *)(v15 + 4 * v14 + 96) = v23;
              *(float *)(v15 + 4 * v14 + 32) = (float)(v22 + v21) + v23;
              v24 = (float)(v16[3] - v16[4]) * 2.5629156;
              v25 = (float)(*v16 - v16[7]) * 0.50979561;
              v26 = (float)(v16[1] - v16[6]) * 0.60134488;
              v27 = v24 + v25;
              v28 = (float)(v16[2] - v16[5]) * 0.89997619;
              v29 = v28 + v26;
              v30 = (float)(v25 - v24) * 0.54119611;
              v31 = (float)(v26 - v28) * 1.306563;
              v32 = v29 + v27;
              v33 = (float)(v27 - v29) * 0.70710677;
              v34 = (float)(v30 - v31) * 0.70710677;
              *(float *)(v15 + 4 * v14 + 112) = v34;
              v35 = (float)(v31 + v30) + v34;
              *(float *)(v15 + 4 * v14 + 16) = v35 + v33;
              *(float *)(v15 + 4 * v14 + 48) = v35 + v32;
              *(float *)(v15 + 4 * v14 + 80) = v34 + v33;
            }
          }
          else
          {
            cost16((*a2)[v11][v8], *((_QWORD *)this + v11 + 1) + 4LL * *(int *)this);
          }
        }
        else
        {
          cost32((*a2)[v11][v8], (float *)(*((_QWORD *)this + v11 + 1) + 4LL * *(int *)this));
        }
        ++v10;
        ++v11;
      }
      while ( v10 < v7 );
    }
    v36 = *(_DWORD *)this;
    if ( v7 == 1 )
      CPolyphase::window_band_m(this, v36, a3, a4);
    else
      CPolyphase::window_band_s(this, v36, a3);
    a3 = (__int16 *)((char *)a3 + v9);
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (int)v8 < 18 );
  return a3;
}

```

## disassembly

```asm
0x180005be0  mov     rax, rsp
0x180005be3  push    rbx
0x180005be4  push    rbp
0x180005be5  push    rsi
0x180005be6  push    rdi
0x180005be7  push    r12
0x180005be9  push    r13
0x180005beb  push    r14
0x180005bed  push    r15
0x180005bef  sub     rsp, 0A8h
0x180005bf6  cmp     dword ptr [rcx+30h], 0
0x180005bfa  mov     r12, r8
0x180005bfd  movaps  xmmword ptr [rax-58h], xmm6
0x180005c01  mov     r14, rdx
0x180005c04  movaps  xmmword ptr [rax-68h], xmm7
0x180005c08  mov     rdi, rcx
0x180005c0b  movaps  xmmword ptr [rax-78h], xmm8
0x180005c10  movaps  [rsp+0E8h+var_88], xmm9
0x180005c16  movaps  [rsp+0E8h+var_98], xmm10
0x180005c1c  movaps  [rsp+0E8h+var_A8], xmm11
0x180005c22  movaps  [rsp+0E8h+var_B8], xmm12
0x180005c28  movaps  [rsp+0E8h+var_C8], xmm13
0x180005c2e  jz      short loc_180005C38
0x180005c30  mov     r15d, 1
0x180005c36  jmp     short loc_180005C3F
0x180005c38  mov     rax, [rcx+20h]
0x180005c3c  mov     r15d, [rax]
0x180005c3f  mov     edx, [rcx+2Ch]
0x180005c42  mov     eax, 10h
0x180005c47  add     edx, [rcx+28h]
0x180005c4a  xor     ebp, ebp
0x180005c4c  movss   xmm7, cs:__real@3f3504f3
0x180005c54  mov     ecx, r15d
0x180005c57  movss   xmm8, cs:__real@3f0a8bd4
0x180005c60  movss   xmm9, cs:__real@3fa73d75
0x180005c69  movss   xmm10, cs:__real@3f0281f7
0x180005c72  movss   xmm11, cs:__real@3f19f1bd
0x180005c7b  movss   xmm12, cs:__real@3f6664d7
0x180005c84  movss   xmm13, cs:__real@402406cf
0x180005c8d  shl     eax, cl
0x180005c8f  movzx   ecx, dl
0x180005c92  movsxd  r13, eax
0x180005c95  sar     r13, cl
0x180005c98  add     r13, r13
0x180005c9b  nop     dword ptr [rax+rax+00h]
0x180005ca0  mov     eax, [rdi]
0x180005ca2  xor     esi, esi
0x180005ca4  sub     eax, 20h ; ' '
0x180005ca7  and     eax, 1FFh
0x180005cac  mov     [rdi], eax
0x180005cae  test    r15d, r15d
0x180005cb1  jle     loc_180005E81
0x180005cb7  xor     ebx, ebx
0x180005cb9  nop     dword ptr [rax+00000000h]
0x180005cc0  mov     ecx, [rdi+28h]
0x180005cc3  test    ecx, ecx
0x180005cc5  jz      loc_180005E4F
0x180005ccb  sub     ecx, 1
0x180005cce  jz      loc_180005E29
0x180005cd4  cmp     ecx, 1
0x180005cd7  jnz     loc_180005E73
0x180005cdd  movsxd  r8, dword ptr [rdi]
0x180005ce0  lea     rcx, [rbx+rbx*8]
0x180005ce4  mov     rdx, [rdi+rbx*8+8]
0x180005ce9  lea     rcx, ds:0[rcx*2]
0x180005cf1  add     rcx, rbp
0x180005cf4  mov     rax, [r14+rcx*8]
0x180005cf8  movss   xmm4, dword ptr [rax+8]
0x180005cfd  addss   xmm4, dword ptr [rax+14h]
0x180005d02  movss   xmm3, dword ptr [rax+0Ch]
0x180005d07  addss   xmm3, dword ptr [rax+10h]
0x180005d0c  movss   xmm6, dword ptr [rax]
0x180005d10  addss   xmm6, dword ptr [rax+1Ch]
0x180005d15  movss   xmm5, dword ptr [rax+4]
0x180005d1a  movaps  xmm1, xmm4
0x180005d1d  addss   xmm5, dword ptr [rax+18h]
0x180005d22  movaps  xmm2, xmm3
0x180005d25  addss   xmm2, xmm6
0x180005d29  subss   xmm6, xmm3
0x180005d2d  addss   xmm1, xmm5
0x180005d31  subss   xmm5, xmm4
0x180005d35  mulss   xmm6, xmm8
0x180005d3a  movaps  xmm0, xmm1
0x180005d3d  mulss   xmm5, xmm9
0x180005d42  addss   xmm0, xmm2
0x180005d46  subss   xmm2, xmm1
0x180005d4a  movss   dword ptr [rdx+r8*4], xmm0
0x180005d50  movaps  xmm0, xmm6
0x180005d53  subss   xmm0, xmm5
0x180005d57  mulss   xmm2, xmm7
0x180005d5b  addss   xmm5, xmm6
0x180005d5f  movss   dword ptr [rdx+r8*4+40h], xmm2
0x180005d66  mulss   xmm0, xmm7
0x180005d6a  movss   dword ptr [rdx+r8*4+60h], xmm0
0x180005d71  addss   xmm5, xmm0
0x180005d75  movss   dword ptr [rdx+r8*4+20h], xmm5
0x180005d7c  movss   xmm1, dword ptr [rax+0Ch]
0x180005d81  subss   xmm1, dword ptr [rax+10h]
0x180005d86  movss   xmm5, dword ptr [rax]
0x180005d8a  subss   xmm5, dword ptr [rax+1Ch]
0x180005d8f  movss   xmm3, dword ptr [rax+8]
0x180005d94  movss   xmm6, dword ptr [rax+4]
0x180005d99  subss   xmm6, dword ptr [rax+18h]
0x180005d9e  subss   xmm3, dword ptr [rax+14h]
0x180005da3  mulss   xmm1, xmm13
0x180005da8  mulss   xmm5, xmm10
0x180005dad  mulss   xmm6, xmm11
0x180005db2  movaps  xmm4, xmm1
0x180005db5  addss   xmm4, xmm5
0x180005db9  mulss   xmm3, xmm12
0x180005dbe  subss   xmm5, xmm1
0x180005dc2  movaps  xmm0, xmm3
0x180005dc5  addss   xmm0, xmm6
0x180005dc9  subss   xmm6, xmm3
0x180005dcd  mulss   xmm5, xmm8
0x180005dd2  movaps  xmm2, xmm0
0x180005dd5  mulss   xmm6, xmm9
0x180005dda  addss   xmm2, xmm4
0x180005dde  subss   xmm4, xmm0
0x180005de2  movaps  xmm1, xmm5
0x180005de5  subss   xmm1, xmm6
0x180005de9  addss   xmm6, xmm5
0x180005ded  mulss   xmm4, xmm7
0x180005df1  mulss   xmm1, xmm7
0x180005df5  addss   xmm6, xmm1
0x180005df9  movss   dword ptr [rdx+r8*4+70h], xmm1
0x180005e00  movaps  xmm0, xmm6
0x180005e03  addss   xmm6, xmm4
0x180005e07  addss   xmm0, xmm2
0x180005e0b  movss   dword ptr [rdx+r8*4+10h], xmm6
0x180005e12  movss   dword ptr [rdx+r8*4+30h], xmm0
0x180005e19  movaps  xmm0, xmm1
0x180005e1c  addss   xmm0, xmm4
0x180005e20  movss   dword ptr [rdx+r8*4+50h], xmm0
0x180005e27  jmp     short loc_180005E73
0x180005e29  movsxd  rcx, dword ptr [rdi]
0x180005e2c  mov     rax, [rdi+rbx*8+8]
0x180005e31  lea     rdx, [rax+rcx*4]
0x180005e35  lea     rcx, [rbx+rbx*8]
0x180005e39  lea     rcx, ds:0[rcx*2]
0x180005e41  add     rcx, rbp
0x180005e44  mov     rcx, [r14+rcx*8]
0x180005e48  call    cost16
0x180005e4d  jmp     short loc_180005E73
0x180005e4f  movsxd  rcx, dword ptr [rdi]
0x180005e52  mov     rax, [rdi+rbx*8+8]
0x180005e57  lea     rdx, [rax+rcx*4]
0x180005e5b  lea     rcx, [rbx+rbx*8]
0x180005e5f  lea     rcx, ds:0[rcx*2]
0x180005e67  add     rcx, rbp
0x180005e6a  mov     rcx, [r14+rcx*8]
0x180005e6e  call    cost32
0x180005e73  inc     esi
0x180005e75  inc     rbx
0x180005e78  cmp     esi, r15d
0x180005e7b  jl      loc_180005CC0
0x180005e81  mov     edx, [rdi]; int
0x180005e83  mov     r8, r12; __int16 *
0x180005e86  mov     rcx, rdi; this
0x180005e89  cmp     r15d, 1
0x180005e8d  jnz     short loc_180005E96
0x180005e8f  call    ?window_band_m@CPolyphase@@IEAAXHPEAFH@Z; CPolyphase::window_band_m(int,short *,int)
0x180005e94  jmp     short loc_180005E9B
0x180005e96  call    ?window_band_s@CPolyphase@@IEAAXHPEAFH@Z; CPolyphase::window_band_s(int,short *,int)
0x180005e9b  add     r12, r13
0x180005e9e  inc     ebp
0x180005ea0  cmp     ebp, 12h
0x180005ea3  jl      loc_180005CA0
0x180005ea9  movaps  xmm13, [rsp+0E8h+var_C8]
0x180005eaf  lea     r11, [rsp+0E8h+var_40]
0x180005eb7  movaps  xmm6, xmmword ptr [r11-18h]
0x180005ebc  mov     rax, r12
0x180005ebf  movaps  xmm7, xmmword ptr [r11-28h]
0x180005ec4  movaps  xmm8, xmmword ptr [r11-38h]
0x180005ec9  movaps  xmm9, xmmword ptr [r11-48h]
0x180005ece  movaps  xmm10, xmmword ptr [r11-58h]
0x180005ed3  movaps  xmm11, xmmword ptr [r11-68h]
0x180005ed8  movaps  xmm12, xmmword ptr [r11-78h]
0x180005edd  mov     rsp, r11
0x180005ee0  pop     r15
0x180005ee2  pop     r14
0x180005ee4  pop     r13
0x180005ee6  pop     r12
0x180005ee8  pop     rdi
0x180005ee9  pop     rsi
0x180005eea  pop     rbp
0x180005eeb  pop     rbx
0x180005eec  retn
```
