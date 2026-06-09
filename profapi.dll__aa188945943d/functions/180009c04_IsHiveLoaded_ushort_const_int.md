# _IsHiveLoaded(ushort const *,int *)

- ea: `0x180009c04`
- end: `0x180009ca7`
- name: `?_IsHiveLoaded@@YAJPEBGPEAH@Z`
- size: `163`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d23c`

## callees

- `0x180003fdc`
- `0x180009c04`
- `0x180009cb0`
- `0x18000a1f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009c4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009c4c`

## pseudocode

```c
__int64 __fastcall _IsHiveLoaded(LPCWSTR lpSubKey, int *a2)
{
  unsigned int v4; // eax
  unsigned int v6; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v4 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( v4 != 2 )
  {
    if ( v4 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x25,
             (unsigned int)"minio\\profapi\\load.cpp",
             (const char *)v4,
             phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
    *a2 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180009c04  mov     [rsp+arg_0], rbx
0x180009c09  push    rdi
0x180009c0a  sub     rsp, 30h
0x180009c0e  mov     rdi, rdx
0x180009c11  mov     dword ptr [rdx], 0
0x180009c17  mov     rbx, rcx
0x180009c1a  mov     [rsp+38h+hKey], 0
0x180009c23  xor     edx, edx
0x180009c25  lea     rcx, [rsp+38h+hKey]
0x180009c2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180009c2f  lea     rax, [rsp+38h+hKey]
0x180009c34  mov     r9d, 2001Fh; samDesired
0x180009c3a  xor     r8d, r8d; ulOptions
0x180009c3d  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180009c42  mov     rdx, rbx; lpSubKey
0x180009c45  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180009c4c  call    cs:__imp_RegOpenKeyExW
0x180009c52  cmp     eax, 2
0x180009c55  jz      short loc_180009C61
0x180009c57  test    eax, eax
0x180009c59  jnz     short loc_180009C7E
0x180009c5b  mov     dword ptr [rdi], 1
0x180009c61  mov     rcx, [rsp+38h+hKey]; hKey
0x180009c66  test    rcx, rcx
0x180009c69  jz      short loc_180009C71
0x180009c6b  call    cs:__imp_RegCloseKey
0x180009c71  xor     eax, eax
0x180009c73  mov     rbx, [rsp+38h+arg_0]
0x180009c78  add     rsp, 30h
0x180009c7c  pop     rdi
0x180009c7d  retn
0x180009c7e  mov     rcx, [rsp+38h]; this
0x180009c83  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180009c8a  mov     r9d, eax; char *
0x180009c8d  mov     edx, 25h ; '%'; void *
0x180009c92  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009c97  lea     rcx, [rsp+38h+hKey]
0x180009c9c  mov     ebx, eax
0x180009c9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009ca3  mov     eax, ebx
0x180009ca5  jmp     short loc_180009C73
```
