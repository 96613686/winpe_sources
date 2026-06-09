# CDriverMap::GetDriverPathFromServiceName(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180044bcc`
- end: `0x180044f19`
- name: `?GetDriverPathFromServiceName@CDriverMap@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800438cc`
- `0x180044940`
- `0x18005d170`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x18000fa50`
- `0x180016440`
- `0x180044bcc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044c7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044d05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044c7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044d05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044e2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044e2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044e3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044e3c`

## string_xrefs

- `0x180044e23`: `ImagePath`
- `0x180044cab`: `Software\Microsoft\Windows Nt\CurrentVersion\WUDF\Services`
- `0x180044c25`: `System\CurrentControlSet\Services`
- `0x180044d36`: `CDriverMap::GetDriverPathFromServiceName`
- `0x180044d62`: `CDriverMap::GetDriverPathFromServiceName`
- `0x180044e6b`: `CDriverMap::GetDriverPathFromServiceName`
- `0x180044e9a`: `CDriverMap::GetDriverPathFromServiceName`
- `0x180044d29`: `0x%08x Failed to open service key: %ws`
- `0x180044d85`: `0x%08x Failed to open service key: %ws`
- `0x180044db1`: `0x%08x Failed to open service key: %ws`
- `0x180044e5e`: `0x%08x Failed to get ImagePath for service (%ws)`
- `0x180044ebd`: `0x%08x Failed to get ImagePath for service (%ws)`
- `0x180044eed`: `0x%08x Failed to get ImagePath for service (%ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDriverMap::GetDriverPathFromServiceName(void *a1, void *Src)
{
  const WCHAR *v4; // rdx
  LPCWSTR *v5; // rcx
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  FILE *v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-278h]
  PHKEY phkResulta; // [rsp+20h] [rbp-278h]
  HKEY hKey; // [rsp+38h] [rbp-260h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-258h] BYREF
  DWORD Type; // [rsp+44h] [rbp-254h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-250h] BYREF
  __int64 v31; // [rsp+58h] [rbp-240h]
  unsigned __int64 v32; // [rsp+60h] [rbp-238h]
  BYTE Data[528]; // [rsp+70h] [rbp-228h] BYREF

  *(_OWORD *)lpSubKey = 0;
  v31 = 0;
  v32 = 7;
  LOWORD(lpSubKey[0]) = 0;
  cbData = 520;
  hKey = 0;
  try
  {
    std::wstring::append(lpSubKey, L"System\\CurrentControlSet\\Services");
    std::wstring::append(lpSubKey, (void *)L"\\");
    std::wstring::append(lpSubKey, a1);
  }
  catch ( std::bad_alloc )
  {
    AslLogCallPrintf(2, "CDriverMap::GetDriverPathFromServiceName", 2315, "Out of memory");
    if ( EnableDevInvStdErrLog )
    {
      v22 = o___acrt_iob_func_0(2u);
      fprintf(v22, "Error: %s, %u: ", "CDriverMap::GetDriverPathFromServiceName", 2315);
      v23 = o___acrt_iob_func_0(2u);
      fprintf(v23, "Out of memory");
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Out of memory");
    v8 = -2147024888;
    goto LABEL_17;
  }
  v4 = (const WCHAR *)lpSubKey;
  if ( v32 > 7 )
    v4 = lpSubKey[0];
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey) )
    goto LABEL_18;
  v5 = lpSubKey;
  if ( v32 > 7 )
    v5 = (LPCWSTR *)lpSubKey[0];
  v31 = 0;
  *(_WORD *)v5 = 0;
  try
  {
    std::wstring::append(lpSubKey, (void *)L"Software\\Microsoft\\Windows Nt\\CurrentVersion\\WUDF\\Services");
    std::wstring::append(lpSubKey, (void *)L"\\");
    std::wstring::append(lpSubKey, a1);
  }
  catch ( std::bad_alloc )
  {
    AslLogCallPrintf(2, "CDriverMap::GetDriverPathFromServiceName", 2341, "Out of memory");
    if ( EnableDevInvStdErrLog )
    {
      v16 = o___acrt_iob_func_0(2u);
      fprintf(v16, "Error: %s, %u: ", "CDriverMap::GetDriverPathFromServiceName", 2341);
      v17 = o___acrt_iob_func_0(2u);
      fprintf(v17, "Out of memory");
      v18 = o___acrt_iob_func_0(2u);
      fprintf(v18, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Out of memory");
    v8 = -2147024888;
    goto LABEL_17;
  }
  v6 = (const WCHAR *)lpSubKey;
  if ( v32 > 7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    LODWORD(phkResult) = v8;
    AslLogCallPrintf(
      2,
      "CDriverMap::GetDriverPathFromServiceName",
      2356,
      "0x%08x Failed to open service key: %ws",
      phkResult,
      a1);
    if ( EnableDevInvStdErrLog )
    {
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "Warning: %s, %u: ", "CDriverMap::GetDriverPathFromServiceName", 2356);
      v10 = o___acrt_iob_func_0(2u);
      fprintf(v10, "0x%08x Failed to open service key: %ws", v8, a1);
      v11 = o___acrt_iob_func_0(2u);
      fprintf(v11, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(50331648, "0x%08x Failed to open service key: %ws", v8, a1);
  }
  else
  {
LABEL_18:
    Type = 1;
    v8 = RegQueryValueExW(hKey, L"ImagePath", 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
    if ( v8 )
    {
      if ( (int)v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      LODWORD(phkResulta) = v8;
      AslLogCallPrintf(
        3,
        "CDriverMap::GetDriverPathFromServiceName",
        2382,
        "0x%08x Failed to get ImagePath for service (%ws)",
        phkResulta,
        a1);
      if ( EnableDevInvStdErrLog )
      {
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "Info: %s, %u: ", "CDriverMap::GetDriverPathFromServiceName", 2382);
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "0x%08x Failed to get ImagePath for service (%ws)", v8, a1);
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x4000000, "0x%08x Failed to get ImagePath for service (%ws)", v8, a1);
    }
    else
    {
      try
      {
        std::wstring::append(Src, Data);
      }
      catch ( std::bad_alloc )
      {
        AslLogCallPrintf(2, "CDriverMap::GetDriverPathFromServiceName", 2393, "Out of memory");
        if ( EnableDevInvStdErrLog )
        {
          v19 = o___acrt_iob_func_0(2u);
          fprintf(v19, "Error: %s, %u: ", "CDriverMap::GetDriverPathFromServiceName", 2393);
          v20 = o___acrt_iob_func_0(2u);
          fprintf(v20, "Out of memory");
          v21 = o___acrt_iob_func_0(2u);
          fprintf(v21, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Out of memory");
        v8 = -2147024888;
        goto LABEL_17;
      }
      v8 = 0;
    }
  }
LABEL_17:
  std::wstring::~wstring(lpSubKey);
  return v8;
}

```

## disassembly

```asm
0x180044bcc  mov     [rsp+arg_10], rbx
0x180044bd1  mov     [rsp+arg_18], rsi
0x180044bd6  push    rdi
0x180044bd7  sub     rsp, 290h
0x180044bde  mov     rax, cs:__security_cookie
0x180044be5  xor     rax, rsp
0x180044be8  mov     [rsp+298h+var_18], rax
0x180044bf0  mov     rsi, rdx
0x180044bf3  mov     rdi, rcx
0x180044bf6  xorps   xmm0, xmm0
0x180044bf9  movups  xmmword ptr [rsp+298h+lpSubKey], xmm0
0x180044bfe  mov     [rsp+298h+var_240], 0
0x180044c07  mov     ebx, 7
0x180044c0c  mov     [rsp+298h+var_238], rbx
0x180044c11  xor     eax, eax
0x180044c13  mov     word ptr [rsp+298h+lpSubKey], ax
0x180044c18  mov     [rsp+298h+cbData], 208h
0x180044c20  mov     [rsp+298h+hKey], rax
0x180044c25  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services"
0x180044c2c  lea     rcx, [rsp+298h+lpSubKey]; Src
0x180044c31  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044c36  lea     rdx, SubBlock; "\\"
0x180044c3d  lea     rcx, [rsp+298h+lpSubKey]; Src
0x180044c42  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044c47  mov     rdx, rdi; void *
0x180044c4a  lea     rcx, [rsp+298h+lpSubKey]; Src
0x180044c4f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044c54  nop
0x180044c55  lea     rdx, [rsp+298h+lpSubKey]
0x180044c5a  cmp     [rsp+298h+var_238], rbx
0x180044c5f  cmova   rdx, [rsp+298h+lpSubKey]; lpSubKey
0x180044c65  lea     rax, [rsp+298h+hKey]
0x180044c6a  mov     [rsp+298h+phkResult], rax; phkResult
0x180044c6f  mov     r9d, 20019h; samDesired
0x180044c75  xor     r8d, r8d; ulOptions
0x180044c78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044c7f  call    cs:__imp_RegOpenKeyExW
0x180044c85  test    eax, eax
0x180044c87  jz      loc_180044DFF
0x180044c8d  lea     rcx, [rsp+298h+lpSubKey]
0x180044c92  cmp     [rsp+298h+var_238], rbx
0x180044c97  cmova   rcx, [rsp+298h+lpSubKey]
0x180044c9d  mov     [rsp+298h+var_240], 0
0x180044ca6  xor     eax, eax
0x180044ca8  mov     [rcx], ax
0x180044cab  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Nt\\Curren"...
0x180044cb2  lea     rcx, [rsp+298h+lpSubKey]; Src
0x180044cb7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044cbc  lea     rdx, SubBlock; "\\"
0x180044cc3  lea     rcx, [rsp+298h+lpSubKey]; Src
0x180044cc8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044ccd  mov     rdx, rdi; void *
0x180044cd0  lea     rcx, [rsp+298h+lpSubKey]; Src
0x180044cd5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044cda  nop
0x180044cdb  lea     rdx, [rsp+298h+lpSubKey]
0x180044ce0  cmp     [rsp+298h+var_238], rbx
0x180044ce5  cmova   rdx, [rsp+298h+lpSubKey]; lpSubKey
0x180044ceb  lea     rax, [rsp+298h+hKey]
0x180044cf0  mov     [rsp+298h+phkResult], rax; phkResult
0x180044cf5  mov     r9d, 20019h; samDesired
0x180044cfb  xor     r8d, r8d; ulOptions
0x180044cfe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044d05  call    cs:__imp_RegOpenKeyExW
0x180044d0b  mov     ebx, eax
0x180044d0d  test    eax, eax
0x180044d0f  jz      loc_180044DFF
0x180044d15  jle     short loc_180044D20
0x180044d17  movzx   ebx, ax
0x180044d1a  or      ebx, 80070000h
0x180044d20  mov     [rsp+298h+lpcbData], rdi
0x180044d25  mov     dword ptr [rsp+298h+phkResult], ebx
0x180044d29  lea     r9, a0x08xFailedToO_2; "0x%08x Failed to open service key: %ws"
0x180044d30  mov     r8d, 934h
0x180044d36  lea     rdx, aCdrivermapGetd_1; "CDriverMap::GetDriverPathFromServiceNam"...
0x180044d3d  mov     esi, 2
0x180044d42  mov     ecx, esi
0x180044d44  call    AslLogCallPrintf
0x180044d49  cmp     cs:EnableDevInvStdErrLog, 0
0x180044d50  jz      short loc_180044DA7
0x180044d52  mov     ecx, esi; Ix
0x180044d54  call    _o___acrt_iob_func_0
0x180044d59  mov     rcx, rax; Stream
0x180044d5c  mov     r9d, 934h
0x180044d62  lea     r8, aCdrivermapGetd_1; "CDriverMap::GetDriverPathFromServiceNam"...
0x180044d69  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180044d70  call    fprintf
0x180044d75  mov     ecx, esi; Ix
0x180044d77  call    _o___acrt_iob_func_0
0x180044d7c  mov     rcx, rax; Stream
0x180044d7f  mov     r9, rdi
0x180044d82  mov     r8d, ebx
0x180044d85  lea     rdx, a0x08xFailedToO_2; "0x%08x Failed to open service key: %ws"
0x180044d8c  call    fprintf
0x180044d91  mov     ecx, esi; Ix
0x180044d93  call    _o___acrt_iob_func_0
0x180044d98  mov     rcx, rax; Stream
0x180044d9b  lea     rdx, asc_18011EAD8; "\n"
0x180044da2  call    fprintf
0x180044da7  cmp     cs:g_DeviceMapLogFunction, 0
0x180044daf  jz      short loc_180044DCE
0x180044db1  lea     rdx, a0x08xFailedToO_2; "0x%08x Failed to open service key: %ws"
0x180044db8  mov     ecx, 3000000h
0x180044dbd  mov     r8d, ebx
0x180044dc0  mov     r9, rdi
0x180044dc3  call    TraceMessageCallback
0x180044dc8  jmp     short loc_180044DCE
0x180044dca  mov     ebx, [rsp+298h+var_268]
0x180044dce  lea     rcx, [rsp+298h+lpSubKey]; void *
0x180044dd3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044dd8  mov     eax, ebx
0x180044dda  mov     rcx, [rsp+298h+var_18]
0x180044de2  xor     rcx, rsp; StackCookie
0x180044de5  call    __security_check_cookie
0x180044dea  lea     r11, [rsp+298h+var_8]
0x180044df2  mov     rbx, [r11+20h]
0x180044df6  mov     rsi, [r11+28h]
0x180044dfa  mov     rsp, r11
0x180044dfd  pop     rdi
0x180044dfe  retn
0x180044dff  mov     [rsp+298h+Type], 1
0x180044e07  lea     rax, [rsp+298h+cbData]
0x180044e0c  mov     [rsp+298h+lpcbData], rax; lpcbData
0x180044e11  lea     rax, [rsp+298h+Data]
0x180044e16  mov     [rsp+298h+phkResult], rax; lpData
0x180044e1b  lea     r9, [rsp+298h+Type]; lpType
0x180044e20  xor     r8d, r8d; lpReserved
0x180044e23  lea     rdx, aImagepath; "ImagePath"
0x180044e2a  mov     rcx, [rsp+298h+hKey]; hKey
0x180044e2f  call    cs:__imp_RegQueryValueExW
0x180044e35  mov     ebx, eax
0x180044e37  mov     rcx, [rsp+298h+hKey]; hKey
0x180044e3c  call    cs:__imp_RegCloseKey
0x180044e42  test    ebx, ebx
0x180044e44  jz      loc_180044EFE
0x180044e4a  jle     short loc_180044E55
0x180044e4c  movzx   ebx, bx
0x180044e4f  or      ebx, 80070000h
0x180044e55  mov     [rsp+298h+lpcbData], rdi
0x180044e5a  mov     dword ptr [rsp+298h+phkResult], ebx
0x180044e5e  lea     r9, a0x08xFailedToG_3; "0x%08x Failed to get ImagePath for serv"...
0x180044e65  mov     r8d, 94Eh
0x180044e6b  lea     rdx, aCdrivermapGetd_1; "CDriverMap::GetDriverPathFromServiceNam"...
0x180044e72  mov     ecx, 3
0x180044e77  call    AslLogCallPrintf
0x180044e7c  cmp     cs:EnableDevInvStdErrLog, 0
0x180044e83  jz      short loc_180044EDF
0x180044e85  mov     esi, 2
0x180044e8a  mov     ecx, esi; Ix
0x180044e8c  call    _o___acrt_iob_func_0
0x180044e91  mov     rcx, rax; Stream
0x180044e94  mov     r9d, 94Eh
0x180044e9a  lea     r8, aCdrivermapGetd_1; "CDriverMap::GetDriverPathFromServiceNam"...
0x180044ea1  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180044ea8  call    fprintf
0x180044ead  mov     ecx, esi; Ix
0x180044eaf  call    _o___acrt_iob_func_0
0x180044eb4  mov     rcx, rax; Stream
0x180044eb7  mov     r9, rdi
0x180044eba  mov     r8d, ebx
0x180044ebd  lea     rdx, a0x08xFailedToG_3; "0x%08x Failed to get ImagePath for serv"...
0x180044ec4  call    fprintf
0x180044ec9  mov     ecx, esi; Ix
0x180044ecb  call    _o___acrt_iob_func_0
0x180044ed0  mov     rcx, rax; Stream
0x180044ed3  lea     rdx, asc_18011EAD8; "\n"
0x180044eda  call    fprintf
0x180044edf  cmp     cs:g_DeviceMapLogFunction, 0
0x180044ee7  jz      loc_180044DCE
0x180044eed  lea     rdx, a0x08xFailedToG_3; "0x%08x Failed to get ImagePath for serv"...
0x180044ef4  mov     ecx, 4000000h
0x180044ef9  jmp     loc_180044DBD
0x180044efe  lea     rdx, [rsp+298h+Data]; void *
0x180044f03  mov     rcx, rsi; Src
0x180044f06  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180044f0b  nop
0x180044f0c  xor     ebx, ebx
0x180044f0e  jmp     loc_180044DCE
0x180044f13  jmp     loc_180044DCA
```
