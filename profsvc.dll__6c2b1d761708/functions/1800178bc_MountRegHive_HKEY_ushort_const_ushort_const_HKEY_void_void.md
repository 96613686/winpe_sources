# MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)

- ea: `0x1800178bc`
- end: `0x180017d8d`
- name: `?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z`
- size: `1233`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, HKEY, HANDLE hToken, void **)`
- caller_count: `5`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016150`
- `0x18002f844`
- `0x180030050`
- `0x180038798`
- `0x18003b26c`

## callees

- `0x18000721c`
- `0x180007bc0`
- `0x180007c2c`
- `0x180007d40`
- `0x1800084bc`
- `0x18000b060`
- `0x18000d030`
- `0x18000e1a0`
- `0x180014aec`
- `0x1800178bc`
- `0x180017d94`
- `0x180017e3c`
- `0x180017fdc`
- `0x180024be0`
- `0x180030ad0`
- `0x180035860`
- `0x180036438`
- `0x18003651c`
- `0x1800366ec`
- `0x18003bc70`
- `0x18003c870`
- `0x180042880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017b1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017b1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017b02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017b02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c84`
- `ntdll!NtLoadKeyEx` at `0x180017c1c`
- `ntdll!NtLoadKeyEx` at `0x180017c1c`
- `ntdll!NtLoadKey3` at `0x180017be6`
- `ntdll!NtLoadKey3` at `0x180017be6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180017a57`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180017a57`
- `ntdll!RtlInitUnicodeString` at `0x180017a12`
- `ntdll!RtlInitUnicodeString` at `0x180017a12`
- `ntdll!RtlNtStatusToDosError` at `0x180017c3d`
- `ntdll!RtlNtStatusToDosError` at `0x180017c3d`
- `ntdll!RtlFreeUnicodeString` at `0x180017b83`
- `ntdll!RtlFreeUnicodeString` at `0x180017d3f`
- `ntdll!RtlFreeUnicodeString` at `0x180017b83`
- `ntdll!RtlFreeUnicodeString` at `0x180017d3f`

## string_xrefs

- `0x1800179c8`: `\Registry\User\%ws`
- `0x18001791b`: `MountRegHive`
- `0x1800179e9`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180017a87`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180017b59`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180017cb5`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180017cf1`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180017a73`: `Failed to convert file path <%ws> to NT object namespace path.`

## pseudocode

