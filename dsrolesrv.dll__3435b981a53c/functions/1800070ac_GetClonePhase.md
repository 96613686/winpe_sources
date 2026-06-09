# GetClonePhase

- ea: `0x1800070ac`
- end: `0x180007179`
- name: `GetClonePhase`
- size: `205`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180003ff0`
- `0x180012460`

## callees

- `0x1800070ac`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000713c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000713c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007166`

## string_xrefs

- `0x1800070e1`: `System\CurrentControlSet\Services\NTDS\Parameters`
- `0x180007106`: `RegOpenKeyEx failed with %d\n`

## pseudocode

```c
__int64 __fastcall GetClonePhase(LPBYTE lpData)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  *(_DWORD *)lpData = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\NTDS\\Parameters", 0, 0x2000000u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    DsRolepLogPrintRoutine(1, "RegOpenKeyEx failed with %d\n", v2);
  }
  else
  {
    v4 = RegQueryValueExW(hKey, L"ClonePhase", 0, &Type, lpData, &cbData);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 == 2 )
        v3 = 0;
    }
    else if ( Type != 4 )
    {
      v3 = 13;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x1800070ac  mov     rax, rsp
0x1800070af  mov     [rax+20h], rbx
0x1800070b3  push    rdi
0x1800070b4  sub     rsp, 30h
0x1800070b8  mov     qword ptr [rax+18h], 0
0x1800070c0  mov     rdi, rcx
0x1800070c3  mov     dword ptr [rax+8], 0
0x1800070ca  mov     r9d, 2000000h; samDesired
0x1800070d0  mov     dword ptr [rax+10h], 4
0x1800070d7  lea     rax, [rax+18h]
0x1800070db  mov     dword ptr [rcx], 0
0x1800070e1  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\NT"...
0x1800070e8  xor     r8d, r8d; ulOptions
0x1800070eb  mov     [rsp+38h+phkResult], rax; phkResult
0x1800070f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800070f7  call    cs:__imp_RegOpenKeyExW
0x1800070fd  mov     ebx, eax
0x1800070ff  test    eax, eax
0x180007101  jz      short loc_180007119
0x180007103  mov     r8d, eax
0x180007106  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed with %d\n"
0x18000710d  mov     ecx, 1
0x180007112  call    DsRolepLogPrintRoutine
0x180007117  jmp     short loc_18000716C
0x180007119  mov     rcx, [rsp+38h+hKey]; hKey
0x18000711e  lea     rax, [rsp+38h+cbData]
0x180007123  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180007128  lea     r9, [rsp+38h+Type]; lpType
0x18000712d  xor     r8d, r8d; lpReserved
0x180007130  mov     [rsp+38h+phkResult], rdi; lpData
0x180007135  lea     rdx, ValueName; "ClonePhase"
0x18000713c  call    cs:__imp_RegQueryValueExW
0x180007142  mov     ebx, eax
0x180007144  test    eax, eax
0x180007146  jnz     short loc_180007154
0x180007148  cmp     [rsp+38h+Type], 4
0x18000714d  jz      short loc_18000715C
0x18000714f  lea     ebx, [rax+0Dh]
0x180007152  jmp     short loc_18000715C
0x180007154  xor     eax, eax
0x180007156  cmp     ebx, 2
0x180007159  cmovz   ebx, eax
0x18000715c  mov     rcx, [rsp+38h+hKey]; hKey
0x180007161  test    rcx, rcx
0x180007164  jz      short loc_18000716C
0x180007166  call    cs:__imp_RegCloseKey
0x18000716c  mov     eax, ebx
0x18000716e  mov     rbx, [rsp+38h+arg_18]
0x180007173  add     rsp, 30h
0x180007177  pop     rdi
0x180007178  retn
```
