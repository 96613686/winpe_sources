# WaitForServiceToStart(ushort const *,ulong)

- ea: `0x1800526e0`
- end: `0x180052881`
- name: `?WaitForServiceToStart@@YAHPEBGK@Z`
- size: `417`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800b49e0`
- `0x1800b4cc8`

## callees

- `0x1800526e0`
- `0x18007d320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052830`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005284e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005284e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005278c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052842`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005278c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052842`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800527cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800527d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800527cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800527d6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005280b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005280b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052775`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005286e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052775`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005286e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052741`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052741`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180052729`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180052729`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052795`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005279e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052795`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005279e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800527eb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800527eb`

## pseudocode

```c
__int64 __fastcall WaitForServiceToStart(LPCWSTR lpServiceName, DWORD a2)
{
  unsigned int v4; // edi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r14
  SC_HANDLE v7; // rsi
  struct _QUERY_SERVICE_CONFIGW *v8; // rax
  struct _QUERY_SERVICE_CONFIGW *v9; // rbx
  DWORD TickCount; // r15d
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  SIZE_T uBytes; // [rsp+20h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-28h] BYREF

  LODWORD(uBytes) = 512;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v7 = OpenServiceW(v5, lpServiceName, 5u);
    if ( !v7 )
    {
LABEL_8:
      CloseServiceHandle(v6);
      return v4;
    }
    v8 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, (unsigned int)uBytes);
    v9 = v8;
    if ( v8 )
    {
      if ( QueryServiceConfigW(v7, v8, uBytes, (LPDWORD)&uBytes) )
        goto LABEL_26;
      if ( GetLastError() == 122 )
      {
        LocalFree(v9);
        v12 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v9 = v12;
        if ( !v12 )
          goto LABEL_7;
        if ( QueryServiceConfigW(v7, v12, uBytes, (LPDWORD)&uBytes) )
        {
LABEL_26:
          if ( v9->dwStartType == 2 )
          {
            TickCount = GetTickCount();
            while ( 1 )
            {
              v4 = 0;
              if ( GetTickCount() - TickCount > a2 || !QueryServiceStatus(v7, &ServiceStatus) )
                break;
              if ( ServiceStatus.dwCurrentState == 1 )
              {
                if ( ServiceStatus.dwWin32ExitCode != 1077 )
                  break;
              }
              else if ( ServiceStatus.dwCurrentState - 4 <= 3 )
              {
                v4 = 1;
                break;
              }
              Sleep(0x32u);
            }
            if ( !v9 )
              goto LABEL_7;
          }
        }
      }
      LocalFree(v9);
    }
LABEL_7:
    CloseServiceHandle(v7);
    goto LABEL_8;
  }
  return v4;
}

```

## disassembly

