# SrvLoadSamss(ulong,ushort * *)

- ea: `0x1800b3d80`
- end: `0x1800b4209`
- name: `?SrvLoadSamss@@YAXKPEAPEAG@Z`
- size: `1161`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180011278`
- `0x1800284d4`
- `0x1800ada18`
- `0x1800b1f9c`
- `0x1800b3d80`
- `0x1800b86d0`
- `0x1800f308c`
- `0x1800f376c`
- `0x18012d280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b3ef2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b3ef2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b40cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b40cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b408b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b408b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b41d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b41d3`
- `ntdll!RtlGetNtProductType` at `0x1800b3e52`
- `ntdll!RtlGetNtProductType` at `0x1800b3e52`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800b3df7`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800b3df7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800b4052`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800b4160`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800b4052`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800b4160`

## string_xrefs

- `0x1800b3ee5`: `NtdsDelayedStartupCompletedEvent`

## pseudocode

```c
void __fastcall SrvLoadSamss(__int64 a1, unsigned __int16 **a2)
{
  SERVICE_STATUS_HANDLE v2; // rsi
  DWORD LastError; // eax
  HANDLE EventW; // rdi
  DWORD v5; // eax
  LsaHandleCache *v6; // rcx
  enum _NT_PRODUCT_TYPE v7; // eax
  DWORD v8; // eax
  __int64 v9; // rdx
  int v10; // ebx
  LsaHandleCache *v11; // rcx
  DWORD v12; // eax
  DWORD v13; // eax
  LsaHandleCache *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+30h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ProductType = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
  }
  v2 = RegisterServiceCtrlHandlerW(L"SAMSS", DummyControlHandler);
  if ( !v2 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
        LastError,
        LastError);
    }
    return;
  }
  EventW = 0;
  if ( RtlGetNtProductType(&ProductType) )
  {
    v7 = ProductType;
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    v5 = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, v5, v5);
      v6 = WPP_GLOBAL_Control;
    }
    v7 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( v7 != NtProductLanManNt )
  {
    if ( v6 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_DWORD *)v6 + 7) & 0x8000000) == 0 )
      goto LABEL_33;
    v9 = 35;
LABEL_32:
    WPP_SF_(*((_QWORD *)v6 + 2), v9, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
    goto LABEL_33;
  }
  if ( v6 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x8000000) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 31, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
  if ( !LsapSamExtDsIsRunning() )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
    {
      goto LABEL_33;
    }
    v9 = 34;
    goto LABEL_32;
  }
  EventW = CreateEventW(0, 1, 0, L"NtdsDelayedStartupCompletedEvent");
  if ( EventW )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
    {
      goto LABEL_33;
    }
    v9 = 33;
    goto LABEL_32;
  }
  v8 = GetLastError();
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, v8, v8);
  }
LABEL_33:
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwWaitHint = 30000;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwCheckPoint = 1;
  if ( LsapWaitForSamService(v2, &ServiceStatus) )
  {
    if ( EventW )
    {
      ServiceStatus.dwWaitHint = 35000;
      do
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
        }
        if ( SetServiceStatus(v2, &ServiceStatus) )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
              ServiceStatus.dwCheckPoint);
          }
        }
        else
        {
          v12 = GetLastError();
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
          {
            WPP_SF_Ddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              ServiceStatus.dwCheckPoint,
              v12,
              v12,
              ServiceStatus.dwCheckPoint);
          }
        }
        ++ServiceStatus.dwCheckPoint;
        v13 = WaitForSingleObject(EventW, 0x7530u);
      }
      while ( v13 == 258 );
      if ( v13 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
        {
          goto LABEL_63;
        }
        v15 = 41;
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
        {
          goto LABEL_63;
        }
        v15 = 40;
      }
      WPP_SF_(*((_QWORD *)v14 + 2), v15, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
    }
    v14 = WPP_GLOBAL_Control;
LABEL_63:
    v10 = 1;
    if ( v14 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x8000000) != 0 )
      WPP_SF_(*((_QWORD *)v14 + 2), 42, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
    ServiceStatus.dwCurrentState = 4;
    goto LABEL_67;
  }
  v10 = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x8000000) != 0 )
      WPP_SF_(*((_QWORD *)v11 + 2), 43, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
  }
  ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwWin32ExitCode = 31;
  ServiceStatus.dwServiceSpecificExitCode = 31;
LABEL_67:
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  if ( SetServiceStatus(v2, &ServiceStatus) )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
    }
  }
  else
  {
    v16 = GetLastError();
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, v16, v16);
    }
  }
  if ( EventW )
    CloseHandle(EventW);
  if ( v10 )
    LsaAutologgerEventCompleted(2u);
}

```

