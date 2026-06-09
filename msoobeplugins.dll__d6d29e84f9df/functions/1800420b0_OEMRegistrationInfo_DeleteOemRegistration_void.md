# OEMRegistrationInfo::DeleteOemRegistration(void)

- ea: `0x1800420b0`
- end: `0x1800421af`
- name: `?DeleteOemRegistration@OEMRegistrationInfo@@QEAAXXZ`
- size: `255`
- prototype: `void __fastcall(OEMRegistrationInfo *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180042820`

## callees

- `0x180003470`
- `0x18001e9a4`
- `0x1800416d4`
- `0x1800420b0`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x1800420ef`
- `SHELL32!SHGetFolderPathEx` at `0x1800420ef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042120`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042149`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042171`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042120`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042149`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042171`

## string_xrefs

- `0x180042126`: `userchoices.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall OEMRegistrationInfo::DeleteOemRegistration(OEMRegistrationInfo *this)
{
  LPCWSTR v1; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v2; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v4[528]; // [rsp+50h] [rbp-B0h] BYREF

  if ( (int)SHGetFolderPathEx(&FOLDERID_System, 0x4000, -1, v4, 260) >= 0 )
  {
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      lpFileName,
      L"%s\\oobe\\info\\%s",
      v4,
      L"userdata.blob");
    DeleteFileW(lpFileName[0]);
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v2,
      L"%s\\oobe\\info\\%s",
      v4,
      L"userchoices.xml");
    DeleteFileW(v2);
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v1,
      L"%s\\oobe\\info\\%s",
      v4,
      L"sessionkey.blob");
    DeleteFileW(v1);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v1);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v2);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpFileName);
  }
}

```

## disassembly

```asm
0x1800420b0  push    rbp
0x1800420b2  lea     rbp, [rsp-170h]
0x1800420ba  sub     rsp, 270h
0x1800420c1  mov     rax, cs:__security_cookie
0x1800420c8  xor     rax, rsp
0x1800420cb  mov     [rbp+170h+var_10], rax
0x1800420d2  mov     [rsp+270h+var_250], 104h
0x1800420da  lea     r9, [rsp+270h+var_220]
0x1800420df  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800420e3  mov     edx, 4000h
0x1800420e8  lea     rcx, FOLDERID_System
0x1800420ef  call    cs:__imp_SHGetFolderPathEx
0x1800420f5  test    eax, eax
0x1800420f7  js      loc_180042197
0x1800420fd  lea     r9, aUserdataBlob; "userdata.blob"
0x180042104  lea     r8, [rsp+270h+var_220]
0x180042109  lea     rdx, aSOobeInfoS; "%s\\oobe\\info\\%s"
0x180042110  lea     rcx, [rsp+270h+lpFileName]
0x180042115  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x18004211a  nop
0x18004211b  mov     rcx, [rsp+270h+lpFileName]; lpFileName
0x180042120  call    cs:__imp_DeleteFileW
0x180042126  lea     r9, aUserchoicesXml; "userchoices.xml"
0x18004212d  lea     r8, [rsp+270h+var_220]
0x180042132  lea     rdx, aSOobeInfoS; "%s\\oobe\\info\\%s"
0x180042139  lea     rcx, [rsp+270h+var_238]
0x18004213e  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180042143  nop
0x180042144  mov     rcx, [rsp+270h+var_238]; lpFileName
0x180042149  call    cs:__imp_DeleteFileW
0x18004214f  lea     r9, aSessionkeyBlob; "sessionkey.blob"
0x180042156  lea     r8, [rsp+270h+var_220]
0x18004215b  lea     rdx, aSOobeInfoS; "%s\\oobe\\info\\%s"
0x180042162  lea     rcx, [rsp+270h+var_240]
0x180042167  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x18004216c  mov     rcx, [rsp+270h+var_240]; lpFileName
0x180042171  call    cs:__imp_DeleteFileW
0x180042177  lea     rcx, [rsp+270h+var_240]
0x18004217c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180042181  nop
0x180042182  lea     rcx, [rsp+270h+var_238]
0x180042187  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004218c  nop
0x18004218d  lea     rcx, [rsp+270h+lpFileName]
0x180042192  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180042197  mov     rcx, [rbp+170h+var_10]
0x18004219e  xor     rcx, rsp; StackCookie
0x1800421a1  call    __security_check_cookie
0x1800421a6  add     rsp, 270h
0x1800421ad  pop     rbp
0x1800421ae  retn
```
