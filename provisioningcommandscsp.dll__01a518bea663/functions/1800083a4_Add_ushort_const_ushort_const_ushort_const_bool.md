# Add(ushort const *,ushort const *,ushort const *,bool)

- ea: `0x1800083a4`
- end: `0x18000863c`
- name: `?Add@@YAXPEBG00_N@Z`
- size: `664`
- prototype: `void __fastcall(LPCWSTR lpSubKey, LPCWSTR, LPCWSTR, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008644`

## callees

- `0x18000112c`
- `0x1800083a4`
- `0x18000899c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000841d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000841d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008430`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008581`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008581`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000846f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800084ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800084ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000852c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000846f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800084ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800084ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000852c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000856a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000856a`

## string_xrefs

- `0x180008461`: `SOFTWARE\Microsoft\Provisioning\CommandResults`

## pseudocode

```c
void __fastcall Add(LPCWSTR lpSubKey, LPCWSTR a2, LPCWSTR a3, char a4)
{
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int dwOptions; // [rsp+28h] [rbp-39h]
  unsigned int dwOptionsa; // [rsp+28h] [rbp-39h]
  unsigned int dwOptionsb; // [rsp+28h] [rbp-39h]
  unsigned int dwOptionsc; // [rsp+28h] [rbp-39h]
  unsigned int dwOptionsd; // [rsp+28h] [rbp-39h]
  HKEY hKey; // [rsp+58h] [rbp-9h] BYREF
  HKEY v18; // [rsp+60h] [rbp-1h] BYREF
  HKEY v19; // [rsp+68h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+Fh] BYREF
  LPCWSTR v21; // [rsp+78h] [rbp+17h] BYREF
  LPCWSTR v22; // [rsp+80h] [rbp+1Fh] BYREF
  LPCWSTR v23[2]; // [rsp+88h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  int Data; // [rsp+E0h] [rbp+7Fh] BYREF

  LOBYTE(Data) = a4;
  hKey = 0;
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v21 = a3;
    v22 = a2;
    v23[0] = lpSubKey;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)lpSubKey,
      (unsigned int)&unk_1800108E8,
      (_DWORD)a3,
      a4,
      (__int64)v23,
      (__int64)&v22,
      (__int64)&v21);
  }
  hKey = 0;
  v7 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Provisioning\\CommandResults",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x19,
      (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
      (const char *)v7,
      dwOptions);
  phkResult = 0;
  v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1E,
      (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
      (const char *)v8,
      dwOptionsa);
  v19 = 0;
  v9 = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0xF003Fu, 0, &v19, 0);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x23,
      (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
      (const char *)v9,
      dwOptionsb);
  v18 = 0;
  v10 = RegCreateKeyExW(v19, a3, 0, 0, 0, 0xF003Fu, 0, &v18, 0);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x28,
      (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
      (const char *)v10,
      dwOptionsc);
  Data = 1;
  v11 = RegSetValueExW(v18, L"State", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x31,
      (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
      (const char *)v11,
      dwOptionsd);
  if ( v18 )
    RegCloseKey(v18);
  if ( v19 )
    RegCloseKey(v19);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800083a4  mov     rax, rsp
0x1800083a7  mov     [rax+8], rbx
0x1800083ab  mov     [rax+10h], rsi
0x1800083af  mov     [rax+20h], r9b
0x1800083b3  push    rbp
0x1800083b4  push    rdi
0x1800083b5  push    r12
0x1800083b7  push    r14
0x1800083b9  push    r15
0x1800083bb  lea     rbp, [rax-5Fh]
0x1800083bf  sub     rsp, 90h
0x1800083c6  mov     r15, r8
0x1800083c9  mov     r14, rdx
0x1800083cc  mov     rsi, rcx
0x1800083cf  xor     r12d, r12d
0x1800083d2  mov     [rbp+57h+hKey], r12
0x1800083d6  mov     eax, cs:dword_180014230
0x1800083dc  cmp     eax, 4
0x1800083df  jbe     short loc_180008414
0x1800083e1  mov     [rbp+57h+var_40], r8
0x1800083e5  mov     [rbp+57h+var_38], rdx
0x1800083e9  mov     [rbp+57h+var_30], rcx
0x1800083ed  lea     rax, [rbp+57h+var_40]
0x1800083f1  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x1800083f6  lea     rax, [rbp+57h+var_38]
0x1800083fa  mov     qword ptr [rsp+0B0h+samDesired], rax
0x1800083ff  lea     rax, [rbp+57h+var_30]
0x180008403  mov     qword ptr [rsp+0B0h+dwOptions], rax
0x180008408  lea     rdx, unk_1800108E8
0x18000840f  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180008414  mov     rdi, [rbp+57h+hKey]
0x180008418  test    rdi, rdi
0x18000841b  jz      short loc_180008436
0x18000841d  call    cs:__imp_GetLastError
0x180008423  mov     ebx, eax
0x180008425  mov     rcx, rdi; hKey
0x180008428  call    cs:__imp_RegCloseKey
0x18000842e  mov     ecx, ebx; dwErrCode
0x180008430  call    cs:__imp_SetLastError
0x180008436  mov     [rbp+57h+hKey], r12
0x18000843a  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x18000843f  lea     rax, [rbp+57h+hKey]
0x180008443  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180008448  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000844d  mov     ebx, 0F003Fh
0x180008452  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x180008456  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x18000845b  xor     r9d, r9d; lpClass
0x18000845e  xor     r8d, r8d; Reserved
0x180008461  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x180008468  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000846f  call    cs:__imp_RegCreateKeyExW
0x180008475  mov     rcx, [rbp+5Fh]; this
0x180008479  test    eax, eax
0x18000847b  jnz     loc_1800085E8
0x180008481  mov     [rbp+57h+var_48], r12
0x180008485  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x18000848a  lea     rax, [rbp+57h+var_48]
0x18000848e  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180008493  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180008498  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x18000849c  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x1800084a1  xor     r9d, r9d; lpClass
0x1800084a4  xor     r8d, r8d; Reserved
0x1800084a7  mov     rdx, rsi; lpSubKey
0x1800084aa  mov     rcx, [rbp+57h+hKey]; hKey
0x1800084ae  call    cs:__imp_RegCreateKeyExW
0x1800084b4  mov     rcx, [rbp+5Fh]; this
0x1800084b8  test    eax, eax
0x1800084ba  jnz     loc_1800085FD
0x1800084c0  mov     [rbp+57h+var_50], r12
0x1800084c4  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x1800084c9  lea     rax, [rbp+57h+var_50]
0x1800084cd  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800084d2  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800084d7  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x1800084db  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x1800084e0  xor     r9d, r9d; lpClass
0x1800084e3  xor     r8d, r8d; Reserved
0x1800084e6  mov     rdx, r14; lpSubKey
0x1800084e9  mov     rcx, [rbp+57h+var_48]; hKey
0x1800084ed  call    cs:__imp_RegCreateKeyExW
0x1800084f3  mov     rcx, [rbp+5Fh]; this
0x1800084f7  test    eax, eax
0x1800084f9  jnz     loc_180008612
0x1800084ff  mov     [rbp+57h+var_58], r12
0x180008503  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x180008508  lea     rax, [rbp+57h+var_58]
0x18000850c  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180008511  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180008516  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x18000851a  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x18000851f  xor     r9d, r9d; lpClass
0x180008522  xor     r8d, r8d; Reserved
0x180008525  mov     rdx, r15; lpSubKey
0x180008528  mov     rcx, [rbp+57h+var_50]; hKey
0x18000852c  call    cs:__imp_RegCreateKeyExW
0x180008532  mov     rcx, [rbp+5Fh]; this
0x180008536  test    eax, eax
0x180008538  jnz     loc_180008627
0x18000853e  mov     [rbp+57h+Data], 1
0x180008545  mov     [rsp+0B0h+samDesired], 4; cbData
0x18000854d  lea     rax, [rbp+57h+Data]
0x180008551  mov     qword ptr [rsp+0B0h+dwOptions], rax; unsigned int
0x180008556  mov     r9d, 4; dwType
0x18000855c  xor     r8d, r8d; Reserved
0x18000855f  lea     rdx, ValueName; "State"
0x180008566  mov     rcx, [rbp+57h+var_58]; hKey
0x18000856a  call    cs:__imp_RegSetValueExW
0x180008570  mov     rcx, [rbp+5Fh]; this
0x180008574  test    eax, eax
0x180008576  jnz     short loc_1800085D3
0x180008578  mov     rcx, [rbp+57h+var_58]; hKey
0x18000857c  test    rcx, rcx
0x18000857f  jz      short loc_180008588
0x180008581  call    cs:__imp_RegCloseKey
0x180008587  nop
0x180008588  mov     rcx, [rbp+57h+var_50]; hKey
0x18000858c  test    rcx, rcx
0x18000858f  jz      short loc_180008598
0x180008591  call    cs:__imp_RegCloseKey
0x180008597  nop
0x180008598  mov     rcx, [rbp+57h+var_48]; hKey
0x18000859c  test    rcx, rcx
0x18000859f  jz      short loc_1800085A8
0x1800085a1  call    cs:__imp_RegCloseKey
0x1800085a7  nop
0x1800085a8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800085ac  test    rcx, rcx
0x1800085af  jz      short loc_1800085B7
0x1800085b1  call    cs:__imp_RegCloseKey
0x1800085b7  lea     r11, [rsp+0B0h+var_20]
0x1800085bf  mov     rbx, [r11+30h]
0x1800085c3  mov     rsi, [r11+38h]
0x1800085c7  mov     rsp, r11
0x1800085ca  pop     r15
0x1800085cc  pop     r14
0x1800085ce  pop     r12
0x1800085d0  pop     rdi
0x1800085d1  pop     rbp
0x1800085d2  retn
0x1800085d3  mov     r9d, eax; char *
0x1800085d6  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x1800085dd  mov     edx, 31h ; '1'; void *
0x1800085e2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800085e8  mov     r9d, eax; char *
0x1800085eb  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x1800085f2  mov     edx, 19h; void *
0x1800085f7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800085fd  mov     r9d, eax; char *
0x180008600  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008607  mov     edx, 1Eh; void *
0x18000860c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180008612  mov     r9d, eax; char *
0x180008615  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x18000861c  mov     edx, 23h ; '#'; void *
0x180008621  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180008627  mov     r9d, eax; char *
0x18000862a  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008631  mov     edx, 28h ; '('; void *
0x180008636  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
