# CPrepareUserOOBETask::RunTask(void)

- ea: `0x180053060`
- end: `0x1800533fa`
- name: `?RunTask@CPrepareUserOOBETask@@UEAAJXZ`
- size: `922`
- prototype: `__int64 __fastcall(CPrepareUserOOBETask *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180053400`

## callees

- `0x180007bbc`
- `0x18000ac48`
- `0x180018a04`
- `0x180019140`
- `0x180019a38`
- `0x1800230b0`
- `0x180032cd4`
- `0x18003fd90`
- `0x1800516c8`
- `0x180052100`
- `0x180053060`
- `0x180053a64`
- `0x180053c74`
- `0x180053d88`
- `0x180053e7c`
- `0x18005431c`
- `0x1800b8834`
- `0x1800be948`
- `0x1800c4010`

## import_xrefs

- `USERENV!LoadUserProfileW` at `0x1800532c1`
- `USERENV!LoadUserProfileW` at `0x1800532c1`
- `USERENV!UnloadUserProfile` at `0x180053393`
- `USERENV!UnloadUserProfile` at `0x180053393`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800530b9`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800530b9`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x1800531e1`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x1800531e1`
- `ADVAPI32!LogonUserW` at `0x180053256`
- `ADVAPI32!LogonUserW` at `0x180053256`

## string_xrefs

- `0x180053096`: `Failed to delete exiting default account`
- `0x1800533e7`: `Default account: %s is created successfully`
- `0x18005310d`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053206`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053375`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x1800533b8`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x18005311f`: `Failed to create the default account with hr=0x%08X`
- `0x18005332b`: `UnattendXmlAutoLogon`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPrepareUserOOBETask::RunTask(LPCWSTR *this)
{
  __int64 *v2; // rbx
  int DefaultAccountName; // eax
  int Error; // ebx
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  int Instance; // eax
  wil::details::in1diag3 *v9; // rcx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  DWORD dwLogonProvider; // [rsp+20h] [rbp-39h]
  DWORD dwLogonProvidera; // [rsp+20h] [rbp-39h]
  unsigned __int16 *v22[3]; // [rsp+50h] [rbp-9h] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned int v25; // [rsp+C8h] [rbp+6Fh] BYREF
  HANDLE hToken; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v27; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (int)CPrepareUserOOBETask::_RetrieveDefaultAccountName((CPrepareUserOOBETask *)this) >= 0 )
  {
    UnattendLogW(0, L"Deleting existing default account");
    if ( (int)CPrepareUserOOBETask::_DeleteDefaultAccount(this) < 0 )
      UnattendLogW(2, L"Failed to delete exiting default account");
    v2 = (__int64 *)off_1801132A0;
    do
    {
      DeletePersistedRegistryValue(*v2, v2[1], v2[2]);
      v2 += 4;
    }
    while ( v2 != qword_180113320 );
  }
  UnattendLogW(0, L"Creating a new default account");
  DefaultAccountName = CPrepareUserOOBETask::_GenerateDefaultAccountName((CPrepareUserOOBETask *)this);
  Error = DefaultAccountName;
  v5 = retaddr;
  if ( DefaultAccountName < 0 )
  {
    v6 = 72;
LABEL_10:
    wil::details::in1diag3::_Log_Hr(
      v5,
      (void *)v6,
      (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
      (const char *)(unsigned int)DefaultAccountName,
      dwLogonProvider);
    goto LABEL_11;
  }
  DefaultAccountName = CPrepareUserOOBETask::_GenerateDefaultAccountPassword((CPrepareUserOOBETask *)this);
  Error = DefaultAccountName;
  v5 = retaddr;
  if ( DefaultAccountName < 0 )
  {
    v6 = 75;
    goto LABEL_10;
  }
  v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  Instance = CCreateLocalUserTask_CreateInstance((unsigned int)this[69], 0, (unsigned int)this[72], 0);
  Error = Instance;
  v9 = retaddr;
  if ( Instance < 0 )
  {
    v10 = (unsigned int)Instance;
    v11 = 82;
LABEL_21:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v11,
      (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
      (const char *)v10,
      dwLogonProvider);
    goto LABEL_46;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 32LL))(v27);
  Error = v12;
  v9 = retaddr;
  if ( v12 < 0 )
  {
    v10 = (unsigned int)v12;
    v11 = 85;
    goto LABEL_21;
  }
  v13 = SetPersistedRegistryString(
          L"OOBE",
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
          L"DefaultAccountSAMName",
          this[69]);
  Error = v13;
  if ( v13 > 0 )
    Error = (unsigned __int16)v13 | 0x80070000;
  v9 = retaddr;
  if ( Error < 0 )
  {
    v10 = (unsigned int)Error;
    v11 = 100;
    goto LABEL_21;
  }
  hToken = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&hToken);
  if ( LogonUserW(this[69], L".", this[72], 2u, 0, &hToken) )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  v14 = retaddr;
  if ( Error < 0 )
  {
    v15 = 104;
    goto LABEL_44;
  }
  OOBEStartService(L"profsvc", 1);
  memset(&ProfileInfo.lpUserName, 0, 48);
  ProfileInfo.dwSize = 56;
  ProfileInfo.dwFlags = 1;
  ProfileInfo.lpUserName = (LPWSTR)this[69];
  if ( LoadUserProfileW(hToken, &ProfileInfo) )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  v14 = retaddr;
  if ( Error < 0 )
  {
    v15 = 112;
    goto LABEL_44;
  }
  v25 = 0;
  SHRegGetDWORD(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
    L"UnattendSetAutologon",
    &v25);
  if ( v25 == 1 )
  {
    memset(v22, 0, sizeof(v22));
    v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            v22,
            L"%s\\%s",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
            L"UnattendXmlAutoLogon");
    v18 = retaddr;
    if ( v16 >= 0 )
    {
      v16 = TransferUnattendXmlAutologonValues((HKEY)retaddr, v17, (HKEY)ProfileInfo.hProfile, v22[0]);
      v18 = retaddr;
      if ( v16 >= 0 )
      {
LABEL_38:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v22);
        goto LABEL_39;
      }
      v19 = 122;
    }
    else
    {
      v19 = 120;
    }
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
      (const char *)(unsigned int)v16,
      dwLogonProvidera);
    goto LABEL_38;
  }
