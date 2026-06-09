# CADMCOMW::EnumAndStopDependentServices(ulong *,BUFFER *)

- ea: `0x1800046a4`
- end: `0x1800048b7`
- name: `?EnumAndStopDependentServices@CADMCOMW@@AEAAJPEAKPEAVBUFFER@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int *, struct BUFFER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008ae0`

## callees

- `0x1800046a4`
- `0x180009ac4`
- `0x18000fb50`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180004700`
- `ADVAPI32!OpenSCManagerW` at `0x180004700`
- `ADVAPI32!OpenServiceW` at `0x18000473e`
- `ADVAPI32!OpenServiceW` at `0x180004820`
- `ADVAPI32!OpenServiceW` at `0x18000473e`
- `ADVAPI32!OpenServiceW` at `0x180004820`
- `ADVAPI32!EnumDependentServicesW` at `0x180004791`
- `ADVAPI32!EnumDependentServicesW` at `0x1800047e4`
- `ADVAPI32!EnumDependentServicesW` at `0x180004791`
- `ADVAPI32!EnumDependentServicesW` at `0x1800047e4`
- `ADVAPI32!ControlService` at `0x18000483a`
- `ADVAPI32!ControlService` at `0x18000483a`
- `ADVAPI32!CloseServiceHandle` at `0x180004850`
- `ADVAPI32!CloseServiceHandle` at `0x180004868`
- `ADVAPI32!CloseServiceHandle` at `0x180004876`
- `ADVAPI32!CloseServiceHandle` at `0x180004884`
- `ADVAPI32!CloseServiceHandle` at `0x180004850`
- `ADVAPI32!CloseServiceHandle` at `0x180004868`
- `ADVAPI32!CloseServiceHandle` at `0x180004876`
- `ADVAPI32!CloseServiceHandle` at `0x180004884`
- `KERNEL32!GetLastError` at `0x18000470e`
- `KERNEL32!GetLastError` at `0x18000474c`
- `KERNEL32!GetLastError` at `0x18000479b`
- `KERNEL32!GetLastError` at `0x18000470e`
- `KERNEL32!GetLastError` at `0x18000474c`
- `KERNEL32!GetLastError` at `0x18000479b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800047ae`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800047ae`

## pseudocode

```c
__int64 __fastcall CADMCOMW::EnumAndStopDependentServices(CADMCOMW *this, unsigned int *a2, struct BUFFER *a3)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r15
  signed int LastError; // eax
  unsigned int v8; // ebx
  SC_HANDLE v9; // rdi
  SC_HANDLE v10; // r14
  signed int v11; // eax
  struct _ENUM_SERVICE_STATUSW *v12; // r13
  DWORD v13; // ecx
  __int64 i; // rsi
  SC_HANDLE v15; // rax
  DWORD ServicesReturned; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbBufSize; // [rsp+34h] [rbp-2Ch] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  cbBufSize = 0;
  ServicesReturned = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  v5 = OpenSCManagerW(0, 0, 0xF003Fu);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v8;
  }
  v9 = 0;
  v10 = OpenServiceW(v5, L"IISADMIN", 0xF0008u);
  if ( !v10 )
    goto LABEL_7;
  v12 = (struct _ENUM_SERVICE_STATUSW *)*((_QWORD *)a3 + 4);
  if ( EnumDependentServicesW(v10, 1u, v12, *((_DWORD *)a3 + 10), &cbBufSize, &ServicesReturned) )
  {
LABEL_14:
    v13 = ServicesReturned;
    v8 = 0;
    for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
    {
      if ( ((v12[i].ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) != 0 )
      {
        v15 = OpenServiceW(v6, v12[i].lpServiceName, 0xF01FFu);
        v9 = v15;
        if ( v15 )
        {
          ControlService(v15, 1u, &ServiceStatus);
          WaitForServiceStatus(v9, 1u);
          CloseServiceHandle(v9);
          v9 = 0;
        }
        v13 = ServicesReturned;
      }
    }
    *a2 = v13;
    goto LABEL_21;
  }
  if ( GetLastError() != 234 )
  {
LABEL_7:
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_21;
  }
  if ( BUFFER::Resize(a3, cbBufSize) )
  {
    v12 = (struct _ENUM_SERVICE_STATUSW *)*((_QWORD *)a3 + 4);
    if ( EnumDependentServicesW(v10, 1u, v12, cbBufSize, &cbBufSize, &ServicesReturned) )
      goto LABEL_14;
    goto LABEL_7;
  }
  v8 = -2147024882;
LABEL_21:
  CloseServiceHandle(v6);
  if ( v10 )
    CloseServiceHandle(v10);
  if ( v9 )
    CloseServiceHandle(v9);
  return v8;
}

```

