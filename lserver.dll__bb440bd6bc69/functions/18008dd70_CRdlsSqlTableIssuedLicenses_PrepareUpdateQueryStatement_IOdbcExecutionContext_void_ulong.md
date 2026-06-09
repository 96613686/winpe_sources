# CRdlsSqlTableIssuedLicenses::PrepareUpdateQueryStatement(IOdbcExecutionContext *,void *,ulong)

- ea: `0x18008dd70`
- end: `0x18008e641`
- name: `?PrepareUpdateQueryStatement@CRdlsSqlTableIssuedLicenses@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXK@Z`
- size: `2257`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableIssuedLicenses *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180078be4`
- `0x180086778`
- `0x18008d2a8`
- `0x18008dd70`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18008e5e1`
- `msvcrt!wprintf_s` at `0x18008e5f6`
- `msvcrt!wprintf_s` at `0x18008e5e1`
- `msvcrt!wprintf_s` at `0x18008e5f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ddae`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ddae`

## string_xrefs

- `0x18008e5da`: `"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement"`
- `0x18008ddbe`: `UPDATE [Rdls].[IssuedLicense] SET `
- `0x18008e265`: `[RAMSize] = ? `
- `0x18008e252`: `, [RAMSize] = ? `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CRdlsSqlTableIssuedLicenses::PrepareUpdateQueryStatement(
        CRdlsSqlTableIssuedLicenses *this,
        struct IOdbcExecutionContext *a2,
        char *a3,
        int a4)
{
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // edi
  __int64 v13; // r8
  const unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  const unsigned __int16 *v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v24; // rdx
  __int64 v25; // r8
  const unsigned __int16 *v26; // rdx
  __int64 v27; // r8
  const unsigned __int16 *v28; // rdx
  __int64 v29; // r8
  const unsigned __int16 *v30; // rdx
  __int64 v31; // r8
  const unsigned __int16 *v32; // rdx
  __int64 v33; // r8
  const unsigned __int16 *v34; // rdx
  __int64 v35; // r8
  const unsigned __int16 *v36; // rdx
  __int64 v37; // r8
  const unsigned __int16 *v38; // rdx
  __int64 v39; // r8
  const unsigned __int16 *v40; // rdx
  __int64 v41; // r8
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rbx
  __int64 v45; // [rsp+80h] [rbp+40h] BYREF

  v45 = 0;
  v8 = 0;
  if ( !a4 )
    goto LABEL_148;
  SysFreeString(0);
  v45 = 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( aUpdateRdlsIssu[v10] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, L"UPDATE [Rdls].[IssuedLicense] SET ", v10);
  CRdlsSqlTableIssuedLicenses::InitDataSizes(this, a3);
  if ( (a4 & 0x100) != 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( aExpiredate_1[v11] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, L" [ExpireDate] = ? ", v11);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 604,
            (char *)this + 56);
    if ( v12 )
      goto LABEL_145;
    v8 = 1;
  }
  if ( (a4 & 0x800000) != 0 )
  {
    v13 = -1;
    if ( v8 )
    {
      v14 = L", [FloppyBIOS] = ? ";
      do
        ++v13;
      while ( aFloppybios_0[v13] );
    }
    else
    {
      v14 = L"[FloppyBIOS] = ? ";
      do
        ++v13;
      while ( aFloppybios[v13] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v14, v13);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            2,
            0,
            a3 + 624,
            (char *)this + 96);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x1000000) != 0 )
  {
    v15 = -1;
    if ( v8 )
    {
      v16 = L", [HarddiskSize] = ? ";
      do
        ++v15;
      while ( aHarddisksize_0[v15] );
    }
    else
    {
      v16 = L"[HarddiskSize] = ? ";
      do
        ++v15;
      while ( aHarddisksize_1[v15] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v16, v15);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            2,
            0,
            a3 + 628,
            (char *)this + 104);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 2) != 0 )
  {
    v17 = -1;
    if ( v8 )
    {
      v18 = L", [InternalKeyPackId] = ? ";
      do
        ++v17;
      while ( aInternalkeypac_1[v17] );
    }
    else
    {
      v18 = L"[InternalKeyPackId] = ? ";
      do
        ++v17;
      while ( aInternalkeypac_0[v17] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v18, v17);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 8,
            (char *)this + 24);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x80u) != 0 )
  {
    v19 = -1;
    if ( v8 )
    {
      v20 = L", [IssueDate] = ? ";
      do
        ++v19;
      while ( aIssuedate_1[v19] );
    }
    else
    {
      v20 = L"[IssueDate] = ? ";
      do
        ++v19;
      while ( aIssuedate[v19] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v20, v19);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 600,
            (char *)this + 48);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x8000000) != 0 )
  {
    v21 = -1;
    if ( v8 )
    {
      v22 = L", [LastModifyTime] = ? ";
      do
        ++v21;
      while ( aLastmodifytime_2[v21] );
    }
    else
    {
      v22 = L"[LastModifyTime] = ? ";
      do
        ++v21;
      while ( aLastmodifytime_1[v21] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v22, v21);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            12,
            5,
            0,
            a3 + 16,
            (char *)this + 40);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x100000) != 0 )
  {
    v23 = -1;
    if ( v8 )
    {
      v24 = L", [LicenseStatus] = ? ";
      do
        ++v23;
      while ( aLicensestatus_0[v23] );
    }
    else
    {
      v24 = L"[LicenseStatus] = ? ";
      do
        ++v23;
      while ( aLicensestatus_1[v23] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v24, v23);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            11,
            4,
            0,
            a3 + 608,
            (char *)this + 64);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x4000000) != 0 )
  {
    v25 = -1;
    if ( v8 )
    {
      v26 = L", [MatchHint1] = ? ";
      do
        ++v25;
      while ( aMatchhint1_2[v25] );
    }
    else
    {
      v26 = L"[MatchHint1] = ? ";
      do
        ++v25;
      while ( aMatchhint1_0[v25] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v26, v25);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            13,
            9,
            0,
            a3 + 640,
            (char *)this + 120);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x200) != 0 )
  {
    v27 = -1;
    if ( v8 )
    {
      v28 = L", [NumLicenses] = ? ";
      do
        ++v27;
      while ( aNumlicenses[v27] );
    }
    else
    {
      v28 = L"[NumLicenses] = ? ";
      do
        ++v27;
      while ( aNumlicenses_1[v27] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v28, v27);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 612,
            (char *)this + 72);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x2000000) != 0 )
  {
    v29 = -1;
    if ( v8 )
    {
      v30 = L", [RAMSize] = ? ";
      do
        ++v29;
      while ( aRamsize[v29] );
    }
    else
    {
      v30 = L"[RAMSize] = ? ";
      do
        ++v29;
      while ( aRamsize_0[v29] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v30, v29);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            2,
            0,
            a3 + 632,
            (char *)this + 112);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x200000) != 0 )
  {
    v31 = -1;
    if ( v8 )
    {
      v32 = L", [SystemBIOS] = ? ";
      do
        ++v31;
      while ( aSystembios[v31] );
    }
    else
    {
      v32 = L"[SystemBIOS] = ? ";
      do
        ++v31;
      while ( aSystembios_2[v31] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v32, v31);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            2,
            0,
            a3 + 616,
            (char *)this + 80);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x400000) != 0 )
  {
    v33 = -1;
    if ( v8 )
    {
      v34 = L", [VideoBIOS] = ? ";
      do
        ++v33;
      while ( aVideobios_1[v33] );
    }
    else
    {
      v34 = L"[VideoBIOS] = ? ";
      do
        ++v33;
      while ( aVideobios_0[v33] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v34, v33);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            2,
            0,
            a3 + 620,
            (char *)this + 88);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x20000000) != 0 )
  {
    v35 = -1;
    if ( v8 )
    {
      v36 = L", [EntryStatus] = ? ";
      do
        ++v35;
      while ( aEntrystatus_0[v35] );
    }
    else
    {
      v36 = L"[EntryStatus] = ? ";
      do
        ++v35;
      while ( aEntrystatus[v35] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v36, v35);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            11,
            4,
            0,
            a3,
            (char *)this + 8);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 0x10000000) != 0 )
  {
    v37 = -1;
    if ( v8 )
    {
      v38 = L", [KeyPackLicenseId] = ? ";
      do
        ++v37;
      while ( aKeypacklicense[v37] );
    }
    else
    {
      v38 = L"[KeyPackLicenseId] = ? ";
      do
        ++v37;
      while ( aKeypacklicense_2[v37] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v38, v37);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 12,
            (char *)this + 32);
    if ( v12 )
      goto LABEL_145;
    ++v8;
  }
  if ( (a4 & 8) == 0 )
    goto LABEL_135;
  v39 = -1;
  if ( v8 )
  {
    v40 = L", [MachineName] = ? ";
    do
      ++v39;
    while ( aMachinename_2[v39] );
  }
  else
  {
    v40 = L"[MachineName] = ? ";
    do
      ++v39;
    while ( aMachinename[v39] );
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v40, v39);
  v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
          a2,
          0,
          0,
          64,
          a3 + 24);
  if ( v12 )
  {
LABEL_145:
    wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement\"");
    wprintf_s(L" 0x%x \n", (unsigned int)v12);
    goto LABEL_146;
  }
  ++v8;
LABEL_135:
  if ( (a4 & 0x10) != 0 )
  {
    v41 = -1;
    if ( v8 )
    {
      v42 = L", [UserName] = ? ";
      do
        ++v41;
      while ( aUsername_0[v41] );
    }
    else
    {
      v42 = L"[UserName] = ? ";
      do
        ++v41;
      while ( aUsername_2[v41] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, v42, v41);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            512,
            a3 + 88);
    if ( v12 )
      goto LABEL_145;
  }
  do
    ++v9;
  while ( aWhereInternall_0[v9] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v45, L" WHERE [InternalLicenseID] = ? ", v9);
  v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
          a2,
          0,
          2,
          2,
          0,
          a3 + 4,
          (char *)this + 16);
  if ( v12 )
    goto LABEL_145;
LABEL_146:
  if ( v12 < 0 )
  {
LABEL_148:
    v43 = 0;
    goto LABEL_149;
  }
  v43 = v45;
  v45 = 0;
LABEL_149:
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v45);
  return (unsigned __int16 *)v43;
}

```