LABEL_39:
  if ( UnloadUserProfile(hToken, ProfileInfo.hProfile) )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  v14 = retaddr;
  if ( Error >= 0 )
    goto LABEL_45;
  v15 = 130;
LABEL_44:
  wil::details::in1diag3::_Log_Hr(
    v14,
    (void *)v15,
    (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
    (const char *)(unsigned int)Error,
    dwLogonProvidera);
LABEL_45:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  if ( Error >= 0 )
  {
    UnattendLogW(0, L"Default account: %s is created successfully", this[69]);
    goto LABEL_12;
  }
LABEL_11:
  UnattendLogW(1, L"Failed to create the default account with hr=0x%08X", (unsigned int)Error);
LABEL_12:
  OOBE::Health::details::OOBEHealthTracker::HandleEvent<13,long>(Error);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180053060  push    rbp
0x180053062  push    rbx
0x180053063  push    rdi
0x180053064  lea     rbp, [rsp-47h]
0x180053069  sub     rsp, 0A0h
0x180053070  mov     rdi, rcx
0x180053073  call    ?_RetrieveDefaultAccountName@CPrepareUserOOBETask@@AEAAJXZ; CPrepareUserOOBETask::_RetrieveDefaultAccountName(void)
0x180053078  test    eax, eax
0x18005307a  js      short loc_1800530CF
0x18005307c  lea     rdx, aDeletingExisti; "Deleting existing default account"
0x180053083  xor     ecx, ecx
0x180053085  call    UnattendLogW
0x18005308a  mov     rcx, rdi; this
0x18005308d  call    ?_DeleteDefaultAccount@CPrepareUserOOBETask@@AEAAJXZ; CPrepareUserOOBETask::_DeleteDefaultAccount(void)
0x180053092  test    eax, eax
0x180053094  jns     short loc_1800530A7
0x180053096  lea     rdx, aFailedToDelete; "Failed to delete exiting default accoun"...
0x18005309d  mov     ecx, 2
0x1800530a2  call    UnattendLogW
0x1800530a7  lea     rbx, off_1801132A0; "OOBE"
0x1800530ae  mov     r8, [rbx+10h]
0x1800530b2  mov     rdx, [rbx+8]
0x1800530b6  mov     rcx, [rbx]
0x1800530b9  call    cs:__imp_DeletePersistedRegistryValue
0x1800530bf  add     rbx, 20h ; ' '
0x1800530c3  lea     rax, qword_180113320
0x1800530ca  cmp     rbx, rax
0x1800530cd  jnz     short loc_1800530AE
0x1800530cf  lea     rdx, aCreatingANewDe; "Creating a new default account"
0x1800530d6  xor     ecx, ecx
0x1800530d8  call    UnattendLogW
0x1800530dd  mov     rcx, rdi; this
0x1800530e0  call    ?_GenerateDefaultAccountName@CPrepareUserOOBETask@@AEAAJXZ; CPrepareUserOOBETask::_GenerateDefaultAccountName(void)
0x1800530e5  mov     ebx, eax
0x1800530e7  mov     rcx, [rbp+5Fh]
0x1800530eb  test    eax, eax
0x1800530ed  jns     short loc_1800530F6
0x1800530ef  mov     edx, 48h ; 'H'
0x1800530f4  jmp     short loc_18005310D
0x1800530f6  mov     rcx, rdi; this
0x1800530f9  call    ?_GenerateDefaultAccountPassword@CPrepareUserOOBETask@@AEAAJXZ; CPrepareUserOOBETask::_GenerateDefaultAccountPassword(void)
0x1800530fe  mov     ebx, eax
0x180053100  mov     rcx, [rbp+5Fh]; this
0x180053104  test    eax, eax
0x180053106  jns     short loc_180053144
0x180053108  mov     edx, 4Bh ; 'K'; void *
0x18005310d  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053114  mov     r9d, eax; char *
0x180053117  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005311c  mov     r8d, ebx
0x18005311f  lea     rdx, aFailedToCreate_4; "Failed to create the default account wi"...
0x180053126  mov     ecx, 1
0x18005312b  call    UnattendLogW
0x180053130  mov     ecx, ebx
0x180053132  call    ??$HandleEvent@$0N@J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<13,long>(long)
0x180053137  mov     eax, ebx
0x180053139  add     rsp, 0A0h
0x180053140  pop     rdi
0x180053141  pop     rbx
0x180053142  pop     rbp
0x180053143  retn
0x180053144  mov     [rbp+57h+arg_18], 0
0x18005314c  lea     rcx, [rbp+57h+arg_18]
0x180053150  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180053155  lea     rax, [rbp+57h+arg_18]
0x180053159  mov     [rsp+0B0h+var_68], rax
0x18005315e  mov     [rsp+0B0h+var_70], 0
0x180053166  mov     [rsp+0B0h+var_78], 0
0x18005316b  mov     [rsp+0B0h+var_80], 0
0x180053170  mov     byte ptr [rsp+0B0h+phToken], 0
0x180053175  xor     r9d, r9d
0x180053178  mov     r8, [rdi+240h]
0x18005317f  xor     edx, edx
0x180053181  mov     rcx, [rdi+228h]
0x180053188  call    CCreateLocalUserTask_CreateInstance
0x18005318d  mov     ebx, eax
0x18005318f  mov     rcx, [rbp+5Fh]
0x180053193  test    eax, eax
0x180053195  jns     short loc_1800531A1
0x180053197  mov     r9d, eax
0x18005319a  mov     edx, 52h ; 'R'
0x18005319f  jmp     short loc_180053206
0x1800531a1  mov     rcx, [rbp+57h+arg_18]
0x1800531a5  mov     rax, [rcx]
0x1800531a8  mov     rax, [rax+20h]
0x1800531ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531b1  mov     ebx, eax
0x1800531b3  mov     rcx, [rbp+5Fh]
0x1800531b7  test    eax, eax
0x1800531b9  jns     short loc_1800531C5
0x1800531bb  mov     r9d, eax
0x1800531be  mov     edx, 55h ; 'U'
0x1800531c3  jmp     short loc_180053206
0x1800531c5  mov     r9, [rdi+228h]
0x1800531cc  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x1800531d3  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800531da  lea     rcx, aOobe_0; "OOBE"
0x1800531e1  call    cs:__imp_SetPersistedRegistryString
0x1800531e7  mov     ebx, eax
0x1800531e9  test    eax, eax
0x1800531eb  jle     short loc_1800531F6
0x1800531ed  movzx   ebx, ax
0x1800531f0  or      ebx, 80070000h
0x1800531f6  mov     rcx, [rbp+5Fh]; this
0x1800531fa  test    ebx, ebx
0x1800531fc  jns     short loc_180053217
0x1800531fe  mov     r9d, ebx; char *
0x180053201  mov     edx, 64h ; 'd'; void *
0x180053206  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x18005320d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053212  jmp     loc_1800533CF
0x180053217  mov     [rbp+57h+hToken], 0
0x18005321f  xor     edx, edx
0x180053221  lea     rcx, [rbp+57h+hToken]
0x180053225  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005322a  lea     rax, [rbp+57h+hToken]
0x18005322e  mov     [rsp+0B0h+phToken], rax; bool
0x180053233  mov     [rsp+0B0h+dwLogonProvider], 0; int
0x18005323b  mov     r9d, 2; dwLogonType
0x180053241  mov     r8, [rdi+240h]; lpszPassword
0x180053248  lea     rdx, szDomain; "."
0x18005324f  mov     rcx, [rdi+228h]; lpszUsername
0x180053256  call    cs:__imp_LogonUserW
0x18005325c  test    eax, eax
0x18005325e  jz      short loc_180053264
0x180053260  xor     ebx, ebx
0x180053262  jmp     short loc_18005326B
0x180053264  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180053269  mov     ebx, eax
0x18005326b  mov     rcx, [rbp+5Fh]
0x18005326f  test    ebx, ebx
0x180053271  jns     short loc_18005327D
0x180053273  mov     edx, 68h ; 'h'
0x180053278  jmp     loc_1800533B5
0x18005327d  mov     dl, 1; bool
0x18005327f  lea     rcx, aProfsvc; "profsvc"
0x180053286  call    ?OOBEStartService@@YAJPEBG_N@Z; OOBEStartService(ushort const *,bool)
0x18005328b  xorps   xmm0, xmm0
0x18005328e  xor     eax, eax
0x180053290  movups  xmmword ptr [rbp+57h+ProfileInfo.dwSize], xmm0
0x180053294  movups  xmmword ptr [rbp+57h+ProfileInfo.lpProfilePath], xmm0
0x180053298  movups  xmmword ptr [rbp+57h+ProfileInfo.lpServerName], xmm0
0x18005329c  mov     [rbp+57h+ProfileInfo.hProfile], rax
0x1800532a0  mov     [rbp+57h+ProfileInfo.dwSize], 38h ; '8'
0x1800532a7  mov     [rbp+57h+ProfileInfo.dwFlags], 1
0x1800532ae  mov     rax, [rdi+228h]
0x1800532b5  mov     [rbp+57h+ProfileInfo.lpUserName], rax
0x1800532b9  lea     rdx, [rbp+57h+ProfileInfo]; lpProfileInfo
0x1800532bd  mov     rcx, [rbp+57h+hToken]; hToken
0x1800532c1  call    cs:__imp_LoadUserProfileW
0x1800532c7  test    eax, eax
0x1800532c9  jz      short loc_1800532CF
0x1800532cb  xor     ebx, ebx
0x1800532cd  jmp     short loc_1800532D6
0x1800532cf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800532d4  mov     ebx, eax
0x1800532d6  mov     rcx, [rbp+5Fh]
0x1800532da  test    ebx, ebx
0x1800532dc  jns     short loc_1800532E8
0x1800532de  mov     edx, 70h ; 'p'
0x1800532e3  jmp     loc_1800533B5
0x1800532e8  mov     [rbp+57h+arg_8], 0
0x1800532ef  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x1800532f3  lea     r8, aUnattendsetaut; "UnattendSetAutologon"
0x1800532fa  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180053301  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180053308  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18005330d  cmp     [rbp+57h+arg_8], 1
0x180053311  jnz     short loc_18005338B
0x180053313  mov     [rbp+57h+var_60], 0
0x18005331b  mov     [rbp+57h+var_58], 0
0x180053323  mov     [rbp+57h+var_50], 0
0x18005332b  lea     r9, aUnattendxmlaut; "UnattendXmlAutoLogon"
0x180053332  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180053339  lea     rdx, aSS_0; "%s\\%s"
0x180053340  lea     rcx, [rbp+57h+var_60]
0x180053344  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180053349  mov     rcx, [rbp+5Fh]; HKEY
0x18005334d  test    eax, eax
0x18005334f  jns     short loc_180053358
0x180053351  mov     edx, 78h ; 'x'
0x180053356  jmp     short loc_180053372
0x180053358  mov     r9, [rbp+57h+var_60]; unsigned __int16 *
0x18005335c  mov     r8, [rbp+57h+ProfileInfo.hProfile]; HKEY
0x180053360  call    ?TransferUnattendXmlAutologonValues@@YAJPEAUHKEY__@@PEBG01_N2@Z; TransferUnattendXmlAutologonValues(HKEY__ *,ushort const *,HKEY__ *,ushort const *,bool,bool)
0x180053365  mov     rcx, [rbp+5Fh]; this
0x180053369  test    eax, eax
0x18005336b  jns     short loc_180053382
0x18005336d  mov     edx, 7Ah ; 'z'; void *
0x180053372  mov     r9d, eax; char *
0x180053375  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x18005337c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053381  nop
0x180053382  lea     rcx, [rbp+57h+var_60]
0x180053386  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005338b  mov     rdx, [rbp+57h+ProfileInfo.hProfile]; hProfile
0x18005338f  mov     rcx, [rbp+57h+hToken]; hToken
0x180053393  call    cs:__imp_UnloadUserProfile
0x180053399  test    eax, eax
0x18005339b  jz      short loc_1800533A1
0x18005339d  xor     ebx, ebx
0x18005339f  jmp     short loc_1800533A8
0x1800533a1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800533a6  mov     ebx, eax
0x1800533a8  mov     rcx, [rbp+5Fh]; this
0x1800533ac  test    ebx, ebx
0x1800533ae  jns     short loc_1800533C5
0x1800533b0  mov     edx, 82h; void *
0x1800533b5  mov     r9d, ebx; char *
0x1800533b8  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x1800533bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800533c4  nop
0x1800533c5  lea     rcx, [rbp+57h+hToken]
0x1800533c9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800533ce  nop
0x1800533cf  lea     rcx, [rbp+57h+arg_18]
0x1800533d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800533d8  test    ebx, ebx
0x1800533da  js      loc_18005311C
0x1800533e0  mov     r8, [rdi+228h]
0x1800533e7  lea     rdx, aDefaultAccount; "Default account: %s is created successf"...
0x1800533ee  xor     ecx, ecx
0x1800533f0  call    UnattendLogW
0x1800533f5  jmp     loc_180053130
```
