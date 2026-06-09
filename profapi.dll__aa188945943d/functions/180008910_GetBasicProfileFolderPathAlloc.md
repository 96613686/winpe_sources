# GetBasicProfileFolderPathAlloc

- ea: `0x180008910`
- end: `0x180008cda`
- name: `GetBasicProfileFolderPathAlloc`
- size: `970`
- prototype: `int __fastcall(int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006de0`
- `0x180007e40`
- `0x1800087f0`
- `0x180008910`
- `0x180009488`
- `0x180016250`

## callees

- `0x180001ab8`
- `0x180003e20`
- `0x180003fdc`
- `0x180004990`
- `0x180005b60`
- `0x180005b90`
- `0x18000608c`
- `0x180006ad0`
- `0x180008910`
- `0x180009120`
- `0x1800091f0`
- `0x180009488`
- `0x18000a914`
- `0x18000bbc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008afe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008afe`

## string_xrefs

- `0x18000898c`: `ProgramData`
- `0x180008979`: `minio\profapi\path.cpp`
- `0x180008a3a`: `minio\profapi\path.cpp`
- `0x180008b4e`: `minio\profapi\path.cpp`
- `0x180008b7c`: `minio\profapi\path.cpp`
- `0x180008ba6`: `minio\profapi\path.cpp`
- `0x180008ca4`: `minio\profapi\path.cpp`
- `0x180008a09`: `ProfileImagePath`
- `0x180008b0b`: `ProfilesDirectory`

## pseudocode

