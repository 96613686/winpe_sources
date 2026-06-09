# ADAMComputeDynamicGroups

- ea: `0x180124f10`
- end: `0x180125833`
- name: `ADAMComputeDynamicGroups`
- size: `2339`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x180021aa3`
- `0x18011cc00`
- `0x180124f10`
- `0x18012583c`
- `0x180172b30`
- `0x180173e2c`
- `0x180181c60`
- `0x18019e94c`
- `0x1801c4a34`
- `0x1801d0ea0`
- `0x1801d3cfc`
- `0x1801d614c`
- `0x1803befd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180124fd7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180125607`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180124fd7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180125607`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180124f5b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180124f5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180125800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180125800`
- `ntdll!RtlNtStatusToDosError` at `0x18012543a`
- `ntdll!RtlNtStatusToDosError` at `0x18012543a`
- `ntdll!RtlLengthSid` at `0x18012535d`
- `ntdll!RtlLengthSid` at `0x1801254f6`
- `ntdll!RtlLengthSid` at `0x1801255b4`
- `ntdll!RtlLengthSid` at `0x18012535d`
- `ntdll!RtlLengthSid` at `0x1801254f6`
- `ntdll!RtlLengthSid` at `0x1801255b4`

## pseudocode

```c
__int64 __fastcall ADAMComputeDynamicGroups(__int64 a1, const void ****a2, __int64 *a3, unsigned int *a4)
{
  _QWORD *Value; // rax
  _QWORD *v6; // rsi
  unsigned int v7; // edi
  const void **v9; // r15
  _QWORD *v10; // r13
  int v11; // r12d
  const void **v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 *v16; // r9
  unsigned int i; // r8d
  __int64 v18; // rdx
  int v19; // r8d
  int v20; // r9d
  int v21; // ebx
  unsigned int v22; // ebx
  unsigned int j; // r13d
  PSID v24; // rax
  _DWORD *v25; // rbx
  NTSTATUS Memberships2; // eax
  unsigned int v27; // r13d
  bool v28; // zf
  int v29; // eax
  __int64 v30; // rax
  unsigned int *v31; // rdx
  unsigned int k; // ebx
  void *v33; // rax
  ULONG v34; // eax
  __int64 v35; // rdx
  __int64 *v36; // r9
  void *v37; // rcx
  const void ****v38; // r15
  const void **v39; // rbx
  ULONG v40; // eax
  const void **v41; // rcx
  __int64 v42; // rax
  unsigned int v43; // ebx
  unsigned int v44; // ecx
  __int64 v45; // rdx
  unsigned int m; // ebx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  DWORD dwErrCode; // [rsp+60h] [rbp-198h]
  unsigned int v51; // [rsp+68h] [rbp-190h]
  _DWORD Size[3]; // [rsp+6Ch] [rbp-18Ch] BYREF
  unsigned int v53; // [rsp+78h] [rbp-180h]
  _DWORD v54[3]; // [rsp+7Ch] [rbp-17Ch] BYREF
  int v55[2]; // [rsp+88h] [rbp-170h]
  _DWORD *v56; // [rsp+90h] [rbp-168h] BYREF
  PSID *v57; // [rsp+98h] [rbp-160h] BYREF
  void *v58; // [rsp+A0h] [rbp-158h] BYREF
  void *Src; // [rsp+A8h] [rbp-150h]
  int v60; // [rsp+B0h] [rbp-148h]
  int v61; // [rsp+B4h] [rbp-144h]
  unsigned int *v62; // [rsp+B8h] [rbp-140h]
  __int64 v63; // [rsp+C0h] [rbp-138h]
  unsigned int v64; // [rsp+C8h] [rbp-130h]
  int v65; // [rsp+CCh] [rbp-12Ch]
  __int64 *v66; // [rsp+D0h] [rbp-128h]
  _QWORD *v67; // [rsp+D8h] [rbp-120h]
  __int128 v68; // [rsp+E0h] [rbp-118h]
  __int64 v69; // [rsp+F0h] [rbp-108h]
  __int64 v70; // [rsp+F8h] [rbp-100h]
  const void ****v71; // [rsp+100h] [rbp-F8h]
  _OWORD v72[2]; // [rsp+110h] [rbp-E8h] BYREF
  _OWORD v73[4]; // [rsp+130h] [rbp-C8h] BYREF
  _OWORD v74[4]; // [rsp+170h] [rbp-88h] BYREF

  v62 = a4;
  v66 = a3;
  v71 = a2;
  *(_QWORD *)&Size[1] = a1;
  Value = TlsGetValue(dwTSindex);
  v6 = Value;
  v67 = Value;
  v7 = 0;
  dwErrCode = 0;
  v65 = 0;
  v61 = 0;
  if ( !Value )
    return 1;
  v9 = 0;
  if ( a2 && *a2 )
    v9 = **a2;
  v10 = Value + 697;
  v63 = Value[697];
  v11 = -__CFSHR__(*((_DWORD *)Value + 1401), 12);
  v60 = v11;
  if ( !v9 )
    goto LABEL_18;
  a2[1][2] = (const void **)malloc(*(unsigned int *)*v9);
  v12 = a2[1][2];
  if ( v12 )
  {
    memcpy_0(v12, *v9, *(unsigned int *)*v9);
    if ( !v9[3] )
    {
      if ( v9[2] )
        goto LABEL_15;
      *v10 = 0;
      *((_DWORD *)v6 + 1401) |= 0x800u;
      DBOpen2(1, v6 + 697);
      dwErrCode = ADAMComputeGroupMemberships((int)v6, (__int64 *)v9);
      v13 = *v10;
      *v10 = v63;
      *((_DWORD *)v6 + 1401) = (v11 << 11) ^ (*((_DWORD *)v6 + 1401) ^ (v11 << 11)) & 0xFFFFF7FF;
      if ( v13 )
        DBClose(v13, dwErrCode == 0);
      if ( !dwErrCode )
      {
LABEL_15:
        v14 = *((_DWORD *)v9 + 2);
        *v62 = v14;
        v15 = THAlloc_((_DWORD)v6, 1, 16 * v14, 1, 0, 54003102);
        v16 = v66;
        *v66 = v15;
        for ( i = 0; i < *((_DWORD *)v9 + 2); ++i )
        {
          v18 = 2LL * i;
          *(_QWORD *)(*v16 + 8 * v18) = (char *)v9[2] + 28 * i;
          *(_DWORD *)(*v16 + 8 * v18 + 8) = 4;
        }
      }
      goto LABEL_78;
    }
LABEL_18:
    v56 = 0;
    v57 = 0;
    *(_QWORD *)v55 = 0;
    v51 = 0;
    v53 = 0;
    memset(v54, 0, sizeof(v54));
    Size[0] = 0;
    v68 = 0;
    memset(v72, 0, 28);
    v58 = 0;
    *v10 = 0;
    *((_DWORD *)v6 + 1401) |= 0x800u;
    dwErrCode = AuthzGetInfoHelper(v6, *(_QWORD *)&Size[1], 1, &v57);
    if ( dwErrCode )
      goto LABEL_54;
    v21 = 2;
    LODWORD(Src) = 2;
    dwErrCode = AuthzGetInfoHelper(v6, *(_QWORD *)&Size[1], 2, &v56);
    if ( dwErrCode )
      goto LABEL_54;
    DBOpen2(1, v6 + 697);
    if ( v9 && v9[3] )
    {
      memset(v74, 0, 60);
      dwErrCode = DBFindDSName(*v10, *v9);
      if ( dwErrCode )
        goto LABEL_54;
      dwErrCode = DBGetObjectSecurityInfo(*v10, *(_DWORD *)(*v10 + 32LL), 0, 0, (__int64)v74, 0, 3);
      if ( dwErrCode )
        goto LABEL_54;
      MakeSid((char *)&v74[1] + 8, 0x201u, v72, Size);
      *(_QWORD *)&v68 = v72;
      *((_QWORD *)&v68 + 1) = gpEnterpriseUsersSid;
    }
    else
    {
      v21 = 0;
      LODWORD(Src) = 0;
    }
    v22 = *v56 + 1 + v21;
    v53 = v22;
    *(_QWORD *)v55 = THAlloc_((_DWORD)v6, 1, 8 * v22, 1, 0, 54003180);
    v51 = 0;
    v64 = 0;
    for ( j = 0; j < v22; ++j )
    {
      if ( j )
      {
        if ( j > *v56 )
          v24 = (PSID)*((_QWORD *)&v68 + j - *v56 - 1);
        else
          v24 = *(PSID *)&v56[4 * j - 2];
      }
      else
      {
        v24 = *v57;
      }
      *(_QWORD *)&Size[1] = v24;
      Size[0] = RtlLengthSid(v24);
      if ( Size[0] <= 0x1Cu )
      {
        v25 = (_DWORD *)THAlloc_((_DWORD)v6, 1, 58, 1, 0, 54003200);
        *(_QWORD *)(*(_QWORD *)v55 + 8LL * v51++) = v25;
        v64 = v51;
        *v25 = 58;
        memcpy_0(v25 + 6, *(const void **)&Size[1], Size[0]);
        v25[1] = Size[0];
        v22 = v53;
      }
    }
    v53 = v51;
    Memberships2 = SampGetMemberships2(v55[0], v51, 0, 5, 0, (__int64)v54, (__int64)&v54[1], 0, 0, 0, 0, 0);
    if ( Memberships2 )
    {
      dwErrCode = RtlNtStatusToDosError(Memberships2);
    }
    else
    {
      v27 = v54[0];
      v28 = v54[0] + (_DWORD)Src == 0;
      v29 = v54[0] + (_DWORD)Src;
      *v62 = v54[0] + (_DWORD)Src;
      if ( !v28 )
      {
        v30 = THAlloc_((_DWORD)v6, 1, 44 * v29, 1, 0, 54003231);
        *v66 = v30;
        v31 = v62;
        *(_QWORD *)&Size[1] = v30 + 16LL * *v62;
        v70 = *(_QWORD *)&Size[1];
        for ( k = 0; k < *v31; ++k )
        {
          v69 = k;
          if ( k >= v27 )
            v33 = (void *)*((_QWORD *)&v68 + k - v27);
          else
            v33 = (void *)(*(_QWORD *)(*(_QWORD *)&v54[1] + 8LL * k) + 24LL);
          Src = v33;
          v34 = RtlLengthSid(v33);
          Size[0] = v34;
          v35 = 2 * v69;
          v36 = v66;
          v37 = *(void **)&Size[1];
          *(_QWORD *)(*v66 + 8 * v35) = *(_QWORD *)&Size[1];
          *(_DWORD *)(*v36 + 8 * v35 + 8) = 4;
          memcpy_0(v37, Src, v34);
          *(_QWORD *)&Size[1] += 28LL;
          v70 = *(_QWORD *)&Size[1];
          v31 = v62;
        }
      }
      if ( !v9 )
      {
        v38 = v71;
        if ( v71 )
        {
          memset(v73, 0, 60);
          LODWORD(v73[0]) = 58;
          v39 = (const void **)v57;
          v40 = RtlLengthSid(*v57);
          DWORD1(v73[0]) = v40;
          if ( v40 <= 0x1C )
          {
            memcpy_0((char *)&v73[1] + 8, *v39, v40);
            v10 = v6 + 697;
            if ( !(unsigned int)DBRefreshDSName(v6[697], v73, &v58) )
            {
              v38[1][2] = (const void **)malloc(*(unsigned int *)v58);
              v41 = v38[1][2];
              if ( v41 )
                memcpy_0(v41, v58, *(unsigned int *)v58);
              else
                dwErrCode = 14;
            }
            goto LABEL_54;
          }
          dwErrCode = 1337;
        }
      }
    }
    v10 = v6 + 697;
LABEL_54:
    if ( v56 )
    {
      THFreeAux((_DWORD)v6, (_DWORD)v56, v19, v20, 54003282);
      v56 = 0;
    }
    if ( v57 )
    {
      THFreeAux((_DWORD)v6, (_DWORD)v57, v19, v20, 54003285);
      v57 = 0;
    }
    if ( v58 )
    {
      THFreeAux((_DWORD)v6, (_DWORD)v58, v19, v20, 54003288);
      v58 = 0;
    }
    v42 = *(_QWORD *)v55;
    if ( *(_QWORD *)v55 )
    {
      v43 = 0;
      v44 = v51;
      while ( v43 < v44 )
      {
        v45 = *(_QWORD *)(v42 + 8LL * v43);
        if ( v45 )
        {
          THFreeAux((_DWORD)v6, v45, v19, v20, 54003292);
          v42 = *(_QWORD *)v55;
          v44 = v51;
        }
        *(_QWORD *)(v42 + 8LL * v43++) = 0;
      }
      THFreeAux((_DWORD)v6, v42, v19, v20, 54003294);
      *(_QWORD *)v55 = 0;
    }
    if ( *(_QWORD *)&v54[1] )
    {
      for ( m = 0; m < v54[0]; ++m )
      {
        v47 = *(_QWORD *)&v54[1];
        v48 = *(_QWORD *)(*(_QWORD *)&v54[1] + 8LL * m);
        if ( v48 )
        {
          THFreeAux((_DWORD)v6, v48, v19, v20, 54003298);
          v47 = *(_QWORD *)&v54[1];
        }
        *(_QWORD *)(v47 + 8LL * m) = 0;
      }
      if ( *(_QWORD *)&v54[1] )
        THFreeAux((_DWORD)v6, v54[1], v19, v20, 54003300);
      *(_QWORD *)&v54[1] = 0;
    }
    v49 = *v10;
    *v10 = v63;
    *((_DWORD *)v6 + 1401) = (v11 << 11) ^ (*((_DWORD *)v6 + 1401) ^ (v11 << 11)) & 0xFFFFF7FF;
    if ( v49 )
      DBClose(v49, 1);
    goto LABEL_78;
  }
  dwErrCode = 14;
LABEL_78:
  if ( dwErrCode )
    SetLastError(dwErrCode);
  LOBYTE(v7) = dwErrCode == 0;
  return v7;
}

