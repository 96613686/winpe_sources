# MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)

- ea: `0x1800085cc`
- end: `0x180008a78`
- name: `?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z`
- size: `1196`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, HKEY, HANDLE hToken, void **)`
- caller_count: `5`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011200`
- `0x18002ed00`
- `0x18003735c`
- `0x1800393e4`
- `0x180039d6c`

## callees

- `0x1800053a0`
- `0x1800053cc`
- `0x1800085cc`
- `0x180008a80`
- `0x1800099f8`
- `0x18000a37c`
- `0x18000a4a0`
- `0x18000a9b8`
- `0x18000a9e0`
- `0x18000aa5c`
- `0x18000aab8`
- `0x180010f30`
- `0x1800111a0`
- `0x180013d1c`
- `0x180015458`
- `0x180021bd0`
- `0x18002d2d8`
- `0x18002f8e0`
- `0x180035d30`
- `0x180035f88`
- `0x1800360b8`
- `0x18003a730`
- `0x18003b310`
- `0x180040e94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008835`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008835`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000881e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000881e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000897c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000897c`
- `ntdll!NtLoadKeyEx` at `0x180008920`
- `ntdll!NtLoadKeyEx` at `0x180008920`
- `ntdll!NtLoadKey3` at `0x1800088f0`
- `ntdll!NtLoadKey3` at `0x1800088f0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180008761`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180008761`
- `ntdll!RtlInitUnicodeString` at `0x180008722`
- `ntdll!RtlInitUnicodeString` at `0x180008722`
- `ntdll!RtlNtStatusToDosError` at `0x18000893b`
- `ntdll!RtlNtStatusToDosError` at `0x18000893b`
- `ntdll!RtlFreeUnicodeString` at `0x180008893`
- `ntdll!RtlFreeUnicodeString` at `0x180008a31`
- `ntdll!RtlFreeUnicodeString` at `0x180008893`
- `ntdll!RtlFreeUnicodeString` at `0x180008a31`

## string_xrefs

- `0x18000862b`: `MountRegHive`
- `0x1800086f9`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18000878b`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180008869`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x1800089a7`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x1800089e3`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180008777`: `Failed to convert file path <%ws> to NT object namespace path.`
- `0x1800086d8`: `\Registry\User\%ws`

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
  _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES SourceFile; // [rsp+90h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES TargetKey; // [rsp+C0h] [rbp-40h] BYREF
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
  __int64 v50; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v51[3]; // [rsp+230h] [rbp+130h] BYREF
  int v52; // [rsp+248h] [rbp+148h]
  int *v53; // [rsp+250h] [rbp+150h]
  char v54; // [rsp+258h] [rbp+158h]
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
  v51[0] = 0;
  v51[1] = &v37;
  v51[2] = 0;
  v52 = 0;
  v53 = &v40;
  v54 = 0;
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
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v51);
  wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v50);
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(&v38);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800085cc  mov     [rsp-8+arg_0], rbx
0x1800085d1  push    rbp
0x1800085d2  push    rsi
0x1800085d3  push    rdi
0x1800085d4  push    r12
0x1800085d6  push    r13
0x1800085d8  push    r14
0x1800085da  push    r15
0x1800085dc  lea     rbp, [rsp-170h]
0x1800085e4  sub     rsp, 270h
0x1800085eb  mov     rax, cs:__security_cookie
0x1800085f2  xor     rax, rsp
0x1800085f5  mov     [rbp+1A0h+var_40], rax
0x1800085fc  mov     r13, r9
0x1800085ff  mov     rdi, r8
0x180008602  mov     r15, rdx
0x180008605  mov     rsi, [rbp+1A0h+hToken]
0x18000860c  mov     r14, [rbp+1A0h+arg_28]
0x180008613  xor     ebx, ebx
0x180008615  mov     r12d, ebx
0x180008618  mov     [rsp+2A0h+var_260], ebx
0x18000861c  mov     [r14], rbx
0x18000861f  mov     [rbp+1A0h+var_188], ebx
0x180008622  mov     [rbp+1A0h+var_184], bl
0x180008625  mov     [rbp+1A0h+var_148], bl
0x180008628  mov     [rbp+1A0h+var_160], ebx
0x18000862b  lea     rax, aMountreghive; "MountRegHive"
0x180008632  mov     [rbp+1A0h+var_158], rax
0x180008636  mov     [rbp+1A0h+var_150], rbx
0x18000863a  mov     [rbp+1A0h+var_140], ebx
0x18000863d  xorps   xmm0, xmm0
0x180008640  movdqa  [rbp+1A0h+var_A0], xmm0
0x180008648  xor     edx, edx; Val
0x18000864a  mov     r8d, 98h; Size
0x180008650  lea     rcx, [rbp+1A0h+var_138]; void *
0x180008654  call    memset_0
0x180008659  mov     [rbp+1A0h+var_90], 1
0x180008663  xor     eax, eax
0x180008665  mov     [rbp+1A0h+var_88], rax
0x18000866c  lea     rax, [rbp+1A0h+var_188]
0x180008670  mov     [rbp+1A0h+var_80], rax
0x180008677  mov     [rbp+1A0h+var_78], rbx
0x18000867e  mov     [rbp+1A0h+var_70], rbx
0x180008685  lea     rax, [rbp+1A0h+var_190]
0x180008689  mov     [rbp+1A0h+var_68], rax
0x180008690  mov     [rbp+1A0h+var_60], rbx
0x180008697  mov     [rbp+1A0h+var_58], ebx
0x18000869d  lea     rax, [rbp+1A0h+var_160]
0x1800086a1  mov     [rbp+1A0h+var_50], rax
0x1800086a8  mov     [rbp+1A0h+var_48], bl
0x1800086ae  lea     rax, ??_7MountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::MountRegHive::`vftable'
0x1800086b5  mov     [rbp+1A0h+var_190], rax
0x1800086b9  mov     rdx, r15; unsigned __int16 *
0x1800086bc  lea     rcx, [rbp+1A0h+var_190]; this
0x1800086c0  call    ?StartActivity@MountRegHive@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::MountRegHive::StartActivity(ushort const *)
0x1800086c5  nop
0x1800086c6  mov     [rsp+2A0h+SourceString], rbx
0x1800086cb  mov     [rsp+2A0h+var_230], rbx
0x1800086d0  mov     [rsp+2A0h+var_228], rbx
0x1800086d5  mov     r8, r15
0x1800086d8  lea     rdx, aRegistryUserWs; "\\Registry\\User\\%ws"
0x1800086df  lea     rcx, [rsp+2A0h+SourceString]
0x1800086e4  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800086e9  mov     ebx, eax
0x1800086eb  test    eax, eax
0x1800086ed  jns     short loc_18000870F
0x1800086ef  mov     rcx, [rbp+1A8h]; this
0x1800086f6  mov     r9d, eax; char *
0x1800086f9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008700  mov     edx, 0ECh; void *
0x180008705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000870a  jmp     loc_180008A39
0x18000870f  xorps   xmm0, xmm0
0x180008712  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm0
0x180008716  mov     rbx, [rsp+2A0h+SourceString]
0x18000871b  mov     rdx, rbx; SourceString
0x18000871e  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x180008722  call    cs:__imp_RtlInitUnicodeString
0x180008728  xor     eax, eax
0x18000872a  mov     qword ptr [rbp+1A0h+TargetKey.Length], 30h ; '0'
0x180008732  mov     qword ptr [rbp+1A0h+TargetKey.Attributes], 40h ; '@'
0x18000873a  mov     [rbp+1A0h+TargetKey.RootDirectory], rax
0x18000873e  lea     rax, [rbp+1A0h+DestinationString]
0x180008742  mov     [rbp+1A0h+TargetKey.ObjectName], rax
0x180008746  xorps   xmm0, xmm0
0x180008749  movdqu  xmmword ptr [rbp+1A0h+TargetKey.SecurityDescriptor], xmm0
0x18000874e  movups  xmmword ptr [rsp+2A0h+NtPathName.Length], xmm0
0x180008753  xor     r9d, r9d; DirectoryInfo
0x180008756  xor     r8d, r8d; NtFileNamePart
0x180008759  lea     rdx, [rsp+2A0h+NtPathName]; NtPathName
0x18000875e  mov     rcx, rdi; DosPathName
0x180008761  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180008767  test    al, al
0x180008769  jnz     short loc_1800087E5
0x18000876b  mov     rcx, [rbp+1A8h]; this
0x180008772  mov     [rsp+2A0h+var_278], rdi; char *
0x180008777  lea     rax, aFailedToConver_0; "Failed to convert file path <%ws> to NT"...
0x18000877e  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180008783  mov     edi, 8007000Eh
0x180008788  mov     r9d, edi; char *
0x18000878b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008792  mov     edx, 0FBh; void *
0x180008797  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000879c  test    rbx, rbx
0x18000879f  jz      short loc_1800087A9
0x1800087a1  mov     rcx, rbx
0x1800087a4  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800087a9  lea     rax, ??_7MountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::MountRegHive::`vftable'
0x1800087b0  mov     [rbp+1A0h+var_190], rax
0x1800087b4  lea     rcx, [rbp+1A0h+var_190]
0x1800087b8  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800087bd  lea     rcx, [rbp+1A0h+var_70]; this
0x1800087c4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800087c9  lea     rcx, [rbp+1A0h+var_78]
0x1800087d0  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800087d5  lea     rcx, [rbp+1A0h+var_188]
0x1800087d9  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800087de  mov     eax, edi
0x1800087e0  jmp     loc_180008A4E
0x1800087e5  xor     ebx, ebx
0x1800087e7  mov     qword ptr [rbp+1A0h+SourceFile.Length], 30h ; '0'
0x1800087ef  mov     qword ptr [rbp+1A0h+SourceFile.Attributes], 40h ; '@'
0x1800087f7  mov     [rbp+1A0h+SourceFile.RootDirectory], rbx
0x1800087fb  lea     rax, [rsp+2A0h+NtPathName]
0x180008800  mov     [rbp+1A0h+SourceFile.ObjectName], rax
0x180008804  xorps   xmm0, xmm0
0x180008807  movdqu  xmmword ptr [rbp+1A0h+SourceFile.SecurityDescriptor], xmm0
0x18000880c  mov     [rsp+2A0h+var_260], 12h
0x180008814  mov     [rsp+2A0h+var_25C], bx
0x180008819  mov     [rsp+2A0h+TokenHandle], rbx
0x18000881e  call    cs:__imp_GetCurrentThread
0x180008824  lea     r9, [rsp+2A0h+TokenHandle]; TokenHandle
0x180008829  mov     edx, 20008h; DesiredAccess
0x18000882e  lea     r8d, [rbx+1]; OpenAsSelf
0x180008832  mov     rcx, rax; ThreadHandle
0x180008835  call    cs:__imp_OpenThreadToken
0x18000883b  test    eax, eax
0x18000883d  jz      short loc_18000884F
0x18000883f  mov     rax, [rsp+2A0h+TokenHandle]
0x180008844  inc     rax
0x180008847  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000884d  jnz     short loc_1800088A0
0x18000884f  lea     rcx, [rsp+2A0h+var_260]; this
0x180008854  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180008859  mov     ebx, eax
0x18000885b  test    eax, eax
0x18000885d  jns     short loc_18000889E
0x18000885f  mov     rcx, [rbp+1A8h]; this
0x180008866  mov     r9d, eax; char *
0x180008869  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008870  mov     edx, 111h; void *
0x180008875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000887a  lea     rcx, [rsp+2A0h+TokenHandle]
0x18000887f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008884  lea     rcx, [rsp+2A0h+var_260]; this
0x180008889  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x18000888e  lea     rcx, [rsp+2A0h+NtPathName]; UnicodeString
0x180008893  call    cs:__imp_RtlFreeUnicodeString
0x180008899  jmp     loc_180008A39
0x18000889e  xor     ebx, ebx
0x1800088a0  test    rsi, rsi
0x1800088a3  jz      short loc_1800088F8
0x1800088a5  mov     rdx, rdi; lpFileName
0x1800088a8  mov     rcx, rsi; hToken
0x1800088ab  call    ?CheckFullAccessOnFile@@YAHPEAXPEBG@Z; CheckFullAccessOnFile(void *,ushort const *)
0x1800088b0  test    eax, eax
0x1800088b2  jz      short loc_1800088F8
0x1800088b4  mov     [rbp+1A0h+var_1B0], 1
0x1800088b8  mov     [rbp+1A0h+var_1A8], r13
0x1800088bc  mov     [rbp+1A0h+var_1A0], 3
0x1800088c0  mov     [rbp+1A0h+var_198], rsi
0x1800088c4  mov     [rsp+2A0h+var_268], rbx
0x1800088c9  mov     [rsp+2A0h+var_270], r14
0x1800088ce  mov     dword ptr [rsp+2A0h+var_278], 20019h
0x1800088d6  mov     dword ptr [rsp+2A0h+var_280], 2
0x1800088de  lea     r9, [rbp+1A0h+var_1B0]
0x1800088e2  mov     r8d, 800h
0x1800088e8  lea     rdx, [rbp+1A0h+SourceFile]
0x1800088ec  lea     rcx, [rbp+1A0h+TargetKey]
0x1800088f0  call    cs:__imp_NtLoadKey3
0x1800088f6  jmp     short loc_180008926
0x1800088f8  mov     [rsp+2A0h+var_268], rbx
0x1800088fd  mov     [rsp+2A0h+var_270], r14; char *
0x180008902  mov     dword ptr [rsp+2A0h+var_278], 20019h
0x18000890a  mov     qword ptr [rsp+2A0h+var_280], rbx
0x18000890f  mov     r9, r13; TrustClassKey
0x180008912  mov     r8d, 800h; Flags
0x180008918  lea     rdx, [rbp+1A0h+SourceFile]; SourceFile
0x18000891c  lea     rcx, [rbp+1A0h+TargetKey]; TargetKey
0x180008920  call    cs:__imp_NtLoadKeyEx
0x180008926  mov     ebx, eax
0x180008928  test    eax, eax
0x18000892a  jns     loc_1800089BF
0x180008930  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180008937  jz      short loc_180008971
0x180008939  mov     ecx, eax; Status
0x18000893b  call    cs:__imp_RtlNtStatusToDosError
0x180008941  mov     edx, eax; dwMessageId
0x180008943  lea     rcx, [rsp+2A0h+hMem]; lpBuffer
0x180008948  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18000894d  lea     r8, asc_180060EA8; "???"
0x180008954  cmp     qword ptr [rax], 0
0x180008958  cmovnz  r8, [rax]
0x18000895c  mov     r9, rdi
0x18000895f  lea     rdx, EVENT_REGLOADKEYFAILED
0x180008966  call    McTemplateU0zz_EtwEventWriteTransfer
0x18000896b  mov     r12d, 1
0x180008971  test    r12b, 1
0x180008975  jz      short loc_180008982
0x180008977  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18000897c  call    cs:__imp_LocalFree
0x180008982  mov     edx, ebx; unsigned int
0x180008984  mov     rcx, rdi; unsigned __int16 *
0x180008987  call    ?DumpMountedRegkeys@@YAXPEBGK@Z; DumpMountedRegkeys(ushort const *,ulong)
0x18000898c  mov     rcx, [rbp+1A8h]; this
0x180008993  mov     [rsp+2A0h+var_278], r15; char *
0x180008998  lea     rax, aFailedToLoadKe; "Failed to load key <%ws>."
0x18000899f  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800089a4  mov     r9d, ebx; char *
0x1800089a7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800089ae  mov     edx, 13Fh; void *
0x1800089b3  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800089b8  mov     ebx, eax
0x1800089ba  jmp     loc_18000887A
0x1800089bf  cmp     qword ptr [r14], 0
0x1800089c3  setz    al
0x1800089c6  mov     rcx, [rbp+1A8h]; this
0x1800089cd  lea     rdx, aRootHandleToTh; "Root handle to the loaded hive is null"
0x1800089d4  mov     [rsp+2A0h+var_278], rdx; bool
0x1800089d9  mov     [rsp+2A0h+var_280], al; char
0x1800089dd  mov     r9d, 8000FFFFh; char *
0x1800089e3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800089ea  mov     edx, 142h; void *
0x1800089ef  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800089f4  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800089fb  jz      short loc_180008A0F
0x1800089fd  mov     r9, r15
0x180008a00  mov     r8, rdi
0x180008a03  lea     rdx, EVENT_HIVE_LOADED
0x180008a0a  call    McTemplateU0zz_EtwEventWriteTransfer
0x180008a0f  lea     rcx, [rbp+1A0h+var_190]
0x180008a13  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180008a18  lea     rcx, [rsp+2A0h+TokenHandle]
0x180008a1d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008a22  lea     rcx, [rsp+2A0h+var_260]; this
0x180008a27  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180008a2c  lea     rcx, [rsp+2A0h+NtPathName]; UnicodeString
0x180008a31  call    cs:__imp_RtlFreeUnicodeString
0x180008a37  xor     ebx, ebx
0x180008a39  lea     rcx, [rsp+2A0h+SourceString]
0x180008a3e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008a43  lea     rcx, [rbp+1A0h+var_190]; this
0x180008a47  call    ??1MountRegHive@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::MountRegHive::~MountRegHive(void)
0x180008a4c  mov     eax, ebx
0x180008a4e  mov     rcx, [rbp+1A0h+var_40]
0x180008a55  xor     rcx, rsp; StackCookie
0x180008a58  call    __security_check_cookie
0x180008a5d  mov     rbx, [rsp+2A0h+arg_0]
0x180008a65  add     rsp, 270h
0x180008a6c  pop     r15
0x180008a6e  pop     r14
0x180008a70  pop     r13
0x180008a72  pop     r12
0x180008a74  pop     rdi
0x180008a75  pop     rsi
0x180008a76  pop     rbp
0x180008a77  retn
```
