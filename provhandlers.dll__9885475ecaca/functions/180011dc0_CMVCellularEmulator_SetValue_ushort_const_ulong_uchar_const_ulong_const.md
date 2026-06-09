# CMVCellularEmulator::SetValue(ushort const *,ulong,uchar const *,ulong const *)

- ea: `0x180011dc0`
- end: `0x180011ffb`
- name: `?SetValue@CMVCellularEmulator@@UEAAJPEBGKPEBEPEBK@Z`
- size: `571`
- prototype: `int(CMVCellularEmulator *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int8 *, const unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800076a4`
- `0x18001192c`
- `0x180011c08`
- `0x180011dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fe2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011fa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011fa8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011e46`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011eac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011f52`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011e46`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011eac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011f52`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMVCellularEmulator::SetValue(
        CMVCellularEmulator *this,
        const unsigned __int16 *a2,
        DWORD a3,
        const unsigned __int8 *a4)
{
  unsigned int v8; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  const struct Uicc *v12; // rdi
  HKEY v13; // rsi
  DWORD LastError; // ebx
  unsigned int v15; // eax
  __int64 v16; // rdx
  int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  HKEY v24; // [rsp+B0h] [rbp+48h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)0x8007139FLL,
      dwOptions);
    return v8;
  }
  hKey = 0;
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegCellularEmulator, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v10 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xF7,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
           (const char *)v10,
           dwOptionsa);
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  phkResult = 0;
  v11 = RegCreateKeyExW(hKey, L"Datastore", 0, 0, 0, 0x20006u, 0, &phkResult, 0);
  if ( v11 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xFB,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
           (const char *)v11,
           dwOptionsb);
LABEL_10:
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_6;
  }
  v24 = 0;
  v12 = CellState::SelectUicc(*((CellState **)this + 2), (CMVCellularEmulator *)((char *)this + 24));
  v13 = v24;
  if ( v24 )
  {
    LastError = GetLastError();
    RegCloseKey(v13);
    SetLastError(LastError);
  }
  v24 = 0;
  if ( *((_QWORD *)v12 + 3) >= 8u )
    v12 = *(const struct Uicc **)v12;
  v15 = RegCreateKeyExW(phkResult, (LPCWSTR)v12, 0, 0, 0, 2u, 0, &v24, 0);
  if ( v15 )
  {
    v16 = 257;
    goto LABEL_18;
  }
  v15 = RegSetValueExW(v24, a2, 0, 3u, a4, a3);
  if ( v15 )
  {
    v16 = 260;
LABEL_18:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v16,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
           (const char *)v15,
           dwOptionsc);
    if ( v24 )
      RegCloseKey(v24);
    goto LABEL_10;
  }
  if ( v24 )
    RegCloseKey(v24);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180011dc0  push    rbp
0x180011dc2  push    rbx
0x180011dc3  push    rsi
0x180011dc4  push    rdi
0x180011dc5  push    r12
0x180011dc7  push    r13
0x180011dc9  push    r14
0x180011dcb  push    r15
0x180011dcd  mov     rbp, rsp
0x180011dd0  sub     rsp, 68h
0x180011dd4  mov     r14, r9
0x180011dd7  mov     r15d, r8d
0x180011dda  mov     r12, rdx
0x180011ddd  mov     rbx, rcx
0x180011de0  xor     r13d, r13d
0x180011de3  cmp     [rcx+10h], r13
0x180011de7  jnz     short loc_180011E0D
0x180011de9  mov     rcx, [rbp+40h]; this
0x180011ded  mov     ebx, 8007139Fh
0x180011df2  mov     r9d, ebx; char *
0x180011df5  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011dfc  mov     edx, 0F2h; void *
0x180011e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e06  mov     eax, ebx
0x180011e08  jmp     loc_180011FEA
0x180011e0d  mov     [rbp+hKey], r13
0x180011e11  mov     [rsp+68h+lpdwDisposition], r13; lpdwDisposition
0x180011e16  lea     rax, [rbp+hKey]
0x180011e1a  mov     [rsp+68h+phkResult], rax; phkResult
0x180011e1f  mov     [rsp+68h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180011e24  mov     edi, 20006h
0x180011e29  mov     [rsp+68h+samDesired], edi; samDesired
0x180011e2d  mov     [rsp+68h+dwOptions], r13d; unsigned int
0x180011e32  xor     r9d, r9d; lpClass
0x180011e35  xor     r8d, r8d; Reserved
0x180011e38  mov     rdx, cs:?gc_wszRegCellularEmulator@@3PEBGEB; lpSubKey
0x180011e3f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011e46  call    cs:__imp_RegCreateKeyExW
0x180011e4c  test    eax, eax
0x180011e4e  jz      short loc_180011E7B
0x180011e50  mov     rcx, [rbp+40h]; this
0x180011e54  mov     r9d, eax; char *
0x180011e57  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011e5e  mov     edx, 0F7h; void *
0x180011e63  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011e68  mov     ebx, eax
0x180011e6a  mov     rcx, [rbp+hKey]; hKey
0x180011e6e  test    rcx, rcx
0x180011e71  jz      short loc_180011E06
0x180011e73  call    cs:__imp_RegCloseKey
0x180011e79  jmp     short loc_180011E06
0x180011e7b  mov     [rbp+var_10], r13
0x180011e7f  mov     [rsp+68h+lpdwDisposition], r13; lpdwDisposition
0x180011e84  lea     rax, [rbp+var_10]
0x180011e88  mov     [rsp+68h+phkResult], rax; phkResult
0x180011e8d  mov     [rsp+68h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180011e92  mov     [rsp+68h+samDesired], edi; samDesired
0x180011e96  mov     [rsp+68h+dwOptions], r13d; unsigned int
0x180011e9b  xor     r9d, r9d; lpClass
0x180011e9e  xor     r8d, r8d; Reserved
0x180011ea1  lea     rdx, ?c_datastoreKeyName@@3QBGB; "Datastore"
0x180011ea8  mov     rcx, [rbp+hKey]; hKey
0x180011eac  call    cs:__imp_RegCreateKeyExW
0x180011eb2  test    eax, eax
0x180011eb4  jz      short loc_180011EE1
0x180011eb6  mov     rcx, [rbp+40h]; this
0x180011eba  mov     r9d, eax; char *
0x180011ebd  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011ec4  mov     edx, 0FBh; void *
0x180011ec9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011ece  mov     ebx, eax
0x180011ed0  mov     rcx, [rbp+var_10]; hKey
0x180011ed4  test    rcx, rcx
0x180011ed7  jz      short loc_180011E6A
0x180011ed9  call    cs:__imp_RegCloseKey
0x180011edf  jmp     short loc_180011E6A
0x180011ee1  mov     [rbp+arg_0], r13
0x180011ee5  lea     rdx, [rbx+18h]; struct __MIDL___MIDL_itf_mvcellular_0000_0000_0002 *
0x180011ee9  mov     rcx, [rbx+10h]; this
0x180011eed  call    ?SelectUicc@CellState@@QEAAAEBUUicc@@AEBU__MIDL___MIDL_itf_mvcellular_0000_0000_0002@@@Z; CellState::SelectUicc(__MIDL___MIDL_itf_mvcellular_0000_0000_0002 const &)
0x180011ef2  mov     rdi, rax
0x180011ef5  mov     rsi, [rbp+arg_0]
0x180011ef9  test    rsi, rsi
0x180011efc  jz      short loc_180011F17
0x180011efe  call    cs:__imp_GetLastError
0x180011f04  mov     ebx, eax
0x180011f06  mov     rcx, rsi; hKey
0x180011f09  call    cs:__imp_RegCloseKey
0x180011f0f  mov     ecx, ebx; dwErrCode
0x180011f11  call    cs:__imp_SetLastError
0x180011f17  mov     [rbp+arg_0], r13
0x180011f1b  cmp     qword ptr [rdi+18h], 8
0x180011f20  jb      short loc_180011F25
0x180011f22  mov     rdi, [rdi]
0x180011f25  mov     [rsp+68h+lpdwDisposition], r13; lpdwDisposition
0x180011f2a  lea     rax, [rbp+arg_0]
0x180011f2e  mov     [rsp+68h+phkResult], rax; phkResult
0x180011f33  mov     [rsp+68h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180011f38  mov     [rsp+68h+samDesired], 2; samDesired
0x180011f40  mov     [rsp+68h+dwOptions], r13d; unsigned int
0x180011f45  xor     r9d, r9d; lpClass
0x180011f48  xor     r8d, r8d; Reserved
0x180011f4b  mov     rdx, rdi; lpSubKey
0x180011f4e  mov     rcx, [rbp+var_10]; hKey
0x180011f52  call    cs:__imp_RegCreateKeyExW
0x180011f58  test    eax, eax
0x180011f5a  jz      short loc_180011F8E
0x180011f5c  mov     edx, 101h; void *
0x180011f61  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011f68  mov     r9d, eax; char *
0x180011f6b  mov     rcx, [rbp+40h]; this
0x180011f6f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011f74  mov     ebx, eax
0x180011f76  mov     rcx, [rbp+arg_0]; hKey
0x180011f7a  test    rcx, rcx
0x180011f7d  jz      loc_180011ED0
0x180011f83  call    cs:__imp_RegCloseKey
0x180011f89  jmp     loc_180011ED0
0x180011f8e  mov     [rsp+68h+samDesired], r15d; cbData
0x180011f93  mov     qword ptr [rsp+68h+dwOptions], r14; lpData
0x180011f98  mov     r9d, 3; dwType
0x180011f9e  xor     r8d, r8d; Reserved
0x180011fa1  mov     rdx, r12; lpValueName
0x180011fa4  mov     rcx, [rbp+arg_0]; hKey
0x180011fa8  call    cs:__imp_RegSetValueExW
0x180011fae  test    eax, eax
0x180011fb0  jz      short loc_180011FB9
0x180011fb2  mov     edx, 104h
0x180011fb7  jmp     short loc_180011F61
0x180011fb9  mov     rcx, [rbp+arg_0]; hKey
0x180011fbd  test    rcx, rcx
0x180011fc0  jz      short loc_180011FC9
0x180011fc2  call    cs:__imp_RegCloseKey
0x180011fc8  nop
0x180011fc9  mov     rcx, [rbp+var_10]; hKey
0x180011fcd  test    rcx, rcx
0x180011fd0  jz      short loc_180011FD9
0x180011fd2  call    cs:__imp_RegCloseKey
0x180011fd8  nop
0x180011fd9  mov     rcx, [rbp+hKey]; hKey
0x180011fdd  test    rcx, rcx
0x180011fe0  jz      short loc_180011FE8
0x180011fe2  call    cs:__imp_RegCloseKey
0x180011fe8  xor     eax, eax
0x180011fea  add     rsp, 68h
0x180011fee  pop     r15
0x180011ff0  pop     r14
0x180011ff2  pop     r13
0x180011ff4  pop     r12
0x180011ff6  pop     rdi
0x180011ff7  pop     rsi
0x180011ff8  pop     rbx
0x180011ff9  pop     rbp
0x180011ffa  retn
```
