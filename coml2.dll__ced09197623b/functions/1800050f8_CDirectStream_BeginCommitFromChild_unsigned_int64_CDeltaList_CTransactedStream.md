# CDirectStream::BeginCommitFromChild(unsigned __int64,CDeltaList *,CTransactedStream *)

- ea: `0x1800050f8`
- end: `0x180005766`
- name: `?BeginCommitFromChild@CDirectStream@@QEAAJ_KPEAVCDeltaList@@PEAVCTransactedStream@@@Z`
- size: `1646`
- prototype: `int(CDirectStream *__hidden this, unsigned __int64, struct CDeltaList *, struct CTransactedStream *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005080`

## callees

- `0x180003678`
- `0x180003a80`
- `0x1800050f8`
- `0x180008e6c`
- `0x180008ea4`
- `0x180008f30`
- `0x1800093fc`
- `0x18000a084`
- `0x18000a61c`
- `0x18000a68c`
- `0x18000afb0`
- `0x18000b3d0`
- `0x18000bb1c`
- `0x18000c3b0`
- `0x18000e340`
- `0x180011290`
- `0x1800142c0`
- `0x18003b438`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005746`

## pseudocode

```c
__int64 __fastcall CDirectStream::BeginCommitFromChild(
        CDirectStream *this,
        unsigned __int64 a2,
        struct CDeltaList *a3,
        struct CTransactedStream *a4)
{
  __int64 v4; // r13
  char *v8; // rax
  CDeltaList *v9; // rcx
  unsigned __int16 v10; // ax
  __int64 v11; // r10
  __int64 v12; // r8
  unsigned __int64 v13; // r12
  __int64 v14; // rcx
  int Map; // ebx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r12
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int i; // esi
  __int64 v23; // rdx
  __int64 v24; // r12
  CFat *v25; // r12
  unsigned int v26; // r13d
  int v27; // eax
  unsigned int v28; // r8d
  int v29; // eax
  __int64 v30; // r8
  unsigned int v31; // edx
  unsigned int v32; // r12d
  CFat *v33; // r13
  int v34; // eax
  CDeltaList *v35; // rcx
  unsigned __int16 DataSectorSize; // ax
  unsigned __int64 v37; // rsi
  unsigned int v38; // ebx
  char *v39; // rax
  __int64 v40; // rcx
  unsigned int v41; // r12d
  unsigned int v42; // r9d
  char *v43; // r10
  unsigned int v44; // r11d
  unsigned int v45; // esi
  __int64 v46; // rdx
  unsigned int v47; // r9d
  char *v48; // r12
  __int64 v49; // r14
  unsigned int v51; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v52; // [rsp+34h] [rbp-3Ch] BYREF
  char *v53; // [rsp+38h] [rbp-38h]
  LPVOID pv; // [rsp+40h] [rbp-30h]
  int v55; // [rsp+48h] [rbp-28h]
  CDirectory *DataILB; // [rsp+50h] [rbp-20h]
  int v57; // [rsp+58h] [rbp-18h]
  __int16 v58; // [rsp+5Ch] [rbp-14h]
  unsigned __int64 v59; // [rsp+60h] [rbp-10h]
  unsigned int v60; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v61; // [rsp+C0h] [rbp+50h] BYREF
  struct CTransactedStream *v62; // [rsp+C8h] [rbp+58h] BYREF

