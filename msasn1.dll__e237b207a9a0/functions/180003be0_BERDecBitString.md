# _BERDecBitString

- ea: `0x180003be0`
- end: `0x180004026`
- name: `_BERDecBitString`
- size: `1094`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800022b0`
- `0x180003bc0`
- `0x180003be0`

## callees

- `0x180001b30`
- `0x180001f50`
- `0x1800020a0`
- `0x180002200`
- `0x180003be0`
- `0x180004310`
- `0x180004760`
- `0x1800062ec`
- `0x180008dd4`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f89`

## pseudocode

```c
__int64 __fastcall BERDecBitString(_DWORD *a1, int a2, unsigned int *a3, unsigned int a4)
{
  __int64 v7; // rbx
  int v8; // eax
  unsigned __int8 *v9; // rax
  int v10; // ebp
  unsigned __int8 *v11; // r8
  char v12; // di
  int v13; // edi
  __int64 v14; // rax
  __int64 result; // rax
  int v16; // ecx
  int v17; // edx
  unsigned int v18; // edi
  unsigned __int8 *v19; // r8
  int v20; // r14d
  int v21; // eax
  unsigned __int8 *v22; // rax
  unsigned int v23; // edx
  size_t v24; // rbp
  unsigned int v25; // ecx
  unsigned int v26; // edx
  unsigned int v27; // ecx
  int v28; // eax
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r9d
  void *v32; // rax
  _BYTE *v33; // rdx
  __int64 v34; // rdi
  __int64 v35; // r14
  unsigned int v36; // ecx
  void *v37; // rax
  unsigned int v38; // eax
  _BYTE *v39; // rdx
  int v40; // r15d
  _BYTE *v41; // rax
  char v42; // cl
  __int64 v43; // [rsp+30h] [rbp-68h] BYREF
  HLOCAL hMem[12]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+8h] BYREF

  LODWORD(hMem[1]) = 0;
  hMem[0] = 0;
  v7 = (__int64)a1;
  v8 = a1[6] + a1[4] - a1[10];
  v45 = 0;
  v43 = 0;
  if ( !v8 )
    goto LABEL_36;
  v9 = (unsigned __int8 *)*((_QWORD *)a1 + 5);
  v10 = *v9;
  v11 = v9 + 1;
  v12 = *v9;
  *((_QWORD *)a1 + 5) = v9 + 1;
  v13 = v12 & 0x1F;
  if ( v13 == 31 )
  {
    v13 = 0;
    v40 = 0;
    while ( (unsigned int)ASN1BERDecCheck(v7, 1) )
    {
      v41 = *(_BYTE **)(v7 + 40);
      v42 = *v41;
      v11 = v41 + 1;
      *(_QWORD *)(v7 + 40) = v41 + 1;
      if ( (v13 & 0xE0000000) == 0 )
      {
        v13 = (v13 << 7) | v42 & 0x7F;
        if ( v42 >= 0 )
          goto LABEL_3;
        if ( (unsigned int)++v40 < 4 )
          continue;
      }
      ASN1DecSetError(v7, 0xFFFFFC0D);
      return 0;
    }
    return 0;
  }
LABEL_3:
  if ( a2 != (v13 | ((v10 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v14 = *(_QWORD *)(v7 + 56);
      *(_DWORD *)(v7 + 32) = -1011;
      if ( v7 == v14 )
        break;
      v7 = v14;
    }
    while ( v14 );
    return 0;
  }
  v16 = *(_DWORD *)(v7 + 16);
  v17 = *(_DWORD *)(v7 + 24);
  if ( !(v17 + v16 - (_DWORD)v11) )
    goto LABEL_36;
  v18 = *v11;
  v19 = v11 + 1;
  *(_QWORD *)(v7 + 40) = v19;
  if ( v18 < 0x80 )
    goto LABEL_9;
  if ( v18 == 128 )
  {
    v18 = 0;
    v20 = 1;
    goto LABEL_12;
  }
  if ( v18 > 0x84 )
  {
LABEL_17:
    v26 = -1003;
LABEL_18:
    ASN1DecSetError(v7, v26);
    return 0;
  }
  v29 = v18 - 128;
  if ( v18 - 128 > v17 + v16 - (int)v19 )
  {
LABEL_36:
    v26 = -1002;
    goto LABEL_18;
  }
  v18 = 0;
  if ( v29 == 2 )
    goto LABEL_28;
  v30 = v29 - 1;
  if ( !v30 )
    goto LABEL_29;
  v31 = v30 - 2;
  if ( !v31 )
  {
LABEL_33:
    v18 |= *v19++ << 16;
    *(_QWORD *)(v7 + 40) = v19;
LABEL_28:
    v18 |= *v19++ << 8;
    *(_QWORD *)(v7 + 40) = v19;
LABEL_29:
    v18 |= *v19;
    *(_QWORD *)(v7 + 40) = v19 + 1;
    LODWORD(v19) = (_DWORD)v19 + 1;
    goto LABEL_9;
  }
  if ( v31 == 1 )
  {
    v18 = *v19++ << 24;
    *(_QWORD *)(v7 + 40) = v19;
    goto LABEL_33;
  }
LABEL_9:
  v20 = 0;
  if ( v18 > v17 + v16 - (int)v19 )
  {
    ASN1DecSetError(v7, 0xFFFFFC16);
    v21 = 0;
  }
  else
  {
    v21 = 1;
  }
  if ( !v21 )
    return 0;
LABEL_12:
  *a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  if ( (v10 & 0x20) != 0 )
  {
    if ( (unsigned int)BERDecConstructed(v7, v18, v20, (unsigned int)&v45, (__int64)&v43) )
    {
      v34 = v45;
      v35 = v43;
      while ( 1 )
      {
        do
        {
          if ( !(unsigned int)ASN1BERDecNotEndOfContents(v34, v35) )
            return ASN1BERDecEndOfContents(v7, v34, v35);
          if ( !(unsigned int)BERDecBitString(v34, 3, hMem, a4) )
            return 0;
        }
        while ( !LODWORD(hMem[0]) );
        if ( a4 )
        {
          *(_OWORD *)a3 = *(_OWORD *)hMem;
          return ASN1BERDecEndOfContents(v7, v34, v35);
        }
        v36 = *a3 + LODWORD(hMem[0]);
        if ( v36 < *a3 )
          break;
        if ( v36 + 7 < v36 )
          break;
        v37 = (void *)DecMemReAlloc(v34, *((_QWORD *)a3 + 1));
        *((_QWORD *)a3 + 1) = v37;
        if ( !v37 )
          break;
        ASN1bitcpy(v37);
        *a3 += LODWORD(hMem[0]);
        v38 = *a3;
        if ( (*a3 & 7) != 0 )
        {
          v39 = (_BYTE *)(*((_QWORD *)a3 + 1) + ((unsigned __int64)v38 >> 3));
          *v39 &= *((_BYTE *)&qword_18000C618 + (v38 & 7));
        }
        if ( !*(_DWORD *)(v7 + 76) )
          LocalFree(hMem[1]);
        hMem[1] = 0;
      }
      if ( !*(_DWORD *)(v7 + 76) )
        LocalFree(hMem[1]);
    }
    return 0;
  }
  if ( !v18 )
    return 1;
  v22 = *(unsigned __int8 **)(v7 + 40);
  if ( v18 == 1 )
  {
    *(_QWORD *)(v7 + 40) = v22 + 1;
    return 1;
  }
  v23 = *v22;
  if ( (unsigned __int8)v23 >= 8u )
    goto LABEL_17;
  v24 = v18 - 1;
  v25 = 8 * v24;
  if ( 8 * v24 > 0xFFFFFFFF )
    goto LABEL_17;
  *(_QWORD *)(v7 + 40) = v22 + 1;
  if ( v25 < v23 )
  {
    v27 = -1;
    v28 = -2147024362;
  }
  else
  {
    v27 = v25 - v23;
    v28 = 0;
  }
  if ( v28 < 0 )
    goto LABEL_17;
  *a3 = v27;
  if ( a4 )
  {
    *((_QWORD *)a3 + 1) = *(_QWORD *)(v7 + 40);
    result = 1;
    *(_QWORD *)(v7 + 40) += v24;
    return result;
  }
  if ( !v27 )
    return 1;
  if ( v27 + 7 < v27 )
  {
    ASN1DecSetError(v7, 0xFFFFFC14);
    *a3 = 0;
    return 0;
  }
  v32 = (void *)DecMemAlloc(v7, (v27 + 7) >> 3);
  *((_QWORD *)a3 + 1) = v32;
  if ( !v32 )
    return 0;
  memcpy_0(v32, *(const void **)(v7 + 40), v24);
  if ( (*a3 & 7) != 0 )
  {
    v33 = (_BYTE *)(*((_QWORD *)a3 + 1) + (unsigned int)(v24 - 1));
    *v33 &= *((_BYTE *)&qword_18000C618 + (*a3 & 7));
  }
  *(_QWORD *)(v7 + 40) += v24;
  return 1;
}

```

