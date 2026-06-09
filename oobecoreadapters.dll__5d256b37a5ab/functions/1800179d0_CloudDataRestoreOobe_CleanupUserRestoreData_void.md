# CloudDataRestoreOobe::CleanupUserRestoreData(void)

- ea: `0x1800179d0`
- end: `0x180017bcd`
- name: `?CleanupUserRestoreData@CloudDataRestoreOobe@@UEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(CloudDataRestoreOobe *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x180009814`
- `0x18000b098`
- `0x18000b0c8`
- `0x1800162b8`
- `0x180016e38`
- `0x18001763c`
- `0x1800179d0`
- `0x180018b80`
- `0x18001947c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017a3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017a3b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180017b68`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180017b68`

## string_xrefs

- `0x180017a77`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x180017b49`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x180017b7d`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CloudDataRestoreOobe::CleanupUserRestoreData(CloudDataRestoreOobe *this)
{
  LSTATUS ValueW; // eax
  signed int v2; // ebx
  char v3; // al
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-268h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-248h] BYREF
  __int64 v10; // [rsp+48h] [rbp-240h] BYREF
  __int64 v11; // [rsp+50h] [rbp-238h] BYREF
  _BYTE v12[8]; // [rsp+58h] [rbp-230h] BYREF
  _WORD pvData[264]; // [rsp+60h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  memset_0(pvData, 0, 0x208u);
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SystemMetaData",
             L"CloudRestoreProfileId",
             2u,
             0,
             pvData,
             pcbData);
  v2 = ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v2 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( !v2 || (v3 = 1, v2 == -2147024894) )
    v3 = 0;
  if ( v3 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
      (const char *)(unsigned int)v2,
      pdwType);
  if ( v2 >= 0 && pvData[0] )
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
      pcbData,
      L"%LocalAppData%\\Microsoft\\Windows\\CloudStore\\");
    v4 = wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &,unsigned short (&)[260]>(
           v12,
           pcbData,
           pvData);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      pcbData,
      v4);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v12);
    wil::RemoveDirectoryRecursiveNoThrow(*(_QWORD *)pcbData, 0, -1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pcbData);
  }
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
    &v11,
    L"%LocalAppData%\\Microsoft\\Windows\\CloudStoreAssets");
  wil::RemoveDirectoryRecursiveNoThrow(v11, 0, -1);
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
    &v10,
    L"%LocalAppData%\\PlaceholderTileLogoFolder");
  wil::RemoveDirectoryRecursiveNoThrow(v10, 0, -1);
  v5 = CloudDataRestoreOobe::_CleanupBackupData();
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
      (const char *)(unsigned int)v5,
      pdwType);
  v6 = SHDeleteKeyW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudRestore");
  if ( v6 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x78,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
      (const char *)v6,
      pdwType);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  return 0;
}

```

## disassembly