## disassembly

```asm
0x1800046a4  mov     [rsp-38h+arg_0], rbx
0x1800046a9  push    rbp
0x1800046aa  push    rsi
0x1800046ab  push    rdi
0x1800046ac  push    r12
0x1800046ae  push    r13
0x1800046b0  push    r14
0x1800046b2  push    r15
0x1800046b4  mov     rbp, rsp
0x1800046b7  sub     rsp, 60h
0x1800046bb  mov     rax, cs:__security_cookie
0x1800046c2  xor     rax, rsp
0x1800046c5  mov     [rbp+var_8], rax
0x1800046c9  xor     eax, eax
0x1800046cb  xorps   xmm0, xmm0
0x1800046ce  mov     [rbp+cbBufSize], eax
0x1800046d1  mov     rbx, r8
0x1800046d4  mov     [rbp+ServicesReturned], eax
0x1800046d7  mov     r12, rdx
0x1800046da  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1800046de  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1800046e2  test    rdx, rdx
0x1800046e5  jz      loc_18000488C
0x1800046eb  test    rbx, rbx
0x1800046ee  jz      loc_18000488C
0x1800046f4  mov     [rdx], eax
0x1800046f6  xor     ecx, ecx; lpMachineName
0x1800046f8  xor     edx, edx; lpDatabaseName
0x1800046fa  mov     r8d, 0F003Fh; dwDesiredAccess
0x180004700  call    cs:__imp_OpenSCManagerW
0x180004706  mov     r15, rax
0x180004709  test    rax, rax
0x18000470c  jnz     short loc_18000472C
0x18000470e  call    cs:__imp_GetLastError
0x180004714  mov     ebx, eax
0x180004716  test    eax, eax
0x180004718  jle     loc_180004891
0x18000471e  movzx   ebx, ax
0x180004721  or      ebx, 80070000h
0x180004727  jmp     loc_180004891
0x18000472c  mov     r8d, 0F0008h; dwDesiredAccess
0x180004732  lea     rdx, ServiceName; "IISADMIN"
0x180004739  mov     rcx, r15; hSCManager
0x18000473c  xor     edi, edi
0x18000473e  call    cs:__imp_OpenServiceW
0x180004744  mov     r14, rax
0x180004747  test    rax, rax
0x18000474a  jnz     short loc_18000476A
0x18000474c  call    cs:__imp_GetLastError
0x180004752  mov     ebx, eax
0x180004754  test    eax, eax
0x180004756  jle     loc_180004865
0x18000475c  movzx   ebx, ax
0x18000475f  or      ebx, 80070000h
0x180004765  jmp     loc_180004865
0x18000476a  mov     r13, [rbx+20h]
0x18000476e  lea     rax, [rbp+ServicesReturned]
0x180004772  mov     r9d, [rbx+28h]; cbBufSize
0x180004776  mov     esi, 1
0x18000477b  mov     [rsp+60h+lpServicesReturned], rax; lpServicesReturned
0x180004780  mov     r8, r13; lpServices
0x180004783  lea     rax, [rbp+cbBufSize]
0x180004787  mov     edx, esi; dwServiceState
0x180004789  mov     rcx, r14; hService
0x18000478c  mov     [rsp+60h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180004791  call    cs:__imp_EnumDependentServicesW
0x180004797  test    eax, eax
0x180004799  jnz     short loc_1800047F2
0x18000479b  call    cs:__imp_GetLastError
0x1800047a1  cmp     eax, 0EAh
0x1800047a6  jnz     short loc_18000474C
0x1800047a8  mov     edx, [rbp+cbBufSize]
0x1800047ab  mov     rcx, rbx
0x1800047ae  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800047b4  test    al, al
0x1800047b6  jnz     short loc_1800047C2
0x1800047b8  mov     ebx, 8007000Eh
0x1800047bd  jmp     loc_180004865
0x1800047c2  mov     r13, [rbx+20h]
0x1800047c6  lea     rax, [rbp+ServicesReturned]
0x1800047ca  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x1800047ce  mov     r8, r13; lpServices
0x1800047d1  mov     [rsp+60h+lpServicesReturned], rax; lpServicesReturned
0x1800047d6  mov     edx, esi; dwServiceState
0x1800047d8  lea     rax, [rbp+cbBufSize]
0x1800047dc  mov     rcx, r14; hService
0x1800047df  mov     [rsp+60h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800047e4  call    cs:__imp_EnumDependentServicesW
0x1800047ea  test    eax, eax
0x1800047ec  jz      loc_18000474C
0x1800047f2  mov     ecx, [rbp+ServicesReturned]
0x1800047f5  xor     ebx, ebx
0x1800047f7  xor     esi, esi
0x1800047f9  test    ecx, ecx
0x1800047fb  jz      short loc_180004861
0x1800047fd  lea     rdx, [rsi+rsi*2]
0x180004801  add     rdx, rdx
0x180004804  mov     eax, [r13+rdx*8+14h]
0x180004809  dec     eax
0x18000480b  test    eax, 0FFFFFFFDh
0x180004810  jz      short loc_18000485B
0x180004812  mov     rdx, [r13+rdx*8+0]; lpServiceName
0x180004817  mov     r8d, 0F01FFh; dwDesiredAccess
0x18000481d  mov     rcx, r15; hSCManager
0x180004820  call    cs:__imp_OpenServiceW
0x180004826  mov     rdi, rax
0x180004829  test    rax, rax
0x18000482c  jz      short loc_180004858
0x18000482e  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x180004832  mov     edx, 1; dwControl
0x180004837  mov     rcx, rax; hService
0x18000483a  call    cs:__imp_ControlService
0x180004840  mov     edx, 1; unsigned int
0x180004845  mov     rcx, rdi; hService
0x180004848  call    ?WaitForServiceStatus@@YAXPEAUSC_HANDLE__@@K@Z; WaitForServiceStatus(SC_HANDLE__ *,ulong)
0x18000484d  mov     rcx, rdi; hSCObject
0x180004850  call    cs:__imp_CloseServiceHandle
0x180004856  xor     edi, edi
0x180004858  mov     ecx, [rbp+ServicesReturned]
0x18000485b  inc     esi
0x18000485d  cmp     esi, ecx
0x18000485f  jb      short loc_1800047FD
0x180004861  mov     [r12], ecx
0x180004865  mov     rcx, r15; hSCObject
0x180004868  call    cs:__imp_CloseServiceHandle
0x18000486e  test    r14, r14
0x180004871  jz      short loc_18000487C
0x180004873  mov     rcx, r14; hSCObject
0x180004876  call    cs:__imp_CloseServiceHandle
0x18000487c  test    rdi, rdi
0x18000487f  jz      short loc_180004891
0x180004881  mov     rcx, rdi; hSCObject
0x180004884  call    cs:__imp_CloseServiceHandle
0x18000488a  jmp     short loc_180004891
0x18000488c  mov     ebx, 80070057h
0x180004891  mov     eax, ebx
0x180004893  mov     rcx, [rbp+var_8]
0x180004897  xor     rcx, rsp; StackCookie
0x18000489a  call    __security_check_cookie
0x18000489f  mov     rbx, [rsp+60h+arg_0]
0x1800048a7  add     rsp, 60h
0x1800048ab  pop     r15
0x1800048ad  pop     r14
0x1800048af  pop     r13
0x1800048b1  pop     r12
0x1800048b3  pop     rdi
0x1800048b4  pop     rsi
0x1800048b5  pop     rbp
0x1800048b6  retn
```
