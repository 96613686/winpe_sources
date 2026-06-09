# CWriterGlobalHelper::ToString(uchar *,ulong,ulong,ulong,ulong,ushort * *)

- ea: `0x18000674c`
- end: `0x180006d02`
- name: `?ToString@CWriterGlobalHelper@@QEAAJPEAEKKKKPEAPEAG@Z`
- size: `1462`
- prototype: `__int64 __usercall@<rax>(CWriterGlobalHelper *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, CWriterGlobalHelper *, unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180006420`
- `0x18002ec50`
- `0x18002fb58`

## callees

- `0x18000674c`
- `0x1800071a0`
- `0x18000839c`
- `0x180008a08`
- `0x18002bdb4`
- `0x18002d32c`
- `0x18002d3ac`
- `0x18003098e`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180006868`
- `IisRTL!PuDbgPrintW` at `0x180006868`

## string_xrefs

- `0x180006856`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x180006848`: `CWriterGlobalHelper::ToString`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::ToString(
        CWriterGlobalHelper *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        CWriterGlobalHelper *a5,
        char a6,
        unsigned __int16 **a7)
{
  unsigned int v7; // r14d
  int v10; // edi
  void *v12; // rsi
  __int64 v13; // rsi
  CWriterGlobalHelper *v14; // rcx
  int v15; // r13d
  const unsigned __int16 *i; // rsi
  __int64 v17; // r14
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int16 *v20; // r14
  unsigned __int8 *v21; // r13
  size_t v22; // rbx
  __int64 v23; // r13
  size_t v24; // rbx
  __int64 v25; // rax
  size_t v26; // rbx
  __int64 v27; // r12
  int v28; // eax
  unsigned int v29; // r14d
  int v30; // eax
  unsigned int v32; // edx
  unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rdx
  unsigned int j; // r8d
  __int64 k; // r9
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+44h] [rbp-BCh] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h]
  unsigned int v42; // [rsp+58h] [rbp-A8h]
  unsigned int v43; // [rsp+5Ch] [rbp-A4h] BYREF
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v45[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v46[18]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v47[8]; // [rsp+100h] [rbp+0h] BYREF
  unsigned int *v48; // [rsp+108h] [rbp+8h]
  _DWORD *v49; // [rsp+130h] [rbp+30h]

  v7 = a3;
  v42 = a3;
  v44 = a4;
  v10 = 0;
  v45[1] = 13;
  v45[0] = 0;
  memset_0(v46, 0, sizeof(v46));
  v46[0] = *((_QWORD *)this + 29);
  v46[13] = &v44;
  v12 = 0;
  v43 = 0;
  Block = 0;
  v38 = 0;
  v39 = 0;
  *a7 = 0;
  if ( !a2 )
    return (unsigned int)v10;
  if ( (a6 & 4) != 0 )
    goto LABEL_68;
  if ( (_DWORD)a5 == 1 )
  {
    v29 = *(_DWORD *)a2;
    v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)this + 6) + 56LL))(
            *((_QWORD *)this + 6),
            0,
            2,
            v45,
            0,
            v46,
            &v43);
    v10 = v30;
    if ( v30 < 0 )
    {
      if ( v30 != -2145318890 )
        return (unsigned int)v10;
    }
    else
    {
      Block = (void *)0x600000001LL;
      memset_0(v47, 0, 0x90u);
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, void **, _QWORD, _BYTE *))(**((_QWORD **)this + 6) + 32LL))(
              *((_QWORD *)this + 6),
              v43,
              2,
              &Block,
              0,
              v47);
      if ( v10 < 0 )
        return (unsigned int)v10;
      if ( (*v49 & 0x40) != 0 )
        return (unsigned int)CWriterGlobalHelper::FlagToString(this, v29, a7, *((unsigned __int16 **)this + 29), *v48);
      if ( (*v49 & 0x20) != 0 )
      {
        if ( v29 )
        {
          v32 = g_cchTrue;
          v33 = L"TRUE";
        }
        else
        {
          v32 = g_cchFalse;
          v33 = L"FALSE";
        }
        return (unsigned int)StringToNewString(v33, v32, a7);
      }
    }
    v28 = UnsignedLongToNewString(v29, a7);
    goto LABEL_64;
  }
  if ( (_DWORD)a5 == 2 )
  {
LABEL_45:
    v27 = -1;
    do
      ++v27;
    while ( a2[v27] );
    v10 = CWriterGlobalHelper::EscapeString(
            (CWriterGlobalHelper *)(unsigned int)a5,
            a2,
            v27,
            &v39,
            (unsigned __int16 **)&Block,
            &v38);
    if ( v10 < 0 )
    {
LABEL_50:
      v12 = Block;
      goto LABEL_65;
    }
    v12 = Block;
    if ( !Block )
    {
LABEL_65:
      if ( v39 && v12 )
        operator delete(v12);
      return (unsigned int)v10;
    }
    v28 = StringToNewString((unsigned __int16 *)Block, v38, a7);
LABEL_64:
    v10 = v28;
    goto LABEL_65;
  }
  if ( (_DWORD)a5 != 3 )
  {
    if ( (_DWORD)a5 != 4 )
    {
      if ( (_DWORD)a5 != 5 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
            1783,
            "CWriterGlobalHelper::ToString",
            L"[ToString] Unknown data type %d for ID: %d.\n",
            (_DWORD)a5,
            a4);
        return (unsigned int)-2147024809;
      }
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      v10 = CWriterGlobalHelper::EscapeString(
              (CWriterGlobalHelper *)(unsigned int)a5,
              a2,
              v13,
              &v39,
              (unsigned __int16 **)&Block,
              &v38);
      if ( v10 >= 0 )
      {
        v14 = (CWriterGlobalHelper *)v38;
        v15 = 1;
        for ( i = &a2[(unsigned int)v13 + 1]; ; i += v18 + 1 )
        {
          LODWORD(v41) = (_DWORD)v14;
          if ( !*i || i >= (const unsigned __int16 *)((char *)a2 + v7) )
            break;
          if ( v39 )
          {
            v14 = (CWriterGlobalHelper *)Block;
            if ( Block )
            {
              operator delete(Block);
              Block = 0;
              v39 = 0;
            }
          }
          v17 = -1;
          do
            ++v17;
          while ( i[v17] );
          v10 = CWriterGlobalHelper::EscapeString(v14, i, v17, &v39, (unsigned __int16 **)&Block, &v38);
          if ( v10 < 0 )
            goto LABEL_50;
          ++v15;
          v14 = (CWriterGlobalHelper *)(v38 + (unsigned int)v41);
          v18 = (unsigned int)v17;
          v7 = v42;
        }
        v10 = NewString(v15 + (int)v14 + 4 * v15 - 4, a7);
        if ( v10 >= 0 )
        {
          v19 = -1;
          do
            ++v19;
          while ( a2[v19] );
          v20 = *a7;
          v41 = v19;
          v10 = CWriterGlobalHelper::EscapeString(
                  (CWriterGlobalHelper *)&Block,
                  a2,
                  v19,
                  &v39,
                  (unsigned __int16 **)&Block,
                  &v38);
          if ( v10 >= 0 )
          {
            v12 = Block;
            v21 = (unsigned __int8 *)a2;
            if ( v20 && Block )
            {
              v22 = 2LL * v38;
              memcpy_0(v20, Block, v22);
              v20 = (unsigned __int16 *)((char *)v20 + v22);
              v23 = (unsigned int)v41 + 1LL;
              *v20 = 0;
              v21 = (unsigned __int8 *)&a2[v23];
            }
            while ( *(_WORD *)v21 && v21 < (unsigned __int8 *)a2 + v42 )
            {
              if ( v20 )
              {
                v24 = 2LL * g_cchMultiszSeperator;
                memcpy_0(v20, L"\r\n\t\t\t", v24);
                v20 = (unsigned __int16 *)((char *)v20 + v24);
                *v20 = 0;
              }
              if ( v39 && v12 )
              {
                operator delete(v12);
                Block = 0;
                v39 = 0;
              }
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)&v21[2 * v25] );
              v41 = v25;
              v10 = CWriterGlobalHelper::EscapeString(
                      (CWriterGlobalHelper *)&Block,
                      (const unsigned __int16 *)v21,
                      v25,
                      &v39,
                      (unsigned __int16 **)&Block,
                      &v38);
              if ( v10 < 0 )
                goto LABEL_50;
              v12 = Block;
              if ( v20 && Block )
              {
                v26 = 2LL * v38;
                memcpy_0(v20, Block, v26);
                v20 = (unsigned __int16 *)((char *)v20 + v26);
                *v20 = 0;
              }
              v21 += 2 * (unsigned int)v41 + 2;
            }
            goto LABEL_65;
          }
        }
      }
      goto LABEL_50;
    }
    goto LABEL_45;
  }