```asm
0x1800179d0  mov     [rsp+arg_0], rbx
0x1800179d5  push    rdi
0x1800179d6  sub     rsp, 280h
0x1800179dd  mov     rax, cs:__security_cookie
0x1800179e4  xor     rax, rsp
0x1800179e7  mov     [rsp+288h+var_18], rax
0x1800179ef  mov     ebx, 208h
0x1800179f4  mov     r8d, ebx; Size
0x1800179f7  xor     edx, edx; Val
0x1800179f9  lea     rcx, [rsp+288h+var_228]; void *
0x1800179fe  call    memset_0
0x180017a03  mov     [rsp+288h+var_248], ebx
0x180017a07  lea     rax, [rsp+288h+var_248]
0x180017a0c  mov     [rsp+288h+pcbData], rax; pcbData
0x180017a11  lea     rax, [rsp+288h+var_228]
0x180017a16  mov     [rsp+288h+pvData], rax; pvData
0x180017a1b  xor     edi, edi
0x180017a1d  mov     [rsp+288h+pdwType], rdi; unsigned int
0x180017a22  lea     r9d, [rdi+2]; dwFlags
0x180017a26  lea     r8, aCloudrestorepr; "CloudRestoreProfileId"
0x180017a2d  lea     rdx, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017a34  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180017a3b  call    cs:__imp_RegGetValueW
0x180017a41  mov     ebx, eax
0x180017a43  test    eax, eax
0x180017a45  jz      short loc_180017A57
0x180017a47  mov     [rsp+288h+var_228], di
0x180017a4c  jle     short loc_180017A57
0x180017a4e  movzx   ebx, ax
0x180017a51  or      ebx, 80070000h
0x180017a57  test    ebx, ebx
0x180017a59  jz      short loc_180017A65
0x180017a5b  cmp     ebx, 80070002h
0x180017a61  mov     al, 1
0x180017a63  jnz     short loc_180017A68
0x180017a65  mov     al, dil
0x180017a68  mov     rcx, [rsp+288h]; this
0x180017a70  test    al, al
0x180017a72  jz      short loc_180017A88
0x180017a74  mov     r9d, ebx; char *
0x180017a77  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x180017a7e  mov     edx, 65h ; 'e'; void *
0x180017a83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017a88  test    ebx, ebx
0x180017a8a  js      short loc_180017AF0
0x180017a8c  cmp     [rsp+288h+var_228], di
0x180017a91  jz      short loc_180017AF0
0x180017a93  lea     rdx, aLocalappdataMi_0; "%LocalAppData%\\Microsoft\\Windows\\Clo"...
0x180017a9a  lea     rcx, [rsp+288h+var_248]
0x180017a9f  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180017aa4  nop
0x180017aa5  lea     r8, [rsp+288h+var_228]
0x180017aaa  lea     rdx, [rsp+288h+var_248]
0x180017aaf  lea     rcx, [rsp+288h+var_230]
0x180017ab4  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV12@AEAY0BAE@G@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAV10@AEAY0BAE@G@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort (&)[260]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort (&)[260])
0x180017ab9  mov     rdx, rax
0x180017abc  lea     rcx, [rsp+288h+var_248]
0x180017ac1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180017ac6  lea     rcx, [rsp+288h+var_230]
0x180017acb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017ad0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017ad4  mov     r8, rbx
0x180017ad7  xor     edx, edx
0x180017ad9  mov     rcx, qword ptr [rsp+288h+var_248]
0x180017ade  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180017ae3  nop
0x180017ae4  lea     rcx, [rsp+288h+var_248]
0x180017ae9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017aee  jmp     short loc_180017AF4
0x180017af0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017af4  lea     rdx, aLocalappdataMi; "%LocalAppData%\\Microsoft\\Windows\\Clo"...
0x180017afb  lea     rcx, [rsp+288h+var_238]
0x180017b00  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180017b05  nop
0x180017b06  mov     r8, rbx
0x180017b09  xor     edx, edx
0x180017b0b  mov     rcx, [rsp+288h+var_238]
0x180017b10  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180017b15  lea     rdx, aLocalappdataPl; "%LocalAppData%\\PlaceholderTileLogoFold"...
0x180017b1c  lea     rcx, [rsp+288h+var_240]
0x180017b21  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180017b26  mov     r8, rbx
0x180017b29  xor     edx, edx
0x180017b2b  mov     rcx, [rsp+288h+var_240]
0x180017b30  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180017b35  call    ?_CleanupBackupData@CloudDataRestoreOobe@@CAJXZ; CloudDataRestoreOobe::_CleanupBackupData(void)
0x180017b3a  mov     rcx, [rsp+288h]; this
0x180017b42  test    eax, eax
0x180017b44  jns     short loc_180017B5A
0x180017b46  mov     r9d, eax; char *
0x180017b49  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x180017b50  mov     edx, 75h ; 'u'; void *
0x180017b55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017b5a  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017b61  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180017b68  call    cs:__imp_SHDeleteKeyW
0x180017b6e  mov     rcx, [rsp+288h]; this
0x180017b76  test    eax, eax
0x180017b78  jz      short loc_180017B8E
0x180017b7a  mov     r9d, eax; char *
0x180017b7d  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x180017b84  mov     edx, 78h ; 'x'; void *
0x180017b89  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180017b8e  lea     rcx, [rsp+288h+var_240]
0x180017b93  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017b98  nop
0x180017b99  lea     rcx, [rsp+288h+var_238]
0x180017b9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017ba3  xor     eax, eax
0x180017ba5  jmp     short loc_180017BAB
0x180017ba7  mov     eax, [rsp+288h+var_248]
0x180017bab  mov     rcx, [rsp+288h+var_18]
0x180017bb3  xor     rcx, rsp; StackCookie
0x180017bb6  call    __security_check_cookie
0x180017bbb  mov     rbx, [rsp+288h+arg_0]
0x180017bc3  add     rsp, 280h
0x180017bca  pop     rdi
0x180017bcb  retn
```