## disassembly

```asm
0x18008dd70  mov     [rsp-28h+arg_0], rbx
0x18008dd75  mov     [rsp-28h+arg_8], rsi
0x18008dd7a  mov     [rsp-28h+arg_18], rdi
0x18008dd7f  push    rbp
0x18008dd80  push    r12
0x18008dd82  push    r13
0x18008dd84  push    r14
0x18008dd86  push    r15
0x18008dd88  mov     rbp, rsp
0x18008dd8b  sub     rsp, 40h
0x18008dd8f  mov     r14d, r9d
0x18008dd92  mov     r13, r8
0x18008dd95  mov     r15, rdx
0x18008dd98  mov     r12, rcx
0x18008dd9b  xor     edi, edi
0x18008dd9d  mov     [rbp+arg_10], rdi
0x18008dda1  mov     ebx, edi
0x18008dda3  test    r9d, r9d
0x18008dda6  jz      loc_18008E613
0x18008ddac  xor     ecx, ecx; bstrString
0x18008ddae  call    cs:__imp_SysFreeString
0x18008ddb5  nop     dword ptr [rax+rax+00h]
0x18008ddba  mov     [rbp+arg_10], rdi
0x18008ddbe  lea     rdx, aUpdateRdlsIssu; "UPDATE [Rdls].[IssuedLicense] SET "
0x18008ddc5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008ddc9  mov     r8, rsi
0x18008ddcc  inc     r8; int
0x18008ddcf  cmp     [rdx+r8*2], di
0x18008ddd4  jnz     short loc_18008DDCC
0x18008ddd6  lea     rcx, [rbp+arg_10]; this
0x18008ddda  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008dddf  mov     rdx, r13; void *
0x18008dde2  mov     rcx, r12; this
0x18008dde5  call    ?InitDataSizes@CRdlsSqlTableIssuedLicenses@@AEAAXPEAX@Z; CRdlsSqlTableIssuedLicenses::InitDataSizes(void *)
0x18008ddea  bt      r14d, 8
0x18008ddef  jnb     short loc_18008DE55
0x18008ddf1  lea     rdx, aExpiredate_1; " [ExpireDate] = ? "
0x18008ddf8  mov     r8, rsi
0x18008ddfb  inc     r8; int
0x18008ddfe  cmp     [rdx+r8*2], di
0x18008de03  jnz     short loc_18008DDFB
0x18008de05  lea     rcx, [rbp+arg_10]; this
0x18008de09  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008de0e  mov     rax, [r15]
0x18008de11  lea     rcx, [r12+38h]
0x18008de16  lea     rdx, [r13+25Ch]
0x18008de1d  mov     [rsp+40h+var_10], rcx
0x18008de22  mov     [rsp+40h+var_18], rdx
0x18008de27  mov     dword ptr [rsp+40h+var_20], edi
0x18008de2b  mov     ecx, 2
0x18008de30  mov     r9d, ecx
0x18008de33  mov     r8d, ecx
0x18008de36  xor     edx, edx
0x18008de38  mov     rcx, r15
0x18008de3b  mov     rax, [rax+28h]
0x18008de3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de44  mov     edi, eax
0x18008de46  xor     eax, eax
0x18008de48  test    edi, edi
0x18008de4a  jnz     loc_18008E5DA
0x18008de50  lea     ebx, [rax+1]
0x18008de53  jmp     short loc_18008DE57
0x18008de55  xor     eax, eax
0x18008de57  bt      r14d, 17h
0x18008de5c  jnb     short loc_18008DED5
0x18008de5e  mov     r8, rsi
0x18008de61  test    ebx, ebx
0x18008de63  jz      short loc_18008DE78
0x18008de65  lea     rdx, aFloppybios_0; ", [FloppyBIOS] = ? "
0x18008de6c  inc     r8
0x18008de6f  cmp     [rdx+r8*2], ax
0x18008de74  jnz     short loc_18008DE6C
0x18008de76  jmp     short loc_18008DE89
0x18008de78  lea     rdx, aFloppybios; "[FloppyBIOS] = ? "
0x18008de7f  inc     r8; int
0x18008de82  cmp     [rdx+r8*2], ax
0x18008de87  jnz     short loc_18008DE7F
0x18008de89  lea     rcx, [rbp+arg_10]; this
0x18008de8d  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008de92  mov     rax, [r15]
0x18008de95  lea     rcx, [r12+60h]
0x18008de9a  lea     rdx, [r13+270h]
0x18008dea1  mov     [rsp+40h+var_10], rcx
0x18008dea6  mov     [rsp+40h+var_18], rdx
0x18008deab  xor     ecx, ecx
0x18008dead  mov     dword ptr [rsp+40h+var_20], ecx
0x18008deb1  xor     edx, edx
0x18008deb3  lea     r9d, [rcx+2]
0x18008deb7  lea     r8d, [rcx+1]
0x18008debb  mov     rcx, r15
0x18008debe  mov     rax, [rax+28h]
0x18008dec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dec7  mov     edi, eax
0x18008dec9  xor     eax, eax
0x18008decb  test    edi, edi
0x18008decd  jnz     loc_18008E5DA
0x18008ded3  inc     ebx
0x18008ded5  bt      r14d, 18h
0x18008deda  jnb     short loc_18008DF53
0x18008dedc  mov     r8, rsi
0x18008dedf  test    ebx, ebx
0x18008dee1  jz      short loc_18008DEF6
0x18008dee3  lea     rdx, aHarddisksize_0; ", [HarddiskSize] = ? "
0x18008deea  inc     r8
0x18008deed  cmp     [rdx+r8*2], ax
0x18008def2  jnz     short loc_18008DEEA
0x18008def4  jmp     short loc_18008DF07
0x18008def6  lea     rdx, aHarddisksize_1; "[HarddiskSize] = ? "
0x18008defd  inc     r8; int
0x18008df00  cmp     [rdx+r8*2], ax
0x18008df05  jnz     short loc_18008DEFD
0x18008df07  lea     rcx, [rbp+arg_10]; this
0x18008df0b  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008df10  mov     rax, [r15]
0x18008df13  lea     rcx, [r12+68h]
0x18008df18  lea     rdx, [r13+274h]
0x18008df1f  mov     [rsp+40h+var_10], rcx
0x18008df24  mov     [rsp+40h+var_18], rdx
0x18008df29  xor     ecx, ecx
0x18008df2b  mov     dword ptr [rsp+40h+var_20], ecx
0x18008df2f  xor     edx, edx
0x18008df31  lea     r9d, [rcx+2]
0x18008df35  lea     r8d, [rcx+1]
0x18008df39  mov     rcx, r15
0x18008df3c  mov     rax, [rax+28h]
0x18008df40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df45  mov     edi, eax
0x18008df47  xor     eax, eax
0x18008df49  test    edi, edi
0x18008df4b  jnz     loc_18008E5DA
0x18008df51  inc     ebx
0x18008df53  mov     edi, 2
0x18008df58  test    dil, r14b
0x18008df5b  jz      short loc_18008DFD2
0x18008df5d  mov     r8, rsi
0x18008df60  test    ebx, ebx
0x18008df62  jz      short loc_18008DF77
0x18008df64  lea     rdx, aInternalkeypac_1; ", [InternalKeyPackId] = ? "
0x18008df6b  inc     r8
0x18008df6e  cmp     [rdx+r8*2], ax
0x18008df73  jnz     short loc_18008DF6B
0x18008df75  jmp     short loc_18008DF88
0x18008df77  lea     rdx, aInternalkeypac_0; "[InternalKeyPackId] = ? "
0x18008df7e  inc     r8; int
0x18008df81  cmp     [rdx+r8*2], ax
0x18008df86  jnz     short loc_18008DF7E
0x18008df88  lea     rcx, [rbp+arg_10]; this
0x18008df8c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008df91  mov     rax, [r15]
0x18008df94  lea     rcx, [r12+18h]
0x18008df99  lea     rdx, [r13+8]
0x18008df9d  mov     [rsp+40h+var_10], rcx
0x18008dfa2  mov     [rsp+40h+var_18], rdx
0x18008dfa7  xor     ecx, ecx
0x18008dfa9  mov     dword ptr [rsp+40h+var_20], ecx
0x18008dfad  mov     r9d, edi
0x18008dfb0  mov     r8d, edi
0x18008dfb3  xor     edx, edx
0x18008dfb5  mov     rcx, r15
0x18008dfb8  mov     rax, [rax+28h]
0x18008dfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dfc1  mov     edi, eax
0x18008dfc3  xor     eax, eax
0x18008dfc5  test    edi, edi
0x18008dfc7  jnz     loc_18008E5DA
0x18008dfcd  inc     ebx
0x18008dfcf  lea     edi, [rax+2]
0x18008dfd2  test    r14b, r14b
0x18008dfd5  jns     short loc_18008E04C
0x18008dfd7  mov     r8, rsi
0x18008dfda  test    ebx, ebx
0x18008dfdc  jz      short loc_18008DFF1
0x18008dfde  lea     rdx, aIssuedate_1; ", [IssueDate] = ? "
0x18008dfe5  inc     r8
0x18008dfe8  cmp     [rdx+r8*2], ax
0x18008dfed  jnz     short loc_18008DFE5
0x18008dfef  jmp     short loc_18008E002
0x18008dff1  lea     rdx, aIssuedate; "[IssueDate] = ? "
0x18008dff8  inc     r8; int
0x18008dffb  cmp     [rdx+r8*2], ax
0x18008e000  jnz     short loc_18008DFF8
0x18008e002  lea     rcx, [rbp+arg_10]; this
0x18008e006  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008e00b  mov     rax, [r15]
0x18008e00e  lea     rcx, [r12+30h]
0x18008e013  lea     rdx, [r13+258h]
0x18008e01a  mov     [rsp+40h+var_10], rcx
0x18008e01f  mov     [rsp+40h+var_18], rdx
0x18008e024  xor     ecx, ecx
0x18008e026  mov     dword ptr [rsp+40h+var_20], ecx
0x18008e02a  mov     r9d, edi
0x18008e02d  mov     r8d, edi
0x18008e030  xor     edx, edx
0x18008e032  mov     rcx, r15
0x18008e035  mov     rax, [rax+28h]
0x18008e039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e03e  mov     edi, eax
0x18008e040  xor     eax, eax
0x18008e042  test    edi, edi
0x18008e044  jnz     loc_18008E5DA
0x18008e04a  inc     ebx
0x18008e04c  bt      r14d, 1Bh
0x18008e051  jnb     short loc_18008E0C7
0x18008e053  mov     r8, rsi
0x18008e056  test    ebx, ebx
0x18008e058  jz      short loc_18008E06D
0x18008e05a  lea     rdx, aLastmodifytime_2; ", [LastModifyTime] = ? "
0x18008e061  inc     r8
0x18008e064  cmp     [rdx+r8*2], ax
0x18008e069  jnz     short loc_18008E061
0x18008e06b  jmp     short loc_18008E07E
0x18008e06d  lea     rdx, aLastmodifytime_1; "[LastModifyTime] = ? "
0x18008e074  inc     r8; int
0x18008e077  cmp     [rdx+r8*2], ax
0x18008e07c  jnz     short loc_18008E074
0x18008e07e  lea     rcx, [rbp+arg_10]; this
0x18008e082  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008e087  mov     rax, [r15]
0x18008e08a  lea     rcx, [r12+28h]
0x18008e08f  lea     rdx, [r13+10h]
0x18008e093  mov     [rsp+40h+var_10], rcx
0x18008e098  mov     [rsp+40h+var_18], rdx
0x18008e09d  xor     ecx, ecx
0x18008e09f  mov     dword ptr [rsp+40h+var_20], ecx
0x18008e0a3  xor     edx, edx
0x18008e0a5  lea     r9d, [rcx+5]
0x18008e0a9  lea     r8d, [rcx+0Ch]
0x18008e0ad  mov     rcx, r15
0x18008e0b0  mov     rax, [rax+28h]
0x18008e0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e0b9  mov     edi, eax
0x18008e0bb  xor     eax, eax
0x18008e0bd  test    edi, edi
0x18008e0bf  jnz     loc_18008E5DA
0x18008e0c5  inc     ebx
0x18008e0c7  bt      r14d, 14h
0x18008e0cc  jnb     short loc_18008E145
0x18008e0ce  mov     r8, rsi
0x18008e0d1  test    ebx, ebx
0x18008e0d3  jz      short loc_18008E0E8
0x18008e0d5  lea     rdx, aLicensestatus_0; ", [LicenseStatus] = ? "
0x18008e0dc  inc     r8
0x18008e0df  cmp     [rdx+r8*2], ax
0x18008e0e4  jnz     short loc_18008E0DC
0x18008e0e6  jmp     short loc_18008E0F9
0x18008e0e8  lea     rdx, aLicensestatus_1; "[LicenseStatus] = ? "
0x18008e0ef  inc     r8; int
0x18008e0f2  cmp     [rdx+r8*2], ax
0x18008e0f7  jnz     short loc_18008E0EF
0x18008e0f9  lea     rcx, [rbp+arg_10]; this
0x18008e0fd  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008e102  mov     rax, [r15]
0x18008e105  lea     rcx, [r12+40h]
0x18008e10a  lea     rdx, [r13+260h]
0x18008e111  mov     [rsp+40h+var_10], rcx
0x18008e116  mov     [rsp+40h+var_18], rdx
0x18008e11b  xor     ecx, ecx
0x18008e11d  mov     dword ptr [rsp+40h+var_20], ecx
0x18008e121  xor     edx, edx
0x18008e123  lea     r9d, [rcx+4]
0x18008e127  lea     r8d, [rcx+0Bh]
0x18008e12b  mov     rcx, r15
0x18008e12e  mov     rax, [rax+28h]
0x18008e132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e137  mov     edi, eax
0x18008e139  xor     eax, eax
0x18008e13b  test    edi, edi
0x18008e13d  jnz     loc_18008E5DA
0x18008e143  inc     ebx
0x18008e145  bt      r14d, 1Ah
0x18008e14a  jnb     short loc_18008E1C3
0x18008e14c  mov     r8, rsi
0x18008e14f  test    ebx, ebx
0x18008e151  jz      short loc_18008E166
0x18008e153  lea     rdx, aMatchhint1_2; ", [MatchHint1] = ? "
0x18008e15a  inc     r8
0x18008e15d  cmp     [rdx+r8*2], ax
0x18008e162  jnz     short loc_18008E15A
0x18008e164  jmp     short loc_18008E177
0x18008e166  lea     rdx, aMatchhint1_0; "[MatchHint1] = ? "
0x18008e16d  inc     r8; int
0x18008e170  cmp     [rdx+r8*2], ax
0x18008e175  jnz     short loc_18008E16D
0x18008e177  lea     rcx, [rbp+arg_10]; this
0x18008e17b  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008e180  mov     rax, [r15]
0x18008e183  lea     rcx, [r12+78h]
0x18008e188  lea     rdx, [r13+280h]
0x18008e18f  mov     [rsp+40h+var_10], rcx
0x18008e194  mov     [rsp+40h+var_18], rdx
0x18008e199  xor     ecx, ecx
0x18008e19b  mov     dword ptr [rsp+40h+var_20], ecx
0x18008e19f  xor     edx, edx
0x18008e1a1  lea     r9d, [rcx+9]
0x18008e1a5  lea     r8d, [rcx+0Dh]
0x18008e1a9  mov     rcx, r15
0x18008e1ac  mov     rax, [rax+28h]
0x18008e1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1b5  mov     edi, eax
0x18008e1b7  xor     eax, eax
  ... truncated ...
```
