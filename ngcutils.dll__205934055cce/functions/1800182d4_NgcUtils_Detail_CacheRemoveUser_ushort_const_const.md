# NgcUtils::Detail::CacheRemoveUser(ushort const * const)

- ea: `0x1800182d4`
- end: `0x1800183f1`
- name: `?CacheRemoveUser@Detail@NgcUtils@@YAJQEBG@Z`
- size: `285`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016be4`

## callees

- `0x18000a5b4`
- `0x180013dc8`
- `0x180015ca4`
- `0x1800182d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001832e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800183a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800183de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001832e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800183a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800183de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018366`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018366`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800183b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800183b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018395`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800183d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018395`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800183d0`

## string_xrefs

- `0x180018310`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001837a`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::Detail::CacheRemoveUser(LPCWSTR lpSubKey, const unsigned __int16 *const a2)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v4; // ebx
  HLOCAL v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // edi
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF

  hMem = 0;
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        &hMem);
  v4 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x506,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResult);
    if ( hMem )
      LocalFree(hMem);
    return v4;
  }
  v6 = hMem;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)hMem, 0, 0x2001Fu, &hKey);
  if ( v7 )
  {
    v8 = 1295;
LABEL_7:
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v8,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
           (const char *)v7,
           phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v6 )
      LocalFree(v6);
    return v9;
  }
  v7 = RegDeleteTreeW(hKey, lpSubKey);
  if ( v7 )
  {
    v8 = 1300;
    goto LABEL_7;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    LocalFree(v6);
  return 0;
}

```

## disassembly

```asm
0x1800182d4  mov     [rsp+arg_0], rbx
0x1800182d9  push    rdi
0x1800182da  sub     rsp, 30h
0x1800182de  mov     rdi, rcx
0x1800182e1  mov     [rsp+38h+hMem], 0
0x1800182ea  lea     rcx, aNgccredprov; "NgcCredprov"
0x1800182f1  xor     r8d, r8d; unsigned __int16 *
0x1800182f4  lea     r9, [rsp+38h+hMem]; unsigned __int16 *
0x1800182f9  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180018300  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180018305  mov     ebx, eax
0x180018307  test    eax, eax
0x180018309  jns     short loc_18001833B
0x18001830b  mov     rcx, [rsp+38h]; this
0x180018310  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018317  mov     r9d, eax; char *
0x18001831a  mov     edx, 506h; void *
0x18001831f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018324  mov     rcx, [rsp+38h+hMem]; hMem
0x180018329  test    rcx, rcx
0x18001832c  jz      short loc_180018334
0x18001832e  call    cs:__imp_LocalFree
0x180018334  mov     eax, ebx
0x180018336  jmp     loc_1800183E6
0x18001833b  mov     rbx, [rsp+38h+hMem]
0x180018340  lea     rax, [rsp+38h+hKey]
0x180018345  mov     rdx, rbx; lpSubKey
0x180018348  mov     [rsp+38h+hKey], 0
0x180018351  mov     r9d, 2001Fh; samDesired
0x180018357  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x18001835c  xor     r8d, r8d; ulOptions
0x18001835f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018366  call    cs:__imp_RegOpenKeyExW
0x18001836c  test    eax, eax
0x18001836e  jz      short loc_1800183AD
0x180018370  mov     edx, 50Fh; void *
0x180018375  mov     rcx, [rsp+38h]; this
0x18001837a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018381  mov     r9d, eax; char *
0x180018384  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018389  mov     rcx, [rsp+38h+hKey]; hKey
0x18001838e  mov     edi, eax
0x180018390  test    rcx, rcx
0x180018393  jz      short loc_18001839B
0x180018395  call    cs:__imp_RegCloseKey
0x18001839b  test    rbx, rbx
0x18001839e  jz      short loc_1800183A9
0x1800183a0  mov     rcx, rbx; hMem
0x1800183a3  call    cs:__imp_LocalFree
0x1800183a9  mov     eax, edi
0x1800183ab  jmp     short loc_1800183E6
0x1800183ad  mov     rcx, [rsp+38h+hKey]; hKey
0x1800183b2  mov     rdx, rdi; lpSubKey
0x1800183b5  call    cs:__imp_RegDeleteTreeW
0x1800183bb  test    eax, eax
0x1800183bd  jz      short loc_1800183C6
0x1800183bf  mov     edx, 514h
0x1800183c4  jmp     short loc_180018375
0x1800183c6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800183cb  test    rcx, rcx
0x1800183ce  jz      short loc_1800183D6
0x1800183d0  call    cs:__imp_RegCloseKey
0x1800183d6  test    rbx, rbx
0x1800183d9  jz      short loc_1800183E4
0x1800183db  mov     rcx, rbx; hMem
0x1800183de  call    cs:__imp_LocalFree
0x1800183e4  xor     eax, eax
0x1800183e6  mov     rbx, [rsp+38h+arg_0]
0x1800183eb  add     rsp, 30h
0x1800183ef  pop     rdi
0x1800183f0  retn
```
