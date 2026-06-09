# UxpSslPrepareSendBuffer

- ea: `0x1c00c9f30`
- end: `0x1c00ca311`
- name: `UxpSslPrepareSendBuffer`
- size: `993`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0134f04`
- `0x1c0135198`
- `0x1c01566a0`
- `0x1c01587b4`

## callees

- `0x1c0001118`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c00c9f30`
- `0x1c00ca320`
- `0x1c0156e44`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c00c9fe5`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00c9fe5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00ca270`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00ca270`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00ca072`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f59ff`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00ca072`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f59ff`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f5987`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f59bf`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f5987`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f59bf`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00ca2fb`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00ca2fb`

## pseudocode

```c
__int64 __fastcall UxpSslPrepareSendBuffer(
        unsigned int *a1,
        __int64 **a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned __int8 a5,
        _QWORD *a6)
{
  unsigned int v6; // r12d
  __int64 v7; // r10
  unsigned int *v8; // r14
  unsigned int v9; // r8d
  unsigned int v10; // r13d
  __int64 v11; // rcx
  unsigned int v12; // r15d
  __int64 v13; // rdi
  SIZE_T v14; // rdx
  unsigned int v15; // esi
  unsigned int v16; // eax
  PVOID v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // eax
  __int64 v20; // rbp
  _DWORD *PoolWithTagPriority; // rbx
  char v22; // al
  unsigned int v23; // edx
  char *v24; // rbp
  int v25; // edi
  int v26; // eax
  unsigned int v27; // ecx
  __int64 v28; // rax
  char *v29; // r13
  unsigned int v30; // eax
  unsigned int v31; // r15d
  __int64 *v32; // rsi
  _DWORD *v33; // rcx
  int v34; // r14d
  char *v35; // rax
  unsigned int v36; // ecx
  char *v37; // rdx
  unsigned int v38; // eax
  __int64 v39; // rdi
  int v40; // eax
  bool v41; // zf
  unsigned int v43; // r8d
  unsigned int v44; // eax
  _QWORD *v45; // rbx
  unsigned int v46; // r8d
  unsigned int v47; // eax
  __int64 v48; // rbp
  unsigned int v49; // r8d
  unsigned int v50; // eax
  unsigned int v51; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v52; // [rsp+34h] [rbp-64h]
  unsigned int v53; // [rsp+38h] [rbp-60h]
  unsigned int v54; // [rsp+3Ch] [rbp-5Ch]
  unsigned int v55; // [rsp+40h] [rbp-58h]
  unsigned int v56; // [rsp+44h] [rbp-54h]
  unsigned int v60; // [rsp+B8h] [rbp+20h]

  v60 = a4;
  v6 = 0;
  v7 = a1[114];
  v8 = a1;
  v9 = a1[116];
  v10 = a4;
  *a6 = 0;
  v51 = 0;
  v54 = v9;
  if ( (unsigned int)v7 >= 0x10000 )
    return 3221225485LL;
  v11 = a1[115];
  if ( (unsigned int)v11 >= 0x10000 )
    return 3221225485LL;
  v12 = a4 / v9 + (a4 % v9 != 0);
  v53 = v12;
  v13 = a4 + v12 * (v7 + v11);
  v14 = a4 + v12 * ((_DWORD)v7 + (_DWORD)v11);
  if ( v14 != v13 )
    return 3221225621LL;
  v15 = (MmSizeOfMdl((PVOID)0xFFF, v14) + 7) & 0xFFFFFFF8;
  if ( (unsigned int)v13 >= 0xFFFFFFC8 )
    return 3221225626LL;
  v16 = v13 + v15 + 56;
  if ( v16 < v15 )
    return 3221225626LL;
  if ( (unsigned int)v13 < UxSslSmallSendBufferSize )
  {
    if ( !UxCompactMode )
    {
      v17 = (PVOID)qword_1C0074600;
      v43 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v44 = *(_DWORD *)qword_1C0074600 - 1;
      if ( v43 < *(_DWORD *)qword_1C0074600 )
        v44 = v43;
      v20 = *(_QWORD *)(*(_QWORD *)(qword_1C0074600 + 32) + 8LL * v44);
      if ( *(_BYTE *)(v20 + 112) )
        goto LABEL_13;
LABEL_12:
      PplpLazyInitializeLookasideList(v17, v20);
LABEL_13:
      ++*(_DWORD *)(v20 + 20);
      PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v20);
      if ( !PoolWithTagPriority )
      {
        ++*(_DWORD *)(v20 + 24);
        PoolWithTagPriority = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v20 + 48))(
                                          *(unsigned int *)(v20 + 36),
                                          *(unsigned int *)(v20 + 44),
                                          *(unsigned int *)(v20 + 40),
                                          v20);
      }
      v6 = v51;
