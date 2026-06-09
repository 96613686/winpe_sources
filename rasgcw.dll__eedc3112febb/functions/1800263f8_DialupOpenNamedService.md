# DialupOpenNamedService

- ea: `0x1800263f8`
- end: `0x1800264ae`
- name: `DialupOpenNamedService`
- size: `182`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001ffac`
- `0x180020098`
- `0x180020240`
- `0x1800209f8`
- `0x180028f8c`
- `0x180029fc0`

## callees

- `0x180021438`
- `0x180021470`
- `0x1800263f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002646c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002646c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026443`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026443`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002647b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026489`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002647b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026489`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002645d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002645d`

## string_xrefs

- `0x18002643a`: `ServicesActive`

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
0x1800263f8  mov     [rsp+arg_0], rbx
0x1800263fd  mov     [rsp+arg_8], rsi
0x180026402  push    rdi
0x180026403  sub     rsp, 20h
0x180026407  mov     rdi, rdx
0x18002640a  mov     rsi, rcx
0x18002640d  test    rdx, rdx
0x180026410  jnz     short loc_18002641A
0x180026412  lea     eax, [rdx+57h]
0x180026415  jmp     loc_18002649E
0x18002641a  mov     edx, 1
0x18002641f  lea     ecx, [rdx+2Fh]
0x180026422  call    RassrvAlloc
0x180026427  mov     rbx, rax
0x18002642a  test    rax, rax
0x18002642d  jnz     short loc_180026434
0x18002642f  lea     eax, [rbx+8]
0x180026432  jmp     short loc_18002649E
0x180026434  mov     r8d, 20000000h; dwDesiredAccess
0x18002643a  lea     rdx, DatabaseName; "ServicesActive"
0x180026441  xor     ecx, ecx; lpMachineName
0x180026443  call    cs:__imp_OpenSCManagerW
0x180026449  mov     [rbx], rax
0x18002644c  test    rax, rax
0x18002644f  jz      short loc_18002646C
0x180026451  mov     r8d, 36h ; '6'; dwDesiredAccess
0x180026457  mov     rdx, rsi; lpServiceName
0x18002645a  mov     rcx, rax; hSCManager
0x18002645d  call    cs:__imp_OpenServiceW
0x180026463  mov     [rbx+8], rax
0x180026467  test    rax, rax
0x18002646a  jnz     short loc_180026499
0x18002646c  call    cs:__imp_GetLastError
0x180026472  mov     rcx, [rbx+8]; hSCObject
0x180026476  test    rcx, rcx
0x180026479  jz      short loc_180026481
0x18002647b  call    cs:__imp_CloseServiceHandle
0x180026481  mov     rcx, [rbx]; hSCObject
0x180026484  test    rcx, rcx
0x180026487  jz      short loc_18002648F
0x180026489  call    cs:__imp_CloseServiceHandle
0x18002648f  mov     rcx, rbx; lpMem
0x180026492  call    RassrvFree
0x180026497  xor     ebx, ebx
0x180026499  mov     [rdi], rbx
0x18002649c  xor     eax, eax
0x18002649e  mov     rbx, [rsp+28h+arg_0]
0x1800264a3  mov     rsi, [rsp+28h+arg_8]
0x1800264a8  add     rsp, 20h
0x1800264ac  pop     rdi
0x1800264ad  retn
```
