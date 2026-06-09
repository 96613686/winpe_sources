# EnableTaskTriggerInternal(TaskTriggerOption,ushort const *)

- ea: `0x180003aa0`
- end: `0x18000441c`
- name: `?EnableTaskTriggerInternal@@YAJW4TaskTriggerOption@@PEBG@Z`
- size: `2428`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180003a7c`

## callees

- `0x180002e88`
- `0x180003134`
- `0x1800032f8`
- `0x180003aa0`
- `0x180006470`
- `0x1800065e4`
- `0x180006688`
- `0x1800068b4`
- `0x180039010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003ffc`
- `msvcrt!_wcsicmp` at `0x180003ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003db4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000414d`
- `OLEAUT32!__imp_SysFreeString` at `0x180004214`
- `OLEAUT32!__imp_SysFreeString` at `0x180004249`
- `OLEAUT32!__imp_SysFreeString` at `0x180004260`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003db4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000414d`
- `OLEAUT32!__imp_SysFreeString` at `0x180004214`
- `OLEAUT32!__imp_SysFreeString` at `0x180004249`
- `OLEAUT32!__imp_SysFreeString` at `0x180004260`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003b89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003b89`

## string_xrefs

- `0x180003adc`: `EnableTaskTriggerInternal`
- `0x180003bc2`: `Hr = TaskService.CoCreateInstance( CLSID_TaskScheduler )`
- `0x180003c59`: `Hr = TaskService->Connect( EmptyVariant, EmptyVariant, EmptyVariant, EmptyVariant )`
- `0x180003cde`: `Hr = TaskService->GetFolder( TaskPath, &TaskFolder )`
- `0x180003d77`: `Hr = TaskFolder->GetTask( TaskName, &RegisteredTask )`
- `0x180003e0e`: `Hr = RegisteredTask->get_Definition( &TaskDefinition )`
- `0x180003e7b`: `Hr = TaskDefinition->get_Triggers( &TriggerCollection )`
- `0x1800041c2`: `Hr = TaskDefinition->put_Triggers( TriggerCollection )`
- `0x18000431b`: `Hr = TaskFolder->RegisterTaskDefinition( TaskName, TaskDefinition, TASK_UPDATE | TASK_IGNORE_REGISTRATION_TRIGGERS, EmptyVariant, EmptyVariant, TASK_LOGON_NONE, EmptyVariant, &NewRegisteredTask )`

## pseudocode

```c
__int64 __fastcall EnableTaskTriggerInternal(int a1, __int64 a2)
{
  __int64 v3; // r8
  USHORT v4; // dx
  WORD Length; // cx
  VARTYPE v6; // ax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  int v10; // edx
  const char *v11; // r9
  OLECHAR *v12; // rbx
  int v13; // eax
  int v14; // edi
  OLECHAR *v15; // rdi
  int v16; // eax
  int v17; // esi
  int v18; // eax
  _QWORD *v19; // rcx
  int v20; // edx
  const char *v21; // r9
  char v22; // r12
  int v23; // esi
  int v24; // eax
  int v25; // eax
  unsigned __int16 v26; // r14
  int v27; // r8d
  int v28; // r15d
  int v29; // eax
  int v30; // r8d
  PVOID *v31; // rcx
  int v32; // eax
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-98h] BYREF
  const char *v38; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v39; // [rsp+78h] [rbp-88h]
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v42[2]; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v43; // [rsp+A0h] [rbp-60h] BYREF
  BSTR bstrString[2]; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v45; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v46; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG v47[3]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v48; // [rsp+178h] [rbp+78h] BYREF
  int v49; // [rsp+180h] [rbp+80h] BYREF
  __int64 v50; // [rsp+188h] [rbp+88h] BYREF

  v48 = a2;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v3 + 16) = "EnableTaskTriggerInternal";
  v38 = "EnableTaskTriggerInternal";
  v4 = ++*(_WORD *)(v3 + 8);
  Length = GlobalIndentString.Length;
  v6 = GlobalIndentString.Length;
  if ( v4 < GlobalIndentString.Length )
    v6 = *(_WORD *)(v3 + 8);
  v43.vt = v6;
  if ( v4 < GlobalIndentString.Length )
    Length = v4;
  v43.wReserved1 = Length;
  v43.decVal.Hi32 = 0;
  v43.llVal = (LONGLONG)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"EnableTaskTriggerInternal");
  }
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_TaskScheduler, 0, 0x17u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  v8 = v7;
  v39 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_109;
    }
    v10 = 71;
    v11 = "Hr = TaskService.CoCreateInstance( CLSID_TaskScheduler )";
    goto LABEL_19;
  }
  v43 = pvarg;
  v45 = pvarg;
  v46 = pvarg;
  v47[0] = pvarg;
  v7 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         v47,
         &v46,
         &v45,
         &v43);
  v8 = v7;
  v39 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_109;
    }
    v10 = 72;
    v11 = "Hr = TaskService->Connect( EmptyVariant, EmptyVariant, EmptyVariant, EmptyVariant )";
