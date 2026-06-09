# LdrpSearchPath

- ea: `0x1800c29c0`
- end: `0x1800c2f94`
- name: `LdrpSearchPath`
- size: `1492`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029eb0`
- `0x18002bc70`
- `0x1800c25c0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18001d490`
- `0x18001eb80`
- `0x180027a70`
- `0x180029480`
- `0x18002a530`
- `0x180036fa0`
- `0x18004f360`
- `0x1800c29c0`
- `0x1800c2f9c`
- `0x1800c35bc`
- `0x1800c7ac0`
- `0x18010308c`
- `0x180162810`

## string_xrefs

- `0x1800c2a2f`: `DLL name: %wZ\n`
- `0x1800c2a45`: `LdrpSearchPath`
- `0x1800c2a7c`: `LdrpSearchPath`
- `0x1800c2c92`: `LdrpSearchPath`
- `0x1800c2cc0`: `LdrpSearchPath`

## pseudocode

```c
__int64 __fastcall LdrpSearchPath(
        unsigned __int16 *ArgList,
        __int64 a2,
        char a3,
        __int16 **a4,
        __m128i *a5,
        __int64 a6,
        unsigned __int16 *a7,
        bool *a8,
        __int64 a9)
{
  char v10; // si
  unsigned __int16 *v12; // rbx
  int v13; // ebx
  unsigned int v14; // r8d
  __int16 *v15; // rdx
  __int16 *i; // rcx
  int v17; // r9d
  __int16 v18; // ax
  int UnicodeString; // eax
  __int64 v20; // r9
  __int16 *v21; // rdx
  unsigned __int16 *v22; // r12
  __int16 *v23; // r15
  __int16 *v24; // rdi
  __int64 v25; // r8
  __int16 *v26; // rax
  bool v27; // si
  unsigned __int16 *v28; // r13
  int v29; // eax
  __int64 v30; // rcx
  bool *v31; // rcx
  _DWORD *v32; // rsi
  __int16 **v34; // r13
  __int64 v35; // rdx
  int k; // r8d
  int v37; // eax
  __int64 *v38; // rax
  __int64 *v39; // r13
  __int64 *j; // rsi
  unsigned __int16 v41; // cx
  int v42; // eax
  __int64 Heap_0; // rax
  int v44; // eax
  __int64 *v45; // rdx
  int Format; // [rsp+20h] [rbp-99h]
  char v48[16]; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v49; // [rsp+50h] [rbp-69h]
  __m128i *v50; // [rsp+58h] [rbp-61h]
  __int16 *v51; // [rsp+60h] [rbp-59h]
  __int64 v52; // [rsp+68h] [rbp-51h]
  __int16 **v53; // [rsp+70h] [rbp-49h]
  bool *v54; // [rsp+78h] [rbp-41h]
  __int64 v55; // [rsp+80h] [rbp-39h]
  __int64 v56; // [rsp+88h] [rbp-31h] BYREF
  int v57; // [rsp+90h] [rbp-29h]
  int v58; // [rsp+94h] [rbp-25h]
  __int64 v59; // [rsp+98h] [rbp-21h]
  int v60; // [rsp+A0h] [rbp-19h]
  int v61; // [rsp+A4h] [rbp-15h]
  __int64 v62; // [rsp+A8h] [rbp-11h]
  int v63; // [rsp+B0h] [rbp-9h]
  int v64; // [rsp+B4h] [rbp-5h]

  v50 = a5;
  v10 = a3;
  v12 = ArgList;
  v52 = a6;
  v54 = a8;
  v55 = a9;
  v53 = a4;
  v49 = ArgList;
  *(_OWORD *)v48 = 0;
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1212, (int)"LdrpSearchPath", 3, "DLL name: %wZ\n", (char)ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1213, (int)"LdrpSearchPath", 5, "%wZ\n", (char)v12);
  if ( !*(_QWORD *)a2 )
  {
    v13 = LdrpComputeLazyDllPath(a2);
    if ( v13 < 0 )
      goto LABEL_47;
    v12 = v49;
  }
  v14 = 0;
  if ( !a4 || (v15 = *a4) == 0 )
  {
    v15 = *(__int16 **)(a2 + 16);
    if ( !v15 )
      v15 = *(__int16 **)a2;
    goto LABEL_7;
  }
  for ( i = a4[1]; ; i = v15 )
  {
    if ( *i )
    {
      do
      {
        v17 = (int)i;
        do
        {
          if ( *i == 59 )
            break;
          ++i;
        }
        while ( *i );
        if ( (int)i - v17 > v14 )
          v14 = (_DWORD)i - v17;
        v18 = *i;
        if ( *i == 59 )
          v18 = *++i;
      }
      while ( v18 );
    }
    if ( v15 != *(__int16 **)(a2 + 16) || v10 )
      break;
    v15 = *(__int16 **)a2;
    v51 = *(__int16 **)a2;
LABEL_7:
    ;
  }
  UnicodeString = LdrpAllocateUnicodeString(v48, v14 + 2 + *v12);
  v20 = 0;
  v13 = UnicodeString;
  if ( UnicodeString >= 0 )
  {
    v21 = *(__int16 **)&v48[8];
    v22 = 0;
    v51 = *(__int16 **)&v48[8];
    if ( a4 && (v23 = *a4) != 0 )
    {
      v24 = a4[1];
    }
    else
    {
      v23 = *(__int16 **)(a2 + 16);
      if ( !v23 )
        v23 = *(__int16 **)a2;
      v24 = v23;
    }
    while ( 2 )
    {
      v25 = 92;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( !*v24 )
          {
            if ( v23 != *(__int16 **)(a2 + 16) || v10 )
            {
              v13 = -1073741515;
LABEL_41:
              v28 = a7;
              goto LABEL_42;
            }
            v23 = *(__int16 **)a2;
            v24 = *(__int16 **)a2;
          }
          if ( *v24 != 59 )
            break;
          ++v24;
        }
        v26 = v21;
        v27 = v24 == *(__int16 **)(a2 + 8);
        do
        {
          if ( *v24 == 59 )
            break;
          *v26++ = *v24++;
        }
        while ( *v24 );
        if ( *v24 == 59 )
          ++v24;
        if ( v26 != v21 )
          break;
        v10 = a3;
      }
      if ( *(v26 - 1) != 92 && *(v26 - 1) != 47 )
      {
        *v26 = 92;
        LOWORD(v26) = (_WORD)v26 + 2;
      }
      *(_WORD *)v48 = (_WORD)v26 - (_WORD)v21;
      RtlAppendUnicodeStringToString(v48, v49);
      v28 = a7;
      v29 = LdrpResolveDllName((__m128i *)v48, v50, v52, a7, 0);
      v20 = 0;
      v13 = v29;
      if ( v27 )
      {
        if ( v29 < 0 )
          goto LABEL_36;
        v38 = (__int64 *)RtlpLookupSafeCurDirList(v30, v21, v25, 0);
        v39 = v38;
        if ( v38 )
        {
          for ( j = (__int64 *)*v38; j != v39; j = (__int64 *)*j )
          {
            v41 = *((_WORD *)j + 8) >> 1;
            if ( (unsigned __int16)(*a7 >> 1) > v41 )
            {
              LOBYTE(Format) = 1;
              v42 = RtlCompareUnicodeStrings(*((_QWORD *)a7 + 1), v41, j[3], v41, Format);
              v20 = 0;
              if ( !v42 )
                goto LABEL_41;
            }
          }
        }
        Heap_0 = RtlAllocateHeap_0(LdrpHeap, (unsigned int)(NtdllBaseTag + 0x40000), *a7 + 18LL);
        v20 = 0;
        v22 = (unsigned __int16 *)Heap_0;
        if ( Heap_0 )
        {
          *(_WORD *)Heap_0 = 0;
          *(_WORD *)(Heap_0 + 2) = *a7;
          *(_QWORD *)(Heap_0 + 8) = Heap_0 + 16;
          RtlCopyUnicodeString(Heap_0, a7);
          v20 = 0;
          *(_WORD *)(*((_QWORD *)v22 + 1) + 2 * ((unsigned __int64)*a7 >> 1)) = 0;
        }
LABEL_38:
        v21 = v51;
        v10 = a3;
        v50->m128i_i16[0] = 0;
        continue;
      }
      break;
    }
    if ( v29 >= 0 )
      goto LABEL_42;
