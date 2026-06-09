# CADTGRowset::arReadProperties(uchar *,ushort)

- ea: `0x18000fbbc`
- end: `0x180010404`
- name: `?arReadProperties@CADTGRowset@@AEAAXPEAEG@Z`
- size: `2120`
- prototype: `void __fastcall(CADTGRowset *__hidden this, unsigned __int8 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x180010564`
- `0x180010658`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800028b8`
- `0x18000fbbc`
- `0x180016584`
- `0x18001b008`
- `0x18002d9a4`
- `0x18002dca4`
- `0x18002f0aa`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001025e`
- `ole32!CoTaskMemFree` at `0x18001027c`
- `ole32!CoTaskMemFree` at `0x18001028e`
- `ole32!CoTaskMemFree` at `0x18001025e`
- `ole32!CoTaskMemFree` at `0x18001027c`
- `ole32!CoTaskMemFree` at `0x18001028e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001020f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001020f`
- `OLEAUT32!__imp_VariantInit` at `0x18000ffa3`
- `OLEAUT32!__imp_VariantInit` at `0x18000ffa3`
- `OLEAUT32!__imp_VariantClear` at `0x180010345`
- `OLEAUT32!__imp_VariantClear` at `0x180010345`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CADTGRowset::arReadProperties(CADTGRowset *this, unsigned __int8 *a2, unsigned __int16 a3)
{
  int v5; // eax
  int v6; // r14d
  unsigned int v7; // eax
  unsigned __int8 *v8; // r12
  unsigned __int16 v9; // si
  __int64 v10; // r15
  unsigned __int128 v11; // rax
  unsigned __int64 v12; // kr10_8
  struct tagDBPROPSET *v13; // r14
  unsigned int v14; // edx
  unsigned __int16 v15; // ax
  unsigned __int16 v16; // r15
  int v17; // eax
  int v18; // r15d
  __int64 v19; // r15
  GUID v20; // xmm0
  unsigned __int16 v21; // si
  int v22; // eax
  int v23; // r15d
  unsigned __int64 v24; // rcx
  unsigned __int128 v25; // rax
  unsigned __int8 *v26; // rax
  unsigned __int16 v27; // cx
  __int64 v28; // r15
  __int64 v29; // r13
  int v30; // eax
  int v31; // r15d
  unsigned __int16 v32; // si
  int v33; // eax
  int v34; // r15d
  __int64 v35; // r13
  __int16 v36; // r9
  unsigned int j; // edx
  int v38; // eax
  int v39; // r15d
  __int16 v40; // ax
  int v41; // eax
  int v42; // r15d
  int v43; // eax
  int v44; // r15d
  int v45; // eax
  int v46; // r15d
  BSTR v47; // rax
  unsigned int i; // r15d
  unsigned __int16 v49; // r12
  __int64 v50; // r13
  __int64 v51; // rsi
  unsigned __int16 k; // r15
  int v53; // esi
  unsigned __int16 v54; // [rsp+40h] [rbp-B8h]
  unsigned __int16 v55; // [rsp+42h] [rbp-B6h]
  unsigned __int16 v56; // [rsp+44h] [rbp-B4h]
  unsigned __int16 v57; // [rsp+48h] [rbp-B0h]
  unsigned int v58; // [rsp+4Ch] [rbp-ACh] BYREF
  int v59; // [rsp+50h] [rbp-A8h]
  __int64 v60; // [rsp+58h] [rbp-A0h]
  __int64 v61; // [rsp+60h] [rbp-98h]
  LPVOID v62; // [rsp+68h] [rbp-90h] BYREF
  VARIANTARG *v63; // [rsp+70h] [rbp-88h]
  __int64 v64; // [rsp+78h] [rbp-80h]
  LPVOID pv; // [rsp+80h] [rbp-78h] BYREF
  CADTGRowset *v66; // [rsp+88h] [rbp-70h]
  struct tagDBPROPSET *v67; // [rsp+90h] [rbp-68h]
  int v68; // [rsp+98h] [rbp-60h] BYREF
  _OWORD v69[2]; // [rsp+A0h] [rbp-58h] BYREF

  try
  {
    v66 = this;
    v59 = 0;
    v67 = 0;
    v58 = 0;
    if ( a3 < 2u )
    {
      v5 = Exit(-2147467259, 0x85u);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800497D0[0] )
            bidTraceW(off_1800491C8[0], 875520, off_1800497D0[0], (unsigned int)v5, 855);
        }
        ThrowHR(v6);
      }
    }
    v7 = *(unsigned __int16 *)a2;
    v55 = *(_WORD *)a2;
    v57 = *(_WORD *)a2;
    v8 = a2 + 2;
    v9 = a3 - 2;
    v10 = v7;
    v12 = v7;
    v11 = v7 * (unsigned __int128)0x20uLL;
    if ( !is_mul_ok(v12, 0x20u) )
      LODWORD(v11) = -1;
    v13 = (struct tagDBPROPSET *)MMMAlloc(v11, DWORD2(v11));
    v67 = v13;
    OnNullThrowOOM(v13);
    memset_0(v13, 0, 32 * v10);
    v15 = 0;
    v54 = 0;