```c
__int64 __fastcall MountRegHive(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HKEY a4,
        HANDLE hToken,
        void **a6)
{
  char v9; // r12
  int v10; // eax
  unsigned int v11; // ebx
  PCWSTR v12; // rbx
  HANDLE CurrentThread; // rax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  ULONG v18; // eax
  const wchar_t **v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // r8
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-E0h]
  char *v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR SourceString[3]; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES SourceFile; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES TargetKey; // [rsp+C0h] [rbp-40h] BYREF
  char v33[8]; // [rsp+F0h] [rbp-10h] BYREF
  HKEY v34; // [rsp+F8h] [rbp-8h]
  char v35; // [rsp+100h] [rbp+0h]
  HANDLE v36; // [rsp+108h] [rbp+8h]
  void **v37; // [rsp+110h] [rbp+10h] BYREF
  int v38; // [rsp+118h] [rbp+18h] BYREF
  char v39; // [rsp+11Ch] [rbp+1Ch]
  int v40; // [rsp+140h] [rbp+40h] BYREF
  const char *v41; // [rsp+148h] [rbp+48h]
  __int64 v42; // [rsp+150h] [rbp+50h]
  char v43; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+160h] [rbp+60h]
  _BYTE v45[152]; // [rsp+168h] [rbp+68h] BYREF
  __int128 v46; // [rsp+200h] [rbp+100h]
  int v47; // [rsp+210h] [rbp+110h]
  __int64 v48; // [rsp+218h] [rbp+118h]
  int *v49; // [rsp+220h] [rbp+120h]
  __int64 v50; // [rsp+228h] [rbp+128h]
  __int64 v51; // [rsp+230h] [rbp+130h]
  void ***v52; // [rsp+238h] [rbp+138h]
  __int64 v53; // [rsp+240h] [rbp+140h]
  int v54; // [rsp+248h] [rbp+148h]
  int *v55; // [rsp+250h] [rbp+150h]
  char v56; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v9 = 0;
  LODWORD(v25) = 0;
  *a6 = 0;
  v38 = 0;
  v39 = 0;
  v43 = 0;
  v40 = 0;
  v41 = "MountRegHive";
  v42 = 0;
  v44 = 0;
  v46 = 0;
  memset_0(v45, 0, sizeof(v45));
  v47 = 1;
  v48 = 0;
  v49 = &v38;
  v50 = 0;
  v51 = 0;
  v52 = &v37;
  v53 = 0;
  v54 = 0;
  v55 = &v40;
  v56 = 0;
  v37 = &ProfileTelemetry::MountRegHive::`vftable';
  ProfileTelemetry::MountRegHive::StartActivity((ProfileTelemetry::MountRegHive *)&v37, a2);
  memset(SourceString, 0, sizeof(SourceString));
  v10 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          SourceString,
          L"\\Registry\\User\\%ws",
          a2);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
      (const char *)(unsigned int)v10,
      v23);
    goto LABEL_27;
  }
  DestinationString = 0;
  v12 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, SourceString[0]);
  *(_QWORD *)&TargetKey.Length = 48;
  *(_QWORD *)&TargetKey.Attributes = 64;
  TargetKey.RootDirectory = 0;
  TargetKey.ObjectName = &DestinationString;
  *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
  NtPathName = 0;
  if ( RtlDosPathNameToNtPathName_U(a3, &NtPathName, 0, 0) )
  {
    *(_QWORD *)&SourceFile.Length = 48;
    *(_QWORD *)&SourceFile.Attributes = 64;
    SourceFile.RootDirectory = 0;
    SourceFile.ObjectName = &NtPathName;
    *(_OWORD *)&SourceFile.SecurityDescriptor = 0;
    LODWORD(v25) = 18;
    WORD2(v25) = 0;
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle)
      && (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
      || (v15 = PrivilegeAdjuster::AdjustPrivilegeIfNecessary((PrivilegeAdjuster *)&v25), v11 = v15, v15 >= 0) )
    {
      if ( hToken && (unsigned int)CheckFullAccessOnFile(hToken, a3) )
      {
        v33[0] = 1;
        v34 = a4;
        v35 = 3;
        v36 = hToken;
        v16 = NtLoadKey3(&TargetKey, &SourceFile, 2048, v33, 2, 131097, a6, 0, v25);
      }
      else
      {
        v24 = (char *)a6;
        v16 = NtLoadKeyEx(&TargetKey, &SourceFile, 0x800u, a4);
      }
      v17 = v16;
      if ( v16 >= 0 )
      {
        wil::details::in1diag3::Log_HrIfMsg(
          retaddr,
          (void *)0x142,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
          (const char *)0x8000FFFFLL,
          *a6 == 0,
          (bool)"Root handle to the loaded hive is null",
          v24);
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
          McTemplateU0zz_EtwEventWriteTransfer(v22, EVENT_HIVE_LOADED, a3, a2);
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v37);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&v25);
        RtlFreeUnicodeString(&NtPathName);
        v11 = 0;
        goto LABEL_27;
      }
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
      {
        v18 = RtlNtStatusToDosError(v16);
        v19 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v18);
        v21 = L"???";
        if ( *v19 )
          v21 = *v19;
        McTemplateU0zz_EtwEventWriteTransfer(v20, EVENT_REGLOADKEYFAILED, v21, a3);
        v9 = 1;
      }
      if ( (v9 & 1) != 0 )
        LocalFree(hMem);
      DumpMountedRegkeys(a3, v17);
      v11 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x13F,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
              (const char *)v17,
              (int)"Failed to load key <%ws>.",
              (const char *)a2);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
        (const char *)(unsigned int)v15,
        v23);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&v25);
    RtlFreeUnicodeString(&NtPathName);
