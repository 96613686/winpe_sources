# CacheProvisionXmlCrc(PackageContext *,_MVProvisionData &,ushort const *)

- ea: `0x180033c48`
- end: `0x180033ec6`
- name: `?CacheProvisionXmlCrc@@YAJPEAUPackageContext@@AEAU_MVProvisionData@@PEBG@Z`
- size: `638`
- prototype: `__int64 __fastcall(struct PackageContext *, struct _MVProvisionData *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018f74`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x180009900`
- `0x180033c48`
- `0x180034380`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033d0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033d2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033e77`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033e94`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033d0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033d2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033e77`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033e94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033e4b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033e4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033e17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033e65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033e17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033e65`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033de6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033de6`
- `ntdll!RtlCrc32` at `0x180033d9f`
- `ntdll!RtlCrc32` at `0x180033d9f`

## string_xrefs

- `0x180033cf3`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`
- `0x180033df5`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CacheProvisionXmlCrc(
        struct PackageContext *a1,
        struct _MVProvisionData *a2,
        const unsigned __int16 *a3)
{
  int CachedSettingRegPath; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rax
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  const WCHAR *v13; // rdx
  int dwOptions; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-89h]
  HKEY hKey; // [rsp+50h] [rbp-59h] BYREF
  int v17; // [rsp+58h] [rbp-51h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-4Dh] BYREF
  LPCWSTR lpValueName[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v20; // [rsp+70h] [rbp-39h]
  unsigned __int64 v21; // [rsp+78h] [rbp-31h]
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v23; // [rsp+90h] [rbp-19h]
  unsigned __int64 v24; // [rsp+98h] [rbp-11h]
  char v25[32]; // [rsp+A0h] [rbp-9h] BYREF
  int *v26; // [rsp+C0h] [rbp+17h]
  __int64 v27; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v24 = 7;
  v23 = 0;
  LOWORD(lpSubKey[0]) = 0;
  v21 = 7;
  v20 = 0;
  LOWORD(lpValueName[0]) = 0;
  CachedSettingRegPath = GetCachedSettingRegPath(a1, a2, lpSubKey, lpValueName);
  v5 = CachedSettingRegPath;
  if ( CachedSettingRegPath < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      v17 = CachedSettingRegPath;
      v26 = &v17;
      v27 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &unk_18004FF50, 0, 0, 3, v25);
    }
    v6 = 145;
    goto LABEL_5;
  }
  if ( !v23 || !v20 )
    goto LABEL_30;
  if ( !a3 )
  {
    v5 = -2147024809;
LABEL_36:
    v6 = 153;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
      (const char *)v5,
      dwOptions);
LABEL_6:
    if ( v21 >= 8 )
      operator delete((void *)lpValueName[0]);
    v21 = 7;
    v20 = 0;
    LOWORD(lpValueName[0]) = 0;
    if ( v24 >= 8 )
      operator delete((void *)lpSubKey[0]);
    return v5;
  }
  v8 = 0x7FFFFFFF;
  v9 = a3;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v5 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
    goto LABEL_36;
  *(_DWORD *)Data = RtlCrc32(a3, (2 * (0x7FFFFFFF - v8)) & -(__int64)(v8 != 0), 0);
  hKey = 0;
  v10 = (const WCHAR *)lpSubKey;
  if ( v24 >= 8 )
    v10 = lpSubKey[0];
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v11 )
  {
    v12 = 159;
    goto LABEL_22;
  }
  v13 = (const WCHAR *)lpValueName;
  if ( v21 >= 8 )
    v13 = lpValueName[0];
  v11 = RegSetValueExW(hKey, v13, 0, 4u, Data, 4u);
  if ( v11 )
  {
    v12 = 163;
LABEL_22:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v12,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
           (const char *)v11,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_6;
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_30:
  if ( v21 >= 8 )
    operator delete((void *)lpValueName[0]);
  LOWORD(lpValueName[0]) = 0;
  v20 = 0;
  v21 = 7;
  if ( v24 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180033c48  push    rbp
0x180033c4a  push    rbx
0x180033c4b  push    rsi
0x180033c4c  push    rdi
0x180033c4d  push    r14
0x180033c4f  lea     rbp, [rsp-37h]
0x180033c54  sub     rsp, 0E0h
0x180033c5b  mov     rax, cs:__security_cookie
0x180033c62  xor     rax, rsp
0x180033c65  mov     [rbp+57h+var_30], rax
0x180033c69  mov     rdi, r8
0x180033c6c  mov     r14d, 7
0x180033c72  mov     [rbp+57h+var_68], r14
0x180033c76  xor     esi, esi
0x180033c78  mov     [rbp+57h+var_70], rsi
0x180033c7c  mov     word ptr [rbp+57h+lpSubKey], si
0x180033c80  mov     [rbp+57h+var_88], r14
0x180033c84  mov     [rbp+57h+var_90], rsi
0x180033c88  mov     word ptr [rbp+57h+lpValueName], si
0x180033c8c  lea     r9, [rbp+57h+lpValueName]
0x180033c90  lea     r8, [rbp+57h+lpSubKey]
0x180033c94  call    ?GetCachedSettingRegPath@@YAJPEAUPackageContext@@PEAU_MVProvisionData@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; GetCachedSettingRegPath(PackageContext *,_MVProvisionData *,std::wstring *,std::wstring *)
0x180033c99  mov     ebx, eax
0x180033c9b  test    eax, eax
0x180033c9d  jns     loc_180033D39
0x180033ca3  mov     ecx, cs:dword_18005A000
0x180033ca9  cmp     ecx, 2
0x180033cac  jbe     short loc_180033CEB
0x180033cae  mov     [rbp+57h+var_A8], eax
0x180033cb1  lea     rax, [rbp+57h+var_A8]
0x180033cb5  mov     [rbp+57h+var_40], rax
0x180033cb9  mov     [rbp+57h+var_38], 4
0x180033cc1  lea     rax, [rbp+57h+var_60]
0x180033cc5  mov     qword ptr [rsp+100h+samDesired], rax
0x180033cca  mov     [rsp+100h+dwOptions], 3; int
0x180033cd2  xor     r9d, r9d
0x180033cd5  xor     r8d, r8d
0x180033cd8  lea     rdx, unk_18004FF50
0x180033cdf  lea     rcx, dword_18005A000
0x180033ce6  call    _tlgWriteTransfer_EventWriteTransfer
0x180033ceb  mov     edx, 91h; void *
0x180033cf0  mov     r9d, ebx; char *
0x180033cf3  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180033cfa  mov     rcx, [rbp+5Fh]; this
0x180033cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033d03  nop
0x180033d04  cmp     [rbp+57h+var_88], 8
0x180033d09  jb      short loc_180033D15
0x180033d0b  mov     rcx, [rbp+57h+lpValueName]
0x180033d0f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033d15  mov     [rbp+57h+var_88], r14
0x180033d19  mov     [rbp+57h+var_90], rsi
0x180033d1d  mov     word ptr [rbp+57h+lpValueName], si
0x180033d21  cmp     [rbp+57h+var_68], 8
0x180033d26  jb      short loc_180033D32
0x180033d28  mov     rcx, [rbp+57h+lpSubKey]
0x180033d2c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033d32  mov     eax, ebx
0x180033d34  jmp     loc_180033E9C
0x180033d39  cmp     [rbp+57h+var_70], rsi
0x180033d3d  jz      loc_180033E6C
0x180033d43  cmp     [rbp+57h+var_90], rsi
0x180033d47  jz      loc_180033E6C
0x180033d4d  test    rdi, rdi
0x180033d50  jz      loc_180033EB6
0x180033d56  mov     r8d, 7FFFFFFFh
0x180033d5c  mov     ecx, r8d
0x180033d5f  mov     rax, rdi
0x180033d62  cmp     [rax], si
0x180033d65  jz      short loc_180033D71
0x180033d67  add     rax, 2
0x180033d6b  sub     rcx, 1
0x180033d6f  jnz     short loc_180033D62
0x180033d71  mov     rax, rcx
0x180033d74  neg     rax
0x180033d77  sbb     ebx, ebx
0x180033d79  not     ebx
0x180033d7b  and     ebx, 80070057h
0x180033d81  test    rcx, rcx
0x180033d84  jz      loc_180033EBB
0x180033d8a  sub     r8, rcx
0x180033d8d  add     r8, r8
0x180033d90  neg     rcx
0x180033d93  sbb     rdx, rdx
0x180033d96  and     rdx, r8
0x180033d99  xor     r8d, r8d
0x180033d9c  mov     rcx, rdi
0x180033d9f  call    cs:__imp_RtlCrc32
0x180033da5  mov     dword ptr [rbp+57h+Data], eax
0x180033da8  mov     [rbp+57h+hKey], rsi
0x180033dac  lea     rdx, [rbp+57h+lpSubKey]
0x180033db0  cmp     [rbp+57h+var_68], 8
0x180033db5  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180033dba  mov     [rsp+100h+lpdwDisposition], rsi; lpdwDisposition
0x180033dbf  lea     rax, [rbp+57h+hKey]
0x180033dc3  mov     [rsp+100h+phkResult], rax; phkResult
0x180033dc8  mov     [rsp+100h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180033dcd  mov     [rsp+100h+samDesired], 2001Fh; samDesired
0x180033dd5  mov     [rsp+100h+dwOptions], esi; unsigned int
0x180033dd9  xor     r9d, r9d; lpClass
0x180033ddc  xor     r8d, r8d; Reserved
0x180033ddf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033de6  call    cs:__imp_RegCreateKeyExW
0x180033dec  test    eax, eax
0x180033dee  jz      short loc_180033E22
0x180033df0  mov     edx, 9Fh; void *
0x180033df5  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180033dfc  mov     r9d, eax; char *
0x180033dff  mov     rcx, [rbp+5Fh]; this
0x180033e03  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e08  mov     ebx, eax
0x180033e0a  mov     rcx, [rbp+57h+hKey]; hKey
0x180033e0e  test    rcx, rcx
0x180033e11  jz      loc_180033D04
0x180033e17  call    cs:__imp_RegCloseKey
0x180033e1d  jmp     loc_180033D04
0x180033e22  lea     rdx, [rbp+57h+lpValueName]
0x180033e26  cmp     [rbp+57h+var_88], 8
0x180033e2b  cmovnb  rdx, [rbp+57h+lpValueName]; lpValueName
0x180033e30  mov     r9d, 4; dwType
0x180033e36  mov     [rsp+100h+samDesired], r9d; cbData
0x180033e3b  lea     rax, [rbp+57h+Data]
0x180033e3f  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x180033e44  xor     r8d, r8d; Reserved
0x180033e47  mov     rcx, [rbp+57h+hKey]; hKey
0x180033e4b  call    cs:__imp_RegSetValueExW
0x180033e51  test    eax, eax
0x180033e53  jz      short loc_180033E5C
0x180033e55  mov     edx, 0A3h
0x180033e5a  jmp     short loc_180033DF5
0x180033e5c  mov     rcx, [rbp+57h+hKey]; hKey
0x180033e60  test    rcx, rcx
0x180033e63  jz      short loc_180033E6C
0x180033e65  call    cs:__imp_RegCloseKey
0x180033e6b  nop
0x180033e6c  cmp     [rbp+57h+var_88], 8
0x180033e71  jb      short loc_180033E7D
0x180033e73  mov     rcx, [rbp+57h+lpValueName]
0x180033e77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033e7d  mov     word ptr [rbp+57h+lpValueName], si
0x180033e81  mov     [rbp+57h+var_90], rsi
0x180033e85  mov     [rbp+57h+var_88], r14
0x180033e89  cmp     [rbp+57h+var_68], 8
0x180033e8e  jb      short loc_180033E9A
0x180033e90  mov     rcx, [rbp+57h+lpSubKey]
0x180033e94  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033e9a  xor     eax, eax
0x180033e9c  mov     rcx, [rbp+57h+var_30]
0x180033ea0  xor     rcx, rsp; StackCookie
0x180033ea3  call    __security_check_cookie
0x180033ea8  add     rsp, 0E0h
0x180033eaf  pop     r14
0x180033eb1  pop     rdi
0x180033eb2  pop     rsi
0x180033eb3  pop     rbx
0x180033eb4  pop     rbp
0x180033eb5  retn
0x180033eb6  mov     ebx, 80070057h
0x180033ebb  mov     edx, 99h
0x180033ec0  jmp     loc_180033CF0
```