LABEL_11:
    v16 = v55;
    if ( v15 < v55 )
    {
      memset(v69, 0, sizeof(v69));
      v62 = 0;
      pv = 0;
      if ( v9 < 0x10u )
      {
        v17 = Exit(-2147467259, 0x85u);
        v18 = v17;
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800497C8[0] )
            bidTraceW(off_1800491C8[0], 896000, off_1800497C8[0], (unsigned int)v17, 875);
          ThrowHR(v18);
        }
        v15 = v54;
      }
      v19 = 32LL * v15;
      v64 = v19;
      v20 = *(GUID *)v8;
      *(GUID *)((char *)&v13->guidPropertySet + v19) = *(GUID *)v8;
      v21 = v9 - 16;
      *(GUID *)((char *)v69 + 12) = v20;
      DWORD2(v69[0]) = 0;
      *(_QWORD *)&v69[0] = 0;
      v58 = 0;
      (*(void (__fastcall **)(_QWORD, __int64, _OWORD *, unsigned int *, LPVOID *, LPVOID *))(**((_QWORD **)v66 + 67)
                                                                                            + 32LL))(
        *((_QWORD *)v66 + 67),
        1,
        v69,
        &v58,
        &v62,
        &pv);
      if ( v21 < 2u )
      {
        v22 = Exit(-2147467259, 0x85u);
        v23 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800497C0[0] )
            bidTraceW(off_1800491C8[0], 912384, off_1800497C0[0], (unsigned int)v22, 891);
          ThrowHR(v23);
        }
        v19 = v64;
      }
      v24 = *((unsigned __int16 *)v8 + 8);
      *(ULONG *)((char *)&v13->cProperties + v19) = v24;
      v8 += 18;
      v9 = v21 - 2;
      v25 = v24 * (unsigned __int128)0x48uLL;
      if ( !is_mul_ok(v24, 0x48u) )
        LODWORD(v25) = -1;
      v26 = MMMAlloc(v25, DWORD2(v25));
      *(DBPROP **)((char *)&v13->rgProperties + v19) = (DBPROP *)v26;
      OnNullThrowOOM(v26);
      v27 = 0;
      while ( 1 )
      {
        v56 = v27;
        if ( v27 >= *(ULONG *)((char *)&v13->cProperties + v19) )
        {
          for ( i = 0; i < v58; ++i )
            CoTaskMemFree(*((LPVOID *)v62 + 4 * i));
          CoTaskMemFree(pv);
          CoTaskMemFree(v62);
          v15 = ++v54;
          goto LABEL_11;
        }
        v28 = 9LL * v27;
        v60 = v28;
        v29 = *(__int64 *)((char *)&v13->rgProperties + v64);
        v61 = v29;
        *(_DWORD *)(v29 + 8 * v28 + 4) = 0;
        if ( v9 < 4u )
        {
          v30 = Exit(-2147467259, 0x85u);
          v31 = v30;
          if ( v30 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1800497B8[0] )
              bidTraceW(off_1800491C8[0], 930816, off_1800497B8[0], (unsigned int)v30, 909);
            ThrowHR(v31);
          }
          v28 = v60;
        }
        *(_DWORD *)(v29 + 8 * v28) = *(_DWORD *)v8;
        v32 = v9 - 4;
        if ( v32 < 2u )
        {
          v33 = Exit(-2147467259, 0x85u);
          v34 = v33;
          if ( v33 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1800497B0[0] )
              bidTraceW(off_1800491C8[0], 937984, off_1800497B0[0], (unsigned int)v33, 916);
            ThrowHR(v34);
          }
          v28 = v60;
        }
        v35 = *((unsigned __int16 *)v8 + 2);
        v8 += 6;
        v9 = v32 - 2;
        v63 = (VARIANTARG *)(v61 + 8 * v28 + 48);
        VariantInit(v63);
        v36 = 1;
        if ( v62 )
        {
          for ( j = 0; j < *((_DWORD *)v62 + 2); ++j )
          {
            if ( *(_DWORD *)(*(_QWORD *)v62 + 48LL * j + 8) == *(_DWORD *)(v61 + 8 * v28) )
            {
              v36 = *(_WORD *)(*(_QWORD *)v62 + 48LL * j + 16);
              if ( v36 != 3 )
                break;
              v63->vt = 3;
              if ( v9 < 4u )
              {
                v38 = Exit(-2147467259, 0x85u);
                v39 = v38;
                if ( v38 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 && off_1800497A0[0] )
                    bidTraceW(off_1800491C8[0], 961536, off_1800497A0[0], (unsigned int)v38, 939);
                  ThrowHR(v39);
                }
                v28 = v60;
              }
              *(_DWORD *)(v61 + 8 * v28 + 56) = *(_DWORD *)v8;
              v8 += 4;
              v40 = -4;
              goto LABEL_74;
            }
          }
        }
        if ( v36 == 8 )
        {
          if ( v9 < (unsigned __int16)v35 )
          {
            v45 = Exit(-2147467259, 0x85u);
            v46 = v45;
            if ( v45 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049798[0] )
                bidTraceW(off_1800491C8[0], 970752, off_180049798[0], (unsigned int)v45, 948);
              ThrowHR(v46);
            }
            v28 = v60;
          }
          if ( (_WORD)v35 )
          {
            v63->vt = 8;
            v47 = SysAllocStringLen((const OLECHAR *)v8, (unsigned int)v35 >> 1);
            *(_QWORD *)(v61 + 8 * v28 + 56) = v47;
LABEL_84:
            v8 += v35;
            v9 -= v35;
          }
        }
        else
        {
          if ( v36 != 11 )
          {
            if ( v9 < (unsigned __int16)v35 )
            {
              v41 = Exit(-2147467259, 0x85u);
              v42 = v41;
              if ( v41 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 && off_180049790[0] )
                  bidTraceW(off_1800491C8[0], 985088, off_180049790[0], (unsigned int)v41, 962);
                ThrowHR(v42);
              }
            }
            goto LABEL_84;
          }
          v63->vt = 11;
          if ( v9 < 2u )
          {
            v43 = Exit(-2147467259, 0x85u);
            v44 = v43;
            if ( v43 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_1800497A8[0] )
                bidTraceW(off_1800491C8[0], 951296, off_1800497A8[0], (unsigned int)v43, 929);
              ThrowHR(v44);
            }
            v28 = v60;
          }
          *(_WORD *)(v61 + 8 * v28 + 56) = *(_WORD *)v8;
          v8 += 2;
          v40 = -2;
