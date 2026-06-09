# LocalAccountManager::CreateRetailDemoAccount(uchar *,ulong,int)

- ea: `0x18002f9a0`
- end: `0x18002fe72`
- name: `?CreateRetailDemoAccount@LocalAccountManager@@UEAAJPEAEKH@Z`
- size: `1234`
- prototype: `int(LocalAccountManager *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180007bbc`
- `0x180008524`
- `0x180008544`
- `0x180019a38`
- `0x18001de58`
- `0x18002ef34`
- `0x18002f198`
- `0x18002f3bc`
- `0x18002f9a0`
- `0x1800300b0`
- `0x180030c3c`
- `0x180030d7c`
- `0x180031194`
- `0x180031718`
- `0x180031800`
- `0x180032cd4`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002fc4e`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002fe25`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002fc4e`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002fe25`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002fb8f`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002fb8f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fbb1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fbbc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fbb1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fbbc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002fb1b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002fb1b`

## string_xrefs

- `0x18002fa87`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002fb2c`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002fba0`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002fc09`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002fc96`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002fcf5`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002fd4f`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f9db`: `LocalAccountCreate`
- `0x18002fa69`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LocalAccountManager::CreateRetailDemoAccount(
        LocalAccountManager *this,
        unsigned __int8 *a2,
        DWORD a3,
        int a4)
{
  const unsigned __int16 *v7; // rdx
  LocalAccountManager *v8; // rcx
  int RetailDemoUserName; // eax
  __int64 v10; // rbx
  __int64 v11; // rdx
  const WCHAR *v12; // rdi
  int v13; // eax
  const unsigned __int16 *v14; // rcx
  unsigned int v15; // r8d
  __int64 v16; // rbx
  int Instance; // eax
  __int64 v18; // rdx
  const char *v19; // r9
  int v20; // eax
  int v21; // esi
  WCHAR *v22; // rax
  UINT v23; // eax
  int v24; // eax
  int v25; // edi
  WCHAR *v26; // rax
  int v27; // eax
  WCHAR *v28; // rax
  int v29; // eax
  WCHAR *v30; // rax
  WCHAR *v31; // rax
  UINT ACP; // eax
  int pcchMaxUserName; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcchMaxPassword; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcchMaxDomainName; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch]
  LPCWCH lpString2; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  WCHAR *v44; // [rsp+90h] [rbp-70h]
  int v45; // [rsp+98h] [rbp-68h]
  int v46; // [rsp+9Ch] [rbp-64h]
  char v47; // [rsp+A0h] [rbp-60h]
  _QWORD v48[42]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszPassword[264]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR pszDomainName[256]; // [rsp+410h] [rbp+310h] BYREF
  WCHAR pszUserName[264]; // [rsp+610h] [rbp+510h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+758h]

  wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v48,
    "LocalAccountCreate");
  v48[0] = &OOBETelemetry::LocalAccountCreate::`vftable';
  v7 = L"RetailAdminAccount";
  if ( !a4 )
    v7 = L"RetailDemoAccount";
  OOBETelemetry::LocalAccountCreate::StartActivity((OOBETelemetry::LocalAccountCreate *)v48, v7);
  lpString2 = 0;
  v42 = 0;
  v43 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
  v42 = -1;
  v43 = -1;
  RetailDemoUserName = LocalAccountManager::_GetRetailDemoUserName(v8, a4 != 0, (unsigned __int16 **)&lpString2);
  LODWORD(v10) = RetailDemoUserName;
  if ( RetailDemoUserName < 0 )
  {
    v11 = 84;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)RetailDemoUserName,
      pcchMaxUserName);
    goto LABEL_45;
  }
  v12 = lpString2;
  if ( a4 )
  {
    RetailDemoUserName = SHRegSetString(
                           HKEY_LOCAL_MACHINE,
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
                           L"AdminAccount",
                           lpString2);
    LODWORD(v10) = RetailDemoUserName;
    if ( RetailDemoUserName < 0 )
    {
      v11 = 89;
      goto LABEL_8;
    }
  }
  v13 = ValidateUserName(v12, 0);
  if ( v13 < 0 )
  {
    LODWORD(v10) = v13;
    goto LABEL_45;
  }
  memset_0(pszUserName, 0, 0x202u);
  memset_0(pszDomainName, 0, sizeof(pszDomainName));
  memset_0(pszPassword, 0, 0x202u);
  v16 = 257;
  v38 = 257;
  pcchMaxDomainName = 256;
  pcchMaxPassword = 257;
  v35 = 0;
  if ( !a4 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    ACP = GetACP();
    Instance = CCreateLocalUserTask_CreateInstance((_DWORD)v12, ACP, (unsigned int)pszPassword, 0);
    LODWORD(v10) = Instance;
    if ( Instance < 0 )
    {
      v18 = 150;
      goto LABEL_15;
    }
    goto LABEL_43;
  }
  if ( a2 )
  {
    Instance = CoImpersonateClient();
    LODWORD(v10) = Instance;
    if ( Instance < 0 )
    {
      v18 = 107;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)Instance,
        pcchMaxUserName);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      goto LABEL_45;
    }
    if ( !CredUnPackAuthenticationBufferW(
            1u,
            a2,
            a3,
            pszUserName,
            &v38,
            pszDomainName,
            &pcchMaxDomainName,
            pszPassword,
            &pcchMaxPassword) )
    {
      LODWORD(v10) = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x71,
                       (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
                       v19);
      CoRevertToSelf();
      goto LABEL_44;
    }
    CoRevertToSelf();
    v16 = pcchMaxPassword;
  }
  else
  {
    EncodeStringHelper(v14, pszPassword, v15);
  }
  v44 = pszPassword;
  v45 = v16;
  v46 = v40;
  v47 = 1;
  v20 = ValidatePassword(pszPassword);
  v21 = v20;
  if ( v20 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v23 = GetACP();
    v24 = CCreateLocalUserTask_CreateInstance((_DWORD)v12, v23, (unsigned int)pszPassword, 0);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v24,
        pcchMaxUserName);
      if ( v16 )
      {
        v26 = pszPassword;
        do
        {
          *(_BYTE *)v26 = 0;
          v26 = (WCHAR *)((char *)v26 + 1);
          --v16;
        }
        while ( v16 );
      }
