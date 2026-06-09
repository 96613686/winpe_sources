# StopService(CSafeServiceHandle &,bool)

- ea: `0x1800bf084`
- end: `0x1800bf245`
- name: `?StopService@@YAJAEAVCSafeServiceHandle@@_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(struct CSafeServiceHandle *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180142970`

## callees

- `0x18000ee60`
- `0x1800bf084`
- `0x18010ff58`
- `0x1801244c0`
- `0x1801249ec`
- `0x18014094c`
- `0x180149c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf0ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf0ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bf1b8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bf1b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800bf197`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800bf1aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800bf197`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800bf1aa`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800bf18d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800bf20d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800bf18d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800bf20d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800bf1c6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800bf1c6`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800bf0dc`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800bf13b`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800bf0dc`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800bf13b`

## pseudocode

```c
__int64 __fastcall StopService(SC_HANDLE *a1)
{
  struct _ENUM_SERVICE_STATUSW *v2; // rax
  struct _ENUM_SERVICE_STATUSW *v3; // rsi
  const wchar_t *v4; // r9
  __int64 i; // rdi
  ULONGLONG v6; // r14
  SC_HANDLE v7; // rcx
  DWORD cbBufSize; // [rsp+38h] [rbp-19h] BYREF
  DWORD ServicesReturned; // [rsp+3Ch] [rbp-15h] BYREF
  SC_HANDLE hService; // [rsp+40h] [rbp-11h] BYREF
  struct _ENUM_SERVICE_STATUSW *v12; // [rsp+48h] [rbp-9h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+50h] [rbp-1h] BYREF
  struct _SERVICE_STATUS v14; // [rsp+70h] [rbp+1Fh] BYREF

  cbBufSize = 0;
  ServicesReturned = 0;
  if ( !EnumDependentServicesW(*a1, 1u, 0, 0, &cbBufSize, &ServicesReturned) && GetLastError() == 234 )
  {
    v2 = (struct _ENUM_SERVICE_STATUSW *)operator new[](cbBufSize, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v2;
    v3 = v2;
    if ( v2 )
    {
      if ( EnumDependentServicesW(*a1, 1u, v2, cbBufSize, &cbBufSize, &ServicesReturned) )
      {
        for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
        {
          CSafeServiceHandle::CSafeServiceHandle((CSafeServiceHandle *)&hService, v3[i].lpServiceName, 0x24u, v4);
          if ( hService )
          {
            memset(&ServiceStatus, 0, sizeof(ServiceStatus));
            if ( ControlService(hService, 1u, &ServiceStatus) )
            {
              v6 = GetTickCount64() + 30000;
              while ( ServiceStatus.dwCurrentState != 1 )
              {
                if ( GetTickCount64() >= v6 )
                  break;
                Sleep(ServiceStatus.dwWaitHint);
                if ( !QueryServiceStatus(hService, &ServiceStatus) && (int)ResultFromKnownLastError() < 0 )
                  break;
              }
            }
          }
          CSafeServiceHandle::~CSafeServiceHandle((CSafeServiceHandle *)&hService);
        }
      }
    }
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v12);
  }
  v7 = *a1;
  memset(&v14, 0, sizeof(v14));
  if ( ControlService(v7, 1u, &v14) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1800bf084  mov     r11, rsp
0x1800bf087  mov     [r11+10h], rsi
0x1800bf08b  mov     [r11+18h], rdi
0x1800bf08f  push    rbp
0x1800bf090  push    r14
0x1800bf092  push    r15
0x1800bf094  lea     rbp, [r11-5Fh]
0x1800bf098  sub     rsp, 90h
0x1800bf09f  mov     rax, cs:__security_cookie
0x1800bf0a6  xor     rax, rsp
0x1800bf0a9  mov     [rbp+57h+var_18], rax
0x1800bf0ad  xor     r9d, r9d; cbBufSize
0x1800bf0b0  mov     [rbp+57h+cbBufSize], 0
0x1800bf0b7  lea     rax, [rbp+57h+ServicesReturned]
0x1800bf0bb  mov     [rbp+57h+ServicesReturned], 0
0x1800bf0c2  mov     [r11-80h], rax
0x1800bf0c6  mov     r15, rcx
0x1800bf0c9  mov     rcx, [rcx]; hService
0x1800bf0cc  lea     rax, [rbp+57h+cbBufSize]
0x1800bf0d0  lea     edx, [r9+1]; dwServiceState
0x1800bf0d4  mov     [rsp+0A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800bf0d9  xor     r8d, r8d; lpServices
0x1800bf0dc  call    cs:__imp_EnumDependentServicesW
0x1800bf0e2  test    eax, eax
0x1800bf0e4  jnz     loc_1800BF1F6
0x1800bf0ea  call    cs:__imp_GetLastError
0x1800bf0f0  cmp     eax, 0EAh
0x1800bf0f5  jnz     loc_1800BF1F6
0x1800bf0fb  mov     ecx, [rbp+57h+cbBufSize]; unsigned __int64
0x1800bf0fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bf105  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bf10a  mov     [rbp+57h+var_60], rax
0x1800bf10e  mov     rsi, rax
0x1800bf111  test    rax, rax
0x1800bf114  jz      loc_1800BF1ED
0x1800bf11a  mov     r9d, [rbp+57h+cbBufSize]; cbBufSize
0x1800bf11e  lea     rax, [rbp+57h+ServicesReturned]
0x1800bf122  mov     rcx, [r15]; hService
0x1800bf125  mov     r8, rsi; lpServices
0x1800bf128  mov     [rsp+0A0h+lpServicesReturned], rax; lpServicesReturned
0x1800bf12d  mov     edx, 1; dwServiceState
0x1800bf132  lea     rax, [rbp+57h+cbBufSize]
0x1800bf136  mov     [rsp+0A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800bf13b  call    cs:__imp_EnumDependentServicesW
0x1800bf141  test    eax, eax
0x1800bf143  jz      loc_1800BF1ED
0x1800bf149  xor     edi, edi
0x1800bf14b  cmp     [rbp+57h+ServicesReturned], edi
0x1800bf14e  jbe     loc_1800BF1ED
0x1800bf154  lea     rdx, [rdi+rdi*2]
0x1800bf158  mov     r8d, 24h ; '$'; unsigned int
0x1800bf15e  add     rdx, rdx
0x1800bf161  lea     rcx, [rbp+57h+hService]; this
0x1800bf165  mov     rdx, [rsi+rdx*8]; wchar_t *
0x1800bf169  call    ??0CSafeServiceHandle@@QEAA@PEB_WK0@Z; CSafeServiceHandle::CSafeServiceHandle(wchar_t const *,ulong,wchar_t const *)
0x1800bf16e  cmp     [rbp+57h+hService], 0
0x1800bf173  jz      short loc_1800BF1D9
0x1800bf175  mov     rcx, [rbp+57h+hService]; hService
0x1800bf179  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1800bf17d  xorps   xmm0, xmm0
0x1800bf180  mov     edx, 1; dwControl
0x1800bf185  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1800bf189  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800bf18d  call    cs:__imp_ControlService
0x1800bf193  test    eax, eax
0x1800bf195  jz      short loc_1800BF1D9
0x1800bf197  call    cs:__imp_GetTickCount64
0x1800bf19d  lea     r14, [rax+7530h]
0x1800bf1a4  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x1800bf1a8  jz      short loc_1800BF1D9
0x1800bf1aa  call    cs:__imp_GetTickCount64
0x1800bf1b0  cmp     rax, r14
0x1800bf1b3  jnb     short loc_1800BF1D9
0x1800bf1b5  mov     ecx, [rbp+57h+ServiceStatus.dwWaitHint]; dwMilliseconds
0x1800bf1b8  call    cs:__imp_Sleep
0x1800bf1be  mov     rcx, [rbp+57h+hService]; hService
0x1800bf1c2  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1800bf1c6  call    cs:__imp_QueryServiceStatus
0x1800bf1cc  test    eax, eax
0x1800bf1ce  jnz     short loc_1800BF1A4
0x1800bf1d0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bf1d5  test    eax, eax
0x1800bf1d7  jns     short loc_1800BF1A4
0x1800bf1d9  lea     rcx, [rbp+57h+hService]; this
0x1800bf1dd  call    ??1CSafeServiceHandle@@QEAA@XZ; CSafeServiceHandle::~CSafeServiceHandle(void)
0x1800bf1e2  inc     edi
0x1800bf1e4  cmp     edi, [rbp+57h+ServicesReturned]
0x1800bf1e7  jb      loc_1800BF154
0x1800bf1ed  lea     rcx, [rbp+57h+var_60]
0x1800bf1f1  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800bf1f6  mov     rcx, [r15]; hService
0x1800bf1f9  lea     r8, [rbp+57h+var_38]; lpServiceStatus
0x1800bf1fd  xorps   xmm0, xmm0
0x1800bf200  mov     edx, 1; dwControl
0x1800bf205  movups  xmmword ptr [rbp+57h+var_38.dwServiceType], xmm0
0x1800bf209  movups  xmmword ptr [rbp+57h+var_38.dwWin32ExitCode], xmm0
0x1800bf20d  call    cs:__imp_ControlService
0x1800bf213  test    eax, eax
0x1800bf215  jz      short loc_1800BF21B
0x1800bf217  xor     eax, eax
0x1800bf219  jmp     short loc_1800BF220
0x1800bf21b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bf220  mov     rcx, [rbp+57h+var_18]
0x1800bf224  xor     rcx, rsp; StackCookie
0x1800bf227  call    __security_check_cookie
0x1800bf22c  lea     r11, [rsp+0A0h+var_10]
0x1800bf234  mov     rsi, [r11+28h]
0x1800bf238  mov     rdi, [r11+30h]
0x1800bf23c  mov     rsp, r11
0x1800bf23f  pop     r15
0x1800bf241  pop     r14
0x1800bf243  pop     rbp
0x1800bf244  retn
```
