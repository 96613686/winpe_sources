# cdp::CreateServiceReadyMutex(void)

- ea: `0x1800f55d8`
- end: `0x1800f574d`
- name: `?CreateServiceReadyMutex@cdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18011e87c`

## callees

- `0x18000b724`
- `0x1800a29a0`
- `0x1800f55d8`
- `0x180114ab4`
- `0x18012d5cc`
- `0x180197cc4`
- `0x1801f6fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f56ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f56dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f56ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f56dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5726`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5726`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800f5675`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800f5675`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f562e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f562e`

## string_xrefs

- `0x1800f5710`: `.\userservicenotificationclient.cpp`
- `0x1800f56d3`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"Failed to create CDPUserSvc ready mutex"}`
- `0x1800f5704`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"Failed to create CDPUserSvc ready mutex sddl"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall cdp::CreateServiceReadyMutex(_QWORD *a1)
{
  WCHAR *RelativeUserServiceMutexName; // rax
  signed int LastError; // eax
  int v4; // ecx
  HANDLE *v5; // rax
  HANDLE *v6; // r8
  const char *v7; // rdx
  signed int v8; // eax
  int v10; // [rsp+30h] [rbp-19h] BYREF
  HANDLE v11; // [rsp+38h] [rbp-11h] BYREF
  int v12; // [rsp+40h] [rbp-9h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-1h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+50h] [rbp+7h] BYREF
  _QWORD *v15; // [rsp+68h] [rbp+1Fh]
  WCHAR v16[16]; // [rsp+70h] [rbp+27h] BYREF

  v15 = a1;
  *a1 = 0;
  v12 = 1;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;0x00100000;;;AU)(A;;0x00100000;;;WD)(A;;0x00100000;;;S-1-15-2-1)(A;;GA;;;IU)(A;;GA;;;SY)(A;;GA;;;LS)(A;;G"
          "A;;;S-1-5-21-2702878673-795188819-444038987-1030)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    MutexAttributes.nLength = 24;
    MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
    MutexAttributes.bInheritHandle = 0;
    RelativeUserServiceMutexName = cdp::GetRelativeUserServiceMutexName(v16, (void *)0xFFFFFFFFFFFFFFFCLL);
    if ( *((_QWORD *)RelativeUserServiceMutexName + 3) > 7u )
      RelativeUserServiceMutexName = *(WCHAR **)RelativeUserServiceMutexName;
    v11 = CreateMutexW(&MutexAttributes, 0, RelativeUserServiceMutexName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1,
      &v11);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    std::wstring::_Tidy_deallocate(v16);
    if ( ((*a1 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v11) = LastError;
      if ( LastError < 0 )
      {
        v10 = 187;
        v5 = (HANDLE *)&v10;
        v6 = &v11;
        v7 = "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failed to create CDPUserSvc ready mutex\"}";
LABEL_13:
        Log<long &,char const (&)[36],int>(
          v4,
          (_DWORD)v7,
          (_DWORD)v6,
          (unsigned int)".\\userservicenotificationclient.cpp",
          (__int64)v5);
      }
    }
  }
  else
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v10 = v8;
    if ( v8 < 0 )
    {
      LODWORD(v11) = 192;
      v5 = &v11;
      v6 = (HANDLE *)&v10;
      v7 = "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failed to create CDPUserSvc ready mutex sddl\"}";
      goto LABEL_13;
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return a1;
}

```

## disassembly

