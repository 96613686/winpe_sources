# SockLoadTransportList

- ea: `0x18000c8c0`
- end: `0x18000ca18`
- name: `SockLoadTransportList`
- size: `344`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b3a0`
- `0x180010680`
- `0x18002b060`

## callees

- `0x18000c8c0`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000ca0a`
- `ntdll!RtlFreeHeap` at `0x18000ca0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c99f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c99f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c904`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c904`

## string_xrefs

- `0x18000c8fd`: `SYSTEM\CurrentControlSet\Services\Winsock\Parameters`

## pseudocode

```c
LSTATUS __fastcall SockLoadTransportList(PVOID *a1)
{
  LSTATUS result; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // ebx
  BYTE *v5; // rax
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  cbData = 0;
  hKey = 0;
  Type = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\Winsock\\Parameters",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    cbData = 0;
    v3 = RegQueryValueExW(hKey, L"Transports", 0, &Type, 0, &cbData);
    v4 = v3;
    if ( v3 != 234 && v3 )
      goto LABEL_7;
    if ( Type != 7 )
    {
      v4 = 1804;
      goto LABEL_7;
    }
    v5 = (BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0, cbData);
    *a1 = v5;
    if ( v5 )
    {
      v4 = RegQueryValueExW(hKey, L"Transports", 0, &Type, v5, &cbData);
      if ( !v4 )
      {
        if ( Type == 7 )
        {
LABEL_7:
          RegCloseKey(hKey);
          return v4;
        }
        v4 = 1804;
      }
      RegCloseKey(hKey);
      RtlFreeHeap(SockPrivateHeap, 0, *a1);
      return v4;
    }
    v4 = 8;
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x18000c8c0  push    rbp
0x18000c8c2  push    rbx
0x18000c8c3  push    rdi
0x18000c8c4  mov     rbp, rsp
0x18000c8c7  sub     rsp, 30h
0x18000c8cb  mov     rdi, rcx
0x18000c8ce  mov     [rbp+cbData], 0
0x18000c8d5  lea     rax, [rbp+hKey]
0x18000c8d9  mov     [rbp+hKey], 0
0x18000c8e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c8e8  mov     [rsp+30h+phkResult], rax; phkResult
0x18000c8ed  mov     r9d, 20019h; samDesired
0x18000c8f3  mov     [rbp+Type], 0
0x18000c8fa  xor     r8d, r8d; ulOptions
0x18000c8fd  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Wi"...
0x18000c904  call    cs:__imp_RegOpenKeyExW
0x18000c90b  nop     dword ptr [rax+rax+00h]
0x18000c910  test    eax, eax
0x18000c912  jnz     loc_18000C9C9
0x18000c918  mov     rcx, [rbp+hKey]; hKey
0x18000c91c  lea     r9, [rbp+Type]; lpType
0x18000c920  mov     [rbp+cbData], eax
0x18000c923  lea     rdx, ValueName; "Transports"
0x18000c92a  lea     rax, [rbp+cbData]
0x18000c92e  xor     r8d, r8d; lpReserved
0x18000c931  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000c936  mov     [rsp+30h+phkResult], 0; lpData
0x18000c93f  call    cs:__imp_RegQueryValueExW
0x18000c946  nop     dword ptr [rax+rax+00h]
0x18000c94b  mov     ebx, eax
0x18000c94d  cmp     eax, 0EAh
0x18000c952  jnz     short loc_18000C9D2
0x18000c954  cmp     [rbp+Type], 7
0x18000c958  jnz     loc_18000C9E2
0x18000c95e  mov     r8d, [rbp+cbData]
0x18000c962  xor     edx, edx
0x18000c964  mov     rcx, cs:SockPrivateHeap
0x18000c96b  mov     rax, cs:SockAllocateHeapRoutine
0x18000c972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c977  mov     [rdi], rax
0x18000c97a  test    rax, rax
0x18000c97d  jz      short loc_18000C9DB
0x18000c97f  lea     rcx, [rbp+cbData]
0x18000c983  xor     r8d, r8d; lpReserved
0x18000c986  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x18000c98b  lea     r9, [rbp+Type]; lpType
0x18000c98f  mov     rcx, [rbp+hKey]; hKey
0x18000c993  lea     rdx, ValueName; "Transports"
0x18000c99a  mov     [rsp+30h+phkResult], rax; lpData
0x18000c99f  call    cs:__imp_RegQueryValueExW
0x18000c9a6  nop     dword ptr [rax+rax+00h]
0x18000c9ab  mov     ebx, eax
0x18000c9ad  test    eax, eax
0x18000c9af  jnz     short loc_18000C9EE
0x18000c9b1  cmp     [rbp+Type], 7
0x18000c9b5  jnz     short loc_18000C9E9
0x18000c9b7  mov     rcx, [rbp+hKey]; hKey
0x18000c9bb  call    cs:__imp_RegCloseKey
0x18000c9c2  nop     dword ptr [rax+rax+00h]
0x18000c9c7  mov     eax, ebx
0x18000c9c9  add     rsp, 30h
0x18000c9cd  pop     rdi
0x18000c9ce  pop     rbx
0x18000c9cf  pop     rbp
0x18000c9d0  retn
0x18000c9d2  test    eax, eax
0x18000c9d4  jnz     short loc_18000C9B7
0x18000c9d6  jmp     loc_18000C954
0x18000c9db  mov     ebx, 8
0x18000c9e0  jmp     short loc_18000C9B7
0x18000c9e2  mov     ebx, 70Ch
0x18000c9e7  jmp     short loc_18000C9B7
0x18000c9e9  mov     ebx, 70Ch
0x18000c9ee  mov     rcx, [rbp+hKey]; hKey
0x18000c9f2  call    cs:__imp_RegCloseKey
0x18000c9f9  nop     dword ptr [rax+rax+00h]
0x18000c9fe  mov     r8, [rdi]; P
0x18000ca01  xor     edx, edx; Flags
0x18000ca03  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000ca0a  call    cs:__imp_RtlFreeHeap
0x18000ca11  nop     dword ptr [rax+rax+00h]
0x18000ca16  jmp     short loc_18000C9C7
```