LABEL_36:
    if ( v29 == -1073741715 || v29 == -1073741515 || v29 == -1073741790 || v29 == -1073741757 )
      goto LABEL_38;
LABEL_42:
    if ( v22 )
    {
      if ( v13 < 0
        || (LOBYTE(Format) = 1,
            (unsigned int)RtlCompareUnicodeStrings(
                            *((_QWORD *)v28 + 1),
                            (unsigned __int64)*v28 >> 1,
                            *((_QWORD *)v22 + 1),
                            (unsigned __int64)*v22 >> 1,
                            Format)) )
      {
        v58 = 0;
        v61 = 0;
        v56 = *(_QWORD *)(LdrpImageEntry + 80);
        v57 = *(unsigned __int16 *)(LdrpImageEntry + 72) + 2;
        v59 = *((_QWORD *)v22 + 1);
        v60 = *v22 + 2;
        if ( v13 >= 0 )
        {
          v62 = *((_QWORD *)v28 + 1);
          v44 = *v28;
          v64 = 0;
          v63 = v44 + 2;
        }
        v45 = CurDirDllLoadFailureWarning;
        if ( v13 < 0 )
          v45 = CurDirDllLoadFailureError;
        EtwEventWriteNoRegistration(UserLoaderGuid, v45, (unsigned int)((v13 >> 31) + 3), &v56);
      }
      RtlFreeHeap_0(LdrpHeap, 0, v22);
    }
    v31 = *(bool **)&v48[8];
    if ( *(_QWORD *)&v48[8] )
    {
      RtlpSysVolFree(*(_QWORD *)&v48[8]);
      v20 = 0;
      *(_QWORD *)&v48[8] = 0;
    }
    *(_DWORD *)v48 = 0;
    if ( v13 >= 0 )
    {
      v34 = v53;
      if ( v53 )
      {
        *v53 = v23;
        v34[1] = v24;
      }
      v31 = v54;
      if ( v54 )
        *v54 = v23 == *(__int16 **)(a2 + 16);
    }
    v32 = (_DWORD *)v55;
    if ( v55 && (unsigned __int8)LdrpIsSecurityEtwLoggingEnabled(v31, v21, v25, v20) )
    {
      v35 = 0;
      for ( k = 0; (unsigned int)v35 < *(unsigned __int16 *)(a2 + 112); k |= v37 )
      {
        if ( (unsigned __int64)v24 <= *(_QWORD *)(a2 + 8 * v35 + 64) )
          break;
        v37 = 16 << *(_DWORD *)(a2 + 4 * v35 + 40);
        v35 = (unsigned int)(v35 + 1);
      }
      *v32 = k;
    }
  }
