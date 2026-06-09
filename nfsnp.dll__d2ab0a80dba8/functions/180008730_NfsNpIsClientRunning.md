# NfsNpIsClientRunning

- ea: `0x180008730`
- end: `0x180008956`
- name: `NfsNpIsClientRunning`
- size: `550`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004720`
- `0x180005850`
- `0x180005d70`
- `0x180006410`
- `0x1800066c0`
- `0x180007330`
- `0x180007bc0`
- `0x180007fd0`

## callees

- `0x180008730`
- `0x180008d20`
- `0x180011ba0`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180008795`
- `KERNEL32!GetTickCount64` at `0x180008903`
- `KERNEL32!GetTickCount64` at `0x180008795`
- `KERNEL32!GetTickCount64` at `0x180008903`
- `KERNEL32!LeaveCriticalSection` at `0x1800087f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000891b`
- `KERNEL32!LeaveCriticalSection` at `0x1800087f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000891b`
- `KERNEL32!EnterCriticalSection` at `0x180008780`
- `KERNEL32!EnterCriticalSection` at `0x1800088ea`
- `KERNEL32!EnterCriticalSection` at `0x180008780`
- `KERNEL32!EnterCriticalSection` at `0x1800088ea`
- `KERNEL32!GetLastError` at `0x180008862`
- `KERNEL32!GetLastError` at `0x18000889d`
- `KERNEL32!GetLastError` at `0x1800088c8`
- `KERNEL32!GetLastError` at `0x180008862`
- `KERNEL32!GetLastError` at `0x18000889d`
- `KERNEL32!GetLastError` at `0x1800088c8`
- `ADVAPI32!QueryServiceStatus` at `0x1800088be`
- `ADVAPI32!QueryServiceStatus` at `0x1800088be`
- `ADVAPI32!CloseServiceHandle` at `0x180008929`
- `ADVAPI32!CloseServiceHandle` at `0x180008937`
- `ADVAPI32!CloseServiceHandle` at `0x180008929`
- `ADVAPI32!CloseServiceHandle` at `0x180008937`
- `ADVAPI32!OpenServiceW` at `0x18000888f`
- `ADVAPI32!OpenServiceW` at `0x18000888f`
- `ADVAPI32!OpenSCManagerW` at `0x180008854`
- `ADVAPI32!OpenSCManagerW` at `0x180008854`

## string_xrefs

