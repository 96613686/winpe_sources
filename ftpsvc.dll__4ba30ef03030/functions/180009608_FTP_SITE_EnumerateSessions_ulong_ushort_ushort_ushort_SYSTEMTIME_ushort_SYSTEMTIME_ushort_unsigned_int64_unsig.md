# FTP_SITE::EnumerateSessions(ulong *,ushort * * *,ushort * * *,ushort * * *,_SYSTEMTIME * *,ushort * * *,_SYSTEMTIME * *,ushort * * *,unsigned __int64 * *,unsigned __int64 * *,long * *)

- ea: `0x180009608`
- end: `0x180009d23`
- name: `?EnumerateSessions@FTP_SITE@@QEAAJPEAKPEAPEAPEAG11PEAPEAU_SYSTEMTIME@@121PEAPEA_K3PEAPEAJ@Z`
- size: `1819`
- prototype: `__int64 __fastcall(FTP_SITE *__hidden this, unsigned int *, unsigned __int16 ***, unsigned __int16 ***, unsigned __int16 ***, struct _SYSTEMTIME **, unsigned __int16 ***, struct _SYSTEMTIME **, unsigned __int16 ***, unsigned __int64 **, unsigned __int64 **, int **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800163f0`

## callees

- `0x180009608`
- `0x18000aba4`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180009780`
- `ole32!CoTaskMemAlloc` at `0x1800097b7`
- `ole32!CoTaskMemAlloc` at `0x1800097ec`
- `ole32!CoTaskMemAlloc` at `0x18000981e`
- `ole32!CoTaskMemAlloc` at `0x18000983f`
- `ole32!CoTaskMemAlloc` at `0x180009878`
- `ole32!CoTaskMemAlloc` at `0x180009899`
- `ole32!CoTaskMemAlloc` at `0x1800098ca`
- `ole32!CoTaskMemAlloc` at `0x1800098e8`
- `ole32!CoTaskMemAlloc` at `0x18000990c`
- `ole32!CoTaskMemAlloc` at `0x180009966`
- `ole32!CoTaskMemAlloc` at `0x180009780`
- `ole32!CoTaskMemAlloc` at `0x1800097b7`
- `ole32!CoTaskMemAlloc` at `0x1800097ec`
- `ole32!CoTaskMemAlloc` at `0x18000981e`
- `ole32!CoTaskMemAlloc` at `0x18000983f`
- `ole32!CoTaskMemAlloc` at `0x180009878`
- `ole32!CoTaskMemAlloc` at `0x180009899`
- `ole32!CoTaskMemAlloc` at `0x1800098ca`
- `ole32!CoTaskMemAlloc` at `0x1800098e8`
- `ole32!CoTaskMemAlloc` at `0x18000990c`
- `ole32!CoTaskMemAlloc` at `0x180009966`
- `ole32!CoTaskMemFree` at `0x180009b76`
- `ole32!CoTaskMemFree` at `0x180009b89`
- `ole32!CoTaskMemFree` at `0x180009b97`
- `ole32!CoTaskMemFree` at `0x180009bb3`
- `ole32!CoTaskMemFree` at `0x180009bcc`
- `ole32!CoTaskMemFree` at `0x180009be2`
- `ole32!CoTaskMemFree` at `0x180009bfd`
- `ole32!CoTaskMemFree` at `0x180009c15`
- `ole32!CoTaskMemFree` at `0x180009c2b`
- `ole32!CoTaskMemFree` at `0x180009c46`
- `ole32!CoTaskMemFree` at `0x180009c5e`
- `ole32!CoTaskMemFree` at `0x180009c7a`
- `ole32!CoTaskMemFree` at `0x180009c93`
- `ole32!CoTaskMemFree` at `0x180009cae`
- `ole32!CoTaskMemFree` at `0x180009cc6`
- `ole32!CoTaskMemFree` at `0x180009cd9`
- `ole32!CoTaskMemFree` at `0x180009b76`
- `ole32!CoTaskMemFree` at `0x180009b89`
- `ole32!CoTaskMemFree` at `0x180009b97`
- `ole32!CoTaskMemFree` at `0x180009bb3`
- `ole32!CoTaskMemFree` at `0x180009bcc`
- `ole32!CoTaskMemFree` at `0x180009be2`
- `ole32!CoTaskMemFree` at `0x180009bfd`
- `ole32!CoTaskMemFree` at `0x180009c15`
- `ole32!CoTaskMemFree` at `0x180009c2b`
- `ole32!CoTaskMemFree` at `0x180009c46`
- `ole32!CoTaskMemFree` at `0x180009c5e`
- `ole32!CoTaskMemFree` at `0x180009c7a`
- `ole32!CoTaskMemFree` at `0x180009c93`
- `ole32!CoTaskMemFree` at `0x180009cae`
- `ole32!CoTaskMemFree` at `0x180009cc6`
- `ole32!CoTaskMemFree` at `0x180009cd9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009757`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009757`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000973e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000973e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009b63`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009b63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009700`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009700`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009ce8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009cf7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009ce8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009cf7`

