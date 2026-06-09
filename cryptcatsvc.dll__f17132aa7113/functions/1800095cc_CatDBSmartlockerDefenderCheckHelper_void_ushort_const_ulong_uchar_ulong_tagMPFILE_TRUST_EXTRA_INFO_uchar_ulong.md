# CatDBSmartlockerDefenderCheckHelper(void *,ushort const *,ulong,uchar,ulong,tagMPFILE_TRUST_EXTRA_INFO *,uchar *,ulong *,tagMPFILE_TRUST_EXTRA_INFO * *)

- ea: `0x1800095cc`
- end: `0x180009b1b`
- name: `?CatDBSmartlockerDefenderCheckHelper@@YAKPEAXPEBGKEKPEAUtagMPFILE_TRUST_EXTRA_INFO@@PEAEPEAKPEAPEAU1@@Z`
- size: `1359`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, const unsigned __int16 *, int, __int64, unsigned int, struct tagMPFILE_TRUST_EXTRA_INFO *, struct tagMPTRUST_INFO *, unsigned int *, struct tagMPFILE_TRUST_EXTRA_INFO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016c40`

## callees

- `0x1800095cc`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000a790`
- `0x18000ad10`
- `0x18000be40`
- `0x1800153dc`
- `0x180015688`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800097b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800097b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009714`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000975f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009714`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000975f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800097ce`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800097ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009827`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009827`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000976e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000986e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000976e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000986e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800096fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800096fa`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000972f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000972f`
- `RPCRT4!RpcRevertToSelf` at `0x1800099e6`
- `RPCRT4!RpcRevertToSelf` at `0x180009abd`
- `RPCRT4!RpcRevertToSelf` at `0x1800099e6`
- `RPCRT4!RpcRevertToSelf` at `0x180009abd`
- `RPCRT4!RpcImpersonateClient` at `0x18000985f`
- `RPCRT4!RpcImpersonateClient` at `0x18000985f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180009787`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800097f2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180009787`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800097f2`
- `ntdll!NtOpenFile` at `0x1800098d8`
- `ntdll!NtOpenFile` at `0x18000996b`
- `ntdll!NtOpenFile` at `0x1800098d8`
- `ntdll!NtOpenFile` at `0x18000996b`
- `ntdll!NtClose` at `0x180009acd`
- `ntdll!NtClose` at `0x180009acd`
- `ntdll!RtlInitUnicodeString` at `0x180009892`
- `ntdll!RtlInitUnicodeString` at `0x180009892`
- `ntdll!RtlFreeUnicodeString` at `0x180009adc`
- `ntdll!RtlFreeUnicodeString` at `0x180009adc`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180009922`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180009922`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009a80`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009a80`

## string_xrefs

- `0x1800096e5`: `InstallLocation`
- `0x180009704`: `MpClient.dll`
- `0x18000974f`: `\Windows Defender\MpClient.dll`

## pseudocode

```c
__int64 __fastcall CatDBSmartlockerDefenderCheckHelper(
        RPC_BINDING_HANDLE BindingHandle,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        struct tagMPFILE_TRUST_EXTRA_INFO *a6,
        struct tagMPTRUST_INFO *a7,
        unsigned int *a8,
        struct tagMPFILE_TRUST_EXTRA_INFO **a9)
{
  char v10; // r14
  unsigned __int8 v11; // r15
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  int v15; // esi
  int Error; // edi
  unsigned int v17; // edx
  unsigned __int16 *v18; // rcx
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  HMODULE LibraryW; // rax
  unsigned int v22; // edx
  unsigned __int16 *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // edx
  unsigned __int16 *v26; // rcx
  HMODULE v27; // rax
  FARPROC ProcAddress; // rax
  unsigned int v29; // edx
  unsigned __int16 *v30; // rcx
  unsigned int v31; // edx
  unsigned __int16 *v32; // rcx
  PCWSTR v33; // r13
  NTSTATUS v34; // eax
  void *v35; // rdx
  unsigned __int16 *v36; // rcx
  unsigned int v37; // edx
  unsigned __int16 *v38; // rcx
  unsigned __int16 *v39; // rcx
  struct tagMPFILE_TRUST_EXTRA_INFO *v40; // r13
  unsigned int *v41; // r15
  struct tagMPFILE_TRUST_EXTRA_INFO **v42; // rdi
  int v43; // eax
  unsigned int v44; // edx
  unsigned __int16 *v45; // rcx
  unsigned int v46; // edx
  unsigned __int16 *v47; // rcx
  ULONG v48; // eax
  int pvData; // [rsp+30h] [rbp-D8h]
  int pvDataa; // [rsp+30h] [rbp-D8h]
  int pvDatab; // [rsp+30h] [rbp-D8h]
  int pvDatac; // [rsp+30h] [rbp-D8h]
  int pvDatad; // [rsp+30h] [rbp-D8h]
  unsigned __int8 v55[8]; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-B8h] BYREF
  PCWSTR SourceString; // [rsp+58h] [rbp-B0h]
  struct tagMPFILE_TRUST_EXTRA_INFO *v58; // [rsp+60h] [rbp-A8h]
  unsigned int *v59; // [rsp+68h] [rbp-A0h]
  struct tagMPFILE_TRUST_EXTRA_INFO **v60; // [rsp+70h] [rbp-98h]
  __int64 v61; // [rsp+78h] [rbp-90h]
  void *FileHandle; // [rsp+80h] [rbp-88h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp-50h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-48h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-38h] BYREF
  WCHAR Buffer[264]; // [rsp+E8h] [rbp-20h] BYREF

  v61 = -2;
  SourceString = a2;
  v58 = a6;
  v59 = a8;
  v60 = a9;
  DestinationString = 0;
  FileHandle = 0;
  v10 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v11 = 0;
  v55[1] = 0;
  pcbData = 520;
  hModule = 0;
  v55[0] = 0;
  if ( !BindingHandle || a3 != 16 || !a7 )
  {
    SetLastError(0xA0u);
    v14 = 513;
    goto LABEL_56;
  }
  if ( (unsigned int)IsDefenderDisabled() )
  {
    SetLastError(0x422u);
    v14 = 518;
LABEL_56:
    ErrLog_LogError(v13, v12, v14, 0, 0, pvData);
    goto LABEL_57;
  }
  v15 = 0;
  Error = 0;
  if ( byte_1800312D8 )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows Defender",
           L"InstallLocation",
           2u,
           0,
           Buffer,
           &pcbData)
      || (unsigned int)_o_wcscat_s(Buffer, 260, L"MpClient.dll") )
    {
      if ( !GetEnvironmentVariableW(L"ProgramFiles", Buffer, 0x104u) )
      {
        byte_1800312D8 = 0;
        ErrLog_LogError(v18, v17, 0x22Fu, 0, 0, pvDataa);
LABEL_57:
        Error = _CatDBGetNonzeroLastError();
        goto LABEL_58;
      }
      if ( (unsigned int)_o_wcscat_s(Buffer, 260, L"\\Windows Defender\\MpClient.dll") )
      {
        SetLastError(0x32u);
        ErrLog_LogError(v20, v19, 0x239u, 0, 0, pvDataa);
        goto LABEL_57;
      }
    }
    LibraryW = LoadLibraryW(Buffer);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &hModule,
      LibraryW);
    if ( !hLibModule || (unsigned int)_o__wcsnicmp(qword_180032800, Buffer, 260) )
    {
      v24 = _o_wcscpy_s(qword_180032800, 260, Buffer);
      if ( v24 )
        ErrLog_LogError(v26, v25, 0x24Au, v24, 1, pvDataa);
      v27 = LoadLibraryW(Buffer);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        &hLibModule,
        v27);
    }
    if ( !hModule )
    {
      byte_1800312D8 = 0;
      ErrLog_LogError(v23, v22, 0x255u, 0, 0, pvDataa);
      goto LABEL_57;
    }
    if ( !byte_180032A18 )
    {
      ProcAddress = GetProcAddress(hModule, "MpSmartLockerEnable");
      if ( !ProcAddress )
      {
        ErrLog_LogError(v30, v29, 0x260u, 0, 0, pvDataa);
        goto LABEL_57;
      }
      v15 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
      if ( v15 < 0 )
        v15 = 0;
      else
        byte_180032A18 = 1;
    }
    if ( RpcImpersonateClient(BindingHandle) )
    {
      SetLastError(0x32u);
      ErrLog_LogError(v32, v31, 0x27Eu, 0, 0, pvDataa);
      goto LABEL_47;
    }
    v10 = 1;
    v33 = SourceString;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v34 = NtOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 7u, 0);
    Error = v34;
    LODWORD(SourceString) = v34;
    if ( v34 >= 0 )
    {
      v35 = FileHandle;
      if ( FileHandle )
        goto LABEL_35;
    }
    if ( ((v34 + 1073741773) & 0xFFFFFFF7) != 0 )
    {
      ErrLog_LogError(v36, (unsigned int)v35, 0x2B6u, 0, 0, pvDatab);
      goto LABEL_47;
    }
    Error = RtlDosPathNameToNtPathName_U_WithStatus(v33, &DestinationString, 0, 0);
    if ( Error < 0 )
    {
      ErrLog_LogError(v38, v37, 0x2A2u, 0, 0, pvDatab);
      goto LABEL_47;
    }
    v11 = 1;
    v55[1] = 1;
    Error = NtOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 7u, 0);
    LODWORD(SourceString) = Error;
    if ( Error >= 0 && (v35 = FileHandle) != 0 )
    {
LABEL_35:
      *(_DWORD *)a7 = 16;
      v40 = v58;
      v41 = v59;
      v42 = v60;
      while ( 1 )
      {
        v43 = InvokeMpQueryFileTrustByHandle2(hModule, v35, a5, v40, a7, v41, v42, v55);
        v15 = v43;
        if ( v43 != -2147024891 && v43 != -2147418107 )
          break;
        if ( !v10 )
          break;
        RpcRevertToSelf();
        v10 = 0;
        v35 = FileHandle;
      }
      Error = (int)SourceString;
      v11 = v55[1];
      if ( !v55[0] )
      {
        Error = 0;
        if ( v43 >= 0 )
          goto LABEL_58;
        goto LABEL_48;
      }
      ErrLog_LogError(v45, v44, 0x2E7u, 0, 0, pvDatad);
    }
    else
    {
      ErrLog_LogError(v39, (unsigned int)v35, 0x2B0u, 0, 0, pvDatac);
    }
  }
  else
  {
    SetLastError(0x32u);
    ErrLog_LogError(v47, v46, 0x278u, 0, 0, pvData);
  }
