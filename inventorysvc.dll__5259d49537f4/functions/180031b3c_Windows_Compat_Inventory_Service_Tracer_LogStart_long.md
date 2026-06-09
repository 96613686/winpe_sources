# Windows::Compat::Inventory::Service::Tracer::LogStart(long)

- ea: `0x180031b3c`
- end: `0x180031d58`
- name: `?LogStart@Tracer@Service@Inventory@Compat@Windows@@IEAAJJ@Z`
- size: `540`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::Service::Tracer *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c6d60`
- `0x1800c9ec0`
- `0x1800cd050`
- `0x1800cd6e0`

## callees

- `0x1800152d0`
- `0x180031b3c`
- `0x180031ebc`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031c11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bfe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031ba5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031c61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031ba5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031be9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031c09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031c81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031be9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031c09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031c81`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031cc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031d29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031cc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031d29`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031c93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031c93`

## string_xrefs

- `0x180031b97`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Tracers`
- `0x180031bc2`: `Windows::Compat::Inventory::Service::Tracer::LogStart`
- `0x180031ce1`: `Windows::Compat::Inventory::Service::Tracer::LogStart`
- `0x180031bbb`: `RegCreateKeyExW failed [%d]`
- `0x180031cd6`: `RegSetValueExW failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::Service::Tracer::LogStart(
        Windows::Compat::Inventory::Service::Tracer *this,
        int a2)
{
  HKEY *phkResult; // rdi
  int Key; // ebx
  __int64 v5; // r8
  HKEY v7; // r14
  DWORD LastError; // ebx
  const WCHAR *v9; // rax
  __int64 v10; // r8
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  int Data; // [rsp+88h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp+40h] BYREF

  Data = a2;
  phkResult = (HKEY *)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    hKey = 0;
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Tracers",
            0,
            0,
            0,
            0x2001Fu,
            0,
            &hKey,
            0);
    if ( Key )
    {
      v5 = 26;
LABEL_4:
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::Tracer::LogStart",
        v5,
        "RegCreateKeyExW failed [%d]",
        Key);
      if ( Key > 0 )
        Key = (unsigned __int16)Key | 0x80070000;
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)Key;
    }
    v7 = *phkResult;
    if ( *phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    *phkResult = 0;
    v9 = (const WCHAR *)(*(__int64 (__fastcall **)(Windows::Compat::Inventory::Service::Tracer *))(*(_QWORD *)this + 48LL))(this);
    Key = RegCreateKeyExW(hKey, v9, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    if ( Key )
    {
      v5 = 33;
      goto LABEL_4;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)this + 1) = SystemTimeAsFileTime;
  Key = RegSetValueExW(*phkResult, L"StartTime", 0, 0xBu, (const BYTE *)this + 8, 8u);
  if ( Key )
  {
    v10 = 50;
    goto LABEL_17;
  }
  Key = RegSetValueExW(*phkResult, L"Result", 0, 4u, (const BYTE *)&Data, 4u);
  if ( Key )
  {
    v10 = 57;
LABEL_17:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::Tracer::LogStart", v10, "RegSetValueExW failed [%d]", Key);
    if ( Key > 0 )
      return (unsigned __int16)Key | 0x80070000;
    return (unsigned int)Key;
  }
  Windows::Compat::Inventory::Service::Tracer::SendRunTelemetry(this, Data, 0);
  return 0;
}

