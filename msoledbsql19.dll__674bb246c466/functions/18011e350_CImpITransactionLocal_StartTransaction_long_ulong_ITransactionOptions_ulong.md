# CImpITransactionLocal::StartTransaction(long,ulong,ITransactionOptions *,ulong *)

- ea: `0x18011e350`
- end: `0x18011e805`
- name: `?StartTransaction@CImpITransactionLocal@@UEAAJJKPEAUITransactionOptions@@PEAK@Z`
- size: `1205`
- prototype: `int(CImpITransactionLocal *__hidden this, int, unsigned int, struct ITransactionOptions *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003d80`
- `0x180009340`
- `0x180009700`
- `0x180011d60`
- `0x18011e350`
- `0x18013f360`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateGuid` at `0x18011e5e3`
- `ole32!CoCreateGuid` at `0x18011e5e3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011e6ea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011e71a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011e6ea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011e71a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011e6f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011e726`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011e6f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011e726`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18011e4af`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18011e4af`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CImpITransactionLocal::StartTransaction(
        CImpITransactionLocal *this,
        unsigned int a2,
        int a3,
        struct ITransactionOptions *a4,
        unsigned int *a5)
{
  __int64 v9; // rbx
  _QWORD *v10; // r15
  int inited; // ebx
  int v12; // eax
  __int64 v13; // rdx
  HRESULT v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+80h] [rbp-80h]
  GUID pguid; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v29[80]; // [rsp+A0h] [rbp-60h] BYREF

  v23 = -1;
  if ( (bidGblFlags & 4) != 0 && off_180266660[0] )
    bidScopeEnterW(&v23, off_180266660[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  if ( (bidGblFlags & 0x40002) == 0x40002
    && (unsigned int)ConstrBidActID(v29, 0x50u)
    && (bidGblFlags & 2) != 0
    && off_180263900[0] )
  {
    bidTraceW(off_1802605D8[0], 391168, off_180263900[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL));
  }
  v9 = *((_QWORD *)this + 1);
  v10 = *(_QWORD **)(v9 + 840);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  pguid = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v9 + 24) + 32LL) + 8LL))(*(_QWORD *)(v9 + 24) + 32LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v10[11] + 32LL) + 8LL))(v10[11] + 32LL);
  v21 = *(_QWORD *)(v9 + 24);
  v22 = v10[11];
  SetErrorInfo(0, 0);
  if ( a3 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_1802605D8[0], 406537, 2147799051LL);
    inited = CError::PostHResult(g_pCError, -2147168245, &IID_ITransactionLocal);
    goto LABEL_54;
  }
  if ( a5 )
    *a5 = 1;
  if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 848LL) & 9) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v12 = bidTraceHR(off_1802605D8[0], 420873, 2147799059LL);
    else
      v12 = -2147168237;
    goto LABEL_19;
  }
  if ( v10[9] )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v13 = 433161;
LABEL_23:
      v12 = bidTraceHR(off_1802605D8[0], v13, 2147799069LL);
LABEL_19:
      inited = CError::PostHResult(g_pCError, v12, &IID_ITransactionLocal);
      goto LABEL_54;
    }
    goto LABEL_24;
  }
  if ( a4 )
  {
    inited = ((__int64 (__fastcall *)(struct ITransactionOptions *, __int128 *))a4->lpVtbl->GetOptions)(a4, &v24);
    if ( inited < 0 )
      goto LABEL_54;
    if ( (_DWORD)v24 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v12 = bidTraceHR(off_1802605D8[0], 452617, 2147799063LL);
      else
        v12 = -2147168233;
      goto LABEL_19;
    }
  }
  v14 = CoCreateGuid(&pguid);
  if ( v14 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605D8[0], 464905, (unsigned int)v14);
      if ( (bidGblFlags & 2) != 0 )
      {
        v13 = 465929;
        goto LABEL_23;
      }
    }
