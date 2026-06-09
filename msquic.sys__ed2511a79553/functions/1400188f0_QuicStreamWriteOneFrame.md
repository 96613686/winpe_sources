# QuicStreamWriteOneFrame

- ea: `0x1400188f0`
- end: `0x140018ed0`
- name: `QuicStreamWriteOneFrame`
- size: `1504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400183d0`

## callees

- `0x1400188f0`
- `0x14002ea50`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140018bb7`
- `ntoskrnl!_snprintf_s` at `0x140018c39`
- `ntoskrnl!_snprintf_s` at `0x140018bb7`
- `ntoskrnl!_snprintf_s` at `0x140018c39`

## pseudocode

```c
__int64 __fastcall QuicStreamWriteOneFrame(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int16 *a4,
        _WORD *a5,
        __int64 a6,
        __int64 a7)
{
  unsigned __int64 v7; // r12
  unsigned __int8 v8; // r11
  _WORD *v9; // rdi
  char v10; // bl
  __int64 v11; // r15
  __int64 v13; // rbp
  char v14; // al
  char v15; // cl
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // r13
  __int64 *v19; // rbx
  unsigned int *v20; // rcx
  unsigned __int64 v21; // r9
  unsigned int v22; // esi
  unsigned __int64 i; // rax
  unsigned __int16 v24; // r15
  char *v25; // r12
  unsigned __int16 v26; // cx
  __int64 v27; // r8
  __int64 v28; // rdi
  unsigned int v29; // esi
  bool v30; // zf
  unsigned int v31; // eax
  __int64 v32; // rax
  unsigned __int16 v33; // si
  __int16 v34; // cx
  __int64 v35; // rcx
  unsigned int v36; // edx
  __int64 result; // rax
  char v38; // al
  unsigned __int16 v39; // r8
  char v40; // dl
  __int64 v41; // rcx
  char v42; // dl
  _QWORD *v43; // rcx
  __int64 v44; // rax
  __int16 v45; // ax
  char v46; // [rsp+40h] [rbp-138h]
  char *v48; // [rsp+50h] [rbp-128h]
  unsigned __int64 v50; // [rsp+68h] [rbp-110h]
  int v51; // [rsp+90h] [rbp-E8h]
  char DstBuf[128]; // [rsp+B0h] [rbp-C8h] BYREF

  v7 = a1[10];
  v8 = 0;
  v9 = a5;
  v10 = 9;
  v11 = a7;
  v13 = (__int64)a1;
  v46 = 0;
  v50 = v7;
  v51 = v7;
  if ( v7 >= 0x40 )
  {
    if ( v7 >= 0x4000 )
    {
      v14 = 9;
      if ( v7 < 0x40000000 )
        v14 = 5;
    }
    else
    {
      v14 = 3;
    }
  }
  else
  {
    v14 = 2;
  }
  v15 = 8;
  if ( a3 )
  {
    if ( a3 >= 0x40 )
    {
      if ( a3 >= 0x4000 )
      {
        if ( a3 < 0x40000000 )
          v15 = 4;
      }
      else
      {
        v15 = 2;
      }
    }
    else
    {
      v15 = 1;
    }
    v14 += v15;
  }
  v16 = (unsigned __int8)(v14 + 2);
  if ( *a5 < (unsigned __int16)v16 )
  {
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Can't squeeze in a frame (no room for header)");
LABEL_54:
      McTemplateU0ps_EtwWriteTransfer(v17, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, v13, DstBuf);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  v18 = (unsigned __int16)*a5 - v16;
  if ( v18 > *a4 )
    v18 = *a4;
  if ( v18 )
  {
    v19 = *(__int64 **)(v13 + 144);
    if ( v18 > *(_QWORD *)(v13 + 160) - a3 )
      v18 = *(_QWORD *)(v13 + 160) - a3;
    v48 = (char *)(a6 + v16);
    if ( !v19 || v19[3] > a3 )
      v19 = *(__int64 **)(v13 + 128);
    for ( ; v19[3] + v19[4] <= a3; v19 = (__int64 *)*v19 )
      ;
    v20 = (unsigned int *)v19[1];
    v21 = a3 - v19[3];
    v22 = 0;
    for ( i = *v20; v21 >= i; i = v20[4 * v22] )
    {
      v21 -= i;
      ++v22;
    }
    v24 = v18;
    v25 = v48;
    while ( 1 )
    {
      v26 = v24;
      v27 = v19[1] + 16LL * v22;
      if ( v24 >= (unsigned int)(*(_DWORD *)v27 - v21) )
        v26 = *(_WORD *)v27 - v21;
      v28 = v26;
      memmove(v25, (const void *)(v21 + *(_QWORD *)(v27 + 8)), v26);
      v25 += v28;
      v24 -= v28;
      if ( !v24 )
        break;
      v21 = 0;
      do
      {
        v29 = v22 + 1;
        v30 = v29 == *((_DWORD *)v19 + 4);
        if ( v29 == *((_DWORD *)v19 + 4) )
          v19 = (__int64 *)*v19;
        v31 = 0;
        if ( !v30 )
          v31 = v29;
        v22 = v31;
      }
      while ( !*(_DWORD *)(v19[1] + 16LL * v31) );
    }
    v13 = (__int64)a1;
    v11 = a7;
    v7 = v50;
    v9 = a5;
    v32 = a1[9];
    v33 = v18;
    a1[18] = v19;
    v10 = 9;
    *(_QWORD *)(v32 + 3752) += v18;
    v8 = 0;
  }
  else
  {
    v33 = 0;
  }
  v34 = *(_WORD *)(v13 + 96);
  if ( (v34 & 0x40) != 0 && a3 + v18 == *(_QWORD *)(v13 + 160) )
  {
    v8 = 1;
    v46 = 1;
  }
  else if ( !v18 && (v34 & 0x20) == 0 )
  {
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "No more frames");
      goto LABEL_54;
    }
LABEL_55:
    result = (__int64)a4;
    *a4 = 0;
    *v9 = 0;
    return result;
  }
  if ( (byte_14005C48D & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Built stream frame, offset=%llu len=%hu fin=%hhu", a3, v33, v8);
    McTemplateU0ps_EtwWriteTransfer(v35, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, v13, DstBuf);
    v8 = v46;
  }
  v36 = (unsigned __int16)*v9;
  *v9 = 0;
  *a4 = v33;
  if ( v7 >= 0x40 )
  {
    if ( v7 >= 0x4000 )
    {
      if ( v7 < 0x40000000 )
        v10 = 5;
    }
    else
    {
      v10 = 3;
    }
  }
  else
  {
    v10 = 2;
  }
  if ( a3 )
  {
    if ( a3 >= 0x40 )
    {
      if ( a3 >= 0x4000 )
      {
        v38 = 8;
        if ( a3 < 0x40000000 )
          v38 = 4;
      }
      else
      {
        v38 = 2;
      }
    }
    else
    {
      v38 = 1;
    }
    v10 += v38;
  }
  v39 = v33 + (unsigned __int8)(v10 + 2);
  if ( v36 >= (unsigned __int16)*v9 + (unsigned int)v39 )
  {
    v40 = 8;
    if ( a3 )
      v40 = 12;
    v41 = a6 + (unsigned __int16)*v9;
    v42 = v8 & 1 | v40 | 2;
    *(_BYTE *)v41 = v42;
    if ( v7 >= 0x40 )
    {
      if ( v7 >= 0x4000 )
      {
        if ( v7 >= 0x40000000 )
        {
          *(_QWORD *)(v41 + 1) = _byteswap_uint64(v7 | 0xC000000000000000uLL);
          v43 = (_QWORD *)(v41 + 9);
        }
        else
        {
          *(_DWORD *)(v41 + 1) = _byteswap_ulong(v51 | 0x80000000);
          v43 = (_QWORD *)(v41 + 5);
        }
      }
      else
      {
        *(_WORD *)(v41 + 1) = __ROR2__(v51 | 0x4000, 8);
        v43 = (_QWORD *)(v41 + 3);
      }
    }
    else
    {
      *(_BYTE *)(v41 + 1) = v51;
      v43 = (_QWORD *)(v41 + 2);
    }
    if ( (v42 & 4) != 0 )
    {
      if ( a3 >= 0x40 )
      {
        if ( a3 >= 0x4000 )
        {
          if ( a3 >= 0x40000000 )
          {
            *v43++ = _byteswap_uint64(a3 | 0xC000000000000000uLL);
          }
          else
          {
            *(_DWORD *)v43 = _byteswap_ulong(a3 | 0x80000000);
            v43 = (_QWORD *)((char *)v43 + 4);
          }
        }
        else
        {
          *(_WORD *)v43 = __ROR2__(a3 | 0x4000, 8);
          v43 = (_QWORD *)((char *)v43 + 2);
        }
      }
      else
      {
        *(_BYTE *)v43 = a3;
        v43 = (_QWORD *)((char *)v43 + 1);
      }
    }
    if ( (v42 & 2) != 0 )
      *(_WORD *)v43 = __ROR2__(v33 | 0x4000, 8);
    *v9 += v39;
  }
  else
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\stream_send.c", 863, "0");
    __int2c();
    v8 = v46;
  }
  v44 = *(unsigned __int8 *)(v11 + 90);
  *(_BYTE *)(v11 + 88) |= 4u;
  *(_WORD *)(v11 + 24 * v44 + 114) = 8;
  *(_QWORD *)(v11 + 24 * (*(unsigned __int8 *)(v11 + 90) + 4LL)) = v13;
  *(_QWORD *)(v11 + 24LL * *(unsigned __int8 *)(v11 + 90) + 104) = a3;
  *(_WORD *)(v11 + 24LL * *(unsigned __int8 *)(v11 + 90) + 112) = v33;
  *(_BYTE *)(v11 + 24LL * *(unsigned __int8 *)(v11 + 90) + 116) = 0;
  v45 = *(_WORD *)(v13 + 96);
  if ( (v45 & 0x20) != 0 )
  {
    *(_WORD *)(v13 + 96) = v45 & 0xFFDF;
    *(_BYTE *)(v11 + 24LL * *(unsigned __int8 *)(v11 + 90) + 116) |= 1u;
  }
  if ( v8 )
  {
    *(_WORD *)(v13 + 96) &= ~0x40u;
    *(_BYTE *)(v11 + 24LL * *(unsigned __int8 *)(v11 + 90) + 116) |= 2u;
  }
  result = QuicStreamSentMetadataIncrement(v13);
  ++*(_BYTE *)(v11 + 90);
  return result;
}

