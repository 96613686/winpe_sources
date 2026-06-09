# CBackupSession::ScanAllEvents(void)

- ea: `0x18001fee4`
- end: `0x180021230`
- name: `?ScanAllEvents@CBackupSession@@AEAAJXZ`
- size: `4940`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021240`

## callees

- `0x180002524`
- `0x1800031e0`
- `0x1800077f0`
- `0x180007818`
- `0x180009258`
- `0x1800093a8`
- `0x1800094ec`
- `0x1800127b0`
- `0x1800128a8`
- `0x1800128fc`
- `0x180017290`
- `0x18001789c`
- `0x180017bd8`
- `0x180018778`
- `0x18001afe4`
- `0x18001baf8`
- `0x18001c714`
- `0x18001cb74`
- `0x18001eaf0`
- `0x18001f760`
- `0x18001fee4`
- `0x18002204c`
- `0x180031642`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800211df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800211df`
- `ADVAPI32!SetThreadToken` at `0x18002008a`
- `ADVAPI32!SetThreadToken` at `0x180020599`
- `ADVAPI32!SetThreadToken` at `0x180020c81`
- `ADVAPI32!SetThreadToken` at `0x18002110b`
- `ADVAPI32!SetThreadToken` at `0x18002008a`
- `ADVAPI32!SetThreadToken` at `0x180020599`
- `ADVAPI32!SetThreadToken` at `0x180020c81`
- `ADVAPI32!SetThreadToken` at `0x18002110b`
- `KERNEL32!GetLastError` at `0x180020010`
- `KERNEL32!GetLastError` at `0x180020094`
- `KERNEL32!GetLastError` at `0x1800205a3`
- `KERNEL32!GetLastError` at `0x180020c8b`
- `KERNEL32!GetLastError` at `0x180021127`
- `KERNEL32!GetLastError` at `0x180021187`
- `KERNEL32!GetLastError` at `0x180020010`
- `KERNEL32!GetLastError` at `0x180020094`
- `KERNEL32!GetLastError` at `0x1800205a3`
- `KERNEL32!GetLastError` at `0x180020c8b`
- `KERNEL32!GetLastError` at `0x180021127`
- `KERNEL32!GetLastError` at `0x180021187`
- `KERNEL32!GetCurrentThread` at `0x18001ffdc`
- `KERNEL32!GetCurrentThread` at `0x18002115d`
- `KERNEL32!GetCurrentThread` at `0x18001ffdc`
- `KERNEL32!GetCurrentThread` at `0x18002115d`
- `KERNEL32!SetThreadPriority` at `0x18001ffea`
- `KERNEL32!SetThreadPriority` at `0x18002116b`
- `KERNEL32!SetThreadPriority` at `0x18001ffea`
- `KERNEL32!SetThreadPriority` at `0x18002116b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002025d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002034a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800203d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002047a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800204e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180020554`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ae4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002101a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002025d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002034a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800203d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002047a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800204e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180020554`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ae4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002101a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210a1`
- `FHEVENTS!DpElReleaseObjects` at `0x1800211cc`
- `FHEVENTS!DpElReleaseObjects` at `0x1800211cc`
- `FHEVENTS!DpElGetNextEvent` at `0x180020dc6`
- `FHEVENTS!DpElGetNextEvent` at `0x180020dc6`
- `FHEVENTS!DpElScanEvents` at `0x180020682`
- `FHEVENTS!DpElScanEvents` at `0x1800208df`
- `FHEVENTS!DpElScanEvents` at `0x180020682`
- `FHEVENTS!DpElScanEvents` at `0x1800208df`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::ScanAllEvents(CBackupSession *this)
{
  CBackupSession *v1; // r12
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v4; // eax
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  int v10; // ebx
  PVOID *v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  char *v14; // r13
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, _QWORD, char *, _QWORD, int *); // r13
  ATL::CComBSTR *v17; // rax
  __int64 v18; // rbx
  unsigned int v19; // r13d
  ATL::CComBSTR *v20; // rax
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, int *, __int64, int *); // r13
  ATL::CComBSTR *v23; // rax
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, _QWORD, unsigned __int64 *, __int64, int *); // r13
  ATL::CComBSTR *v26; // rax
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, _QWORD, int *, __int64, int *); // r13
  ATL::CComBSTR *v29; // rax
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, _QWORD, unsigned __int64 *, __int64, int *); // r13
  ATL::CComBSTR *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  signed int v35; // eax
  unsigned __int64 v36; // rbx
  void *v37; // rbx
  int v38; // eax
  int v39; // r13d
  int v40; // edx
  int v41; // ebx
  PVOID *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rbx
  ATL::CComBSTR *v45; // rax
  __int64 v46; // r8
  _QWORD *v47; // rcx
  __int64 v48; // rbx
  ATL::CComBSTR *v49; // rax
  __int64 v50; // rbx
  ATL::CComBSTR *v51; // rax
  __int64 *v52; // rdx
  BSTR v53; // rbx
  int v54; // eax
  signed int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // r8
  unsigned int v58; // r13d
  int v59; // eax
  __int64 v60; // rdx
  int NextEvent; // eax
  int v62; // eax
  int v63; // r9d
  __int64 v64; // r9
  __int64 v65; // rcx
  __int64 v66; // rbx
  unsigned int v67; // r13d
  ATL::CComBSTR *v68; // rax
  __int64 v69; // rbx
  __int64 (__fastcall *v70)(__int64, _QWORD, int *, __int64); // r13
  ATL::CComBSTR *v71; // rax
  signed int v72; // eax
  HANDLE v73; // rax
  signed int v74; // eax
  int v76; // [rsp+30h] [rbp-188h] BYREF
  int v77; // [rsp+34h] [rbp-184h] BYREF
  BSTR v78; // [rsp+38h] [rbp-180h] BYREF
  char v79[4]; // [rsp+40h] [rbp-178h] BYREF
  int v80; // [rsp+44h] [rbp-174h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-170h] BYREF
  BSTR v82; // [rsp+50h] [rbp-168h] BYREF
  int v83; // [rsp+58h] [rbp-160h] BYREF
  unsigned __int64 v84; // [rsp+60h] [rbp-158h]
  unsigned int v85; // [rsp+68h] [rbp-150h]
  unsigned __int64 v86; // [rsp+70h] [rbp-148h] BYREF
  unsigned int v87; // [rsp+78h] [rbp-140h] BYREF
  unsigned __int64 v88; // [rsp+80h] [rbp-138h] BYREF
  int v89; // [rsp+88h] [rbp-130h]
  CBackupSession *v90; // [rsp+90h] [rbp-128h]
  OLECHAR *v91; // [rsp+98h] [rbp-120h] BYREF
  __int64 v92; // [rsp+A0h] [rbp-118h] BYREF
  void *v93; // [rsp+A8h] [rbp-110h]
  BSTR v94; // [rsp+B0h] [rbp-108h] BYREF
  _QWORD *v95; // [rsp+B8h] [rbp-100h]
  int v96; // [rsp+C4h] [rbp-F4h] BYREF
  _BYTE v97[24]; // [rsp+D0h] [rbp-E8h] BYREF
  int v98; // [rsp+E8h] [rbp-D0h]
  _QWORD v99[2]; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v100; // [rsp+100h] [rbp-B8h]
  __int64 v101; // [rsp+110h] [rbp-A8h]
  __int64 v102; // [rsp+118h] [rbp-A0h]
  __int64 v103; // [rsp+120h] [rbp-98h] BYREF
  __int64 v104; // [rsp+128h] [rbp-90h]
  char v105; // [rsp+130h] [rbp-88h]
  char v106; // [rsp+158h] [rbp-60h]
  BSTR v107[2]; // [rsp+160h] [rbp-58h] BYREF
  BSTR v108[2]; // [rsp+170h] [rbp-48h] BYREF

  v1 = this;
  v90 = this;
  v93 = 0;
  v83 = 0;
  v91 = 0;
  v87 = 0;
  v99[0] = 0;
  v99[1] = 0;
  v100 = 0;
  v101 = 10;
  v102 = 0;
  v92 = 0;
  memset(v97, 0, sizeof(v97));
  v98 = 0;
  v76 = 0;
  v80 = 0;
  v86 = 0;
  v77 = 0;
  v88 = 0;
  v89 = 0;
  memset_0(&v103, 0, 0x40u);
  v85 = *((_DWORD *)v1 + 195);
  LODWORD(v84) = *((_DWORD *)v1 + 194);
  if ( *((int *)v1 + 87) < 2 )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 0x10000)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)LastError);
    }
    v89 = 1;
  }
  v108[0] = (BSTR)((char *)v1 + 384);
  if ( !SetThreadToken(0, *((HANDLE *)v1 + 48)) )
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 100;
LABEL_15:
      v8 = (unsigned int)v5;