## disassembly

```asm
0x1800b3d80  push    rbp
0x1800b3d82  push    rbx
0x1800b3d83  push    rsi
0x1800b3d84  push    rdi
0x1800b3d85  push    r13
0x1800b3d87  push    r14
0x1800b3d89  push    r15
0x1800b3d8b  mov     rbp, rsp
0x1800b3d8e  sub     rsp, 60h
0x1800b3d92  mov     rax, cs:__security_cookie
0x1800b3d99  xor     rax, rsp
0x1800b3d9c  mov     [rbp+var_8], rax
0x1800b3da0  xorps   xmm0, xmm0
0x1800b3da3  mov     [rbp+ProductType], 0
0x1800b3daa  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1800b3dae  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1800b3db2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3db9  lea     r15, WPP_GLOBAL_Control
0x1800b3dc0  lea     r13, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x1800b3dc7  mov     r14d, 8000000h
0x1800b3dcd  cmp     rcx, r15
0x1800b3dd0  jz      short loc_1800B3DE9
0x1800b3dd2  test    [rcx+1Ch], r14d
0x1800b3dd6  jz      short loc_1800B3DE9
0x1800b3dd8  mov     rcx, [rcx+10h]
0x1800b3ddc  mov     edx, 1Ch
0x1800b3de1  mov     r8, r13
0x1800b3de4  call    WPP_SF_
0x1800b3de9  lea     rdx, ?DummyControlHandler@@YAXK@Z; lpHandlerProc
0x1800b3df0  lea     rcx, ServiceName; "SAMSS"
0x1800b3df7  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1800b3dfe  nop     dword ptr [rax+rax+00h]
0x1800b3e03  mov     rsi, rax
0x1800b3e06  test    rax, rax
0x1800b3e09  jnz     short loc_1800B3E4C
0x1800b3e0b  call    cs:__imp_GetLastError
0x1800b3e12  nop     dword ptr [rax+rax+00h]
0x1800b3e17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e1e  cmp     rcx, r15
0x1800b3e21  jz      loc_1800B41ED
0x1800b3e27  test    [rcx+1Ch], r14d
0x1800b3e2b  jz      loc_1800B41ED
0x1800b3e31  mov     rcx, [rcx+10h]
0x1800b3e35  lea     edx, [rsi+1Dh]
0x1800b3e38  mov     r9d, eax
0x1800b3e3b  mov     [rsp+60h+var_40], eax
0x1800b3e3f  mov     r8, r13
0x1800b3e42  call    WPP_SF_Dd
0x1800b3e47  jmp     loc_1800B41ED
0x1800b3e4c  lea     rcx, [rbp+ProductType]; ProductType
0x1800b3e50  xor     edi, edi
0x1800b3e52  call    cs:__imp_RtlGetNtProductType
0x1800b3e59  nop     dword ptr [rax+rax+00h]
0x1800b3e5e  test    al, al
0x1800b3e60  jnz     short loc_1800B3EA7
0x1800b3e62  call    cs:__imp_GetLastError
0x1800b3e69  nop     dword ptr [rax+rax+00h]
0x1800b3e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e75  cmp     rcx, r15
0x1800b3e78  jz      short loc_1800B3E9D
0x1800b3e7a  test    [rcx+1Ch], r14d
0x1800b3e7e  jz      short loc_1800B3E9D
0x1800b3e80  mov     rcx, [rcx+10h]
0x1800b3e84  lea     edx, [rdi+1Eh]
0x1800b3e87  mov     r9d, eax
0x1800b3e8a  mov     [rsp+60h+var_40], eax
0x1800b3e8e  mov     r8, r13
0x1800b3e91  call    WPP_SF_Dd
0x1800b3e96  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e9d  mov     eax, 1
0x1800b3ea2  mov     [rbp+ProductType], eax
0x1800b3ea5  jmp     short loc_1800B3EB1
0x1800b3ea7  mov     eax, [rbp+ProductType]
0x1800b3eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3eb1  mov     ebx, 20h ; ' '
0x1800b3eb6  cmp     eax, 2
0x1800b3eb9  jnz     loc_1800B3F6D
0x1800b3ebf  cmp     rcx, r15
0x1800b3ec2  jz      short loc_1800B3ED9
0x1800b3ec4  test    [rcx+1Ch], r14d
0x1800b3ec8  jz      short loc_1800B3ED9
0x1800b3eca  mov     rcx, [rcx+10h]
0x1800b3ece  lea     edx, [rbx-1]
0x1800b3ed1  mov     r8, r13
0x1800b3ed4  call    WPP_SF_
0x1800b3ed9  call    ?LsapSamExtDsIsRunning@@YAEXZ; LsapSamExtDsIsRunning(void)
0x1800b3ede  test    al, al
0x1800b3ee0  jz      short loc_1800B3F54
0x1800b3ee2  xor     r8d, r8d; bInitialState
0x1800b3ee5  lea     r9, aNtdsdelayedsta; "NtdsDelayedStartupCompletedEvent"
0x1800b3eec  xor     ecx, ecx; lpEventAttributes
0x1800b3eee  lea     edx, [r8+1]; bManualReset
0x1800b3ef2  call    cs:__imp_CreateEventW
0x1800b3ef9  nop     dword ptr [rax+rax+00h]
0x1800b3efe  mov     rdi, rax
0x1800b3f01  test    rax, rax
0x1800b3f04  jnz     short loc_1800B3F3B
0x1800b3f06  call    cs:__imp_GetLastError
0x1800b3f0d  nop     dword ptr [rax+rax+00h]
0x1800b3f12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f19  cmp     rcx, r15
0x1800b3f1c  jz      short loc_1800B3F89
0x1800b3f1e  test    [rcx+1Ch], r14d
0x1800b3f22  jz      short loc_1800B3F89
0x1800b3f24  mov     rcx, [rcx+10h]
0x1800b3f28  mov     edx, ebx
0x1800b3f2a  mov     r9d, eax
0x1800b3f2d  mov     [rsp+60h+var_40], eax
0x1800b3f31  mov     r8, r13
0x1800b3f34  call    WPP_SF_Dd
0x1800b3f39  jmp     short loc_1800B3F89
0x1800b3f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f42  cmp     rcx, r15
0x1800b3f45  jz      short loc_1800B3F89
0x1800b3f47  test    [rcx+1Ch], r14d
0x1800b3f4b  jz      short loc_1800B3F89
0x1800b3f4d  mov     edx, 21h ; '!'
0x1800b3f52  jmp     short loc_1800B3F7D
0x1800b3f54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f5b  cmp     rcx, r15
0x1800b3f5e  jz      short loc_1800B3F89
0x1800b3f60  test    [rcx+1Ch], r14d
0x1800b3f64  jz      short loc_1800B3F89
0x1800b3f66  mov     edx, 22h ; '"'
0x1800b3f6b  jmp     short loc_1800B3F7D
0x1800b3f6d  cmp     rcx, r15
0x1800b3f70  jz      short loc_1800B3F89
0x1800b3f72  test    [rcx+1Ch], r14d
0x1800b3f76  jz      short loc_1800B3F89
0x1800b3f78  mov     edx, 23h ; '#'
0x1800b3f7d  mov     rcx, [rcx+10h]
0x1800b3f81  mov     r8, r13
0x1800b3f84  call    WPP_SF_
0x1800b3f89  mov     [rbp+ServiceStatus.dwServiceType], ebx
0x1800b3f8c  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800b3f90  mov     ebx, 7530h
0x1800b3f95  mov     qword ptr [rbp+ServiceStatus.dwCurrentState], 2
0x1800b3f9d  mov     rcx, rsi; hServiceStatus
0x1800b3fa0  mov     [rbp+ServiceStatus.dwWaitHint], ebx
0x1800b3fa3  mov     qword ptr [rbp+ServiceStatus.dwWin32ExitCode], 0
0x1800b3fab  mov     [rbp+ServiceStatus.dwCheckPoint], 1
0x1800b3fb2  call    ?LsapWaitForSamService@@YAEPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z; LsapWaitForSamService(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x1800b3fb7  test    al, al
0x1800b3fb9  jnz     short loc_1800B4018
0x1800b3fbb  xor     ebx, ebx
0x1800b3fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3fc4  cmp     rcx, r15
0x1800b3fc7  jz      short loc_1800B4001
0x1800b3fc9  test    [rcx+1Ch], r14d
0x1800b3fcd  jz      short loc_1800B3FE5
0x1800b3fcf  mov     rcx, [rcx+10h]
0x1800b3fd3  lea     edx, [rbx+24h]
0x1800b3fd6  mov     r8, r13
0x1800b3fd9  call    WPP_SF_
0x1800b3fde  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3fe5  cmp     rcx, r15
0x1800b3fe8  jz      short loc_1800B4001
0x1800b3fea  test    [rcx+1Ch], r14d
0x1800b3fee  jz      short loc_1800B4001
0x1800b3ff0  mov     rcx, [rcx+10h]
0x1800b3ff4  mov     edx, 2Bh ; '+'
0x1800b3ff9  mov     r8, r13
0x1800b3ffc  call    WPP_SF_
0x1800b4001  mov     eax, 1Fh
0x1800b4006  mov     [rbp+ServiceStatus.dwCurrentState], 1
0x1800b400d  mov     [rbp+ServiceStatus.dwWin32ExitCode], eax
0x1800b4010  mov     [rbp+ServiceStatus.dwServiceSpecificExitCode], eax
0x1800b4013  jmp     loc_1800B4151
0x1800b4018  test    rdi, rdi
0x1800b401b  jz      loc_1800B4124
0x1800b4021  mov     [rbp+ServiceStatus.dwWaitHint], 88B8h
0x1800b4028  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b402f  cmp     rcx, r15
0x1800b4032  jz      short loc_1800B404B
0x1800b4034  test    [rcx+1Ch], r14d
0x1800b4038  jz      short loc_1800B404B
0x1800b403a  mov     rcx, [rcx+10h]
0x1800b403e  mov     edx, 25h ; '%'
0x1800b4043  mov     r8, r13
0x1800b4046  call    WPP_SF_
0x1800b404b  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800b404f  mov     rcx, rsi; hServiceStatus
0x1800b4052  call    cs:__imp_SetServiceStatus
0x1800b4059  nop     dword ptr [rax+rax+00h]
0x1800b405e  test    eax, eax
0x1800b4060  jz      short loc_1800B408B
0x1800b4062  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4069  cmp     rcx, r15
0x1800b406c  jz      short loc_1800B40C7
0x1800b406e  test    [rcx+1Ch], r14d
0x1800b4072  jz      short loc_1800B40C7
0x1800b4074  mov     r9d, [rbp+ServiceStatus.dwCheckPoint]
0x1800b4078  mov     edx, 26h ; '&'
0x1800b407d  mov     rcx, [rcx+10h]
0x1800b4081  mov     r8, r13
0x1800b4084  call    WPP_SF_d
0x1800b4089  jmp     short loc_1800B40C7
0x1800b408b  call    cs:__imp_GetLastError
0x1800b4092  nop     dword ptr [rax+rax+00h]
0x1800b4097  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b409e  cmp     rcx, r15
0x1800b40a1  jz      short loc_1800B40C7
0x1800b40a3  test    [rcx+1Ch], r14d
0x1800b40a7  jz      short loc_1800B40C7
0x1800b40a9  mov     r8d, [rbp+ServiceStatus.dwCheckPoint]
0x1800b40ad  mov     edx, 27h ; '''
0x1800b40b2  mov     rcx, [rcx+10h]
0x1800b40b6  mov     r9d, eax
0x1800b40b9  mov     [rsp+60h+var_38], r8d
0x1800b40be  mov     [rsp+60h+var_40], eax
0x1800b40c2  call    WPP_SF_Ddd
0x1800b40c7  inc     [rbp+ServiceStatus.dwCheckPoint]
0x1800b40ca  mov     edx, ebx; dwMilliseconds
0x1800b40cc  mov     rcx, rdi; hHandle
0x1800b40cf  call    cs:__imp_WaitForSingleObject
0x1800b40d6  nop     dword ptr [rax+rax+00h]
0x1800b40db  cmp     eax, 102h
0x1800b40e0  jz      loc_1800B4028
0x1800b40e6  test    eax, eax
0x1800b40e8  jnz     short loc_1800B4101
0x1800b40ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b40f1  cmp     rcx, r15
0x1800b40f4  jz      short loc_1800B412B
0x1800b40f6  test    [rcx+1Ch], r14d
0x1800b40fa  jz      short loc_1800B412B
0x1800b40fc  lea     edx, [rax+28h]
0x1800b40ff  jmp     short loc_1800B4118
0x1800b4101  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4108  cmp     rcx, r15
0x1800b410b  jz      short loc_1800B412B
0x1800b410d  test    [rcx+1Ch], r14d
0x1800b4111  jz      short loc_1800B412B
0x1800b4113  mov     edx, 29h ; ')'
0x1800b4118  mov     rcx, [rcx+10h]
0x1800b411c  mov     r8, r13
0x1800b411f  call    WPP_SF_
0x1800b4124  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b412b  mov     ebx, 1
0x1800b4130  cmp     rcx, r15
0x1800b4133  jz      short loc_1800B414A
0x1800b4135  test    [rcx+1Ch], r14d
0x1800b4139  jz      short loc_1800B414A
0x1800b413b  mov     rcx, [rcx+10h]
0x1800b413f  lea     edx, [rbx+29h]
0x1800b4142  mov     r8, r13
0x1800b4145  call    WPP_SF_
0x1800b414a  mov     [rbp+ServiceStatus.dwCurrentState], 4
0x1800b4151  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800b4155  mov     qword ptr [rbp+ServiceStatus.dwCheckPoint], 0
0x1800b415d  mov     rcx, rsi; hServiceStatus
0x1800b4160  call    cs:__imp_SetServiceStatus
0x1800b4167  nop     dword ptr [rax+rax+00h]
0x1800b416c  test    eax, eax
0x1800b416e  jz      short loc_1800B4195
0x1800b4170  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4177  cmp     rcx, r15
0x1800b417a  jz      short loc_1800B41CB
0x1800b417c  test    [rcx+1Ch], r14d
0x1800b4180  jz      short loc_1800B41CB
0x1800b4182  mov     rcx, [rcx+10h]
0x1800b4186  mov     edx, 2Ch ; ','
0x1800b418b  mov     r8, r13
0x1800b418e  call    WPP_SF_
0x1800b4193  jmp     short loc_1800B41CB
0x1800b4195  call    cs:__imp_GetLastError
0x1800b419c  nop     dword ptr [rax+rax+00h]
0x1800b41a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b41a8  cmp     rcx, r15
0x1800b41ab  jz      short loc_1800B41CB
0x1800b41ad  test    [rcx+1Ch], r14d
0x1800b41b1  jz      short loc_1800B41CB
0x1800b41b3  mov     rcx, [rcx+10h]
0x1800b41b7  mov     edx, 2Dh ; '-'
0x1800b41bc  mov     r9d, eax
0x1800b41bf  mov     [rsp+60h+var_40], eax
0x1800b41c3  mov     r8, r13
0x1800b41c6  call    WPP_SF_Dd
0x1800b41cb  test    rdi, rdi
0x1800b41ce  jz      short loc_1800B41DF
0x1800b41d0  mov     rcx, rdi; hObject
0x1800b41d3  call    cs:__imp_CloseHandle
0x1800b41da  nop     dword ptr [rax+rax+00h]
0x1800b41df  test    ebx, ebx
0x1800b41e1  jz      short loc_1800B41ED
0x1800b41e3  mov     ecx, 2; unsigned int
0x1800b41e8  call    ?LsaAutologgerEventCompleted@@YAXK@Z; LsaAutologgerEventCompleted(ulong)
0x1800b41ed  mov     rcx, [rbp+var_8]
0x1800b41f1  xor     rcx, rsp; StackCookie
0x1800b41f4  call    __security_check_cookie
0x1800b41f9  add     rsp, 60h
0x1800b41fd  pop     r15
0x1800b41ff  pop     r14
0x1800b4201  pop     r13
0x1800b4203  pop     rdi
0x1800b4204  pop     rsi
0x1800b4205  pop     rbx
0x1800b4206  pop     rbp
0x1800b4207  retn
```
