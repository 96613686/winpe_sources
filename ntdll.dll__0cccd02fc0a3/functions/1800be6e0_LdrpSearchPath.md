# LdrpSearchPath

- ea: `0x1800be6e0`
- end: `0x1800becb4`
- name: `LdrpSearchPath`
- size: `1492`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029fc0`
- `0x18002c970`
- `0x1800be2e0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18001d490`
- `0x18001eb80`
- `0x180027b80`
- `0x180029590`
- `0x18002ad90`
- `0x18002aec0`
- `0x180041810`
- `0x1800be6e0`
- `0x1800becbc`
- `0x1800bf2dc`
- `0x1800c3810`
- `0x18010243c`
- `0x180162000`

## string_xrefs

- `0x1800be74f`: `DLL name: %wZ\n`
- `0x1800be765`: `LdrpSearchPath`
- `0x1800be79c`: `LdrpSearchPath`
- `0x1800be9b2`: `LdrpSearchPath`
- `0x1800be9e0`: `LdrpSearchPath`

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
0x1800be6e0  mov     [rsp-8+arg_10], rbx
0x1800be6e5  push    rbp
0x1800be6e6  push    rsi
0x1800be6e7  push    rdi
0x1800be6e8  push    r12
0x1800be6ea  push    r13
0x1800be6ec  push    r14
0x1800be6ee  push    r15
0x1800be6f0  lea     rbp, [rsp-7]
0x1800be6f5  sub     rsp, 0C0h
0x1800be6fc  mov     rax, cs:__security_cookie
0x1800be703  xor     rax, rsp
0x1800be706  mov     [rbp+37h+var_38], rax
0x1800be70a  mov     rax, [rbp+37h+arg_20]
0x1800be70e  mov     r13, r9
0x1800be711  mov     [rbp+37h+var_98], rax
0x1800be715  mov     sil, r8b
0x1800be718  mov     rax, [rbp+37h+arg_30]
0x1800be71c  mov     r14, rdx
0x1800be71f  mov     [rsp+0F0h+var_B8], rax
0x1800be724  mov     rbx, rcx
0x1800be727  mov     rax, [rbp+37h+arg_28]
0x1800be72b  xorps   xmm0, xmm0
0x1800be72e  mov     [rbp+37h+var_88], rax
0x1800be732  mov     edx, 4BCh; int
0x1800be737  mov     rax, [rbp+37h+arg_38]
0x1800be73b  mov     [rbp+37h+var_78], rax
0x1800be73f  mov     rax, [rbp+37h+arg_40]
0x1800be746  mov     qword ptr [rsp+0F0h+ArgList], rcx; ArgList
0x1800be74b  mov     [rbp+37h+var_70], rax
0x1800be74f  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800be756  mov     [rbp+37h+var_80], r9
0x1800be75a  mov     r9d, 3; int
0x1800be760  mov     [rsp+0F0h+var_C0], r8b
0x1800be765  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800be76c  mov     [rbp+37h+var_A0], rcx
0x1800be770  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800be777  mov     [rsp+0F0h+Format], rax; Format
0x1800be77c  movups  xmmword ptr [rbp+37h+var_B0], xmm0
0x1800be780  call    LdrpLogInternal
0x1800be785  lea     rax, aWz_0; "%wZ\n"
0x1800be78c  mov     qword ptr [rsp+0F0h+ArgList], rbx; ArgList
0x1800be791  mov     r9d, 5; int
0x1800be797  mov     [rsp+0F0h+Format], rax; Format
0x1800be79c  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800be7a3  mov     edx, 4BDh; int
0x1800be7a8  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800be7af  call    LdrpLogInternal
0x1800be7b4  mov     rax, [r14]
0x1800be7b7  xor     edi, edi
0x1800be7b9  test    rax, rax
0x1800be7bc  jnz     short loc_1800BE7D4
0x1800be7be  mov     rcx, r14
0x1800be7c1  call    LdrpComputeLazyDllPath
0x1800be7c6  mov     ebx, eax
0x1800be7c8  test    eax, eax
0x1800be7ca  js      loc_1800BE99C
0x1800be7d0  mov     rbx, [rbp+37h+var_A0]
0x1800be7d4  mov     r8d, edi
0x1800be7d7  test    r13, r13
0x1800be7da  jnz     loc_1800BEA2B
0x1800be7e0  mov     rdx, [r14+10h]
0x1800be7e4  test    rdx, rdx
0x1800be7e7  jz      loc_1800BEACC
0x1800be7ed  mov     rcx, rdx
0x1800be7f0  cmp     [rcx], di
0x1800be7f3  jz      short loc_1800BE828
0x1800be7f5  mov     r9, rcx
0x1800be7f8  cmp     word ptr [rcx], 3Bh ; ';'
0x1800be7fc  jz      short loc_1800BE807
0x1800be7fe  add     rcx, 2
0x1800be802  cmp     [rcx], di
0x1800be805  jnz     short loc_1800BE7F8
0x1800be807  mov     eax, ecx
0x1800be809  sub     eax, r9d
0x1800be80c  cmp     eax, r8d
0x1800be80f  cmova   r8d, eax
0x1800be813  movzx   eax, word ptr [rcx]
0x1800be816  cmp     ax, 3Bh ; ';'
0x1800be81a  jnz     short loc_1800BE823
0x1800be81c  add     rcx, 2
0x1800be820  movzx   eax, word ptr [rcx]
0x1800be823  test    ax, ax
0x1800be826  jnz     short loc_1800BE7F5
0x1800be828  cmp     rdx, [r14+10h]
0x1800be82c  jz      loc_1800BEB03
0x1800be832  movzx   edx, word ptr [rbx]
0x1800be835  lea     rcx, [rbp+37h+var_B0]
0x1800be839  add     r8d, 2
0x1800be83d  add     edx, r8d
0x1800be840  call    LdrpAllocateUnicodeString
0x1800be845  xor     r9d, r9d
0x1800be848  mov     ebx, eax
0x1800be84a  test    eax, eax
0x1800be84c  js      loc_1800BE99C
0x1800be852  mov     rdx, qword ptr [rbp+37h+var_B0+8]
0x1800be856  mov     r12d, r9d
0x1800be859  mov     [rbp+37h+var_90], rdx
0x1800be85d  test    r13, r13
0x1800be860  jz      loc_1800BEA4B
0x1800be866  mov     r15, [r13+0]
0x1800be86a  test    r15, r15
0x1800be86d  jz      loc_1800BEA4B
0x1800be873  mov     rdi, [r13+8]
0x1800be877  mov     r8d, 5Ch ; '\'
0x1800be87d  cmp     [rdi], r9w
0x1800be881  jz      loc_1800BE94E
0x1800be887  cmp     word ptr [rdi], 3Bh ; ';'
0x1800be88b  jz      loc_1800BEB18
0x1800be891  cmp     rdi, [r14+8]
0x1800be895  mov     rax, rdx
0x1800be898  setz    sil
0x1800be89c  movzx   ecx, word ptr [rdi]
0x1800be89f  cmp     cx, 3Bh ; ';'
0x1800be8a3  jz      short loc_1800BE8B6
0x1800be8a5  mov     [rax], cx
0x1800be8a8  add     rdi, 2
0x1800be8ac  add     rax, 2
0x1800be8b0  cmp     [rdi], r9w
0x1800be8b4  jnz     short loc_1800BE89C
0x1800be8b6  cmp     word ptr [rdi], 3Bh ; ';'
0x1800be8ba  jz      loc_1800BEA22
0x1800be8c0  cmp     rax, rdx
0x1800be8c3  jz      loc_1800BEA41
0x1800be8c9  cmp     [rax-2], r8w
0x1800be8ce  jz      short loc_1800BE8DF
0x1800be8d0  cmp     word ptr [rax-2], 2Fh ; '/'
0x1800be8d5  jz      short loc_1800BE8DF
0x1800be8d7  mov     [rax], r8w
0x1800be8db  add     rax, 2
0x1800be8df  sub     ax, dx
0x1800be8e2  lea     rcx, [rbp+37h+var_B0]
0x1800be8e6  mov     rdx, [rbp+37h+var_A0]
0x1800be8ea  mov     word ptr [rbp+37h+var_B0], ax
0x1800be8ee  call    RtlAppendUnicodeStringToString
0x1800be8f3  mov     r13, [rsp+0F0h+var_B8]
0x1800be8f8  lea     rcx, [rbp+37h+var_B0]; ArgList
0x1800be8fc  mov     r8, [rbp+37h+var_88]
0x1800be900  mov     r9, r13
0x1800be903  mov     rdx, [rbp+37h+var_98]
0x1800be907  mov     dword ptr [rsp+0F0h+Format], 0; int
0x1800be90f  call    LdrpResolveDllName
0x1800be914  xor     r9d, r9d
0x1800be917  mov     ebx, eax
0x1800be919  test    sil, sil
0x1800be91c  jnz     loc_1800BEB21
0x1800be922  test    eax, eax
0x1800be924  jns     short loc_1800BE962
0x1800be926  cmp     eax, 0C000006Dh
0x1800be92b  jz      short loc_1800BE938
0x1800be92d  cmp     eax, 0C0000135h
0x1800be932  jnz     loc_1800BEAE8
0x1800be938  mov     rcx, [rbp+37h+var_98]
0x1800be93c  mov     rdx, [rbp+37h+var_90]
0x1800be940  mov     sil, [rsp+0F0h+var_C0]
0x1800be945  mov     [rcx], r9w
0x1800be949  jmp     loc_1800BE877
0x1800be94e  cmp     r15, [r14+10h]
0x1800be952  jz      loc_1800BEAD4
0x1800be958  mov     ebx, 0C0000135h
0x1800be95d  mov     r13, [rsp+0F0h+var_B8]
0x1800be962  test    r12, r12
0x1800be965  jnz     loc_1800BEBF1
0x1800be96b  mov     rcx, qword ptr [rbp+37h+var_B0+8]
0x1800be96f  test    rcx, rcx
0x1800be972  jz      short loc_1800BE980
0x1800be974  call    RtlpSysVolFree
0x1800be979  xor     r9d, r9d
0x1800be97c  mov     qword ptr [rbp+37h+var_B0+8], r9
0x1800be980  mov     dword ptr [rbp+37h+var_B0], 0
0x1800be987  test    ebx, ebx
0x1800be989  jns     loc_1800BEA5F
0x1800be98f  mov     rsi, [rbp+37h+var_70]
0x1800be993  test    rsi, rsi
0x1800be996  jnz     loc_1800BEA8B
0x1800be99c  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x1800be9a3  mov     dword ptr [rsp+0F0h+ArgList], ebx; ArgList
0x1800be9a7  mov     r9d, 4; int
0x1800be9ad  mov     [rsp+0F0h+Format], rax; Format
0x1800be9b2  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800be9b9  mov     edx, 5FEh; int
0x1800be9be  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800be9c5  call    LdrpLogInternal
0x1800be9ca  lea     rax, asc_180175AB4; "%x\n"
0x1800be9d1  mov     dword ptr [rsp+0F0h+ArgList], ebx; ArgList
0x1800be9d5  mov     r9d, 6; int
0x1800be9db  mov     [rsp+0F0h+Format], rax; Format
0x1800be9e0  lea     r8, aLdrpsearchpath; "LdrpSearchPath"
0x1800be9e7  mov     edx, 5FFh; int
0x1800be9ec  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x1800be9f3  call    LdrpLogInternal
0x1800be9f8  mov     eax, ebx
0x1800be9fa  mov     rcx, [rbp+37h+var_38]
0x1800be9fe  xor     rcx, rsp; StackCookie
0x1800bea01  call    __security_check_cookie
0x1800bea06  mov     rbx, [rsp+0F0h+arg_10]
0x1800bea0e  add     rsp, 0C0h
0x1800bea15  pop     r15
0x1800bea17  pop     r14
0x1800bea19  pop     r13
0x1800bea1b  pop     r12
0x1800bea1d  pop     rdi
0x1800bea1e  pop     rsi
0x1800bea1f  pop     rbp
0x1800bea20  retn
0x1800bea22  add     rdi, 2
0x1800bea26  jmp     loc_1800BE8C0
0x1800bea2b  mov     rdx, [r13+0]
0x1800bea2f  test    rdx, rdx
0x1800bea32  jz      loc_1800BE7E0
0x1800bea38  mov     rcx, [r13+8]
0x1800bea3c  jmp     loc_1800BE7F0
0x1800bea41  mov     sil, [rsp+0F0h+var_C0]
0x1800bea46  jmp     loc_1800BE87D
0x1800bea4b  mov     r15, [r14+10h]
0x1800bea4f  test    r15, r15
0x1800bea52  jnz     short loc_1800BEA57
0x1800bea54  mov     r15, [r14]
0x1800bea57  mov     rdi, r15
0x1800bea5a  jmp     loc_1800BE877
0x1800bea5f  mov     r13, [rbp+37h+var_80]
0x1800bea63  test    r13, r13
0x1800bea66  jz      short loc_1800BEA70
0x1800bea68  mov     [r13+0], r15
0x1800bea6c  mov     [r13+8], rdi
0x1800bea70  mov     rcx, [rbp+37h+var_78]
0x1800bea74  test    rcx, rcx
0x1800bea77  jz      loc_1800BE98F
0x1800bea7d  cmp     r15, [r14+10h]
0x1800bea81  setz    al
0x1800bea84  mov     [rcx], al
0x1800bea86  jmp     loc_1800BE98F
0x1800bea8b  call    LdrpIsSecurityEtwLoggingEnabled
0x1800bea90  test    al, al
0x1800bea92  jz      loc_1800BE99C
0x1800bea98  movzx   r9d, word ptr [r14+70h]
0x1800bea9d  xor     edx, edx
0x1800bea9f  xor     r8d, r8d
0x1800beaa2  test    r9d, r9d
0x1800beaa5  jz      short loc_1800BEAC4
0x1800beaa7  cmp     rdi, [r14+rdx*8+40h]
0x1800beaac  jbe     short loc_1800BEAC4
0x1800beaae  mov     ecx, [r14+rdx*4+28h]
0x1800beab3  mov     eax, 10h
0x1800beab8  shl     eax, cl
0x1800beaba  inc     edx
0x1800beabc  or      r8d, eax
0x1800beabf  cmp     edx, r9d
0x1800beac2  jb      short loc_1800BEAA7
0x1800beac4  mov     [rsi], r8d
0x1800beac7  jmp     loc_1800BE99C
0x1800beacc  mov     rdx, [r14]
0x1800beacf  jmp     loc_1800BE7ED
0x1800bead4  test    sil, sil
0x1800bead7  jnz     loc_1800BE958
0x1800beadd  mov     r15, [r14]
0x1800beae0  mov     rdi, r15
0x1800beae3  jmp     loc_1800BE87D
0x1800beae8  cmp     eax, 0C0000022h
0x1800beaed  jz      loc_1800BE938
0x1800beaf3  cmp     eax, 0C0000043h
0x1800beaf8  jnz     loc_1800BE962
0x1800beafe  jmp     loc_1800BE938
0x1800beb03  test    sil, sil
0x1800beb06  jnz     loc_1800BE832
0x1800beb0c  mov     rdx, [r14]
0x1800beb0f  mov     [rbp+37h+var_90], rdx
0x1800beb13  jmp     loc_1800BE7ED
0x1800beb18  add     rdi, 2
0x1800beb1c  jmp     loc_1800BE87D
0x1800beb21  test    eax, eax
0x1800beb23  js      loc_1800BE926
0x1800beb29  call    RtlpLookupSafeCurDirList
0x1800beb2e  mov     r13, rax
0x1800beb31  test    rax, rax
0x1800beb34  jz      short loc_1800BEB7E
0x1800beb36  mov     rsi, [rax]
0x1800beb39  cmp     rsi, r13
0x1800beb3c  jz      short loc_1800BEB7E
0x1800beb3e  mov     r10, [rsp+0F0h+var_B8]
0x1800beb43  movzx   ecx, word ptr [rsi+10h]
0x1800beb47  shr     cx, 1
0x1800beb4a  movzx   eax, word ptr [r10]
0x1800beb4e  shr     ax, 1
0x1800beb51  cmp     ax, cx
0x1800beb54  jbe     short loc_1800BEB79
0x1800beb56  mov     r8, [rsi+18h]
0x1800beb5a  movzx   edx, cx
0x1800beb5d  mov     rcx, [r10+8]
0x1800beb61  mov     r9d, edx
0x1800beb64  mov     byte ptr [rsp+0F0h+Format], 1
0x1800beb69  call    RtlCompareUnicodeStrings
0x1800beb6e  xor     r9d, r9d
0x1800beb71  test    eax, eax
0x1800beb73  jz      loc_1800BE95D
0x1800beb79  mov     rsi, [rsi]
0x1800beb7c  jmp     short loc_1800BEB39
0x1800beb7e  mov     edx, cs:NtdllBaseTag
0x1800beb84  mov     r13, [rsp+0F0h+var_B8]
0x1800beb89  add     edx, 40000h
  ... truncated ...
```
