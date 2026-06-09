# StartFhService(void)

- ea: `0x180002680`
- end: `0x180002907`
- name: `?StartFhService@@YAJXZ`
- size: `647`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180003230`

## callees

- `0x180002538`
- `0x180002680`
- `0x180002910`
- `0x180002964`
- `0x180004f20`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1800028a1`
- `ADVAPI32!CloseServiceHandle` at `0x1800028aa`
- `ADVAPI32!CloseServiceHandle` at `0x1800028a1`
- `ADVAPI32!CloseServiceHandle` at `0x1800028aa`
- `ADVAPI32!StartServiceW` at `0x1800027f7`
- `ADVAPI32!StartServiceW` at `0x1800027f7`
- `ADVAPI32!QueryServiceStatus` at `0x180002789`
- `ADVAPI32!QueryServiceStatus` at `0x180002852`
- `ADVAPI32!QueryServiceStatus` at `0x180002789`
- `ADVAPI32!QueryServiceStatus` at `0x180002852`
- `ADVAPI32!OpenServiceW` at `0x18000272b`
- `ADVAPI32!OpenServiceW` at `0x18000272b`
- `ADVAPI32!OpenSCManagerW` at `0x1800026ba`
- `ADVAPI32!OpenSCManagerW` at `0x1800026ba`
- `KERNEL32!GetLastError` at `0x1800026c8`
- `KERNEL32!GetLastError` at `0x180002739`
- `KERNEL32!GetLastError` at `0x180002793`
- `KERNEL32!GetLastError` at `0x180002801`
- `KERNEL32!GetLastError` at `0x1800028cf`
- `KERNEL32!GetLastError` at `0x1800026c8`
- `KERNEL32!GetLastError` at `0x180002739`
- `KERNEL32!GetLastError` at `0x180002793`
- `KERNEL32!GetLastError` at `0x180002801`
- `KERNEL32!GetLastError` at `0x1800028cf`
- `KERNEL32!Sleep` at `0x180002844`
- `KERNEL32!Sleep` at `0x180002844`

## string_xrefs

- `0x1800026a1`: `ServicesActive`

## pseudocode

