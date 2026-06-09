# CLogonTaskFramework::s_StartSkydriveSyncMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140015f70`
- end: `0x140016113`
- name: `?s_StartSkydriveSyncMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140015f70`
- `0x140016188`
- `0x140016268`
- `0x140016b10`
- `0x1401040e0`
- `0x140104ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1400160fe`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1400160fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001602a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001602a`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1400160d6`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1400160d6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140016011`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140016046`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140016011`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140016046`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140016062`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001606b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140016062`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001606b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140015ff0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140015ff0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140015fcb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140015fcb`

## pseudocode

```c
__int64 __fastcall CLogonTaskFramework::s_StartSkydriveSyncMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  char v4; // r14
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  struct _QUERY_SERVICE_CONFIGW *v8; // rbx
  signed int v10; // eax
  bool v11; // sf
  DWORD pcbBytesNeeded[4]; // [rsp+20h] [rbp-39h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+30h] [rbp-29h] BYREF

  if ( (*((_DWORD *)a1 + 54) & 0x100) == 0 )
  {
    pcbBytesNeeded[0] = 0;
    if ( (int)GetFileSyncAllowed((enum FileSyncBlockedReason *)pcbBytesNeeded) >= 0 && !pcbBytesNeeded[0] )
    {
      v2 = OpenSCManagerW(0, 0, 4u);
      v3 = v2;
      if ( v2 )
      {
        v4 = 0;
        v5 = OpenServiceW(v2, L"WSearch", 5u);
        v6 = v5;
        if ( v5 )
        {
          pcbBytesNeeded[0] = 0;
          if ( !QueryServiceConfigW(v5, 0, 0, pcbBytesNeeded) && (unsigned int)ResultFromKnownLastError() == -2147024774 )
          {
            v7 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemAlloc(pcbBytesNeeded[0]);
            v8 = v7;
            if ( v7 )
            {
              if ( (QueryServiceConfigW(v6, v7, pcbBytesNeeded[0], pcbBytesNeeded)
                 || (int)ResultFromKnownLastError() >= 0)
                && v8->dwStartType != 4 )
              {
                memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
                pNotifyBuffer.dwVersion = 2;
                pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)CXHHostAppManagerBase::v_OnActivation;
                pNotifyBuffer.pContext = 0;
                v10 = NotifyServiceStatusChangeW(v6, 8u, &pNotifyBuffer);
                v11 = v10 < 0;
                if ( v10 > 0 )
                  v11 = 1;
                if ( !v11 )
                {
                  v4 = 1;
                  SleepEx(0xEA60u, 1);
                }
              }
              CoTaskMemFree(v8);
            }
            CloseServiceHandle(v6);
          }
        }
        CloseServiceHandle(v3);
        if ( v4 )
          StartFileSyncIfAllowed();
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140015f70  push    rbp
0x140015f72  push    rbx
0x140015f73  push    rsi
0x140015f74  push    rdi
0x140015f75  push    r14
0x140015f77  lea     rbp, [rsp-37h]
0x140015f7c  sub     rsp, 90h
0x140015f83  mov     rax, cs:__security_cookie
0x140015f8a  xor     rax, rsp
0x140015f8d  mov     [rbp+57h+var_30], rax
0x140015f91  test    dword ptr [rcx+0D8h], 100h
0x140015f9b  jnz     loc_14001607A
0x140015fa1  lea     rcx, [rbp+57h+pcbBytesNeeded]; enum FileSyncBlockedReason *
0x140015fa5  mov     [rbp+57h+pcbBytesNeeded], 0
0x140015fac  call    GetFileSyncAllowed
0x140015fb1  test    eax, eax
0x140015fb3  js      loc_14001607A
0x140015fb9  cmp     [rbp+57h+pcbBytesNeeded], 0
0x140015fbd  jnz     loc_14001607A
0x140015fc3  xor     edx, edx; lpDatabaseName
0x140015fc5  xor     ecx, ecx; lpMachineName
0x140015fc7  lea     r8d, [rdx+4]; dwDesiredAccess
0x140015fcb  call    cs:__imp_OpenSCManagerW
0x140015fd1  mov     rsi, rax
0x140015fd4  test    rax, rax
0x140015fd7  jz      loc_14001607A
0x140015fdd  mov     r8d, 5; dwDesiredAccess
0x140015fe3  lea     rdx, ServiceName; "WSearch"
0x140015fea  mov     rcx, rax; hSCManager
0x140015fed  xor     r14b, r14b
0x140015ff0  call    cs:__imp_OpenServiceW
0x140015ff6  mov     rdi, rax
0x140015ff9  test    rax, rax
0x140015ffc  jz      short loc_140016068
0x140015ffe  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x140016002  mov     [rbp+57h+pcbBytesNeeded], 0
0x140016009  xor     r8d, r8d; cbBufSize
0x14001600c  xor     edx, edx; lpServiceConfig
0x14001600e  mov     rcx, rax; hService
0x140016011  call    cs:__imp_QueryServiceConfigW
0x140016017  test    eax, eax
0x140016019  jnz     short loc_140016068
0x14001601b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140016020  cmp     eax, 8007007Ah
0x140016025  jnz     short loc_140016068
0x140016027  mov     ecx, [rbp+57h+pcbBytesNeeded]; cb
0x14001602a  call    cs:__imp_CoTaskMemAlloc
0x140016030  mov     rbx, rax
0x140016033  test    rax, rax
0x140016036  jz      short loc_14001605F
0x140016038  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x14001603c  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x140016040  mov     rdx, rax; lpServiceConfig
0x140016043  mov     rcx, rdi; hService
0x140016046  call    cs:__imp_QueryServiceConfigW
0x14001604c  test    eax, eax
0x14001604e  jz      short loc_140016096
0x140016050  cmp     dword ptr [rbx+4], 4
0x140016054  jnz     short loc_1400160A1
0x140016056  mov     rcx, rbx; pv
0x140016059  call    cs:__imp_CoTaskMemFree
0x14001605f  mov     rcx, rdi; hSCObject
0x140016062  call    cs:__imp_CloseServiceHandle
0x140016068  mov     rcx, rsi; hSCObject
0x14001606b  call    cs:__imp_CloseServiceHandle
0x140016071  test    r14b, r14b
0x140016074  jnz     loc_140016109
0x14001607a  xor     eax, eax
0x14001607c  mov     rcx, [rbp+57h+var_30]
0x140016080  xor     rcx, rsp; StackCookie
0x140016083  call    __security_check_cookie
0x140016088  add     rsp, 90h
0x14001608f  pop     r14
0x140016091  pop     rdi
0x140016092  pop     rsi
0x140016093  pop     rbx
0x140016094  pop     rbp
0x140016095  retn
0x140016096  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001609b  test    eax, eax
0x14001609d  js      short loc_140016056
0x14001609f  jmp     short loc_140016050
0x1400160a1  xor     edx, edx; Val
0x1400160a3  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x1400160a7  lea     r8d, [rdx+50h]; Size
0x1400160ab  call    memset_0
0x1400160b0  lea     rax, ?v_OnActivation@CXHHostAppManagerBase@@MEAAXJ@Z; CXHHostAppManagerBase::v_OnActivation(long)
0x1400160b7  mov     [rbp+57h+pNotifyBuffer.dwVersion], 2
0x1400160be  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x1400160c2  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x1400160c6  mov     edx, 8; dwNotifyMask
0x1400160cb  mov     [rbp+57h+pNotifyBuffer.pContext], 0
0x1400160d3  mov     rcx, rdi; hService
0x1400160d6  call    cs:__imp_NotifyServiceStatusChangeW
0x1400160dc  test    eax, eax
0x1400160de  jle     short loc_1400160EA
0x1400160e0  movzx   eax, ax
0x1400160e3  or      eax, 80070000h
0x1400160e8  test    eax, eax
0x1400160ea  js      loc_140016056
0x1400160f0  mov     r14d, 1
0x1400160f6  mov     ecx, 0EA60h; dwMilliseconds
0x1400160fb  mov     edx, r14d; bAlertable
0x1400160fe  call    cs:__imp_SleepEx
0x140016104  jmp     loc_140016056
0x140016109  call    StartFileSyncIfAllowed
0x14001610e  jmp     loc_14001607A
```