LABEL_47:
  if ( v15 < 0 )
  {
LABEL_48:
    Error = (unsigned __int16)v15;
    if ( (v15 & 0x1FFF0000) != 0x70000 )
      Error = v15;
    goto LABEL_58;
  }
  if ( Error >= 0 )
    goto LABEL_57;
  v48 = RtlNtStatusToDosErrorNoTeb(Error);
  if ( v48 != 317 )
    Error = v48;
LABEL_58:
  if ( v10 )
    RpcRevertToSelf();
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v11 )
    RtlFreeUnicodeString(&DestinationString);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800095cc  mov     rax, rsp
0x1800095cf  push    rbp
0x1800095d0  push    r12
0x1800095d2  push    r13
0x1800095d4  push    r14
0x1800095d6  push    r15
0x1800095d8  lea     rbp, [rax-228h]
0x1800095df  sub     rsp, 300h
0x1800095e6  mov     [rsp+320h+var_2B0], 0FFFFFFFFFFFFFFFEh
0x1800095ef  mov     [rax+18h], rsi
0x1800095f3  mov     [rax+20h], rdi
0x1800095f7  mov     rax, cs:__security_cookie
0x1800095fe  xor     rax, rsp
0x180009601  mov     [rbp+220h+var_30], rax
0x180009608  mov     [rsp+320h+SourceString], rdx
0x18000960d  mov     r13, rcx
0x180009610  mov     r12, [rbp+220h+arg_30]
0x180009617  mov     rax, [rbp+220h+arg_28]
0x18000961e  mov     [rsp+320h+var_2C8], rax
0x180009623  mov     rax, [rbp+220h+arg_38]
0x18000962a  mov     [rsp+320h+var_2C0], rax
0x18000962f  mov     rax, [rbp+220h+arg_40]
0x180009636  mov     [rsp+320h+var_2B8], rax
0x18000963b  xorps   xmm0, xmm0
0x18000963e  movups  xmmword ptr [rbp+220h+DestinationString.Length], xmm0
0x180009642  mov     [rsp+320h+FileHandle], 0
0x18000964b  xor     r14b, r14b
0x18000964e  movups  xmmword ptr [rbp+220h+IoStatusBlock], xmm0
0x180009652  xorps   xmm1, xmm1
0x180009655  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm1
0x180009659  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm1
0x18000965d  movups  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm1
0x180009661  xor     r15b, r15b
0x180009664  mov     [rsp+320h+var_2E0+1], r15b
0x180009669  mov     [rbp+220h+var_270], 208h
0x180009670  mov     [rsp+320h+hModule], 0
0x180009679  mov     [rsp+320h+var_2E0], r15b
0x18000967e  test    rcx, rcx
0x180009681  jz      loc_180009A90
0x180009687  cmp     r8d, 10h
0x18000968b  jnz     loc_180009A90
0x180009691  test    r12, r12
0x180009694  jz      loc_180009A90
0x18000969a  call    ?IsDefenderDisabled@@YAHXZ; IsDefenderDisabled(void)
0x18000969f  test    eax, eax
0x1800096a1  jz      short loc_1800096B9
0x1800096a3  mov     ecx, 422h; dwErrCode
0x1800096a8  call    cs:__imp_SetLastError
0x1800096ae  mov     r8d, 206h
0x1800096b4  jmp     loc_180009AA1
0x1800096b9  xor     esi, esi
0x1800096bb  xor     edi, edi
0x1800096bd  cmp     cs:byte_1800312D8, sil
0x1800096c4  jz      loc_180009A45
0x1800096ca  lea     rax, [rbp+220h+var_270]
0x1800096ce  mov     [rsp+320h+pcbData], rax; pcbData
0x1800096d3  lea     rax, [rbp+220h+Buffer]
0x1800096d7  mov     [rsp+320h+pvData], rax; int
0x1800096dc  mov     [rsp+320h+pdwType], rsi; pdwType
0x1800096e1  lea     r9d, [rsi+2]; dwFlags
0x1800096e5  lea     r8, Value; "InstallLocation"
0x1800096ec  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Defender"
0x1800096f3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800096fa  call    cs:__imp_RegGetValueW
0x180009700  test    eax, eax
0x180009702  jnz     short loc_18000971E
0x180009704  lea     r8, aMpclientDll; "MpClient.dll"
0x18000970b  mov     edx, 104h
0x180009710  lea     rcx, [rbp+220h+Buffer]
0x180009714  call    cs:__imp__o_wcscat_s
0x18000971a  test    eax, eax
0x18000971c  jz      short loc_180009783
0x18000971e  mov     r8d, 104h; nSize
0x180009724  lea     rdx, [rbp+220h+Buffer]; lpBuffer
0x180009728  lea     rcx, Name; "ProgramFiles"
0x18000972f  call    cs:__imp_GetEnvironmentVariableW
0x180009735  test    eax, eax
0x180009737  jnz     short loc_18000974F
0x180009739  mov     cs:byte_1800312D8, sil
0x180009740  mov     dword ptr [rsp+320h+pdwType], esi
0x180009744  mov     r8d, 22Fh
0x18000974a  jmp     loc_180009AA9
0x18000974f  lea     r8, aWindowsDefende; "\\Windows Defender\\MpClient.dll"
0x180009756  mov     edx, 104h
0x18000975b  lea     rcx, [rbp+220h+Buffer]
0x18000975f  call    cs:__imp__o_wcscat_s
0x180009765  test    eax, eax
0x180009767  jz      short loc_180009783
0x180009769  mov     ecx, 32h ; '2'; dwErrCode
0x18000976e  call    cs:__imp_SetLastError
0x180009774  mov     dword ptr [rsp+320h+pdwType], esi
0x180009778  mov     r8d, 239h
0x18000977e  jmp     loc_180009AA9
0x180009783  lea     rcx, [rbp+220h+Buffer]; lpLibFileName
0x180009787  call    cs:__imp_LoadLibraryW
0x18000978d  mov     rdx, rax
0x180009790  lea     rcx, [rsp+320h+hModule]
0x180009795  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000979a  cmp     cs:hLibModule, rsi
0x1800097a1  jz      short loc_1800097BE
0x1800097a3  mov     r8d, 104h
0x1800097a9  lea     rdx, [rbp+220h+Buffer]
0x1800097ad  lea     rcx, qword_180032800
0x1800097b4  call    cs:__imp__o__wcsnicmp
0x1800097ba  test    eax, eax
0x1800097bc  jz      short loc_180009807
0x1800097be  lea     r8, [rbp+220h+Buffer]
0x1800097c2  mov     edx, 104h
0x1800097c7  lea     rcx, qword_180032800
0x1800097ce  call    cs:__imp__o_wcscpy_s
0x1800097d4  test    eax, eax
0x1800097d6  jz      short loc_1800097EE
0x1800097d8  mov     dword ptr [rsp+320h+pdwType], 1; int
0x1800097e0  mov     r9d, eax; unsigned int
0x1800097e3  mov     r8d, 24Ah; unsigned int
0x1800097e9  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800097ee  lea     rcx, [rbp+220h+Buffer]; lpLibFileName
0x1800097f2  call    cs:__imp_LoadLibraryW
0x1800097f8  mov     rdx, rax
0x1800097fb  lea     rcx, hLibModule
0x180009802  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180009807  cmp     [rsp+320h+hModule], rsi
0x18000980c  jz      loc_180009A32
0x180009812  cmp     cs:byte_180032A18, sil
0x180009819  jnz     short loc_18000985C
0x18000981b  lea     rdx, aMpsmartlockere; "MpSmartLockerEnable"
0x180009822  mov     rcx, [rsp+320h+hModule]; hModule
0x180009827  call    cs:__imp_GetProcAddress
0x18000982d  test    rax, rax
0x180009830  jnz     short loc_180009841
0x180009832  mov     dword ptr [rsp+320h+pdwType], esi
0x180009836  mov     r8d, 260h
0x18000983c  jmp     loc_180009AA9
0x180009841  mov     ecx, 1
0x180009846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984b  mov     esi, eax
0x18000984d  test    eax, eax
0x18000984f  js      short loc_18000985A
0x180009851  mov     cs:byte_180032A18, 1
0x180009858  jmp     short loc_18000985C
0x18000985a  xor     esi, esi
0x18000985c  mov     rcx, r13; BindingHandle
0x18000985f  call    cs:__imp_RpcImpersonateClient
0x180009865  test    eax, eax
0x180009867  jz      short loc_180009883
0x180009869  mov     ecx, 32h ; '2'; dwErrCode
0x18000986e  call    cs:__imp_SetLastError
0x180009874  mov     dword ptr [rsp+320h+pdwType], edi
0x180009878  mov     r8d, 27Eh
0x18000987e  jmp     loc_180009A5A
0x180009883  mov     r14b, 1
0x180009886  mov     r13, [rsp+320h+SourceString]
0x18000988b  mov     rdx, r13; SourceString
0x18000988e  lea     rcx, [rbp+220h+DestinationString]; DestinationString
0x180009892  call    cs:__imp_RtlInitUnicodeString
0x180009898  mov     [rbp+220h+ObjectAttributes.Length], 30h ; '0'
0x18000989f  mov     [rbp+220h+ObjectAttributes.RootDirectory], rdi
0x1800098a3  mov     [rbp+220h+ObjectAttributes.Attributes], 40h ; '@'
0x1800098aa  lea     rax, [rbp+220h+DestinationString]
0x1800098ae  mov     [rbp+220h+ObjectAttributes.ObjectName], rax
0x1800098b2  xorps   xmm0, xmm0
0x1800098b5  movdqu  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800098ba  mov     dword ptr [rsp+320h+pvData], edi; OpenOptions
0x1800098be  mov     dword ptr [rsp+320h+pdwType], 7; ShareAccess
0x1800098c6  lea     r9, [rbp+220h+IoStatusBlock]; IoStatusBlock
0x1800098ca  lea     r8, [rbp+220h+ObjectAttributes]; ObjectAttributes
0x1800098ce  mov     edx, 80000000h; DesiredAccess
0x1800098d3  lea     rcx, [rsp+320h+FileHandle]; FileHandle
0x1800098d8  call    cs:__imp_NtOpenFile
0x1800098de  mov     edi, eax
0x1800098e0  mov     dword ptr [rsp+320h+SourceString], eax
0x1800098e4  test    eax, eax
0x1800098e6  js      short loc_1800098F6
0x1800098e8  mov     rdx, [rsp+320h+FileHandle]
0x1800098ed  test    rdx, rdx
0x1800098f0  jnz     loc_18000998D
0x1800098f6  add     eax, 3FFFFFCDh
0x1800098fb  test    eax, 0FFFFFFF7h
0x180009900  jz      short loc_180009915
0x180009902  mov     dword ptr [rsp+320h+pdwType], 0
0x18000990a  mov     r8d, 2B6h
0x180009910  jmp     loc_180009A5A
0x180009915  xor     r9d, r9d
0x180009918  xor     r8d, r8d
0x18000991b  lea     rdx, [rbp+220h+DestinationString]
0x18000991f  mov     rcx, r13
0x180009922  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180009928  mov     edi, eax
0x18000992a  test    eax, eax
0x18000992c  jns     short loc_180009941
0x18000992e  mov     dword ptr [rsp+320h+pdwType], 0
0x180009936  mov     r8d, 2A2h
0x18000993c  jmp     loc_180009A5A
0x180009941  mov     r15b, r14b
0x180009944  mov     [rsp+320h+var_2E0+1], r14b
0x180009949  mov     dword ptr [rsp+320h+pvData], 0; OpenOptions
0x180009951  mov     dword ptr [rsp+320h+pdwType], 7; ShareAccess
0x180009959  lea     r9, [rbp+220h+IoStatusBlock]; IoStatusBlock
0x18000995d  lea     r8, [rbp+220h+ObjectAttributes]; ObjectAttributes
0x180009961  mov     edx, 80000000h; DesiredAccess
0x180009966  lea     rcx, [rsp+320h+FileHandle]; FileHandle
0x18000996b  call    cs:__imp_NtOpenFile
0x180009971  mov     edi, eax
0x180009973  mov     dword ptr [rsp+320h+SourceString], eax
0x180009977  test    eax, eax
0x180009979  js      loc_180009A22
0x18000997f  mov     rdx, [rsp+320h+FileHandle]; void *
0x180009984  test    rdx, rdx
0x180009987  jz      loc_180009A22
0x18000998d  mov     dword ptr [r12], 10h
0x180009995  mov     r13, [rsp+320h+var_2C8]
0x18000999a  mov     r15, [rsp+320h+var_2C0]
0x18000999f  mov     rdi, [rsp+320h+var_2B8]
0x1800099a4  lea     rax, [rsp+320h+var_2E0]
0x1800099a9  mov     [rsp+320h+var_2E8], rax; unsigned __int8 *
0x1800099ae  mov     [rsp+320h+pcbData], rdi; struct tagMPFILE_TRUST_EXTRA_INFO **
0x1800099b3  mov     [rsp+320h+pvData], r15; unsigned int *
0x1800099b8  mov     [rsp+320h+pdwType], r12; struct tagMPTRUST_INFO *
0x1800099bd  mov     r9, r13; struct tagMPFILE_TRUST_EXTRA_INFO *
0x1800099c0  mov     r8d, [rbp+220h+arg_20]; unsigned int
0x1800099c7  mov     rcx, [rsp+320h+hModule]; HINSTANCE
0x1800099cc  call    ?InvokeMpQueryFileTrustByHandle2@@YAJPEAUHINSTANCE__@@PEAXKPEAUtagMPFILE_TRUST_EXTRA_INFO@@PEAUtagMPTRUST_INFO@@PEAKPEAPEAU2@PEAE@Z; InvokeMpQueryFileTrustByHandle2(HINSTANCE__ *,void *,ulong,tagMPFILE_TRUST_EXTRA_INFO *,tagMPTRUST_INFO *,ulong *,tagMPFILE_TRUST_EXTRA_INFO * *,uchar *)
0x1800099d1  mov     esi, eax
0x1800099d3  cmp     eax, 80070005h
0x1800099d8  jz      short loc_1800099E1
0x1800099da  cmp     eax, 80010005h
0x1800099df  jnz     short loc_1800099F6
0x1800099e1  test    r14b, r14b
0x1800099e4  jz      short loc_1800099F6
0x1800099e6  call    cs:__imp_RpcRevertToSelf
0x1800099ec  xor     r14b, r14b
0x1800099ef  mov     rdx, [rsp+320h+FileHandle]
0x1800099f4  jmp     short loc_1800099A4
0x1800099f6  cmp     [rsp+320h+var_2E0], 0
0x1800099fb  mov     edi, dword ptr [rsp+320h+SourceString]
0x1800099ff  mov     r15b, [rsp+320h+var_2E0+1]
0x180009a04  jz      short loc_180009A16
0x180009a06  mov     dword ptr [rsp+320h+pdwType], 0
0x180009a0e  mov     r8d, 2E7h
0x180009a14  jmp     short loc_180009A5A
0x180009a16  xor     edi, edi
0x180009a18  test    eax, eax
0x180009a1a  jns     loc_180009AB8
0x180009a20  jmp     short loc_180009A66
0x180009a22  mov     dword ptr [rsp+320h+pdwType], 0
0x180009a2a  mov     r8d, 2B0h
0x180009a30  jmp     short loc_180009A5A
0x180009a32  mov     cs:byte_1800312D8, sil
0x180009a39  mov     dword ptr [rsp+320h+pdwType], esi
0x180009a3d  mov     r8d, 255h
0x180009a43  jmp     short loc_180009AA9
0x180009a45  mov     ecx, 32h ; '2'; dwErrCode
0x180009a4a  call    cs:__imp_SetLastError
0x180009a50  mov     dword ptr [rsp+320h+pdwType], esi; int
0x180009a54  mov     r8d, 278h; unsigned int
0x180009a5a  xor     r9d, r9d; unsigned int
0x180009a5d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180009a62  test    esi, esi
0x180009a64  jns     short loc_180009A7A
0x180009a66  mov     eax, esi
0x180009a68  and     eax, 1FFF0000h
0x180009a6d  movzx   edi, si
0x180009a70  cmp     eax, 70000h
0x180009a75  cmovnz  edi, esi
0x180009a78  jmp     short loc_180009AB8
0x180009a7a  test    edi, edi
0x180009a7c  jns     short loc_180009AB1
0x180009a7e  mov     ecx, edi; Status
0x180009a80  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009a86  cmp     eax, 13Dh
0x180009a8b  cmovnz  edi, eax
0x180009a8e  jmp     short loc_180009AB8
0x180009a90  mov     ecx, 0A0h; dwErrCode
0x180009a95  call    cs:__imp_SetLastError
0x180009a9b  mov     r8d, 201h; unsigned int
0x180009aa1  mov     dword ptr [rsp+320h+pdwType], 0; int
0x180009aa9  xor     r9d, r9d; unsigned int
0x180009aac  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180009ab1  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180009ab6  mov     edi, eax
0x180009ab8  test    r14b, r14b
0x180009abb  jz      short loc_180009AC3
0x180009abd  call    cs:__imp_RpcRevertToSelf
0x180009ac3  mov     rcx, [rsp+320h+FileHandle]; Handle
0x180009ac8  test    rcx, rcx
0x180009acb  jz      short loc_180009AD3
0x180009acd  call    cs:__imp_NtClose
0x180009ad3  test    r15b, r15b
0x180009ad6  jz      short loc_180009AE3
0x180009ad8  lea     rcx, [rbp+220h+DestinationString]; UnicodeString
0x180009adc  call    cs:__imp_RtlFreeUnicodeString
0x180009ae2  nop
0x180009ae3  lea     rcx, [rsp+320h+hModule]
0x180009ae8  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180009aed  mov     eax, edi
0x180009aef  mov     rcx, [rbp+220h+var_30]
0x180009af6  xor     rcx, rsp; StackCookie
0x180009af9  call    __security_check_cookie
0x180009afe  lea     r11, [rsp+320h+var_20]
0x180009b06  mov     rsi, [r11+40h]
  ... truncated ...
```