```c
__int64 StartFhService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  signed int v2; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD dwCurrentState; // eax
  signed int v11; // eax
  int v12; // ebx
  signed int v14; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"fhsvc", 0x14u);
    v5 = v4;
    if ( !v4 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2));
      goto LABEL_37;
    }
    if ( QueryServiceStatus(v4, &ServiceStatus) )
    {
      dwCurrentState = ServiceStatus.dwCurrentState;
      if ( ServiceStatus.dwCurrentState == 4 )
      {
LABEL_32:
        v3 = 0;
        if ( dwCurrentState != 4 )
        {
          v3 = -2147023843;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        goto LABEL_36;
      }
      if ( StartServiceW(v5, 0, 0) || (v11 = GetLastError(), v3 = v11, v11 == 1056) )
      {
        v12 = 0;
        while ( 1 )
        {
          Sleep(0xC8u);
          if ( !QueryServiceStatus(v5, &ServiceStatus) )
            break;
          dwCurrentState = ServiceStatus.dwCurrentState;
          if ( ServiceStatus.dwCurrentState == 2 && ++v12 < 25 )
            continue;
          goto LABEL_32;
        }
        v14 = GetLastError();
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v9 = 14;
      }
      else
      {
        if ( v11 > 0 )
          v3 = (unsigned __int16)v11 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v9 = 13;
      }
    }
    else
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v9 = 12;
    }
    WPP_SF_d(v8[2], v9, &WPP_3aa27aedce4a398f677a57a0155b8d9f_Traceguids, v3);
LABEL_36:
    CloseServiceHandle(v5);
LABEL_37:
    CloseServiceHandle(v1);
    return v3;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_3aa27aedce4a398f677a57a0155b8d9f_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180002680  mov     [rsp+arg_0], rbx
0x180002685  mov     [rsp+arg_8], rsi
0x18000268a  push    rdi
0x18000268b  sub     rsp, 60h
0x18000268f  mov     rax, cs:__security_cookie
0x180002696  xor     rax, rsp
0x180002699  mov     [rsp+68h+var_18], rax
0x18000269e  xorps   xmm0, xmm0
0x1800026a1  lea     rdx, DatabaseName; "ServicesActive"
0x1800026a8  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1800026ad  mov     r8d, 1; dwDesiredAccess
0x1800026b3  xor     ecx, ecx; lpMachineName
0x1800026b5  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800026ba  call    cs:__imp_OpenSCManagerW
0x1800026c0  mov     rsi, rax
0x1800026c3  test    rax, rax
0x1800026c6  jnz     short loc_18000271B
0x1800026c8  call    cs:__imp_GetLastError
0x1800026ce  mov     ebx, eax
0x1800026d0  test    eax, eax
0x1800026d2  jle     short loc_1800026DD
0x1800026d4  movzx   ebx, ax
0x1800026d7  or      ebx, 80070000h
0x1800026dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026e4  lea     rax, WPP_GLOBAL_Control
0x1800026eb  cmp     rcx, rax
0x1800026ee  jz      loc_1800028B0
0x1800026f4  test    byte ptr [rcx+1Ch], 1
0x1800026f8  jz      loc_1800028B0
0x1800026fe  mov     rcx, [rcx+10h]
0x180002702  lea     r8, WPP_3aa27aedce4a398f677a57a0155b8d9f_Traceguids
0x180002709  mov     edx, 0Ah
0x18000270e  mov     r9d, ebx
0x180002711  call    WPP_SF_d
0x180002716  jmp     loc_1800028B0
0x18000271b  mov     r8d, 14h; dwDesiredAccess
0x180002721  lea     rdx, ServiceName; "fhsvc"
0x180002728  mov     rcx, rsi; hSCManager
0x18000272b  call    cs:__imp_OpenServiceW
0x180002731  mov     rdi, rax
0x180002734  test    rax, rax
0x180002737  jnz     short loc_180002781
0x180002739  call    cs:__imp_GetLastError
0x18000273f  mov     ebx, eax
0x180002741  test    eax, eax
0x180002743  jle     short loc_18000274E
0x180002745  movzx   ebx, ax
0x180002748  or      ebx, 80070000h
0x18000274e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002755  lea     rax, WPP_GLOBAL_Control
0x18000275c  cmp     rcx, rax
0x18000275f  jz      loc_1800028A7
0x180002765  test    byte ptr [rcx+1Ch], 1
0x180002769  jz      loc_1800028A7
0x18000276f  mov     rcx, [rcx+10h]
0x180002773  mov     [rsp+68h+var_48], ebx
0x180002777  call    WPP_SF_Sd
0x18000277c  jmp     loc_1800028A7
0x180002781  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180002786  mov     rcx, rdi; hService
0x180002789  call    cs:__imp_QueryServiceStatus
0x18000278f  test    eax, eax
0x180002791  jnz     short loc_1800027E6
0x180002793  call    cs:__imp_GetLastError
0x180002799  mov     ebx, eax
0x18000279b  test    eax, eax
0x18000279d  jle     short loc_1800027A8
0x18000279f  movzx   ebx, ax
0x1800027a2  or      ebx, 80070000h
0x1800027a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027af  lea     rax, WPP_GLOBAL_Control
0x1800027b6  cmp     rcx, rax
0x1800027b9  jz      loc_18000289E
0x1800027bf  test    byte ptr [rcx+1Ch], 1
0x1800027c3  jz      loc_18000289E
0x1800027c9  mov     edx, 0Ch
0x1800027ce  mov     rcx, [rcx+10h]
0x1800027d2  lea     r8, WPP_3aa27aedce4a398f677a57a0155b8d9f_Traceguids
0x1800027d9  mov     r9d, ebx
0x1800027dc  call    WPP_SF_d
0x1800027e1  jmp     loc_18000289E
0x1800027e6  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x1800027ea  cmp     eax, 4
0x1800027ed  jz      short loc_18000286C
0x1800027ef  xor     r8d, r8d; lpServiceArgVectors
0x1800027f2  xor     edx, edx; dwNumServiceArgs
0x1800027f4  mov     rcx, rdi; hService
0x1800027f7  call    cs:__imp_StartServiceW
0x1800027fd  test    eax, eax
0x1800027ff  jnz     short loc_18000283D
0x180002801  call    cs:__imp_GetLastError
0x180002807  mov     ebx, eax
0x180002809  cmp     eax, 420h
0x18000280e  jz      short loc_18000283D
0x180002810  test    eax, eax
0x180002812  jle     short loc_18000281D
0x180002814  movzx   ebx, ax
0x180002817  or      ebx, 80070000h
0x18000281d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002824  lea     rax, WPP_GLOBAL_Control
0x18000282b  cmp     rcx, rax
0x18000282e  jz      short loc_18000289E
0x180002830  test    byte ptr [rcx+1Ch], 1
0x180002834  jz      short loc_18000289E
0x180002836  mov     edx, 0Dh
0x18000283b  jmp     short loc_1800027CE
0x18000283d  xor     ebx, ebx
0x18000283f  mov     ecx, 0C8h; dwMilliseconds
0x180002844  call    cs:__imp_Sleep
0x18000284a  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18000284f  mov     rcx, rdi; hService
0x180002852  call    cs:__imp_QueryServiceStatus
0x180002858  test    eax, eax
0x18000285a  jz      short loc_1800028CF
0x18000285c  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x180002860  cmp     eax, 2
0x180002863  jnz     short loc_18000286C
0x180002865  inc     ebx
0x180002867  cmp     ebx, 19h
0x18000286a  jl      short loc_18000283F
0x18000286c  xor     ebx, ebx
0x18000286e  cmp     eax, 4
0x180002871  jz      short loc_18000289E
0x180002873  mov     ebx, 8007041Dh
0x180002878  mov     rcx, cs:WPP_GLOBAL_Control
0x18000287f  lea     rax, WPP_GLOBAL_Control
0x180002886  cmp     rcx, rax
0x180002889  jz      short loc_18000289E
0x18000288b  test    byte ptr [rcx+1Ch], 1
0x18000288f  jz      short loc_18000289E
0x180002891  mov     rcx, [rcx+10h]
0x180002895  mov     [rsp+68h+var_40], ebx
0x180002899  call    WPP_SF_Sdd
0x18000289e  mov     rcx, rdi; hSCObject
0x1800028a1  call    cs:__imp_CloseServiceHandle
0x1800028a7  mov     rcx, rsi; hSCObject
0x1800028aa  call    cs:__imp_CloseServiceHandle
0x1800028b0  mov     eax, ebx
0x1800028b2  mov     rcx, [rsp+68h+var_18]
0x1800028b7  xor     rcx, rsp; StackCookie
0x1800028ba  call    __security_check_cookie
0x1800028bf  mov     rbx, [rsp+68h+arg_0]
0x1800028c4  mov     rsi, [rsp+68h+arg_8]
0x1800028c9  add     rsp, 60h
0x1800028cd  pop     rdi
0x1800028ce  retn
0x1800028cf  call    cs:__imp_GetLastError
0x1800028d5  mov     ebx, eax
0x1800028d7  test    eax, eax
0x1800028d9  jle     short loc_1800028E4
0x1800028db  movzx   ebx, ax
0x1800028de  or      ebx, 80070000h
0x1800028e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028eb  lea     rax, WPP_GLOBAL_Control
0x1800028f2  cmp     rcx, rax
0x1800028f5  jz      short loc_18000289E
0x1800028f7  test    byte ptr [rcx+1Ch], 1
0x1800028fb  jz      short loc_18000289E
0x1800028fd  mov     edx, 0Eh
0x180002902  jmp     loc_1800027CE
```