LABEL_19:
    WPP_SF_sd(v9[2], v10, (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (_DWORD)v11, v7);
    goto LABEL_109;
  }
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"\\Microsoft\\Windows\\Data Integrity Scan");
  v50 = 0;
  v12 = bstrString[0];
  v13 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, bstrString[0], &v50);
  v14 = v13;
  v39 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        (unsigned int)"Hr = TaskService->GetFolder( TaskPath, &TaskFolder )",
        v13);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
    SysFreeString(v12);
    v8 = v14;
    goto LABEL_109;
  }
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v43, L"Data Integrity Check And Scan");
  v36 = 0;
  v15 = *(OLECHAR **)&v43.vt;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v50 + 104LL))(v50, *(_QWORD *)&v43.vt, &v36);
  v17 = v16;
  v39 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        (unsigned int)"Hr = TaskFolder->GetTask( TaskName, &RegisteredTask )",
        v16);
    }
    goto LABEL_31;
  }
  v34 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 152LL))(v36, &v34);
  v17 = v18;
  v39 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        (unsigned int)"Hr = RegisteredTask->get_Definition( &TaskDefinition )",
        v18);
    }
    goto LABEL_37;
  }
  v35 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 72LL))(v34, &v35);
  v39 = v17;
  if ( v17 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_44;
    }
    v20 = 76;
    v21 = "Hr = TaskDefinition->get_Triggers( &TriggerCollection )";
    goto LABEL_43;
  }
  v49 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 56LL))(v35, &v49);
  v39 = v17;
  if ( v17 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_44;
    }
    v20 = 77;
    v21 = "Hr = TriggerCollection->get_Count( &TriggerCount )";
LABEL_43:
    WPP_SF_sd(v19[2], v20, (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (_DWORD)v21, v17);
    goto LABEL_44;
  }
  v22 = 0;
  v23 = 1;
  if ( v49 < 1 )
  {
LABEL_104:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    }
LABEL_108:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    SysFreeString(v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
    SysFreeString(v12);
    v8 = 0;
    goto LABEL_109;
  }
  do
  {
    v40 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 64LL))(v35, (unsigned int)v23, &v40);
    v39 = v24;
    if ( v24 >= 0 )
    {
      String1 = 0;
      v25 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v40 + 64LL))(v40, &String1);
      v39 = v25;
      if ( v25 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
            (unsigned int)"Hr = Trigger->get_Id( &TriggerId )",
            v25);
        }
        goto LABEL_80;
      }
      if ( !String1 || _wcsicmp(String1, L"Resume") )
      {
LABEL_80:
        SysFreeString(String1);
        goto LABEL_81;
      }
      LOWORD(v48) = 0;
      v26 = (a1 != 1) - 1;
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 144LL))(v40, &v48);
      v39 = v28;
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
            (unsigned int)"Hr = Trigger->get_Enabled( &CurrentValue )",
            v28);
        }
        SysFreeString(String1);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
        SysFreeString(v15);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
        SysFreeString(v12);
        v8 = v28;
        goto LABEL_109;
      }
      if ( v26 == (_WORD)v48 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, v27, (_DWORD)String1, v23, v49, a1);
        }
        goto LABEL_80;
      }
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 152LL))(v40, v26);
      v39 = v29;
      if ( v29 < 0 )
      {
        v31 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_75:
          v22 = 1;
          goto LABEL_80;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_71:
          if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 && *((_BYTE *)v31 + 25) >= 4u )
            WPP_SF_SDDD((unsigned int)v31[2], 82, v30, (_DWORD)String1, v23, v49, a1);
          goto LABEL_75;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
          (unsigned int)"Hr = Trigger->put_Enabled( NewValue )",
          v29);
      }
      v31 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_71;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        (unsigned int)"Hr = TriggerCollection->get_Item( Index, &Trigger )",
        v24);
    }