LABEL_29:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      LODWORD(v10) = v25;
      goto LABEL_45;
    }
    v39 = 0;
    v27 = Microsoft::WRL::ComPtr<IOOBERunnableTask>::As<ILocalAccountTaskPrivate>(&v35, (__int64)&v39);
    v25 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v27,
        pcchMaxUserName);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      if ( v16 )
      {
        v28 = pszPassword;
        do
        {
          *(_BYTE *)v28 = 0;
          v28 = (WCHAR *)((char *)v28 + 1);
          --v16;
        }
        while ( v16 );
      }
      goto LABEL_29;
    }
    v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 40LL))(v39, 0);
    v25 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v29,
        pcchMaxUserName);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      if ( v16 )
      {
        v30 = pszPassword;
        do
        {
          *(_BYTE *)v30 = 0;
          v30 = (WCHAR *)((char *)v30 + 1);
          --v16;
        }
        while ( v16 );
      }
      goto LABEL_29;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    if ( v16 )
    {
      v31 = pszPassword;
      do
      {
        *(_BYTE *)v31 = 0;
        v31 = (WCHAR *)((char *)v31 + 1);
        --v16;
      }
      while ( v16 );
    }
LABEL_43:
    v10 = ((unsigned int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v35)[4])(v35);
    wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v48, v10);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7E,
    (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
    (const char *)(unsigned int)v20,
    pcchMaxUserName);
  if ( v16 )
  {
    v22 = pszPassword;
    do
    {
      *(_BYTE *)v22 = 0;
      v22 = (WCHAR *)((char *)v22 + 1);
      --v16;
    }
    while ( v16 );
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  LODWORD(v10) = v21;
LABEL_45:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
  OOBETelemetry::LocalAccountCreate::~LocalAccountCreate((OOBETelemetry::LocalAccountCreate *)v48);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f9a0  mov     [rsp-8+arg_0], rbx
0x18002f9a5  mov     [rsp-8+arg_18], rsi
0x18002f9aa  push    rbp
0x18002f9ab  push    rdi
0x18002f9ac  push    r12
0x18002f9ae  push    r14
0x18002f9b0  push    r15
0x18002f9b2  lea     rbp, [rsp-730h]
0x18002f9ba  sub     rsp, 830h
0x18002f9c1  mov     rax, cs:__security_cookie
0x18002f9c8  xor     rax, rsp
0x18002f9cb  mov     [rbp+750h+var_30], rax
0x18002f9d2  mov     esi, r9d
0x18002f9d5  mov     r15d, r8d
0x18002f9d8  mov     r14, rdx
0x18002f9db  lea     rdx, aLocalaccountcr; "LocalAccountCreate"
0x18002f9e2  lea     rcx, [rbp+750h+var_7A0]
0x18002f9e6  call    ??0?$ActivityBase@VOOBELogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002f9eb  lea     rax, ??_7LocalAccountCreate@OOBETelemetry@@6B@; const OOBETelemetry::LocalAccountCreate::`vftable'
0x18002f9f2  mov     [rbp+750h+var_7A0], rax
0x18002f9f6  lea     rax, aRetaildemoacco; "RetailDemoAccount"
0x18002f9fd  lea     rdx, aRetailadminacc; "RetailAdminAccount"
0x18002fa04  xor     r12d, r12d
0x18002fa07  test    esi, esi
0x18002fa09  cmovz   rdx, rax; unsigned __int16 *
0x18002fa0d  lea     rcx, [rbp+750h+var_7A0]; this
0x18002fa11  call    ?StartActivity@LocalAccountCreate@OOBETelemetry@@QEAAXPEBG@Z; OOBETelemetry::LocalAccountCreate::StartActivity(ushort const *)
0x18002fa16  nop
0x18002fa17  mov     [rsp+850h+lpString2], r12
0x18002fa1c  mov     [rbp+750h+var_7D0], r12
0x18002fa20  mov     [rbp+750h+var_7C8], r12
0x18002fa24  lea     rcx, [rsp+850h+lpString2]
0x18002fa29  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002fa2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fa32  mov     [rbp+750h+var_7D0], rax
0x18002fa36  mov     [rbp+750h+var_7C8], rax
0x18002fa3a  test    esi, esi
0x18002fa3c  setnz   dl; bool
0x18002fa3f  lea     r8, [rsp+850h+lpString2]; unsigned __int16 **
0x18002fa44  call    ?_GetRetailDemoUserName@LocalAccountManager@@AEAAJ_NPEAPEAG@Z; LocalAccountManager::_GetRetailDemoUserName(bool,ushort * *)
0x18002fa49  mov     ebx, eax
0x18002fa4b  test    eax, eax
0x18002fa4d  jns     short loc_18002FA56
0x18002fa4f  lea     edx, [r12+54h]
0x18002fa54  jmp     short loc_18002FA87
0x18002fa56  mov     rdi, [rsp+850h+lpString2]
0x18002fa5b  test    esi, esi
0x18002fa5d  jz      short loc_18002FAA2
0x18002fa5f  mov     r9, rdi; unsigned __int16 *
0x18002fa62  lea     r8, ?c_retailDemoValueAdminAccountName@@3QBGB; "AdminAccount"
0x18002fa69  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002fa70  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002fa77  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002fa7c  mov     ebx, eax
0x18002fa7e  test    eax, eax
0x18002fa80  jns     short loc_18002FAA2
0x18002fa82  mov     edx, 59h ; 'Y'; void *
0x18002fa87  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fa8e  mov     r9d, eax; char *
0x18002fa91  mov     rcx, [rbp+758h]; this
0x18002fa98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fa9d  jmp     loc_18002FDDA
0x18002faa2  xor     edx, edx; lpString1
0x18002faa4  mov     rcx, rdi; lpString2
0x18002faa7  call    ?ValidateUserName@@YAJPEBG0@Z; ValidateUserName(ushort const *,ushort const *)
0x18002faac  test    eax, eax
0x18002faae  jns     short loc_18002FAB7
0x18002fab0  mov     ebx, eax
0x18002fab2  jmp     loc_18002FDDA
0x18002fab7  mov     ebx, 202h
0x18002fabc  mov     r8d, ebx; Size
0x18002fabf  xor     edx, edx; Val
0x18002fac1  lea     rcx, [rbp+750h+pszUserName]; void *
0x18002fac8  call    memset_0
0x18002facd  xor     edx, edx; Val
0x18002facf  lea     r8d, [rbx-2]; Size
0x18002fad3  lea     rcx, [rbp+750h+var_440]; void *
0x18002fada  call    memset_0
0x18002fadf  mov     r8d, ebx; Size
0x18002fae2  xor     edx, edx; Val
0x18002fae4  lea     rcx, [rbp+750h+var_650]; void *
0x18002faeb  call    memset_0
0x18002faf0  mov     ebx, 101h
0x18002faf5  mov     [rsp+850h+var_7F0], ebx
0x18002faf9  mov     [rsp+850h+var_7F4], 100h
0x18002fb01  mov     [rsp+850h+var_7F8], ebx
0x18002fb05  mov     [rsp+850h+var_800], r12
0x18002fb0a  test    esi, esi
0x18002fb0c  jz      loc_18002FE1B
0x18002fb12  test    r14, r14
0x18002fb15  jz      loc_18002FBC8
0x18002fb1b  call    cs:__imp_CoImpersonateClient
0x18002fb21  mov     ebx, eax
0x18002fb23  test    eax, eax
0x18002fb25  jns     short loc_18002FB47
0x18002fb27  mov     edx, 6Bh ; 'k'; void *
0x18002fb2c  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fb33  mov     r9d, eax; char *
0x18002fb36  mov     rcx, [rbp+758h]; this
0x18002fb3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb42  jmp     loc_18002FDCF
0x18002fb47  lea     rax, [rsp+850h+var_7F8]
0x18002fb4c  mov     [rsp+850h+pcchMaxPassword], rax; pcchMaxPassword
0x18002fb51  lea     rax, [rbp+750h+var_650]
0x18002fb58  mov     [rsp+850h+pszPassword], rax; pszPassword
0x18002fb5d  lea     rax, [rsp+850h+var_7F4]
0x18002fb62  mov     [rsp+850h+pcchMaxDomainName], rax; pcchMaxDomainName
0x18002fb67  lea     rax, [rbp+750h+var_440]
0x18002fb6e  mov     [rsp+850h+pszDomainName], rax; pszDomainName
0x18002fb73  lea     rax, [rsp+850h+var_7F0]
0x18002fb78  mov     [rsp+850h+pcchMaxUserName], rax; pcchMaxUserName
0x18002fb7d  lea     r9, [rbp+750h+pszUserName]; pszUserName
0x18002fb84  mov     r8d, r15d; cbAuthBuffer
0x18002fb87  mov     rdx, r14; pAuthBuffer
0x18002fb8a  mov     ecx, 1; dwFlags
0x18002fb8f  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18002fb95  test    eax, eax
0x18002fb97  jnz     short loc_18002FBBC
0x18002fb99  mov     rcx, [rbp+758h]; this
0x18002fba0  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fba7  lea     edx, [rax+71h]; void *
0x18002fbaa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fbaf  mov     ebx, eax
0x18002fbb1  call    cs:__imp_CoRevertToSelf
0x18002fbb7  jmp     loc_18002FDCF
0x18002fbbc  call    cs:__imp_CoRevertToSelf
0x18002fbc2  mov     ebx, [rsp+850h+var_7F8]
0x18002fbc6  jmp     short loc_18002FBD4
0x18002fbc8  lea     rdx, [rbp+750h+var_650]; unsigned __int16 *
0x18002fbcf  call    ?EncodeStringHelper@@YAPEBGPEBGPEAGI@Z; EncodeStringHelper(ushort const *,ushort *,uint)
0x18002fbd4  lea     rax, [rbp+750h+var_650]
0x18002fbdb  mov     [rbp+750h+var_7C0], rax
0x18002fbdf  mov     [rbp+750h+var_7B8], ebx
0x18002fbe2  mov     eax, [rsp+850h+var_7DC]
0x18002fbe6  mov     [rbp+750h+var_7B4], eax
0x18002fbe9  mov     [rbp+750h+var_7B0], 1
0x18002fbed  lea     rcx, [rbp+750h+var_650]; unsigned __int16 *
0x18002fbf4  call    ?ValidatePassword@@YAJPEBG@Z; ValidatePassword(ushort const *)
0x18002fbf9  mov     esi, eax
0x18002fbfb  test    eax, eax
0x18002fbfd  jns     short loc_18002FC44
0x18002fbff  mov     rcx, [rbp+758h]; this
0x18002fc06  mov     r9d, eax; char *
0x18002fc09  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fc10  mov     edx, 7Eh ; '~'; void *
0x18002fc15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fc1a  nop
0x18002fc1b  test    rbx, rbx
0x18002fc1e  jz      short loc_18002FC33
0x18002fc20  lea     rax, [rbp+750h+var_650]
0x18002fc27  mov     [rax], r12b
0x18002fc2a  inc     rax
0x18002fc2d  sub     rbx, 1
0x18002fc31  jnz     short loc_18002FC27
0x18002fc33  lea     rcx, [rsp+850h+var_800]
0x18002fc38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fc3d  mov     ebx, esi
0x18002fc3f  jmp     loc_18002FDDA
0x18002fc44  lea     rcx, [rsp+850h+var_800]
0x18002fc49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fc4e  call    cs:__imp_GetACP
0x18002fc54  lea     rcx, [rsp+850h+var_800]
0x18002fc59  mov     [rsp+850h+var_808], rcx
0x18002fc5e  mov     dword ptr [rsp+850h+pcchMaxPassword], r12d
0x18002fc63  mov     byte ptr [rsp+850h+pszPassword], 1
0x18002fc68  mov     byte ptr [rsp+850h+pcchMaxDomainName], 1
0x18002fc6d  mov     byte ptr [rsp+850h+pszDomainName], r12b
0x18002fc72  xor     r9d, r9d
0x18002fc75  lea     r8, [rbp+750h+var_650]
0x18002fc7c  mov     edx, eax
0x18002fc7e  mov     rcx, rdi
0x18002fc81  call    CCreateLocalUserTask_CreateInstance
0x18002fc86  mov     edi, eax
0x18002fc88  test    eax, eax
0x18002fc8a  jns     short loc_18002FCD1
0x18002fc8c  mov     rcx, [rbp+758h]; this
0x18002fc93  mov     r9d, eax; char *
0x18002fc96  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fc9d  mov     edx, 86h; void *
0x18002fca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fca7  nop
0x18002fca8  test    rbx, rbx
0x18002fcab  jz      short loc_18002FCC0
0x18002fcad  lea     rax, [rbp+750h+var_650]
0x18002fcb4  mov     [rax], r12b
0x18002fcb7  inc     rax
0x18002fcba  sub     rbx, 1
0x18002fcbe  jnz     short loc_18002FCB4
0x18002fcc0  lea     rcx, [rsp+850h+var_800]
0x18002fcc5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fcca  mov     ebx, edi
0x18002fccc  jmp     loc_18002FDDA
0x18002fcd1  mov     [rsp+850h+var_7E8], r12
0x18002fcd6  lea     rdx, [rsp+850h+var_7E8]
0x18002fcdb  lea     rcx, [rsp+850h+var_800]
0x18002fce0  call    ??$As@UILocalAccountTaskPrivate@@@?$ComPtr@UIOOBERunnableTask@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILocalAccountTaskPrivate@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IOOBERunnableTask>::As<ILocalAccountTaskPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILocalAccountTaskPrivate>>)
0x18002fce5  mov     edi, eax
0x18002fce7  test    eax, eax
0x18002fce9  jns     short loc_18002FD2C
0x18002fceb  mov     rcx, [rbp+758h]; this
0x18002fcf2  mov     r9d, eax; char *
0x18002fcf5  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fcfc  mov     edx, 8Bh; void *
0x18002fd01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd06  nop
0x18002fd07  lea     rcx, [rsp+850h+var_7E8]
0x18002fd0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fd11  nop
0x18002fd12  test    rbx, rbx
0x18002fd15  jz      short loc_18002FCC0
0x18002fd17  lea     rax, [rbp+750h+var_650]
0x18002fd1e  mov     [rax], r12b
0x18002fd21  inc     rax
0x18002fd24  sub     rbx, 1
0x18002fd28  jnz     short loc_18002FD1E
0x18002fd2a  jmp     short loc_18002FCC0
0x18002fd2c  mov     rcx, [rsp+850h+var_7E8]
0x18002fd31  mov     rax, [rcx]
0x18002fd34  xor     edx, edx
0x18002fd36  mov     rax, [rax+28h]
0x18002fd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd3f  mov     edi, eax
0x18002fd41  test    eax, eax
0x18002fd43  jns     short loc_18002FD8D
0x18002fd45  mov     rcx, [rbp+758h]; this
0x18002fd4c  mov     r9d, eax; char *
0x18002fd4f  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002fd56  mov     edx, 8Ch; void *
0x18002fd5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd60  nop
0x18002fd61  lea     rcx, [rsp+850h+var_7E8]
0x18002fd66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fd6b  nop
0x18002fd6c  test    rbx, rbx
0x18002fd6f  jz      loc_18002FCC0
0x18002fd75  lea     rax, [rbp+750h+var_650]
0x18002fd7c  mov     [rax], r12b
0x18002fd7f  inc     rax
0x18002fd82  sub     rbx, 1
0x18002fd86  jnz     short loc_18002FD7C
0x18002fd88  jmp     loc_18002FCC0
0x18002fd8d  lea     rcx, [rsp+850h+var_7E8]
0x18002fd92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fd97  nop
0x18002fd98  test    rbx, rbx
0x18002fd9b  jz      short loc_18002FDB0
0x18002fd9d  lea     rax, [rbp+750h+var_650]
0x18002fda4  mov     [rax], r12b
0x18002fda7  inc     rax
0x18002fdaa  sub     rbx, 1
0x18002fdae  jnz     short loc_18002FDA4
0x18002fdb0  mov     rcx, [rsp+850h+var_800]
0x18002fdb5  mov     rax, [rcx]
0x18002fdb8  mov     rax, [rax+20h]
0x18002fdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdc1  mov     ebx, eax
0x18002fdc3  mov     edx, eax
0x18002fdc5  lea     rcx, [rbp+750h+var_7A0]
0x18002fdc9  call    ?Stop@?$ActivityBase@VOOBELogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<OOBELogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002fdce  nop
0x18002fdcf  lea     rcx, [rsp+850h+var_800]
0x18002fdd4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fdd9  nop
0x18002fdda  lea     rcx, [rsp+850h+lpString2]
0x18002fddf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002fde4  nop
0x18002fde5  lea     rcx, [rbp+750h+var_7A0]; this
0x18002fde9  call    ??1LocalAccountCreate@OOBETelemetry@@QEAA@XZ; OOBETelemetry::LocalAccountCreate::~LocalAccountCreate(void)
0x18002fdee  mov     eax, ebx
0x18002fdf0  mov     rcx, [rbp+750h+var_30]
0x18002fdf7  xor     rcx, rsp; StackCookie
0x18002fdfa  call    __security_check_cookie
0x18002fdff  lea     r11, [rsp+850h+var_20]
0x18002fe07  mov     rbx, [r11+30h]
0x18002fe0b  mov     rsi, [r11+48h]
0x18002fe0f  mov     rsp, r11
0x18002fe12  pop     r15
0x18002fe14  pop     r14
0x18002fe16  pop     r12
0x18002fe18  pop     rdi
0x18002fe19  pop     rbp
0x18002fe1a  retn
0x18002fe1b  lea     rcx, [rsp+850h+var_800]
0x18002fe20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fe25  call    cs:__imp_GetACP
0x18002fe2b  lea     rcx, [rsp+850h+var_800]
0x18002fe30  mov     [rsp+850h+var_808], rcx
0x18002fe35  mov     dword ptr [rsp+850h+pcchMaxPassword], r12d
0x18002fe3a  mov     byte ptr [rsp+850h+pszPassword], 1
0x18002fe3f  mov     byte ptr [rsp+850h+pcchMaxDomainName], r12b
0x18002fe44  mov     byte ptr [rsp+850h+pszDomainName], 1
0x18002fe49  xor     r9d, r9d
0x18002fe4c  lea     r8, [rbp+750h+var_650]
0x18002fe53  mov     edx, eax
0x18002fe55  mov     rcx, rdi
0x18002fe58  call    CCreateLocalUserTask_CreateInstance
0x18002fe5d  mov     ebx, eax
0x18002fe5f  test    eax, eax
0x18002fe61  jns     loc_18002FDB0
0x18002fe67  mov     edx, 96h
  ... truncated ...
```
