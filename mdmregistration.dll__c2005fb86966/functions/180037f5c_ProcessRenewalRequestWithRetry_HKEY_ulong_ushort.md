# ProcessRenewalRequestWithRetry(HKEY__ *,ulong,ushort * *)

- ea: `0x180037f5c`
- end: `0x180038945`
- name: `?ProcessRenewalRequestWithRetry@@YAJPEAUHKEY__@@KPEAPEAG@Z`
- size: `2537`
- prototype: `__int64 __fastcall(HKEY, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x18000b0f4`
- `0x180019f44`
- `0x18001d3e8`
- `0x180037f5c`
- `0x180038c6c`
- `0x180038cf4`
- `0x180041410`
- `0x180043ad0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800382c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800382c0`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180037fb1`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180037fb1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800380e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800380e1`
- `OLEAUT32!__imp_SysAllocString` at `0x180037fc1`
- `OLEAUT32!__imp_SysAllocString` at `0x180037fc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180037fe3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003812d`
- `OLEAUT32!__imp_SysFreeString` at `0x180038144`
- `OLEAUT32!__imp_SysFreeString` at `0x1800382b2`
- `OLEAUT32!__imp_SysFreeString` at `0x180038469`
- `OLEAUT32!__imp_SysFreeString` at `0x180038480`
- `OLEAUT32!__imp_SysFreeString` at `0x180038628`
- `OLEAUT32!__imp_SysFreeString` at `0x1800386f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003870c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387df`
- `OLEAUT32!__imp_SysFreeString` at `0x180038866`
- `OLEAUT32!__imp_SysFreeString` at `0x18003887d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800388f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003890f`
- `OLEAUT32!__imp_SysFreeString` at `0x180037fe3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003812d`
- `OLEAUT32!__imp_SysFreeString` at `0x180038144`
- `OLEAUT32!__imp_SysFreeString` at `0x1800382b2`
- `OLEAUT32!__imp_SysFreeString` at `0x180038469`
- `OLEAUT32!__imp_SysFreeString` at `0x180038480`
- `OLEAUT32!__imp_SysFreeString` at `0x180038628`
- `OLEAUT32!__imp_SysFreeString` at `0x1800386f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003870c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387df`
- `OLEAUT32!__imp_SysFreeString` at `0x180038866`
- `OLEAUT32!__imp_SysFreeString` at `0x18003887d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800388f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003890f`

## string_xrefs

