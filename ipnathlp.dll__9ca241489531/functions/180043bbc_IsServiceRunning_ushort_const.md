# IsServiceRunning(ushort const *)

- ea: `0x180043bbc`
- end: `0x180043d6b`
- name: `?IsServiceRunning@@YAHPEBG@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180024c90`
- `0x1800613c0`

## callees

- `0x18000c750`
- `0x180037cf4`
- `0x18004215c`
- `0x180043bbc`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043cb9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180043c29`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180043c29`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043d13`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043d1c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043d13`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043d1c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180043c93`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180043c93`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180043cf3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180043cf3`

## pseudocode

```c
_BOOL8 __fastcall IsServiceRunning(const unsigned __int16 *a1)
{
  BOOL v1; // ebx
  SC_HANDLE v2; // rax
  __int64 v3; // r9
  SC_HANDLE v4; // rsi
  PVOID *v5; // rcx
  DWORD v6; // eax
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  DWORD LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, L"DNS");
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = 0;
  v2 = OpenSCManagerW(0, 0, 0x80000000);
  v4 = v2;
  if ( v2 )
  {
    v7 = OpenServiceW(v2, L"DNS", 4u);
    v8 = v7;
    if ( v7 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v7, &ServiceStatus) )
        v1 = ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) != 0;
      CloseServiceHandle(v8);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, LastError);
    }
    CloseServiceHandle(v4);
    goto LABEL_19;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v6);
LABEL_19:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 6u )
  {
    LOBYTE(v3) = v1;
    WPP_SF_c(v5[2], 36, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180043bbc  push    rbx
0x180043bbe  push    rsi
0x180043bbf  push    rdi
0x180043bc0  push    r14
0x180043bc2  sub     rsp, 58h
0x180043bc6  mov     rax, cs:__security_cookie
0x180043bcd  xor     rax, rsp
0x180043bd0  mov     [rsp+78h+var_38], rax
0x180043bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bdc  lea     r14, WPP_GLOBAL_Control
0x180043be3  cmp     rcx, r14
0x180043be6  jz      short loc_180043C10
0x180043be8  test    byte ptr [rcx+1Ch], 10h
0x180043bec  jz      short loc_180043C10
0x180043bee  cmp     byte ptr [rcx+19h], 6
0x180043bf2  jb      short loc_180043C10
0x180043bf4  mov     rcx, [rcx+10h]
0x180043bf8  lea     r9, aDns_0; "DNS"
0x180043bff  mov     edx, 21h ; '!'
0x180043c04  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180043c0b  call    WPP_SF_S
0x180043c10  xorps   xmm0, xmm0
0x180043c13  xor     edx, edx; lpDatabaseName
0x180043c15  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180043c1a  xor     ecx, ecx; lpMachineName
0x180043c1c  mov     r8d, 80000000h; dwDesiredAccess
0x180043c22  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180043c27  xor     ebx, ebx
0x180043c29  call    cs:__imp_OpenSCManagerW
0x180043c2f  mov     rsi, rax
0x180043c32  test    rax, rax
0x180043c35  jnz     short loc_180043C83
0x180043c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c3e  cmp     rcx, r14
0x180043c41  jz      loc_180043D52
0x180043c47  test    byte ptr [rcx+1Ch], 10h
0x180043c4b  jz      loc_180043D29
0x180043c51  cmp     byte ptr [rcx+19h], 2
0x180043c55  jb      loc_180043D29
0x180043c5b  call    cs:__imp_GetLastError
0x180043c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c68  lea     edx, [rbx+22h]
0x180043c6b  mov     r9d, eax
0x180043c6e  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180043c75  mov     rcx, [rcx+10h]
0x180043c79  call    WPP_SF_d
0x180043c7e  jmp     loc_180043D22
0x180043c83  mov     r8d, 4; dwDesiredAccess
0x180043c89  lea     rdx, aDns_0; "DNS"
0x180043c90  mov     rcx, rsi; hSCManager
0x180043c93  call    cs:__imp_OpenServiceW
0x180043c99  mov     rdi, rax
0x180043c9c  test    rax, rax
0x180043c9f  jnz     short loc_180043CDE
0x180043ca1  mov     rax, cs:WPP_GLOBAL_Control
0x180043ca8  cmp     rax, r14
0x180043cab  jz      short loc_180043D19
0x180043cad  test    byte ptr [rax+1Ch], 10h
0x180043cb1  jz      short loc_180043D19
0x180043cb3  cmp     byte ptr [rax+19h], 2
0x180043cb7  jb      short loc_180043D19
0x180043cb9  call    cs:__imp_GetLastError
0x180043cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180043cc6  lea     edx, [rdi+23h]
0x180043cc9  mov     r9d, eax
0x180043ccc  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180043cd3  mov     rcx, [rcx+10h]
0x180043cd7  call    WPP_SF_d
0x180043cdc  jmp     short loc_180043D19
0x180043cde  xorps   xmm0, xmm0
0x180043ce1  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180043ce6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180043ceb  mov     rcx, rdi; hService
0x180043cee  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180043cf3  call    cs:__imp_QueryServiceStatus
0x180043cf9  test    eax, eax
0x180043cfb  jz      short loc_180043D10
0x180043cfd  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x180043d01  dec     eax
0x180043d03  test    eax, 0FFFFFFFDh
0x180043d08  mov     eax, 1
0x180043d0d  cmovnz  ebx, eax
0x180043d10  mov     rcx, rdi; hSCObject
0x180043d13  call    cs:__imp_CloseServiceHandle
0x180043d19  mov     rcx, rsi; hSCObject
0x180043d1c  call    cs:__imp_CloseServiceHandle
0x180043d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d29  cmp     rcx, r14
0x180043d2c  jz      short loc_180043D52
0x180043d2e  test    byte ptr [rcx+1Ch], 10h
0x180043d32  jz      short loc_180043D52
0x180043d34  cmp     byte ptr [rcx+19h], 6
0x180043d38  jb      short loc_180043D52
0x180043d3a  mov     rcx, [rcx+10h]
0x180043d3e  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180043d45  mov     r9b, bl
0x180043d48  mov     edx, 24h ; '$'
0x180043d4d  call    WPP_SF_c
0x180043d52  mov     eax, ebx
0x180043d54  mov     rcx, [rsp+78h+var_38]
0x180043d59  xor     rcx, rsp; StackCookie
0x180043d5c  call    __security_check_cookie
0x180043d61  add     rsp, 58h
0x180043d65  pop     r14
0x180043d67  pop     rdi
0x180043d68  pop     rsi
0x180043d69  pop     rbx
0x180043d6a  retn
```
