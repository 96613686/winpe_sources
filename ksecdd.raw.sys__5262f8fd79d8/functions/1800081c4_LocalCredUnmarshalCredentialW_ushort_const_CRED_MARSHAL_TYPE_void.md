# LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)

- ea: `0x1800081c4`
- end: `0x180008432`
- name: `?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z`
- size: `622`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, enum _CRED_MARSHAL_TYPE *, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007fc4`
- `0x180008a40`
- `0x1800092d0`
- `0x18000a070`

## callees

- `0x180004050`
- `0x1800081c4`
- `0x180020480`
- `0x1800205d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800082ba`
- `ntoskrnl!ExAllocatePool2` at `0x180008354`
- `ntoskrnl!ExAllocatePool2` at `0x1800083c7`
- `ntoskrnl!ExAllocatePool2` at `0x1800082ba`
- `ntoskrnl!ExAllocatePool2` at `0x180008354`
- `ntoskrnl!ExAllocatePool2` at `0x1800083c7`

## pseudocode

```c
__int64 __fastcall LocalCredUnmarshalCredentialW(const unsigned __int16 *a1, enum _CRED_MARSHAL_TYPE *a2, char **a3)
{
  unsigned __int64 v4; // r10
  const unsigned __int16 *v5; // r14
  _DWORD *v6; // r8
  int v7; // r10d
  unsigned int v8; // ebx
  int i; // edx
  char *Pool2; // rsi
  __int64 v12; // r9
  __int64 v13; // rbx
  char *v14; // r15
  char *v15; // rax
  _QWORD v16[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v18; // [rsp+78h] [rbp+48h] BYREF

  v18 = 0;
  v17 = 0;
  if ( !a1 )
    goto LABEL_12;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 <= 2 )
    goto LABEL_12;
  if ( *a1 != 64 )
    goto LABEL_12;
  if ( a1[1] != 64 )
    goto LABEL_12;
  v5 = &a1[v4];
  v16[0] = a1 + 2;
  if ( !(unsigned int)CredpUnmarshalChar(v16, v5, a2) )
    goto LABEL_12;
  if ( *v6 != 1 )
  {
    if ( *v6 != 2 )
    {
      if ( *v6 == 3 )
      {
        for ( i = 0; i < 5; ++i )
        {
          if ( asc_180015B48[i] != *(_WORD *)(v16[0] + 2LL * i) )
            goto LABEL_12;
        }
        v16[0] += 10LL;
        Pool2 = (char *)ExAllocatePool2(256, (unsigned int)(2 * v7 + 18) + 2LL, 1230267731);
        if ( Pool2 )
        {
          if ( !(unsigned int)CredpUnmarshalBytes(v16, v5, &v17, 4) )
            goto LABEL_22;
          v12 = v17;
          v13 = v17;
          if ( v17 != ((v17 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) || !v17 )
            goto LABEL_22;
          v14 = Pool2 + 16;
          *(_DWORD *)Pool2 = v17;
          *((_QWORD *)Pool2 + 1) = Pool2 + 16;
LABEL_26:
          if ( (unsigned int)CredpUnmarshalBytes(v16, v5, v14, v12) )
          {
            *(_WORD *)&v14[v13] = 0;
            goto LABEL_35;
          }
LABEL_22:
          v8 = 87;
          *a3 = 0;
LABEL_37:
          SspiLocalFree(Pool2);
          return v8;
        }
LABEL_20:
        v8 = 8;
        goto LABEL_13;
      }
      if ( *v6 != 4 )
      {
LABEL_12:
        v8 = 87;
LABEL_13:
        *a3 = 0;
        return v8;
      }
    }
    Pool2 = (char *)ExAllocatePool2(256, (unsigned int)(2 * v7 + 10) + 2LL, 1230267731);
    if ( Pool2 )
    {
      if ( !(unsigned int)CredpUnmarshalBytes(v16, v5, &v18, 4) )
        goto LABEL_22;
      v12 = v18;
      v13 = v18;
      if ( v18 != ((v18 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) || !v18 )
        goto LABEL_22;
      v14 = Pool2 + 8;
      *(_QWORD *)Pool2 = Pool2 + 8;
      goto LABEL_26;
    }
    goto LABEL_20;
  }
  v15 = (char *)ExAllocatePool2(256, 26, 1230267731);
  Pool2 = v15;
  if ( !v15 )
    goto LABEL_20;
  *(_DWORD *)v15 = 24;
  if ( !(unsigned int)CredpUnmarshalBytes(v16, v5, v15 + 4, 20) )
    goto LABEL_22;
LABEL_35:
  if ( (const unsigned __int16 *)v16[0] == v5 )
  {
    v8 = 0;
    *a3 = Pool2;
    return v8;
  }
  *a3 = 0;
  v8 = 87;
  if ( Pool2 )
    goto LABEL_37;
  return v8;
}

```

## disassembly

```asm
0x1800081c4  mov     [rsp-28h+arg_8], rbx
0x1800081c9  mov     [rsp-28h+arg_10], rsi
0x1800081ce  push    rbp
0x1800081cf  push    rdi
0x1800081d0  push    r12
0x1800081d2  push    r14
0x1800081d4  push    r15
0x1800081d6  mov     rbp, rsp
0x1800081d9  sub     rsp, 30h
0x1800081dd  xor     r12d, r12d
0x1800081e0  mov     rdi, r8
0x1800081e3  mov     [rbp+arg_18], r12d
0x1800081e7  mov     r8, rdx
0x1800081ea  mov     [rbp+arg_0], r12d
0x1800081ee  test    rcx, rcx
0x1800081f1  jz      short loc_180008253
0x1800081f3  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800081f7  inc     r10
0x1800081fa  cmp     [rcx+r10*2], r12w
0x1800081ff  jnz     short loc_1800081F7
0x180008201  cmp     r10, 2
0x180008205  jbe     short loc_180008253
0x180008207  cmp     word ptr [rcx], 40h ; '@'
0x18000820b  jnz     short loc_180008253
0x18000820d  cmp     word ptr [rcx+2], 40h ; '@'
0x180008212  jnz     short loc_180008253
0x180008214  lea     r14, [rcx+r10*2]
0x180008218  lea     rax, [rcx+4]
0x18000821c  mov     rdx, r14
0x18000821f  lea     rcx, [rbp+var_10]
0x180008223  mov     [rbp+var_10], rax
0x180008227  call    CredpUnmarshalChar
0x18000822c  test    eax, eax
0x18000822e  jz      short loc_180008253
0x180008230  mov     ecx, [r8]
0x180008233  sub     ecx, 1
0x180008236  jz      loc_1800083B7
0x18000823c  sub     ecx, 1
0x18000823f  jz      loc_18000833D
0x180008245  sub     ecx, 1
0x180008248  jz      short loc_180008275
0x18000824a  cmp     ecx, 1
0x18000824d  jz      loc_18000833D
0x180008253  mov     ebx, 57h ; 'W'
0x180008258  mov     [rdi], r12
0x18000825b  mov     rsi, [rsp+30h+arg_10]
0x180008260  mov     eax, ebx
0x180008262  mov     rbx, [rsp+30h+arg_8]
0x180008267  add     rsp, 30h
0x18000826b  pop     r15
0x18000826d  pop     r14
0x18000826f  pop     r12
0x180008271  pop     rdi
0x180008272  pop     rbp
0x180008273  retn
0x180008275  mov     r8, [rbp+var_10]
0x180008279  mov     edx, r12d
0x18000827c  cmp     edx, 5
0x18000827f  jge     short loc_18000829B
0x180008281  movsxd  rcx, edx
0x180008284  lea     r9, asc_180015B48; "\a\b"
0x18000828b  movzx   eax, word ptr [r8+rcx*2]
0x180008290  cmp     [r9+rcx*2], ax
0x180008295  jnz     short loc_180008253
0x180008297  inc     edx
0x180008299  jmp     short loc_18000827C
0x18000829b  add     r8, 0Ah
0x18000829f  lea     edx, ds:12h[r10*2]
0x1800082a7  mov     [rbp+var_10], r8
0x1800082ab  add     rdx, 2
0x1800082af  mov     r8d, 49546553h
0x1800082b5  mov     ecx, 100h
0x1800082ba  call    cs:__imp_ExAllocatePool2
0x1800082c1  nop     dword ptr [rax+rax+00h]
0x1800082c6  mov     rsi, rax
0x1800082c9  test    rax, rax
0x1800082cc  jnz     short loc_1800082D5
0x1800082ce  mov     ebx, 8
0x1800082d3  jmp     short loc_180008258
0x1800082d5  mov     r9d, 4
0x1800082db  lea     r8, [rbp+arg_0]
0x1800082df  mov     rdx, r14
0x1800082e2  lea     rcx, [rbp+var_10]
0x1800082e6  call    CredpUnmarshalBytes
0x1800082eb  test    eax, eax
0x1800082ed  jnz     short loc_1800082FC
0x1800082ef  mov     ebx, 57h ; 'W'
0x1800082f4  mov     [rdi], r12
0x1800082f7  jmp     loc_18000841A
0x1800082fc  mov     r9d, [rbp+arg_0]
0x180008300  mov     ebx, r9d
0x180008303  lea     rax, [r9+1]
0x180008307  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000830b  cmp     r9, rax
0x18000830e  jnz     short loc_1800082EF
0x180008310  test    r9d, r9d
0x180008313  jz      short loc_1800082EF
0x180008315  lea     r15, [rsi+10h]
0x180008319  mov     [rsi], r9d
0x18000831c  mov     [rsi+8], r15
0x180008320  mov     r8, r15
0x180008323  lea     rcx, [rbp+var_10]
0x180008327  mov     rdx, r14
0x18000832a  call    CredpUnmarshalBytes
0x18000832f  test    eax, eax
0x180008331  jz      short loc_1800082EF
0x180008333  mov     [r15+rbx], r12w
0x180008338  jmp     loc_180008403
0x18000833d  lea     edx, ds:0Ah[r10*2]
0x180008345  mov     ecx, 100h
0x18000834a  add     rdx, 2
0x18000834e  mov     r8d, 49546553h
0x180008354  call    cs:__imp_ExAllocatePool2
0x18000835b  nop     dword ptr [rax+rax+00h]
0x180008360  mov     rsi, rax
0x180008363  test    rax, rax
0x180008366  jz      loc_1800082CE
0x18000836c  mov     r9d, 4
0x180008372  lea     r8, [rbp+arg_18]
0x180008376  mov     rdx, r14
0x180008379  lea     rcx, [rbp+var_10]
0x18000837d  call    CredpUnmarshalBytes
0x180008382  test    eax, eax
0x180008384  jz      loc_1800082EF
0x18000838a  mov     r9d, [rbp+arg_18]
0x18000838e  mov     ebx, r9d
0x180008391  lea     rax, [r9+1]
0x180008395  and     rax, 0FFFFFFFFFFFFFFFEh
0x180008399  cmp     r9, rax
0x18000839c  jnz     loc_1800082EF
0x1800083a2  test    r9d, r9d
0x1800083a5  jz      loc_1800082EF
0x1800083ab  lea     r15, [rsi+8]
0x1800083af  mov     [rsi], r15
0x1800083b2  jmp     loc_180008320
0x1800083b7  mov     edx, 1Ah
0x1800083bc  mov     ecx, 100h
0x1800083c1  mov     r8d, 49546553h
0x1800083c7  call    cs:__imp_ExAllocatePool2
0x1800083ce  nop     dword ptr [rax+rax+00h]
0x1800083d3  mov     rsi, rax
0x1800083d6  test    rax, rax
0x1800083d9  jz      loc_1800082CE
0x1800083df  lea     r8, [rax+4]
0x1800083e3  mov     dword ptr [rax], 18h
0x1800083e9  mov     r9d, 14h
0x1800083ef  lea     rcx, [rbp+var_10]
0x1800083f3  mov     rdx, r14
0x1800083f6  call    CredpUnmarshalBytes
0x1800083fb  test    eax, eax
0x1800083fd  jz      loc_1800082EF
0x180008403  cmp     [rbp+var_10], r14
0x180008407  jz      short loc_180008427
0x180008409  mov     [rdi], r12
0x18000840c  mov     ebx, 57h ; 'W'
0x180008411  test    rsi, rsi
0x180008414  jz      loc_18000825B
0x18000841a  mov     rcx, rsi; DataBuffer
0x18000841d  call    SspiLocalFree
0x180008422  jmp     loc_18000825B
0x180008427  mov     ebx, r12d
0x18000842a  mov     [rdi], rsi
0x18000842d  jmp     loc_18000825B
```
