# DoubleToChar(double,int,ushort,void *,unsigned __int64 *,unsigned __int64,ulong *,int)

- ea: `0x180016130`
- end: `0x1800166ce`
- name: `?DoubleToChar@@YAJNHGPEAXPEA_K_KPEAKH@Z`
- size: `1438`
- prototype: `int(double, int, unsigned __int16, void *, unsigned __int64 *, unsigned __int64, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180003320`

## callees

- `0x180016130`
- `0x1800166d4`
- `0x180029560`
- `0x18002e848`
- `0x18002ec26`
- `0x18003fdf4`
- `0x18003feb8`
- `0x18007e700`

## import_xrefs

- `msvcrt!_finite` at `0x180016192`
- `msvcrt!_finite` at `0x180016192`
- `msvcrt!_ecvt_s` at `0x1800161c3`
- `msvcrt!_ecvt_s` at `0x1800161c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180016397`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180016397`
- `ole32!CoTaskMemAlloc` at `0x180016305`
- `ole32!CoTaskMemAlloc` at `0x1800165d3`
- `ole32!CoTaskMemAlloc` at `0x180016305`
- `ole32!CoTaskMemAlloc` at `0x1800165d3`
- `ole32!CoTaskMemFree` at `0x18001662e`
- `ole32!CoTaskMemFree` at `0x18001662e`

## pseudocode

```c
__int64 __fastcall DoubleToChar(
        double a1,
        int a2,
        __int16 a3,
        char *a4,
        unsigned __int64 *a5,
        SIZE_T a6,
        unsigned int *a7,
        int a8)
{
  char *v8; // rbx
  __int64 v12; // rdi
  unsigned int v13; // r13d
  char *v14; // rcx
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int i; // eax
  char v19; // al
  int v20; // edi
  __int64 v21; // rdi
  __int64 v22; // rbx
  int v23; // esi
  char *v24; // rax
  size_t v25; // r8
  BSTR v27; // rax
  __int64 v28; // rdx
  char v29; // dl
  int v30; // r10d
  char *j; // r9
  int v32; // eax
  char v33; // al
  char v34; // al
  char k; // al
  int v36; // ecx
  int v37; // eax
  int v38; // r10d
  int v39; // r10d
  char *v40; // rax
  int PtSign; // [rsp+40h] [rbp-A9h] BYREF
  int PtDec; // [rsp+44h] [rbp-A5h] BYREF
  unsigned int *v43; // [rsp+48h] [rbp-A1h]
  unsigned __int64 v44; // [rsp+50h] [rbp-99h] BYREF
  char v45; // [rsp+58h] [rbp-91h] BYREF
  char v46[31]; // [rsp+59h] [rbp-90h] BYREF
  char v47[8]; // [rsp+78h] [rbp-71h] BYREF
  char Buffer[24]; // [rsp+80h] [rbp-69h] BYREF
  OLECHAR Src[28]; // [rsp+98h] [rbp-51h] BYREF

  v8 = &v45;
  v43 = a7;
  v12 = a2;
  v13 = 0;
  PtDec = 0;
  PtSign = 0;
  if ( !_finite(a1) )
  {
    *v43 = 6;
    goto LABEL_33;
  }
  if ( _ecvt_s(Buffer, 0x13u, a1, v12, &PtDec, &PtSign) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v13 = bidTraceHR(off_1800C8390[0], 12565513, L"<DoubleToChar|Trace|HR> ", 2147500037LL);
      goto LABEL_33;
    }
    goto LABEL_47;
  }
  v14 = Buffer;
  v15 = 1;
  if ( PtSign )
  {
    v45 = 45;
    v8 = v46;
  }
  v16 = PtDec;
  v17 = -PtDec;
  if ( PtDec > 0 )
    v17 = PtDec;
  if ( v17 >= (int)v12 )
    goto LABEL_57;
  if ( PtDec >= 0 )
  {
    if ( !PtDec )
      *v8++ = 48;
    for ( i = v16; i; --i )
    {
      v29 = *v14;
      if ( *v14 )
      {
        ++v14;
        *v8 = v29;
      }
      else
      {
        *v8 = 48;
      }
      ++v8;
    }
    v19 = *v14;
    *v8++ = 46;
    if ( v19 )
    {
      do
      {
        *v8 = v19;
        v19 = *++v14;
        ++v8;
      }
      while ( *v14 );
    }
    v15 = 0;
    goto LABEL_16;
  }
  v30 = 0;
  for ( j = &v47[v12 + 7]; *j == 48; ++v30 )
    --j;
  j[1] = 0;
  if ( v30 >= -v16 )
  {
    *(_WORD *)v8 = 11824;
    v32 = v16;
    v8 += 2;
    do
    {
      *v8++ = 48;
      ++v32;
    }
    while ( v32 );
    v33 = Buffer[0];
    if ( Buffer[0] )
    {
      do
      {
        ++v14;
        *v8++ = v33;
        v33 = *v14;
      }
      while ( *v14 );
    }
    v15 = 0;
  }
  if ( v15 )
  {
LABEL_57:
    v34 = *v14++;
    *v8 = v34;
    v8[1] = 46;
    v8 += 2;
    for ( k = *v14; *v14; ++v8 )
    {
      *v8 = k;
      k = *++v14;
    }
  }