## disassembly

```asm
0x180003be0  mov     r11, rsp
0x180003be3  push    rbx
0x180003be4  push    rbp
0x180003be5  push    rsi
0x180003be6  push    rdi
0x180003be7  push    r12
0x180003be9  push    r13
0x180003beb  push    r14
0x180003bed  push    r15
0x180003bef  sub     rsp, 58h
0x180003bf3  xor     eax, eax
0x180003bf5  xor     r13d, r13d
0x180003bf8  mov     [r11-5Ch], rax
0x180003bfc  mov     r12d, r9d
0x180003bff  mov     [r11-60h], rax
0x180003c03  mov     rsi, r8
0x180003c06  mov     eax, [rcx+10h]
0x180003c09  mov     r14d, edx
0x180003c0c  sub     eax, [rcx+28h]
0x180003c0f  mov     rbx, rcx
0x180003c12  add     eax, [rcx+18h]
0x180003c15  mov     [r11+8], r13
0x180003c19  mov     [r11-68h], r13
0x180003c1d  cmp     eax, 1
0x180003c20  jb      loc_180003DE2
0x180003c26  mov     rax, [rcx+28h]
0x180003c2a  movzx   ebp, byte ptr [rax]
0x180003c2d  lea     r8, [rax+1]
0x180003c31  mov     edi, ebp
0x180003c33  mov     [rcx+28h], r8
0x180003c37  and     edi, 1Fh
0x180003c3a  cmp     edi, 1Fh
0x180003c3d  jz      loc_180003F99
0x180003c43  mov     eax, ebp
0x180003c45  mov     r9d, r8d
0x180003c48  and     eax, 0FFFFFFC0h
0x180003c4b  shl     eax, 18h
0x180003c4e  or      eax, edi
0x180003c50  cmp     r14d, eax
0x180003c53  jz      short loc_180003C80
0x180003c55  mov     rax, [rbx+38h]
0x180003c59  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x180003c60  cmp     rbx, rax
0x180003c63  jz      short loc_180003C6D
0x180003c65  mov     rbx, rax
0x180003c68  test    rax, rax
0x180003c6b  jnz     short loc_180003C55
0x180003c6d  xor     eax, eax
0x180003c6f  add     rsp, 58h
0x180003c73  pop     r15
0x180003c75  pop     r14
0x180003c77  pop     r13
0x180003c79  pop     r12
0x180003c7b  pop     rdi
0x180003c7c  pop     rsi
0x180003c7d  pop     rbp
0x180003c7e  pop     rbx
0x180003c7f  retn
0x180003c80  mov     ecx, [rbx+10h]
0x180003c83  mov     eax, ecx
0x180003c85  mov     edx, [rbx+18h]
0x180003c88  sub     eax, r9d
0x180003c8b  add     eax, edx
0x180003c8d  cmp     eax, 1
0x180003c90  jb      loc_180003DE2
0x180003c96  movzx   edi, byte ptr [r8]
0x180003c9a  inc     r8
0x180003c9d  mov     [rbx+28h], r8
0x180003ca1  cmp     edi, 80h
0x180003ca7  jnb     loc_180003D57
0x180003cad  sub     ecx, r8d
0x180003cb0  mov     r14d, r13d
0x180003cb3  add     ecx, edx
0x180003cb5  cmp     edi, ecx
0x180003cb7  ja      loc_180003E60
0x180003cbd  mov     eax, 1
0x180003cc2  test    eax, eax
0x180003cc4  jz      short loc_180003C6D
0x180003cc6  mov     [rsi], r13d
0x180003cc9  mov     [rsi+8], r13
0x180003ccd  test    bpl, 20h
0x180003cd1  jnz     loc_180003E75
0x180003cd7  test    edi, edi
0x180003cd9  jz      loc_180003DD8
0x180003cdf  mov     rax, [rbx+28h]
0x180003ce3  cmp     edi, 1
0x180003ce6  jz      loc_180003DD0
0x180003cec  movzx   edx, byte ptr [rax]
0x180003cef  cmp     dl, 8
0x180003cf2  jnb     short loc_180003D0C
0x180003cf4  lea     ebp, [rdi-1]
0x180003cf7  mov     r9d, 0FFFFFFFFh
0x180003cfd  lea     rcx, ds:0[rbp*8]
0x180003d05  mov     edi, ebp
0x180003d07  cmp     rcx, r9
0x180003d0a  jbe     short loc_180003D1E
0x180003d0c  mov     edx, 0FFFFFC15h
0x180003d11  mov     rcx, rbx
0x180003d14  call    ASN1DecSetError
0x180003d19  jmp     loc_180003C6D
0x180003d1e  inc     rax
0x180003d21  mov     [rbx+28h], rax
0x180003d25  cmp     ecx, edx
0x180003d27  jb      loc_180004019
0x180003d2d  sub     ecx, edx
0x180003d2f  mov     eax, r13d
0x180003d32  test    eax, eax
0x180003d34  js      short loc_180003D0C
0x180003d36  mov     [rsi], ecx
0x180003d38  test    r12d, r12d
0x180003d3b  jz      loc_180003DEC
0x180003d41  mov     rax, [rbx+28h]
0x180003d45  mov     [rsi+8], rax
0x180003d49  mov     eax, 1
0x180003d4e  add     [rbx+28h], rdi
0x180003d52  jmp     loc_180003C6F
0x180003d57  jz      short loc_180003DA0
0x180003d59  cmp     edi, 84h
0x180003d5f  ja      short loc_180003D0C
0x180003d61  mov     eax, ecx
0x180003d63  lea     r9d, [rdi-80h]
0x180003d67  sub     eax, r8d
0x180003d6a  add     eax, edx
0x180003d6c  cmp     r9d, eax
0x180003d6f  ja      short loc_180003DE2
0x180003d71  mov     edi, r13d
0x180003d74  cmp     r9d, 2
0x180003d78  jnz     short loc_180003DAE
0x180003d7a  movzx   eax, byte ptr [r8]
0x180003d7e  shl     eax, 8
0x180003d81  or      edi, eax
0x180003d83  inc     r8
0x180003d86  mov     [rbx+28h], r8
0x180003d8a  movzx   eax, byte ptr [r8]
0x180003d8e  or      edi, eax
0x180003d90  lea     rax, [r8+1]
0x180003d94  mov     [rbx+28h], rax
0x180003d98  mov     r8d, eax
0x180003d9b  jmp     loc_180003CAD
0x180003da0  mov     edi, r13d
0x180003da3  mov     r14d, 1
0x180003da9  jmp     loc_180003CC6
0x180003dae  sub     r9d, 1
0x180003db2  jz      short loc_180003D8A
0x180003db4  sub     r9d, 2
0x180003db8  jnz     loc_180003FFC
0x180003dbe  movzx   eax, byte ptr [r8]
0x180003dc2  shl     eax, 10h
0x180003dc5  or      edi, eax
0x180003dc7  inc     r8
0x180003dca  mov     [rbx+28h], r8
0x180003dce  jmp     short loc_180003D7A
0x180003dd0  lea     rcx, [rax+1]
0x180003dd4  mov     [rbx+28h], rcx
0x180003dd8  mov     eax, 1
0x180003ddd  jmp     loc_180003C6F
0x180003de2  mov     edx, 0FFFFFC16h
0x180003de7  jmp     loc_180003D11
0x180003dec  test    ecx, ecx
0x180003dee  jz      short loc_180003DD8
0x180003df0  lea     edx, [rcx+7]
0x180003df3  cmp     edx, ecx
0x180003df5  mov     rcx, rbx
0x180003df8  jb      short loc_180003E4E
0x180003dfa  shr     edx, 3
0x180003dfd  call    DecMemAlloc
0x180003e02  mov     [rsi+8], rax
0x180003e06  test    rax, rax
0x180003e09  jz      loc_180003C6D
0x180003e0f  mov     rdx, [rbx+28h]; Src
0x180003e13  mov     r8, rdi; Size
0x180003e16  mov     rcx, rax; void *
0x180003e19  call    memcpy_0
0x180003e1e  mov     r8d, [rsi]
0x180003e21  test    r8b, 7
0x180003e25  jz      short loc_180003E40
0x180003e27  lea     edx, [rbp-1]
0x180003e2a  and     r8d, 7
0x180003e2e  add     rdx, [rsi+8]
0x180003e32  lea     rbp, qword_18000C618
0x180003e39  movzx   eax, byte ptr [r8+rbp]
0x180003e3e  and     [rdx], al
0x180003e40  add     [rbx+28h], rdi
0x180003e44  mov     eax, 1
0x180003e49  jmp     loc_180003C6F
0x180003e4e  mov     edx, 0FFFFFC14h
0x180003e53  call    ASN1DecSetError
0x180003e58  mov     [rsi], r13d
0x180003e5b  jmp     loc_180003C6D
0x180003e60  mov     edx, 0FFFFFC16h
0x180003e65  mov     rcx, rbx
0x180003e68  call    ASN1DecSetError
0x180003e6d  mov     eax, r13d
0x180003e70  jmp     loc_180003CC2
0x180003e75  lea     rax, [rsp+98h+var_68]
0x180003e7a  mov     r8d, r14d
0x180003e7d  lea     r9, [rsp+98h+arg_0]
0x180003e85  mov     [rsp+98h+var_78], rax
0x180003e8a  mov     edx, edi
0x180003e8c  mov     rcx, rbx
0x180003e8f  call    _BERDecConstructed
0x180003e94  test    eax, eax
0x180003e96  jz      loc_180003C6D
0x180003e9c  mov     rdi, [rsp+98h+arg_0]
0x180003ea4  lea     rbp, qword_18000C618
0x180003eab  mov     r14, [rsp+98h+var_68]
0x180003eb0  mov     rdx, r14
0x180003eb3  mov     rcx, rdi
0x180003eb6  call    ASN1BERDecNotEndOfContents
0x180003ebb  test    eax, eax
0x180003ebd  jz      short loc_180003F1A
0x180003ebf  mov     r9d, r12d
0x180003ec2  lea     r8, [rsp+98h+hMem]
0x180003ec7  mov     edx, 3
0x180003ecc  mov     rcx, rdi
0x180003ecf  call    _BERDecBitString
0x180003ed4  test    eax, eax
0x180003ed6  jz      loc_180003C6D
0x180003edc  mov     ecx, dword ptr [rsp+98h+hMem]
0x180003ee0  test    ecx, ecx
0x180003ee2  jz      short loc_180003EB0
0x180003ee4  test    r12d, r12d
0x180003ee7  jnz     short loc_180003F12
0x180003ee9  add     ecx, [rsi]
0x180003eeb  cmp     ecx, [rsi]
0x180003eed  jb      short loc_180003EF8
0x180003eef  lea     r8d, [rcx+7]
0x180003ef3  cmp     r8d, ecx
0x180003ef6  jnb     short loc_180003F2D
0x180003ef8  cmp     [rbx+4Ch], r13d
0x180003efc  jnz     loc_180003C6D
0x180003f02  mov     rcx, [rsp+98h+hMem+8]; hMem
0x180003f07  call    cs:__imp_LocalFree
0x180003f0d  jmp     loc_180003C6D
0x180003f12  movups  xmm0, xmmword ptr [rsp+98h+hMem]
0x180003f17  movups  xmmword ptr [rsi], xmm0
0x180003f1a  mov     r8, r14
0x180003f1d  mov     rdx, rdi
0x180003f20  mov     rcx, rbx
0x180003f23  call    ASN1BERDecEndOfContents
0x180003f28  jmp     loc_180003C6F
0x180003f2d  mov     rdx, [rsi+8]
0x180003f31  mov     rcx, rdi
0x180003f34  shr     r8d, 3
0x180003f38  call    DecMemReAlloc
0x180003f3d  mov     [rsi+8], rax
0x180003f41  test    rax, rax
0x180003f44  jz      short loc_180003EF8
0x180003f46  mov     r9d, dword ptr [rsp+98h+hMem]
0x180003f4b  mov     rcx, rax; void *
0x180003f4e  mov     r8, [rsp+98h+hMem+8]
0x180003f53  mov     edx, [rsi]
0x180003f55  call    ASN1bitcpy
0x180003f5a  mov     eax, dword ptr [rsp+98h+hMem]
0x180003f5e  add     [rsi], eax
0x180003f60  mov     eax, [rsi]
0x180003f62  test    al, 7
0x180003f64  jz      short loc_180003F7E
0x180003f66  mov     r8d, eax
0x180003f69  mov     edx, eax
0x180003f6b  shr     rdx, 3
0x180003f6f  and     r8d, 7
0x180003f73  add     rdx, [rsi+8]
0x180003f77  movzx   eax, byte ptr [r8+rbp]
0x180003f7c  and     [rdx], al
0x180003f7e  cmp     [rbx+4Ch], r13d
0x180003f82  jnz     short loc_180003F8F
0x180003f84  mov     rcx, [rsp+98h+hMem+8]; hMem
0x180003f89  call    cs:__imp_LocalFree
0x180003f8f  mov     [rsp+98h+hMem+8], r13
0x180003f94  jmp     loc_180003EB0
0x180003f99  mov     edi, r13d
0x180003f9c  mov     r15d, r13d
0x180003f9f  mov     edx, 1
0x180003fa4  mov     rcx, rbx
0x180003fa7  call    ASN1BERDecCheck
0x180003fac  test    eax, eax
0x180003fae  jz      loc_180003C6D
0x180003fb4  mov     rax, [rbx+28h]
0x180003fb8  movzx   ecx, byte ptr [rax]
0x180003fbb  lea     r8, [rax+1]
0x180003fbf  mov     [rbx+28h], r8
0x180003fc3  test    edi, 0E0000000h
0x180003fc9  jnz     short loc_180003FEA
0x180003fcb  mov     eax, edi
0x180003fcd  mov     edx, ecx
0x180003fcf  and     ecx, 7Fh
0x180003fd2  shl     eax, 7
0x180003fd5  mov     edi, ecx
0x180003fd7  or      edi, eax
0x180003fd9  test    dl, dl
0x180003fdb  jns     loc_180003C43
0x180003fe1  inc     r15d
0x180003fe4  cmp     r15d, 4
0x180003fe8  jb      short loc_180003F9F
0x180003fea  mov     edx, 0FFFFFC0Dh
0x180003fef  mov     rcx, rbx
0x180003ff2  call    ASN1DecSetError
0x180003ff7  jmp     loc_180003C6D
0x180003ffc  cmp     r9d, 1
  ... truncated ...
```
