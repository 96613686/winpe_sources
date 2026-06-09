# DplWrapProtect

- ea: `0x1400083b0`
- end: `0x140008d1f`
- name: `DplWrapProtect`
- size: `2415`
- prototype: `__int64 __fastcall(UCHAR *, ULONG, void *, unsigned int, void *, unsigned int, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000972c`
- `0x14004fca0`

## callees

- `0x1400080e4`
- `0x1400083b0`
- `0x140009a30`
- `0x140009a58`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008beb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ced`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d53e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d577`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d63e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d677`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008beb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ced`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d53e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d577`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d63e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d677`
- `ntoskrnl!ExAllocatePool2` at `0x1400084dc`
- `ntoskrnl!ExAllocatePool2` at `0x140008516`
- `ntoskrnl!ExAllocatePool2` at `0x14000870c`
- `ntoskrnl!ExAllocatePool2` at `0x1400088af`
- `ntoskrnl!ExAllocatePool2` at `0x140008a7a`
- `ntoskrnl!ExAllocatePool2` at `0x1400084dc`
- `ntoskrnl!ExAllocatePool2` at `0x140008516`
- `ntoskrnl!ExAllocatePool2` at `0x14000870c`
- `ntoskrnl!ExAllocatePool2` at `0x1400088af`
- `ntoskrnl!ExAllocatePool2` at `0x140008a7a`
- `ksecdd!BCryptGenRandom` at `0x14000884e`
- `ksecdd!BCryptGenRandom` at `0x14000884e`
- `ksecdd!BCryptGetProperty` at `0x140008573`
- `ksecdd!BCryptGetProperty` at `0x140008573`
- `ksecdd!BCryptEncrypt` at `0x1400089d3`
- `ksecdd!BCryptEncrypt` at `0x1400089d3`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x1400088f7`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x1400088f7`
- `ksecdd!BCryptCreateHash` at `0x140008acc`
- `ksecdd!BCryptCreateHash` at `0x140008acc`
- `ksecdd!BCryptHashData` at `0x140008af7`
- `ksecdd!BCryptHashData` at `0x140008af7`
- `ksecdd!BCryptDestroyHash` at `0x140008c86`
- `ksecdd!BCryptDestroyHash` at `0x14000d5ff`
- `ksecdd!BCryptDestroyHash` at `0x140008c86`
- `ksecdd!BCryptDestroyHash` at `0x14000d5ff`
- `ksecdd!BCryptFinishHash` at `0x140008b29`
- `ksecdd!BCryptFinishHash` at `0x140008b29`
- `ksecdd!BCryptDestroyKey` at `0x140008c29`
- `ksecdd!BCryptDestroyKey` at `0x14000d59a`
- `ksecdd!BCryptDestroyKey` at `0x140008c29`
- `ksecdd!BCryptDestroyKey` at `0x14000d59a`

## pseudocode

