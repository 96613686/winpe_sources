# CImpIColumnsUpdateInfo::GetColumnUpdateInfo(unsigned __int64 *,DBCOLUMNUPDATEINFO * *,ushort * *,uchar * *)

- ea: `0x180013180`
- end: `0x1800139db`
- name: `?GetColumnUpdateInfo@CImpIColumnsUpdateInfo@@UEAAJPEA_KPEAPEAUDBCOLUMNUPDATEINFO@@PEAPEAGPEAPEAE@Z`
- size: `2139`
- prototype: `__int64 __fastcall(CImpIColumnsUpdateInfo *__hidden this, unsigned __int64 *, struct DBCOLUMNUPDATEINFO **, unsigned __int16 **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x180002770`
- `0x180013180`
- `0x1800139e4`
- `0x180016584`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f092`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001397a`
- `ole32!CoTaskMemFree` at `0x18001398c`
- `ole32!CoTaskMemFree` at `0x18001399e`
- `ole32!CoTaskMemFree` at `0x1800139ae`
- `ole32!CoTaskMemFree` at `0x18001397a`
- `ole32!CoTaskMemFree` at `0x18001398c`
- `ole32!CoTaskMemFree` at `0x18001399e`
- `ole32!CoTaskMemFree` at `0x1800139ae`
- `ole32!CoTaskMemAlloc` at `0x1800132d4`
- `ole32!CoTaskMemAlloc` at `0x1800134d9`
- `ole32!CoTaskMemAlloc` at `0x1800132d4`
- `ole32!CoTaskMemAlloc` at `0x1800134d9`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800131e6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800131e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CImpIColumnsUpdateInfo::GetColumnUpdateInfo(
        CImpIColumnsUpdateInfo *this,
        unsigned __int64 *a2,
        struct DBCOLUMNUPDATEINFO **a3,
        unsigned __int16 **a4,
        unsigned __int8 **a5)
{
  unsigned __int16 **v5; // rdi
  unsigned __int8 *v9; // r12
  SIZE_T v10; // r14
  __int64 v11; // r15
  unsigned __int8 **v12; // rsi
  int v13; // eax
  int v14; // ebx
  struct DBCOLUMNUPDATEINFO *v15; // r13
  void *v16; // r11
  unsigned int v17; // r8d
  __int64 v18; // r9
  __int64 v19; // rdx
  _OWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int16 v23; // ax
  __int64 v24; // rax
  __int16 v25; // ax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rbx
  unsigned int v33; // eax
  __int64 v34; // r11
  __int64 v35; // rdi
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // r11
  int v39; // esi
  _QWORD *v40; // rsi
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // eax
  int v44; // r12d
  __int64 v45; // rax
  __int64 v46; // rax
  int v47; // eax
  int v48; // r12d
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // eax
  int v52; // r12d
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  int v56; // r8d
  void *v57; // rbx
  unsigned __int16 *v58; // rax
  void *v59; // rdi
  unsigned int v60; // esi
  unsigned int v62; // [rsp+30h] [rbp-88h]
  LPVOID pv; // [rsp+38h] [rbp-80h] BYREF
  int v64; // [rsp+40h] [rbp-78h]
  unsigned __int16 *v65; // [rsp+48h] [rbp-70h]
  struct DBCOLUMNUPDATEINFO *v66; // [rsp+50h] [rbp-68h]
  unsigned __int16 *v67; // [rsp+58h] [rbp-60h]
  LPVOID v68; // [rsp+60h] [rbp-58h] BYREF
  __int64 v69; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int64 v70[9]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v71; // [rsp+C0h] [rbp+8h]

  v5 = a4;
  v69 = 0;
  v66 = 0;
  v68 = 0;
  pv = 0;
  v9 = 0;
  v67 = 0;
  v10 = 0;
  v11 = *((_QWORD *)this + 3);
  v71 = *(_DWORD *)(v11 + 152);
  v70[0] = 0;
  v64 = 0;
  SetErrorInfo(0, 0);
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( v5 )
    *v5 = 0;
  v12 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 || !a3 || !v5 || !a5 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049988[0] )
      bidTraceW(off_1800491D8[0], 70656, off_180049988[0], 2147942487LL, 69);
    ThrowHR(-2147024809);
  }
  (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(*((_QWORD *)this + 3), &IID_IColumnsInfo, &v69);
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v69 + 24LL))(
          v69,
          v70,
          &v68,
          &pv);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049980[0] )
        bidTraceW(off_1800491D8[0], 76800, off_180049980[0], (unsigned int)v13, 75);
    }
    ThrowHR(v14);
  }
  v15 = (struct DBCOLUMNUPDATEINFO *)CoTaskMemAlloc(168LL * v71);
  v66 = v15;
  v16 = 0;
  if ( !v15 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049978[0] )
      bidTraceW(off_1800491D8[0], 88064, off_180049978[0], 2147942414LL, 86);
    ThrowHR(-2147024882);
  }
  v17 = 0;
  if ( !v71 )
    goto LABEL_105;
  v18 = 0;
  do
  {
    v19 = 168 * v18;
    v20 = v68;
    *(_OWORD *)((char *)v15 + v19) = *((_OWORD *)v68 + 5 * v18);
    *(_OWORD *)((char *)v15 + v19 + 16) = v20[5 * v18 + 1];
    *(_OWORD *)((char *)v15 + v19 + 32) = v20[5 * v18 + 2];
    *(_OWORD *)((char *)v15 + v19 + 48) = v20[5 * v18 + 3];
    *(_OWORD *)((char *)v15 + v19 + 64) = v20[5 * v18 + 4];
    v21 = 9648 * v18;
    v22 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(9648 * v18 + v22 + 9532) )
      v23 = 0;
    else
      v23 = *(_WORD *)(v21 + v22 + 9528);
    *(_WORD *)((char *)v15 + v19 + 114) = v23;
    v24 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(v24 + v21 + 9584) )
      v25 = 0;
    else
      v25 = *(_WORD *)(v24 + v21 + 9580);
    *(_WORD *)((char *)v15 + v19 + 112) = v25;
    v26 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(v21 + v26 + 9608) )
      v27 = 0;
    else
      v27 = *(_QWORD *)(v21 + v26 + 9616);
    *(_QWORD *)((char *)v15 + v19 + 120) = v27;
    v28 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(v21 + v28 + 9632) )
      v29 = 0;
    else
      v29 = *(_QWORD *)(v21 + v28 + 9640);
    *(_QWORD *)((char *)v15 + v19 + 128) = v29;
    *(_QWORD *)((char *)v15 + v19 + 152) = 0;
    *(_DWORD *)((char *)v15 + v19 + 160) = 0;
    v30 = *(_QWORD *)(v11 + 336);
    if ( !*(_DWORD *)(v30 + v21 + 3216) )
      v10 += *(_QWORD *)(v30 + v21 + 3224) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 4260) )
      v10 += *(_QWORD *)(v30 + v21 + 4264) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 5300) )
      v10 += *(_QWORD *)(v30 + v21 + 5304) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 6340) )
      v10 += *(_QWORD *)(v30 + v21 + 6344) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 9608) )
      v10 += *(_QWORD *)(v30 + v21 + 9616) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 9632) )
      v10 += *(_QWORD *)(v30 + v21 + 9640) + 2LL;
    ++v17;
    ++v18;
  }
  while ( v17 < v71 );
  if ( v10 )
  {
    v31 = (unsigned __int16 *)CoTaskMemAlloc(v10);
    v9 = (unsigned __int8 *)v31;
    v65 = v31;
    v67 = v31;
    v16 = 0;
    if ( !v31 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049970[0] )
        bidTraceW(off_1800491D8[0], 141312, off_180049970[0], 2147942414LL, 138);
      ThrowHR(-2147024882);
    }
    v32 = v31;
    v33 = 0;
    while ( 1 )
    {
      v62 = v33;
      if ( v33 >= v71 )
        break;
      v34 = v33;
      v35 = 9648LL * v33;
      v36 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v36 + 3216) )
      {
        v40 = (_QWORD *)((char *)v15 + 168 * v34);
        v16 = 0;
        v40[12] = 0;
      }
      else
      {
        v37 = StringCbCopyW(v32, (unsigned __int64)&v9[v10 - (_QWORD)v32], (const unsigned __int16 *)(v35 + v36 + 2188));
        v39 = v37;
        if ( v37 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049968[0] )
            bidTraceW(off_1800491D8[0], 152576, off_180049968[0], (unsigned int)v37, 149);
          ThrowHR(v39);
        }
        v40 = (_QWORD *)((char *)v15 + 168 * v38);
        v40[12] = v32;
        v41 = -1;
        v16 = 0;
        do
          ++v41;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v41 + 2188) );
        v32 += v41 + 1;
      }
      v42 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v42 + 4260) )
      {
        v40[13] = 0;
      }
      else
      {
        v43 = StringCbCopyW(v32, (unsigned __int64)&v9[v10 - (_QWORD)v32], (const unsigned __int16 *)(v35 + v42 + 3232));
        v44 = v43;
        if ( v43 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049960[0] )
            bidTraceW(off_1800491D8[0], 163840, off_180049960[0], (unsigned int)v43, 160);
          ThrowHR(v44);
        }
        v40[13] = v32;
        v45 = -1;
        do
          ++v45;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v45 + 3232) != (_WORD)v16 );
        v32 += v45 + 1;
        v9 = (unsigned __int8 *)v65;
      }
      v46 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v46 + 5300) == (_DWORD)v16 )
      {
        v47 = StringCbCopyW(v32, (unsigned __int64)&v9[v10 - (_QWORD)v32], (const unsigned __int16 *)(v35 + v46 + 4272));
        v48 = v47;
        if ( v47 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049958[0] )
            bidTraceW(off_1800491D8[0], 175104, off_180049958[0], (unsigned int)v47, 171);
          ThrowHR(v48);
        }
        v40[11] = v32;
        v49 = -1;
        do
          ++v49;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v49 + 4272) != (_WORD)v16 );
        v32 += v49 + 1;
      }
      else
      {
        v40[11] = v16;
      }
      v50 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v50 + 6340) == (_DWORD)v16 )
      {
        v51 = StringCbCopyW(
                v32,
                (unsigned __int64)v65 + v10 - (_QWORD)v32,
                (const unsigned __int16 *)(v35 + v50 + 5312));
        v52 = v51;
        if ( v51 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049950[0] )
            bidTraceW(off_1800491D8[0], 186368, off_180049950[0], (unsigned int)v51, 182);
          ThrowHR(v52);
        }
        v40[10] = v32;
        v53 = -1;
        do
          ++v53;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v53 + 5312) != (_WORD)v16 );
        v32 += v53 + 1;
      }
      else
      {
        v40[10] = v16;
      }
      v54 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v54 + 9608) == (_DWORD)v16 )
      {
        memcpy_0(v32, *(const void **)(v35 + v54 + 9600), *(_QWORD *)(v35 + v54 + 9616));
        v40[17] = v32;
        v32 = (unsigned __int16 *)((char *)v32 + *(_QWORD *)(v35 + *(_QWORD *)(v11 + 336) + 9616));
        v16 = 0;
      }
      else
      {
        v40[17] = v16;
      }
      v55 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v55 + 9632) == (_DWORD)v16 )
      {
        memcpy_0(v32, *(const void **)(v35 + v55 + 9624), *(_QWORD *)(v35 + v55 + 9640));
        v40[18] = v32;
        v32 = (unsigned __int16 *)((char *)v32 + *(_QWORD *)(v35 + *(_QWORD *)(v11 + 336) + 9640));
        v16 = 0;
      }
      else
      {
        v40[18] = v16;
      }
      v33 = v62 + 1;
      v9 = (unsigned __int8 *)v65;
    }
    v12 = a5;
    v5 = a4;
    v56 = v64;
  }
  else
  {
LABEL_105:
    v56 = 1;
  }
  v57 = v16;
  v66 = (struct DBCOLUMNUPDATEINFO *)v16;
  *a3 = v15;
  v58 = (unsigned __int16 *)pv;
  pv = v16;
  *v5 = v58;
  v59 = v16;
  v67 = (unsigned __int16 *)v16;
  *v12 = v9;
  *a2 = v70[0];
  v60 = Exit(v56, 0);
  CoTaskMemFree(v59);
  CoTaskMemFree(pv);
  CoTaskMemFree(v68);
  CoTaskMemFree(v57);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v69);
  return v60;
}

