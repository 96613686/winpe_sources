# PlaiBreakForDebugger(void)

- ea: `0x18010e338`
- end: `0x18010e3ed`
- name: `?PlaiBreakForDebugger@@YAXXZ`
- size: `181`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800f2870`

## callees

- `0x18010e338`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18010e35e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18010e35e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010e3d2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010e3d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e388`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e388`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e3e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e3e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010e3b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010e3b6`

## string_xrefs

- `0x18010e37a`: `System\CurrentControlSet\Services\PLA`

## pseudocode

```c
void PlaiBreakForDebugger(void)
{
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Type = 0;
  Data = 0;
  hKey = 0;
  cbData = 4;
  if ( IsDebuggerPresent()
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\PLA", 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, L"BreakOnStartup", 0, &Type, (LPBYTE)&Data, &cbData)
    && cbData == 4
    && Type == 4
    && Data == 1 )
  {
    DebugBreak();
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18010e338  push    rbp
0x18010e33a  mov     rbp, rsp
0x18010e33d  sub     rsp, 30h
0x18010e341  mov     [rbp+Type], 0
0x18010e348  mov     [rbp+Data], 0
0x18010e34f  mov     [rbp+hKey], 0
0x18010e357  mov     [rbp+cbData], 4
0x18010e35e  call    cs:__imp_IsDebuggerPresent
0x18010e364  test    eax, eax
0x18010e366  jz      short loc_18010E3D8
0x18010e368  lea     rax, [rbp+hKey]
0x18010e36c  mov     r9d, 1; samDesired
0x18010e372  xor     r8d, r8d; ulOptions
0x18010e375  mov     [rsp+30h+phkResult], rax; phkResult
0x18010e37a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\PL"...
0x18010e381  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18010e388  call    cs:__imp_RegOpenKeyExW
0x18010e38e  test    eax, eax
0x18010e390  jnz     short loc_18010E3D8
0x18010e392  mov     rcx, [rbp+hKey]; hKey
0x18010e396  lea     rax, [rbp+cbData]
0x18010e39a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18010e39f  lea     r9, [rbp+Type]; lpType
0x18010e3a3  lea     rax, [rbp+Data]
0x18010e3a7  xor     r8d, r8d; lpReserved
0x18010e3aa  lea     rdx, aBreakonstartup; "BreakOnStartup"
0x18010e3b1  mov     [rsp+30h+phkResult], rax; lpData
0x18010e3b6  call    cs:__imp_RegQueryValueExW
0x18010e3bc  test    eax, eax
0x18010e3be  jnz     short loc_18010E3D8
0x18010e3c0  cmp     [rbp+cbData], 4
0x18010e3c4  jnz     short loc_18010E3D8
0x18010e3c6  cmp     [rbp+Type], 4
0x18010e3ca  jnz     short loc_18010E3D8
0x18010e3cc  cmp     [rbp+Data], 1
0x18010e3d0  jnz     short loc_18010E3D8
0x18010e3d2  call    cs:__imp_DebugBreak
0x18010e3d8  mov     rcx, [rbp+hKey]; hKey
0x18010e3dc  test    rcx, rcx
0x18010e3df  jz      short loc_18010E3E7
0x18010e3e1  call    cs:__imp_RegCloseKey
0x18010e3e7  add     rsp, 30h
0x18010e3eb  pop     rbp
0x18010e3ec  retn
```
