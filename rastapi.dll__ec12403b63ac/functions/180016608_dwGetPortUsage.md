# dwGetPortUsage

- ea: `0x180016608`
- end: `0x1800166d9`
- name: `dwGetPortUsage`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000de88`

## callees

- `0x180016608`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016671`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016671`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166be`
- `rtutils!TracePrintfExA` at `0x18001663b`
- `rtutils!TracePrintfExA` at `0x18001668d`
- `rtutils!TracePrintfExA` at `0x18001663b`
- `rtutils!TracePrintfExA` at `0x18001668d`

## string_xrefs

- `0x180016681`: `dwAssignDefaultPortUsage: RemoteAccess not installed`
- `0x18001665e`: `System\CurrentControlSet\Services\RemoteAccess`

## pseudocode

```c
__int64 __fastcall dwGetPortUsage(_DWORD *a1)
{
  char v2; // al
  HKEY v3; // rcx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  TracePrintfExA(dwTraceId, 0x10006u, "dwGetPorTUsage:...");
  v2 = g_dwRasComponent;
  if ( !g_dwRasComponent )
  {
    g_dwRasComponent = 1;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RemoteAccess", 0, 1u, &hKey) )
    {
      TracePrintfExA(dwTraceId, 0x10006u, "dwAssignDefaultPortUsage: RemoteAccess not installed");
      v2 = g_dwRasComponent;
    }
    else
    {
      v2 = 2;
      g_dwRasComponent = 2;
    }
  }
  v3 = hKey;
  *a1 = (v2 & 2) != 0 ? 7 : 2;
  if ( v3 )
    RegCloseKey(v3);
  return 0;
}

```

## disassembly

```asm
0x180016608  push    rbx
0x18001660a  sub     rsp, 40h
0x18001660e  mov     rax, cs:__security_cookie
0x180016615  xor     rax, rsp
0x180016618  mov     [rsp+48h+var_10], rax
0x18001661d  mov     rbx, rcx
0x180016620  mov     [rsp+48h+hKey], 0
0x180016629  mov     ecx, cs:dwTraceId; dwTraceID
0x18001662f  lea     r8, aDwgetportusage; "dwGetPorTUsage:..."
0x180016636  mov     edx, 10006h; dwFlags
0x18001663b  call    cs:__imp_TracePrintfExA
0x180016641  mov     eax, cs:g_dwRasComponent
0x180016647  test    eax, eax
0x180016649  jnz     short loc_1800166A6
0x18001664b  lea     r9d, [rax+1]; samDesired
0x18001664f  xor     r8d, r8d; ulOptions
0x180016652  lea     rax, [rsp+48h+hKey]
0x180016657  mov     cs:g_dwRasComponent, r9d
0x18001665e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x180016665  mov     [rsp+48h+phkResult], rax; phkResult
0x18001666a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016671  call    cs:__imp_RegOpenKeyExW
0x180016677  test    eax, eax
0x180016679  jz      short loc_18001669B
0x18001667b  mov     ecx, cs:dwTraceId; dwTraceID
0x180016681  lea     r8, aDwassigndefaul; "dwAssignDefaultPortUsage: RemoteAccess "...
0x180016688  mov     edx, 10006h; dwFlags
0x18001668d  call    cs:__imp_TracePrintfExA
0x180016693  mov     eax, cs:g_dwRasComponent
0x180016699  jmp     short loc_1800166A6
0x18001669b  mov     eax, 2
0x1800166a0  mov     cs:g_dwRasComponent, eax
0x1800166a6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800166ab  and     al, 2
0x1800166ad  neg     al
0x1800166af  sbb     eax, eax
0x1800166b1  and     eax, 5
0x1800166b4  add     eax, 2
0x1800166b7  mov     [rbx], eax
0x1800166b9  test    rcx, rcx
0x1800166bc  jz      short loc_1800166C4
0x1800166be  call    cs:__imp_RegCloseKey
0x1800166c4  xor     eax, eax
0x1800166c6  mov     rcx, [rsp+48h+var_10]
0x1800166cb  xor     rcx, rsp; StackCookie
0x1800166ce  call    __security_check_cookie
0x1800166d3  add     rsp, 40h
0x1800166d7  pop     rbx
0x1800166d8  retn
```
