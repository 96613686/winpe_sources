# RegistryConfig::AddCommand(ushort const *,ushort const *,Command const *)

- ea: `0x18000ad90`
- end: `0x18000b05d`
- name: `?AddCommand@RegistryConfig@@QEAAXPEBG0PEBUCommand@@@Z`
- size: `717`
- prototype: `void(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct Command *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006e40`

## callees

- `0x1800013e0`
- `0x180007b84`
- `0x180008da4`
- `0x18000ad90`
- `0x18000b254`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000afe2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000afe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ae8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ae8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000af20`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000af20`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000af97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000af97`

## string_xrefs

- `0x18000af8c`: `WorkingDirectory`
- `0x18000b00c`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b021`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b036`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b048`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18000ad90  push    rbp
0x18000ad92  push    rbx
0x18000ad93  push    rsi
0x18000ad94  push    rdi
0x18000ad95  push    r14
0x18000ad97  lea     rbp, [rsp-37h]
0x18000ad9c  sub     rsp, 0B0h
0x18000ada3  mov     rax, cs:__security_cookie
0x18000adaa  xor     rax, rsp
0x18000adad  mov     [rbp+57h+var_28], rax
0x18000adb1  mov     rdi, r9
0x18000adb4  mov     r14, r8
0x18000adb7  mov     rsi, rdx
0x18000adba  mov     rbx, rcx
0x18000adbd  mov     eax, cs:dword_180014230
0x18000adc3  cmp     eax, 4
0x18000adc6  jbe     short loc_18000AE25
0x18000adc8  lea     rax, [r9+40h]
0x18000adcc  cmp     qword ptr [rax+18h], 8
0x18000add1  jb      short loc_18000ADD6
0x18000add3  mov     rax, [rax]
0x18000add6  mov     [rbp+57h+var_68], rax
0x18000adda  cmp     qword ptr [r9+18h], 8
0x18000addf  jb      short loc_18000ADE6
0x18000ade1  mov     rax, [r9]
0x18000ade4  jmp     short loc_18000ADE9
0x18000ade6  mov     rax, rdi
0x18000ade9  mov     [rbp+57h+var_60], rax
0x18000aded  mov     [rbp+57h+var_58], r14
0x18000adf1  mov     [rbp+57h+var_50], rsi
0x18000adf5  lea     rax, [rbp+57h+var_68]
0x18000adf9  mov     [rsp+0D0h+var_98], rax
0x18000adfe  lea     rax, [rbp+57h+var_60]
0x18000ae02  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x18000ae07  lea     rax, [rbp+57h+var_58]
0x18000ae0b  mov     qword ptr [rsp+0D0h+samDesired], rax
0x18000ae10  lea     rax, [rbp+57h+var_50]
0x18000ae14  mov     [rsp+0D0h+phkResult], rax
0x18000ae19  lea     rdx, byte_180010CA7
0x18000ae20  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000ae25  lea     r9, [rbx+8]
0x18000ae29  cmp     qword ptr [r9+18h], 8
0x18000ae2e  jb      short loc_18000AE33
0x18000ae30  mov     r9, [r9]
0x18000ae33  mov     [rsp+0D0h+var_98], r14
0x18000ae38  lea     rax, asc_180010164; "\\"
0x18000ae3f  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x18000ae44  mov     qword ptr [rsp+0D0h+samDesired], rsi
0x18000ae49  mov     [rsp+0D0h+phkResult], rax
0x18000ae4e  mov     r8d, 5
0x18000ae54  lea     rdx, [rbp+57h+lpSubKey]
0x18000ae58  mov     rcx, rbx
0x18000ae5b  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000ae60  nop
0x18000ae61  xor     r14d, r14d
0x18000ae64  mov     [rbp+57h+hKey], r14
0x18000ae68  mov     [rbp+57h+var_70], r14
0x18000ae6c  lea     rdx, [rbp+57h+lpSubKey]
0x18000ae70  cmp     [rbp+57h+var_30], 8
0x18000ae75  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000ae7a  lea     rax, [rbp+57h+var_70]
0x18000ae7e  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18000ae83  mov     r9d, 0F003Fh; samDesired
0x18000ae89  xor     r8d, r8d; ulOptions
0x18000ae8c  mov     rcx, [rbx]; hKey
0x18000ae8f  call    cs:__imp_RegOpenKeyExW
0x18000ae96  nop     dword ptr [rax+rax+00h]
0x18000ae9b  mov     rcx, [rbp+5Fh]; this
0x18000ae9f  test    eax, eax
0x18000aea1  jnz     loc_18000B01E
0x18000aea7  mov     [rbp+57h+dwDisposition], r14d
0x18000aeab  mov     rsi, [rbp+57h+hKey]
0x18000aeaf  test    rsi, rsi
0x18000aeb2  jz      short loc_18000AEDF
0x18000aeb4  call    cs:__imp_GetLastError
0x18000aebb  nop     dword ptr [rax+rax+00h]
0x18000aec0  mov     ebx, eax
0x18000aec2  mov     rcx, rsi; hKey
0x18000aec5  call    cs:__imp_RegCloseKey
0x18000aecc  nop     dword ptr [rax+rax+00h]
0x18000aed1  mov     ecx, ebx; dwErrCode
0x18000aed3  call    cs:__imp_SetLastError
0x18000aeda  nop     dword ptr [rax+rax+00h]
0x18000aedf  mov     [rbp+57h+hKey], r14
0x18000aee3  cmp     qword ptr [rdi+18h], 8
0x18000aee8  jb      short loc_18000AEEF
0x18000aeea  mov     rdx, [rdi]
0x18000aeed  jmp     short loc_18000AEF2
0x18000aeef  mov     rdx, rdi; lpSubKey
0x18000aef2  lea     rax, [rbp+57h+dwDisposition]
0x18000aef6  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18000aefb  lea     rax, [rbp+57h+hKey]
0x18000aeff  mov     [rsp+0D0h+var_98], rax; phkResult
0x18000af04  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000af09  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x18000af11  mov     dword ptr [rsp+0D0h+phkResult], r14d; int
0x18000af16  xor     r9d, r9d; lpClass
0x18000af19  xor     r8d, r8d; Reserved
0x18000af1c  mov     rcx, [rbp+57h+var_70]; hKey
0x18000af20  call    cs:__imp_RegCreateKeyExW
0x18000af27  nop     dword ptr [rax+rax+00h]
0x18000af2c  mov     rcx, [rbp+5Fh]; this
0x18000af30  test    eax, eax
0x18000af32  jnz     loc_18000B033
0x18000af38  mov     rax, [rdi+50h]
0x18000af3c  lea     rax, ds:2[rax*2]
0x18000af44  mov     edx, 0FFFFFFFFh
0x18000af49  cmp     rax, rdx
0x18000af4c  mov     ecx, eax
0x18000af4e  jbe     short loc_18000AF52
0x18000af50  mov     ecx, edx
0x18000af52  cmp     rdx, rax
0x18000af55  sbb     r9d, r9d
0x18000af58  and     r9d, 80070216h; char *
0x18000af5f  mov     r10, [rbp+5Fh]
0x18000af63  cmp     rax, rdx
0x18000af66  ja      loc_18000B048
0x18000af6c  add     rdi, 40h ; '@'
0x18000af70  cmp     qword ptr [rdi+18h], 8
0x18000af75  jb      short loc_18000AF7A
0x18000af77  mov     rdi, [rdi]
0x18000af7a  mov     [rsp+0D0h+samDesired], ecx; cbData
0x18000af7e  mov     [rsp+0D0h+phkResult], rdi; unsigned int
0x18000af83  mov     r9d, 1; dwType
0x18000af89  xor     r8d, r8d; Reserved
0x18000af8c  lea     rdx, aWorkingdirecto; "WorkingDirectory"
0x18000af93  mov     rcx, [rbp+57h+hKey]; hKey
0x18000af97  call    cs:__imp_RegSetValueExW
0x18000af9e  nop     dword ptr [rax+rax+00h]
0x18000afa3  mov     rcx, [rbp+5Fh]; this
0x18000afa7  test    eax, eax
0x18000afa9  jnz     short loc_18000B009
0x18000afab  mov     rcx, [rbp+57h+var_70]; hKey
0x18000afaf  test    rcx, rcx
0x18000afb2  jz      short loc_18000AFC1
0x18000afb4  call    cs:__imp_RegCloseKey
0x18000afbb  nop     dword ptr [rax+rax+00h]
0x18000afc0  nop
0x18000afc1  mov     rcx, [rbp+57h+hKey]; hKey
0x18000afc5  test    rcx, rcx
0x18000afc8  jz      short loc_18000AFD7
0x18000afca  call    cs:__imp_RegCloseKey
0x18000afd1  nop     dword ptr [rax+rax+00h]
0x18000afd6  nop
0x18000afd7  cmp     [rbp+57h+var_30], 8
0x18000afdc  jb      short loc_18000AFEE
0x18000afde  mov     rcx, [rbp+57h+lpSubKey]
0x18000afe2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000afe9  nop     dword ptr [rax+rax+00h]
0x18000afee  mov     rcx, [rbp+57h+var_28]
0x18000aff2  xor     rcx, rsp; StackCookie
0x18000aff5  call    __security_check_cookie
0x18000affa  add     rsp, 0B0h
0x18000b001  pop     r14
0x18000b003  pop     rdi
0x18000b004  pop     rsi
0x18000b005  pop     rbx
0x18000b006  pop     rbp
0x18000b007  retn
0x18000b009  mov     r9d, eax; char *
0x18000b00c  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b013  mov     edx, 72h ; 'r'; void *
0x18000b018  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b01e  mov     r9d, eax; char *
0x18000b021  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b028  mov     edx, 62h ; 'b'; void *
0x18000b02d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b033  mov     r9d, eax; char *
0x18000b036  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b03d  mov     edx, 67h ; 'g'; void *
0x18000b042  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b048  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b04f  mov     edx, 6Dh ; 'm'; void *
0x18000b054  mov     rcx, r10; this
0x18000b057  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
