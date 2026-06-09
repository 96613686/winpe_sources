# GetDLLNameForDispatchEntryService(char *,char *,ulong)

- ea: `0x14000193c`
- end: `0x140001b39`
- name: `?GetDLLNameForDispatchEntryService@@YAHPEAD0K@Z`
- size: `509`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, char *lpData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140001b40`

## callees

- `0x14000193c`
- `0x140002850`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x140001a90`
- `ADVAPI32!RegQueryValueExA` at `0x140001a90`
- `ADVAPI32!RegCloseKey` at `0x140001b02`
- `ADVAPI32!RegCloseKey` at `0x140001b12`
- `ADVAPI32!RegCloseKey` at `0x140001b02`
- `ADVAPI32!RegCloseKey` at `0x140001b12`
- `ADVAPI32!RegOpenKeyExA` at `0x1400019a9`
- `ADVAPI32!RegOpenKeyExA` at `0x140001a25`
- `ADVAPI32!RegOpenKeyExA` at `0x1400019a9`
- `ADVAPI32!RegOpenKeyExA` at `0x140001a25`
- `msvcrt!sprintf_s` at `0x1400019c7`
- `msvcrt!sprintf_s` at `0x140001a47`
- `msvcrt!sprintf_s` at `0x140001ab9`
- `msvcrt!sprintf_s` at `0x1400019c7`
- `msvcrt!sprintf_s` at `0x140001a47`
- `msvcrt!sprintf_s` at `0x140001ab9`
- `iisutil!PuDbgPrint` at `0x1400019ff`
- `iisutil!PuDbgPrint` at `0x140001aed`
- `iisutil!PuDbgPrint` at `0x1400019ff`
- `iisutil!PuDbgPrint` at `0x140001aed`

## string_xrefs

- `0x140001983`: `System\CurrentControlSet\Services`
- `0x1400019b6`: `Inetinfo: Failed to open service key: %ld\n`
- `0x1400019ec`: `GetDLLNameForDispatchEntryService`
- `0x140001ad4`: `GetDLLNameForDispatchEntryService`
- `0x140001a36`: `Inetinfo: Failed to open service key for %s: %ld\n`
- `0x140001a81`: `IISDllPath`
- `0x140001aa8`: `Service Dll is %s`

## pseudocode

