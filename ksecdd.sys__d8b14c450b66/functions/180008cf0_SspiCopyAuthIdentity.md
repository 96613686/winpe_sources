# SspiCopyAuthIdentity

- ea: `0x180008cf0`
- end: `0x1800092bd`
- name: `SspiCopyAuthIdentity`
- size: `1485`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *AuthDataCopy)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a6d0`

## callees

- `0x180006700`
- `0x180006830`
- `0x180008cf0`
- `0x18000aa60`
- `0x180010980`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180008d58`
- `ntoskrnl!ExAllocatePool2` at `0x180008deb`
- `ntoskrnl!ExAllocatePool2` at `0x180008fd9`
- `ntoskrnl!ExAllocatePool2` at `0x18000904e`
- `ntoskrnl!ExAllocatePool2` at `0x1800090aa`
- `ntoskrnl!ExAllocatePool2` at `0x18000912c`
- `ntoskrnl!ExAllocatePool2` at `0x1800091e8`
- `ntoskrnl!ExAllocatePool2` at `0x180009261`
- `ntoskrnl!ExAllocatePool2` at `0x180008d58`
- `ntoskrnl!ExAllocatePool2` at `0x180008deb`
- `ntoskrnl!ExAllocatePool2` at `0x180008fd9`
- `ntoskrnl!ExAllocatePool2` at `0x18000904e`
- `ntoskrnl!ExAllocatePool2` at `0x1800090aa`
- `ntoskrnl!ExAllocatePool2` at `0x18000912c`
- `ntoskrnl!ExAllocatePool2` at `0x1800091e8`
- `ntoskrnl!ExAllocatePool2` at `0x180009261`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiCopyAuthIdentity(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *AuthDataCopy)
{
  _QWORD *v3; // rbp
  void *v4; // r15
  _DWORD *v5; // rsi
  _DWORD *v6; // rdi
  SECURITY_STATUS v7; // ebx
  int v8; // eax
  _DWORD *Pool2; // rax
  unsigned int v10; // ecx
  size_t v11; // r8
  unsigned int v12; // ecx
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // rbp
  __int64 v16; // rax
  unsigned __int64 v17; // r15
  _WORD *v18; // rbx
  int v19; // r10d
  _WORD *v20; // rbp
  char *v21; // rcx
  size_t v22; // r8
  unsigned int v23; // r12d
  __int64 v24; // rdx
  _QWORD *v25; // rax
  char *v26; // r12
  void *v27; // rax
  _OWORD *v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // eax
  void *v31; // rax
  unsigned int v33; // ecx
  unsigned int v34; // eax
  void *v35; // rax
  unsigned int v36; // ecx
  unsigned int v37; // eax
  void *v38; // rax
  unsigned int v39; // ecx
  unsigned __int16 v40; // [rsp+70h] [rbp+8h]

  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = AuthData;
  v7 = SspiValidateAuthIdentity(AuthData);
  if ( v7 < 0 )
  {
LABEL_50:
    *AuthDataCopy = 0;
    if ( v4 )
      SspiFreeAuthIdentity(v4);
    if ( !v3 )
      goto LABEL_54;
    goto LABEL_53;
  }
  if ( *v6 == 513 )
  {
    v8 = v6[9];
    if ( (v8 & 0x10070) != 0 )
    {
      if ( (v8 & 0x10000) != 0 )
      {
        Pool2 = (_DWORD *)ExAllocatePool2(256, (unsigned int)(v6[2] + 8) + 2LL, 1230267731);
        v5 = Pool2;
        if ( Pool2 )
        {
          v10 = v6[2];
          v11 = v10 + 8;
          if ( !_bittest(v6 + 9, 0x10u) )
            v11 = v10;
          memmove(Pool2, v6, v11);
          goto LABEL_9;
        }
        goto LABEL_44;
      }
LABEL_35:
      v7 = -1073741811;
LABEL_45:
      *AuthDataCopy = 0;
      goto LABEL_54;
    }
    v12 = *((unsigned __int16 *)v6 + 8) + 64;
    v13 = v12 + *((unsigned __int16 *)v6 + 12);
    if ( v13 < v12 )
      goto LABEL_35;
    v14 = v13 + *((unsigned __int16 *)v6 + 22);
    if ( v14 < v13 )
      goto LABEL_35;
    v15 = v14 + *((unsigned __int16 *)v6 + 16);
    if ( (unsigned int)v15 < v14 || (unsigned int)v15 > 0xFFFF )
      goto LABEL_35;
    v16 = ExAllocatePool2(256, v15 + 2, 1230267731);
    v5 = (_DWORD *)v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = 513;
      v17 = v16 + v15;
      *(_WORD *)(v16 + 4) = 48;
      v18 = (_WORD *)(v16 + 48);
      *(_DWORD *)(v16 + 8) = v15 - 8;
      if ( v6[3] )
      {
        *(_DWORD *)(v16 + 12) = 48;
        *(_WORD *)(v16 + 16) = *((_WORD *)v6 + 8);
        memmove(v18, (char *)v6 + (unsigned int)v6[3], *((unsigned __int16 *)v6 + 8));
        v18 = (_WORD *)((char *)v18 + *((unsigned __int16 *)v5 + 8));
      }
      if ( v6[5] )
      {
        v5[5] = (_DWORD)v18 - (_DWORD)v5;
        *((_WORD *)v5 + 12) = *((_WORD *)v6 + 12);
        memmove(v18, (char *)v6 + (unsigned int)v6[5], *((unsigned __int16 *)v6 + 12));
        v18 = (_WORD *)((char *)v18 + *((unsigned __int16 *)v5 + 12));
      }
      if ( v6[7] )
      {
        v19 = (int)v18;
        v5[7] = (_DWORD)v18 - (_DWORD)v5;
        v20 = v18;
        if ( v17 - (unsigned __int64)v18 < 0x1C )
          goto LABEL_35;
        v21 = (char *)v6 + (unsigned int)v6[7];
        if ( *((_WORD *)v6 + 16) < *((_WORD *)v21 + 1) )
          goto LABEL_35;
        *v18 = 28;
        *(_OWORD *)(v18 + 2) = *(_OWORD *)(v21 + 4);
        v22 = *((unsigned __int16 *)v21 + 12);
        v18 += 14;
        v23 = (v22 + 7) & 0xFFFFFFF8;
        if ( (int)v17 - (int)v18 < v23
          || (v24 = *((unsigned int *)v21 + 5), (int)v24 + (int)v22 < (unsigned int)v24)
          || (int)v24 + (int)v22 > (unsigned int)*((unsigned __int16 *)v21 + 1) )
        {
          v7 = -1073741811;
          *AuthDataCopy = 0;
          goto LABEL_54;
        }
        if ( (_DWORD)v24 )
        {
          v20[12] = v22;
          *((_DWORD *)v20 + 5) = (_DWORD)v18 - v19;
          memmove(v18, &v21[v24], v22);
          v18 = (_WORD *)((char *)v18 + v23);
        }
        v20[1] = (_WORD)v18 - (_WORD)v20;
        *((_WORD *)v5 + 16) = (_WORD)v18 - (_WORD)v20;
      }
      if ( v6[10] )
      {
        if ( (int)v17 - (int)v18 < (unsigned int)*((unsigned __int16 *)v6 + 22) )
          goto LABEL_35;
        v5[10] = (_DWORD)v18 - (_DWORD)v5;
        *((_WORD *)v5 + 22) = *((_WORD *)v6 + 22);
        memmove(v18, (char *)v6 + (unsigned int)v6[10], *((unsigned __int16 *)v6 + 22));
        v18 = (_WORD *)((char *)v18 + *((unsigned __int16 *)v5 + 22));
      }
      if ( (unsigned __int64)(v18 + 4) <= v17 )
      {
        v5[9] = v6[9] | 0x10000;
LABEL_9:
        *AuthDataCopy = v5;
LABEL_10:
        v7 = 0;
        return SspNtStatusToSecStatus((unsigned int)v7);
      }
      goto LABEL_35;
    }
LABEL_44:
    v7 = -1073741801;
    goto LABEL_45;
  }
  if ( *v6 != 512 )
  {
    v40 = 2 - ((v6[11] & 1) != 0);
    v28 = (_OWORD *)ExAllocatePool2(256, 50, 1230267731);
    v4 = v28;
    if ( !v28 )
      goto LABEL_44;
    *v28 = *(_OWORD *)v6;
    v28[1] = *((_OWORD *)v6 + 1);
    v28[2] = *((_OWORD *)v6 + 2);
    *((_QWORD *)v28 + 2) = 0;
    *(_QWORD *)v28 = 0;
    *((_QWORD *)v28 + 4) = 0;
    v26 = (char *)v28;
    *AuthDataCopy = v28;
LABEL_47:
    v29 = v40;
    if ( *(_QWORD *)v6 )
    {
      v30 = ((v6[2] * v40 + 7) & 0xFFFFFFF8) / v40;
      *((_DWORD *)v26 + 2) = v30;
      v31 = (void *)ExAllocatePool2(256, v40 * (v30 + 1) + 2LL, 1230267731);
      *(_QWORD *)v26 = v31;
      if ( !v31 )
      {
LABEL_49:
        v7 = -1073741801;
        goto LABEL_50;
      }
      v33 = v6[2] * v40;
      if ( (v6[11] & 0x10000) != 0 )
        v33 = (v33 + 7) & 0xFFFFFFF8;
      memmove(v31, *(const void **)v6, v33);
      v29 = v40;
      *((_DWORD *)v26 + 2) = v6[2];
    }
    if ( *((_QWORD *)v6 + 2) )
    {
      v34 = ((v6[6] * v29 + 7) & 0xFFFFFFF8) / v29;
      *((_DWORD *)v26 + 6) = v34;
      v35 = (void *)ExAllocatePool2(256, v29 * (v34 + 1) + 2LL, 1230267731);
      *((_QWORD *)v26 + 2) = v35;
      if ( !v35 )
        goto LABEL_49;
      v36 = v6[6] * v40;
      if ( (v6[11] & 0x10000) != 0 )
        v36 = (v36 + 7) & 0xFFFFFFF8;
      memmove(v35, *((const void **)v6 + 2), v36);
      *((_DWORD *)v26 + 6) = v6[6];
    }
    if ( *((_QWORD *)v6 + 4) )
    {
      v37 = ((v40 * (v6[10] + 1) + 7) & 0xFFFFFFF8) / v40;
      *((_DWORD *)v26 + 10) = v37;
      v38 = (void *)ExAllocatePool2(256, v40 * (v37 + 1) + 2LL, 1230267731);
      *((_QWORD *)v26 + 4) = v38;
      if ( !v38 )
        goto LABEL_49;
      v39 = v6[10] * v40;
      if ( (v6[11] & 0x10000) != 0 )
        v39 = (v39 + 7) & 0xFFFFFFF8;
      memmove(v38, *((const void **)v6 + 4), v39);
      *((_DWORD *)v26 + 10) = v6[10];
    }
    *((_DWORD *)v26 + 11) = *((_DWORD *)v26 + 11) & 0xFFFEFFFB | 0x10000;
    goto LABEL_10;
  }
  v40 = 2 - ((v6[13] & 1) != 0);
  v25 = (_QWORD *)ExAllocatePool2(256, 74, 1230267731);
  v3 = v25;
  if ( !v25 )
    goto LABEL_44;
  *(_OWORD *)v25 = *(_OWORD *)v6;
  *((_OWORD *)v25 + 1) = *((_OWORD *)v6 + 1);
  *((_OWORD *)v25 + 2) = *((_OWORD *)v6 + 2);
  *((_OWORD *)v25 + 3) = *((_OWORD *)v6 + 3);
  v25[8] = *((_QWORD *)v6 + 8);
  v25[3] = 0;
  v26 = (char *)(v25 + 1);
  v25[1] = 0;
  v25[5] = 0;
  v25[7] = 0;
  *AuthDataCopy = v25;
  if ( !*((_QWORD *)v6 + 7) )
  {
LABEL_42:
    v6 += 2;
    goto LABEL_47;
  }
  v27 = (void *)ExAllocatePool2(256, (unsigned int)v40 * (v6[16] + 1) + 2LL, 1230267731);
  v3[7] = v27;
  if ( v27 )
  {
    memmove(v27, *((const void **)v6 + 7), v6[16] * (unsigned int)v40);
    goto LABEL_42;
  }
  v7 = -1073741801;
  *AuthDataCopy = 0;
