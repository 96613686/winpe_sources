# AdvertisingIdHelpers::DeleteAdvertisingRegKeyForUser

- ea: `0x180005e44`
- end: `0x180005f2b`
- name: `AdvertisingIdHelpers::DeleteAdvertisingRegKeyForUser`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800061c4`

## callees

- `0x180005e44`
- `0x180005f34`
- `0x180005f54`
- `0x180006324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005e66`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005edb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005e66`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005edb`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::DeleteAdvertisingRegKeyForUser(unsigned __int16 *a1)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  int UserAdvertisingRegPath; // eax
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  LSTATUS v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    lpSubKey = 0;
    UserAdvertisingRegPath = AdvertisingIdHelpers::GetUserAdvertisingRegPath(a1);
    v2 = UserAdvertisingRegPath;
    if ( UserAdvertisingRegPath >= 0 )
    {
      v7 = RegDeleteKeyExW(HKEY_USERS, lpSubKey, 0x100u, 0);
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( (v2 & 0x80000000) == 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
        return 0;
      }
      v5 = v2;
      v6 = 835;
    }
    else
    {
      v5 = (unsigned int)UserAdvertisingRegPath;
      v6 = 833;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)v5,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    return v2;
  }
  v1 = RegDeleteKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo", 0x100u, 0);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x33C,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)v2,
      v8);
    return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x180005e44  push    rbx; int
0x180005e46  sub     rsp, 20h
0x180005e4a  test    rcx, rcx
0x180005e4d  jnz     short loc_180005EA3
0x180005e4f  xor     r9d, r9d; Reserved
0x180005e52  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180005e59  mov     r8d, 100h; samDesired
0x180005e5f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180005e66  call    cs:__imp_RegDeleteKeyExW
0x180005e6c  mov     ebx, eax
0x180005e6e  test    eax, eax
0x180005e70  jle     short loc_180005E7B
0x180005e72  movzx   ebx, ax
0x180005e75  or      ebx, 80070000h
0x180005e7b  test    ebx, ebx
0x180005e7d  jns     loc_180005F23
0x180005e83  mov     rcx, [rsp+28h]; this
0x180005e88  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180005e8f  mov     r9d, ebx; char *
0x180005e92  mov     edx, 33Ch; void *
0x180005e97  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005e9c  mov     eax, ebx
0x180005e9e  jmp     loc_180005F25
0x180005ea3  lea     rdx, [rsp+28h+lpSubKey]
0x180005ea8  mov     [rsp+28h+lpSubKey], 0
0x180005eb1  call    AdvertisingIdHelpers__GetUserAdvertisingRegPath
0x180005eb6  mov     ebx, eax
0x180005eb8  test    eax, eax
0x180005eba  jns     short loc_180005EC6
0x180005ebc  mov     r9d, eax
0x180005ebf  mov     edx, 341h
0x180005ec4  jmp     short loc_180005EFC
0x180005ec6  mov     rdx, [rsp+28h+lpSubKey]; lpSubKey
0x180005ecb  xor     r9d, r9d; Reserved
0x180005ece  mov     r8d, 100h; samDesired
0x180005ed4  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180005edb  call    cs:__imp_RegDeleteKeyExW
0x180005ee1  mov     ebx, eax
0x180005ee3  test    eax, eax
0x180005ee5  jle     short loc_180005EF0
0x180005ee7  movzx   ebx, ax
0x180005eea  or      ebx, 80070000h
0x180005ef0  test    ebx, ebx
0x180005ef2  jns     short loc_180005F19
0x180005ef4  mov     r9d, ebx; char *
0x180005ef7  mov     edx, 343h; void *
0x180005efc  mov     rcx, [rsp+28h]; this
0x180005f01  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180005f08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005f0d  lea     rcx, [rsp+28h+lpSubKey]
0x180005f12  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180005f17  jmp     short loc_180005E9C
0x180005f19  lea     rcx, [rsp+28h+lpSubKey]
0x180005f1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180005f23  xor     eax, eax
0x180005f25  add     rsp, 20h
0x180005f29  pop     rbx
0x180005f2a  retn
```