  v62 = a4;
  v4 = 0;
  v52 = 0;
  pv = 0;
  if ( a3 )
    v8 = (char *)a3 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v8 = 0;
  *((_QWORD *)this + 24) = v8;
  if ( !(unsigned int)CDeltaList::IsNoScratch(a3)
    || a2 < 0x1000
    || (unsigned __int64)(*((_QWORD *)this + 22) - 1LL) <= 0xFFE
    || (unsigned int)CDeltaList::IsEmpty(a3) )
  {
    Map = CDirectStream::SetSize(this, a2);
    if ( Map < 0 )
      goto LABEL_83;
    *((_QWORD *)this + 23) = *((_QWORD *)this + 22);
    if ( (unsigned int)CDeltaList::IsEmpty(a3) )
      goto LABEL_83;
    DataSectorSize = CDeltaList::GetDataSectorSize(v35);
    v37 = DataSectorSize;
    LOWORD(v62) = DataSectorSize;
    LOWORD(v55) = CDeltaList::GetDataSectorShift(a3);
    v38 = 15 * v37;
    v57 = v37;
    while ( 1 )
    {
      v39 = (char *)CoTaskMemAlloc(v38);
      pv = v39;
      if ( v39 )
        break;
      v38 >>= 1;
      if ( v38 < (unsigned int)v37 )
      {
        pv = 0;
        Map = -2147287032;
        goto LABEL_83;
      }
    }
    v40 = *((_QWORD *)this + 22);
    v53 = v39;
    v51 = v38 / (unsigned int)v37;
    v41 = -2;
    v60 = -2;
    v61 = -2;
    v58 = (v40 - 1) % v37 + 1;
    v59 = (v37 + v40 - 1) / v37;
    DataILB = (CDirectory *)CDeltaList::GetDataILB(a3);
    v45 = 0;
    Map = 0;
    while ( 1 )
    {
      if ( v45 >= v44 )
      {
        if ( (_WORD)v4 )
        {
          v49 = (unsigned __int16)v62;
          Map = (*(__int64 (__fastcall **)(CDirectory *, unsigned __int64, char *, _QWORD, unsigned int *))(*(_QWORD *)DataILB + 24LL))(
                  DataILB,
                  (unsigned __int64)(v60 + 1) << v55,
                  v43,
                  (unsigned __int16)v62 * (unsigned int)(unsigned __int16)v4,
                  &v52);
          if ( Map >= 0 )
            Map = CDirectStream::WriteAt(this, v49 * v41, pv, v58 + (unsigned int)v49 * (v45 - v41 - 1), &v52);
        }
        goto LABEL_83;
      }
      if ( v42 == -2 )
        v41 = v45;
      Map = CDeltaList::GetMap(a3, v45, 2u, &v61);
      if ( Map < 0 )
        goto LABEL_83;
      v42 = v61;
      if ( (_WORD)v4 && (v61 == -2 || v61 != v60 + (unsigned __int16)v4 || v45 - v41 == v51) )
      {
        LODWORD(v4) = v57 * (unsigned __int16)v4;
        Map = (*(__int64 (__fastcall **)(CDirectory *, unsigned __int64, char *, _QWORD, unsigned int *))(*(_QWORD *)DataILB + 24LL))(
                DataILB,
                (unsigned __int64)(v60 + 1) << v55,
                v53,
                (unsigned int)v4,
                &v52);
        if ( Map < 0 )
          goto LABEL_83;
        v42 = v61;
        v53 += (int)v4;
        v60 = v61;
        LOWORD(v4) = v61 != -2;
      }
      else
      {
        if ( v61 == -2 )
          goto LABEL_74;
        if ( v60 == -2 )
        {
          v60 = v61;
          LOWORD(v4) = 1;
        }
        else if ( v61 == v60 + (unsigned __int16)v4 )
        {
          LOWORD(v4) = v4 + 1;
        }
      }
      if ( v42 == -2 )
      {
LABEL_74:
        if ( v41 != v45 )
          goto LABEL_76;
      }
      if ( v45 - v41 != v51 )
      {
        v43 = v53;
        goto LABEL_79;
      }
LABEL_76:
      v46 = v41;
      v47 = v45 - v41;
      v48 = (char *)pv;
      Map = CDirectStream::WriteAt(this, (unsigned __int16)v62 * v46, pv, (unsigned __int16)v62 * v47, &v52);
      if ( Map < 0 )
        goto LABEL_83;
      v42 = v61;
      v43 = v48;
      v53 = v48;
      v41 = v45;
LABEL_79:
      v44 = v59;
      ++v45;
    }
  }
  v10 = CDeltaList::GetDataSectorSize(v9);
  *((_QWORD *)this + 23) = v11;
  *((_QWORD *)this + 22) = a2;
  v12 = *((_QWORD *)this + 2);
  v13 = v10;
  v60 = -2;
  if ( v12 )
    v14 = v12 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v14 = 0;
  Map = CDirectory::SetSize((CDirectory *)(v14 + 536), *((_DWORD *)this + 6), a2);
  if ( Map >= 0 )
  {
    v16 = *((_QWORD *)this + 22);
    v17 = (v13 + a2 - 1) / v13;
    v53 = (char *)v17;
    if ( *((_QWORD *)this + 23) > v16 )
    {
      v18 = *((_QWORD *)this + 2);
      LODWORD(v62) = 0;
      if ( v18 )
        v19 = v18 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
      else
        v19 = 0;
      Map = CDirectory::GetStart((CDirectory *)(v19 + 536), *((_DWORD *)this + 6), (unsigned int *)&v62);
      if ( Map < 0 )
        goto LABEL_83;
      v20 = *((_QWORD *)this + 2);
      if ( v20 )
        v21 = v20 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
      else
        v21 = 0;
      CFat::SetChainLength((CFat *)(v21 + 616), (unsigned int)v62, v17);
      CStreamCache::Empty((CDirectStream *)((char *)this + 32));
    }
    for ( i = 0; i < (unsigned int)v17; ++i )
    {
      LODWORD(v62) = 0;
      v51 = 0;
      v61 = 0;
      Map = CDeltaList::GetMap(a3, i, 2u, (unsigned int *)&v62);
      if ( Map < 0 )
        break;
      if ( (_DWORD)v62 != -2 )
      {
        v23 = *((_QWORD *)this + 2);
        if ( i )
        {
          if ( v23 )
            v24 = v23 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v24 = 0;
          Map = CStreamCache::GetSect((CDirectStream *)((char *)this + 32), i - 1, &v60);
          if ( Map < 0 )
            break;
          v25 = (CFat *)(v24 + 616);
          Map = CFat::GetNext(v25, v60, &v51);
          if ( Map < 0 )
            break;
          Map = CFat::SetNext(v25, v60, (unsigned int)v62);
          if ( Map < 0 )
            break;
          v26 = v51;
          if ( v51 == -2 )
          {
            v28 = -2;
            v4 = 0;
          }
          else
          {
            Map = CFat::GetNext(v25, v51, &v61);
            if ( Map < 0 )
              break;
            v27 = CFat::SetNext(v25, v26, 0xFFFFFFFF);
            v4 = 0;
            Map = v27;
            if ( v27 < 0 )
              break;
            v28 = v61;
          }
          v29 = CFat::SetNext(v25, (unsigned int)v62, v28);
        }
        else
        {
          if ( v23 )
          {
            v30 = v23 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            v4 = v30;
          }
          else
          {
            v30 = 0;
          }
          v31 = *((_DWORD *)this + 6);
          DataILB = (CDirectory *)(v30 + 536);
          v61 = -2;
          Map = CDirectory::GetStart((CDirectory *)(v30 + 536), v31, &v60);
          if ( Map < 0 )
            break;
          v32 = v60;
          v33 = (CFat *)(v4 + 616);
          if ( v60 != -2 )
          {
            Map = CFat::GetNext(v33, v60, &v61);
            if ( Map < 0 )
              break;
            Map = CFat::SetNext(v33, v32, 0xFFFFFFFF);
            if ( Map < 0 )
              break;
          }
          v34 = CFat::SetNext(v33, (unsigned int)v62, v61);
          v4 = 0;
          Map = v34;
          if ( v34 < 0 )
            break;
          v29 = CDirectory::SetStart(DataILB, *((_DWORD *)this + 6), (unsigned int)v62);
        }
        Map = v29;
        if ( v29 < 0 )
          break;
        Map = CStreamCache::EmptyRegion((CDirectStream *)((char *)this + 32), i, i);
        if ( Map < 0 )
          break;
        LODWORD(v17) = (_DWORD)v53;
      }
    }
  }
LABEL_83:
  CoTaskMemFree(pv);
  return (unsigned int)Map;
}

