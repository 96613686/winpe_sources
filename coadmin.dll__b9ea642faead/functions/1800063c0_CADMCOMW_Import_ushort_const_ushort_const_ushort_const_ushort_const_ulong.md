# CADMCOMW::Import(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800063c0`
- end: `0x1800068cd`
- name: `?Import@CADMCOMW@@UEAAJPEBG000K@Z`
- size: `1293`
- prototype: `__int64 __fastcall(CADMCOMW *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *Src, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800010b0`
- `0x1800010bc`
- `0x180001cec`
- `0x18000238c`
- `0x1800063c0`
- `0x180007068`
- `0x180007394`
- `0x180007f40`
- `0x18000be20`
- `0x18000fb06`
- `0x18000fb1e`
- `0x18000fb50`
- `0x18000fbe0`
- `0x180010010`

## import_xrefs

- `ole32!CoImpersonateClient` at `0x1800064b3`
- `ole32!CoImpersonateClient` at `0x1800064b3`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x1800068a2`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x1800068a2`
- `IisRTL!PuDbgPrint` at `0x180006542`
- `IisRTL!PuDbgPrint` at `0x1800066e1`
- `IisRTL!PuDbgPrint` at `0x18000677e`
- `IisRTL!PuDbgPrint` at `0x180006542`
- `IisRTL!PuDbgPrint` at `0x1800066e1`
- `IisRTL!PuDbgPrint` at `0x18000677e`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000646f`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000646f`

## string_xrefs

