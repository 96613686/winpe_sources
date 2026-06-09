# IsServiceRunning

- ea: `0x180004138`
- end: `0x18000422e`
- name: `IsServiceRunning`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006710`

## callees

- `0x180004138`
- `0x180051160`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004167`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004167`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004207`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004210`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004207`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004210`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004187`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800041c5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004187`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800041c5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000419d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800041db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000419d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800041db`

## string_xrefs

- `0x180004180`: `RemoteAccess`

## pseudocode

```c
_BOOL8 __fastcall IsServiceRunning(const WCHAR *a1)
{
  BOOL v1; // edi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbp
  SC_HANDLE v6; // rbx
  SC_HANDLE v7; // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = 0;
  v2 = OpenSCManagerW(a1, 0, 0x80000000);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"RemoteAccess", 4u);
    v5 = v4;
    if ( v4 )
    {
      if ( QueryServiceStatus(v4, &ServiceStatus) && ServiceStatus.dwCurrentState == 4 )
      {
        v6 = 0;
        v1 = 1;
      }
      else
      {
        v7 = OpenServiceW(v3, L"Router", 4u);
        v6 = v7;
        if ( v7 && QueryServiceStatus(v7, &ServiceStatus) )
          v1 = ServiceStatus.dwCurrentState == 4;
      }
      CloseServiceHandle(v5);
      if ( v6 )
        CloseServiceHandle(v6);
    }
    CloseServiceHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180004138  push    rbx
0x18000413a  push    rbp
0x18000413b  push    rsi
0x18000413c  push    rdi
0x18000413d  sub     rsp, 58h
0x180004141  mov     rax, cs:__security_cookie
0x180004148  xor     rax, rsp
0x18000414b  mov     [rsp+78h+var_38], rax
0x180004150  xorps   xmm0, xmm0
0x180004153  xor     edx, edx; lpDatabaseName
0x180004155  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18000415a  mov     r8d, 80000000h; dwDesiredAccess
0x180004160  xor     edi, edi
0x180004162  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180004167  call    cs:__imp_OpenSCManagerW
0x18000416d  mov     rsi, rax
0x180004170  test    rax, rax
0x180004173  jz      loc_180004216
0x180004179  lea     r8d, [rdi+4]; dwDesiredAccess
0x18000417d  mov     rcx, rax; hSCManager
0x180004180  lea     rdx, ServiceName; "RemoteAccess"
0x180004187  call    cs:__imp_OpenServiceW
0x18000418d  mov     rbp, rax
0x180004190  test    rax, rax
0x180004193  jz      short loc_18000420D
0x180004195  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18000419a  mov     rcx, rax; hService
0x18000419d  call    cs:__imp_QueryServiceStatus
0x1800041a3  test    eax, eax
0x1800041a5  jz      short loc_1800041B5
0x1800041a7  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800041ac  jnz     short loc_1800041B5
0x1800041ae  xor     ebx, ebx
0x1800041b0  lea     edi, [rbx+1]
0x1800041b3  jmp     short loc_1800041F6
0x1800041b5  mov     r8d, 4; dwDesiredAccess
0x1800041bb  lea     rdx, aRouter; "Router"
0x1800041c2  mov     rcx, rsi; hSCManager
0x1800041c5  call    cs:__imp_OpenServiceW
0x1800041cb  mov     rbx, rax
0x1800041ce  test    rax, rax
0x1800041d1  jz      short loc_1800041F6
0x1800041d3  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800041d8  mov     rcx, rax; hService
0x1800041db  call    cs:__imp_QueryServiceStatus
0x1800041e1  test    eax, eax
0x1800041e3  jz      short loc_1800041F6
0x1800041e5  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800041ea  mov     eax, edi
0x1800041ec  mov     edi, 1
0x1800041f1  cmovz   eax, edi
0x1800041f4  mov     edi, eax
0x1800041f6  mov     rcx, rbp; hSCObject
0x1800041f9  call    cs:__imp_CloseServiceHandle
0x1800041ff  test    rbx, rbx
0x180004202  jz      short loc_18000420D
0x180004204  mov     rcx, rbx; hSCObject
0x180004207  call    cs:__imp_CloseServiceHandle
0x18000420d  mov     rcx, rsi; hSCObject
0x180004210  call    cs:__imp_CloseServiceHandle
0x180004216  mov     eax, edi
0x180004218  mov     rcx, [rsp+78h+var_38]
0x18000421d  xor     rcx, rsp; StackCookie
0x180004220  call    __security_check_cookie
0x180004225  add     rsp, 58h
0x180004229  pop     rdi
0x18000422a  pop     rsi
0x18000422b  pop     rbp
0x18000422c  pop     rbx
0x18000422d  retn
```
