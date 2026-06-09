# RegistryConfig::AddCommand(ushort const *,ushort const *,Command const *)

- ea: `0x18000a7f8`
- end: `0x18000aa8e`
- name: `?AddCommand@RegistryConfig@@QEAAXPEBG0PEBUCommand@@@Z`
- size: `662`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, const unsigned __int16 *, const struct Command *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x1800013d0`
- `0x180007800`
- `0x18000899c`
- `0x18000a7f8`
- `0x18000ac58`
- `0x18000c600`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aa1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aa1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a916`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a929`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a8f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a8f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a970`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a970`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a9e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a9e1`

## string_xrefs

- `0x18000a9d6`: `WorkingDirectory`
- `0x18000aa3d`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000aa52`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000aa67`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000aa79`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
void __fastcall RegistryConfig::AddCommand(
        HKEY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct Command *a4)
{
  _QWORD *v6; // rax
  const struct Command *v7; // rax
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  DWORD v13; // ecx
  char *v14; // rdi
  unsigned int v15; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-21h] BYREF
  HKEY v21; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v22; // [rsp+68h] [rbp-11h] BYREF
  const struct Command *v23; // [rsp+70h] [rbp-9h] BYREF
  const unsigned __int16 *v24; // [rsp+78h] [rbp-1h] BYREF
  const unsigned __int16 *v25; // [rsp+80h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+88h] [rbp+Fh] BYREF
  unsigned __int64 v27; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( (unsigned int)dword_180014230 > 4 )
  {
    v6 = (_QWORD *)((char *)a4 + 64);
    if ( *((_QWORD *)a4 + 11) >= 8u )
      v6 = (_QWORD *)*v6;
    v22 = v6;
    if ( *((_QWORD *)a4 + 3) < 8u )
      v7 = a4;
    else
      v7 = *(const struct Command **)a4;
    v23 = v7;
    v24 = a3;
    v25 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)this,
      (unsigned int)&byte_180010CA7,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22);
  }
  RegistryConfig::AppendStrings(this, lpSubKey, 5);
  hKey = 0;
  v21 = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v27 >= 8 )
    v8 = lpSubKey[0];
  v9 = RegOpenKeyExW(*this, v8, 0, 0xF003Fu, &v21);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x62,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v9,
      phkResult);
  dwDisposition = 0;
  hKey = 0;
  if ( *((_QWORD *)a4 + 3) < 8u )
    v10 = (const WCHAR *)a4;
  else
    v10 = *(const WCHAR **)a4;
  v11 = RegCreateKeyExW(v21, v10, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x67,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v11,
      phkResulta);
  v12 = 2LL * *((_QWORD *)a4 + 10) + 2;
  v13 = 2 * *((_DWORD *)a4 + 20) + 2;
  if ( v12 > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      v12 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      phkResulta);
  v14 = (char *)a4 + 64;
  if ( *((_QWORD *)v14 + 3) >= 8u )
    v14 = *(char **)v14;
  v15 = RegSetValueExW(hKey, L"WorkingDirectory", 0, 1u, (const BYTE *)v14, v13);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x72,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v15,
      phkResultb);
  if ( v21 )
    RegCloseKey(v21);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v27 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x18000a7f8  push    rbp
0x18000a7fa  push    rbx
0x18000a7fb  push    rsi
0x18000a7fc  push    rdi
0x18000a7fd  push    r14
0x18000a7ff  lea     rbp, [rsp-37h]
0x18000a804  sub     rsp, 0B0h
0x18000a80b  mov     rax, cs:__security_cookie
0x18000a812  xor     rax, rsp
0x18000a815  mov     [rbp+57h+var_28], rax
0x18000a819  mov     rdi, r9
0x18000a81c  mov     r14, r8
0x18000a81f  mov     rsi, rdx
0x18000a822  mov     rbx, rcx
0x18000a825  mov     eax, cs:dword_180014230
0x18000a82b  cmp     eax, 4
0x18000a82e  jbe     short loc_18000A88D
0x18000a830  lea     rax, [r9+40h]
0x18000a834  cmp     qword ptr [rax+18h], 8
0x18000a839  jb      short loc_18000A83E
0x18000a83b  mov     rax, [rax]
0x18000a83e  mov     [rbp+57h+var_68], rax
0x18000a842  cmp     qword ptr [r9+18h], 8
0x18000a847  jb      short loc_18000A84E
0x18000a849  mov     rax, [r9]
0x18000a84c  jmp     short loc_18000A851
0x18000a84e  mov     rax, rdi
0x18000a851  mov     [rbp+57h+var_60], rax
0x18000a855  mov     [rbp+57h+var_58], r14
0x18000a859  mov     [rbp+57h+var_50], rsi
0x18000a85d  lea     rax, [rbp+57h+var_68]
0x18000a861  mov     [rsp+0D0h+var_98], rax
0x18000a866  lea     rax, [rbp+57h+var_60]
0x18000a86a  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x18000a86f  lea     rax, [rbp+57h+var_58]
0x18000a873  mov     qword ptr [rsp+0D0h+samDesired], rax
0x18000a878  lea     rax, [rbp+57h+var_50]
0x18000a87c  mov     [rsp+0D0h+phkResult], rax
0x18000a881  lea     rdx, byte_180010CA7
0x18000a888  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000a88d  lea     r9, [rbx+8]
0x18000a891  cmp     qword ptr [r9+18h], 8
0x18000a896  jb      short loc_18000A89B
0x18000a898  mov     r9, [r9]
0x18000a89b  mov     [rsp+0D0h+var_98], r14
0x18000a8a0  lea     rax, asc_180010164; "\\"
0x18000a8a7  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x18000a8ac  mov     qword ptr [rsp+0D0h+samDesired], rsi
0x18000a8b1  mov     [rsp+0D0h+phkResult], rax
0x18000a8b6  mov     r8d, 5
0x18000a8bc  lea     rdx, [rbp+57h+lpSubKey]
0x18000a8c0  mov     rcx, rbx
0x18000a8c3  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000a8c8  nop
0x18000a8c9  xor     r14d, r14d
0x18000a8cc  mov     [rbp+57h+hKey], r14
0x18000a8d0  mov     [rbp+57h+var_70], r14
0x18000a8d4  lea     rdx, [rbp+57h+lpSubKey]
0x18000a8d8  cmp     [rbp+57h+var_30], 8
0x18000a8dd  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000a8e2  lea     rax, [rbp+57h+var_70]
0x18000a8e6  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18000a8eb  mov     r9d, 0F003Fh; samDesired
0x18000a8f1  xor     r8d, r8d; ulOptions
0x18000a8f4  mov     rcx, [rbx]; hKey
0x18000a8f7  call    cs:__imp_RegOpenKeyExW
0x18000a8fd  mov     rcx, [rbp+5Fh]; this
0x18000a901  test    eax, eax
0x18000a903  jnz     loc_18000AA4F
0x18000a909  mov     [rbp+57h+dwDisposition], r14d
0x18000a90d  mov     rsi, [rbp+57h+hKey]
0x18000a911  test    rsi, rsi
0x18000a914  jz      short loc_18000A92F
0x18000a916  call    cs:__imp_GetLastError
0x18000a91c  mov     ebx, eax
0x18000a91e  mov     rcx, rsi; hKey
0x18000a921  call    cs:__imp_RegCloseKey
0x18000a927  mov     ecx, ebx; dwErrCode
0x18000a929  call    cs:__imp_SetLastError
0x18000a92f  mov     [rbp+57h+hKey], r14
0x18000a933  cmp     qword ptr [rdi+18h], 8
0x18000a938  jb      short loc_18000A93F
0x18000a93a  mov     rdx, [rdi]
0x18000a93d  jmp     short loc_18000A942
0x18000a93f  mov     rdx, rdi; lpSubKey
0x18000a942  lea     rax, [rbp+57h+dwDisposition]
0x18000a946  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18000a94b  lea     rax, [rbp+57h+hKey]
0x18000a94f  mov     [rsp+0D0h+var_98], rax; phkResult
0x18000a954  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000a959  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x18000a961  mov     dword ptr [rsp+0D0h+phkResult], r14d; int
0x18000a966  xor     r9d, r9d; lpClass
0x18000a969  xor     r8d, r8d; Reserved
0x18000a96c  mov     rcx, [rbp+57h+var_70]; hKey
0x18000a970  call    cs:__imp_RegCreateKeyExW
0x18000a976  mov     rcx, [rbp+5Fh]; this
0x18000a97a  test    eax, eax
0x18000a97c  jnz     loc_18000AA64
0x18000a982  mov     rax, [rdi+50h]
0x18000a986  lea     rax, ds:2[rax*2]
0x18000a98e  mov     edx, 0FFFFFFFFh
0x18000a993  cmp     rax, rdx
0x18000a996  mov     ecx, eax
0x18000a998  jbe     short loc_18000A99C
0x18000a99a  mov     ecx, edx
0x18000a99c  cmp     rdx, rax
0x18000a99f  sbb     r9d, r9d
0x18000a9a2  and     r9d, 80070216h; char *
0x18000a9a9  mov     r10, [rbp+5Fh]
0x18000a9ad  cmp     rax, rdx
0x18000a9b0  ja      loc_18000AA79
0x18000a9b6  add     rdi, 40h ; '@'
0x18000a9ba  cmp     qword ptr [rdi+18h], 8
0x18000a9bf  jb      short loc_18000A9C4
0x18000a9c1  mov     rdi, [rdi]
0x18000a9c4  mov     [rsp+0D0h+samDesired], ecx; cbData
0x18000a9c8  mov     [rsp+0D0h+phkResult], rdi; unsigned int
0x18000a9cd  mov     r9d, 1; dwType
0x18000a9d3  xor     r8d, r8d; Reserved
0x18000a9d6  lea     rdx, aWorkingdirecto; "WorkingDirectory"
0x18000a9dd  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a9e1  call    cs:__imp_RegSetValueExW
0x18000a9e7  mov     rcx, [rbp+5Fh]; this
0x18000a9eb  test    eax, eax
0x18000a9ed  jnz     short loc_18000AA3A
0x18000a9ef  mov     rcx, [rbp+57h+var_70]; hKey
0x18000a9f3  test    rcx, rcx
0x18000a9f6  jz      short loc_18000A9FF
0x18000a9f8  call    cs:__imp_RegCloseKey
0x18000a9fe  nop
0x18000a9ff  mov     rcx, [rbp+57h+hKey]; hKey
0x18000aa03  test    rcx, rcx
0x18000aa06  jz      short loc_18000AA0F
0x18000aa08  call    cs:__imp_RegCloseKey
0x18000aa0e  nop
0x18000aa0f  cmp     [rbp+57h+var_30], 8
0x18000aa14  jb      short loc_18000AA20
0x18000aa16  mov     rcx, [rbp+57h+lpSubKey]
0x18000aa1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aa20  mov     rcx, [rbp+57h+var_28]
0x18000aa24  xor     rcx, rsp; StackCookie
0x18000aa27  call    __security_check_cookie
0x18000aa2c  add     rsp, 0B0h
0x18000aa33  pop     r14
0x18000aa35  pop     rdi
0x18000aa36  pop     rsi
0x18000aa37  pop     rbx
0x18000aa38  pop     rbp
0x18000aa39  retn
0x18000aa3a  mov     r9d, eax; char *
0x18000aa3d  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000aa44  mov     edx, 72h ; 'r'; void *
0x18000aa49  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000aa4f  mov     r9d, eax; char *
0x18000aa52  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000aa59  mov     edx, 62h ; 'b'; void *
0x18000aa5e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000aa64  mov     r9d, eax; char *
0x18000aa67  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000aa6e  mov     edx, 67h ; 'g'; void *
0x18000aa73  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000aa79  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000aa80  mov     edx, 6Dh ; 'm'; void *
0x18000aa85  mov     rcx, r10; this
0x18000aa88  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
