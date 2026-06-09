# ASN1BERDecCharString

- ea: `0x180002c20`
- end: `0x180003060`
- name: `ASN1BERDecCharString`
- size: `1088`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180002250`
- `0x180002c20`

## callees

- `0x180001b30`
- `0x180001f50`
- `0x1800020a0`
- `0x180002200`
- `0x180002c20`
- `0x180004310`
- `0x1800062ec`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002d4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002d4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fc5`

## pseudocode

```c
__int64 __fastcall ASN1BERDecCharString(_DWORD *a1, int a2, unsigned int *a3)
{
  __int64 v5; // rdi
  int v6; // eax
  unsigned __int8 *v7; // rax
  int v8; // ebp
  unsigned __int8 *v9; // r8
  char v10; // bl
  int v11; // ebx
  __int64 v12; // rax
  int v14; // ecx
  int v15; // edx
  __int64 v16; // rsi
  unsigned __int8 *v17; // r8
  int v18; // ebx
  int v19; // eax
  char *v20; // rbp
  unsigned int v21; // ecx
  int v22; // r9d
  int v23; // r9d
  int v24; // r9d
  __int64 v25; // rdx
  __int64 v26; // rax
  unsigned int v27; // edx
  int v28; // r15d
  _BYTE *v29; // rax
  char v30; // cl
  unsigned int v31; // edx
  unsigned int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rsi
  size_t Size; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-30h]
  __int64 v38; // [rsp+70h] [rbp+8h] BYREF
  __int64 v39; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(hMem) = 0;
  Size = 0;
  v5 = (__int64)a1;
  v6 = a1[6] + a1[4] - a1[10];
  v38 = 0;
  v39 = 0;
  if ( !v6 )
    goto LABEL_41;
  v7 = (unsigned __int8 *)*((_QWORD *)a1 + 5);
  v8 = *v7;
  v9 = v7 + 1;
  v10 = *v7;
  *((_QWORD *)a1 + 5) = v7 + 1;
  v11 = v10 & 0x1F;
  if ( v11 == 31 )
  {
    v11 = 0;
    v28 = 0;
    while ( (unsigned int)ASN1BERDecCheck((_DWORD *)v5, 1u) )
    {
      v29 = *(_BYTE **)(v5 + 40);
      v30 = *v29;
      v9 = v29 + 1;
      *(_QWORD *)(v5 + 40) = v29 + 1;
      if ( (v11 & 0xE0000000) == 0 )
      {
        v11 = (v11 << 7) | v30 & 0x7F;
        if ( v30 >= 0 )
          goto LABEL_3;
        if ( (unsigned int)++v28 < 4 )
          continue;
      }
      ASN1DecSetError(v5, 0xFFFFFC0D);
      return 0;
    }
    return 0;
  }
LABEL_3:
  if ( a2 != (v11 | ((v8 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v12 = *(_QWORD *)(v5 + 56);
      *(_DWORD *)(v5 + 32) = -1011;
      if ( v5 == v12 )
        break;
      v5 = v12;
    }
    while ( v12 );
    return 0;
  }
  v14 = *(_DWORD *)(v5 + 16);
  v15 = *(_DWORD *)(v5 + 24);
  if ( !(v15 + v14 - (_DWORD)v9) )
    goto LABEL_41;
  LODWORD(v16) = *v9;
  v17 = v9 + 1;
  *(_QWORD *)(v5 + 40) = v17;
  if ( (unsigned int)v16 < 0x80 )
    goto LABEL_9;
  if ( (_DWORD)v16 == 128 )
  {
    LODWORD(v16) = 0;
    v18 = 1;
    goto LABEL_12;
  }
  if ( (unsigned int)v16 > 0x84 )
  {
    v27 = -1003;
    goto LABEL_42;
  }
  v22 = v16 - 128;
  if ( (int)v16 - 128 > (unsigned int)(v15 + v14 - (_DWORD)v17) )
  {
LABEL_41:
    v27 = -1002;
LABEL_42:
    ASN1DecSetError(v5, v27);
    return 0;
  }
  LODWORD(v16) = 0;
  if ( v22 == 2 )
  {
LABEL_26:
    LODWORD(v16) = (*v17++ << 8) | v16;
    *(_QWORD *)(v5 + 40) = v17;
LABEL_27:
    LODWORD(v16) = *v17 | (unsigned int)v16;
    *(_QWORD *)(v5 + 40) = v17 + 1;
    LODWORD(v17) = (_DWORD)v17 + 1;
    goto LABEL_9;
  }
  v23 = v22 - 1;
  if ( !v23 )
    goto LABEL_27;
  v24 = v23 - 2;
  if ( !v24 )
  {
LABEL_31:
    LODWORD(v16) = (*v17++ << 16) | v16;
    *(_QWORD *)(v5 + 40) = v17;
    goto LABEL_26;
  }
  if ( v24 == 1 )
  {
    LODWORD(v16) = *v17++ << 24;
    *(_QWORD *)(v5 + 40) = v17;
    goto LABEL_31;
  }
LABEL_9:
  v18 = 0;
  if ( (unsigned int)v16 > v15 + v14 - (int)v17 )
  {
    ASN1DecSetError(v5, 0xFFFFFC16);
    v19 = 0;
  }
  else
  {
    v19 = 1;
  }
  if ( !v19 )
    return 0;
LABEL_12:
  if ( (v8 & 0x20) != 0 )
  {
    *a3 = 0;
    *((_QWORD *)a3 + 1) = 0;
    if ( (unsigned int)BERDecConstructed(v5, v16, v18, (unsigned int)&v38, (__int64)&v39) )
    {
      v34 = v38;
      v35 = v39;
      while ( 1 )
      {
        do
        {
          if ( !(unsigned int)ASN1BERDecNotEndOfContents(v34, v35) )
            return ASN1BERDecEndOfContents(v5, v34, v35);
          if ( !(unsigned int)ASN1BERDecCharString(v34, 4, &Size) )
            return 0;
        }
        while ( !(_DWORD)Size );
        v32 = *a3 + Size;
        if ( v32 < *a3 )
          break;
        if ( v32 + 1 < v32 )
          break;
        v33 = DecMemReAlloc(v34, *((_QWORD *)a3 + 1));
        *((_QWORD *)a3 + 1) = v33;
        if ( !v33 )
          break;
        memcpy_0((void *)(v33 + *a3), hMem, (unsigned int)Size);
        *a3 += Size;
        *(_BYTE *)(*a3 + *((_QWORD *)a3 + 1)) = 0;
        if ( !*(_DWORD *)(v5 + 76) )
          LocalFree(hMem);
        hMem = 0;
      }
      if ( !*(_DWORD *)(v5 + 76) )
        LocalFree(hMem);
    }
    return 0;
  }
  *a3 = v16;
  if ( (_DWORD)v16 )
  {
    if ( (int)v16 + 1 < (unsigned int)v16 )
      return 0;
    v20 = 0;
    v21 = (v16 + 4) & 0xFFFFFFFC;
    if ( (int)v16 + 1 <= v21 )
    {
      if ( !*(_DWORD *)(v5 + 76) )
      {
        v20 = (char *)LocalAlloc(0x40u, v21);
        goto LABEL_18;
      }
      v31 = *(_DWORD *)(v5 + 104);
      if ( v31 >= v21 )
      {
        v20 = *(char **)(v5 + 96);
        *(_QWORD *)(v5 + 96) = &v20[v21];
        *(_DWORD *)(v5 + 104) = v31 - v21;
LABEL_18:
        if ( v20 )
          goto LABEL_19;
      }
    }
    ASN1DecSetError(v5, 0xFFFFFC12);
LABEL_19:
    *((_QWORD *)a3 + 1) = v20;
    if ( v20 )
    {
      memcpy_0(v20, *(const void **)(v5 + 40), (unsigned int)v16);
      *(_QWORD *)(v5 + 40) += (unsigned int)v16;
      *(_BYTE *)((unsigned int)v16 + *((_QWORD *)a3 + 1)) = 0;
      if ( (g_dwDecodingRules & 2) == 0 )
      {
        v25 = *((_QWORD *)a3 + 1);
        while ( 1 )
        {
          LODWORD(v26) = v16;
          v16 = (unsigned int)(v16 - 1);
          if ( *(_BYTE *)(v16 + v25) )
            break;
          if ( !(_DWORD)v16 )
            return 1;
        }
        while ( (_DWORD)v26 )
        {
          v26 = (unsigned int)(v26 - 1);
          if ( !*(_BYTE *)(v26 + v25) )
          {
            if ( !*(_DWORD *)(v5 + 76) )
              LocalFree(*((HLOCAL *)a3 + 1));
            *((_QWORD *)a3 + 1) = 0;
            *a3 = 0;
            ASN1DecSetError(v5, 0xFFFFFC0B);
            return 0;
          }
        }
      }
      return 1;
    }
    return 0;
  }
  *((_QWORD *)a3 + 1) = 0;
  return 1;
}

```