LABEL_81:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    ++v23;
  }
  while ( v23 <= v49 );
  if ( !v22 )
    goto LABEL_104;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 80LL))(v34, v35);
  v39 = v17;
  if ( v17 >= 0 )
  {
    v42[0] = 0;
    v47[0] = pvarg;
    v46 = pvarg;
    v45 = pvarg;
    v32 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, _DWORD, VARIANTARG *, _QWORD *))(*(_QWORD *)v50 + 136LL))(
            v50,
            v15,
            v34,
            36,
            &v45,
            &v46,
            0,
            v47,
            v42);
    v17 = v32;
    v39 = v32;
    if ( v32 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
          (unsigned int)"Hr = TaskFolder->RegisterTaskDefinition( TaskName, TaskDefinition, TASK_UPDATE | TASK_IGNORE_REG"
                        "ISTRATION_TRIGGERS, EmptyVariant, EmptyVariant, TASK_LOGON_NONE, EmptyVariant, &NewRegisteredTask )",
          v32);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v42);
      goto LABEL_44;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v42);
    goto LABEL_108;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = 84;
    v21 = "Hr = TaskDefinition->put_Triggers( TriggerCollection )";
    goto LABEL_43;
  }
LABEL_44:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
LABEL_37:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
LABEL_31:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  SysFreeString(v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
  SysFreeString(v12);
  v8 = v17;
LABEL_109:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  CHResultImp::~CHResultImp((CHResultImp *)&v38);
  return v8;
}

