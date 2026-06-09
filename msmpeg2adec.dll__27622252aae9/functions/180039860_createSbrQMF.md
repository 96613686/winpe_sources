# createSbrQMF

- ea: `0x180039860`
- end: `0x180039b13`
- name: `createSbrQMF`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180039380`

## callees

- `0x180039860`
- `0x18003d2a0`

## import_xrefs

- `mfperfhelper!__imp_ippsZero_8u` at `0x18003995c`
- `mfperfhelper!__imp_ippsZero_8u` at `0x18003995c`

## pseudocode

```c
__int64 __fastcall createSbrQMF(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4, int a5, int a6, __int64 a7, __int64 a8)
{
  int v11; // ebx
  __int64 v13; // rax
  int v14; // r11d
  int v15; // r10d
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // ecx
  int v19; // edx
  _BYTE *v20; // r9
  __int16 v21; // bx
  char v22; // r11
  char v23; // r12
  char v24; // di
  char v25; // r13
  int v26; // r8d
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rax

  v11 = *(unsigned __int8 *)(a2 + 6) * *(unsigned __int8 *)(a2 + 7);
  v13 = *(_QWORD *)(a2 + 32);
  v14 = *(unsigned __int8 *)(v13 + 5);
  v15 = *(unsigned __int8 *)(v13 + 4);
  *(_QWORD *)(a1 + 32776) = 32;
  *(_QWORD *)(a1 + 32792) = 0;
  *(_QWORD *)(a1 + 32856) = 0;
  *(_QWORD *)(a1 + 32864) = 0;
  *(_QWORD *)(a1 + 32884) = 0;
  *(_DWORD *)(a1 + 32892) = 0;
  *(_QWORD *)(a1 + 32800) = cplxAnalysisQmfFiltering_SSE;
  *(_QWORD *)(a1 + 32784) = sbr_qmf_64_320_unscrambled;
  *(_QWORD *)(a1 + 32808) = sbr_cos_twiddle_L32;
  *(_QWORD *)(a1 + 32816) = sbr_sin_twiddle_L32;
  *(_QWORD *)(a1 + 32824) = sbr_alt_sin_twiddle_L32;
  *(_QWORD *)(a1 + 32832) = sbr_t_cos_L32;
  *(_QWORD *)(a1 + 32840) = sbr_t_sin_L32;
  *(_DWORD *)(a1 + 32872) = v11;
  *(_DWORD *)(a1 + 32876) = v15;
  *(_DWORD *)(a1 + 32880) = v14;
  v16 = a3 + 1280LL * a5;
  *(_QWORD *)(a1 + 32848) = v16;
  ippsZero_8u(v16, 1280);
  *(_QWORD *)(a1 + 32888) = a7;
  v17 = *(_QWORD *)(a2 + 32);
  v18 = *(unsigned __int8 *)(v17 + 5);
  v19 = *(unsigned __int8 *)(v17 + 4);
  *(_QWORD *)(a1 + 32896) = 64;
  *(_QWORD *)(a1 + 32920) = 0;
  *(_OWORD *)(a1 + 32952) = 0;
  *(_QWORD *)(a1 + 32968) = 0;
  *(_QWORD *)(a1 + 32984) = 0;
  *(_QWORD *)(a1 + 32912) = QmfFiltering_SSE;
  *(_QWORD *)(a1 + 32904) = sbr_qmf_64_640_unscrambled;
  *(_QWORD *)(a1 + 33008) = a8;
  *(_DWORD *)(a1 + 33000) = v18;
  *(_DWORD *)(a1 + 33004) = 640;
  *(_DWORD *)(a1 + 32992) = v11;
  *(_DWORD *)(a1 + 32996) = v19;
  *(_QWORD *)(a1 + 32928) = sbr_cos_twiddle_L64;
  *(_QWORD *)(a1 + 32936) = sbr_sin_twiddle_L64;
  *(_QWORD *)(a1 + 32944) = sbr_alt_sin_twiddle_L64;
  *(_QWORD *)(a1 + 32976) = a3 + 4 * (640 * a5 + 2560LL);
  v20 = *(_BYTE **)(a2 + 32);
  v21 = *(_WORD *)(a2 + 10);
  v22 = *(_BYTE *)(a1 + 32872);
  v23 = *(_BYTE *)(a1 + 33000);
  v24 = v20[2];
  v25 = v20[3];
  v26 = (unsigned __int8)v20[4];
  *(_QWORD *)(a1 + 33064) = a4;
  *a4 = v22;
  v27 = (unsigned __int64)(unsigned __int8)a5 << 8;
  v28 = v27 + a3 + 58368;
  *(_QWORD *)(a1 + 33096) = v28;
  *(_QWORD *)(a1 + 33104) = v28 + 128;
  v29 = v27 + a3 + 60416;
  *(_QWORD *)(a1 + 33112) = v29;
  *(_QWORD *)(a1 + 33120) = v29 + 128;
  if ( !(_BYTE)a5 )
  {
    **(_BYTE **)(a1 + 33064) = v22;
    if ( (unsigned int)resetLppTransposer(
                         (int)a1 + 33064,
                         0,
                         v26,
                         (int)v20 + 144,
                         v25,
                         (__int64)(v20 + 138),
                         v24,
                         v23,
                         v21) )
      return 0xFFFFFFFFLL;
  }
  *(_QWORD *)(a1 + 0x8000) = a3 + 3072 * (a5 + 11LL);
  return 0;
}

