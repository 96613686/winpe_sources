# CDimSetup::GetRouterTransportEntries(ulong *)

- ea: `0x180030c4c`
- end: `0x180030d17`
- name: `?GetRouterTransportEntries@CDimSetup@@AEAAKPEAK@Z`
- size: `203`
- prototype: `unsigned int __fastcall(CDimSetup *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180031e60`

## callees

- `0x180030c4c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180030d01`
- `ADVAPI32!RegCloseKey` at `0x180030d01`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180030ce5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180030ce5`
- `ADVAPI32!RegOpenKeyW` at `0x180030c7f`
- `ADVAPI32!RegOpenKeyW` at `0x180030c7f`

## string_xrefs

- `0x180030c65`: `System\CurrentControlSet\Services\RemoteAccess\RouterManagers`

## pseudocode

```c
__int64 __fastcall CDimSetup::GetRouterTransportEntries(CDimSetup *this, unsigned int *a2)
{
  unsigned int InfoKeyW; // ebx
  CDimSetup *cSubKeys; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  cSubKeys = this;
  *a2 = 0;
  hKey = 0;
  InfoKeyW = RegOpenKeyW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Services\\RemoteAccess\\RouterManagers",
               &hKey);
  if ( !InfoKeyW )
  {
    LODWORD(cSubKeys) = 0;
    InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !InfoKeyW )
      *a2 = (unsigned int)cSubKeys;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return InfoKeyW;
}

```

## disassembly

```asm
0x180030c4c  mov     rax, rsp
0x180030c4f  mov     [rax+18h], rbx
0x180030c53  mov     [rax+8], rcx
0x180030c57  push    rdi
0x180030c58  sub     rsp, 60h
0x180030c5c  mov     rdi, rdx
0x180030c5f  mov     dword ptr [rdx], 0
0x180030c65  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Re"...
0x180030c6c  mov     qword ptr [rax+10h], 0
0x180030c74  lea     r8, [rax+10h]; phkResult
0x180030c78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030c7f  call    cs:__imp_RegOpenKeyW
0x180030c85  mov     ebx, eax
0x180030c87  test    eax, eax
0x180030c89  jnz     short loc_180030CF7
0x180030c8b  mov     rcx, [rsp+68h+hKey]; hKey
0x180030c90  xor     r9d, r9d; lpReserved
0x180030c93  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180030c9c  xor     r8d, r8d; lpcchClass
0x180030c9f  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180030ca8  xor     edx, edx; lpClass
0x180030caa  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180030cb3  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180030cbc  mov     [rsp+68h+lpcValues], 0; lpcValues
0x180030cc5  mov     dword ptr [rsp+68h+cSubKeys], eax
0x180030cc9  lea     rax, [rsp+68h+cSubKeys]
0x180030cce  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180030cd7  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180030ce0  mov     [rsp+68h+lpcSubKeys], rax; lpcSubKeys
0x180030ce5  call    cs:__imp_RegQueryInfoKeyW
0x180030ceb  mov     ebx, eax
0x180030ced  test    eax, eax
0x180030cef  jnz     short loc_180030CF7
0x180030cf1  mov     eax, dword ptr [rsp+68h+cSubKeys]
0x180030cf5  mov     [rdi], eax
0x180030cf7  mov     rcx, [rsp+68h+hKey]; hKey
0x180030cfc  test    rcx, rcx
0x180030cff  jz      short loc_180030D07
0x180030d01  call    cs:__imp_RegCloseKey
0x180030d07  mov     eax, ebx
0x180030d09  mov     rbx, [rsp+68h+arg_10]
0x180030d11  add     rsp, 60h
0x180030d15  pop     rdi
0x180030d16  retn
```