- `0x1800380ff`: `CoCreateInstance IX509CertificateRequestPkcs7`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall ProcessRenewalRequestWithRetry(HKEY a1, char a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rbx
  int v8; // esi
  LPVOID v9; // rcx
  CEnrollmentLogger *Logger; // rcx
  __int64 v11; // rcx
  LPVOID v12; // rdx
  LPVOID v13; // rcx
  HRESULT v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // edi
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  LPVOID v23; // r14
  __int64 (__fastcall *v24)(LPVOID, __int64, BSTR *); // r15
  OLECHAR *v25; // rsi
  DWORD LastError; // edi
  int v27; // eax
  __int64 v28; // rcx
  unsigned int v29; // esi
  unsigned __int16 *v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  _QWORD *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  _QWORD *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  _QWORD *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  _QWORD *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  _QWORD *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v61; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v62; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v65; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v66; // [rsp+68h] [rbp-98h] BYREF
  BSTR v67; // [rsp+70h] [rbp-90h] BYREF
  int v68; // [rsp+78h] [rbp-88h] BYREF
  LPVOID *v69; // [rsp+80h] [rbp-80h]
  struct IX509CertificateRequestPkcs7 *v70; // [rsp+88h] [rbp-78h] BYREF
  char v71; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v72; // [rsp+98h] [rbp-68h]
  OLECHAR psz[48]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  bstrString = 0;
  psz[0] = 0;
  OmaDmRegistryGetString(a1, 0, L"DMPCertThumbPrint", psz, 0x2Au);
  v6 = SysAllocString(psz);
  v72 = v6;
  if ( !v6 )
    return 2147942414LL;
  v61 = 0;
  v69 = &v61;
  v70 = 0;
  v71 = 1;
  v8 = SetUpLimitedCertRequest(a1, v6, a2, &v70);
  if ( v71 )
  {
    v9 = *v69;
    *v69 = v70;
    if ( v9 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  Logger = CEnrollmentLogger::GetLogger();
  if ( v8 >= 0 )
  {
    CEnrollmentLogger::LogLimitedRenewStatus(Logger, 0);
  }
  else
  {
    CEnrollmentLogger::LogLimitedRenewStatus(Logger, v8);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, FunctionFailedEvent, L"SetUpLimitedCertRequest", (unsigned int)v8);
    v12 = v61;
    v13 = 0;
    v61 = 0;
    if ( v12 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
      v13 = v61;
    }
    v61 = 0;
    if ( v13 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    v14 = CoCreateInstance(
            &GUID_884e2044_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab344_217d_11da_b2a4_000e7bbb2b09,
            &v61);
    v16 = v14;
    if ( v14 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v15,
          FunctionFailedEvent,
          L"CoCreateInstance IX509CertificateRequestPkcs7",
          (unsigned int)v14);
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
LABEL_18:
      SysFreeString(v6);
      if ( bstrString )
        SysFreeString(bstrString);
      return v16;
    }
    ppv = 12;
    v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v61 + 264LL))(
            v61,
            (unsigned int)((a2 & 4) != 0) + 1,
            1,
            v6);
    v16 = v17;
    if ( v17 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v18,
          FunctionFailedEvent,
          L"IX509CertificateRequestPkcs7->InitializeFromCertificate",
          (unsigned int)v17);
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      goto LABEL_18;
    }
  }
  v19 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v61 + 160LL))(v61, 1);
  v16 = v19;
  if ( v19 < 0 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v20,
        FunctionFailedEvent,
        L"IX509CertificateRequestPkcs7->put_SuppressDefaults",
        (unsigned int)v19);
    if ( v61 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    goto LABEL_18;
  }
  v21 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 64LL))(v61);
  v16 = v21;
  if ( v21 < 0 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v22,
        FunctionFailedEvent,
        L"IX509CertificateRequestPkcs7->Encode",
        (unsigned int)v21);
    if ( v61 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    goto LABEL_18;
  }
  v23 = v61;
  v24 = *(__int64 (__fastcall **)(LPVOID, __int64, BSTR *))(*(_QWORD *)v61 + 248LL);
  v25 = bstrString;
  if ( bstrString )
  {
    LastError = GetLastError();
    SysFreeString(v25);
    SetLastError(LastError);
  }
  bstrString = 0;
  v27 = v24(v23, 1, &bstrString);
  v29 = v27;
  if ( v27 < 0 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v28,
        FunctionFailedEvent,
        L"IX509CertificateRequestPkcs7->get_RawData",
        (unsigned int)v27);
    if ( v61 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
LABEL_139:
    SysFreeString(v6);
    if ( bstrString )
      SysFreeString(bstrString);
    return v29;
  }
  v30 = HeapStrDup(bstrString);
  *a3 = v30;
  if ( !v30 )
  {
LABEL_137:
    if ( v61 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    goto LABEL_139;
  }
  v62 = 0;
  v31 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v61 + 80LL))(v61, 0, &v62);
  v16 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x964,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v31,
      ppv);
    v32 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    if ( v61 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    goto LABEL_18;
  }
  v68 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 88LL))(v62, &v68);
  v16 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x967,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v33,
      ppv);
    v34 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    if ( v61 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    goto LABEL_18;
  }
  if ( v68 == 1 )
  {
    v64 = 0;
    v36 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v62)(
            v62,
            &GUID_728ab342_217d_11da_b2a4_000e7bbb2b09,
            &v64);
    v16 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x971,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
        (const char *)(unsigned int)v36,
        ppv);
      v37 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      goto LABEL_18;
    }
    v65 = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v64 + 328LL))(v64, &v65);
    v16 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x974,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
        (const char *)(unsigned int)v39,
        ppv);
      v40 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
      }
      v41 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      goto LABEL_18;
    }
    v66 = 0;
    v43 = *v65;
    v66 = 0;
    v44 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(v43 + 120))(v65, &v66);
    v16 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x977,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
        (const char *)(unsigned int)v44,
        ppv);
      if ( v66 )
        SysFreeString(v66);
      v45 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
      }
      v46 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      goto LABEL_18;
    }
    v67 = 0;
    v48 = *v65;
    v67 = 0;
    v49 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(v48 + 200))(v65, &v67);
    v16 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
        (const char *)(unsigned int)v49,
        ppv);
      if ( v67 )
        SysFreeString(v67);
      if ( v66 )
        SysFreeString(v66);
      v50 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
      }
      v51 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
      v52 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      goto LABEL_18;
    }
    v53 = SetNewContainerAndProvider(a1, v66, v67);
    v16 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
        (const char *)(unsigned int)v53,
        ppv);
      if ( v67 )
        SysFreeString(v67);
      if ( v66 )
        SysFreeString(v66);
      v54 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
      }
      v55 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      if ( v61 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      goto LABEL_18;
    }
    if ( v67 )
      SysFreeString(v67);
    if ( v66 )
      SysFreeString(v66);
    v57 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
    }
    v58 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    v59 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    goto LABEL_137;
  }
  v35 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  if ( v61 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
  SysFreeString(v6);
  if ( bstrString )
    SysFreeString(bstrString);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180037f5c  mov     [rsp-8+arg_18], rbx
0x180037f61  push    rbp
0x180037f62  push    rsi
0x180037f63  push    rdi
0x180037f64  push    r12
0x180037f66  push    r13
0x180037f68  push    r14
0x180037f6a  push    r15
0x180037f6c  lea     rbp, [rsp-10h]
0x180037f71  sub     rsp, 110h
0x180037f78  mov     rax, cs:__security_cookie
0x180037f7f  xor     rax, rsp
0x180037f82  mov     [rbp+40h+var_40], rax
0x180037f86  mov     r13, r8
0x180037f89  mov     r14d, edx
0x180037f8c  mov     r12, rcx
0x180037f8f  xor     r15d, r15d
0x180037f92  mov     [rsp+140h+bstrString], r15
0x180037f97  mov     [rbp+40h+psz], r15w
0x180037f9c  mov     dword ptr [rsp+140h+ppv], 2Ah ; '*'; int
0x180037fa4  lea     r9, [rbp+40h+psz]
0x180037fa8  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180037faf  xor     edx, edx
0x180037fb1  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180037fb8  nop     dword ptr [rax+rax+00h]
0x180037fbd  lea     rcx, [rbp+40h+psz]; psz
0x180037fc1  call    cs:__imp_SysAllocString
0x180037fc8  nop     dword ptr [rax+rax+00h]
0x180037fcd  mov     rbx, rax
0x180037fd0  mov     [rbp+40h+var_A8], rax
0x180037fd4  test    rax, rax
0x180037fd7  jnz     short loc_180037FF9
0x180037fd9  mov     rcx, [rsp+140h+bstrString]; bstrString
0x180037fde  test    rcx, rcx
0x180037fe1  jz      short loc_180037FEF
0x180037fe3  call    cs:__imp_SysFreeString
0x180037fea  nop     dword ptr [rax+rax+00h]
0x180037fef  mov     eax, 8007000Eh
0x180037ff4  jmp     loc_18003891D
0x180037ff9  mov     [rsp+140h+var_100], r15
0x180037ffe  lea     rax, [rsp+140h+var_100]
0x180038003  mov     [rbp+40h+var_C0], rax
0x180038007  mov     [rbp+40h+var_B8], r15
0x18003800b  mov     [rbp+40h+var_B0], 1
0x18003800f  lea     r9, [rbp+40h+var_B8]; struct IX509CertificateRequestPkcs7 **
0x180038013  mov     r8d, r14d; unsigned int
0x180038016  mov     rdx, rbx; unsigned __int16 *
0x180038019  mov     rcx, r12; HKEY
0x18003801c  call    ?SetUpLimitedCertRequest@@YAJPEAUHKEY__@@PEAGKPEAPEAUIX509CertificateRequestPkcs7@@@Z; SetUpLimitedCertRequest(HKEY__ *,ushort *,ulong,IX509CertificateRequestPkcs7 * *)
0x180038021  mov     esi, eax
0x180038023  mov     edi, eax
0x180038025  shr     edi, 1Fh
0x180038028  cmp     [rbp+40h+var_B0], r15b
0x18003802c  jz      short loc_18003804E
0x18003802e  mov     r8, [rbp+40h+var_B8]
0x180038032  mov     rdx, [rbp+40h+var_C0]
0x180038036  mov     rcx, [rdx]
0x180038039  mov     [rdx], r8
0x18003803c  test    rcx, rcx
0x18003803f  jz      short loc_18003804E
0x180038041  mov     rax, [rcx]
0x180038044  mov     rax, [rax+10h]
0x180038048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003804d  nop
0x18003804e  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180038053  mov     rcx, rax; this
0x180038056  test    dil, dil
0x180038059  jz      loc_1800381D3
0x18003805f  mov     edx, esi; int
0x180038061  call    ?LogLimitedRenewStatus@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogLimitedRenewStatus(long)
0x180038066  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18003806d  jz      short loc_180038086
0x18003806f  mov     r9d, esi
0x180038072  lea     r8, aSetuplimitedce; "SetUpLimitedCertRequest"
0x180038079  lea     rdx, FunctionFailedEvent
0x180038080  call    McTemplateU0zq_EventWriteTransfer
0x180038085  nop
0x180038086  mov     rdx, [rsp+140h+var_100]
0x18003808b  mov     rcx, r15
0x18003808e  mov     [rsp+140h+var_100], rcx
0x180038093  test    rdx, rdx
0x180038096  jz      short loc_1800380AC
0x180038098  mov     rax, [rdx]
0x18003809b  mov     rcx, rdx
0x18003809e  mov     rax, [rax+10h]
0x1800380a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380a7  mov     rcx, [rsp+140h+var_100]
0x1800380ac  mov     [rsp+140h+var_100], r15
0x1800380b1  test    rcx, rcx
0x1800380b4  jz      short loc_1800380C3
0x1800380b6  mov     rax, [rcx]
0x1800380b9  mov     rax, [rax+10h]
0x1800380bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380c2  nop
0x1800380c3  lea     rax, [rsp+140h+var_100]
0x1800380c8  mov     [rsp+140h+ppv], rax; ppv
0x1800380cd  lea     r9, _GUID_728ab344_217d_11da_b2a4_000e7bbb2b09; riid
0x1800380d4  xor     edx, edx; pUnkOuter
0x1800380d6  lea     r8d, [rdx+1]; dwClsContext
0x1800380da  lea     rcx, _GUID_884e2044_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800380e1  call    cs:__imp_CoCreateInstance
0x1800380e8  nop     dword ptr [rax+rax+00h]
0x1800380ed  mov     edi, eax
0x1800380ef  test    eax, eax
0x1800380f1  jns     short loc_180038157
0x1800380f3  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800380fa  jz      short loc_180038113
0x1800380fc  mov     r9d, eax
0x1800380ff  lea     r8, aCocreateinstan_1; "CoCreateInstance IX509CertificateReques"...
0x180038106  lea     rdx, FunctionFailedEvent
0x18003810d  call    McTemplateU0zq_EventWriteTransfer
0x180038112  nop
0x180038113  mov     rcx, [rsp+140h+var_100]
0x180038118  test    rcx, rcx
0x18003811b  jz      short loc_18003812A
0x18003811d  mov     rax, [rcx]
0x180038120  mov     rax, [rax+10h]
0x180038124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038129  nop
0x18003812a  mov     rcx, rbx; bstrString
0x18003812d  call    cs:__imp_SysFreeString
0x180038134  nop     dword ptr [rax+rax+00h]
0x180038139  nop
0x18003813a  mov     rcx, [rsp+140h+bstrString]; bstrString
0x18003813f  test    rcx, rcx
0x180038142  jz      short loc_180038150
0x180038144  call    cs:__imp_SysFreeString
0x18003814b  nop     dword ptr [rax+rax+00h]
0x180038150  mov     eax, edi
0x180038152  jmp     loc_18003891D
0x180038157  mov     rcx, [rsp+140h+var_100]
0x18003815c  mov     rax, [rcx]
0x18003815f  mov     r8d, 1
0x180038165  and     r14b, 4
0x180038169  neg     r14b
0x18003816c  sbb     edx, edx
0x18003816e  neg     edx
0x180038170  inc     edx
0x180038172  mov     [rsp+140h+var_118], 2
0x18003817a  mov     dword ptr [rsp+140h+ppv], 0Ch
0x180038182  mov     r9, rbx
0x180038185  mov     rax, [rax+108h]
0x18003818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038191  mov     edi, eax
0x180038193  test    eax, eax
0x180038195  jns     short loc_1800381DA
0x180038197  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18003819e  jz      short loc_1800381B7
0x1800381a0  mov     r9d, eax
0x1800381a3  lea     r8, aIx509certifica_2; "IX509CertificateRequestPkcs7->Initializ"...
0x1800381aa  lea     rdx, FunctionFailedEvent
0x1800381b1  call    McTemplateU0zq_EventWriteTransfer
0x1800381b6  nop
0x1800381b7  mov     rcx, [rsp+140h+var_100]
0x1800381bc  test    rcx, rcx
0x1800381bf  jz      short loc_1800381CE
0x1800381c1  mov     rax, [rcx]
0x1800381c4  mov     rax, [rax+10h]
0x1800381c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381cd  nop
0x1800381ce  jmp     loc_18003812A
0x1800381d3  xor     edx, edx; int
0x1800381d5  call    ?LogLimitedRenewStatus@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogLimitedRenewStatus(long)
0x1800381da  mov     rcx, [rsp+140h+var_100]
0x1800381df  mov     rax, [rcx]
0x1800381e2  mov     edx, 1
0x1800381e7  mov     rax, [rax+0A0h]
0x1800381ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381f3  mov     edi, eax
0x1800381f5  test    eax, eax
0x1800381f7  jns     short loc_180038235
0x1800381f9  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180038200  jz      short loc_180038219
0x180038202  mov     r9d, eax
0x180038205  lea     r8, aIx509certifica_5; "IX509CertificateRequestPkcs7->put_Suppr"...
0x18003820c  lea     rdx, FunctionFailedEvent
0x180038213  call    McTemplateU0zq_EventWriteTransfer
0x180038218  nop
0x180038219  mov     rcx, [rsp+140h+var_100]
0x18003821e  test    rcx, rcx
0x180038221  jz      short loc_180038230
0x180038223  mov     rax, [rcx]
0x180038226  mov     rax, [rax+10h]
0x18003822a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003822f  nop
0x180038230  jmp     loc_18003812A
0x180038235  mov     rcx, [rsp+140h+var_100]
0x18003823a  mov     rax, [rcx]
0x18003823d  mov     rax, [rax+40h]
0x180038241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038246  mov     edi, eax
0x180038248  test    eax, eax
0x18003824a  jns     short loc_180038288
0x18003824c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180038253  jz      short loc_18003826C
0x180038255  mov     r9d, eax
0x180038258  lea     r8, aIx509certifica_4; "IX509CertificateRequestPkcs7->Encode"
0x18003825f  lea     rdx, FunctionFailedEvent
0x180038266  call    McTemplateU0zq_EventWriteTransfer
0x18003826b  nop
0x18003826c  mov     rcx, [rsp+140h+var_100]
0x180038271  test    rcx, rcx
0x180038274  jz      short loc_180038283
0x180038276  mov     rax, [rcx]
0x180038279  mov     rax, [rax+10h]
0x18003827d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038282  nop
0x180038283  jmp     loc_18003812A
0x180038288  mov     r14, [rsp+140h+var_100]
0x18003828d  mov     rax, [r14]
0x180038290  mov     r15, [rax+0F8h]
0x180038297  mov     rsi, [rsp+140h+bstrString]
0x18003829c  test    rsi, rsi
0x18003829f  jz      short loc_1800382CC
0x1800382a1  call    cs:__imp_GetLastError
0x1800382a8  nop     dword ptr [rax+rax+00h]
0x1800382ad  mov     edi, eax
0x1800382af  mov     rcx, rsi; bstrString
0x1800382b2  call    cs:__imp_SysFreeString
0x1800382b9  nop     dword ptr [rax+rax+00h]
0x1800382be  mov     ecx, edi; dwErrCode
0x1800382c0  call    cs:__imp_SetLastError
0x1800382c7  nop     dword ptr [rax+rax+00h]
0x1800382cc  mov     [rsp+140h+bstrString], 0
0x1800382d5  lea     r8, [rsp+140h+bstrString]
0x1800382da  mov     edx, 1
0x1800382df  mov     rcx, r14
0x1800382e2  mov     rax, r15
0x1800382e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382ea  mov     esi, eax
0x1800382ec  xor     r14d, r14d
0x1800382ef  test    eax, eax
0x1800382f1  jns     short loc_18003832F
0x1800382f3  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800382fa  jz      short loc_180038313
0x1800382fc  mov     r9d, eax
0x1800382ff  lea     r8, aIx509certifica_7; "IX509CertificateRequestPkcs7->get_RawDa"...
0x180038306  lea     rdx, FunctionFailedEvent
0x18003830d  call    McTemplateU0zq_EventWriteTransfer
0x180038312  nop
0x180038313  mov     rcx, [rsp+140h+var_100]
0x180038318  test    rcx, rcx
0x18003831b  jz      short loc_18003832A
0x18003831d  mov     rax, [rcx]
0x180038320  mov     rax, [rax+10h]
0x180038324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038329  nop
0x18003832a  jmp     loc_1800388F5
0x18003832f  mov     rcx, [rsp+140h+bstrString]; unsigned __int16 *
0x180038334  call    ?HeapStrDup@@YAPEAGPEBG@Z; HeapStrDup(ushort const *)
0x180038339  mov     [r13+0], rax
0x18003833d  test    rax, rax
0x180038340  jz      loc_1800388DE
0x180038346  mov     [rsp+140h+var_F8], r14
0x18003834b  mov     rcx, [rsp+140h+var_100]
0x180038350  mov     rax, [rcx]
0x180038353  lea     r8, [rsp+140h+var_F8]
0x180038358  xor     edx, edx
0x18003835a  mov     rax, [rax+50h]
0x18003835e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038363  mov     edi, eax
0x180038365  test    eax, eax
0x180038367  jns     short loc_1800383BA
0x180038369  mov     rcx, [rbp+48h]; this
0x18003836d  mov     r9d, eax; char *
0x180038370  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038377  mov     edx, 964h; void *
0x18003837c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038381  nop
0x180038382  mov     rcx, [rsp+140h+var_F8]
0x180038387  test    rcx, rcx
0x18003838a  jz      short loc_18003839E
0x18003838c  mov     [rsp+140h+var_F8], r14
0x180038391  mov     rax, [rcx]
0x180038394  mov     rax, [rax+10h]
0x180038398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003839d  nop
0x18003839e  mov     rcx, [rsp+140h+var_100]
0x1800383a3  test    rcx, rcx
0x1800383a6  jz      short loc_1800383B5
0x1800383a8  mov     rax, [rcx]
0x1800383ab  mov     rax, [rax+10h]
0x1800383af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383b4  nop
0x1800383b5  jmp     loc_18003812A
0x1800383ba  mov     [rsp+140h+var_C8], r14d
0x1800383bf  mov     rcx, [rsp+140h+var_F8]
0x1800383c4  mov     rax, [rcx]
0x1800383c7  lea     rdx, [rsp+140h+var_C8]
0x1800383cc  mov     rax, [rax+58h]
0x1800383d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383d5  mov     edi, eax
0x1800383d7  test    eax, eax
0x1800383d9  jns     short loc_18003842C
0x1800383db  mov     rcx, [rbp+48h]; this
0x1800383df  mov     r9d, eax; char *
0x1800383e2  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800383e9  mov     edx, 967h; void *
0x1800383ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800383f3  nop
  ... truncated ...
```
