# StopService(ushort const *,ulong)

- ea: `0x1800420ac`
- end: `0x1800422b7`
- name: `?StopService@@YAJPEBGK@Z`
- size: `523`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800411c0`
- `0x180041610`
- `0x1800420ac`

## callees

- `0x1800420ac`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042150`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004213d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004222b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004224b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004225e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004227e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004213d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004222b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004224b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004225e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004227e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004220a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004220a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800420dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800420dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042215`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004221e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042243`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042276`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042215`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004221e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042243`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042276`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800420f9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800420f9`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004212f`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x180042180`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004212f`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x180042180`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800421f4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800421f4`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800421d6`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800421d6`

## pseudocode

```c
__int64 __fastcall StopService(const unsigned __int16 *a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  struct _ENUM_SERVICE_STATUSW *v6; // rax
  DWORD i; // ebx
  unsigned int v8; // ebx
  unsigned int j; // esi
  signed int LastError; // eax
  signed int v12; // eax
  signed int v13; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-48h] BYREF

  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, a1, 0x2Cu);
    v5 = v4;
    if ( v4 )
    {
      if ( !EnumDependentServicesW(v4, 1u, 0, 0, &dependentSize, &entries) && GetLastError() == 234 )
      {
        v6 = (struct _ENUM_SERVICE_STATUSW *)CWin32DefaultArena::WbemMemAlloc(dependentSize);
        dependent = v6;
        if ( !v6 )
        {
          CloseServiceHandle(v5);
          CloseServiceHandle(v3);
          return 2147749894LL;
        }
        if ( EnumDependentServicesW(v5, 1u, v6, dependentSize, &dependentSize, &entries) )
        {
          for ( i = 0; i < entries; ++i )
            StopService(dependent[i].lpServiceName, 0x3Cu);
        }
      }
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(v5, 1u, &ServiceStatus) )
      {
        v8 = -2147217303;
        for ( j = 0; j < 0x3C; ++j )
        {
          if ( !QueryServiceStatus(v5, &ServiceStatus) )
          {
            LastError = GetLastError();
            v8 = LastError;
            goto LABEL_17;
          }
          if ( ServiceStatus.dwCurrentState == 1 )
            goto LABEL_21;
          Sleep(0x3E8u);
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError == 1062 )
        {
LABEL_21:
          v8 = 0;
        }
        else
        {
LABEL_17:
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      CloseServiceHandle(v5);
    }
    else
    {
      v12 = GetLastError();
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      return (unsigned __int16)v13 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x1800420ac  mov     [rsp+arg_8], rbx
0x1800420b1  mov     [rsp+arg_10], rbp
0x1800420b6  push    rsi
0x1800420b7  push    rdi
0x1800420b8  push    r14
0x1800420ba  sub     rsp, 60h
0x1800420be  mov     rax, cs:__security_cookie
0x1800420c5  xor     rax, rsp
0x1800420c8  mov     [rsp+78h+var_28], rax
0x1800420cd  mov     rbx, rcx
0x1800420d0  mov     r14d, 1
0x1800420d6  mov     r8d, r14d; dwDesiredAccess
0x1800420d9  xor     edx, edx; lpDatabaseName
0x1800420db  xor     ecx, ecx; lpMachineName
0x1800420dd  call    cs:__imp_OpenSCManagerW
0x1800420e3  mov     rbp, rax
0x1800420e6  test    rax, rax
0x1800420e9  jz      loc_18004227E
0x1800420ef  lea     r8d, [r14+2Bh]; dwDesiredAccess
0x1800420f3  mov     rdx, rbx; lpServiceName
0x1800420f6  mov     rcx, rax; hSCManager
0x1800420f9  call    cs:__imp_OpenServiceW
0x1800420ff  mov     rdi, rax
0x180042102  test    rax, rax
0x180042105  jz      loc_18004225E
0x18004210b  lea     rbx, ?entries@@3KA; ulong entries
0x180042112  xor     r9d, r9d; cbBufSize
0x180042115  lea     rsi, ?dependentSize@@3KA; ulong dependentSize
0x18004211c  mov     [rsp+78h+lpServicesReturned], rbx; lpServicesReturned
0x180042121  xor     r8d, r8d; lpServices
0x180042124  mov     [rsp+78h+pcbBytesNeeded], rsi; pcbBytesNeeded
0x180042129  mov     edx, r14d; dwServiceState
0x18004212c  mov     rcx, rax; hService
0x18004212f  call    cs:__imp_EnumDependentServicesW
0x180042135  test    eax, eax
0x180042137  jnz     loc_1800421BE
0x18004213d  call    cs:__imp_GetLastError
0x180042143  cmp     eax, 0EAh
0x180042148  jnz     short loc_1800421BE
0x18004214a  mov     ecx, cs:?dependentSize@@3KA; ulong dependentSize
0x180042150  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180042156  mov     cs:?dependent@@3PEAU_ENUM_SERVICE_STATUSW@@EA, rax; _ENUM_SERVICE_STATUSW * dependent
0x18004215d  mov     rcx, rdi; hSCObject
0x180042160  test    rax, rax
0x180042163  jz      loc_180042215
0x180042169  mov     r9d, cs:?dependentSize@@3KA; cbBufSize
0x180042170  mov     r8, rax; lpServices
0x180042173  mov     [rsp+78h+lpServicesReturned], rbx; lpServicesReturned
0x180042178  mov     edx, r14d; dwServiceState
0x18004217b  mov     [rsp+78h+pcbBytesNeeded], rsi; pcbBytesNeeded
0x180042180  call    cs:__imp_EnumDependentServicesW
0x180042186  test    eax, eax
0x180042188  jz      short loc_1800421BE
0x18004218a  xor     ebx, ebx
0x18004218c  cmp     cs:?entries@@3KA, ebx; ulong entries
0x180042192  jbe     short loc_1800421BE
0x180042194  mov     rcx, cs:?dependent@@3PEAU_ENUM_SERVICE_STATUSW@@EA; _ENUM_SERVICE_STATUSW * dependent
0x18004219b  mov     edx, 3Ch ; '<'; unsigned int
0x1800421a0  movsxd  rax, ebx
0x1800421a3  lea     r8, [rax+rax*2]
0x1800421a7  add     r8, r8
0x1800421aa  mov     rcx, [rcx+r8*8]; unsigned __int16 *
0x1800421ae  call    ?StopService@@YAJPEBGK@Z; StopService(ushort const *,ulong)
0x1800421b3  add     ebx, r14d
0x1800421b6  cmp     ebx, cs:?entries@@3KA; ulong entries
0x1800421bc  jb      short loc_180042194
0x1800421be  xorps   xmm0, xmm0
0x1800421c1  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800421c6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800421cb  mov     edx, r14d; dwControl
0x1800421ce  mov     rcx, rdi; hService
0x1800421d1  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800421d6  call    cs:__imp_ControlService
0x1800421dc  test    eax, eax
0x1800421de  jz      short loc_18004224B
0x1800421e0  mov     ebx, 80041069h
0x1800421e5  xor     esi, esi
0x1800421e7  cmp     esi, 3Ch ; '<'
0x1800421ea  jnb     short loc_180042240
0x1800421ec  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800421f1  mov     rcx, rdi; hService
0x1800421f4  call    cs:__imp_QueryServiceStatus
0x1800421fa  test    eax, eax
0x1800421fc  jz      short loc_18004222B
0x1800421fe  cmp     [rsp+78h+ServiceStatus.dwCurrentState], r14d
0x180042203  jz      short loc_18004225A
0x180042205  mov     ecx, 3E8h; dwMilliseconds
0x18004220a  call    cs:__imp_Sleep
0x180042210  add     esi, r14d
0x180042213  jmp     short loc_1800421E7
0x180042215  call    cs:__imp_CloseServiceHandle
0x18004221b  mov     rcx, rbp; hSCObject
0x18004221e  call    cs:__imp_CloseServiceHandle
0x180042224  mov     eax, 80041006h
0x180042229  jmp     short loc_180042295
0x18004222b  call    cs:__imp_GetLastError
0x180042231  mov     ebx, eax
0x180042233  test    eax, eax
0x180042235  jle     short loc_180042240
0x180042237  movzx   ebx, ax
0x18004223a  or      ebx, 80070000h
0x180042240  mov     rcx, rdi; hSCObject
0x180042243  call    cs:__imp_CloseServiceHandle
0x180042249  jmp     short loc_180042273
0x18004224b  call    cs:__imp_GetLastError
0x180042251  mov     ebx, eax
0x180042253  cmp     eax, 426h
0x180042258  jnz     short loc_180042233
0x18004225a  xor     ebx, ebx
0x18004225c  jmp     short loc_180042240
0x18004225e  call    cs:__imp_GetLastError
0x180042264  mov     ebx, eax
0x180042266  test    eax, eax
0x180042268  jle     short loc_180042273
0x18004226a  movzx   ebx, ax
0x18004226d  or      ebx, 80070000h
0x180042273  mov     rcx, rbp; hSCObject
0x180042276  call    cs:__imp_CloseServiceHandle
0x18004227c  jmp     short loc_180042293
0x18004227e  call    cs:__imp_GetLastError
0x180042284  mov     ebx, eax
0x180042286  test    eax, eax
0x180042288  jle     short loc_180042293
0x18004228a  movzx   ebx, ax
0x18004228d  or      ebx, 80070000h
0x180042293  mov     eax, ebx
0x180042295  mov     rcx, [rsp+78h+var_28]
0x18004229a  xor     rcx, rsp; StackCookie
0x18004229d  call    __security_check_cookie
0x1800422a2  lea     r11, [rsp+78h+var_18]
0x1800422a7  mov     rbx, [r11+28h]
0x1800422ab  mov     rbp, [r11+30h]
0x1800422af  mov     rsp, r11
0x1800422b2  pop     r14
0x1800422b4  pop     rdi
0x1800422b5  pop     rsi
0x1800422b6  retn
```
