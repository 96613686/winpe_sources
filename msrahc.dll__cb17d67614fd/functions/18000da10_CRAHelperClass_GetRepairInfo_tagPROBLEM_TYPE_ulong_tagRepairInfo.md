# CRAHelperClass::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x18000da10`
- end: `0x18000e001`
- name: `?GetRepairInfo@CRAHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `1521`
- prototype: `__int64 __fastcall(CRAHelperClass *this, const struct _EVENT_DESCRIPTOR *, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000da10`
- `0x18000f248`
- `0x18000f420`
- `0x180010718`
- `0x1800114d0`
- `0x180011874`
- `0x180011a04`
- `0x18001223c`
- `0x180014660`
- `0x180017ac4`
- `0x180017d20`
- `0x180018bf8`
- `0x180018d1c`
- `0x180018d88`
- `0x18001919c`
- `0x180019ae0`
- `0x18001a5a2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de85`

## string_xrefs

- `0x18000da55`: `CRAHelperClass::GetRepairInfo`
- `0x18000df00`: `CRAHelperClass::GetRepairInfo`
- `0x18000df38`: `CRAHelperClass::GetRepairInfo`
- `0x18000df6c`: `CRAHelperClass::GetRepairInfo`
- `0x18000dfad`: `CRAHelperClass::GetRepairInfo`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::GetRepairInfo(
        CRAHelperClass *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  unsigned int *v5; // r15
  unsigned int v7; // r9d
  unsigned int v9; // edi
  __int64 v10; // r8
  __int64 v11; // xmm0_8
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r8
  signed int v15; // eax
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  CEventLogger *v17; // rcx
  signed int v18; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  __int64 v21; // rax
  struct _GUID v22; // xmm0
  signed int v23; // eax
  const struct _EVENT_DESCRIPTOR *v24; // rdx
  CEventLogger *v25; // rcx
  unsigned int v26; // r13d
  __int64 v27; // rdx
  __int128 v28; // kr00_16
  __int128 v29; // kr10_16
  __int64 v30; // rbx
  struct tagRepairInfo *v31; // rsi
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  LPWSTR pwszDescription; // rcx
  signed int v36; // eax
  const struct _EVENT_DESCRIPTOR *v37; // rdx
  CEventLogger *v38; // rcx
  const struct _EVENT_DESCRIPTOR *v39; // rdx
  const unsigned __int16 *v40; // rdi
  int v41; // r12d
  CEventLogger *v42; // rcx
  signed int v43; // eax
  const struct _EVENT_DESCRIPTOR *v44; // rdx
  CEventLogger *v45; // rcx
  DiagnosisTextBuilderImpl *v46; // r15
  struct tagRepairInfo *v47; // rsi
  signed int v48; // eax
  signed int XML; // eax
  const struct _EVENT_DESCRIPTOR *v50; // rdx
  LPWSTR v51; // rcx
  __int64 v52; // r8
  void *v53; // rbx
  int v54; // eax
  unsigned int v55; // r9d
  int v56; // [rsp+20h] [rbp-B9h]
  int v57; // [rsp+38h] [rbp-A1h]
  DiagnosisTextBuilderImpl *v58; // [rsp+40h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-91h] BYREF
  unsigned int *v60; // [rsp+50h] [rbp-89h]
  struct tagRepairInfo **v61; // [rsp+58h] [rbp-81h]
  struct _GUID v62[13]; // [rsp+60h] [rbp-79h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v61 = a4;
  v5 = a3;
  v60 = a3;
  if ( !a3 )
  {
    v7 = 1100;
LABEL_3:
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      v7,
      L"CRAHelperClass::GetRepairInfo",
      0x80070057);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    v7 = 1101;
    goto LABEL_3;
  }
  v9 = 0;
  v62[0].Data1 = 0;
  memset_0(&v62[0].Data2, 0, 0x9Cu);
  LODWORD(pv) = 1;
  LODWORD(v58) = 1;
  if ( !*((_DWORD *)this + 34) )
  {
    v62[0].Data1 = -1227837850;
    v11 = *(__int64 *)((char *)&ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT + 4);
    v12 = -1911212279;
LABEL_10:
    v13 = 1;
    *(_DWORD *)&v62[0].Data4[4] = v12;
    *(_QWORD *)&v62[0].Data2 = v11;
    goto LABEL_11;
  }
  v13 = 0;
  if ( !*((_DWORD *)this + 35) )
  {
    v62[0].Data1 = -670846457;
    v11 = *(__int64 *)((char *)&ID_RA_LOWH_REPAIR_SYSSETTING_DISABLED + 4);
    v12 = 751099042;
    goto LABEL_10;
  }
LABEL_11:
  if ( !*((_DWORD *)this + 39) || !*((_DWORD *)this + 37) )
    v62[v13++] = (struct _GUID)ID_RA_LOWH_REPAIR_FIREWALL_DISABLED;
  if ( *((_DWORD *)this + 56) == 2 )
    v62[v13++] = (struct _GUID)ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC;
  if ( *((_DWORD *)this + 85) == 1 )
    v62[v13++] = (struct _GUID)ID_RA_LOWH_REPAIR_IP_ADDRESS_CHANGED;
  if ( *((_DWORD *)this + 41) )
    goto LABEL_33;
  if ( (unsigned int)IsFWProfilePublic() )
  {
    LogRAProblem(1006, 1, v14);
    v22 = (struct _GUID)ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT;
  }
  else
  {
    v15 = IsBuiltInRuleEnabled(0x8103u, (int *)&pv);
    v9 = v15;
    if ( v15 < 0 )
    {
      CEventLogger::LogError(
        v17,
        v16,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x48Fu,
        L"CRAHelperClass::GetRepairInfo",
        v15);
      goto LABEL_91;
    }
    v18 = IsBuiltInRuleEnabled(0x80FBu, (int *)&v58);
    v9 = v18;
    if ( v18 < 0 )
    {
      CEventLogger::LogError(
        v20,
        v19,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x492u,
        L"CRAHelperClass::GetRepairInfo",
        v18);
      goto LABEL_91;
    }
    if ( (_DWORD)pv && (_DWORD)v58 )
    {
      v21 = v13;
      if ( *((_DWORD *)this + 42) == 1 )
        v22 = (struct _GUID)ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT;
      else
        v22 = (struct _GUID)ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT;
      goto LABEL_32;
    }
    LogRAProblem(1005, 1, v10);
    v22 = (struct _GUID)ID_RA_LOWH_REPAIR_FIREWALL_DISABLED;
  }
  v21 = v13;
LABEL_32:
  ++v13;
  v62[v21] = v22;
LABEL_33:
  if ( *((_DWORD *)this + 80) == 1 )
    v62[v13++] = (struct _GUID)ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT;
  if ( !v13 )
  {
LABEL_90:
    if ( (v9 & 0x80000000) != 0 )
      goto LABEL_91;
    return v9;
  }
  v23 = BuildRepairInfos(
          9u,
          (const struct tagRepairInfoMap *)&CRAHelperClass::m_repairInfos,
          (enum tagPROBLEM_TYPE)v10,
          v62,
          v13,
          v5,
          a4,
          v57);
  v9 = v23;
  if ( v23 < 0 )
  {
    CEventLogger::LogError(
      v25,
      v24,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x4D6u,
      L"CRAHelperClass::GetRepairInfo",
      v23);
    goto LABEL_91;
  }
  if ( !*a4 )
    return v9;
  v26 = 0;
  v27 = ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT;
  v28 = ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT;
  v29 = ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC;
  while ( 1 )
  {
    if ( v26 >= *v5 )
      goto LABEL_90;
    v30 = 112LL * v26;
    v31 = *v61;
    v32 = v27 - *(_QWORD *)&(*v61)[(unsigned __int64)v30 / 0x70].guid.Data1;
    if ( v27 == *(_QWORD *)&(*v61)[(unsigned __int64)v30 / 0x70].guid.Data1 )
      v32 = 0x8E15370975C29793uLL - *(_QWORD *)v31[(unsigned __int64)v30 / 0x70].guid.Data4;
    if ( !v32 )
      break;
    v33 = v28 - *(_QWORD *)&v31[(unsigned __int64)v30 / 0x70].guid.Data1;
    if ( (_QWORD)v28 == *(_QWORD *)&v31[(unsigned __int64)v30 / 0x70].guid.Data1 )
      v33 = *((_QWORD *)&v28 + 1) - *(_QWORD *)v31[(unsigned __int64)v30 / 0x70].guid.Data4;
    if ( !v33 )
      break;
    v34 = v29 - *(_QWORD *)&v31[(unsigned __int64)v30 / 0x70].guid.Data1;
    if ( (_QWORD)v29 == *(_QWORD *)&v31[(unsigned __int64)v30 / 0x70].guid.Data1 )
      v34 = *((_QWORD *)&v29 + 1) - *(_QWORD *)v31[(unsigned __int64)v30 / 0x70].guid.Data4;
    if ( !v34 )
    {
      pwszDescription = v31[(unsigned __int64)v30 / 0x70].pwszDescription;
      if ( pwszDescription )
      {
        CoTaskMemFree(pwszDescription);
        v31[(unsigned __int64)v30 / 0x70].pwszDescription = 0;
      }
      v36 = BuildTimeSyncRepairMsg(
              *((_DWORD *)this + 62),
              *((_QWORD *)this + 30),
              *((_QWORD *)this + 29),
              &v31[(unsigned __int64)v30 / 0x70].pwszDescription);
      v9 = v36;
      if ( v36 < 0 )
      {
        CEventLogger::LogError(
          v38,
          v37,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x525u,
          L"CRAHelperClass::GetRepairInfo",
          v36);
        goto LABEL_91;
      }
LABEL_78:
      v28 = ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT;
      v29 = ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC;
      v27 = ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT;
    }
    ++v26;
  }
  v39 = (const struct _EVENT_DESCRIPTOR *)(v27 - *(_QWORD *)&v31[(unsigned __int64)v30 / 0x70].guid.Data1);
  if ( !v39 )
    v39 = (const struct _EVENT_DESCRIPTOR *)(0x8E15370975C29793uLL
                                           - *(_QWORD *)v31[(unsigned __int64)v30 / 0x70].guid.Data4);
  if ( v39 )
  {
    v42 = (CEventLogger *)(v28 - *(_QWORD *)&v31[(unsigned __int64)v30 / 0x70].guid.Data1);
    if ( !v42 )
      v42 = (CEventLogger *)(*((_QWORD *)&v28 + 1) - *(_QWORD *)v31[(unsigned __int64)v30 / 0x70].guid.Data4);
    if ( v42 )
    {
      v9 = -2147467259;
      CEventLogger::LogError(
        v42,
        v39,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x4F3u,
        L"CRAHelperClass::GetRepairInfo",
        0x80004005);
      goto LABEL_91;
    }
    v40 = L"mshelp://windows/?id=6ddfa83c-01c8-441e-b041-1fd912c3fe60";
    v41 = 411;
  }
  else
  {
    v40 = L"mshelp://windows/?id=ca607790-adf6-41a7-abd8-0a1f2feb70b1";
    v41 = 408;
  }
  DiagnosisTextBuilder::DiagnosisTextBuilder((DiagnosisTextBuilder *)&v58, hInstance);
  pv = 0;
  v43 = StringCchCopyWithAlloc(&(&v31->UiInfo.pwzNull)[(unsigned __int64)v30 / 8], 0x400u, v40);
  v9 = v43;
  if ( v43 < 0 )
  {
    CEventLogger::LogError(
      v45,
      v44,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x4FCu,
      L"CRAHelperClass::GetRepairInfo",
      v43);
    DiagnosisTextBuilder::~DiagnosisTextBuilder((DiagnosisTextBuilder *)&v58);
    goto LABEL_91;
  }
  v31[(unsigned __int64)v30 / 0x70].UiInfo.type = UIT_HELP_PANE;
  v46 = v58;
  if ( v58 )
  {
    v47 = &v31[(unsigned __int64)v30 / 0x70];
    v48 = DiagnosisTextBuilderImpl::SetText(v58, v47->pwszDescription);
    v9 = v48;
    if ( v48 < 0 )
      goto LABEL_85;
    XML = StringCchCopyWithAlloc((unsigned __int16 **)&pv, (int)v44, v41);
    v9 = XML;
    if ( XML < 0 )
    {
      v55 = 1291;
      goto LABEL_83;
    }
    v53 = pv;
    if ( v46 )
      v54 = DiagnosisTextBuilderImpl::AddParameter(v46, (char *)v46 + 40, v52, pv);
    else
      v54 = -2147024882;
    if ( v54 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x50F,
        (unsigned int)"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        (const char *)(unsigned int)v54,
        v56);
    if ( v53 )
      CoTaskMemFree(v53);
    v51 = v47->pwszDescription;
    if ( v51 )
    {
      CoTaskMemFree(v51);
      v47->pwszDescription = 0;
    }
    if ( !v46 )
    {
      XML = -2147024882;
      v9 = -2147024882;
LABEL_81:
      v55 = 1301;
LABEL_83:
      CEventLogger::LogError(
        (CEventLogger *)v51,
        v50,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        v55,
        L"CRAHelperClass::GetRepairInfo",
        XML);
      DiagnosisTextBuilder::~DiagnosisTextBuilder((DiagnosisTextBuilder *)&v58);
      v5 = v60;
      goto LABEL_91;
    }
    XML = DiagnosisTextBuilderImpl::GetXML(v46, &v47->pwszDescription);
    v9 = XML;
    if ( XML < 0 )
      goto LABEL_81;
    DiagnosisTextBuilder::~DiagnosisTextBuilder((DiagnosisTextBuilder *)&v58);
    v5 = v60;
    goto LABEL_78;
  }
  v48 = -2147024882;
  v9 = -2147024882;
LABEL_85:
  CEventLogger::LogError(
    v45,
    v44,
    L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
    0x507u,
    L"CRAHelperClass::GetRepairInfo",
    v48);
  DiagnosisTextBuilder::~DiagnosisTextBuilder((DiagnosisTextBuilder *)&v58);
  v5 = v60;
LABEL_91:
  FreeRepairInfos(*v61, *v5, 1);
  *v5 = 0;
  return v9;
}

```

## disassembly

```asm
0x18000da10  mov     [rsp-8+arg_8], rbx
0x18000da15  push    rbp
0x18000da16  push    rsi
0x18000da17  push    rdi
0x18000da18  push    r12
0x18000da1a  push    r13
0x18000da1c  push    r14
0x18000da1e  push    r15
0x18000da20  lea     rbp, [rsp-27h]
0x18000da25  sub     rsp, 100h
0x18000da2c  mov     r13, r9
0x18000da2f  mov     [rsp+130h+var_D8], r9
0x18000da34  mov     r15, r8
0x18000da37  mov     [rsp+130h+var_E0], r8
0x18000da3c  mov     r14, rcx
0x18000da3f  xor     r12d, r12d
0x18000da42  test    r8, r8
0x18000da45  jnz     short loc_18000DA77
0x18000da47  mov     r9d, 44Ch; unsigned int
0x18000da4d  mov     dword ptr [rsp+130h+var_108], 80070057h; unsigned int
0x18000da55  lea     rax, aCrahelperclass_9; "CRAHelperClass::GetRepairInfo"
0x18000da5c  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18000da61  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000da68  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000da6d  mov     eax, 80070057h
0x18000da72  jmp     loc_18000DFE6
0x18000da77  test    r13, r13
0x18000da7a  jnz     short loc_18000DA84
0x18000da7c  mov     r9d, 44Dh
0x18000da82  jmp     short loc_18000DA4D
0x18000da84  mov     edi, r12d
0x18000da87  mov     [rbp+57h+var_D0.Data1], r12d
0x18000da8b  xor     edx, edx; Val
0x18000da8d  mov     r8d, 9Ch; Size
0x18000da93  lea     rcx, [rbp+57h+var_D0.Data2]; void *
0x18000da97  call    memset_0
0x18000da9c  mov     dword ptr [rsp+130h+pv], 1
0x18000daa4  mov     dword ptr [rsp+130h+var_F0], 1
0x18000daac  cmp     [r14+88h], r12d
0x18000dab3  jnz     short loc_18000DACC
0x18000dab5  mov     [rbp+57h+var_D0.Data1], 0B6D0AE66h
0x18000dabc  movsd   xmm0, cs:ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT+4
0x18000dac4  mov     eax, cs:dword_180020F9C
0x18000daca  jmp     short loc_18000DAED
0x18000dacc  mov     ebx, r12d
0x18000dacf  cmp     [r14+8Ch], r12d
0x18000dad6  jnz     short loc_18000DAFA
0x18000dad8  mov     [rbp+57h+var_D0.Data1], 0D803B207h
0x18000dadf  movsd   xmm0, cs:ID_RA_LOWH_REPAIR_SYSSETTING_DISABLED+4
0x18000dae7  mov     eax, cs:dword_180020FAC
0x18000daed  mov     ebx, 1
0x18000daf2  mov     dword ptr [rbp+57h+var_D0.Data4+4], eax
0x18000daf5  movsd   qword ptr [rbp+57h+var_D0.Data2], xmm0
0x18000dafa  cmp     [r14+9Ch], r12d
0x18000db01  jz      short loc_18000DB0C
0x18000db03  cmp     [r14+94h], r12d
0x18000db0a  jnz     short loc_18000DB20
0x18000db0c  mov     eax, ebx
0x18000db0e  add     rax, rax
0x18000db11  movups  xmm0, cs:ID_RA_LOWH_REPAIR_FIREWALL_DISABLED
0x18000db18  movdqu  xmmword ptr [rbp+rax*8+57h+var_D0.Data1], xmm0
0x18000db1e  inc     ebx
0x18000db20  cmp     dword ptr [r14+0E0h], 2
0x18000db28  jnz     short loc_18000DB3E
0x18000db2a  mov     eax, ebx
0x18000db2c  add     rax, rax
0x18000db2f  movups  xmm0, cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC
0x18000db36  movdqu  xmmword ptr [rbp+rax*8+57h+var_D0.Data1], xmm0
0x18000db3c  inc     ebx
0x18000db3e  cmp     dword ptr [r14+154h], 1
0x18000db46  jnz     short loc_18000DB5C
0x18000db48  mov     eax, ebx
0x18000db4a  add     rax, rax
0x18000db4d  movups  xmm0, cs:ID_RA_LOWH_REPAIR_IP_ADDRESS_CHANGED
0x18000db54  movdqu  xmmword ptr [rbp+rax*8+57h+var_D0.Data1], xmm0
0x18000db5a  inc     ebx
0x18000db5c  cmp     [r14+0A4h], r12d
0x18000db63  jnz     loc_18000DC28
0x18000db69  call    ?IsFWProfilePublic@@YAHXZ; IsFWProfilePublic(void)
0x18000db6e  test    eax, eax
0x18000db70  jnz     loc_18000DC05
0x18000db76  lea     rdx, [rsp+130h+pv]; int *
0x18000db7b  mov     ecx, 8103h; uID
0x18000db80  call    ?IsBuiltInRuleEnabled@@YAJHPEAH@Z; IsBuiltInRuleEnabled(int,int *)
0x18000db85  mov     edi, eax
0x18000db87  test    eax, eax
0x18000db89  jns     short loc_18000DB9A
0x18000db8b  mov     dword ptr [rsp+130h+var_108], eax
0x18000db8f  mov     r9d, 48Fh
0x18000db95  jmp     loc_18000DFAD
0x18000db9a  lea     rdx, [rsp+130h+var_F0]; int *
0x18000db9f  mov     ecx, 80FBh; uID
0x18000dba4  call    ?IsBuiltInRuleEnabled@@YAJHPEAH@Z; IsBuiltInRuleEnabled(int,int *)
0x18000dba9  mov     edi, eax
0x18000dbab  test    eax, eax
0x18000dbad  jns     short loc_18000DBBE
0x18000dbaf  mov     dword ptr [rsp+130h+var_108], eax
0x18000dbb3  mov     r9d, 492h
0x18000dbb9  jmp     loc_18000DFAD
0x18000dbbe  cmp     dword ptr [rsp+130h+pv], r12d
0x18000dbc3  jz      short loc_18000DBED
0x18000dbc5  cmp     dword ptr [rsp+130h+var_F0], r12d
0x18000dbca  jz      short loc_18000DBED
0x18000dbcc  mov     eax, ebx
0x18000dbce  add     rax, rax
0x18000dbd1  cmp     dword ptr [r14+0A8h], 1
0x18000dbd9  jnz     short loc_18000DBE4
0x18000dbdb  movups  xmm0, cs:ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT
0x18000dbe2  jmp     short loc_18000DC20
0x18000dbe4  movups  xmm0, cs:ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT
0x18000dbeb  jmp     short loc_18000DC20
0x18000dbed  mov     edx, 1
0x18000dbf2  mov     ecx, 3EDh
0x18000dbf7  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000dbfc  movups  xmm0, cs:ID_RA_LOWH_REPAIR_FIREWALL_DISABLED
0x18000dc03  jmp     short loc_18000DC1B
0x18000dc05  mov     edx, 1
0x18000dc0a  mov     ecx, 3EEh
0x18000dc0f  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000dc14  movups  xmm0, cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT
0x18000dc1b  mov     eax, ebx
0x18000dc1d  add     rax, rax
0x18000dc20  inc     ebx
0x18000dc22  movdqu  xmmword ptr [rbp+rax*8+57h+var_D0.Data1], xmm0
0x18000dc28  cmp     dword ptr [r14+140h], 1
0x18000dc30  jnz     short loc_18000DC46
0x18000dc32  mov     eax, ebx
0x18000dc34  add     rax, rax
0x18000dc37  movups  xmm0, cs:ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT
0x18000dc3e  movdqu  xmmword ptr [rbp+rax*8+57h+var_D0.Data1], xmm0
0x18000dc44  inc     ebx
0x18000dc46  test    ebx, ebx
0x18000dc48  jz      loc_18000DFC7
0x18000dc4e  mov     [rsp+130h+var_100], r13; struct tagRepairInfo **
0x18000dc53  mov     [rsp+130h+var_108], r15; unsigned int *
0x18000dc58  mov     dword ptr [rsp+130h+var_110], ebx; int
0x18000dc5c  lea     r9, [rbp+57h+var_D0]; struct _GUID *
0x18000dc60  lea     rdx, ?m_repairInfos@CRAHelperClass@@0QBUtagRepairInfoMap@@B; struct tagRepairInfoMap *
0x18000dc67  mov     ecx, 9; unsigned int
0x18000dc6c  call    ?BuildRepairInfos@@YAJKPEBUtagRepairInfoMap@@W4tagPROBLEM_TYPE@@PEAU_GUID@@KPEAKPEAPEAUtagRepairInfo@@H@Z; BuildRepairInfos(ulong,tagRepairInfoMap const *,tagPROBLEM_TYPE,_GUID *,ulong,ulong *,tagRepairInfo * *,int)
0x18000dc71  mov     edi, eax
0x18000dc73  test    eax, eax
0x18000dc75  jns     short loc_18000DC86
0x18000dc77  mov     dword ptr [rsp+130h+var_108], eax
0x18000dc7b  mov     r9d, 4D6h
0x18000dc81  jmp     loc_18000DFAD
0x18000dc86  cmp     [r13+0], r12
0x18000dc8a  jz      loc_18000DFE4
0x18000dc90  mov     r13d, r12d
0x18000dc93  mov     r8, qword ptr cs:byte_180020F98
0x18000dc9a  mov     rdx, cs:ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT
0x18000dca1  mov     r10, qword ptr cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC+8
0x18000dca8  mov     r11, qword ptr cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC
0x18000dcaf  mov     r9, qword ptr cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT+8
0x18000dcb6  mov     rcx, qword ptr cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT
0x18000dcbd  cmp     r13d, [r15]
0x18000dcc0  jnb     loc_18000DFC7
0x18000dcc6  mov     eax, r13d
0x18000dcc9  imul    rbx, rax, 70h ; 'p'
0x18000dccd  mov     rax, [rsp+130h+var_D8]
0x18000dcd2  mov     rsi, [rax]
0x18000dcd5  mov     rax, rdx
0x18000dcd8  sub     rax, [rbx+rsi]
0x18000dcdc  jnz     short loc_18000DCE6
0x18000dcde  mov     rax, r8
0x18000dce1  sub     rax, [rbx+rsi+8]
0x18000dce6  test    rax, rax
0x18000dce9  jz      short loc_18000DD6A
0x18000dceb  mov     rax, rcx
0x18000dcee  sub     rax, [rbx+rsi]
0x18000dcf2  jnz     short loc_18000DCFC
0x18000dcf4  mov     rax, r9
0x18000dcf7  sub     rax, [rbx+rsi+8]
0x18000dcfc  test    rax, rax
0x18000dcff  jz      short loc_18000DD6A
0x18000dd01  mov     rax, r11
0x18000dd04  sub     rax, [rbx+rsi]
0x18000dd08  jnz     short loc_18000DD12
0x18000dd0a  mov     rax, r10
0x18000dd0d  sub     rax, [rbx+rsi+8]
0x18000dd12  test    rax, rax
0x18000dd15  jnz     loc_18000DEDF
0x18000dd1b  mov     rcx, [rbx+rsi+18h]; pv
0x18000dd20  test    rcx, rcx
0x18000dd23  jz      short loc_18000DD30
0x18000dd25  call    cs:__imp_CoTaskMemFree
0x18000dd2b  mov     [rbx+rsi+18h], r12
0x18000dd30  lea     r9, [rsi+18h]
0x18000dd34  add     r9, rbx; unsigned __int16 **
0x18000dd37  mov     r8, [r14+0E8h]; __int64
0x18000dd3e  mov     rdx, [r14+0F0h]; __int64
0x18000dd45  mov     ecx, [r14+0F8h]; int
0x18000dd4c  call    ?BuildTimeSyncRepairMsg@@YAJH_J0PEAPEAG@Z; BuildTimeSyncRepairMsg(int,__int64,__int64,ushort * *)
0x18000dd51  mov     edi, eax
0x18000dd53  test    eax, eax
0x18000dd55  jns     loc_18000DEB5
0x18000dd5b  mov     dword ptr [rsp+130h+var_108], eax
0x18000dd5f  mov     r9d, 525h
0x18000dd65  jmp     loc_18000DFAD
0x18000dd6a  sub     rdx, [rbx+rsi]
0x18000dd6e  jnz     short loc_18000DD78
0x18000dd70  mov     rdx, r8
0x18000dd73  sub     rdx, [rbx+rsi+8]; struct _EVENT_DESCRIPTOR *
0x18000dd78  test    rdx, rdx
0x18000dd7b  jnz     short loc_18000DD8C
0x18000dd7d  lea     rdi, aMshelpWindowsI_0; "mshelp://windows/?id=ca607790-adf6-41a7"...
0x18000dd84  mov     r12d, 198h
0x18000dd8a  jmp     short loc_18000DDB0
0x18000dd8c  sub     rcx, [rbx+rsi]
0x18000dd90  jnz     short loc_18000DD9A
0x18000dd92  mov     rcx, r9
0x18000dd95  sub     rcx, [rbx+rsi+8]; this
0x18000dd9a  test    rcx, rcx
0x18000dd9d  jnz     loc_18000DF9A
0x18000dda3  lea     rdi, aMshelpWindowsI; "mshelp://windows/?id=6ddfa83c-01c8-441e"...
0x18000ddaa  mov     r12d, 19Bh
0x18000ddb0  mov     rdx, cs:hInstance; HINSTANCE
0x18000ddb7  lea     rcx, [rsp+130h+var_F0]; this
0x18000ddbc  call    ??0DiagnosisTextBuilder@@QEAA@PEAUHINSTANCE__@@@Z; DiagnosisTextBuilder::DiagnosisTextBuilder(HINSTANCE__ *)
0x18000ddc1  nop
0x18000ddc2  mov     [rsp+130h+pv], 0
0x18000ddcb  lea     rcx, [rsi+40h]
0x18000ddcf  add     rcx, rbx; unsigned __int16 **
0x18000ddd2  mov     r8, rdi; unsigned __int16 *
0x18000ddd5  mov     edx, 400h; unsigned __int64
0x18000ddda  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000dddf  mov     edi, eax
0x18000dde1  test    eax, eax
0x18000dde3  js      loc_18000DF68
0x18000dde9  mov     dword ptr [rbx+rsi+38h], 3
0x18000ddf1  mov     r15, [rsp+130h+var_F0]
0x18000ddf6  test    r15, r15
0x18000ddf9  jz      loc_18000DF2D
0x18000ddff  add     rsi, rbx
0x18000de02  mov     rdx, [rsi+18h]; unsigned __int16 *
0x18000de06  mov     rcx, r15; this
0x18000de09  call    ?SetText@DiagnosisTextBuilderImpl@@QEAAJPEBG@Z; DiagnosisTextBuilderImpl::SetText(ushort const *)
0x18000de0e  mov     edi, eax
0x18000de10  test    eax, eax
0x18000de12  js      loc_18000DF34
0x18000de18  mov     r8d, r12d; int
0x18000de1b  lea     rcx, [rsp+130h+pv]; unsigned __int16 **
0x18000de20  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000de25  mov     edi, eax
0x18000de27  xor     r12d, r12d
0x18000de2a  test    eax, eax
0x18000de2c  js      loc_18000DEF6
0x18000de32  mov     rbx, [rsp+130h+pv]
0x18000de37  test    r15, r15
0x18000de3a  jz      short loc_18000DE4D
0x18000de3c  lea     rdx, [r15+28h]
0x18000de40  mov     r9, rbx
0x18000de43  mov     rcx, r15
0x18000de46  call    ?AddParameter@DiagnosisTextBuilderImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEBG1@Z; DiagnosisTextBuilderImpl::AddParameter(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,ushort const *,ushort const *)
0x18000de4b  jmp     short loc_18000DE52
0x18000de4d  mov     eax, 8007000Eh
0x18000de52  mov     rcx, [rbp+5Fh]; this
0x18000de56  test    eax, eax
0x18000de58  jns     short loc_18000DE6E
0x18000de5a  mov     r9d, eax; char *
0x18000de5d  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000de64  mov     edx, 50Fh; void *
0x18000de69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000de6e  test    rbx, rbx
0x18000de71  jz      short loc_18000DE7C
0x18000de73  mov     rcx, rbx; pv
0x18000de76  call    cs:__imp_CoTaskMemFree
0x18000de7c  mov     rcx, [rsi+18h]; pv
0x18000de80  test    rcx, rcx
0x18000de83  jz      short loc_18000DE8F
0x18000de85  call    cs:__imp_CoTaskMemFree
0x18000de8b  mov     [rsi+18h], r12
0x18000de8f  test    r15, r15
0x18000de92  jz      short loc_18000DEE7
0x18000de94  lea     rdx, [rsi+18h]; unsigned __int16 **
0x18000de98  mov     rcx, r15; this
0x18000de9b  call    ?GetXML@DiagnosisTextBuilderImpl@@QEAAJPEAPEAG@Z; DiagnosisTextBuilderImpl::GetXML(ushort * *)
0x18000dea0  mov     edi, eax
0x18000dea2  test    eax, eax
0x18000dea4  js      short loc_18000DEEE
0x18000dea6  lea     rcx, [rsp+130h+var_F0]; this
0x18000deab  call    ??1DiagnosisTextBuilder@@QEAA@XZ; DiagnosisTextBuilder::~DiagnosisTextBuilder(void)
0x18000deb0  mov     r15, [rsp+130h+var_E0]
0x18000deb5  mov     rcx, qword ptr cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT
0x18000debc  mov     r9, qword ptr cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT+8
0x18000dec3  mov     r11, qword ptr cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC
0x18000deca  mov     r10, qword ptr cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC+8
0x18000ded1  mov     rdx, cs:ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT
0x18000ded8  mov     r8, qword ptr cs:byte_180020F98
0x18000dedf  inc     r13d
0x18000dee2  jmp     loc_18000DCBD
0x18000dee7  mov     eax, 8007000Eh
0x18000deec  mov     edi, eax
0x18000deee  mov     r9d, 515h
0x18000def4  jmp     short loc_18000DEFC
0x18000def6  mov     r9d, 50Bh; unsigned int
0x18000defc  mov     dword ptr [rsp+130h+var_108], eax; unsigned int
0x18000df00  lea     rax, aCrahelperclass_9; "CRAHelperClass::GetRepairInfo"
0x18000df07  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18000df0c  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
  ... truncated ...
```
