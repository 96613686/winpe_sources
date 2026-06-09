# NfsNpIsClientRunning

- ea: `0x180008d00`
- end: `0x180008f7f`
- name: `NfsNpIsClientRunning`
- size: `639`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004a40`
- `0x180005c40`
- `0x1800061c0`
- `0x180006890`
- `0x180006b50`
- `0x180007860`
- `0x180008150`
- `0x180008570`

## callees

- `0x180008d00`
- `0x18000937c`
- `0x180012e70`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180008d6b`
- `KERNEL32!GetTickCount64` at `0x180008f13`
- `KERNEL32!GetTickCount64` at `0x180008d6b`
- `KERNEL32!GetTickCount64` at `0x180008f13`
- `KERNEL32!LeaveCriticalSection` at `0x180008dd5`
- `KERNEL32!LeaveCriticalSection` at `0x180008f31`
- `KERNEL32!LeaveCriticalSection` at `0x180008dd5`
- `KERNEL32!LeaveCriticalSection` at `0x180008f31`
- `KERNEL32!EnterCriticalSection` at `0x180008d50`
- `KERNEL32!EnterCriticalSection` at `0x180008ef4`
- `KERNEL32!EnterCriticalSection` at `0x180008d50`
- `KERNEL32!EnterCriticalSection` at `0x180008ef4`
- `KERNEL32!GetLastError` at `0x180008e4a`
- `KERNEL32!GetLastError` at `0x180008e91`
- `KERNEL32!GetLastError` at `0x180008ecc`
- `KERNEL32!GetLastError` at `0x180008e4a`
- `KERNEL32!GetLastError` at `0x180008e91`
- `KERNEL32!GetLastError` at `0x180008ecc`
- `ADVAPI32!QueryServiceStatus` at `0x180008ebc`
- `ADVAPI32!QueryServiceStatus` at `0x180008ebc`
- `ADVAPI32!CloseServiceHandle` at `0x180008f45`
- `ADVAPI32!CloseServiceHandle` at `0x180008f59`
- `ADVAPI32!CloseServiceHandle` at `0x180008f45`
- `ADVAPI32!CloseServiceHandle` at `0x180008f59`
- `ADVAPI32!OpenServiceW` at `0x180008e7d`
- `ADVAPI32!OpenServiceW` at `0x180008e7d`
- `ADVAPI32!OpenSCManagerW` at `0x180008e36`
- `ADVAPI32!OpenSCManagerW` at `0x180008e36`

## string_xrefs

