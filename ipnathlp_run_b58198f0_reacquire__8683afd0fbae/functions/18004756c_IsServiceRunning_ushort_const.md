# IsServiceRunning(ushort const *)

- ea: `0x18004756c`
- end: `0x180047746`
- name: `?IsServiceRunning@@YAHPEBG@Z`
- size: `474`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800271d0`
- `0x180065f20`

## callees

- `0x18000d090`
- `0x18003a66c`
- `0x18004561c`
- `0x18004756c`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004767b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004767b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800475d9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800475d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800476e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800476f0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800476e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800476f0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004764f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004764f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800476bb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800476bb`

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
0x18004756c  push    rbx
0x18004756e  push    rsi
0x18004756f  push    rdi
0x180047570  push    r14
0x180047572  sub     rsp, 58h
0x180047576  mov     rax, cs:__security_cookie
0x18004757d  xor     rax, rsp
0x180047580  mov     [rsp+78h+var_38], rax
0x180047585  mov     rcx, cs:WPP_GLOBAL_Control
0x18004758c  lea     r14, WPP_GLOBAL_Control
0x180047593  cmp     rcx, r14
0x180047596  jz      short loc_1800475C0
0x180047598  test    byte ptr [rcx+1Ch], 10h
0x18004759c  jz      short loc_1800475C0
0x18004759e  cmp     byte ptr [rcx+19h], 6
0x1800475a2  jb      short loc_1800475C0
0x1800475a4  mov     rcx, [rcx+10h]
0x1800475a8  lea     r9, aDns_0; "DNS"
0x1800475af  mov     edx, 21h ; '!'
0x1800475b4  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x1800475bb  call    WPP_SF_S
0x1800475c0  xorps   xmm0, xmm0
0x1800475c3  xor     edx, edx; lpDatabaseName
0x1800475c5  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800475ca  xor     ecx, ecx; lpMachineName
0x1800475cc  mov     r8d, 80000000h; dwDesiredAccess
0x1800475d2  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800475d7  xor     ebx, ebx
0x1800475d9  call    cs:__imp_OpenSCManagerW
0x1800475e0  nop     dword ptr [rax+rax+00h]
0x1800475e5  mov     rsi, rax
0x1800475e8  test    rax, rax
0x1800475eb  jnz     short loc_18004763F
0x1800475ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475f4  cmp     rcx, r14
0x1800475f7  jz      loc_18004772C
0x1800475fd  test    byte ptr [rcx+1Ch], 10h
0x180047601  jz      loc_180047703
0x180047607  cmp     byte ptr [rcx+19h], 2
0x18004760b  jb      loc_180047703
0x180047611  call    cs:__imp_GetLastError
0x180047618  nop     dword ptr [rax+rax+00h]
0x18004761d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047624  lea     edx, [rbx+22h]
0x180047627  mov     r9d, eax
0x18004762a  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180047631  mov     rcx, [rcx+10h]
0x180047635  call    WPP_SF_d
0x18004763a  jmp     loc_1800476FC
0x18004763f  mov     r8d, 4; dwDesiredAccess
0x180047645  lea     rdx, aDns_0; "DNS"
0x18004764c  mov     rcx, rsi; hSCManager
0x18004764f  call    cs:__imp_OpenServiceW
0x180047656  nop     dword ptr [rax+rax+00h]
0x18004765b  mov     rdi, rax
0x18004765e  test    rax, rax
0x180047661  jnz     short loc_1800476A6
0x180047663  mov     rax, cs:WPP_GLOBAL_Control
0x18004766a  cmp     rax, r14
0x18004766d  jz      short loc_1800476ED
0x18004766f  test    byte ptr [rax+1Ch], 10h
0x180047673  jz      short loc_1800476ED
0x180047675  cmp     byte ptr [rax+19h], 2
0x180047679  jb      short loc_1800476ED
0x18004767b  call    cs:__imp_GetLastError
0x180047682  nop     dword ptr [rax+rax+00h]
0x180047687  mov     rcx, cs:WPP_GLOBAL_Control
0x18004768e  lea     edx, [rdi+23h]
0x180047691  mov     r9d, eax
0x180047694  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18004769b  mov     rcx, [rcx+10h]
0x18004769f  call    WPP_SF_d
0x1800476a4  jmp     short loc_1800476ED
0x1800476a6  xorps   xmm0, xmm0
0x1800476a9  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800476ae  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800476b3  mov     rcx, rdi; hService
0x1800476b6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800476bb  call    cs:__imp_QueryServiceStatus
0x1800476c2  nop     dword ptr [rax+rax+00h]
0x1800476c7  test    eax, eax
0x1800476c9  jz      short loc_1800476DE
0x1800476cb  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x1800476cf  dec     eax
0x1800476d1  test    eax, 0FFFFFFFDh
0x1800476d6  mov     eax, 1
0x1800476db  cmovnz  ebx, eax
0x1800476de  mov     rcx, rdi; hSCObject
0x1800476e1  call    cs:__imp_CloseServiceHandle
0x1800476e8  nop     dword ptr [rax+rax+00h]
0x1800476ed  mov     rcx, rsi; hSCObject
0x1800476f0  call    cs:__imp_CloseServiceHandle
0x1800476f7  nop     dword ptr [rax+rax+00h]
0x1800476fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180047703  cmp     rcx, r14
0x180047706  jz      short loc_18004772C
0x180047708  test    byte ptr [rcx+1Ch], 10h
0x18004770c  jz      short loc_18004772C
0x18004770e  cmp     byte ptr [rcx+19h], 6
0x180047712  jb      short loc_18004772C
0x180047714  mov     rcx, [rcx+10h]
0x180047718  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18004771f  mov     r9b, bl
0x180047722  mov     edx, 24h ; '$'
0x180047727  call    WPP_SF_c
0x18004772c  mov     eax, ebx
0x18004772e  mov     rcx, [rsp+78h+var_38]
0x180047733  xor     rcx, rsp; StackCookie
0x180047736  call    __security_check_cookie
0x18004773b  add     rsp, 58h
0x18004773f  pop     r14
0x180047741  pop     rdi
0x180047742  pop     rsi
0x180047743  pop     rbx
0x180047744  retn
```
