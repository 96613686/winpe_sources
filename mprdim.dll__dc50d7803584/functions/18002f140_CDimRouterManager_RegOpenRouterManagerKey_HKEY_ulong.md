# CDimRouterManager::RegOpenRouterManagerKey(HKEY__ * &,ulong &)

- ea: `0x18002f140`
- end: `0x18002f226`
- name: `?RegOpenRouterManagerKey@CDimRouterManager@@CAKAEAPEAUHKEY__@@AEAK@Z`
- size: `230`
- prototype: `static unsigned int(HKEY *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002eb5c`
- `0x18002f22c`

## callees

- `0x18002f140`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002f18d`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f18d`
- `ADVAPI32!RegCloseKey` at `0x18002f20f`
- `ADVAPI32!RegCloseKey` at `0x18002f20f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002f1f4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002f1f4`

## string_xrefs

- `0x18002f161`: `System\CurrentControlSet\Services\RemoteAccess\RouterManagers`

## pseudocode

```c
__int64 __fastcall CDimRouterManager::RegOpenRouterManagerKey(HKEY *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  LSTATUS v5; // eax
  DWORD cbMaxValueNameLen; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbMaxValueLen; // [rsp+88h] [rbp+10h] BYREF
  DWORD cValues; // [rsp+90h] [rbp+18h] BYREF

  *a1 = 0;
  *a2 = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\RouterManagers",
         0,
         0x20019u,
         a1);
  if ( v4
    || (v5 = RegQueryInfoKeyW(*a1, 0, 0, 0, a2, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0),
        ++cbMaxValueNameLen,
        (v4 = v5) != 0) )
  {
    if ( *a1 )
    {
      RegCloseKey(*a1);
      *a1 = 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002f140  mov     rax, rsp
0x18002f143  push    rbx
0x18002f144  push    rsi
0x18002f145  push    rdi
0x18002f146  sub     rsp, 60h
0x18002f14a  mov     qword ptr [rcx], 0
0x18002f151  mov     rsi, rdx
0x18002f154  mov     dword ptr [rdx], 0
0x18002f15a  mov     rbx, rcx
0x18002f15d  mov     [rax-58h], rcx
0x18002f161  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Re"...
0x18002f168  mov     r9d, 20019h; samDesired
0x18002f16e  mov     dword ptr [rax+8], 0
0x18002f175  xor     r8d, r8d; ulOptions
0x18002f178  mov     dword ptr [rax+18h], 0
0x18002f17f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f186  mov     dword ptr [rax+10h], 0
0x18002f18d  call    cs:__imp_RegOpenKeyExW
0x18002f193  mov     edi, eax
0x18002f195  test    eax, eax
0x18002f197  jnz     short loc_18002F207
0x18002f199  mov     rcx, [rbx]; hKey
0x18002f19c  lea     rax, [rsp+78h+cbMaxValueLen]
0x18002f1a4  mov     [rsp+78h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002f1ad  xor     r9d, r9d; lpReserved
0x18002f1b0  mov     [rsp+78h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18002f1b9  xor     r8d, r8d; lpcchClass
0x18002f1bc  mov     [rsp+78h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002f1c1  xor     edx, edx; lpClass
0x18002f1c3  lea     rax, [rsp+78h+cbMaxValueNameLen]
0x18002f1cb  mov     [rsp+78h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002f1d0  lea     rax, [rsp+78h+cValues]
0x18002f1d8  mov     [rsp+78h+lpcValues], rax; lpcValues
0x18002f1dd  mov     [rsp+78h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18002f1e6  mov     [rsp+78h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18002f1ef  mov     [rsp+78h+lpcSubKeys], rsi; lpcSubKeys
0x18002f1f4  call    cs:__imp_RegQueryInfoKeyW
0x18002f1fa  inc     [rsp+78h+cbMaxValueNameLen]
0x18002f201  mov     edi, eax
0x18002f203  test    eax, eax
0x18002f205  jz      short loc_18002F21C
0x18002f207  mov     rcx, [rbx]; hKey
0x18002f20a  test    rcx, rcx
0x18002f20d  jz      short loc_18002F21C
0x18002f20f  call    cs:__imp_RegCloseKey
0x18002f215  mov     qword ptr [rbx], 0
0x18002f21c  mov     eax, edi
0x18002f21e  add     rsp, 60h
0x18002f222  pop     rdi
0x18002f223  pop     rsi
0x18002f224  pop     rbx
0x18002f225  retn
```
