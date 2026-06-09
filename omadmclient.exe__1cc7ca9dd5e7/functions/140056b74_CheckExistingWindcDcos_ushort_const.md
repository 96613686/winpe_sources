# CheckExistingWindcDcos(ushort const *)

- ea: `0x140056b74`
- end: `0x140057075`
- name: `?CheckExistingWindcDcos@@YAJPEBG@Z`
- size: `1281`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14004b5a0`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x140013068`
- `0x140056b74`
- `0x1400576f0`
- `0x1400580ac`
- `0x1400585f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056daa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056e70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056daa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140056d3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140056d3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140056d0f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140056d0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056cbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056f7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005700c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056cbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140056f7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005700c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057021`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140056c1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140056c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056e8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140056ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140056ea9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056c55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056e9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056fbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140057062`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056c55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056e9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140056fbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140057062`
- `DMCmnUtils!DmGetActiveUserSid` at `0x140056ec2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x140056ec2`

## string_xrefs

- `0x140056c38`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x140057043`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CheckExistingWindcDcos(const unsigned __int16 *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  char v5; // r14
  DWORD v6; // r12d
  unsigned int v7; // eax
  int v8; // edi
  void *v9; // rcx
  int v10; // edi
  void *v11; // rcx
  int v12; // edi
  void *v13; // rcx
  HLOCAL v14; // r15
  DWORD LastError; // edi
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rdx
  __int64 v18; // rdx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v25; // [rsp+80h] [rbp-80h] BYREF
  DWORD cSubKeys; // [rsp+88h] [rbp-78h] BYREF
  void **p_Block; // [rsp+90h] [rbp-70h]
  void *v28; // [rsp+98h] [rbp-68h] BYREF
  char v29; // [rsp+A0h] [rbp-60h]
  DWORD cchName; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  phkResult = 0;
  v32 = 0;
  cSubKeys = 0;
  cchName = 0;
  v25 = 0;
  v24 = 0;
  Block = 0;
  hMem = 0;
  hKey = 0;
  DCGetReadonlyHKey(qword_140085158);
  v2 = RegQueryInfoKeyW(0, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x4B4,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
           (const char *)v2,
           lpcSubKeys);
    goto LABEL_3;
  }
  v5 = 0;
  v6 = 0;
  if ( !cSubKeys )
  {
LABEL_38:
    if ( hMem )
      LocalFree(hMem);
    if ( Block )
      operator delete(Block);
    if ( v24 )
      operator delete(v24);
    if ( v25 )
      operator delete(v25);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147500037LL;
  }
  while ( 1 )
  {
    cchName = 260;
    v7 = RegEnumKeyExW(0, v6, Name, &cchName, 0, 0, 0, 0);
    if ( v7 )
      break;
    v7 = RegOpenKeyExW(0, Name, 0, 0x20019u, &phkResult);
    if ( v7 )
    {
      v18 = 1229;
      goto LABEL_62;
    }
    p_Block = (void **)&v25;
    v28 = 0;
    v29 = 1;
    v8 = DCGetRegistryString(phkResult, 0, L"EnrollmentId", &v28);
    if ( v29 )
    {
      v9 = *p_Block;
      *p_Block = v28;
      if ( v9 )
        operator delete(v9);
    }
    if ( v8 >= 0 && !(unsigned int)_o__wcsicmp(v25, a1) )
    {
      p_Block = (void **)&v24;
      v28 = 0;
      v29 = 1;
      v10 = DCGetRegistryString(phkResult, 0, L"DocId", &v28);
      if ( v29 )
      {
        v11 = *p_Block;
        *p_Block = v28;
        if ( v11 )
          operator delete(v11);
      }
      if ( v10 >= 0 )
      {
        p_Block = &Block;
        v28 = 0;
        v29 = 1;
        v12 = DCGetRegistryString(phkResult, 0, L"UserId", &v28);
        if ( v29 )
        {
          v13 = *p_Block;
          *p_Block = v28;
          if ( v13 )
            operator delete(v13);
        }
        if ( v12 >= 0 )
        {
          if ( (unsigned int)_o__wcsicmp(Block, L"User") )
          {
            v16 = v24;
            if ( v5 )
              goto LABEL_34;
            v17 = (unsigned __int16 *)Block;
          }
          else
          {
            v14 = hMem;
            if ( hMem )
            {
              LastError = GetLastError();
              LocalFree(v14);
              SetLastError(LastError);
            }
            hMem = 0;
            if ( (int)DmGetActiveUserSid((unsigned __int16 **)&hMem) < 0 )
              goto LABEL_37;
            v5 = 1;
            v16 = v24;
LABEL_34:
            v17 = (unsigned __int16 *)hMem;
          }
          if ( DeclaredConfigurationStore_CheckForCorruption(v25, v17, v16) >= 0 )
          {
            if ( hMem )
              LocalFree(hMem);
            if ( Block )
              operator delete(Block);
            if ( v24 )
              operator delete(v24);
            if ( v25 )
              operator delete(v25);
            if ( phkResult )
              RegCloseKey(phkResult);
            return 0;
          }
        }
      }
    }
LABEL_37:
    if ( ++v6 >= cSubKeys )
      goto LABEL_38;
  }
  v18 = 1223;
LABEL_62:
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v18,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
         (const char *)v7,
         lpcSubKeysa);
  if ( hMem )
    LocalFree(hMem);
LABEL_3:
  if ( Block )
    operator delete(Block);
  if ( v24 )
    operator delete(v24);
  if ( v25 )
    operator delete(v25);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v3;
}

```