```

## disassembly

```asm
0x180039860  push    rbx
0x180039862  push    rbp
0x180039863  push    rsi
0x180039864  push    rdi
0x180039865  push    r12
0x180039867  push    r13
0x180039869  push    r14
0x18003986b  push    r15
0x18003986d  sub     rsp, 58h
0x180039871  movzx   eax, byte ptr [rdx+6]
0x180039875  mov     rbp, rcx
0x180039878  movzx   ebx, byte ptr [rdx+7]
0x18003987c  mov     rdi, rdx
0x18003987f  movsxd  r14, [rsp+98h+arg_20]
0x180039887  mov     rsi, r9
0x18003988a  imul    ebx, eax
0x18003988d  mov     r15, r8
0x180039890  mov     rax, [rdx+20h]
0x180039894  mov     edx, 500h
0x180039899  movzx   r11d, byte ptr [rax+5]
0x18003989e  movzx   r10d, byte ptr [rax+4]
0x1800398a3  xor     eax, eax
0x1800398a5  mov     qword ptr [rcx+8008h], 20h ; ' '
0x1800398b0  mov     [rcx+8018h], rax
0x1800398b7  mov     [rcx+8058h], rax
0x1800398be  mov     [rcx+8060h], rax
0x1800398c5  mov     [rcx+8074h], rax
0x1800398cc  mov     [rcx+807Ch], eax
0x1800398d2  lea     rax, cplxAnalysisQmfFiltering_SSE
0x1800398d9  mov     [rcx+8020h], rax
0x1800398e0  lea     rax, sbr_qmf_64_320_unscrambled
0x1800398e7  mov     [rcx+8010h], rax
0x1800398ee  lea     rax, sbr_cos_twiddle_L32
0x1800398f5  mov     [rcx+8028h], rax
0x1800398fc  lea     rax, sbr_sin_twiddle_L32
0x180039903  mov     [rcx+8030h], rax
0x18003990a  lea     rax, sbr_alt_sin_twiddle_L32
0x180039911  mov     [rcx+8038h], rax
0x180039918  lea     rax, sbr_t_cos_L32
0x18003991f  mov     [rcx+8040h], rax
0x180039926  lea     rax, sbr_t_sin_L32
0x18003992d  mov     [rcx+8048h], rax
0x180039934  lea     eax, [r14+r14*4]
0x180039938  shl     eax, 6
0x18003993b  cdqe
0x18003993d  mov     [rcx+8068h], ebx
0x180039943  mov     [rcx+806Ch], r10d
0x18003994a  mov     [rcx+8070h], r11d
0x180039951  lea     rcx, [r8+rax*4]
0x180039955  mov     [rbp+8050h], rcx
0x18003995c  call    cs:__imp_ippsZero_8u
0x180039963  nop     dword ptr [rax+rax+00h]
0x180039968  mov     rax, [rsp+98h+arg_30]
0x180039970  xorps   xmm0, xmm0
0x180039973  mov     [rbp+8078h], rax
0x18003997a  mov     rax, [rdi+20h]
0x18003997e  movzx   ecx, byte ptr [rax+5]
0x180039982  movzx   edx, byte ptr [rax+4]
0x180039986  xor     eax, eax
0x180039988  mov     qword ptr [rbp+8080h], 40h ; '@'
0x180039993  mov     [rbp+8098h], rax
0x18003999a  movups  xmmword ptr [rbp+80B8h], xmm0
0x1800399a1  mov     [rbp+80C8h], rax
0x1800399a8  mov     [rbp+80D8h], rax
0x1800399af  lea     rax, QmfFiltering_SSE
0x1800399b6  mov     [rbp+8090h], rax
0x1800399bd  lea     rax, sbr_qmf_64_640_unscrambled
0x1800399c4  mov     [rbp+8088h], rax
0x1800399cb  mov     rax, [rsp+98h+arg_38]
0x1800399d3  mov     [rbp+80F0h], rax
0x1800399da  lea     rax, sbr_cos_twiddle_L64
0x1800399e1  mov     [rbp+80E8h], ecx
0x1800399e7  mov     dword ptr [rbp+80ECh], 280h
0x1800399f1  mov     [rbp+80E0h], ebx
0x1800399f7  mov     [rbp+80E4h], edx
0x1800399fd  mov     [rbp+80A0h], rax
0x180039a04  lea     rax, sbr_sin_twiddle_L64
0x180039a0b  mov     [rbp+80A8h], rax
0x180039a12  lea     rax, sbr_alt_sin_twiddle_L64
0x180039a19  mov     [rbp+80B0h], rax
0x180039a20  lea     eax, [r14+r14*4]
0x180039a24  shl     eax, 7
0x180039a27  cdqe
0x180039a29  add     rax, 0A00h
0x180039a2f  lea     rcx, [r15+rax*4]
0x180039a33  mov     [rbp+80D0h], rcx
0x180039a3a  mov     r9, [rdi+20h]
0x180039a3e  movzx   ebx, word ptr [rdi+0Ah]
0x180039a42  movzx   r11d, byte ptr [rbp+8068h]
0x180039a4a  movzx   r12d, byte ptr [rbp+80E8h]
0x180039a52  movzx   edi, byte ptr [r9+2]
0x180039a57  movzx   r13d, byte ptr [r9+3]
0x180039a5c  lea     r10, [rbp+8128h]
0x180039a63  movzx   r8d, byte ptr [r9+4]
0x180039a68  lea     rax, [r15+0E400h]
0x180039a6f  mov     [r10], rsi
0x180039a72  mov     [rsi], r11b
0x180039a75  movzx   ecx, r14b
0x180039a79  shl     rcx, 8
0x180039a7d  add     rax, rcx
0x180039a80  mov     [r10+20h], rax
0x180039a84  sub     rax, 0FFFFFFFFFFFFFF80h
0x180039a88  mov     [r10+28h], rax
0x180039a8c  lea     rax, [r15+0EC00h]
0x180039a93  add     rax, rcx
0x180039a96  mov     [r10+30h], rax
0x180039a9a  sub     rax, 0FFFFFFFFFFFFFF80h
0x180039a9e  mov     [r10+38h], rax
0x180039aa2  test    r14b, r14b
0x180039aa5  jnz     short loc_180039AE9
0x180039aa7  mov     rax, [r10]
0x180039aaa  xor     edx, edx
0x180039aac  mov     [rsp+98h+var_58], bx
0x180039ab1  mov     rcx, r10
0x180039ab4  mov     [rsp+98h+var_60], r12b
0x180039ab9  mov     [rsp+98h+var_68], dil
0x180039abe  mov     [rax], r11b
0x180039ac1  lea     rax, [r9+8Ah]
0x180039ac8  mov     [rsp+98h+var_70], rax
0x180039acd  add     r9, 90h
0x180039ad4  mov     [rsp+98h+var_78], r13b
0x180039ad9  call    resetLppTransposer
0x180039ade  test    eax, eax
0x180039ae0  jz      short loc_180039AE9
0x180039ae2  mov     eax, 0FFFFFFFFh
0x180039ae7  jmp     short loc_180039B01
0x180039ae9  lea     rax, [r14+0Bh]
0x180039aed  lea     rcx, [rax+rax*2]
0x180039af1  shl     rcx, 0Ah
0x180039af5  add     rcx, r15
0x180039af8  mov     [rbp+8000h], rcx
0x180039aff  xor     eax, eax
0x180039b01  add     rsp, 58h
0x180039b05  pop     r15
0x180039b07  pop     r14
0x180039b09  pop     r13
0x180039b0b  pop     r12
0x180039b0d  pop     rdi
0x180039b0e  pop     rsi
0x180039b0f  pop     rbp
0x180039b10  pop     rbx
0x180039b11  retn
```
