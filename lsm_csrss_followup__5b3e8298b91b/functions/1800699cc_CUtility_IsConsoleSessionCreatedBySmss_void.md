# CUtility::IsConsoleSessionCreatedBySmss(void)

- ea: `0x1800699cc`
- end: `0x180069ab8`
- name: `?IsConsoleSessionCreatedBySmss@CUtility@@SAHXZ`
- size: `236`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002ae4c`
- `0x18005fcc4`

## callees

- `0x18001eab0`
- `0x1800699cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069a18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069a4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069a4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069aa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069aa9`

## string_xrefs

- `0x180069a77`: `Number of session created by SMSS`

## pseudocode

```c
_BOOL8 CUtility::IsConsoleSessionCreatedBySmss(void)
{
  BOOL v0; // ebx
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  __int64 v6; // [rsp+48h] [rbp-20h] BYREF
  const char *v7; // [rsp+50h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+80h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF
  DWORD Type; // [rsp+90h] [rbp+28h] BYREF
  BOOL v11; // [rsp+98h] [rbp+30h] BYREF

  Type = 0;
  cbData = 4;
  Data = 0;
  hKey = 0;
  v0 = 1;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Session Manager", 0, 0x20019u, &hKey);
  if ( hKey )
  {
    if ( !RegQueryValueExW(hKey, L"NumberOfInitialSessions", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v0 = Data == 2;
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v6 = Data;
        v7 = "Number of session created by SMSS";
        v11 = Data == 2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v1,
          (unsigned int)byte_1800C38D5,
          v2,
          v3,
          (__int64)&v7,
          (__int64)&v6,
          (__int64)&v11);
      }
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x1800699cc  push    rbp
0x1800699ce  push    rbx
0x1800699cf  mov     rbp, rsp
0x1800699d2  sub     rsp, 68h
0x1800699d6  lea     rax, [rbp+hKey]
0x1800699da  mov     [rbp+Type], 0
0x1800699e1  mov     r9d, 20019h; samDesired
0x1800699e7  mov     [rsp+68h+phkResult], rax; phkResult
0x1800699ec  xor     r8d, r8d; ulOptions
0x1800699ef  mov     [rbp+cbData], 4
0x1800699f6  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Control\\Ses"...
0x1800699fd  mov     [rbp+Data], 0
0x180069a04  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069a0b  mov     [rbp+hKey], 0
0x180069a13  mov     ebx, 1
0x180069a18  call    cs:__imp_RegOpenKeyExW
0x180069a1e  mov     rcx, [rbp+hKey]; hKey
0x180069a22  test    rcx, rcx
0x180069a25  jz      loc_180069AAF
0x180069a2b  lea     rax, [rbp+cbData]
0x180069a2f  xor     r8d, r8d; lpReserved
0x180069a32  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180069a37  lea     r9, [rbp+Type]; lpType
0x180069a3b  lea     rax, [rbp+Data]
0x180069a3f  lea     rdx, aNumberofinitia; "NumberOfInitialSessions"
0x180069a46  mov     [rsp+68h+phkResult], rax; lpData
0x180069a4b  call    cs:__imp_RegQueryValueExW
0x180069a51  test    eax, eax
0x180069a53  jnz     short loc_180069AA5
0x180069a55  mov     eax, cs:dword_1800DA020
0x180069a5b  xor     ebx, ebx
0x180069a5d  cmp     [rbp+Data], 2
0x180069a61  setz    bl
0x180069a64  cmp     eax, 4
0x180069a67  jbe     short loc_180069AA5
0x180069a69  mov     eax, [rbp+Data]
0x180069a6c  lea     rdx, byte_1800C38D5
0x180069a73  mov     [rbp+var_20], rax
0x180069a77  lea     rax, aNumberOfSessio; "Number of session created by SMSS"
0x180069a7e  mov     [rbp+var_18], rax
0x180069a82  lea     rax, [rbp+arg_18]
0x180069a86  mov     [rsp+68h+var_38], rax
0x180069a8b  lea     rax, [rbp+var_20]
0x180069a8f  mov     [rsp+68h+lpcbData], rax
0x180069a94  lea     rax, [rbp+var_18]
0x180069a98  mov     [rsp+68h+phkResult], rax
0x180069a9d  mov     [rbp+arg_18], ebx
0x180069aa0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180069aa5  mov     rcx, [rbp+hKey]; hKey
0x180069aa9  call    cs:__imp_RegCloseKey
0x180069aaf  mov     eax, ebx
0x180069ab1  add     rsp, 68h
0x180069ab5  pop     rbx
0x180069ab6  pop     rbp
0x180069ab7  retn
```