## disassembly

```asm
0x180002c20  mov     r11, rsp
0x180002c23  mov     [r11+10h], rbx
0x180002c27  mov     [r11+18h], rbp
0x180002c2b  push    rsi
0x180002c2c  push    rdi
0x180002c2d  push    r12
0x180002c2f  push    r14
0x180002c31  push    r15
0x180002c33  sub     rsp, 40h
0x180002c37  xor     eax, eax
0x180002c39  xor     r12d, r12d
0x180002c3c  mov     [r11-34h], rax
0x180002c40  mov     r14, r8
0x180002c43  mov     [r11-38h], rax
0x180002c47  mov     esi, edx
0x180002c49  mov     eax, [rcx+10h]
0x180002c4c  mov     rdi, rcx
0x180002c4f  sub     eax, [rcx+28h]
0x180002c52  add     eax, [rcx+18h]
0x180002c55  mov     [r11+8], r12
0x180002c59  mov     [r11+20h], r12
0x180002c5d  cmp     eax, 1
0x180002c60  jb      loc_180002E6F
0x180002c66  mov     rax, [rcx+28h]
0x180002c6a  movzx   ebp, byte ptr [rax]
0x180002c6d  lea     r8, [rax+1]
0x180002c71  mov     ebx, ebp
0x180002c73  mov     [rcx+28h], r8
0x180002c77  and     ebx, 1Fh
0x180002c7a  cmp     ebx, 1Fh
0x180002c7d  jz      loc_180002EB1
0x180002c83  mov     eax, ebp
0x180002c85  mov     r9d, r8d
0x180002c88  and     eax, 0FFFFFFC0h
0x180002c8b  shl     eax, 18h
0x180002c8e  or      eax, ebx
0x180002c90  cmp     esi, eax
0x180002c92  jz      short loc_180002CC8
0x180002c94  mov     rax, [rdi+38h]
0x180002c98  mov     dword ptr [rdi+20h], 0FFFFFC0Dh
0x180002c9f  cmp     rdi, rax
0x180002ca2  jz      short loc_180002CAC
0x180002ca4  mov     rdi, rax
0x180002ca7  test    rax, rax
0x180002caa  jnz     short loc_180002C94
0x180002cac  xor     eax, eax
0x180002cae  mov     rbx, [rsp+68h+arg_8]
0x180002cb3  mov     rbp, [rsp+68h+arg_10]
0x180002cbb  add     rsp, 40h
0x180002cbf  pop     r15
0x180002cc1  pop     r14
0x180002cc3  pop     r12
0x180002cc5  pop     rdi
0x180002cc6  pop     rsi
0x180002cc7  retn
0x180002cc8  mov     ecx, [rdi+10h]
0x180002ccb  mov     eax, ecx
0x180002ccd  mov     edx, [rdi+18h]
0x180002cd0  sub     eax, r9d
0x180002cd3  add     eax, edx
0x180002cd5  cmp     eax, 1
0x180002cd8  jb      loc_180002E6F
0x180002cde  movzx   esi, byte ptr [r8]
0x180002ce2  inc     r8
0x180002ce5  mov     [rdi+28h], r8
0x180002ce9  cmp     esi, 80h
0x180002cef  jnb     loc_180002DA0
0x180002cf5  sub     ecx, r8d
0x180002cf8  mov     ebx, r12d
0x180002cfb  add     ecx, edx
0x180002cfd  cmp     esi, ecx
0x180002cff  ja      loc_180002E81
0x180002d05  mov     eax, 1
0x180002d0a  test    eax, eax
0x180002d0c  jz      short loc_180002CAC
0x180002d0e  test    bpl, 20h
0x180002d12  jnz     loc_180002FD2
0x180002d18  mov     [r14], esi
0x180002d1b  test    esi, esi
0x180002d1d  jz      loc_180002EA8
0x180002d23  lea     eax, [rsi+1]
0x180002d26  cmp     eax, esi
0x180002d28  jb      short loc_180002CAC
0x180002d2a  lea     ecx, [rax+3]
0x180002d2d  mov     rbp, r12
0x180002d30  and     ecx, 0FFFFFFFCh
0x180002d33  cmp     eax, ecx
0x180002d35  ja      loc_180002E96
0x180002d3b  cmp     [rdi+4Ch], r12d
0x180002d3f  jnz     loc_180002F31
0x180002d45  mov     edx, ecx; uBytes
0x180002d47  mov     ecx, 40h ; '@'; uFlags
0x180002d4c  call    cs:__imp_LocalAlloc
0x180002d52  mov     rbp, rax
0x180002d55  test    rbp, rbp
0x180002d58  jz      loc_180002E96
0x180002d5e  mov     [r14+8], rbp
0x180002d62  test    rbp, rbp
0x180002d65  jz      loc_180002CAC
0x180002d6b  mov     rdx, [rdi+28h]; Src
0x180002d6f  mov     rcx, rbp; void *
0x180002d72  mov     r8d, esi; Size
0x180002d75  mov     ebx, esi
0x180002d77  call    memcpy_0
0x180002d7c  add     [rdi+28h], rbx
0x180002d80  mov     rax, [r14+8]
0x180002d84  mov     [rbx+rax], r12b
0x180002d88  mov     eax, cs:g_dwDecodingRules
0x180002d8e  test    al, 2
0x180002d90  jz      loc_180002E20
0x180002d96  mov     eax, 1
0x180002d9b  jmp     loc_180002CAE
0x180002da0  jz      short loc_180002DF1
0x180002da2  cmp     esi, 84h
0x180002da8  ja      loc_180003056
0x180002dae  mov     eax, ecx
0x180002db0  lea     r9d, [rsi-80h]
0x180002db4  sub     eax, r8d
0x180002db7  add     eax, edx
0x180002db9  cmp     r9d, eax
0x180002dbc  ja      loc_180002E6F
0x180002dc2  mov     esi, r12d
0x180002dc5  cmp     r9d, 2
0x180002dc9  jnz     short loc_180002DFE
0x180002dcb  movzx   eax, byte ptr [r8]
0x180002dcf  shl     eax, 8
0x180002dd2  or      esi, eax
0x180002dd4  inc     r8
0x180002dd7  mov     [rdi+28h], r8
0x180002ddb  movzx   eax, byte ptr [r8]
0x180002ddf  or      esi, eax
0x180002de1  lea     rax, [r8+1]
0x180002de5  mov     [rdi+28h], rax
0x180002de9  mov     r8d, eax
0x180002dec  jmp     loc_180002CF5
0x180002df1  mov     esi, r12d
0x180002df4  mov     ebx, 1
0x180002df9  jmp     loc_180002D0E
0x180002dfe  sub     r9d, 1
0x180002e02  jz      short loc_180002DDB
0x180002e04  sub     r9d, 2
0x180002e08  jnz     loc_180002F14
0x180002e0e  movzx   eax, byte ptr [r8]
0x180002e12  shl     eax, 10h
0x180002e15  or      esi, eax
0x180002e17  inc     r8
0x180002e1a  mov     [rdi+28h], r8
0x180002e1e  jmp     short loc_180002DCB
0x180002e20  mov     rdx, [r14+8]
0x180002e24  mov     eax, esi
0x180002e26  dec     esi
0x180002e28  cmp     [rsi+rdx], r12b
0x180002e2c  jnz     short loc_180002E37
0x180002e2e  test    esi, esi
0x180002e30  jnz     short loc_180002E24
0x180002e32  jmp     loc_180002D96
0x180002e37  test    eax, eax
0x180002e39  jz      loc_180002D96
0x180002e3f  dec     eax
0x180002e41  mov     rcx, rdx; hMem
0x180002e44  cmp     [rax+rdx], r12b
0x180002e48  jnz     short loc_180002E37
0x180002e4a  cmp     [rdi+4Ch], r12d
0x180002e4e  jnz     short loc_180002E56
0x180002e50  call    cs:__imp_LocalFree
0x180002e56  mov     [r14+8], r12
0x180002e5a  mov     edx, 0FFFFFC0Bh
0x180002e5f  mov     rcx, rdi
0x180002e62  mov     [r14], r12d
0x180002e65  call    ASN1DecSetError
0x180002e6a  jmp     loc_180002CAC
0x180002e6f  mov     edx, 0FFFFFC16h
0x180002e74  mov     rcx, rdi
0x180002e77  call    ASN1DecSetError
0x180002e7c  jmp     loc_180002CAC
0x180002e81  mov     edx, 0FFFFFC16h
0x180002e86  mov     rcx, rdi
0x180002e89  call    ASN1DecSetError
0x180002e8e  mov     eax, r12d
0x180002e91  jmp     loc_180002D0A
0x180002e96  mov     edx, 0FFFFFC12h
0x180002e9b  mov     rcx, rdi
0x180002e9e  call    ASN1DecSetError
0x180002ea3  jmp     loc_180002D5E
0x180002ea8  mov     [r14+8], r12
0x180002eac  jmp     loc_180002D96
0x180002eb1  mov     ebx, r12d
0x180002eb4  mov     r15d, r12d
0x180002eb7  mov     edx, 1
0x180002ebc  mov     rcx, rdi
0x180002ebf  call    ASN1BERDecCheck
0x180002ec4  test    eax, eax
0x180002ec6  jz      loc_180002CAC
0x180002ecc  mov     rax, [rdi+28h]
0x180002ed0  movzx   ecx, byte ptr [rax]
0x180002ed3  lea     r8, [rax+1]
0x180002ed7  mov     [rdi+28h], r8
0x180002edb  test    ebx, 0E0000000h
0x180002ee1  jnz     short loc_180002F02
0x180002ee3  mov     eax, ebx
0x180002ee5  mov     edx, ecx
0x180002ee7  and     ecx, 7Fh
0x180002eea  shl     eax, 7
0x180002eed  mov     ebx, ecx
0x180002eef  or      ebx, eax
0x180002ef1  test    dl, dl
0x180002ef3  jns     loc_180002C83
0x180002ef9  inc     r15d
0x180002efc  cmp     r15d, 4
0x180002f00  jb      short loc_180002EB7
0x180002f02  mov     edx, 0FFFFFC0Dh
0x180002f07  mov     rcx, rdi
0x180002f0a  call    ASN1DecSetError
0x180002f0f  jmp     loc_180002CAC
0x180002f14  cmp     r9d, 1
0x180002f18  jnz     loc_180002CF5
0x180002f1e  movzx   esi, byte ptr [r8]
0x180002f22  shl     esi, 18h
0x180002f25  inc     r8
0x180002f28  mov     [rdi+28h], r8
0x180002f2c  jmp     loc_180002E0E
0x180002f31  mov     edx, [rdi+68h]
0x180002f34  cmp     edx, ecx
0x180002f36  jb      loc_180002E96
0x180002f3c  mov     rbp, [rdi+60h]
0x180002f40  mov     eax, ecx
0x180002f42  add     rax, rbp
0x180002f45  sub     edx, ecx
0x180002f47  mov     [rdi+60h], rax
0x180002f4b  mov     [rdi+68h], edx
0x180002f4e  jmp     loc_180002D55
0x180002f53  add     ecx, [r14]
0x180002f56  cmp     ecx, [r14]
0x180002f59  jnb     short loc_180002F75
0x180002f5b  cmp     [rdi+4Ch], r12d
0x180002f5f  jnz     loc_180002CAC
0x180002f65  mov     rcx, [rsp+68h+hMem]; hMem
0x180002f6a  call    cs:__imp_LocalFree
0x180002f70  jmp     loc_180002CAC
0x180002f75  lea     r8d, [rcx+1]
0x180002f79  cmp     r8d, ecx
0x180002f7c  jb      short loc_180002F5B
0x180002f7e  mov     rdx, [r14+8]
0x180002f82  mov     rcx, rbx
0x180002f85  call    DecMemReAlloc
0x180002f8a  mov     [r14+8], rax
0x180002f8e  test    rax, rax
0x180002f91  jz      short loc_180002F5B
0x180002f93  mov     ecx, [r14]
0x180002f96  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180002f9b  add     rcx, rax; void *
0x180002f9e  mov     rdx, [rsp+68h+hMem]; Src
0x180002fa3  call    memcpy_0
0x180002fa8  mov     eax, dword ptr [rsp+68h+Size]
0x180002fac  add     [r14], eax
0x180002faf  mov     ecx, [r14]
0x180002fb2  mov     rax, [r14+8]
0x180002fb6  mov     [rcx+rax], r12b
0x180002fba  cmp     [rdi+4Ch], r12d
0x180002fbe  jnz     short loc_180002FCB
0x180002fc0  mov     rcx, [rsp+68h+hMem]; hMem
0x180002fc5  call    cs:__imp_LocalFree
0x180002fcb  mov     [rsp+68h+hMem], r12
0x180002fd0  jmp     short loc_18000300D
0x180002fd2  lea     rax, [rsp+68h+arg_18]
0x180002fda  mov     [r14], r12d
0x180002fdd  lea     r9, [rsp+68h+arg_0]
0x180002fe2  mov     [rsp+68h+var_48], rax
0x180002fe7  mov     r8d, ebx
0x180002fea  mov     [r14+8], r12
0x180002fee  mov     edx, esi
0x180002ff0  mov     rcx, rdi
0x180002ff3  call    _BERDecConstructed
0x180002ff8  test    eax, eax
0x180002ffa  jz      loc_180002CAC
0x180003000  mov     rbx, [rsp+68h+arg_0]
0x180003005  mov     rsi, [rsp+68h+arg_18]
0x18000300d  mov     rdx, rsi
0x180003010  mov     rcx, rbx
0x180003013  call    ASN1BERDecNotEndOfContents
0x180003018  test    eax, eax
0x18000301a  jz      short loc_180003043
0x18000301c  lea     r8, [rsp+68h+Size]
0x180003021  mov     edx, 4
0x180003026  mov     rcx, rbx
0x180003029  call    ASN1BERDecCharString
0x18000302e  test    eax, eax
0x180003030  jz      loc_180002CAC
0x180003036  mov     ecx, dword ptr [rsp+68h+Size]
0x18000303a  test    ecx, ecx
0x18000303c  jz      short loc_18000300D
0x18000303e  jmp     loc_180002F53
0x180003043  mov     r8, rsi
0x180003046  mov     rdx, rbx
0x180003049  mov     rcx, rdi
0x18000304c  call    ASN1BERDecEndOfContents
0x180003051  jmp     loc_180002CAE
0x180003056  mov     edx, 0FFFFFC15h
0x18000305b  jmp     loc_180002E74
```
