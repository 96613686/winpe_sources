# _CloseHandle

- ea: `0x180005240`
- end: `0x180005276`
- name: `_CloseHandle`
- size: `54`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ac0`
- `0x1800050b0`

## callees

- `0x180005240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005252`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000525d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000525d`

## pseudocode

```c
void __fastcall CloseHandle(HANDLE hObject)
{
  DWORD LastError; // edi

  if ( hObject )
  {
    LastError = GetLastError();
    CloseHandle(hObject);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x180005240  test    rcx, rcx
0x180005243  jz      short locret_180005275
0x180005245  push    rbx
0x180005246  sub     rsp, 20h
0x18000524a  mov     rbx, rcx
0x18000524d  mov     [rsp+28h+arg_0], rdi
0x180005252  call    cs:__imp_GetLastError
0x180005258  mov     rcx, rbx; hObject
0x18000525b  mov     edi, eax
0x18000525d  call    cs:__imp_CloseHandle
0x180005263  mov     ecx, edi; dwErrCode
0x180005265  call    cs:__imp_SetLastError
0x18000526b  mov     rdi, [rsp+28h+arg_0]
0x180005270  add     rsp, 20h
0x180005274  pop     rbx
0x180005275  retn
```
