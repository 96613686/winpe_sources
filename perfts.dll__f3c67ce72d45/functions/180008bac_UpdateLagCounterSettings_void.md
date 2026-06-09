# UpdateLagCounterSettings(void)

- ea: `0x180008bac`
- end: `0x180008d59`
- name: `?UpdateLagCounterSettings@@YAXXZ`
- size: `429`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180007668`

## callees

- `0x180001098`
- `0x180008bac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180008cd4`
- `ADVAPI32!RegCloseKey` at `0x180008cd4`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bf4`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bf4`
- `ADVAPI32!RegQueryValueExW` at `0x180008c2a`
- `ADVAPI32!RegQueryValueExW` at `0x180008c70`
- `ADVAPI32!RegQueryValueExW` at `0x180008cb6`
- `ADVAPI32!RegQueryValueExW` at `0x180008c2a`
- `ADVAPI32!RegQueryValueExW` at `0x180008c70`
- `ADVAPI32!RegQueryValueExW` at `0x180008cb6`

## pseudocode

```c
void UpdateLagCounterSettings(void)
{
  int v0; // r8d
  int v1; // r9d
  int v2; // ecx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v4[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF
  int Data; // [rsp+70h] [rbp+28h] BYREF
  int v8; // [rsp+78h] [rbp+30h] BYREF

  Type = 0;
  cbData = 4;
  Data = 0;
  hKey = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v2 = (int)hKey;
  if ( hKey )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"LagCounterImageNameFirst", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data == 1 )
    {
      CounterHelper::LagCounterImageNameFirst = 1;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"LagCounterShowUnknown", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
      CounterHelper::LagCounterShowUnknown = 1;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"LagCounterCleanZombie", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && !Data )
      CounterHelper::LagCounterCleanZombie = 0;
    RegCloseKey(hKey);
  }
  if ( (unsigned int)dword_180012020 > 4 )
  {
    v8 = CounterHelper::LagCounterImageNameFirst;
    v4[0] = "Lag counter Report Process Name First set";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&unk_18000F34F,
      v0,
      v1,
      (__int64)v4,
      (__int64)&v8);
  }
  if ( (unsigned int)dword_180012020 > 4 )
  {
    v8 = CounterHelper::LagCounterShowUnknown;
    v4[0] = "Lag counter show unknown set";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&unk_18000EF1B,
      v0,
      v1,
      (__int64)v4,
      (__int64)&v8);
  }
}

