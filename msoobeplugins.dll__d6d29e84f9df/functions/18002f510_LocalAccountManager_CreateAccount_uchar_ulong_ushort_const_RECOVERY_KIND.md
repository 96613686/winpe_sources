# LocalAccountManager::CreateAccount(uchar *,ulong,ushort const *,RECOVERY_KIND)

- ea: `0x18002f510`
- end: `0x18002f917`
- name: `?CreateAccount@LocalAccountManager@@UEAAJPEAEKPEBGW4RECOVERY_KIND@@@Z`
- size: `1031`
- prototype: `int __high(unsigned __int8 *, unsigned int, const unsigned __int16 *, enum RECOVERY_KIND)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180007bbc`
- `0x180008524`
- `0x180008544`
- `0x18002ef34`
- `0x18002f510`
- `0x180030280`
- `0x180031718`
- `0x180031800`
- `0x180032cd4`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002f701`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002f701`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002f601`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002f601`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002f623`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002f64e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002f623`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002f64e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002f58b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002f58b`

## string_xrefs

- `0x18002f5a1`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f612`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f672`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f6bc`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f74f`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f7c1`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f82c`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18002f8a2`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LocalAccountManager::CreateAccount(__int64 a1, void *a2, DWORD a3, int a4)
{
  HRESULT v7; // eax
  unsigned int LastError; // ebx
  const char *v9; // r9
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  WCHAR *v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  WCHAR *v16; // rax
  UINT ACP; // eax
  int Instance; // eax
  __int64 v19; // rcx
  WCHAR *v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  WCHAR *v23; // rax
  int v24; // eax
  __int64 v25; // rcx
  WCHAR *v26; // rax
  int v27; // eax
  unsigned int v28; // esi
  __int64 v29; // rbx
  WCHAR *v30; // rax
  WCHAR *v31; // rax
  int pcchMaxUserName; // [rsp+20h] [rbp-E0h]
  int pcchMaxUserNamea; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-B0h] BYREF
  char v36; // [rsp+59h] [rbp-A7h]
  DWORD pcchMaxPassword; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD pcchMaxDomainName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v39; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+74h] [rbp-8Ch]
  WCHAR *v42; // [rsp+78h] [rbp-88h]
  DWORD v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+84h] [rbp-7Ch]
  char v45; // [rsp+88h] [rbp-78h]
  WCHAR pszPassword[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszUserName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszDomainName[256]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  memset_0(pszUserName, 0, 0x202u);
  memset_0(pszDomainName, 0, sizeof(pszDomainName));
  memset_0(pszPassword, 0, 0x202u);
  v39 = 257;
  pcchMaxDomainName = 256;
  pcchMaxPassword = 257;
  v7 = CoImpersonateClient();
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)v7,
      pcchMaxUserName);
    return LastError;
  }
  v36 = 1;
  if ( !CredUnPackAuthenticationBufferW(
          1u,
          a2,
          a3,
          pszUserName,
          &v39,
          pszDomainName,
          &pcchMaxDomainName,
          pszPassword,
          &pcchMaxPassword) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x32,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
                  v9);
    CoRevertToSelf();
    return LastError;
  }
  v10 = pcchMaxPassword;
  v42 = pszPassword;
  v43 = pcchMaxPassword;
  v44 = v41;
  v45 = 1;
  v36 = 0;
  CoRevertToSelf();
  v11 = ValidateUserName(pszUserName, 0);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)v11,
      pcchMaxUserNamea);
    v12 = (unsigned int)v10;
    if ( (_DWORD)v10 )
    {
      v13 = pszPassword;
      do
      {
        *(_BYTE *)v13 = 0;
        v13 = (WCHAR *)((char *)v13 + 1);
        --v12;
      }
      while ( v12 );
    }
    return LastError;
  }
  v14 = ValidatePassword(pszPassword);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)v14,
      pcchMaxUserNamea);
    v15 = v10;
    if ( (_DWORD)v10 )
    {
      v16 = pszPassword;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (WCHAR *)((char *)v16 + 1);
        --v15;
      }
      while ( v15 );
    }
    return LastError;
  }
  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  ACP = GetACP();
  Instance = CCreateLocalUserTask_CreateInstance((unsigned int)pszUserName, ACP, (unsigned int)pszPassword, a4);
  LastError = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)Instance,
      pcchMaxUserNamea);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v19 = v10;
    if ( (_DWORD)v10 )
    {
      v20 = pszPassword;
      do
      {
        *(_BYTE *)v20 = 0;
        v20 = (WCHAR *)((char *)v20 + 1);
        --v19;
      }
      while ( v19 );
    }
    return LastError;
  }
  if ( !IsUserOOBE() )
  {
    v40 = 0;
    v21 = Microsoft::WRL::ComPtr<IOOBERunnableTask>::As<ILocalAccountTaskPrivate>(&v35, (__int64)&v40);
    LastError = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v21,
        pcchMaxUserNamea);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      v22 = v10;
      if ( (_DWORD)v10 )
      {
        v23 = pszPassword;
        do
        {
          *(_BYTE *)v23 = 0;
          v23 = (WCHAR *)((char *)v23 + 1);
          --v22;
        }
        while ( v22 );
      }
      return LastError;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 40LL))(v40, 0);
    LastError = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v24,
        pcchMaxUserNamea);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      v25 = v10;
      if ( (_DWORD)v10 )
      {
        v26 = pszPassword;
        do
        {
          *(_BYTE *)v26 = 0;
          v26 = (WCHAR *)((char *)v26 + 1);
          --v25;
        }
        while ( v25 );
      }
      return LastError;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  }
  v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v35)[4])(v35);
  v28 = v27;
  v29 = v10;
  if ( v27 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    if ( (_DWORD)v10 )
    {
      v31 = pszPassword;
      do
      {
        *(_BYTE *)v31 = 0;
        v31 = (WCHAR *)((char *)v31 + 1);
        --v29;
      }
      while ( v29 );
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)v27,
      pcchMaxUserNamea);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    if ( (_DWORD)v10 )
    {
      v30 = pszPassword;
      do
      {
        *(_BYTE *)v30 = 0;
        v30 = (WCHAR *)((char *)v30 + 1);
        --v29;
      }
      while ( v29 );
    }
    return v28;
  }
}

