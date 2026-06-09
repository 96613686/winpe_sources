# _BERDecOctetStringWorker

- ea: `0x180004a60`
- end: `0x180004ed8`
- name: `_BERDecOctetStringWorker`
- size: `1144`
- prototype: `__int64 __fastcall(_DWORD *, int, unsigned int *, int, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x1800047e0`
- `0x180004810`
- `0x180004a30`
- `0x180004a60`

## callees

- `0x180001b30`
- `0x180001f50`
- `0x1800020a0`
- `0x180002200`
- `0x180004310`
- `0x180004a60`
- `0x1800062ec`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004dac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004dac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ead`

## pseudocode

```c
__int64 __fastcall BERDecOctetStringWorker(_DWORD *a1, int a2, unsigned int *a3, int a4, int a5)
{
  int v5; // r13d
  _DWORD *v9; // rbx
  unsigned __int8 *v10; // rax
  int v11; // ebp
  unsigned __int8 *v12; // r8
  char v13; // di
  int v14; // edi
  _DWORD *v15; // rax
  __int64 result; // rax
  int v17; // ecx
  int v18; // edx
  size_t v19; // rdi
  unsigned __int8 *v20; // r8
  int v21; // r14d
  int v22; // eax
  int v23; // r9d
  char *v24; // rbp
  unsigned int v25; // ecx
  int v26; // r9d
  int v27; // r9d
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 v30; // rbp
  int v31; // eax
  __int64 v32; // rax
  _BYTE *v33; // rax
  char v34; // cl
  unsigned int v35; // edx
  __int64 v36; // [rsp+30h] [rbp-48h] BYREF
  __int64 v37; // [rsp+38h] [rbp-40h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-38h] BYREF

  v5 = 0;
  v36 = 0;
  v37 = 0;
  v9 = a1;
  if ( !a5 )
  {
    ASN1DecSetError(a1, 4294966293LL);
    return 0xFFFFFFFFLL;
  }
  if ( !(a1[4] + a1[6] - a1[10]) )
    goto LABEL_34;
  v10 = (unsigned __int8 *)*((_QWORD *)a1 + 5);
  v11 = *v10;
  v12 = v10 + 1;
  v13 = *v10;
  *((_QWORD *)a1 + 5) = v10 + 1;
  v14 = v13 & 0x1F;
  if ( v14 == 31 )
  {
    v14 = 0;
    while ( (unsigned int)ASN1BERDecCheck(v9, 1) )
    {
      v33 = (_BYTE *)*((_QWORD *)v9 + 5);
      v34 = *v33;
      v12 = v33 + 1;
      *((_QWORD *)v9 + 5) = v33 + 1;
      if ( (v14 & 0xE0000000) == 0 )
      {
        v14 = (v14 << 7) | v34 & 0x7F;
        if ( v34 >= 0 )
          goto LABEL_4;
        if ( (unsigned int)++v5 < 4 )
          continue;
      }
      ASN1DecSetError(v9, 4294966285LL);
      return 0;
    }
    return 0;
  }
LABEL_4:
  if ( a2 != (v14 | ((v11 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v15 = (_DWORD *)*((_QWORD *)v9 + 7);
      v9[8] = -1011;
      if ( v9 == v15 )
        break;
      v9 = v15;
    }
    while ( v15 );
    return 0;
  }
  v17 = v9[4];
  v18 = v9[6];
  if ( !(v18 + v17 - (_DWORD)v12) )
    goto LABEL_34;
  v19 = *v12;
  v20 = v12 + 1;
  *((_QWORD *)v9 + 5) = v20;
  if ( (unsigned int)v19 < 0x80 )
    goto LABEL_11;
  if ( (_DWORD)v19 == 128 )
  {
    v19 = 0;
    v21 = 1;
    goto LABEL_14;
  }
  if ( (unsigned int)v19 > 0x84 )
  {
    v28 = 4294966293LL;
    goto LABEL_35;
  }
  v23 = v19 - 128;
  if ( (int)v19 - 128 > (unsigned int)(v18 + v17 - (_DWORD)v20) )
  {
LABEL_34:
    v28 = 4294966294LL;
LABEL_35:
    ASN1DecSetError(v9, v28);
    return 0;
  }
  v19 = 0;
  if ( v23 == 2 )
  {
LABEL_21:
    LODWORD(v19) = (*v20++ << 8) | v19;
    *((_QWORD *)v9 + 5) = v20;
LABEL_22:
    v19 = *v20 | (unsigned int)v19;
    *((_QWORD *)v9 + 5) = v20 + 1;
    LODWORD(v20) = (_DWORD)v20 + 1;
    goto LABEL_11;
  }
  v26 = v23 - 1;
  if ( !v26 )
    goto LABEL_22;
  v27 = v26 - 2;
  if ( !v27 )
  {
LABEL_33:
    LODWORD(v19) = (*v20++ << 16) | v19;
    *((_QWORD *)v9 + 5) = v20;
    goto LABEL_21;
  }
  if ( v27 == 1 )
  {
    LODWORD(v19) = *v20++ << 24;
    *((_QWORD *)v9 + 5) = v20;
    goto LABEL_33;
  }
LABEL_11:
  v21 = 0;
  if ( (unsigned int)v19 > v18 + v17 - (int)v20 )
  {
    ASN1DecSetError(v9, 4294966294LL);
    v22 = 0;
  }
  else
  {
    v22 = 1;
  }
  if ( !v22 )
    return 0;
LABEL_14:
  if ( (v11 & 0x20) == 0 )
  {
    *a3 = v19;
    if ( a4 )
    {
      result = 1;
      *((_QWORD *)a3 + 1) = *((_QWORD *)v9 + 5);
      *((_QWORD *)v9 + 5) += (unsigned int)v19;
      return result;
    }
    if ( !(_DWORD)v19 )
    {
      *((_QWORD *)a3 + 1) = 0;
      return 1;
    }
    v24 = 0;
    v25 = (v19 + 3) & 0xFFFFFFFC;
    if ( (unsigned int)v19 <= v25 )
    {
      if ( !v9[19] )
      {
        v24 = (char *)LocalAlloc(0x40u, v25);
        goto LABEL_27;
      }
      v35 = v9[26];
      if ( v35 >= v25 )
      {
        v24 = (char *)*((_QWORD *)v9 + 12);
        *((_QWORD *)v9 + 12) = &v24[v25];
        v9[26] = v35 - v25;
LABEL_27:
        if ( v24 )
          goto LABEL_28;
      }
    }
    ASN1DecSetError(v9, 4294966290LL);
LABEL_28:
    *((_QWORD *)a3 + 1) = v24;
    if ( v24 )
    {
      memcpy_0(v24, *((const void **)v9 + 5), v19);
      *((_QWORD *)v9 + 5) += v19;
      return 1;
    }
    return 0;
  }
  *a3 = 0;
  LODWORD(Src[1]) = 0;
  Src[0] = 0;
  *((_QWORD *)a3 + 1) = 0;
  if ( !(unsigned int)BERDecConstructed((_DWORD)v9, v19, v21, (unsigned int)&v36, (__int64)&v37) )
    return 0;
  v29 = v36;
  v30 = v37;
  while ( 1 )
  {
    if ( !(unsigned int)ASN1BERDecNotEndOfContents(v29, v30) )
      return ASN1BERDecEndOfContents(v9, v29, v30);
    LODWORD(Src[0]) = 0;
    Src[1] = 0;
    v31 = BERDecOctetStringWorker(v29, 4, (unsigned int)Src, a4, a5 - 1);
    if ( v31 == -1 )
      break;
    if ( !v31 )
      return 0;
    if ( LODWORD(Src[0]) )
    {
      if ( a4 )
      {
        *(_OWORD *)a3 = *(_OWORD *)Src;
        return ASN1BERDecEndOfContents(v9, v29, v30);
      }
      v32 = DecMemReAlloc(v29, *((_QWORD *)a3 + 1));
      *((_QWORD *)a3 + 1) = v32;
      if ( !v32 )
      {
        if ( !v9[19] )
          LocalFree(Src[1]);
        return 0;
      }
      memcpy_0((void *)(v32 + *a3), Src[1], LODWORD(Src[0]));
      *a3 += LODWORD(Src[0]);
      if ( !v9[19] )
        LocalFree(Src[1]);
      Src[1] = 0;
    }
  }
  if ( LODWORD(Src[0]) && !v9[19] )
    LocalFree(Src[1]);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180004a60  mov     rax, rsp
0x180004a63  mov     [rax+18h], rbx
0x180004a67  push    rsi
0x180004a68  push    r12
0x180004a6a  push    r13
0x180004a6c  push    r14
0x180004a6e  push    r15
0x180004a70  sub     rsp, 50h
0x180004a74  mov     r12d, [rsp+78h+arg_20]
0x180004a7c  xor     r13d, r13d
0x180004a7f  mov     [rax-48h], r13
0x180004a83  mov     r15d, r9d
0x180004a86  mov     [rax-40h], r13
0x180004a8a  mov     rsi, r8
0x180004a8d  mov     r14d, edx
0x180004a90  mov     rbx, rcx
0x180004a93  test    r12d, r12d
0x180004a96  jz      loc_180004CA6
0x180004a9c  mov     [rax+8], rbp
0x180004aa0  mov     [rax+10h], rdi
0x180004aa4  mov     eax, [rcx+18h]
0x180004aa7  sub     eax, [rcx+28h]
0x180004aaa  add     eax, [rcx+10h]
0x180004aad  cmp     eax, 1
0x180004ab0  jb      loc_180004C86
0x180004ab6  mov     rax, [rcx+28h]
0x180004aba  movzx   ebp, byte ptr [rax]
0x180004abd  lea     r8, [rax+1]
0x180004ac1  mov     edi, ebp
0x180004ac3  mov     [rcx+28h], r8
0x180004ac7  and     edi, 1Fh
0x180004aca  cmp     edi, 1Fh
0x180004acd  jz      loc_180004DE9
0x180004ad3  mov     eax, ebp
0x180004ad5  mov     r9d, r8d
0x180004ad8  and     eax, 0FFFFFFC0h
0x180004adb  shl     eax, 18h
0x180004ade  or      eax, edi
0x180004ae0  cmp     r14d, eax
0x180004ae3  jz      short loc_180004B25
0x180004ae5  mov     rax, [rbx+38h]
0x180004ae9  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x180004af0  cmp     rbx, rax
0x180004af3  jz      short loc_180004AFD
0x180004af5  mov     rbx, rax
0x180004af8  test    rax, rax
0x180004afb  jnz     short loc_180004AE5
0x180004afd  xor     eax, eax
0x180004aff  mov     rbp, [rsp+78h+arg_0]
0x180004b07  mov     rdi, [rsp+78h+arg_8]
0x180004b0f  mov     rbx, [rsp+78h+arg_10]
0x180004b17  add     rsp, 50h
0x180004b1b  pop     r15
0x180004b1d  pop     r14
0x180004b1f  pop     r13
0x180004b21  pop     r12
0x180004b23  pop     rsi
0x180004b24  retn
0x180004b25  mov     ecx, [rbx+10h]
0x180004b28  mov     eax, ecx
0x180004b2a  mov     edx, [rbx+18h]
0x180004b2d  sub     eax, r9d
0x180004b30  add     eax, edx
0x180004b32  cmp     eax, 1
0x180004b35  jb      loc_180004C86
0x180004b3b  movzx   edi, byte ptr [r8]
0x180004b3f  inc     r8
0x180004b42  mov     [rbx+28h], r8
0x180004b46  cmp     edi, 80h
0x180004b4c  jnb     short loc_180004B90
0x180004b4e  sub     ecx, r8d
0x180004b51  mov     r14d, r13d
0x180004b54  add     ecx, edx
0x180004b56  cmp     edi, ecx
0x180004b58  ja      loc_180004CBA
0x180004b5e  mov     eax, 1
0x180004b63  test    eax, eax
0x180004b65  jz      short loc_180004AFD
0x180004b67  test    bpl, 20h
0x180004b6b  jnz     loc_180004CCF
0x180004b71  mov     [rsi], edi
0x180004b73  test    r15d, r15d
0x180004b76  jz      short loc_180004BE9
0x180004b78  mov     rcx, [rbx+28h]
0x180004b7c  mov     eax, 1
0x180004b81  mov     [rsi+8], rcx
0x180004b85  mov     ecx, edi
0x180004b87  add     [rbx+28h], rcx
0x180004b8b  jmp     loc_180004AFF
0x180004b90  jz      loc_180004C4F
0x180004b96  cmp     edi, 84h
0x180004b9c  ja      loc_180004ECE
0x180004ba2  mov     eax, ecx
0x180004ba4  lea     r9d, [rdi-80h]
0x180004ba8  sub     eax, r8d
0x180004bab  add     eax, edx
0x180004bad  cmp     r9d, eax
0x180004bb0  ja      loc_180004C86
0x180004bb6  mov     edi, r13d
0x180004bb9  cmp     r9d, 2
0x180004bbd  jnz     loc_180004C5D
0x180004bc3  movzx   eax, byte ptr [r8]
0x180004bc7  shl     eax, 8
0x180004bca  or      edi, eax
0x180004bcc  inc     r8
0x180004bcf  mov     [rbx+28h], r8
0x180004bd3  movzx   eax, byte ptr [r8]
0x180004bd7  or      edi, eax
0x180004bd9  lea     rax, [r8+1]
0x180004bdd  mov     [rbx+28h], rax
0x180004be1  mov     r8d, eax
0x180004be4  jmp     loc_180004B4E
0x180004be9  test    edi, edi
0x180004beb  jz      loc_180004C98
0x180004bf1  lea     ecx, [rdi+3]
0x180004bf4  mov     rbp, r13
0x180004bf7  and     ecx, 0FFFFFFFCh
0x180004bfa  cmp     edi, ecx
0x180004bfc  ja      loc_180004DD7
0x180004c02  cmp     dword ptr [rbx+4Ch], 0
0x180004c06  jnz     loc_180004E66
0x180004c0c  mov     edx, ecx; uBytes
0x180004c0e  mov     ecx, 40h ; '@'; uFlags
0x180004c13  call    cs:__imp_LocalAlloc
0x180004c19  mov     rbp, rax
0x180004c1c  test    rbp, rbp
0x180004c1f  jz      loc_180004DD7
0x180004c25  mov     [rsi+8], rbp
0x180004c29  test    rbp, rbp
0x180004c2c  jz      loc_180004AFD
0x180004c32  mov     rdx, [rbx+28h]; Src
0x180004c36  mov     r8, rdi; Size
0x180004c39  mov     rcx, rbp; void *
0x180004c3c  call    memcpy_0
0x180004c41  add     [rbx+28h], rdi
0x180004c45  mov     eax, 1
0x180004c4a  jmp     loc_180004AFF
0x180004c4f  mov     edi, r13d
0x180004c52  mov     r14d, 1
0x180004c58  jmp     loc_180004B67
0x180004c5d  sub     r9d, 1
0x180004c61  jz      loc_180004BD3
0x180004c67  sub     r9d, 2
0x180004c6b  jnz     loc_180004E49
0x180004c71  movzx   eax, byte ptr [r8]
0x180004c75  shl     eax, 10h
0x180004c78  or      edi, eax
0x180004c7a  inc     r8
0x180004c7d  mov     [rbx+28h], r8
0x180004c81  jmp     loc_180004BC3
0x180004c86  mov     edx, 0FFFFFC16h
0x180004c8b  mov     rcx, rbx
0x180004c8e  call    ASN1DecSetError
0x180004c93  jmp     loc_180004AFD
0x180004c98  mov     [rsi+8], r13
0x180004c9c  mov     eax, 1
0x180004ca1  jmp     loc_180004AFF
0x180004ca6  mov     edx, 0FFFFFC15h
0x180004cab  call    ASN1DecSetError
0x180004cb0  mov     eax, 0FFFFFFFFh
0x180004cb5  jmp     loc_180004B0F
0x180004cba  mov     edx, 0FFFFFC16h
0x180004cbf  mov     rcx, rbx
0x180004cc2  call    ASN1DecSetError
0x180004cc7  mov     eax, r13d
0x180004cca  jmp     loc_180004B63
0x180004ccf  xor     eax, eax
0x180004cd1  mov     [rsi], r13d
0x180004cd4  mov     [rsp+78h+Src+4], rax
0x180004cd9  lea     r9, [rsp+78h+var_48]
0x180004cde  mov     [rsp+40h], rax
0x180004ce3  mov     r8d, r14d
0x180004ce6  lea     rax, [rsp+78h+var_40]
0x180004ceb  mov     [rsi+8], r13
0x180004cef  mov     edx, edi
0x180004cf1  mov     [rsp+78h+var_58], rax
0x180004cf6  mov     rcx, rbx
0x180004cf9  dec     r12d
0x180004cfc  call    _BERDecConstructed
0x180004d01  test    eax, eax
0x180004d03  jz      loc_180004AFD
0x180004d09  mov     rdi, [rsp+78h+var_48]
0x180004d0e  mov     rbp, [rsp+78h+var_40]
0x180004d13  mov     rdx, rbp
0x180004d16  mov     rcx, rdi
0x180004d19  call    ASN1BERDecNotEndOfContents
0x180004d1e  test    eax, eax
0x180004d20  jz      loc_180004DC4
0x180004d26  mov     r9d, r15d
0x180004d29  mov     dword ptr [rsp+78h+Src], r13d
0x180004d2e  lea     r8, [rsp+78h+Src]
0x180004d33  mov     [rsp+78h+Src+8], r13
0x180004d38  mov     edx, 4
0x180004d3d  mov     dword ptr [rsp+78h+var_58], r12d
0x180004d42  mov     rcx, rdi
0x180004d45  call    _BERDecOctetStringWorker
0x180004d4a  cmp     eax, 0FFFFFFFFh
0x180004d4d  jz      loc_180004EC5
0x180004d53  test    eax, eax
0x180004d55  jz      loc_180004AFD
0x180004d5b  mov     ecx, dword ptr [rsp+78h+Src]
0x180004d5f  test    ecx, ecx
0x180004d61  jz      short loc_180004D13
0x180004d63  test    r15d, r15d
0x180004d66  jnz     short loc_180004DBC
0x180004d68  mov     r8d, [rsi]
0x180004d6b  mov     rdx, [rsi+8]
0x180004d6f  add     r8d, ecx
0x180004d72  mov     rcx, rdi
0x180004d75  call    DecMemReAlloc
0x180004d7a  mov     [rsi+8], rax
0x180004d7e  test    rax, rax
0x180004d81  jz      loc_180004E88
0x180004d87  mov     ecx, [rsi]
0x180004d89  mov     r8d, dword ptr [rsp+78h+Src]; Size
0x180004d8e  add     rcx, rax; void *
0x180004d91  mov     rdx, [rsp+78h+Src+8]; Src
0x180004d96  call    memcpy_0
0x180004d9b  mov     eax, dword ptr [rsp+78h+Src]
0x180004d9f  add     [rsi], eax
0x180004da1  cmp     [rbx+4Ch], r15d
0x180004da5  jnz     short loc_180004DB2
0x180004da7  mov     rcx, [rsp+78h+Src+8]; hMem
0x180004dac  call    cs:__imp_LocalFree
0x180004db2  mov     [rsp+78h+Src+8], r13
0x180004db7  jmp     loc_180004D13
0x180004dbc  movups  xmm0, xmmword ptr [rsp+78h+Src]
0x180004dc1  movups  xmmword ptr [rsi], xmm0
0x180004dc4  mov     r8, rbp
0x180004dc7  mov     rdx, rdi
0x180004dca  mov     rcx, rbx
0x180004dcd  call    ASN1BERDecEndOfContents
0x180004dd2  jmp     loc_180004AFF
0x180004dd7  mov     edx, 0FFFFFC12h
0x180004ddc  mov     rcx, rbx
0x180004ddf  call    ASN1DecSetError
0x180004de4  jmp     loc_180004C25
0x180004de9  mov     edi, r13d
0x180004dec  mov     edx, 1
0x180004df1  mov     rcx, rbx
0x180004df4  call    ASN1BERDecCheck
0x180004df9  test    eax, eax
0x180004dfb  jz      loc_180004AFD
0x180004e01  mov     rax, [rbx+28h]
0x180004e05  movzx   ecx, byte ptr [rax]
0x180004e08  lea     r8, [rax+1]
0x180004e0c  mov     [rbx+28h], r8
0x180004e10  test    edi, 0E0000000h
0x180004e16  jnz     short loc_180004E37
0x180004e18  mov     eax, edi
0x180004e1a  mov     edx, ecx
0x180004e1c  and     ecx, 7Fh
0x180004e1f  shl     eax, 7
0x180004e22  mov     edi, ecx
0x180004e24  or      edi, eax
0x180004e26  test    dl, dl
0x180004e28  jns     loc_180004EBD
0x180004e2e  inc     r13d
0x180004e31  cmp     r13d, 4
0x180004e35  jb      short loc_180004DEC
0x180004e37  mov     edx, 0FFFFFC0Dh
0x180004e3c  mov     rcx, rbx
0x180004e3f  call    ASN1DecSetError
0x180004e44  jmp     loc_180004AFD
0x180004e49  cmp     r9d, 1
0x180004e4d  jnz     loc_180004B4E
0x180004e53  movzx   edi, byte ptr [r8]
0x180004e57  shl     edi, 18h
0x180004e5a  inc     r8
0x180004e5d  mov     [rbx+28h], r8
0x180004e61  jmp     loc_180004C71
0x180004e66  mov     edx, [rbx+68h]
0x180004e69  cmp     edx, ecx
0x180004e6b  jb      loc_180004DD7
0x180004e71  mov     rbp, [rbx+60h]
0x180004e75  mov     eax, ecx
0x180004e77  add     rax, rbp
0x180004e7a  sub     edx, ecx
0x180004e7c  mov     [rbx+60h], rax
0x180004e80  mov     [rbx+68h], edx
0x180004e83  jmp     loc_180004C1C
0x180004e88  cmp     dword ptr [rbx+4Ch], 0
0x180004e8c  jnz     loc_180004AFD
0x180004e92  mov     rcx, [rsp+78h+Src+8]; hMem
0x180004e97  call    cs:__imp_LocalFree
0x180004e9d  jmp     loc_180004AFD
0x180004ea2  cmp     dword ptr [rbx+4Ch], 0
0x180004ea6  jnz     short loc_180004EB3
0x180004ea8  mov     rcx, [rsp+78h+Src+8]; hMem
0x180004ead  call    cs:__imp_LocalFree
0x180004eb3  mov     eax, 0FFFFFFFFh
0x180004eb8  jmp     loc_180004AFF
0x180004ebd  xor     r13d, r13d
0x180004ec0  jmp     loc_180004AD3
0x180004ec5  cmp     dword ptr [rsp+78h+Src], 0
0x180004eca  jz      short loc_180004EB3
0x180004ecc  jmp     short loc_180004EA2
0x180004ece  mov     edx, 0FFFFFC15h
0x180004ed3  jmp     loc_180004C8B
```
