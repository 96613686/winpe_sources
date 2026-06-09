# RegUtil::SetAutologgerLastRunTime(unsigned __int64 const &)

- ea: `0x18000d568`
- end: `0x18000d60a`
- name: `?SetAutologgerLastRunTime@RegUtil@@SAJAEB_K@Z`
- size: `162`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180009a80`

## callees

- `0x18000d568`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d5f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d5f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d5d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d5d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d59e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d59e`

## pseudocode

```c
__int64 __fastcall RegUtil::SetAutologgerLastRunTime(BYTE *lpData)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegUtil::SERVICE_KEY, 0, 0x20006u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v3 = 0;
    v4 = RegSetValueExW(hKey, L"AutologgerLastRunTime", 0, 0xBu, lpData, 8u);
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      else
        v3 = v4;
    }
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d568  mov     r11, rsp
0x18000d56b  mov     [r11+8], rbx
0x18000d56f  push    rdi
0x18000d570  sub     rsp, 30h
0x18000d574  mov     rdx, cs:?SERVICE_KEY@RegUtil@@0QEBGEB; lpSubKey
0x18000d57b  lea     rax, [r11+10h]
0x18000d57f  mov     rdi, rcx
0x18000d582  mov     [r11-18h], rax
0x18000d586  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d58d  mov     qword ptr [r11+10h], 0
0x18000d595  mov     r9d, 20006h; samDesired
0x18000d59b  xor     r8d, r8d; ulOptions
0x18000d59e  call    cs:__imp_RegOpenKeyExW
0x18000d5a4  mov     ebx, eax
0x18000d5a6  test    eax, eax
0x18000d5a8  jz      short loc_18000D5B7
0x18000d5aa  jle     short loc_18000D5FD
0x18000d5ac  movzx   ebx, ax
0x18000d5af  or      ebx, 80070000h
0x18000d5b5  jmp     short loc_18000D5FD
0x18000d5b7  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d5bc  lea     rdx, ValueName; "AutologgerLastRunTime"
0x18000d5c3  xor     ebx, ebx
0x18000d5c5  mov     [rsp+38h+cbData], 8; cbData
0x18000d5cd  xor     r8d, r8d; Reserved
0x18000d5d0  mov     [rsp+38h+lpData], rdi; lpData
0x18000d5d5  lea     r9d, [rbx+0Bh]; dwType
0x18000d5d9  call    cs:__imp_RegSetValueExW
0x18000d5df  test    eax, eax
0x18000d5e1  jz      short loc_18000D5F2
0x18000d5e3  jg      short loc_18000D5E9
0x18000d5e5  mov     ebx, eax
0x18000d5e7  jmp     short loc_18000D5F2
0x18000d5e9  movzx   ebx, ax
0x18000d5ec  or      ebx, 80070000h
0x18000d5f2  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d5f7  call    cs:__imp_RegCloseKey
0x18000d5fd  mov     eax, ebx
0x18000d5ff  mov     rbx, [rsp+38h+arg_0]
0x18000d604  add     rsp, 30h
0x18000d608  pop     rdi
0x18000d609  retn
```
