# DispatchSiuf(ushort *)

- ea: `0x140005b34`
- end: `0x140006a20`
- name: `?DispatchSiuf@@YAHPEAG@Z`
- size: `3820`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c47c`

## callees

- `0x1400015fc`
- `0x140004388`
- `0x140004820`
- `0x140005b34`
- `0x14000a19c`
- `0x14000a9f0`
- `0x14000aa08`
- `0x1400187b2`
- `0x1400187e0`
- `0x1400188a0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140005b97`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140005b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005f19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400060a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400065ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005f19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400060a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400065ba`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140005d45`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140005d45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140005ce6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140005ce6`

## pseudocode

```c
__int64 __fastcall DispatchSiuf(unsigned __int16 *a1)
{
  unsigned int v2; // r8d
  __int64 result; // rax
  __int64 v4; // rdx
  int v5; // ebx
  int v6; // r9d
  __int64 v7; // r15
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  unsigned int v11; // r14d
  _QWORD *v12; // rcx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int (__fastcall ***v16)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v17; // rcx
  unsigned int v18; // r8d
  _QWORD *v19; // rcx
  int (__fastcall ***v20)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v21; // rcx
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rbx
  __int64 v24; // rdi
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  int (__fastcall ***v30)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v31; // rcx
  _QWORD *v32; // rbx
  __int64 v33; // rdi
  __int64 v34; // rsi
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  int (__fastcall ***v40)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rcx
  _QWORD *v45; // rcx
  int (__fastcall ***v46)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v47; // rcx
  _QWORD *v48; // rbx
  __int64 v49; // rdi
  __int64 v50; // rsi
  HRESULT v51; // eax
  int v52; // edx
  unsigned int v53; // r8d
  __int64 v54; // rcx
  __int64 v55; // rcx
  _QWORD *v56; // rcx
  int (__fastcall ***v57)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  _QWORD *v62; // rcx
  int (__fastcall ***v63)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v64; // rcx
  const char *v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  _QWORD *v69; // rcx
  int (__fastcall ***v70)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v71; // rcx
  __int64 v72; // rcx
  const char *v73; // rcx
  const char *v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  _QWORD *v78; // rcx
  int (__fastcall ***v79)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v80; // rcx
  __int64 v81; // rbx
  int (__fastcall *v82)(__int64, GUID *, const char **); // rdi
  const char *v83; // rcx
  __int64 v84; // rcx
  const char *v85; // rcx
  const char *v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  _QWORD *v90; // rcx
  int (__fastcall ***v91)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v92; // rcx
  const char *v93; // rbx
  __int64 v94; // rdi
  HRESULT v95; // eax
  int v96; // edx
  unsigned int v97; // r8d
  int v98; // ebx
  __int64 v99; // rcx
  const char *v100; // rcx
  const char *v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  _QWORD *v105; // rcx
  int (__fastcall ***v106)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v107; // rcx
  int v108; // eax
  __int64 v109; // rcx
  const char *v110; // rcx
  const char *v111; // rcx
  __int64 v112; // rcx
  __int64 v113; // rcx
  __int64 v114; // rcx
  _QWORD *v115; // rcx
  int (__fastcall ***v116)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v117; // rcx
  __int64 v118; // rcx
  const char *v119; // rcx
  const char *v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  _QWORD *v124; // rcx
  int (__fastcall ***v125)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v126; // rcx
  _QWORD *v127; // [rsp+50h] [rbp-B0h] BYREF
  int (__fastcall ***v128)(_QWORD, GUID *, _QWORD **); // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v129; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v130; // [rsp+68h] [rbp-98h] BYREF
  char v131; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v132[7]; // [rsp+71h] [rbp-8Fh] BYREF
  __int64 v133; // [rsp+78h] [rbp-88h] BYREF
  __int64 v134; // [rsp+80h] [rbp-80h] BYREF
  const char *v135; // [rsp+88h] [rbp-78h] BYREF
  const char *v136; // [rsp+90h] [rbp-70h] BYREF
  int v137; // [rsp+98h] [rbp-68h] BYREF
  __int64 v138; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v139; // [rsp+A8h] [rbp-58h] BYREF
  int v140; // [rsp+B0h] [rbp-50h]
  __int64 v141; // [rsp+B8h] [rbp-48h] BYREF
  GUID v142; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-18h] BYREF
  GUID pclsid; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR sourceString[5000]; // [rsp+100h] [rbp+0h] BYREF

  v141 = 0;
  memset_0(sourceString, 0, sizeof(sourceString));
  pclsid = 0;
  v137 = 4;
  if ( CLSIDFromString(a1, &pclsid) < 0 )
    return 98369817;
  result = ReadPayloadFromRegistry(a1, (LPBYTE)sourceString, v2);
  if ( (_DWORD)result == 6148113 )
  {
    v5 = OpenAppServiceConnection(0, &v141, &v137);
    if ( v5 < 0 )
    {
      if ( (unsigned int)dword_140027000 > 2 )
      {
        v4 = qword_140027018;
        if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v138 = 0x1000000;
          v137 = 465;
          v136 = "DispatchSiuf";
          v135 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          LODWORD(v127) = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140027010,
            (unsigned int)byte_140020E89,
            0,
            v6,
            (__int64)&v127,
            (__int64)&v135,
            (__int64)&v136,
            (__int64)&v137,
            (__int64)&v138);
        }
      }
      if ( v141 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v141 + 16LL))(v141, v4);
      return (unsigned int)v5;
    }
    v7 = v141;
    if ( v137 )
    {
      if ( v137 == 1 )
        v11 = 98369811;
      else
        v11 = ((unsigned int)(v137 - 2) > 1) + 98369812;
LABEL_233:
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return v11;
    }
    v127 = 0;
    string = 0;
    v8 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
    if ( v8 >= 0 )
    {
      v11 = 98369813;
      if ( (int)RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v127) < 0 )
      {
        v12 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
        }
        goto LABEL_233;
      }
      v128 = 0;
      string = 0;
      v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string);
      if ( v13 < 0 )
        goto LABEL_239;
      if ( (int)RoActivateInstance(string, &v128) < 0 )
      {
        v16 = v128;
        if ( v128 )
        {
          v128 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v16)[2])(v16);
        }
        v17 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
        }
        goto LABEL_233;
      }
      v129 = 0;
      if ( (**v128)(v128, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v129) < 0 )
      {
        v19 = v129;
        if ( v129 )
        {
          v129 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
        }
        v20 = v128;
        if ( v128 )
        {
          v128 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v20)[2])(v20);
        }
        v21 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
        }
        goto LABEL_233;
      }
      v130 = 0;
      v22 = -1;
      do
        ++v22;
      while ( sourceString[v22] );
      if ( v22 <= 0xFFFFFFFF )
      {
        if ( (int)v22 + 1 < (unsigned int)v22 )
        {
LABEL_244:
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v18);
          JUMPOUT(0x140006A1FLL);
        }
        v23 = v127;
        v24 = *v127;
        v25 = WindowsCreateStringReference(sourceString, v22, &hstringHeader, &string);
        if ( v25 >= 0 )
        {
          if ( (*(int (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v24 + 144))(v23, string, &v130) < 0 )
          {
            v28 = v130;
            if ( v130 )
            {
              v130 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            v29 = v129;
            if ( v129 )
            {
              v129 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
            }
            v30 = v128;
            if ( v128 )
            {
              v128 = 0;
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v30)[2])(v30);
            }
            v31 = v127;
            if ( v127 )
            {
              v127 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
            }
            goto LABEL_233;
          }
          v131 = 0;
          v32 = v129;
          v33 = *v129;
          v34 = v130;
          string = 0;
          v35 = WindowsCreateStringReference(L"Payload", 7u, &hstringHeader, &string);
          if ( v35 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
          }
          else
          {
            if ( (*(int (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v33 + 80))(v32, string, v34, &v131) < 0 )
            {
              v38 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              }
              v39 = v129;
              if ( v129 )
              {
                v129 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
              }
              v40 = v128;
              if ( v128 )
              {
                v128 = 0;
                ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v40)[2])(v40);
              }
              v41 = v127;
              if ( v127 )
              {
                v127 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
              }
              goto LABEL_233;
            }
            v133 = 0;
            v42 = *v127;
            v142 = pclsid;
            if ( (*(int (__fastcall **)(_QWORD *, GUID *, __int64 *))(v42 + 160))(v127, &v142, &v133) < 0 )
            {
              v43 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              }
              v44 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              }
              v45 = v129;
              if ( v129 )
              {
                v129 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
              }
              v46 = v128;
              if ( v128 )
              {
                v128 = 0;
                ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v46)[2])(v46);
              }
              v47 = v127;
              if ( v127 )
              {
                v127 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
              }
              goto LABEL_233;
            }
            v48 = v129;
            v49 = *v129;
            v50 = v133;
            string = 0;
            v51 = WindowsCreateStringReference(L"InstanceId", 0xAu, &hstringHeader, &string);
            if ( v51 >= 0 )
            {
              if ( (*(int (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v49 + 80))(v48, string, v50, &v131) < 0 )
              {
                v54 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                }
                v55 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                }
                v56 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
                }
                v57 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v57)[2])(v57);
                }
                v58 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
                }
                goto LABEL_233;
              }
              v134 = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 88LL))(v7, v128, &v134) < 0 )
              {
                v59 = v134;
                if ( v134 )
                {
                  v134 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
                }
                v60 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                }
                v61 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                }
                v62 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
                }
                v63 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v63)[2])(v63);
                }
                v64 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
                }
                goto LABEL_233;
              }
              wil::WaitForCompletion<Windows::ApplicationModel::AppService::AppServiceResponse *,Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse>>(
                &v136,
                v134);
              v137 = 0;
              if ( (*(int (__fastcall **)(const char *, int *))(*(_QWORD *)v136 + 56LL))(v136, &v137) < 0 )
              {
                v65 = v136;
                if ( v136 )
                {
                  v136 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v65 + 16LL))(v65);
                }
                v66 = v134;
                if ( v134 )
                {
                  v134 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                }
                v67 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
                }
                v68 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
                }
                v69 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v69 + 16LL))(v69);
                }
                v70 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v70)[2])(v70);
                }
                v71 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v71 + 16LL))(v71);
                }
                goto LABEL_233;
              }
              if ( v137 )
              {
LABEL_192:
                v111 = v136;
                if ( v136 )
                {
                  v136 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v111 + 16LL))(v111);
                }
                v112 = v134;
                if ( v134 )
                {
                  v134 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
                }
                v113 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
                }
                v114 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
                }
                v115 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v115 + 16LL))(v115);
                }
                v116 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v116)[2])(v116);
                }
                v117 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v117 + 16LL))(v117);
                }
                goto LABEL_233;
              }
              v135 = 0;
              v138 = 0;
              if ( (*(int (__fastcall **)(const char *, __int64 *))(*(_QWORD *)v136 + 48LL))(v136, &v138) < 0 )
              {
                v72 = v138;
                if ( v138 )
                {
                  v138 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
                }
                v73 = v135;
                if ( v135 )
                {
                  v135 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v73 + 16LL))(v73);
                }
                v74 = v136;
                if ( v136 )
                {
                  v136 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v74 + 16LL))(v74);
                }
                v75 = v134;
                if ( v134 )
                {
                  v134 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
                }
                v76 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
                }
                v77 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
                }
                v78 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v78 + 16LL))(v78);
                }
                v79 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v79)[2])(v79);
                }
                v80 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v80 + 16LL))(v80);
                }
                goto LABEL_233;
              }
              v81 = v138;
              v82 = **(int (__fastcall ***)(__int64, GUID *, const char **))v138;
              v83 = v135;
              if ( v135 )
              {
                v135 = 0;
                (*(void (__fastcall **)(const char *))(*(_QWORD *)v83 + 16LL))(v83);
              }
              if ( v82(v81, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v135) < 0 )
              {
                v84 = v138;
                if ( v138 )
                {
                  v138 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                }
                v85 = v135;
                if ( v135 )
                {
                  v135 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v85 + 16LL))(v85);
                }
                v86 = v136;
                if ( v136 )
                {
                  v136 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v86 + 16LL))(v86);
                }
                v87 = v134;
                if ( v134 )
                {
                  v134 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
                }
                v88 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
                }
                v89 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
                }
                v90 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v90 + 16LL))(v90);
                }
                v91 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v91)[2])(v91);
                }
                v92 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v92 + 16LL))(v92);
                }
                goto LABEL_233;
              }
              v139 = 0;
              v140 = 0;
              v93 = v135;
              v94 = *(_QWORD *)v135;
              *(_QWORD *)&v142.Data1 = &v139;
              *(_QWORD *)v142.Data4 = 0;
              string = 0;
              v95 = WindowsCreateStringReference(L"Status", 6u, &hstringHeader, &string);
              if ( v95 >= 0 )
              {
                v98 = (*(__int64 (__fastcall **)(const char *, HSTRING, unsigned __int8 *))(v94 + 48))(
                        v93,
                        string,
                        v142.Data4);
                string = 0;
                RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v142);
                if ( v98 < 0 )
                {
                  if ( v139 && ((v140 - 3) & 0xFFFFFFFB) == 0 )
                    (*(void (**)(void))(*(_QWORD *)v139 + 16LL))();
                  v99 = v138;
                  if ( v138 )
                  {
                    v138 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
                  }
                  v100 = v135;
                  if ( v135 )
                  {
                    v135 = 0;
                    (*(void (__fastcall **)(const char *))(*(_QWORD *)v100 + 16LL))(v100);
                  }
                  v101 = v136;
                  if ( v136 )
                  {
                    v136 = 0;
                    (*(void (__fastcall **)(const char *))(*(_QWORD *)v101 + 16LL))(v101);
                  }
                  v102 = v134;
                  if ( v134 )
                  {
                    v134 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
                  }
                  v103 = v133;
                  if ( v133 )
                  {
                    v133 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
                  }
                  v104 = v130;
                  if ( v130 )
                  {
                    v130 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
                  }
                  v105 = v129;
                  if ( v129 )
                  {
                    v129 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v105 + 16LL))(v105);
                  }
                  v106 = v128;
                  if ( v128 )
                  {
                    v128 = 0;
                    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v106)[2])(v106);
                  }
                  v107 = v127;
                  if ( v127 )
                  {
                    v127 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v107 + 16LL))(v107);
                  }
                  goto LABEL_233;
                }
                v108 = v140;
                v132[0] = 0;
                if ( v140 == 7 )
                {
                  if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v139 + 144LL))(v139, v132) >= 0 )
                  {
                    if ( v132[0] )
                      v11 = 6148113;
                    if ( v139 && ((v140 - 3) & 0xFFFFFFFB) == 0 )
                      (*(void (**)(void))(*(_QWORD *)v139 + 16LL))();
                    v109 = v138;
                    if ( v138 )
                    {
                      v138 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
                    }
                    v110 = v135;
                    if ( v135 )
                    {
                      v135 = 0;
                      (*(void (__fastcall **)(const char *))(*(_QWORD *)v110 + 16LL))(v110);
                    }
                    goto LABEL_192;
                  }
                  v108 = v140;
                }
                if ( v139 && ((v108 - 3) & 0xFFFFFFFB) == 0 )
                  (*(void (**)(void))(*(_QWORD *)v139 + 16LL))();
                v118 = v138;
                if ( v138 )
                {
                  v138 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
                }
                v119 = v135;
                if ( v135 )
                {
                  v135 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v119 + 16LL))(v119);
                }
                v120 = v136;
                if ( v136 )
                {
                  v136 = 0;
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v120 + 16LL))(v120);
                }
                v121 = v134;
                if ( v134 )
                {
                  v134 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
                }
                v122 = v133;
                if ( v133 )
                {
                  v133 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
                }
                v123 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
                }
                v124 = v129;
                if ( v129 )
                {
                  v129 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v124 + 16LL))(v124);
                }
                v125 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v125)[2])(v125);
                }
                v126 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v126 + 16LL))(v126);
                }
                goto LABEL_233;
              }
              goto LABEL_243;
            }
          }
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v51, v52, v53);
LABEL_243:
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v95, v96, v97);
          goto LABEL_244;
        }
LABEL_240:
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
        __debugbreak();
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v18);
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
LABEL_239:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    goto LABEL_240;
  }
  return result;
}

```

