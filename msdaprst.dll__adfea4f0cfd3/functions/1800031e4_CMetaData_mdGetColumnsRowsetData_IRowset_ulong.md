# CMetaData::mdGetColumnsRowsetData(IRowset *,ulong)

- ea: `0x1800031e4`
- end: `0x180003785`
- name: `?mdGetColumnsRowsetData@CMetaData@@AEAAXPEAUIRowset@@K@Z`
- size: `1441`
- prototype: `void __fastcall(CMetaData *__hidden this, struct IRowset *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180002c1c`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180002770`
- `0x1800028b8`
- `0x1800031e4`
- `0x1800043c8`
- `0x180005264`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f086`
- `0x18002f0aa`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003737`
- `ole32!CoTaskMemFree` at `0x180003737`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CMetaData::mdGetColumnsRowsetData(CMetaData *this, struct IRowset *a2, unsigned int a3)
{
  unsigned int v3; // esi
  CMetaData *v4; // r15
  unsigned __int64 *v5; // rbx
  unsigned __int8 *v6; // rdi
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  unsigned __int64 **v12; // r12
  unsigned __int128 v13; // rax
  unsigned int v14; // r14d
  unsigned int v15; // edx
  unsigned int v16; // r13d
  __int64 v17; // rbx
  unsigned int i; // r15d
  __int64 v19; // rax
  unsigned __int64 *v20; // rcx
  CMetaData *v21; // rcx
  unsigned __int64 v22; // r12
  unsigned __int64 v23; // r14
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  unsigned __int64 *v28; // rax
  unsigned __int128 v29; // rax
  unsigned __int64 v30; // rsi
  unsigned __int128 v31; // rax
  unsigned __int8 *v32; // rax
  unsigned __int128 v33; // rax
  unsigned __int8 *v34; // rax
  int v35; // r13d
  __int64 v36; // rdx
  CMetaData *v37; // r13
  int v38; // r15d
  __int64 v39; // rdx
  int v40; // r15d
  int v41; // eax
  int v42; // esi
  int v43; // eax
  int v44; // esi
  unsigned __int64 *v45; // rcx
  unsigned __int64 *v46; // [rsp+50h] [rbp+0h] BYREF
  struct IRowset *v47; // [rsp+58h] [rbp+8h] BYREF
  __int64 v48; // [rsp+60h] [rbp+10h] BYREF
  __int64 v49; // [rsp+68h] [rbp+18h]
  __int64 v50; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v51[2]; // [rsp+78h] [rbp+28h] BYREF
  __int64 v52; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int64 *v53; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int64 *v54; // [rsp+90h] [rbp+40h]
  CMetaData *v55; // [rsp+98h] [rbp+48h]
  unsigned __int8 *v56; // [rsp+A0h] [rbp+50h]
  __int128 Buf1; // [rsp+B0h] [rbp+60h] BYREF
  __int128 v58; // [rsp+C0h] [rbp+70h]

  v3 = a3;
  LODWORD(v49) = a3;
  v4 = this;
  v55 = this;
  v5 = 0;
  v48 = 0;
  v47 = 0;
  v52 = 0;
  v53 = 0;
  v50 = 0;
  *(_QWORD *)v51 = 0;
  if ( *((_QWORD *)this + 4) || *((_QWORD *)this + 1) )
  {
    v45 = 0;
  }
  else
  {
    if ( ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsRowset,
           &v48) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *, unsigned __int64 **))(*(_QWORD *)v48 + 24LL))(v48, &v50, &v53) >= 0 )
    {
      v6 = 0;
      v56 = 0;
      if ( (unsigned int)v50 > 0x20 )
      {
        v13 = (unsigned int)v50 * (unsigned __int128)0x20uLL;
        if ( !is_mul_ok((unsigned int)v50, 0x20u) )
          LODWORD(v13) = -1;
        v6 = MMMAlloc(v13, DWORD2(v13));
        v56 = v6;
        v12 = (unsigned __int64 **)v6;
      }
      else
      {
        v7 = 32LL * (unsigned int)v50;
        v8 = v7 + 15;
        if ( v7 + 15 < v7 )
          v8 = 0xFFFFFFFFFFFFFF0LL;
        v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
        v10 = alloca(v9);
        v11 = alloca(v9);
        v12 = &v46;
      }
      OnNullThrowOOM(v12);
      v14 = 0;
      v15 = 0;
      LODWORD(v46) = 0;
      v16 = v50;
      if ( (_DWORD)v50 )
      {
        do
        {
          v17 = 4LL * v14;
          v54 = v53;
          Buf1 = *(_OWORD *)&v53[v17];
          v58 = *(_OWORD *)&v53[v17 + 2];
          for ( i = 11; i < 0x1F; ++i )
          {
            if ( (_DWORD)v58 == *((_DWORD *)&g_rgDesiredColumn + 20 * i + 4)
              && !memcmp_0(&Buf1, &g_rgDesiredColumn + 10 * i, 0x10u)
              && DWORD2(v58) == *((_DWORD *)&g_rgDesiredColumn + 20 * i + 6) )
            {
              v19 = 4LL * (unsigned int)v46;
              v15 = (_DWORD)v46 + 1;
              LODWORD(v46) = (_DWORD)v46 + 1;
              v20 = v54;
              *(_OWORD *)&v12[v19] = *(_OWORD *)&v54[v17];
              *(_OWORD *)&v12[v19 + 2] = *(_OWORD *)&v20[v17 + 2];
              v16 = v50;
              goto LABEL_21;
            }
          }
          v15 = (unsigned int)v46;
LABEL_21:
          ++v14;
        }
        while ( v14 < v16 );
        v4 = v55;
        v3 = v49;
        v5 = 0;
      }
      if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int64 **, GUID *, _DWORD, _QWORD, struct IRowset **))(*(_QWORD *)v48 + 32LL))(
             v48,
             0,
             v15,
             v12,
             &IID_IRowset,
             0,
             0,
             &v47) >= 0 )
      {
        v22 = CMetaData::mdSetupAccessor(v21, v47);
        if ( v22 )
        {
          v46 = 0;
          v54 = 0;
          v23 = v3;
          if ( v3 > 0x80 )
          {
            v29 = v3 * (unsigned __int128)8uLL;
            if ( !is_mul_ok(v3, 8u) )
              LODWORD(v29) = -1;
            v28 = (unsigned __int64 *)MMMAlloc(v29, DWORD2(v29));
            v5 = v28;
            v54 = v28;
          }
          else
          {
            v24 = 8LL * v3 + 15;
            if ( v24 <= 8 * (unsigned __int64)v3 )
              v24 = 0xFFFFFFFFFFFFFF0LL;
            v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
            v26 = alloca(v25);
            v27 = alloca(v25);
            v28 = (unsigned __int64 *)&v46;
          }
          v46 = v28;
          v30 = 0;
          v31 = v23 * (unsigned __int128)0x25B0uLL;
          if ( !is_mul_ok(v23, 0x25B0u) )
            LODWORD(v31) = -1;
          v32 = MMMAlloc(v31, DWORD2(v31));
          *((_QWORD *)v4 + 4) = v32;
          OnNullThrowOOM(v32);
          v33 = v23 * (unsigned __int128)4u;
          if ( !is_mul_ok(v23, 4u) )
            LODWORD(v33) = -1;
          v34 = MMMAlloc(v33, DWORD2(v33));
          *((_QWORD *)v4 + 5) = v34;
          OnNullThrowOOM(v34);
          v35 = v49;
          memset_0(*((void **)v4 + 5), 0, (unsigned int)(4 * v49));
          v36 = (unsigned int)(v35 + 1);
          v49 = v36;
          v37 = v55;
          while ( 1 )
          {
            v38 = ((__int64 (__fastcall *)(struct IRowset *, _QWORD, _QWORD, unsigned __int64, unsigned int *, unsigned __int64 **))v47->lpVtbl->GetNextRows)(
                    v47,
                    0,
                    0,
                    v36 - v30,
                    v51,
                    &v46);
            if ( v38 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049470[0] )
                bidTraceW(off_1800491B8[0], 504832, off_180049470[0], (unsigned int)v38, 493);
              ThrowHR(v38);
            }
            v39 = *(_QWORD *)v51;
            v30 += *(_QWORD *)v51;
            if ( v30 <= v23 )
            {
              CMetaData::mdIterateColumns(v37, v47, v46, v22, v51[0]);
              v39 = *(_QWORD *)v51;
            }
            v40 = ((__int64 (__fastcall *)(struct IRowset *, __int64, unsigned __int64 *, _QWORD, _QWORD, _QWORD))v47->lpVtbl->ReleaseRows)(
                    v47,
                    v39,
                    v46,
                    0,
                    0,
                    0);
            if ( v40 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049468[0] )
                bidTraceW(off_1800491B8[0], 508928, off_180049468[0], (unsigned int)v40, 497);
              ThrowHR(v40);
            }
            if ( v30 >= v23 )
              break;
            if ( !*(_QWORD *)v51 )
              goto LABEL_45;
            v36 = v49;
          }
          if ( v30 != v23 )
          {
LABEL_45:
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_180049460[0] )
                bidTraceW(off_1800491B8[0], 518144, off_180049460[0], 2147549183LL, 506);
            }
            ThrowHR(-2147418113);
          }
          v41 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))v47->lpVtbl->QueryInterface)(
                  v47,
                  &IID_IAccessor,
                  &v52);
          v42 = v41;
          if ( v41 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049458[0] )
              bidTraceW(off_1800491B8[0], 521216, off_180049458[0], (unsigned int)v41, 509);
            ThrowHR(v42);
          }
          v43 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v52 + 48LL))(v52, v22, 0);
          v44 = v43;
          if ( v43 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049450[0] )
              bidTraceW(off_1800491B8[0], 522240, off_180049450[0], (unsigned int)v43, 510);
            ThrowHR(v44);
          }
          operator delete(v5);
        }
      }
      operator delete(v6);
    }
    v45 = v53;
  }
  CoTaskMemFree(v45);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v52);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v47);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v48);
}

```

