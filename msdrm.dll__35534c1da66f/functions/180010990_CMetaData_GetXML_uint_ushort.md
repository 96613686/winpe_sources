# CMetaData::GetXML(uint *,ushort * *)

- ea: `0x180010990`
- end: `0x1800111f3`
- name: `?GetXML@CMetaData@@QEAAJPEAIPEAPEAG@Z`
- size: `2147`
- prototype: `__int64 __fastcall(CMetaData *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000cd4c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180010990`
- `0x180015438`
- `0x180017358`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800109eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010b3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800109eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010b3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CMetaData::GetXML(CMetaData *this, unsigned int *a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // r13
  unsigned __int16 *v6; // r12
  int v7; // edi
  unsigned __int16 *v8; // r13
  __int64 v9; // rbx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rax
  unsigned int v12; // edx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // r8
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // r8
  __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // r9
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdx
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // r15
  unsigned int v43; // r14d
  unsigned __int16 *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // rdi
  unsigned __int16 *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  unsigned __int64 v53; // rdi
  unsigned __int16 *v54; // rax
  const unsigned __int16 *v55; // rdx
  const unsigned __int16 *v56; // r14
  const unsigned __int16 *v57; // r9
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rcx
  unsigned __int64 v63; // rdi
  unsigned __int16 *v64; // rax
  __int64 v65; // rcx
  const unsigned __int16 *v66; // r8
  unsigned __int16 *v68; // [rsp+40h] [rbp-1A8h]
  unsigned __int16 *Block; // [rsp+48h] [rbp-1A0h]
  unsigned __int16 *v70; // [rsp+50h] [rbp-198h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+88h] [rbp-160h]
  unsigned __int16 v74[12]; // [rsp+A0h] [rbp-148h] BYREF
  unsigned __int16 v75[8]; // [rsp+B8h] [rbp-130h] BYREF
  __int128 v76; // [rsp+C8h] [rbp-120h]
  unsigned __int16 v77[8]; // [rsp+D8h] [rbp-110h] BYREF
  __int128 v78; // [rsp+E8h] [rbp-100h]
  __int128 v79; // [rsp+F8h] [rbp-F0h]
  unsigned __int16 v80[8]; // [rsp+108h] [rbp-E0h] BYREF
  __int128 v81; // [rsp+118h] [rbp-D0h]
  __int128 v82; // [rsp+128h] [rbp-C0h]
  int v83; // [rsp+138h] [rbp-B0h]
  unsigned __int16 v84[8]; // [rsp+140h] [rbp-A8h] BYREF
  __int128 v85; // [rsp+150h] [rbp-98h]
  __int128 v86; // [rsp+160h] [rbp-88h]
  __int128 v87; // [rsp+170h] [rbp-78h]
  _OWORD v88[2]; // [rsp+180h] [rbp-68h]

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *(_OWORD *)v84 = *(_OWORD *)L"<OBJECT%s><ID type=\"%s\">%s</ID>%s</OBJECT>";
  v85 = *(_OWORD *)L"s><ID type=\"%s\">%s</ID>%s</OBJECT>";
  v86 = *(_OWORD *)L"pe=\"%s\">%s</ID>%s</OBJECT>";
  v87 = *(_OWORD *)L"%s</ID>%s</OBJECT>";
  v88[0] = *(_OWORD *)L"s</OBJECT>";
  *(_QWORD *)((char *)v88 + 14) = *(_QWORD *)L"CT>";
  *(_OWORD *)v74 = *(_OWORD *)L" type=\"%s\"";
  *(_QWORD *)&v74[7] = *(_QWORD *)L"%s\"";
  *(_OWORD *)v75 = *(_OWORD *)L"<NAME>%s</NAME>";
  v76 = *(_OWORD *)L"</NAME>";
  *(_OWORD *)v77 = *(_OWORD *)L"<SKU type=\"%s\">%s</SKU>";
  v78 = *(_OWORD *)L"e=\"%s\">%s</SKU>";
  v79 = *(_OWORD *)L"s</SKU>";
  *(_OWORD *)v80 = *(_OWORD *)L"<METADATA>%s%s</METADATA>";
  v81 = *(_OWORD *)L"A>%s%s</METADATA>";
  v82 = *(_OWORD *)L"METADATA>";
  v83 = *(_DWORD *)L">";
  v6 = 0;
  Block = 0;
  v70 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = 0;
    goto LABEL_114;
  }
  v7 = 0;
  *a2 = 0;
  EnterCriticalSection(v5);
  v9 = *((_QWORD *)this + 16);
  LeaveCriticalSection(v5);
  if ( !v9 )
  {
    v8 = 0;
    goto LABEL_114;
  }
  if ( !**((_WORD **)this + 16) )
  {
    v7 = -2147168433;
    v8 = 0;
    goto LABEL_114;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(*((_QWORD *)this + 16) + 2 * v11) );
  if ( v11 > 0xFFFFFFD5 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(4294967253LL);
  v12 = v11 + 42;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*((_QWORD *)this + 17) + 2 * v13) );
  v14 = v12 + v13;
  if ( v14 < v12 || v14 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v14);
  if ( (unsigned int)v14 < 4 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v14);
  v15 = (unsigned int)(v14 - 4);
  v16 = *((_QWORD *)this + 20);
  if ( v16 )
  {
    v17 = (unsigned int)v15;
    v18 = v15 + 10;
    if ( v18 < v17 || v18 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v18);
    v19 = (unsigned int)v18;
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(v16 + 2 * v20) );
    v21 = (unsigned int)v18 + v20;
    if ( v19 + v20 < v19 || v21 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v21);
    if ( (unsigned int)v21 < 4 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v21);
    v15 = (unsigned int)(v21 - 4);
  }
  v22 = *((_QWORD *)this + 21);
  if ( v22 )
  {
    v23 = (unsigned int)v15;
    v24 = v15 + 15;
    if ( v24 < v23 || v24 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v24);
    v25 = (unsigned int)v24;
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(v22 + 2 * v26) );
    v27 = (unsigned int)v24 + v26;
    if ( v25 + v26 < v25 || v27 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v27);
    if ( (unsigned int)v27 < 2 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v27);
    v15 = (unsigned int)(v27 - 2);
  }
  v28 = *((_QWORD *)this + 18);
  if ( v28 )
  {
    v29 = (unsigned int)v15;
    v30 = v15 + 23;
    if ( v30 < v29 || v30 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v30);
    v31 = (unsigned int)v30;
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)(v28 + 2 * v32) );
    v33 = (unsigned int)v30 + v32;
    if ( v31 + v32 < v31 || v33 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v33);
    v34 = (unsigned int)v33;
    v35 = -1;
    do
      ++v35;
    while ( *(_WORD *)(*((_QWORD *)this + 19) + 2 * v35) );
    v36 = (unsigned int)v33 + v35;
    if ( v34 + v35 < v34 || v36 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36);
    if ( (unsigned int)v36 < 4 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36);
    v15 = (unsigned int)(v36 - 4);
  }
  v37 = *((_QWORD *)this + 22);
  if ( v37 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *(_WORD *)(v37 + 2 * v38) );
    v39 = (unsigned int)v15;
    v40 = v38 + v15;
    if ( v40 < v39 || v40 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v40);
    if ( (unsigned int)v40 < 2 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v40);
    v15 = (unsigned int)(v40 - 2);
  }
  if ( v28 || v37 )
  {
    v41 = (unsigned int)v15;
    v15 += 25LL;
    if ( v15 < v41 || v15 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
  }
  if ( (_DWORD)v15 == -1 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
  v42 = (unsigned int)(v15 + 1);
  v43 = 2 * v42;
  if ( 2 * v42 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
  if ( !a3 || !v43 )
  {
    v8 = 0;
LABEL_112:
    *a2 = v42;
    goto LABEL_114;
  }
  v44 = (unsigned __int16 *)operator new[](saturated_mul(v42, 2u));
  v6 = v44;
  if ( !v44 )
  {
    v7 = -2147024882;
    v8 = 0;
    goto LABEL_114;
  }
  memset_0(v44, 0, v43);
  v45 = *((_QWORD *)this + 20);
  if ( v45 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v74[v46] );
    v47 = -1;
    do
      ++v47;
    while ( *(_WORD *)(v45 + 2 * v47) );
    v48 = (unsigned int)(v46 + v47 + 1);
    v49 = (unsigned __int16 *)operator new[](saturated_mul(v48, 2u));
    Block = v49;
    if ( !v49 )
    {
      v7 = -2147024882;
      v8 = 0;
      goto LABEL_114;
    }
    memset_0(v49, 0, 2 * v48);
    v7 = StringCchPrintfW(Block, v48, v74, *((_QWORD *)this + 20));
    if ( v7 < 0 )
    {
      v8 = 0;
      goto LABEL_114;
    }
  }
  v50 = *((_QWORD *)this + 21);
  if ( v50 )
  {
    v51 = -1;
    do
      ++v51;
    while ( v75[v51] );
    v52 = -1;
    do
      ++v52;
    while ( *(_WORD *)(v50 + 2 * v52) );
    v53 = (unsigned int)(v51 + v52 + 1);
    v54 = (unsigned __int16 *)operator new[](saturated_mul(v53, 2u));
    v70 = v54;
    if ( !v54 )
    {
      v7 = -2147024882;
      v8 = 0;
      goto LABEL_114;
    }
    memset_0(v54, 0, 2 * v53);
    v7 = StringCchPrintfW(v70, v53, v75, *((_QWORD *)this + 21));
    if ( v7 < 0 )
    {
      v8 = 0;
      goto LABEL_114;
    }
    v55 = v70;
    v56 = &Src;
  }
  else
  {
    v56 = &Src;
    v55 = &Src;
  }
  v57 = &Src;
  if ( *((_QWORD *)this + 20) )
    v57 = Block;
  v7 = StringCchPrintfW(v6, v42, v84, v57, *((_QWORD *)this + 17), *((_QWORD *)this + 16), v55);
  if ( v7 < 0 )
  {
    v8 = 0;
    goto LABEL_114;
  }
  v59 = *((_QWORD *)this + 18);
  if ( v59 )
  {
    v60 = -1;
    do
      ++v60;
    while ( v77[v60] );
    v61 = -1;
    do
      ++v61;
    while ( *(_WORD *)(v59 + 2 * v61) );
    v62 = -1;
    do
      ++v62;
    while ( *(_WORD *)(*((_QWORD *)this + 19) + 2 * v62) );
    v63 = (unsigned int)(v61 + 1 + v60 + v62);
    v64 = (unsigned __int16 *)operator new[](saturated_mul(v63, 2u));
    v68 = v64;
    if ( !v64 )
    {
      v7 = -2147024882;
      v8 = 0;
      goto LABEL_114;
    }
    memset_0(v64, 0, 2 * v63);
    v8 = v68;
    v7 = StringCchPrintfW(v68, v63, v77, *((_QWORD *)this + 19), *((_QWORD *)this + 18));
    if ( v7 < 0 )
      goto LABEL_114;
  }
  else
  {
    v8 = 0;
  }
  if ( !*((_QWORD *)this + 18) && !*((_QWORD *)this + 22) )
    goto LABEL_137;
  v65 = -1;
  do
    ++v65;
  while ( v6[v65] );
  v66 = &Src;
  if ( v8 )
    v66 = v8;
  if ( *((_QWORD *)this + 22) )
    v56 = (const unsigned __int16 *)*((_QWORD *)this + 22);
  if ( (unsigned int)v65 > (unsigned int)v42 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v65);
  v7 = StringCchPrintfW(&v6[(unsigned int)v65], (unsigned int)(v42 - v65), v80, v56, v66);
  if ( v7 >= 0 )
  {
LABEL_137:
    do
      ++v10;
    while ( v6[v10] );
    LODWORD(v42) = v10;
    if ( v10 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v58);
    *a3 = v6;
    v6 = 0;
    goto LABEL_112;
  }
LABEL_114:
  operator delete(v6);
  operator delete(Block);
  operator delete(v70);
  operator delete(v8);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010990  push    rbx
0x180010992  push    rsi
0x180010993  push    rdi
0x180010994  push    r12
0x180010996  push    r13
0x180010998  push    r14
0x18001099a  push    r15
0x18001099c  sub     rsp, 1B0h
0x1800109a3  mov     [rsp+1E8h+var_158], 0FFFFFFFFFFFFFFFEh
0x1800109af  mov     rax, cs:__security_cookie
0x1800109b6  xor     rax, rsp
0x1800109b9  mov     [rsp+1E8h+var_40], rax
0x1800109c1  mov     [rsp+1E8h+var_188], r8
0x1800109c6  mov     rbx, rdx
0x1800109c9  mov     [rsp+1E8h+var_168], rdx
0x1800109d1  mov     rsi, rcx
0x1800109d4  lea     r13, [rcx+58h]
0x1800109d8  mov     [rsp+1E8h+lpCriticalSection], r13
0x1800109e0  mov     [rsp+1E8h+var_150], r13
0x1800109e8  mov     rcx, r13; lpCriticalSection
0x1800109eb  call    cs:__imp_EnterCriticalSection
0x1800109f1  nop
0x1800109f2  movaps  xmm0, xmmword ptr cs:aObjectSIdTypeS; "<OBJECT%s><ID type=\"%s\">%s</ID>%s</OB"...
0x1800109f9  movaps  xmmword ptr [rsp+1E8h+var_A8], xmm0
0x180010a01  movaps  xmm1, xmmword ptr cs:aObjectSIdTypeS+10h; "s><ID type=\"%s\">%s</ID>%s</OBJECT>"
0x180010a08  movaps  [rsp+1E8h+var_98], xmm1
0x180010a10  movaps  xmm0, xmmword ptr cs:aObjectSIdTypeS+20h; "pe=\"%s\">%s</ID>%s</OBJECT>"
0x180010a17  movaps  [rsp+1E8h+var_88], xmm0
0x180010a1f  movaps  xmm1, xmmword ptr cs:aObjectSIdTypeS+30h; "%s</ID>%s</OBJECT>"
0x180010a26  movaps  [rsp+1E8h+var_78], xmm1
0x180010a2e  movaps  xmm0, xmmword ptr cs:aObjectSIdTypeS+40h; "s</OBJECT>"
0x180010a35  movaps  xmmword ptr [rsp+1E8h+var_68], xmm0
0x180010a3d  movsd   xmm1, qword ptr cs:aObjectSIdTypeS+4Eh; "CT>"
0x180010a45  movsd   qword ptr [rsp+1E8h+var_68+0Eh], xmm1
0x180010a4e  movups  xmm0, xmmword ptr cs:aTypeS; " type=\"%s\""
0x180010a55  movups  xmmword ptr [rsp+1E8h+var_148], xmm0
0x180010a5d  movsd   xmm1, qword ptr cs:aTypeS+0Eh; "%s\""
0x180010a65  movsd   qword ptr [rsp+1E8h+var_148+0Eh], xmm1
0x180010a6e  movups  xmm0, xmmword ptr cs:aNameSName; "<NAME>%s</NAME>"
0x180010a75  movups  xmmword ptr [rsp+1E8h+var_130], xmm0
0x180010a7d  movups  xmm1, xmmword ptr cs:aNameSName+10h; "</NAME>"
0x180010a84  movups  [rsp+1E8h+var_120], xmm1
0x180010a8c  movups  xmm0, xmmword ptr cs:aSkuTypeSSSku; "<SKU type=\"%s\">%s</SKU>"
0x180010a93  movups  xmmword ptr [rsp+1E8h+var_110], xmm0
0x180010a9b  movups  xmm1, xmmword ptr cs:aSkuTypeSSSku+10h; "e=\"%s\">%s</SKU>"
0x180010aa2  movups  [rsp+1E8h+var_100], xmm1
0x180010aaa  movups  xmm0, xmmword ptr cs:aSkuTypeSSSku+20h; "s</SKU>"
0x180010ab1  movups  [rsp+1E8h+var_F0], xmm0
0x180010ab9  movups  xmm1, xmmword ptr cs:aMetadataSSMeta; "<METADATA>%s%s</METADATA>"
0x180010ac0  movups  xmmword ptr [rsp+1E8h+var_E0], xmm1
0x180010ac8  movups  xmm0, xmmword ptr cs:aMetadataSSMeta+10h; "A>%s%s</METADATA>"
0x180010acf  movups  [rsp+1E8h+var_D0], xmm0
0x180010ad7  movups  xmm1, xmmword ptr cs:aMetadataSSMeta+20h; "METADATA>"
0x180010ade  movups  [rsp+1E8h+var_C0], xmm1
0x180010ae6  mov     eax, dword ptr cs:aMetadataSSMeta+30h; ">"
0x180010aec  mov     [rsp+1E8h+var_B0], eax
0x180010af3  xor     r14d, r14d
0x180010af6  mov     r12d, r14d
0x180010af9  mov     [rsp+1E8h+var_190], r14
0x180010afe  mov     eax, r14d
0x180010b01  mov     [rsp+1E8h+Block], rax
0x180010b06  mov     [rsp+1E8h+var_180], rax
0x180010b0b  mov     [rsp+1E8h+var_198], rax
0x180010b10  mov     [rsp+1E8h+var_178], rax
0x180010b15  mov     [rsp+1E8h+var_1A8], rax
0x180010b1a  mov     [rsp+1E8h+var_170], rax
0x180010b1f  test    rbx, rbx
0x180010b22  jnz     short loc_180010B31
0x180010b24  mov     edi, 80070057h
0x180010b29  mov     r13d, eax
0x180010b2c  jmp     loc_180011134
0x180010b31  mov     edi, r14d
0x180010b34  mov     [rbx], r14d
0x180010b37  mov     rcx, r13; lpCriticalSection
0x180010b3a  call    cs:__imp_EnterCriticalSection
0x180010b40  mov     rbx, [rsi+80h]
0x180010b47  mov     rcx, r13; lpCriticalSection
0x180010b4a  call    cs:__imp_LeaveCriticalSection
0x180010b50  test    rbx, rbx
0x180010b53  jz      loc_180011131
0x180010b59  mov     rax, [rsi+80h]
0x180010b60  cmp     [rax], r14w
0x180010b64  jnz     short loc_180010B73
0x180010b66  mov     edi, 8004CF4Fh
0x180010b6b  mov     r13, r12
0x180010b6e  jmp     loc_180011134
0x180010b73  mov     rcx, [rsi+80h]
0x180010b7a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010b7e  mov     rax, rbx
0x180010b81  inc     rax
0x180010b84  cmp     [rcx+rax*2], r14w
0x180010b89  jnz     short loc_180010B81
0x180010b8b  mov     ecx, 0FFFFFFD5h
0x180010b90  cmp     rax, rcx
0x180010b93  ja      loc_1800111EC
0x180010b99  lea     edx, [rax+2Ah]
0x180010b9c  mov     rax, [rsi+88h]
0x180010ba3  mov     rcx, rbx
0x180010ba6  inc     rcx
0x180010ba9  cmp     [rax+rcx*2], r14w
0x180010bae  jnz     short loc_180010BA6
0x180010bb0  mov     eax, edx
0x180010bb2  add     rcx, rax
0x180010bb5  cmp     rcx, rax
0x180010bb8  jb      loc_1800111E7
0x180010bbe  mov     r10d, 0FFFFFFFFh
0x180010bc4  cmp     rcx, r10
0x180010bc7  ja      loc_1800111E7
0x180010bcd  cmp     ecx, 4
0x180010bd0  jb      loc_18001118C
0x180010bd6  add     ecx, 0FFFFFFFCh
0x180010bd9  mov     rdx, [rsi+0A0h]
0x180010be0  test    rdx, rdx
0x180010be3  jz      short loc_180010C2F
0x180010be5  mov     eax, ecx
0x180010be7  add     rcx, 0Ah
0x180010beb  cmp     rcx, rax
0x180010bee  jb      loc_1800111A1
0x180010bf4  cmp     rcx, r10
0x180010bf7  ja      loc_1800111A1
0x180010bfd  mov     r8d, ecx
0x180010c00  mov     rax, rbx
0x180010c03  inc     rax
0x180010c06  cmp     [rdx+rax*2], r14w
0x180010c0b  jnz     short loc_180010C03
0x180010c0d  lea     rcx, [r8+rax]
0x180010c11  cmp     rcx, r8
0x180010c14  jb      loc_18001119C
0x180010c1a  cmp     rcx, r10
0x180010c1d  ja      loc_18001119C
0x180010c23  cmp     ecx, 4
0x180010c26  jb      loc_180011192
0x180010c2c  add     ecx, 0FFFFFFFCh
0x180010c2f  mov     rdx, [rsi+0A8h]
0x180010c36  test    rdx, rdx
0x180010c39  jz      short loc_180010C85
0x180010c3b  mov     eax, ecx
0x180010c3d  add     rcx, 0Fh
0x180010c41  cmp     rcx, rax
0x180010c44  jb      loc_1800111B0
0x180010c4a  cmp     rcx, r10
0x180010c4d  ja      loc_1800111B0
0x180010c53  mov     r8d, ecx
0x180010c56  mov     rax, rbx
0x180010c59  inc     rax
0x180010c5c  cmp     [rdx+rax*2], r14w
0x180010c61  jnz     short loc_180010C59
0x180010c63  lea     rcx, [r8+rax]
0x180010c67  cmp     rcx, r8
0x180010c6a  jb      loc_1800111AB
0x180010c70  cmp     rcx, r10
0x180010c73  ja      loc_1800111AB
0x180010c79  cmp     ecx, 2
0x180010c7c  jb      loc_180011197
0x180010c82  add     ecx, 0FFFFFFFEh
0x180010c85  mov     r9, [rsi+90h]
0x180010c8c  test    r9, r9
0x180010c8f  jz      short loc_180010D06
0x180010c91  mov     eax, ecx
0x180010c93  add     rcx, 17h
0x180010c97  cmp     rcx, rax
0x180010c9a  jb      loc_1800111C4
0x180010ca0  cmp     rcx, r10
0x180010ca3  ja      loc_1800111C4
0x180010ca9  mov     edx, ecx
0x180010cab  mov     rax, rbx
0x180010cae  inc     rax
0x180010cb1  cmp     [r9+rax*2], r14w
0x180010cb6  jnz     short loc_180010CAE
0x180010cb8  lea     rcx, [rdx+rax]
0x180010cbc  cmp     rcx, rdx
0x180010cbf  jb      loc_1800111BF
0x180010cc5  cmp     rcx, r10
0x180010cc8  ja      loc_1800111BF
0x180010cce  mov     edx, ecx
0x180010cd0  mov     rcx, [rsi+98h]
0x180010cd7  mov     rax, rbx
0x180010cda  inc     rax
0x180010cdd  cmp     [rcx+rax*2], r14w
0x180010ce2  jnz     short loc_180010CDA
0x180010ce4  lea     rcx, [rdx+rax]
0x180010ce8  cmp     rcx, rdx
0x180010ceb  jb      loc_1800111BA
0x180010cf1  cmp     rcx, r10
0x180010cf4  ja      loc_1800111BA
0x180010cfa  cmp     ecx, 4
0x180010cfd  jb      loc_1800111A6
0x180010d03  add     ecx, 0FFFFFFFCh
0x180010d06  mov     r8, [rsi+0B0h]
0x180010d0d  test    r8, r8
0x180010d10  jz      short loc_180010D42
0x180010d12  mov     rdx, rbx
0x180010d15  inc     rdx
0x180010d18  cmp     [r8+rdx*2], r14w
0x180010d1d  jnz     short loc_180010D15
0x180010d1f  mov     eax, ecx
0x180010d21  add     rcx, rdx
0x180010d24  cmp     rcx, rax
0x180010d27  jb      loc_1800111CE
0x180010d2d  cmp     rcx, r10
0x180010d30  ja      loc_1800111CE
0x180010d36  cmp     ecx, 2
0x180010d39  jb      loc_1800111B5
0x180010d3f  add     ecx, 0FFFFFFFEh
0x180010d42  test    r9, r9
0x180010d45  jnz     short loc_180010D4C
0x180010d47  test    r8, r8
0x180010d4a  jz      short loc_180010D64
0x180010d4c  mov     eax, ecx
0x180010d4e  add     rcx, 19h
0x180010d52  cmp     rcx, rax
0x180010d55  jb      loc_1800111E2
0x180010d5b  cmp     rcx, r10
0x180010d5e  ja      loc_1800111E2
0x180010d64  cmp     ecx, r10d
0x180010d67  jz      loc_1800111C9
0x180010d6d  lea     r15d, [rcx+1]
0x180010d71  mov     r13d, r15d
0x180010d74  lea     r14, ds:0[r15*2]
0x180010d7c  cmp     r14, r10
0x180010d7f  ja      loc_1800111D3
0x180010d85  xor     eax, eax
0x180010d87  cmp     [rsp+1E8h+var_188], rax
0x180010d8c  jz      loc_1800110FD
0x180010d92  test    r14d, r14d
0x180010d95  jz      loc_1800110FD
0x180010d9b  mov     eax, 2
0x180010da0  mul     r13
0x180010da3  cmovb   rax, rbx
0x180010da7  mov     rcx, rax; unsigned __int64
0x180010daa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010daf  mov     r12, rax
0x180010db2  mov     [rsp+1E8h+var_190], rax
0x180010db7  test    rax, rax
0x180010dba  jnz     short loc_180010DCB
0x180010dbc  mov     edi, 8007000Eh
0x180010dc1  mov     r13, [rsp+1E8h+var_1A8]
0x180010dc6  jmp     loc_180011134
0x180010dcb  mov     r8d, r14d; Size
0x180010dce  xor     edx, edx; Val
0x180010dd0  mov     rcx, r12; void *
0x180010dd3  call    memset_0
0x180010dd8  mov     rdx, [rsi+0A0h]
0x180010ddf  xor     r14d, r14d
0x180010de2  test    rdx, rdx
0x180010de5  jz      loc_180010E82
0x180010deb  lea     rax, [rsp+1E8h+var_148]
0x180010df3  mov     rcx, rbx
0x180010df6  inc     rcx
0x180010df9  cmp     [rax+rcx*2], r14w
0x180010dfe  jnz     short loc_180010DF6
0x180010e00  mov     rax, rbx
0x180010e03  inc     rax
0x180010e06  cmp     [rdx+rax*2], r14w
0x180010e0b  jnz     short loc_180010E03
0x180010e0d  lea     rdi, [rax+1]
0x180010e11  add     rdi, rcx
0x180010e14  mov     edi, edi
0x180010e16  mov     eax, 2
0x180010e1b  mul     rdi
0x180010e1e  cmovb   rax, rbx
0x180010e22  mov     rcx, rax; unsigned __int64
0x180010e25  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010e2a  mov     [rsp+1E8h+Block], rax
0x180010e2f  mov     [rsp+1E8h+var_180], rax
0x180010e34  test    rax, rax
0x180010e37  jnz     short loc_180010E48
0x180010e39  mov     edi, 8007000Eh
0x180010e3e  mov     r13, [rsp+1E8h+var_1A8]
0x180010e43  jmp     loc_180011134
0x180010e48  lea     r8, [rdi+rdi]; Size
0x180010e4c  xor     edx, edx; Val
0x180010e4e  mov     rcx, rax; void *
0x180010e51  call    memset_0
0x180010e56  mov     r9, [rsi+0A0h]
0x180010e5d  lea     r8, [rsp+1E8h+var_148]; unsigned __int16 *
0x180010e65  mov     rdx, rdi; unsigned __int64
0x180010e68  mov     rcx, [rsp+1E8h+Block]; unsigned __int16 *
0x180010e6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010e72  mov     edi, eax
0x180010e74  test    eax, eax
0x180010e76  jns     short loc_180010E82
0x180010e78  mov     r13, [rsp+1E8h+var_1A8]
0x180010e7d  jmp     loc_180011134
0x180010e82  mov     rdx, [rsi+0A8h]
0x180010e89  test    rdx, rdx
0x180010e8c  jz      loc_180010F38
0x180010e92  lea     rax, [rsp+1E8h+var_130]
0x180010e9a  mov     rcx, rbx
0x180010e9d  inc     rcx
0x180010ea0  cmp     [rax+rcx*2], r14w
0x180010ea5  jnz     short loc_180010E9D
0x180010ea7  mov     rax, rbx
0x180010eaa  inc     rax
0x180010ead  cmp     [rdx+rax*2], r14w
0x180010eb2  jnz     short loc_180010EAA
0x180010eb4  lea     rdi, [rax+1]
0x180010eb8  add     rdi, rcx
0x180010ebb  mov     edi, edi
0x180010ebd  mov     eax, 2
  ... truncated ...
```
