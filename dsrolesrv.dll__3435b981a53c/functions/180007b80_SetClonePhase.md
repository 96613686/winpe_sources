# SetClonePhase

- ea: `0x180007b80`
- end: `0x180007c19`
- name: `SetClonePhase`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180006b70`

## callees

- `0x180007b80`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007bb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007bb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007bfe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007bfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c0b`

## string_xrefs

- `0x180007baa`: `System\CurrentControlSet\Services\NTDS\Parameters`
- `0x180007bc7`: `RegOpenKeyEx failed with %d\n`

## pseudocode

```c
__int64 SetClonePhase()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  BYTE Data[24]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  *(_DWORD *)Data = 1;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\NTDS\\Parameters", 0, 2u, &hKey);
  v1 = v0;
  if ( v0 )
  {
    DsRolepLogPrintRoutine(1, "RegOpenKeyEx failed with %d\n", v0);
  }
  else
  {
    v1 = RegSetValueExW(hKey, L"ClonePhase", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x180007b80  push    rbx
0x180007b82  sub     rsp, 40h
0x180007b86  lea     rax, [rsp+48h+hKey]
0x180007b8b  mov     dword ptr [rsp+48h+Data], 1
0x180007b93  mov     r9d, 2; samDesired
0x180007b99  mov     [rsp+48h+phkResult], rax; phkResult
0x180007b9e  xor     r8d, r8d; ulOptions
0x180007ba1  mov     [rsp+48h+hKey], 0
0x180007baa  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\NT"...
0x180007bb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007bb8  call    cs:__imp_RegOpenKeyExW
0x180007bbe  mov     ebx, eax
0x180007bc0  test    eax, eax
0x180007bc2  jz      short loc_180007BDA
0x180007bc4  mov     r8d, eax
0x180007bc7  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed with %d\n"
0x180007bce  mov     ecx, 1
0x180007bd3  call    DsRolepLogPrintRoutine
0x180007bd8  jmp     short loc_180007C11
0x180007bda  mov     rcx, [rsp+48h+hKey]; hKey
0x180007bdf  lea     rax, [rsp+48h+Data]
0x180007be4  mov     r9d, 4; dwType
0x180007bea  lea     rdx, ValueName; "ClonePhase"
0x180007bf1  mov     [rsp+48h+cbData], r9d; cbData
0x180007bf6  xor     r8d, r8d; Reserved
0x180007bf9  mov     [rsp+48h+phkResult], rax; lpData
0x180007bfe  call    cs:__imp_RegSetValueExW
0x180007c04  mov     rcx, [rsp+48h+hKey]; hKey
0x180007c09  mov     ebx, eax
0x180007c0b  call    cs:__imp_RegCloseKey
0x180007c11  mov     eax, ebx
0x180007c13  add     rsp, 40h
0x180007c17  pop     rbx
0x180007c18  retn
```