- `0x18000883b`: `ServicesActive`

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
  if ( !dword_1800180D0 && GetTickCount64() - qword_1800186E0 <= 0xEA60 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v11);
    v2 = 1;
    *a1 = dword_1800186D8;
  }
  dword_1800180D0 = 0;
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
        dword_1800186D8 = ServiceStatus.dwCurrentState == 4;
        *a1 = dword_1800186D8;
        qword_1800186E0 = GetTickCount64();
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
0x180008730  push    rbx
0x180008732  push    rsi
0x180008733  push    rdi
0x180008734  push    r14
0x180008736  sub     rsp, 68h
0x18000873a  mov     rax, cs:__security_cookie
0x180008741  xor     rax, rsp
0x180008744  mov     [rsp+88h+var_30], rax
0x180008749  movups  xmm0, xmmword ptr cs:aNfsnpisclientr; "NfsNpIsClientRunning"
0x180008750  mov     r14, rcx
0x180008753  mov     rcx, cs:pGlobalNPCB
0x18000875a  movsd   xmm1, qword ptr cs:aNfsnpisclientr+0Dh; "Running"
0x180008762  add     rcx, 70h ; 'p'; lpCriticalSection
0x180008766  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x18000876b  xor     ebx, ebx
0x18000876d  xorps   xmm0, xmm0
0x180008770  movsd   qword ptr [rsp+88h+var_48+0Dh], xmm1
0x180008776  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18000877b  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008780  call    cs:__imp_EnterCriticalSection
0x180008786  cmp     cs:dword_1800180D0, ebx
0x18000878c  lea     rdi, WPP_GLOBAL_Control
0x180008793  jnz     short loc_1800087E4
0x180008795  call    cs:__imp_GetTickCount64
0x18000879b  sub     rax, cs:qword_1800186E0
0x1800087a2  cmp     rax, 0EA60h
0x1800087a8  ja      short loc_1800087E4
0x1800087aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087b1  cmp     rcx, rdi
0x1800087b4  jz      short loc_1800087D6
0x1800087b6  test    byte ptr [rcx+1Ch], 8
0x1800087ba  jz      short loc_1800087D6
0x1800087bc  mov     rcx, [rcx+10h]
0x1800087c0  lea     r9, [rsp+88h+var_48]
0x1800087c5  mov     edx, 0FCh
0x1800087ca  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800087d1  call    WPP_SF_s
0x1800087d6  mov     eax, cs:dword_1800186D8
0x1800087dc  mov     ebx, 1
0x1800087e1  mov     [r14], eax
0x1800087e4  mov     rcx, cs:pGlobalNPCB
0x1800087eb  add     rcx, 70h ; 'p'; lpCriticalSection
0x1800087ef  mov     cs:dword_1800180D0, 0
0x1800087f9  call    cs:__imp_LeaveCriticalSection
0x1800087ff  test    ebx, ebx
0x180008801  jz      short loc_18000880A
0x180008803  xor     eax, eax
0x180008805  jmp     loc_18000893F
0x18000880a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008811  xor     ebx, ebx
0x180008813  cmp     rcx, rdi
0x180008816  jz      short loc_180008838
0x180008818  test    byte ptr [rcx+1Ch], 8
0x18000881c  jz      short loc_180008838
0x18000881e  mov     rcx, [rcx+10h]
0x180008822  lea     r9, [rsp+88h+var_48]
0x180008827  mov     edx, 0FDh
0x18000882c  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008833  call    WPP_SF_s
0x180008838  xorps   xmm0, xmm0
0x18000883b  lea     rdx, DatabaseName; "ServicesActive"
0x180008842  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x180008847  mov     r8d, 20000h; dwDesiredAccess
0x18000884d  xor     ecx, ecx; lpMachineName
0x18000884f  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008854  call    cs:__imp_OpenSCManagerW
0x18000885a  mov     rsi, rax
0x18000885d  test    rax, rax
0x180008860  jnz     short loc_18000887F
0x180008862  call    cs:__imp_GetLastError
0x180008868  mov     ebx, eax
0x18000886a  test    eax, eax
0x18000886c  jle     short loc_180008877
0x18000886e  movzx   ebx, ax
0x180008871  or      ebx, 80070000h
0x180008877  test    ebx, ebx
0x180008879  js      loc_18000893D
0x18000887f  mov     r8d, 4; dwDesiredAccess
0x180008885  lea     rdx, ServiceName; "NfsClnt"
0x18000888c  mov     rcx, rsi; hSCManager
0x18000888f  call    cs:__imp_OpenServiceW
0x180008895  mov     rdi, rax
0x180008898  test    rax, rax
0x18000889b  jnz     short loc_1800088B6
0x18000889d  call    cs:__imp_GetLastError
0x1800088a3  mov     ebx, eax
0x1800088a5  test    eax, eax
0x1800088a7  jle     short loc_1800088B2
0x1800088a9  movzx   ebx, ax
0x1800088ac  or      ebx, 80070000h
0x1800088b2  test    ebx, ebx
0x1800088b4  js      short loc_18000892F
0x1800088b6  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800088bb  mov     rcx, rdi; hService
0x1800088be  call    cs:__imp_QueryServiceStatus
0x1800088c4  test    eax, eax
0x1800088c6  jnz     short loc_1800088DF
0x1800088c8  call    cs:__imp_GetLastError
0x1800088ce  mov     ebx, eax
0x1800088d0  test    eax, eax
0x1800088d2  jle     short loc_180008921
0x1800088d4  movzx   ebx, ax
0x1800088d7  or      ebx, 80070000h
0x1800088dd  jmp     short loc_180008921
0x1800088df  mov     rcx, cs:pGlobalNPCB
0x1800088e6  add     rcx, 70h ; 'p'; lpCriticalSection
0x1800088ea  call    cs:__imp_EnterCriticalSection
0x1800088f0  xor     eax, eax
0x1800088f2  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x1800088f7  setz    al
0x1800088fa  mov     cs:dword_1800186D8, eax
0x180008900  mov     [r14], eax
0x180008903  call    cs:__imp_GetTickCount64
0x180008909  mov     rcx, cs:pGlobalNPCB
0x180008910  add     rcx, 70h ; 'p'; lpCriticalSection
0x180008914  mov     cs:qword_1800186E0, rax
0x18000891b  call    cs:__imp_LeaveCriticalSection
0x180008921  test    rdi, rdi
0x180008924  jz      short loc_18000892F
0x180008926  mov     rcx, rdi; hSCObject
0x180008929  call    cs:__imp_CloseServiceHandle
0x18000892f  test    rsi, rsi
0x180008932  jz      short loc_18000893D
0x180008934  mov     rcx, rsi; hSCObject
0x180008937  call    cs:__imp_CloseServiceHandle
0x18000893d  mov     eax, ebx
0x18000893f  mov     rcx, [rsp+88h+var_30]
0x180008944  xor     rcx, rsp; StackCookie
0x180008947  call    __security_check_cookie
0x18000894c  add     rsp, 68h
0x180008950  pop     r14
0x180008952  pop     rdi
0x180008953  pop     rsi
0x180008954  pop     rbx
0x180008955  retn
```