LABEL_24:
    v12 = -2147168227;
    goto LABEL_19;
  }
  inited = CDBConnection::InitLocalXactMode((CDBConnection *)v10, a2);
  if ( inited >= 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) |= 1u;
    *(_DWORD *)(*((_QWORD *)this + 1) + 872LL) = a2;
    if ( *((_QWORD *)this + 1) == -856 )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      *(GUID *)(*((_QWORD *)this + 1) + 856LL) = pguid;
    }
    v17 = *((_QWORD *)this + 1) + 896LL;
    if ( a4 )
    {
      if ( *((_QWORD *)this + 1) == -896 )
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
LABEL_53:
        inited = 0;
        goto LABEL_54;
      }
      *(_OWORD *)v17 = v24;
      *(_OWORD *)(v17 + 16) = v25;
      *(_QWORD *)(v17 + 32) = v26;
      v18 = v27;
    }
    else
    {
      v18 = 0;
      *(_OWORD *)v17 = 0;
      *(_OWORD *)(v17 + 16) = 0;
      *(_QWORD *)(v17 + 32) = 0;
    }
    *(_DWORD *)(v17 + 40) = v18;
    goto LABEL_53;
  }
  v15 = -2147467259;
  _mm_lfence();
  if ( inited == -2147467259 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      v15 = bidTraceHR(off_1802605D8[0], 474121, 2147500037LL);
    }
    CError::PostSqlErrors(g_pCError, v15, &IID_ITransactionLocal, (struct CErrorData *)(v10 + 17));
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      v16 = bidTraceHR(off_1802605D8[0], 478217, (unsigned int)inited);
    }
    else
    {
      v16 = inited;
    }
    CError::PostHResult(g_pCError, v16, &IID_ITransactionLocal);
  }
LABEL_54:
  if ( (bidGblFlags & 2) != 0 && off_180263908[0] )
    bidTraceW(off_1802605D8[0], 508928, off_180263908[0], (unsigned int)inited);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v22 + 32) + 24LL))(v22 + 32);
    v19 = v21;
LABEL_60:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v19 + 32) + 24LL))(v19 + 32);
    goto LABEL_61;
  }
  v19 = v21;
  if ( v21 )
    goto LABEL_60;
