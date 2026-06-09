# CLogStorage::GetRestart(_RESTARTLOG *,_STRMTBL *)

- ea: `0x18000a288`
- end: `0x18000a98a`
- name: `?GetRestart@CLogStorage@@QEAAXPEAU_RESTARTLOG@@PEAU_STRMTBL@@@Z`
- size: `1794`
- prototype: `void __fastcall(CLogStorage *__hidden this, struct _RESTARTLOG *, struct _STRMTBL *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800065c8`

## callees

- `0x180001300`
- `0x18000a288`
- `0x18000b06c`
- `0x18000b2c8`
- `0x18000b658`
- `0x18000b798`
- `0x18000b974`
- `0x18000c6b8`
- `0x18000c7fc`
- `0x18000d998`
- `0x18001266c`
- `0x1800127f2`
- `0x18001280a`
- `0x180012830`
- `0x180015010`

## string_xrefs

- `0x18000a8a2`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000a8da`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000a912`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000a958`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000a8e1`: `IDS_DTC_LOG_INCOMPATIBLE`
- `0x18000a95f`: `IDS_DTC_LOG_INCOMPATIBLE`

## pseudocode

```c
void __fastcall CLogStorage::GetRestart(CLogStorage *this, struct _RESTARTLOG *a2, struct _STRMTBL *a3)
{
  ulong v3; // r12d
  unsigned int v5; // r14d
  struct CBuffer *v6; // r13
  struct CBuffer *v7; // rsi
  unsigned int v8; // ebx
  ulong v9; // r9d
  struct CBuffer *v10; // r15
  _DWORD *v11; // rcx
  unsigned int v12; // ecx
  struct _RESTARTPAGE *v13; // rbx
  ulong v14; // r9d
  struct _RESTARTPAGE *v15; // rax
  struct _RESTARTPAGE *v16; // rsi
  BOOL v17; // eax
  int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // r12d
  int v21; // r8d
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm2
  __int128 v25; // xmm3
  __int128 v26; // xmm4
  int v27; // r12d
  int v28; // ecx
  unsigned int v29; // edx
  struct CBuffer *v30; // rax
  int v31; // ebx
  unsigned int v32; // r8d
  int v33; // ecx
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  struct _RESTARTLOG *v38; // rcx
  int v39; // eax
  int v40; // eax
  void *v41; // r8
  ulong pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  int v43; // [rsp+34h] [rbp-CCh] BYREF
  BOOL v44; // [rsp+38h] [rbp-C8h]
  unsigned int v45; // [rsp+3Ch] [rbp-C4h] BYREF
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+44h] [rbp-BCh] BYREF
  int v48; // [rsp+48h] [rbp-B8h]
  struct CBuffer *v49; // [rsp+50h] [rbp-B0h] BYREF
  struct CBuffer *v50; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  struct _RESTARTLOG *v52; // [rsp+68h] [rbp-98h]
  void *v53; // [rsp+70h] [rbp-90h]
  __int128 v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-60h]
  _OWORD v58[5]; // [rsp+B0h] [rbp-50h] BYREF
  int v59; // [rsp+100h] [rbp+0h]

  v3 = 0;
  v53 = a3;
  v52 = a2;
  v50 = 0;
  v49 = 0;
  v45 = 0;
  v47 = 0;
  v43 = 0;
  v46 = 0;
  Block = 0;
  memset_0(v58, 0, 0x54u);
  v5 = *((_DWORD *)this + 10);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( 2 * v5 )
  {
    while ( 1 )
    {
      v10 = CLogStorage::_MapBuffer(this, v8, v5, 0, 0);
      v11 = (_DWORD *)*((_QWORD *)v10 + 3);
      if ( !v11 )
      {
        TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x55Eu);
        CLogStorage::_UnmapBuffer(this, (LPCVOID *)v10, 0);
        pExceptionObject = -2147024809;
        throw &pExceptionObject;
      }
      if ( *v11 != 1381258066 )
        break;
      v12 = v11[20];
      if ( v12 < 0x2000 || ((v12 - 1) & v12) != 0 )
      {
LABEL_17:
        if ( v6 )
          goto LABEL_20;
        CLogStorage::_UnmapBuffer(this, (LPCVOID *)v10, 0);
        goto LABEL_19;
      }
      if ( v12 == v5 || v6 )
        goto LABEL_10;
      v5 = v12;
      CLogStorage::_UnmapBuffer(this, (LPCVOID *)v10, 0);
LABEL_14:
      if ( v8 >= 2 * v5 )
      {
        if ( !v6 )
          goto LABEL_19;
        v10 = v7;
        goto LABEL_20;
      }
    }
    if ( *v11 != *((_DWORD *)this + 14) )
      goto LABEL_17;
LABEL_10:
    if ( v8 )
      v7 = v10;
    else
      v6 = v10;
    v8 += v5;
    goto LABEL_14;
  }
LABEL_19:
  v5 = CLogStorage::_GrovelDisk(this, &v50, &v49);
  v6 = v50;
  v10 = v49;
LABEL_20:
  if ( v5 && v5 != *((_DWORD *)this + 10) )
  {
    TraceFile(-1073737662, "IDS_DTC_LOG_INCOMPATIBLE", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x133u);
    pExceptionObject = -1073737662;
    throw &pExceptionObject;
  }
  pExceptionObject = 0;
  v44 = 0;
  v13 = CLogStorage::_VerifyRestart(this, v6, &v45, v9, &v43, 0);
  v15 = CLogStorage::_VerifyRestart(this, v10, &v47, v14, &v46, 0);
  v16 = v15;
  if ( v13 && *((_DWORD *)v13 + 1) && *((_DWORD *)v13 + 19) )
  {
    LOBYTE(v3) = *((_WORD *)v13 + 44) == 0;
    pExceptionObject = v3;
  }
  if ( v15 && *((_DWORD *)v15 + 1) && *((_DWORD *)v15 + 19) )
  {
    v17 = *((_WORD *)v15 + 44) == 0;
    v44 = *((_WORD *)v16 + 44) == 0;
  }
  else
  {
    v17 = v44;
  }
  v18 = v46;
  v48 = v46;
  if ( v3 || v17 || v43 || v46 )
  {
    v57 = 0;
    v55 = 0;
    v56 = 0;
    v54 = 0;
    if ( !(unsigned int)CLogStorage::_FindEOF(
                          this,
                          (unsigned int *)&v50,
                          (unsigned int *)&v49,
                          (struct _LOGRECHEADER *)&v56,
                          (struct _LOGRECHEADER *)&v54)
      || !(_DWORD)v54
      || (v56 = v54, v57 = v55, !(unsigned int)CLogStorage::_FillRSL(this, v58, &Block, &v56)) )
    {
      TraceFile(
        -1073737670,
        "IDS_DTC_E_LOG_CORRUPT_ERROR",
        "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
        0x16Du);
      pExceptionObject = -1073737670;
      throw &pExceptionObject;
    }
    v21 = v59;
    v22 = v58[4];
    v23 = v58[3];
    v24 = v58[2];
    v25 = v58[1];
    v20 = DWORD1(v58[0]);
    v26 = v58[0];
    if ( v43 || pExceptionObject )
    {
      *(_OWORD *)((char *)v13 + 24) = v58[0];
      v19 = v20;
      *(_OWORD *)((char *)v13 + 40) = v25;
      *(_OWORD *)((char *)v13 + 56) = v24;
      *(_OWORD *)((char *)v13 + 72) = v23;
      *(_OWORD *)((char *)v13 + 88) = v22;
      *((_DWORD *)v13 + 26) = v21;
    }
    else
    {
      v19 = v45;
    }
    v18 = v46;
    v43 = v19;
    if ( v46 || v44 )
    {
      *(_OWORD *)((char *)v16 + 24) = v26;
      v18 = 0;
      *(_OWORD *)((char *)v16 + 40) = v25;
      v48 = 0;
      *(_OWORD *)((char *)v16 + 56) = v24;
      *(_OWORD *)((char *)v16 + 72) = v23;
      *(_OWORD *)((char *)v16 + 88) = v22;
      *((_DWORD *)v16 + 26) = v21;
    }
    else
    {
      v20 = v47;
    }
    if ( Block )
    {
      operator delete(Block);
      v19 = v43;
      v18 = v48;
    }
  }
  else
  {
    v19 = v45;
    v20 = v47;
    v43 = v45;
  }
  if ( v5 != *((_DWORD *)this + 10) )
  {
    if ( v18 || v19 > v20 || v19 == v20 && *((_DWORD *)v13 + 17) > *((_DWORD *)v16 + 17) )
    {
      v27 = *((_DWORD *)v13 + 18);
      v28 = *((_DWORD *)v13 + 17);
    }
    else
    {
      v27 = *((_DWORD *)v16 + 18);
      v28 = *((_DWORD *)v16 + 17);
    }
    v29 = v5 + (v28 & -v5);
    if ( v29 >= *((_DWORD *)this + 8) )
      v29 = 4 * v5;
    v30 = CLogStorage::_MapBuffer(this, v29, v5, 0, 0);
    v31 = *(_DWORD *)(*((_QWORD *)v30 + 3) + 8LL);
    CLogStorage::_UnmapBuffer(this, (LPCVOID *)v30, 0);
    CLogStorage::_UnmapBuffer(this, (LPCVOID *)v6, 0);
    CLogStorage::_UnmapBuffer(this, (LPCVOID *)v10, 0);
    if ( v31 == v27 )
    {
      TraceFile(
        -1073737662,
        "IDS_DTC_LOG_INCOMPATIBLE",
        "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
        0x19Cu);
      pExceptionObject = -1073737662;
      throw &pExceptionObject;
    }
    v32 = *((_DWORD *)this + 10);
    v43 = 0;
    v20 = 0;
    v6 = CLogStorage::_MapBuffer(this, 0, v32, 0, 0);
    v13 = (struct _RESTARTPAGE *)*((_QWORD *)v6 + 3);
    memset_0(v13, 255, *((unsigned int *)this + 10));
    v10 = CLogStorage::_MapBuffer(this, *((_DWORD *)this + 10), *((_DWORD *)this + 10), 0, 0);
    v16 = (struct _RESTARTPAGE *)*((_QWORD *)v10 + 3);
    memset_0(v16, 255, *((unsigned int *)this + 10));
  }
  if ( (v43 || v20) && (v43 != 1 || v20 != 1) )
  {
    if ( !v48 && *(_QWORD *)((char *)v13 + 68) <= *(_QWORD *)((char *)v16 + 68) )
    {
      memcpy_0(v13, v16, 0x2000u);
      *((_DWORD *)v13 + 3) = 0;
      goto LABEL_70;
    }
    memcpy_0(v16, v13, 0x2000u);
  }
  else
  {
    *(_DWORD *)this = 2;
    *((_DWORD *)v13 + 2) = 2;
    *(_DWORD *)v13 = 1381258066;
    *((_DWORD *)v13 + 5) = *((_DWORD *)this + 10);
    v33 = *((_DWORD *)this + 27) + 32;
    *((_DWORD *)v13 + 6) = v33;
    v34 = *(_DWORD *)this;
    *((_DWORD *)v13 + 8) = v33;
    *((_DWORD *)v13 + 9) = 2;
    *((_DWORD *)v13 + 7) = v34;
    v35 = *((_DWORD *)this + 8);
    *((_DWORD *)v13 + 12) = v33;
    *((_DWORD *)v13 + 13) = 2;
    *((_DWORD *)v13 + 14) = v35;
    *(_QWORD *)((char *)v13 + 60) = 0;
    *(_QWORD *)((char *)v13 + 68) = 0;
    *((_DWORD *)v13 + 10) = -1;
    *((_DWORD *)v13 + 11) = -1;
    *((_DWORD *)v13 + 20) = *((_DWORD *)this + 10);
    v36 = *((_DWORD *)this + 8) / *((_DWORD *)this + 10);
    *((_DWORD *)v13 + 21) = 65537;
    *((_DWORD *)v13 + 19) = 8160 * v36 - 32640;
    v37 = *((_DWORD *)this + 29);
    *((_DWORD *)v13 + 22) = 0;
    *((_DWORD *)v13 + 26) = v37;
    memcpy_0(v16, v13, 0x2000u);
    *((_DWORD *)v13 + 3) = 0;
  }
  *((_DWORD *)v16 + 3) = 1;
LABEL_70:
  v38 = v52;
  *(_OWORD *)v52 = *(_OWORD *)((char *)v13 + 24);
  *((_OWORD *)v38 + 1) = *(_OWORD *)((char *)v13 + 40);
  *((_OWORD *)v38 + 2) = *(_OWORD *)((char *)v13 + 56);
  *((_OWORD *)v38 + 3) = *(_OWORD *)((char *)v13 + 72);
  *((_OWORD *)v38 + 4) = *(_OWORD *)((char *)v13 + 88);
  *((_DWORD *)v38 + 20) = *((_DWORD *)v13 + 26);
  v39 = 2;
  if ( *((_DWORD *)v38 + 1) != 1 )
    v39 = *((_DWORD *)v38 + 1);
  *(_DWORD *)this = v39;
  memcpy_0(v53, (char *)v13 + 108, 44LL * *((unsigned __int16 *)v38 + 32));
  v40 = ((__int64 (__fastcall *)(_QWORD, char *, void *))lpCalcCRC)(
          (unsigned int)(*((_DWORD *)this + 10) - 8),
          (char *)v13 + 8,
          pulCRCTable);
  v41 = pulCRCTable;
  *((_DWORD *)v13 + 1) = v40;
  *((_DWORD *)v16 + 1) = ((__int64 (__fastcall *)(_QWORD, char *, void *))lpCalcCRC)(
                           (unsigned int)(*((_DWORD *)this + 10) - 8),
                           (char *)v16 + 8,
                           v41);
  CLogStorage::_UnmapBuffer(this, (LPCVOID *)v6, 1);
  CLogStorage::_UnmapBuffer(this, (LPCVOID *)v10, 1);
  CLogStorage::_InitResidue(this, *((_DWORD *)this + 10) == v5);
}

```

