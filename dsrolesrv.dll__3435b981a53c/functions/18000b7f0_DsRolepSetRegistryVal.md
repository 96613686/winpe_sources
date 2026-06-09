# DsRolepSetRegistryVal

- ea: `0x18000b7f0`
- end: `0x18000b8c6`
- name: `DsRolepSetRegistryVal`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000d698`

## callees

- `0x18000b7f0`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b882`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b847`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b847`

## string_xrefs

- `0x18000b85a`: `SetRegistryVal: RegCreateKeyExW %ws failed with error 0x%x\n`
- `0x18000b895`: `SetRegistryVal: RegSetValueExW %ws failed with error 0x%x\n`
- `0x18000b810`: `System\CurrentControlSet\services\Netlogon\parameters\`
- `0x18000b853`: `System\CurrentControlSet\services\Netlogon\parameters\`
- `0x18000b868`: `SysvolReady`
- `0x18000b88e`: `SysvolReady`

## pseudocode

```c
__int64 __fastcall DsRolepSetRegistryVal(__int64 a1, __int64 a2, __int64 a3, const BYTE *a4)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\services\\Netlogon\\parameters\\",
         0,
         0,
         1u,
         0xF003Fu,
         0,
         &hKey,
         0);
  v6 = v5;
  if ( v5 )
  {
    DsRolepLogPrintRoutine(
      1,
      "SetRegistryVal: RegCreateKeyExW %ws failed with error 0x%x\n",
      L"System\\CurrentControlSet\\services\\Netlogon\\parameters\\",
      v5);
  }
  else
  {
    v7 = RegSetValueExW(hKey, L"SysvolReady", 0, 4u, a4, 4u);
    v6 = v7;
    if ( v7 )
      DsRolepLogPrintRoutine(1, "SetRegistryVal: RegSetValueExW %ws failed with error 0x%x\n", L"SysvolReady", v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000b7f0  mov     r11, rsp
0x18000b7f3  mov     [r11+8], rbx
0x18000b7f7  mov     [r11+18h], r8
0x18000b7fb  push    rdi
0x18000b7fc  sub     rsp, 50h
0x18000b800  mov     qword ptr [r11-18h], 0
0x18000b808  lea     rax, [r11+18h]
0x18000b80c  mov     [r11-20h], rax
0x18000b810  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\services\\Ne"...
0x18000b817  mov     qword ptr [r11-28h], 0
0x18000b81f  mov     rdi, r9
0x18000b822  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18000b82a  xor     r9d, r9d; lpClass
0x18000b82d  xor     r8d, r8d; Reserved
0x18000b830  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18000b838  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b83f  mov     qword ptr [r11+18h], 0
0x18000b847  call    cs:__imp_RegCreateKeyExW
0x18000b84d  mov     ebx, eax
0x18000b84f  test    eax, eax
0x18000b851  jz      short loc_18000B863
0x18000b853  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\services\\Ne"...
0x18000b85a  lea     rdx, aSetregistryval; "SetRegistryVal: RegCreateKeyExW %ws fai"...
0x18000b861  jmp     short loc_18000B89C
0x18000b863  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b868  lea     rdx, aSysvolready; "SysvolReady"
0x18000b86f  mov     r9d, 4; dwType
0x18000b875  xor     r8d, r8d; Reserved
0x18000b878  mov     [rsp+58h+samDesired], r9d; cbData
0x18000b87d  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x18000b882  call    cs:__imp_RegSetValueExW
0x18000b888  mov     ebx, eax
0x18000b88a  test    eax, eax
0x18000b88c  jz      short loc_18000B8A9
0x18000b88e  lea     r8, aSysvolready; "SysvolReady"
0x18000b895  lea     rdx, aSetregistryval_0; "SetRegistryVal: RegSetValueExW %ws fail"...
0x18000b89c  mov     r9d, eax
0x18000b89f  mov     ecx, 1
0x18000b8a4  call    DsRolepLogPrintRoutine
0x18000b8a9  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b8ae  test    rcx, rcx
0x18000b8b1  jz      short loc_18000B8B9
0x18000b8b3  call    cs:__imp_RegCloseKey
0x18000b8b9  mov     eax, ebx
0x18000b8bb  mov     rbx, [rsp+58h+arg_0]
0x18000b8c0  add     rsp, 50h
0x18000b8c4  pop     rdi
0x18000b8c5  retn
```