## disassembly

```asm
0x1800031e4  push    rbp
0x1800031e6  push    rbx
0x1800031e7  push    rsi
0x1800031e8  push    rdi
0x1800031e9  push    r12
0x1800031eb  push    r13
0x1800031ed  push    r14
0x1800031ef  push    r15
0x1800031f1  sub     rsp, 0E8h
0x1800031f8  lea     rbp, [rsp+50h]
0x1800031fd  mov     rax, cs:__security_cookie
0x180003204  xor     rax, rbp
0x180003207  mov     [rbp+0D0h+var_50], rax
0x18000320e  mov     esi, r8d
0x180003211  mov     dword ptr [rbp+0D0h+var_B8], r8d
0x180003215  mov     r9, rdx
0x180003218  mov     r15, rcx
0x18000321b  mov     [rbp+0D0h+var_88], rcx
0x18000321f  xor     ebx, ebx
0x180003221  mov     [rbp+0D0h+var_C0], rbx
0x180003225  mov     [rbp+0D0h+var_C8], rbx
0x180003229  mov     [rbp+0D0h+var_A0], rbx
0x18000322d  mov     [rbp+0D0h+var_98], rbx
0x180003231  mov     [rbp+0D0h+var_B0], rbx
0x180003235  mov     qword ptr [rbp+0D0h+var_A8], rbx
0x180003239  cmp     [rcx+20h], rbx
0x18000323d  jnz     loc_180003735
0x180003243  cmp     [rcx+8], rbx
0x180003247  jnz     loc_180003735
0x18000324d  mov     rax, [rdx]
0x180003250  lea     r8, [rbp+0D0h+var_C0]
0x180003254  lea     rdx, IID_IColumnsRowset
0x18000325b  mov     rcx, r9
0x18000325e  mov     rax, [rax]
0x180003261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003266  test    eax, eax
0x180003268  js      loc_1800036AA
0x18000326e  mov     rcx, [rbp+0D0h+var_C0]
0x180003272  mov     rax, [rcx]
0x180003275  lea     r8, [rbp+0D0h+var_98]
0x180003279  lea     rdx, [rbp+0D0h+var_B0]
0x18000327d  mov     rax, [rax+18h]
0x180003281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003286  test    eax, eax
0x180003288  js      loc_1800036AA
0x18000328e  mov     edi, ebx
0x180003290  mov     [rbp+0D0h+var_80], rbx
0x180003294  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003298  mov     rdx, 0FFFFFFFFFFFFFF0h; unsigned int
0x1800032a2  mov     rax, [rbp+0D0h+var_B0]
0x1800032a6  cmp     eax, 20h ; ' '
0x1800032a9  ja      short loc_1800032D3
0x1800032ab  mov     eax, eax
0x1800032ad  shl     rax, 5
0x1800032b1  lea     rcx, [rax+0Fh]
0x1800032b5  cmp     rcx, rax
0x1800032b8  ja      short loc_1800032BD
0x1800032ba  mov     rcx, rdx
0x1800032bd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800032c1  mov     rax, rcx
0x1800032c4  call    _alloca_probe
0x1800032c9  sub     rsp, rcx
0x1800032cc  lea     r12, [rsp+120h+var_D0]
0x1800032d1  jmp     short loc_1800032F2
0x1800032d3  mov     ecx, eax
0x1800032d5  mov     eax, 20h ; ' '
0x1800032da  mul     rcx
0x1800032dd  cmovb   rax, r8
0x1800032e1  mov     ecx, eax; unsigned int
0x1800032e3  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800032e8  mov     rdi, rax
0x1800032eb  mov     [rbp+0D0h+var_80], rax
0x1800032ef  mov     r12, rax
0x1800032f2  mov     rcx, r12; void *
0x1800032f5  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800032fa  mov     r14d, ebx
0x1800032fd  mov     edx, ebx
0x1800032ff  mov     dword ptr [rbp+0D0h+var_D0], ebx
0x180003302  mov     r13, [rbp+0D0h+var_B0]
0x180003306  test    r13d, r13d
0x180003309  jz      loc_1800033CC
0x18000330f  lea     rcx, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180003316  mov     ebx, r14d
0x180003319  shl     rbx, 5
0x18000331d  mov     rax, [rbp+0D0h+var_98]
0x180003321  mov     [rbp+0D0h+var_90], rax
0x180003325  movups  xmm0, xmmword ptr [rbx+rax]
0x180003329  movaps  [rbp+0D0h+Buf1], xmm0
0x18000332d  movups  xmm1, xmmword ptr [rbx+rax+10h]
0x180003332  movaps  [rbp+0D0h+var_60], xmm1
0x180003336  mov     r15d, 0Bh
0x18000333c  cmp     r15d, 1Fh
0x180003340  jnb     short loc_1800033B4
0x180003342  mov     eax, r15d
0x180003345  lea     rsi, [rax+rax*4]
0x180003349  add     rsi, rsi
0x18000334c  mov     eax, dword ptr [rbp+0D0h+var_60]
0x18000334f  cmp     eax, [rcx+rsi*8+10h]
0x180003353  jnz     short loc_18000337C
0x180003355  lea     rdx, [rcx+rsi*8]; Buf2
0x180003359  mov     r8d, 10h; Size
0x18000335f  lea     rcx, [rbp+0D0h+Buf1]; Buf1
0x180003363  call    memcmp_0
0x180003368  lea     rcx, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x18000336f  test    eax, eax
0x180003371  jnz     short loc_18000337C
0x180003373  mov     eax, dword ptr [rbp+0D0h+var_60+8]
0x180003376  cmp     eax, [rcx+rsi*8+18h]
0x18000337a  jz      short loc_180003381
0x18000337c  inc     r15d
0x18000337f  jmp     short loc_18000333C
0x180003381  mov     edx, dword ptr [rbp+0D0h+var_D0]
0x180003384  mov     eax, edx
0x180003386  shl     rax, 5
0x18000338a  inc     edx
0x18000338c  mov     dword ptr [rbp+0D0h+var_D0], edx
0x18000338f  mov     rcx, [rbp+0D0h+var_90]
0x180003393  movups  xmm0, xmmword ptr [rbx+rcx]
0x180003397  movups  xmmword ptr [rax+r12], xmm0
0x18000339c  movups  xmm1, xmmword ptr [rbx+rcx+10h]
0x1800033a1  movups  xmmword ptr [rax+r12+10h], xmm1
0x1800033a7  mov     r13, [rbp+0D0h+var_B0]
0x1800033ab  lea     rcx, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x1800033b2  jmp     short loc_1800033B7
0x1800033b4  mov     edx, dword ptr [rbp+0D0h+var_D0]
0x1800033b7  inc     r14d
0x1800033ba  cmp     r14d, r13d
0x1800033bd  jb      loc_180003316
0x1800033c3  mov     r15, [rbp+0D0h+var_88]
0x1800033c7  mov     esi, dword ptr [rbp+0D0h+var_B8]
0x1800033ca  xor     ebx, ebx
0x1800033cc  mov     rcx, [rbp+0D0h+var_C0]
0x1800033d0  mov     rax, [rcx]
0x1800033d3  mov     r8d, edx
0x1800033d6  lea     rdx, [rbp+0D0h+var_C8]
0x1800033da  mov     [rsp+120h+var_E8], rdx
0x1800033df  mov     [rsp+120h+var_F0], rbx
0x1800033e4  mov     dword ptr [rsp+120h+var_F8], ebx
0x1800033e8  lea     rdx, IID_IRowset
0x1800033ef  mov     qword ptr [rsp+120h+var_100], rdx
0x1800033f4  mov     r9, r12
0x1800033f7  xor     edx, edx
0x1800033f9  mov     rax, [rax+20h]
0x1800033fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003402  test    eax, eax
0x180003404  js      loc_1800036A1
0x18000340a  mov     rdx, [rbp+0D0h+var_C8]; struct IRowset *
0x18000340e  call    ?mdSetupAccessor@CMetaData@@AEAA_KPEAUIRowset@@@Z; CMetaData::mdSetupAccessor(IRowset *)
0x180003413  mov     r12, rax
0x180003416  test    rax, rax
0x180003419  jz      loc_1800036A1
0x18000341f  mov     [rbp+0D0h+var_D0], rbx
0x180003423  mov     [rbp+0D0h+var_90], rbx
0x180003427  mov     r14d, esi
0x18000342a  cmp     esi, 80h
0x180003430  ja      short loc_180003467
0x180003432  lea     rax, ds:0[r14*8]
0x18000343a  lea     rcx, [rax+0Fh]
0x18000343e  cmp     rcx, rax
0x180003441  ja      short loc_18000344D
0x180003443  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000344d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180003451  mov     rax, rcx
0x180003454  call    _alloca_probe
0x180003459  sub     rsp, rcx
0x18000345c  lea     rax, [rsp+120h+var_D0]
0x180003461  or      r13, 0FFFFFFFFFFFFFFFFh
0x180003465  jmp     short loc_180003488
0x180003467  mov     eax, 8
0x18000346c  mul     r14
0x18000346f  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180003476  cmovb   rax, r13
0x18000347a  mov     ecx, eax; unsigned int
0x18000347c  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180003481  mov     rbx, rax
0x180003484  mov     [rbp+0D0h+var_90], rax
0x180003488  mov     [rbp+0D0h+var_D0], rax
0x18000348c  xor     esi, esi
0x18000348e  mov     eax, 25B0h
0x180003493  mul     r14
0x180003496  cmovb   rax, r13
0x18000349a  mov     ecx, eax; unsigned int
0x18000349c  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800034a1  mov     [r15+20h], rax
0x1800034a5  mov     rcx, rax; void *
0x1800034a8  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800034ad  lea     eax, [rsi+4]
0x1800034b0  mul     r14
0x1800034b3  cmovb   rax, r13
0x1800034b7  mov     ecx, eax; unsigned int
0x1800034b9  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800034be  mov     [r15+28h], rax
0x1800034c2  mov     rcx, rax; void *
0x1800034c5  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800034ca  mov     r13d, dword ptr [rbp+0D0h+var_B8]
0x1800034ce  lea     r8d, ds:0[r13*4]; Size
0x1800034d6  xor     edx, edx; Val
0x1800034d8  mov     rcx, [r15+28h]; void *
0x1800034dc  call    memset_0
0x1800034e1  lea     edx, [r13+1]
0x1800034e5  mov     [rbp+0D0h+var_B8], rdx
0x1800034e9  mov     r13, [rbp+0D0h+var_88]
0x1800034ed  mov     rcx, [rbp+0D0h+var_C8]
0x1800034f1  mov     rax, [rcx]
0x1800034f4  mov     r9, rdx
0x1800034f7  sub     r9, rsi
0x1800034fa  lea     rdx, [rbp+0D0h+var_D0]
0x1800034fe  mov     [rsp+120h+var_F8], rdx
0x180003503  lea     rdx, [rbp+0D0h+var_A8]
0x180003507  mov     qword ptr [rsp+120h+var_100], rdx
0x18000350c  xor     r8d, r8d
0x18000350f  xor     edx, edx
0x180003511  mov     rax, [rax+28h]
0x180003515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351a  mov     r15d, eax
0x18000351d  test    eax, eax
0x18000351f  js      loc_1800036F4
0x180003525  mov     rdx, qword ptr [rbp+0D0h+var_A8]
0x180003529  add     rsi, rdx
0x18000352c  cmp     rsi, r14
0x18000352f  ja      short loc_18000354C
0x180003531  mov     [rsp+120h+var_100], edx; unsigned int
0x180003535  mov     r9, r12; unsigned __int64
0x180003538  mov     r8, [rbp+0D0h+var_D0]; unsigned __int64 *
0x18000353c  mov     rdx, [rbp+0D0h+var_C8]; struct IRowset *
0x180003540  mov     rcx, r13; this
0x180003543  call    ?mdIterateColumns@CMetaData@@AEAAXPEAUIRowset@@PEA_K_KK@Z; CMetaData::mdIterateColumns(IRowset *,unsigned __int64 *,unsigned __int64,ulong)
0x180003548  mov     rdx, qword ptr [rbp+0D0h+var_A8]
0x18000354c  mov     rcx, [rbp+0D0h+var_C8]
0x180003550  mov     rax, [rcx]
0x180003553  mov     [rsp+120h+var_F8], 0
0x18000355c  mov     qword ptr [rsp+120h+var_100], 0
0x180003565  xor     r9d, r9d
0x180003568  mov     r8, [rbp+0D0h+var_D0]
0x18000356c  mov     rax, [rax+30h]
0x180003570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003575  mov     r15d, eax
0x180003578  test    eax, eax
0x18000357a  js      loc_1800036B3
0x180003580  cmp     rsi, r14
0x180003583  jnb     short loc_180003595
0x180003585  cmp     qword ptr [rbp+0D0h+var_A8], 0
0x18000358a  jz      short loc_180003597
0x18000358c  mov     rdx, [rbp+0D0h+var_B8]
0x180003590  jmp     loc_1800034ED
0x180003595  jz      short loc_1800035DC
0x180003597  mov     ebx, 8000FFFFh
0x18000359c  test    byte ptr cs:_bidGblFlags, 2
0x1800035a3  jz      short loc_1800035D4
0x1800035a5  mov     rax, cs:off_180049460; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x1800035ac  test    rax, rax
0x1800035af  jz      short loc_1800035D4
0x1800035b1  mov     [rsp+120h+var_100], 1FAh
0x1800035b9  mov     r9d, ebx
0x1800035bc  mov     r8, cs:off_180049460; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x1800035c3  mov     edx, 7E800h
0x1800035c8  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800035cf  call    _bidTraceW
0x1800035d4  mov     ecx, ebx; int
0x1800035d6  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800035dc  mov     rcx, [rbp+0D0h+var_C8]
0x1800035e0  mov     rax, [rcx]
0x1800035e3  lea     r8, [rbp+0D0h+var_A0]
0x1800035e7  lea     rdx, IID_IAccessor
0x1800035ee  mov     rax, [rax]
0x1800035f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f6  mov     esi, eax
0x1800035f8  test    eax, eax
0x1800035fa  jns     short loc_18000363C
0x1800035fc  test    byte ptr cs:_bidGblFlags, 2
0x180003603  jz      short loc_180003634
0x180003605  mov     rcx, cs:off_180049458; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x18000360c  test    rcx, rcx
0x18000360f  jz      short loc_180003634
0x180003611  mov     [rsp+120h+var_100], 1FDh
0x180003619  mov     r9d, eax
0x18000361c  mov     r8, cs:off_180049458; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x180003623  mov     edx, 7F400h
0x180003628  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000362f  call    _bidTraceW
0x180003634  mov     ecx, esi; int
0x180003636  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000363c  mov     rcx, [rbp+0D0h+var_A0]
0x180003640  mov     rax, [rcx]
0x180003643  xor     r8d, r8d
0x180003646  mov     rdx, r12
0x180003649  mov     rax, [rax+30h]
0x18000364d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003652  mov     esi, eax
0x180003654  test    eax, eax
0x180003656  jns     short loc_180003698
0x180003658  test    byte ptr cs:_bidGblFlags, 2
0x18000365f  jz      short loc_180003690
0x180003661  mov     rcx, cs:off_180049450; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x180003668  test    rcx, rcx
0x18000366b  jz      short loc_180003690
0x18000366d  mov     [rsp+120h+var_100], 1FEh
0x180003675  mov     r9d, eax
0x180003678  mov     r8, cs:off_180049450; "<CMetaData::mdGetColumnsRowsetData|ADO|"...
0x18000367f  mov     edx, 7F800h
  ... truncated ...
```