```

## disassembly

```asm
0x1400188f0  push    rbx
0x1400188f2  push    rbp
0x1400188f3  push    rdi
0x1400188f4  push    r12
0x1400188f6  push    r14
0x1400188f8  push    r15
0x1400188fa  sub     rsp, 148h
0x140018901  mov     rax, cs:__security_cookie
0x140018908  xor     rax, rsp
0x14001890b  mov     [rsp+178h+var_48], rax
0x140018913  mov     r12, [rcx+50h]
0x140018917  xor     r11b, r11b
0x14001891a  mov     rdi, [rsp+178h+arg_20]
0x140018922  mov     ebx, 9
0x140018927  mov     r15, [rsp+178h+arg_30]
0x14001892f  mov     r14, r8
0x140018932  mov     r8, [rsp+178h+arg_28]
0x14001893a  mov     rbp, rcx
0x14001893d  mov     [rsp+178h+var_120], rcx
0x140018942  mov     [rsp+178h+var_130], r9
0x140018947  lea     ecx, [rbx-4]
0x14001894a  mov     [rsp+178h+var_108], rdi
0x14001894f  mov     [rsp+178h+var_F8], r8
0x140018957  mov     [rsp+178h+var_118], r15
0x14001895c  mov     [rsp+178h+var_138], r11b
0x140018961  mov     [rsp+178h+var_110], r12
0x140018966  mov     qword ptr [rsp+178h+var_E8], r12
0x14001896e  cmp     r12, 40h ; '@'
0x140018972  jnb     short loc_140018978
0x140018974  mov     al, 2
0x140018976  jmp     short loc_140018991
0x140018978  cmp     r12, 4000h
0x14001897f  jnb     short loc_140018985
0x140018981  mov     al, 3
0x140018983  jmp     short loc_140018991
0x140018985  cmp     r12, 40000000h
0x14001898c  mov     eax, ebx
0x14001898e  cmovb   eax, ecx
0x140018991  mov     ecx, 8
0x140018996  lea     r10d, [rcx-4]
0x14001899a  test    r14, r14
0x14001899d  jz      short loc_1400189C3
0x14001899f  cmp     r14, 40h ; '@'
0x1400189a3  jnb     short loc_1400189A9
0x1400189a5  mov     cl, 1
0x1400189a7  jmp     short loc_1400189C1
0x1400189a9  cmp     r14, 4000h
0x1400189b0  jnb     short loc_1400189B6
0x1400189b2  mov     cl, 2
0x1400189b4  jmp     short loc_1400189C1
0x1400189b6  cmp     r14, 40000000h
0x1400189bd  cmovb   ecx, r10d
0x1400189c1  add     al, cl
0x1400189c3  add     al, 2
0x1400189c5  mov     [rsp+178h+arg_8], rsi
0x1400189cd  movzx   ecx, al
0x1400189d0  xor     r10d, r10d
0x1400189d3  movzx   eax, word ptr [rdi]
0x1400189d6  mov     [rsp+178h+var_38], r13
0x1400189de  cmp     ax, cx
0x1400189e1  jnb     short loc_1400189FC
0x1400189e3  test    cs:byte_14005C48D, 1
0x1400189ea  jz      loc_140018C5C
0x1400189f0  lea     r9, aCanTSqueezeInA; "Can't squeeze in a frame (no room for h"...
0x1400189f7  jmp     loc_140018C25
0x1400189fc  mov     r13, rax
0x1400189ff  movzx   eax, word ptr [r9]
0x140018a03  sub     r13, rcx
0x140018a06  cmp     r13, rax
0x140018a09  cmova   r13, rax
0x140018a0d  test    r13, r13
0x140018a10  jz      loc_140018B56
0x140018a16  mov     rax, [rbp+0A0h]
0x140018a1d  mov     rbx, [rbp+90h]
0x140018a24  sub     rax, r14
0x140018a27  cmp     r13, rax
0x140018a2a  cmova   r13, rax
0x140018a2e  lea     rax, [r8+rcx]
0x140018a32  mov     [rsp+178h+var_128], rax
0x140018a37  movzx   eax, r13w
0x140018a3b  mov     [rsp+178h+var_100], rax
0x140018a40  mov     [rsp+178h+var_136], ax
0x140018a45  test    rbx, rbx
0x140018a48  jz      short loc_140018A50
0x140018a4a  cmp     [rbx+18h], r14
0x140018a4e  jbe     short loc_140018A57
0x140018a50  mov     rbx, [rbp+80h]
0x140018a57  mov     rax, [rbx+20h]
0x140018a5b  add     rax, [rbx+18h]
0x140018a5f  cmp     rax, r14
0x140018a62  ja      short loc_140018A80
0x140018a64  nop     dword ptr [rax+00h]
0x140018a68  nop     dword ptr [rax+rax+00000000h]
0x140018a70  mov     rbx, [rbx]
0x140018a73  mov     rax, [rbx+20h]
0x140018a77  add     rax, [rbx+18h]
0x140018a7b  cmp     rax, r14
0x140018a7e  jbe     short loc_140018A70
0x140018a80  mov     rcx, [rbx+8]
0x140018a84  mov     r9, r14
0x140018a87  sub     r9, [rbx+18h]
0x140018a8b  mov     esi, r10d
0x140018a8e  mov     eax, [rcx]
0x140018a90  cmp     r9, rax
0x140018a93  jb      short loc_140018AB2
0x140018a95  nop     word ptr [rax+rax+00000000h]
0x140018aa0  sub     r9, rax
0x140018aa3  inc     esi
0x140018aa5  mov     eax, esi
0x140018aa7  add     rax, rax
0x140018aaa  mov     eax, [rcx+rax*8]
0x140018aad  cmp     r9, rax
0x140018ab0  jnb     short loc_140018AA0
0x140018ab2  movzx   r15d, [rsp+178h+var_136]
0x140018ab8  xor     ebp, ebp
0x140018aba  mov     r12, [rsp+178h+var_128]
0x140018abf  nop
0x140018ac0  movzx   eax, r15w
0x140018ac4  movzx   ecx, r15w
0x140018ac8  mov     r8d, esi
0x140018acb  shl     r8, 4
0x140018acf  add     r8, [rbx+8]
0x140018ad3  mov     edx, [r8]
0x140018ad6  sub     edx, r9d
0x140018ad9  cmp     eax, edx
0x140018adb  cmovnb  cx, dx
0x140018adf  mov     rdx, [r8+8]
0x140018ae3  movzx   edi, cx
0x140018ae6  add     rdx, r9; Src
0x140018ae9  mov     r8d, edi; Size
0x140018aec  mov     rcx, r12; void *
0x140018aef  call    memmove
0x140018af4  add     r12, rdi
0x140018af7  sub     r15w, di
0x140018afb  jz      short loc_140018B21
0x140018afd  mov     r9, rbp
0x140018b00  inc     esi
0x140018b02  cmp     esi, [rbx+10h]
0x140018b05  jnz     short loc_140018B0A
0x140018b07  mov     rbx, [rbx]
0x140018b0a  mov     eax, ebp
0x140018b0c  cmovnz  eax, esi
0x140018b0f  mov     ecx, eax
0x140018b11  mov     esi, eax
0x140018b13  add     rcx, rcx
0x140018b16  mov     rax, [rbx+8]
0x140018b1a  cmp     [rax+rcx*8], ebp
0x140018b1d  jz      short loc_140018B00
0x140018b1f  jmp     short loc_140018AC0
0x140018b21  mov     rbp, [rsp+178h+var_120]
0x140018b26  mov     r15, [rsp+178h+var_118]
0x140018b2b  mov     r12, [rsp+178h+var_110]
0x140018b30  mov     rdi, [rsp+178h+var_108]
0x140018b35  mov     rax, [rbp+48h]
0x140018b39  mov     rsi, [rsp+178h+var_100]
0x140018b3e  mov     [rbp+90h], rbx
0x140018b45  mov     ebx, 9
0x140018b4a  add     [rax+0EA8h], r13
0x140018b51  xor     r11b, r11b
0x140018b54  jmp     short loc_140018B59
0x140018b56  mov     rsi, r13
0x140018b59  movzx   ecx, word ptr [rbp+60h]
0x140018b5d  test    cl, 40h
0x140018b60  jz      loc_140018C03
0x140018b66  lea     rax, [r14+r13]
0x140018b6a  cmp     rax, [rbp+0A0h]
0x140018b71  jnz     loc_140018C03
0x140018b77  mov     r11b, 1
0x140018b7a  mov     [rsp+178h+var_138], r11b
0x140018b7f  test    cs:byte_14005C48D, 1
0x140018b86  jz      short loc_140018BE0
0x140018b88  movzx   eax, r11b
0x140018b8c  lea     r9, aBuiltStreamFra; "Built stream frame, offset=%llu len=%hu"...
0x140018b93  mov     [rsp+178h+var_148], eax
0x140018b97  mov     edx, 80h; SizeInBytes
0x140018b9c  movzx   ecx, si
0x140018b9f  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140018ba6  mov     [rsp+178h+var_150], ecx
0x140018baa  lea     rcx, [rsp+178h+DstBuf]; DstBuf
0x140018bb2  mov     [rsp+178h+var_158], r14
0x140018bb7  call    cs:__imp__snprintf_s
0x140018bbe  nop     dword ptr [rax+rax+00h]
0x140018bc3  lea     r9, [rsp+178h+DstBuf]
0x140018bcb  mov     r8, rbp
0x140018bce  lea     rdx, QuicStreamLogVerbose
0x140018bd5  call    McTemplateU0ps_EtwWriteTransfer
0x140018bda  movzx   r11d, [rsp+178h+var_138]
0x140018be0  movzx   edx, word ptr [rdi]
0x140018be3  xor     ecx, ecx
0x140018be5  mov     rax, [rsp+178h+var_130]
0x140018bea  mov     r13d, 4000h
0x140018bf0  mov     [rdi], cx
0x140018bf3  mov     [rax], si
0x140018bf6  cmp     r12, 40h ; '@'
0x140018bfa  jnb     short loc_140018C6E
0x140018bfc  mov     bl, 2
0x140018bfe  jmp     loc_140018C86
0x140018c03  test    r13, r13
0x140018c06  jnz     loc_140018B7F
0x140018c0c  test    cl, 20h
0x140018c0f  jnz     loc_140018B7F
0x140018c15  test    cs:byte_14005C48D, 1
0x140018c1c  jz      short loc_140018C5C
0x140018c1e  lea     r9, aNoMoreFrames; "No more frames"
0x140018c25  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140018c2c  lea     rcx, [rsp+178h+DstBuf]; DstBuf
0x140018c34  mov     edx, 80h; SizeInBytes
0x140018c39  call    cs:__imp__snprintf_s
0x140018c40  nop     dword ptr [rax+rax+00h]
0x140018c45  lea     r9, [rsp+178h+DstBuf]
0x140018c4d  mov     r8, rbp
0x140018c50  lea     rdx, QuicStreamLogVerbose
0x140018c57  call    McTemplateU0ps_EtwWriteTransfer
0x140018c5c  mov     rax, [rsp+178h+var_130]
0x140018c61  xor     ecx, ecx
0x140018c63  mov     [rax], cx
0x140018c66  mov     [rdi], cx
0x140018c69  jmp     loc_140018E9E
0x140018c6e  cmp     r12, r13
0x140018c71  jnb     short loc_140018C77
0x140018c73  mov     bl, 3
0x140018c75  jmp     short loc_140018C86
0x140018c77  cmp     r12, 40000000h
0x140018c7e  mov     eax, 5
0x140018c83  cmovb   ebx, eax
0x140018c86  test    r14, r14
0x140018c89  jz      short loc_140018CB4
0x140018c8b  cmp     r14, 40h ; '@'
0x140018c8f  jnb     short loc_140018C95
0x140018c91  mov     al, 1
0x140018c93  jmp     short loc_140018CB2
0x140018c95  cmp     r14, r13
0x140018c98  jnb     short loc_140018C9E
0x140018c9a  mov     al, 2
0x140018c9c  jmp     short loc_140018CB2
0x140018c9e  cmp     r14, 40000000h
0x140018ca5  mov     eax, 8
0x140018caa  mov     ecx, 4
0x140018caf  cmovb   eax, ecx
0x140018cb2  add     bl, al
0x140018cb4  movzx   r9d, word ptr [rdi]
0x140018cb8  add     bl, 2
0x140018cbb  movzx   r8d, bl
0x140018cbf  mov     r10b, 1
0x140018cc2  add     r8w, si
0x140018cc6  movzx   ecx, r8w
0x140018cca  add     ecx, r9d
0x140018ccd  cmp     edx, ecx
0x140018ccf  jnb     short loc_140018CF6
0x140018cd1  lea     r8, a0; "0"
0x140018cd8  mov     edx, 35Fh
0x140018cdd  lea     rcx, aCW1SMsquicSrcC_14; "C:\\__w\\1\\s\\msquic\\src\\core\\strea"...
0x140018ce4  call    CxPlatLogAssert
0x140018ce9  int     2Ch; Windows NT - assertion failure
0x140018ceb  movzx   r11d, [rsp+178h+var_138]
0x140018cf1  jmp     loc_140018DFF
0x140018cf6  test    r14, r14
0x140018cf9  mov     eax, 0Ch
0x140018cfe  mov     rcx, r9
0x140018d01  mov     edx, 8
0x140018d06  cmovnz  edx, eax
0x140018d09  mov     r9, 0C000000000000000h
0x140018d13  add     rcx, [rsp+178h+var_F8]
0x140018d1b  and     r10b, r10b
0x140018d1e  add     r10b, r10b
0x140018d21  movzx   eax, r11b
0x140018d25  or      dl, r10b
0x140018d28  and     al, 1
0x140018d2a  or      dl, al
0x140018d2c  mov     [rcx], dl
0x140018d2e  cmp     r12, 40h ; '@'
0x140018d32  jnb     short loc_140018D45
0x140018d34  movzx   eax, byte ptr [rsp+178h+var_E8]
0x140018d3c  mov     [rcx+1], al
0x140018d3f  add     rcx, 2
0x140018d43  jmp     short loc_140018D91
0x140018d45  cmp     r12, r13
0x140018d48  jnb     short loc_140018D64
0x140018d4a  movzx   eax, word ptr [rsp+178h+var_E8]
0x140018d52  or      ax, r13w
0x140018d56  ror     ax, 8
0x140018d5a  mov     [rcx+1], ax
0x140018d5e  add     rcx, 3
0x140018d62  jmp     short loc_140018D91
0x140018d64  cmp     r12, 40000000h
0x140018d6b  jnb     short loc_140018D83
0x140018d6d  mov     eax, [rsp+178h+var_E8]
0x140018d74  bts     eax, 1Fh
0x140018d78  bswap   eax
0x140018d7a  mov     [rcx+1], eax
0x140018d7d  add     rcx, 5
0x140018d81  jmp     short loc_140018D91
0x140018d83  or      r12, r9
0x140018d86  bswap   r12
0x140018d89  mov     [rcx+1], r12
0x140018d8d  add     rcx, 9
0x140018d91  test    dl, 4
0x140018d94  jz      short loc_140018DE8
0x140018d96  cmp     r14, 40h ; '@'
0x140018d9a  jnb     short loc_140018DA4
  ... truncated ...
```
