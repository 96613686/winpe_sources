# DumpKeySecurityInfo(HKEY__ *)

- ea: `0x18010937c`
- end: `0x18010951e`
- name: `?DumpKeySecurityInfo@@YAXPEAUHKEY__@@@Z`
- size: `418`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058b98`

## callees

- `0x18004f454`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x1800ad504`
- `0x1800eb920`
- `0x1801026fc`
- `0x18010937c`
- `0x180109524`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1801093ac`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1801093f0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1801093ac`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1801093f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801094f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801094f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1801094a2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1801094a2`

## string_xrefs

- `0x180109420`: `Failed getting key security dacl information`
- `0x1801094b2`: `Failed converting security descriptor to string`
- `0x1801094e1`: `  Key Security: {}`

## pseudocode

```c
void __fastcall DumpKeySecurityInfo(HKEY hKey)
{
  LSTATUS KeySecurity; // eax
  signed int v3; // ebx
  int v4; // edx
  int v5; // edx
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-40h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+30h] [rbp-30h] BYREF
  int v8[2]; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+48h] [rbp-18h] BYREF
  signed int v11; // [rsp+4Ch] [rbp-14h] BYREF
  ULONG v12; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  cbSecurityDescriptor = 0;
  if ( RegGetKeySecurity(hKey, 5u, 0, &cbSecurityDescriptor) == 122 )
  {
    pSecurityDescriptor = 0;
    Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(
      &pSecurityDescriptor,
      cbSecurityDescriptor);
    if ( pSecurityDescriptor )
    {
      KeySecurity = RegGetKeySecurity(hKey, 5u, pSecurityDescriptor, &cbSecurityDescriptor);
      v3 = KeySecurity;
      if ( KeySecurity > 0 )
        v3 = (unsigned __int16)KeySecurity | 0x80070000;
      if ( v3 >= 0 )
      {
        StringSecurityDescriptor = 0;
        v12 = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
               pSecurityDescriptor,
               1u,
               5u,
               &StringSecurityDescriptor,
               &v12) )
        {
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v5) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v5,
              1,
              (unsigned int)"  Key Security: {}",
              (__int64)&StringSecurityDescriptor);
          }
          LocalFree(StringSecurityDescriptor);
        }
        else
        {
          LogAdapter::TraceAtLevel<>(3, "Failed converting security descriptor to string");
        }
      }
      else
      {
        v11 = v3;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed getting key security dacl information");
          *(_QWORD *)v8 = &v11;
          LOBYTE(v4) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v4,
            3,
            (unsigned int)": {}",
            (__int64)v8);
        }
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x3A8,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)(unsigned int)v3,
          StringSecurityDescriptorLen);
      }
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pSecurityDescriptor);
  }
}

```

## disassembly

```asm
0x18010937c  mov     [rsp-8+arg_8], rbx
0x180109381  push    rbp
0x180109382  mov     rbp, rsp
0x180109385  sub     rsp, 60h
0x180109389  mov     rax, cs:__security_cookie
0x180109390  xor     rax, rsp
0x180109393  mov     [rbp+var_8], rax
0x180109397  xor     r8d, r8d; pSecurityDescriptor
0x18010939a  mov     [rbp+cbSecurityDescriptor], 0
0x1801093a1  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1801093a5  mov     rbx, rcx
0x1801093a8  lea     edx, [r8+5]; SecurityInformation
0x1801093ac  call    cs:__imp_RegGetKeySecurity
0x1801093b3  nop     dword ptr [rax+rax+00h]
0x1801093b8  cmp     eax, 7Ah ; 'z'
0x1801093bb  jnz     loc_180109506
0x1801093c1  mov     edx, [rbp+cbSecurityDescriptor]
0x1801093c4  lea     rcx, [rbp+pSecurityDescriptor]
0x1801093c8  mov     [rbp+pSecurityDescriptor], 0
0x1801093d0  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x1801093d5  cmp     [rbp+pSecurityDescriptor], 0
0x1801093da  jz      loc_1801094FD
0x1801093e0  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1801093e4  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1801093e8  mov     edx, 5; SecurityInformation
0x1801093ed  mov     rcx, rbx; hKey
0x1801093f0  call    cs:__imp_RegGetKeySecurity
0x1801093f7  nop     dword ptr [rax+rax+00h]
0x1801093fc  mov     ebx, eax
0x1801093fe  test    eax, eax
0x180109400  jle     short loc_18010940B
0x180109402  movzx   ebx, ax
0x180109405  or      ebx, 80070000h
0x18010940b  test    ebx, ebx
0x18010940d  jns     short loc_180109479
0x18010940f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180109416  mov     [rbp+var_14], ebx
0x180109419  test    rcx, rcx
0x18010941c  jz      short loc_18010945C
0x18010941e  xor     edx, edx
0x180109420  lea     r9, aFailedGettingK; "Failed getting key security dacl inform"...
0x180109427  lea     r8d, [rdx+3]
0x18010942b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180109430  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180109437  lea     rax, [rbp+var_14]
0x18010943b  mov     qword ptr [rbp+var_28], rax
0x18010943f  lea     r9, asc_1802EE7AC; ": {}"
0x180109446  lea     rax, [rbp+var_28]
0x18010944a  mov     r8d, 3
0x180109450  mov     dl, 1
0x180109452  mov     qword ptr [rsp+60h+StringSecurityDescriptorLen], rax; int
0x180109457  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010945c  mov     rcx, [rbp+8]; this
0x180109460  lea     r8, aOnecoreBaseCbs_80; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180109467  mov     r9d, ebx; char *
0x18010946a  mov     edx, 3A8h; void *
0x18010946f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180109474  jmp     loc_1801094FD
0x180109479  mov     rcx, [rbp+pSecurityDescriptor]; SecurityDescriptor
0x18010947d  lea     rax, [rbp+var_10]
0x180109481  mov     edx, 1; RequestedStringSDRevision
0x180109486  mov     [rbp+StringSecurityDescriptor], 0
0x18010948e  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180109492  mov     [rbp+var_10], 0
0x180109499  mov     qword ptr [rsp+60h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18010949e  lea     r8d, [rdx+4]; SecurityInformation
0x1801094a2  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1801094a9  nop     dword ptr [rax+rax+00h]
0x1801094ae  test    eax, eax
0x1801094b0  jnz     short loc_1801094C3
0x1801094b2  lea     rdx, aFailedConverti_6; "Failed converting security descriptor t"...
0x1801094b9  lea     ecx, [rax+3]
0x1801094bc  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801094c1  jmp     short loc_1801094FD
0x1801094c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801094ca  test    rcx, rcx
0x1801094cd  jz      short loc_1801094ED
0x1801094cf  mov     r8d, 1
0x1801094d5  lea     rax, [rbp+StringSecurityDescriptor]
0x1801094d9  mov     dl, r8b
0x1801094dc  mov     qword ptr [rsp+60h+StringSecurityDescriptorLen], rax
0x1801094e1  lea     r9, aKeySecurity; "  Key Security: {}"
0x1801094e8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801094ed  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x1801094f1  call    cs:__imp_LocalFree
0x1801094f8  nop     dword ptr [rax+rax+00h]
0x1801094fd  lea     rcx, [rbp+pSecurityDescriptor]
0x180109501  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x180109506  mov     rcx, [rbp+var_8]
0x18010950a  xor     rcx, rsp; StackCookie
0x18010950d  call    __security_check_cookie
0x180109512  mov     rbx, [rsp+60h+arg_8]
0x180109517  add     rsp, 60h
0x18010951b  pop     rbp
0x18010951c  retn
```
