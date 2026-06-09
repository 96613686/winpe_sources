# DllRegisterServer

- ea: `0x180013280`
- end: `0x1800134af`
- name: `DllRegisterServer`
- size: `559`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c1a4`
- `0x18001128c`
- `0x180013280`
- `0x1800181e0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180013388`
- `msvcrt!wcsrchr` at `0x180013388`
- `msvcrt!wcscpy_s` at `0x180013378`
- `msvcrt!wcscpy_s` at `0x1800133ac`
- `msvcrt!wcscpy_s` at `0x180013378`
- `msvcrt!wcscpy_s` at `0x1800133ac`
- `ADVAPI32!RegSetValueExW` at `0x18001344d`
- `ADVAPI32!RegSetValueExW` at `0x18001344d`
- `ADVAPI32!RegCloseKey` at `0x18001346a`
- `ADVAPI32!RegCloseKey` at `0x18001346a`
- `ADVAPI32!CloseServiceHandle` at `0x1800132e4`
- `ADVAPI32!CloseServiceHandle` at `0x180013303`
- `ADVAPI32!CloseServiceHandle` at `0x1800132e4`
- `ADVAPI32!CloseServiceHandle` at `0x180013303`
- `ADVAPI32!OpenSCManagerW` at `0x1800132ba`
- `ADVAPI32!OpenSCManagerW` at `0x1800132ba`
- `ADVAPI32!RegCreateKeyExW` at `0x1800133f4`
- `ADVAPI32!RegCreateKeyExW` at `0x1800133f4`
- `ADVAPI32!OpenServiceW` at `0x1800132d6`
- `ADVAPI32!OpenServiceW` at `0x1800132d6`
- `KERNEL32!GetModuleFileNameW` at `0x180013354`
- `KERNEL32!GetModuleFileNameW` at `0x180013354`
- `KERNEL32!GetLastError` at `0x1800132f2`
- `KERNEL32!GetLastError` at `0x180013472`
- `KERNEL32!GetLastError` at `0x1800132f2`
- `KERNEL32!GetLastError` at `0x180013472`
- `KERNEL32!GetCurrentProcess` at `0x18001330d`
- `KERNEL32!GetCurrentProcess` at `0x18001330d`
- `KERNEL32!IsWow64Process` at `0x18001331b`
- `KERNEL32!IsWow64Process` at `0x18001331b`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x180013337`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x180013337`

## string_xrefs

- `0x1800133e6`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`
- `0x1800132b1`: `ServicesActive`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rax
  char v3; // bl
  HANDLE CurrentProcess; // rax
  DWORD ModuleFileNameW; // eax
  wchar_t *v6; // rax
  signed int LastError; // eax
  const unsigned __int16 *v8; // rdx
  ATL::CComModule *v9; // rcx
  const struct _GUID *v10; // r8
  HRESULT v11; // ebx
  bool v12; // cc
  HKEY v13; // rdi
  __int64 v14; // rax
  WINBOOL Wow64Process; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+270h] [rbp+170h] BYREF

  Wow64Process = 0;
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"IAS", 4u);
    if ( v2 )
    {
      CloseServiceHandle(v2);
      v3 = 1;
    }
    else
    {
      v3 = 0;
      if ( GetLastError() == 1060 )
        v3 = 0;
    }
    CloseServiceHandle(v1);
    if ( !v3 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( IsWow64Process(CurrentProcess, &Wow64Process) )
      {
        if ( !Wow64Process )
          UnloadPerfCounterTextStringsW((LPWSTR)L"LODCTR IAS", 1);
      }
    }
  }
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = LastError <= 0;
  }
  else
  {
    wcscpy_s(Destination, 0x104u, Filename);
    v6 = wcsrchr(Destination, 0x5Cu);
    wcscpy_s(v6, 260 - (v6 - Destination), L"\\IAS");
    dwDisposition = 0;
    hKey = 0;
    LastError = RegCreateKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
                  0,
                  0,
                  0,
                  2u,
                  0,
                  &hKey,
                  &dwDisposition);
    v11 = LastError;
    v12 = LastError <= 0;
    if ( !LastError )
    {
      v13 = hKey;
      v11 = IASPublishLicenseType(hKey);
      if ( !v11 )
      {
        v14 = -1;
        do
          ++v14;
        while ( Destination[v14] );
        v11 = RegSetValueExW(v13, L"ProductDir", 0, 1u, (const BYTE *)Destination, 2 * v14 + 2);
      }
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_24;
    }
  }
  if ( !v12 )
    v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_24:
  if ( v11 >= 0 )
    return ATL::CComModule::RegisterServer(v9, v8, v10);
  else
    return v11;
}

