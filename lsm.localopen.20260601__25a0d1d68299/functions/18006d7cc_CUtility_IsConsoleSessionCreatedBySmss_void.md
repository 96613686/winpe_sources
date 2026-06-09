# CUtility::IsConsoleSessionCreatedBySmss(void)

- ea: `0x18006d7cc`
- end: `0x18006d8cb`
- name: `?IsConsoleSessionCreatedBySmss@CUtility@@SAHXZ`
- size: `255`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002cf00`
- `0x1800637cc`

## callees

- `0x18001eb00`
- `0x18006d7cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d818`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d818`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006d851`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006d851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d8b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d8b5`

## string_xrefs

- `0x18006d883`: `Number of session created by SMSS`

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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v6 = Data;
        v7 = "Number of session created by SMSS";
        v11 = Data == 2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v1,
          (unsigned int)byte_1800C8A5D,
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
0x18006d7cc  push    rbp
0x18006d7ce  push    rbx
0x18006d7cf  mov     rbp, rsp
0x18006d7d2  sub     rsp, 68h
0x18006d7d6  lea     rax, [rbp+hKey]
0x18006d7da  mov     [rbp+Type], 0
0x18006d7e1  mov     r9d, 20019h; samDesired
0x18006d7e7  mov     [rsp+68h+phkResult], rax; phkResult
0x18006d7ec  xor     r8d, r8d; ulOptions
0x18006d7ef  mov     [rbp+cbData], 4
0x18006d7f6  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Control\\Ses"...
0x18006d7fd  mov     [rbp+Data], 0
0x18006d804  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d80b  mov     [rbp+hKey], 0
0x18006d813  mov     ebx, 1
0x18006d818  call    cs:__imp_RegOpenKeyExW
0x18006d81f  nop     dword ptr [rax+rax+00h]
0x18006d824  mov     rcx, [rbp+hKey]; hKey
0x18006d828  test    rcx, rcx
0x18006d82b  jz      loc_18006D8C1
0x18006d831  lea     rax, [rbp+cbData]
0x18006d835  xor     r8d, r8d; lpReserved
0x18006d838  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18006d83d  lea     r9, [rbp+Type]; lpType
0x18006d841  lea     rax, [rbp+Data]
0x18006d845  lea     rdx, aNumberofinitia; "NumberOfInitialSessions"
0x18006d84c  mov     [rsp+68h+phkResult], rax; lpData
0x18006d851  call    cs:__imp_RegQueryValueExW
0x18006d858  nop     dword ptr [rax+rax+00h]
0x18006d85d  test    eax, eax
0x18006d85f  jnz     short loc_18006D8B1
0x18006d861  mov     eax, cs:dword_1800DF020
0x18006d867  xor     ebx, ebx
0x18006d869  cmp     [rbp+Data], 2
0x18006d86d  setz    bl
0x18006d870  cmp     eax, 4
0x18006d873  jbe     short loc_18006D8B1
0x18006d875  mov     eax, [rbp+Data]
0x18006d878  lea     rdx, byte_1800C8A5D
0x18006d87f  mov     [rbp+var_20], rax
0x18006d883  lea     rax, aNumberOfSessio; "Number of session created by SMSS"
0x18006d88a  mov     [rbp+var_18], rax
0x18006d88e  lea     rax, [rbp+arg_18]
0x18006d892  mov     [rsp+68h+var_38], rax
0x18006d897  lea     rax, [rbp+var_20]
0x18006d89b  mov     [rsp+68h+lpcbData], rax
0x18006d8a0  lea     rax, [rbp+var_18]
0x18006d8a4  mov     [rsp+68h+phkResult], rax
0x18006d8a9  mov     [rbp+arg_18], ebx
0x18006d8ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18006d8b1  mov     rcx, [rbp+hKey]; hKey
0x18006d8b5  call    cs:__imp_RegCloseKey
0x18006d8bc  nop     dword ptr [rax+rax+00h]
0x18006d8c1  mov     eax, ebx
0x18006d8c3  add     rsp, 68h
0x18006d8c7  pop     rbx
0x18006d8c8  pop     rbp
0x18006d8c9  retn
```