```c
int __fastcall GetBasicProfileFolderPathAlloc(int a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  const unsigned __int16 *v4; // rsi
  wchar_t *v6; // rcx
  int PerMachinePathFromProfileList; // eax
  int v8; // ecx
  unsigned __int16 *v9; // rbx
  const unsigned __int16 *v10; // r8
  int v11; // eax
  int v12; // esi
  int v13; // eax
  int v14; // esi
  int IsRunningInAppContainer; // eax
  int BasicProfileFolderPathAlloc; // ebx
  int SidStringFromSelf; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  unsigned __int16 *v21; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+28h] [rbp-28h]
  __int64 v23; // [rsp+30h] [rbp-20h]
  _QWORD v24[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v26; // [rsp+70h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp+30h] BYREF

  *a3 = 0;
  v4 = a2;
  switch ( a1 )
  {
    case 1:
      v6 = L"ProfilesDirectory";
      goto LABEL_11;
    case 2:
      v6 = L"Default";
      goto LABEL_11;
    case 4:
      v6 = (wchar_t *)L"ProgramData";
LABEL_11:
      PerMachinePathFromProfileList = _GetPerMachinePathFromProfileList((char *)v6, a3);
      v8 = 0;
      if ( PerMachinePathFromProfileList < 0 )
        return PerMachinePathFromProfileList;
      return v8;
    case 3:
      v6 = L"Public";
      goto LABEL_11;
  }
  if ( a1 != 5 )
  {
    switch ( a1 )
    {
      case 7:
        hObject = 0;
        if ( !a2 )
        {
          SidStringFromSelf = _GetSidStringFromSelf((unsigned __int16 **)&hObject);
          BasicProfileFolderPathAlloc = SidStringFromSelf;
          if ( SidStringFromSelf < 0 )
          {
            v18 = 282;
            break;
          }
          v4 = (const unsigned __int16 *)hObject;
        }
        SidStringFromSelf = _GetUserFolderPathFromSid(v4, L"AppData", a3);
        BasicProfileFolderPathAlloc = SidStringFromSelf;
        if ( SidStringFromSelf >= 0 )
        {
          if ( IsWin32DeviceNamespacePathWithoutDriveLetter(*a3) )
          {
            v19 = 292;
LABEL_43:
            BasicProfileFolderPathAlloc = wil::details::in1diag3::Return_Win32(
                                            retaddr,
                                            (void *)v19,
                                            (unsigned int)"minio\\profapi\\path.cpp",
                                            (const char *)0xA1,
                                            (unsigned int)v21);
            goto LABEL_44;
          }
LABEL_52:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hObject);
          return 0;
        }
        v18 = 285;
        break;
      case 8:
        hObject = 0;
        if ( !a2 )
        {
          SidStringFromSelf = _GetSidStringFromSelf((unsigned __int16 **)&hObject);
          BasicProfileFolderPathAlloc = SidStringFromSelf;
          if ( SidStringFromSelf < 0 )
          {
            v18 = 300;
            break;
          }
          v4 = (const unsigned __int16 *)hObject;
        }
        SidStringFromSelf = _GetUserFolderPathFromSid(v4, L"Local AppData", a3);
        BasicProfileFolderPathAlloc = SidStringFromSelf;
        if ( SidStringFromSelf >= 0 )
        {
          if ( IsWin32DeviceNamespacePathWithoutDriveLetter(*a3) )
          {
            v19 = 310;
            goto LABEL_43;
          }
          goto LABEL_52;
        }
        v18 = 303;
        break;
      case 6:
        v26 = 0;
        hObject = 0;
        IsRunningInAppContainer = _IsRunningInAppContainer(&v26, &hObject);
        BasicProfileFolderPathAlloc = IsRunningInAppContainer;
        if ( IsRunningInAppContainer < 0 )
        {
          v20 = 318;
        }
        else
        {
          if ( !v26 )
          {
            BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(8, v4, a3);
            if ( BasicProfileFolderPathAlloc < 0 )
            {
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hObject);
              return BasicProfileFolderPathAlloc;
            }
            goto LABEL_64;
          }
          IsRunningInAppContainer = _GetAppContainerFolderPath(hObject, a3);
          BasicProfileFolderPathAlloc = IsRunningInAppContainer;
          if ( IsRunningInAppContainer >= 0 )
          {
LABEL_64:
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
            return 0;
          }
          v20 = 323;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"minio\\profapi\\path.cpp",
          (const char *)(unsigned int)IsRunningInAppContainer,
          (int)v21);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        return BasicProfileFolderPathAlloc;
      default:
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x14D,
                 (unsigned int)"minio\\profapi\\path.cpp",
                 (const char *)0x32,
                 (unsigned int)v21);
    }
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)(unsigned int)SidStringFromSelf,
      (int)v21);
LABEL_44:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hObject);
    return BasicProfileFolderPathAlloc;
  }
  v9 = 0;
  hObject = 0;
  if ( !a2 )
  {
    SidStringFromSelf = _GetSidStringFromSelf((unsigned __int16 **)&hObject);
    BasicProfileFolderPathAlloc = SidStringFromSelf;
    if ( SidStringFromSelf < 0 )
    {
      v18 = 264;
      goto LABEL_38;
    }
    v9 = (unsigned __int16 *)hObject;
  }
  v24[0] = 0;
  v10 = v9;
  v24[1] = 0;
  if ( v4 )
    v10 = v4;
  v24[2] = 0;
  v11 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          v24,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\%s",
          v10);
  v12 = v11;
  if ( v11 == -2147024894 )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v24);
    BasicProfileFolderPathAlloc = -2147024894;
    goto LABEL_44;
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)(unsigned int)v11,
      (int)v21);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v24);
    BasicProfileFolderPathAlloc = v12;
    goto LABEL_44;
  }
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
          &v21,
          -2147483646,
          v24[0],
          L"ProfileImagePath");
  v14 = v13;
  if ( v13 >= 0 )
  {
    *a3 = v21;
    v21 = 0;
    v23 = 0;
    v22 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v24);
    if ( v9 )
      LocalFree(v9);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x111,
    (unsigned int)"minio\\profapi\\path.cpp",
    (const char *)(unsigned int)v13,
    (int)v21);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v24);
  if ( v9 )
    LocalFree(v9);
  return v14;
}

```

## disassembly

