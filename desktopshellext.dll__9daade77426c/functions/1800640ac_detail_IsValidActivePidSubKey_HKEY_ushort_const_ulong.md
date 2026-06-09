# detail::IsValidActivePidSubKey(HKEY__ *,ushort const *,ulong)

- ea: `0x1800640ac`
- end: `0x180064229`
- name: `?IsValidActivePidSubKey@detail@@YA_NPEAUHKEY__@@PEBGK@Z`
- size: `381`
- prototype: `bool __fastcall(HKEY hKey, HKEY lpSubKey, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180060df4`

## callees

- `0x18001a100`
- `0x1800640ac`
- `0x180068160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800640fa`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800640fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064185`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064185`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800641dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800641fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800641dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800641fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006413b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006413b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800640c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800640c9`
- `ntdll!NtQueryInformationProcess` at `0x1800641b6`
- `ntdll!NtQueryInformationProcess` at `0x1800641b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall detail::IsValidActivePidSubKey(HKEY hKey, const WCHAR *lpSubKey, const unsigned __int16 *a3)
{
  char *v5; // rbx
  NTSTATUS v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  bool v9; // bl
  const char *v11; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-34h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-30h] BYREF
  __int64 ProcessInformation; // [rsp+40h] [rbp-28h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v18[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD ExitCode; // [rsp+88h] [rbp+20h] BYREF

  v5 = (char *)OpenProcess(0x1000u, 0, (DWORD)a3);
  v18[0] = v5;
  if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (ExitCode = 0, !GetExitCodeProcess(v5, &ExitCode))
    || ExitCode != 259 )
  {
LABEL_13:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
    return 0;
  }
  hKeya = 0;
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya)
    || (*(_QWORD *)Data = 0, Type = 0, cbData = 8, RegQueryValueExW(hKeya, L"SequenceNumber", 0, &Type, Data, &cbData))
    || Type != 11 )
  {
LABEL_11:
    if ( hKeya )
      RegCloseKey(hKeya);
    goto LABEL_13;
  }
  ProcessInformation = 0;
  v6 = NtQueryInformationProcess(v5, ProcessLUIDDeviceMapsEnabled|0x40, &ProcessInformation, 8u, 0);
  if ( v6 < 0 )
  {
    try
    {
      wil::details::in1diag3::_Throw_NtStatus(retaddr, v7, v8, (const char *)(unsigned int)v6, (int)phkResult);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x6E,
        (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\ShellFeatureRolloutCoordinatorHelpers.h",
        v11);
      goto LABEL_11;
    }
  }
  v9 = *(_QWORD *)Data == ProcessInformation;
  if ( hKeya )
    RegCloseKey(hKeya);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
  return v9;
}

```

## disassembly

```asm
0x1800640ac  mov     [rsp+arg_0], rbx
0x1800640b1  mov     [rsp+arg_8], rsi
0x1800640b6  push    r14
0x1800640b8  sub     rsp, 60h
0x1800640bc  mov     rsi, rdx
0x1800640bf  mov     r14, rcx
0x1800640c2  xor     edx, edx; bInheritHandle
0x1800640c4  mov     ecx, 1000h; dwDesiredAccess
0x1800640c9  call    cs:__imp_OpenProcess
0x1800640cf  mov     rbx, rax
0x1800640d2  mov     [rsp+68h+var_18], rax
0x1800640d7  dec     rax
0x1800640da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800640de  ja      loc_180064202
0x1800640e4  mov     [rsp+68h+ExitCode], 0
0x1800640ef  lea     rdx, [rsp+68h+ExitCode]; lpExitCode
0x1800640f7  mov     rcx, rbx; hProcess
0x1800640fa  call    cs:__imp_GetExitCodeProcess
0x180064100  test    eax, eax
0x180064102  jz      loc_180064202
0x180064108  cmp     [rsp+68h+ExitCode], 103h
0x180064113  jnz     loc_180064202
0x180064119  mov     [rsp+68h+hKey], 0
0x180064122  lea     rax, [rsp+68h+hKey]
0x180064127  mov     [rsp+68h+phkResult], rax; phkResult
0x18006412c  mov     r9d, 20019h; samDesired
0x180064132  xor     r8d, r8d; ulOptions
0x180064135  mov     rdx, rsi; lpSubKey
0x180064138  mov     rcx, r14; hKey
0x18006413b  call    cs:__imp_RegOpenKeyExW
0x180064141  test    eax, eax
0x180064143  jnz     loc_1800641F1
0x180064149  mov     qword ptr [rsp+68h+Data], 0
0x180064152  mov     [rsp+68h+Type], eax
0x180064156  lea     esi, [rax+8]
0x180064159  mov     [rsp+68h+cbData], esi
0x18006415d  lea     rax, [rsp+68h+cbData]
0x180064162  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180064167  lea     rax, [rsp+68h+Data]
0x18006416c  mov     [rsp+68h+phkResult], rax; lpData
0x180064171  lea     r9, [rsp+68h+Type]; lpType
0x180064176  xor     r8d, r8d; lpReserved
0x180064179  lea     rdx, aSequencenumber; "SequenceNumber"
0x180064180  mov     rcx, [rsp+68h+hKey]; hKey
0x180064185  call    cs:__imp_RegQueryValueExW
0x18006418b  test    eax, eax
0x18006418d  jnz     short loc_1800641F1
0x18006418f  cmp     [rsp+68h+Type], 0Bh
0x180064194  jnz     short loc_1800641F1
0x180064196  mov     [rsp+68h+ProcessInformation], 0
0x18006419f  mov     [rsp+68h+phkResult], 0; int
0x1800641a8  mov     r9d, esi; ProcessInformationLength
0x1800641ab  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x1800641b0  lea     edx, [rsi+54h]; ProcessInformationClass
0x1800641b3  mov     rcx, rbx; ProcessHandle
0x1800641b6  call    cs:__imp_NtQueryInformationProcess
0x1800641bc  mov     rcx, [rsp+68h]; this
0x1800641c1  test    eax, eax
0x1800641c3  js      short loc_18006421F
0x1800641c5  mov     rax, [rsp+68h+ProcessInformation]
0x1800641ca  cmp     qword ptr [rsp+68h+Data], rax
0x1800641cf  setz    bl
0x1800641d2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800641d7  test    rcx, rcx
0x1800641da  jz      short loc_1800641E3
0x1800641dc  call    cs:__imp_RegCloseKey
0x1800641e2  nop
0x1800641e3  lea     rcx, [rsp+68h+var_18]
0x1800641e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800641ed  mov     al, bl
0x1800641ef  jmp     short loc_18006420E
0x1800641f1  mov     rcx, [rsp+68h+hKey]; hKey
0x1800641f6  test    rcx, rcx
0x1800641f9  jz      short loc_180064202
0x1800641fb  call    cs:__imp_RegCloseKey
0x180064201  nop
0x180064202  lea     rcx, [rsp+68h+var_18]
0x180064207  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006420c  xor     al, al
0x18006420e  mov     rbx, [rsp+68h+arg_0]
0x180064213  mov     rsi, [rsp+68h+arg_8]
0x180064218  add     rsp, 60h
0x18006421c  pop     r14
0x18006421e  retn
0x18006421f  mov     r9d, eax; char *
0x180064222  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
