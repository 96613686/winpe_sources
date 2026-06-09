# RegisterSplVectoredHandler

- ea: `0x14005715c`
- end: `0x140057296`
- name: `RegisterSplVectoredHandler`
- size: `314`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x140056080`

## callees

- `0x14005715c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005726f`
- `ADVAPI32!RegCloseKey` at `0x14005726f`
- `ADVAPI32!RegOpenKeyExW` at `0x14005718d`
- `ADVAPI32!RegOpenKeyExW` at `0x14005718d`
- `ADVAPI32!RegQueryValueExW` at `0x1400571d0`
- `ADVAPI32!RegQueryValueExW` at `0x14005721a`
- `ADVAPI32!RegQueryValueExW` at `0x140057258`
- `ADVAPI32!RegQueryValueExW` at `0x1400571d0`
- `ADVAPI32!RegQueryValueExW` at `0x14005721a`
- `ADVAPI32!RegQueryValueExW` at `0x140057258`
- `KERNEL32!AddVectoredExceptionHandler` at `0x14005728a`
- `KERNEL32!AddVectoredExceptionHandler` at `0x14005728a`

## pseudocode

```c
LSTATUS RegisterSplVectoredHandler()
{
  LSTATUS result; // eax
  int v1; // eax
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Print", 0, 0x20019u, &hKey);
  if ( !result )
  {
    Data = 0;
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"ExceptionHandlerEnabled", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v1 = g_bExceptionHandlerEnabled;
    }
    else
    {
      v1 = Data;
      g_bExceptionHandlerEnabled = Data;
    }
    if ( v1 )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"TerminateOnFatalException", 0, &Type, (LPBYTE)&Data, &cbData) )
        g_bTerminateOnFatalException = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BreakOnFatalException", 0, &Type, (LPBYTE)&Data, &cbData) )
        g_bBreakOnFatalException = Data;
    }
    result = RegCloseKey(hKey);
  }
  if ( g_bExceptionHandlerEnabled )
    return (unsigned int)AddVectoredExceptionHandler(1u, SpoolerVectoredHandler);
  return result;
}

```

## disassembly

```asm
0x14005715c  push    rbp
0x14005715e  mov     rbp, rsp
0x140057161  sub     rsp, 30h
0x140057165  lea     rax, [rbp+hKey]
0x140057169  mov     [rbp+hKey], 0
0x140057171  mov     r9d, 20019h; samDesired
0x140057177  mov     [rsp+30h+phkResult], rax; phkResult
0x14005717c  xor     r8d, r8d; ulOptions
0x14005717f  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x140057186  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005718d  call    cs:__imp_RegOpenKeyExW
0x140057193  test    eax, eax
0x140057195  jnz     loc_140057275
0x14005719b  mov     rcx, [rbp+hKey]; hKey
0x14005719f  lea     r9, [rbp+Type]; lpType
0x1400571a3  mov     [rbp+Data], eax
0x1400571a6  lea     rdx, aExceptionhandl; "ExceptionHandlerEnabled"
0x1400571ad  lea     rax, [rbp+cbData]
0x1400571b1  mov     [rbp+Type], 4
0x1400571b8  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1400571bd  xor     r8d, r8d; lpReserved
0x1400571c0  lea     rax, [rbp+Data]
0x1400571c4  mov     [rbp+cbData], 4
0x1400571cb  mov     [rsp+30h+phkResult], rax; lpData
0x1400571d0  call    cs:__imp_RegQueryValueExW
0x1400571d6  test    eax, eax
0x1400571d8  jnz     short loc_1400571E5
0x1400571da  mov     eax, [rbp+Data]
0x1400571dd  mov     cs:?g_bExceptionHandlerEnabled@@3HA, eax; int g_bExceptionHandlerEnabled
0x1400571e3  jmp     short loc_1400571EB
0x1400571e5  mov     eax, cs:?g_bExceptionHandlerEnabled@@3HA; int g_bExceptionHandlerEnabled
0x1400571eb  test    eax, eax
0x1400571ed  jz      short loc_14005726B
0x1400571ef  mov     rcx, [rbp+hKey]; hKey
0x1400571f3  lea     rax, [rbp+cbData]
0x1400571f7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1400571fc  lea     r9, [rbp+Type]; lpType
0x140057200  lea     rax, [rbp+Data]
0x140057204  mov     [rbp+cbData], 4
0x14005720b  xor     r8d, r8d; lpReserved
0x14005720e  mov     [rsp+30h+phkResult], rax; lpData
0x140057213  lea     rdx, aTerminateonfat; "TerminateOnFatalException"
0x14005721a  call    cs:__imp_RegQueryValueExW
0x140057220  test    eax, eax
0x140057222  jnz     short loc_14005722D
0x140057224  mov     eax, [rbp+Data]
0x140057227  mov     cs:?g_bTerminateOnFatalException@@3HA, eax; int g_bTerminateOnFatalException
0x14005722d  mov     rcx, [rbp+hKey]; hKey
0x140057231  lea     rax, [rbp+cbData]
0x140057235  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14005723a  lea     r9, [rbp+Type]; lpType
0x14005723e  lea     rax, [rbp+Data]
0x140057242  mov     [rbp+cbData], 4
0x140057249  xor     r8d, r8d; lpReserved
0x14005724c  mov     [rsp+30h+phkResult], rax; lpData
0x140057251  lea     rdx, aBreakonfatalex; "BreakOnFatalException"
0x140057258  call    cs:__imp_RegQueryValueExW
0x14005725e  test    eax, eax
0x140057260  jnz     short loc_14005726B
0x140057262  mov     eax, [rbp+Data]
0x140057265  mov     cs:?g_bBreakOnFatalException@@3HA, eax; int g_bBreakOnFatalException
0x14005726b  mov     rcx, [rbp+hKey]; hKey
0x14005726f  call    cs:__imp_RegCloseKey
0x140057275  cmp     cs:?g_bExceptionHandlerEnabled@@3HA, 0; int g_bExceptionHandlerEnabled
0x14005727c  jz      short loc_140057290
0x14005727e  lea     rdx, SpoolerVectoredHandler; Handler
0x140057285  mov     ecx, 1; First
0x14005728a  call    cs:__imp_AddVectoredExceptionHandler
0x140057290  add     rsp, 30h
0x140057294  pop     rbp
0x140057295  retn
```
