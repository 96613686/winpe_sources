# RegistryConfig::Delete(ushort const *,ushort const *,ushort const *)

- ea: `0x140008628`
- end: `0x1400088a6`
- name: `?Delete@RegistryConfig@@QEAAXPEBG00@Z`
- size: `638`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400063b0`

## callees

- `0x1400015a8`
- `0x1400064d0`
- `0x140008484`
- `0x140008628`
- `0x14000a370`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000880e`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008845`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000880e`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008845`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14000876c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400087f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14000876c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400087f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400086bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400086bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400087d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400087d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008833`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008833`

## string_xrefs

- `0x14000886a`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x14000887f`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x140008894`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-89h]
  LPDWORD lpcValues; // [rsp+38h] [rbp-81h]
  DWORD cSubKeys; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR *v27; // [rsp+70h] [rbp-49h] BYREF
  const unsigned __int16 *v28; // [rsp+78h] [rbp-41h] BYREF
  const unsigned __int16 *v29; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v30[2]; // [rsp+88h] [rbp-31h] BYREF
  LPCWSTR v31[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v32; // [rsp+A8h] [rbp-11h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v34; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v7 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) < 8u )
    v8 = (char *)this + 8;
  else
    v8 = *(char **)v7;
  RegistryConfig::AppendStrings(this, lpSubKey, 5, v8, L"\\", a2, L"\\", a3);
  hKey = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( v34 >= 8 )
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
  if ( v34 >= 8 )
    v11 = (LPCWSTR *)lpSubKey[0];
  RegistryConfig::AppendStrings(this, v31, 3, v11, L"\\", a4, lpcbMaxClassLen, lpcValues);
  if ( (unsigned int)dword_140010000 > 4 )
  {
    v15 = v31;
    if ( v32 >= 8 )
      v15 = (LPCWSTR *)v31[0];
    v27 = v15;
    v28 = a4;
    v29 = a3;
    if ( *((_QWORD *)v7 + 3) >= 8u )
      v7 = *(char **)v7;
    *(_QWORD *)v30 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v12,
      (unsigned int)&unk_14000D6E0,
      v13,
      v14,
      (__int64)v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27);
  }
  v16 = (const WCHAR *)v31;
  if ( v32 >= 8 )
    v16 = v31[0];
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
    if ( v34 >= 8 )
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
  if ( v32 >= 8 )
    operator delete((void *)v31[0]);
  v32 = 7;
  v31[2] = 0;
  LOWORD(v31[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v34 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x140008628  push    rbp
0x14000862a  push    rbx
0x14000862b  push    rsi
0x14000862c  push    rdi
0x14000862d  push    r12
0x14000862f  push    r14
0x140008631  lea     rbp, [rsp-2Fh]
0x140008636  sub     rsp, 0E8h
0x14000863d  mov     rax, cs:__security_cookie
0x140008644  xor     rax, rsp
0x140008647  mov     [rbp+57h+var_40], rax
0x14000864b  mov     rsi, r9
0x14000864e  mov     r14, r8
0x140008651  mov     rdi, rcx
0x140008654  lea     rbx, [rcx+8]
0x140008658  cmp     qword ptr [rbx+18h], 8
0x14000865d  jb      short loc_140008664
0x14000865f  mov     r9, [rbx]
0x140008662  jmp     short loc_140008667
0x140008664  mov     r9, rbx
0x140008667  mov     [rsp+110h+lpcValues], r14
0x14000866c  lea     r12, asc_14000CE24; "\\"
0x140008673  mov     [rsp+110h+lpcbMaxClassLen], r12
0x140008678  mov     [rsp+110h+lpcbMaxSubKeyLen], rdx
0x14000867d  mov     [rsp+110h+phkResult], r12
0x140008682  mov     r8d, 5
0x140008688  lea     rdx, [rbp+57h+lpSubKey]
0x14000868c  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x140008691  nop
0x140008692  mov     [rbp+57h+hKey], 0
0x14000869a  lea     rdx, [rbp+57h+lpSubKey]
0x14000869e  cmp     [rbp+57h+var_48], 8
0x1400086a3  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400086a8  lea     rax, [rbp+57h+hKey]
0x1400086ac  mov     [rsp+110h+phkResult], rax; unsigned int
0x1400086b1  mov     r9d, 0F003Fh; samDesired
0x1400086b7  xor     r8d, r8d; ulOptions
0x1400086ba  mov     rcx, [rdi]; hKey
0x1400086bd  call    cs:__imp_RegOpenKeyExW
0x1400086c3  mov     rcx, [rbp+5Fh]; this
0x1400086c7  test    eax, eax
0x1400086c9  jnz     loc_14000887C
0x1400086cf  lea     r9, [rbp+57h+lpSubKey]
0x1400086d3  cmp     [rbp+57h+var_48], 8
0x1400086d8  cmovnb  r9, [rbp+57h+lpSubKey]
0x1400086dd  mov     [rsp+110h+lpcbMaxSubKeyLen], rsi
0x1400086e2  mov     [rsp+110h+phkResult], r12
0x1400086e7  lea     r8d, [rax+3]
0x1400086eb  lea     rdx, [rbp+57h+var_80]
0x1400086ef  mov     rcx, rdi
0x1400086f2  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x1400086f7  nop
0x1400086f8  mov     eax, cs:dword_140010000
0x1400086fe  cmp     eax, 4
0x140008701  jbe     short loc_14000875B
0x140008703  lea     rax, [rbp+57h+var_80]
0x140008707  cmp     [rbp+57h+var_68], 8
0x14000870c  cmovnb  rax, [rbp+57h+var_80]
0x140008711  mov     [rbp+57h+var_A0], rax
0x140008715  mov     [rbp+57h+var_98], rsi
0x140008719  mov     [rbp+57h+var_90], r14
0x14000871d  cmp     qword ptr [rbx+18h], 8
0x140008722  jb      short loc_140008727
0x140008724  mov     rbx, [rbx]
0x140008727  mov     qword ptr [rbp+57h+var_88], rbx
0x14000872b  lea     rax, [rbp+57h+var_A0]
0x14000872f  mov     [rsp+110h+lpcValues], rax
0x140008734  lea     rax, [rbp+57h+var_98]
0x140008738  mov     [rsp+110h+lpcbMaxClassLen], rax
0x14000873d  lea     rax, [rbp+57h+var_90]
0x140008741  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x140008746  lea     rax, [rbp+57h+var_88]
0x14000874a  mov     [rsp+110h+phkResult], rax; unsigned int
0x14000874f  lea     rdx, unk_14000D6E0
0x140008756  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000875b  lea     rdx, [rbp+57h+var_80]
0x14000875f  cmp     [rbp+57h+var_68], 8
0x140008764  cmovnb  rdx, [rbp+57h+var_80]; lpSubKey
0x140008769  mov     rcx, [rdi]; hKey
0x14000876c  call    cs:__imp_RegDeleteTreeW
0x140008772  mov     rcx, [rbp+5Fh]; this
0x140008776  test    eax, eax
0x140008778  jnz     loc_140008891
0x14000877e  mov     [rbp+57h+cSubKeys], eax
0x140008781  mov     [rsp+110h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14000878a  mov     [rsp+110h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140008793  mov     [rsp+110h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14000879c  mov     [rsp+110h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1400087a5  mov     [rsp+110h+lpcValues], 0; lpcValues
0x1400087ae  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1400087b7  mov     [rsp+110h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1400087c0  lea     rax, [rbp+57h+cSubKeys]
0x1400087c4  mov     [rsp+110h+phkResult], rax; unsigned int
0x1400087c9  xor     r9d, r9d; lpReserved
0x1400087cc  xor     r8d, r8d; lpcchClass
0x1400087cf  xor     edx, edx; lpClass
0x1400087d1  mov     rcx, [rbp+57h+hKey]; hKey
0x1400087d5  call    cs:__imp_RegQueryInfoKeyW
0x1400087db  test    eax, eax
0x1400087dd  jnz     short loc_140008803
0x1400087df  cmp     [rbp+57h+cSubKeys], eax
0x1400087e2  jnz     short loc_140008803
0x1400087e4  lea     rdx, [rbp+57h+lpSubKey]
0x1400087e8  cmp     [rbp+57h+var_48], 8
0x1400087ed  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400087f2  mov     rcx, [rdi]; hKey
0x1400087f5  call    cs:__imp_RegDeleteTreeW
0x1400087fb  mov     rcx, [rbp+5Fh]; this
0x1400087ff  test    eax, eax
0x140008801  jnz     short loc_140008867
0x140008803  cmp     [rbp+57h+var_68], 8
0x140008808  jb      short loc_140008814
0x14000880a  mov     rcx, [rbp+57h+var_80]
0x14000880e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008814  mov     [rbp+57h+var_68], 7
0x14000881c  mov     [rbp+57h+var_70], 0
0x140008824  xor     eax, eax
0x140008826  mov     word ptr [rbp+57h+var_80], ax
0x14000882a  mov     rcx, [rbp+57h+hKey]; hKey
0x14000882e  test    rcx, rcx
0x140008831  jz      short loc_14000883A
0x140008833  call    cs:__imp_RegCloseKey
0x140008839  nop
0x14000883a  cmp     [rbp+57h+var_48], 8
0x14000883f  jb      short loc_14000884B
0x140008841  mov     rcx, [rbp+57h+lpSubKey]
0x140008845  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000884b  mov     rcx, [rbp+57h+var_40]
0x14000884f  xor     rcx, rsp; StackCookie
0x140008852  call    __security_check_cookie
0x140008857  add     rsp, 0E8h
0x14000885e  pop     r14
0x140008860  pop     r12
0x140008862  pop     rdi
0x140008863  pop     rsi
0x140008864  pop     rbx
0x140008865  pop     rbp
0x140008866  retn
0x140008867  mov     r9d, eax; char *
0x14000886a  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x140008871  mov     edx, 0A8h; void *
0x140008876  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000887c  mov     r9d, eax; char *
0x14000887f  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x140008886  mov     edx, 95h; void *
0x14000888b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140008891  mov     r9d, eax; char *
0x140008894  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x14000889b  mov     edx, 0A0h; void *
0x1400088a0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