```

## disassembly

```asm
0x180031b3c  mov     [rsp-28h+Data], edx
0x180031b40  push    rbp
0x180031b41  push    rbx
0x180031b42  push    rsi
0x180031b43  push    rdi
0x180031b44  push    r14
0x180031b46  mov     rbp, rsp
0x180031b49  sub     rsp, 50h
0x180031b4d  mov     rsi, rcx
0x180031b50  lea     rdi, [rcx+10h]
0x180031b54  cmp     qword ptr [rdi], 0
0x180031b58  jnz     loc_180031C87
0x180031b5e  mov     [rbp+hKey], 0
0x180031b66  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180031b6f  lea     rax, [rbp+hKey]
0x180031b73  mov     [rsp+50h+phkResult], rax; phkResult
0x180031b78  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180031b81  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180031b89  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180031b91  xor     r9d, r9d; lpClass
0x180031b94  xor     r8d, r8d; Reserved
0x180031b97  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180031b9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031ba5  call    cs:__imp_RegCreateKeyExW
0x180031bab  mov     ebx, eax
0x180031bad  test    eax, eax
0x180031baf  jz      short loc_180031BF6
0x180031bb1  mov     r8d, 1Ah
0x180031bb7  mov     [rsp+50h+dwOptions], ebx
0x180031bbb  lea     r9, aRegcreatekeyex; "RegCreateKeyExW failed [%d]"
0x180031bc2  lea     rdx, aWindowsCompatI_74; "Windows::Compat::Inventory::Service::Tr"...
0x180031bc9  mov     ecx, 1
0x180031bce  call    AslLogCallPrintf
0x180031bd3  test    ebx, ebx
0x180031bd5  jle     short loc_180031BE0
0x180031bd7  movzx   ebx, bx
0x180031bda  or      ebx, 80070000h
0x180031be0  mov     rcx, [rbp+hKey]; hKey
0x180031be4  test    rcx, rcx
0x180031be7  jz      short loc_180031BEF
0x180031be9  call    cs:__imp_RegCloseKey
0x180031bef  mov     eax, ebx
0x180031bf1  jmp     loc_180031D4D
0x180031bf6  mov     r14, [rdi]
0x180031bf9  test    r14, r14
0x180031bfc  jz      short loc_180031C17
0x180031bfe  call    cs:__imp_GetLastError
0x180031c04  mov     ebx, eax
0x180031c06  mov     rcx, r14; hKey
0x180031c09  call    cs:__imp_RegCloseKey
0x180031c0f  mov     ecx, ebx; dwErrCode
0x180031c11  call    cs:__imp_SetLastError
0x180031c17  mov     qword ptr [rdi], 0
0x180031c1e  mov     rax, [rsi]
0x180031c21  mov     rcx, rsi
0x180031c24  mov     rax, [rax+30h]
0x180031c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c2d  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180031c36  mov     [rsp+50h+phkResult], rdi; phkResult
0x180031c3b  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180031c44  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180031c4c  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180031c54  xor     r9d, r9d; lpClass
0x180031c57  xor     r8d, r8d; Reserved
0x180031c5a  mov     rdx, rax; lpSubKey
0x180031c5d  mov     rcx, [rbp+hKey]; hKey
0x180031c61  call    cs:__imp_RegCreateKeyExW
0x180031c67  mov     ebx, eax
0x180031c69  test    eax, eax
0x180031c6b  jz      short loc_180031C78
0x180031c6d  mov     r8d, 21h ; '!'
0x180031c73  jmp     loc_180031BB7
0x180031c78  mov     rcx, [rbp+hKey]; hKey
0x180031c7c  test    rcx, rcx
0x180031c7f  jz      short loc_180031C87
0x180031c81  call    cs:__imp_RegCloseKey
0x180031c87  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180031c8f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180031c93  call    cs:__imp_GetSystemTimeAsFileTime
0x180031c99  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180031c9d  lea     rcx, [rsi+8]
0x180031ca1  mov     [rcx], rax
0x180031ca4  mov     [rsp+50h+samDesired], 8; cbData
0x180031cac  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x180031cb1  mov     r9d, 0Bh; dwType
0x180031cb7  xor     r8d, r8d; Reserved
0x180031cba  lea     rdx, aStarttime; "StartTime"
0x180031cc1  mov     rcx, [rdi]; hKey
0x180031cc4  call    cs:__imp_RegSetValueExW
0x180031cca  mov     ebx, eax
0x180031ccc  test    eax, eax
0x180031cce  jz      short loc_180031D08
0x180031cd0  mov     r8d, 32h ; '2'
0x180031cd6  lea     r9, aRegsetvalueexw_0; "RegSetValueExW failed [%d]"
0x180031cdd  mov     [rsp+50h+dwOptions], ebx
0x180031ce1  lea     rdx, aWindowsCompatI_74; "Windows::Compat::Inventory::Service::Tr"...
0x180031ce8  mov     ecx, 1
0x180031ced  call    AslLogCallPrintf
0x180031cf2  test    ebx, ebx
0x180031cf4  jle     loc_180031BEF
0x180031cfa  movzx   ebx, bx
0x180031cfd  or      ebx, 80070000h
0x180031d03  jmp     loc_180031BEF
0x180031d08  mov     r9d, 4; dwType
0x180031d0e  mov     [rsp+50h+samDesired], r9d; cbData
0x180031d13  lea     rax, [rbp+Data]
0x180031d17  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180031d1c  xor     r8d, r8d; Reserved
0x180031d1f  lea     rdx, aResult; "Result"
0x180031d26  mov     rcx, [rdi]; hKey
0x180031d29  call    cs:__imp_RegSetValueExW
0x180031d2f  mov     ebx, eax
0x180031d31  test    eax, eax
0x180031d33  jz      short loc_180031D3D
0x180031d35  mov     r8d, 39h ; '9'
0x180031d3b  jmp     short loc_180031CD6
0x180031d3d  xor     r8d, r8d; unsigned __int64
0x180031d40  mov     edx, [rbp+Data]; int
0x180031d43  mov     rcx, rsi; this
0x180031d46  call    ?SendRunTelemetry@Tracer@Service@Inventory@Compat@Windows@@AEAAJJ_K@Z; Windows::Compat::Inventory::Service::Tracer::SendRunTelemetry(long,unsigned __int64)
0x180031d4b  xor     eax, eax
0x180031d4d  add     rsp, 50h
0x180031d51  pop     r14
0x180031d53  pop     rdi
0x180031d54  pop     rsi
0x180031d55  pop     rbx
0x180031d56  pop     rbp
0x180031d57  retn
```