```

## disassembly

```asm
0x180008bac  push    rbp
0x180008bae  push    rbx
0x180008baf  mov     rbp, rsp
0x180008bb2  sub     rsp, 48h
0x180008bb6  lea     rax, [rbp+hKey]
0x180008bba  mov     [rbp+Type], 0
0x180008bc1  mov     ebx, 4
0x180008bc6  mov     [rsp+48h+phkResult], rax; phkResult
0x180008bcb  mov     r9d, 20019h; samDesired
0x180008bd1  mov     [rbp+cbData], ebx
0x180008bd4  xor     r8d, r8d; ulOptions
0x180008bd7  mov     [rbp+Data], 0
0x180008bde  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180008be5  mov     [rbp+hKey], 0
0x180008bed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008bf4  call    cs:__imp_RegOpenKeyExW
0x180008bfa  mov     rcx, [rbp+hKey]; hKey
0x180008bfe  test    rcx, rcx
0x180008c01  jz      loc_180008CDA
0x180008c07  lea     rax, [rbp+cbData]
0x180008c0b  mov     [rbp+cbData], ebx
0x180008c0e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180008c13  lea     r9, [rbp+Type]; lpType
0x180008c17  lea     rax, [rbp+Data]
0x180008c1b  xor     r8d, r8d; lpReserved
0x180008c1e  lea     rdx, aLagcounterimag; "LagCounterImageNameFirst"
0x180008c25  mov     [rsp+48h+phkResult], rax; lpData
0x180008c2a  call    cs:__imp_RegQueryValueExW
0x180008c30  test    eax, eax
0x180008c32  jnz     short loc_180008C49
0x180008c34  cmp     [rbp+Type], ebx
0x180008c37  jnz     short loc_180008C49
0x180008c39  cmp     [rbp+Data], 1
0x180008c3d  jnz     short loc_180008C49
0x180008c3f  mov     cs:?LagCounterImageNameFirst@CounterHelper@@2HA, 1; int CounterHelper::LagCounterImageNameFirst
0x180008c49  mov     rcx, [rbp+hKey]; hKey
0x180008c4d  lea     rax, [rbp+cbData]
0x180008c51  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180008c56  lea     r9, [rbp+Type]; lpType
0x180008c5a  lea     rax, [rbp+Data]
0x180008c5e  mov     [rbp+cbData], ebx
0x180008c61  xor     r8d, r8d; lpReserved
0x180008c64  mov     [rsp+48h+phkResult], rax; lpData
0x180008c69  lea     rdx, aLagcountershow; "LagCounterShowUnknown"
0x180008c70  call    cs:__imp_RegQueryValueExW
0x180008c76  test    eax, eax
0x180008c78  jnz     short loc_180008C8F
0x180008c7a  cmp     [rbp+Type], ebx
0x180008c7d  jnz     short loc_180008C8F
0x180008c7f  cmp     [rbp+Data], 1
0x180008c83  jnz     short loc_180008C8F
0x180008c85  mov     cs:?LagCounterShowUnknown@CounterHelper@@2HA, 1; int CounterHelper::LagCounterShowUnknown
0x180008c8f  mov     rcx, [rbp+hKey]; hKey
0x180008c93  lea     rax, [rbp+cbData]
0x180008c97  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180008c9c  lea     r9, [rbp+Type]; lpType
0x180008ca0  lea     rax, [rbp+Data]
0x180008ca4  mov     [rbp+cbData], ebx
0x180008ca7  xor     r8d, r8d; lpReserved
0x180008caa  mov     [rsp+48h+phkResult], rax; lpData
0x180008caf  lea     rdx, aLagcounterclea; "LagCounterCleanZombie"
0x180008cb6  call    cs:__imp_RegQueryValueExW
0x180008cbc  test    eax, eax
0x180008cbe  jnz     short loc_180008CD0
0x180008cc0  cmp     [rbp+Type], ebx
0x180008cc3  jnz     short loc_180008CD0
0x180008cc5  cmp     [rbp+Data], eax
0x180008cc8  jnz     short loc_180008CD0
0x180008cca  mov     cs:?LagCounterCleanZombie@CounterHelper@@2HA, eax; int CounterHelper::LagCounterCleanZombie
0x180008cd0  mov     rcx, [rbp+hKey]; hKey
0x180008cd4  call    cs:__imp_RegCloseKey
0x180008cda  mov     eax, cs:dword_180012020
0x180008ce0  cmp     eax, ebx
0x180008ce2  jbe     short loc_180008D16
0x180008ce4  mov     eax, cs:?LagCounterImageNameFirst@CounterHelper@@2HA; int CounterHelper::LagCounterImageNameFirst
0x180008cea  lea     rdx, unk_18000F34F
0x180008cf1  mov     [rbp+arg_18], eax
0x180008cf4  lea     rax, aLagCounterRepo; "Lag counter Report Process Name First s"...
0x180008cfb  mov     [rbp+var_10], rax
0x180008cff  lea     rax, [rbp+arg_18]
0x180008d03  mov     [rsp+48h+lpcbData], rax
0x180008d08  lea     rax, [rbp+var_10]
0x180008d0c  mov     [rsp+48h+phkResult], rax
0x180008d11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180008d16  mov     eax, cs:dword_180012020
0x180008d1c  cmp     eax, ebx
0x180008d1e  jbe     short loc_180008D52
0x180008d20  mov     eax, cs:?LagCounterShowUnknown@CounterHelper@@2HA; int CounterHelper::LagCounterShowUnknown
0x180008d26  lea     rdx, unk_18000EF1B
0x180008d2d  mov     [rbp+arg_18], eax
0x180008d30  lea     rax, aLagCounterShow; "Lag counter show unknown set"
0x180008d37  mov     [rbp+var_10], rax
0x180008d3b  lea     rax, [rbp+arg_18]
0x180008d3f  mov     [rsp+48h+lpcbData], rax
0x180008d44  lea     rax, [rbp+var_10]
0x180008d48  mov     [rsp+48h+phkResult], rax
0x180008d4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180008d52  add     rsp, 48h
0x180008d56  pop     rbx
0x180008d57  pop     rbp
0x180008d58  retn
```