```

## disassembly

```asm
0x180003aa0  mov     [rsp-8+arg_0], rbx
0x180003aa5  mov     [rsp-8+arg_8], rdx
0x180003aaa  push    rbp
0x180003aab  push    rsi
0x180003aac  push    rdi
0x180003aad  push    r12
0x180003aaf  push    r13
0x180003ab1  push    r14
0x180003ab3  push    r15
0x180003ab5  lea     rbp, [rsp-30h]
0x180003aba  sub     rsp, 130h
0x180003ac1  mov     r13d, ecx
0x180003ac4  mov     edx, cs:_tls_index
0x180003aca  mov     rax, gs:58h
0x180003ad3  mov     r8, [rax+rdx*8]
0x180003ad7  mov     eax, 10h
0x180003adc  lea     r9, aEnabletasktrig; "EnableTaskTriggerInternal"
0x180003ae3  mov     [rax+r8], r9
0x180003ae7  mov     [rsp+160h+var_F0], r9
0x180003aec  mov     edx, 8
0x180003af1  mov     r15d, 1
0x180003af7  add     [rdx+r8], r15w
0x180003afc  movzx   edx, word ptr [rdx+r8]
0x180003b01  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180003b08  movzx   eax, cx
0x180003b0b  cmp     dx, cx
0x180003b0e  cmovb   ax, dx
0x180003b12  mov     word ptr [rbp+60h+var_C0], ax
0x180003b16  cmovb   cx, dx
0x180003b1a  mov     word ptr [rbp+60h+var_C0+2], cx
0x180003b1e  xor     eax, eax
0x180003b20  mov     dword ptr [rbp+60h+var_C0+4], eax
0x180003b23  mov     rax, cs:off_180047060; "                                       "...
0x180003b2a  mov     [rbp+60h+var_C0+8], rax
0x180003b2e  lea     r14, WPP_GLOBAL_Control
0x180003b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b3c  cmp     rcx, r14
0x180003b3f  jz      short loc_180003B64
0x180003b41  test    [rcx+1Ch], r15b
0x180003b45  jz      short loc_180003B64
0x180003b47  cmp     byte ptr [rcx+19h], 5
0x180003b4b  jb      short loc_180003B64
0x180003b4d  lea     edx, [r15+0Ch]
0x180003b51  mov     [rsp+160h+ppv], r9; __int64
0x180003b56  lea     r9, [rbp+60h+var_C0]
0x180003b5a  mov     rcx, [rcx+10h]; LoggerHandle
0x180003b5e  call    WPP_SF_aZs
0x180003b63  nop
0x180003b64  mov     [rbp+60h+var_D8], 0
0x180003b6c  lea     rax, [rbp+60h+var_D8]
0x180003b70  mov     [rsp+160h+ppv], rax; ppv
0x180003b75  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180003b7c  xor     edx, edx; pUnkOuter
0x180003b7e  lea     r8d, [rdx+17h]; dwClsContext
0x180003b82  lea     rcx, CLSID_TaskScheduler; rclsid
0x180003b89  call    cs:__imp_CoCreateInstance
0x180003b8f  mov     ebx, eax
0x180003b91  mov     [rsp+160h+var_E8], eax
0x180003b95  test    eax, eax
0x180003b97  jns     short loc_180003BCE
0x180003b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ba0  cmp     rcx, r14
0x180003ba3  jz      loc_1800043EB
0x180003ba9  test    [rcx+1Ch], r15b
0x180003bad  jz      loc_1800043EB
0x180003bb3  cmp     byte ptr [rcx+19h], 2
0x180003bb7  jb      loc_1800043EB
0x180003bbd  mov     edx, 47h ; 'G'
0x180003bc2  lea     r9, aHrTaskserviceC_0; "Hr = TaskService.CoCreateInstance( CLSI"...
0x180003bc9  jmp     loc_180003C60
0x180003bce  mov     rcx, [rbp+60h+var_D8]
0x180003bd2  movups  xmm1, xmmword ptr cs:pvarg
0x180003bd9  movsd   xmm0, qword ptr cs:pvarg+10h
0x180003be1  movaps  xmmword ptr [rbp+60h+var_C0], xmm1
0x180003be5  movsd   [rbp+60h+var_B0], xmm0
0x180003bea  movaps  [rbp+60h+var_90], xmm1
0x180003bee  movsd   [rbp+60h+var_80], xmm0
0x180003bf3  movaps  [rbp+60h+var_70], xmm1
0x180003bf7  movsd   [rbp+60h+var_60], xmm0
0x180003bfc  movaps  [rbp+60h+var_50], xmm1
0x180003c00  movsd   [rbp+60h+var_40], xmm0
0x180003c05  mov     rax, [rcx]
0x180003c08  lea     rdx, [rbp+60h+var_C0]
0x180003c0c  mov     [rsp+160h+ppv], rdx
0x180003c11  lea     r9, [rbp+60h+var_90]
0x180003c15  lea     r8, [rbp+60h+var_70]
0x180003c19  lea     rdx, [rbp+60h+var_50]
0x180003c1d  mov     rax, [rax+50h]
0x180003c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c26  mov     ebx, eax
0x180003c28  mov     [rsp+160h+var_E8], eax
0x180003c2c  test    eax, eax
0x180003c2e  jns     short loc_180003C79
0x180003c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c37  cmp     rcx, r14
0x180003c3a  jz      loc_1800043EB
0x180003c40  test    [rcx+1Ch], r15b
0x180003c44  jz      loc_1800043EB
0x180003c4a  cmp     byte ptr [rcx+19h], 2
0x180003c4e  jb      loc_1800043EB
0x180003c54  mov     edx, 48h ; 'H'
0x180003c59  lea     r9, aHrTaskserviceC; "Hr = TaskService->Connect( EmptyVariant"...
0x180003c60  mov     dword ptr [rsp+160h+ppv], eax
0x180003c64  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180003c6b  mov     rcx, [rcx+10h]
0x180003c6f  call    WPP_SF_sd
0x180003c74  jmp     loc_1800043EB
0x180003c79  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Data Integrity Sc"...
0x180003c80  lea     rcx, [rbp+60h+bstrString]; this
0x180003c84  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180003c89  nop
0x180003c8a  mov     [rbp+60h+arg_18], 0
0x180003c95  mov     rcx, [rbp+60h+var_D8]
0x180003c99  mov     rax, [rcx]
0x180003c9c  lea     r8, [rbp+60h+arg_18]
0x180003ca3  mov     rbx, [rbp+60h+bstrString]
0x180003ca7  mov     rdx, rbx
0x180003caa  mov     rax, [rax+38h]
0x180003cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb3  mov     edi, eax
0x180003cb5  mov     [rsp+160h+var_E8], eax
0x180003cb9  test    eax, eax
0x180003cbb  jns     short loc_180003D13
0x180003cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cc4  cmp     rcx, r14
0x180003cc7  jz      short loc_180003CF6
0x180003cc9  test    [rcx+1Ch], r15b
0x180003ccd  jz      short loc_180003CF6
0x180003ccf  cmp     byte ptr [rcx+19h], 2
0x180003cd3  jb      short loc_180003CF6
0x180003cd5  mov     edx, 49h ; 'I'
0x180003cda  mov     dword ptr [rsp+160h+ppv], eax
0x180003cde  lea     r9, aHrTaskserviceG; "Hr = TaskService->GetFolder( TaskPath, "...
0x180003ce5  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180003cec  mov     rcx, [rcx+10h]
0x180003cf0  call    WPP_SF_sd
0x180003cf5  nop
0x180003cf6  lea     rcx, [rbp+60h+arg_18]
0x180003cfd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003d02  nop
0x180003d03  mov     rcx, rbx; bstrString
0x180003d06  call    cs:__imp_SysFreeString
0x180003d0c  mov     ebx, edi
0x180003d0e  jmp     loc_1800043EB
0x180003d13  lea     rdx, aDataIntegrityC; "Data Integrity Check And Scan"
0x180003d1a  lea     rcx, [rbp+60h+var_C0]; this
0x180003d1e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180003d23  nop
0x180003d24  mov     [rsp+160h+var_100], 0
0x180003d2d  mov     rcx, [rbp+60h+arg_18]
0x180003d34  mov     rax, [rcx]
0x180003d37  lea     r8, [rsp+160h+var_100]
0x180003d3c  mov     rdi, [rbp+60h+var_C0]
0x180003d40  mov     rdx, rdi
0x180003d43  mov     rax, [rax+68h]
0x180003d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4c  mov     esi, eax
0x180003d4e  mov     [rsp+160h+var_E8], eax
0x180003d52  test    eax, eax
0x180003d54  jns     short loc_180003DC1
0x180003d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d5d  cmp     rcx, r14
0x180003d60  jz      short loc_180003D8F
0x180003d62  test    [rcx+1Ch], r15b
0x180003d66  jz      short loc_180003D8F
0x180003d68  cmp     byte ptr [rcx+19h], 2
0x180003d6c  jb      short loc_180003D8F
0x180003d6e  mov     edx, 4Ah ; 'J'
0x180003d73  mov     dword ptr [rsp+160h+ppv], eax
0x180003d77  lea     r9, aHrTaskfolderGe; "Hr = TaskFolder->GetTask( TaskName, &Re"...
0x180003d7e  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180003d85  mov     rcx, [rcx+10h]
0x180003d89  call    WPP_SF_sd
0x180003d8e  nop
0x180003d8f  lea     rcx, [rsp+160h+var_100]
0x180003d94  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003d99  nop
0x180003d9a  mov     rcx, rdi; bstrString
0x180003d9d  call    cs:__imp_SysFreeString
0x180003da3  nop
0x180003da4  lea     rcx, [rbp+60h+arg_18]
0x180003dab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003db0  nop
0x180003db1  mov     rcx, rbx; bstrString
0x180003db4  call    cs:__imp_SysFreeString
0x180003dba  mov     ebx, esi
0x180003dbc  jmp     loc_1800043EB
0x180003dc1  mov     [rsp+160h+var_110], 0
0x180003dca  mov     rcx, [rsp+160h+var_100]
0x180003dcf  mov     rax, [rcx]
0x180003dd2  lea     rdx, [rsp+160h+var_110]
0x180003dd7  mov     rax, [rax+98h]
0x180003dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de3  mov     esi, eax
0x180003de5  mov     [rsp+160h+var_E8], eax
0x180003de9  test    eax, eax
0x180003deb  jns     short loc_180003E35
0x180003ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180003df4  cmp     rcx, r14
0x180003df7  jz      short loc_180003E26
0x180003df9  test    [rcx+1Ch], r15b
0x180003dfd  jz      short loc_180003E26
0x180003dff  cmp     byte ptr [rcx+19h], 2
0x180003e03  jb      short loc_180003E26
0x180003e05  mov     edx, 4Bh ; 'K'
0x180003e0a  mov     dword ptr [rsp+160h+ppv], eax
0x180003e0e  lea     r9, aHrRegisteredta; "Hr = RegisteredTask->get_Definition( &T"...
0x180003e15  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180003e1c  mov     rcx, [rcx+10h]
0x180003e20  call    WPP_SF_sd
0x180003e25  nop
0x180003e26  lea     rcx, [rsp+160h+var_110]
0x180003e2b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003e30  jmp     loc_180003D8F
0x180003e35  mov     [rsp+160h+var_108], 0
0x180003e3e  mov     rcx, [rsp+160h+var_110]
0x180003e43  mov     rax, [rcx]
0x180003e46  lea     rdx, [rsp+160h+var_108]
0x180003e4b  mov     rax, [rax+48h]
0x180003e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e54  mov     esi, eax
0x180003e56  mov     [rsp+160h+var_E8], eax
0x180003e5a  test    eax, eax
0x180003e5c  jns     short loc_180003EA3
0x180003e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e65  cmp     rcx, r14
0x180003e68  jz      short loc_180003E97
0x180003e6a  test    [rcx+1Ch], r15b
0x180003e6e  jz      short loc_180003E97
0x180003e70  cmp     byte ptr [rcx+19h], 2
0x180003e74  jb      short loc_180003E97
0x180003e76  mov     edx, 4Ch ; 'L'
0x180003e7b  lea     r9, aHrTaskdefiniti; "Hr = TaskDefinition->get_Triggers( &Tri"...
0x180003e82  mov     dword ptr [rsp+160h+ppv], esi
0x180003e86  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180003e8d  mov     rcx, [rcx+10h]
0x180003e91  call    WPP_SF_sd
0x180003e96  nop
0x180003e97  lea     rcx, [rsp+160h+var_108]
0x180003e9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003ea1  jmp     short loc_180003E26
0x180003ea3  mov     [rbp+60h+arg_10], 0
0x180003ead  mov     rcx, [rsp+160h+var_108]
0x180003eb2  mov     rax, [rcx]
0x180003eb5  lea     rdx, [rbp+60h+arg_10]
0x180003ebc  mov     rax, [rax+38h]
0x180003ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec5  mov     esi, eax
0x180003ec7  mov     [rsp+160h+var_E8], eax
0x180003ecb  test    eax, eax
0x180003ecd  jns     short loc_180003EF5
0x180003ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ed6  cmp     rcx, r14
0x180003ed9  jz      short loc_180003E97
0x180003edb  test    [rcx+1Ch], r15b
0x180003edf  jz      short loc_180003E97
0x180003ee1  cmp     byte ptr [rcx+19h], 2
0x180003ee5  jb      short loc_180003E97
0x180003ee7  mov     edx, 4Dh ; 'M'
0x180003eec  lea     r9, aHrTriggercolle_0; "Hr = TriggerCollection->get_Count( &Tri"...
0x180003ef3  jmp     short loc_180003E82
0x180003ef5  xor     r12b, r12b
0x180003ef8  mov     esi, r15d
0x180003efb  cmp     [rbp+60h+arg_10], r15d
0x180003f02  jl      loc_18000437A
0x180003f08  mov     [rbp+60h+var_E0], 0
0x180003f10  mov     rcx, [rsp+160h+var_108]
0x180003f15  mov     rax, [rcx]
0x180003f18  lea     r8, [rbp+60h+var_E0]
0x180003f1c  mov     edx, esi
0x180003f1e  mov     rax, [rax+40h]
0x180003f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f27  mov     [rsp+160h+var_E8], eax
0x180003f2b  test    eax, eax
0x180003f2d  jns     short loc_180003F78
0x180003f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f36  cmp     rcx, r14
0x180003f39  jz      loc_180004154
0x180003f3f  test    [rcx+1Ch], r15b
0x180003f43  jz      loc_180004154
0x180003f49  cmp     byte ptr [rcx+19h], 2
0x180003f4d  jb      loc_180004154
0x180003f53  mov     edx, 4Eh ; 'N'
0x180003f58  mov     dword ptr [rsp+160h+ppv], eax
0x180003f5c  lea     r9, aHrTriggercolle; "Hr = TriggerCollection->get_Item( Index"...
0x180003f63  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180003f6a  mov     rcx, [rcx+10h]
0x180003f6e  call    WPP_SF_sd
0x180003f73  jmp     loc_180004154
0x180003f78  mov     [rsp+160h+String1], 0
0x180003f81  mov     rcx, [rbp+60h+var_E0]
0x180003f85  mov     rax, [rcx]
0x180003f88  lea     rdx, [rsp+160h+String1]
0x180003f8d  mov     rax, [rax+40h]
0x180003f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f96  mov     [rsp+160h+var_E8], eax
0x180003f9a  test    eax, eax
0x180003f9c  jns     short loc_180003FE7
0x180003f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fa5  cmp     rcx, r14
  ... truncated ...
```