```

## disassembly

```asm
0x18002f510  push    rbp
0x18002f512  push    rbx
0x18002f513  push    rsi
0x18002f514  push    rdi
0x18002f515  push    r14
0x18002f517  lea     rbp, [rsp-5C0h]
0x18002f51f  sub     rsp, 6C0h
0x18002f526  mov     rax, cs:__security_cookie
0x18002f52d  xor     rax, rsp
0x18002f530  mov     [rbp+5E0h+var_30], rax
0x18002f537  mov     r14, r9
0x18002f53a  mov     esi, r8d
0x18002f53d  mov     rdi, rdx
0x18002f540  mov     ebx, 202h
0x18002f545  mov     r8d, ebx; Size
0x18002f548  xor     edx, edx; Val
0x18002f54a  lea     rcx, [rbp+5E0h+pszUserName]; void *
0x18002f551  call    memset_0
0x18002f556  xor     edx, edx; Val
0x18002f558  lea     r8d, [rbx-2]; Size
0x18002f55c  lea     rcx, [rbp+5E0h+var_230]; void *
0x18002f563  call    memset_0
0x18002f568  mov     r8d, ebx; Size
0x18002f56b  xor     edx, edx; Val
0x18002f56d  lea     rcx, [rbp+5E0h+var_650]; void *
0x18002f571  call    memset_0
0x18002f576  mov     eax, 101h
0x18002f57b  mov     [rsp+6E0h+var_67C], eax
0x18002f57f  mov     [rsp+6E0h+var_680], 100h
0x18002f587  mov     [rsp+6E0h+var_684], eax
0x18002f58b  call    cs:__imp_CoImpersonateClient
0x18002f591  mov     ebx, eax
0x18002f593  test    eax, eax
0x18002f595  jns     short loc_18002F5B7
0x18002f597  mov     rcx, [rbp+5E8h]; this
0x18002f59e  mov     r9d, eax; char *
0x18002f5a1  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f5a8  mov     edx, 2Ch ; ','; void *
0x18002f5ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f5b2  jmp     loc_18002F8F8
0x18002f5b7  mov     [rsp+6E0h+var_687], 1
0x18002f5bc  lea     rax, [rsp+6E0h+var_684]
0x18002f5c1  mov     [rsp+6E0h+pcchMaxPassword], rax; pcchMaxPassword
0x18002f5c6  lea     rax, [rbp+5E0h+var_650]
0x18002f5ca  mov     [rsp+6E0h+pszPassword], rax; pszPassword
0x18002f5cf  lea     rax, [rsp+6E0h+var_680]
0x18002f5d4  mov     [rsp+6E0h+pcchMaxDomainName], rax; pcchMaxDomainName
0x18002f5d9  lea     rax, [rbp+5E0h+var_230]
0x18002f5e0  mov     [rsp+6E0h+pszDomainName], rax; pszDomainName
0x18002f5e5  lea     rax, [rsp+6E0h+var_67C]
0x18002f5ea  mov     [rsp+6E0h+pcchMaxUserName], rax; int
0x18002f5ef  lea     r9, [rbp+5E0h+pszUserName]; pszUserName
0x18002f5f6  mov     r8d, esi; cbAuthBuffer
0x18002f5f9  mov     rdx, rdi; pAuthBuffer
0x18002f5fc  mov     ecx, 1; dwFlags
0x18002f601  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18002f607  test    eax, eax
0x18002f609  jnz     short loc_18002F62E
0x18002f60b  mov     rcx, [rbp+5E8h]; this
0x18002f612  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f619  lea     edx, [rax+32h]; void *
0x18002f61c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f621  mov     ebx, eax
0x18002f623  call    cs:__imp_CoRevertToSelf
0x18002f629  jmp     loc_18002F8F8
0x18002f62e  mov     edi, [rsp+6E0h+var_684]
0x18002f632  lea     rax, [rbp+5E0h+var_650]
0x18002f636  mov     [rsp+6E0h+var_668], rax
0x18002f63b  mov     [rbp+5E0h+var_660], edi
0x18002f63e  mov     eax, [rsp+6E0h+var_66C]
0x18002f642  mov     [rbp+5E0h+var_65C], eax
0x18002f645  mov     [rbp+5E0h+var_658], 1
0x18002f649  mov     [rsp+6E0h+var_687], 0
0x18002f64e  call    cs:__imp_CoRevertToSelf
0x18002f654  xor     edx, edx; lpString1
0x18002f656  lea     rcx, [rbp+5E0h+pszUserName]; lpString2
0x18002f65d  call    ?ValidateUserName@@YAJPEBG0@Z; ValidateUserName(ushort const *,ushort const *)
0x18002f662  mov     ebx, eax
0x18002f664  test    eax, eax
0x18002f666  jns     short loc_18002F6A3
0x18002f668  mov     rcx, [rbp+5E8h]; this
0x18002f66f  mov     r9d, eax; char *
0x18002f672  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f679  mov     edx, 3Ah ; ':'; void *
0x18002f67e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f683  nop
0x18002f684  mov     ecx, edi
0x18002f686  test    edi, edi
0x18002f688  jz      loc_18002F8F8
0x18002f68e  lea     rax, [rbp+5E0h+var_650]
0x18002f692  mov     byte ptr [rax], 0
0x18002f695  inc     rax
0x18002f698  sub     rcx, 1
0x18002f69c  jnz     short loc_18002F692
0x18002f69e  jmp     loc_18002F8F8
0x18002f6a3  lea     rcx, [rbp+5E0h+var_650]; unsigned __int16 *
0x18002f6a7  call    ?ValidatePassword@@YAJPEBG@Z; ValidatePassword(ushort const *)
0x18002f6ac  mov     ebx, eax
0x18002f6ae  test    eax, eax
0x18002f6b0  jns     short loc_18002F6EE
0x18002f6b2  mov     rcx, [rbp+5E8h]; this
0x18002f6b9  mov     r9d, eax; char *
0x18002f6bc  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f6c3  mov     edx, 3Dh ; '='; void *
0x18002f6c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f6cd  nop
0x18002f6ce  mov     rcx, rdi
0x18002f6d1  test    edi, edi
0x18002f6d3  jz      loc_18002F8F8
0x18002f6d9  lea     rax, [rbp+5E0h+var_650]
0x18002f6dd  mov     byte ptr [rax], 0
0x18002f6e0  inc     rax
0x18002f6e3  sub     rcx, 1
0x18002f6e7  jnz     short loc_18002F6DD
0x18002f6e9  jmp     loc_18002F8F8
0x18002f6ee  mov     [rsp+6E0h+var_690], 0
0x18002f6f7  lea     rcx, [rsp+6E0h+var_690]
0x18002f6fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f701  call    cs:__imp_GetACP
0x18002f707  lea     rcx, [rsp+6E0h+var_690]
0x18002f70c  mov     [rsp+6E0h+var_698], rcx
0x18002f711  mov     ecx, [rbp+5E0h+arg_20]
0x18002f717  mov     dword ptr [rsp+6E0h+pcchMaxPassword], ecx
0x18002f71b  mov     byte ptr [rsp+6E0h+pszPassword], 1
0x18002f720  mov     byte ptr [rsp+6E0h+pcchMaxDomainName], 1
0x18002f725  mov     byte ptr [rsp+6E0h+pszDomainName], 0
0x18002f72a  mov     r9, r14
0x18002f72d  lea     r8, [rbp+5E0h+var_650]
0x18002f731  mov     edx, eax
0x18002f733  lea     rcx, [rbp+5E0h+pszUserName]
0x18002f73a  call    CCreateLocalUserTask_CreateInstance
0x18002f73f  mov     ebx, eax
0x18002f741  test    eax, eax
0x18002f743  jns     short loc_18002F78C
0x18002f745  mov     rcx, [rbp+5E8h]; this
0x18002f74c  mov     r9d, eax; char *
0x18002f74f  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f756  mov     edx, 41h ; 'A'; void *
0x18002f75b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f760  nop
0x18002f761  lea     rcx, [rsp+6E0h+var_690]
0x18002f766  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f76b  nop
0x18002f76c  mov     rcx, rdi
0x18002f76f  test    edi, edi
0x18002f771  jz      loc_18002F8F8
0x18002f777  lea     rax, [rbp+5E0h+var_650]
0x18002f77b  mov     byte ptr [rax], 0
0x18002f77e  inc     rax
0x18002f781  sub     rcx, 1
0x18002f785  jnz     short loc_18002F77B
0x18002f787  jmp     loc_18002F8F8
0x18002f78c  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18002f791  test    al, al
0x18002f793  jnz     loc_18002F87E
0x18002f799  mov     [rsp+6E0h+var_678], 0
0x18002f7a2  lea     rdx, [rsp+6E0h+var_678]
0x18002f7a7  lea     rcx, [rsp+6E0h+var_690]
0x18002f7ac  call    ??$As@UILocalAccountTaskPrivate@@@?$ComPtr@UIOOBERunnableTask@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILocalAccountTaskPrivate@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IOOBERunnableTask>::As<ILocalAccountTaskPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILocalAccountTaskPrivate>>)
0x18002f7b1  mov     ebx, eax
0x18002f7b3  test    eax, eax
0x18002f7b5  jns     short loc_18002F809
0x18002f7b7  mov     rcx, [rbp+5E8h]; this
0x18002f7be  mov     r9d, eax; char *
0x18002f7c1  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f7c8  mov     edx, 47h ; 'G'; void *
0x18002f7cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f7d2  nop
0x18002f7d3  lea     rcx, [rsp+6E0h+var_678]
0x18002f7d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f7dd  nop
0x18002f7de  lea     rcx, [rsp+6E0h+var_690]
0x18002f7e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f7e8  nop
0x18002f7e9  mov     rcx, rdi
0x18002f7ec  test    edi, edi
0x18002f7ee  jz      loc_18002F8F8
0x18002f7f4  lea     rax, [rbp+5E0h+var_650]
0x18002f7f8  mov     byte ptr [rax], 0
0x18002f7fb  inc     rax
0x18002f7fe  sub     rcx, 1
0x18002f802  jnz     short loc_18002F7F8
0x18002f804  jmp     loc_18002F8F8
0x18002f809  mov     rcx, [rsp+6E0h+var_678]
0x18002f80e  mov     rax, [rcx]
0x18002f811  xor     edx, edx
0x18002f813  mov     rax, [rax+28h]
0x18002f817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f81c  mov     ebx, eax
0x18002f81e  test    eax, eax
0x18002f820  jns     short loc_18002F874
0x18002f822  mov     rcx, [rbp+5E8h]; this
0x18002f829  mov     r9d, eax; char *
0x18002f82c  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f833  mov     edx, 48h ; 'H'; void *
0x18002f838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f83d  nop
0x18002f83e  lea     rcx, [rsp+6E0h+var_678]
0x18002f843  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f848  nop
0x18002f849  lea     rcx, [rsp+6E0h+var_690]
0x18002f84e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f853  nop
0x18002f854  mov     rcx, rdi
0x18002f857  test    edi, edi
0x18002f859  jz      loc_18002F8F8
0x18002f85f  lea     rax, [rbp+5E0h+var_650]
0x18002f863  mov     byte ptr [rax], 0
0x18002f866  inc     rax
0x18002f869  sub     rcx, 1
0x18002f86d  jnz     short loc_18002F863
0x18002f86f  jmp     loc_18002F8F8
0x18002f874  lea     rcx, [rsp+6E0h+var_678]
0x18002f879  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f87e  mov     rcx, [rsp+6E0h+var_690]
0x18002f883  mov     rax, [rcx]
0x18002f886  mov     rax, [rax+20h]
0x18002f88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f88f  mov     esi, eax
0x18002f891  mov     rbx, rdi
0x18002f894  test    eax, eax
0x18002f896  jns     short loc_18002F8D7
0x18002f898  mov     rcx, [rbp+5E8h]; this
0x18002f89f  mov     r9d, eax; char *
0x18002f8a2  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002f8a9  mov     edx, 4Ah ; 'J'; void *
0x18002f8ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f8b3  nop
0x18002f8b4  lea     rcx, [rsp+6E0h+var_690]
0x18002f8b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f8be  nop
0x18002f8bf  test    edi, edi
0x18002f8c1  jz      short loc_18002F8D3
0x18002f8c3  lea     rax, [rbp+5E0h+var_650]
0x18002f8c7  mov     byte ptr [rax], 0
0x18002f8ca  inc     rax
0x18002f8cd  sub     rbx, 1
0x18002f8d1  jnz     short loc_18002F8C7
0x18002f8d3  mov     ebx, esi
0x18002f8d5  jmp     short loc_18002F8F8
0x18002f8d7  lea     rcx, [rsp+6E0h+var_690]
0x18002f8dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f8e1  nop
0x18002f8e2  test    edi, edi
0x18002f8e4  jz      short loc_18002F8F6
0x18002f8e6  lea     rax, [rbp+5E0h+var_650]
0x18002f8ea  mov     byte ptr [rax], 0
0x18002f8ed  inc     rax
0x18002f8f0  sub     rbx, 1
0x18002f8f4  jnz     short loc_18002F8EA
0x18002f8f6  xor     ebx, ebx
0x18002f8f8  mov     eax, ebx
0x18002f8fa  mov     rcx, [rbp+5E0h+var_30]
0x18002f901  xor     rcx, rsp; StackCookie
0x18002f904  call    __security_check_cookie
0x18002f909  add     rsp, 6C0h
0x18002f910  pop     r14
0x18002f912  pop     rdi
0x18002f913  pop     rsi
0x18002f914  pop     rbx
0x18002f915  pop     rbp
0x18002f916  retn
```