## disassembly

```asm
0x140056b74  push    rbp
0x140056b76  push    rbx
0x140056b77  push    rsi
0x140056b78  push    rdi
0x140056b79  push    r12
0x140056b7b  push    r13
0x140056b7d  push    r14
0x140056b7f  push    r15
0x140056b81  lea     rbp, [rsp-1E8h]
0x140056b89  sub     rsp, 2E8h
0x140056b90  mov     rax, cs:__security_cookie
0x140056b97  xor     rax, rsp
0x140056b9a  mov     [rbp+220h+var_50], rax
0x140056ba1  mov     r13, rcx
0x140056ba4  xor     r15d, r15d
0x140056ba7  mov     [rsp+320h+phkResult], r15
0x140056bac  mov     [rbp+220h+var_268], r15
0x140056bb0  mov     [rbp+220h+cSubKeys], r15d
0x140056bb4  mov     [rbp+220h+cchName], r15d
0x140056bb8  mov     [rbp+220h+var_2A0], r15
0x140056bbc  mov     [rsp+320h+var_2A8], r15
0x140056bc1  mov     [rsp+320h+Block], r15
0x140056bc6  mov     [rsp+320h+hMem], r15
0x140056bcb  mov     [rbp+220h+hKey], r15
0x140056bcf  lea     rdx, [rbp+220h+hKey]
0x140056bd3  mov     rcx, cs:qword_140085158; lpSubKey
0x140056bda  call    DCGetReadonlyHKey
0x140056bdf  mov     [rsp+320h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140056be4  mov     [rsp+320h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140056be9  mov     [rsp+320h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140056bee  mov     [rsp+320h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140056bf3  mov     [rsp+320h+lpcValues], r15; lpcValues
0x140056bf8  mov     [rsp+320h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140056bfd  mov     [rsp+320h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140056c02  lea     rax, [rbp+220h+cSubKeys]
0x140056c06  mov     [rsp+320h+lpcSubKeys], rax; unsigned int
0x140056c0b  xor     r9d, r9d; lpReserved
0x140056c0e  xor     r8d, r8d; lpcchClass
0x140056c11  xor     edx, edx; lpClass
0x140056c13  mov     rbx, [rbp+220h+hKey]
0x140056c17  mov     rcx, rbx; hKey
0x140056c1a  call    cs:__imp_RegQueryInfoKeyW
0x140056c21  nop     dword ptr [rax+rax+00h]
0x140056c26  test    eax, eax
0x140056c28  jz      loc_140056CD1
0x140056c2e  mov     rcx, [rbp+228h]; this
0x140056c35  mov     r9d, eax; char *
0x140056c38  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x140056c3f  mov     edx, 4B4h; void *
0x140056c44  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140056c49  mov     edi, eax
0x140056c4b  mov     rcx, [rsp+320h+hMem]; hMem
0x140056c50  test    rcx, rcx
0x140056c53  jz      short loc_140056C62
0x140056c55  call    cs:__imp_LocalFree
0x140056c5c  nop     dword ptr [rax+rax+00h]
0x140056c61  nop
0x140056c62  mov     esi, 2
0x140056c67  mov     rcx, [rsp+320h+Block]; Block
0x140056c6c  test    rcx, rcx
0x140056c6f  jz      short loc_140056C7A
0x140056c71  mov     rdx, rsi
0x140056c74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056c79  nop
0x140056c7a  mov     rcx, [rsp+320h+var_2A8]; Block
0x140056c7f  test    rcx, rcx
0x140056c82  jz      short loc_140056C8D
0x140056c84  mov     rdx, rsi
0x140056c87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056c8c  nop
0x140056c8d  mov     rcx, [rbp+220h+var_2A0]; Block
0x140056c91  test    rcx, rcx
0x140056c94  jz      short loc_140056C9F
0x140056c96  mov     rdx, rsi
0x140056c99  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056c9e  nop
0x140056c9f  mov     rcx, [rsp+320h+phkResult]; hKey
0x140056ca4  test    rcx, rcx
0x140056ca7  jz      short loc_140056CB6
0x140056ca9  call    cs:__imp_RegCloseKey
0x140056cb0  nop     dword ptr [rax+rax+00h]
0x140056cb5  nop
0x140056cb6  test    rbx, rbx
0x140056cb9  jz      short loc_140056CCA
0x140056cbb  mov     rcx, rbx; hKey
0x140056cbe  call    cs:__imp_RegCloseKey
0x140056cc5  nop     dword ptr [rax+rax+00h]
0x140056cca  mov     eax, edi
0x140056ccc  jmp     loc_140056F8F
0x140056cd1  mov     r14b, r15b
0x140056cd4  mov     r12d, r15d
0x140056cd7  mov     esi, 2
0x140056cdc  cmp     [rbp+220h+cSubKeys], r15d
0x140056ce0  jbe     loc_140056F10
0x140056ce6  mov     [rbp+220h+cchName], 104h
0x140056ced  mov     [rsp+320h+lpcValues], r15; lpftLastWriteTime
0x140056cf2  mov     [rsp+320h+lpcbMaxClassLen], r15; lpcchClass
0x140056cf7  mov     [rsp+320h+lpcbMaxSubKeyLen], r15; lpClass
0x140056cfc  mov     [rsp+320h+lpcSubKeys], r15; unsigned int
0x140056d01  lea     r9, [rbp+220h+cchName]; lpcchName
0x140056d05  lea     r8, [rbp+220h+Name]; lpName
0x140056d09  mov     edx, r12d; dwIndex
0x140056d0c  mov     rcx, rbx; hKey
0x140056d0f  call    cs:__imp_RegEnumKeyExW
0x140056d16  nop     dword ptr [rax+rax+00h]
0x140056d1b  test    eax, eax
0x140056d1d  jnz     loc_14005703B
0x140056d23  lea     rax, [rsp+320h+phkResult]
0x140056d28  mov     [rsp+320h+lpcSubKeys], rax; phkResult
0x140056d2d  mov     r9d, 20019h; samDesired
0x140056d33  xor     r8d, r8d; ulOptions
0x140056d36  lea     rdx, [rbp+220h+Name]; lpSubKey
0x140056d3a  mov     rcx, rbx; hKey
0x140056d3d  call    cs:__imp_RegOpenKeyExW
0x140056d44  nop     dword ptr [rax+rax+00h]
0x140056d49  test    eax, eax
0x140056d4b  jnz     loc_140057034
0x140056d51  lea     rax, [rbp+220h+var_2A0]
0x140056d55  mov     [rbp+220h+var_290], rax
0x140056d59  mov     [rbp+220h+var_288], r15
0x140056d5d  mov     [rbp+220h+var_280], 1
0x140056d61  lea     r9, [rbp+220h+var_288]
0x140056d65  lea     r8, aEnrollmentid; "EnrollmentId"
0x140056d6c  xor     edx, edx
0x140056d6e  mov     rcx, [rsp+320h+phkResult]
0x140056d73  call    DCGetRegistryString
0x140056d78  mov     edi, eax
0x140056d7a  cmp     [rbp+220h+var_280], r15b
0x140056d7e  jz      short loc_140056D9B
0x140056d80  mov     r8, [rbp+220h+var_290]
0x140056d84  mov     rcx, [r8]; Block
0x140056d87  mov     rdx, [rbp+220h+var_288]
0x140056d8b  mov     [r8], rdx
0x140056d8e  test    rcx, rcx
0x140056d91  jz      short loc_140056D9B
0x140056d93  mov     rdx, rsi
0x140056d96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056d9b  test    edi, edi
0x140056d9d  js      loc_140056F03
0x140056da3  mov     rdx, r13
0x140056da6  mov     rcx, [rbp+220h+var_2A0]
0x140056daa  call    cs:__imp__o__wcsicmp
0x140056db1  nop     dword ptr [rax+rax+00h]
0x140056db6  test    eax, eax
0x140056db8  jnz     loc_140056F03
0x140056dbe  lea     rax, [rsp+320h+var_2A8]
0x140056dc3  mov     [rbp+220h+var_290], rax
0x140056dc7  mov     [rbp+220h+var_288], r15
0x140056dcb  mov     [rbp+220h+var_280], 1
0x140056dcf  lea     r9, [rbp+220h+var_288]
0x140056dd3  lea     r8, aDocid; "DocId"
0x140056dda  xor     edx, edx
0x140056ddc  mov     rcx, [rsp+320h+phkResult]
0x140056de1  call    DCGetRegistryString
0x140056de6  mov     edi, eax
0x140056de8  cmp     [rbp+220h+var_280], r15b
0x140056dec  jz      short loc_140056E09
0x140056dee  mov     r8, [rbp+220h+var_290]
0x140056df2  mov     rcx, [r8]; Block
0x140056df5  mov     rdx, [rbp+220h+var_288]
0x140056df9  mov     [r8], rdx
0x140056dfc  test    rcx, rcx
0x140056dff  jz      short loc_140056E09
0x140056e01  mov     rdx, rsi
0x140056e04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056e09  test    edi, edi
0x140056e0b  js      loc_140056F03
0x140056e11  lea     rax, [rsp+320h+Block]
0x140056e16  mov     [rbp+220h+var_290], rax
0x140056e1a  mov     [rbp+220h+var_288], r15
0x140056e1e  mov     [rbp+220h+var_280], 1
0x140056e22  lea     r9, [rbp+220h+var_288]
0x140056e26  lea     r8, aUserid; "UserId"
0x140056e2d  xor     edx, edx
0x140056e2f  mov     rcx, [rsp+320h+phkResult]
0x140056e34  call    DCGetRegistryString
0x140056e39  mov     edi, eax
0x140056e3b  cmp     [rbp+220h+var_280], r15b
0x140056e3f  jz      short loc_140056E5C
0x140056e41  mov     r8, [rbp+220h+var_290]
0x140056e45  mov     rcx, [r8]; Block
0x140056e48  mov     rdx, [rbp+220h+var_288]
0x140056e4c  mov     [r8], rdx
0x140056e4f  test    rcx, rcx
0x140056e52  jz      short loc_140056E5C
0x140056e54  mov     rdx, rsi
0x140056e57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056e5c  test    edi, edi
0x140056e5e  js      loc_140056F03
0x140056e64  lea     rdx, aUser_1; "User"
0x140056e6b  mov     rcx, [rsp+320h+Block]
0x140056e70  call    cs:__imp__o__wcsicmp
0x140056e77  nop     dword ptr [rax+rax+00h]
0x140056e7c  test    eax, eax
0x140056e7e  jnz     short loc_140056EDC
0x140056e80  mov     r15, [rsp+320h+hMem]
0x140056e85  test    r15, r15
0x140056e88  jz      short loc_140056EB5
0x140056e8a  call    cs:__imp_GetLastError
0x140056e91  nop     dword ptr [rax+rax+00h]
0x140056e96  mov     edi, eax
0x140056e98  mov     rcx, r15; hMem
0x140056e9b  call    cs:__imp_LocalFree
0x140056ea2  nop     dword ptr [rax+rax+00h]
0x140056ea7  mov     ecx, edi; dwErrCode
0x140056ea9  call    cs:__imp_SetLastError
0x140056eb0  nop     dword ptr [rax+rax+00h]
0x140056eb5  xor     r15d, r15d
0x140056eb8  mov     [rsp+320h+hMem], r15
0x140056ebd  lea     rcx, [rsp+320h+hMem]
0x140056ec2  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x140056ec9  nop     dword ptr [rax+rax+00h]
0x140056ece  test    eax, eax
0x140056ed0  js      short loc_140056F03
0x140056ed2  mov     r14b, 1
0x140056ed5  mov     r8, [rsp+320h+var_2A8]
0x140056eda  jmp     short loc_140056EE6
0x140056edc  mov     r8, [rsp+320h+var_2A8]; unsigned __int16 *
0x140056ee1  test    r14b, r14b
0x140056ee4  jz      short loc_140056EED
0x140056ee6  mov     rdx, [rsp+320h+hMem]
0x140056eeb  jmp     short loc_140056EF2
0x140056eed  mov     rdx, [rsp+320h+Block]; unsigned __int16 *
0x140056ef2  mov     rcx, [rbp+220h+var_2A0]; unsigned __int16 *
0x140056ef6  call    ?DeclaredConfigurationStore_CheckForCorruption@@YAJPEAG00@Z; DeclaredConfigurationStore_CheckForCorruption(ushort *,ushort *,ushort *)
0x140056efb  test    eax, eax
0x140056efd  jns     loc_140056FB3
0x140056f03  inc     r12d
0x140056f06  cmp     r12d, [rbp+220h+cSubKeys]
0x140056f0a  jb      loc_140056CE6
0x140056f10  mov     rcx, [rsp+320h+hMem]; hMem
0x140056f15  test    rcx, rcx
0x140056f18  jz      short loc_140056F27
0x140056f1a  call    cs:__imp_LocalFree
0x140056f21  nop     dword ptr [rax+rax+00h]
0x140056f26  nop
0x140056f27  mov     rcx, [rsp+320h+Block]; Block
0x140056f2c  test    rcx, rcx
0x140056f2f  jz      short loc_140056F3A
0x140056f31  mov     rdx, rsi
0x140056f34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056f39  nop
0x140056f3a  mov     rcx, [rsp+320h+var_2A8]; Block
0x140056f3f  test    rcx, rcx
0x140056f42  jz      short loc_140056F4D
0x140056f44  mov     rdx, rsi
0x140056f47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056f4c  nop
0x140056f4d  mov     rcx, [rbp+220h+var_2A0]; Block
0x140056f51  test    rcx, rcx
0x140056f54  jz      short loc_140056F5F
0x140056f56  mov     rdx, rsi
0x140056f59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056f5e  nop
0x140056f5f  mov     rcx, [rsp+320h+phkResult]; hKey
0x140056f64  test    rcx, rcx
0x140056f67  jz      short loc_140056F76
0x140056f69  call    cs:__imp_RegCloseKey
0x140056f70  nop     dword ptr [rax+rax+00h]
0x140056f75  nop
0x140056f76  test    rbx, rbx
0x140056f79  jz      short loc_140056F8A
0x140056f7b  mov     rcx, rbx; hKey
0x140056f7e  call    cs:__imp_RegCloseKey
0x140056f85  nop     dword ptr [rax+rax+00h]
0x140056f8a  mov     eax, 80004005h
0x140056f8f  mov     rcx, [rbp+220h+var_50]
0x140056f96  xor     rcx, rsp; StackCookie
0x140056f99  call    __security_check_cookie
0x140056f9e  add     rsp, 2E8h
0x140056fa5  pop     r15
0x140056fa7  pop     r14
0x140056fa9  pop     r13
0x140056fab  pop     r12
0x140056fad  pop     rdi
0x140056fae  pop     rsi
0x140056faf  pop     rbx
0x140056fb0  pop     rbp
0x140056fb1  retn
0x140056fb3  mov     rcx, [rsp+320h+hMem]; hMem
0x140056fb8  test    rcx, rcx
0x140056fbb  jz      short loc_140056FCA
0x140056fbd  call    cs:__imp_LocalFree
0x140056fc4  nop     dword ptr [rax+rax+00h]
0x140056fc9  nop
0x140056fca  mov     rcx, [rsp+320h+Block]; Block
0x140056fcf  test    rcx, rcx
0x140056fd2  jz      short loc_140056FDD
0x140056fd4  mov     rdx, rsi
0x140056fd7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056fdc  nop
0x140056fdd  mov     rcx, [rsp+320h+var_2A8]; Block
0x140056fe2  test    rcx, rcx
0x140056fe5  jz      short loc_140056FF0
0x140056fe7  mov     rdx, rsi
0x140056fea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056fef  nop
0x140056ff0  mov     rcx, [rbp+220h+var_2A0]; Block
0x140056ff4  test    rcx, rcx
0x140056ff7  jz      short loc_140057002
  ... truncated ...
```
