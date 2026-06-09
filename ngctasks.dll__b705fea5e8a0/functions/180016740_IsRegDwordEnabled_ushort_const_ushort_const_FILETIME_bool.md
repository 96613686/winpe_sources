# IsRegDwordEnabled(ushort const *,ushort const *,_FILETIME *,bool *)

- ea: `0x180016740`
- end: `0x180016847`
- name: `?IsRegDwordEnabled@@YAXPEBG0PEAU_FILETIME@@PEA_N@Z`
- size: `263`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016b24`

## callees

- `0x180008c74`
- `0x18000ef9c`
- `0x180016740`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800167d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800167d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001680f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001680f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016778`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016778`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016786`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016786`

## string_xrefs

- `0x1800167c6`: `System\CurrentControlSet\Services\TPM\WMI`

## pseudocode

```c
void __fastcall IsRegDwordEnabled(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _FILETIME *a3,
        bool *a4)
{
  bool v5; // bl
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  const unsigned __int16 *Data; // [rsp+60h] [rbp+20h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp+28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+30h] BYREF

  Data = a1;
  SystemTimeAsFileTime = 0;
  FileTime2 = (FILETIME)(qword_180031708 + 3000000000LL);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) > 0 )
  {
    qword_180031708 = (__int64)SystemTimeAsFileTime;
    v5 = 0;
    hKey[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 0, 0x20019u, hKey) )
    {
      SystemTimeAsFileTime.dwLowDateTime = 0;
      LODWORD(Data) = 0;
      FileTime2.dwLowDateTime = 4;
      if ( !RegQueryValueExW(
              hKey[0],
              L"IsActiveZeroExhaust",
              0,
              (LPDWORD)&SystemTimeAsFileTime,
              (LPBYTE)&Data,
              (LPDWORD)&FileTime2)
        && SystemTimeAsFileTime.dwLowDateTime == 4
        && FileTime2.dwLowDateTime == 4 )
      {
        v5 = (_DWORD)Data != 0;
      }
    }
    *a4 = v5;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  }
}

```

## disassembly

```asm
0x180016740  mov     qword ptr [rsp-18h+SystemTimeAsFileTime.dwLowDateTime], r8
0x180016745  mov     qword ptr [rsp-18h+FileTime2.dwLowDateTime], rdx
0x18001674a  mov     [rsp-18h+Data], rcx
0x18001674f  push    rbp
0x180016750  push    rbx
0x180016751  push    rdi
0x180016752  mov     rbp, rsp
0x180016755  sub     rsp, 40h
0x180016759  mov     rdi, r9
0x18001675c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180016764  mov     ecx, 0B2D05E00h
0x180016769  add     rcx, cs:qword_180031708
0x180016770  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rcx
0x180016774  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016778  call    cs:__imp_GetSystemTimeAsFileTime
0x18001677e  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180016782  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180016786  call    cs:__imp_CompareFileTime
0x18001678c  test    eax, eax
0x18001678e  jle     loc_18001683F
0x180016794  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180016798  mov     cs:qword_180031708, rax
0x18001679f  xor     bl, bl
0x1800167a1  mov     [rbp+hKey], 0
0x1800167a9  xor     edx, edx
0x1800167ab  lea     rcx, [rbp+hKey]
0x1800167af  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800167b4  lea     rax, [rbp+hKey]
0x1800167b8  mov     [rsp+40h+phkResult], rax; phkResult
0x1800167bd  mov     r9d, 20019h; samDesired
0x1800167c3  xor     r8d, r8d; ulOptions
0x1800167c6  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\TP"...
0x1800167cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800167d4  call    cs:__imp_RegOpenKeyExW
0x1800167da  test    eax, eax
0x1800167dc  jnz     short loc_180016834
0x1800167de  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], eax
0x1800167e1  mov     dword ptr [rbp+Data], eax
0x1800167e4  mov     [rbp+FileTime2.dwLowDateTime], 4
0x1800167eb  lea     rax, [rbp+FileTime2]
0x1800167ef  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800167f4  lea     rax, [rbp+Data]
0x1800167f8  mov     [rsp+40h+phkResult], rax; lpData
0x1800167fd  lea     r9, [rbp+SystemTimeAsFileTime]; lpType
0x180016801  xor     r8d, r8d; lpReserved
0x180016804  lea     rdx, aIsactivezeroex; "IsActiveZeroExhaust"
0x18001680b  mov     rcx, [rbp+hKey]; hKey
0x18001680f  call    cs:__imp_RegQueryValueExW
0x180016815  test    eax, eax
0x180016817  jnz     short loc_180016834
0x180016819  cmp     [rbp+SystemTimeAsFileTime.dwLowDateTime], 4
0x18001681d  jnz     short loc_180016834
0x18001681f  cmp     [rbp+FileTime2.dwLowDateTime], 4
0x180016823  jnz     short loc_180016834
0x180016825  movzx   ebx, bl
0x180016828  mov     eax, 1
0x18001682d  cmp     dword ptr [rbp+Data], 0
0x180016831  cmovnz  ebx, eax
0x180016834  mov     [rdi], bl
0x180016836  lea     rcx, [rbp+hKey]
0x18001683a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001683f  add     rsp, 40h
0x180016843  pop     rdi
0x180016844  pop     rbx
0x180016845  pop     rbp
0x180016846  retn
```