LABEL_61:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v23);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18011e350  push    rbp
0x18011e352  push    rbx
0x18011e353  push    rsi
0x18011e354  push    rdi
0x18011e355  push    r12
0x18011e357  push    r13
0x18011e359  push    r14
0x18011e35b  push    r15
0x18011e35d  lea     rbp, [rsp-58h]
0x18011e362  sub     rsp, 158h
0x18011e369  mov     rax, cs:__security_cookie
0x18011e370  xor     rax, rsp
0x18011e373  mov     [rbp+90h+var_50], rax
0x18011e377  mov     rsi, r9
0x18011e37a  mov     r13d, r8d
0x18011e37d  mov     r12d, edx
0x18011e380  mov     rdi, rcx
0x18011e383  mov     r14, [rbp+90h+arg_20]
0x18011e38a  mov     [rsp+190h+var_140], 0FFFFFFFFFFFFFFFFh
0x18011e393  test    byte ptr cs:_bidGblFlags, 4
0x18011e39a  jz      short loc_18011E3D3
0x18011e39c  mov     rax, cs:off_180266660; "<ITransactionLocal::StartTransaction|OL"...
0x18011e3a3  test    rax, rax
0x18011e3a6  jz      short loc_18011E3D3
0x18011e3a8  mov     r8, [rcx+8]
0x18011e3ac  mov     [rsp+190h+var_160], r14
0x18011e3b1  mov     [rsp+190h+var_168], r9
0x18011e3b6  mov     dword ptr [rsp+190h+var_170], r13d
0x18011e3bb  mov     r9d, edx
0x18011e3be  mov     r8d, [r8+34h]
0x18011e3c2  mov     rdx, cs:off_180266660; "<ITransactionLocal::StartTransaction|OL"...
0x18011e3c9  lea     rcx, [rsp+190h+var_140]
0x18011e3ce  call    _bidScopeEnterW
0x18011e3d3  mov     eax, cs:_bidGblFlags
0x18011e3d9  and     eax, 40002h
0x18011e3de  cmp     eax, 40002h
0x18011e3e3  jnz     short loc_18011E441
0x18011e3e5  mov     edx, 50h ; 'P'; unsigned __int64
0x18011e3ea  lea     rcx, [rbp+90h+var_F0]; wchar_t *
0x18011e3ee  call    ?ConstrBidActID@@YAHPEA_W_K@Z; ConstrBidActID(wchar_t *,unsigned __int64)
0x18011e3f3  test    eax, eax
0x18011e3f5  jz      short loc_18011E441
0x18011e3f7  test    byte ptr cs:_bidGblFlags, 2
0x18011e3fe  jz      short loc_18011E441
0x18011e400  mov     rax, cs:off_180263900; "<CImpITransactionLocal::StartTransactio"...
0x18011e407  test    rax, rax
0x18011e40a  jz      short loc_18011E441
0x18011e40c  mov     r9, [rdi+8]
0x18011e410  lea     rax, [rbp+90h+var_F0]
0x18011e414  mov     [rsp+190h+var_168], rax
0x18011e419  lea     rax, aSession; "Session"
0x18011e420  mov     [rsp+190h+var_170], rax
0x18011e425  mov     r9d, [r9+34h]
0x18011e429  mov     r8, cs:off_180263900; "<CImpITransactionLocal::StartTransactio"...
0x18011e430  mov     edx, 5F800h
0x18011e435  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e43c  call    _bidTraceW
0x18011e441  mov     rbx, [rdi+8]
0x18011e445  mov     r15, [rbx+348h]
0x18011e44c  xorps   xmm0, xmm0
0x18011e44f  xor     eax, eax
0x18011e451  movups  [rsp+190h+var_138], xmm0
0x18011e456  movups  [rsp+190h+var_128], xmm0
0x18011e45b  mov     [rsp+190h+var_118], rax
0x18011e460  mov     [rbp+90h+var_110], eax
0x18011e463  movups  xmmword ptr [rbp+90h+pguid.Data1], xmm0
0x18011e467  xorps   xmm1, xmm1
0x18011e46a  movups  [rsp+190h+var_150], xmm1
0x18011e46f  mov     rcx, [rbx+18h]
0x18011e473  add     rcx, 20h ; ' '
0x18011e477  mov     rax, [rcx]
0x18011e47a  mov     rax, [rax+8]
0x18011e47e  call    cs:__guard_dispatch_icall_fptr
0x18011e484  mov     rcx, [r15+58h]
0x18011e488  add     rcx, 20h ; ' '
0x18011e48c  mov     rax, [rcx]
0x18011e48f  mov     rax, [rax+8]
0x18011e493  call    cs:__guard_dispatch_icall_fptr
0x18011e499  mov     rax, [rbx+18h]
0x18011e49d  mov     qword ptr [rsp+190h+var_150], rax
0x18011e4a2  mov     rax, [r15+58h]
0x18011e4a6  mov     qword ptr [rsp+190h+var_150+8], rax
0x18011e4ab  xor     edx, edx; perrinfo
0x18011e4ad  xor     ecx, ecx; dwReserved
0x18011e4af  call    cs:__imp_SetErrorInfo
0x18011e4b5  test    r13d, r13d
0x18011e4b8  jz      short loc_18011E4F9
0x18011e4ba  test    byte ptr cs:_bidGblFlags, 2
0x18011e4c1  jz      short loc_18011E4DA
0x18011e4c3  mov     edx, 63409h
0x18011e4c8  mov     r8d, 8004D00Bh
0x18011e4ce  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e4d5  call    _bidTraceHR
0x18011e4da  lea     r8, IID_ITransactionLocal; struct _GUID *
0x18011e4e1  mov     edx, 8004D00Bh; int
0x18011e4e6  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011e4ed  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18011e4f2  mov     ebx, eax
0x18011e4f4  jmp     loc_18011E764
0x18011e4f9  test    r14, r14
0x18011e4fc  jz      short loc_18011E505
0x18011e4fe  mov     dword ptr [r14], 1
0x18011e505  mov     rax, [rdi+8]
0x18011e509  test    byte ptr [rax+350h], 9
0x18011e510  jz      short loc_18011E555
0x18011e512  test    byte ptr cs:_bidGblFlags, 2
0x18011e519  jz      short loc_18011E534
0x18011e51b  mov     edx, 66C09h
0x18011e520  mov     r8d, 8004D013h
0x18011e526  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e52d  call    _bidTraceHR
0x18011e532  jmp     short loc_18011E539
0x18011e534  mov     eax, 8004D013h
0x18011e539  lea     r8, IID_ITransactionLocal; struct _GUID *
0x18011e540  mov     edx, eax; int
0x18011e542  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011e549  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18011e54e  mov     ebx, eax
0x18011e550  jmp     loc_18011E764
0x18011e555  cmp     qword ptr [r15+48h], 0
0x18011e55a  jz      short loc_18011E585
0x18011e55c  test    byte ptr cs:_bidGblFlags, 2
0x18011e563  jz      short loc_18011E57E
0x18011e565  mov     edx, 69C09h
0x18011e56a  mov     r8d, 8004D01Dh
0x18011e570  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e577  call    _bidTraceHR
0x18011e57c  jmp     short loc_18011E539
0x18011e57e  mov     eax, 8004D01Dh
0x18011e583  jmp     short loc_18011E539
0x18011e585  test    rsi, rsi
0x18011e588  jz      short loc_18011E5DF
0x18011e58a  mov     rax, [rsi]
0x18011e58d  lea     rdx, [rsp+190h+var_138]
0x18011e592  mov     rcx, rsi
0x18011e595  mov     rax, [rax+20h]
0x18011e599  call    cs:__guard_dispatch_icall_fptr
0x18011e59f  mov     ebx, eax
0x18011e5a1  test    eax, eax
0x18011e5a3  js      loc_18011E764
0x18011e5a9  cmp     dword ptr [rsp+190h+var_138], 0
0x18011e5ae  jz      short loc_18011E5DF
0x18011e5b0  test    byte ptr cs:_bidGblFlags, 2
0x18011e5b7  jz      short loc_18011E5D5
0x18011e5b9  mov     edx, 6E809h
0x18011e5be  mov     r8d, 8004D017h
0x18011e5c4  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e5cb  call    _bidTraceHR
0x18011e5d0  jmp     loc_18011E539
0x18011e5d5  mov     eax, 8004D017h
0x18011e5da  jmp     loc_18011E539
0x18011e5df  lea     rcx, [rbp+90h+pguid]; pguid
0x18011e5e3  call    cs:__imp_CoCreateGuid
0x18011e5e9  test    eax, eax
0x18011e5eb  jns     short loc_18011E628
0x18011e5ed  mov     ecx, cs:_bidGblFlags
0x18011e5f3  test    cl, 2
0x18011e5f6  jz      short loc_18011E57E
0x18011e5f8  lfence
0x18011e5fb  mov     r8d, eax
0x18011e5fe  mov     edx, 71809h
0x18011e603  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e60a  call    _bidTraceHR
0x18011e60f  mov     ecx, cs:_bidGblFlags
0x18011e615  test    cl, 2
0x18011e618  jz      loc_18011E57E
0x18011e61e  mov     edx, 71C09h
0x18011e623  jmp     loc_18011E56A
0x18011e628  mov     edx, r12d; int
0x18011e62b  mov     rcx, r15; this
0x18011e62e  call    ?InitLocalXactMode@CDBConnection@@QEAAJJ@Z; CDBConnection::InitLocalXactMode(long)
0x18011e633  mov     ebx, eax
0x18011e635  test    eax, eax
0x18011e637  jns     loc_18011E6C8
0x18011e63d  mov     eax, 80004005h
0x18011e642  lfence
0x18011e645  cmp     ebx, eax
0x18011e647  jnz     short loc_18011E68A
0x18011e649  test    byte ptr cs:_bidGblFlags, 2
0x18011e650  jz      short loc_18011E669
0x18011e652  lfence
0x18011e655  mov     r8d, eax
0x18011e658  mov     edx, 73C09h
0x18011e65d  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e664  call    _bidTraceHR
0x18011e669  lea     r9, [r15+88h]; struct CErrorData *
0x18011e670  lea     r8, IID_ITransactionLocal; struct _GUID *
0x18011e677  mov     edx, eax; int
0x18011e679  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011e680  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x18011e685  jmp     loc_18011E764
0x18011e68a  test    byte ptr cs:_bidGblFlags, 2
0x18011e691  jz      short loc_18011E6AC
0x18011e693  lfence
0x18011e696  mov     r8d, ebx
0x18011e699  mov     edx, 74C09h
0x18011e69e  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e6a5  call    _bidTraceHR
0x18011e6aa  jmp     short loc_18011E6AE
0x18011e6ac  mov     eax, ebx
0x18011e6ae  lea     r8, IID_ITransactionLocal; struct _GUID *
0x18011e6b5  mov     edx, eax; int
0x18011e6b7  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011e6be  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18011e6c3  jmp     loc_18011E764
0x18011e6c8  mov     rax, [rdi+8]
0x18011e6cc  or      dword ptr [rax+350h], 1
0x18011e6d3  mov     rax, [rdi+8]
0x18011e6d7  mov     [rax+368h], r12d
0x18011e6de  mov     rax, [rdi+8]
0x18011e6e2  add     rax, 358h
0x18011e6e8  jnz     short loc_18011E6FE
0x18011e6ea  call    cs:__imp__errno
0x18011e6f0  mov     dword ptr [rax], 16h
0x18011e6f6  call    cs:__imp__invalid_parameter_noinfo
0x18011e6fc  jmp     short loc_18011E705
0x18011e6fe  movups  xmm0, xmmword ptr [rbp+90h+pguid.Data1]
0x18011e702  movups  xmmword ptr [rax], xmm0
0x18011e705  mov     rcx, [rdi+8]
0x18011e709  add     rcx, 380h
0x18011e710  test    rsi, rsi
0x18011e713  jz      short loc_18011E74F
0x18011e715  test    rcx, rcx
0x18011e718  jnz     short loc_18011E72E
0x18011e71a  call    cs:__imp__errno
0x18011e720  mov     dword ptr [rax], 16h
0x18011e726  call    cs:__imp__invalid_parameter_noinfo
0x18011e72c  jmp     short loc_18011E762
0x18011e72e  movups  xmm0, [rsp+190h+var_138]
0x18011e733  movups  xmmword ptr [rcx], xmm0
0x18011e736  movups  xmm1, [rsp+190h+var_128]
0x18011e73b  movups  xmmword ptr [rcx+10h], xmm1
0x18011e73f  movsd   xmm0, [rsp+190h+var_118]
0x18011e745  movsd   qword ptr [rcx+20h], xmm0
0x18011e74a  mov     eax, [rbp+90h+var_110]
0x18011e74d  jmp     short loc_18011E75F
0x18011e74f  xorps   xmm0, xmm0
0x18011e752  xor     eax, eax
0x18011e754  movups  xmmword ptr [rcx], xmm0
0x18011e757  movups  xmmword ptr [rcx+10h], xmm0
0x18011e75b  mov     [rcx+20h], rax
0x18011e75f  mov     [rcx+28h], eax
0x18011e762  xor     ebx, ebx
0x18011e764  test    byte ptr cs:_bidGblFlags, 2
0x18011e76b  jz      short loc_18011E79A
0x18011e76d  mov     rax, cs:off_180263908; "<ITransactionLocal::StartTransaction|OL"...
0x18011e774  test    rax, rax
0x18011e777  jz      short loc_18011E79A
0x18011e779  mov     [rsp+190h+var_170], r14
0x18011e77e  mov     r9d, ebx
0x18011e781  mov     r8, cs:off_180263908; "<ITransactionLocal::StartTransaction|OL"...
0x18011e788  mov     edx, 7C400h
0x18011e78d  mov     rcx, cs:off_1802605D8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011e794  call    _bidTraceW
0x18011e799  nop
0x18011e79a  mov     rcx, qword ptr [rsp+190h+var_150+8]
0x18011e79f  test    rcx, rcx
0x18011e7a2  jz      short loc_18011E7BC
0x18011e7a4  add     rcx, 20h ; ' '
0x18011e7a8  mov     rax, [rcx]
0x18011e7ab  mov     rax, [rax+18h]
0x18011e7af  call    cs:__guard_dispatch_icall_fptr
0x18011e7b5  mov     rcx, qword ptr [rsp+190h+var_150]
0x18011e7ba  jmp     short loc_18011E7C6
0x18011e7bc  mov     rcx, qword ptr [rsp+190h+var_150]
0x18011e7c1  test    rcx, rcx
0x18011e7c4  jz      short loc_18011E7D8
0x18011e7c6  add     rcx, 20h ; ' '
0x18011e7ca  mov     rax, [rcx]
0x18011e7cd  mov     rax, [rax+18h]
0x18011e7d1  call    cs:__guard_dispatch_icall_fptr
0x18011e7d7  nop
0x18011e7d8  lea     rcx, [rsp+190h+var_140]; this
0x18011e7dd  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18011e7e2  nop
0x18011e7e3  mov     eax, ebx
0x18011e7e5  mov     rcx, [rbp+90h+var_50]
0x18011e7e9  xor     rcx, rsp; StackCookie
0x18011e7ec  call    __security_check_cookie
0x18011e7f1  add     rsp, 158h
0x18011e7f8  pop     r15
0x18011e7fa  pop     r14
0x18011e7fc  pop     r13
0x18011e7fe  pop     r12
0x18011e800  pop     rdi
0x18011e801  pop     rsi
0x18011e802  pop     rbx
0x18011e803  pop     rbp
0x18011e804  retn
```
