# RegistryConfig::Delete(ushort const *,ushort const *,ushort const *)

- ea: `0x18000acc4`
- end: `0x18000af42`
- name: `?Delete@RegistryConfig@@QEAAXPEBG00@Z`
- size: `638`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180008cc0`

## callees

- `0x1800013d0`
- `0x18000899c`
- `0x18000ac58`
- `0x18000acc4`
- `0x18000c600`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aeaa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aee1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aeaa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aecf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aecf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000ae08`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000ae91`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000ae08`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000ae91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ad59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ad59`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ae71`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ae71`

## string_xrefs

- `0x18000af06`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000af1b`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000af30`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
void __fastcall RegistryConfig::Delete(
        RegistryConfig *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char *v7; // rbx
  char *v8; // r9
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  LPCWSTR *v11; // r9
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  LPCWSTR *v15; // rax
  const WCHAR *v16; // rdx
  unsigned int v17; // eax
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  DWORD cSubKeys; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR *v25; // [rsp+70h] [rbp-49h] BYREF
  const unsigned __int16 *v26; // [rsp+78h] [rbp-41h] BYREF
  const unsigned __int16 *v27; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v28[2]; // [rsp+88h] [rbp-31h] BYREF
  LPCWSTR v29[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v30; // [rsp+A8h] [rbp-11h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v32; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v7 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) < 8u )
    v8 = (char *)this + 8;
  else
    v8 = *(char **)v7;
  RegistryConfig::AppendStrings((__int64)this, lpSubKey, 5, v8, L"\\", a2, L"\\", a3);
  hKey = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( v32 >= 8 )
    v9 = lpSubKey[0];
  v10 = RegOpenKeyExW(*(HKEY *)this, v9, 0, 0xF003Fu, &hKey);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x95,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v10,
      phkResult);
  v11 = lpSubKey;
  if ( v32 >= 8 )
    v11 = (LPCWSTR *)lpSubKey[0];
  RegistryConfig::AppendStrings((__int64)this, v29, 3, v11, L"\\", a4);
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v15 = v29;
    if ( v30 >= 8 )
      v15 = (LPCWSTR *)v29[0];
    v25 = v15;
    v26 = a4;
    v27 = a3;
    if ( *((_QWORD *)v7 + 3) >= 8u )
      v7 = *(char **)v7;
    *(_QWORD *)v28 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v12,
      (unsigned int)&dword_180010C54,
      v13,
      v14,
      (__int64)v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  v16 = (const WCHAR *)v29;
  if ( v30 >= 8 )
    v16 = v29[0];
  v17 = RegDeleteTreeW(*(HKEY *)this, v16);
  if ( v17 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xA0,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v17,
      phkResulta);
  cSubKeys = 0;
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) && !cSubKeys )
  {
    v18 = (const WCHAR *)lpSubKey;
    if ( v32 >= 8 )
      v18 = lpSubKey[0];
    v19 = RegDeleteTreeW(*(HKEY *)this, v18);
    if ( v19 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xA8,
        (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
        (const char *)v19,
        phkResultb);
  }
  if ( v30 >= 8 )
    operator delete((void *)v29[0]);
  v30 = 7;
  v29[2] = 0;
  LOWORD(v29[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v32 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x18000acc4  push    rbp
0x18000acc6  push    rbx
0x18000acc7  push    rsi
0x18000acc8  push    rdi
0x18000acc9  push    r12
0x18000accb  push    r14
0x18000accd  lea     rbp, [rsp-2Fh]
0x18000acd2  sub     rsp, 0E8h
0x18000acd9  mov     rax, cs:__security_cookie
0x18000ace0  xor     rax, rsp
0x18000ace3  mov     [rbp+57h+var_40], rax
0x18000ace7  mov     rsi, r9
0x18000acea  mov     r14, r8
0x18000aced  mov     rdi, rcx
0x18000acf0  lea     rbx, [rcx+8]
0x18000acf4  cmp     qword ptr [rbx+18h], 8
0x18000acf9  jb      short loc_18000AD00
0x18000acfb  mov     r9, [rbx]
0x18000acfe  jmp     short loc_18000AD03
0x18000ad00  mov     r9, rbx
0x18000ad03  mov     [rsp+110h+lpcValues], r14
0x18000ad08  lea     r12, asc_180010164; "\\"
0x18000ad0f  mov     [rsp+110h+lpcbMaxClassLen], r12
0x18000ad14  mov     [rsp+110h+lpcbMaxSubKeyLen], rdx
0x18000ad19  mov     [rsp+110h+phkResult], r12
0x18000ad1e  mov     r8d, 5
0x18000ad24  lea     rdx, [rbp+57h+lpSubKey]
0x18000ad28  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000ad2d  nop
0x18000ad2e  mov     [rbp+57h+hKey], 0
0x18000ad36  lea     rdx, [rbp+57h+lpSubKey]
0x18000ad3a  cmp     [rbp+57h+var_48], 8
0x18000ad3f  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000ad44  lea     rax, [rbp+57h+hKey]
0x18000ad48  mov     [rsp+110h+phkResult], rax; unsigned int
0x18000ad4d  mov     r9d, 0F003Fh; samDesired
0x18000ad53  xor     r8d, r8d; ulOptions
0x18000ad56  mov     rcx, [rdi]; hKey
0x18000ad59  call    cs:__imp_RegOpenKeyExW
0x18000ad5f  mov     rcx, [rbp+5Fh]; this
0x18000ad63  test    eax, eax
0x18000ad65  jnz     loc_18000AF18
0x18000ad6b  lea     r9, [rbp+57h+lpSubKey]
0x18000ad6f  cmp     [rbp+57h+var_48], 8
0x18000ad74  cmovnb  r9, [rbp+57h+lpSubKey]
0x18000ad79  mov     [rsp+110h+lpcbMaxSubKeyLen], rsi
0x18000ad7e  mov     [rsp+110h+phkResult], r12
0x18000ad83  lea     r8d, [rax+3]
0x18000ad87  lea     rdx, [rbp+57h+var_80]
0x18000ad8b  mov     rcx, rdi
0x18000ad8e  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000ad93  nop
0x18000ad94  mov     eax, cs:dword_180014230
0x18000ad9a  cmp     eax, 4
0x18000ad9d  jbe     short loc_18000ADF7
0x18000ad9f  lea     rax, [rbp+57h+var_80]
0x18000ada3  cmp     [rbp+57h+var_68], 8
0x18000ada8  cmovnb  rax, [rbp+57h+var_80]
0x18000adad  mov     [rbp+57h+var_A0], rax
0x18000adb1  mov     [rbp+57h+var_98], rsi
0x18000adb5  mov     [rbp+57h+var_90], r14
0x18000adb9  cmp     qword ptr [rbx+18h], 8
0x18000adbe  jb      short loc_18000ADC3
0x18000adc0  mov     rbx, [rbx]
0x18000adc3  mov     qword ptr [rbp+57h+var_88], rbx
0x18000adc7  lea     rax, [rbp+57h+var_A0]
0x18000adcb  mov     [rsp+110h+lpcValues], rax
0x18000add0  lea     rax, [rbp+57h+var_98]
0x18000add4  mov     [rsp+110h+lpcbMaxClassLen], rax
0x18000add9  lea     rax, [rbp+57h+var_90]
0x18000addd  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18000ade2  lea     rax, [rbp+57h+var_88]
0x18000ade6  mov     [rsp+110h+phkResult], rax; unsigned int
0x18000adeb  lea     rdx, dword_180010C54
0x18000adf2  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000adf7  lea     rdx, [rbp+57h+var_80]
0x18000adfb  cmp     [rbp+57h+var_68], 8
0x18000ae00  cmovnb  rdx, [rbp+57h+var_80]; lpSubKey
0x18000ae05  mov     rcx, [rdi]; hKey
0x18000ae08  call    cs:__imp_RegDeleteTreeW
0x18000ae0e  mov     rcx, [rbp+5Fh]; this
0x18000ae12  test    eax, eax
0x18000ae14  jnz     loc_18000AF2D
0x18000ae1a  mov     [rbp+57h+cSubKeys], eax
0x18000ae1d  mov     [rsp+110h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000ae26  mov     [rsp+110h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000ae2f  mov     [rsp+110h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000ae38  mov     [rsp+110h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000ae41  mov     [rsp+110h+lpcValues], 0; lpcValues
0x18000ae4a  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000ae53  mov     [rsp+110h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000ae5c  lea     rax, [rbp+57h+cSubKeys]
0x18000ae60  mov     [rsp+110h+phkResult], rax; unsigned int
0x18000ae65  xor     r9d, r9d; lpReserved
0x18000ae68  xor     r8d, r8d; lpcchClass
0x18000ae6b  xor     edx, edx; lpClass
0x18000ae6d  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ae71  call    cs:__imp_RegQueryInfoKeyW
0x18000ae77  test    eax, eax
0x18000ae79  jnz     short loc_18000AE9F
0x18000ae7b  cmp     [rbp+57h+cSubKeys], eax
0x18000ae7e  jnz     short loc_18000AE9F
0x18000ae80  lea     rdx, [rbp+57h+lpSubKey]
0x18000ae84  cmp     [rbp+57h+var_48], 8
0x18000ae89  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000ae8e  mov     rcx, [rdi]; hKey
0x18000ae91  call    cs:__imp_RegDeleteTreeW
0x18000ae97  mov     rcx, [rbp+5Fh]; this
0x18000ae9b  test    eax, eax
0x18000ae9d  jnz     short loc_18000AF03
0x18000ae9f  cmp     [rbp+57h+var_68], 8
0x18000aea4  jb      short loc_18000AEB0
0x18000aea6  mov     rcx, [rbp+57h+var_80]
0x18000aeaa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aeb0  mov     [rbp+57h+var_68], 7
0x18000aeb8  mov     [rbp+57h+var_70], 0
0x18000aec0  xor     eax, eax
0x18000aec2  mov     word ptr [rbp+57h+var_80], ax
0x18000aec6  mov     rcx, [rbp+57h+hKey]; hKey
0x18000aeca  test    rcx, rcx
0x18000aecd  jz      short loc_18000AED6
0x18000aecf  call    cs:__imp_RegCloseKey
0x18000aed5  nop
0x18000aed6  cmp     [rbp+57h+var_48], 8
0x18000aedb  jb      short loc_18000AEE7
0x18000aedd  mov     rcx, [rbp+57h+lpSubKey]
0x18000aee1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aee7  mov     rcx, [rbp+57h+var_40]
0x18000aeeb  xor     rcx, rsp; StackCookie
0x18000aeee  call    __security_check_cookie
0x18000aef3  add     rsp, 0E8h
0x18000aefa  pop     r14
0x18000aefc  pop     r12
0x18000aefe  pop     rdi
0x18000aeff  pop     rsi
0x18000af00  pop     rbx
0x18000af01  pop     rbp
0x18000af02  retn
0x18000af03  mov     r9d, eax; char *
0x18000af06  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000af0d  mov     edx, 0A8h; void *
0x18000af12  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000af18  mov     r9d, eax; char *
0x18000af1b  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000af22  mov     edx, 95h; void *
0x18000af27  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000af2d  mov     r9d, eax; char *
0x18000af30  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000af37  mov     edx, 0A0h; void *
0x18000af3c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