LABEL_16:
      WPP_SF_d(v6[2], v7, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v8);
      goto LABEL_254;
    }
    goto LABEL_254;
  }
  v9 = CBackupSession::RebuildMissingOrCorruptSearchIndex(v1);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)v9);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != -2147220479 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      WPP_SF_ss(
        (unsigned int)v11[2],
        102,
        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)"hr == FHE_E_SESSION_CANCELLED",
        (__int64)"RebuildMissingOrCorruptSearchIndex has failed");
  }
  v12 = CBackupSession::ProcessRestoreLog(v1);
  v5 = v12;
  if ( v12 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_254;
    v7 = 103;
    goto LABEL_29;
  }
  v95 = (_QWORD *)((char *)v1 + 16);
  v13 = *((_QWORD *)v1 + 2);
  v14 = (char *)v1 + 24;
  v94 = (BSTR)((char *)v1 + 24);
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 168LL))(v13, *((_QWORD *)v1 + 3));
  v5 = v12;
  if ( v12 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_254;
    v7 = 104;
    goto LABEL_29;
  }
  v82 = (BSTR)((char *)v1 + 24);
  v12 = CBackupSession::PreprocessElSyncRecords(v1);
  v5 = v12;
  if ( v12 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_254;
    v7 = 105;
    goto LABEL_29;
  }
  v79[0] = 0;
  v15 = *(_QWORD *)v14;
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, _QWORD, int *))(**(_QWORD **)v14 + 176LL);
  v17 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"EventListenerWatermarks");
  v5 = v16(v15, *(_QWORD *)v17, v79, 0, &v83);
  SysFreeString(bstrString);
  if ( v5 != -2147023728 )
  {
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v5);
      goto LABEL_254;
    }
    v93 = operator new[](v83, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v93 )
    {
      v5 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          "oldWatermarks");
      goto LABEL_254;
    }
    v18 = *(_QWORD *)v82;
    bstrString = *(BSTR *)(**(_QWORD **)v82 + 176LL);
    v19 = v83;
    v20 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v78, L"EventListenerWatermarks");
    v5 = ((__int64 (__fastcall *)(__int64, _QWORD, void *, _QWORD, int *))bstrString)(
           v18,
           *(_QWORD *)v20,
           v93,
           v19,
           &v83);
    SysFreeString(v78);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v5);
      goto LABEL_254;
    }
    v76 = 4;
    v21 = *(_QWORD *)v82;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64, int *))(**(_QWORD **)v82 + 176LL);
    v23 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ReassociationPerformed");
    LODWORD(v21) = v22(v21, *(_QWORD *)v23, &v80, 4, &v76);
    SysFreeString(bstrString);
    if ( (int)v21 < 0 || v76 != 4 )
      v80 = 0;
  }
  try
  {
    v76 = 8;
    v24 = *(_QWORD *)v82;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *, __int64, int *))(**(_QWORD **)v82 + 176LL);
    v26 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"EarliestConsecutiveElFailure");
    LODWORD(v24) = v25(v24, *(_QWORD *)v26, &v86, 8, &v76);
    SysFreeString(bstrString);
    if ( (int)v24 < 0 || v76 != 8 )
      v86 = 0;
    v76 = 4;
    v27 = *(_QWORD *)v82;
    v28 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64, int *))(**(_QWORD **)v82 + 176LL);
    v29 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ConsecutiveElFailureCount");
    LODWORD(v27) = v28(v27, *(_QWORD *)v29, &v77, 4, &v76);
    SysFreeString(bstrString);
    if ( (int)v27 < 0 || v76 != 4 )
      v77 = 0;
    v76 = 8;
    v30 = *(_QWORD *)v82;
    v31 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *, __int64, int *))(**(_QWORD **)v82 + 176LL);
    v32 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"LastFullElScan");
    LODWORD(v30) = v31(v30, *(_QWORD *)v32, &v88, 8, &v76);
    SysFreeString(bstrString);
    if ( (int)v30 < 0 || v76 != 8 )
      v88 = 0;
  }
  catch ( ATL::CAtlException v96 )
  {
    LODWORD(v78) = v96;
    if ( v96 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v96);
      v5 = (int)v78;
      goto LABEL_254;
    }
    v1 = v90;
  }
  if ( SetThreadToken(0, *((HANDLE *)v1 + 49)) )
  {
    LODWORD(bstrString) = 0;
    v36 = (unsigned int)v84 + ((unsigned __int64)v85 << 32);
    v84 = v36;
    if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v33, UsnJournalScanStart, v34, 1, v107);
    if ( (*((_DWORD *)v1 + 86) & 0x10000000) != 0 )
    {
      if ( !v80 )
      {
        v42 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
          v42 = (PVOID *)WPP_GLOBAL_Control;
        }
        v39 = -2147220992;
        goto LABEL_97;
      }
    }
    else if ( !v80 )
    {
      v37 = v93;
      *((_DWORD *)v1 + 210) |= v93 == 0;
      v38 = DpElScanEvents(*v95, v37, (char *)v1 + 160, &v92, &v91, &v87);
      v39 = v38;
      if ( v37 )
      {
        v40 = v77;
        v41 = 0;
      }
      else
      {
        if ( v38 == -2147220987 )
        {
          v40 = v77;
          v42 = (PVOID *)WPP_GLOBAL_Control;
          v41 = 0;
          goto LABEL_102;
        }
        v86 = 0;
        v40 = 0;
        v77 = 0;
        v88 = v84;
        v41 = 1;
      }
      v42 = (PVOID *)WPP_GLOBAL_Control;
      if ( v38 == -2147220987 )
      {
LABEL_102:
        if ( !v39 )
          goto LABEL_112;
        if ( v40 >= 3 )
        {
          (*(void (__fastcall **)(CBackupSession *, _QWORD, _QWORD))(*(_QWORD *)v1 + 104LL))(
            v1,
            (unsigned int)v39,
            (unsigned int)v40);
          v40 = v77;
          v42 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v39 != -2147220992 && (unsigned int)(v39 + 2147220989) > 1 )
        {
LABEL_112:
          if ( (int)(v39 + 0x80000000) < 0 || v39 == -2147220987 || *((_QWORD *)v1 + 54) != -1 )
          {
            if ( v40 < 10 || (v34 = 0xC92A69BFFFLL, v84 - v86 <= 0xC92A69BFFFLL) || v84 - v88 <= 0x25B7F3D3FFFLL )
            {
              v85 = 0;
              if ( ((v39 + 0x80000000) & 0x80000000) != 0
                || v39 == -2147220987
                || v42 == &WPP_GLOBAL_Control
                || (*((_BYTE *)v42 + 28) & 2) == 0 )
              {
                goto LABEL_141;
              }
              WPP_SF_d(v42[2], 119, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, (unsigned int)v39);
              goto LABEL_140;
            }
          }
        }
        v85 = 1;
        switch ( v39 )
        {
          case -2147220992:
            if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
            {
              v43 = 114;
LABEL_129:
              WPP_SF_(v42[2], v43, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
            }
            break;
          case -2147220988:
            if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
              WPP_SF_(v42[2], 115, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
            LODWORD(bstrString) = 1;
            break;
          case -2147220989:
            if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
            {
              v43 = 116;
              goto LABEL_129;
            }
            break;
          default:
            if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
            {
              v43 = 117;
              goto LABEL_129;
            }
            break;
        }
        *((_DWORD *)v1 + 210) = 1;
        v39 = DpElScanEvents(*v95, 0, (char *)v1 + 160, &v92, &v91, &v87);
        if ( v39 != -2147220987 )
        {
          v86 = 0;
          v77 = 0;
          v88 = v84;
          v41 = 1;
          if ( v39 < 0 )
          {
            v42 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                118,
                &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                (unsigned int)v39);
              LODWORD(v84) = v39;
              goto LABEL_142;
            }
LABEL_141:
            LODWORD(v84) = v39;
            if ( !v41 )
            {
              v53 = v94;
              goto LABEL_170;
            }
LABEL_142:
            v44 = *(_QWORD *)v82;
            v78 = *(BSTR *)(**(_QWORD **)v82 + 168LL);
            v45 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v107, L"EarliestConsecutiveElFailure");
            v5 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int64 *, __int64))v78)(
                   v44,
                   *(_QWORD *)v45,
                   &v86,
                   8);
            SysFreeString(v107[0]);
            if ( v5 < 0 )
            {
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  120,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v5);
LABEL_158:
              if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) == 0 )
                goto LABEL_254;
              v52 = UsnJournalScanStop;
