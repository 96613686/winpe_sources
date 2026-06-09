# DispatchSiuf(ushort *)

- ea: `0x140005bd4`
- end: `0x140006af7`
- name: `?DispatchSiuf@@YAHPEAG@Z`
- size: `3875`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x140001604`
- `0x140004418`
- `0x140004880`
- `0x140005bd4`
- `0x14000a3c4`
- `0x14000ac50`
- `0x14000ac6c`
- `0x1400195e2`
- `0x140019610`
- `0x1400196d0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140005c37`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140005c37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000616c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000668a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000616c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000668a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140005dfd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140005dfd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140005d92`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140005d92`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
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
      if ( (unsigned int)dword_140028000 > 2 )
      {
        v4 = qword_140028018;
        if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v138 = 0x1000000;
          v137 = 465;
          v136 = "DispatchSiuf";
          v135 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          LODWORD(v127) = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028010,
            (unsigned int)byte_140021E91,
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
          JUMPOUT(0x140006AF6LL);
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
0x140005bd4  push    rbp
0x140005bd6  push    rbx
0x140005bd7  push    rsi
0x140005bd8  push    rdi
0x140005bd9  push    r12
0x140005bdb  push    r13
0x140005bdd  push    r14
0x140005bdf  push    r15
0x140005be1  lea     rbp, [rsp-2728h]
0x140005be9  mov     eax, 2828h
0x140005bee  call    _alloca_probe
0x140005bf3  sub     rsp, rax
0x140005bf6  mov     rax, cs:__security_cookie
0x140005bfd  xor     rax, rsp
0x140005c00  mov     [rbp+2760h+var_50], rax
0x140005c07  mov     rbx, rcx
0x140005c0a  xor     r12d, r12d
0x140005c0d  mov     [rbp+2760h+var_27A8], r12
0x140005c11  xor     edx, edx; Val
0x140005c13  mov     r8d, 2710h; Size
0x140005c19  lea     rcx, [rbp+2760h+sourceString]; void *
0x140005c1d  call    memset_0
0x140005c22  xorps   xmm0, xmm0
0x140005c25  movups  xmmword ptr [rbp+2760h+pclsid.Data1], xmm0
0x140005c29  mov     [rbp+2760h+var_27C8], 4
0x140005c30  lea     rdx, [rbp+2760h+pclsid]; pclsid
0x140005c34  mov     rcx, rbx; lpsz
0x140005c37  call    cs:__imp_CLSIDFromString
0x140005c3e  nop     dword ptr [rax+rax+00h]
0x140005c43  test    eax, eax
0x140005c45  jns     short loc_140005C51
0x140005c47  mov     eax, 5DD0119h
0x140005c4c  jmp     loc_140006A8D
0x140005c51  lea     rdx, [rbp+2760h+sourceString]; lpData
0x140005c55  mov     rcx, rbx; lpSubKey
0x140005c58  call    ?ReadPayloadFromRegistry@@YAHPEBGPEAGK@Z; ReadPayloadFromRegistry(ushort const *,ushort *,ulong)
0x140005c5d  mov     r13d, 5DD011h
0x140005c63  cmp     eax, r13d
0x140005c66  jz      short loc_140005C6D
0x140005c68  jmp     loc_140006A8D
0x140005c6d  lea     r8, [rbp+2760h+var_27C8]
0x140005c71  lea     rdx, [rbp+2760h+var_27A8]
0x140005c75  xor     ecx, ecx
0x140005c77  call    ?OpenAppServiceConnection@@YAJW4AppServiceType@@PEAPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAW4AppServiceConnectionStatus@345@@Z; OpenAppServiceConnection(AppServiceType,Windows::ApplicationModel::AppService::IAppServiceConnection * *,Windows::ApplicationModel::AppService::AppServiceConnectionStatus *)
0x140005c7c  mov     ebx, eax
0x140005c7e  test    eax, eax
0x140005c80  jns     loc_140005D3E
0x140005c86  mov     ecx, cs:dword_140028000
0x140005c8c  cmp     ecx, 2
0x140005c8f  jbe     loc_140005D21
0x140005c95  mov     rdx, cs:qword_140028018
0x140005c9c  mov     rcx, cs:qword_140028010
0x140005ca3  mov     r8, 400000000000h
0x140005cad  test    r8, rcx
0x140005cb0  jz      short loc_140005D21
0x140005cb2  mov     rax, rdx
0x140005cb5  and     rax, r8
0x140005cb8  cmp     rax, rdx
0x140005cbb  jnz     short loc_140005D21
0x140005cbd  mov     [rbp+2760h+var_27C0], 1000000h
0x140005cc5  mov     [rbp+2760h+var_27C8], 1D1h
0x140005ccc  lea     rax, aDispatchsiuf; "DispatchSiuf"
0x140005cd3  mov     [rbp+2760h+var_27D0], rax
0x140005cd7  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140005cde  mov     [rbp+2760h+var_27D8], rax
0x140005ce2  mov     dword ptr [rsp+2860h+var_2810], ebx
0x140005ce6  lea     rax, [rbp+2760h+var_27C0]
0x140005cea  mov     [rsp+2860h+var_2820], rax
0x140005cef  lea     rax, [rbp+2760h+var_27C8]
0x140005cf3  mov     [rsp+2860h+var_2828], rax
0x140005cf8  lea     rax, [rbp+2760h+var_27D0]
0x140005cfc  mov     [rsp+2860h+var_2830], rax
0x140005d01  lea     rax, [rbp+2760h+var_27D8]
0x140005d05  mov     [rsp+2860h+var_2838], rax
0x140005d0a  lea     rax, [rsp+2860h+var_2810]
0x140005d0f  mov     [rsp+2860h+var_2840], rax
0x140005d14  lea     rdx, byte_140021E91
0x140005d1b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140005d20  nop
0x140005d21  mov     rcx, [rbp+2760h+var_27A8]
0x140005d25  test    rcx, rcx
0x140005d28  jz      short loc_140005D37
0x140005d2a  mov     rax, [rcx]
0x140005d2d  mov     rax, [rax+10h]
0x140005d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d36  nop
0x140005d37  mov     eax, ebx
0x140005d39  jmp     loc_140006A8D
0x140005d3e  mov     r15, [rbp+2760h+var_27A8]
0x140005d42  mov     eax, [rbp+2760h+var_27C8]
0x140005d45  test    eax, eax
0x140005d47  jnz     loc_140006A54
0x140005d4d  mov     [rsp+2860h+var_2810], r12
0x140005d52  mov     [rbp+2760h+string], r12
0x140005d56  lea     r9, [rbp+2760h+string]; string
0x140005d5a  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005d5e  lea     edx, [rax+20h]; length
0x140005d61  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x140005d68  call    cs:__imp_WindowsCreateStringReference
0x140005d6f  nop     dword ptr [rax+rax+00h]
0x140005d74  test    eax, eax
0x140005d76  js      loc_140006ABC
0x140005d7c  mov     r14d, 5DD0115h
0x140005d82  lea     r8, [rsp+2860h+var_2810]
0x140005d87  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x140005d8e  mov     rcx, [rbp+2760h+string]
0x140005d92  call    cs:__imp_RoGetActivationFactory
0x140005d99  nop     dword ptr [rax+rax+00h]
0x140005d9e  test    eax, eax
0x140005da0  jns     short loc_140005DC3
0x140005da2  mov     rcx, [rsp+2860h+var_2810]
0x140005da7  test    rcx, rcx
0x140005daa  jz      short loc_140005DBE
0x140005dac  mov     [rsp+2860h+var_2810], r12
0x140005db1  mov     rax, [rcx]
0x140005db4  mov     rax, [rax+10h]
0x140005db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005dbd  nop
0x140005dbe  jmp     loc_140006A75
0x140005dc3  mov     [rsp+2860h+var_2808], r12
0x140005dc8  mov     [rbp+2760h+string], r12
0x140005dcc  lea     r9, [rbp+2760h+string]; string
0x140005dd0  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005dd4  mov     edx, 2Ah ; '*'; length
0x140005dd9  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x140005de0  call    cs:__imp_WindowsCreateStringReference
0x140005de7  nop     dword ptr [rax+rax+00h]
0x140005dec  test    eax, eax
0x140005dee  js      loc_140006AC4
0x140005df4  lea     rdx, [rsp+2860h+var_2808]
0x140005df9  mov     rcx, [rbp+2760h+string]
0x140005dfd  call    cs:__imp_RoActivateInstance
0x140005e04  nop     dword ptr [rax+rax+00h]
0x140005e09  test    eax, eax
0x140005e0b  jns     short loc_140005E4A
0x140005e0d  mov     rcx, [rsp+2860h+var_2808]
0x140005e12  test    rcx, rcx
0x140005e15  jz      short loc_140005E29
0x140005e17  mov     [rsp+2860h+var_2808], r12
0x140005e1c  mov     rax, [rcx]
0x140005e1f  mov     rax, [rax+10h]
0x140005e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e28  nop
0x140005e29  mov     rcx, [rsp+2860h+var_2810]
0x140005e2e  test    rcx, rcx
0x140005e31  jz      short loc_140005E45
0x140005e33  mov     [rsp+2860h+var_2810], r12
0x140005e38  mov     rax, [rcx]
0x140005e3b  mov     rax, [rax+10h]
0x140005e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e44  nop
0x140005e45  jmp     loc_140006A75
0x140005e4a  mov     [rsp+2860h+var_2800], r12
0x140005e4f  mov     rcx, [rsp+2860h+var_2808]
0x140005e54  mov     rax, [rcx]
0x140005e57  lea     r8, [rsp+2860h+var_2800]
0x140005e5c  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x140005e63  mov     rax, [rax]
0x140005e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e6b  nop
0x140005e6c  test    eax, eax
0x140005e6e  jns     short loc_140005EC9
0x140005e70  mov     rcx, [rsp+2860h+var_2800]
0x140005e75  test    rcx, rcx
0x140005e78  jz      short loc_140005E8C
0x140005e7a  mov     [rsp+2860h+var_2800], r12
0x140005e7f  mov     rax, [rcx]
0x140005e82  mov     rax, [rax+10h]
0x140005e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e8b  nop
0x140005e8c  mov     rcx, [rsp+2860h+var_2808]
0x140005e91  test    rcx, rcx
0x140005e94  jz      short loc_140005EA8
0x140005e96  mov     [rsp+2860h+var_2808], r12
0x140005e9b  mov     rax, [rcx]
0x140005e9e  mov     rax, [rax+10h]
0x140005ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ea7  nop
0x140005ea8  mov     rcx, [rsp+2860h+var_2810]
0x140005ead  test    rcx, rcx
0x140005eb0  jz      short loc_140005EC4
0x140005eb2  mov     [rsp+2860h+var_2810], r12
0x140005eb7  mov     rax, [rcx]
0x140005eba  mov     rax, [rax+10h]
0x140005ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ec3  nop
0x140005ec4  jmp     loc_140006A75
0x140005ec9  mov     [rsp+2860h+var_27F8], r12
0x140005ece  lea     rax, [rbp+2760h+sourceString]
0x140005ed2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140005ed6  inc     rdx; int
0x140005ed9  cmp     [rax+rdx*2], r12w
0x140005ede  jnz     short loc_140005ED6
0x140005ee0  mov     eax, 0FFFFFFFFh
0x140005ee5  cmp     rdx, rax
0x140005ee8  ja      loc_140006AB1
0x140005eee  lea     eax, [rdx+1]
0x140005ef1  cmp     eax, edx
0x140005ef3  jb      loc_140006AEC
0x140005ef9  mov     rbx, [rsp+2860h+var_2810]
0x140005efe  mov     rdi, [rbx]
0x140005f01  lea     r9, [rbp+2760h+string]; string
0x140005f05  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005f09  lea     rcx, [rbp+2760h+sourceString]; sourceString
0x140005f0d  call    cs:__imp_WindowsCreateStringReference
0x140005f14  nop     dword ptr [rax+rax+00h]
0x140005f19  test    eax, eax
0x140005f1b  js      loc_140006ACC
0x140005f21  lea     r8, [rsp+2860h+var_27F8]
0x140005f26  mov     rdx, [rbp+2760h+string]
0x140005f2a  mov     rcx, rbx
0x140005f2d  mov     rax, [rdi+90h]
0x140005f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f39  nop
0x140005f3a  test    eax, eax
0x140005f3c  jns     short loc_140005FB3
0x140005f3e  mov     rcx, [rsp+2860h+var_27F8]
0x140005f43  test    rcx, rcx
0x140005f46  jz      short loc_140005F5A
0x140005f48  mov     [rsp+2860h+var_27F8], r12
0x140005f4d  mov     rax, [rcx]
0x140005f50  mov     rax, [rax+10h]
0x140005f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f59  nop
0x140005f5a  mov     rcx, [rsp+2860h+var_2800]
0x140005f5f  test    rcx, rcx
0x140005f62  jz      short loc_140005F76
0x140005f64  mov     [rsp+2860h+var_2800], r12
0x140005f69  mov     rax, [rcx]
0x140005f6c  mov     rax, [rax+10h]
0x140005f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f75  nop
0x140005f76  mov     rcx, [rsp+2860h+var_2808]
0x140005f7b  test    rcx, rcx
0x140005f7e  jz      short loc_140005F92
0x140005f80  mov     [rsp+2860h+var_2808], r12
0x140005f85  mov     rax, [rcx]
0x140005f88  mov     rax, [rax+10h]
0x140005f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f91  nop
0x140005f92  mov     rcx, [rsp+2860h+var_2810]
0x140005f97  test    rcx, rcx
0x140005f9a  jz      short loc_140005FAE
0x140005f9c  mov     [rsp+2860h+var_2810], r12
0x140005fa1  mov     rax, [rcx]
0x140005fa4  mov     rax, [rax+10h]
0x140005fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fad  nop
0x140005fae  jmp     loc_140006A75
0x140005fb3  mov     [rsp+2860h+var_27F0], r12b
0x140005fb8  mov     rbx, [rsp+2860h+var_2800]
0x140005fbd  mov     rdi, [rbx]
0x140005fc0  mov     rsi, [rsp+2860h+var_27F8]
0x140005fc5  mov     [rbp+2760h+string], r12
0x140005fc9  lea     r9, [rbp+2760h+string]; string
0x140005fcd  lea     r8, [rbp+2760h+hstringHeader]; hstringHeader
0x140005fd1  mov     edx, 7; length
0x140005fd6  lea     rcx, sourceString; "Payload"
0x140005fdd  call    cs:__imp_WindowsCreateStringReference
0x140005fe4  nop     dword ptr [rax+rax+00h]
0x140005fe9  test    eax, eax
0x140005feb  js      loc_140006AD4
0x140005ff1  lea     r9, [rsp+2860h+var_27F0]
0x140005ff6  mov     r8, rsi
0x140005ff9  mov     rdx, [rbp+2760h+string]
0x140005ffd  mov     rcx, rbx
0x140006000  mov     rax, [rdi+50h]
0x140006004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006009  nop
0x14000600a  test    eax, eax
0x14000600c  jns     short loc_140006083
0x14000600e  mov     rcx, [rsp+2860h+var_27F8]
0x140006013  test    rcx, rcx
0x140006016  jz      short loc_14000602A
0x140006018  mov     [rsp+2860h+var_27F8], r12
0x14000601d  mov     rax, [rcx]
0x140006020  mov     rax, [rax+10h]
0x140006024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006029  nop
0x14000602a  mov     rcx, [rsp+2860h+var_2800]
0x14000602f  test    rcx, rcx
0x140006032  jz      short loc_140006046
0x140006034  mov     [rsp+2860h+var_2800], r12
0x140006039  mov     rax, [rcx]
0x14000603c  mov     rax, [rax+10h]
0x140006040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006045  nop
0x140006046  mov     rcx, [rsp+2860h+var_2808]
0x14000604b  test    rcx, rcx
0x14000604e  jz      short loc_140006062
0x140006050  mov     [rsp+2860h+var_2808], r12
0x140006055  mov     rax, [rcx]
0x140006058  mov     rax, [rax+10h]
0x14000605c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006061  nop
0x140006062  mov     rcx, [rsp+2860h+var_2810]
0x140006067  test    rcx, rcx
0x14000606a  jz      short loc_14000607E
0x14000606c  mov     [rsp+2860h+var_2810], r12
0x140006071  mov     rax, [rcx]
  ... truncated ...
```