```

## disassembly

```asm
0x180013180  mov     rax, rsp
0x180013183  mov     [rax+20h], r9
0x180013187  mov     [rax+18h], r8
0x18001318b  mov     [rax+10h], rdx
0x18001318f  push    rbx
0x180013190  push    rsi
0x180013191  push    rdi
0x180013192  push    r12
0x180013194  push    r13
0x180013196  push    r14
0x180013198  push    r15
0x18001319a  sub     rsp, 80h
0x1800131a1  mov     rdi, r9
0x1800131a4  mov     r13, r8
0x1800131a7  mov     rsi, rdx
0x1800131aa  mov     rbx, rcx
0x1800131ad  xor     ecx, ecx; dwReserved
0x1800131af  mov     [rax-50h], rcx
0x1800131b3  mov     [rax-68h], rcx
0x1800131b7  mov     [rax-58h], rcx
0x1800131bb  mov     [rax-80h], rcx
0x1800131bf  mov     r12d, ecx
0x1800131c2  mov     [rax-60h], rcx
0x1800131c6  mov     r14d, ecx
0x1800131c9  mov     r15, [rbx+18h]
0x1800131cd  mov     eax, [r15+98h]
0x1800131d4  mov     [rsp+0B8h+arg_0], eax
0x1800131db  mov     [rsp+0B8h+var_48], rcx
0x1800131e0  mov     [rsp+0B8h+var_78], ecx
0x1800131e4  xor     edx, edx; perrinfo
0x1800131e6  call    cs:__imp_SetErrorInfo
0x1800131ed  nop     dword ptr [rax+rax+00h]
0x1800131f2  xor     ecx, ecx
0x1800131f4  test    rsi, rsi
0x1800131f7  jz      short loc_1800131FC
0x1800131f9  mov     [rsi], rcx
0x1800131fc  test    r13, r13
0x1800131ff  jz      short loc_180013205
0x180013201  mov     [r13+0], rcx
0x180013205  test    rdi, rdi
0x180013208  jz      short loc_18001320D
0x18001320a  mov     [rdi], rcx
0x18001320d  mov     rsi, [rsp+0B8h+arg_20]
0x180013215  test    rsi, rsi
0x180013218  jz      short loc_18001321D
0x18001321a  mov     [rsi], rcx
0x18001321d  cmp     [rsp+0B8h+arg_8], rcx
0x180013225  jz      loc_180013913
0x18001322b  test    r13, r13
0x18001322e  jz      loc_180013913
0x180013234  test    rdi, rdi
0x180013237  jz      loc_180013913
0x18001323d  test    rsi, rsi
0x180013240  jz      loc_180013913
0x180013246  mov     rcx, [rbx+18h]
0x18001324a  mov     rax, [rcx]
0x18001324d  lea     r8, [rsp+0B8h+var_50]
0x180013252  lea     rdx, IID_IColumnsInfo
0x180013259  mov     rax, [rax]
0x18001325c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013261  mov     rcx, [rsp+0B8h+var_50]
0x180013266  mov     rax, [rcx]
0x180013269  lea     r9, [rsp+0B8h+pv]
0x18001326e  lea     r8, [rsp+0B8h+var_58]
0x180013273  lea     rdx, [rsp+0B8h+var_48]
0x180013278  mov     rax, [rax+18h]
0x18001327c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013281  mov     ebx, eax
0x180013283  test    eax, eax
0x180013285  jns     short loc_1800132C6
0x180013287  test    byte ptr cs:_bidGblFlags, 2
0x18001328e  jz      short loc_1800132BF
0x180013290  mov     rcx, cs:off_180049980; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013297  test    rcx, rcx
0x18001329a  jz      short loc_1800132BF
0x18001329c  mov     [rsp+0B8h+var_98], 4Bh ; 'K'
0x1800132a4  mov     r9d, eax
0x1800132a7  mov     r8, cs:off_180049980; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x1800132ae  mov     edx, 12C00h
0x1800132b3  mov     rcx, cs:off_1800491D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800132ba  call    _bidTraceW
0x1800132bf  mov     ecx, ebx; int
0x1800132c1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800132c6  mov     ebx, [rsp+0B8h+arg_0]
0x1800132cd  imul    rcx, rbx, 0A8h; cb
0x1800132d4  call    cs:__imp_CoTaskMemAlloc
0x1800132db  nop     dword ptr [rax+rax+00h]
0x1800132e0  mov     r13, rax
0x1800132e3  mov     [rsp+0B8h+var_68], rax
0x1800132e8  xor     r11d, r11d
0x1800132eb  test    rax, rax
0x1800132ee  jnz     short loc_180013335
0x1800132f0  test    byte ptr cs:_bidGblFlags, 2
0x1800132f7  jz      short loc_18001332B
0x1800132f9  mov     rax, cs:off_180049978; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013300  test    rax, rax
0x180013303  jz      short loc_18001332B
0x180013305  mov     [rsp+0B8h+var_98], 56h ; 'V'
0x18001330d  mov     r9d, 8007000Eh
0x180013313  mov     r8, cs:off_180049978; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x18001331a  mov     edx, 15800h
0x18001331f  mov     rcx, cs:off_1800491D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180013326  call    _bidTraceW
0x18001332b  mov     ecx, 8007000Eh; int
0x180013330  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180013335  mov     r8d, r11d
0x180013338  test    ebx, ebx
0x18001333a  jz      loc_1800138B9
0x180013340  mov     r9, r11
0x180013343  imul    rdx, r9, 0A8h
0x18001334a  lea     rcx, [r9+r9*4]
0x18001334e  add     rcx, rcx
0x180013351  mov     rax, [rsp+0B8h+var_58]
0x180013356  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001335a  movups  xmmword ptr [rdx+r13], xmm0
0x18001335f  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x180013364  movups  xmmword ptr [rdx+r13+10h], xmm1
0x18001336a  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x18001336f  movups  xmmword ptr [rdx+r13+20h], xmm0
0x180013375  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x18001337a  movups  xmmword ptr [rdx+r13+30h], xmm1
0x180013380  movups  xmm0, xmmword ptr [rax+rcx*8+40h]
0x180013385  movups  xmmword ptr [rdx+r13+40h], xmm0
0x18001338b  imul    rcx, r9, 25B0h
0x180013392  mov     rax, [r15+150h]
0x180013399  cmp     [rcx+rax+253Ch], r11d
0x1800133a1  jnz     short loc_1800133AD
0x1800133a3  movzx   eax, word ptr [rcx+rax+2538h]
0x1800133ab  jmp     short loc_1800133B0
0x1800133ad  mov     eax, r11d
0x1800133b0  mov     [rdx+r13+72h], ax
0x1800133b6  mov     rax, [r15+150h]
0x1800133bd  cmp     [rax+rcx+2570h], r11d
0x1800133c5  jnz     short loc_1800133D1
0x1800133c7  movzx   eax, word ptr [rax+rcx+256Ch]
0x1800133cf  jmp     short loc_1800133D4
0x1800133d1  mov     eax, r11d
0x1800133d4  mov     [rdx+r13+70h], ax
0x1800133da  mov     rax, [r15+150h]
0x1800133e1  cmp     [rcx+rax+2588h], r11d
0x1800133e9  jnz     short loc_1800133F5
0x1800133eb  mov     rax, [rcx+rax+2590h]
0x1800133f3  jmp     short loc_1800133F8
0x1800133f5  mov     rax, r11
0x1800133f8  mov     [rdx+r13+78h], rax
0x1800133fd  mov     rax, [r15+150h]
0x180013404  cmp     [rcx+rax+25A0h], r11d
0x18001340c  jnz     short loc_180013418
0x18001340e  mov     rax, [rcx+rax+25A8h]
0x180013416  jmp     short loc_18001341B
0x180013418  mov     rax, r11
0x18001341b  mov     [rdx+r13+80h], rax
0x180013423  mov     [rdx+r13+98h], r11
0x18001342b  mov     [rdx+r13+0A0h], r11d
0x180013433  mov     rdx, [r15+150h]
0x18001343a  cmp     [rdx+rcx+0C90h], r11d
0x180013442  jnz     short loc_180013450
0x180013444  add     r14, 2
0x180013448  add     r14, [rdx+rcx+0C98h]
0x180013450  cmp     [rdx+rcx+10A4h], r11d
0x180013458  jnz     short loc_180013466
0x18001345a  add     r14, 2
0x18001345e  add     r14, [rdx+rcx+10A8h]
0x180013466  cmp     [rdx+rcx+14B4h], r11d
0x18001346e  jnz     short loc_18001347C
0x180013470  add     r14, 2
0x180013474  add     r14, [rdx+rcx+14B8h]
0x18001347c  cmp     [rdx+rcx+18C4h], r11d
0x180013484  jnz     short loc_180013492
0x180013486  add     r14, 2
0x18001348a  add     r14, [rdx+rcx+18C8h]
0x180013492  cmp     [rdx+rcx+2588h], r11d
0x18001349a  jnz     short loc_1800134A8
0x18001349c  add     r14, 2
0x1800134a0  add     r14, [rdx+rcx+2590h]
0x1800134a8  cmp     [rdx+rcx+25A0h], r11d
0x1800134b0  jnz     short loc_1800134BE
0x1800134b2  add     r14, 2
0x1800134b6  add     r14, [rdx+rcx+25A8h]
0x1800134be  inc     r8d
0x1800134c1  inc     r9
0x1800134c4  cmp     r8d, ebx
0x1800134c7  jb      loc_180013343
0x1800134cd  test    r14, r14
0x1800134d0  jz      loc_1800138B9
0x1800134d6  mov     rcx, r14; cb
0x1800134d9  call    cs:__imp_CoTaskMemAlloc
0x1800134e0  nop     dword ptr [rax+rax+00h]
0x1800134e5  mov     r12, rax
0x1800134e8  mov     [rsp+0B8h+var_70], rax
0x1800134ed  mov     [rsp+0B8h+var_60], rax
0x1800134f2  xor     r11d, r11d
0x1800134f5  test    rax, rax
0x1800134f8  jnz     short loc_18001353F
0x1800134fa  test    byte ptr cs:_bidGblFlags, 2
0x180013501  jz      short loc_180013535
0x180013503  mov     rax, cs:off_180049970; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x18001350a  test    rax, rax
0x18001350d  jz      short loc_180013535
0x18001350f  mov     [rsp+0B8h+var_98], 8Ah
0x180013517  mov     r9d, 8007000Eh
0x18001351d  mov     r8, cs:off_180049970; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013524  mov     edx, 22800h
0x180013529  mov     rcx, cs:off_1800491D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180013530  call    _bidTraceW
0x180013535  mov     ecx, 8007000Eh; int
0x18001353a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001353f  mov     rbx, rax
0x180013542  mov     eax, r11d
0x180013545  mov     [rsp+0B8h+var_88], eax
0x180013549  cmp     eax, [rsp+0B8h+arg_0]
0x180013550  jnb     loc_1800138C1
0x180013556  mov     r11d, eax
0x180013559  imul    rdi, r11, 25B0h
0x180013560  mov     rax, [r15+150h]
0x180013567  cmp     dword ptr [rdi+rax+0C90h], 0
0x18001356f  jnz     loc_18001360C
0x180013575  lea     r8, [rax+88Ch]
0x18001357c  add     r8, rdi; unsigned __int16 *
0x18001357f  mov     rdx, r14
0x180013582  sub     rdx, rbx
0x180013585  add     rdx, r12; unsigned __int64
0x180013588  mov     rcx, rbx; unsigned __int16 *
0x18001358b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180013590  mov     esi, eax
0x180013592  test    eax, eax
0x180013594  jns     short loc_1800135D5
0x180013596  test    byte ptr cs:_bidGblFlags, 2
0x18001359d  jz      short loc_1800135CE
0x18001359f  mov     rcx, cs:off_180049968; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x1800135a6  test    rcx, rcx
0x1800135a9  jz      short loc_1800135CE
0x1800135ab  mov     [rsp+0B8h+var_98], 95h
0x1800135b3  mov     r9d, eax
0x1800135b6  mov     r8, cs:off_180049968; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x1800135bd  mov     edx, 25400h
0x1800135c2  mov     rcx, cs:off_1800491D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800135c9  call    _bidTraceW
0x1800135ce  mov     ecx, esi; int
0x1800135d0  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800135d5  imul    rsi, r11, 0A8h
0x1800135dc  add     rsi, r13
0x1800135df  mov     [rsi+60h], rbx
0x1800135e3  mov     rcx, [r15+150h]
0x1800135ea  add     rcx, rdi
0x1800135ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800135f1  xor     r11d, r11d
0x1800135f4  inc     rax
0x1800135f7  cmp     [rcx+rax*2+88Ch], r11w
0x180013600  jnz     short loc_1800135F4
0x180013602  lea     rbx, [rbx+rax*2]
0x180013606  add     rbx, 2
0x18001360a  jmp     short loc_18001361D
0x18001360c  imul    rsi, r11, 0A8h
0x180013613  add     rsi, r13
0x180013616  xor     r11d, r11d
0x180013619  mov     [rsi+60h], r11
0x18001361d  mov     rax, [r15+150h]
0x180013624  cmp     [rdi+rax+10A4h], r11d
0x18001362c  jnz     loc_1800136C3
0x180013632  lea     r8, [rax+0CA0h]
0x180013639  add     r8, rdi; unsigned __int16 *
0x18001363c  mov     rdx, r14
0x18001363f  sub     rdx, rbx
0x180013642  add     rdx, r12; unsigned __int64
0x180013645  mov     rcx, rbx; unsigned __int16 *
0x180013648  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001364d  mov     r12d, eax
0x180013650  test    eax, eax
0x180013652  jns     short loc_180013694
0x180013654  test    byte ptr cs:_bidGblFlags, 2
0x18001365b  jz      short loc_18001368C
0x18001365d  mov     rcx, cs:off_180049960; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013664  test    rcx, rcx
0x180013667  jz      short loc_18001368C
0x180013669  mov     [rsp+0B8h+var_98], 0A0h
0x180013671  mov     r9d, eax
0x180013674  mov     r8, cs:off_180049960; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x18001367b  mov     edx, 28000h
0x180013680  mov     rcx, cs:off_1800491D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180013687  call    _bidTraceW
0x18001368c  mov     ecx, r12d; int
0x18001368f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180013694  mov     [rsi+68h], rbx
0x180013698  mov     rcx, [r15+150h]
0x18001369f  add     rcx, rdi
0x1800136a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800136a6  inc     rax
0x1800136a9  cmp     [rcx+rax*2+0CA0h], r11w
0x1800136b2  jnz     short loc_1800136A6
0x1800136b4  lea     rbx, [rbx+rax*2]
0x1800136b8  add     rbx, 2
0x1800136bc  mov     r12, [rsp+0B8h+var_70]
0x1800136c1  jmp     short loc_1800136C7
0x1800136c3  mov     [rsi+68h], r11
0x1800136c7  mov     rax, [r15+150h]
0x1800136ce  cmp     [rdi+rax+14B4h], r11d
0x1800136d6  jnz     loc_180013768
0x1800136dc  lea     r8, [rax+10B0h]
0x1800136e3  add     r8, rdi; unsigned __int16 *
  ... truncated ...
```