## pseudocode

```c
__int64 __fastcall FTP_SITE::EnumerateSessions(
        FTP_SITE *this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        unsigned __int16 ***a4,
        unsigned __int16 ***a5,
        struct _SYSTEMTIME **a6,
        unsigned __int16 ***a7,
        struct _SYSTEMTIME **a8,
        unsigned __int16 ***a9,
        unsigned __int64 **a10,
        unsigned __int64 **a11,
        int **a12)
{
  unsigned __int16 **v13; // r12
  unsigned __int16 **v14; // rbp
  unsigned __int16 **v15; // rsi
  unsigned __int16 **v16; // r14
  unsigned __int16 **v17; // r13
  unsigned __int64 *v18; // rdi
  unsigned int v19; // r15d
  __int64 v20; // rax
  int v21; // ebx
  unsigned __int16 **v22; // rax
  unsigned __int16 **v23; // rax
  unsigned __int16 **v24; // rax
  unsigned __int16 **v25; // rax
  unsigned __int16 **v26; // rax
  FTP_SITE *v27; // rax
  char *v28; // rsi
  __int64 v29; // rbx
  const unsigned __int16 *v30; // rax
  __int64 i; // rdi
  unsigned __int16 *v32; // rcx
  __int64 j; // rdi
  unsigned __int16 *v34; // rcx
  __int64 k; // rdi
  unsigned __int16 *v36; // rcx
  __int64 m; // rdi
  unsigned __int16 *v38; // rcx
  __int64 n; // rdi
  unsigned __int16 *v40; // rcx
  unsigned __int16 *v42; // [rsp+60h] [rbp-1A8h]
  unsigned __int16 **v43; // [rsp+68h] [rbp-1A0h]
  int *pv; // [rsp+70h] [rbp-198h]
  unsigned __int64 *v45; // [rsp+78h] [rbp-190h]
  struct _SYSTEMTIME *v46; // [rsp+80h] [rbp-188h]
  struct _SYSTEMTIME *v47; // [rsp+88h] [rbp-180h]
  unsigned __int16 **v48; // [rsp+90h] [rbp-178h]
  unsigned __int16 **v49; // [rsp+98h] [rbp-170h]
  unsigned __int64 *v50; // [rsp+A0h] [rbp-168h]
  FTP_SITE **v51; // [rsp+A8h] [rbp-160h]
  char *v53; // [rsp+B8h] [rbp-150h]
  FTP_SITE *v54; // [rsp+C0h] [rbp-148h]
  CReaderWriterLock3 *v57; // [rsp+118h] [rbp-F0h]
  _BYTE v58[56]; // [rsp+120h] [rbp-E8h] BYREF
  _BYTE v59[56]; // [rsp+158h] [rbp-B0h] BYREF
  _OWORD v60[2]; // [rsp+190h] [rbp-78h] BYREF
  __int64 v61; // [rsp+1B0h] [rbp-58h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v47 = 0;
  v16 = 0;
  v46 = 0;
  v17 = 0;
  v45 = 0;
  v18 = 0;
  pv = 0;
  v19 = 0;
  STRU::STRU(v59);
  v42 = 0;
  memset(v60, 0, sizeof(v60));
  v61 = 0;
  STRU::STRU((STRU *)v58, (unsigned __int16 *)v60, 0x14u);
  v57 = (FTP_SITE *)((char *)this + 200);
  CReaderWriterLock3::ReadLock((FTP_SITE *)((char *)this + 200));
  v20 = *((unsigned int *)this + 64);
  if ( (_DWORD)v20 )
  {
    v22 = (unsigned __int16 **)CoTaskMemAlloc(8 * v20);
    v13 = v22;
    if ( !v22 )
      goto LABEL_4;
    memset_0(v22, 0, 8LL * *((unsigned int *)this + 64));
    v23 = (unsigned __int16 **)CoTaskMemAlloc(8LL * *((unsigned int *)this + 64));
    v14 = v23;
    v49 = v23;
    if ( !v23 )
      goto LABEL_4;
    memset_0(v23, 0, 8LL * *((unsigned int *)this + 64));
    v24 = (unsigned __int16 **)CoTaskMemAlloc(8LL * *((unsigned int *)this + 64));
    v15 = v24;
    v43 = v24;
    if ( !v24 )
      goto LABEL_4;
    memset_0(v24, 0, 8LL * *((unsigned int *)this + 64));
    v47 = (struct _SYSTEMTIME *)CoTaskMemAlloc(16LL * *((unsigned int *)this + 64));
    if ( !v47 )
      goto LABEL_4;
    v25 = (unsigned __int16 **)CoTaskMemAlloc(8LL * *((unsigned int *)this + 64));
    v16 = v25;
    v48 = v25;
    if ( !v25 )
      goto LABEL_4;
    memset_0(v25, 0, 8LL * *((unsigned int *)this + 64));
    v46 = (struct _SYSTEMTIME *)CoTaskMemAlloc(16LL * *((unsigned int *)this + 64));
    if ( !v46 )
      goto LABEL_4;
    v26 = (unsigned __int16 **)CoTaskMemAlloc(8LL * *((unsigned int *)this + 64));
    v17 = v26;
    if ( v26
      && (memset_0(v26, 0, 8LL * *((unsigned int *)this + 64)),
          (v45 = (unsigned __int64 *)CoTaskMemAlloc(8LL * *((unsigned int *)this + 64))) != 0)
      && (v18 = (unsigned __int64 *)CoTaskMemAlloc(8LL * *((unsigned int *)this + 64)), (v50 = v18) != 0)
      && (pv = (int *)CoTaskMemAlloc(4LL * *((unsigned int *)this + 64))) != 0 )
    {
      v54 = (FTP_SITE *)((char *)this + 240);
      v27 = (FTP_SITE *)*((_QWORD *)this + 30);
      v51 = (FTP_SITE **)v27;
      if ( v27 == (FTP_SITE *)((char *)this + 240) )
      {
LABEL_20:
        *a2 = v19;
        *a4 = v13;
        *a3 = v14;
        *a5 = v15;
        *a6 = v47;
        *a7 = v16;
        *a8 = v46;
        *a9 = v17;
        *a10 = v45;
        *a11 = v18;
        *a12 = pv;
        v13 = 0;
        v14 = 0;
        v15 = 0;
        v47 = 0;
        v16 = 0;
        v46 = 0;
        v17 = 0;
        v45 = 0;
        v18 = 0;
        pv = 0;
        v19 = 0;
        v21 = 0;
        v42 = 0;
      }
      else
      {
        while ( 1 )
        {
          v28 = (char *)v27 - 112;
          v53 = (char *)v27 - 112;
          v29 = (*(unsigned int (__fastcall **)(__int64))(*((_QWORD *)v27 - 14) + 72LL))((__int64)v27 - 112) + 1;
          v42 = (unsigned __int16 *)CoTaskMemAlloc(2 * v29);
          if ( !v42 )
            break;
          v30 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v28 + 64LL))(v28);
          v21 = StringCchCopyNW(v42, (unsigned int)v29, v30, (unsigned int)v29);
          if ( v21 < 0 )
            goto LABEL_22;
          v14[v19] = v42;
          v42 = 0;
          v21 = (*(__int64 (__fastcall **)(char *, unsigned __int16 **, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, unsigned __int64 *, unsigned __int64 *, int *))(*(_QWORD *)v28 + 56LL))(
                  v53,
                  &v13[v19],
                  &v43[v19],
                  &v47[v19],
                  &v16[v19],
                  &v46[v19],
                  &v17[v19],
                  &v45[v19],
                  &v18[v19],
                  &pv[v19]);
          v16 = v48;
          v14 = v49;
          v18 = v50;
          if ( v21 < 0 )
            goto LABEL_22;
          ++v19;
          v27 = *v51;
          v51 = (FTP_SITE **)v27;
          if ( v27 == v54 )
          {
            v15 = v43;
            goto LABEL_20;
          }
        }
        v21 = -2147024882;
LABEL_22:
        v15 = v43;
      }
    }
    else
    {
LABEL_4:
      v21 = -2147024882;
    }
  }
  else
  {
    *a2 = 0;
    v21 = 0;
  }
  CReaderWriterLock3::ReadUnlock(v57);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v45 )
    CoTaskMemFree(v45);
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v17 )
  {
    for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
    {
      v32 = v17[i];
      if ( v32 )
      {
        CoTaskMemFree(v32);
        v17[i] = 0;
      }
    }
    CoTaskMemFree(v17);
  }
  if ( v46 )
    CoTaskMemFree(v46);
  if ( v16 )
  {
    for ( j = 0; (unsigned int)j < v19; j = (unsigned int)(j + 1) )
    {
      v34 = v16[j];
      if ( v34 )
      {
        CoTaskMemFree(v34);
        v16[j] = 0;
      }
    }
    CoTaskMemFree(v16);
  }
  if ( v47 )
    CoTaskMemFree(v47);
  if ( v15 )
  {
    for ( k = 0; (unsigned int)k < v19; k = (unsigned int)(k + 1) )
    {
      v36 = v15[k];
      if ( v36 )
      {
        CoTaskMemFree(v36);
        v15[k] = 0;
      }
    }
    CoTaskMemFree(v15);
  }
  if ( v14 )
  {
    for ( m = 0; (unsigned int)m < v19; m = (unsigned int)(m + 1) )
    {
      v38 = v14[m];
      if ( v38 )
      {
        CoTaskMemFree(v38);
        v14[m] = 0;
      }
    }
    CoTaskMemFree(v14);
  }
  if ( v13 )
  {
    for ( n = 0; (unsigned int)n < v19; n = (unsigned int)(n + 1) )
    {
      v40 = v13[n];
      if ( v40 )
      {
        CoTaskMemFree(v40);
        v13[n] = 0;
      }
    }
    CoTaskMemFree(v13);
  }
  if ( v42 )
    CoTaskMemFree(v42);
  STRU::~STRU(v58);
  STRU::~STRU(v59);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180009608  push    rbx
0x18000960a  push    rbp
0x18000960b  push    rsi
0x18000960c  push    rdi
0x18000960d  push    r12
0x18000960f  push    r13
0x180009611  push    r14
0x180009613  push    r15
0x180009615  sub     rsp, 1C8h
0x18000961c  mov     rax, cs:__security_cookie
0x180009623  xor     rax, rsp
0x180009626  mov     [rsp+208h+var_50], rax
0x18000962e  mov     [rsp+208h+var_140], r9
0x180009636  mov     [rsp+208h+var_138], r8
0x18000963e  mov     [rsp+208h+var_158], rdx
0x180009646  mov     rbx, rcx
0x180009649  mov     rax, [rsp+208h+arg_20]
0x180009651  mov     [rsp+208h+var_130], rax
0x180009659  mov     rax, [rsp+208h+arg_28]
0x180009661  mov     [rsp+208h+var_128], rax
0x180009669  mov     rax, [rsp+208h+arg_30]
0x180009671  mov     [rsp+208h+var_120], rax
0x180009679  mov     rax, [rsp+208h+arg_38]
0x180009681  mov     [rsp+208h+var_118], rax
0x180009689  mov     rax, [rsp+208h+arg_40]
0x180009691  mov     [rsp+208h+var_110], rax
0x180009699  mov     rax, [rsp+208h+arg_48]
0x1800096a1  mov     [rsp+208h+var_108], rax
0x1800096a9  mov     rax, [rsp+208h+arg_50]
0x1800096b1  mov     [rsp+208h+var_100], rax
0x1800096b9  mov     rax, [rsp+208h+arg_58]
0x1800096c1  mov     [rsp+208h+var_F8], rax
0x1800096c9  xor     r12d, r12d
0x1800096cc  mov     ebp, r12d
0x1800096cf  mov     esi, r12d
0x1800096d2  mov     [rsp+208h+var_180], r12
0x1800096da  mov     r14d, r12d
0x1800096dd  mov     [rsp+208h+var_188], r12
0x1800096e5  mov     r13d, r12d
0x1800096e8  mov     [rsp+208h+var_190], r12
0x1800096ed  mov     edi, r12d
0x1800096f0  mov     [rsp+208h+pv], r12
0x1800096f5  mov     r15d, r12d
0x1800096f8  lea     rcx, [rsp+208h+var_B0]
0x180009700  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009706  nop
0x180009707  mov     [rsp+208h+var_1A8], r12
0x18000970c  xorps   xmm0, xmm0
0x18000970f  xor     eax, eax
0x180009711  movups  [rsp+208h+var_78], xmm0
0x180009719  movups  [rsp+208h+var_68], xmm0
0x180009721  mov     [rsp+208h+var_58], rax
0x180009729  lea     r8d, [r12+14h]
0x18000972e  lea     rdx, [rsp+208h+var_78]
0x180009736  lea     rcx, [rsp+208h+var_E8]
0x18000973e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009744  nop
0x180009745  lea     rax, [rbx+0C8h]
0x18000974c  mov     [rsp+208h+var_F0], rax
0x180009754  mov     rcx, rax
0x180009757  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000975d  mov     eax, [rbx+100h]
0x180009763  test    eax, eax
0x180009765  jnz     short loc_180009779
0x180009767  mov     rax, [rsp+208h+var_158]
0x18000976f  mov     [rax], r12d
0x180009772  xor     ebx, ebx
0x180009774  jmp     loc_180009B5B
0x180009779  mov     rcx, rax
0x18000977c  shl     rcx, 3; cb
0x180009780  call    cs:__imp_CoTaskMemAlloc
0x180009786  mov     r12, rax
0x180009789  test    rax, rax
0x18000978c  jnz     short loc_180009798
0x18000978e  mov     ebx, 8007000Eh
0x180009793  jmp     loc_180009B5B
0x180009798  mov     r8d, [rbx+100h]
0x18000979f  shl     r8, 3; Size
0x1800097a3  xor     edx, edx; Val
0x1800097a5  mov     rcx, r12; void *
0x1800097a8  call    memset_0
0x1800097ad  mov     ecx, [rbx+100h]
0x1800097b3  shl     rcx, 3; cb
0x1800097b7  call    cs:__imp_CoTaskMemAlloc
0x1800097bd  mov     rbp, rax
0x1800097c0  mov     [rsp+208h+var_170], rax
0x1800097c8  test    rax, rax
0x1800097cb  jz      short loc_18000978E
0x1800097cd  mov     r8d, [rbx+100h]
0x1800097d4  shl     r8, 3; Size
0x1800097d8  xor     edx, edx; Val
0x1800097da  mov     rcx, rax; void *
0x1800097dd  call    memset_0
0x1800097e2  mov     ecx, [rbx+100h]
0x1800097e8  shl     rcx, 3; cb
0x1800097ec  call    cs:__imp_CoTaskMemAlloc
0x1800097f2  mov     rsi, rax
0x1800097f5  mov     [rsp+208h+var_1A0], rax
0x1800097fa  test    rax, rax
0x1800097fd  jz      short loc_18000978E
0x1800097ff  mov     r8d, [rbx+100h]
0x180009806  shl     r8, 3; Size
0x18000980a  xor     edx, edx; Val
0x18000980c  mov     rcx, rax; void *
0x18000980f  call    memset_0
0x180009814  mov     ecx, [rbx+100h]
0x18000981a  shl     rcx, 4; cb
0x18000981e  call    cs:__imp_CoTaskMemAlloc
0x180009824  mov     [rsp+208h+var_180], rax
0x18000982c  test    rax, rax
0x18000982f  jz      loc_18000978E
0x180009835  mov     ecx, [rbx+100h]
0x18000983b  shl     rcx, 3; cb
0x18000983f  call    cs:__imp_CoTaskMemAlloc
0x180009845  mov     r14, rax
0x180009848  mov     [rsp+208h+var_178], rax
0x180009850  test    rax, rax
0x180009853  jz      loc_18000978E
0x180009859  mov     r8d, [rbx+100h]
0x180009860  shl     r8, 3; Size
0x180009864  xor     edx, edx; Val
0x180009866  mov     rcx, rax; void *
0x180009869  call    memset_0
0x18000986e  mov     ecx, [rbx+100h]
0x180009874  shl     rcx, 4; cb
0x180009878  call    cs:__imp_CoTaskMemAlloc
0x18000987e  mov     [rsp+208h+var_188], rax
0x180009886  test    rax, rax
0x180009889  jz      loc_18000978E
0x18000988f  mov     ecx, [rbx+100h]
0x180009895  shl     rcx, 3; cb
0x180009899  call    cs:__imp_CoTaskMemAlloc
0x18000989f  mov     r13, rax
0x1800098a2  test    rax, rax
0x1800098a5  jz      loc_18000978E
0x1800098ab  mov     r8d, [rbx+100h]
0x1800098b2  shl     r8, 3; Size
0x1800098b6  xor     edx, edx; Val
0x1800098b8  mov     rcx, rax; void *
0x1800098bb  call    memset_0
0x1800098c0  mov     ecx, [rbx+100h]
0x1800098c6  shl     rcx, 3; cb
0x1800098ca  call    cs:__imp_CoTaskMemAlloc
0x1800098d0  mov     [rsp+208h+var_190], rax
0x1800098d5  test    rax, rax
0x1800098d8  jz      loc_18000978E
0x1800098de  mov     ecx, [rbx+100h]
0x1800098e4  shl     rcx, 3; cb
0x1800098e8  call    cs:__imp_CoTaskMemAlloc
0x1800098ee  mov     rdi, rax
0x1800098f1  mov     [rsp+208h+var_168], rax
0x1800098f9  test    rax, rax
0x1800098fc  jz      loc_18000978E
0x180009902  mov     ecx, [rbx+100h]
0x180009908  shl     rcx, 2; cb
0x18000990c  call    cs:__imp_CoTaskMemAlloc
0x180009912  mov     [rsp+208h+pv], rax
0x180009917  test    rax, rax
0x18000991a  jz      loc_18000978E
0x180009920  lea     rcx, [rbx+0F0h]
0x180009927  mov     [rsp+208h+var_148], rcx
0x18000992f  mov     rax, [rcx]
0x180009932  mov     [rsp+208h+var_160], rax
0x18000993a  cmp     rax, rcx
0x18000993d  jz      loc_180009A87
0x180009943  lea     rsi, [rax-70h]
0x180009947  mov     [rsp+208h+var_150], rsi
0x18000994f  mov     rax, [rsi]
0x180009952  mov     rcx, rsi
0x180009955  mov     rax, [rax+48h]
0x180009959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995e  inc     eax
0x180009960  mov     ebx, eax
0x180009962  lea     rcx, [rax+rax]; cb
0x180009966  call    cs:__imp_CoTaskMemAlloc
0x18000996c  mov     [rsp+208h+var_1A8], rax
0x180009971  test    rax, rax
0x180009974  jz      loc_180009B51
0x18000997a  mov     rcx, [rsi]
0x18000997d  mov     rax, [rcx+40h]
0x180009981  mov     rcx, rsi
0x180009984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009989  mov     r8, rax; unsigned __int16 *
0x18000998c  mov     r9d, ebx; unsigned __int64
0x18000998f  mov     edx, ebx; unsigned __int64
0x180009991  mov     rcx, [rsp+208h+var_1A8]; unsigned __int16 *
0x180009996  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000999b  mov     ebx, eax
0x18000999d  test    eax, eax
0x18000999f  js      loc_180009B56
0x1800099a5  mov     edx, r15d
0x1800099a8  mov     rax, [rsp+208h+var_1A8]
0x1800099ad  mov     [rbp+rdx*8+0], rax
0x1800099b2  mov     [rsp+208h+var_1A8], 0
0x1800099bb  mov     eax, r15d
0x1800099be  shl     rax, 4
0x1800099c2  mov     r10, [rsi]
0x1800099c5  mov     rcx, [rsp+208h+pv]
0x1800099ca  lea     r11, [rcx+rdx*4]
0x1800099ce  lea     rbx, [rdi+rdx*8]
0x1800099d2  mov     rcx, [rsp+208h+var_190]
0x1800099d7  lea     rdi, [rcx+rdx*8]
0x1800099db  lea     rsi, ds:0[rdx*8]
0x1800099e3  add     rsi, r13
0x1800099e6  mov     rbp, [rsp+208h+var_188]
0x1800099ee  add     rbp, rax
0x1800099f1  lea     r14, [r14+rdx*8]
0x1800099f5  mov     r9, [rsp+208h+var_180]
0x1800099fd  add     r9, rax
0x180009a00  mov     rax, [rsp+208h+var_1A0]
0x180009a05  lea     r8, [rax+rdx*8]
0x180009a09  lea     rdx, [r12+rdx*8]
0x180009a0d  mov     [rsp+208h+var_1C0], r11
0x180009a12  mov     [rsp+208h+var_1C8], rbx
0x180009a17  mov     [rsp+208h+var_1D0], rdi
0x180009a1c  mov     [rsp+208h+var_1D8], rsi
0x180009a21  mov     [rsp+208h+var_1E0], rbp
0x180009a26  mov     [rsp+208h+var_1E8], r14
0x180009a2b  mov     rcx, [rsp+208h+var_150]
0x180009a33  mov     rax, [r10+38h]
0x180009a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a3c  mov     ebx, eax
0x180009a3e  mov     r14, [rsp+208h+var_178]
0x180009a46  mov     rbp, [rsp+208h+var_170]
0x180009a4e  mov     rdi, [rsp+208h+var_168]
0x180009a56  test    eax, eax
0x180009a58  js      loc_180009B56
0x180009a5e  inc     r15d
0x180009a61  mov     rax, [rsp+208h+var_160]
0x180009a69  mov     rax, [rax]
0x180009a6c  mov     [rsp+208h+var_160], rax
0x180009a74  cmp     rax, [rsp+208h+var_148]
0x180009a7c  jnz     loc_180009943
0x180009a82  mov     rsi, [rsp+208h+var_1A0]
0x180009a87  mov     rax, [rsp+208h+var_158]
0x180009a8f  mov     [rax], r15d
0x180009a92  mov     rax, [rsp+208h+var_140]
0x180009a9a  mov     [rax], r12
0x180009a9d  mov     rax, [rsp+208h+var_138]
0x180009aa5  mov     [rax], rbp
0x180009aa8  mov     rax, [rsp+208h+var_130]
0x180009ab0  mov     [rax], rsi
0x180009ab3  mov     rax, [rsp+208h+var_180]
0x180009abb  mov     rcx, [rsp+208h+var_128]
0x180009ac3  mov     [rcx], rax
0x180009ac6  mov     rax, [rsp+208h+var_120]
0x180009ace  mov     [rax], r14
0x180009ad1  mov     rax, [rsp+208h+var_188]
0x180009ad9  mov     rcx, [rsp+208h+var_118]
0x180009ae1  mov     [rcx], rax
0x180009ae4  mov     rax, [rsp+208h+var_110]
0x180009aec  mov     [rax], r13
0x180009aef  mov     rax, [rsp+208h+var_190]
0x180009af4  mov     rcx, [rsp+208h+var_108]
0x180009afc  mov     [rcx], rax
0x180009aff  mov     rax, [rsp+208h+var_100]
0x180009b07  mov     [rax], rdi
0x180009b0a  mov     rax, [rsp+208h+pv]
0x180009b0f  mov     rcx, [rsp+208h+var_F8]
0x180009b17  mov     [rcx], rax
0x180009b1a  xor     eax, eax
0x180009b1c  mov     r12d, eax
0x180009b1f  mov     ebp, eax
0x180009b21  mov     esi, eax
0x180009b23  mov     [rsp+208h+var_180], rax
0x180009b2b  mov     r14d, eax
0x180009b2e  mov     [rsp+208h+var_188], rax
0x180009b36  mov     r13d, eax
0x180009b39  mov     [rsp+208h+var_190], rax
0x180009b3e  mov     edi, eax
0x180009b40  mov     [rsp+208h+pv], rax
0x180009b45  mov     r15d, eax
0x180009b48  mov     ebx, eax
0x180009b4a  mov     [rsp+208h+var_1A8], rax
0x180009b4f  jmp     short loc_180009B5B
0x180009b51  mov     ebx, 8007000Eh
0x180009b56  mov     rsi, [rsp+208h+var_1A0]
0x180009b5b  mov     rcx, [rsp+208h+var_F0]
0x180009b63  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180009b69  mov     rax, [rsp+208h+pv]
0x180009b6e  test    rax, rax
0x180009b71  jz      short loc_180009B7C
0x180009b73  mov     rcx, rax; pv
0x180009b76  call    cs:__imp_CoTaskMemFree
0x180009b7c  mov     rax, [rsp+208h+var_190]
0x180009b81  test    rax, rax
0x180009b84  jz      short loc_180009B8F
0x180009b86  mov     rcx, rax; pv
0x180009b89  call    cs:__imp_CoTaskMemFree
0x180009b8f  test    rdi, rdi
0x180009b92  jz      short loc_180009B9D
0x180009b94  mov     rcx, rdi; pv
0x180009b97  call    cs:__imp_CoTaskMemFree
0x180009b9d  test    r13, r13
0x180009ba0  jz      short loc_180009BD2
0x180009ba2  xor     edi, edi
0x180009ba4  test    r15d, r15d
0x180009ba7  jz      short loc_180009BC9
0x180009ba9  mov     rcx, [r13+rdi*8+0]; pv
0x180009bae  test    rcx, rcx
  ... truncated ...
```