LABEL_16:
  while ( v8 >= v46 )
  {
    if ( *(v8 - 1) != 48 )
      break;
    --v8;
  }
  if ( v8 >= v46 && *(v8 - 1) == 46 )
    --v8;
  *v8 = 0;
  v20 = (_DWORD)v8 - (unsigned int)&v45;
  if ( v15 )
  {
    v44 = 6;
    v36 = 1 - v16;
    if ( 1 - v16 < 0 )
      v36 = v16 - 1;
    v37 = 43;
    if ( v16 < 0 )
      v37 = 45;
    StringCchPrintfExA(v47, 6u, 0, &v44, 0, "E%c%d", v37, v36);
    v38 = 6 - v44;
    if ( v20 > -1 && 25 - v38 - 1 >= 1 )
      *((_BYTE *)&v44 + 25 - v38 + 7) = 0;
    v13 = StringCchCopyA(v8, 25LL - v20, v47);
    v20 += v39;
  }
  if ( (unsigned __int64)v20 > 0x19 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v13 = bidTraceHR(off_1800C8390[0], 12715017, L"<DoubleToChar|Trace|HR> ", 2147500037LL);
      goto LABEL_33;
    }
LABEL_47:
    v13 = -2147467259;
    goto LABEL_33;
  }
  if ( a3 != 129 )
  {
    v21 = (unsigned int)FastMultiByteToWideChar((unsigned int)v14, 0, &v45, v20, Src, 24);
    v22 = 2 * v21;
    if ( (unsigned __int64)(2 * v21) >= 0x32 )
      _report_rangecheckfailure();
    Src[v21] = 0;
    if ( a3 == 130 )
    {
      v23 = a8;
      *a5 = v22;
      if ( !a8 )
        goto LABEL_30;
      a6 = v22 + 2;
      v24 = (char *)CoTaskMemAlloc(v22 + 2);
      *(_QWORD *)a4 = v24;
      if ( v24 )
      {
        a4 = v24;
LABEL_30:
        if ( a6 >= 2 )
        {
          v25 = 2 * (int)v21;
          if ( v25 + 2 > a6 )
          {
            *v43 = 4;
            memcpy_0(a4, Src, a6 - 2);
            *(_WORD *)&a4[2 * (a6 >> 1) - 2] = 0;
          }
          else
          {
            memcpy_0(a4, Src, v25);
            *(_WORD *)&a4[v22] = 0;
          }
          goto LABEL_33;
        }
        goto LABEL_78;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        v28 = 12814345;
        goto LABEL_39;
      }
LABEL_85:
      v13 = -2147024882;
      goto LABEL_33;
    }
    *a5 = 8;
    v27 = SysAllocStringLen(Src, v21);
    *(_QWORD *)a4 = v27;
    if ( v27 )
      goto LABEL_33;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_85;
    v28 = 12869641;
LABEL_39:
    v13 = bidTraceHR(off_1800C8390[0], v28, L"<DoubleToChar|Trace|HR> ", 2147942414LL);
    goto LABEL_33;
  }
  v23 = a8;
  *a5 = v20;
  if ( a8 )
  {
    a6 = v20 + 1LL;
    v40 = (char *)CoTaskMemAlloc(a6);
    *(_QWORD *)a4 = v40;
    if ( !v40 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_85;
      v28 = 12737545;
      goto LABEL_39;
    }
    a4 = v40;
  }
  if ( a6 )
  {
    if ( v20 + 1LL > a6 )
    {
      *v43 = 4;
      memcpy_0(a4, &v45, a6 - 1);
      a4[a6 - 1] = 0;
    }
    else
    {
      memcpy_0(a4, &v45, v20);
      a4[v20] = 0;
    }
    goto LABEL_33;
  }