LABEL_160:
              McGenEventWrite_EventWriteTransfer(v47, v52, v46, 1, v108);
              goto LABEL_254;
            }
            v48 = *(_QWORD *)v82;
            v107[0] = *(BSTR *)(**(_QWORD **)v82 + 168LL);
            v49 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v78, L"ConsecutiveElFailureCount");
            v5 = ((__int64 (__fastcall *)(__int64, _QWORD, int *, __int64))v107[0])(v48, *(_QWORD *)v49, &v77, 4);
            SysFreeString(v78);
            if ( v5 < 0 )
            {
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  121,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v5);
              goto LABEL_158;
            }
            v50 = *(_QWORD *)v82;
            v107[0] = *(BSTR *)(**(_QWORD **)v82 + 168LL);
            v51 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v82, L"LastFullElScan");
            v5 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int64 *, __int64))v107[0])(
                   v50,
                   *(_QWORD *)v51,
                   &v88,
                   8);
            SysFreeString(v82);
            if ( v5 < 0 )
            {
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  122,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v5);
              goto LABEL_158;
            }
            v53 = v94;
            v54 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v94 + 56LL))(*(_QWORD *)v94, 0);
            if ( v54 >= 0 )
              goto LABEL_168;
            v42 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  124,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v54);
                v42 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 4) != 0 )
              {
                WPP_SF_ss(
                  (unsigned int)v42[2],
                  125,
                  (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)"FALSE",
                  (__int64)"IFhCatalog::Save has failed unexpectedly");
LABEL_168:
                v42 = (PVOID *)WPP_GLOBAL_Control;
              }
            }
