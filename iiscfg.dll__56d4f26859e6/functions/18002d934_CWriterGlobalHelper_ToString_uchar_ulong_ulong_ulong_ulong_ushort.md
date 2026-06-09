# CWriterGlobalHelper::ToString(uchar *,ulong,ulong,ulong,ulong,ushort * *)

- ea: `0x18002d934`
- end: `0x18002dee4`
- name: `?ToString@CWriterGlobalHelper@@QEAAJPEAEKKKKPEAPEAG@Z`
- size: `1456`
- prototype: `__int64 __usercall@<rax>(CWriterGlobalHelper *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, CWriterGlobalHelper *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18002b52c`

## callees

- `0x18002c2d4`
- `0x18002c604`
- `0x18002d730`
- `0x18002d8b4`
- `0x18002d934`
- `0x18002deec`
- `0x18002e0b2`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002dacd`
- `ole32!CoTaskMemFree` at `0x18002dc30`
- `ole32!CoTaskMemFree` at `0x18002deb9`
- `ole32!CoTaskMemFree` at `0x18002dacd`
- `ole32!CoTaskMemFree` at `0x18002dc30`
- `ole32!CoTaskMemFree` at `0x18002deb9`
- `IisRTL!PuDbgPrintW` at `0x18002da43`
- `IisRTL!PuDbgPrintW` at `0x18002da43`

## string_xrefs

- `0x18002da31`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002da23`: `CWriterGlobalHelper::ToString`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::ToString(
        CWriterGlobalHelper *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        CWriterGlobalHelper *a5,
        unsigned int a6,
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
  unsigned __int16 *v27; // rdx
  unsigned int j; // r8d
  __int64 k; // r9
  __int64 v30; // r12
  int v31; // eax
  unsigned int v32; // r14d
  int v33; // eax
  unsigned int v35; // edx
  unsigned __int16 *v36; // rcx
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
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
  pv = 0;
  v38 = 0;
  v39 = 0;
  *a7 = 0;
  if ( !a2 )
    return (unsigned int)v10;
  if ( (_DWORD)a5 == 1 )
  {
    v32 = *(_DWORD *)a2;
    v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)this + 6) + 56LL))(
            *((_QWORD *)this + 6),
            0,
            2,
            v45,
            0,
            v46,
            &v43);
    v10 = v33;
    if ( v33 < 0 )
    {
      if ( v33 != -2145318890 )
        return (unsigned int)v10;
    }
    else
    {
      pv = (LPVOID)0x600000001LL;
      memset_0(v47, 0, 0x90u);
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *, _QWORD, _BYTE *))(**((_QWORD **)this + 6)
                                                                                          + 32LL))(
              *((_QWORD *)this + 6),
              v43,
              2,
              &pv,
              0,
              v47);
      if ( v10 < 0 )
        return (unsigned int)v10;
      if ( (*v49 & 0x40) != 0 )
        return (unsigned int)CWriterGlobalHelper::FlagToString(this, v32, a7, *((unsigned __int16 **)this + 29), *v48);
      if ( (*v49 & 0x20) != 0 )
      {
        if ( v32 )
        {
          v35 = g_cchTrue;
          v36 = L"TRUE";
        }
        else
        {
          v35 = g_cchFalse;
          v36 = L"FALSE";
        }
        return (unsigned int)StringToNewString(v36, v35, a7);
      }
    }
    v31 = UnsignedLongToNewString(v32, a7);
    goto LABEL_72;
  }
  if ( (_DWORD)a5 == 2 )
  {
LABEL_53:
    v30 = -1;
    do
      ++v30;
    while ( a2[v30] );
    v10 = CWriterGlobalHelper::EscapeString(
            (CWriterGlobalHelper *)(unsigned int)a5,
            a2,
            v30,
            &v39,
            (unsigned __int16 **)&pv,
            &v38);
    if ( v10 < 0 )
    {
LABEL_58:
      v12 = pv;
      goto LABEL_73;
    }
    v12 = pv;
    if ( !pv )
    {
LABEL_73:
      if ( v39 && v12 )
        CoTaskMemFree(v12);
      return (unsigned int)v10;
    }
    v31 = StringToNewString((unsigned __int16 *)pv, v38, a7);
LABEL_72:
    v10 = v31;
    goto LABEL_73;
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
              (unsigned __int16 **)&pv,
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
            v14 = (CWriterGlobalHelper *)pv;
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
              v39 = 0;
            }
          }
          v17 = -1;
          do
            ++v17;
          while ( i[v17] );
          v10 = CWriterGlobalHelper::EscapeString(v14, i, v17, &v39, (unsigned __int16 **)&pv, &v38);
          if ( v10 < 0 )
            goto LABEL_58;
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
                  (CWriterGlobalHelper *)&pv,
                  a2,
                  v19,
                  &v39,
                  (unsigned __int16 **)&pv,
                  &v38);
          if ( v10 >= 0 )
          {
            v12 = pv;
            v21 = (unsigned __int8 *)a2;
            if ( v20 && pv )
            {
              v22 = 2LL * v38;
              memcpy_0(v20, pv, v22);
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
                CoTaskMemFree(v12);
                pv = 0;
                v39 = 0;
              }
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)&v21[2 * v25] );
              v41 = v25;
              v10 = CWriterGlobalHelper::EscapeString(
                      (CWriterGlobalHelper *)&pv,
                      (const unsigned __int16 *)v21,
                      v25,
                      &v39,
                      (unsigned __int16 **)&pv,
                      &v38);
              if ( v10 < 0 )
                goto LABEL_58;
              v12 = pv;
              if ( v20 && pv )
              {
                v26 = 2LL * v38;
                memcpy_0(v20, pv, v26);
                v20 = (unsigned __int16 *)((char *)v20 + v26);
                *v20 = 0;
              }
              v21 += 2 * (unsigned int)v41 + 2;
            }
            goto LABEL_73;
          }
        }
      }
      goto LABEL_58;
    }
    goto LABEL_53;
  }
  v10 = NewString(2 * v7, a7);
  if ( v10 >= 0 )
  {
    v27 = *a7;
    for ( j = 0; j < v7; ++j )
    {
      if ( v27 )
      {
        for ( k = 0; k != 2; ++k )
          v27[k] = off_180031F60[*((unsigned __int8 *)a2 + j)][k];
        v27 += 2;
      }
    }
    if ( v27 )
      *v27 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002d934  push    rbp
0x18002d936  push    rbx
0x18002d937  push    rsi
0x18002d938  push    rdi
0x18002d939  push    r12
0x18002d93b  push    r13
0x18002d93d  push    r14
0x18002d93f  push    r15
0x18002d941  lea     rbp, [rsp-0A8h]
0x18002d949  sub     rsp, 1A8h
0x18002d950  mov     rax, cs:__security_cookie
0x18002d957  xor     rax, rsp
0x18002d95a  mov     [rbp+0E0h+var_50], rax
0x18002d961  mov     rbx, [rbp+0E0h+arg_30]
0x18002d968  mov     r14d, r8d
0x18002d96b  mov     [rsp+1E0h+var_188], r8d
0x18002d970  mov     r15, rdx
0x18002d973  mov     r13, rcx
0x18002d976  mov     [rsp+1E0h+var_180], r9d
0x18002d97b  xor     edi, edi
0x18002d97d  mov     [rsp+1E0h+var_174], 0Dh
0x18002d985  xor     edx, edx; Val
0x18002d987  mov     [rsp+1E0h+var_178], edi
0x18002d98b  mov     r8d, 90h; Size
0x18002d991  lea     rcx, [rsp+1E0h+var_170]; void *
0x18002d996  mov     r12d, r9d
0x18002d999  call    memset_0
0x18002d99e  mov     rax, [r13+0E8h]
0x18002d9a5  xor     r8d, r8d
0x18002d9a8  mov     [rsp+1E0h+var_170], rax
0x18002d9ad  lea     rax, [rsp+1E0h+var_180]
0x18002d9b2  mov     [rbp+0E0h+var_108], rax
0x18002d9b6  mov     esi, r8d
0x18002d9b9  mov     [rsp+1E0h+var_184], r8d
0x18002d9be  mov     [rsp+1E0h+pv], r8
0x18002d9c3  mov     [rsp+1E0h+var_1A0], r8d
0x18002d9c8  mov     [rsp+1E0h+var_19C], r8d
0x18002d9cd  mov     [rbx], r8
0x18002d9d0  test    r15, r15
0x18002d9d3  jz      loc_18002DEBF
0x18002d9d9  mov     ecx, dword ptr [rbp+0E0h+arg_20]; this
0x18002d9df  mov     eax, ecx
0x18002d9e1  sub     eax, 1
0x18002d9e4  jz      loc_18002DD99
0x18002d9ea  sub     eax, 1
0x18002d9ed  jz      loc_18002DD33
0x18002d9f3  sub     eax, 1
0x18002d9f6  jz      loc_18002DCC3
0x18002d9fc  sub     eax, 1
0x18002d9ff  jz      loc_18002DD33
0x18002da05  cmp     eax, 1
0x18002da08  jz      short loc_18002DA53
0x18002da0a  test    byte ptr cs:g_dwDebugFlags, 3
0x18002da11  jz      short loc_18002DA49
0x18002da13  mov     dword ptr [rsp+1E0h+var_1B0], r12d
0x18002da18  lea     rax, aTostringUnknow; "[ToString] Unknown data type %d for ID:"...
0x18002da1f  mov     dword ptr [rsp+1E0h+var_1B8], ecx
0x18002da23  lea     r9, aCwriterglobalh_0; "CWriterGlobalHelper::ToString"
0x18002da2a  mov     rcx, cs:g_pDebug
0x18002da31  lea     rdx, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002da38  mov     r8d, 6F7h
0x18002da3e  mov     [rsp+1E0h+var_1C0], rax
0x18002da43  call    cs:__imp_PuDbgPrintW
0x18002da49  mov     edi, 80070057h
0x18002da4e  jmp     loc_18002DEBF
0x18002da53  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002da57  mov     rsi, r12
0x18002da5a  inc     rsi
0x18002da5d  cmp     [r15+rsi*2], r8w
0x18002da62  jnz     short loc_18002DA5A
0x18002da64  lea     rax, [rsp+1E0h+var_1A0]
0x18002da69  mov     r8d, esi; unsigned int
0x18002da6c  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x18002da71  lea     r9, [rsp+1E0h+var_19C]; int *
0x18002da76  lea     rax, [rsp+1E0h+pv]
0x18002da7b  mov     rdx, r15; unsigned __int16 *
0x18002da7e  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x18002da83  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x18002da88  xor     edx, edx
0x18002da8a  mov     edi, eax
0x18002da8c  test    eax, eax
0x18002da8e  js      loc_18002DD8C
0x18002da94  mov     ecx, [rsp+1E0h+var_1A0]
0x18002da98  lea     r13d, [rdx+1]
0x18002da9c  mov     esi, esi
0x18002da9e  inc     rsi
0x18002daa1  lea     rsi, [r15+rsi*2]
0x18002daa5  mov     dword ptr [rsp+1E0h+var_190], ecx
0x18002daa9  cmp     dx, [rsi]
0x18002daac  jz      loc_18002DB3B
0x18002dab2  mov     eax, r14d
0x18002dab5  add     rax, r15
0x18002dab8  cmp     rsi, rax
0x18002dabb  jnb     short loc_18002DB3B
0x18002dabd  cmp     [rsp+1E0h+var_19C], edx
0x18002dac1  jz      short loc_18002DADE
0x18002dac3  mov     rcx, [rsp+1E0h+pv]; pv
0x18002dac8  test    rcx, rcx
0x18002dacb  jz      short loc_18002DADE
0x18002dacd  call    cs:__imp_CoTaskMemFree
0x18002dad3  xor     edx, edx
0x18002dad5  mov     [rsp+1E0h+pv], rdx
0x18002dada  mov     [rsp+1E0h+var_19C], edx
0x18002dade  mov     r14, r12
0x18002dae1  inc     r14
0x18002dae4  cmp     [rsi+r14*2], dx
0x18002dae9  jnz     short loc_18002DAE1
0x18002daeb  lea     rax, [rsp+1E0h+var_1A0]
0x18002daf0  mov     r8d, r14d; unsigned int
0x18002daf3  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x18002daf8  lea     r9, [rsp+1E0h+var_19C]; int *
0x18002dafd  lea     rax, [rsp+1E0h+pv]
0x18002db02  mov     rdx, rsi; unsigned __int16 *
0x18002db05  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x18002db0a  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x18002db0f  xor     edx, edx
0x18002db11  mov     edi, eax
0x18002db13  test    eax, eax
0x18002db15  js      loc_18002DD8C
0x18002db1b  mov     ecx, dword ptr [rsp+1E0h+var_190]
0x18002db1f  inc     r13d
0x18002db22  add     ecx, [rsp+1E0h+var_1A0]
0x18002db26  mov     eax, r14d
0x18002db29  mov     r14d, [rsp+1E0h+var_188]
0x18002db2e  lea     rsi, [rsi+rax*2]
0x18002db32  add     rsi, 2
0x18002db36  jmp     loc_18002DAA5
0x18002db3b  lea     ecx, [rcx+r13*4]
0x18002db3f  mov     rdx, rbx; unsigned __int16 **
0x18002db42  add     ecx, 0FFFFFFFCh
0x18002db45  add     ecx, r13d; unsigned int
0x18002db48  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002db4d  xor     edx, edx
0x18002db4f  mov     edi, eax
0x18002db51  test    eax, eax
0x18002db53  js      loc_18002DD8C
0x18002db59  mov     rax, r12
0x18002db5c  inc     rax
0x18002db5f  cmp     [r15+rax*2], dx
0x18002db64  jnz     short loc_18002DB5C
0x18002db66  mov     r14, [rbx]
0x18002db69  lea     rcx, [rsp+1E0h+var_1A0]
0x18002db6e  mov     [rsp+1E0h+var_1B8], rcx; unsigned int *
0x18002db73  lea     r9, [rsp+1E0h+var_19C]; int *
0x18002db78  lea     rcx, [rsp+1E0h+pv]; this
0x18002db7d  mov     [rsp+1E0h+var_190], rax
0x18002db82  mov     r8d, eax; unsigned int
0x18002db85  mov     [rsp+1E0h+var_1C0], rcx; unsigned __int16 **
0x18002db8a  mov     rdx, r15; unsigned __int16 *
0x18002db8d  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x18002db92  xor     edx, edx
0x18002db94  mov     edi, eax
0x18002db96  test    eax, eax
0x18002db98  js      loc_18002DD8C
0x18002db9e  mov     rsi, [rsp+1E0h+pv]
0x18002dba3  mov     r13, r15
0x18002dba6  test    r14, r14
0x18002dba9  jz      short loc_18002DBDE
0x18002dbab  test    rsi, rsi
0x18002dbae  jz      short loc_18002DBDE
0x18002dbb0  mov     eax, [rsp+1E0h+var_1A0]
0x18002dbb4  mov     rdx, rsi; Src
0x18002dbb7  mov     rcx, r14; void *
0x18002dbba  lea     rbx, [rax+rax]
0x18002dbbe  mov     r8, rbx; Size
0x18002dbc1  call    memcpy_0
0x18002dbc6  mov     r13d, dword ptr [rsp+1E0h+var_190]
0x18002dbcb  lea     rcx, [rbx+r14]
0x18002dbcf  xor     edx, edx
0x18002dbd1  mov     r14, rcx
0x18002dbd4  inc     r13
0x18002dbd7  mov     [rcx], dx
0x18002dbda  lea     r13, [r15+r13*2]
0x18002dbde  cmp     dx, [r13+0]
0x18002dbe3  jz      loc_18002DD91
0x18002dbe9  mov     eax, [rsp+1E0h+var_188]
0x18002dbed  add     rax, r15
0x18002dbf0  cmp     r13, rax
0x18002dbf3  jnb     loc_18002DD91
0x18002dbf9  test    r14, r14
0x18002dbfc  jz      short loc_18002DC22
0x18002dbfe  mov     ebx, cs:?g_cchMultiszSeperator@@3KA; ulong g_cchMultiszSeperator
0x18002dc04  lea     rdx, asc_18003D3B8; "\r\n\t\t\t"
0x18002dc0b  add     rbx, rbx
0x18002dc0e  mov     rcx, r14; void *
0x18002dc11  mov     r8, rbx; Size
0x18002dc14  call    memcpy_0
0x18002dc19  add     r14, rbx
0x18002dc1c  xor     edx, edx
0x18002dc1e  mov     [r14], dx
0x18002dc22  cmp     [rsp+1E0h+var_19C], edx
0x18002dc26  jz      short loc_18002DC41
0x18002dc28  test    rsi, rsi
0x18002dc2b  jz      short loc_18002DC41
0x18002dc2d  mov     rcx, rsi; pv
0x18002dc30  call    cs:__imp_CoTaskMemFree
0x18002dc36  xor     edx, edx
0x18002dc38  mov     [rsp+1E0h+pv], rdx
0x18002dc3d  mov     [rsp+1E0h+var_19C], edx
0x18002dc41  mov     rax, r12
0x18002dc44  inc     rax
0x18002dc47  cmp     [r13+rax*2+0], dx
0x18002dc4d  jnz     short loc_18002DC44
0x18002dc4f  lea     rcx, [rsp+1E0h+var_1A0]
0x18002dc54  mov     [rsp+1E0h+var_190], rax
0x18002dc59  mov     [rsp+1E0h+var_1B8], rcx; unsigned int *
0x18002dc5e  lea     r9, [rsp+1E0h+var_19C]; int *
0x18002dc63  lea     rcx, [rsp+1E0h+pv]; this
0x18002dc68  mov     r8d, eax; unsigned int
0x18002dc6b  mov     rdx, r13; unsigned __int16 *
0x18002dc6e  mov     [rsp+1E0h+var_1C0], rcx; unsigned __int16 **
0x18002dc73  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x18002dc78  xor     edx, edx
0x18002dc7a  mov     edi, eax
0x18002dc7c  test    eax, eax
0x18002dc7e  js      loc_18002DD8C
0x18002dc84  mov     rsi, [rsp+1E0h+pv]
0x18002dc89  test    r14, r14
0x18002dc8c  jz      short loc_18002DCB1
0x18002dc8e  test    rsi, rsi
0x18002dc91  jz      short loc_18002DCB1
0x18002dc93  mov     ebx, [rsp+1E0h+var_1A0]
0x18002dc97  mov     rdx, rsi; Src
0x18002dc9a  add     rbx, rbx
0x18002dc9d  mov     rcx, r14; void *
0x18002dca0  mov     r8, rbx; Size
0x18002dca3  call    memcpy_0
0x18002dca8  add     r14, rbx
0x18002dcab  xor     edx, edx
0x18002dcad  mov     [r14], dx
0x18002dcb1  mov     eax, dword ptr [rsp+1E0h+var_190]
0x18002dcb5  lea     r13, [r13+rax*2+0]
0x18002dcba  add     r13, 2
0x18002dcbe  jmp     loc_18002DBDE
0x18002dcc3  lea     ecx, [r14+r14]; unsigned int
0x18002dcc7  mov     rdx, rbx; unsigned __int16 **
0x18002dcca  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002dccf  mov     edi, eax
0x18002dcd1  xor     eax, eax
0x18002dcd3  test    edi, edi
0x18002dcd5  js      loc_18002DEBF
0x18002dcdb  mov     rdx, [rbx]
0x18002dcde  mov     r8d, eax
0x18002dce1  test    r14d, r14d
0x18002dce4  jz      short loc_18002DD22
0x18002dce6  test    rdx, rdx
0x18002dce9  jz      short loc_18002DD1A
0x18002dceb  mov     r10d, r8d
0x18002dcee  mov     r9, rax
0x18002dcf1  movzx   eax, byte ptr [r10+r15]
0x18002dcf6  lea     rcx, off_180031F60; "00"
0x18002dcfd  mov     rax, [rcx+rax*8]
0x18002dd01  movzx   ecx, word ptr [rax+r9*2]
0x18002dd06  mov     [rdx+r9*2], cx
0x18002dd0b  inc     r9
0x18002dd0e  cmp     r9, 2
0x18002dd12  jnz     short loc_18002DCF1
0x18002dd14  add     rdx, 4
0x18002dd18  xor     eax, eax
0x18002dd1a  inc     r8d
0x18002dd1d  cmp     r8d, r14d
0x18002dd20  jb      short loc_18002DCE6
0x18002dd22  test    rdx, rdx
0x18002dd25  jz      loc_18002DEBF
0x18002dd2b  mov     [rdx], ax
0x18002dd2e  jmp     loc_18002DEBF
0x18002dd33  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002dd37  inc     r12
0x18002dd3a  cmp     [r15+r12*2], r8w
0x18002dd3f  jnz     short loc_18002DD37
0x18002dd41  lea     rax, [rsp+1E0h+var_1A0]
0x18002dd46  mov     r8d, r12d; unsigned int
0x18002dd49  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x18002dd4e  lea     r9, [rsp+1E0h+var_19C]; int *
0x18002dd53  lea     rax, [rsp+1E0h+pv]
0x18002dd58  mov     rdx, r15; unsigned __int16 *
0x18002dd5b  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x18002dd60  call    ?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z; CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)
0x18002dd65  mov     edi, eax
0x18002dd67  test    eax, eax
0x18002dd69  js      short loc_18002DD8C
0x18002dd6b  mov     rsi, [rsp+1E0h+pv]
0x18002dd70  test    rsi, rsi
0x18002dd73  jz      short loc_18002DD91
0x18002dd75  mov     edx, [rsp+1E0h+var_1A0]; unsigned int
0x18002dd79  mov     r8, rbx; unsigned __int16 **
0x18002dd7c  mov     rcx, rsi; Src
0x18002dd7f  call    ?StringToNewString@@YAJPEAGKPEAPEAG@Z; StringToNewString(ushort *,ulong,ushort * *)
0x18002dd84  xor     r15d, r15d
0x18002dd87  jmp     loc_18002DEA8
0x18002dd8c  mov     rsi, [rsp+1E0h+pv]
0x18002dd91  xor     r15d, r15d
0x18002dd94  jmp     loc_18002DEAA
0x18002dd99  mov     rcx, [r13+30h]
0x18002dd9d  lea     rdx, [rsp+1E0h+var_184]
0x18002dda2  mov     r14d, [r15]
0x18002dda5  lea     r9, [rsp+1E0h+var_178]
0x18002ddaa  mov     [rsp+1E0h+var_1B0], rdx
0x18002ddaf  lea     rdx, [rsp+1E0h+var_170]
0x18002ddb4  mov     [rsp+1E0h+var_1B8], rdx
  ... truncated ...
```
