# KnownUiccs::UndoConnectivitySettings(ushort const *)

- ea: `0x180035bb0`
- end: `0x180035c2b`
- name: `?UndoConnectivitySettings@KnownUiccs@@SAXPEBG@Z`
- size: `123`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180031410`

## callees

- `0x180012390`
- `0x180035bb0`
- `0x180035c34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035c0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035c0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035be3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035be3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall KnownUiccs::UndoConnectivitySettings(LPCWSTR lpSubKey)
{
  unsigned int v2; // eax
  const char *v3; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegUicc, 0, 0x10009u, &hKey);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x172,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v2,
      phkResult);
  try
  {
    UndoForUicc(hKey, lpSubKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x179,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180035bb0  push    rbx
0x180035bb2  sub     rsp, 30h
0x180035bb6  mov     rbx, rcx
0x180035bb9  mov     [rsp+38h+hKey], 0
0x180035bc2  lea     rax, [rsp+38h+hKey]
0x180035bc7  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180035bcc  mov     r9d, 10009h; samDesired
0x180035bd2  xor     r8d, r8d; ulOptions
0x180035bd5  mov     rdx, cs:?gc_wszRegUicc@@3PEBGEB; lpSubKey
0x180035bdc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035be3  call    cs:__imp_RegOpenKeyExW
0x180035be9  mov     rcx, [rsp+38h]; this
0x180035bee  test    eax, eax
0x180035bf0  jnz     short loc_180035C16
0x180035bf2  mov     rdx, rbx; lpSubKey
0x180035bf5  mov     rcx, [rsp+38h+hKey]; hKey
0x180035bfa  call    UndoForUicc
0x180035bff  nop
0x180035c00  mov     rcx, [rsp+38h+hKey]; hKey
0x180035c05  test    rcx, rcx
0x180035c08  jz      short loc_180035C10
0x180035c0a  call    cs:__imp_RegCloseKey
0x180035c10  add     rsp, 30h
0x180035c14  pop     rbx
0x180035c15  retn
0x180035c16  mov     r9d, eax; char *
0x180035c19  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035c20  mov     edx, 172h; void *
0x180035c25  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