## disassembly

```asm
0x140005b34  push    rbp
0x140005b36  push    rbx
0x140005b37  push    rsi
0x140005b38  push    rdi
0x140005b39  push    r12
0x140005b3b  push    r13
0x140005b3d  push    r14
0x140005b3f  push    r15
0x140005b41  lea     rbp, [rsp-2728h]
0x140005b49  mov     eax, 2828h
0x140005b4e  call    _alloca_probe
0x140005b53  sub     rsp, rax
0x140005b56  mov     rax, cs:__security_cookie
0x140005b5d  xor     rax, rsp
0x140005b60  mov     [rbp+2760h+var_50], rax
0x140005b67  mov     rbx, rcx
0x140005b6a  xor     r12d, r12d
0x140005b6d  mov     [rbp+2760h+var_27A8], r12
0x140005b71  xor     edx, edx; Val
0x140005b73  mov     r8d, 2710h; Size
0x140005b79  lea     rcx, [rbp+2760h+sourceString]; void *
0x140005b7d  call    memset_0
0x140005b82  xorps   xmm0, xmm0
0x140005b85  movups  xmmword ptr [rbp+2760h+pclsid.Data1], xmm0
0x140005b89  mov     [rbp+2760h+var_27C8], 4
0x140005b90  lea     rdx, [rbp+2760h+pclsid]; pclsid
0x140005b94  mov     rcx, rbx; lpsz
0x140005b97  call    cs:__imp_CLSIDFromString
0x140005b9d  test    eax, eax
0x140005b9f  jns     short loc_140005BAB
0x140005ba1  mov     eax, 5DD0119h
0x140005ba6  jmp     loc_1400069B7
0x140005bab  lea     rdx, [rbp+2760h+sourceString]; lpData
0x140005baf  mov     rcx, rbx; lpSubKey
0x140005bb2  call    ?ReadPayloadFromRegistry@@YAHPEBGPEAGK@Z; ReadPayloadFromRegistry(ushort const *,ushort *,ulong)
0x140005bb7  mov     r13d, 5DD011h
0x140005bbd  cmp     eax, r13d
0x140005bc0  jz      short loc_140005BC7
0x140005bc2  jmp     loc_1400069B7
0x140005bc7  lea     r8, [rbp+2760h+var_27C8]
0x140005bcb  lea     rdx, [rbp+2760h+var_27A8]
0x140005bcf  xor     ecx, ecx
0x140005bd1  call    ?OpenAppServiceConnection@@YAJW4AppServiceType@@PEAPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAW4AppServiceConnectionStatus@345@@Z; OpenAppServiceConnection(AppServiceType,Windows::ApplicationModel::AppService::IAppServiceConnection * *,Windows::ApplicationModel::AppService::AppServiceConnectionStatus *)
0x140005bd6  mov     ebx, eax
0x140005bd8  test    eax, eax
0x140005bda  jns     loc_140005C98
0x140005be0  mov     ecx, cs:dword_140027000
0x140005be6  cmp     ecx, 2
0x140005be9  jbe     loc_140005C7B
0x140005bef  mov     rdx, cs:qword_140027018
0x140005bf6  mov     rcx, cs:qword_140027010
0x140005bfd  mov     r8, 400000000000h
0x140005c07  test    r8, rcx
0x140005c0a  jz      short loc_140005C7B
0x140005c0c  mov     rax, rdx
0x140005c0f  and     rax, r8
0x140005c12  cmp     rax, rdx
0x140005c15  jnz     short loc_140005C7B
0x140005c17  mov     [rbp+2760h+var_27C0], 1000000h
0x140005c1f  mov     [rbp+2760h+var_27C8], 1D1h
0x140005c26  lea     rax, aDispatchsiuf; "DispatchSiuf"
0x140005c2d  mov     [rbp+2760h+var_27D0], rax
0x140005c31  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140005c38  mov     [rbp+2760h+var_27D8], rax
0x140005c3c  mov     dword ptr [rsp+2860h+var_2810], ebx
0x140005c40  lea     rax, [rbp+2760h+var_27C0]
0x140005c44  mov     [rsp+2860h+var_2820], rax
0x140005c49  lea     rax, [rbp+2760h+var_27C8]
0x140005c4d  mov     [rsp+2860h+var_2828], rax
0x140005c52  lea     rax, [rbp+2760h+var_27D0]
0x140005c56  mov     [rsp+2860h+var_2830], rax
0x140005c5b  lea     rax, [rbp+2760h+var_27D8]
0x140005c5f  mov     [rsp+2860h+var_2838], rax
0x140005c64  lea     rax, [rsp+2860h+var_2810]
0x140005c69  mov     [rsp+2860h+var_2840], rax
0x140005c6e  lea     rdx, byte_140020E89
0x140005c75  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140005c7a  nop
0x140005c7b  mov     rcx, [rbp+2760h+var_27A8]
0x140005c7f  test    rcx, rcx
0x140005c82  jz      short loc_140005C91
0x140005c84  mov     rax, [rcx]
0x140005c87  mov     rax, [rax+10h]
0x140005c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c90  nop
0x140005c91  mov     eax, ebx
0x140005c93  jmp     loc_1400069B7
0x140005c98  mov     r15, [rbp+2760h+var_27A8]
0x140005c9c  mov     eax, [rbp+2760h+var_27C8]
0x140005c9f  test    eax, eax
0x140005ca1  jnz     loc_14000697E
0x140005ca7  mov     [rsp+2860h+var_2810], r12
0x140005cac  mov     [rbp+2760h+string], r12
0x140005cb0  lea     r9, [rbp+2760h+string]; string
0x140005cb4  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005cb8  lea     edx, [rax+20h]; length
0x140005cbb  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x140005cc2  call    cs:__imp_WindowsCreateStringReference
0x140005cc8  test    eax, eax
0x140005cca  js      loc_1400069E5
0x140005cd0  mov     r14d, 5DD0115h
0x140005cd6  lea     r8, [rsp+2860h+var_2810]
0x140005cdb  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x140005ce2  mov     rcx, [rbp+2760h+string]
0x140005ce6  call    cs:__imp_RoGetActivationFactory
0x140005cec  test    eax, eax
0x140005cee  jns     short loc_140005D11
0x140005cf0  mov     rcx, [rsp+2860h+var_2810]
0x140005cf5  test    rcx, rcx
0x140005cf8  jz      short loc_140005D0C
0x140005cfa  mov     [rsp+2860h+var_2810], r12
0x140005cff  mov     rax, [rcx]
0x140005d02  mov     rax, [rax+10h]
0x140005d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d0b  nop
0x140005d0c  jmp     loc_14000699F
0x140005d11  mov     [rsp+2860h+var_2808], r12
0x140005d16  mov     [rbp+2760h+string], r12
0x140005d1a  lea     r9, [rbp+2760h+string]; string
0x140005d1e  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005d22  mov     edx, 2Ah ; '*'; length
0x140005d27  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x140005d2e  call    cs:__imp_WindowsCreateStringReference
0x140005d34  test    eax, eax
0x140005d36  js      loc_1400069ED
0x140005d3c  lea     rdx, [rsp+2860h+var_2808]
0x140005d41  mov     rcx, [rbp+2760h+string]
0x140005d45  call    cs:__imp_RoActivateInstance
0x140005d4b  test    eax, eax
0x140005d4d  jns     short loc_140005D8C
0x140005d4f  mov     rcx, [rsp+2860h+var_2808]
0x140005d54  test    rcx, rcx
0x140005d57  jz      short loc_140005D6B
0x140005d59  mov     [rsp+2860h+var_2808], r12
0x140005d5e  mov     rax, [rcx]
0x140005d61  mov     rax, [rax+10h]
0x140005d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d6a  nop
0x140005d6b  mov     rcx, [rsp+2860h+var_2810]
0x140005d70  test    rcx, rcx
0x140005d73  jz      short loc_140005D87
0x140005d75  mov     [rsp+2860h+var_2810], r12
0x140005d7a  mov     rax, [rcx]
0x140005d7d  mov     rax, [rax+10h]
0x140005d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d86  nop
0x140005d87  jmp     loc_14000699F
0x140005d8c  mov     [rsp+2860h+var_2800], r12
0x140005d91  mov     rcx, [rsp+2860h+var_2808]
0x140005d96  mov     rax, [rcx]
0x140005d99  lea     r8, [rsp+2860h+var_2800]
0x140005d9e  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x140005da5  mov     rax, [rax]
0x140005da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005dad  nop
0x140005dae  test    eax, eax
0x140005db0  jns     short loc_140005E0B
0x140005db2  mov     rcx, [rsp+2860h+var_2800]
0x140005db7  test    rcx, rcx
0x140005dba  jz      short loc_140005DCE
0x140005dbc  mov     [rsp+2860h+var_2800], r12
0x140005dc1  mov     rax, [rcx]
0x140005dc4  mov     rax, [rax+10h]
0x140005dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005dcd  nop
0x140005dce  mov     rcx, [rsp+2860h+var_2808]
0x140005dd3  test    rcx, rcx
0x140005dd6  jz      short loc_140005DEA
0x140005dd8  mov     [rsp+2860h+var_2808], r12
0x140005ddd  mov     rax, [rcx]
0x140005de0  mov     rax, [rax+10h]
0x140005de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005de9  nop
0x140005dea  mov     rcx, [rsp+2860h+var_2810]
0x140005def  test    rcx, rcx
0x140005df2  jz      short loc_140005E06
0x140005df4  mov     [rsp+2860h+var_2810], r12
0x140005df9  mov     rax, [rcx]
0x140005dfc  mov     rax, [rax+10h]
0x140005e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e05  nop
0x140005e06  jmp     loc_14000699F
0x140005e0b  mov     [rsp+2860h+var_27F8], r12
0x140005e10  lea     rax, [rbp+2760h+sourceString]
0x140005e14  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140005e18  inc     rdx; int
0x140005e1b  cmp     [rax+rdx*2], r12w
0x140005e20  jnz     short loc_140005E18
0x140005e22  mov     eax, 0FFFFFFFFh
0x140005e27  cmp     rdx, rax
0x140005e2a  ja      loc_1400069DA
0x140005e30  lea     eax, [rdx+1]
0x140005e33  cmp     eax, edx
0x140005e35  jb      loc_140006A15
0x140005e3b  mov     rbx, [rsp+2860h+var_2810]
0x140005e40  mov     rdi, [rbx]
0x140005e43  lea     r9, [rbp+2760h+string]; string
0x140005e47  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005e4b  lea     rcx, [rbp+2760h+sourceString]; sourceString
0x140005e4f  call    cs:__imp_WindowsCreateStringReference
0x140005e55  test    eax, eax
0x140005e57  js      loc_1400069F5
0x140005e5d  lea     r8, [rsp+2860h+var_27F8]
0x140005e62  mov     rdx, [rbp+2760h+string]
0x140005e66  mov     rcx, rbx
0x140005e69  mov     rax, [rdi+90h]
0x140005e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e75  nop
0x140005e76  test    eax, eax
0x140005e78  jns     short loc_140005EEF
0x140005e7a  mov     rcx, [rsp+2860h+var_27F8]
0x140005e7f  test    rcx, rcx
0x140005e82  jz      short loc_140005E96
0x140005e84  mov     [rsp+2860h+var_27F8], r12
0x140005e89  mov     rax, [rcx]
0x140005e8c  mov     rax, [rax+10h]
0x140005e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e95  nop
0x140005e96  mov     rcx, [rsp+2860h+var_2800]
0x140005e9b  test    rcx, rcx
0x140005e9e  jz      short loc_140005EB2
0x140005ea0  mov     [rsp+2860h+var_2800], r12
0x140005ea5  mov     rax, [rcx]
0x140005ea8  mov     rax, [rax+10h]
0x140005eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eb1  nop
0x140005eb2  mov     rcx, [rsp+2860h+var_2808]
0x140005eb7  test    rcx, rcx
0x140005eba  jz      short loc_140005ECE
0x140005ebc  mov     [rsp+2860h+var_2808], r12
0x140005ec1  mov     rax, [rcx]
0x140005ec4  mov     rax, [rax+10h]
0x140005ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ecd  nop
0x140005ece  mov     rcx, [rsp+2860h+var_2810]
0x140005ed3  test    rcx, rcx
0x140005ed6  jz      short loc_140005EEA
0x140005ed8  mov     [rsp+2860h+var_2810], r12
0x140005edd  mov     rax, [rcx]
0x140005ee0  mov     rax, [rax+10h]
0x140005ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ee9  nop
0x140005eea  jmp     loc_14000699F
0x140005eef  mov     [rsp+2860h+var_27F0], r12b
0x140005ef4  mov     rbx, [rsp+2860h+var_2800]
0x140005ef9  mov     rdi, [rbx]
0x140005efc  mov     rsi, [rsp+2860h+var_27F8]
0x140005f01  mov     [rbp+2760h+string], r12
0x140005f05  lea     r9, [rbp+2760h+string]; string
0x140005f09  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005f0d  mov     edx, 7; length
0x140005f12  lea     rcx, sourceString; "Payload"
0x140005f19  call    cs:__imp_WindowsCreateStringReference
0x140005f1f  test    eax, eax
0x140005f21  js      loc_1400069FD
0x140005f27  lea     r9, [rsp+2860h+var_27F0]
0x140005f2c  mov     r8, rsi
0x140005f2f  mov     rdx, [rbp+2760h+string]
0x140005f33  mov     rcx, rbx
0x140005f36  mov     rax, [rdi+50h]
0x140005f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f3f  nop
0x140005f40  test    eax, eax
0x140005f42  jns     short loc_140005FB9
0x140005f44  mov     rcx, [rsp+2860h+var_27F8]
0x140005f49  test    rcx, rcx
0x140005f4c  jz      short loc_140005F60
0x140005f4e  mov     [rsp+2860h+var_27F8], r12
0x140005f53  mov     rax, [rcx]
0x140005f56  mov     rax, [rax+10h]
0x140005f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f5f  nop
0x140005f60  mov     rcx, [rsp+2860h+var_2800]
0x140005f65  test    rcx, rcx
0x140005f68  jz      short loc_140005F7C
0x140005f6a  mov     [rsp+2860h+var_2800], r12
0x140005f6f  mov     rax, [rcx]
0x140005f72  mov     rax, [rax+10h]
0x140005f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f7b  nop
0x140005f7c  mov     rcx, [rsp+2860h+var_2808]
0x140005f81  test    rcx, rcx
0x140005f84  jz      short loc_140005F98
0x140005f86  mov     [rsp+2860h+var_2808], r12
0x140005f8b  mov     rax, [rcx]
0x140005f8e  mov     rax, [rax+10h]
0x140005f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f97  nop
0x140005f98  mov     rcx, [rsp+2860h+var_2810]
0x140005f9d  test    rcx, rcx
0x140005fa0  jz      short loc_140005FB4
0x140005fa2  mov     [rsp+2860h+var_2810], r12
0x140005fa7  mov     rax, [rcx]
0x140005faa  mov     rax, [rax+10h]
0x140005fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fb3  nop
0x140005fb4  jmp     loc_14000699F
0x140005fb9  mov     [rsp+2860h+var_27E8], r12
0x140005fbe  mov     rcx, [rsp+2860h+var_2810]
0x140005fc3  mov     rax, [rcx]
  ... truncated ...
```