```asm
0x180008910  mov     [rsp-18h+arg_8], rbx
0x180008915  mov     [rsp-18h+arg_18], rsi
0x18000891a  push    rbp
0x18000891b  push    rdi
0x18000891c  push    r14
0x18000891e  mov     rbp, rsp
0x180008921  sub     rsp, 50h
0x180008925  xor     r14d, r14d
0x180008928  mov     rdi, r8
0x18000892b  mov     [r8], r14
0x18000892e  mov     rsi, rdx
0x180008931  cmp     ecx, 1
0x180008934  jz      loc_180008B0B
0x18000893a  cmp     ecx, 2
0x18000893d  jz      loc_180008B17
0x180008943  cmp     ecx, 4
0x180008946  jz      short loc_18000898C
0x180008948  cmp     ecx, 3
0x18000894b  jz      loc_180008B23
0x180008951  cmp     ecx, 5
0x180008954  jz      short loc_1800089BA
0x180008956  cmp     ecx, 7
0x180008959  jz      loc_180008BC8
0x18000895f  cmp     ecx, 8
0x180008962  jz      loc_180008C2A
0x180008968  cmp     ecx, 6
0x18000896b  jz      loc_180008A75
0x180008971  mov     rcx, [rbp+18h]; this
0x180008975  lea     r9d, [r14+32h]; char *
0x180008979  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180008980  mov     edx, 14Dh; void *
0x180008985  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000898a  jmp     short loc_1800089A5
0x18000898c  lea     rcx, aProgramdata; "ProgramData"
0x180008993  mov     rdx, rdi; unsigned __int16 **
0x180008996  call    ?_GetPerMachinePathFromProfileList@@YAJPEBGPEAPEAG@Z; _GetPerMachinePathFromProfileList(ushort const *,ushort * *)
0x18000899b  test    eax, eax
0x18000899d  mov     ecx, r14d
0x1800089a0  cmovs   ecx, eax
0x1800089a3  mov     eax, ecx
0x1800089a5  lea     r11, [rsp+50h+var_s0]
0x1800089aa  mov     rbx, [r11+28h]
0x1800089ae  mov     rsi, [r11+38h]
0x1800089b2  mov     rsp, r11
0x1800089b5  pop     r14
0x1800089b7  pop     rdi
0x1800089b8  pop     rbp
0x1800089b9  retn
0x1800089ba  mov     rbx, r14
0x1800089bd  mov     [rbp+hObject], rbx
0x1800089c1  test    rsi, rsi
0x1800089c4  jz      loc_180008B2F
0x1800089ca  test    rsi, rsi
0x1800089cd  mov     [rbp+var_18], r14
0x1800089d1  mov     r8, rbx
0x1800089d4  mov     [rbp+var_10], r14
0x1800089d8  cmovnz  r8, rsi
0x1800089dc  mov     [rbp+var_8], r14
0x1800089e0  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800089e7  lea     rcx, [rbp+var_18]
0x1800089eb  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800089f0  mov     esi, eax
0x1800089f2  cmp     eax, 80070002h
0x1800089f7  jz      loc_180008B68
0x1800089fd  test    eax, eax
0x1800089ff  js      loc_180008B78
0x180008a05  mov     r8, [rbp+var_18]
0x180008a09  lea     r9, aProfileimagepa; "ProfileImagePath"
0x180008a10  mov     rdx, 0FFFFFFFF80000002h
0x180008a17  mov     [rbp+var_30], r14
0x180008a1b  lea     rcx, [rbp+var_30]
0x180008a1f  mov     [rbp+var_28], r14
0x180008a23  mov     [rbp+var_20], r14
0x180008a27  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180008a2c  mov     esi, eax
0x180008a2e  test    eax, eax
0x180008a30  jns     loc_180008AD1
0x180008a36  mov     rcx, [rbp+18h]; this
0x180008a3a  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180008a41  mov     r9d, eax; char *
0x180008a44  mov     edx, 111h; void *
0x180008a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a4e  lea     rcx, [rbp+var_30]
0x180008a52  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008a57  lea     rcx, [rbp+var_18]
0x180008a5b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008a60  test    rbx, rbx
0x180008a63  jz      short loc_180008A6E
0x180008a65  mov     rcx, rbx; hMem
0x180008a68  call    cs:__imp_LocalFree
0x180008a6e  mov     eax, esi
0x180008a70  jmp     loc_1800089A5
0x180008a75  lea     rdx, [rbp+hObject]; void **
0x180008a79  mov     [rbp+arg_0], r14d
0x180008a7d  lea     rcx, [rbp+arg_0]; int *
0x180008a81  mov     [rbp+hObject], r14
0x180008a85  call    ?_IsRunningInAppContainer@@YAJPEAHPEAPEAX@Z; _IsRunningInAppContainer(int *,void * *)
0x180008a8a  mov     ebx, eax
0x180008a8c  test    eax, eax
0x180008a8e  js      loc_180008C82
0x180008a94  cmp     [rbp+arg_0], r14d
0x180008a98  jnz     loc_180008C89
0x180008a9e  mov     r8, rdi
0x180008aa1  mov     rdx, rsi
0x180008aa4  mov     ecx, 8
0x180008aa9  call    GetBasicProfileFolderPathAlloc
0x180008aae  mov     ebx, eax
0x180008ab0  test    eax, eax
0x180008ab2  jns     loc_180008CCC
0x180008ab8  mov     rcx, [rbp+hObject]; hObject
0x180008abc  lea     rdx, [rcx-1]
0x180008ac0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180008ac4  jbe     loc_180008CC1
0x180008aca  mov     eax, ebx
0x180008acc  jmp     loc_1800089A5
0x180008ad1  mov     rax, [rbp+var_30]
0x180008ad5  lea     rcx, [rbp+var_30]
0x180008ad9  mov     [rdi], rax
0x180008adc  mov     [rbp+var_30], r14
0x180008ae0  mov     [rbp+var_20], r14
0x180008ae4  mov     [rbp+var_28], r14
0x180008ae8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008aed  lea     rcx, [rbp+var_18]
0x180008af1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008af6  test    rbx, rbx
0x180008af9  jz      short loc_180008B04
0x180008afb  mov     rcx, rbx; hMem
0x180008afe  call    cs:__imp_LocalFree
0x180008b04  xor     eax, eax
0x180008b06  jmp     loc_1800089A5
0x180008b0b  lea     rcx, aProfilesdirect; "ProfilesDirectory"
0x180008b12  jmp     loc_180008993
0x180008b17  lea     rcx, aDefault; "Default"
0x180008b1e  jmp     loc_180008993
0x180008b23  lea     rcx, aPublic; "Public"
0x180008b2a  jmp     loc_180008993
0x180008b2f  lea     rcx, [rbp+hObject]; unsigned __int16 **
0x180008b33  call    ?_GetSidStringFromSelf@@YAJPEAPEAG@Z; _GetSidStringFromSelf(ushort * *)
0x180008b38  mov     ebx, eax
0x180008b3a  test    eax, eax
0x180008b3c  jns     short loc_180008B5F
0x180008b3e  mov     edx, 108h
0x180008b43  jmp     short loc_180008B4A
0x180008b45  mov     edx, 12Fh; void *
0x180008b4a  mov     rcx, [rbp+18h]; this
0x180008b4e  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180008b55  mov     r9d, eax; char *
0x180008b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b5d  jmp     short loc_180008BBA
0x180008b5f  mov     rbx, [rbp+hObject]
0x180008b63  jmp     loc_1800089CA
0x180008b68  lea     rcx, [rbp+var_18]
0x180008b6c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008b71  mov     ebx, 80070002h
0x180008b76  jmp     short loc_180008BBA
0x180008b78  mov     rcx, [rbp+18h]; this
0x180008b7c  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180008b83  mov     r9d, esi; char *
0x180008b86  mov     edx, 10Eh; void *
0x180008b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b90  lea     rcx, [rbp+var_18]
0x180008b94  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008b99  mov     ebx, esi
0x180008b9b  jmp     short loc_180008BBA
0x180008b9d  mov     edx, 124h; void *
0x180008ba2  mov     rcx, [rbp+18h]; this
0x180008ba6  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180008bad  mov     r9d, 0A1h; char *
0x180008bb3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008bb8  mov     ebx, eax
0x180008bba  lea     rcx, [rbp+hObject]
0x180008bbe  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180008bc3  jmp     loc_180008ACA
0x180008bc8  mov     [rbp+hObject], r14
0x180008bcc  test    rsi, rsi
0x180008bcf  jnz     short loc_180008BEE
0x180008bd1  lea     rcx, [rbp+hObject]; unsigned __int16 **
0x180008bd5  call    ?_GetSidStringFromSelf@@YAJPEAPEAG@Z; _GetSidStringFromSelf(ushort * *)
0x180008bda  mov     ebx, eax
0x180008bdc  test    eax, eax
0x180008bde  jns     short loc_180008BEA
0x180008be0  mov     edx, 11Ah
0x180008be5  jmp     loc_180008B4A
0x180008bea  mov     rsi, [rbp+hObject]
0x180008bee  mov     r8, rdi; unsigned __int16 **
0x180008bf1  lea     rdx, aAppdata_0; "AppData"
0x180008bf8  mov     rcx, rsi; unsigned __int16 *
0x180008bfb  call    ?_GetUserFolderPathFromSid@@YAJPEBG0PEAPEAG@Z; _GetUserFolderPathFromSid(ushort const *,ushort const *,ushort * *)
0x180008c00  mov     ebx, eax
0x180008c02  test    eax, eax
0x180008c04  jns     short loc_180008C10
0x180008c06  mov     edx, 11Dh
0x180008c0b  jmp     loc_180008B4A
0x180008c10  mov     rcx, [rdi]; lpString1
0x180008c13  call    ?IsWin32DeviceNamespacePathWithoutDriveLetter@@YA_NPEBG@Z; IsWin32DeviceNamespacePathWithoutDriveLetter(ushort const *)
0x180008c18  test    al, al
0x180008c1a  jnz     short loc_180008B9D
0x180008c1c  lea     rcx, [rbp+hObject]
0x180008c20  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180008c25  jmp     loc_180008B04
0x180008c2a  mov     [rbp+hObject], r14
0x180008c2e  test    rsi, rsi
0x180008c31  jnz     short loc_180008C50
0x180008c33  lea     rcx, [rbp+hObject]; unsigned __int16 **
0x180008c37  call    ?_GetSidStringFromSelf@@YAJPEAPEAG@Z; _GetSidStringFromSelf(ushort * *)
0x180008c3c  mov     ebx, eax
0x180008c3e  test    eax, eax
0x180008c40  jns     short loc_180008C4C
0x180008c42  mov     edx, 12Ch
0x180008c47  jmp     loc_180008B4A
0x180008c4c  mov     rsi, [rbp+hObject]
0x180008c50  mov     r8, rdi; unsigned __int16 **
0x180008c53  lea     rdx, aLocalAppdata; "Local AppData"
0x180008c5a  mov     rcx, rsi; unsigned __int16 *
0x180008c5d  call    ?_GetUserFolderPathFromSid@@YAJPEBG0PEAPEAG@Z; _GetUserFolderPathFromSid(ushort const *,ushort const *,ushort * *)
0x180008c62  mov     ebx, eax
0x180008c64  test    eax, eax
0x180008c66  js      loc_180008B45
0x180008c6c  mov     rcx, [rdi]; lpString1
0x180008c6f  call    ?IsWin32DeviceNamespacePathWithoutDriveLetter@@YA_NPEBG@Z; IsWin32DeviceNamespacePathWithoutDriveLetter(ushort const *)
0x180008c74  test    al, al
0x180008c76  jz      short loc_180008C1C
0x180008c78  mov     edx, 136h
0x180008c7d  jmp     loc_180008BA2
0x180008c82  mov     edx, 13Eh
0x180008c87  jmp     short loc_180008CA0
0x180008c89  mov     rcx, [rbp+hObject]; void *
0x180008c8d  mov     rdx, rdi; unsigned __int16 **
0x180008c90  call    ?_GetAppContainerFolderPath@@YAJPEAXPEAPEAG@Z; _GetAppContainerFolderPath(void *,ushort * *)
0x180008c95  mov     ebx, eax
0x180008c97  test    eax, eax
0x180008c99  jns     short loc_180008CCC
0x180008c9b  mov     edx, 143h; void *
0x180008ca0  mov     rcx, [rbp+18h]; this
0x180008ca4  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180008cab  mov     r9d, eax; char *
0x180008cae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cb3  lea     rcx, [rbp+hObject]
0x180008cb7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008cbc  jmp     loc_180008ACA
0x180008cc1  call    cs:__imp_CloseHandle
0x180008cc7  jmp     loc_180008ACA
0x180008ccc  lea     rcx, [rbp+hObject]
0x180008cd0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008cd5  jmp     loc_180008B04
```