LABEL_170:
            if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
            {
              McGenEventWrite_EventWriteTransfer(v42, UsnJournalScanStop, v34, 1, v107);
              v42 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v39 == -2147220987 )
            {
              if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
                WPP_SF_(v42[2], 126, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
              v5 = -2147220479;
              goto LABEL_254;
            }
            if ( v39 < 0 )
            {
              v5 = v39;
              goto LABEL_254;
            }
            *((_DWORD *)v1 + 38) = 1;
            if ( !SetThreadToken(0, *(HANDLE *)v108[0]) )
            {
              v55 = GetLastError();
              v5 = v55;
              if ( v55 > 0 )
                v5 = (unsigned __int16)v55 | 0x80070000;
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v7 = 127;
                goto LABEL_15;
              }
              goto LABEL_254;
            }
            v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v95 + 176LL))(*v95, *(_QWORD *)v53);
            v5 = v12;
            if ( v12 < 0 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_254;
              v7 = 128;
LABEL_29:
              v8 = (unsigned int)v12;
              goto LABEL_16;
            }
            if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
              McGenEventWrite_EventWriteTransfer(v56, UsnEventProcessingStart, v57, 1, v108);
            v58 = v85;
            if ( v85 )
            {
              v59 = CBackupSession::EnumerateVisibleFiles(v1, v99, (unsigned int)(*((_DWORD *)v1 + 11) - 1));
              v5 = v59;
              if ( v59 >= 0 )
              {
                v59 = CBackupSession::EnumeratePendingBackupFiles((__int64)v1, (__int64)v99);
                v5 = v59;
                if ( v59 >= 0 )
                  goto LABEL_199;
                v47 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v60 = 130;
LABEL_235:
                  v64 = (unsigned int)v59;
LABEL_236:
                  WPP_SF_d(v47[2], v60, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v64);
                }
              }
              else
              {
                v47 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v60 = 129;
                  goto LABEL_235;
                }
              }
            }
            else
            {
LABEL_199:
              while ( 1 )
              {
                NextEvent = DpElGetNextEvent(v92, &v103);
                if ( NextEvent < 0 )
                  break;
                if ( *((_DWORD *)v1 + 40) )
                {
                  v47 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
                  v5 = -2147220479;
                  goto LABEL_237;
                }
                if ( v58 )
                {
                  v62 = CBackupSession::ProcessSingleFileEventOnWrap(v1, (struct _DPEL_EVENT *)&v103);
                }
                else if ( (v106 & 0x10) != 0 )
                {
                  v62 = CBackupSession::ProcessSingleDirEvent(v1, (struct _DPEL_EVENT *)&v103);
                }
                else
                {
                  v62 = CBackupSession::ProcessSingleFileEvent(v1, &v103, (__int64)v97);
                }
                v5 = v62;
                if ( v62 < 0 )
                {
                  v47 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v63 = v103;
                    if ( (v105 & 8) != 0 )
                      v63 = v104;
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      132,
                      (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                      v63,
                      v62);
                  }
                  goto LABEL_237;
                }
              }
              v5 = 0;
              if ( NextEvent != -2147220990 )
                v5 = NextEvent;
              if ( v5 >= 0 )
              {
                if ( v58 )
                {
                  v59 = CBackupSession::FinalizeUntouchedItems(v1, v99, *((unsigned int *)v1 + 11));
                  v5 = v59;
                  if ( v59 < 0 )
                  {
                    v47 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v60 = 134;
                      goto LABEL_235;
                    }
                    goto LABEL_237;
                  }
                }
                else
                {
                  v59 = CBackupSession::ActivateQueuedNamespaceRecords(v1, v97);
                  v5 = v59;
                  if ( v59 < 0 )
                  {
                    v47 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v60 = 135;
                      goto LABEL_235;
                    }
                    goto LABEL_237;
                  }
                }
                v59 = CBackupSession::CleanupElSyncRecords(v1);
                v5 = v59;
                if ( v59 >= 0 )
                {
                  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
                    McGenEventWrite_EventWriteTransfer(v65, UsnEventProcessingStop, v46, 1, v108);
                  v66 = *((_QWORD *)v1 + 3);
                  v107[0] = *(BSTR *)(*(_QWORD *)v66 + 168LL);
                  v67 = v87;
                  v108[0] = v91;
                  v68 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v94, L"EventListenerWatermarks");
                  v5 = ((__int64 (__fastcall *)(__int64, _QWORD, BSTR, _QWORD))v107[0])(
                         v66,
                         *(_QWORD *)v68,
                         v108[0],
                         v67);
                  SysFreeString(v94);
                  if ( v5 >= 0 )
                  {
                    if ( v80
                      && (v80 = 0,
                          v69 = *((_QWORD *)v1 + 3),
                          v70 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64))(*(_QWORD *)v69 + 168LL),
                          v71 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v108, L"ReassociationPerformed"),
                          v5 = v70(v69, *(_QWORD *)v71, &v80, 4),
                          SysFreeString(v108[0]),
                          v5 < 0) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          138,
                          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                          (unsigned int)v5);
                    }
                    else
                    {
                      *((_DWORD *)v1 + 38) = 0;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      137,
                      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                      (unsigned int)v5);
                  }
                  goto LABEL_254;
                }
                v47 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v60 = 136;
                  goto LABEL_235;
                }
                goto LABEL_237;
              }
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v60 = 133;
                v64 = (unsigned int)v5;
                goto LABEL_236;
              }
            }