```

## disassembly

```asm
0x1800050f8  mov     [rsp-38h+arg_8], rbx
0x1800050fd  mov     [rsp-38h+arg_18], r9
0x180005102  push    rbp
0x180005103  push    rsi
0x180005104  push    rdi
0x180005105  push    r12
0x180005107  push    r13
0x180005109  push    r14
0x18000510b  push    r15
0x18000510d  mov     rbp, rsp
0x180005110  sub     rsp, 70h
0x180005114  xor     r13d, r13d
0x180005117  mov     r15, r8
0x18000511a  mov     [rbp+var_3C], r13d
0x18000511e  mov     rsi, rdx
0x180005121  mov     [rbp+pv], r13
0x180005125  mov     rdi, rcx
0x180005128  test    r8, r8
0x18000512b  jz      short loc_180005145
0x18000512d  mov     rax, gs:30h
0x180005136  mov     r9, [rax+1758h]
0x18000513d  mov     rax, r8
0x180005140  sub     rax, [r9]
0x180005143  jmp     short loc_180005148
0x180005145  mov     rax, r13
0x180005148  mov     [rcx+0C0h], rax
0x18000514f  mov     rcx, r15; this
0x180005152  call    ?IsNoScratch@CDeltaList@@QEAAHXZ; CDeltaList::IsNoScratch(void)
0x180005157  test    eax, eax
0x180005159  jz      loc_1800054B1
0x18000515f  cmp     rsi, 1000h
0x180005166  jb      loc_1800054B1
0x18000516c  mov     r10, [rdi+0B0h]
0x180005173  lea     rax, [r10-1]
0x180005177  cmp     rax, 0FFEh
0x18000517d  jbe     loc_1800054B1
0x180005183  mov     rcx, r15; this
0x180005186  call    ?IsEmpty@CDeltaList@@QEAAHXZ; CDeltaList::IsEmpty(void)
0x18000518b  test    eax, eax
0x18000518d  jnz     loc_1800054B1
0x180005193  call    ?GetDataSectorSize@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorSize(void)
0x180005198  mov     [rdi+0B8h], r10
0x18000519f  mov     r14d, 0FFFFFFFEh
0x1800051a5  mov     [rdi+0B0h], rsi
0x1800051ac  mov     r8, [rdi+10h]
0x1800051b0  movzx   r12d, ax
0x1800051b4  mov     [rbp+arg_0], r14d
0x1800051b8  test    r8, r8
0x1800051bb  jz      short loc_1800051D5
0x1800051bd  mov     rcx, gs:30h
0x1800051c6  mov     rdx, [rcx+1758h]
0x1800051cd  mov     rcx, [rdx]
0x1800051d0  add     rcx, r8
0x1800051d3  jmp     short loc_1800051D8
0x1800051d5  mov     rcx, r13
0x1800051d8  mov     edx, [rdi+18h]; unsigned int
0x1800051db  add     rcx, 218h; this
0x1800051e2  mov     r8, rsi; unsigned __int64
0x1800051e5  call    ?SetSize@CDirectory@@QEAAJK_K@Z; CDirectory::SetSize(ulong,unsigned __int64)
0x1800051ea  mov     ebx, eax
0x1800051ec  test    eax, eax
0x1800051ee  js      loc_180005742
0x1800051f4  mov     rcx, [rdi+0B0h]
0x1800051fb  lea     rax, [rsi-1]
0x1800051ff  add     rax, r12
0x180005202  xor     edx, edx
0x180005204  div     r12
0x180005207  mov     r12, rax
0x18000520a  mov     [rbp+var_38], rax
0x18000520e  cmp     [rdi+0B8h], rcx
0x180005215  jbe     loc_18000529F
0x18000521b  mov     r8, [rdi+10h]
0x18000521f  mov     dword ptr [rbp+arg_18], r13d
0x180005223  test    r8, r8
0x180005226  jz      short loc_180005240
0x180005228  mov     rcx, gs:30h
0x180005231  mov     rdx, [rcx+1758h]
0x180005238  mov     rcx, [rdx]
0x18000523b  add     rcx, r8
0x18000523e  jmp     short loc_180005243
0x180005240  mov     rcx, r13
0x180005243  mov     edx, [rdi+18h]; unsigned int
0x180005246  lea     r8, [rbp+arg_18]; unsigned int *
0x18000524a  add     rcx, 218h; this
0x180005251  call    ?GetStart@CDirectory@@QEAAJKPEAK@Z; CDirectory::GetStart(ulong,ulong *)
0x180005256  mov     ebx, eax
0x180005258  test    eax, eax
0x18000525a  js      loc_180005742
0x180005260  mov     rdx, [rdi+10h]
0x180005264  test    rdx, rdx
0x180005267  jz      short loc_180005281
0x180005269  mov     rax, gs:30h
0x180005272  mov     rcx, [rax+1758h]
0x180005279  mov     rcx, [rcx]
0x18000527c  add     rcx, rdx
0x18000527f  jmp     short loc_180005284
0x180005281  mov     rcx, r13
0x180005284  mov     edx, dword ptr [rbp+arg_18]; unsigned int
0x180005287  add     rcx, 268h; this
0x18000528e  mov     r8d, r12d; unsigned int
0x180005291  call    ?SetChainLength@CFat@@QEAAJKK@Z; CFat::SetChainLength(ulong,ulong)
0x180005296  lea     rcx, [rdi+20h]; this
0x18000529a  call    ?Empty@CStreamCache@@QEAAXXZ; CStreamCache::Empty(void)
0x18000529f  mov     esi, r13d
0x1800052a2  cmp     esi, r12d
0x1800052a5  jnb     loc_180005742
0x1800052ab  lea     r9, [rbp+arg_18]; unsigned int *
0x1800052af  mov     dword ptr [rbp+arg_18], r13d
0x1800052b3  mov     r8d, 2; unsigned int
0x1800052b9  mov     [rbp+var_40], r13d
0x1800052bd  mov     edx, esi; unsigned int
0x1800052bf  mov     [rbp+arg_10], r13d
0x1800052c3  mov     rcx, r15; this
0x1800052c6  call    ?GetMap@CDeltaList@@QEAAJKKPEAK@Z; CDeltaList::GetMap(ulong,ulong,ulong *)
0x1800052cb  mov     ebx, eax
0x1800052cd  test    eax, eax
0x1800052cf  js      loc_180005742
0x1800052d5  cmp     dword ptr [rbp+arg_18], r14d
0x1800052d9  jz      loc_1800054AA
0x1800052df  mov     rdx, [rdi+10h]
0x1800052e3  test    esi, esi
0x1800052e5  jz      loc_1800053B8
0x1800052eb  test    rdx, rdx
0x1800052ee  jz      short loc_180005308
0x1800052f0  mov     rax, gs:30h
0x1800052f9  mov     rcx, [rax+1758h]
0x180005300  mov     r12, [rcx]
0x180005303  add     r12, rdx
0x180005306  jmp     short loc_18000530B
0x180005308  mov     r12, r13
0x18000530b  lea     rcx, [rdi+20h]; this
0x18000530f  lea     edx, [rsi-1]; unsigned int
0x180005312  lea     r8, [rbp+arg_0]; unsigned int *
0x180005316  call    ?GetSect@CStreamCache@@QEAAJKPEAK@Z; CStreamCache::GetSect(ulong,ulong *)
0x18000531b  mov     ebx, eax
0x18000531d  test    eax, eax
0x18000531f  js      loc_180005742
0x180005325  mov     edx, [rbp+arg_0]; unsigned int
0x180005328  lea     r8, [rbp+var_40]; unsigned int *
0x18000532c  add     r12, 268h
0x180005333  mov     rcx, r12; this
0x180005336  call    ?GetNext@CFat@@QEAAJKPEAK@Z; CFat::GetNext(ulong,ulong *)
0x18000533b  mov     ebx, eax
0x18000533d  test    eax, eax
0x18000533f  js      loc_180005742
0x180005345  mov     r8d, dword ptr [rbp+arg_18]; unsigned int
0x180005349  mov     rcx, r12; this
0x18000534c  mov     edx, [rbp+arg_0]; unsigned int
0x18000534f  call    ?SetNext@CFat@@QEAAJKK@Z; CFat::SetNext(ulong,ulong)
0x180005354  mov     ebx, eax
0x180005356  test    eax, eax
0x180005358  js      loc_180005742
0x18000535e  mov     r13d, [rbp+var_40]
0x180005362  cmp     r13d, r14d
0x180005365  jz      short loc_1800053A2
0x180005367  lea     r8, [rbp+arg_10]; unsigned int *
0x18000536b  mov     edx, r13d; unsigned int
0x18000536e  mov     rcx, r12; this
0x180005371  call    ?GetNext@CFat@@QEAAJKPEAK@Z; CFat::GetNext(ulong,ulong *)
0x180005376  mov     ebx, eax
0x180005378  test    eax, eax
0x18000537a  js      loc_180005742
0x180005380  or      r8d, 0FFFFFFFFh; unsigned int
0x180005384  mov     edx, r13d; unsigned int
0x180005387  mov     rcx, r12; this
0x18000538a  call    ?SetNext@CFat@@QEAAJKK@Z; CFat::SetNext(ulong,ulong)
0x18000538f  xor     r13d, r13d
0x180005392  mov     ebx, eax
0x180005394  test    eax, eax
0x180005396  js      loc_180005742
0x18000539c  mov     r8d, [rbp+arg_10]
0x1800053a0  jmp     short loc_1800053A8
0x1800053a2  mov     r8d, r14d; unsigned int
0x1800053a5  xor     r13d, r13d
0x1800053a8  mov     edx, dword ptr [rbp+arg_18]; unsigned int
0x1800053ab  mov     rcx, r12; this
0x1800053ae  call    ?SetNext@CFat@@QEAAJKK@Z; CFat::SetNext(ulong,ulong)
0x1800053b3  jmp     loc_180005484
0x1800053b8  test    rdx, rdx
0x1800053bb  jz      short loc_1800053EB
0x1800053bd  mov     rax, gs:30h
0x1800053c6  mov     rcx, [rax+1758h]
0x1800053cd  mov     rax, gs:30h
0x1800053d6  mov     r8, [rcx]
0x1800053d9  mov     rcx, [rax+1758h]
0x1800053e0  add     r8, rdx
0x1800053e3  mov     r13, [rcx]
0x1800053e6  add     r13, rdx
0x1800053e9  jmp     short loc_1800053EE
0x1800053eb  mov     r8, r13
0x1800053ee  mov     edx, [rdi+18h]; unsigned int
0x1800053f1  lea     rax, [r8+218h]
0x1800053f8  mov     rcx, rax; this
0x1800053fb  mov     [rbp+var_20], rax
0x1800053ff  lea     r8, [rbp+arg_0]; unsigned int *
0x180005403  mov     [rbp+arg_10], r14d
0x180005407  call    ?GetStart@CDirectory@@QEAAJKPEAK@Z; CDirectory::GetStart(ulong,ulong *)
0x18000540c  mov     ebx, eax
0x18000540e  test    eax, eax
0x180005410  js      loc_180005742
0x180005416  mov     r12d, [rbp+arg_0]
0x18000541a  add     r13, 268h
0x180005421  cmp     r12d, r14d
0x180005424  jz      short loc_180005458
0x180005426  lea     r8, [rbp+arg_10]; unsigned int *
0x18000542a  mov     edx, r12d; unsigned int
0x18000542d  mov     rcx, r13; this
0x180005430  call    ?GetNext@CFat@@QEAAJKPEAK@Z; CFat::GetNext(ulong,ulong *)
0x180005435  mov     ebx, eax
0x180005437  test    eax, eax
0x180005439  js      loc_180005742
0x18000543f  or      r8d, 0FFFFFFFFh; unsigned int
0x180005443  mov     edx, r12d; unsigned int
0x180005446  mov     rcx, r13; this
0x180005449  call    ?SetNext@CFat@@QEAAJKK@Z; CFat::SetNext(ulong,ulong)
0x18000544e  mov     ebx, eax
0x180005450  test    eax, eax
0x180005452  js      loc_180005742
0x180005458  mov     r8d, [rbp+arg_10]; unsigned int
0x18000545c  mov     rcx, r13; this
0x18000545f  mov     edx, dword ptr [rbp+arg_18]; unsigned int
0x180005462  call    ?SetNext@CFat@@QEAAJKK@Z; CFat::SetNext(ulong,ulong)
0x180005467  xor     r13d, r13d
0x18000546a  mov     ebx, eax
0x18000546c  test    eax, eax
0x18000546e  js      loc_180005742
0x180005474  mov     r8d, dword ptr [rbp+arg_18]; unsigned int
0x180005478  mov     edx, [rdi+18h]; unsigned int
0x18000547b  mov     rcx, [rbp+var_20]; this
0x18000547f  call    ?SetStart@CDirectory@@QEAAJKK@Z; CDirectory::SetStart(ulong,ulong)
0x180005484  mov     ebx, eax
0x180005486  test    eax, eax
0x180005488  js      loc_180005742
0x18000548e  mov     r8d, esi; unsigned int
0x180005491  lea     rcx, [rdi+20h]; this
0x180005495  mov     edx, esi; unsigned int
0x180005497  call    ?EmptyRegion@CStreamCache@@QEAAJKK@Z; CStreamCache::EmptyRegion(ulong,ulong)
0x18000549c  mov     ebx, eax
0x18000549e  test    eax, eax
0x1800054a0  js      loc_180005742
0x1800054a6  mov     r12, [rbp+var_38]
0x1800054aa  inc     esi
0x1800054ac  jmp     loc_1800052A2
0x1800054b1  mov     rdx, rsi; unsigned __int64
0x1800054b4  mov     rcx, rdi; this
0x1800054b7  call    ?SetSize@CDirectStream@@QEAAJ_K@Z; CDirectStream::SetSize(unsigned __int64)
0x1800054bc  mov     ebx, eax
0x1800054be  test    eax, eax
0x1800054c0  js      loc_180005742
0x1800054c6  mov     rax, [rdi+0B0h]
0x1800054cd  mov     rcx, r15; this
0x1800054d0  mov     [rdi+0B8h], rax
0x1800054d7  call    ?IsEmpty@CDeltaList@@QEAAHXZ; CDeltaList::IsEmpty(void)
0x1800054dc  test    eax, eax
0x1800054de  jnz     loc_180005742
0x1800054e4  call    ?GetDataSectorSize@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorSize(void)
0x1800054e9  movzx   esi, ax
0x1800054ec  mov     rcx, r15; this
0x1800054ef  mov     word ptr [rbp+arg_18], si
0x1800054f3  call    ?GetDataSectorShift@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorShift(void)
0x1800054f8  mov     word ptr [rbp+var_28], ax
0x1800054fc  mov     r14d, esi
0x1800054ff  imul    ebx, esi, 0Fh
0x180005502  mov     [rbp+var_18], esi
0x180005505  mov     ecx, ebx; cb
0x180005507  call    cs:__imp_CoTaskMemAlloc
0x18000550d  mov     [rbp+pv], rax
0x180005511  test    rax, rax
0x180005514  jnz     short loc_18000552E
0x180005516  shr     ebx, 1
0x180005518  cmp     ebx, r14d
0x18000551b  jnb     short loc_180005505
0x18000551d  mov     rbx, rax
0x180005520  mov     [rbp+pv], rax
0x180005524  mov     ebx, 80030008h
0x180005529  jmp     loc_180005742
0x18000552e  mov     rcx, [rdi+0B0h]
0x180005535  mov     r10, rax
0x180005538  mov     [rbp+var_38], rax
0x18000553c  xor     edx, edx
0x18000553e  mov     eax, ebx
0x180005540  div     r14d
0x180005543  xor     edx, edx
0x180005545  mov     r14d, 0FFFFFFFEh
0x18000554b  mov     [rbp+var_40], eax
0x18000554e  mov     r12d, r14d
0x180005551  lea     rax, [rcx-1]
0x180005555  mov     [rbp+arg_0], r14d
0x180005559  div     rsi
0x18000555c  lea     rax, [rcx-1]
0x180005560  mov     [rbp+arg_10], r14d
0x180005564  inc     dx
0x180005567  add     rax, rsi
0x18000556a  mov     [rbp+var_14], dx
0x18000556e  mov     rcx, r15; this
0x180005571  xor     edx, edx
0x180005573  mov     r9d, r14d
0x180005576  div     rsi
0x180005579  mov     r11, rax
0x18000557c  mov     [rbp+var_10], rax
  ... truncated ...
```