- `0x180006529`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800066c8`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180006777`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180006530`: `AccessCheck failed hr = 0x%08x\n`
- `0x1800066cf`: `AccessCheck failed hr = 0x%08x\n`
- `0x18000651e`: `CADMCOMW::Import`
- `0x1800066bd`: `CADMCOMW::Import`
- `0x180006765`: `CADMCOMW::Import`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Import(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Src,
        unsigned int a6)
{
  unsigned int v9; // r13d
  wchar_t *v10; // r12
  const unsigned __int16 *v12; // rax
  HRESULT PathCanonicalizationProof; // ebx
  int v14; // eax
  __int64 v15; // rdi
  unsigned __int64 v16; // rsi
  wchar_t *v17; // rax
  int v18; // esi
  wchar_t *v19; // r14
  int v20; // eax
  unsigned __int16 *v21; // rsi
  int v22; // eax
  struct COpenHandle *v23; // rdi
  int v24; // eax
  __int64 v25; // rax
  unsigned __int16 *v26; // rdi
  int v27; // eax
  const unsigned __int16 *v28; // r14
  unsigned __int16 *v29; // r13
  HRESULT v30; // eax
  struct COpenHandle *v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v35; // [rsp+78h] [rbp-88h]
  unsigned int v36; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v37; // [rsp+84h] [rbp-7Ch] BYREF
  int v38; // [rsp+88h] [rbp-78h] BYREF
  int v39; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+94h] [rbp-6Ch] BYREF
  const unsigned __int16 *v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  _BYTE *v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  _BYTE v49[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-18h]
  _BYTE v51[8192]; // [rsp+100h] [rbp+0h] BYREF

  v34 = Src;
  v37 = 0;
  v36 = 0;
  v40 = 0;
  v33 = 0;
  v9 = 0;
  v35 = a4;
  v10 = 0;
  memset_0(v51, 0, sizeof(v51));
  v43 = 1002;
  v41 = 0;
  v48 = 0;
  v44 = 1;
  v45 = 2;
  v46 = 0x2000;
  v47 = v51;
  STRU::STRU((STRU *)v49);
  v38 = 0;
  v39 = 0;
  if ( !a3 || !*a3 || !a4 || !Src )
  {
    PathCanonicalizationProof = -2147024809;
    goto LABEL_47;
  }
  v12 = &byte_1800127D8;
  if ( a2 )
    v12 = a2;
  v42 = v12;
  PathCanonicalizationProof = CoImpersonateClient();
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_47;
  v14 = CADMCOMW::AccessCheck(
          (__int64)this,
          0,
          &byte_1800127D8,
          2u,
          2u,
          0,
          (struct COpenHandle *)&g_ohMasterRootHandle,
          0,
          &v38);
  PathCanonicalizationProof = v14;
  if ( v14 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        4019,
        "CADMCOMW::Import",
        "AccessCheck failed hr = 0x%08x\n",
        v14);
LABEL_47:
      v21 = Src;
LABEL_48:
      v23 = v33;
      goto LABEL_49;
    }
    v21 = Src;
    v28 = a3;
LABEL_45:
    v23 = v33;
LABEL_50:
    v29 = v35;
    goto LABEL_51;
  }
  v15 = -1;
  do
    ++v15;
  while ( Src[v15] );
  v16 = (int)v15 + 1;
  v17 = (wchar_t *)operator new[](saturated_mul(v16, 2u));
  v10 = v17;
  if ( !v17 )
  {
    PathCanonicalizationProof = -2147024882;
    goto LABEL_47;
  }
  memcpy_0(v17, Src, 2 * v16);
  while ( (int)v15 > 0 && (v10[(unsigned int)v15 - 1] == 47 || v10[(unsigned int)v15 - 1] == 92) )
    LODWORD(v15) = v15 - 1;
  v18 = v15;
  v19 = &v10[(int)v15];
  if ( (int)v15 >= 0 )
  {
    while ( 1 )
    {
      if ( !v18 || v18 == (_DWORD)v15 || *v19 == 47 || *v19 == 92 )
      {
        *v19 = 0;
        v20 = CADMCOMW::OpenKeyHelper(this, 0, v10, 3u, 0x1388u, &v37);
        PathCanonicalizationProof = v20;
        if ( v20 >= 0 )
          goto LABEL_30;
        if ( v20 != -2147024893 )
          break;
      }
      --v19;
      if ( --v18 < 0 )
      {
        if ( PathCanonicalizationProof < 0 )
        {
          v21 = v34;
          goto LABEL_48;
        }
LABEL_30:
        v9 = v37;
        goto LABEL_31;
      }
    }
    v21 = v34;
    v28 = a3;
    goto LABEL_45;
  }
LABEL_31:
  v22 = CADMCOMW::Lookup(this, v9, &v36, &v40, &v33);
  v23 = v33;
  PathCanonicalizationProof = v22;
  if ( v22 < 0 )
    goto LABEL_35;
  COpenHandle::Release(v33, this);
  v24 = CADMCOMW::AccessCheck((__int64)this, v9, &byte_1800127D8, 2u, 2u, 0, v23, 0, &v39);
  PathCanonicalizationProof = v24;
  if ( v24 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        4101,
        "CADMCOMW::Import",
        "AccessCheck failed hr = 0x%08x\n",
        v24);
      v21 = v34;
LABEL_49:
      v28 = a3;
      goto LABEL_50;
    }
LABEL_35:
    v21 = v34;
    goto LABEL_49;
  }
  v25 = v18;
  v21 = v34;
  v26 = &v34[v25];
  v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64 *, int *))(**((_QWORD **)this + 4) + 168LL))(
          *((_QWORD *)this + 4),
          v36,
          v26,
          &v43,
          &v41);
  PathCanonicalizationProof = v27;
  if ( v27 != -2147024893 && v27 != -2146646015 && v27 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        4118,
        "CADMCOMW::Import",
        "Error trying to retrieve keytype for %ws\n",
        v26);
    goto LABEL_48;
  }
  v28 = a3;
  PathCanonicalizationProof = MakePathCanonicalizationProof(a3, 1, (struct STRU *)v49);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_45;
  v28 = 0;
  v29 = v35;
  v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _BYTE *, const unsigned __int16 *, __int64, unsigned __int16 *, unsigned int))(**((_QWORD **)this + 4) + 480LL))(
          *((_QWORD *)this + 4),
          v36,
          v26,
          v51,
          v42,
          v50,
          v35,
          a6);
  v23 = v33;
  PathCanonicalizationProof = v30;
LABEL_51:
  if ( v38 || v39 )
    CADMCOMW::AuditAccess(this, 0x11A0u, PathCanonicalizationProof, 0, v29, 0, v21, 0, 0, 0, v28);
  if ( v23 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4), v36);
    COpenHandle::Release(v23, this);
  }
  if ( v10 )
    operator delete[](v10);
  STRU::~STRU((STRU *)v49);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x1800063c0  push    rbp
0x1800063c2  push    rbx
0x1800063c3  push    rsi
0x1800063c4  push    rdi
0x1800063c5  push    r12
0x1800063c7  push    r13
0x1800063c9  push    r14
0x1800063cb  push    r15
0x1800063cd  lea     rbp, [rsp-2018h]
0x1800063d5  mov     eax, 2118h
0x1800063da  call    _alloca_probe
0x1800063df  sub     rsp, rax
0x1800063e2  mov     rax, cs:__security_cookie
0x1800063e9  xor     rax, rsp
0x1800063ec  mov     [rbp+2050h+var_50], rax
0x1800063f3  mov     r14, [rbp+2050h+Src]
0x1800063fa  xor     eax, eax
0x1800063fc  mov     rdi, r8
0x1800063ff  mov     [rsp+2150h+var_20F0], r8
0x180006404  mov     rbx, rdx
0x180006407  mov     [rsp+2150h+var_20E0], r14
0x18000640c  mov     r15, rcx
0x18000640f  mov     [rbp+2050h+var_20CC], eax
0x180006412  xor     edx, edx; Val
0x180006414  mov     [rbp+2050h+var_20D0], eax
0x180006417  mov     r8d, 2000h; Size
0x18000641d  mov     [rbp+2050h+var_20C0], eax
0x180006420  lea     rcx, [rbp+2050h+var_2050]; void *
0x180006424  mov     [rsp+2150h+var_20E8], rax
0x180006429  mov     r13d, eax
0x18000642c  mov     [rsp+2150h+var_20D8], r9
0x180006431  mov     r12d, eax
0x180006434  mov     rsi, r9
0x180006437  call    memset_0
0x18000643c  xor     ecx, ecx
0x18000643e  mov     [rbp+2050h+var_20B0], 3EAh
0x180006446  mov     [rbp+2050h+var_20BC], ecx
0x180006449  lea     rax, [rbp+2050h+var_2050]
0x18000644d  mov     [rbp+2050h+var_2090], rcx
0x180006451  lea     rcx, [rbp+2050h+var_2088]
0x180006455  mov     [rbp+2050h+var_20A8], 1
0x18000645c  mov     [rbp+2050h+var_20A4], 2
0x180006463  mov     [rbp+2050h+var_20A0], 2000h
0x18000646b  mov     [rbp+2050h+var_2098], rax
0x18000646f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006475  xor     ecx, ecx
0x180006477  mov     [rbp+2050h+var_20C8], ecx
0x18000647a  mov     [rbp+2050h+var_20C4], ecx
0x18000647d  test    rdi, rdi
0x180006480  jz      loc_180006816
0x180006486  cmp     [rdi], cx
0x180006489  jz      loc_180006816
0x18000648f  test    rsi, rsi
0x180006492  jz      loc_180006816
0x180006498  test    r14, r14
0x18000649b  jz      loc_180006816
0x1800064a1  test    rbx, rbx
0x1800064a4  lea     rax, byte_1800127D8
0x1800064ab  cmovnz  rax, rbx
0x1800064af  mov     [rbp+2050h+var_20B8], rax
0x1800064b3  call    cs:__imp_CoImpersonateClient
0x1800064b9  xor     ecx, ecx
0x1800064bb  mov     ebx, eax
0x1800064bd  test    eax, eax
0x1800064bf  js      loc_18000681B
0x1800064c5  lea     rax, [rbp+2050h+var_20C8]
0x1800064c9  xor     edx, edx
0x1800064cb  mov     [rsp+2150h+var_2110], rax
0x1800064d0  lea     r9d, [r12+2]
0x1800064d5  mov     qword ptr [rsp+2150h+var_2118], rcx
0x1800064da  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x1800064e1  mov     [rsp+2150h+var_2120], rax
0x1800064e6  lea     r8, byte_1800127D8
0x1800064ed  mov     [rsp+2150h+var_2128], rcx
0x1800064f2  mov     rcx, r15
0x1800064f5  mov     dword ptr [rsp+2150h+var_2130], 2
0x1800064fd  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180006502  xor     ecx, ecx
0x180006504  mov     ebx, eax
0x180006506  test    eax, eax
0x180006508  jns     short loc_18000654F
0x18000650a  test    byte ptr cs:g_dwDebugFlags, 3
0x180006511  jz      loc_180006809
0x180006517  mov     rcx, cs:g_pDebug
0x18000651e  lea     r9, aCadmcomwImport; "CADMCOMW::Import"
0x180006525  mov     dword ptr [rsp+2150h+var_2128], eax
0x180006529  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180006530  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180006537  mov     r8d, 0FB3h
0x18000653d  mov     [rsp+2150h+var_2130], rax
0x180006542  call    cs:__imp_PuDbgPrint
0x180006548  xor     ecx, ecx
0x18000654a  jmp     loc_18000681B
0x18000654f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006553  mov     rdi, r8
0x180006556  inc     rdi
0x180006559  cmp     [r14+rdi*2], cx
0x18000655e  jnz     short loc_180006556
0x180006560  lea     eax, [rdi+1]
0x180006563  movsxd  rsi, eax
0x180006566  mov     eax, 2
0x18000656b  mul     rsi
0x18000656e  cmovb   rax, r8
0x180006572  mov     rcx, rax; unsigned __int64
0x180006575  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000657a  xor     ecx, ecx
0x18000657c  mov     r12, rax
0x18000657f  test    rax, rax
0x180006582  jnz     short loc_18000658E
0x180006584  mov     ebx, 8007000Eh
0x180006589  jmp     loc_18000681B
0x18000658e  lea     r8, [rsi+rsi]; Size
0x180006592  mov     rdx, r14; Src
0x180006595  mov     rcx, r12; void *
0x180006598  call    memcpy_0
0x18000659d  xor     ecx, ecx
0x18000659f  jmp     short loc_1800065B7
0x1800065a1  mov     eax, edi
0x1800065a3  cmp     word ptr [r12+rax*2-2], 2Fh ; '/'
0x1800065aa  jz      short loc_1800065B5
0x1800065ac  cmp     word ptr [r12+rax*2-2], 5Ch ; '\'
0x1800065b3  jnz     short loc_1800065BB
0x1800065b5  dec     edi
0x1800065b7  test    edi, edi
0x1800065b9  jg      short loc_1800065A1
0x1800065bb  movsxd  rax, edi
0x1800065be  mov     esi, edi
0x1800065c0  lea     r14, [r12+rax*2]
0x1800065c4  test    edi, edi
0x1800065c6  js      short loc_180006634
0x1800065c8  test    esi, esi
0x1800065ca  jz      short loc_1800065DE
0x1800065cc  cmp     esi, edi
0x1800065ce  jz      short loc_1800065DE
0x1800065d0  cmp     word ptr [r14], 2Fh ; '/'
0x1800065d5  jz      short loc_1800065DE
0x1800065d7  cmp     word ptr [r14], 5Ch ; '\'
0x1800065dc  jnz     short loc_180006619
0x1800065de  lea     rax, [rbp+2050h+var_20CC]
0x1800065e2  mov     [r14], cx
0x1800065e6  mov     [rsp+2150h+var_2128], rax; unsigned int *
0x1800065eb  mov     r9d, 3; unsigned int
0x1800065f1  mov     r8, r12; Str
0x1800065f4  mov     dword ptr [rsp+2150h+var_2130], 1388h; unsigned int
0x1800065fc  xor     edx, edx; unsigned int
0x1800065fe  mov     rcx, r15; this
0x180006601  call    ?OpenKeyHelper@CADMCOMW@@QEAAJKPEBGKKPEAK@Z; CADMCOMW::OpenKeyHelper(ulong,ushort const *,ulong,ulong,ulong *)
0x180006606  xor     ecx, ecx
0x180006608  mov     ebx, eax
0x18000660a  test    eax, eax
0x18000660c  jns     short loc_180006630
0x18000660e  cmp     eax, 80070003h
0x180006613  jnz     loc_1800067FD
0x180006619  sub     r14, 2
0x18000661d  sub     esi, 1
0x180006620  jns     short loc_1800065C8
0x180006622  test    ebx, ebx
0x180006624  jns     short loc_180006630
0x180006626  mov     rsi, [rsp+2150h+var_20E0]
0x18000662b  jmp     loc_18000681E
0x180006630  mov     r13d, [rbp+2050h+var_20CC]
0x180006634  lea     rax, [rsp+2150h+var_20E8]
0x180006639  mov     edx, r13d; unsigned int
0x18000663c  lea     r9, [rbp+2050h+var_20C0]; unsigned int *
0x180006640  mov     [rsp+2150h+var_2130], rax; struct COpenHandle **
0x180006645  lea     r8, [rbp+2050h+var_20D0]; unsigned int *
0x180006649  mov     rcx, r15; this
0x18000664c  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x180006651  mov     rdi, [rsp+2150h+var_20E8]
0x180006656  xor     ecx, ecx
0x180006658  mov     ebx, eax
0x18000665a  test    eax, eax
0x18000665c  js      loc_1800066F3
0x180006662  mov     rdx, r15; void *
0x180006665  mov     rcx, rdi; this
0x180006668  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x18000666d  xor     ecx, ecx
0x18000666f  lea     rax, [rbp+2050h+var_20C4]
0x180006673  mov     [rsp+2150h+var_2110], rax
0x180006678  lea     r8, byte_1800127D8
0x18000667f  mov     qword ptr [rsp+2150h+var_2118], rcx
0x180006684  mov     edx, r13d
0x180006687  mov     [rsp+2150h+var_2120], rdi
0x18000668c  mov     [rsp+2150h+var_2128], rcx
0x180006691  lea     r9d, [rcx+2]
0x180006695  mov     rcx, r15
0x180006698  mov     dword ptr [rsp+2150h+var_2130], 2
0x1800066a0  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x1800066a5  xor     ecx, ecx
0x1800066a7  mov     ebx, eax
0x1800066a9  test    eax, eax
0x1800066ab  jns     short loc_1800066FD
0x1800066ad  test    byte ptr cs:g_dwDebugFlags, 3
0x1800066b4  jz      short loc_1800066F3
0x1800066b6  mov     rcx, cs:g_pDebug
0x1800066bd  lea     r9, aCadmcomwImport; "CADMCOMW::Import"
0x1800066c4  mov     dword ptr [rsp+2150h+var_2128], eax
0x1800066c8  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800066cf  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x1800066d6  mov     r8d, 1005h
0x1800066dc  mov     [rsp+2150h+var_2130], rax
0x1800066e1  call    cs:__imp_PuDbgPrint
0x1800066e7  mov     rsi, [rsp+2150h+var_20E0]
0x1800066ec  xor     ecx, ecx
0x1800066ee  jmp     loc_180006823
0x1800066f3  mov     rsi, [rsp+2150h+var_20E0]
0x1800066f8  jmp     loc_180006823
0x1800066fd  mov     rcx, [r15+20h]
0x180006701  lea     rdx, [rbp+2050h+var_20BC]
0x180006705  movsxd  rax, esi
0x180006708  lea     r9, [rbp+2050h+var_20B0]
0x18000670c  mov     rsi, [rsp+2150h+var_20E0]
0x180006711  mov     [rsp+2150h+var_2130], rdx
0x180006716  mov     edx, [rbp+2050h+var_20D0]
0x180006719  lea     rdi, [rsi+rax*2]
0x18000671d  mov     rax, [rcx]
0x180006720  mov     r8, rdi
0x180006723  mov     rax, [rax+0A8h]
0x18000672a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000672f  mov     ebx, eax
0x180006731  cmp     eax, 80070003h
0x180006736  jz      short loc_18000678B
0x180006738  cmp     eax, 800CC801h
0x18000673d  jz      short loc_18000678B
0x18000673f  xor     ecx, ecx
0x180006741  test    eax, eax
0x180006743  jns     short loc_18000678B
0x180006745  test    byte ptr cs:g_dwDebugFlags, 3
0x18000674c  jz      loc_18000681E
0x180006752  mov     rcx, cs:g_pDebug
0x180006759  lea     rax, aErrorTryingToR; "Error trying to retrieve keytype for %w"...
0x180006760  mov     [rsp+2150h+var_2128], rdi
0x180006765  lea     r9, aCadmcomwImport; "CADMCOMW::Import"
0x18000676c  mov     r8d, 1016h
0x180006772  mov     [rsp+2150h+var_2130], rax
0x180006777  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000677e  call    cs:__imp_PuDbgPrint
0x180006784  xor     ecx, ecx
0x180006786  jmp     loc_18000681E
0x18000678b  mov     r14, [rsp+2150h+var_20F0]
0x180006790  lea     r8, [rbp+2050h+var_2088]; struct STRU *
0x180006794  mov     rcx, r14; unsigned __int16 *
0x180006797  mov     edx, 1; int
0x18000679c  call    ?MakePathCanonicalizationProof@@YAJPEBGHPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,int,STRU *)
0x1800067a1  xor     ecx, ecx
0x1800067a3  mov     ebx, eax
0x1800067a5  test    eax, eax
0x1800067a7  js      short loc_18000680F
0x1800067a9  mov     r10, [r15+20h]
0x1800067ad  lea     r9, [rbp+2050h+var_2050]
0x1800067b1  mov     rdx, [rbp+2050h+var_2068]
0x1800067b5  mov     r14d, ecx
0x1800067b8  mov     ecx, [rbp+2050h+arg_28]
0x1800067be  mov     r8, rdi
0x1800067c1  mov     r13, [rsp+2150h+var_20D8]
0x1800067c6  mov     rax, [r10]
0x1800067c9  mov     [rsp+2150h+var_2118], ecx
0x1800067cd  mov     rcx, [rbp+2050h+var_20B8]
0x1800067d1  mov     [rsp+2150h+var_2120], r13
0x1800067d6  mov     rax, [rax+1E0h]
0x1800067dd  mov     [rsp+2150h+var_2128], rdx
0x1800067e2  mov     edx, [rbp+2050h+var_20D0]
0x1800067e5  mov     [rsp+2150h+var_2130], rcx
0x1800067ea  mov     rcx, r10
0x1800067ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f2  mov     rdi, [rsp+2150h+var_20E8]
0x1800067f7  mov     ebx, eax
0x1800067f9  xor     ecx, ecx
0x1800067fb  jmp     short loc_18000682D
0x1800067fd  mov     rsi, [rsp+2150h+var_20E0]
0x180006802  mov     r14, [rsp+2150h+var_20F0]
0x180006807  jmp     short loc_18000680F
0x180006809  mov     rsi, r14
0x18000680c  mov     r14, rdi
0x18000680f  mov     rdi, [rsp+2150h+var_20E8]
0x180006814  jmp     short loc_180006828
0x180006816  mov     ebx, 80070057h
0x18000681b  mov     rsi, r14
0x18000681e  mov     rdi, [rsp+2150h+var_20E8]
0x180006823  mov     r14, [rsp+2150h+var_20F0]
0x180006828  mov     r13, [rsp+2150h+var_20D8]
0x18000682d  cmp     [rbp+2050h+var_20C8], ecx
0x180006830  jnz     short loc_180006837
0x180006832  cmp     [rbp+2050h+var_20C4], ecx
0x180006835  jz      short loc_18000686B
0x180006837  mov     [rsp+2150h+var_2100], r14; unsigned __int16 *
0x18000683c  xor     r9d, r9d; unsigned int
0x18000683f  mov     [rsp+2150h+var_2108], rcx; struct _METADATA_RECORD *
0x180006844  mov     r8d, ebx; int
0x180006847  mov     [rsp+2150h+var_2110], rcx; struct _METADATA_RECORD *
0x18000684c  mov     edx, 11A0h; unsigned int
0x180006851  mov     [rsp+2150h+var_2118], ecx; unsigned int
0x180006855  mov     [rsp+2150h+var_2120], rsi; unsigned __int16 *
0x18000685a  mov     dword ptr [rsp+2150h+var_2128], ecx; unsigned int
0x18000685e  mov     rcx, r15; this
0x180006861  mov     [rsp+2150h+var_2130], r13; unsigned __int16 *
0x180006866  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x18000686b  test    rdi, rdi
0x18000686e  jz      short loc_180006891
0x180006870  mov     rcx, [r15+20h]
  ... truncated ...
```