LABEL_237:
            if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) == 0 )
              goto LABEL_254;
            v52 = UsnEventProcessingStop;
            goto LABEL_160;
          }
        }
LABEL_140:
        v42 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_141;
      }
      if ( v38 >= 0 )
      {
        if ( v40 <= 0 )
          goto LABEL_102;
        v86 = 0;
        v40 = 0;
        goto LABEL_101;
      }
      v36 = v84;
LABEL_98:
      if ( !v40 )
        v86 = v36;
      ++v40;
LABEL_101:
      v41 = 1;
      v77 = v40;
      goto LABEL_102;
    }
    v42 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v42 = (PVOID *)WPP_GLOBAL_Control;
    }
    v39 = -2147220988;
LABEL_97:
    v40 = v77;
    goto LABEL_98;
  }
  v35 = GetLastError();
  v5 = v35;
  if ( v35 > 0 )
    v5 = (unsigned __int16)v35 | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 111;
    goto LABEL_15;
  }
LABEL_254:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v72 = GetLastError();
    if ( v72 > 0 )
      v72 = (unsigned __int16)v72 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      140,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v72);
  }
  if ( v89 )
  {
    v73 = GetCurrentThread();
    if ( !SetThreadPriority(v73, 0x20000)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v74 = GetLastError();
      if ( v74 > 0 )
        v74 = (unsigned __int16)v74 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)v74);
    }
  }
  DpElReleaseObjects(&v92, &v91, &v103);
  if ( v93 )
    operator delete[](v93);
  ATL::CAtlArray<long,ATL::CElementTraits<long>>::~CAtlArray<long,ATL::CElementTraits<long>>(v97);
  ATL::CRBTree<long,int,ATL::CElementTraits<long>,ATL::CElementTraits<int>>::~CRBTree<long,int,ATL::CElementTraits<long>,ATL::CElementTraits<int>>(v99);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001fee4  mov     r11, rsp
