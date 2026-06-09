# CLogonTaskFramework::s_StartSkydriveSyncMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x14001b660`
- end: `0x14001b844`
- name: `?s_StartSkydriveSyncMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14001b660`
- `0x14001b8bc`
- `0x14001b9a4`
- `0x14001c330`
- `0x14010e160`
- `0x14010ed90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x14001b829`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x14001b829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b76b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b76b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001b730`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001b730`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001b711`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001b752`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001b711`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001b752`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x14001b7fb`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x14001b7fb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001b77a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001b789`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001b77a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001b789`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14001b6e6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14001b6e6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14001b6bb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14001b6bb`

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
0x14001b660  push    rbp
0x14001b662  push    rbx
0x14001b663  push    rsi
0x14001b664  push    rdi
0x14001b665  push    r14
0x14001b667  lea     rbp, [rsp-37h]
0x14001b66c  sub     rsp, 90h
0x14001b673  mov     rax, cs:__security_cookie
0x14001b67a  xor     rax, rsp
0x14001b67d  mov     [rbp+57h+var_30], rax
0x14001b681  test    dword ptr [rcx+0D8h], 100h
0x14001b68b  jnz     loc_14001B79E
0x14001b691  lea     rcx, [rbp+57h+pcbBytesNeeded]; enum FileSyncBlockedReason *
0x14001b695  mov     [rbp+57h+pcbBytesNeeded], 0
0x14001b69c  call    GetFileSyncAllowed
0x14001b6a1  test    eax, eax
0x14001b6a3  js      loc_14001B79E
0x14001b6a9  cmp     [rbp+57h+pcbBytesNeeded], 0
0x14001b6ad  jnz     loc_14001B79E
0x14001b6b3  xor     edx, edx; lpDatabaseName
0x14001b6b5  xor     ecx, ecx; lpMachineName
0x14001b6b7  lea     r8d, [rdx+4]; dwDesiredAccess
0x14001b6bb  call    cs:__imp_OpenSCManagerW
0x14001b6c2  nop     dword ptr [rax+rax+00h]
0x14001b6c7  mov     rsi, rax
0x14001b6ca  test    rax, rax
0x14001b6cd  jz      loc_14001B79E
0x14001b6d3  mov     r8d, 5; dwDesiredAccess
0x14001b6d9  lea     rdx, ServiceName; "WSearch"
0x14001b6e0  mov     rcx, rax; hSCManager
0x14001b6e3  xor     r14b, r14b
0x14001b6e6  call    cs:__imp_OpenServiceW
0x14001b6ed  nop     dword ptr [rax+rax+00h]
0x14001b6f2  mov     rdi, rax
0x14001b6f5  test    rax, rax
0x14001b6f8  jz      loc_14001B786
0x14001b6fe  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x14001b702  mov     [rbp+57h+pcbBytesNeeded], 0
0x14001b709  xor     r8d, r8d; cbBufSize
0x14001b70c  xor     edx, edx; lpServiceConfig
0x14001b70e  mov     rcx, rax; hService
0x14001b711  call    cs:__imp_QueryServiceConfigW
0x14001b718  nop     dword ptr [rax+rax+00h]
0x14001b71d  test    eax, eax
0x14001b71f  jnz     short loc_14001B786
0x14001b721  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001b726  cmp     eax, 8007007Ah
0x14001b72b  jnz     short loc_14001B786
0x14001b72d  mov     ecx, [rbp+57h+pcbBytesNeeded]; cb
0x14001b730  call    cs:__imp_CoTaskMemAlloc
0x14001b737  nop     dword ptr [rax+rax+00h]
0x14001b73c  mov     rbx, rax
0x14001b73f  test    rax, rax
0x14001b742  jz      short loc_14001B777
0x14001b744  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x14001b748  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x14001b74c  mov     rdx, rax; lpServiceConfig
0x14001b74f  mov     rcx, rdi; hService
0x14001b752  call    cs:__imp_QueryServiceConfigW
0x14001b759  nop     dword ptr [rax+rax+00h]
0x14001b75e  test    eax, eax
0x14001b760  jz      short loc_14001B7BB
0x14001b762  cmp     dword ptr [rbx+4], 4
0x14001b766  jnz     short loc_14001B7C6
0x14001b768  mov     rcx, rbx; pv
0x14001b76b  call    cs:__imp_CoTaskMemFree
0x14001b772  nop     dword ptr [rax+rax+00h]
0x14001b777  mov     rcx, rdi; hSCObject
0x14001b77a  call    cs:__imp_CloseServiceHandle
0x14001b781  nop     dword ptr [rax+rax+00h]
0x14001b786  mov     rcx, rsi; hSCObject
0x14001b789  call    cs:__imp_CloseServiceHandle
0x14001b790  nop     dword ptr [rax+rax+00h]
0x14001b795  test    r14b, r14b
0x14001b798  jnz     loc_14001B83A
0x14001b79e  xor     eax, eax
0x14001b7a0  mov     rcx, [rbp+57h+var_30]
0x14001b7a4  xor     rcx, rsp; StackCookie
0x14001b7a7  call    __security_check_cookie
0x14001b7ac  add     rsp, 90h
0x14001b7b3  pop     r14
0x14001b7b5  pop     rdi
0x14001b7b6  pop     rsi
0x14001b7b7  pop     rbx
0x14001b7b8  pop     rbp
0x14001b7b9  retn
0x14001b7bb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001b7c0  test    eax, eax
0x14001b7c2  js      short loc_14001B768
0x14001b7c4  jmp     short loc_14001B762
0x14001b7c6  xor     edx, edx; Val
0x14001b7c8  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x14001b7cc  lea     r8d, [rdx+50h]; Size
0x14001b7d0  call    memset_0
0x14001b7d5  lea     rax, ?v_OnActivation@CXHHostAppManagerBase@@MEAAXJ@Z; CXHHostAppManagerBase::v_OnActivation(long)
0x14001b7dc  mov     [rbp+57h+pNotifyBuffer.dwVersion], 2
0x14001b7e3  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x14001b7e7  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x14001b7eb  mov     edx, 8; dwNotifyMask
0x14001b7f0  mov     [rbp+57h+pNotifyBuffer.pContext], 0
0x14001b7f8  mov     rcx, rdi; hService
0x14001b7fb  call    cs:__imp_NotifyServiceStatusChangeW
0x14001b802  nop     dword ptr [rax+rax+00h]
0x14001b807  test    eax, eax
0x14001b809  jle     short loc_14001B815
0x14001b80b  movzx   eax, ax
0x14001b80e  or      eax, 80070000h
0x14001b813  test    eax, eax
0x14001b815  js      loc_14001B768
0x14001b81b  mov     r14d, 1
0x14001b821  mov     ecx, 0EA60h; dwMilliseconds
0x14001b826  mov     edx, r14d; bAlertable
0x14001b829  call    cs:__imp_SleepEx
0x14001b830  nop     dword ptr [rax+rax+00h]
0x14001b835  jmp     loc_14001B768
0x14001b83a  call    StartFileSyncIfAllowed
0x14001b83f  jmp     loc_14001B79E
```
