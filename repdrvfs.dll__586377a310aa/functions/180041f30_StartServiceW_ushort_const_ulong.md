# StartServiceW(ushort const *,ulong)

- ea: `0x180041f30`
- end: `0x1800420a3`
- name: `?StartServiceW@@YAJPEBGK@Z`
- size: `371`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800411c0`
- `0x180041610`
- `0x180041f30`

## callees

- `0x180041f30`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180042065`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180042065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042016`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041fc8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041fc8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041f53`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041f53`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041fee`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004200e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041fee`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004200e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041f71`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041f71`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180041f87`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180041f87`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180041fb2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180041fb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartServiceW(const unsigned __int16 *a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  unsigned int v6; // ebx
  unsigned int i; // edi
  signed int LastError; // eax
  signed int v9; // eax
  signed int v10; // eax
  DWORD j; // edi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, a1, 0x14u);
    v5 = v4;
    if ( v4 )
    {
      if ( StartServiceW(v4, 0, 0) )
      {
        v6 = -2147217303;
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        for ( i = 0; i < 0x3C; ++i )
        {
          if ( !QueryServiceStatus(v5, &ServiceStatus) )
            goto LABEL_10;
          if ( ServiceStatus.dwCurrentState == 4 )
          {
            v6 = 0;
            break;
          }
          Sleep(0x3E8u);
        }
      }
      else
      {
LABEL_10:
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v5);
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v10 = GetLastError();
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
  }
  for ( j = 0; j < entries; ++j )
    StartServiceW(dependent[j].lpServiceName, 0x3Cu);
  CWin32DefaultArena::WbemMemFree(dependent);
  entries = 0;
  dependent = 0;
  dependentSize = 0;
  return v6;
}

```

## disassembly

```asm
0x180041f30  push    rbx
0x180041f32  push    rbp
0x180041f33  push    rsi
0x180041f34  push    rdi
0x180041f35  sub     rsp, 58h
0x180041f39  mov     rax, cs:__security_cookie
0x180041f40  xor     rax, rsp
0x180041f43  mov     [rsp+78h+var_38], rax
0x180041f48  mov     rbx, rcx
0x180041f4b  xor     edx, edx; lpDatabaseName
0x180041f4d  xor     ecx, ecx; lpMachineName
0x180041f4f  lea     r8d, [rdx+1]; dwDesiredAccess
0x180041f53  call    cs:__imp_OpenSCManagerW
0x180041f59  mov     rbp, rax
0x180041f5c  test    rax, rax
0x180041f5f  jz      loc_180042016
0x180041f65  mov     r8d, 14h; dwDesiredAccess
0x180041f6b  mov     rdx, rbx; lpServiceName
0x180041f6e  mov     rcx, rax; hSCManager
0x180041f71  call    cs:__imp_OpenServiceW
0x180041f77  mov     rsi, rax
0x180041f7a  test    rax, rax
0x180041f7d  jz      short loc_180041FF6
0x180041f7f  xor     r8d, r8d; lpServiceArgVectors
0x180041f82  xor     edx, edx; dwNumServiceArgs
0x180041f84  mov     rcx, rax; hService
0x180041f87  call    cs:__imp_StartServiceW
0x180041f8d  test    eax, eax
0x180041f8f  jz      short loc_180041FD6
0x180041f91  mov     ebx, 80041069h
0x180041f96  xorps   xmm0, xmm0
0x180041f99  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180041f9e  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180041fa3  xor     edi, edi
0x180041fa5  cmp     edi, 3Ch ; '<'
0x180041fa8  jnb     short loc_180041FEB
0x180041faa  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180041faf  mov     rcx, rsi; hService
0x180041fb2  call    cs:__imp_QueryServiceStatus
0x180041fb8  test    eax, eax
0x180041fba  jz      short loc_180041FD6
0x180041fbc  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180041fc1  jz      short loc_180041FD2
0x180041fc3  mov     ecx, 3E8h; dwMilliseconds
0x180041fc8  call    cs:__imp_Sleep
0x180041fce  inc     edi
0x180041fd0  jmp     short loc_180041FA5
0x180041fd2  xor     ebx, ebx
0x180041fd4  jmp     short loc_180041FEB
0x180041fd6  call    cs:__imp_GetLastError
0x180041fdc  test    eax, eax
0x180041fde  mov     ebx, eax
0x180041fe0  jle     short loc_180041FEB
0x180041fe2  movzx   ebx, ax
0x180041fe5  or      ebx, 80070000h
0x180041feb  mov     rcx, rsi; hSCObject
0x180041fee  call    cs:__imp_CloseServiceHandle
0x180041ff4  jmp     short loc_18004200B
0x180041ff6  call    cs:__imp_GetLastError
0x180041ffc  mov     ebx, eax
0x180041ffe  test    eax, eax
0x180042000  jle     short loc_18004200B
0x180042002  movzx   ebx, ax
0x180042005  or      ebx, 80070000h
0x18004200b  mov     rcx, rbp; hSCObject
0x18004200e  call    cs:__imp_CloseServiceHandle
0x180042014  jmp     short loc_18004202B
0x180042016  call    cs:__imp_GetLastError
0x18004201c  mov     ebx, eax
0x18004201e  test    eax, eax
0x180042020  jle     short loc_18004202B
0x180042022  movzx   ebx, ax
0x180042025  or      ebx, 80070000h
0x18004202b  xor     edi, edi
0x18004202d  cmp     cs:?entries@@3KA, edi; ulong entries
0x180042033  jbe     short loc_18004205E
0x180042035  movsxd  rax, edi
0x180042038  lea     r8, [rax+rax*2]
0x18004203c  add     r8, r8
0x18004203f  mov     edx, 3Ch ; '<'; unsigned int
0x180042044  mov     rcx, cs:?dependent@@3PEAU_ENUM_SERVICE_STATUSW@@EA; _ENUM_SERVICE_STATUSW * dependent
0x18004204b  mov     rcx, [rcx+r8*8]; unsigned __int16 *
0x18004204f  call    ?StartServiceW@@YAJPEBGK@Z; StartServiceW(ushort const *,ulong)
0x180042054  inc     edi
0x180042056  cmp     edi, cs:?entries@@3KA; ulong entries
0x18004205c  jb      short loc_180042035
0x18004205e  mov     rcx, cs:?dependent@@3PEAU_ENUM_SERVICE_STATUSW@@EA; _ENUM_SERVICE_STATUSW * dependent
0x180042065  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18004206b  nop
0x18004206c  mov     cs:?entries@@3KA, 0; ulong entries
0x180042076  mov     cs:?dependent@@3PEAU_ENUM_SERVICE_STATUSW@@EA, 0; _ENUM_SERVICE_STATUSW * dependent
0x180042081  mov     cs:?dependentSize@@3KA, 0; ulong dependentSize
0x18004208b  mov     eax, ebx
0x18004208d  mov     rcx, [rsp+78h+var_38]
0x180042092  xor     rcx, rsp; StackCookie
0x180042095  call    __security_check_cookie
0x18004209a  add     rsp, 58h
0x18004209e  pop     rdi
0x18004209f  pop     rsi
0x1800420a0  pop     rbp
0x1800420a1  pop     rbx
0x1800420a2  retn
```