```

## disassembly

```asm
0x180124f10  push    rbx
0x180124f12  push    rsi
0x180124f13  push    rdi
0x180124f14  push    r12
0x180124f16  push    r13
0x180124f18  push    r14
0x180124f1a  push    r15
0x180124f1c  sub     rsp, 1C0h
0x180124f23  mov     rax, cs:__security_cookie
0x180124f2a  xor     rax, rsp
0x180124f2d  mov     [rsp+1F8h+var_48], rax
0x180124f35  mov     [rsp+1F8h+var_140], r9
0x180124f3d  mov     [rsp+1F8h+var_128], r8
0x180124f45  mov     rbx, rdx
0x180124f48  mov     [rsp+1F8h+var_F8], rdx
0x180124f50  mov     qword ptr [rsp+1F8h+Size+4], rcx
0x180124f55  mov     ecx, cs:dwTSindex; dwTlsIndex
0x180124f5b  call    cs:__imp_TlsGetValue
0x180124f61  mov     rsi, rax
0x180124f64  mov     [rsp+1F8h+var_120], rax
0x180124f6c  xor     edi, edi
0x180124f6e  mov     [rsp+1F8h+dwErrCode], edi
0x180124f72  mov     [rsp+1F8h+var_12C], edi
0x180124f79  mov     [rsp+1F8h+var_144], edi
0x180124f80  test    rax, rax
0x180124f83  jnz     short loc_180124F8D
0x180124f85  lea     eax, [rsi+1]
0x180124f88  jmp     loc_180125810
0x180124f8d  mov     r15, rdi
0x180124f90  test    rbx, rbx
0x180124f93  jz      short loc_180124FA0
0x180124f95  mov     rax, [rbx]
0x180124f98  test    rax, rax
0x180124f9b  jz      short loc_180124FA0
0x180124f9d  mov     r15, [rax]
0x180124fa0  lea     r13, [rsi+15C8h]
0x180124fa7  mov     rax, [r13+0]
0x180124fab  mov     [rsp+1F8h+var_138], rax
0x180124fb3  mov     r12d, [rsi+15E4h]
0x180124fba  shr     r12d, 0Ch
0x180124fbe  sbb     r12d, r12d
0x180124fc1  mov     [rsp+1F8h+var_148], r12d
0x180124fc9  test    r15, r15
0x180124fcc  jz      loc_18012511A
0x180124fd2  mov     rax, [r15]
0x180124fd5  mov     ecx, [rax]; Size
0x180124fd7  call    cs:__imp_malloc
0x180124fdd  mov     rcx, [rbx+8]
0x180124fe1  mov     [rcx+10h], rax
0x180124fe5  mov     rax, [rbx+8]
0x180124fe9  mov     rcx, [rax+10h]; void *
0x180124fed  test    rcx, rcx
0x180124ff0  jnz     short loc_180124FFF
0x180124ff2  mov     [rsp+1F8h+dwErrCode], 0Eh
0x180124ffa  jmp     loc_1801257D1
0x180124fff  mov     rdx, [r15]; Src
0x180125002  mov     r8d, [rdx]; Size
0x180125005  call    memcpy_0
0x18012500a  test    r15, r15
0x18012500d  jz      loc_18012511A
0x180125013  cmp     [r15+18h], rdi
0x180125017  jnz     loc_18012511A
0x18012501d  cmp     [r15+10h], rdi
0x180125021  jnz     short loc_18012509C
0x180125023  mov     [r13+0], rdi
0x180125027  bts     dword ptr [rsi+15E4h], 0Bh
0x18012502f  mov     rdx, r13
0x180125032  mov     r14d, 1
0x180125038  mov     ecx, r14d
0x18012503b  call    DBOpen2
0x180125040  mov     rdx, r15
0x180125043  mov     rcx, rsi
0x180125046  call    ADAMComputeGroupMemberships
0x18012504b  mov     [rsp+1F8h+dwErrCode], eax
0x18012504f  mov     rcx, [r13+0]
0x180125053  mov     rax, [rsp+1F8h+var_138]
0x18012505b  mov     [r13+0], rax
0x18012505f  shl     r12d, 0Bh
0x180125063  mov     eax, r12d
0x180125066  xor     eax, [rsi+15E4h]
0x18012506c  btr     eax, 0Bh
0x180125070  xor     eax, r12d
0x180125073  mov     [rsi+15E4h], eax
0x180125079  test    rcx, rcx
0x18012507c  jz      short loc_18012508E
0x18012507e  mov     eax, [rsp+1F8h+dwErrCode]
0x180125082  mov     edx, edi
0x180125084  test    eax, eax
0x180125086  setz    dl
0x180125089  call    DBClose
0x18012508e  mov     eax, [rsp+1F8h+dwErrCode]
0x180125092  test    eax, eax
0x180125094  jnz     loc_1801257D1
0x18012509a  jmp     short loc_1801250A2
0x18012509c  mov     r14d, 1
0x1801250a2  mov     eax, [r15+8]
0x1801250a6  mov     rcx, [rsp+1F8h+var_140]
0x1801250ae  mov     [rcx], eax
0x1801250b0  mov     r8d, eax
0x1801250b3  shl     r8, 4
0x1801250b7  mov     dword ptr [rsp+1F8h+var_1D0], 338059Eh
0x1801250bf  mov     [rsp+1F8h+var_1D8], edi
0x1801250c3  mov     r9d, r14d
0x1801250c6  mov     rdx, r14
0x1801250c9  mov     rcx, rsi
0x1801250cc  call    THAlloc_
0x1801250d1  mov     r9, [rsp+1F8h+var_128]
0x1801250d9  mov     [r9], rax
0x1801250dc  mov     r8d, edi
0x1801250df  mov     [rsp+1F8h+var_194], edi
0x1801250e3  cmp     r8d, [r15+8]
0x1801250e7  jnb     loc_1801257D1
0x1801250ed  mov     eax, r8d
0x1801250f0  mov     edx, r8d
0x1801250f3  add     rdx, rdx
0x1801250f6  imul    rcx, rax, 1Ch
0x1801250fa  add     rcx, [r15+10h]
0x1801250fe  mov     rax, [r9]
0x180125101  mov     [rax+rdx*8], rcx
0x180125105  mov     rax, [r9]
0x180125108  mov     dword ptr [rax+rdx*8+8], 4
0x180125110  add     r8d, r14d
0x180125113  mov     [rsp+1F8h+var_194], r8d
0x180125118  jmp     short loc_1801250E3
0x18012511a  mov     [rsp+1F8h+var_168], rdi
0x180125122  mov     [rsp+1F8h+var_160], rdi
0x18012512a  mov     qword ptr [rsp+1F8h+var_170], rdi
0x180125132  mov     ebx, edi
0x180125134  mov     [rsp+1F8h+var_190], ebx
0x180125138  mov     [rsp+1F8h+var_180], ebx
0x18012513c  mov     qword ptr [rsp+1F8h+var_17C+4], rdi
0x180125144  mov     dword ptr [rsp+1F8h+var_17C], edi
0x180125148  mov     dword ptr [rsp+1F8h+Size], edi
0x18012514c  xorps   xmm0, xmm0
0x18012514f  movups  [rsp+1F8h+var_118], xmm0
0x180125157  xorps   xmm1, xmm1
0x18012515a  movups  [rsp+1F8h+var_E8], xmm1
0x180125162  movups  [rsp+1F8h+var_E8+0Ch], xmm1
0x18012516a  mov     [rsp+1F8h+var_158], rdi
0x180125172  mov     [r13+0], rdi
0x180125176  bts     dword ptr [rsi+15E4h], 0Bh
0x18012517e  lea     r9, [rsp+1F8h+var_160]
0x180125186  mov     r14d, 1
0x18012518c  mov     r8d, r14d
0x18012518f  mov     rdx, qword ptr [rsp+1F8h+Size+4]
0x180125194  mov     rcx, rsi
0x180125197  call    AuthzGetInfoHelper
0x18012519c  mov     [rsp+1F8h+dwErrCode], eax
0x1801251a0  mov     eax, [rsp+1F8h+dwErrCode]
0x1801251a4  test    eax, eax
0x1801251a6  jnz     loc_18012564D
0x1801251ac  lea     r9, [rsp+1F8h+var_168]
0x1801251b4  lea     ebx, [rax+2]
0x1801251b7  mov     dword ptr [rsp+1F8h+Src], ebx
0x1801251be  mov     r8d, ebx
0x1801251c1  mov     rdx, qword ptr [rsp+1F8h+Size+4]
0x1801251c6  mov     rcx, rsi
0x1801251c9  call    AuthzGetInfoHelper
0x1801251ce  mov     [rsp+1F8h+dwErrCode], eax
0x1801251d2  mov     eax, [rsp+1F8h+dwErrCode]
0x1801251d6  test    eax, eax
0x1801251d8  jnz     loc_18012564D
0x1801251de  mov     rdx, r13
0x1801251e1  mov     ecx, r14d
0x1801251e4  call    DBOpen2
0x1801251e9  test    r15, r15
0x1801251ec  jz      loc_1801252B7
0x1801251f2  cmp     [r15+18h], rdi
0x1801251f6  jz      loc_1801252B7
0x1801251fc  xorps   xmm0, xmm0
0x1801251ff  movups  [rsp+1F8h+var_88], xmm0
0x180125207  movups  [rsp+1F8h+var_78], xmm0
0x18012520f  movups  xmmword ptr [rsp+1F8h+var_68], xmm0
0x180125217  movups  xmmword ptr [rsp+1F8h+var_68+0Ch], xmm0
0x18012521f  mov     rdx, [r15]
0x180125222  mov     rcx, [r13+0]
0x180125226  call    DBFindDSName
0x18012522b  mov     [rsp+1F8h+dwErrCode], eax
0x18012522f  mov     eax, [rsp+1F8h+dwErrCode]
0x180125233  test    eax, eax
0x180125235  jnz     loc_18012564D
0x18012523b  mov     rcx, [r13+0]
0x18012523f  mov     dword ptr [rsp+1F8h+var_1C8], 3
0x180125247  mov     [rsp+1F8h+var_1D0], rdi
0x18012524c  lea     rax, [rsp+1F8h+var_88]
0x180125254  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x180125259  xor     r9d, r9d
0x18012525c  xor     r8d, r8d
0x18012525f  mov     edx, [rcx+20h]
0x180125262  call    DBGetObjectSecurityInfo
0x180125267  mov     [rsp+1F8h+dwErrCode], eax
0x18012526b  mov     eax, [rsp+1F8h+dwErrCode]
0x18012526f  test    eax, eax
0x180125271  jnz     loc_18012564D
0x180125277  lea     r9, [rsp+1F8h+Size]
0x18012527c  lea     r8, [rsp+1F8h+var_E8]
0x180125284  mov     edx, 201h
0x180125289  lea     rcx, [rsp+1F8h+var_78+8]; Src
0x180125291  call    MakeSid
0x180125296  lea     rax, [rsp+1F8h+var_E8]
0x18012529e  mov     qword ptr [rsp+1F8h+var_118], rax
0x1801252a6  mov     rax, cs:gpEnterpriseUsersSid
0x1801252ad  mov     qword ptr [rsp+1F8h+var_118+8], rax
0x1801252b5  jmp     short loc_1801252C0
0x1801252b7  mov     ebx, edi
0x1801252b9  mov     dword ptr [rsp+1F8h+Src], ebx
0x1801252c0  mov     rax, [rsp+1F8h+var_168]
0x1801252c8  mov     ecx, [rax]
0x1801252ca  inc     ecx
0x1801252cc  add     ebx, ecx
0x1801252ce  mov     [rsp+1F8h+var_180], ebx
0x1801252d2  mov     r8d, ebx
0x1801252d5  shl     r8, 3
0x1801252d9  mov     dword ptr [rsp+1F8h+var_1D0], 33805ECh
0x1801252e1  mov     [rsp+1F8h+var_1D8], edi
0x1801252e5  mov     r9d, r14d
0x1801252e8  mov     rdx, r14
0x1801252eb  mov     rcx, rsi
0x1801252ee  call    THAlloc_
0x1801252f3  mov     qword ptr [rsp+1F8h+var_170], rax
0x1801252fb  mov     eax, edi
0x1801252fd  mov     [rsp+1F8h+var_190], eax
0x180125301  mov     [rsp+1F8h+var_130], eax
0x180125308  mov     r13d, edi
0x18012530b  mov     [rsp+1F8h+var_194], edi
0x18012530f  cmp     r13d, ebx
0x180125312  jnb     loc_1801253E0
0x180125318  test    r13d, r13d
0x18012531b  jnz     short loc_18012532A
0x18012531d  mov     rax, [rsp+1F8h+var_160]
0x180125325  mov     rax, [rax]
0x180125328  jmp     short loc_180125355
0x18012532a  mov     rdx, [rsp+1F8h+var_168]
0x180125332  cmp     r13d, [rdx]
0x180125335  ja      short loc_180125345
0x180125337  lea     ecx, [r13-1]
0x18012533b  add     rcx, rcx
0x18012533e  mov     rax, [rdx+rcx*8+8]
0x180125343  jmp     short loc_180125355
0x180125345  mov     eax, r13d
0x180125348  sub     eax, [rdx]
0x18012534a  sub     eax, r14d
0x18012534d  mov     rax, qword ptr [rsp+rax*8+1F8h+var_118]
0x180125355  mov     qword ptr [rsp+1F8h+Size+4], rax
0x18012535a  mov     rcx, rax; Sid
0x18012535d  call    cs:__imp_RtlLengthSid
0x180125363  mov     dword ptr [rsp+1F8h+Size], eax
0x180125367  cmp     eax, 1Ch
0x18012536a  jbe     short loc_18012536E
0x18012536c  jmp     short loc_1801253D3
0x18012536e  mov     dword ptr [rsp+1F8h+var_1D0], 3380600h
0x180125376  mov     [rsp+1F8h+var_1D8], edi
0x18012537a  mov     r9d, r14d
0x18012537d  mov     r8d, 3Ah ; ':'
0x180125383  mov     rdx, r14
0x180125386  mov     rcx, rsi
0x180125389  call    THAlloc_
0x18012538e  mov     rbx, rax
0x180125391  mov     edx, [rsp+1F8h+var_190]
0x180125395  mov     rax, qword ptr [rsp+1F8h+var_170]
0x18012539d  mov     [rax+rdx*8], rbx
0x1801253a1  add     edx, r14d
0x1801253a4  mov     [rsp+1F8h+var_190], edx
0x1801253a8  mov     [rsp+1F8h+var_130], edx
0x1801253af  mov     dword ptr [rbx], 3Ah ; ':'
0x1801253b5  mov     r8d, dword ptr [rsp+1F8h+Size]; Size
0x1801253ba  lea     rcx, [rbx+18h]; void *
0x1801253be  mov     rdx, qword ptr [rsp+1F8h+Size+4]; Src
0x1801253c3  call    memcpy_0
0x1801253c8  mov     eax, dword ptr [rsp+1F8h+Size]
0x1801253cc  mov     [rbx+4], eax
0x1801253cf  mov     ebx, [rsp+1F8h+var_180]
0x1801253d3  add     r13d, r14d
0x1801253d6  mov     [rsp+1F8h+var_194], r13d
0x1801253db  jmp     loc_18012530F
0x1801253e0  mov     eax, [rsp+1F8h+var_190]
0x1801253e4  mov     [rsp+1F8h+var_180], eax
0x1801253e8  mov     [rsp+1F8h+var_1A0], rdi; void *
0x1801253ed  mov     [rsp+1F8h+var_1A8], rdi; __int64
0x1801253f2  mov     [rsp+1F8h+var_1B0], rdi; __int64
0x1801253f7  mov     [rsp+1F8h+var_1B8], rdi; __int64
0x1801253fc  mov     [rsp+1F8h+var_1C0], rdi; __int64
0x180125401  lea     rcx, [rsp+1F8h+var_17C+4]
0x180125409  mov     [rsp+1F8h+var_1C8], rcx; __int64
0x18012540e  lea     rcx, [rsp+1F8h+var_17C]
0x180125413  mov     [rsp+1F8h+var_1D0], rcx; __int64
0x180125418  mov     [rsp+1F8h+var_1D8], edi; int
0x18012541c  mov     r9d, 5; int
0x180125422  xor     r8d, r8d; int
0x180125425  mov     edx, eax; int
0x180125427  mov     rcx, qword ptr [rsp+1F8h+var_170]; int
0x18012542f  call    SampGetMemberships2
0x180125434  test    eax, eax
0x180125436  jz      short loc_180125449
0x180125438  mov     ecx, eax; Status
0x18012543a  call    cs:__imp_RtlNtStatusToDosError
0x180125440  mov     [rsp+1F8h+dwErrCode], eax
0x180125444  jmp     loc_180125646
0x180125449  mov     r13d, dword ptr [rsp+1F8h+var_17C]
0x18012544e  mov     eax, dword ptr [rsp+1F8h+Src]
  ... truncated ...
```
