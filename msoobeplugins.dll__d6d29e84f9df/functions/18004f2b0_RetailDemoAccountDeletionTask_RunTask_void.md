# RetailDemoAccountDeletionTask::RunTask(void)

- ea: `0x18004f2b0`
- end: `0x18004f650`
- name: `?RunTask@RetailDemoAccountDeletionTask@@UEAAJXZ`
- size: `928`
- prototype: `__int64 __fastcall(RetailDemoAccountDeletionTask *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180018a04`
- `0x18001e9a4`
- `0x180021988`
- `0x180023574`
- `0x18002f198`
- `0x180030d7c`
- `0x18004ef3c`
- `0x18004f1bc`
- `0x18004f2b0`
- `0x18004f658`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18004f59f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18004f5e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18004f59f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18004f5e9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f5c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f5c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f349`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f38b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f40a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f492`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f55a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f349`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f38b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f40a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f492`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f55a`

## string_xrefs

- `0x18004f381`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004f400`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004f488`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004f4f5`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004f338`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004f399`: `Retail Demo mode is enabled, skipping creating maintenance task.`
- `0x18004f2d5`: `RemoveRetailDemoData`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoAccountDeletionTask::RunTask(RetailDemoAccountDeletionTask *this)
{
  int ValueW; // eax
  RetailDemoAccountDeletionTask *v2; // rcx
  LSTATUS v3; // eax
  RetailDemoAccountDeletionTask *v4; // rcx
  bool v5; // sf
  LSTATUS v6; // eax
  bool v7; // sf
  wchar_t *i; // rax
  const unsigned __int16 *v9; // rbx
  RetailDemoAccountDeletionTask *v10; // rcx
  const char *v11; // r9
  __int64 result; // rax
  DWORD pvData; // [rsp+40h] [rbp-7B8h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-7B0h] BYREF
  wchar_t *Context[2]; // [rsp+50h] [rbp-7A8h] BYREF
  _QWORD v16[42]; // [rsp+60h] [rbp-798h] BYREF
  WCHAR String1[264]; // [rsp+1B0h] [rbp-648h] BYREF
  unsigned __int16 v18[264]; // [rsp+3C0h] [rbp-438h] BYREF
  unsigned __int16 v19[264]; // [rsp+5D0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7F8h] [rbp+0h]

  wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "RemoveRetailDemoData");
  v16[0] = &OOBETelemetry::RemoveRetailDemoData::`vftable';
  OOBETelemetry::RemoveRetailDemoData::StartActivity((OOBETelemetry::RemoveRetailDemoData *)v16);
  try
  {
    pvData = 0;
    pcbData[0] = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
           L"Enabled",
           0x10010u,
           0,
           &pvData,
           pcbData) )
    {
      pcbData[0] = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
        L"Enabled",
        0x20010010u,
        0,
        &pvData,
        pcbData);
    }
    if ( pvData )
    {
      UnattendLogW(0, L"Retail Demo mode is enabled, skipping creating maintenance task.");
    }
    else
    {
      UnattendLogW(0, L"Retail Demo mode is not enabled, removing demo accounts if they exist.");
      memset_0(v18, 0, 0x202u);
      pvData = 514;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
                 L"Account",
                 2u,
                 0,
                 v18,
                 &pvData);
      if ( ValueW )
      {
        v2 = 0;
        v18[0] = 0;
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
      }
      if ( ValueW >= 0 )
        RetailDemoAccountDeletionTask::RemoveUser(v2, v18);
      memset_0(v19, 0, 0x202u);
      pvData = 514;
      v3 = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"AdminAccount",
             2u,
             0,
             v19,
             &pvData);
      v5 = v3 < 0;
      if ( v3 )
      {
        v4 = 0;
        v19[0] = 0;
        v5 = v3 < 0;
        if ( v3 > 0 )
          v5 = 1;
      }
      if ( !v5 )
        RetailDemoAccountDeletionTask::RemoveUser(v4, v19);
      *(_QWORD *)pcbData = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        pcbData,
        0);
      if ( (int)SHRegAllocData(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
                  L"PostOOBEAccounts",
                  2u,
                  (void **)pcbData,
                  0) >= 0 )
      {
        memset_0(String1, 0, 0x202u);
        pvData = 514;
        v6 = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
               L"DefaultAccountSAMName",
               2u,
               0,
               String1,
               &pvData);
        v7 = v6 < 0;
        if ( v6 )
        {
          String1[0] = 0;
          v7 = v6 < 0;
          if ( v6 > 0 )
            v7 = 1;
        }
        if ( v7 )
          String1[0] = 0;
        Context[0] = 0;
        for ( i = wcstok_s(*(wchar_t **)pcbData, L",", Context); ; i = wcstok_s(0, L",", Context) )
        {
          v9 = i;
          if ( !i )
            break;
          if ( CompareStringOrdinal(String1, -1, i, -1, 1) != 2 )
            RetailDemoAccountDeletionTask::RemoveUser(v10, v9);
        }
      }
      OOBEStartService(L"Schedule", 1);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pcbData);
    }
    wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, 0);
    OOBETelemetry::RemoveRetailDemoData::~RemoveRetailDemoData((OOBETelemetry::RemoveRetailDemoData *)v16);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6C,
                           (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemotasks.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18004f2b0  mov     [rsp+arg_0], rbx
0x18004f2b5  mov     [rsp+arg_8], rsi
0x18004f2ba  push    r14
0x18004f2bc  sub     rsp, 7F0h
0x18004f2c3  mov     rax, cs:__security_cookie
0x18004f2ca  xor     rax, rsp
0x18004f2cd  mov     [rsp+7F8h+var_18], rax
0x18004f2d5  lea     rdx, aRemoveretailde; "RemoveRetailDemoData"
0x18004f2dc  lea     rcx, [rsp+7F8h+var_798]
0x18004f2e1  call    ??0?$ActivityBase@VOOBELogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004f2e6  lea     rax, ??_7RemoveRetailDemoData@OOBETelemetry@@6B@; const OOBETelemetry::RemoveRetailDemoData::`vftable'
0x18004f2ed  mov     [rsp+7F8h+var_798], rax
0x18004f2f2  lea     rcx, [rsp+7F8h+var_798]; this
0x18004f2f7  call    ?StartActivity@RemoveRetailDemoData@OOBETelemetry@@QEAAXXZ; OOBETelemetry::RemoveRetailDemoData::StartActivity(void)
0x18004f2fc  nop
0x18004f2fd  mov     [rsp+7F8h+var_7B8], 0
0x18004f305  mov     ebx, 4
0x18004f30a  mov     [rsp+7F8h+var_7B0], ebx
0x18004f30e  lea     rax, [rsp+7F8h+var_7B0]
0x18004f313  mov     [rsp+7F8h+pcbData], rax; pcbData
0x18004f318  lea     rax, [rsp+7F8h+var_7B8]
0x18004f31d  mov     [rsp+7F8h+pvData], rax; pvData
0x18004f322  mov     [rsp+7F8h+pdwType], 0; pdwType
0x18004f32b  mov     r9d, 10010h; dwFlags
0x18004f331  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18004f338  lea     rdx, aOsdataSoftware_0; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18004f33f  mov     rsi, 0FFFFFFFF80000002h
0x18004f346  mov     rcx, rsi; hkey
0x18004f349  call    cs:__imp_RegGetValueW
0x18004f34f  test    eax, eax
0x18004f351  jz      short loc_18004F391
0x18004f353  mov     [rsp+7F8h+var_7B0], ebx
0x18004f357  lea     rax, [rsp+7F8h+var_7B0]
0x18004f35c  mov     [rsp+7F8h+pcbData], rax; pcbData
0x18004f361  lea     rax, [rsp+7F8h+var_7B8]
0x18004f366  mov     [rsp+7F8h+pvData], rax; pvData
0x18004f36b  mov     [rsp+7F8h+pdwType], 0; pdwType
0x18004f374  mov     r9d, 20010010h; dwFlags
0x18004f37a  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18004f381  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f388  mov     rcx, rsi; hkey
0x18004f38b  call    cs:__imp_RegGetValueW
0x18004f391  xor     ecx, ecx
0x18004f393  cmp     [rsp+7F8h+var_7B8], ecx
0x18004f397  jz      short loc_18004F3AA
0x18004f399  lea     rdx, aRetailDemoMode; "Retail Demo mode is enabled, skipping c"...
0x18004f3a0  call    UnattendLogW
0x18004f3a5  jmp     loc_18004F60A
0x18004f3aa  lea     rdx, aRetailDemoMode_0; "Retail Demo mode is not enabled, removi"...
0x18004f3b1  call    UnattendLogW
0x18004f3b6  mov     r14d, 202h
0x18004f3bc  mov     r8d, r14d; Size
0x18004f3bf  xor     edx, edx; Val
0x18004f3c1  lea     rcx, [rsp+7F8h+var_438]; void *
0x18004f3c9  call    memset_0
0x18004f3ce  mov     [rsp+7F8h+var_7B8], r14d
0x18004f3d3  lea     rax, [rsp+7F8h+var_7B8]
0x18004f3d8  mov     [rsp+7F8h+pcbData], rax; pcbData
0x18004f3dd  lea     rax, [rsp+7F8h+var_438]
0x18004f3e5  mov     [rsp+7F8h+pvData], rax; pvData
0x18004f3ea  mov     [rsp+7F8h+pdwType], 0; pdwType
0x18004f3f3  mov     r9d, 2; dwFlags
0x18004f3f9  lea     r8, ?c_retailDemoValueDemoAccountName@@3QBGB; "Account"
0x18004f400  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f407  mov     rcx, rsi; hkey
0x18004f40a  call    cs:__imp_RegGetValueW
0x18004f410  test    eax, eax
0x18004f412  jz      short loc_18004F42E
0x18004f414  xor     ecx, ecx
0x18004f416  mov     [rsp+7F8h+var_438], cx
0x18004f41e  test    eax, eax
0x18004f420  jle     short loc_18004F42E
0x18004f422  movzx   eax, ax
0x18004f425  mov     ebx, 80070000h
0x18004f42a  or      eax, ebx
0x18004f42c  jmp     short loc_18004F433
0x18004f42e  mov     ebx, 80070000h
0x18004f433  test    eax, eax
0x18004f435  js      short loc_18004F444
0x18004f437  lea     rdx, [rsp+7F8h+var_438]; unsigned __int16 *
0x18004f43f  call    ?RemoveUser@RetailDemoAccountDeletionTask@@AEAAXPEBG@Z; RetailDemoAccountDeletionTask::RemoveUser(ushort const *)
0x18004f444  mov     r8, r14; Size
0x18004f447  xor     edx, edx; Val
0x18004f449  lea     rcx, [rsp+7F8h+var_228]; void *
0x18004f451  call    memset_0
0x18004f456  mov     [rsp+7F8h+var_7B8], r14d
0x18004f45b  lea     rax, [rsp+7F8h+var_7B8]
0x18004f460  mov     [rsp+7F8h+pcbData], rax; pcbData
0x18004f465  lea     rax, [rsp+7F8h+var_228]
0x18004f46d  mov     [rsp+7F8h+pvData], rax; pvData
0x18004f472  mov     [rsp+7F8h+pdwType], 0; pdwType
0x18004f47b  mov     r9d, 2; dwFlags
0x18004f481  lea     r8, ?c_retailDemoValueAdminAccountName@@3QBGB; "AdminAccount"
0x18004f488  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f48f  mov     rcx, rsi; hkey
0x18004f492  call    cs:__imp_RegGetValueW
0x18004f498  test    eax, eax
0x18004f49a  jz      short loc_18004F4B1
0x18004f49c  xor     ecx, ecx; this
0x18004f49e  mov     [rsp+7F8h+var_228], cx
0x18004f4a6  test    eax, eax
0x18004f4a8  jle     short loc_18004F4B1
0x18004f4aa  movzx   eax, ax
0x18004f4ad  or      eax, ebx
0x18004f4af  test    eax, eax
0x18004f4b1  js      short loc_18004F4C0
0x18004f4b3  lea     rdx, [rsp+7F8h+var_228]; unsigned __int16 *
0x18004f4bb  call    ?RemoveUser@RetailDemoAccountDeletionTask@@AEAAXPEBG@Z; RetailDemoAccountDeletionTask::RemoveUser(ushort const *)
0x18004f4c0  mov     qword ptr [rsp+7F8h+var_7B0], 0
0x18004f4c9  xor     edx, edx
0x18004f4cb  lea     rcx, [rsp+7F8h+var_7B0]
0x18004f4d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004f4d5  mov     [rsp+7F8h+pvData], 0; unsigned int *
0x18004f4de  lea     rax, [rsp+7F8h+var_7B0]
0x18004f4e3  mov     [rsp+7F8h+pdwType], rax; void **
0x18004f4e8  mov     r9d, 2; int
0x18004f4ee  lea     r8, ?c_retailDemoValuePostOOBEAccounts@@3QBGB; "PostOOBEAccounts"
0x18004f4f5  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f4fc  mov     rcx, rsi; HKEY
0x18004f4ff  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18004f504  test    eax, eax
0x18004f506  js      loc_18004F5F1
0x18004f50c  mov     r8, r14; Size
0x18004f50f  xor     edx, edx; Val
0x18004f511  lea     rcx, [rsp+7F8h+String1]; void *
0x18004f519  call    memset_0
0x18004f51e  mov     [rsp+7F8h+var_7B8], r14d
0x18004f523  lea     rax, [rsp+7F8h+var_7B8]
0x18004f528  mov     [rsp+7F8h+pcbData], rax; pcbData
0x18004f52d  lea     rax, [rsp+7F8h+String1]
0x18004f535  mov     [rsp+7F8h+pvData], rax; pvData
0x18004f53a  mov     [rsp+7F8h+pdwType], 0; pdwType
0x18004f543  mov     r9d, 2; dwFlags
0x18004f549  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x18004f550  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004f557  mov     rcx, rsi; hkey
0x18004f55a  call    cs:__imp_RegGetValueW
0x18004f560  test    eax, eax
0x18004f562  jz      short loc_18004F579
0x18004f564  xor     ecx, ecx
0x18004f566  mov     [rsp+7F8h+String1], cx
0x18004f56e  test    eax, eax
0x18004f570  jle     short loc_18004F579
0x18004f572  movzx   eax, ax
0x18004f575  or      eax, ebx
0x18004f577  test    eax, eax
0x18004f579  jns     short loc_18004F585
0x18004f57b  xor     eax, eax
0x18004f57d  mov     [rsp+7F8h+String1], ax
0x18004f585  mov     [rsp+7F8h+Context], 0
0x18004f58e  lea     r8, [rsp+7F8h+Context]; Context
0x18004f593  lea     rdx, asc_1800E7590; ","
0x18004f59a  mov     rcx, qword ptr [rsp+7F8h+var_7B0]; String
0x18004f59f  call    cs:__imp_wcstok_s
0x18004f5a5  or      esi, 0FFFFFFFFh
0x18004f5a8  mov     rbx, rax
0x18004f5ab  test    rax, rax
0x18004f5ae  jz      short loc_18004F5F1
0x18004f5b0  mov     dword ptr [rsp+7F8h+pdwType], 1; bIgnoreCase
0x18004f5b8  mov     r9d, esi; cchCount2
0x18004f5bb  mov     r8, rax; lpString2
0x18004f5be  mov     edx, esi; cchCount1
0x18004f5c0  lea     rcx, [rsp+7F8h+String1]; lpString1
0x18004f5c8  call    cs:__imp_CompareStringOrdinal
0x18004f5ce  cmp     eax, 2
0x18004f5d1  jz      short loc_18004F5DB
0x18004f5d3  mov     rdx, rbx; unsigned __int16 *
0x18004f5d6  call    ?RemoveUser@RetailDemoAccountDeletionTask@@AEAAXPEBG@Z; RetailDemoAccountDeletionTask::RemoveUser(ushort const *)
0x18004f5db  lea     r8, [rsp+7F8h+Context]; Context
0x18004f5e0  lea     rdx, asc_1800E7590; ","
0x18004f5e7  xor     ecx, ecx; String
0x18004f5e9  call    cs:__imp_wcstok_s
0x18004f5ef  jmp     short loc_18004F5A8
0x18004f5f1  mov     dl, 1; bool
0x18004f5f3  lea     rcx, aSchedule; "Schedule"
0x18004f5fa  call    ?OOBEStartService@@YAJPEBG_N@Z; OOBEStartService(ushort const *,bool)
0x18004f5ff  nop
0x18004f600  lea     rcx, [rsp+7F8h+var_7B0]
0x18004f605  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f60a  xor     edx, edx
0x18004f60c  lea     rcx, [rsp+7F8h+var_798]
0x18004f611  call    ?Stop@?$ActivityBase@VOOBELogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004f616  nop
0x18004f617  lea     rcx, [rsp+7F8h+var_798]; this
0x18004f61c  call    ??1RemoveRetailDemoData@OOBETelemetry@@QEAA@XZ; OOBETelemetry::RemoveRetailDemoData::~RemoveRetailDemoData(void)
0x18004f621  nop
0x18004f622  xor     eax, eax
0x18004f624  jmp     short loc_18004F62A
0x18004f626  mov     eax, [rsp+7F8h+var_7B8]
0x18004f62a  mov     rcx, [rsp+7F8h+var_18]
0x18004f632  xor     rcx, rsp; StackCookie
0x18004f635  call    __security_check_cookie
0x18004f63a  lea     r11, [rsp+7F8h+var_8]
0x18004f642  mov     rbx, [r11+10h]
0x18004f646  mov     rsi, [r11+18h]
0x18004f64a  mov     rsp, r11
0x18004f64d  pop     r14
0x18004f64f  retn
```