```asm
0x1800526e0  mov     [rsp-28h+arg_8], rbx
0x1800526e5  mov     [rsp-28h+arg_10], rsi
0x1800526ea  push    rbp
0x1800526eb  push    rdi
0x1800526ec  push    r12
0x1800526ee  push    r14
0x1800526f0  push    r15
0x1800526f2  mov     rbp, rsp
0x1800526f5  sub     rsp, 50h
0x1800526f9  mov     rax, cs:__security_cookie
0x180052700  xor     rax, rsp
0x180052703  mov     [rbp+var_8], rax
0x180052707  xorps   xmm0, xmm0
0x18005270a  mov     dword ptr [rbp+uBytes], 200h
0x180052711  mov     r12d, edx
0x180052714  mov     rbx, rcx
0x180052717  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18005271b  xor     edi, edi
0x18005271d  xor     edx, edx; lpDatabaseName
0x18005271f  xor     ecx, ecx; lpMachineName
0x180052721  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180052725  lea     r8d, [rdi+1]; dwDesiredAccess
0x180052729  call    cs:__imp_OpenSCManagerW
0x18005272f  mov     r14, rax
0x180052732  test    rax, rax
0x180052735  jz      short loc_1800527A4
0x180052737  lea     r8d, [rdi+5]; dwDesiredAccess
0x18005273b  mov     rdx, rbx; lpServiceName
0x18005273e  mov     rcx, rax; hSCManager
0x180052741  call    cs:__imp_OpenServiceW
0x180052747  mov     rsi, rax
0x18005274a  test    rax, rax
0x18005274d  jz      short loc_18005279B
0x18005274f  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180052752  lea     r15d, [rdi+40h]
0x180052756  mov     ecx, r15d; uFlags
0x180052759  call    cs:__imp_LocalAlloc
0x18005275f  mov     rbx, rax
0x180052762  test    rax, rax
0x180052765  jz      short loc_180052792
0x180052767  mov     r8d, dword ptr [rbp+uBytes]; cbBufSize
0x18005276b  lea     r9, [rbp+uBytes]; pcbBytesNeeded
0x18005276f  mov     rdx, rax; lpServiceConfig
0x180052772  mov     rcx, rsi; hService
0x180052775  call    cs:__imp_QueryServiceConfigW
0x18005277b  test    eax, eax
0x18005277d  jz      loc_180052830
0x180052783  cmp     dword ptr [rbx+4], 2
0x180052787  jz      short loc_1800527CB
0x180052789  mov     rcx, rbx; hMem
0x18005278c  call    cs:__imp_LocalFree
0x180052792  mov     rcx, rsi; hSCObject
0x180052795  call    cs:__imp_CloseServiceHandle
0x18005279b  mov     rcx, r14; hSCObject
0x18005279e  call    cs:__imp_CloseServiceHandle
0x1800527a4  mov     eax, edi
0x1800527a6  mov     rcx, [rbp+var_8]
0x1800527aa  xor     rcx, rsp; StackCookie
0x1800527ad  call    __security_check_cookie
0x1800527b2  lea     r11, [rsp+50h+var_s0]
0x1800527b7  mov     rbx, [r11+38h]
0x1800527bb  mov     rsi, [r11+40h]
0x1800527bf  mov     rsp, r11
0x1800527c2  pop     r15
0x1800527c4  pop     r14
0x1800527c6  pop     r12
0x1800527c8  pop     rdi
0x1800527c9  pop     rbp
0x1800527ca  retn
0x1800527cb  call    cs:__imp_GetTickCount
0x1800527d1  mov     r15d, eax
0x1800527d4  xor     edi, edi
0x1800527d6  call    cs:__imp_GetTickCount
0x1800527dc  sub     eax, r15d
0x1800527df  cmp     eax, r12d
0x1800527e2  ja      short loc_180052813
0x1800527e4  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800527e8  mov     rcx, rsi; hService
0x1800527eb  call    cs:__imp_QueryServiceStatus
0x1800527f1  test    eax, eax
0x1800527f3  jz      short loc_180052813
0x1800527f5  mov     ecx, [rbp+ServiceStatus.dwCurrentState]
0x1800527f8  cmp     ecx, 1
0x1800527fb  jnz     short loc_180052821
0x1800527fd  cmp     [rbp+ServiceStatus.dwWin32ExitCode], 435h
0x180052804  jnz     short loc_180052813
0x180052806  mov     ecx, 32h ; '2'; dwMilliseconds
0x18005280b  call    cs:__imp_Sleep
0x180052811  jmp     short loc_1800527D4
0x180052813  test    rbx, rbx
0x180052816  jz      loc_180052792
0x18005281c  jmp     loc_180052789
0x180052821  lea     eax, [rcx-4]
0x180052824  cmp     eax, 3
0x180052827  ja      short loc_180052806
0x180052829  mov     edi, 1
0x18005282e  jmp     short loc_180052813
0x180052830  call    cs:__imp_GetLastError
0x180052836  cmp     eax, 7Ah ; 'z'
0x180052839  jnz     loc_180052789
0x18005283f  mov     rcx, rbx; hMem
0x180052842  call    cs:__imp_LocalFree
0x180052848  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18005284b  mov     ecx, r15d; uFlags
0x18005284e  call    cs:__imp_LocalAlloc
0x180052854  mov     rbx, rax
0x180052857  test    rax, rax
0x18005285a  jz      loc_180052792
0x180052860  mov     r8d, dword ptr [rbp+uBytes]; cbBufSize
0x180052864  lea     r9, [rbp+uBytes]; pcbBytesNeeded
0x180052868  mov     rdx, rax; lpServiceConfig
0x18005286b  mov     rcx, rsi; hService
0x18005286e  call    cs:__imp_QueryServiceConfigW
0x180052874  test    eax, eax
0x180052876  jz      loc_180052789
0x18005287c  jmp     loc_180052783
```
