# DplWrapUnprotect

- ea: `0x140008d28`
- end: `0x140009724`
- name: `DplWrapUnprotect`
- size: `2556`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14004fca0`

## callees

- `0x1400080e4`
- `0x140008d28`
- `0x14000c380`
- `0x14000c680`
- `0x14000cba0`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009519`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009541`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009594`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400095ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009623`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009662`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009690`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d886`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d904`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009519`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009541`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009594`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400095ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009623`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009662`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009690`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d886`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d904`
- `ntoskrnl!ExAllocatePool2` at `0x140008e19`
- `ntoskrnl!ExAllocatePool2` at `0x140008e4e`
- `ntoskrnl!ExAllocatePool2` at `0x140008e76`
- `ntoskrnl!ExAllocatePool2` at `0x140009000`
- `ntoskrnl!ExAllocatePool2` at `0x1400090be`
- `ntoskrnl!ExAllocatePool2` at `0x140009122`
- `ntoskrnl!ExAllocatePool2` at `0x1400092bf`
- `ntoskrnl!ExAllocatePool2` at `0x14000930d`
- `ntoskrnl!ExAllocatePool2` at `0x140009351`
- `ntoskrnl!ExAllocatePool2` at `0x140008e19`
- `ntoskrnl!ExAllocatePool2` at `0x140008e4e`
- `ntoskrnl!ExAllocatePool2` at `0x140008e76`
- `ntoskrnl!ExAllocatePool2` at `0x140009000`
- `ntoskrnl!ExAllocatePool2` at `0x1400090be`
- `ntoskrnl!ExAllocatePool2` at `0x140009122`
- `ntoskrnl!ExAllocatePool2` at `0x1400092bf`
- `ntoskrnl!ExAllocatePool2` at `0x14000930d`
- `ntoskrnl!ExAllocatePool2` at `0x140009351`
- `ksecdd!BCryptDecrypt` at `0x14000942b`
- `ksecdd!BCryptDecrypt` at `0x14000942b`
- `ksecdd!BCryptGetProperty` at `0x140009095`
- `ksecdd!BCryptGetProperty` at `0x140009095`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x140009396`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x140009396`
- `ksecdd!BCryptCreateHash` at `0x14000916a`
- `ksecdd!BCryptCreateHash` at `0x14000916a`
- `ksecdd!BCryptHashData` at `0x14000919a`
- `ksecdd!BCryptHashData` at `0x14000919a`
- `ksecdd!BCryptDestroyHash` at `0x1400095ad`
- `ksecdd!BCryptDestroyHash` at `0x14000d77e`
- `ksecdd!BCryptDestroyHash` at `0x1400095ad`
- `ksecdd!BCryptDestroyHash` at `0x14000d77e`
- `ksecdd!BCryptFinishHash` at `0x1400091d2`
- `ksecdd!BCryptFinishHash` at `0x1400091d2`
- `ksecdd!BCryptDestroyKey` at `0x14000944a`
- `ksecdd!BCryptDestroyKey` at `0x140009557`
- `ksecdd!BCryptDestroyKey` at `0x14000d71c`
- `ksecdd!BCryptDestroyKey` at `0x14000944a`
- `ksecdd!BCryptDestroyKey` at `0x140009557`
- `ksecdd!BCryptDestroyKey` at `0x14000d71c`

## pseudocode

```c
__int64 __fastcall DplWrapUnprotect(
        UCHAR *a1,
        ULONG a2,
        const void *a3,
        unsigned int a4,
        _OWORD *a5,
        ULONG pbOutput,
        void *a7,
        ULONG *a8)
{
  size_t v8; // rbx
  UCHAR *v10; // rdi
  UCHAR *Pool2; // r12
  UCHAR *v12; // r14
  __int64 v13; // r13
  NTSTATUS Property; // ebx
  UCHAR *v15; // rax
  __int64 v16; // rcx
  unsigned __int16 v17; // ax
  unsigned int v18; // r9d
  unsigned int v19; // eax
  unsigned int v20; // r8d
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // edx
  ULONG v24; // r15d
  unsigned int v25; // edx
  __int64 v26; // rax
  __int64 v27; // rbx
  void *v28; // rax
  PUCHAR v29; // r15
  __int64 v30; // rax
  UCHAR *v31; // rcx
  ULONG v32; // eax
  UCHAR *v33; // rax
  ULONG v34; // ebx
  ULONG v35; // ecx
  __int64 v36; // rdx
  void *v37; // r15
  ULONG v38; // eax
  void *v39; // rax
  __int64 v40; // rax
  UCHAR *v41; // rcx
  ULONG v42; // r15d
  __int64 v43; // rcx
  UCHAR *v44; // rax
  UCHAR *v45; // rax
  PVOID v46; // r8
  __int64 v47; // rcx
  _BYTE *v48; // rax
  PVOID v49; // r8
  __int64 v50; // rcx
  _BYTE *v51; // rax
  PUCHAR v52; // r8
  __int64 v53; // rcx
  PUCHAR v54; // rax
  PVOID v55; // r8
  ULONG v56; // eax
  __int64 v57; // rcx
  _BYTE *i; // rax
  __int64 v59; // rcx
  UCHAR *v60; // rax
  PUCHAR v61; // rcx
  PUCHAR v62; // rax
  __int64 v63; // rdx
  PUCHAR v64; // r8
  __int64 v65; // rax
  PUCHAR v66; // rcx
  ULONG Size; // [rsp+54h] [rbp-C4h]
  ULONG cbInput; // [rsp+60h] [rbp-B8h] BYREF
  int v70; // [rsp+64h] [rbp-B4h]
  unsigned int v71; // [rsp+68h] [rbp-B0h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-A8h] BYREF
  unsigned int v73; // [rsp+78h] [rbp-A0h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+80h] [rbp-98h] BYREF
  PUCHAR pbInput; // [rsp+88h] [rbp-90h]
  PUCHAR pbIV; // [rsp+90h] [rbp-88h]
  PUCHAR v77; // [rsp+98h] [rbp-80h]
  PVOID P; // [rsp+A0h] [rbp-78h]
  PVOID v79; // [rsp+A8h] [rbp-70h]
  PVOID v80; // [rsp+B0h] [rbp-68h]
  ULONG pcbResult; // [rsp+B8h] [rbp-60h] BYREF
  UCHAR *v82; // [rsp+C0h] [rbp-58h]
  UCHAR *v83; // [rsp+C8h] [rbp-50h]
  UCHAR *v84; // [rsp+D0h] [rbp-48h]
  __int64 v85; // [rsp+D8h] [rbp-40h]
  UCHAR *v86; // [rsp+E0h] [rbp-38h]
  __int64 v87; // [rsp+E8h] [rbp-30h]

  v8 = a4;
  v10 = 0;
  v83 = 0;
  v73 = 0;
  pbIV = 0;
  Pool2 = 0;
  v82 = 0;
  v12 = 0;
  phKey = 0;
  P = 0;
  phHash = 0;
  v79 = 0;
  v80 = 0;
  Size = 0;
  cbInput = 0;
  pbInput = 0;
  v71 = 0;
  v70 = 0;
  v77 = 0;
  pbOutput = 0;
  pcbResult = 0;
  if ( !a1 || !a2 || !a3 || a4 < 0x10 || !a5 || !a7 || !a8 )
  {
    Property = -1073741811;
    EfspTraceLogAssert(a1, 9, 1032, 3221225485LL);
    v13 = 32;
    goto LABEL_75;
  }
  v13 = 32;
  Pool2 = (UCHAR *)ExAllocatePool2(64, 32, 1265854021);
  v82 = Pool2;
  if ( !Pool2 )
    goto LABEL_9;
  v12 = (UCHAR *)ExAllocatePool2(64, 32, 1265854021);
  if ( !v12 )
    goto LABEL_9;
  v73 = v8;
  v15 = (UCHAR *)ExAllocatePool2(64, v8, 1265854021);
  v10 = v15;
  v83 = v15;
  if ( !v15 )
  {
LABEL_12:
    Property = -1073741670;
    goto LABEL_75;
  }
  memmove(v15, a3, v8);
  v16 = *(unsigned __int16 *)v10;
  if ( (unsigned __int16)v16 < 0x10u || (v17 = *((_WORD *)v10 + 1), (unsigned __int16)v16 > v17) )
  {
    v21 = 1090;
    goto LABEL_23;
  }
  if ( v17 < 0x10u
    || (v18 = *((unsigned __int16 *)v10 + 2), v16 = v18 + v17, (unsigned int)v16 <= v17)
    || (v19 = *((unsigned __int16 *)v10 + 3), (unsigned int)v16 > v19) )
  {
    v21 = 1098;
    goto LABEL_23;
  }
  v16 = *((unsigned __int16 *)v10 + 5);
  if ( (unsigned int)v16 + v19 <= v19 || (v20 = *((unsigned __int16 *)v10 + 6), (unsigned int)v16 + v19 > v20) )
  {
    v21 = 1105;
    goto LABEL_23;
  }
  if ( (unsigned int)v16 % v18 )
  {
    v21 = 1111;
LABEL_23:
    v22 = 3221225485LL;
    Property = -1073741811;
LABEL_24:
    EfspTraceLogAssert(v16, 9, v21, v22);
    goto LABEL_75;
  }
  if ( *((_WORD *)v10 + 4) > (unsigned __int16)v16 )
  {
    v21 = 1117;
    goto LABEL_23;
  }
  v23 = *((unsigned __int16 *)v10 + 7) + v20;
  if ( v23 <= v20 || v23 > (unsigned int)v8 )
  {
    v21 = 1124;
    goto LABEL_23;
  }
  v70 = 20;
  v24 = -1;
  v25 = -1;
  if ( v18 + 20 >= 0x14 )
    v25 = v18 + 20;
  v71 = v25;
  v70 = v25;
  Property = v18 >= 0xFFFFFFEC ? 0xC0000095 : 0;
  if ( v18 + 20 < 0x14 )
  {
    v22 = (unsigned int)Property;
    v21 = 1152;
    goto LABEL_24;
  }
  if ( (unsigned int)v16 + v25 < v25 )
  {
    v71 = -1;
    v70 = -1;
    Property = -1073741675;
  }
  else
  {
    v24 = v16 + v25;
    v71 = v16 + v25;
    v70 = v16 + v25;
    Property = 0;
  }
  if ( Property < 0 )
  {
    v22 = (unsigned int)Property;
    v21 = 1159;
    goto LABEL_24;
  }
  v26 = ExAllocatePool2(64, v24, 1265854021);
  v27 = v26;
  pbInput = (PUCHAR)v26;
  if ( !v26 )
    goto LABEL_12;
  *(_DWORD *)v26 = 16;
  *(_OWORD *)(v26 + 4) = *a5;
  memmove((void *)(v26 + 20), &v10[*((unsigned __int16 *)v10 + 1)], *((unsigned __int16 *)v10 + 2));
  memmove(
    (void *)(v27 + *((unsigned __int16 *)v10 + 2) + 20LL),
    &v10[*((unsigned __int16 *)v10 + 3)],
    *((unsigned __int16 *)v10 + 5));
  Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_75;
  v77 = (PUCHAR)ExAllocatePool2(64, pbOutput, 1265854021);
  if ( !v77 )
    goto LABEL_12;
  Property = DplWrapDeriveKey(a1, a2, (__int64)v12);
  if ( Property >= 0 )
  {
    v28 = (void *)ExAllocatePool2(64, cbHashObject, 1265854021);
    v79 = v28;
    if ( !v28 )
      goto LABEL_9;
    Property = BCryptCreateHash(hObject, &phHash, (PUCHAR)v28, cbHashObject, v12, 0x20u, 0);
    if ( Property < 0 )
      goto LABEL_75;
    Property = BCryptHashData(phHash, pbInput, v24, 0);
    if ( Property < 0 )
      goto LABEL_75;
    v29 = v77;
    Property = BCryptFinishHash(phHash, v77, pbOutput, 0);
    v30 = 32;
    v85 = 32;
    v31 = v12;
    v84 = v12;
    while ( v30 )
    {
      *v31++ = 0;
      v84 = v31;
      v85 = --v30;
    }
    if ( Property < 0 )
      goto LABEL_75;
    if ( pbOutput != *((unsigned __int16 *)v10 + 7) || memcmp(v29, &v10[*((unsigned __int16 *)v10 + 6)], pbOutput) )
    {
      Property = -1073700862;
      EfspTraceLogAssert(v31, 9, 1289, 3221266434LL);
      goto LABEL_75;
    }
    v32 = *((unsigned __int16 *)v10 + 4);
    if ( *a8 < v32 )
    {
      if ( *a8 )
        Property = -1073741789;
      *a8 = v32;
      goto LABEL_75;
    }
    Property = DplWrapDeriveKey(a1, a2, (__int64)Pool2);
    if ( Property >= 0 )
    {
      v33 = (UCHAR *)ExAllocatePool2(64, *((unsigned __int16 *)v10 + 2), 1265854021);
      pbIV = v33;
      if ( v33 )
      {
        memmove(v33, &v10[*((unsigned __int16 *)v10 + 1)], *((unsigned __int16 *)v10 + 2));
        v34 = *((unsigned __int16 *)v10 + 4);
        Size = v34;
        v35 = *((unsigned __int16 *)v10 + 5);
        cbInput = v35;
        v36 = v34;
        if ( v34 <= v35 )
          v36 = v35;
        v37 = (void *)ExAllocatePool2(64, v36, 1265854021);
        v80 = v37;
        if ( v37 )
        {
          v38 = cbInput;
          if ( v34 > cbInput )
            v38 = v34;
          memset(v37, 0, v38);
          v39 = (void *)ExAllocatePool2(64, dword_1400178CC, 1265854021);
          P = v39;
          if ( v39 )
          {
            Property = BCryptGenerateSymmetricKey(
                         qword_1400178C0,
                         &phKey,
                         (PUCHAR)v39,
                         dword_1400178CC,
                         Pool2,
                         0x20u,
                         0);
            v40 = 32;
            v87 = 32;
            v41 = Pool2;
            v86 = Pool2;
            while ( v40 )
            {
              *v41++ = 0;
              v86 = v41;
              v87 = --v40;
            }
            if ( Property >= 0 )
            {
              Property = BCryptDecrypt(
                           phKey,
                           &v10[*((unsigned __int16 *)v10 + 3)],
                           cbInput,
                           0,
                           pbIV,
                           *((unsigned __int16 *)v10 + 2),
                           (PUCHAR)v37,
                           cbInput,
                           &cbInput,
                           0);
              if ( Property >= 0 )
              {
                BCryptDestroyKey(phKey);
                phKey = 0;
                memmove(a7, v37, Size);
                v42 = Size;
                *a8 = Size;
                goto LABEL_76;
              }
            }
            goto LABEL_75;
          }
        }
      }
LABEL_9:
      Property = -1073741670;
    }
  }
LABEL_75:
  v42 = Size;
LABEL_76:
  if ( Pool2 )
  {
    v43 = 32;
    v44 = Pool2;
    do
    {
      *v44++ = 0;
      --v43;
    }
    while ( v43 );
    ExFreePoolWithTag(Pool2, 0x4B736645u);
  }
  if ( v12 )
  {
    v45 = v12;
    do
    {
      *v45++ = 0;
      --v13;
    }
    while ( v13 );
    ExFreePoolWithTag(v12, 0x4B736645u);
  }
  if ( phKey )
  {
    BCryptDestroyKey(phKey);
    phKey = 0;
  }
  v46 = P;
  if ( P )
  {
    v47 = dword_1400178CC;
    v48 = P;
    if ( dword_1400178CC )
    {
      do
      {
        *v48++ = 0;
        --v47;
      }
      while ( v47 );
    }
    ExFreePoolWithTag(v46, 0x4B736645u);
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  v49 = v79;
  if ( v79 )
  {
    v50 = cbHashObject;
    v51 = v79;
    if ( cbHashObject )
    {
      do
      {
        *v51++ = 0;
        --v50;
      }
      while ( v50 );
    }
    ExFreePoolWithTag(v49, 0x4B736645u);
  }
  v52 = pbInput;
  if ( pbInput )
  {
    v53 = v71;
    v54 = pbInput;
    if ( v71 )
    {
      do
      {
        *v54++ = 0;
        --v53;
      }
      while ( v53 );
    }
    ExFreePoolWithTag(v52, 0x4B736645u);
  }
  v55 = v80;
  if ( v80 )
  {
    v56 = cbInput;
    if ( v42 > cbInput )
      v56 = v42;
    v57 = v56;
    for ( i = v80; v57; --v57 )
      *i++ = 0;
    ExFreePoolWithTag(v55, 0x4B736645u);
  }
  if ( v10 )
  {
    v59 = v73;
    v60 = v10;
    if ( v73 )
    {
      do
      {
        *v60++ = 0;
        --v59;
      }
      while ( v59 );
    }
    ExFreePoolWithTag(v10, 0x4B736645u);
  }
  v61 = pbIV;
  if ( pbIV )
  {
    v62 = pbIV;
    v63 = 16;
    do
    {
      *v62++ = 0;
      --v63;
    }
    while ( v63 );
    ExFreePoolWithTag(v61, 0x4B736645u);
  }
  v64 = v77;
  if ( v77 )
  {
    v65 = pbOutput;
    v66 = v77;
    if ( pbOutput )
    {
      do
      {
        *v66++ = 0;
        --v65;
      }
      while ( v65 );
    }
    ExFreePoolWithTag(v64, 0x4B736645u);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140008d28  mov     r11, rsp
0x140008d2b  mov     [r11+18h], rbx
0x140008d2f  mov     [r11+20h], rsi
0x140008d33  mov     [rsp+cbSecret], edx
0x140008d37  mov     [r11+8], rcx
0x140008d3b  push    rdi
0x140008d3c  push    r12
0x140008d3e  push    r13
0x140008d40  push    r14
0x140008d42  push    r15
0x140008d44  sub     rsp, 0F0h
0x140008d4b  mov     ebx, r9d
0x140008d4e  mov     r15, r8
0x140008d51  xor     r8d, r8d
0x140008d54  mov     edi, r8d
0x140008d57  mov     [r11-50h], r8
0x140008d5b  mov     [rsp+118h+var_A0], r8d
0x140008d60  mov     [r11-88h], r8
0x140008d67  mov     r12d, r8d
0x140008d6a  mov     [r11-58h], r8
0x140008d6e  mov     r14d, r8d
0x140008d71  mov     qword ptr [rsp+118h+Size+4], r8
0x140008d76  mov     [rsp+118h+phKey], r8
0x140008d7b  mov     [r11-78h], r8
0x140008d7f  mov     [r11-98h], r8
0x140008d86  mov     [r11-70h], r8
0x140008d8a  mov     [r11-68h], r8
0x140008d8e  mov     [rsp+118h+Size], r8d
0x140008d93  mov     [rsp+118h+cbInput], r8d
0x140008d98  mov     [r11-90h], r8
0x140008d9f  mov     eax, r8d
0x140008da2  mov     [rsp+118h+var_B0], eax
0x140008da6  mov     [rsp+118h+var_B4], eax
0x140008daa  mov     [r11-80h], r8
0x140008dae  mov     [r11+30h], r8d
0x140008db2  mov     [r11-60h], r8d
0x140008db6  test    rcx, rcx
0x140008db9  jz      loc_1400094D0
0x140008dbf  test    edx, edx
0x140008dc1  jz      loc_1400094D0
0x140008dc7  test    r15, r15
0x140008dca  jz      loc_1400094D0
0x140008dd0  cmp     ebx, 10h
0x140008dd3  jb      loc_1400094D0
0x140008dd9  cmp     [rsp+118h+arg_20], r8
0x140008de1  jz      loc_1400094D0
0x140008de7  cmp     [rsp+118h+arg_30], r8
0x140008def  jz      loc_1400094D0
0x140008df5  mov     rax, [rsp+118h+arg_38]
0x140008dfd  test    rax, rax
0x140008e00  jz      loc_1400094D0
0x140008e06  mov     esi, 4B736645h
0x140008e0b  mov     r8d, esi
0x140008e0e  lea     r13d, [r14+20h]
0x140008e12  mov     edx, r13d
0x140008e15  lea     ecx, [r14+40h]
0x140008e19  call    cs:__imp_ExAllocatePool2
0x140008e20  nop     dword ptr [rax+rax+00h]
0x140008e25  mov     r12, rax
0x140008e28  mov     [rsp+118h+var_58], rax
0x140008e30  test    rax, rax
0x140008e33  jnz     short loc_140008E43
0x140008e35  mov     ebx, 0C000009Ah
0x140008e3a  mov     [rsp+118h+var_C8], ebx
0x140008e3e  jmp     loc_1400094F8
0x140008e43  mov     r8d, esi
0x140008e46  mov     rdx, r13
0x140008e49  mov     ecx, 40h ; '@'
0x140008e4e  call    cs:__imp_ExAllocatePool2
0x140008e55  nop     dword ptr [rax+rax+00h]
0x140008e5a  mov     r14, rax
0x140008e5d  mov     qword ptr [rsp+118h+Size+4], rax
0x140008e62  test    rax, rax
0x140008e65  jz      short loc_140008E35
0x140008e67  mov     [rsp+118h+var_A0], ebx
0x140008e6b  mov     r8d, esi
0x140008e6e  mov     rdx, rbx
0x140008e71  mov     ecx, 40h ; '@'
0x140008e76  call    cs:__imp_ExAllocatePool2
0x140008e7d  nop     dword ptr [rax+rax+00h]
0x140008e82  mov     rdi, rax
0x140008e85  mov     [rsp+118h+var_50], rax
0x140008e8d  test    rax, rax
0x140008e90  jnz     short loc_140008EA5
0x140008e92  mov     ebx, 0C000009Ah
0x140008e97  mov     [rsp+118h+var_C8], ebx
0x140008e9b  mov     r14, qword ptr [rsp+118h+Size+4]
0x140008ea0  jmp     loc_1400094F8
0x140008ea5  mov     r8, rbx; Size
0x140008ea8  mov     rdx, r15; Src
0x140008eab  mov     rcx, rdi; void *
0x140008eae  call    memmove
0x140008eb3  movzx   ecx, word ptr [rdi]
0x140008eb6  mov     r14d, 10h
0x140008ebc  cmp     cx, r14w
0x140008ec0  jb      loc_1400094C5
0x140008ec6  movzx   eax, word ptr [rdi+2]
0x140008eca  cmp     cx, ax
0x140008ecd  ja      loc_1400094C5
0x140008ed3  cmp     ax, r14w
0x140008ed7  jb      loc_1400094BA
0x140008edd  movzx   eax, ax
0x140008ee0  movzx   r9d, word ptr [rdi+4]
0x140008ee5  lea     ecx, [r9+rax]
0x140008ee9  cmp     ecx, eax
0x140008eeb  jbe     loc_1400094BA
0x140008ef1  movzx   eax, word ptr [rdi+6]
0x140008ef5  cmp     ecx, eax
0x140008ef7  ja      loc_1400094BA
0x140008efd  movzx   ecx, word ptr [rdi+0Ah]
0x140008f01  lea     edx, [rcx+rax]
0x140008f04  cmp     edx, eax
0x140008f06  jbe     loc_1400094AF
0x140008f0c  movzx   r8d, word ptr [rdi+0Ch]
0x140008f11  cmp     edx, r8d
0x140008f14  ja      loc_1400094AF
0x140008f1a  xor     edx, edx
0x140008f1c  mov     eax, ecx
0x140008f1e  div     r9d
0x140008f21  test    edx, edx
0x140008f23  jz      short loc_140008F47
0x140008f25  mov     r8d, 457h
0x140008f2b  mov     r9d, 0C000000Dh
0x140008f31  mov     ebx, r9d
0x140008f34  mov     [rsp+118h+var_C8], ebx
0x140008f38  mov     edx, 9
0x140008f3d  call    EfspTraceLogAssert
0x140008f42  jmp     loc_140008E9B
0x140008f47  cmp     [rdi+8], cx
0x140008f4b  jbe     short loc_140008F55
0x140008f4d  mov     r8d, 45Dh
0x140008f53  jmp     short loc_140008F2B
0x140008f55  movzx   eax, word ptr [rdi+0Eh]
0x140008f59  lea     edx, [rax+r8]
0x140008f5d  cmp     edx, r8d
0x140008f60  jbe     loc_1400094A4
0x140008f66  cmp     edx, ebx
0x140008f68  ja      loc_1400094A4
0x140008f6e  mov     r10d, 14h
0x140008f74  mov     [rsp+118h+var_B4], r10d
0x140008f79  mov     [rsp+118h+var_C8], 0
0x140008f81  lea     eax, [r9+14h]
0x140008f85  or      r15d, 0FFFFFFFFh
0x140008f89  mov     edx, r15d
0x140008f8c  cmp     eax, r10d
0x140008f8f  cmovnb  edx, eax
0x140008f92  mov     [rsp+118h+var_B0], edx
0x140008f96  mov     [rsp+118h+var_B4], edx
0x140008f9a  sbb     ebx, ebx
0x140008f9c  mov     r8d, 0C0000095h
0x140008fa2  and     ebx, r8d
0x140008fa5  mov     [rsp+118h+var_C8], ebx
0x140008fa9  cmp     eax, r10d
0x140008fac  jnb     short loc_140008FBC
0x140008fae  mov     r9d, ebx
0x140008fb1  mov     r8d, 480h
0x140008fb7  jmp     loc_140008F38
0x140008fbc  lea     eax, [rcx+rdx]
0x140008fbf  cmp     eax, edx
0x140008fc1  jb      short loc_140008FD2
0x140008fc3  mov     r15d, eax
0x140008fc6  mov     [rsp+118h+var_B0], eax
0x140008fca  mov     [rsp+118h+var_B4], eax
0x140008fce  xor     ebx, ebx
0x140008fd0  jmp     short loc_140008FDF
0x140008fd2  mov     [rsp+118h+var_B0], r15d
0x140008fd7  mov     [rsp+118h+var_B4], r15d
0x140008fdc  mov     ebx, r8d
0x140008fdf  mov     [rsp+118h+var_C8], ebx
0x140008fe3  test    ebx, ebx
0x140008fe5  jns     short loc_140008FF5
0x140008fe7  mov     r9d, ebx
0x140008fea  mov     r8d, 487h
0x140008ff0  jmp     loc_140008F38
0x140008ff5  mov     edx, r15d
0x140008ff8  mov     r8d, esi
0x140008ffb  mov     ecx, 40h ; '@'
0x140009000  call    cs:__imp_ExAllocatePool2
0x140009007  nop     dword ptr [rax+rax+00h]
0x14000900c  mov     rbx, rax
0x14000900f  mov     [rsp+118h+pbInput], rax
0x140009017  test    rax, rax
0x14000901a  jz      loc_140008E92
0x140009020  mov     [rax], r14d
0x140009023  mov     rax, [rsp+118h+arg_20]
0x14000902b  movups  xmm0, xmmword ptr [rax]
0x14000902e  movdqu  xmmword ptr [rbx+4], xmm0
0x140009033  movzx   r8d, word ptr [rdi+4]; Size
0x140009038  movzx   edx, word ptr [rdi+2]
0x14000903c  add     rdx, rdi; Src
0x14000903f  lea     rcx, [rbx+14h]; void *
0x140009043  call    memmove
0x140009048  movzx   r8d, word ptr [rdi+0Ah]; Size
0x14000904d  movzx   edx, word ptr [rdi+6]
0x140009051  add     rdx, rdi; Src
0x140009054  movzx   ecx, word ptr [rdi+4]
0x140009058  add     rcx, 14h
0x14000905c  add     rcx, rbx; void *
0x14000905f  call    memmove
0x140009064  mov     [rsp+118h+dwFlags], 0; dwFlags
0x14000906c  lea     rax, [rsp+118h+var_60]
0x140009074  mov     [rsp+118h+pcbResult], rax; pcbResult
0x140009079  mov     r9d, 4; cbOutput
0x14000907f  lea     r8, [rsp+118h+pbOutput]; pbOutput
0x140009087  lea     rdx, pszProperty; "HashDigestLength"
0x14000908e  mov     rcx, cs:hObject; hObject
0x140009095  call    cs:__imp_BCryptGetProperty
0x14000909c  nop     dword ptr [rax+rax+00h]
0x1400090a1  mov     ebx, eax
0x1400090a3  mov     [rsp+118h+var_C8], eax
0x1400090a7  test    eax, eax
0x1400090a9  js      loc_140008E9B
0x1400090af  mov     edx, [rsp+118h+pbOutput]
0x1400090b6  mov     r8d, esi
0x1400090b9  mov     ecx, 40h ; '@'
0x1400090be  call    cs:__imp_ExAllocatePool2
0x1400090c5  nop     dword ptr [rax+rax+00h]
0x1400090ca  mov     [rsp+118h+var_80], rax
0x1400090d2  test    rax, rax
0x1400090d5  jz      loc_140008E92
0x1400090db  mov     r14, qword ptr [rsp+118h+Size+4]
0x1400090e0  mov     [rsp+118h+pcbResult], r14; __int64
0x1400090e5  mov     r9d, 19h
0x1400090eb  lea     r8, aDplwrapAuthHma; "DplWrap-Auth-HMAC-SHA256"
0x1400090f2  mov     edx, [rsp+118h+cbSecret]; cbSecret
0x1400090f9  mov     rcx, [rsp+118h+pbSecret]; pbSecret
0x140009101  call    DplWrapDeriveKey
0x140009106  mov     ebx, eax
0x140009108  mov     [rsp+118h+var_C8], eax
0x14000910c  test    eax, eax
0x14000910e  js      loc_1400094F8
0x140009114  mov     edx, cs:cbHashObject
0x14000911a  mov     r8d, esi
0x14000911d  mov     ecx, 40h ; '@'
0x140009122  call    cs:__imp_ExAllocatePool2
0x140009129  nop     dword ptr [rax+rax+00h]
0x14000912e  mov     [rsp+118h+var_70], rax
0x140009136  test    rax, rax
0x140009139  jz      loc_140008E35
0x14000913f  mov     [rsp+118h+var_E8], 0; dwFlags
0x140009147  mov     [rsp+118h+dwFlags], r13d; cbSecret
0x14000914c  mov     [rsp+118h+pcbResult], r14; pbSecret
0x140009151  mov     r9d, cs:cbHashObject; cbHashObject
0x140009158  mov     r8, rax; pbHashObject
0x14000915b  lea     rdx, [rsp+118h+phHash]; phHash
0x140009163  mov     rcx, cs:hObject; hAlgorithm
0x14000916a  call    cs:__imp_BCryptCreateHash
0x140009171  nop     dword ptr [rax+rax+00h]
0x140009176  mov     ebx, eax
0x140009178  mov     [rsp+118h+var_C8], eax
0x14000917c  test    eax, eax
0x14000917e  js      loc_1400094F8
0x140009184  xor     r9d, r9d; dwFlags
0x140009187  mov     r8d, r15d; cbInput
0x14000918a  mov     rdx, [rsp+118h+pbInput]; pbInput
0x140009192  mov     rcx, [rsp+118h+phHash]; hHash
0x14000919a  call    cs:__imp_BCryptHashData
0x1400091a1  nop     dword ptr [rax+rax+00h]
0x1400091a6  mov     ebx, eax
0x1400091a8  mov     [rsp+118h+var_C8], eax
0x1400091ac  test    eax, eax
0x1400091ae  js      loc_1400094F8
0x1400091b4  xor     r9d, r9d; dwFlags
0x1400091b7  mov     r8d, [rsp+118h+pbOutput]; cbOutput
0x1400091bf  mov     r15, [rsp+118h+var_80]
0x1400091c7  mov     rdx, r15; pbOutput
0x1400091ca  mov     rcx, [rsp+118h+phHash]; hHash
0x1400091d2  call    cs:__imp_BCryptFinishHash
0x1400091d9  nop     dword ptr [rax+rax+00h]
0x1400091de  mov     ebx, eax
0x1400091e0  mov     [rsp+118h+var_C8], eax
0x1400091e4  mov     rax, r13
0x1400091e7  mov     [rsp+118h+var_40], rax
0x1400091ef  mov     rcx, r14
0x1400091f2  mov     [rsp+118h+var_48], rcx
0x1400091fa  test    rax, rax
0x1400091fd  jz      short loc_14000921A
0x1400091ff  mov     byte ptr [rcx], 0
0x140009202  inc     rcx
0x140009205  mov     [rsp+118h+var_48], rcx
0x14000920d  dec     rax
0x140009210  mov     [rsp+118h+var_40], rax
0x140009218  jmp     short loc_1400091FA
0x14000921a  test    ebx, ebx
0x14000921c  js      loc_1400094F8
0x140009222  movzx   eax, word ptr [rdi+0Eh]
0x140009226  cmp     [rsp+118h+pbOutput], eax
0x14000922d  jnz     loc_140009486
0x140009233  mov     r8d, [rsp+118h+pbOutput]; Size
0x14000923b  movzx   edx, word ptr [rdi+0Ch]
0x14000923f  add     rdx, rdi; Buf2
0x140009242  mov     rcx, r15; Buf1
0x140009245  call    memcmp
0x14000924a  test    eax, eax
0x14000924c  jnz     loc_140009486
0x140009252  movzx   eax, word ptr [rdi+8]
0x140009256  mov     rdx, [rsp+118h+arg_38]
0x14000925e  mov     ecx, [rdx]
0x140009260  cmp     ecx, eax
0x140009262  jnb     short loc_14000927B
  ... truncated ...
```
