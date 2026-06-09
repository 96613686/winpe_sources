# DialupOpenNamedService

- ea: `0x1800345d8`
- end: `0x18003468e`
- name: `DialupOpenNamedService`
- size: `182`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, __int64 *)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002df80`
- `0x18002e370`
- `0x18002e660`
- `0x18002e6bc`
- `0x18002ee94`
- `0x18003708c`
- `0x1800380d4`

## callees

- `0x180033a4c`
- `0x180033a84`
- `0x1800345d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003464c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003464c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003463d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003463d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003465b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180034669`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003465b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180034669`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180034623`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180034623`

## string_xrefs

- `0x18003461a`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall DialupOpenNamedService(LPCWSTR lpServiceName, __int64 *a2)
{
  __int64 v5; // rbx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rcx

  if ( !a2 )
    return 87;
  v5 = RassrvAlloc(48, 1);
  if ( !v5 )
    return 8;
  v6 = OpenSCManagerW(0, L"ServicesActive", 0x20000000u);
  *(_QWORD *)v5 = v6;
  if ( !v6 || (v7 = OpenServiceW(v6, lpServiceName, 0x36u), (*(_QWORD *)(v5 + 8) = v7) == 0) )
  {
    GetLastError();
    v8 = *(SC_HANDLE *)(v5 + 8);
    if ( v8 )
      CloseServiceHandle(v8);
    if ( *(_QWORD *)v5 )
      CloseServiceHandle(*(SC_HANDLE *)v5);
    RassrvFree((LPVOID)v5);
    v5 = 0;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800345d8  mov     [rsp+arg_0], rbx
0x1800345dd  mov     [rsp+arg_8], rsi
0x1800345e2  push    rdi
0x1800345e3  sub     rsp, 20h
0x1800345e7  mov     rdi, rdx
0x1800345ea  mov     rsi, rcx
0x1800345ed  test    rdx, rdx
0x1800345f0  jnz     short loc_1800345FA
0x1800345f2  lea     eax, [rdx+57h]
0x1800345f5  jmp     loc_18003467E
0x1800345fa  mov     edx, 1
0x1800345ff  lea     ecx, [rdx+2Fh]
0x180034602  call    RassrvAlloc
0x180034607  mov     rbx, rax
0x18003460a  test    rax, rax
0x18003460d  jnz     short loc_180034614
0x18003460f  lea     eax, [rbx+8]
0x180034612  jmp     short loc_18003467E
0x180034614  mov     r8d, 20000000h; dwDesiredAccess
0x18003461a  lea     rdx, DatabaseName; "ServicesActive"
0x180034621  xor     ecx, ecx; lpMachineName
0x180034623  call    cs:__imp_OpenSCManagerW
0x180034629  mov     [rbx], rax
0x18003462c  test    rax, rax
0x18003462f  jz      short loc_18003464C
0x180034631  mov     r8d, 36h ; '6'; dwDesiredAccess
0x180034637  mov     rdx, rsi; lpServiceName
0x18003463a  mov     rcx, rax; hSCManager
0x18003463d  call    cs:__imp_OpenServiceW
0x180034643  mov     [rbx+8], rax
0x180034647  test    rax, rax
0x18003464a  jnz     short loc_180034679
0x18003464c  call    cs:__imp_GetLastError
0x180034652  mov     rcx, [rbx+8]; hSCObject
0x180034656  test    rcx, rcx
0x180034659  jz      short loc_180034661
0x18003465b  call    cs:__imp_CloseServiceHandle
0x180034661  mov     rcx, [rbx]; hSCObject
0x180034664  test    rcx, rcx
0x180034667  jz      short loc_18003466F
0x180034669  call    cs:__imp_CloseServiceHandle
0x18003466f  mov     rcx, rbx; lpMem
0x180034672  call    RassrvFree
0x180034677  xor     ebx, ebx
0x180034679  mov     [rdi], rbx
0x18003467c  xor     eax, eax
0x18003467e  mov     rbx, [rsp+28h+arg_0]
0x180034683  mov     rsi, [rsp+28h+arg_8]
0x180034688  add     rsp, 20h
0x18003468c  pop     rdi
0x18003468d  retn
```
