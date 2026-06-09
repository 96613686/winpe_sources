# CCatalogServer::CreateApplicationService(_GUID,ushort *,ulong,ulong,ushort *,ushort *,ushort *,short)

- ea: `0x18001cd30`
- end: `0x18001d652`
- name: `?CreateApplicationService@CCatalogServer@@UEAAJU_GUID@@PEAGKK111F@Z`
- size: `2338`
- prototype: `__int64 __fastcall(CCatalogServer *this, struct _GUID *, unsigned __int16 *, DWORD, DWORD dwErrorControl, unsigned __int16 *, unsigned __int16 *lpServiceStartName, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001cd30`
- `0x18001ece0`
- `0x18002f158`
- `0x180031b4c`
- `0x180031cdc`
- `0x1800554f6`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d0d8`
- `msvcrt!_wcsicmp` at `0x18001d0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d40e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d44a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d40e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d44a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d504`
- `comsvcs!GetObjectContext` at `0x18001d5c7`
- `comsvcs!GetObjectContext` at `0x1800561af`
- `comsvcs!GetObjectContext` at `0x18001d5c7`
- `comsvcs!GetObjectContext` at `0x1800561af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ce1c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ce1c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d56e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d57c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005614e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180056161`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d56e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d57c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005614e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180056161`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d10d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d10d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d3d5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d3d5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001d4fa`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001d4fa`
- `ADVAPI32!LockServiceDatabase` at `0x18001d15c`
- `ADVAPI32!LockServiceDatabase` at `0x18001d15c`
- `ADVAPI32!UnlockServiceDatabase` at `0x18001d560`
- `ADVAPI32!UnlockServiceDatabase` at `0x18005613b`
- `ADVAPI32!UnlockServiceDatabase` at `0x18001d560`
- `ADVAPI32!UnlockServiceDatabase` at `0x18005613b`

## pseudocode