```

## disassembly

```asm
0x180013280  push    rbp
0x180013282  push    rbx
0x180013283  push    rsi
0x180013284  push    rdi
0x180013285  lea     rbp, [rsp-398h]
0x18001328d  sub     rsp, 498h
0x180013294  mov     rax, cs:__security_cookie
0x18001329b  xor     rax, rsp
0x18001329e  mov     [rbp+3B0h+var_30], rax
0x1800132a5  xor     esi, esi
0x1800132a7  mov     [rsp+4B0h+Wow64Process], esi
0x1800132ab  mov     r8d, 80000000h; dwDesiredAccess
0x1800132b1  lea     rdx, DatabaseName; "ServicesActive"
0x1800132b8  xor     ecx, ecx; lpMachineName
0x1800132ba  call    cs:__imp_OpenSCManagerW
0x1800132c0  mov     rdi, rax
0x1800132c3  test    rax, rax
0x1800132c6  jz      short loc_18001333E
0x1800132c8  lea     r8d, [rsi+4]; dwDesiredAccess
0x1800132cc  lea     rdx, ServiceName; "IAS"
0x1800132d3  mov     rcx, rax; hSCManager
0x1800132d6  call    cs:__imp_OpenServiceW
0x1800132dc  test    rax, rax
0x1800132df  jz      short loc_1800132EE
0x1800132e1  mov     rcx, rax; hSCObject
0x1800132e4  call    cs:__imp_CloseServiceHandle
0x1800132ea  mov     bl, 1
0x1800132ec  jmp     short loc_180013300
0x1800132ee  movzx   ebx, sil
0x1800132f2  call    cs:__imp_GetLastError
0x1800132f8  cmp     eax, 424h
0x1800132fd  cmovz   ebx, esi
0x180013300  mov     rcx, rdi; hSCObject
0x180013303  call    cs:__imp_CloseServiceHandle
0x180013309  test    bl, bl
0x18001330b  jnz     short loc_18001333E
0x18001330d  call    cs:__imp_GetCurrentProcess
0x180013313  mov     rcx, rax; hProcess
0x180013316  lea     rdx, [rsp+4B0h+Wow64Process]; Wow64Process
0x18001331b  call    cs:__imp_IsWow64Process
0x180013321  test    eax, eax
0x180013323  jz      short loc_18001333E
0x180013325  cmp     [rsp+4B0h+Wow64Process], esi
0x180013329  jnz     short loc_18001333E
0x18001332b  mov     edx, 1; bQuietModeArg
0x180013330  lea     rcx, CommandLine; "LODCTR IAS"
0x180013337  call    cs:__imp_UnloadPerfCounterTextStringsW
0x18001333d  nop
0x18001333e  mov     ebx, 104h
0x180013343  mov     r8d, ebx; nSize
0x180013346  lea     rdx, [rbp+3B0h+Filename]; lpFilename
0x18001334d  mov     rcx, cs:hModule; hModule
0x180013354  call    cs:__imp_GetModuleFileNameW
0x18001335a  test    eax, eax
0x18001335c  jz      loc_180013472
0x180013362  cmp     eax, ebx
0x180013364  jz      loc_180013472
0x18001336a  lea     r8, [rbp+3B0h+Filename]; Source
0x180013371  mov     edx, ebx; SizeInWords
0x180013373  lea     rcx, [rsp+4B0h+Destination]; Destination
0x180013378  call    cs:__imp_wcscpy_s
0x18001337e  mov     edx, 5Ch ; '\'; Ch
0x180013383  lea     rcx, [rsp+4B0h+Destination]; Str
0x180013388  call    cs:__imp_wcsrchr
0x18001338e  lea     rdx, [rsp+4B0h+Destination]
0x180013393  mov     rcx, rax
0x180013396  sub     rcx, rdx
0x180013399  sar     rcx, 1
0x18001339c  sub     rbx, rcx
0x18001339f  lea     r8, aIas; "\\IAS"
0x1800133a6  mov     rdx, rbx; SizeInWords
0x1800133a9  mov     rcx, rax; Destination
0x1800133ac  call    cs:__imp_wcscpy_s
0x1800133b2  mov     [rsp+4B0h+dwDisposition], esi
0x1800133b6  mov     [rsp+4B0h+hKey], rsi
0x1800133bb  lea     rax, [rsp+4B0h+dwDisposition]
0x1800133c0  mov     [rsp+4B0h+lpdwDisposition], rax; lpdwDisposition
0x1800133c5  lea     rax, [rsp+4B0h+hKey]
0x1800133ca  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800133cf  mov     [rsp+4B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800133d4  mov     [rsp+4B0h+samDesired], 2; samDesired
0x1800133dc  mov     [rsp+4B0h+dwOptions], esi; dwOptions
0x1800133e0  xor     r9d, r9d; lpClass
0x1800133e3  xor     r8d, r8d; Reserved
0x1800133e6  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800133ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800133f4  call    cs:__imp_RegCreateKeyExW
0x1800133fa  mov     ebx, eax
0x1800133fc  test    eax, eax
0x1800133fe  jnz     short loc_18001347C
0x180013400  mov     rdi, [rsp+4B0h+hKey]
0x180013405  mov     rcx, rdi; hKey
0x180013408  call    IASPublishLicenseType
0x18001340d  mov     ebx, eax
0x18001340f  test    eax, eax
0x180013411  jnz     short loc_180013455
0x180013413  lea     rcx, [rsp+4B0h+Destination]
0x180013418  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001341c  inc     rax
0x18001341f  cmp     [rcx+rax*2], si
0x180013423  jnz     short loc_18001341C
0x180013425  lea     eax, ds:2[rax*2]
0x18001342c  mov     [rsp+4B0h+samDesired], eax; cbData
0x180013430  lea     rax, [rsp+4B0h+Destination]
0x180013435  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18001343a  mov     r9d, 1; dwType
0x180013440  xor     r8d, r8d; Reserved
0x180013443  lea     rdx, aProductdir; "ProductDir"
0x18001344a  mov     rcx, rdi; hKey
0x18001344d  call    cs:__imp_RegSetValueExW
0x180013453  mov     ebx, eax
0x180013455  test    ebx, ebx
0x180013457  jle     short loc_180013462
0x180013459  movzx   ebx, bx
0x18001345c  or      ebx, 80070000h
0x180013462  test    rdi, rdi
0x180013465  jz      short loc_180013487
0x180013467  mov     rcx, rdi; hKey
0x18001346a  call    cs:__imp_RegCloseKey
0x180013470  jmp     short loc_180013487
0x180013472  call    cs:__imp_GetLastError
0x180013478  mov     ebx, eax
0x18001347a  test    eax, eax
0x18001347c  jle     short loc_180013487
0x18001347e  movzx   ebx, ax
0x180013481  or      ebx, 80070000h
0x180013487  test    ebx, ebx
0x180013489  jns     short loc_18001348F
0x18001348b  mov     eax, ebx
0x18001348d  jmp     short loc_180013494
0x18001348f  call    ?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::RegisterServer(int,_GUID const *)
0x180013494  mov     rcx, [rbp+3B0h+var_30]
0x18001349b  xor     rcx, rsp; StackCookie
0x18001349e  call    __security_check_cookie
0x1800134a3  add     rsp, 498h
0x1800134aa  pop     rdi
0x1800134ab  pop     rsi
0x1800134ac  pop     rbx
0x1800134ad  pop     rbp
0x1800134ae  retn
```