```c
__int64 __fastcall DplWrapProtect(
        UCHAR *a1,
        ULONG a2,
        void *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        __int64 a7,
        unsigned int *a8)
{
  size_t v8; // r12
  UCHAR *v9; // r13
  ULONG v10; // edi
  __int64 v11; // r14
  UCHAR *Pool2; // r8
  signed int Property; // ebx
  PUCHAR v14; // r15
  UCHAR *v15; // r12
  int v16; // edx
  __int64 v17; // rcx
  unsigned int v18; // r9d
  ULONG v19; // eax
  __int64 v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // r10d
  unsigned int v23; // r11d
  int v24; // eax
  int v25; // eax
  USHORT *v26; // rdx
  USHORT *v27; // r9
  unsigned __int16 *v28; // r9
  UCHAR *v29; // rbx
  void *v30; // rax
  __int64 v31; // rax
  UCHAR *v32; // rcx
  ULONG cbOutput; // r8d
  size_t v34; // r8
  UCHAR *v35; // r12
  unsigned int v36; // eax
  __int64 v37; // rbx
  UCHAR *v38; // rax
  __int64 v39; // rax
  UCHAR *v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rcx
  UCHAR *v43; // rax
  UCHAR *v44; // rax
  PVOID v45; // r8
  __int64 v46; // rcx
  _BYTE *v47; // rax
  __int64 v48; // rcx
  UCHAR *v49; // rax
  __int64 v50; // rcx
  PUCHAR v51; // rax
  UCHAR *pbSecret; // [rsp+58h] [rbp-110h]
  PUCHAR v54; // [rsp+68h] [rbp-100h]
  ULONG ulOperand; // [rsp+70h] [rbp-F8h] BYREF
  int v56; // [rsp+74h] [rbp-F4h]
  UCHAR pbOutput[4]; // [rsp+78h] [rbp-F0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+80h] [rbp-E8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+88h] [rbp-E0h] BYREF
  unsigned int Size; // [rsp+90h] [rbp-D8h]
  ULONG Size_4; // [rsp+94h] [rbp-D4h]
  PVOID P; // [rsp+98h] [rbp-D0h]
  ULONG pcbResult; // [rsp+A0h] [rbp-C8h] BYREF
  unsigned int v64; // [rsp+A4h] [rbp-C4h]
  UCHAR *v65; // [rsp+A8h] [rbp-C0h]
  PUCHAR pbInput; // [rsp+B0h] [rbp-B8h]
  UCHAR *v67; // [rsp+B8h] [rbp-B0h]
  PUCHAR v68; // [rsp+C0h] [rbp-A8h]
  unsigned int *v69; // [rsp+C8h] [rbp-A0h]
  void *Src; // [rsp+D0h] [rbp-98h]
  UCHAR *v71; // [rsp+D8h] [rbp-90h]
  __int64 v72; // [rsp+E0h] [rbp-88h]
  size_t v73; // [rsp+E8h] [rbp-80h]
  void *v74; // [rsp+F0h] [rbp-78h]
  PUCHAR v75; // [rsp+F8h] [rbp-70h]
  UCHAR *v76; // [rsp+100h] [rbp-68h]
  __int64 v77; // [rsp+108h] [rbp-60h]
  UCHAR pbIV[16]; // [rsp+110h] [rbp-58h] BYREF

  v8 = a4;
  Src = a3;
  Size_4 = a2;
  v68 = a1;
  v74 = a5;
  Size = a6;
  v69 = a8;
  *(_OWORD *)pbIV = 0;
  pbSecret = 0;
  v9 = 0;
  v65 = 0;
  phKey = 0;
  P = 0;
  ulOperand = 0;
  phHash = 0;
  v54 = 0;
  v10 = 0;
  v56 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( !a1 || !a2 )
  {
    v41 = 497;
    goto LABEL_83;
  }
  if ( !a3 || !a4 )
  {
    v41 = 504;
    goto LABEL_83;
  }
  if ( !a5 || !a6 || !a7 || !a8 )
  {
    v41 = 513;
LABEL_83:
    Property = -1073741811;
    EfspTraceLogAssert(a8, 9, v41);
    v11 = 32;
    goto LABEL_14;
  }
  v11 = 32;
  Pool2 = (UCHAR *)ExAllocatePool2(64, 32, 1265854021);
  pbSecret = Pool2;
  if ( !Pool2 )
  {
    Property = -1073741670;
LABEL_11:
    v14 = v54;
    v15 = 0;
    goto LABEL_88;
  }
  v9 = (UCHAR *)ExAllocatePool2(64, 32, 1265854021);
  v65 = v9;
  if ( !v9 )
  {
LABEL_13:
    Property = -1073741670;
LABEL_14:
    v14 = v54;
    goto LABEL_86;
  }
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_14;
  v17 = 0;
  v16 = v8 & 0xF;
  v18 = v8 + (v16 != 0 ? 16 - v16 : 0);
  if ( v18 < (unsigned int)v8 )
  {
    v18 = -1;
    ulOperand = -1;
    Property = -1073741675;
    v19 = -1;
  }
  else
  {
    ulOperand = v8 + (v16 != 0 ? 16 - v16 : 0);
    Property = 0;
    v19 = ulOperand;
  }
  if ( Property < 0 )
  {
    v20 = 576;
LABEL_21:
    EfspTraceLogAssert(v17, 9, v20);
    goto LABEL_14;
  }
  if ( (unsigned int)v8 > v19 )
    v19 = v8;
  v21 = v19 + 32;
  v22 = -1;
  if ( v21 >= 0x20 )
    v22 = v21;
  Property = v21 < 0x20 ? 0xC0000095 : 0;
  if ( v21 < 0x20 )
  {
    v20 = 607;
    goto LABEL_21;
  }
  v17 = v22 + *(_DWORD *)pbOutput;
  v23 = -1;
  if ( (unsigned int)v17 >= v22 )
    v23 = v22 + *(_DWORD *)pbOutput;
  v64 = v23;
  Property = (unsigned int)v17 < v22 ? 0xC0000095 : 0;
  if ( (unsigned int)v17 < v22 )
  {
    v20 = 614;
    goto LABEL_21;
  }
  v10 = -1;
  if ( Size < 0xFFFFFFFC )
    v10 = Size + 4;
  v56 = v10;
  Property = Size >= 0xFFFFFFFC ? 0xC0000095 : 0;
  if ( Size + 4 < 4 )
  {
    v20 = 635;
    goto LABEL_21;
  }
  v24 = v10 + 16;
  if ( v10 + 16 < v10 )
  {
    v10 = -1;
    v56 = -1;
    Property = -1073741675;
  }
  else
  {
    v10 += 16;
    v56 = v24;
    Property = 0;
  }
  if ( Property < 0 )
  {
    v20 = 642;
    goto LABEL_21;
  }
  v25 = v10 + v18;
  if ( v10 + v18 < v10 )
  {
    v10 = -1;
    v56 = -1;
    Property = -1073741675;
  }
  else
  {
    v10 += v18;
    v56 = v25;
    Property = 0;
  }
  if ( Property < 0 )
  {
    v20 = 649;
    goto LABEL_21;
  }
  if ( v23 > *v69 )
  {
    if ( *v69 )
      Property = -1073741789;
    *v69 = v23;
    goto LABEL_14;
  }
  v54 = (PUCHAR)ExAllocatePool2(64, v10, 1265854021);
  if ( !v54 )
    goto LABEL_13;
  *(_DWORD *)a7 = 1048592;
  *(_WORD *)(a7 + 4) = 16;
  Property = RtlUShortAdd(0x10u, 0x10u, (USHORT *)(a7 + 6));
  if ( Property < 0 )
  {
    v20 = 703;
    goto LABEL_21;
  }
  Property = RtlULongToUShort(v8, (USHORT *)(a7 + 8));
  if ( Property < 0 )
  {
    v20 = 710;
    goto LABEL_21;
  }
  Property = RtlULongToUShort(ulOperand, (USHORT *)(a7 + 10));
  if ( Property < 0 )
  {
    v20 = 717;
    goto LABEL_21;
  }
  Property = RtlUShortAdd(*v27, *v26, (USHORT *)(a7 + 12));
  if ( Property < 0 )
  {
    v20 = 724;
    goto LABEL_21;
  }
  Property = RtlULongToUShort(*(ULONG *)pbOutput, (USHORT *)(a7 + 14));
  if ( Property < 0 )
  {
    v20 = 731;
    goto LABEL_21;
  }
  v67 = (UCHAR *)(a7 + *(unsigned __int16 *)(a7 + 2));
  v29 = v67;
  pbInput = (PUCHAR)(a7 + *v28);
  v75 = (PUCHAR)(a7 + *(unsigned __int16 *)(a7 + 12));
  v73 = v8;
  memmove(pbInput, Src, v8);
  Property = BCryptGenRandom(0, v29, 0x10u, 2u);
  if ( Property < 0 )
    goto LABEL_14;
  Property = DplWrapDeriveKey(v68, Size_4, "DplWrap-Enc-AES-CBC", 0x14u, (__int64)pbSecret);
  if ( Property < 0 )
    goto LABEL_14;
  v30 = (void *)ExAllocatePool2(64, dword_1400178CC, 1265854021);
  P = v30;
  if ( !v30 )
    goto LABEL_13;
  Property = BCryptGenerateSymmetricKey(qword_1400178C0, &phKey, (PUCHAR)v30, dword_1400178CC, pbSecret, 0x20u, 0);
  v31 = 32;
  v72 = 32;
  Pool2 = pbSecret;
  v32 = pbSecret;
  v71 = pbSecret;
  while ( v31 )
  {
    *v32++ = 0;
    v71 = v32;
    v72 = --v31;
  }
  if ( Property < 0 )
    goto LABEL_11;
  cbOutput = ulOperand;
  if ( ulOperand <= (unsigned int)v8 )
  {
    v35 = pbInput;
  }
  else
  {
    v34 = ulOperand - (unsigned int)v8;
    v35 = pbInput;
    memset(&pbInput[v73], 0, v34);
    cbOutput = ulOperand;
  }
  *(_OWORD *)pbIV = *(_OWORD *)v67;
  Property = BCryptEncrypt(phKey, v35, cbOutput, 0, pbIV, 0x10u, v35, cbOutput, &ulOperand, 0);
  v14 = v54;
  if ( Property >= 0 )
  {
    v36 = Size;
    *(_DWORD *)v54 = Size;
    v37 = v36;
    memmove(v54 + 4, v74, v36);
    *(_OWORD *)&v54[v37 + 4] = *(_OWORD *)v67;
    memmove(&v54[v37 + 20], v35, ulOperand);
    Property = DplWrapDeriveKey(v68, Size_4, "DplWrap-Auth-HMAC-SHA256", 0x19u, (__int64)v9);
    if ( Property >= 0 )
    {
      v38 = (UCHAR *)ExAllocatePool2(64, cbHashObject, 1265854021);
      v15 = v38;
      if ( v38 )
      {
        Property = BCryptCreateHash(hObject, &phHash, v38, cbHashObject, v9, 0x20u, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, v54, v10, 0);
          if ( Property >= 0 )
          {
            Property = BCryptFinishHash(phHash, v75, *(ULONG *)pbOutput, 0);
            v39 = 32;
            v77 = 32;
            v40 = v9;
            v76 = v9;
            while ( v39 )
            {
              *v40++ = 0;
              v76 = v40;
              v77 = --v39;
            }
            if ( Property >= 0 )
              *v69 = v64;
          }
        }
      }
      else
      {
        Property = -1073741670;
      }
      goto LABEL_87;
    }
  }
LABEL_86:
  v15 = 0;
LABEL_87:
  Pool2 = pbSecret;
LABEL_88:
  if ( Pool2 )
  {
    v42 = 32;
    v43 = Pool2;
    do
    {
      *v43++ = 0;
      --v42;
    }
    while ( v42 );
    ExFreePoolWithTag(Pool2, 0x4B736645u);
  }
  if ( v9 )
  {
    v44 = v9;
    do
    {
      *v44++ = 0;
      --v11;
    }
    while ( v11 );
    ExFreePoolWithTag(v9, 0x4B736645u);
  }
  if ( phKey )
  {
    BCryptDestroyKey(phKey);
    phKey = 0;
  }
  v45 = P;
  if ( P )
  {
    v46 = dword_1400178CC;
    v47 = P;
    if ( dword_1400178CC )
    {
      do
      {
        *v47++ = 0;
        --v46;
      }
      while ( v46 );
    }
    ExFreePoolWithTag(v45, 0x4B736645u);
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( v15 )
  {
    v48 = cbHashObject;
    v49 = v15;
    if ( cbHashObject )
    {
      do
      {
        *v49++ = 0;
        --v48;
      }
      while ( v48 );
    }
    ExFreePoolWithTag(v15, 0x4B736645u);
  }
  if ( v14 )
  {
    v50 = v10;
    v51 = v14;
    if ( v10 )
    {
      do
      {
        *v51++ = 0;
        --v50;
      }
      while ( v50 );
    }
    ExFreePoolWithTag(v14, 0x4B736645u);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400083b0  push    rbx
0x1400083b2  push    rsi
0x1400083b3  push    rdi
0x1400083b4  push    r12
0x1400083b6  push    r13
0x1400083b8  push    r14
0x1400083ba  push    r15
0x1400083bc  sub     rsp, 130h
0x1400083c3  mov     rax, cs:__security_cookie
0x1400083ca  xor     rax, rsp
0x1400083cd  mov     [rsp+168h+var_48], rax
0x1400083d5  mov     r12d, r9d
0x1400083d8  mov     [rsp+168h+Src], r8
0x1400083e0  mov     r10d, edx
0x1400083e3  mov     dword ptr [rsp+168h+Size+4], edx
0x1400083ea  mov     r9, rcx
0x1400083ed  mov     [rsp+168h+var_A8], rcx
0x1400083f5  mov     r15, [rsp+168h+arg_30]
0x1400083fd  mov     r11, [rsp+168h+arg_20]
0x140008405  mov     [rsp+168h+var_78], r11
0x14000840d  mov     edx, [rsp+168h+arg_28]
0x140008414  mov     dword ptr [rsp+168h+Size], edx
0x14000841b  mov     rcx, [rsp+168h+arg_38]
0x140008423  mov     [rsp+168h+var_A0], rcx
0x14000842b  xorps   xmm0, xmm0
0x14000842e  movups  xmmword ptr [rsp+168h+pbIV], xmm0
0x140008436  xor     ebx, ebx
0x140008438  mov     [rsp+168h+pbSecret], rbx
0x14000843d  mov     r13d, ebx
0x140008440  mov     [rsp+168h+var_C0], rbx
0x140008448  mov     [rsp+168h+phKey], rbx
0x140008450  mov     [rsp+168h+P], rbx
0x140008458  mov     [rsp+168h+ulOperand], ebx
0x14000845c  mov     [rsp+168h+phHash], rbx
0x140008464  mov     [rsp+168h+var_108], rbx
0x140008469  mov     eax, ebx
0x14000846b  mov     [rsp+168h+var_100], rbx
0x140008470  mov     edi, ebx
0x140008472  mov     [rsp+168h+var_F4], ebx
0x140008476  mov     dword ptr [rsp+168h+pbOutput], ebx
0x14000847a  mov     [rsp+168h+var_C8], ebx
0x140008481  test    r9, r9
0x140008484  jz      loc_140008BBD
0x14000848a  test    r10d, r10d
0x14000848d  jz      loc_140008BBD
0x140008493  test    r8, r8
0x140008496  jz      loc_140008BB5
0x14000849c  test    r12d, r12d
0x14000849f  jz      loc_140008BB5
0x1400084a5  test    r11, r11
0x1400084a8  jz      loc_140008B88
0x1400084ae  test    edx, edx
0x1400084b0  jz      loc_140008B88
0x1400084b6  test    r15, r15
0x1400084b9  jz      loc_140008B88
0x1400084bf  test    rcx, rcx
0x1400084c2  jz      loc_140008B88
0x1400084c8  mov     esi, 4B736645h
0x1400084cd  mov     r8d, esi
0x1400084d0  lea     r14d, [rbx+20h]
0x1400084d4  mov     edx, r14d
0x1400084d7  lea     ebx, [rax+40h]
0x1400084da  mov     ecx, ebx
0x1400084dc  call    cs:__imp_ExAllocatePool2
0x1400084e3  nop     dword ptr [rax+rax+00h]
0x1400084e8  mov     r8, rax
0x1400084eb  mov     [rsp+168h+pbSecret], rax
0x1400084f0  test    rax, rax
0x1400084f3  jnz     short loc_14000850D
0x1400084f5  mov     ebx, 0C000009Ah
0x1400084fa  mov     [rsp+168h+var_118], ebx
0x1400084fe  mov     r15, [rsp+168h+var_100]
0x140008503  mov     r12, [rsp+168h+var_108]
0x140008508  jmp     loc_140008BCF
0x14000850d  mov     r8d, esi
0x140008510  mov     rdx, r14
0x140008513  mov     rcx, rbx
0x140008516  call    cs:__imp_ExAllocatePool2
0x14000851d  nop     dword ptr [rax+rax+00h]
0x140008522  mov     r13, rax
0x140008525  mov     [rsp+168h+var_C0], rax
0x14000852d  test    rax, rax
0x140008530  jnz     short loc_140008545
0x140008532  mov     ebx, 0C000009Ah
0x140008537  mov     [rsp+168h+var_118], ebx
0x14000853b  mov     r15, [rsp+168h+var_100]
0x140008540  jmp     loc_140008BC5
0x140008545  mov     [rsp+168h+dwFlags], 0; dwFlags
0x14000854d  lea     rax, [rsp+168h+var_C8]
0x140008555  mov     [rsp+168h+pcbResult], rax; pcbResult
0x14000855a  mov     r9d, 4; cbOutput
0x140008560  lea     r8, [rsp+168h+pbOutput]; pbOutput
0x140008565  lea     rdx, pszProperty; "HashDigestLength"
0x14000856c  mov     rcx, cs:hObject; hObject
0x140008573  call    cs:__imp_BCryptGetProperty
0x14000857a  nop     dword ptr [rax+rax+00h]
0x14000857f  mov     ebx, eax
0x140008581  mov     [rsp+168h+var_118], eax
0x140008585  test    eax, eax
0x140008587  js      short loc_14000853B
0x140008589  mov     edx, r12d
0x14000858c  and     edx, 0Fh
0x14000858f  mov     ecx, 0
0x140008594  cmovnz  ebx, ecx
0x140008597  mov     [rsp+168h+var_118], ebx
0x14000859b  lea     r9d, [rcx+10h]
0x14000859f  sub     r9d, edx
0x1400085a2  neg     edx
0x1400085a4  sbb     eax, eax
0x1400085a6  and     r9d, eax
0x1400085a9  add     r9d, r12d
0x1400085ac  mov     r8d, 0C0000095h
0x1400085b2  cmp     r9d, r12d
0x1400085b5  jb      short loc_1400085C6
0x1400085b7  mov     [rsp+168h+ulOperand], r9d
0x1400085bc  xor     ebx, ebx
0x1400085be  mov     eax, r9d
0x1400085c1  or      edx, 0FFFFFFFFh
0x1400085c4  jmp     short loc_1400085D5
0x1400085c6  or      edx, 0FFFFFFFFh
0x1400085c9  mov     r9d, edx
0x1400085cc  mov     [rsp+168h+ulOperand], edx
0x1400085d0  mov     ebx, r8d
0x1400085d3  mov     eax, edx
0x1400085d5  mov     [rsp+168h+var_118], ebx
0x1400085d9  test    ebx, ebx
0x1400085db  jns     short loc_1400085F5
0x1400085dd  mov     r8d, 240h
0x1400085e3  mov     r9d, ebx
0x1400085e6  mov     edx, 9
0x1400085eb  call    EfspTraceLogAssert
0x1400085f0  jmp     loc_14000853B
0x1400085f5  mov     [rsp+168h+var_118], ecx
0x1400085f9  cmp     r12d, eax
0x1400085fc  cmova   eax, r12d
0x140008600  add     eax, r14d
0x140008603  mov     r10d, edx
0x140008606  cmp     eax, r14d
0x140008609  cmovnb  r10d, eax
0x14000860d  sbb     ebx, ebx
0x14000860f  and     ebx, r8d
0x140008612  mov     [rsp+168h+var_118], ebx
0x140008616  cmp     eax, r14d
0x140008619  jnb     short loc_140008623
0x14000861b  mov     r8d, 25Fh
0x140008621  jmp     short loc_1400085E3
0x140008623  mov     eax, dword ptr [rsp+168h+pbOutput]
0x140008627  lea     ecx, [r10+rax]
0x14000862b  mov     r11d, edx
0x14000862e  cmp     ecx, r10d
0x140008631  cmovnb  r11d, ecx
0x140008635  mov     [rsp+168h+var_C4], r11d
0x14000863d  sbb     ebx, ebx
0x14000863f  and     ebx, r8d
0x140008642  mov     [rsp+168h+var_118], ebx
0x140008646  cmp     ecx, r10d
0x140008649  jnb     short loc_140008653
0x14000864b  mov     r8d, 266h
0x140008651  jmp     short loc_1400085E3
0x140008653  mov     eax, dword ptr [rsp+168h+Size]
0x14000865a  add     eax, 4
0x14000865d  mov     edi, edx
0x14000865f  cmp     eax, 4
0x140008662  cmovnb  edi, eax
0x140008665  mov     [rsp+168h+var_F4], edi
0x140008669  sbb     ebx, ebx
0x14000866b  and     ebx, r8d
0x14000866e  mov     [rsp+168h+var_118], ebx
0x140008672  cmp     eax, 4
0x140008675  jnb     short loc_140008682
0x140008677  mov     r8d, 27Bh
0x14000867d  jmp     loc_1400085E3
0x140008682  lea     eax, [rdi+10h]
0x140008685  cmp     eax, edi
0x140008687  jb      short loc_140008693
0x140008689  mov     edi, eax
0x14000868b  mov     [rsp+168h+var_F4], eax
0x14000868f  xor     ebx, ebx
0x140008691  jmp     short loc_14000869C
0x140008693  mov     edi, edx
0x140008695  mov     [rsp+168h+var_F4], edx
0x140008699  mov     ebx, r8d
0x14000869c  mov     [rsp+168h+var_118], ebx
0x1400086a0  test    ebx, ebx
0x1400086a2  jns     short loc_1400086AF
0x1400086a4  mov     r8d, 282h
0x1400086aa  jmp     loc_1400085E3
0x1400086af  lea     eax, [rdi+r9]
0x1400086b3  cmp     eax, edi
0x1400086b5  jb      short loc_1400086C1
0x1400086b7  mov     edi, eax
0x1400086b9  mov     [rsp+168h+var_F4], eax
0x1400086bd  xor     ebx, ebx
0x1400086bf  jmp     short loc_1400086CA
0x1400086c1  mov     edi, edx
0x1400086c3  mov     [rsp+168h+var_F4], edx
0x1400086c7  mov     ebx, r8d
0x1400086ca  mov     [rsp+168h+var_118], ebx
0x1400086ce  test    ebx, ebx
0x1400086d0  jns     short loc_1400086DD
0x1400086d2  mov     r8d, 289h
0x1400086d8  jmp     loc_1400085E3
0x1400086dd  mov     rcx, [rsp+168h+var_A0]
0x1400086e5  mov     eax, [rcx]
0x1400086e7  cmp     r11d, eax
0x1400086ea  jbe     short loc_140008702
0x1400086ec  mov     edx, 0C0000023h
0x1400086f1  test    eax, eax
0x1400086f3  cmovnz  ebx, edx
0x1400086f6  mov     [rsp+168h+var_118], ebx
0x1400086fa  mov     [rcx], r11d
0x1400086fd  jmp     loc_14000853B
0x140008702  mov     edx, edi
0x140008704  mov     r8d, esi
0x140008707  mov     ecx, 40h ; '@'
0x14000870c  call    cs:__imp_ExAllocatePool2
0x140008713  nop     dword ptr [rax+rax+00h]
0x140008718  mov     [rsp+168h+var_100], rax
0x14000871d  test    rax, rax
0x140008720  jz      loc_140008532
0x140008726  mov     eax, 10h
0x14000872b  mov     dword ptr [r15], 100010h
0x140008732  mov     [r15+4], ax
0x140008737  lea     r9, [r15+6]
0x14000873b  mov     edx, eax; usAddend
0x14000873d  mov     ecx, eax; usAugend
0x14000873f  mov     r8, r9; pusResult
0x140008742  call    RtlUShortAdd
0x140008747  mov     ebx, eax
0x140008749  mov     [rsp+168h+var_118], eax
0x14000874d  test    eax, eax
0x14000874f  jns     short loc_14000875F
0x140008751  mov     r9d, eax
0x140008754  mov     r8d, 2BFh
0x14000875a  jmp     loc_1400085E6
0x14000875f  lea     rdx, [r15+8]; pusResult
0x140008763  mov     ecx, r12d; ulOperand
0x140008766  call    RtlULongToUShort
0x14000876b  mov     ebx, eax
0x14000876d  mov     [rsp+168h+var_118], eax
0x140008771  test    eax, eax
0x140008773  jns     short loc_140008783
0x140008775  mov     r9d, eax
0x140008778  mov     r8d, 2C6h
0x14000877e  jmp     loc_1400085E6
0x140008783  lea     rdx, [r15+0Ah]; pusResult
0x140008787  mov     ecx, [rsp+168h+ulOperand]; ulOperand
0x14000878b  call    RtlULongToUShort
0x140008790  mov     ebx, eax
0x140008792  mov     [rsp+168h+var_118], eax
0x140008796  test    eax, eax
0x140008798  jns     short loc_1400087A8
0x14000879a  mov     r9d, eax
0x14000879d  mov     r8d, 2CDh
0x1400087a3  jmp     loc_1400085E6
0x1400087a8  lea     r8, [r15+0Ch]; pusResult
0x1400087ac  movzx   edx, word ptr [rdx]; usAddend
0x1400087af  movzx   ecx, word ptr [r9]; usAugend
0x1400087b3  call    RtlUShortAdd
0x1400087b8  mov     ebx, eax
0x1400087ba  mov     [rsp+168h+var_118], eax
0x1400087be  test    eax, eax
0x1400087c0  jns     short loc_1400087D0
0x1400087c2  mov     r9d, eax
0x1400087c5  mov     r8d, 2D4h
0x1400087cb  jmp     loc_1400085E6
0x1400087d0  lea     rdx, [r15+0Eh]; pusResult
0x1400087d4  mov     ecx, dword ptr [rsp+168h+pbOutput]; ulOperand
0x1400087d8  call    RtlULongToUShort
0x1400087dd  mov     ebx, eax
0x1400087df  mov     [rsp+168h+var_118], eax
0x1400087e3  test    eax, eax
0x1400087e5  jns     short loc_1400087F5
0x1400087e7  mov     r9d, eax
0x1400087ea  mov     r8d, 2DBh
0x1400087f0  jmp     loc_1400085E6
0x1400087f5  movzx   ebx, word ptr [r15+2]
0x1400087fa  add     rbx, r15
0x1400087fd  mov     [rsp+168h+var_B0], rbx
0x140008805  movzx   eax, word ptr [r9]
0x140008809  add     rax, r15
0x14000880c  mov     [rsp+168h+pbInput], rax
0x140008814  movzx   ecx, word ptr [r15+0Ch]
0x140008819  add     rcx, r15
0x14000881c  mov     [rsp+168h+var_70], rcx
0x140008824  mov     [rsp+168h+var_80], r12
0x14000882c  mov     r8, r12; Size
0x14000882f  mov     rdx, [rsp+168h+Src]; Src
0x140008837  mov     rcx, rax; void *
0x14000883a  call    memmove
0x14000883f  mov     r9d, 2; dwFlags
0x140008845  lea     r8d, [r9+0Eh]; cbBuffer
0x140008849  mov     rdx, rbx; pbBuffer
0x14000884c  xor     ecx, ecx; hAlgorithm
0x14000884e  call    cs:__imp_BCryptGenRandom
0x140008855  nop     dword ptr [rax+rax+00h]
0x14000885a  mov     ebx, eax
0x14000885c  mov     [rsp+168h+var_118], eax
0x140008860  test    eax, eax
0x140008862  js      loc_14000853B
  ... truncated ...
```