```asm
0x1800f55d8  mov     [rsp-8+arg_8], rbx
0x1800f55dd  push    rbp
0x1800f55de  lea     rbp, [rsp-57h]
0x1800f55e3  sub     rsp, 0A0h
0x1800f55ea  mov     rax, cs:__security_cookie
0x1800f55f1  xor     rax, rsp
0x1800f55f4  mov     [rbp+57h+var_10], rax
0x1800f55f8  mov     rbx, rcx
0x1800f55fb  mov     [rbp+57h+var_38], rcx
0x1800f55ff  mov     [rbp+57h+var_60], 0
0x1800f5606  mov     qword ptr [rcx], 0
0x1800f560d  mov     [rbp+57h+var_60], 1
0x1800f5614  mov     [rbp+57h+SecurityDescriptor], 0
0x1800f561c  xor     r9d, r9d; SecurityDescriptorSize
0x1800f561f  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800f5623  lea     edx, [r9+1]; StringSDRevision
0x1800f5627  lea     rcx, aDA0x00100000Au; "D:(A;;0x00100000;;;AU)(A;;0x00100000;;;"...
0x1800f562e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f5634  test    eax, eax
0x1800f5636  jz      loc_1800F56DC
0x1800f563c  mov     [rbp+57h+MutexAttributes.nLength], 18h
0x1800f5643  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800f5647  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x1800f564b  mov     [rbp+57h+MutexAttributes.bInheritHandle], 0
0x1800f5652  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x1800f5659  lea     rcx, [rbp+57h+var_30]
0x1800f565d  call    ?GetRelativeUserServiceMutexName@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; cdp::GetRelativeUserServiceMutexName(void *)
0x1800f5662  cmp     qword ptr [rax+18h], 7
0x1800f5667  jbe     short loc_1800F566C
0x1800f5669  mov     rax, [rax]
0x1800f566c  mov     r8, rax; lpName
0x1800f566f  xor     edx, edx; bInitialOwner
0x1800f5671  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x1800f5675  call    cs:__imp_CreateMutexW
0x1800f567b  mov     [rbp+57h+var_68], rax
0x1800f567f  lea     rdx, [rbp+57h+var_68]
0x1800f5683  mov     rcx, rbx
0x1800f5686  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800f568b  lea     rcx, [rbp+57h+var_68]
0x1800f568f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f5694  lea     rcx, [rbp+57h+var_30]
0x1800f5698  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f569d  mov     rax, [rbx]
0x1800f56a0  inc     rax
0x1800f56a3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800f56a9  jnz     short loc_1800F571D
0x1800f56ab  call    cs:__imp_GetLastError
0x1800f56b1  test    eax, eax
0x1800f56b3  jle     short loc_1800F56BD
0x1800f56b5  movzx   eax, ax
0x1800f56b8  or      eax, 80070000h
0x1800f56bd  mov     dword ptr [rbp+57h+var_68], eax
0x1800f56c0  test    eax, eax
0x1800f56c2  jns     short loc_1800F571D
0x1800f56c4  mov     [rbp+57h+var_70], 0BBh
0x1800f56cb  lea     rax, [rbp+57h+var_70]
0x1800f56cf  lea     r8, [rbp+57h+var_68]
0x1800f56d3  lea     rdx, aHr0x08xFileSLi_17; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800f56da  jmp     short loc_1800F570B
0x1800f56dc  call    cs:__imp_GetLastError
0x1800f56e2  test    eax, eax
0x1800f56e4  jle     short loc_1800F56EE
0x1800f56e6  movzx   eax, ax
0x1800f56e9  or      eax, 80070000h
0x1800f56ee  mov     [rbp+57h+var_70], eax
0x1800f56f1  test    eax, eax
0x1800f56f3  jns     short loc_1800F571D
0x1800f56f5  mov     dword ptr [rbp+57h+var_68], 0C0h
0x1800f56fc  lea     rax, [rbp+57h+var_68]
0x1800f5700  lea     r8, [rbp+57h+var_70]
0x1800f5704  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800f570b  mov     [rsp+0A0h+var_80], rax
0x1800f5710  lea     r9, aUserservicenot; ".\\userservicenotificationclient.cpp"
0x1800f5717  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800f571c  nop
0x1800f571d  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800f5721  test    rcx, rcx
0x1800f5724  jz      short loc_1800F572C
0x1800f5726  call    cs:__imp_LocalFree
0x1800f572c  mov     rax, rbx
0x1800f572f  mov     rcx, [rbp+57h+var_10]
0x1800f5733  xor     rcx, rsp; StackCookie
0x1800f5736  call    __security_check_cookie
0x1800f573b  mov     rbx, [rsp+0A0h+arg_8]
0x1800f5743  add     rsp, 0A0h
0x1800f574a  pop     rbp
0x1800f574b  retn
```