LABEL_74:
          v9 += v40;
        }
        v27 = v56 + 1;
        v19 = v64;
      }
    }
    CUtlProps::utlSetProperties(
      (CADTGRowset *)((char *)v66 + 400),
      v14,
      v55,
      v13,
      (CADTGRowset *)((char *)v66 + 112),
      1);
  }
  catch ( long v68 )
  {
    v59 = v68;
    v16 = v57;
    v55 = v57;
    v13 = v67;
  }
  if ( v13 )
  {
    v49 = 0;
    if ( v16 )
    {
      v50 = 0;
      do
      {
        v51 = v50;
        if ( v13[v50].rgProperties )
        {
          for ( k = 0; k < v13[v51].cProperties; ++k )
            VariantClear(&v13[v51].rgProperties[k].vValue);
          operator delete(v13[v51].rgProperties);
          v16 = v55;
        }
        ++v49;
        ++v50;
      }
      while ( v49 < v16 );
    }
    operator delete(v13);
  }
  v53 = v59;
  if ( v59 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049788[0] )
      bidTraceW(off_1800491C8[0], 1018880, off_180049788[0], (unsigned int)v59, 995);
    ThrowHR(v53);
  }
}

```

## disassembly

```asm
0x18000fbbc  mov     [rsp+arg_10], rbx
0x18000fbc1  mov     [rsp+arg_18], rsi
0x18000fbc6  push    rdi
0x18000fbc7  push    r12
0x18000fbc9  push    r13
0x18000fbcb  push    r14
0x18000fbcd  push    r15
0x18000fbcf  sub     rsp, 0D0h
0x18000fbd6  mov     rax, cs:__security_cookie
0x18000fbdd  xor     rax, rsp
0x18000fbe0  mov     [rsp+0F8h+var_38], rax
0x18000fbe8  movzx   esi, r8w
0x18000fbec  mov     r12, rdx
0x18000fbef  mov     [rsp+0F8h+var_70], rcx
0x18000fbf7  xor     ebx, ebx
0x18000fbf9  mov     [rsp+0F8h+var_B0], bx
0x18000fbfe  mov     [rsp+0F8h+var_A8], ebx
0x18000fc02  mov     [rsp+0F8h+var_68], rbx
0x18000fc0a  mov     [rsp+0F8h+var_AC], ebx
0x18000fc0e  lea     edi, [rbx+2]
0x18000fc11  cmp     r8w, di
0x18000fc15  jnb     short loc_18000FC6D
0x18000fc17  mov     edx, 85h; unsigned int
0x18000fc1c  mov     ecx, 80004005h; int
0x18000fc21  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fc26  mov     r14d, eax
0x18000fc29  test    eax, eax
0x18000fc2b  jns     short loc_18000FC6D
0x18000fc2d  test    byte ptr cs:_bidGblFlags, dil
0x18000fc34  jz      short loc_18000FC65
0x18000fc36  mov     rcx, cs:off_1800497D0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fc3d  test    rcx, rcx
0x18000fc40  jz      short loc_18000FC65
0x18000fc42  mov     dword ptr [rsp+0F8h+var_D8], 357h
0x18000fc4a  mov     r9d, eax
0x18000fc4d  mov     r8, cs:off_1800497D0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fc54  mov     edx, 0D5C00h
0x18000fc59  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fc60  call    _bidTraceW
0x18000fc65  mov     ecx, r14d; int
0x18000fc68  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fc6d  movzx   eax, word ptr [r12]
0x18000fc72  mov     [rsp+0F8h+var_B6], ax
0x18000fc77  mov     [rsp+0F8h+var_B0], ax
0x18000fc7c  add     r12, rdi
0x18000fc7f  mov     ecx, 0FFFEh
0x18000fc84  add     si, cx
0x18000fc87  mov     r15d, eax
0x18000fc8a  mov     eax, 20h ; ' '
0x18000fc8f  mul     r15
0x18000fc92  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc99  cmovb   rax, rcx
0x18000fc9d  mov     ecx, eax; unsigned int
0x18000fc9f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000fca4  mov     r14, rax
0x18000fca7  mov     [rsp+0F8h+var_68], rax
0x18000fcaf  mov     rcx, rax; void *
0x18000fcb2  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000fcb7  shl     r15, 5
0x18000fcbb  mov     r8, r15; Size
0x18000fcbe  xor     edx, edx; Val
0x18000fcc0  mov     rcx, r14; void *
0x18000fcc3  call    memset_0
0x18000fcc8  movzx   eax, bx
0x18000fccb  mov     [rsp+0F8h+var_B8], bx
0x18000fcd0  mov     r13d, 1
0x18000fcd6  movzx   r15d, [rsp+0F8h+var_B6]
0x18000fcdc  cmp     ax, r15w
0x18000fce0  jnb     loc_1800102AD
0x18000fce6  xorps   xmm0, xmm0
0x18000fce9  movups  [rsp+0F8h+var_58], xmm0
0x18000fcf1  movups  [rsp+0F8h+var_48], xmm0
0x18000fcf9  mov     [rsp+0F8h+var_90], rbx
0x18000fcfe  mov     [rsp+0F8h+pv], rbx
0x18000fd06  cmp     si, 10h
0x18000fd0a  jnb     short loc_18000FD67
0x18000fd0c  mov     edx, 85h; unsigned int
0x18000fd11  mov     ecx, 80004005h; int
0x18000fd16  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fd1b  mov     r15d, eax
0x18000fd1e  test    eax, eax
0x18000fd20  jns     short loc_18000FD62
0x18000fd22  test    byte ptr cs:_bidGblFlags, dil
0x18000fd29  jz      short loc_18000FD5A
0x18000fd2b  mov     rcx, cs:off_1800497C8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fd32  test    rcx, rcx
0x18000fd35  jz      short loc_18000FD5A
0x18000fd37  mov     dword ptr [rsp+0F8h+var_D8], 36Bh
0x18000fd3f  mov     r9d, eax
0x18000fd42  mov     r8, cs:off_1800497C8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fd49  mov     edx, 0DAC00h
0x18000fd4e  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fd55  call    _bidTraceW
0x18000fd5a  mov     ecx, r15d; int
0x18000fd5d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fd62  movzx   eax, [rsp+0F8h+var_B8]
0x18000fd67  movzx   r15d, ax
0x18000fd6b  shl     r15, 5
0x18000fd6f  mov     [rsp+0F8h+var_80], r15
0x18000fd74  movups  xmm0, xmmword ptr [r12]
0x18000fd79  movdqu  xmmword ptr [r15+r14+0Ch], xmm0
0x18000fd80  sub     si, 10h
0x18000fd84  movdqu  [rsp+0F8h+var_58+0Ch], xmm0
0x18000fd8d  mov     dword ptr [rsp+0F8h+var_58+8], ebx
0x18000fd94  mov     qword ptr [rsp+0F8h+var_58], rbx
0x18000fd9c  mov     [rsp+0F8h+var_AC], ebx
0x18000fda0  mov     rcx, [rsp+0F8h+var_70]
0x18000fda8  mov     rcx, [rcx+218h]
0x18000fdaf  mov     rax, [rcx]
0x18000fdb2  lea     rdx, [rsp+0F8h+pv]
0x18000fdba  mov     qword ptr [rsp+0F8h+var_D0], rdx
0x18000fdbf  lea     rdx, [rsp+0F8h+var_90]
0x18000fdc4  mov     [rsp+0F8h+var_D8], rdx
0x18000fdc9  lea     r9, [rsp+0F8h+var_AC]
0x18000fdce  lea     r8, [rsp+0F8h+var_58]
0x18000fdd6  mov     edx, r13d
0x18000fdd9  mov     rax, [rax+20h]
0x18000fddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde2  cmp     si, di
0x18000fde5  jnb     short loc_18000FE42
0x18000fde7  mov     edx, 85h; unsigned int
0x18000fdec  mov     ecx, 80004005h; int
0x18000fdf1  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fdf6  mov     r15d, eax
0x18000fdf9  test    eax, eax
0x18000fdfb  jns     short loc_18000FE3D
0x18000fdfd  test    byte ptr cs:_bidGblFlags, dil
0x18000fe04  jz      short loc_18000FE35
0x18000fe06  mov     rcx, cs:off_1800497C0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fe0d  test    rcx, rcx
0x18000fe10  jz      short loc_18000FE35
0x18000fe12  mov     dword ptr [rsp+0F8h+var_D8], 37Bh
0x18000fe1a  mov     r9d, eax
0x18000fe1d  mov     r8, cs:off_1800497C0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fe24  mov     edx, 0DEC00h
0x18000fe29  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fe30  call    _bidTraceW
0x18000fe35  mov     ecx, r15d; int
0x18000fe38  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fe3d  mov     r15, [rsp+0F8h+var_80]
0x18000fe42  movzx   ecx, word ptr [r12+10h]
0x18000fe48  mov     [r15+r14+8], ecx
0x18000fe4d  add     r12, 12h
0x18000fe51  sub     si, di
0x18000fe54  mov     eax, 48h ; 'H'
0x18000fe59  mul     rcx
0x18000fe5c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fe63  cmovb   rax, rcx
0x18000fe67  mov     ecx, eax; unsigned int
0x18000fe69  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000fe6e  mov     [r15+r14], rax
0x18000fe72  mov     rcx, rax; void *
0x18000fe75  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000fe7a  movzx   ecx, bx
0x18000fe7d  mov     [rsp+0F8h+var_B4], cx
0x18000fe82  movzx   eax, cx
0x18000fe85  cmp     eax, [r15+r14+8]
0x18000fe8a  jnb     loc_180010245
0x18000fe90  movzx   eax, cx
0x18000fe93  lea     r15, [rax+rax*8]
0x18000fe97  mov     [rsp+0F8h+var_A0], r15
0x18000fe9c  mov     r13, [rsp+0F8h+var_80]
0x18000fea1  mov     r13, [r14+r13]
0x18000fea5  mov     [rsp+0F8h+var_98], r13
0x18000feaa  mov     [r13+r15*8+4], ebx
0x18000feaf  mov     eax, 4
0x18000feb4  cmp     si, ax
0x18000feb7  jnb     short loc_18000FF14
0x18000feb9  mov     edx, 85h; unsigned int
0x18000febe  mov     ecx, 80004005h; int
0x18000fec3  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fec8  mov     r15d, eax
0x18000fecb  test    eax, eax
0x18000fecd  jns     short loc_18000FF0F
0x18000fecf  test    byte ptr cs:_bidGblFlags, dil
0x18000fed6  jz      short loc_18000FF07
0x18000fed8  mov     rcx, cs:off_1800497B8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fedf  test    rcx, rcx
0x18000fee2  jz      short loc_18000FF07
0x18000fee4  mov     dword ptr [rsp+0F8h+var_D8], 38Dh
0x18000feec  mov     r9d, eax
0x18000feef  mov     r8, cs:off_1800497B8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fef6  mov     edx, 0E3400h
0x18000fefb  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000ff02  call    _bidTraceW
0x18000ff07  mov     ecx, r15d; int
0x18000ff0a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000ff0f  mov     r15, [rsp+0F8h+var_A0]
0x18000ff14  mov     eax, [r12]
0x18000ff18  mov     [r13+r15*8+0], eax
0x18000ff1d  sub     si, 4
0x18000ff21  cmp     si, di
0x18000ff24  jnb     short loc_18000FF81
0x18000ff26  mov     edx, 85h; unsigned int
0x18000ff2b  mov     ecx, 80004005h; int
0x18000ff30  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000ff35  mov     r15d, eax
0x18000ff38  test    eax, eax
0x18000ff3a  jns     short loc_18000FF7C
0x18000ff3c  test    byte ptr cs:_bidGblFlags, dil
0x18000ff43  jz      short loc_18000FF74
0x18000ff45  mov     rcx, cs:off_1800497B0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000ff4c  test    rcx, rcx
0x18000ff4f  jz      short loc_18000FF74
0x18000ff51  mov     dword ptr [rsp+0F8h+var_D8], 394h
0x18000ff59  mov     r9d, eax
0x18000ff5c  mov     r8, cs:off_1800497B0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000ff63  mov     edx, 0E5000h
0x18000ff68  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000ff6f  call    _bidTraceW
0x18000ff74  mov     ecx, r15d; int
0x18000ff77  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000ff7c  mov     r15, [rsp+0F8h+var_A0]
0x18000ff81  movzx   r13d, word ptr [r12+4]
0x18000ff87  add     r12, 6
0x18000ff8b  sub     si, di
0x18000ff8e  mov     rax, [rsp+0F8h+var_98]
0x18000ff93  lea     rax, [rax+r15*8]
0x18000ff97  add     rax, 30h ; '0'
0x18000ff9b  mov     [rsp+0F8h+var_88], rax
0x18000ffa0  mov     rcx, rax; pvarg
0x18000ffa3  call    cs:__imp_VariantInit
0x18000ffaa  nop     dword ptr [rax+rax+00h]
0x18000ffaf  mov     r10, [rsp+0F8h+var_90]
0x18000ffb4  mov     ecx, 1
0x18000ffb9  movzx   r9d, cx
0x18000ffbd  test    r10, r10
0x18000ffc0  jz      loc_18001008F
0x18000ffc6  mov     rax, [rsp+0F8h+var_98]
0x18000ffcb  mov     r11d, [rax+r15*8]
0x18000ffcf  mov     edx, ebx
0x18000ffd1  cmp     edx, [r10+8]
0x18000ffd5  jnb     loc_18001008F
0x18000ffdb  mov     eax, edx
0x18000ffdd  lea     r8, [rax+rax*2]
0x18000ffe1  add     r8, r8
0x18000ffe4  mov     rax, [r10]
0x18000ffe7  cmp     [rax+r8*8+8], r11d
0x18000ffec  jz      short loc_18000FFF2
0x18000ffee  add     edx, ecx
0x18000fff0  jmp     short loc_18000FFD1
0x18000fff2  movzx   r9d, word ptr [rax+r8*8+10h]
0x18000fff8  mov     ecx, 3
0x18000fffd  cmp     r9w, cx
0x180010001  jnz     loc_18001008F
0x180010007  mov     rax, [rsp+0F8h+var_88]
0x18001000c  mov     [rax], cx
0x18001000f  lea     r13d, [rcx+1]
0x180010013  cmp     si, r13w
0x180010017  jnb     short loc_180010074
0x180010019  mov     edx, 85h; unsigned int
0x18001001e  mov     ecx, 80004005h; int
0x180010023  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180010028  mov     r15d, eax
0x18001002b  test    eax, eax
0x18001002d  jns     short loc_18001006F
0x18001002f  test    byte ptr cs:_bidGblFlags, dil
0x180010036  jz      short loc_180010067
0x180010038  mov     rcx, cs:off_1800497A0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18001003f  test    rcx, rcx
0x180010042  jz      short loc_180010067
0x180010044  mov     dword ptr [rsp+0F8h+var_D8], 3ABh
0x18001004c  mov     r9d, eax
0x18001004f  mov     r8, cs:off_1800497A0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x180010056  mov     edx, 0EAC00h
0x18001005b  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180010062  call    _bidTraceW
0x180010067  mov     ecx, r15d; int
0x18001006a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001006f  mov     r15, [rsp+0F8h+var_A0]
0x180010074  mov     eax, [r12]
0x180010078  mov     rcx, [rsp+0F8h+var_98]
0x18001007d  mov     [rcx+r15*8+38h], eax
0x180010082  add     r12, r13
0x180010085  mov     eax, 0FFFCh
0x18001008a  jmp     loc_18001018B
0x18001008f  mov     ecx, 8
0x180010094  cmp     r9w, cx
0x180010098  jz      loc_180010193
0x18001009e  mov     ecx, 0Bh
0x1800100a3  cmp     r9w, cx
0x1800100a7  jz      short loc_18001010B
0x1800100a9  cmp     si, r13w
0x1800100ad  jnb     loc_180010225
0x1800100b3  lea     edx, [rcx+7Ah]; unsigned int
0x1800100b6  mov     ecx, 80004005h; int
0x1800100bb  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800100c0  mov     r15d, eax
0x1800100c3  test    eax, eax
0x1800100c5  jns     loc_180010225
0x1800100cb  test    byte ptr cs:_bidGblFlags, dil
0x1800100d2  jz      short loc_180010103
0x1800100d4  mov     rcx, cs:off_180049790; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x1800100db  test    rcx, rcx
0x1800100de  jz      short loc_180010103
0x1800100e0  mov     dword ptr [rsp+0F8h+var_D8], 3C2h
0x1800100e8  mov     r9d, eax
0x1800100eb  mov     r8, cs:off_180049790; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x1800100f2  mov     edx, 0F0800h
0x1800100f7  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
  ... truncated ...
```