LABEL_16:
      v22 = 1;
      goto LABEL_17;
    }
    v45 = (_QWORD *)qword_1C0074600;
    v46 = KeGetCurrentNodeNumber() + 1;
    v47 = *(_DWORD *)v45 - 1;
    if ( v46 < *(_DWORD *)v45 )
      v47 = v46;
    v48 = *(_QWORD *)(v45[4] + 8LL * v47);
    if ( !*(_BYTE *)(v48 + 112) )
      goto LABEL_54;
    goto LABEL_55;
  }
  if ( (unsigned int)v13 <= UxSslSendBufferSize )
  {
    if ( !UxCompactMode )
    {
      v17 = P;
      v18 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v19 = *(_DWORD *)P - 1;
      if ( v18 < *(_DWORD *)P )
        v19 = v18;
      v20 = *(_QWORD *)(*((_QWORD *)P + 4) + 8LL * v19);
      if ( *(_BYTE *)(v20 + 112) )
        goto LABEL_13;
      goto LABEL_12;
    }
    v45 = P;
    v49 = KeGetCurrentNodeNumber() + 1;
    v50 = *(_DWORD *)v45 - 1;
    if ( v49 < *(_DWORD *)v45 )
      v50 = v49;
    v48 = *(_QWORD *)(v45[4] + 8LL * v50);
    if ( !*(_BYTE *)(v48 + 112) )
LABEL_54:
      PplpLazyInitializeLookasideList(v45, v48);
LABEL_55:
    ++*(_DWORD *)(v48 + 20);
    PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v48);
    if ( !PoolWithTagPriority )
    {
      ++*(_DWORD *)(v48 + 24);
      PoolWithTagPriority = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v48 + 48))(
                                        *(unsigned int *)(v48 + 36),
                                        *(unsigned int *)(v48 + 44),
                                        *(unsigned int *)(v48 + 40),
                                        v48);
    }
    goto LABEL_16;
  }
  PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)512, v16, 0x53537855u, LowPoolPriority);
  v22 = 0;