## disassembly

```asm
0x18000a288  mov     [rsp-8+arg_18], rbx
0x18000a28d  push    rbp
0x18000a28e  push    rsi
0x18000a28f  push    rdi
0x18000a290  push    r12
0x18000a292  push    r13
0x18000a294  push    r14
0x18000a296  push    r15
0x18000a298  lea     rbp, [rsp-20h]
0x18000a29d  sub     rsp, 120h
0x18000a2a4  mov     rax, cs:__security_cookie
0x18000a2ab  xor     rax, rsp
0x18000a2ae  mov     [rbp+50h+var_40], rax
0x18000a2b2  xor     r12d, r12d
0x18000a2b5  mov     [rsp+150h+var_E0], r8
0x18000a2ba  mov     [rsp+150h+var_E8], rdx
0x18000a2bf  mov     rdi, rcx
0x18000a2c2  xor     edx, edx; Val
0x18000a2c4  mov     [rsp+150h+var_F8], r12
0x18000a2c9  lea     rcx, [rbp+50h+var_A0]; void *
0x18000a2cd  mov     [rsp+150h+var_100], r12
0x18000a2d2  lea     r8d, [r12+54h]; Size
0x18000a2d7  mov     [rsp+150h+var_114], r12d
0x18000a2dc  mov     [rsp+150h+var_10C], r12d
0x18000a2e1  mov     [rsp+150h+var_11C], r12d
0x18000a2e6  mov     [rsp+150h+var_110], r12d
0x18000a2eb  mov     [rsp+150h+Block], r12
0x18000a2f0  call    memset_0
0x18000a2f5  mov     r14d, [rdi+28h]
0x18000a2f9  mov     r13d, r12d
0x18000a2fc  mov     esi, r12d
0x18000a2ff  mov     ebx, r12d
0x18000a302  lea     eax, [r14+r14]
0x18000a306  test    eax, eax
0x18000a308  jz      loc_18000A3A4
0x18000a30e  xor     r9d, r9d; int
0x18000a311  mov     dword ptr [rsp+150h+var_130], r12d; unsigned int
0x18000a316  mov     r8d, r14d; unsigned int
0x18000a319  mov     edx, ebx; unsigned int
0x18000a31b  mov     rcx, rdi; this
0x18000a31e  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000a323  mov     r15, rax
0x18000a326  mov     rcx, [rax+18h]
0x18000a32a  test    rcx, rcx
0x18000a32d  jz      loc_18000A90C
0x18000a333  mov     eax, [rcx]
0x18000a335  cmp     eax, 52545352h
0x18000a33a  jnz     short loc_18000A36B
0x18000a33c  mov     ecx, [rcx+50h]
0x18000a33f  cmp     ecx, 2000h
0x18000a345  jb      short loc_18000A391
0x18000a347  lea     eax, [rcx-1]
0x18000a34a  test    ecx, eax
0x18000a34c  jnz     short loc_18000A391
0x18000a34e  cmp     ecx, r14d
0x18000a351  jz      short loc_18000A370
0x18000a353  test    r13, r13
0x18000a356  jnz     short loc_18000A370
0x18000a358  mov     r14d, ecx
0x18000a35b  xor     r8d, r8d; int
0x18000a35e  mov     rcx, rdi; this
0x18000a361  mov     rdx, r15; struct CBuffer *
0x18000a364  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a369  jmp     short loc_18000A37F
0x18000a36b  cmp     eax, [rdi+38h]
0x18000a36e  jnz     short loc_18000A391
0x18000a370  test    ebx, ebx
0x18000a372  jnz     short loc_18000A379
0x18000a374  mov     r13, r15
0x18000a377  jmp     short loc_18000A37C
0x18000a379  mov     rsi, r15
0x18000a37c  add     ebx, r14d
0x18000a37f  lea     eax, [r14+r14]
0x18000a383  cmp     ebx, eax
0x18000a385  jb      short loc_18000A30E
0x18000a387  test    r13, r13
0x18000a38a  jz      short loc_18000A3A4
0x18000a38c  mov     r15, rsi
0x18000a38f  jmp     short loc_18000A3C3
0x18000a391  test    r13, r13
0x18000a394  jnz     short loc_18000A3C3
0x18000a396  xor     r8d, r8d; int
0x18000a399  mov     rdx, r15; struct CBuffer *
0x18000a39c  mov     rcx, rdi; this
0x18000a39f  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a3a4  lea     r8, [rsp+150h+var_100]; struct CBuffer **
0x18000a3a9  mov     rcx, rdi; this
0x18000a3ac  lea     rdx, [rsp+150h+var_F8]; struct CBuffer **
0x18000a3b1  call    ?_GrovelDisk@CLogStorage@@AEAAKPEAPEAVCBuffer@@0@Z; CLogStorage::_GrovelDisk(CBuffer * *,CBuffer * *)
0x18000a3b6  mov     r14d, eax
0x18000a3b9  mov     r13, [rsp+150h+var_F8]
0x18000a3be  mov     r15, [rsp+150h+var_100]
0x18000a3c3  test    r14d, r14d
0x18000a3c6  jz      short loc_18000A3D2
0x18000a3c8  cmp     r14d, [rdi+28h]
0x18000a3cc  jnz     loc_18000A8D4
0x18000a3d2  xor     esi, esi
0x18000a3d4  mov     [rsp+150h+pExceptionObject], r12d
0x18000a3d9  lea     rax, [rsp+150h+var_11C]
0x18000a3de  mov     [rsp+150h+var_128], rsi; unsigned int *
0x18000a3e3  lea     r8, [rsp+150h+var_114]; unsigned int *
0x18000a3e8  mov     [rsp+150h+var_130], rax; int *
0x18000a3ed  mov     rdx, r13; struct CBuffer *
0x18000a3f0  mov     [rsp+150h+var_118], esi
0x18000a3f4  mov     rcx, rdi; this
0x18000a3f7  call    ?_VerifyRestart@CLogStorage@@AEAAPEAU_RESTARTPAGE@@PEAVCBuffer@@PEAKKPEAH1@Z; CLogStorage::_VerifyRestart(CBuffer *,ulong *,ulong,int *,ulong *)
0x18000a3fc  mov     rbx, rax
0x18000a3ff  mov     [rsp+150h+var_128], rsi; unsigned int *
0x18000a404  lea     rax, [rsp+150h+var_110]
0x18000a409  mov     rdx, r15; struct CBuffer *
0x18000a40c  lea     r8, [rsp+150h+var_10C]; unsigned int *
0x18000a411  mov     [rsp+150h+var_130], rax; int *
0x18000a416  mov     rcx, rdi; this
0x18000a419  call    ?_VerifyRestart@CLogStorage@@AEAAPEAU_RESTARTPAGE@@PEAVCBuffer@@PEAKKPEAH1@Z; CLogStorage::_VerifyRestart(CBuffer *,ulong *,ulong,int *,ulong *)
0x18000a41e  xor     r9d, r9d
0x18000a421  mov     rsi, rax
0x18000a424  test    rbx, rbx
0x18000a427  jz      short loc_18000A443
0x18000a429  cmp     [rbx+4], r9d
0x18000a42d  jz      short loc_18000A443
0x18000a42f  cmp     [rbx+4Ch], r9d
0x18000a433  jz      short loc_18000A443
0x18000a435  cmp     [rbx+58h], r9w
0x18000a43a  setz    r12b
0x18000a43e  mov     [rsp+150h+pExceptionObject], r12d
0x18000a443  test    rsi, rsi
0x18000a446  jz      short loc_18000A465
0x18000a448  cmp     [rax+4], r9d
0x18000a44c  jz      short loc_18000A465
0x18000a44e  cmp     [rax+4Ch], r9d
0x18000a452  jz      short loc_18000A465
0x18000a454  cmp     [rsi+58h], r9w
0x18000a459  mov     eax, r9d
0x18000a45c  setz    al
0x18000a45f  mov     [rsp+150h+var_118], eax
0x18000a463  jmp     short loc_18000A469
0x18000a465  mov     eax, [rsp+150h+var_118]
0x18000a469  mov     ecx, [rsp+150h+var_110]
0x18000a46d  mov     [rsp+150h+var_108], ecx
0x18000a471  test    r12d, r12d
0x18000a474  jnz     short loc_18000A497
0x18000a476  test    eax, eax
0x18000a478  jnz     short loc_18000A497
0x18000a47a  cmp     [rsp+150h+var_11C], r9d
0x18000a47f  jnz     short loc_18000A497
0x18000a481  test    ecx, ecx
0x18000a483  jnz     short loc_18000A497
0x18000a485  mov     eax, [rsp+150h+var_114]
0x18000a489  mov     r12d, [rsp+150h+var_10C]
0x18000a48e  mov     [rsp+150h+var_11C], eax
0x18000a492  jmp     loc_18000A5B7
0x18000a497  xor     eax, eax
0x18000a499  lea     r9, [rbp+50h+var_C0]; struct _LOGRECHEADER *
0x18000a49d  mov     [rbp+50h+var_B0], rax
0x18000a4a1  lea     r8, [rsp+150h+var_100]; unsigned int *
0x18000a4a6  mov     [rbp+50h+var_C8], rax
0x18000a4aa  lea     rdx, [rsp+150h+var_F8]; unsigned int *
0x18000a4af  lea     rax, [rsp+150h+var_D8]
0x18000a4b4  xorps   xmm0, xmm0
0x18000a4b7  xorps   xmm1, xmm1
0x18000a4ba  mov     [rsp+150h+var_130], rax; struct _LOGRECHEADER *
0x18000a4bf  mov     rcx, rdi; this
0x18000a4c2  movups  [rbp+50h+var_C0], xmm0
0x18000a4c6  movups  [rsp+150h+var_D8], xmm1
0x18000a4cb  call    ?_FindEOF@CLogStorage@@AEAAHPEAK0PEAU_LOGRECHEADER@@1@Z; CLogStorage::_FindEOF(ulong *,ulong *,_LOGRECHEADER *,_LOGRECHEADER *)
0x18000a4d0  test    eax, eax
0x18000a4d2  jz      loc_18000A89C
0x18000a4d8  cmp     dword ptr [rsp+150h+var_D8], 0
0x18000a4dd  jz      loc_18000A89C
0x18000a4e3  movups  xmm0, [rsp+150h+var_D8]
0x18000a4e8  lea     r9, [rbp+50h+var_C0]
0x18000a4ec  mov     rcx, rdi
0x18000a4ef  movsd   xmm1, [rbp+50h+var_C8]
0x18000a4f4  lea     r8, [rsp+150h+Block]
0x18000a4f9  lea     rdx, [rbp+50h+var_A0]
0x18000a4fd  movaps  [rbp+50h+var_C0], xmm0
0x18000a501  movsd   [rbp+50h+var_B0], xmm1
0x18000a506  call    ?_FillRSL@CLogStorage@@AEAAHPEAU_RESTARTLOG@@PEAPEAU_STRMTBL@@U_LOGRECHEADER@@@Z; CLogStorage::_FillRSL(_RESTARTLOG *,_STRMTBL * *,_LOGRECHEADER)
0x18000a50b  xor     r9d, r9d
0x18000a50e  test    eax, eax
0x18000a510  jz      loc_18000A89C
0x18000a516  mov     r8d, [rbp+50h+var_50]
0x18000a51a  movaps  xmm0, [rbp+50h+var_60]
0x18000a51e  movaps  xmm1, [rbp+50h+var_70]
0x18000a522  movaps  xmm2, [rbp+50h+var_80]
0x18000a526  movaps  xmm3, [rbp+50h+var_90]
0x18000a52a  mov     r12d, dword ptr [rbp+50h+var_A0+4]
0x18000a52e  movaps  xmm4, [rbp+50h+var_A0]
0x18000a532  cmp     [rsp+150h+var_11C], r9d
0x18000a537  jnz     short loc_18000A546
0x18000a539  cmp     [rsp+150h+pExceptionObject], r9d
0x18000a53e  jnz     short loc_18000A546
0x18000a540  mov     eax, [rsp+150h+var_114]
0x18000a544  jmp     short loc_18000A561
0x18000a546  movups  xmmword ptr [rbx+18h], xmm4
0x18000a54a  mov     eax, r12d
0x18000a54d  movups  xmmword ptr [rbx+28h], xmm3
0x18000a551  movups  xmmword ptr [rbx+38h], xmm2
0x18000a555  movups  xmmword ptr [rbx+48h], xmm1
0x18000a559  movups  xmmword ptr [rbx+58h], xmm0
0x18000a55d  mov     [rbx+68h], r8d
0x18000a561  mov     ecx, [rsp+150h+var_110]
0x18000a565  mov     [rsp+150h+var_11C], eax
0x18000a569  test    ecx, ecx
0x18000a56b  jnz     short loc_18000A57B
0x18000a56d  cmp     [rsp+150h+var_118], r9d
0x18000a572  jnz     short loc_18000A57B
0x18000a574  mov     r12d, [rsp+150h+var_10C]
0x18000a579  jmp     short loc_18000A59A
0x18000a57b  movups  xmmword ptr [rsi+18h], xmm4
0x18000a57f  mov     ecx, r9d
0x18000a582  movups  xmmword ptr [rsi+28h], xmm3
0x18000a586  mov     [rsp+150h+var_108], ecx
0x18000a58a  movups  xmmword ptr [rsi+38h], xmm2
0x18000a58e  movups  xmmword ptr [rsi+48h], xmm1
0x18000a592  movups  xmmword ptr [rsi+58h], xmm0
0x18000a596  mov     [rsi+68h], r8d
0x18000a59a  mov     rdx, [rsp+150h+Block]
0x18000a59f  test    rdx, rdx
0x18000a5a2  jz      short loc_18000A5B7
0x18000a5a4  mov     rcx, rdx; Block
0x18000a5a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a5ac  mov     eax, [rsp+150h+var_11C]
0x18000a5b0  xor     r9d, r9d
0x18000a5b3  mov     ecx, [rsp+150h+var_108]
0x18000a5b7  cmp     r14d, [rdi+28h]
0x18000a5bb  jz      loc_18000A6AB
0x18000a5c1  test    ecx, ecx
0x18000a5c3  jnz     short loc_18000A5DD
0x18000a5c5  cmp     eax, r12d
0x18000a5c8  ja      short loc_18000A5DD
0x18000a5ca  jnz     short loc_18000A5D4
0x18000a5cc  mov     eax, [rsi+44h]
0x18000a5cf  cmp     [rbx+44h], eax
0x18000a5d2  ja      short loc_18000A5DD
0x18000a5d4  mov     r12d, [rsi+48h]
0x18000a5d8  mov     ecx, [rsi+44h]
0x18000a5db  jmp     short loc_18000A5E4
0x18000a5dd  mov     r12d, [rbx+48h]
0x18000a5e1  mov     ecx, [rbx+44h]
0x18000a5e4  mov     edx, r14d
0x18000a5e7  neg     edx
0x18000a5e9  and     edx, ecx
0x18000a5eb  add     edx, r14d
0x18000a5ee  cmp     edx, [rdi+20h]
0x18000a5f1  jb      short loc_18000A5FB
0x18000a5f3  lea     edx, ds:0[r14*4]; unsigned int
0x18000a5fb  mov     dword ptr [rsp+150h+var_130], r9d; unsigned int
0x18000a600  mov     r8d, r14d; unsigned int
0x18000a603  xor     r9d, r9d; int
0x18000a606  mov     rcx, rdi; this
0x18000a609  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000a60e  xor     r8d, r8d; int
0x18000a611  mov     rdx, rax; struct CBuffer *
0x18000a614  mov     rcx, [rax+18h]
0x18000a618  mov     ebx, [rcx+8]
0x18000a61b  mov     rcx, rdi; this
0x18000a61e  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a623  xor     r8d, r8d; int
0x18000a626  mov     rdx, r13; struct CBuffer *
0x18000a629  mov     rcx, rdi; this
0x18000a62c  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a631  xor     r8d, r8d; int
0x18000a634  mov     rdx, r15; struct CBuffer *
0x18000a637  mov     rcx, rdi; this
0x18000a63a  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a63f  cmp     ebx, r12d
0x18000a642  jz      loc_18000A952
0x18000a648  mov     r8d, [rdi+28h]; unsigned int
0x18000a64c  xor     esi, esi
0x18000a64e  xor     r9d, r9d; int
0x18000a651  mov     [rsp+150h+var_11C], esi
0x18000a655  xor     edx, edx; unsigned int
0x18000a657  mov     dword ptr [rsp+150h+var_130], esi; unsigned int
0x18000a65b  mov     rcx, rdi; this
0x18000a65e  mov     r12d, esi
0x18000a661  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000a666  mov     r8d, [rdi+28h]; Size
0x18000a66a  mov     edx, 0FFh; Val
0x18000a66f  mov     r13, rax
0x18000a672  mov     rbx, [rax+18h]
0x18000a676  mov     rcx, rbx; void *
0x18000a679  call    memset_0
0x18000a67e  mov     edx, [rdi+28h]; unsigned int
0x18000a681  xor     r9d, r9d; int
0x18000a684  mov     r8d, edx; unsigned int
0x18000a687  mov     dword ptr [rsp+150h+var_130], esi; unsigned int
0x18000a68b  mov     rcx, rdi; this
0x18000a68e  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000a693  mov     r8d, [rdi+28h]; Size
0x18000a697  mov     edx, 0FFh; Val
0x18000a69c  mov     r15, rax
0x18000a69f  mov     rsi, [rax+18h]
0x18000a6a3  mov     rcx, rsi; void *
0x18000a6a6  call    memset_0
0x18000a6ab  mov     eax, [rsp+150h+var_11C]
0x18000a6af  mov     edx, 2
0x18000a6b4  xor     r8d, r8d
0x18000a6b7  lea     r9d, [rdx-1]
0x18000a6bb  test    eax, eax
  ... truncated ...
```