LABEL_68:
  v10 = NewString(2 * v7, a7);
  if ( v10 >= 0 )
  {
    v34 = *a7;
    for ( j = 0; j < v7; ++j )
    {
      if ( v34 )
      {
        for ( k = 0; k != 2; ++k )
          v34[k] = off_1800324B0[*((unsigned __int8 *)a2 + j)][k];
        v34 += 2;
      }
    }
    if ( v34 )
      *v34 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000674c  push    rbp
0x18000674e  push    rbx
0x18000674f  push    rsi
0x180006750  push    rdi
0x180006751  push    r12
0x180006753  push    r13
0x180006755  push    r14
0x180006757  push    r15
0x180006759  lea     rbp, [rsp-0A8h]
0x180006761  sub     rsp, 1A8h
0x180006768  mov     rax, cs:__security_cookie
0x18000676f  xor     rax, rsp
0x180006772  mov     [rbp+0E0h+var_50], rax
0x180006779  mov     rbx, [rbp+0E0h+arg_30]
0x180006780  mov     r14d, r8d
0x180006783  mov     [rsp+1E0h+var_188], r8d
0x180006788  mov     r15, rdx
0x18000678b  mov     r13, rcx
0x18000678e  mov     [rsp+1E0h+var_180], r9d
0x180006793  xor     edi, edi
0x180006795  mov     [rsp+1E0h+var_174], 0Dh
0x18000679d  xor     edx, edx; Val
0x18000679f  mov     [rsp+1E0h+var_178], edi
0x1800067a3  mov     r8d, 90h; Size
0x1800067a9  lea     rcx, [rsp+1E0h+var_170]; void *
0x1800067ae  mov     r12d, r9d
0x1800067b1  call    memset_0
0x1800067b6  mov     rax, [r13+0E8h]
0x1800067bd  xor     r8d, r8d
0x1800067c0  mov     [rsp+1E0h+var_170], rax
0x1800067c5  lea     rax, [rsp+1E0h+var_180]
0x1800067ca  mov     [rbp+0E0h+var_108], rax
0x1800067ce  mov     esi, r8d
0x1800067d1  mov     [rsp+1E0h+var_184], r8d
0x1800067d6  mov     [rsp+1E0h+Block], r8
0x1800067db  mov     [rsp+1E0h+var_1A0], r8d
0x1800067e0  mov     [rsp+1E0h+var_19C], r8d
0x1800067e5  mov     [rbx], r8
0x1800067e8  test    r15, r15
0x1800067eb  jz      loc_180006CDD
0x1800067f1  test    [rbp+0E0h+arg_28], 4
0x1800067f8  jnz     loc_180006C7A
0x1800067fe  mov     ecx, dword ptr [rbp+0E0h+arg_20]; this
0x180006804  mov     eax, ecx
0x180006806  sub     eax, 1
0x180006809  jz      loc_180006B4C
0x18000680f  sub     eax, 1
0x180006812  jz      loc_180006AE6
0x180006818  sub     eax, 1
0x18000681b  jz      loc_180006C7A
0x180006821  sub     eax, 1
0x180006824  jz      loc_180006AE6
0x18000682a  cmp     eax, 1
0x18000682d  jz      short loc_180006878
0x18000682f  test    byte ptr cs:g_dwDebugFlags, 3
0x180006836  jz      short loc_18000686E
0x180006838  mov     dword ptr [rsp+1E0h+var_1B0], r12d
0x18000683d  lea     rax, aTostringUnknow; "[ToString] Unknown data type %d for ID:"...
0x180006844  mov     dword ptr [rsp+1E0h+var_1B8], ecx
0x180006848  lea     r9, aCwriterglobalh_0; "CWriterGlobalHelper::ToString"
0x18000684f  mov     rcx, cs:g_pDebug
0x180006856  lea     rdx, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18000685d  mov     r8d, 6F7h
0x180006863  mov     [rsp+1E0h+var_1C0], rax
0x180006868  call    cs:__imp_PuDbgPrintW
0x18000686e  mov     edi, 80070057h
0x180006873  jmp     loc_180006CDD
0x180006878  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000687c  mov     rsi, r12
0x18000687f  inc     rsi
0x180006882  cmp     [r15+rsi*2], r8w
0x180006887  jnz     short loc_18000687F
0x180006889  lea     rax, [rsp+1E0h+var_1A0]
0x18000688e  mov     r8d, esi; unsigned int
0x180006891  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x180006896  lea     r9, [rsp+1E0h+var_19C]; int *
0x18000689b  lea     rax, [rsp+1E0h+Block]
0x1800068a0  mov     rdx, r15; unsigned __int16 *
0x1800068a3  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x1800068a8  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x1800068ad  xor     edx, edx
0x1800068af  mov     edi, eax
0x1800068b1  test    eax, eax
0x1800068b3  js      loc_180006B3F
0x1800068b9  mov     ecx, [rsp+1E0h+var_1A0]
0x1800068bd  lea     r13d, [rdx+1]
0x1800068c1  mov     esi, esi
0x1800068c3  inc     rsi
0x1800068c6  lea     rsi, [r15+rsi*2]
0x1800068ca  mov     dword ptr [rsp+1E0h+var_190], ecx
0x1800068ce  cmp     dx, [rsi]
0x1800068d1  jz      loc_18000695F
0x1800068d7  mov     eax, r14d
0x1800068da  add     rax, r15
0x1800068dd  cmp     rsi, rax
0x1800068e0  jnb     short loc_18000695F
0x1800068e2  cmp     [rsp+1E0h+var_19C], edx
0x1800068e6  jz      short loc_180006902
0x1800068e8  mov     rcx, [rsp+1E0h+Block]; Block
0x1800068ed  test    rcx, rcx
0x1800068f0  jz      short loc_180006902
0x1800068f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800068f7  xor     edx, edx
0x1800068f9  mov     [rsp+1E0h+Block], rdx
0x1800068fe  mov     [rsp+1E0h+var_19C], edx
0x180006902  mov     r14, r12
0x180006905  inc     r14
0x180006908  cmp     [rsi+r14*2], dx
0x18000690d  jnz     short loc_180006905
0x18000690f  lea     rax, [rsp+1E0h+var_1A0]
0x180006914  mov     r8d, r14d; unsigned int
0x180006917  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x18000691c  lea     r9, [rsp+1E0h+var_19C]; int *
0x180006921  lea     rax, [rsp+1E0h+Block]
0x180006926  mov     rdx, rsi; unsigned __int16 *
0x180006929  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x18000692e  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x180006933  xor     edx, edx
0x180006935  mov     edi, eax
0x180006937  test    eax, eax
0x180006939  js      loc_180006B3F
0x18000693f  mov     ecx, dword ptr [rsp+1E0h+var_190]
0x180006943  inc     r13d
0x180006946  add     ecx, [rsp+1E0h+var_1A0]
0x18000694a  mov     eax, r14d
0x18000694d  mov     r14d, [rsp+1E0h+var_188]
0x180006952  lea     rsi, [rsi+rax*2]
0x180006956  add     rsi, 2
0x18000695a  jmp     loc_1800068CA
0x18000695f  lea     ecx, [rcx+r13*4]
0x180006963  mov     rdx, rbx; unsigned __int16 **
0x180006966  add     ecx, 0FFFFFFFCh
0x180006969  add     ecx, r13d; unsigned int
0x18000696c  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x180006971  xor     edx, edx
0x180006973  mov     edi, eax
0x180006975  test    eax, eax
0x180006977  js      loc_180006B3F
0x18000697d  mov     rax, r12
0x180006980  inc     rax
0x180006983  cmp     [r15+rax*2], dx
0x180006988  jnz     short loc_180006980
0x18000698a  mov     r14, [rbx]
0x18000698d  lea     rcx, [rsp+1E0h+var_1A0]
0x180006992  mov     [rsp+1E0h+var_1B8], rcx; unsigned int *
0x180006997  lea     r9, [rsp+1E0h+var_19C]; int *
0x18000699c  lea     rcx, [rsp+1E0h+Block]; this
0x1800069a1  mov     [rsp+1E0h+var_190], rax
0x1800069a6  mov     r8d, eax; unsigned int
0x1800069a9  mov     [rsp+1E0h+var_1C0], rcx; unsigned __int16 **
0x1800069ae  mov     rdx, r15; unsigned __int16 *
0x1800069b1  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x1800069b6  xor     edx, edx
0x1800069b8  mov     edi, eax
0x1800069ba  test    eax, eax
0x1800069bc  js      loc_180006B3F
0x1800069c2  mov     rsi, [rsp+1E0h+Block]
0x1800069c7  mov     r13, r15
0x1800069ca  test    r14, r14
0x1800069cd  jz      short loc_180006A02
0x1800069cf  test    rsi, rsi
0x1800069d2  jz      short loc_180006A02
0x1800069d4  mov     eax, [rsp+1E0h+var_1A0]
0x1800069d8  mov     rdx, rsi; Src
0x1800069db  mov     rcx, r14; void *
0x1800069de  lea     rbx, [rax+rax]
0x1800069e2  mov     r8, rbx; Size
0x1800069e5  call    memcpy_0
0x1800069ea  mov     r13d, dword ptr [rsp+1E0h+var_190]
0x1800069ef  lea     rcx, [rbx+r14]
0x1800069f3  xor     edx, edx
0x1800069f5  mov     r14, rcx
0x1800069f8  inc     r13
0x1800069fb  mov     [rcx], dx
0x1800069fe  lea     r13, [r15+r13*2]
0x180006a02  cmp     dx, [r13+0]
0x180006a07  jz      loc_180006B44
0x180006a0d  mov     eax, [rsp+1E0h+var_188]
0x180006a11  add     rax, r15
0x180006a14  cmp     r13, rax
0x180006a17  jnb     loc_180006B44
0x180006a1d  test    r14, r14
0x180006a20  jz      short loc_180006A46
0x180006a22  mov     ebx, cs:?g_cchMultiszSeperator@@3KA; ulong g_cchMultiszSeperator
0x180006a28  lea     rdx, asc_180040F58; "\r\n\t\t\t"
0x180006a2f  add     rbx, rbx
0x180006a32  mov     rcx, r14; void *
0x180006a35  mov     r8, rbx; Size
0x180006a38  call    memcpy_0
0x180006a3d  add     r14, rbx
0x180006a40  xor     edx, edx
0x180006a42  mov     [r14], dx
0x180006a46  cmp     [rsp+1E0h+var_19C], edx
0x180006a4a  jz      short loc_180006A64
0x180006a4c  test    rsi, rsi
0x180006a4f  jz      short loc_180006A64
0x180006a51  mov     rcx, rsi; Block
0x180006a54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a59  xor     edx, edx
0x180006a5b  mov     [rsp+1E0h+Block], rdx
0x180006a60  mov     [rsp+1E0h+var_19C], edx
0x180006a64  mov     rax, r12
0x180006a67  inc     rax
0x180006a6a  cmp     [r13+rax*2+0], dx
0x180006a70  jnz     short loc_180006A67
0x180006a72  lea     rcx, [rsp+1E0h+var_1A0]
0x180006a77  mov     [rsp+1E0h+var_190], rax
0x180006a7c  mov     [rsp+1E0h+var_1B8], rcx; unsigned int *
0x180006a81  lea     r9, [rsp+1E0h+var_19C]; int *
0x180006a86  lea     rcx, [rsp+1E0h+Block]; this
0x180006a8b  mov     r8d, eax; unsigned int
0x180006a8e  mov     rdx, r13; unsigned __int16 *
0x180006a91  mov     [rsp+1E0h+var_1C0], rcx; unsigned __int16 **
0x180006a96  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x180006a9b  xor     edx, edx
0x180006a9d  mov     edi, eax
0x180006a9f  test    eax, eax
0x180006aa1  js      loc_180006B3F
0x180006aa7  mov     rsi, [rsp+1E0h+Block]
0x180006aac  test    r14, r14
0x180006aaf  jz      short loc_180006AD4
0x180006ab1  test    rsi, rsi
0x180006ab4  jz      short loc_180006AD4
0x180006ab6  mov     ebx, [rsp+1E0h+var_1A0]
0x180006aba  mov     rdx, rsi; Src
0x180006abd  add     rbx, rbx
0x180006ac0  mov     rcx, r14; void *
0x180006ac3  mov     r8, rbx; Size
0x180006ac6  call    memcpy_0
0x180006acb  add     r14, rbx
0x180006ace  xor     edx, edx
0x180006ad0  mov     [r14], dx
0x180006ad4  mov     eax, dword ptr [rsp+1E0h+var_190]
0x180006ad8  lea     r13, [r13+rax*2+0]
0x180006add  add     r13, 2
0x180006ae1  jmp     loc_180006A02
0x180006ae6  or      r12, 0FFFFFFFFFFFFFFFFh
0x180006aea  inc     r12
0x180006aed  cmp     [r15+r12*2], r8w
0x180006af2  jnz     short loc_180006AEA
0x180006af4  lea     rax, [rsp+1E0h+var_1A0]
0x180006af9  mov     r8d, r12d; unsigned int
0x180006afc  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x180006b01  lea     r9, [rsp+1E0h+var_19C]; int *
0x180006b06  lea     rax, [rsp+1E0h+Block]
0x180006b0b  mov     rdx, r15; unsigned __int16 *
0x180006b0e  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x180006b13  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x180006b18  mov     edi, eax
0x180006b1a  test    eax, eax
0x180006b1c  js      short loc_180006B3F
0x180006b1e  mov     rsi, [rsp+1E0h+Block]
0x180006b23  test    rsi, rsi
0x180006b26  jz      short loc_180006B44
0x180006b28  mov     edx, [rsp+1E0h+var_1A0]; unsigned int
0x180006b2c  mov     r8, rbx; unsigned __int16 **
0x180006b2f  mov     rcx, rsi; Src
0x180006b32  call    ?StringToNewString@@YAJPEAGKPEAPEAG@Z; StringToNewString(ushort *,ulong,ushort * *)
0x180006b37  xor     r15d, r15d
0x180006b3a  jmp     loc_180006C62
0x180006b3f  mov     rsi, [rsp+1E0h+Block]
0x180006b44  xor     r15d, r15d
0x180006b47  jmp     loc_180006C64
0x180006b4c  mov     rcx, [r13+30h]
0x180006b50  lea     rdx, [rsp+1E0h+var_184]
0x180006b55  mov     r14d, [r15]
0x180006b58  lea     r9, [rsp+1E0h+var_178]
0x180006b5d  mov     [rsp+1E0h+var_1B0], rdx
0x180006b62  lea     rdx, [rsp+1E0h+var_170]
0x180006b67  mov     [rsp+1E0h+var_1B8], rdx
0x180006b6c  xor     edx, edx
0x180006b6e  mov     rax, [rcx]
0x180006b71  mov     [rsp+1E0h+var_1C0], r8
0x180006b76  lea     r8d, [rdx+2]
0x180006b7a  mov     rax, [rax+38h]
0x180006b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b83  xor     r15d, r15d
0x180006b86  mov     edi, eax
0x180006b88  test    eax, eax
0x180006b8a  js      loc_180006C4C
0x180006b90  xor     edx, edx; Val
0x180006b92  mov     dword ptr [rsp+1E0h+Block], 1
0x180006b9a  mov     r8d, 90h; Size
0x180006ba0  mov     dword ptr [rsp+1E0h+Block+4], 6
0x180006ba8  lea     rcx, [rbp+0E0h+var_E0]; void *
0x180006bac  call    memset_0
0x180006bb1  mov     rcx, [r13+30h]
0x180006bb5  lea     rdx, [rbp+0E0h+var_E0]
0x180006bb9  mov     [rsp+1E0h+var_1B8], rdx
0x180006bbe  lea     r9, [rsp+1E0h+Block]
0x180006bc3  mov     edx, [rsp+1E0h+var_184]
0x180006bc7  lea     r8d, [r15+2]
0x180006bcb  mov     [rsp+1E0h+var_1C0], r15
0x180006bd0  mov     rax, [rcx]
0x180006bd3  mov     rax, [rax+20h]
0x180006bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdc  mov     edi, eax
0x180006bde  test    eax, eax
0x180006be0  js      loc_180006CDD
0x180006be6  mov     rax, [rbp+0E0h+var_B0]
  ... truncated ...
```
