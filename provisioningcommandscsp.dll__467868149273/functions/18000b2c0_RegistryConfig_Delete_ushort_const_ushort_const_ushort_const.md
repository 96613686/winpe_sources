# RegistryConfig::Delete(ushort const *,ushort const *,ushort const *)

- ea: `0x18000b2c0`
- end: `0x18000b569`
- name: `?Delete@RegistryConfig@@QEAAXPEBG00@Z`
- size: `681`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800090e0`

## callees

- `0x1800013e0`
- `0x180008da4`
- `0x18000b254`
- `0x18000b2c0`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b501`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b501`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4e9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b40a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b49f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b40a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b49f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b355`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b355`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b479`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b479`

## string_xrefs

- `0x18000b52d`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b542`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b557`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RegistryConfig::Delete(
        HKEY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rbx
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  LPCWSTR *v13; // rax
  const WCHAR *v14; // rdx
  unsigned int v15; // eax
  const WCHAR *v16; // rdx
  unsigned int v17; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  PHKEY phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  DWORD cSubKeys; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR *v23; // [rsp+70h] [rbp-49h] BYREF
  const unsigned __int16 *v24; // [rsp+78h] [rbp-41h] BYREF
  const unsigned __int16 *v25; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v26[2]; // [rsp+88h] [rbp-31h] BYREF
  LPCWSTR v27[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v28; // [rsp+A8h] [rbp-11h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v30; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v7 = this + 1;
  RegistryConfig::AppendStrings(this, lpSubKey, 5);
  hKey = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v30 >= 8 )
    v8 = lpSubKey[0];
  v9 = RegOpenKeyExW(*this, v8, 0, 0xF003Fu, &hKey);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x95,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v9,
      phkResult);
  phkResulta = (PHKEY)L"\\";
  RegistryConfig::AppendStrings(this, v27, 3);
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v13 = v27;
    if ( v28 >= 8 )
      v13 = (LPCWSTR *)v27[0];
    v23 = v13;
    v24 = a4;
    v25 = a3;
    if ( v7[3] >= 8u )
      v7 = (_QWORD *)*v7;
    *(_QWORD *)v26 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v10,
      (unsigned int)&dword_180010C54,
      v11,
      v12,
      (__int64)v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23);
  }
  v14 = (const WCHAR *)v27;
  if ( v28 >= 8 )
    v14 = v27[0];
  v15 = RegDeleteTreeW(*this, v14);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xA0,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v15,
      (unsigned int)phkResulta);
  cSubKeys = 0;
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) && !cSubKeys )
  {
    v16 = (const WCHAR *)lpSubKey;
    if ( v30 >= 8 )
      v16 = lpSubKey[0];
    v17 = RegDeleteTreeW(*this, v16);
    if ( v17 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xA8,
        (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
        (const char *)v17,
        phkResultb);
  }
  if ( v28 >= 8 )
    operator delete((void *)v27[0]);
  v28 = 7;
  v27[2] = 0;
  LOWORD(v27[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v30 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x18000b2c0  push    rbp
0x18000b2c2  push    rbx
0x18000b2c3  push    rsi
0x18000b2c4  push    rdi
0x18000b2c5  push    r12
0x18000b2c7  push    r14
0x18000b2c9  lea     rbp, [rsp-2Fh]
0x18000b2ce  sub     rsp, 0E8h
0x18000b2d5  mov     rax, cs:__security_cookie
0x18000b2dc  xor     rax, rsp
0x18000b2df  mov     [rbp+57h+var_40], rax
0x18000b2e3  mov     rsi, r9
0x18000b2e6  mov     r14, r8
0x18000b2e9  mov     rdi, rcx
0x18000b2ec  lea     rbx, [rcx+8]
0x18000b2f0  cmp     qword ptr [rbx+18h], 8
0x18000b2f5  jb      short loc_18000B2FC
0x18000b2f7  mov     r9, [rbx]
0x18000b2fa  jmp     short loc_18000B2FF
0x18000b2fc  mov     r9, rbx
0x18000b2ff  mov     [rsp+110h+lpcValues], r14
0x18000b304  lea     r12, asc_180010164; "\\"
0x18000b30b  mov     [rsp+110h+lpcbMaxClassLen], r12
0x18000b310  mov     [rsp+110h+lpcbMaxSubKeyLen], rdx
0x18000b315  mov     [rsp+110h+phkResult], r12
0x18000b31a  mov     r8d, 5
0x18000b320  lea     rdx, [rbp+57h+lpSubKey]
0x18000b324  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000b329  nop
0x18000b32a  mov     [rbp+57h+hKey], 0
0x18000b332  lea     rdx, [rbp+57h+lpSubKey]
0x18000b336  cmp     [rbp+57h+var_48], 8
0x18000b33b  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000b340  lea     rax, [rbp+57h+hKey]
0x18000b344  mov     [rsp+110h+phkResult], rax; unsigned int
0x18000b349  mov     r9d, 0F003Fh; samDesired
0x18000b34f  xor     r8d, r8d; ulOptions
0x18000b352  mov     rcx, [rdi]; hKey
0x18000b355  call    cs:__imp_RegOpenKeyExW
0x18000b35c  nop     dword ptr [rax+rax+00h]
0x18000b361  mov     rcx, [rbp+5Fh]; this
0x18000b365  test    eax, eax
0x18000b367  jnz     loc_18000B53F
0x18000b36d  lea     r9, [rbp+57h+lpSubKey]
0x18000b371  cmp     [rbp+57h+var_48], 8
0x18000b376  cmovnb  r9, [rbp+57h+lpSubKey]
0x18000b37b  mov     [rsp+110h+lpcbMaxSubKeyLen], rsi
0x18000b380  mov     [rsp+110h+phkResult], r12
0x18000b385  lea     r8d, [rax+3]
0x18000b389  lea     rdx, [rbp+57h+var_80]
0x18000b38d  mov     rcx, rdi
0x18000b390  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000b395  nop
0x18000b396  mov     eax, cs:dword_180014230
0x18000b39c  cmp     eax, 4
0x18000b39f  jbe     short loc_18000B3F9
0x18000b3a1  lea     rax, [rbp+57h+var_80]
0x18000b3a5  cmp     [rbp+57h+var_68], 8
0x18000b3aa  cmovnb  rax, [rbp+57h+var_80]
0x18000b3af  mov     [rbp+57h+var_A0], rax
0x18000b3b3  mov     [rbp+57h+var_98], rsi
0x18000b3b7  mov     [rbp+57h+var_90], r14
0x18000b3bb  cmp     qword ptr [rbx+18h], 8
0x18000b3c0  jb      short loc_18000B3C5
0x18000b3c2  mov     rbx, [rbx]
0x18000b3c5  mov     qword ptr [rbp+57h+var_88], rbx
0x18000b3c9  lea     rax, [rbp+57h+var_A0]
0x18000b3cd  mov     [rsp+110h+lpcValues], rax
0x18000b3d2  lea     rax, [rbp+57h+var_98]
0x18000b3d6  mov     [rsp+110h+lpcbMaxClassLen], rax
0x18000b3db  lea     rax, [rbp+57h+var_90]
0x18000b3df  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18000b3e4  lea     rax, [rbp+57h+var_88]
0x18000b3e8  mov     [rsp+110h+phkResult], rax; unsigned int
0x18000b3ed  lea     rdx, dword_180010C54
0x18000b3f4  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b3f9  lea     rdx, [rbp+57h+var_80]
0x18000b3fd  cmp     [rbp+57h+var_68], 8
0x18000b402  cmovnb  rdx, [rbp+57h+var_80]; lpSubKey
0x18000b407  mov     rcx, [rdi]; hKey
0x18000b40a  call    cs:__imp_RegDeleteTreeW
0x18000b411  nop     dword ptr [rax+rax+00h]
0x18000b416  mov     rcx, [rbp+5Fh]; this
0x18000b41a  test    eax, eax
0x18000b41c  jnz     loc_18000B554
0x18000b422  mov     [rbp+57h+cSubKeys], eax
0x18000b425  mov     [rsp+110h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000b42e  mov     [rsp+110h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000b437  mov     [rsp+110h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000b440  mov     [rsp+110h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000b449  mov     [rsp+110h+lpcValues], 0; lpcValues
0x18000b452  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000b45b  mov     [rsp+110h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000b464  lea     rax, [rbp+57h+cSubKeys]
0x18000b468  mov     [rsp+110h+phkResult], rax; unsigned int
0x18000b46d  xor     r9d, r9d; lpReserved
0x18000b470  xor     r8d, r8d; lpcchClass
0x18000b473  xor     edx, edx; lpClass
0x18000b475  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b479  call    cs:__imp_RegQueryInfoKeyW
0x18000b480  nop     dword ptr [rax+rax+00h]
0x18000b485  test    eax, eax
0x18000b487  jnz     short loc_18000B4B3
0x18000b489  cmp     [rbp+57h+cSubKeys], eax
0x18000b48c  jnz     short loc_18000B4B3
0x18000b48e  lea     rdx, [rbp+57h+lpSubKey]
0x18000b492  cmp     [rbp+57h+var_48], 8
0x18000b497  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000b49c  mov     rcx, [rdi]; hKey
0x18000b49f  call    cs:__imp_RegDeleteTreeW
0x18000b4a6  nop     dword ptr [rax+rax+00h]
0x18000b4ab  mov     rcx, [rbp+5Fh]; this
0x18000b4af  test    eax, eax
0x18000b4b1  jnz     short loc_18000B52A
0x18000b4b3  cmp     [rbp+57h+var_68], 8
0x18000b4b8  jb      short loc_18000B4CA
0x18000b4ba  mov     rcx, [rbp+57h+var_80]
0x18000b4be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b4c5  nop     dword ptr [rax+rax+00h]
0x18000b4ca  mov     [rbp+57h+var_68], 7
0x18000b4d2  mov     [rbp+57h+var_70], 0
0x18000b4da  xor     eax, eax
0x18000b4dc  mov     word ptr [rbp+57h+var_80], ax
0x18000b4e0  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b4e4  test    rcx, rcx
0x18000b4e7  jz      short loc_18000B4F6
0x18000b4e9  call    cs:__imp_RegCloseKey
0x18000b4f0  nop     dword ptr [rax+rax+00h]
0x18000b4f5  nop
0x18000b4f6  cmp     [rbp+57h+var_48], 8
0x18000b4fb  jb      short loc_18000B50D
0x18000b4fd  mov     rcx, [rbp+57h+lpSubKey]
0x18000b501  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b508  nop     dword ptr [rax+rax+00h]
0x18000b50d  mov     rcx, [rbp+57h+var_40]
0x18000b511  xor     rcx, rsp; StackCookie
0x18000b514  call    __security_check_cookie
0x18000b519  add     rsp, 0E8h
0x18000b520  pop     r14
0x18000b522  pop     r12
0x18000b524  pop     rdi
0x18000b525  pop     rsi
0x18000b526  pop     rbx
0x18000b527  pop     rbp
0x18000b528  retn
0x18000b52a  mov     r9d, eax; char *
0x18000b52d  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b534  mov     edx, 0A8h; void *
0x18000b539  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b53f  mov     r9d, eax; char *
0x18000b542  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b549  mov     edx, 95h; void *
0x18000b54e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b554  mov     r9d, eax; char *
0x18000b557  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b55e  mov     edx, 0A0h; void *
0x18000b563  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