LABEL_53:
  SspiFreeAuthIdentity(v3);
LABEL_54:
  if ( v5 )
    SspiFreeAuthIdentity(v5);
  return SspNtStatusToSecStatus((unsigned int)v7);
}

```

## disassembly

```asm
0x180008cf0  push    rbx
0x180008cf2  push    rbp
0x180008cf3  push    rsi
0x180008cf4  push    rdi
0x180008cf5  push    r12
0x180008cf7  push    r13
0x180008cf9  push    r14
0x180008cfb  push    r15
0x180008cfd  sub     rsp, 28h
0x180008d01  xor     r12d, r12d
0x180008d04  mov     r14, rdx
0x180008d07  mov     ebp, r12d
0x180008d0a  mov     r15d, r12d
0x180008d0d  mov     esi, r12d
0x180008d10  mov     rdi, rcx
0x180008d13  call    SspiValidateAuthIdentity
0x180008d18  mov     ebx, eax
0x180008d1a  test    eax, eax
0x180008d1c  js      loc_180009149
0x180008d22  mov     eax, [rdi]
0x180008d24  cmp     eax, 201h
0x180008d29  jnz     loc_180008FA6
0x180008d2f  mov     eax, [rdi+24h]
0x180008d32  test    eax, 10070h
0x180008d37  jz      short loc_180008D96
0x180008d39  bt      eax, 10h
0x180008d3d  jnb     loc_180008F9C
0x180008d43  mov     edx, [rdi+8]
0x180008d46  mov     ecx, 100h
0x180008d4b  add     edx, 8
0x180008d4e  mov     r8d, 49546553h
0x180008d54  add     rdx, 2
0x180008d58  call    cs:__imp_ExAllocatePool2
0x180008d5f  nop     dword ptr [rax+rax+00h]
0x180008d64  mov     rsi, rax
0x180008d67  test    rax, rax
0x180008d6a  jz      loc_1800090BE
0x180008d70  mov     ecx, [rdi+8]
0x180008d73  bt      dword ptr [rdi+24h], 10h
0x180008d78  mov     rdx, rdi; Src
0x180008d7b  lea     r8d, [rcx+8]
0x180008d7f  cmovnb  r8d, ecx; Size
0x180008d83  mov     rcx, rax; void *
0x180008d86  call    memmove
0x180008d8b  mov     [r14], rsi
0x180008d8e  mov     ebx, r12d
0x180008d91  jmp     loc_180009173
0x180008d96  movzx   ecx, word ptr [rdi+10h]
0x180008d9a  add     ecx, 40h ; '@'
0x180008d9d  cmp     ecx, 40h ; '@'
0x180008da0  jb      loc_180008F9C
0x180008da6  movzx   edx, word ptr [rdi+18h]
0x180008daa  add     edx, ecx
0x180008dac  cmp     edx, ecx
0x180008dae  jb      loc_180008F9C
0x180008db4  movzx   ecx, word ptr [rdi+2Ch]
0x180008db8  add     ecx, edx
0x180008dba  cmp     ecx, edx
0x180008dbc  jb      loc_180008F9C
0x180008dc2  movzx   ebp, word ptr [rdi+20h]
0x180008dc6  add     ebp, ecx
0x180008dc8  cmp     ebp, ecx
0x180008dca  jb      loc_180008F9C
0x180008dd0  cmp     ebp, 0FFFFh
0x180008dd6  ja      loc_180008F9C
0x180008ddc  lea     rdx, [rbp+2]
0x180008de0  mov     ecx, 100h
0x180008de5  mov     r8d, 49546553h
0x180008deb  call    cs:__imp_ExAllocatePool2
0x180008df2  nop     dword ptr [rax+rax+00h]
0x180008df7  mov     rsi, rax
0x180008dfa  test    rax, rax
0x180008dfd  jz      loc_1800090BE
0x180008e03  mov     dword ptr [rax], 201h
0x180008e09  lea     r15, [rax+rbp]
0x180008e0d  mov     word ptr [rax+4], 30h ; '0'
0x180008e13  lea     rbx, [rax+30h]
0x180008e17  lea     eax, [rbp-8]
0x180008e1a  mov     [rsi+8], eax
0x180008e1d  cmp     [rdi+0Ch], r12d
0x180008e21  jz      short loc_180008E4C
0x180008e23  mov     eax, ebx
0x180008e25  mov     rcx, rbx; void *
0x180008e28  sub     eax, esi
0x180008e2a  mov     [rsi+0Ch], eax
0x180008e2d  movzx   eax, word ptr [rdi+10h]
0x180008e31  mov     [rsi+10h], ax
0x180008e35  mov     edx, [rdi+0Ch]
0x180008e38  movzx   r8d, word ptr [rdi+10h]; Size
0x180008e3d  add     rdx, rdi; Src
0x180008e40  call    memmove
0x180008e45  movzx   eax, word ptr [rsi+10h]
0x180008e49  add     rbx, rax
0x180008e4c  mov     ebp, esi
0x180008e4e  cmp     [rdi+14h], r12d
0x180008e52  jz      short loc_180008E7D
0x180008e54  mov     eax, ebx
0x180008e56  mov     rcx, rbx; void *
0x180008e59  sub     eax, esi
0x180008e5b  mov     [rsi+14h], eax
0x180008e5e  movzx   eax, word ptr [rdi+18h]
0x180008e62  mov     [rsi+18h], ax
0x180008e66  mov     edx, [rdi+14h]
0x180008e69  movzx   r8d, word ptr [rdi+18h]; Size
0x180008e6e  add     rdx, rdi; Src
0x180008e71  call    memmove
0x180008e76  movzx   eax, word ptr [rsi+18h]
0x180008e7a  add     rbx, rax
0x180008e7d  cmp     [rdi+1Ch], r12d
0x180008e81  jz      loc_180008F37
0x180008e87  mov     eax, ebx
0x180008e89  mov     edx, 1Ch
0x180008e8e  sub     eax, ebp
0x180008e90  mov     r10d, ebx
0x180008e93  mov     [rsi+1Ch], eax
0x180008e96  mov     rbp, rbx
0x180008e99  mov     rax, r15
0x180008e9c  sub     rax, rbx
0x180008e9f  cmp     rax, rdx
0x180008ea2  jb      loc_180008F9C
0x180008ea8  mov     ecx, [rdi+1Ch]
0x180008eab  add     rcx, rdi
0x180008eae  movzx   eax, word ptr [rcx+2]
0x180008eb2  cmp     [rdi+20h], ax
0x180008eb6  jb      loc_180008F9C
0x180008ebc  mov     [rbx], dx
0x180008ebf  mov     eax, r15d
0x180008ec2  movups  xmm0, xmmword ptr [rcx+4]
0x180008ec6  movdqu  xmmword ptr [rbx+4], xmm0
0x180008ecb  movzx   r8d, word ptr [rcx+18h]; Size
0x180008ed0  add     rbx, rdx
0x180008ed3  sub     eax, ebx
0x180008ed5  mov     r13, rbx
0x180008ed8  lea     r12d, [r8+7]
0x180008edc  and     r12d, 0FFFFFFF8h
0x180008ee0  cmp     eax, r12d
0x180008ee3  jb      loc_180008F8B
0x180008ee9  mov     edx, [rcx+14h]
0x180008eec  lea     r9d, [rdx+r8]
0x180008ef0  cmp     r9d, edx
0x180008ef3  jb      loc_180008F8B
0x180008ef9  movzx   eax, word ptr [rcx+2]
0x180008efd  cmp     r9d, eax
0x180008f00  ja      loc_180008F8B
0x180008f06  test    edx, edx
0x180008f08  jz      short loc_180008F26
0x180008f0a  sub     ebx, r10d
0x180008f0d  mov     [rbp+18h], r8w
0x180008f12  add     rdx, rcx; Src
0x180008f15  mov     [rbp+14h], ebx
0x180008f18  mov     rcx, r13; void *
0x180008f1b  call    memmove
0x180008f20  mov     ebx, r12d
0x180008f23  add     rbx, r13
0x180008f26  movzx   eax, bx
0x180008f29  sub     ax, bp
0x180008f2c  mov     [rbp+2], ax
0x180008f30  xor     r12d, r12d
0x180008f33  mov     [rsi+20h], ax
0x180008f37  cmp     [rdi+28h], r12d
0x180008f3b  jz      short loc_180008F73
0x180008f3d  movzx   eax, word ptr [rdi+2Ch]
0x180008f41  mov     ecx, r15d
0x180008f44  sub     ecx, ebx
0x180008f46  cmp     ecx, eax
0x180008f48  jb      short loc_180008F9C
0x180008f4a  mov     eax, ebx
0x180008f4c  mov     rcx, rbx; void *
0x180008f4f  sub     eax, esi
0x180008f51  mov     [rsi+28h], eax
0x180008f54  movzx   eax, word ptr [rdi+2Ch]
0x180008f58  mov     [rsi+2Ch], ax
0x180008f5c  mov     edx, [rdi+28h]
0x180008f5f  movzx   r8d, word ptr [rdi+2Ch]; Size
0x180008f64  add     rdx, rdi; Src
0x180008f67  call    memmove
0x180008f6c  movzx   eax, word ptr [rsi+2Ch]
0x180008f70  add     rbx, rax
0x180008f73  lea     rax, [rbx+8]
0x180008f77  cmp     rax, r15
0x180008f7a  ja      short loc_180008F9C
0x180008f7c  mov     eax, [rdi+24h]
0x180008f7f  bts     eax, 10h
0x180008f83  mov     [rsi+24h], eax
0x180008f86  jmp     loc_180008D8B
0x180008f8b  mov     ebx, 0C000000Dh
0x180008f90  mov     qword ptr [r14], 0
0x180008f97  jmp     loc_180009166
0x180008f9c  mov     ebx, 0C000000Dh
0x180008fa1  jmp     loc_1800090C3
0x180008fa6  mov     r13d, 49546553h
0x180008fac  mov     r8d, r13d
0x180008faf  cmp     eax, 200h
0x180008fb4  jnz     loc_18000908D
0x180008fba  mov     eax, [rdi+34h]
0x180008fbd  mov     ebx, 100h
0x180008fc2  and     al, 1
0x180008fc4  mov     edx, 4Ah ; 'J'
0x180008fc9  neg     al
0x180008fcb  mov     ecx, ebx
0x180008fcd  sbb     ax, ax
0x180008fd0  add     ax, 2
0x180008fd4  mov     [rsp+68h+arg_0], ax
0x180008fd9  call    cs:__imp_ExAllocatePool2
0x180008fe0  nop     dword ptr [rax+rax+00h]
0x180008fe5  mov     rbp, rax
0x180008fe8  test    rax, rax
0x180008feb  jz      loc_1800090BE
0x180008ff1  movups  xmm0, xmmword ptr [rdi]
0x180008ff4  movups  xmmword ptr [rax], xmm0
0x180008ff7  movups  xmm1, xmmword ptr [rdi+10h]
0x180008ffb  movups  xmmword ptr [rax+10h], xmm1
0x180008fff  movups  xmm0, xmmword ptr [rdi+20h]
0x180009003  movups  xmmword ptr [rax+20h], xmm0
0x180009007  movups  xmm1, xmmword ptr [rdi+30h]
0x18000900b  movups  xmmword ptr [rax+30h], xmm1
0x18000900f  movsd   xmm0, qword ptr [rdi+40h]
0x180009014  movsd   qword ptr [rax+40h], xmm0
0x180009019  mov     [rax+18h], r12
0x18000901d  lea     r12, [rax+8]
0x180009021  xor     eax, eax
0x180009023  mov     [r12], rax
0x180009027  mov     [rbp+28h], rax
0x18000902b  mov     [rbp+38h], rax
0x18000902f  mov     [r14], rbp
0x180009032  cmp     [rdi+38h], rax
0x180009036  jz      short loc_180009087
0x180009038  mov     edx, [rdi+40h]
0x18000903b  mov     r8d, r13d
0x18000903e  movzx   ecx, [rsp+68h+arg_0]
0x180009043  inc     edx
0x180009045  imul    edx, ecx
0x180009048  mov     ecx, ebx
0x18000904a  add     rdx, 2
0x18000904e  call    cs:__imp_ExAllocatePool2
0x180009055  nop     dword ptr [rax+rax+00h]
0x18000905a  mov     [rbp+38h], rax
0x18000905e  mov     rcx, rax; void *
0x180009061  test    rax, rax
0x180009064  jnz     short loc_180009073
0x180009066  mov     ebx, 0C0000017h
0x18000906b  mov     [r14], rsi
0x18000906e  jmp     loc_18000915E
0x180009073  movzx   r8d, [rsp+68h+arg_0]
0x180009079  imul    r8d, [rdi+40h]; Size
0x18000907e  mov     rdx, [rdi+38h]; Src
0x180009082  call    memmove
0x180009087  add     rdi, 8
0x18000908b  jmp     short loc_1800090F2
0x18000908d  mov     eax, [rdi+2Ch]
0x180009090  mov     edx, 32h ; '2'
0x180009095  and     al, 1
0x180009097  mov     ecx, 100h
0x18000909c  neg     al
0x18000909e  sbb     ax, ax
0x1800090a1  add     ax, 2
0x1800090a5  mov     [rsp+68h+arg_0], ax
0x1800090aa  call    cs:__imp_ExAllocatePool2
0x1800090b1  nop     dword ptr [rax+rax+00h]
0x1800090b6  mov     r15, rax
0x1800090b9  test    rax, rax
0x1800090bc  jnz     short loc_1800090CB
0x1800090be  mov     ebx, 0C0000017h
0x1800090c3  mov     [r14], r12
0x1800090c6  jmp     loc_180009166
0x1800090cb  movups  xmm0, xmmword ptr [rdi]
0x1800090ce  movups  xmmword ptr [rax], xmm0
0x1800090d1  movups  xmm1, xmmword ptr [rdi+10h]
0x1800090d5  movups  xmmword ptr [rax+10h], xmm1
0x1800090d9  movups  xmm0, xmmword ptr [rdi+20h]
0x1800090dd  movups  xmmword ptr [rax+20h], xmm0
0x1800090e1  mov     [rax+10h], r12
0x1800090e5  mov     [rax], r12
0x1800090e8  mov     [rax+20h], r12
0x1800090ec  mov     r12, rax
0x1800090ef  mov     [r14], rax
0x1800090f2  mov     ebx, 10000h
0x1800090f7  movzx   ecx, [rsp+68h+arg_0]
0x1800090fc  cmp     [rdi], rsi
0x1800090ff  jz      loc_1800091BB
0x180009105  xor     edx, edx
0x180009107  mov     eax, ecx
0x180009109  imul    eax, [rdi+8]
0x18000910d  mov     r8d, r13d
0x180009110  add     eax, 7
0x180009113  and     eax, 0FFFFFFF8h
0x180009116  div     ecx
0x180009118  mov     [r12+8], eax
0x18000911d  lea     edx, [rax+1]
0x180009120  imul    edx, ecx
0x180009123  mov     ecx, 100h
0x180009128  add     rdx, 2
0x18000912c  call    cs:__imp_ExAllocatePool2
0x180009133  nop     dword ptr [rax+rax+00h]
0x180009138  mov     [r12], rax
0x18000913c  test    rax, rax
0x18000913f  jnz     short loc_18000918C
0x180009141  mov     ebx, 0C0000017h
0x180009146  xor     r12d, r12d
0x180009149  mov     [r14], r12
  ... truncated ...
```