LABEL_78:
  if ( v23 )
    CoTaskMemFree(a4);
  *v43 = 6;
LABEL_33:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8390[0], 12876809, L"<DoubleToChar|Trace|HR> ", v13);
  return v13;
}

```

## disassembly

```asm
0x180016130  mov     [rsp-8+arg_10], rbx
0x180016135  push    rbp
0x180016136  push    rsi
0x180016137  push    rdi
0x180016138  push    r12
0x18001613a  push    r13
0x18001613c  push    r14
0x18001613e  push    r15
0x180016140  lea     rbp, [rsp-7]
0x180016145  sub     rsp, 0F0h
0x18001614c  movaps  [rsp+120h+var_40], xmm6
0x180016154  mov     rax, cs:__security_cookie
0x18001615b  xor     rax, rsp
0x18001615e  mov     [rbp+37h+var_50], rax
0x180016162  mov     rax, [rbp+37h+arg_30]
0x180016166  lea     rbx, [rsp+120h+var_C8]
0x18001616b  mov     r12, [rbp+37h+arg_20]
0x18001616f  mov     r14, r9
0x180016172  mov     r15, [rbp+37h+arg_28]
0x180016176  movzx   esi, r8w
0x18001617a  mov     [rsp+120h+var_D8], rax
0x18001617f  movaps  xmm6, xmm0
0x180016182  xor     eax, eax
0x180016184  movsxd  rdi, edx
0x180016187  mov     r13d, eax
0x18001618a  mov     [rsp+120h+var_DC], eax
0x18001618e  mov     [rsp+120h+var_E0], eax
0x180016192  call    cs:__imp__finite
0x180016198  test    eax, eax
0x18001619a  jz      loc_1800163FE
0x1800161a0  lea     rax, [rsp+120h+var_E0]
0x1800161a5  mov     r9d, edi; DigitCount
0x1800161a8  mov     [rsp+120h+PtSign], rax; PtSign
0x1800161ad  lea     rcx, [rbp+37h+Buffer]; Buffer
0x1800161b1  lea     rax, [rsp+120h+var_DC]
0x1800161b6  movaps  xmm2, xmm6; Value
0x1800161b9  mov     edx, 13h; BufferCount
0x1800161be  mov     [rsp+120h+PtDec], rax; PtDec
0x1800161c3  call    cs:__imp__ecvt_s
0x1800161c9  test    eax, eax
0x1800161cb  jnz     loc_18001640E
0x1800161d1  lea     rcx, [rbp+37h+Buffer]; unsigned int
0x1800161d5  mov     edx, 1
0x1800161da  cmp     [rsp+120h+var_E0], r13d
0x1800161df  jnz     loc_180016448
0x1800161e5  mov     r8d, [rsp+120h+var_DC]
0x1800161ea  mov     eax, r8d
0x1800161ed  neg     eax
0x1800161ef  cmovs   eax, r8d
0x1800161f3  cmp     eax, edi
0x1800161f5  jge     loc_1800164C4
0x1800161fb  test    r8d, r8d
0x1800161fe  js      loc_180016457
0x180016204  jnz     short loc_18001620C
0x180016206  mov     byte ptr [rbx], 30h ; '0'
0x180016209  inc     rbx
0x18001620c  mov     eax, r8d
0x18001620f  test    r8d, r8d
0x180016212  jnz     loc_1800163E0
0x180016218  movzx   eax, byte ptr [rcx]
0x18001621b  mov     byte ptr [rbx], 2Eh ; '.'
0x18001621e  inc     rbx
0x180016221  test    al, al
0x180016223  jz      short loc_180016240
0x180016225  nop     word ptr [rax+rax+00000000h]
0x180016230  mov     [rbx], al
0x180016232  lea     rcx, [rcx+1]
0x180016236  movzx   eax, byte ptr [rcx]
0x180016239  inc     rbx
0x18001623c  test    al, al
0x18001623e  jnz     short loc_180016230
0x180016240  xor     edx, edx
0x180016242  jmp     short loc_18001624C
0x180016244  test    edx, edx
0x180016246  jnz     loc_1800164C4
0x18001624c  lea     rax, [rsp+120h+var_C7]
0x180016251  cmp     rbx, rax
0x180016254  jb      short loc_180016269
0x180016256  cmp     byte ptr [rbx-1], 30h ; '0'
0x18001625a  jnz     short loc_180016269
0x18001625c  dec     rbx
0x18001625f  lea     rax, [rsp+120h+var_C7]
0x180016264  cmp     rbx, rax
0x180016267  jnb     short loc_180016256
0x180016269  lea     rax, [rsp+120h+var_C7]
0x18001626e  cmp     rbx, rax
0x180016271  jb      short loc_18001627F
0x180016273  cmp     byte ptr [rbx-1], 2Eh ; '.'
0x180016277  lea     rax, [rbx-1]
0x18001627b  cmovz   rbx, rax
0x18001627f  lea     rax, [rsp+120h+var_C8]
0x180016284  mov     [rbx], r13b
0x180016287  mov     edi, ebx
0x180016289  sub     edi, eax
0x18001628b  test    edx, edx
0x18001628d  jnz     loc_1800164F4
0x180016293  movsxd  rbx, edi
0x180016296  cmp     rbx, 19h
0x18001629a  ja      loc_18001658E
0x1800162a0  mov     eax, 81h
0x1800162a5  cmp     si, ax
0x1800162a8  jz      loc_1800165C1
0x1800162ae  lea     rax, [rbp+37h+Src]
0x1800162b2  mov     dword ptr [rsp+120h+PtSign], 18h; int
0x1800162ba  mov     r9d, edi; int
0x1800162bd  mov     [rsp+120h+PtDec], rax; unsigned __int16 *
0x1800162c2  lea     r8, [rsp+120h+var_C8]; char *
0x1800162c7  xor     edx, edx; unsigned int
0x1800162c9  call    ?FastMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; FastMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x1800162ce  mov     edi, eax
0x1800162d0  lea     rbx, [rdi+rdi]
0x1800162d4  cmp     rbx, 32h ; '2'
0x1800162d8  jnb     loc_1800166C8
0x1800162de  xor     ecx, ecx
0x1800162e0  mov     eax, 82h
0x1800162e5  mov     [rbp+rbx+37h+Src], cx
0x1800162ea  cmp     si, ax
0x1800162ed  jnz     loc_180016389
0x1800162f3  mov     esi, [rbp+37h+arg_38]
0x1800162f6  mov     [r12], rbx
0x1800162fa  test    esi, esi
0x1800162fc  jz      short loc_18001631A
0x1800162fe  lea     r15, [rbx+2]
0x180016302  mov     rcx, r15; cb
0x180016305  call    cs:__imp_CoTaskMemAlloc
0x18001630b  mov     [r14], rax
0x18001630e  test    rax, rax
0x180016311  jz      loc_180016663
0x180016317  mov     r14, rax
0x18001631a  cmp     r15, 2
0x18001631e  jb      loc_180016627
0x180016324  lea     eax, [rdi+rdi]
0x180016327  mov     rcx, r14; void *
0x18001632a  movsxd  r8, eax; Size
0x18001632d  lea     rdx, [rbp+37h+Src]; Src
0x180016331  lea     rax, [r8+2]
0x180016335  cmp     rax, r15
0x180016338  ja      loc_180016676
0x18001633e  call    memcpy_0
0x180016343  xor     eax, eax
0x180016345  mov     [rbx+r14], ax
0x18001634a  test    byte ptr cs:_bidGblFlags, 2
0x180016351  jnz     loc_1800166A5
0x180016357  mov     eax, r13d
0x18001635a  mov     rcx, [rbp+37h+var_50]
0x18001635e  xor     rcx, rsp; StackCookie
0x180016361  call    __security_check_cookie
0x180016366  mov     rbx, [rsp+120h+arg_10]
0x18001636e  movaps  xmm6, [rsp+120h+var_40]
0x180016376  add     rsp, 0F0h
0x18001637d  pop     r15
0x18001637f  pop     r14
0x180016381  pop     r13
0x180016383  pop     r12
0x180016385  pop     rdi
0x180016386  pop     rsi
0x180016387  pop     rbp
0x180016388  retn
0x180016389  mov     edx, edi; ui
0x18001638b  mov     qword ptr [r12], 8
0x180016393  lea     rcx, [rbp+37h+Src]; strIn
0x180016397  call    cs:__imp_SysAllocStringLen
0x18001639d  mov     [r14], rax
0x1800163a0  test    rax, rax
0x1800163a3  jnz     short loc_18001634A
0x1800163a5  test    byte ptr cs:_bidGblFlags, 2
0x1800163ac  jz      loc_18001669A
0x1800163b2  mov     edx, 0C46009h
0x1800163b7  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800163be  lea     r8, aDoubletocharTr; "<DoubleToChar|Trace|HR> "
0x1800163c5  mov     r9d, 8007000Eh
0x1800163cb  call    _bidTraceHR
0x1800163d0  mov     r13d, eax
0x1800163d3  jmp     loc_18001634A
0x1800163e0  movzx   edx, byte ptr [rcx]
0x1800163e3  test    dl, dl
0x1800163e5  jz      loc_1800164BC
0x1800163eb  inc     rcx
0x1800163ee  mov     [rbx], dl
0x1800163f0  inc     rbx
0x1800163f3  sub     eax, 1
0x1800163f6  jz      loc_180016218
0x1800163fc  jmp     short loc_1800163E0
0x1800163fe  mov     rax, [rsp+120h+var_D8]
0x180016403  mov     dword ptr [rax], 6
0x180016409  jmp     loc_18001634A
0x18001640e  test    byte ptr cs:_bidGblFlags, 2
0x180016415  jz      short loc_18001643D
0x180016417  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001641e  lea     r8, aDoubletocharTr; "<DoubleToChar|Trace|HR> "
0x180016425  mov     r9d, 80004005h
0x18001642b  mov     edx, 0BFBC09h
0x180016430  call    _bidTraceHR
0x180016435  mov     r13d, eax
0x180016438  jmp     loc_18001634A
0x18001643d  mov     r13d, 80004005h
0x180016443  jmp     loc_18001634A
0x180016448  mov     [rsp+120h+var_C8], 2Dh ; '-'
0x18001644d  lea     rbx, [rsp+120h+var_C7]
0x180016452  jmp     loc_1800161E5
0x180016457  xor     r10d, r10d
0x18001645a  lea     r9, [rbp+rdi+37h+var_A1]
0x18001645f  cmp     byte ptr [r9], 30h ; '0'
0x180016463  jnz     short loc_180016471
0x180016465  dec     r9
0x180016468  inc     r10d
0x18001646b  cmp     byte ptr [r9], 30h ; '0'
0x18001646f  jz      short loc_180016465
0x180016471  mov     eax, r8d
0x180016474  mov     [r9+1], r13b
0x180016478  neg     eax
0x18001647a  cmp     r10d, eax
0x18001647d  jl      loc_180016244
0x180016483  mov     word ptr [rbx], 2E30h
0x180016488  mov     eax, r8d
0x18001648b  add     rbx, 2
0x18001648f  test    r8d, r8d
0x180016492  jz      short loc_18001649E
0x180016494  mov     byte ptr [rbx], 30h ; '0'
0x180016497  inc     rbx
0x18001649a  add     eax, edx
0x18001649c  jnz     short loc_180016494
0x18001649e  movzx   eax, [rbp+37h+Buffer]
0x1800164a2  test    al, al
0x1800164a4  jz      short loc_1800164B5
0x1800164a6  inc     rcx
0x1800164a9  mov     [rbx], al
0x1800164ab  inc     rbx
0x1800164ae  movzx   eax, byte ptr [rcx]
0x1800164b1  test    al, al
0x1800164b3  jnz     short loc_1800164A6
0x1800164b5  xor     edx, edx
0x1800164b7  jmp     loc_180016244
0x1800164bc  mov     byte ptr [rbx], 30h ; '0'
0x1800164bf  jmp     loc_1800163F0
0x1800164c4  movzx   eax, byte ptr [rcx]
0x1800164c7  inc     rcx
0x1800164ca  mov     [rbx], al
0x1800164cc  mov     byte ptr [rbx+1], 2Eh ; '.'
0x1800164d0  add     rbx, 2
0x1800164d4  movzx   eax, byte ptr [rcx]
0x1800164d7  test    al, al
0x1800164d9  jz      loc_18001624C
0x1800164df  mov     [rbx], al
0x1800164e1  lea     rcx, [rcx+1]
0x1800164e5  movzx   eax, byte ptr [rcx]
0x1800164e8  inc     rbx
0x1800164eb  test    al, al
0x1800164ed  jnz     short loc_1800164DF
0x1800164ef  jmp     loc_18001624C
0x1800164f4  lea     eax, [r8-1]
0x1800164f8  mov     [rsp+120h+var_D0], 6
0x180016501  mov     ecx, eax
0x180016503  lea     r9, [rsp+120h+var_D0]; unsigned __int64 *
0x180016508  neg     ecx
0x18001650a  mov     edx, 2Dh ; '-'
0x18001650f  cmovs   ecx, eax
0x180016512  test    r8d, r8d
0x180016515  mov     [rsp+120h+var_E8], ecx
0x180016519  mov     eax, 2Bh ; '+'
0x18001651e  cmovs   eax, edx
0x180016521  lea     rcx, [rbp+37h+var_A8]; char *
0x180016525  mov     [rsp+120h+var_F0], eax
0x180016529  xor     r8d, r8d; char **
0x18001652c  lea     rax, aECD; "E%c%d"
0x180016533  mov     edx, 6; Size
0x180016538  mov     [rsp+120h+PtSign], rax; char *
0x18001653d  mov     [rsp+120h+PtDec], r13; unsigned int
0x180016542  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180016547  mov     r10d, 6
0x18001654d  mov     edx, 19h
0x180016552  sub     r10, [rsp+120h+var_D0]
0x180016557  cmp     edi, 0FFFFFFFFh
0x18001655a  jle     short loc_180016571
0x18001655c  mov     ecx, edx
0x18001655e  sub     ecx, r10d
0x180016561  lea     eax, [rcx-1]
0x180016564  cmp     eax, 1
0x180016567  jl      short loc_180016571
0x180016569  movsxd  rax, ecx
0x18001656c  mov     byte ptr [rsp+rax+120h+var_D0+7], r13b
0x180016571  movsxd  rax, edi
0x180016574  lea     r8, [rbp+37h+var_A8]; char *
0x180016578  sub     rdx, rax; unsigned __int64
0x18001657b  mov     rcx, rbx; char *
0x18001657e  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180016583  mov     r13d, eax
0x180016586  add     edi, r10d
0x180016589  jmp     loc_180016293
0x18001658e  test    byte ptr cs:_bidGblFlags, 2
0x180016595  jz      loc_18001643D
0x18001659b  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800165a2  lea     r8, aDoubletocharTr; "<DoubleToChar|Trace|HR> "
0x1800165a9  mov     r9d, 80004005h
0x1800165af  mov     edx, 0C20409h
0x1800165b4  call    _bidTraceHR
0x1800165b9  mov     r13d, eax
0x1800165bc  jmp     loc_18001634A
0x1800165c1  mov     esi, [rbp+37h+arg_38]
0x1800165c4  mov     [r12], rbx
  ... truncated ...
```