LABEL_17:
  if ( !PoolWithTagPriority )
    return 3221225626LL;
  *(_OWORD *)PoolWithTagPriority = 0;
  *((_OWORD *)PoolWithTagPriority + 1) = 0;
  *((_OWORD *)PoolWithTagPriority + 2) = 0;
  *PoolWithTagPriority = 1397979221;
  *((_BYTE *)PoolWithTagPriority + 4) = v22;
  PoolWithTagPriority[11] = v13;
  *((_QWORD *)PoolWithTagPriority + 6) = (char *)PoolWithTagPriority + v15 + 56;
  v23 = PoolWithTagPriority[11];
  v52 = v23;
  v24 = (char *)PoolWithTagPriority + v15 + 56;
  v25 = 0;
  v26 = (_DWORD)PoolWithTagPriority + v15 + 56;
  if ( v12 )
  {
    while ( 1 )
    {
      v27 = v54;
      v28 = v8[114];
      if ( v10 <= v54 )
        v27 = v10;
      v56 = v27;
      v29 = &v24[v28];
      v30 = v8[115] + v27 + v28;
      v55 = v30;
      if ( v30 > v23 )
        break;
      v31 = v27;
      v32 = *a2;
      v33 = a3;
      v34 = *a3;
      if ( v31 )
      {
        while ( 1 )
        {
          v35 = (*((_BYTE *)v32 + 10) & 5) != 0
              ? (char *)v32[3]
              : (char *)MmMapLockedPagesSpecifyCache((PMDL)v32, 0, MmCached, 0, 0, 0x40000000u);
          if ( !v35 )
            break;
          v36 = *((_DWORD *)v32 + 10) - v34;
          v37 = &v35[v34];
          if ( v36 <= v31 )
            v32 = (__int64 *)*v32;
          v34 += v31;
          v38 = v31;
          if ( v36 <= v31 )
          {
            v38 = v36;
            v34 = 0;
          }
          v39 = v38;
          memmove(v29, v37, v38);
          v29 += v39;
          v31 -= v39;
          if ( !v31 )
          {
            v30 = v55;
            v33 = a3;
            goto LABEL_32;
          }
        }
        v8 = a1;
        v25 = -1073741670;
      }
      else
      {
LABEL_32:
        *a2 = v32;
        *v33 = v34;
        v8 = a1;
        v40 = UxpSslSealMessage((_DWORD)a1, (_DWORD)v24, v30, a5, (__int64)&v51);
        v6 = v51;
        v25 = v40;
      }
      if ( v25 < 0 )
        goto LABEL_60;
      if ( v6 > v52 )
      {
        v25 = -1073741675;
        goto LABEL_60;
      }
      v23 = v52 - v6;
      v10 = v60 - v56;
      v24 += v6;
      v52 -= v6;
      v41 = v53-- == 1;
      v60 -= v56;
      if ( v41 )
      {
        v26 = PoolWithTagPriority[12];
        goto LABEL_37;
      }
    }
    v25 = -1073741789;
LABEL_60:
    UxSslFreeSendBufferList(PoolWithTagPriority);
  }
  else
  {
LABEL_37:
    PoolWithTagPriority[10] = (_DWORD)v24 - v26;
    *a6 = PoolWithTagPriority;
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1c00c9f30  mov     r11, rsp
0x1c00c9f33  mov     [r11+20h], r9d
0x1c00c9f37  mov     [r11+18h], r8
0x1c00c9f3b  mov     [r11+10h], rdx
0x1c00c9f3f  mov     [r11+8], rcx
0x1c00c9f43  push    r12
0x1c00c9f45  push    r13
0x1c00c9f47  push    r14
0x1c00c9f49  sub     rsp, 80h
0x1c00c9f50  mov     rax, [rsp+98h+arg_28]
0x1c00c9f58  xor     r12d, r12d
0x1c00c9f5b  mov     r10d, [rcx+1C8h]
0x1c00c9f62  mov     r14, rcx
0x1c00c9f65  mov     r8d, [rcx+1D0h]
0x1c00c9f6c  mov     r13d, r9d
0x1c00c9f6f  mov     [rax], r12
0x1c00c9f72  mov     [r11-68h], r12d
0x1c00c9f76  mov     [rsp+98h+var_5C], r8d
0x1c00c9f7b  cmp     r10d, 10000h
0x1c00c9f82  jnb     loc_1C00F5A6F
0x1c00c9f88  mov     ecx, [rcx+1CCh]
0x1c00c9f8e  cmp     ecx, 10000h
0x1c00c9f94  jnb     loc_1C00F5A6F
0x1c00c9f9a  xor     edx, edx
0x1c00c9f9c  mov     [r11-38h], rdi
0x1c00c9fa0  mov     eax, r13d
0x1c00c9fa3  mov     [r11-40h], r15
0x1c00c9fa7  div     r8d
0x1c00c9faa  xor     r15d, r15d
0x1c00c9fad  lea     rdi, [r10+rcx]
0x1c00c9fb1  test    edx, edx
0x1c00c9fb3  setnz   r15b
0x1c00c9fb7  add     r15d, eax
0x1c00c9fba  mov     eax, r15d
0x1c00c9fbd  imul    rdi, rax
0x1c00c9fc1  mov     [rsp+98h+var_60], r15d
0x1c00c9fc6  add     rdi, r13
0x1c00c9fc9  mov     edx, edi; Length
0x1c00c9fcb  cmp     rdx, rdi
0x1c00c9fce  jnz     loc_1C00F5976
0x1c00c9fd4  mov     [r11-20h], rbx
0x1c00c9fd8  mov     ecx, 0FFFh; Base
0x1c00c9fdd  mov     [r11-28h], rbp
0x1c00c9fe1  mov     [r11-30h], rsi
0x1c00c9fe5  call    cs:__imp_MmSizeOfMdl
0x1c00c9fec  nop     dword ptr [rax+rax+00h]
0x1c00c9ff1  lea     ecx, [rdi+38h]
0x1c00c9ff4  lea     esi, [rax+7]
0x1c00c9ff7  and     esi, 0FFFFFFF8h
0x1c00c9ffa  cmp     ecx, 38h ; '8'
0x1c00c9ffd  jb      loc_1C00F5A65
0x1c00ca003  lea     eax, [rsi+38h]
0x1c00ca006  add     eax, edi
0x1c00ca008  cmp     eax, esi
0x1c00ca00a  jb      loc_1C00F5A65
0x1c00ca010  cmp     edi, cs:UxSslSmallSendBufferSize
0x1c00ca016  jb      loc_1C00CA2A6
0x1c00ca01c  cmp     edi, cs:UxSslSendBufferSize
0x1c00ca022  ja      loc_1C00CA2EB
0x1c00ca028  cmp     cs:UxCompactMode, r12b
0x1c00ca02f  jnz     loc_1C00F59B8
0x1c00ca035  mov     eax, gs:1A4h
0x1c00ca03d  mov     rcx, cs:P
0x1c00ca044  lea     r8d, [rax+1]
0x1c00ca048  mov     edx, [rcx]
0x1c00ca04a  cmp     r8d, edx
0x1c00ca04d  lea     eax, [rdx-1]
0x1c00ca050  cmovb   eax, r8d
0x1c00ca054  mov     edx, eax
0x1c00ca056  mov     rax, [rcx+20h]
0x1c00ca05a  mov     rbp, [rax+rdx*8]
0x1c00ca05e  cmp     [rbp+70h], r12b
0x1c00ca062  jnz     short loc_1C00CA06C
0x1c00ca064  mov     rdx, rbp
0x1c00ca067  call    PplpLazyInitializeLookasideList
0x1c00ca06c  inc     dword ptr [rbp+14h]
0x1c00ca06f  mov     rcx, rbp; ListHead
0x1c00ca072  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00ca079  nop     dword ptr [rax+rax+00h]
0x1c00ca07e  mov     rbx, rax
0x1c00ca081  test    rax, rax
0x1c00ca084  jz      loc_1C00CA284
0x1c00ca08a  mov     r12d, [rsp+98h+var_68]
0x1c00ca08f  mov     al, 1
0x1c00ca091  test    rbx, rbx
0x1c00ca094  jz      loc_1C00F5A65
0x1c00ca09a  xorps   xmm0, xmm0
0x1c00ca09d  mov     ecx, esi
0x1c00ca09f  movups  xmmword ptr [rbx], xmm0
0x1c00ca0a2  add     rcx, 38h ; '8'
0x1c00ca0a6  movups  xmmword ptr [rbx+10h], xmm0
0x1c00ca0aa  add     rcx, rbx
0x1c00ca0ad  movups  xmmword ptr [rbx+20h], xmm0
0x1c00ca0b1  mov     dword ptr [rbx], 53537855h
0x1c00ca0b7  mov     [rbx+4], al
0x1c00ca0ba  mov     [rbx+2Ch], edi
0x1c00ca0bd  mov     [rbx+30h], rcx
0x1c00ca0c1  test    rbx, rbx
0x1c00ca0c4  jz      loc_1C00F5A65
0x1c00ca0ca  mov     edx, [rbx+2Ch]
0x1c00ca0cd  xor     r8d, r8d
0x1c00ca0d0  mov     [rsp+98h+var_64], edx
0x1c00ca0d4  mov     rbp, rcx
0x1c00ca0d7  mov     edi, r8d
0x1c00ca0da  mov     eax, ebp
0x1c00ca0dc  test    r15d, r15d
0x1c00ca0df  jz      loc_1C00CA21D
0x1c00ca0e5  mov     ecx, [rsp+98h+var_5C]
0x1c00ca0e9  cmp     r13d, ecx
0x1c00ca0ec  mov     eax, [r14+1C8h]
0x1c00ca0f3  cmovbe  ecx, r13d
0x1c00ca0f7  mov     [rsp+98h+var_54], ecx
0x1c00ca0fb  lea     r13, [rax+rbp]
0x1c00ca0ff  add     eax, ecx
0x1c00ca101  add     eax, [r14+1CCh]
0x1c00ca108  mov     [rsp+98h+var_58], eax
0x1c00ca10c  cmp     eax, edx
0x1c00ca10e  ja      loc_1C00F5A52
0x1c00ca114  mov     r15d, ecx
0x1c00ca117  mov     rcx, [rsp+98h+arg_8]
0x1c00ca11f  mov     rsi, [rcx]
0x1c00ca122  mov     rcx, [rsp+98h+arg_10]
0x1c00ca12a  mov     r14d, [rcx]
0x1c00ca12d  test    r15d, r15d
0x1c00ca130  jz      short loc_1C00CA194
0x1c00ca132  test    byte ptr [rsi+0Ah], 5
0x1c00ca136  jz      loc_1C00CA257
0x1c00ca13c  mov     rax, [rsi+18h]
0x1c00ca140  test    rax, rax
0x1c00ca143  jz      loc_1C00F5A39
0x1c00ca149  mov     ecx, [rsi+28h]
0x1c00ca14c  mov     edx, r14d
0x1c00ca14f  sub     ecx, r14d
0x1c00ca152  add     rdx, rax; Src
0x1c00ca155  cmp     ecx, r15d
0x1c00ca158  ja      short loc_1C00CA15D
0x1c00ca15a  mov     rsi, [rsi]
0x1c00ca15d  add     r14d, r15d
0x1c00ca160  mov     eax, r15d
0x1c00ca163  cmp     ecx, r15d
0x1c00ca166  cmovbe  eax, ecx
0x1c00ca169  cmovbe  r14d, r8d
0x1c00ca16d  mov     r8d, eax; Size
0x1c00ca170  mov     rcx, r13; void *
0x1c00ca173  mov     edi, eax
0x1c00ca175  call    memmove
0x1c00ca17a  add     r13, rdi
0x1c00ca17d  mov     r8d, 0
0x1c00ca183  sub     r15d, edi
0x1c00ca186  jnz     short loc_1C00CA132
0x1c00ca188  mov     eax, [rsp+98h+var_58]
0x1c00ca18c  mov     rcx, [rsp+98h+arg_10]
0x1c00ca194  mov     rdx, [rsp+98h+arg_8]
0x1c00ca19c  mov     [rdx], rsi
0x1c00ca19f  mov     [rcx], r14d
0x1c00ca1a2  mov     r14, [rsp+98h+arg_0]
0x1c00ca1aa  lea     rcx, [rsp+98h+var_68]
0x1c00ca1af  movzx   r9d, [rsp+98h+arg_20]
0x1c00ca1b8  mov     r8d, eax
0x1c00ca1bb  mov     qword ptr [rsp+98h+BugCheckOnFailure], rcx
0x1c00ca1c0  mov     rdx, rbp
0x1c00ca1c3  mov     rcx, r14
0x1c00ca1c6  call    UxpSslSealMessage
0x1c00ca1cb  mov     r12d, [rsp+98h+var_68]
0x1c00ca1d0  mov     edi, eax
0x1c00ca1d2  test    edi, edi
0x1c00ca1d4  js      loc_1C00F5A57
0x1c00ca1da  mov     edx, [rsp+98h+var_64]
0x1c00ca1de  cmp     r12d, edx
0x1c00ca1e1  ja      loc_1C00F5A4B
0x1c00ca1e7  mov     r13d, [rsp+98h+arg_18]
0x1c00ca1ef  sub     edx, r12d
0x1c00ca1f2  sub     r13d, [rsp+98h+var_54]
0x1c00ca1f7  mov     r8d, 0
0x1c00ca1fd  mov     eax, r12d
0x1c00ca200  add     rbp, rax
0x1c00ca203  mov     [rsp+98h+var_64], edx
0x1c00ca207  add     [rsp+98h+var_60], 0FFFFFFFFh
0x1c00ca20c  mov     [rsp+98h+arg_18], r13d
0x1c00ca214  jnz     loc_1C00CA0E5
0x1c00ca21a  mov     eax, [rbx+30h]
0x1c00ca21d  sub     ebp, eax
0x1c00ca21f  mov     rax, [rsp+98h+arg_28]
0x1c00ca227  mov     [rbx+28h], ebp
0x1c00ca22a  mov     [rax], rbx
0x1c00ca22d  mov     eax, edi
0x1c00ca22f  mov     rbp, [rsp+98h+var_28]
0x1c00ca234  mov     rsi, [rsp+98h+var_30]
0x1c00ca239  mov     rbx, [rsp+98h+var_20]
0x1c00ca23e  mov     rdi, [rsp+98h+var_38]
0x1c00ca243  mov     r15, [rsp+98h+var_40]
0x1c00ca248  add     rsp, 80h
0x1c00ca24f  pop     r14
0x1c00ca251  pop     r13
0x1c00ca253  pop     r12
0x1c00ca255  retn
0x1c00ca257  xor     r9d, r9d; RequestedAddress
0x1c00ca25a  mov     [rsp+98h+Priority], 40000000h; Priority
0x1c00ca262  mov     [rsp+98h+BugCheckOnFailure], r8d; BugCheckOnFailure
0x1c00ca267  xor     edx, edx; AccessMode
0x1c00ca269  mov     rcx, rsi; MemoryDescriptorList
0x1c00ca26c  lea     r8d, [r9+1]; CacheType
0x1c00ca270  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c00ca277  nop     dword ptr [rax+rax+00h]
0x1c00ca27c  xor     r8d, r8d
0x1c00ca27f  jmp     loc_1C00CA140
0x1c00ca284  inc     dword ptr [rbp+18h]
0x1c00ca287  mov     r9, rbp
0x1c00ca28a  mov     edx, [rbp+2Ch]
0x1c00ca28d  mov     rax, [rbp+30h]
0x1c00ca291  mov     r8d, [rbp+28h]
0x1c00ca295  mov     ecx, [rbp+24h]
0x1c00ca298  call    cs:__guard_dispatch_icall_fptr
0x1c00ca29e  mov     rbx, rax
0x1c00ca2a1  jmp     loc_1C00CA08A
0x1c00ca2a6  cmp     cs:UxCompactMode, r12b
0x1c00ca2ad  jnz     loc_1C00F5980
0x1c00ca2b3  mov     eax, gs:1A4h
0x1c00ca2bb  mov     rcx, cs:qword_1C0074600
0x1c00ca2c2  lea     r8d, [rax+1]
0x1c00ca2c6  mov     edx, [rcx]
0x1c00ca2c8  cmp     r8d, edx
0x1c00ca2cb  lea     eax, [rdx-1]
0x1c00ca2ce  cmovb   eax, r8d
0x1c00ca2d2  mov     edx, eax
0x1c00ca2d4  mov     rax, [rcx+20h]
0x1c00ca2d8  mov     rbp, [rax+rdx*8]
0x1c00ca2dc  cmp     [rbp+70h], r12b
0x1c00ca2e0  jnz     loc_1C00CA06C
0x1c00ca2e6  jmp     loc_1C00CA064
0x1c00ca2eb  mov     edx, eax; NumberOfBytes
0x1c00ca2ed  xor     r9d, r9d; Priority
0x1c00ca2f0  mov     ecx, 200h; PoolType
0x1c00ca2f5  mov     r8d, 53537855h; Tag
0x1c00ca2fb  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00ca302  nop     dword ptr [rax+rax+00h]
0x1c00ca307  mov     rbx, rax
0x1c00ca30a  xor     al, al
0x1c00ca30c  jmp     loc_1C00CA091
0x1c00f5976  mov     eax, 0C0000095h
0x1c00f597b  jmp     loc_1C00CA23E
0x1c00f5980  mov     rbx, cs:qword_1C0074600
0x1c00f5987  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00f598e  nop     dword ptr [rax+rax+00h]
0x1c00f5993  mov     edx, [rbx]
0x1c00f5995  movzx   r8d, ax
0x1c00f5999  inc     r8d
0x1c00f599c  cmp     r8d, edx
0x1c00f599f  lea     eax, [rdx-1]
0x1c00f59a2  cmovb   eax, r8d
0x1c00f59a6  mov     edx, eax
0x1c00f59a8  mov     rax, [rbx+20h]
0x1c00f59ac  mov     rbp, [rax+rdx*8]
0x1c00f59b0  cmp     [rbp+70h], r12b
0x1c00f59b4  jz      short loc_1C00F59EE
0x1c00f59b6  jmp     short loc_1C00F59F9
0x1c00f59b8  mov     rbx, cs:P
0x1c00f59bf  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00f59c6  nop     dword ptr [rax+rax+00h]
0x1c00f59cb  mov     edx, [rbx]
0x1c00f59cd  movzx   r8d, ax
0x1c00f59d1  inc     r8d
0x1c00f59d4  cmp     r8d, edx
0x1c00f59d7  lea     eax, [rdx-1]
0x1c00f59da  cmovb   eax, r8d
0x1c00f59de  mov     edx, eax
0x1c00f59e0  mov     rax, [rbx+20h]
0x1c00f59e4  mov     rbp, [rax+rdx*8]
0x1c00f59e8  cmp     [rbp+70h], r12b
0x1c00f59ec  jnz     short loc_1C00F59F9
0x1c00f59ee  mov     rdx, rbp
0x1c00f59f1  mov     rcx, rbx
0x1c00f59f4  call    PplpLazyInitializeLookasideList
0x1c00f59f9  inc     dword ptr [rbp+14h]
0x1c00f59fc  mov     rcx, rbp; ListHead
0x1c00f59ff  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00f5a06  nop     dword ptr [rax+rax+00h]
0x1c00f5a0b  mov     rbx, rax
0x1c00f5a0e  test    rax, rax
0x1c00f5a11  jnz     loc_1C00CA08F
0x1c00f5a17  inc     dword ptr [rbp+18h]
0x1c00f5a1a  mov     r9, rbp
0x1c00f5a1d  mov     edx, [rbp+2Ch]
0x1c00f5a20  mov     rax, [rbp+30h]
0x1c00f5a24  mov     r8d, [rbp+28h]
0x1c00f5a28  mov     ecx, [rbp+24h]
0x1c00f5a2b  call    cs:__guard_dispatch_icall_fptr
0x1c00f5a31  mov     rbx, rax
0x1c00f5a34  jmp     loc_1C00CA08F
0x1c00f5a39  mov     r14, [rsp+98h+arg_0]
0x1c00f5a41  mov     edi, 0C000009Ah
0x1c00f5a46  jmp     loc_1C00CA1D2
0x1c00f5a4b  mov     edi, 0C0000095h
0x1c00f5a50  jmp     short loc_1C00F5A57
0x1c00f5a52  mov     edi, 0C0000023h
0x1c00f5a57  mov     rcx, rbx; P
0x1c00f5a5a  call    UxSslFreeSendBufferList
0x1c00f5a5f  nop
0x1c00f5a60  jmp     loc_1C00CA22D
0x1c00f5a65  mov     eax, 0C000009Ah
  ... truncated ...
```