0x18001fee7  mov     [r11+10h], rbx
0x18001feeb  mov     [r11+18h], rsi
0x18001feef  push    rdi
0x18001fef0  push    r12
0x18001fef2  push    r13
0x18001fef4  push    r14
0x18001fef6  push    r15
0x18001fef8  sub     rsp, 190h
0x18001feff  mov     rax, cs:__security_cookie
0x18001ff06  xor     rax, rsp
0x18001ff09  mov     [rsp+1B8h+var_38], rax
0x18001ff11  mov     r12, rcx
0x18001ff14  mov     [rsp+1B8h+var_128], rcx
0x18001ff1c  xor     edi, edi
0x18001ff1e  mov     [rsp+1B8h+var_110], rdi
0x18001ff26  mov     [rsp+1B8h+var_160], edi
0x18001ff2a  mov     [r11-120h], rdi
0x18001ff31  mov     [rsp+1B8h+var_140], edi
0x18001ff35  mov     [r11-0C8h], rdi
0x18001ff3c  mov     [r11-0C0h], rdi
0x18001ff43  xorps   xmm0, xmm0
0x18001ff46  movdqu  [rsp+1B8h+var_B8], xmm0
0x18001ff4f  mov     qword ptr [r11-0A8h], 0Ah
0x18001ff5a  mov     [r11-0A0h], rdi
0x18001ff61  mov     [r11-118h], rdi
0x18001ff68  mov     [r11-0E8h], rdi
0x18001ff6f  mov     [r11-0E0h], rdi
0x18001ff76  mov     [r11-0D8h], rdi
0x18001ff7d  mov     [rsp+1B8h+var_D0], edi
0x18001ff84  mov     [rsp+1B8h+var_188], edi
0x18001ff88  mov     [rsp+1B8h+var_174], edi
0x18001ff8c  mov     [rsp+1B8h+var_148], rdi
0x18001ff91  mov     [rsp+1B8h+var_184], edi
0x18001ff95  mov     [r11-138h], rdi
0x18001ff9c  mov     [rsp+1B8h+var_130], edi
0x18001ffa3  xor     edx, edx; Val
0x18001ffa5  lea     r8d, [rdi+40h]; Size
0x18001ffa9  lea     rcx, [r11-98h]; void *
0x18001ffb0  call    memset_0
0x18001ffb5  mov     eax, [r12+30Ch]
0x18001ffbd  mov     [rsp+1B8h+var_150], eax
0x18001ffc1  mov     eax, [r12+308h]
0x18001ffc9  mov     dword ptr [rsp+1B8h+var_158], eax
0x18001ffcd  cmp     dword ptr [r12+15Ch], 2
0x18001ffd6  jge     loc_180020062
0x18001ffdc  call    cs:__imp_GetCurrentThread
0x18001ffe2  mov     rcx, rax; hThread
0x18001ffe5  mov     edx, 10000h; nPriority
0x18001ffea  call    cs:__imp_SetThreadPriority
0x18001fff0  test    eax, eax
0x18001fff2  jnz     short loc_180020046
0x18001fff4  lea     r14, WPP_GLOBAL_Control
0x18001fffb  mov     rax, cs:WPP_GLOBAL_Control
0x180020002  lea     esi, [rdi+1]
0x180020005  cmp     rax, r14
0x180020008  jz      short loc_180020052
0x18002000a  test    [rax+1Ch], sil
0x18002000e  jz      short loc_180020052
0x180020010  call    cs:__imp_GetLastError
0x180020016  test    eax, eax
0x180020018  jle     short loc_180020022
0x18002001a  movzx   eax, ax
0x18002001d  or      eax, 80070000h
0x180020022  mov     edx, 63h ; 'c'
0x180020027  mov     r9d, eax
0x18002002a  lea     r15, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180020031  mov     r8, r15
0x180020034  mov     rcx, cs:WPP_GLOBAL_Control
0x18002003b  mov     rcx, [rcx+10h]
0x18002003f  call    WPP_SF_d
0x180020044  jmp     short loc_180020059
0x180020046  lea     r14, WPP_GLOBAL_Control
0x18002004d  mov     esi, 1
0x180020052  lea     r15, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180020059  mov     [rsp+1B8h+var_130], esi
0x180020060  jmp     short loc_180020075
0x180020062  lea     r14, WPP_GLOBAL_Control
0x180020069  mov     esi, 1
0x18002006e  lea     r15, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180020075  lea     rdx, [r12+180h]
0x18002007d  mov     [rsp+1B8h+var_48], rdx
0x180020085  mov     rdx, [rdx]; Token
0x180020088  xor     ecx, ecx; Thread
0x18002008a  call    cs:__imp_SetThreadToken
0x180020090  test    eax, eax
0x180020092  jnz     short loc_1800200DC
0x180020094  call    cs:__imp_GetLastError
0x18002009a  mov     ebx, eax
0x18002009c  test    eax, eax
0x18002009e  jle     short loc_1800200A9
0x1800200a0  movzx   ebx, ax
0x1800200a3  or      ebx, 80070000h
0x1800200a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200b0  cmp     rcx, r14
0x1800200b3  jz      loc_180021107
0x1800200b9  test    [rcx+1Ch], sil
0x1800200bd  jz      loc_180021107
0x1800200c3  mov     edx, 64h ; 'd'
0x1800200c8  mov     r9d, ebx
0x1800200cb  mov     r8, r15
0x1800200ce  mov     rcx, [rcx+10h]
0x1800200d2  call    WPP_SF_d
0x1800200d7  jmp     loc_180021107
0x1800200dc  mov     rcx, r12; this
0x1800200df  call    ?RebuildMissingOrCorruptSearchIndex@CBackupSession@@AEAAJXZ; CBackupSession::RebuildMissingOrCorruptSearchIndex(void)
0x1800200e4  mov     ebx, eax
0x1800200e6  test    eax, eax
0x1800200e8  jns     short loc_18002014E
0x1800200ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200f1  cmp     rcx, r14
0x1800200f4  jz      short loc_180020117
0x1800200f6  test    [rcx+1Ch], sil
0x1800200fa  jz      short loc_180020117
0x1800200fc  mov     edx, 65h ; 'e'
0x180020101  mov     r9d, eax
0x180020104  mov     r8, r15
0x180020107  mov     rcx, [rcx+10h]
0x18002010b  call    WPP_SF_d
0x180020110  mov     rcx, cs:WPP_GLOBAL_Control
0x180020117  cmp     ebx, 80040401h
0x18002011d  jz      short loc_18002014E
0x18002011f  cmp     rcx, r14
0x180020122  jz      short loc_18002014E
0x180020124  test    byte ptr [rcx+1Ch], 4
0x180020128  jz      short loc_18002014E
0x18002012a  mov     edx, 66h ; 'f'
0x18002012f  lea     rax, aRebuildmissing; "RebuildMissingOrCorruptSearchIndex has "...
0x180020136  mov     [rsp+1B8h+var_198], rax
0x18002013b  lea     r9, aHrFheESessionC; "hr == FHE_E_SESSION_CANCELLED"
0x180020142  mov     r8, r15
0x180020145  mov     rcx, [rcx+10h]
0x180020149  call    WPP_SF_ss
0x18002014e  mov     rcx, r12; this
0x180020151  call    ?ProcessRestoreLog@CBackupSession@@AEAAJXZ; CBackupSession::ProcessRestoreLog(void)
0x180020156  mov     ebx, eax
0x180020158  test    eax, eax
0x18002015a  jns     short loc_180020183
0x18002015c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020163  cmp     rcx, r14
0x180020166  jz      loc_180021107
0x18002016c  test    [rcx+1Ch], sil
0x180020170  jz      loc_180021107
0x180020176  mov     edx, 67h ; 'g'
0x18002017b  mov     r9d, eax
0x18002017e  jmp     loc_1800200CB
0x180020183  lea     rax, [r12+10h]
0x180020188  mov     [rsp+1B8h+var_100], rax
0x180020190  mov     rcx, [rax]
0x180020193  lea     r13, [r12+18h]
0x180020198  mov     [rsp+1B8h+var_108], r13
0x1800201a0  mov     rax, [rcx]
0x1800201a3  mov     rdx, [r13+0]
0x1800201a7  mov     rax, [rax+0A8h]
0x1800201ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201b3  mov     ebx, eax
0x1800201b5  test    eax, eax
0x1800201b7  jns     short loc_1800201DA
0x1800201b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201c0  cmp     rcx, r14
0x1800201c3  jz      loc_180021107
0x1800201c9  test    [rcx+1Ch], sil
0x1800201cd  jz      loc_180021107
0x1800201d3  mov     edx, 68h ; 'h'
0x1800201d8  jmp     short loc_18002017B
0x1800201da  mov     [rsp+1B8h+var_168], r13
0x1800201df  mov     rcx, r12; this
0x1800201e2  call    ?PreprocessElSyncRecords@CBackupSession@@AEAAJXZ; CBackupSession::PreprocessElSyncRecords(void)
0x1800201e7  mov     ebx, eax
0x1800201e9  test    eax, eax
0x1800201eb  jns     short loc_180020211
0x1800201ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201f4  cmp     rcx, r14
0x1800201f7  jz      loc_180021107
0x1800201fd  test    [rcx+1Ch], sil
0x180020201  jz      loc_180021107
0x180020207  mov     edx, 69h ; 'i'
0x18002020c  jmp     loc_18002017B
0x180020211  mov     [rsp+1B8h+var_178], dil
0x180020216  mov     rbx, [r13+0]
0x18002021a  mov     rax, [rbx]
0x18002021d  mov     r13, [rax+0B0h]
0x180020224  lea     rdx, aEventlistenerw; "EventListenerWatermarks"
0x18002022b  lea     rcx, [rsp+1B8h+bstrString]; this
0x180020230  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180020235  nop
0x180020236  lea     rcx, [rsp+1B8h+var_160]
0x18002023b  mov     [rsp+1B8h+var_198], rcx
0x180020240  xor     r9d, r9d
0x180020243  lea     r8, [rsp+1B8h+var_178]
0x180020248  mov     rdx, [rax]
0x18002024b  mov     rcx, rbx
0x18002024e  mov     rax, r13
0x180020251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020256  mov     ebx, eax
0x180020258  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18002025d  call    cs:__imp_SysFreeString
0x180020263  cmp     ebx, 80070490h
0x180020269  jz      loc_1800203EB
0x18002026f  test    ebx, ebx
0x180020271  jns     short loc_18002029F
0x180020273  mov     rcx, cs:WPP_GLOBAL_Control
0x18002027a  cmp     rcx, r14
0x18002027d  jz      short loc_18002029A
0x18002027f  test    [rcx+1Ch], sil
0x180020283  jz      short loc_18002029A
0x180020285  mov     edx, 6Ah ; 'j'
0x18002028a  mov     r9d, ebx
0x18002028d  mov     r8, r15
0x180020290  mov     rcx, [rcx+10h]
0x180020294  call    WPP_SF_d
0x180020299  nop
0x18002029a  jmp     loc_180021107
0x18002029f  movsxd  rcx, [rsp+1B8h+var_160]; unsigned __int64
0x1800202a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800202ab  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800202b0  mov     [rsp+1B8h+var_110], rax
0x1800202b8  test    rax, rax
0x1800202bb  jnz     short loc_1800202F0
0x1800202bd  mov     ebx, 8007000Eh
0x1800202c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202c9  cmp     rcx, r14
0x1800202cc  jz      short loc_1800202EB
0x1800202ce  test    [rcx+1Ch], sil
0x1800202d2  jz      short loc_1800202EB
0x1800202d4  lea     edx, [rax+6Bh]
0x1800202d7  lea     r9, aOldwatermarks; "oldWatermarks"
0x1800202de  mov     r8, r15
0x1800202e1  mov     rcx, [rcx+10h]
0x1800202e5  call    WPP_SF_s
0x1800202ea  nop
0x1800202eb  jmp     loc_180021107
0x1800202f0  mov     rbx, [rsp+1B8h+var_168]
0x1800202f5  mov     rbx, [rbx]
0x1800202f8  mov     rax, [rbx]
0x1800202fb  mov     rax, [rax+0B0h]
0x180020302  mov     [rsp+1B8h+bstrString], rax
0x180020307  mov     r13d, [rsp+1B8h+var_160]
0x18002030c  lea     rdx, aEventlistenerw; "EventListenerWatermarks"
0x180020313  lea     rcx, [rsp+1B8h+var_180]; this
0x180020318  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002031d  nop
0x18002031e  lea     rcx, [rsp+1B8h+var_160]
0x180020323  mov     [rsp+1B8h+var_198], rcx
0x180020328  mov     r9d, r13d
0x18002032b  mov     r8, [rsp+1B8h+var_110]
0x180020333  mov     rdx, [rax]
0x180020336  mov     rcx, rbx
0x180020339  mov     rax, [rsp+1B8h+bstrString]
0x18002033e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020343  mov     ebx, eax
0x180020345  mov     rcx, [rsp+1B8h+var_180]; bstrString
0x18002034a  call    cs:__imp_SysFreeString
0x180020350  test    ebx, ebx
0x180020352  jns     short loc_180020380
0x180020354  mov     rcx, cs:WPP_GLOBAL_Control
0x18002035b  cmp     rcx, r14
0x18002035e  jz      short loc_18002037B
0x180020360  test    [rcx+1Ch], sil
0x180020364  jz      short loc_18002037B
0x180020366  mov     edx, 6Ch ; 'l'
0x18002036b  mov     r9d, ebx
0x18002036e  mov     r8, r15
0x180020371  mov     rcx, [rcx+10h]
0x180020375  call    WPP_SF_d
0x18002037a  nop
0x18002037b  jmp     loc_180021107
0x180020380  mov     [rsp+1B8h+var_188], 4
0x180020388  mov     rax, [rsp+1B8h+var_168]
0x18002038d  mov     rbx, [rax]
0x180020390  mov     rax, [rbx]
0x180020393  mov     r13, [rax+0B0h]
0x18002039a  lea     rdx, Value; "ReassociationPerformed"
0x1800203a1  lea     rcx, [rsp+1B8h+bstrString]; this
0x1800203a6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800203ab  nop
0x1800203ac  lea     rcx, [rsp+1B8h+var_188]
0x1800203b1  mov     [rsp+1B8h+var_198], rcx
0x1800203b6  mov     r9d, 4
0x1800203bc  lea     r8, [rsp+1B8h+var_174]
0x1800203c1  mov     rdx, [rax]
0x1800203c4  mov     rcx, rbx
0x1800203c7  mov     rax, r13
0x1800203ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203cf  mov     ebx, eax
0x1800203d1  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x1800203d6  call    cs:__imp_SysFreeString
0x1800203dc  test    ebx, ebx
0x1800203de  js      short loc_1800203E7
0x1800203e0  cmp     [rsp+1B8h+var_188], 4
0x1800203e5  jz      short loc_1800203EB
0x1800203e7  mov     [rsp+1B8h+var_174], edi
0x1800203eb  jmp     short loc_180020424
0x1800203ed  xor     edi, edi
0x1800203ef  lea     r14, WPP_GLOBAL_Control
0x1800203f6  lea     esi, [rdi+1]
0x1800203f9  lea     r15, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180020400  mov     ebx, dword ptr [rsp+1B8h+var_180]
0x180020404  jmp     loc_180021107
0x180020409  xor     edi, edi
  ... truncated ...
```