```c
__int64 __fastcall CCatalogServer::CreateApplicationService(
        CCatalogServer *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        DWORD a4,
        DWORD dwErrorControl,
        unsigned __int16 *a6,
        unsigned __int16 *lpServiceStartName,
        unsigned __int16 *a8,
        __int16 a9)
{
  const WCHAR *lpPassword; // r12
  int v12; // eax
  __int64 v13; // rax
  const wchar_t *v14; // rcx
  SC_HANDLE v15; // r14
  signed int LastError; // eax
  void *v17; // r15
  signed int v18; // eax
  __int64 v19; // rax
  unsigned int v20; // ecx
  int v21; // eax
  SC_HANDLE v22; // rsi
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  DWORD v28; // edx
  const WCHAR *v29; // rax
  signed int v30; // eax
  int v31; // edi
  int ObjectContext; // eax
  __int64 v33; // [rsp+0h] [rbp-118h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-F8h]
  HRESULT v35; // [rsp+60h] [rbp-B8h]
  __int64 *v36; // [rsp+68h] [rbp-B0h]
  __int64 *v37; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+78h] [rbp-A0h] BYREF
  unsigned int v39; // [rsp+80h] [rbp-98h] BYREF
  LPVOID v40; // [rsp+88h] [rbp-90h] BYREF
  const wchar_t *v41; // [rsp+90h] [rbp-88h] BYREF
  DWORD dwStartType; // [rsp+98h] [rbp-80h]
  void *v43; // [rsp+A0h] [rbp-78h]
  SC_HANDLE v44; // [rsp+A8h] [rbp-70h]
  SC_HANDLE v45; // [rsp+B0h] [rbp-68h]
  unsigned int *v46; // [rsp+B8h] [rbp-60h] BYREF
  LPCWSTR lpDependencies; // [rsp+C0h] [rbp-58h]
  _QWORD v48[2]; // [rsp+C8h] [rbp-50h] BYREF
  int v49; // [rsp+D8h] [rbp-40h]
  int v50; // [rsp+DCh] [rbp-3Ch]

  v36 = &v33;
  dwStartType = a4;
  lpDependencies = a6;
  lpPassword = a8;
  v40 = 0;
  v37 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  v46 = 0;
  v48[0] = a2;
  v48[1] = 0;
  v49 = 72;
  v50 = 16;
  if ( !*((_DWORD *)this + 24) )
    return 2148598828LL;
  v35 = TxInitialize();
  if ( v35 >= 0 )
  {
    v44 = 0;
    v45 = 0;
    v43 = 0;
    UTSemReadWrite::LockWrite((UTSemReadWrite *)&g_semRW);
    v35 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &v40);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v35 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, const struct _GUID *, _QWORD *, __int64, int, _DWORD, __int64 **))(*(_QWORD *)v40 + 24LL))(
            v40,
            didCOMSERVICES,
            &TID_APPLICATION,
            v48,
            1,
            1,
            0,
            &v37);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v35 = (*(__int64 (__fastcall **)(__int64 *))(*v37 + 24))(v37);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v35 = (*(__int64 (__fastcall **)(__int64 *))(*v37 + 40))(v37);
    v12 = v35;
    if ( v35 == -2146367487 )
      v12 = local_unwind_0(v36, &loc_18001D63B);
    if ( v12 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v13 = *v37;
    ppv = (LPVOID *)&v41;
    v35 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v13 + 64))(v37, 6, 0);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    if ( v41 )
    {
      v35 = -2147023823;
      local_unwind_0(v36, &loc_18001D63B);
    }
    v35 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, const wchar_t **))(*v37 + 64))(
            v37,
            16,
            0,
            0,
            &v41);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v14 = v41;
    if ( !v41 )
    {
      v35 = -2147418113;
      local_unwind_0(v36, &loc_18001D63B);
    }
    if ( !_wcsicmp(v14, L"Inproc") )
    {
      v35 = -2146367468;
      local_unwind_0(v36, &loc_18001D63B);
    }
    v15 = OpenSCManagerW(0, 0, 0x40000008u);
    v44 = v15;
    if ( !v15 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v35 = LastError;
      if ( LastError < 0 )
        local_unwind_0(v36, &loc_18001D63B);
    }
    v17 = LockServiceDatabase(v15);
    v43 = v17;
    if ( !v17 )
    {
      v18 = GetLastError();
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v35 = v18;
      if ( v18 < 0 )
        local_unwind_0(v36, &loc_18001D63B);
    }
    v35 = (*(__int64 (__fastcall **)(__int64 *))(*v37 + 128))(v37);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v19 = *v37;
    ppv = (LPVOID *)&v46;
    v35 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v19 + 64))(v37, 24, 0);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v20 = *v46;
    v39 = v20;
    v21 = 2;
    if ( v20 < 2 )
      v21 = v20;
    v39 = v21;
    v35 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, unsigned int *))(*v37 + 160))(v37, 24, 0, &v39);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v35 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, unsigned __int16 *))(*v37 + 160))(v37, 6, 0, a3);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v35 = (*(__int64 (__fastcall **)(__int64 *))(*v37 + 144))(v37);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v35 = (*(__int64 (__fastcall **)(__int64 *))(*v37 + 96))(v37);
    if ( v35 < 0 )
      local_unwind_0(v36, &loc_18001D63B);
    v22 = OpenServiceW(v15, a3, 2u);
    v45 = v22;
    if ( !v22 )
    {
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      v35 = v23;
      if ( v23 < 0 )
      {
        v24 = GetLastError();
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        v35 = v24;
        if ( v24 != -2147024882 )
        {
          v25 = GetLastError();
          if ( v25 > 0 )
            v25 = (unsigned __int16)v25 | 0x80070000;
          v35 = v25;
          if ( v25 != -2147023441 )
          {
            v26 = GetLastError();
            if ( v26 > 0 )
              v26 = (unsigned __int16)v26 | 0x80070000;
            v35 = v26;
            if ( v26 != -2147023781 )
            {
              v27 = GetLastError();
              if ( v27 > 0 )
                v27 = (unsigned __int16)v27 | 0x80070000;
              v35 = v27;
            }
          }
        }
        local_unwind_0(v36, &loc_18001D63B);
      }
    }
    v28 = 272;
    if ( a9 != -1 )
      v28 = 16;
    if ( lpServiceStartName )
    {
      v29 = &word_18005C890;
      if ( a8 )
        v29 = a8;
      lpPassword = v29;
    }
    if ( !ChangeServiceConfigW(
            v22,
            v28,
            dwStartType,
            dwErrorControl,
            0,
            0,
            0,
            lpDependencies,
            lpServiceStartName,
            lpPassword,
            0) )
    {
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      v35 = v30;
      if ( v30 < 0 )
        local_unwind_0(v36, &loc_18001D63B);
    }
    UTSemReadWrite::UnlockWrite((UTSemReadWrite *)&g_semRW);
    if ( v17 )
      UnlockServiceDatabase(v17);
    if ( v15 )
      CloseServiceHandle(v15);
    if ( v22 )
      CloseServiceHandle(v22);
    if ( v40 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
      v40 = 0;
    }
    if ( v37 )
    {
      (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
      v37 = 0;
    }
    v31 = v35;
    ObjectContext = GetObjectContext(&v38);
    if ( v31 < 0 )
    {
      if ( ObjectContext < 0 )
      {
        if ( ObjectContext == -2147164156 )
          ObjectContext = 0;
      }
      else
      {
        ObjectContext = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38);
      }
      if ( ObjectContext < 0 )
        v31 = ObjectContext;
      v35 = v31;
    }
    else
    {
      v35 = ObjectContext;
      if ( ObjectContext < 0 )
      {
        if ( ObjectContext == -2147164156 )
          v35 = 0;
      }
      else
      {
        v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 32LL))(v38);
      }
    }
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x18001cd30  mov     r11, rsp
0x18001cd33  push    rbx
0x18001cd34  push    rsi
0x18001cd35  push    rdi
0x18001cd36  push    r12
0x18001cd38  push    r13
0x18001cd3a  push    r14
0x18001cd3c  push    r15
0x18001cd3e  sub     rsp, 0E0h
0x18001cd45  mov     [rsp+118h+var_B0], rsp
0x18001cd4a  mov     [rsp+118h+dwStartType], r9d
0x18001cd52  mov     rsi, r8
0x18001cd55  mov     rax, [rsp+118h+arg_28]
0x18001cd5d  mov     [rsp+118h+var_58], rax
0x18001cd65  mov     r13, [rsp+118h+arg_30]
0x18001cd6d  mov     r12, [rsp+118h+arg_38]
0x18001cd75  xor     ebx, ebx
0x18001cd77  mov     [r11-90h], rbx
0x18001cd7e  mov     [rsp+118h+var_A8], rbx
0x18001cd83  mov     [r11-88h], rbx
0x18001cd8a  mov     [rsp+118h+var_A0], rbx
0x18001cd8f  mov     [rsp+118h+var_98], ebx
0x18001cd96  mov     [r11-60h], rbx
0x18001cd9a  mov     [r11-50h], rdx
0x18001cd9e  mov     [r11-48h], rbx
0x18001cda2  mov     dword ptr [r11-40h], 48h ; 'H'
0x18001cdaa  lea     r14d, [rbx+10h]
0x18001cdae  mov     [r11-3Ch], r14d
0x18001cdb2  cmp     [rcx+60h], ebx
0x18001cdb5  jnz     short loc_18001CDC1
0x18001cdb7  mov     eax, 8011042Ch
0x18001cdbc  jmp     loc_18001D63F
0x18001cdc1  call    ?TxInitialize@@YAJXZ; TxInitialize(void)
0x18001cdc6  mov     [rsp+118h+var_B8], eax
0x18001cdca  test    eax, eax
0x18001cdcc  js      loc_18001D63B
0x18001cdd2  mov     [rsp+118h+var_70], rbx
0x18001cdda  mov     [rsp+118h+var_68], rbx
0x18001cde2  mov     [rsp+118h+var_78], rbx
0x18001cdea  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x18001cdf1  call    ?LockWrite@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::LockWrite(void)
0x18001cdf6  nop
0x18001cdf7  lea     rax, [rsp+118h+var_90]
0x18001cdff  mov     [rsp+118h+ppv], rax; ppv
0x18001ce04  lea     r9, IID_ISimpleTableDispenser; riid
0x18001ce0b  mov     edi, 1
0x18001ce10  mov     r8d, edi; dwClsContext
0x18001ce13  xor     edx, edx; pUnkOuter
0x18001ce15  lea     rcx, CLSID_STDispenser; rclsid
0x18001ce1c  call    cs:__imp_CoCreateInstance
0x18001ce22  mov     [rsp+118h+var_B8], eax
0x18001ce26  mov     eax, [rsp+118h+var_B8]
0x18001ce2a  test    eax, eax
0x18001ce2c  jns     short loc_18001CE64
0x18001ce2e  mov     eax, [rsp+118h+var_B8]
0x18001ce32  cmp     eax, 8007000Eh
0x18001ce37  jz      short loc_18001CE53
0x18001ce39  mov     eax, [rsp+118h+var_B8]
0x18001ce3d  cmp     eax, 800705AFh
0x18001ce42  jz      short loc_18001CE53
0x18001ce44  mov     eax, [rsp+118h+var_B8]
0x18001ce48  cmp     eax, 8007045Bh
0x18001ce4d  jz      short loc_18001CE53
0x18001ce4f  mov     eax, [rsp+118h+var_B8]
0x18001ce53  lea     rdx, loc_18001D63B
0x18001ce5a  mov     rcx, [rsp+118h+var_B0]
0x18001ce5f  call    _local_unwind_0
0x18001ce64  mov     rcx, [rsp+118h+var_90]
0x18001ce6c  mov     rax, [rcx]
0x18001ce6f  lea     rdx, [rsp+118h+var_A8]
0x18001ce74  mov     [rsp+118h+lpDependencies], rdx
0x18001ce79  mov     dword ptr [rsp+118h+lpdwTagId], ebx
0x18001ce7d  mov     dword ptr [rsp+118h+lpLoadOrderGroup], edi
0x18001ce81  mov     [rsp+118h+ppv], rdi
0x18001ce86  lea     r9, [rsp+118h+var_50]
0x18001ce8e  lea     r8, TID_APPLICATION
0x18001ce95  lea     rdx, didCOMSERVICES
0x18001ce9c  mov     rax, [rax+18h]
0x18001cea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cea5  mov     [rsp+118h+var_B8], eax
0x18001cea9  mov     eax, [rsp+118h+var_B8]
0x18001cead  test    eax, eax
0x18001ceaf  jns     short loc_18001CEE7
0x18001ceb1  mov     eax, [rsp+118h+var_B8]
0x18001ceb5  cmp     eax, 8007000Eh
0x18001ceba  jz      short loc_18001CED6
0x18001cebc  mov     eax, [rsp+118h+var_B8]
0x18001cec0  cmp     eax, 800705AFh
0x18001cec5  jz      short loc_18001CED6
0x18001cec7  mov     eax, [rsp+118h+var_B8]
0x18001cecb  cmp     eax, 8007045Bh
0x18001ced0  jz      short loc_18001CED6
0x18001ced2  mov     eax, [rsp+118h+var_B8]
0x18001ced6  lea     rdx, loc_18001D63B
0x18001cedd  mov     rcx, [rsp+118h+var_B0]
0x18001cee2  call    _local_unwind_0
0x18001cee7  mov     rcx, [rsp+118h+var_A8]
0x18001ceec  mov     rax, [rcx]
0x18001ceef  mov     rax, [rax+18h]
0x18001cef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cef8  mov     [rsp+118h+var_B8], eax
0x18001cefc  mov     eax, [rsp+118h+var_B8]
0x18001cf00  test    eax, eax
0x18001cf02  jns     short loc_18001CF3A
0x18001cf04  mov     eax, [rsp+118h+var_B8]
0x18001cf08  cmp     eax, 8007000Eh
0x18001cf0d  jz      short loc_18001CF29
0x18001cf0f  mov     eax, [rsp+118h+var_B8]
0x18001cf13  cmp     eax, 800705AFh
0x18001cf18  jz      short loc_18001CF29
0x18001cf1a  mov     eax, [rsp+118h+var_B8]
0x18001cf1e  cmp     eax, 8007045Bh
0x18001cf23  jz      short loc_18001CF29
0x18001cf25  mov     eax, [rsp+118h+var_B8]
0x18001cf29  lea     rdx, loc_18001D63B
0x18001cf30  mov     rcx, [rsp+118h+var_B0]
0x18001cf35  call    _local_unwind_0
0x18001cf3a  mov     rcx, [rsp+118h+var_A8]
0x18001cf3f  mov     rax, [rcx]
0x18001cf42  mov     rax, [rax+28h]
0x18001cf46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf4b  mov     [rsp+118h+var_B8], eax
0x18001cf4f  mov     eax, [rsp+118h+var_B8]
0x18001cf53  cmp     eax, 80110801h
0x18001cf58  mov     eax, [rsp+118h+var_B8]
0x18001cf5c  jnz     short loc_18001CF73
0x18001cf5e  test    eax, eax
0x18001cf60  jns     short loc_18001CFAD
0x18001cf62  lea     rdx, loc_18001D63B
0x18001cf69  mov     rcx, [rsp+118h+var_B0]
0x18001cf6e  call    _local_unwind_0
0x18001cf73  test    eax, eax
0x18001cf75  jns     short loc_18001CFAD
0x18001cf77  mov     eax, [rsp+118h+var_B8]
0x18001cf7b  cmp     eax, 8007000Eh
0x18001cf80  jz      short loc_18001CF9C
0x18001cf82  mov     eax, [rsp+118h+var_B8]
0x18001cf86  cmp     eax, 800705AFh
0x18001cf8b  jz      short loc_18001CF9C
0x18001cf8d  mov     eax, [rsp+118h+var_B8]
0x18001cf91  cmp     eax, 8007045Bh
0x18001cf96  jz      short loc_18001CF9C
0x18001cf98  mov     eax, [rsp+118h+var_B8]
0x18001cf9c  lea     rdx, loc_18001D63B
0x18001cfa3  mov     rcx, [rsp+118h+var_B0]
0x18001cfa8  call    _local_unwind_0
0x18001cfad  mov     rcx, [rsp+118h+var_A8]
0x18001cfb2  mov     rax, [rcx]
0x18001cfb5  lea     rdx, [rsp+118h+var_88]
0x18001cfbd  mov     [rsp+118h+ppv], rdx
0x18001cfc2  xor     r9d, r9d
0x18001cfc5  xor     r8d, r8d
0x18001cfc8  lea     edx, [r9+6]
0x18001cfcc  mov     rax, [rax+40h]
0x18001cfd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfd5  mov     [rsp+118h+var_B8], eax
0x18001cfd9  mov     eax, [rsp+118h+var_B8]
0x18001cfdd  test    eax, eax
0x18001cfdf  jns     short loc_18001D017
0x18001cfe1  mov     eax, [rsp+118h+var_B8]
0x18001cfe5  cmp     eax, 8007000Eh
0x18001cfea  jz      short loc_18001D006
0x18001cfec  mov     eax, [rsp+118h+var_B8]
0x18001cff0  cmp     eax, 800705AFh
0x18001cff5  jz      short loc_18001D006
0x18001cff7  mov     eax, [rsp+118h+var_B8]
0x18001cffb  cmp     eax, 8007045Bh
0x18001d000  jz      short loc_18001D006
0x18001d002  mov     eax, [rsp+118h+var_B8]
0x18001d006  lea     rdx, loc_18001D63B
0x18001d00d  mov     rcx, [rsp+118h+var_B0]
0x18001d012  call    _local_unwind_0
0x18001d017  cmp     [rsp+118h+var_88], rbx
0x18001d01f  jz      short loc_18001D042
0x18001d021  mov     [rsp+118h+var_B8], 80070431h
0x18001d029  mov     eax, [rsp+118h+var_B8]
0x18001d02d  test    eax, eax
0x18001d02f  jns     short loc_18001D042
0x18001d031  lea     rdx, loc_18001D63B
0x18001d038  mov     rcx, [rsp+118h+var_B0]
0x18001d03d  call    _local_unwind_0
0x18001d042  mov     rcx, [rsp+118h+var_A8]
0x18001d047  mov     rax, [rcx]
0x18001d04a  lea     rdx, [rsp+118h+var_88]
0x18001d052  mov     [rsp+118h+ppv], rdx
0x18001d057  xor     r9d, r9d
0x18001d05a  xor     r8d, r8d
0x18001d05d  mov     edx, r14d
0x18001d060  mov     rax, [rax+40h]
0x18001d064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d069  mov     [rsp+118h+var_B8], eax
0x18001d06d  mov     eax, [rsp+118h+var_B8]
0x18001d071  test    eax, eax
0x18001d073  jns     short loc_18001D0AB
0x18001d075  mov     eax, [rsp+118h+var_B8]
0x18001d079  cmp     eax, 8007000Eh
0x18001d07e  jz      short loc_18001D09A
0x18001d080  mov     eax, [rsp+118h+var_B8]
0x18001d084  cmp     eax, 800705AFh
0x18001d089  jz      short loc_18001D09A
0x18001d08b  mov     eax, [rsp+118h+var_B8]
0x18001d08f  cmp     eax, 8007045Bh
0x18001d094  jz      short loc_18001D09A
0x18001d096  mov     eax, [rsp+118h+var_B8]
0x18001d09a  lea     rdx, loc_18001D63B
0x18001d0a1  mov     rcx, [rsp+118h+var_B0]
0x18001d0a6  call    _local_unwind_0
0x18001d0ab  mov     rcx, [rsp+118h+var_88]
0x18001d0b3  test    rcx, rcx
0x18001d0b6  jnz     short loc_18001D0D1
0x18001d0b8  mov     [rsp+118h+var_B8], 8000FFFFh
0x18001d0c0  lea     rdx, loc_18001D63B
0x18001d0c7  mov     rcx, [rsp+118h+var_B0]
0x18001d0cc  call    _local_unwind_0
0x18001d0d1  lea     rdx, aInproc; "Inproc"
0x18001d0d8  call    cs:__imp__wcsicmp
0x18001d0de  test    eax, eax
0x18001d0e0  jnz     short loc_18001D103
0x18001d0e2  mov     [rsp+118h+var_B8], 80110814h
0x18001d0ea  mov     eax, [rsp+118h+var_B8]
0x18001d0ee  test    eax, eax
0x18001d0f0  jns     short loc_18001D103
0x18001d0f2  lea     rdx, loc_18001D63B
0x18001d0f9  mov     rcx, [rsp+118h+var_B0]
0x18001d0fe  call    _local_unwind_0
0x18001d103  xor     edx, edx; lpDatabaseName
0x18001d105  xor     ecx, ecx; lpMachineName
0x18001d107  mov     r8d, 40000008h; dwDesiredAccess
0x18001d10d  call    cs:__imp_OpenSCManagerW
0x18001d113  mov     r14, rax
0x18001d116  mov     [rsp+118h+var_70], rax
0x18001d11e  test    rax, rax
0x18001d121  jnz     short loc_18001D154
0x18001d123  call    cs:__imp_GetLastError
0x18001d129  mov     edi, 80070000h
0x18001d12e  test    eax, eax
0x18001d130  jle     short loc_18001D137
0x18001d132  movzx   eax, ax
0x18001d135  or      eax, edi
0x18001d137  mov     [rsp+118h+var_B8], eax
0x18001d13b  mov     eax, [rsp+118h+var_B8]
0x18001d13f  test    eax, eax
0x18001d141  jns     short loc_18001D159
0x18001d143  lea     rdx, loc_18001D63B
0x18001d14a  mov     rcx, [rsp+118h+var_B0]
0x18001d14f  call    _local_unwind_0
0x18001d154  mov     edi, 80070000h
0x18001d159  mov     rcx, r14; hSCManager
0x18001d15c  call    cs:__imp_LockServiceDatabase
0x18001d162  mov     r15, rax
0x18001d165  mov     [rsp+118h+var_78], rax
0x18001d16d  test    rax, rax
0x18001d170  jnz     short loc_18001D19E
0x18001d172  call    cs:__imp_GetLastError
0x18001d178  test    eax, eax
0x18001d17a  jle     short loc_18001D181
0x18001d17c  movzx   eax, ax
0x18001d17f  or      eax, edi
0x18001d181  mov     [rsp+118h+var_B8], eax
0x18001d185  mov     eax, [rsp+118h+var_B8]
0x18001d189  test    eax, eax
0x18001d18b  jns     short loc_18001D19E
0x18001d18d  lea     rdx, loc_18001D63B
0x18001d194  mov     rcx, [rsp+118h+var_B0]
0x18001d199  call    _local_unwind_0
0x18001d19e  mov     rcx, [rsp+118h+var_A8]
0x18001d1a3  mov     rax, [rcx]
0x18001d1a6  mov     rax, [rax+80h]
0x18001d1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b2  mov     [rsp+118h+var_B8], eax
0x18001d1b6  mov     eax, [rsp+118h+var_B8]
0x18001d1ba  test    eax, eax
0x18001d1bc  jns     short loc_18001D1F4
0x18001d1be  mov     eax, [rsp+118h+var_B8]
0x18001d1c2  cmp     eax, 8007000Eh
0x18001d1c7  jz      short loc_18001D1E3
0x18001d1c9  mov     eax, [rsp+118h+var_B8]
0x18001d1cd  cmp     eax, 800705AFh
0x18001d1d2  jz      short loc_18001D1E3
0x18001d1d4  mov     eax, [rsp+118h+var_B8]
0x18001d1d8  cmp     eax, 8007045Bh
0x18001d1dd  jz      short loc_18001D1E3
0x18001d1df  mov     eax, [rsp+118h+var_B8]
0x18001d1e3  lea     rdx, loc_18001D63B
0x18001d1ea  mov     rcx, [rsp+118h+var_B0]
0x18001d1ef  call    _local_unwind_0
0x18001d1f4  mov     rcx, [rsp+118h+var_A8]
0x18001d1f9  mov     rax, [rcx]
0x18001d1fc  lea     rdx, [rsp+118h+var_60]
0x18001d204  mov     [rsp+118h+ppv], rdx
0x18001d209  xor     r9d, r9d
0x18001d20c  xor     r8d, r8d
0x18001d20f  lea     edx, [r9+18h]
0x18001d213  mov     rax, [rax+40h]
0x18001d217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d21c  mov     [rsp+118h+var_B8], eax
0x18001d220  mov     eax, [rsp+118h+var_B8]
0x18001d224  test    eax, eax
0x18001d226  jns     short loc_18001D25E
0x18001d228  mov     eax, [rsp+118h+var_B8]
  ... truncated ...
```