LABEL_27:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(SourceString);
    ProfileTelemetry::MountRegHive::~MountRegHive((ProfileTelemetry::MountRegHive *)&v37);
    return v11;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xFB,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
    (const char *)0x8007000ELL,
    (int)"Failed to convert file path <%ws> to NT object namespace path.",
    (const char *)a3);
  if ( v12 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v12);
  v37 = &ProfileTelemetry::MountRegHive::`vftable';
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v37);
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v37);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800178bc  mov     [rsp-8+arg_0], rbx
0x1800178c1  push    rbp
0x1800178c2  push    rsi
0x1800178c3  push    rdi
0x1800178c4  push    r12
0x1800178c6  push    r13
0x1800178c8  push    r14
0x1800178ca  push    r15
0x1800178cc  lea     rbp, [rsp-170h]
0x1800178d4  sub     rsp, 270h
0x1800178db  mov     rax, cs:__security_cookie
0x1800178e2  xor     rax, rsp
0x1800178e5  mov     [rbp+1A0h+var_40], rax
0x1800178ec  mov     r13, r9
0x1800178ef  mov     rdi, r8
0x1800178f2  mov     r15, rdx
0x1800178f5  mov     rsi, [rbp+1A0h+hToken]
0x1800178fc  mov     r14, [rbp+1A0h+arg_28]
0x180017903  xor     ebx, ebx
0x180017905  mov     r12d, ebx
0x180017908  mov     [rsp+2A0h+var_260], ebx
0x18001790c  mov     [r14], rbx
0x18001790f  mov     [rbp+1A0h+var_188], ebx
0x180017912  mov     [rbp+1A0h+var_184], bl
0x180017915  mov     [rbp+1A0h+var_148], bl
0x180017918  mov     [rbp+1A0h+var_160], ebx
0x18001791b  lea     rax, aMountreghive; "MountRegHive"
0x180017922  mov     [rbp+1A0h+var_158], rax
0x180017926  mov     [rbp+1A0h+var_150], rbx
0x18001792a  mov     [rbp+1A0h+var_140], ebx
0x18001792d  xorps   xmm0, xmm0
0x180017930  movdqa  [rbp+1A0h+var_A0], xmm0
0x180017938  xor     edx, edx; Val
0x18001793a  mov     r8d, 98h; Size
0x180017940  lea     rcx, [rbp+1A0h+var_138]; void *
0x180017944  call    memset_0
0x180017949  mov     [rbp+1A0h+var_90], 1
0x180017953  xor     eax, eax
0x180017955  mov     [rbp+1A0h+var_88], rax
0x18001795c  lea     rax, [rbp+1A0h+var_188]
0x180017960  mov     [rbp+1A0h+var_80], rax
0x180017967  mov     [rbp+1A0h+var_78], rbx
0x18001796e  mov     [rbp+1A0h+var_70], rbx
0x180017975  lea     rax, [rbp+1A0h+var_190]
0x180017979  mov     [rbp+1A0h+var_68], rax
0x180017980  mov     [rbp+1A0h+var_60], rbx
0x180017987  mov     [rbp+1A0h+var_58], ebx
0x18001798d  lea     rax, [rbp+1A0h+var_160]
0x180017991  mov     [rbp+1A0h+var_50], rax
0x180017998  mov     [rbp+1A0h+var_48], bl
0x18001799e  lea     rax, ??_7MountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::MountRegHive::`vftable'
0x1800179a5  mov     [rbp+1A0h+var_190], rax
0x1800179a9  mov     rdx, r15; unsigned __int16 *
0x1800179ac  lea     rcx, [rbp+1A0h+var_190]; this
0x1800179b0  call    ?StartActivity@MountRegHive@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::MountRegHive::StartActivity(ushort const *)
0x1800179b5  nop
0x1800179b6  mov     [rsp+2A0h+SourceString], rbx
0x1800179bb  mov     [rsp+2A0h+var_230], rbx
0x1800179c0  mov     [rsp+2A0h+var_228], rbx
0x1800179c5  mov     r8, r15
0x1800179c8  lea     rdx, aRegistryUserWs; "\\Registry\\User\\%ws"
0x1800179cf  lea     rcx, [rsp+2A0h+SourceString]
0x1800179d4  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800179d9  mov     ebx, eax
0x1800179db  test    eax, eax
0x1800179dd  jns     short loc_1800179FF
0x1800179df  mov     rcx, [rbp+1A8h]; this
0x1800179e6  mov     r9d, eax; char *
0x1800179e9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800179f0  mov     edx, 0ECh; void *
0x1800179f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800179fa  jmp     loc_180017D4D
0x1800179ff  xorps   xmm0, xmm0
0x180017a02  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm0
0x180017a06  mov     rbx, [rsp+2A0h+SourceString]
0x180017a0b  mov     rdx, rbx; SourceString
0x180017a0e  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x180017a12  call    cs:__imp_RtlInitUnicodeString
0x180017a19  nop     dword ptr [rax+rax+00h]
0x180017a1e  xor     eax, eax
0x180017a20  mov     qword ptr [rbp+1A0h+TargetKey.Length], 30h ; '0'
0x180017a28  mov     qword ptr [rbp+1A0h+TargetKey.Attributes], 40h ; '@'
0x180017a30  mov     [rbp+1A0h+TargetKey.RootDirectory], rax
0x180017a34  lea     rax, [rbp+1A0h+DestinationString]
0x180017a38  mov     [rbp+1A0h+TargetKey.ObjectName], rax
0x180017a3c  xorps   xmm0, xmm0
0x180017a3f  movdqu  xmmword ptr [rbp+1A0h+TargetKey.SecurityDescriptor], xmm0
0x180017a44  movups  xmmword ptr [rsp+2A0h+NtPathName.Length], xmm0
0x180017a49  xor     r9d, r9d; DirectoryInfo
0x180017a4c  xor     r8d, r8d; NtFileNamePart
0x180017a4f  lea     rdx, [rsp+2A0h+NtPathName]; NtPathName
0x180017a54  mov     rcx, rdi; DosPathName
0x180017a57  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180017a5e  nop     dword ptr [rax+rax+00h]
0x180017a63  test    al, al
0x180017a65  jnz     short loc_180017AC9
0x180017a67  mov     rcx, [rbp+1A8h]; this
0x180017a6e  mov     [rsp+2A0h+var_278], rdi; char *
0x180017a73  lea     rax, aFailedToConver_0; "Failed to convert file path <%ws> to NT"...
0x180017a7a  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180017a7f  mov     edi, 8007000Eh
0x180017a84  mov     r9d, edi; char *
0x180017a87  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017a8e  mov     edx, 0FBh; void *
0x180017a93  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017a98  test    rbx, rbx
0x180017a9b  jz      short loc_180017AA5
0x180017a9d  mov     rcx, rbx
0x180017aa0  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180017aa5  lea     rax, ??_7MountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::MountRegHive::`vftable'
0x180017aac  mov     [rbp+1A0h+var_190], rax
0x180017ab0  lea     rcx, [rbp+1A0h+var_190]
0x180017ab4  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017ab9  lea     rcx, [rbp+1A0h+var_190]
0x180017abd  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017ac2  mov     eax, edi
0x180017ac4  jmp     loc_180017D62
0x180017ac9  xor     ebx, ebx
0x180017acb  mov     qword ptr [rbp+1A0h+SourceFile.Length], 30h ; '0'
0x180017ad3  mov     qword ptr [rbp+1A0h+SourceFile.Attributes], 40h ; '@'
0x180017adb  mov     [rbp+1A0h+SourceFile.RootDirectory], rbx
0x180017adf  lea     rax, [rsp+2A0h+NtPathName]
0x180017ae4  mov     [rbp+1A0h+SourceFile.ObjectName], rax
0x180017ae8  xorps   xmm0, xmm0
0x180017aeb  movdqu  xmmword ptr [rbp+1A0h+SourceFile.SecurityDescriptor], xmm0
0x180017af0  mov     [rsp+2A0h+var_260], 12h
0x180017af8  mov     [rsp+2A0h+var_25C], bx
0x180017afd  mov     [rsp+2A0h+TokenHandle], rbx
0x180017b02  call    cs:__imp_GetCurrentThread
0x180017b09  nop     dword ptr [rax+rax+00h]
0x180017b0e  lea     r9, [rsp+2A0h+TokenHandle]; TokenHandle
0x180017b13  mov     edx, 20008h; DesiredAccess
0x180017b18  lea     r8d, [rbx+1]; OpenAsSelf
0x180017b1c  mov     rcx, rax; ThreadHandle
0x180017b1f  call    cs:__imp_OpenThreadToken
0x180017b26  nop     dword ptr [rax+rax+00h]
0x180017b2b  test    eax, eax
0x180017b2d  jz      short loc_180017B3F
0x180017b2f  mov     rax, [rsp+2A0h+TokenHandle]
0x180017b34  inc     rax
0x180017b37  test    rax, 0FFFFFFFFFFFFFFFEh
0x180017b3d  jnz     short loc_180017B96
0x180017b3f  lea     rcx, [rsp+2A0h+var_260]; this
0x180017b44  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180017b49  mov     ebx, eax
0x180017b4b  test    eax, eax
0x180017b4d  jns     short loc_180017B94
0x180017b4f  mov     rcx, [rbp+1A8h]; this
0x180017b56  mov     r9d, eax; char *
0x180017b59  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017b60  mov     edx, 111h; void *
0x180017b65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b6a  lea     rcx, [rsp+2A0h+TokenHandle]
0x180017b6f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017b74  lea     rcx, [rsp+2A0h+var_260]; this
0x180017b79  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180017b7e  lea     rcx, [rsp+2A0h+NtPathName]; UnicodeString
0x180017b83  call    cs:__imp_RtlFreeUnicodeString
0x180017b8a  nop     dword ptr [rax+rax+00h]
0x180017b8f  jmp     loc_180017D4D
0x180017b94  xor     ebx, ebx
0x180017b96  test    rsi, rsi
0x180017b99  jz      short loc_180017BF4
0x180017b9b  mov     rdx, rdi; lpFileName
0x180017b9e  mov     rcx, rsi; hToken
0x180017ba1  call    ?CheckFullAccessOnFile@@YAHPEAXPEBG@Z; CheckFullAccessOnFile(void *,ushort const *)
0x180017ba6  test    eax, eax
0x180017ba8  jz      short loc_180017BF4
0x180017baa  mov     [rbp+1A0h+var_1B0], 1
0x180017bae  mov     [rbp+1A0h+var_1A8], r13
0x180017bb2  mov     [rbp+1A0h+var_1A0], 3
0x180017bb6  mov     [rbp+1A0h+var_198], rsi
0x180017bba  mov     [rsp+2A0h+var_268], rbx
0x180017bbf  mov     [rsp+2A0h+var_270], r14
0x180017bc4  mov     dword ptr [rsp+2A0h+var_278], 20019h
0x180017bcc  mov     dword ptr [rsp+2A0h+var_280], 2
0x180017bd4  lea     r9, [rbp+1A0h+var_1B0]
0x180017bd8  mov     r8d, 800h
0x180017bde  lea     rdx, [rbp+1A0h+SourceFile]
0x180017be2  lea     rcx, [rbp+1A0h+TargetKey]
0x180017be6  call    cs:__imp_NtLoadKey3
0x180017bed  nop     dword ptr [rax+rax+00h]
0x180017bf2  jmp     short loc_180017C28
0x180017bf4  mov     [rsp+2A0h+var_268], rbx
0x180017bf9  mov     [rsp+2A0h+var_270], r14; char *
0x180017bfe  mov     dword ptr [rsp+2A0h+var_278], 20019h
0x180017c06  mov     qword ptr [rsp+2A0h+var_280], rbx
0x180017c0b  mov     r9, r13; TrustClassKey
0x180017c0e  mov     r8d, 800h; Flags
0x180017c14  lea     rdx, [rbp+1A0h+SourceFile]; SourceFile
0x180017c18  lea     rcx, [rbp+1A0h+TargetKey]; TargetKey
0x180017c1c  call    cs:__imp_NtLoadKeyEx
0x180017c23  nop     dword ptr [rax+rax+00h]
0x180017c28  mov     ebx, eax
0x180017c2a  test    eax, eax
0x180017c2c  jns     loc_180017CCD
0x180017c32  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180017c39  jz      short loc_180017C79
0x180017c3b  mov     ecx, eax; Status
0x180017c3d  call    cs:__imp_RtlNtStatusToDosError
0x180017c44  nop     dword ptr [rax+rax+00h]
0x180017c49  mov     edx, eax; dwMessageId
0x180017c4b  lea     rcx, [rsp+2A0h+hMem]; lpBuffer
0x180017c50  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180017c55  lea     r8, asc_180063710; "???"
0x180017c5c  cmp     qword ptr [rax], 0
0x180017c60  cmovnz  r8, [rax]
0x180017c64  mov     r9, rdi
0x180017c67  lea     rdx, EVENT_REGLOADKEYFAILED
0x180017c6e  call    McTemplateU0zz_EtwEventWriteTransfer
0x180017c73  mov     r12d, 1
0x180017c79  test    r12b, 1
0x180017c7d  jz      short loc_180017C90
0x180017c7f  mov     rcx, [rsp+2A0h+hMem]; hMem
0x180017c84  call    cs:__imp_LocalFree
0x180017c8b  nop     dword ptr [rax+rax+00h]
0x180017c90  mov     edx, ebx; unsigned int
0x180017c92  mov     rcx, rdi; unsigned __int16 *
0x180017c95  call    ?DumpMountedRegkeys@@YAXPEBGK@Z; DumpMountedRegkeys(ushort const *,ulong)
0x180017c9a  mov     rcx, [rbp+1A8h]; this
0x180017ca1  mov     [rsp+2A0h+var_278], r15; char *
0x180017ca6  lea     rax, aFailedToLoadKe; "Failed to load key <%ws>."
0x180017cad  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180017cb2  mov     r9d, ebx; char *
0x180017cb5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017cbc  mov     edx, 13Fh; void *
0x180017cc1  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180017cc6  mov     ebx, eax
0x180017cc8  jmp     loc_180017B6A
0x180017ccd  cmp     qword ptr [r14], 0
0x180017cd1  setz    al
0x180017cd4  mov     rcx, [rbp+1A8h]; this
0x180017cdb  lea     rdx, aRootHandleToTh; "Root handle to the loaded hive is null"
0x180017ce2  mov     [rsp+2A0h+var_278], rdx; bool
0x180017ce7  mov     [rsp+2A0h+var_280], al; char
0x180017ceb  mov     r9d, 8000FFFFh; char *
0x180017cf1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017cf8  mov     edx, 142h; void *
0x180017cfd  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180017d02  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180017d09  jz      short loc_180017D1D
0x180017d0b  mov     r9, r15
0x180017d0e  mov     r8, rdi
0x180017d11  lea     rdx, EVENT_HIVE_LOADED
0x180017d18  call    McTemplateU0zz_EtwEventWriteTransfer
0x180017d1d  lea     rcx, [rbp+1A0h+var_190]
0x180017d21  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180017d26  lea     rcx, [rsp+2A0h+TokenHandle]
0x180017d2b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017d30  lea     rcx, [rsp+2A0h+var_260]; this
0x180017d35  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180017d3a  lea     rcx, [rsp+2A0h+NtPathName]; UnicodeString
0x180017d3f  call    cs:__imp_RtlFreeUnicodeString
0x180017d46  nop     dword ptr [rax+rax+00h]
0x180017d4b  xor     ebx, ebx
0x180017d4d  lea     rcx, [rsp+2A0h+SourceString]
0x180017d52  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017d57  lea     rcx, [rbp+1A0h+var_190]; this
0x180017d5b  call    ??1MountRegHive@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::MountRegHive::~MountRegHive(void)
0x180017d60  mov     eax, ebx
0x180017d62  mov     rcx, [rbp+1A0h+var_40]
0x180017d69  xor     rcx, rsp; StackCookie
0x180017d6c  call    __security_check_cookie
0x180017d71  mov     rbx, [rsp+2A0h+arg_0]
0x180017d79  add     rsp, 270h
0x180017d80  pop     r15
0x180017d82  pop     r14
0x180017d84  pop     r13
0x180017d86  pop     r12
0x180017d88  pop     rdi
0x180017d89  pop     rsi
0x180017d8a  pop     rbp
0x180017d8b  retn
```