- `0x180008e1d`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall NfsNpIsClientRunning(_DWORD *a1)
{
  int v2; // ebx
  signed int v4; // ebx
  SC_HANDLE v5; // rsi
  signed int LastError; // eax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  signed int v9; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF
  char v11[24]; // [rsp+40h] [rbp-48h] BYREF

  strcpy(v11, "NfsNpIsClientRunning");
  v2 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)pGlobalNPCB + 112));
  if ( !dword_1800190D0 && GetTickCount64() - qword_1800196E0 <= 0xEA60 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v11);
    v2 = 1;
    *a1 = dword_1800196D8;
  }
  dword_1800190D0 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)pGlobalNPCB + 112));
  if ( v2 )
    return 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v11);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v5 = OpenSCManagerW(0, L"ServicesActive", 0x20000u);
  if ( v5 )
    goto LABEL_16;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_16:
    v7 = OpenServiceW(v5, L"NfsClnt", 4u);
    if ( v7 )
      goto LABEL_31;
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_31:
      if ( QueryServiceStatus(v7, &ServiceStatus) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)pGlobalNPCB + 112));
        dword_1800196D8 = ServiceStatus.dwCurrentState == 4;
        *a1 = dword_1800196D8;
        qword_1800196E0 = GetTickCount64();
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)pGlobalNPCB + 112));
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
      }
      if ( v7 )
        CloseServiceHandle(v7);
    }
    if ( v5 )
      CloseServiceHandle(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008d00  push    rbx
0x180008d02  push    rsi
0x180008d03  push    rdi
0x180008d04  push    r14
0x180008d06  sub     rsp, 68h
0x180008d0a  mov     rax, cs:__security_cookie
0x180008d11  xor     rax, rsp
0x180008d14  mov     [rsp+88h+var_30], rax
0x180008d19  movups  xmm0, xmmword ptr cs:aNfsnpisclientr; "NfsNpIsClientRunning"
0x180008d20  mov     r14, rcx
0x180008d23  mov     rcx, cs:pGlobalNPCB
0x180008d2a  movsd   xmm1, qword ptr cs:aNfsnpisclientr+0Dh; "Running"
0x180008d32  add     rcx, 70h ; 'p'; lpCriticalSection
0x180008d36  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x180008d3b  xor     ebx, ebx
0x180008d3d  xorps   xmm0, xmm0
0x180008d40  movsd   qword ptr [rsp+88h+var_48+0Dh], xmm1
0x180008d46  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x180008d4b  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008d50  call    cs:__imp_EnterCriticalSection
0x180008d57  nop     dword ptr [rax+rax+00h]
0x180008d5c  cmp     cs:dword_1800190D0, ebx
0x180008d62  lea     rdi, WPP_GLOBAL_Control
0x180008d69  jnz     short loc_180008DC0
0x180008d6b  call    cs:__imp_GetTickCount64
0x180008d72  nop     dword ptr [rax+rax+00h]
0x180008d77  sub     rax, cs:qword_1800196E0
0x180008d7e  cmp     rax, 0EA60h
0x180008d84  ja      short loc_180008DC0
0x180008d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d8d  cmp     rcx, rdi
0x180008d90  jz      short loc_180008DB2
0x180008d92  test    byte ptr [rcx+1Ch], 8
0x180008d96  jz      short loc_180008DB2
0x180008d98  mov     rcx, [rcx+10h]
0x180008d9c  lea     r9, [rsp+88h+var_48]
0x180008da1  mov     edx, 0FCh
0x180008da6  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008dad  call    WPP_SF_s
0x180008db2  mov     eax, cs:dword_1800196D8
0x180008db8  mov     ebx, 1
0x180008dbd  mov     [r14], eax
0x180008dc0  mov     rcx, cs:pGlobalNPCB
0x180008dc7  add     rcx, 70h ; 'p'; lpCriticalSection
0x180008dcb  mov     cs:dword_1800190D0, 0
0x180008dd5  call    cs:__imp_LeaveCriticalSection
0x180008ddc  nop     dword ptr [rax+rax+00h]
0x180008de1  test    ebx, ebx
0x180008de3  jz      short loc_180008DEC
0x180008de5  xor     eax, eax
0x180008de7  jmp     loc_180008F67
0x180008dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180008df3  xor     ebx, ebx
0x180008df5  cmp     rcx, rdi
0x180008df8  jz      short loc_180008E1A
0x180008dfa  test    byte ptr [rcx+1Ch], 8
0x180008dfe  jz      short loc_180008E1A
0x180008e00  mov     rcx, [rcx+10h]
0x180008e04  lea     r9, [rsp+88h+var_48]
0x180008e09  mov     edx, 0FDh
0x180008e0e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008e15  call    WPP_SF_s
0x180008e1a  xorps   xmm0, xmm0
0x180008e1d  lea     rdx, DatabaseName; "ServicesActive"
0x180008e24  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x180008e29  mov     r8d, 20000h; dwDesiredAccess
0x180008e2f  xor     ecx, ecx; lpMachineName
0x180008e31  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008e36  call    cs:__imp_OpenSCManagerW
0x180008e3d  nop     dword ptr [rax+rax+00h]
0x180008e42  mov     rsi, rax
0x180008e45  test    rax, rax
0x180008e48  jnz     short loc_180008E6D
0x180008e4a  call    cs:__imp_GetLastError
0x180008e51  nop     dword ptr [rax+rax+00h]
0x180008e56  mov     ebx, eax
0x180008e58  test    eax, eax
0x180008e5a  jle     short loc_180008E65
0x180008e5c  movzx   ebx, ax
0x180008e5f  or      ebx, 80070000h
0x180008e65  test    ebx, ebx
0x180008e67  js      loc_180008F65
0x180008e6d  mov     r8d, 4; dwDesiredAccess
0x180008e73  lea     rdx, ServiceName; "NfsClnt"
0x180008e7a  mov     rcx, rsi; hSCManager
0x180008e7d  call    cs:__imp_OpenServiceW
0x180008e84  nop     dword ptr [rax+rax+00h]
0x180008e89  mov     rdi, rax
0x180008e8c  test    rax, rax
0x180008e8f  jnz     short loc_180008EB4
0x180008e91  call    cs:__imp_GetLastError
0x180008e98  nop     dword ptr [rax+rax+00h]
0x180008e9d  mov     ebx, eax
0x180008e9f  test    eax, eax
0x180008ea1  jle     short loc_180008EAC
0x180008ea3  movzx   ebx, ax
0x180008ea6  or      ebx, 80070000h
0x180008eac  test    ebx, ebx
0x180008eae  js      loc_180008F51
0x180008eb4  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180008eb9  mov     rcx, rdi; hService
0x180008ebc  call    cs:__imp_QueryServiceStatus
0x180008ec3  nop     dword ptr [rax+rax+00h]
0x180008ec8  test    eax, eax
0x180008eca  jnz     short loc_180008EE9
0x180008ecc  call    cs:__imp_GetLastError
0x180008ed3  nop     dword ptr [rax+rax+00h]
0x180008ed8  mov     ebx, eax
0x180008eda  test    eax, eax
0x180008edc  jle     short loc_180008F3D
0x180008ede  movzx   ebx, ax
0x180008ee1  or      ebx, 80070000h
0x180008ee7  jmp     short loc_180008F3D
0x180008ee9  mov     rcx, cs:pGlobalNPCB
0x180008ef0  add     rcx, 70h ; 'p'; lpCriticalSection
0x180008ef4  call    cs:__imp_EnterCriticalSection
0x180008efb  nop     dword ptr [rax+rax+00h]
0x180008f00  xor     eax, eax
0x180008f02  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x180008f07  setz    al
0x180008f0a  mov     cs:dword_1800196D8, eax
0x180008f10  mov     [r14], eax
0x180008f13  call    cs:__imp_GetTickCount64
0x180008f1a  nop     dword ptr [rax+rax+00h]
0x180008f1f  mov     rcx, cs:pGlobalNPCB
0x180008f26  add     rcx, 70h ; 'p'; lpCriticalSection
0x180008f2a  mov     cs:qword_1800196E0, rax
0x180008f31  call    cs:__imp_LeaveCriticalSection
0x180008f38  nop     dword ptr [rax+rax+00h]
0x180008f3d  test    rdi, rdi
0x180008f40  jz      short loc_180008F51
0x180008f42  mov     rcx, rdi; hSCObject
0x180008f45  call    cs:__imp_CloseServiceHandle
0x180008f4c  nop     dword ptr [rax+rax+00h]
0x180008f51  test    rsi, rsi
0x180008f54  jz      short loc_180008F65
0x180008f56  mov     rcx, rsi; hSCObject
0x180008f59  call    cs:__imp_CloseServiceHandle
0x180008f60  nop     dword ptr [rax+rax+00h]
0x180008f65  mov     eax, ebx
0x180008f67  mov     rcx, [rsp+88h+var_30]
0x180008f6c  xor     rcx, rsp; StackCookie
0x180008f6f  call    __security_check_cookie
0x180008f74  add     rsp, 68h
0x180008f78  pop     r14
0x180008f7a  pop     rdi
0x180008f7b  pop     rsi
0x180008f7c  pop     rbx
0x180008f7d  retn
```
