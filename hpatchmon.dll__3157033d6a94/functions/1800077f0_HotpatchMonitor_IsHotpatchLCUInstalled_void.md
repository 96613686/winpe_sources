# HotpatchMonitor::IsHotpatchLCUInstalled(void)

- ea: `0x1800077f0`
- end: `0x1800078bc`
- name: `?IsHotpatchLCUInstalled@HotpatchMonitor@@MEAA_NXZ`
- size: `204`
- prototype: `bool __fastcall(HotpatchMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800077f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800078a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800078a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000787f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000787f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007827`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007827`

## pseudocode

```c
bool __fastcall HotpatchMonitor::IsHotpatchLCUInstalled(HotpatchMonitor *this)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  LSTATUS v3; // eax
  DWORD cSubKeys; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  cSubKeys = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegUtil::HOTPATCH_COMPONENT_KEY, 0, 0x20019u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    v2 = 0;
    v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v3 )
    {
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
      else
        v2 = v3;
    }
    RegCloseKey(hKey);
  }
  return v2 >= 0 && cSubKeys != 0;
}

```

## disassembly

```asm
0x1800077f0  mov     rax, rsp
0x1800077f3  push    rbx
0x1800077f4  sub     rsp, 60h
0x1800077f8  mov     rdx, cs:?HOTPATCH_COMPONENT_KEY@RegUtil@@0QEBGEB; lpSubKey
0x1800077ff  mov     r9d, 20019h; samDesired
0x180007805  mov     dword ptr [rax+10h], 0
0x18000780c  xor     r8d, r8d; ulOptions
0x18000780f  mov     qword ptr [rax+18h], 0
0x180007817  lea     rax, [rax+18h]
0x18000781b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007822  mov     [rsp+68h+phkResult], rax; phkResult
0x180007827  call    cs:__imp_RegOpenKeyExW
0x18000782d  mov     ebx, eax
0x18000782f  test    eax, eax
0x180007831  jz      short loc_180007840
0x180007833  jle     short loc_1800078A6
0x180007835  movzx   ebx, ax
0x180007838  or      ebx, 80070000h
0x18000783e  jmp     short loc_1800078A6
0x180007840  mov     rcx, [rsp+68h+hKey]; hKey
0x180007848  lea     rax, [rsp+68h+cSubKeys]
0x18000784d  xor     ebx, ebx
0x18000784f  xor     r9d, r9d; lpReserved
0x180007852  mov     [rsp+68h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180007857  xor     r8d, r8d; lpcchClass
0x18000785a  mov     [rsp+68h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18000785f  xor     edx, edx; lpClass
0x180007861  mov     [rsp+68h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180007866  mov     [rsp+68h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18000786b  mov     [rsp+68h+lpcValues], rbx; lpcValues
0x180007870  mov     [rsp+68h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180007875  mov     [rsp+68h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18000787a  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x18000787f  call    cs:__imp_RegQueryInfoKeyW
0x180007885  test    eax, eax
0x180007887  jz      short loc_180007898
0x180007889  jg      short loc_18000788F
0x18000788b  mov     ebx, eax
0x18000788d  jmp     short loc_180007898
0x18000788f  movzx   ebx, ax
0x180007892  or      ebx, 80070000h
0x180007898  mov     rcx, [rsp+68h+hKey]; hKey
0x1800078a0  call    cs:__imp_RegCloseKey
0x1800078a6  test    ebx, ebx
0x1800078a8  js      short loc_1800078B4
0x1800078aa  cmp     [rsp+68h+cSubKeys], 0
0x1800078af  setnz   al
0x1800078b2  jmp     short loc_1800078B6
0x1800078b4  xor     al, al
0x1800078b6  add     rsp, 60h
0x1800078ba  pop     rbx
0x1800078bb  retn
```
