# IsServiceDisabled(ushort const *)

- ea: `0x18001ec44`
- end: `0x18001ecc8`
- name: `?IsServiceDisabled@@YAHPEBG@Z`
- size: `132`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000b384`

## callees

- `0x18001ec44`
- `0x18001eda8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecb7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecb7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ec62`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ec62`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ec80`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ec80`

## string_xrefs

- `0x18001ec57`: `ServicesActive`

## pseudocode

```c
_BOOL8 __fastcall IsServiceDisabled(const unsigned __int16 *a1)
{
  BOOL v1; // ebx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  const unsigned __int16 *v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = a1;
  v1 = 0;
  v2 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"netprofm", 1u);
    v5 = v4;
    if ( v4 )
    {
      LODWORD(v7) = 0;
      if ( !(unsigned int)QueryServiceStartType(v4, (unsigned int *)&v7) )
        v1 = (_DWORD)v7 == 4;
      CloseServiceHandle(v5);
    }
    CloseServiceHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18001ec44  mov     [rsp+arg_0], rcx
0x18001ec49  push    rbx
0x18001ec4a  push    rbp
0x18001ec4b  push    rsi
0x18001ec4c  push    rdi
0x18001ec4d  sub     rsp, 28h
0x18001ec51  mov     r8d, 80000000h; dwDesiredAccess
0x18001ec57  lea     rdx, DatabaseName; "ServicesActive"
0x18001ec5e  xor     ecx, ecx; lpMachineName
0x18001ec60  xor     ebx, ebx
0x18001ec62  call    cs:__imp_OpenSCManagerW
0x18001ec68  mov     rdi, rax
0x18001ec6b  test    rax, rax
0x18001ec6e  jz      short loc_18001ECBD
0x18001ec70  lea     ebp, [rbx+1]
0x18001ec73  mov     rcx, rax; hSCManager
0x18001ec76  mov     r8d, ebp; dwDesiredAccess
0x18001ec79  lea     rdx, ServiceName; "netprofm"
0x18001ec80  call    cs:__imp_OpenServiceW
0x18001ec86  mov     rsi, rax
0x18001ec89  test    rax, rax
0x18001ec8c  jz      short loc_18001ECB4
0x18001ec8e  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x18001ec93  mov     dword ptr [rsp+48h+arg_0], ebx
0x18001ec97  mov     rcx, rax; hService
0x18001ec9a  call    ?QueryServiceStartType@@YAJPEAUSC_HANDLE__@@PEAK@Z; QueryServiceStartType(SC_HANDLE__ *,ulong *)
0x18001ec9f  test    eax, eax
0x18001eca1  jnz     short loc_18001ECAB
0x18001eca3  cmp     dword ptr [rsp+48h+arg_0], 4
0x18001eca8  cmovz   ebx, ebp
0x18001ecab  mov     rcx, rsi; hSCObject
0x18001ecae  call    cs:__imp_CloseServiceHandle
0x18001ecb4  mov     rcx, rdi; hSCObject
0x18001ecb7  call    cs:__imp_CloseServiceHandle
0x18001ecbd  mov     eax, ebx
0x18001ecbf  add     rsp, 28h
0x18001ecc3  pop     rdi
0x18001ecc4  pop     rsi
0x18001ecc5  pop     rbp
0x18001ecc6  pop     rbx
0x18001ecc7  retn
```
