# _CloseRegistryKey

- ea: `0x1800095e0`
- end: `0x180009616`
- name: `_CloseRegistryKey`
- size: `54`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009388`
- `0x180009428`

## callees

- `0x1800095e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009605`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009605`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095fd`

## pseudocode

```c
void __fastcall CloseRegistryKey(HKEY hKey)
{
  DWORD LastError; // edi

  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x1800095e0  test    rcx, rcx
0x1800095e3  jz      short locret_180009615
0x1800095e5  push    rbx
0x1800095e6  sub     rsp, 20h
0x1800095ea  mov     rbx, rcx
0x1800095ed  mov     [rsp+28h+arg_0], rdi
0x1800095f2  call    cs:__imp_GetLastError
0x1800095f8  mov     rcx, rbx; hKey
0x1800095fb  mov     edi, eax
0x1800095fd  call    cs:__imp_RegCloseKey
0x180009603  mov     ecx, edi; dwErrCode
0x180009605  call    cs:__imp_SetLastError
0x18000960b  mov     rdi, [rsp+28h+arg_0]
0x180009610  add     rsp, 20h
0x180009614  pop     rbx
0x180009615  retn
```
