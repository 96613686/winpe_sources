# SERVICES_MANAGER::ResolveDependenciesRecursive(SC_HANDLE__ *,ushort *,int)

- ea: `0x140003dc4`
- end: `0x140003fe5`
- name: `?ResolveDependenciesRecursive@SERVICES_MANAGER@@AEAAJPEAUSC_HANDLE__@@PEAGH@Z`
- size: `545`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, struct SC_HANDLE__ *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140003d1c`
- `0x140003dc4`

## callees

- `0x1400035a8`
- `0x140003dc4`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003eb7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003fb5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003fb5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003e37`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003e37`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x140003fbf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x140003fbf`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140003e8a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140003f47`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140003e8a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140003f47`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140003e6f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140003ead`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140003e6f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140003ead`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140003f36`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140003f77`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140003f36`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140003f77`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140003ee0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140003ee0`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::ResolveDependenciesRecursive(
        SERVICES_MANAGER *this,
        SC_HANDLE a2,
        unsigned __int16 *a3,
        int a4)
{
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  signed int v10; // eax
  signed int inserted; // ebx
  signed int LastError; // eax
  LPQUERY_SERVICE_CONFIGW v13; // rbx
  DWORD v14; // edi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-39h] BYREF
  DWORD ServicesReturned; // [rsp+34h] [rbp-35h] BYREF
  _QWORD v18[4]; // [rsp+38h] [rbp-31h] BYREF
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+58h] [rbp-11h]
  DWORD cbBufSize; // [rsp+60h] [rbp-9h]
  __int16 v21; // [rsp+64h] [rbp-5h]
  _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-1h] BYREF

  v18[0] = 0;
  cbBufSize = 32;
  v21 = 256;
  pcbBytesNeeded = 0;
  ServicesReturned = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  lpServiceConfig = (LPQUERY_SERVICE_CONFIGW)v18;
  v8 = OpenServiceW(a2, a3, 0xF01FFu);
  v9 = v8;
  if ( v8 )
  {
    if ( QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) )
    {
      inserted = -2147418113;
LABEL_23:
      CloseServiceHandle(v9);
      goto LABEL_24;
    }
    if ( !BUFFER::Resize((BUFFER *)v18, pcbBytesNeeded) )
    {
LABEL_7:
      inserted = -2147024888;
      goto LABEL_23;
    }
    if ( QueryServiceConfigW(v9, lpServiceConfig, cbBufSize, &pcbBytesNeeded) )
    {
      v13 = lpServiceConfig;
      if ( QueryServiceStatus(v9, &ServiceStatus) )
      {
        if ( a4 && v13->dwStartType == 3 || v13->dwStartType < 3 || (inserted = 0, ServiceStatus.dwCurrentState != 1) )
        {
          inserted = SERVICES_MANAGER::InsertServiceName(this, a3);
          if ( inserted < 0 )
            goto LABEL_23;
        }
        if ( EnumDependentServicesW(v9, 3u, 0, 0, &pcbBytesNeeded, &ServicesReturned) )
          goto LABEL_23;
        if ( !BUFFER::Resize((BUFFER *)v18, pcbBytesNeeded) )
          goto LABEL_7;
        if ( EnumDependentServicesW(
               v9,
               3u,
               (LPENUM_SERVICE_STATUSW)lpServiceConfig,
               cbBufSize,
               &pcbBytesNeeded,
               &ServicesReturned) )
        {
          v14 = ServicesReturned;
          do
          {
            if ( (--v14 & 0x80000000) != 0 )
              break;
            inserted = SERVICES_MANAGER::ResolveDependenciesRecursive(
                         this,
                         a2,
                         *((unsigned __int16 **)&lpServiceConfig->dwServiceType + 6 * v14),
                         0);
          }
          while ( inserted >= 0 );
          goto LABEL_23;
        }
      }
    }
    LastError = GetLastError();
    inserted = LastError;
    if ( LastError > 0 )
      inserted = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_23;
  }
  v10 = GetLastError();
  inserted = v10;
  if ( v10 > 0 )
    inserted = (unsigned __int16)v10 | 0x80070000;
LABEL_24:
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140003dc4  push    rbp
0x140003dc6  push    rbx
0x140003dc7  push    rsi
0x140003dc8  push    rdi
0x140003dc9  push    r12
0x140003dcb  push    r14
0x140003dcd  push    r15
0x140003dcf  lea     rbp, [rsp-27h]
0x140003dd4  sub     rsp, 90h
0x140003ddb  mov     rax, cs:__security_cookie
0x140003de2  xor     rax, rsp
0x140003de5  mov     [rbp+57h+var_38], rax
0x140003de9  mov     r14, r8
0x140003dec  mov     [rbp+57h+var_88], 0
0x140003df4  mov     r12, rdx
0x140003df7  mov     [rbp+57h+cbBufSize], 20h ; ' '
0x140003dfe  xorps   xmm0, xmm0
0x140003e01  mov     [rbp+57h+var_5C], 100h
0x140003e07  mov     r15, rcx
0x140003e0a  mov     [rbp+57h+pcbBytesNeeded], 0
0x140003e11  lea     rax, [rbp+57h+var_88]
0x140003e15  mov     [rbp+57h+ServicesReturned], 0
0x140003e1c  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x140003e20  mov     rdx, r14; lpServiceName
0x140003e23  mov     [rbp+57h+lpServiceConfig], rax
0x140003e27  mov     rcx, r12; hSCManager
0x140003e2a  mov     r8d, 0F01FFh; dwDesiredAccess
0x140003e30  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x140003e34  mov     edi, r9d
0x140003e37  call    cs:__imp_OpenServiceW
0x140003e3d  mov     rsi, rax
0x140003e40  test    rax, rax
0x140003e43  jnz     short loc_140003E63
0x140003e45  call    cs:__imp_GetLastError
0x140003e4b  mov     ebx, eax
0x140003e4d  test    eax, eax
0x140003e4f  jle     loc_140003FBB
0x140003e55  movzx   ebx, ax
0x140003e58  or      ebx, 80070000h
0x140003e5e  jmp     loc_140003FBB
0x140003e63  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x140003e67  xor     r8d, r8d; cbBufSize
0x140003e6a  xor     edx, edx; lpServiceConfig
0x140003e6c  mov     rcx, rsi; hService
0x140003e6f  call    cs:__imp_QueryServiceConfigW
0x140003e75  test    eax, eax
0x140003e77  jz      short loc_140003E83
0x140003e79  mov     ebx, 8000FFFFh
0x140003e7e  jmp     loc_140003FB2
0x140003e83  mov     edx, [rbp+57h+pcbBytesNeeded]
0x140003e86  lea     rcx, [rbp+57h+var_88]
0x140003e8a  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x140003e90  test    al, al
0x140003e92  jnz     short loc_140003E9E
0x140003e94  mov     ebx, 80070008h
0x140003e99  jmp     loc_140003FB2
0x140003e9e  mov     r8d, [rbp+57h+cbBufSize]; cbBufSize
0x140003ea2  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x140003ea6  mov     rdx, [rbp+57h+lpServiceConfig]; lpServiceConfig
0x140003eaa  mov     rcx, rsi; hService
0x140003ead  call    cs:__imp_QueryServiceConfigW
0x140003eb3  test    eax, eax
0x140003eb5  jnz     short loc_140003ED5
0x140003eb7  call    cs:__imp_GetLastError
0x140003ebd  mov     ebx, eax
0x140003ebf  test    eax, eax
0x140003ec1  jle     loc_140003FB2
0x140003ec7  movzx   ebx, ax
0x140003eca  or      ebx, 80070000h
0x140003ed0  jmp     loc_140003FB2
0x140003ed5  mov     rbx, [rbp+57h+lpServiceConfig]
0x140003ed9  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x140003edd  mov     rcx, rsi; hService
0x140003ee0  call    cs:__imp_QueryServiceStatus
0x140003ee6  test    eax, eax
0x140003ee8  jz      short loc_140003EB7
0x140003eea  test    edi, edi
0x140003eec  jz      short loc_140003EF4
0x140003eee  cmp     dword ptr [rbx+4], 3
0x140003ef2  jz      short loc_140003F02
0x140003ef4  cmp     dword ptr [rbx+4], 3
0x140003ef8  jb      short loc_140003F02
0x140003efa  xor     ebx, ebx
0x140003efc  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x140003f00  jz      short loc_140003F17
0x140003f02  mov     rdx, r14; unsigned __int16 *
0x140003f05  mov     rcx, r15; this
0x140003f08  call    ?InsertServiceName@SERVICES_MANAGER@@AEAAJPEAG@Z; SERVICES_MANAGER::InsertServiceName(ushort *)
0x140003f0d  mov     ebx, eax
0x140003f0f  test    eax, eax
0x140003f11  js      loc_140003FB2
0x140003f17  xor     r9d, r9d; cbBufSize
0x140003f1a  lea     rax, [rbp+57h+ServicesReturned]
0x140003f1e  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x140003f23  xor     r8d, r8d; lpServices
0x140003f26  lea     rax, [rbp+57h+pcbBytesNeeded]
0x140003f2a  mov     rcx, rsi; hService
0x140003f2d  mov     [rsp+0C0h+var_A0], rax; pcbBytesNeeded
0x140003f32  lea     edx, [r9+3]; dwServiceState
0x140003f36  call    cs:__imp_EnumDependentServicesW
0x140003f3c  test    eax, eax
0x140003f3e  jnz     short loc_140003FB2
0x140003f40  mov     edx, [rbp+57h+pcbBytesNeeded]
0x140003f43  lea     rcx, [rbp+57h+var_88]
0x140003f47  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x140003f4d  test    al, al
0x140003f4f  jz      loc_140003E94
0x140003f55  mov     r9d, [rbp+57h+cbBufSize]; cbBufSize
0x140003f59  lea     rax, [rbp+57h+ServicesReturned]
0x140003f5d  mov     r8, [rbp+57h+lpServiceConfig]; lpServices
0x140003f61  mov     edx, 3; dwServiceState
0x140003f66  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x140003f6b  mov     rcx, rsi; hService
0x140003f6e  lea     rax, [rbp+57h+pcbBytesNeeded]
0x140003f72  mov     [rsp+0C0h+var_A0], rax; pcbBytesNeeded
0x140003f77  call    cs:__imp_EnumDependentServicesW
0x140003f7d  test    eax, eax
0x140003f7f  jz      loc_140003EB7
0x140003f85  mov     edi, [rbp+57h+ServicesReturned]
0x140003f88  jmp     short loc_140003FAD
0x140003f8a  mov     r8, [rbp+57h+lpServiceConfig]
0x140003f8e  lea     rcx, [rdi+rdi*2]
0x140003f92  add     rcx, rcx
0x140003f95  xor     r9d, r9d; int
0x140003f98  mov     rdx, r12; struct SC_HANDLE__ *
0x140003f9b  mov     r8, [r8+rcx*8]; unsigned __int16 *
0x140003f9f  mov     rcx, r15; this
0x140003fa2  call    ?ResolveDependenciesRecursive@SERVICES_MANAGER@@AEAAJPEAUSC_HANDLE__@@PEAGH@Z; SERVICES_MANAGER::ResolveDependenciesRecursive(SC_HANDLE__ *,ushort *,int)
0x140003fa7  mov     ebx, eax
0x140003fa9  test    eax, eax
0x140003fab  js      short loc_140003FB2
0x140003fad  sub     edi, 1
0x140003fb0  jns     short loc_140003F8A
0x140003fb2  mov     rcx, rsi; hSCObject
0x140003fb5  call    cs:__imp_CloseServiceHandle
0x140003fbb  lea     rcx, [rbp+57h+var_88]
0x140003fbf  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x140003fc5  mov     eax, ebx
0x140003fc7  mov     rcx, [rbp+57h+var_38]
0x140003fcb  xor     rcx, rsp; StackCookie
0x140003fce  call    __security_check_cookie
0x140003fd3  add     rsp, 90h
0x140003fda  pop     r15
0x140003fdc  pop     r14
0x140003fde  pop     r12
0x140003fe0  pop     rdi
0x140003fe1  pop     rsi
0x140003fe2  pop     rbx
0x140003fe3  pop     rbp
0x140003fe4  retn
```