```c
__int64 __fastcall GetDLLNameForDispatchEntryService(LPCSTR lpSubKey, char *lpData)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  __int64 v6; // r8
  LSTATUS v7; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  char Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  phkResult = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v4 = 0;
  v5 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services", 0, 0x20019u, &hKey);
  if ( v5 )
  {
    sprintf_s(Buffer, 0x100u, "Inetinfo: Failed to open service key: %ld\n", v5);
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_13;
    v6 = 388;
    goto LABEL_4;
  }
  v7 = RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( v7 )
  {
    sprintf_s(Buffer, 0x100u, "Inetinfo: Failed to open service key for %s: %ld\n", lpSubKey, v7);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v6 = 405;
LABEL_4:
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx",
        v6,
        "GetDLLNameForDispatchEntryService",
        Buffer);
    }
  }
  else
  {
    cbData = 261;
    if ( !RegQueryValueExA(phkResult, "IISDllPath", 0, &Type, (LPBYTE)lpData, &cbData) && Type - 1 <= 1 )
    {
      sprintf_s(Buffer, 0x100u, "Service Dll is %s", lpData);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx",
          424,
          "GetDLLNameForDispatchEntryService",
          Buffer);
      v4 = 1;
    }
  }
LABEL_13:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x14000193c  mov     [rsp-8+arg_10], rbx
0x140001941  push    rbp
0x140001942  push    rsi
0x140001943  push    rdi
0x140001944  lea     rbp, [rsp-60h]
0x140001949  sub     rsp, 160h
0x140001950  mov     rax, cs:__security_cookie
0x140001957  xor     rax, rsp
0x14000195a  mov     [rbp+70h+var_20], rax
0x14000195e  mov     rdi, rdx
0x140001961  mov     [rsp+170h+var_138], 0
0x14000196a  mov     rsi, rcx
0x14000196d  mov     [rsp+170h+hKey], 0
0x140001976  lea     rax, [rsp+170h+hKey]
0x14000197b  mov     [rsp+170h+Type], 0
0x140001983  lea     rdx, SubKey; "System\\CurrentControlSet\\Services"
0x14000198a  mov     [rsp+170h+phkResult], rax; phkResult
0x14000198f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001996  mov     [rsp+170h+cbData], 0
0x14000199e  mov     r9d, 20019h; samDesired
0x1400019a4  xor     r8d, r8d; ulOptions
0x1400019a7  xor     ebx, ebx
0x1400019a9  call    cs:__imp_RegOpenKeyExA
0x1400019af  test    eax, eax
0x1400019b1  jz      short loc_140001A0A
0x1400019b3  mov     r9d, eax
0x1400019b6  lea     r8, aInetinfoFailed_0; "Inetinfo: Failed to open service key: %"...
0x1400019bd  mov     edx, 100h; BufferCount
0x1400019c2  lea     rcx, [rsp+170h+Buffer]; Buffer
0x1400019c7  call    cs:__imp_sprintf_s
0x1400019cd  test    cs:g_dwDebugFlags, 3
0x1400019d4  jz      loc_140001AF8
0x1400019da  mov     r8d, 184h
0x1400019e0  mov     rcx, cs:g_pDebug
0x1400019e7  lea     rax, [rsp+170h+Buffer]
0x1400019ec  lea     r9, aGetdllnameford; "GetDLLNameForDispatchEntryService"
0x1400019f3  mov     [rsp+170h+phkResult], rax
0x1400019f8  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x1400019ff  call    cs:__imp_PuDbgPrint
0x140001a05  jmp     loc_140001AF8
0x140001a0a  mov     rcx, [rsp+170h+hKey]; hKey
0x140001a0f  lea     rax, [rsp+170h+var_138]
0x140001a14  mov     r9d, 20019h; samDesired
0x140001a1a  mov     [rsp+170h+phkResult], rax; phkResult
0x140001a1f  xor     r8d, r8d; ulOptions
0x140001a22  mov     rdx, rsi; lpSubKey
0x140001a25  call    cs:__imp_RegOpenKeyExA
0x140001a2b  test    eax, eax
0x140001a2d  jz      short loc_140001A65
0x140001a2f  mov     r9, rsi
0x140001a32  mov     dword ptr [rsp+170h+phkResult], eax
0x140001a36  lea     r8, aInetinfoFailed; "Inetinfo: Failed to open service key fo"...
0x140001a3d  mov     edx, 100h; BufferCount
0x140001a42  lea     rcx, [rsp+170h+Buffer]; Buffer
0x140001a47  call    cs:__imp_sprintf_s
0x140001a4d  test    cs:g_dwDebugFlags, 3
0x140001a54  jz      loc_140001AF8
0x140001a5a  mov     r8d, 195h
0x140001a60  jmp     loc_1400019E0
0x140001a65  mov     rcx, [rsp+170h+var_138]; hKey
0x140001a6a  lea     rax, [rsp+170h+cbData]
0x140001a6f  mov     [rsp+170h+lpcbData], rax; lpcbData
0x140001a74  lea     r9, [rsp+170h+Type]; lpType
0x140001a79  xor     r8d, r8d; lpReserved
0x140001a7c  mov     [rsp+170h+phkResult], rdi; lpData
0x140001a81  lea     rdx, ValueName; "IISDllPath"
0x140001a88  mov     [rsp+170h+cbData], 105h
0x140001a90  call    cs:__imp_RegQueryValueExA
0x140001a96  test    eax, eax
0x140001a98  jnz     short loc_140001AF8
0x140001a9a  mov     eax, [rsp+170h+Type]
0x140001a9e  dec     eax
0x140001aa0  cmp     eax, 1
0x140001aa3  ja      short loc_140001AF8
0x140001aa5  mov     r9, rdi
0x140001aa8  lea     r8, aServiceDllIsS; "Service Dll is %s"
0x140001aaf  mov     edx, 100h; BufferCount
0x140001ab4  lea     rcx, [rsp+170h+Buffer]; Buffer
0x140001ab9  call    cs:__imp_sprintf_s
0x140001abf  test    cs:g_dwDebugFlags, 3
0x140001ac6  jz      short loc_140001AF3
0x140001ac8  mov     rcx, cs:g_pDebug
0x140001acf  lea     rax, [rsp+170h+Buffer]
0x140001ad4  lea     r9, aGetdllnameford; "GetDLLNameForDispatchEntryService"
0x140001adb  mov     [rsp+170h+phkResult], rax
0x140001ae0  mov     r8d, 1A8h
0x140001ae6  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140001aed  call    cs:__imp_PuDbgPrint
0x140001af3  mov     ebx, 1
0x140001af8  mov     rcx, [rsp+170h+var_138]; hKey
0x140001afd  test    rcx, rcx
0x140001b00  jz      short loc_140001B08
0x140001b02  call    cs:__imp_RegCloseKey
0x140001b08  mov     rcx, [rsp+170h+hKey]; hKey
0x140001b0d  test    rcx, rcx
0x140001b10  jz      short loc_140001B18
0x140001b12  call    cs:__imp_RegCloseKey
0x140001b18  mov     eax, ebx
0x140001b1a  mov     rcx, [rbp+70h+var_20]
0x140001b1e  xor     rcx, rsp; StackCookie
0x140001b21  call    __security_check_cookie
0x140001b26  mov     rbx, [rsp+170h+arg_10]
0x140001b2e  add     rsp, 160h
0x140001b35  pop     rdi
0x140001b36  pop     rsi
0x140001b37  pop     rbp
0x140001b38  retn
```
