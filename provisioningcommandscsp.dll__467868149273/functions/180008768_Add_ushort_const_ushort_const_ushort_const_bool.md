# Add(ushort const *,ushort const *,ushort const *,bool)

- ea: `0x180008768`
- end: `0x180008a49`
- name: `?Add@@YAXPEBG00_N@Z`
- size: `737`
- prototype: `void __fastcall(LPCWSTR lpSubKey, LPCWSTR, LPCWSTR, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008a50`

## callees

- `0x180001134`
- `0x180008768`
- `0x180008da4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008800`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000898b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000898b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008845`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000888a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800088cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008914`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008845`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000888a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800088cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008914`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008958`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008958`

## string_xrefs

- `0x180008837`: `SOFTWARE\Microsoft\Provisioning\CommandResults`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180008768  mov     rax, rsp
0x18000876b  mov     [rax+8], rbx
0x18000876f  mov     [rax+10h], rsi
0x180008773  mov     [rax+20h], r9b
0x180008777  push    rbp
0x180008778  push    rdi
0x180008779  push    r12
0x18000877b  push    r14
0x18000877d  push    r15
0x18000877f  lea     rbp, [rax-5Fh]
0x180008783  sub     rsp, 90h
0x18000878a  mov     r15, r8
0x18000878d  mov     r14, rdx
0x180008790  mov     rsi, rcx
0x180008793  xor     r12d, r12d
0x180008796  mov     [rbp+57h+hKey], r12
0x18000879a  mov     eax, cs:dword_180014230
0x1800087a0  cmp     eax, 4
0x1800087a3  jbe     short loc_1800087D8
0x1800087a5  mov     [rbp+57h+var_40], r8
0x1800087a9  mov     [rbp+57h+var_38], rdx
0x1800087ad  mov     [rbp+57h+var_30], rcx
0x1800087b1  lea     rax, [rbp+57h+var_40]
0x1800087b5  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x1800087ba  lea     rax, [rbp+57h+var_38]
0x1800087be  mov     qword ptr [rsp+0B0h+samDesired], rax
0x1800087c3  lea     rax, [rbp+57h+var_30]
0x1800087c7  mov     qword ptr [rsp+0B0h+dwOptions], rax
0x1800087cc  lea     rdx, unk_1800108E8
0x1800087d3  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800087d8  mov     rdi, [rbp+57h+hKey]
0x1800087dc  test    rdi, rdi
0x1800087df  jz      short loc_18000880C
0x1800087e1  call    cs:__imp_GetLastError
0x1800087e8  nop     dword ptr [rax+rax+00h]
0x1800087ed  mov     ebx, eax
0x1800087ef  mov     rcx, rdi; hKey
0x1800087f2  call    cs:__imp_RegCloseKey
0x1800087f9  nop     dword ptr [rax+rax+00h]
0x1800087fe  mov     ecx, ebx; dwErrCode
0x180008800  call    cs:__imp_SetLastError
0x180008807  nop     dword ptr [rax+rax+00h]
0x18000880c  mov     [rbp+57h+hKey], r12
0x180008810  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x180008815  lea     rax, [rbp+57h+hKey]
0x180008819  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18000881e  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180008823  mov     ebx, 0F003Fh
0x180008828  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x18000882c  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x180008831  xor     r9d, r9d; lpClass
0x180008834  xor     r8d, r8d; Reserved
0x180008837  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x18000883e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008845  call    cs:__imp_RegCreateKeyExW
0x18000884c  nop     dword ptr [rax+rax+00h]
0x180008851  mov     rcx, [rbp+5Fh]; this
0x180008855  test    eax, eax
0x180008857  jnz     loc_1800089F5
0x18000885d  mov     [rbp+57h+var_48], r12
0x180008861  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x180008866  lea     rax, [rbp+57h+var_48]
0x18000886a  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18000886f  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180008874  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x180008878  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x18000887d  xor     r9d, r9d; lpClass
0x180008880  xor     r8d, r8d; Reserved
0x180008883  mov     rdx, rsi; lpSubKey
0x180008886  mov     rcx, [rbp+57h+hKey]; hKey
0x18000888a  call    cs:__imp_RegCreateKeyExW
0x180008891  nop     dword ptr [rax+rax+00h]
0x180008896  mov     rcx, [rbp+5Fh]; this
0x18000889a  test    eax, eax
0x18000889c  jnz     loc_180008A0A
0x1800088a2  mov     [rbp+57h+var_50], r12
0x1800088a6  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x1800088ab  lea     rax, [rbp+57h+var_50]
0x1800088af  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800088b4  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800088b9  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x1800088bd  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x1800088c2  xor     r9d, r9d; lpClass
0x1800088c5  xor     r8d, r8d; Reserved
0x1800088c8  mov     rdx, r14; lpSubKey
0x1800088cb  mov     rcx, [rbp+57h+var_48]; hKey
0x1800088cf  call    cs:__imp_RegCreateKeyExW
0x1800088d6  nop     dword ptr [rax+rax+00h]
0x1800088db  mov     rcx, [rbp+5Fh]; this
0x1800088df  test    eax, eax
0x1800088e1  jnz     loc_180008A1F
0x1800088e7  mov     [rbp+57h+var_58], r12
0x1800088eb  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x1800088f0  lea     rax, [rbp+57h+var_58]
0x1800088f4  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800088f9  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800088fe  mov     [rsp+0B0h+samDesired], ebx; samDesired
0x180008902  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x180008907  xor     r9d, r9d; lpClass
0x18000890a  xor     r8d, r8d; Reserved
0x18000890d  mov     rdx, r15; lpSubKey
0x180008910  mov     rcx, [rbp+57h+var_50]; hKey
0x180008914  call    cs:__imp_RegCreateKeyExW
0x18000891b  nop     dword ptr [rax+rax+00h]
0x180008920  mov     rcx, [rbp+5Fh]; this
0x180008924  test    eax, eax
0x180008926  jnz     loc_180008A34
0x18000892c  mov     [rbp+57h+Data], 1
0x180008933  mov     [rsp+0B0h+samDesired], 4; cbData
0x18000893b  lea     rax, [rbp+57h+Data]
0x18000893f  mov     qword ptr [rsp+0B0h+dwOptions], rax; unsigned int
0x180008944  mov     r9d, 4; dwType
0x18000894a  xor     r8d, r8d; Reserved
0x18000894d  lea     rdx, ValueName; "State"
0x180008954  mov     rcx, [rbp+57h+var_58]; hKey
0x180008958  call    cs:__imp_RegSetValueExW
0x18000895f  nop     dword ptr [rax+rax+00h]
0x180008964  mov     rcx, [rbp+5Fh]; this
0x180008968  test    eax, eax
0x18000896a  jnz     short loc_1800089E0
0x18000896c  mov     rcx, [rbp+57h+var_58]; hKey
0x180008970  test    rcx, rcx
0x180008973  jz      short loc_180008982
0x180008975  call    cs:__imp_RegCloseKey
0x18000897c  nop     dword ptr [rax+rax+00h]
0x180008981  nop
0x180008982  mov     rcx, [rbp+57h+var_50]; hKey
0x180008986  test    rcx, rcx
0x180008989  jz      short loc_180008998
0x18000898b  call    cs:__imp_RegCloseKey
0x180008992  nop     dword ptr [rax+rax+00h]
0x180008997  nop
0x180008998  mov     rcx, [rbp+57h+var_48]; hKey
0x18000899c  test    rcx, rcx
0x18000899f  jz      short loc_1800089AE
0x1800089a1  call    cs:__imp_RegCloseKey
0x1800089a8  nop     dword ptr [rax+rax+00h]
0x1800089ad  nop
0x1800089ae  mov     rcx, [rbp+57h+hKey]; hKey
0x1800089b2  test    rcx, rcx
0x1800089b5  jz      short loc_1800089C3
0x1800089b7  call    cs:__imp_RegCloseKey
0x1800089be  nop     dword ptr [rax+rax+00h]
0x1800089c3  lea     r11, [rsp+0B0h+var_20]
0x1800089cb  mov     rbx, [r11+30h]
0x1800089cf  mov     rsi, [r11+38h]
0x1800089d3  mov     rsp, r11
0x1800089d6  pop     r15
0x1800089d8  pop     r14
0x1800089da  pop     r12
0x1800089dc  pop     rdi
0x1800089dd  pop     rbp
0x1800089de  retn
0x1800089e0  mov     r9d, eax; char *
0x1800089e3  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x1800089ea  mov     edx, 31h ; '1'; void *
0x1800089ef  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800089f5  mov     r9d, eax; char *
0x1800089f8  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x1800089ff  mov     edx, 19h; void *
0x180008a04  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180008a0a  mov     r9d, eax; char *
0x180008a0d  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008a14  mov     edx, 1Eh; void *
0x180008a19  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180008a1f  mov     r9d, eax; char *
0x180008a22  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008a29  mov     edx, 23h ; '#'; void *
0x180008a2e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180008a34  mov     r9d, eax; char *
0x180008a37  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008a3e  mov     edx, 28h ; '('; void *
0x180008a43  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