LABEL_47:
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1534, (int)"LdrpSearchPath", 4, "Status: 0x%08lx\n", v13);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1535, (int)"LdrpSearchPath", 6, "%x\n", v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800c29c0  mov     [rsp-8+arg_10], rbx
0x1800c29c5  push    rbp
0x1800c29c6  push    rsi
0x1800c29c7  push    rdi
0x1800c29c8  push    r12
0x1800c29ca  push    r13
0x1800c29cc  push    r14
0x1800c29ce  push    r15
0x1800c29d0  lea     rbp, [rsp-7]
0x1800c29d5  sub     rsp, 0C0h
0x1800c29dc  mov     rax, cs:__security_cookie
0x1800c29e3  xor     rax, rsp
0x1800c29e6  mov     [rbp+37h+var_38], rax
0x1800c29ea  mov     rax, [rbp+37h+arg_20]
0x1800c29ee  mov     r13, r9
0x1800c29f1  mov     [rbp+37h+var_98], rax
0x1800c29f5  mov     sil, r8b
0x1800c29f8  mov     rax, [rbp+37h+arg_30]
0x1800c29fc  mov     r14, rdx
0x1800c29ff  mov     [rsp+0F0h+var_B8], rax
0x1800c2a04  mov     rbx, rcx
0x1800c2a07  mov     rax, [rbp+37h+arg_28]
0x1800c2a0b  xorps   xmm0, xmm0
0x1800c2a0e  mov     [rbp+37h+var_88], rax
0x1800c2a12  mov     edx, 4BCh; int
0x1800c2a17  mov     rax, [rbp+37h+arg_38]
0x1800c2a1b  mov     [rbp+37h+var_78], rax
0x1800c2a1f  mov     rax, [rbp+37h+arg_40]
0x1800c2a26  mov     qword ptr [rsp+0F0h+ArgList], rcx; ArgList
0x1800c2a2b  mov     [rbp+37h+var_70], rax
0x1800c2a2f  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800c2a36  mov     [rbp+37h+var_80], r9
0x1800c2a3a  mov     r9d, 3; int
0x1800c2a40  mov     [rsp+0F0h+var_C0], r8b
0x1800c2a45  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800c2a4c  mov     [rbp+37h+var_A0], rcx
0x1800c2a50  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800c2a57  mov     [rsp+0F0h+Format], rax; Format
0x1800c2a5c  movups  xmmword ptr [rbp+37h+var_B0], xmm0
0x1800c2a60  call    LdrpLogInternal
0x1800c2a65  lea     rax, aWz_0; "%wZ\n"
0x1800c2a6c  mov     qword ptr [rsp+0F0h+ArgList], rbx; ArgList
0x1800c2a71  mov     r9d, 5; int
0x1800c2a77  mov     [rsp+0F0h+Format], rax; Format
0x1800c2a7c  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800c2a83  mov     edx, 4BDh; int
0x1800c2a88  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800c2a8f  call    LdrpLogInternal
0x1800c2a94  mov     rax, [r14]
0x1800c2a97  xor     edi, edi
0x1800c2a99  test    rax, rax
0x1800c2a9c  jnz     short loc_1800C2AB4
0x1800c2a9e  mov     rcx, r14
0x1800c2aa1  call    LdrpComputeLazyDllPath
0x1800c2aa6  mov     ebx, eax
0x1800c2aa8  test    eax, eax
0x1800c2aaa  js      loc_1800C2C7C
0x1800c2ab0  mov     rbx, [rbp+37h+var_A0]
0x1800c2ab4  mov     r8d, edi
0x1800c2ab7  test    r13, r13
0x1800c2aba  jnz     loc_1800C2D0B
0x1800c2ac0  mov     rdx, [r14+10h]
0x1800c2ac4  test    rdx, rdx
0x1800c2ac7  jz      loc_1800C2DAC
0x1800c2acd  mov     rcx, rdx
0x1800c2ad0  cmp     [rcx], di
0x1800c2ad3  jz      short loc_1800C2B08
0x1800c2ad5  mov     r9, rcx
0x1800c2ad8  cmp     word ptr [rcx], 3Bh ; ';'
0x1800c2adc  jz      short loc_1800C2AE7
0x1800c2ade  add     rcx, 2
0x1800c2ae2  cmp     [rcx], di
0x1800c2ae5  jnz     short loc_1800C2AD8
0x1800c2ae7  mov     eax, ecx
0x1800c2ae9  sub     eax, r9d
0x1800c2aec  cmp     eax, r8d
0x1800c2aef  cmova   r8d, eax
0x1800c2af3  movzx   eax, word ptr [rcx]
0x1800c2af6  cmp     ax, 3Bh ; ';'
0x1800c2afa  jnz     short loc_1800C2B03
0x1800c2afc  add     rcx, 2
0x1800c2b00  movzx   eax, word ptr [rcx]
0x1800c2b03  test    ax, ax
0x1800c2b06  jnz     short loc_1800C2AD5
0x1800c2b08  cmp     rdx, [r14+10h]
0x1800c2b0c  jz      loc_1800C2DE3
0x1800c2b12  movzx   edx, word ptr [rbx]
0x1800c2b15  lea     rcx, [rbp+37h+var_B0]
0x1800c2b19  add     r8d, 2
0x1800c2b1d  add     edx, r8d
0x1800c2b20  call    LdrpAllocateUnicodeString
0x1800c2b25  xor     r9d, r9d
0x1800c2b28  mov     ebx, eax
0x1800c2b2a  test    eax, eax
0x1800c2b2c  js      loc_1800C2C7C
0x1800c2b32  mov     rdx, qword ptr [rbp+37h+var_B0+8]
0x1800c2b36  mov     r12d, r9d
0x1800c2b39  mov     [rbp+37h+var_90], rdx
0x1800c2b3d  test    r13, r13
0x1800c2b40  jz      loc_1800C2D2B
0x1800c2b46  mov     r15, [r13+0]
0x1800c2b4a  test    r15, r15
0x1800c2b4d  jz      loc_1800C2D2B
0x1800c2b53  mov     rdi, [r13+8]
0x1800c2b57  mov     r8d, 5Ch ; '\'
0x1800c2b5d  cmp     [rdi], r9w
0x1800c2b61  jz      loc_1800C2C2E
0x1800c2b67  cmp     word ptr [rdi], 3Bh ; ';'
0x1800c2b6b  jz      loc_1800C2DF8
0x1800c2b71  cmp     rdi, [r14+8]
0x1800c2b75  mov     rax, rdx
0x1800c2b78  setz    sil
0x1800c2b7c  movzx   ecx, word ptr [rdi]
0x1800c2b7f  cmp     cx, 3Bh ; ';'
0x1800c2b83  jz      short loc_1800C2B96
0x1800c2b85  mov     [rax], cx
0x1800c2b88  add     rdi, 2
0x1800c2b8c  add     rax, 2
0x1800c2b90  cmp     [rdi], r9w
0x1800c2b94  jnz     short loc_1800C2B7C
0x1800c2b96  cmp     word ptr [rdi], 3Bh ; ';'
0x1800c2b9a  jz      loc_1800C2D02
0x1800c2ba0  cmp     rax, rdx
0x1800c2ba3  jz      loc_1800C2D21
0x1800c2ba9  cmp     [rax-2], r8w
0x1800c2bae  jz      short loc_1800C2BBF
0x1800c2bb0  cmp     word ptr [rax-2], 2Fh ; '/'
0x1800c2bb5  jz      short loc_1800C2BBF
0x1800c2bb7  mov     [rax], r8w
0x1800c2bbb  add     rax, 2
0x1800c2bbf  sub     ax, dx
0x1800c2bc2  lea     rcx, [rbp+37h+var_B0]
0x1800c2bc6  mov     rdx, [rbp+37h+var_A0]
0x1800c2bca  mov     word ptr [rbp+37h+var_B0], ax
0x1800c2bce  call    RtlAppendUnicodeStringToString
0x1800c2bd3  mov     r13, [rsp+0F0h+var_B8]
0x1800c2bd8  lea     rcx, [rbp+37h+var_B0]; ArgList
0x1800c2bdc  mov     r8, [rbp+37h+var_88]
0x1800c2be0  mov     r9, r13
0x1800c2be3  mov     rdx, [rbp+37h+var_98]
0x1800c2be7  mov     dword ptr [rsp+0F0h+Format], 0; int
0x1800c2bef  call    LdrpResolveDllName
0x1800c2bf4  xor     r9d, r9d
0x1800c2bf7  mov     ebx, eax
0x1800c2bf9  test    sil, sil
0x1800c2bfc  jnz     loc_1800C2E01
0x1800c2c02  test    eax, eax
0x1800c2c04  jns     short loc_1800C2C42
0x1800c2c06  cmp     eax, 0C000006Dh
0x1800c2c0b  jz      short loc_1800C2C18
0x1800c2c0d  cmp     eax, 0C0000135h
0x1800c2c12  jnz     loc_1800C2DC8
0x1800c2c18  mov     rcx, [rbp+37h+var_98]
0x1800c2c1c  mov     rdx, [rbp+37h+var_90]
0x1800c2c20  mov     sil, [rsp+0F0h+var_C0]
0x1800c2c25  mov     [rcx], r9w
0x1800c2c29  jmp     loc_1800C2B57
0x1800c2c2e  cmp     r15, [r14+10h]
0x1800c2c32  jz      loc_1800C2DB4
0x1800c2c38  mov     ebx, 0C0000135h
0x1800c2c3d  mov     r13, [rsp+0F0h+var_B8]
0x1800c2c42  test    r12, r12
0x1800c2c45  jnz     loc_1800C2ED1
0x1800c2c4b  mov     rcx, qword ptr [rbp+37h+var_B0+8]
0x1800c2c4f  test    rcx, rcx
0x1800c2c52  jz      short loc_1800C2C60
0x1800c2c54  call    RtlpSysVolFree
0x1800c2c59  xor     r9d, r9d
0x1800c2c5c  mov     qword ptr [rbp+37h+var_B0+8], r9
0x1800c2c60  mov     dword ptr [rbp+37h+var_B0], 0
0x1800c2c67  test    ebx, ebx
0x1800c2c69  jns     loc_1800C2D3F
0x1800c2c6f  mov     rsi, [rbp+37h+var_70]
0x1800c2c73  test    rsi, rsi
0x1800c2c76  jnz     loc_1800C2D6B
0x1800c2c7c  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x1800c2c83  mov     dword ptr [rsp+0F0h+ArgList], ebx; ArgList
0x1800c2c87  mov     r9d, 4; int
0x1800c2c8d  mov     [rsp+0F0h+Format], rax; Format
0x1800c2c92  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800c2c99  mov     edx, 5FEh; int
0x1800c2c9e  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800c2ca5  call    LdrpLogInternal
0x1800c2caa  lea     rax, asc_180175AB4; "%x\n"
0x1800c2cb1  mov     dword ptr [rsp+0F0h+ArgList], ebx; ArgList
0x1800c2cb5  mov     r9d, 6; int
0x1800c2cbb  mov     [rsp+0F0h+Format], rax; Format
0x1800c2cc0  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800c2cc7  mov     edx, 5FFh; int
0x1800c2ccc  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800c2cd3  call    LdrpLogInternal
0x1800c2cd8  mov     eax, ebx
0x1800c2cda  mov     rcx, [rbp+37h+var_38]
0x1800c2cde  xor     rcx, rsp; StackCookie
0x1800c2ce1  call    __security_check_cookie
0x1800c2ce6  mov     rbx, [rsp+0F0h+arg_10]
0x1800c2cee  add     rsp, 0C0h
0x1800c2cf5  pop     r15
0x1800c2cf7  pop     r14
0x1800c2cf9  pop     r13
0x1800c2cfb  pop     r12
0x1800c2cfd  pop     rdi
0x1800c2cfe  pop     rsi
0x1800c2cff  pop     rbp
0x1800c2d00  retn
0x1800c2d02  add     rdi, 2
0x1800c2d06  jmp     loc_1800C2BA0
0x1800c2d0b  mov     rdx, [r13+0]
0x1800c2d0f  test    rdx, rdx
0x1800c2d12  jz      loc_1800C2AC0
0x1800c2d18  mov     rcx, [r13+8]
0x1800c2d1c  jmp     loc_1800C2AD0
0x1800c2d21  mov     sil, [rsp+0F0h+var_C0]
0x1800c2d26  jmp     loc_1800C2B5D
0x1800c2d2b  mov     r15, [r14+10h]
0x1800c2d2f  test    r15, r15
0x1800c2d32  jnz     short loc_1800C2D37
0x1800c2d34  mov     r15, [r14]
0x1800c2d37  mov     rdi, r15
0x1800c2d3a  jmp     loc_1800C2B57
0x1800c2d3f  mov     r13, [rbp+37h+var_80]
0x1800c2d43  test    r13, r13
0x1800c2d46  jz      short loc_1800C2D50
0x1800c2d48  mov     [r13+0], r15
0x1800c2d4c  mov     [r13+8], rdi
0x1800c2d50  mov     rcx, [rbp+37h+var_78]
0x1800c2d54  test    rcx, rcx
0x1800c2d57  jz      loc_1800C2C6F
0x1800c2d5d  cmp     r15, [r14+10h]
0x1800c2d61  setz    al
0x1800c2d64  mov     [rcx], al
0x1800c2d66  jmp     loc_1800C2C6F
0x1800c2d6b  call    LdrpIsSecurityEtwLoggingEnabled
0x1800c2d70  test    al, al
0x1800c2d72  jz      loc_1800C2C7C
0x1800c2d78  movzx   r9d, word ptr [r14+70h]
0x1800c2d7d  xor     edx, edx
0x1800c2d7f  xor     r8d, r8d
0x1800c2d82  test    r9d, r9d
0x1800c2d85  jz      short loc_1800C2DA4
0x1800c2d87  cmp     rdi, [r14+rdx*8+40h]
0x1800c2d8c  jbe     short loc_1800C2DA4
0x1800c2d8e  mov     ecx, [r14+rdx*4+28h]
0x1800c2d93  mov     eax, 10h
0x1800c2d98  shl     eax, cl
0x1800c2d9a  inc     edx
0x1800c2d9c  or      r8d, eax
0x1800c2d9f  cmp     edx, r9d
0x1800c2da2  jb      short loc_1800C2D87
0x1800c2da4  mov     [rsi], r8d
0x1800c2da7  jmp     loc_1800C2C7C
0x1800c2dac  mov     rdx, [r14]
0x1800c2daf  jmp     loc_1800C2ACD
0x1800c2db4  test    sil, sil
0x1800c2db7  jnz     loc_1800C2C38
0x1800c2dbd  mov     r15, [r14]
0x1800c2dc0  mov     rdi, r15
0x1800c2dc3  jmp     loc_1800C2B5D
0x1800c2dc8  cmp     eax, 0C0000022h
0x1800c2dcd  jz      loc_1800C2C18
0x1800c2dd3  cmp     eax, 0C0000043h
0x1800c2dd8  jnz     loc_1800C2C42
0x1800c2dde  jmp     loc_1800C2C18
0x1800c2de3  test    sil, sil
0x1800c2de6  jnz     loc_1800C2B12
0x1800c2dec  mov     rdx, [r14]
0x1800c2def  mov     [rbp+37h+var_90], rdx
0x1800c2df3  jmp     loc_1800C2ACD
0x1800c2df8  add     rdi, 2
0x1800c2dfc  jmp     loc_1800C2B5D
0x1800c2e01  test    eax, eax
0x1800c2e03  js      loc_1800C2C06
0x1800c2e09  call    RtlpLookupSafeCurDirList
0x1800c2e0e  mov     r13, rax
0x1800c2e11  test    rax, rax
0x1800c2e14  jz      short loc_1800C2E5E
0x1800c2e16  mov     rsi, [rax]
0x1800c2e19  cmp     rsi, r13
0x1800c2e1c  jz      short loc_1800C2E5E
0x1800c2e1e  mov     r10, [rsp+0F0h+var_B8]
0x1800c2e23  movzx   ecx, word ptr [rsi+10h]
0x1800c2e27  shr     cx, 1
0x1800c2e2a  movzx   eax, word ptr [r10]
0x1800c2e2e  shr     ax, 1
0x1800c2e31  cmp     ax, cx
0x1800c2e34  jbe     short loc_1800C2E59
0x1800c2e36  mov     r8, [rsi+18h]
0x1800c2e3a  movzx   edx, cx
0x1800c2e3d  mov     rcx, [r10+8]
0x1800c2e41  mov     r9d, edx
0x1800c2e44  mov     byte ptr [rsp+0F0h+Format], 1
0x1800c2e49  call    RtlCompareUnicodeStrings
0x1800c2e4e  xor     r9d, r9d
0x1800c2e51  test    eax, eax
0x1800c2e53  jz      loc_1800C2C3D
0x1800c2e59  mov     rsi, [rsi]
0x1800c2e5c  jmp     short loc_1800C2E19
0x1800c2e5e  mov     edx, cs:NtdllBaseTag
0x1800c2e64  mov     r13, [rsp+0F0h+var_B8]
0x1800c2e69  add     edx, 40000h
  ... truncated ...
```
