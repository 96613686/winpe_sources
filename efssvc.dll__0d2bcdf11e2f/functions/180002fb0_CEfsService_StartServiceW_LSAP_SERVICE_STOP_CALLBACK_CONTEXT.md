# CEfsService::StartServiceW(_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)

- ea: `0x180002fb0`
- end: `0x180003247`
- name: `?StartServiceW@CEfsService@@SAJPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180003370`

## callees

- `0x180001864`
- `0x180002c6c`
- `0x180002cd4`
- `0x180002e10`
- `0x180002fb0`
- `0x180003320`
- `0x18000339c`
- `0x180003714`
- `0x1800037b8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000307a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000307a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800030b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800030b5`
- `ntdll!EtwEventUnregister` at `0x180003045`
- `ntdll!EtwEventUnregister` at `0x180003045`
- `ntdll!EtwEventRegister` at `0x180003014`
- `ntdll!EtwEventRegister` at `0x180003014`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000313c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000313c`
- `EFSCORE!EfsInitialize` at `0x18000314e`
- `EFSCORE!EfsInitialize` at `0x18000314e`

## pseudocode

```c
__int64 __fastcall CEfsService::StartServiceW(struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *a1)
{
  char *v2; // rax
  struct _SERVICE_STATUS *v3; // rdi
  signed int updated; // ebx
  __int64 v5; // rcx
  bool v6; // sf
  SERVICE_STATUS_HANDLE v7; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  NTSTATUS v10; // eax
  bool v11; // cc
  bool v12; // al
  signed int v13; // eax
  int v14; // ecx
  bool v15; // al
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v2 = (char *)operator new(0x40u);
  v3 = (struct _SERVICE_STATUS *)v2;
  if ( !v2 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 6) = 0;
  *((_DWORD *)v2 + 14) = -1;
  *(_OWORD *)v2 = 0;
  v17 = 0;
  *(_OWORD *)(v2 + 12) = 0;
  updated = EtwEventRegister(EFS_PUBLISHER, 0, 0, &v17);
  if ( updated )
  {
    v5 = v17;
  }
  else
  {
    v5 = 0;
    g_hPublisher = v17;
    v17 = 0;
  }
  if ( v5 )
    EtwEventUnregister();
  v6 = updated < 0;
  if ( updated > 0 )
  {
    updated = (unsigned __int16)updated | 0x80070000;
    v6 = updated < 0;
  }
  if ( v6 )
    goto LABEL_16;
  v7 = RegisterServiceCtrlHandlerExW(L"EFS", CEfsService::SvcCtrlHandler, v3);
  *(_QWORD *)&v3[1].dwCurrentState = v7;
  if ( v7 )
  {
    v3->dwServiceType = 32;
    updated = CEfsService::UpdateServiceStatus(v3, 0, 2u);
    if ( updated >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *(_QWORD *)&v3[1].dwWin32ExitCode = EventW;
      if ( !EventW )
        goto LABEL_13;
      updated = CEfsService::UpdateServiceStatus(v3, 0, 2u);
      if ( updated >= 0 )
      {
        v10 = BCryptOpenAlgorithmProvider(&g_hSha256Alg, L"SHA256", 0, 0);
        updated = v10;
        v11 = v10 <= 0;
        if ( v10 || (v10 = EfsInitialize(), updated = v10, v11 = v10 <= 0, v10) )
        {
          if ( !v11 )
            updated = (unsigned __int16)v10 | 0x80070000;
          if ( updated < 0 )
            goto LABEL_16;
LABEL_26:
          v12 = CEfsService::AllowServiceStop((CEfsService *)v3);
          updated = CEfsService::UpdateServiceStatus(v3, v12, 4u);
          if ( updated >= 0 )
          {
            v13 = CEfsService::NotifyDriverServiceReady((CEfsService *)v3);
            updated = v13;
            if ( v13 >= 0 )
            {
              v15 = CEfsService::AllowServiceStop((CEfsService *)v3);
              updated = CEfsService::UpdateServiceStatus(v3, (unsigned int)v15 + 4224, 4u);
              if ( updated >= 0 )
              {
                *((_QWORD *)a1 + 1) = *(_QWORD *)&v3[1].dwWin32ExitCode;
                *(_QWORD *)a1 = CEfsService::ServiceStopCallback;
                *((_QWORD *)a1 + 2) = v3;
                return (unsigned int)updated;
              }
            }
            else
            {
              fnEfsLogTrace1(v14, (unsigned int)EFS_SERVICE_INIT_NOTIFYNTFS_ERROR, v13, 18, 142);
            }
          }
          goto LABEL_16;
        }
        EfsServerInitialized = 1;
        updated = EfsRpcRegisterServer(v3);
        if ( updated >= 0 )
        {
          fnEfsLogTrace0(v5, EFS_SERVER_READY, 18, 349);
          goto LABEL_26;
        }
      }
    }
LABEL_16:
    fnEfsLogTrace1(v5, (unsigned int)EFS_SERVICE_START_FAILED, updated, 18, 159);
    CEfsService::CleanupService(v3);
    return (unsigned int)updated;
  }
LABEL_13:
  LastError = GetLastError();
  updated = LastError;
  if ( LastError > 0 )
    updated = (unsigned __int16)LastError | 0x80070000;
  if ( updated < 0 )
    goto LABEL_16;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180002fb0  push    rbx
0x180002fb2  push    rsi
0x180002fb3  push    rdi
0x180002fb4  push    r14
0x180002fb6  sub     rsp, 38h
0x180002fba  mov     rsi, rcx
0x180002fbd  mov     ecx, 40h ; '@'; Size
0x180002fc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002fc7  mov     rdi, rax
0x180002fca  test    rax, rax
0x180002fcd  jz      loc_180003235
0x180002fd3  mov     qword ptr [rax+20h], 0
0x180002fdb  lea     r9, [rsp+58h+arg_8]
0x180002fe0  mov     qword ptr [rax+28h], 0
0x180002fe8  lea     rcx, EFS_PUBLISHER
0x180002fef  mov     qword ptr [rax+30h], 0
0x180002ff7  xorps   xmm0, xmm0
0x180002ffa  mov     dword ptr [rax+38h], 0FFFFFFFFh
0x180003001  xor     r8d, r8d
0x180003004  xor     eax, eax
0x180003006  xor     edx, edx
0x180003008  movups  xmmword ptr [rdi], xmm0
0x18000300b  mov     [rsp+58h+arg_8], rax
0x180003010  movups  xmmword ptr [rdi+0Ch], xmm0
0x180003014  call    cs:__imp_EtwEventRegister
0x18000301b  nop     dword ptr [rax+rax+00h]
0x180003020  mov     ebx, eax
0x180003022  test    eax, eax
0x180003024  jnz     short loc_18000303B
0x180003026  mov     rax, [rsp+58h+arg_8]
0x18000302b  xor     ecx, ecx
0x18000302d  mov     cs:g_hPublisher, rax
0x180003034  mov     [rsp+58h+arg_8], rcx
0x180003039  jmp     short loc_180003040
0x18000303b  mov     rcx, [rsp+58h+arg_8]
0x180003040  test    rcx, rcx
0x180003043  jz      short loc_180003051
0x180003045  call    cs:__imp_EtwEventUnregister
0x18000304c  nop     dword ptr [rax+rax+00h]
0x180003051  mov     r14d, 80070000h
0x180003057  test    ebx, ebx
0x180003059  jle     short loc_180003063
0x18000305b  movzx   ebx, bx
0x18000305e  or      ebx, r14d
0x180003061  test    ebx, ebx
0x180003063  js      loc_1800030EA
0x180003069  mov     r8, rdi; lpContext
0x18000306c  lea     rdx, ?SvcCtrlHandler@CEfsService@@CAKKKPEAX0@Z; lpHandlerProc
0x180003073  lea     rcx, ServiceName; "EFS"
0x18000307a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180003081  nop     dword ptr [rax+rax+00h]
0x180003086  mov     [rdi+20h], rax
0x18000308a  test    rax, rax
0x18000308d  jz      short loc_1800030CA
0x18000308f  xor     edx, edx; unsigned int
0x180003091  mov     dword ptr [rdi], 20h ; ' '
0x180003097  mov     rcx, rdi; lpServiceStatus
0x18000309a  lea     r8d, [rdx+2]; unsigned int
0x18000309e  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x1800030a3  mov     ebx, eax
0x1800030a5  test    eax, eax
0x1800030a7  js      short loc_1800030EA
0x1800030a9  xor     r9d, r9d; lpName
0x1800030ac  xor     r8d, r8d; bInitialState
0x1800030af  xor     ecx, ecx; lpEventAttributes
0x1800030b1  lea     edx, [r9+1]; bManualReset
0x1800030b5  call    cs:__imp_CreateEventW
0x1800030bc  nop     dword ptr [rax+rax+00h]
0x1800030c1  mov     [rdi+28h], rax
0x1800030c5  test    rax, rax
0x1800030c8  jnz     short loc_180003114
0x1800030ca  call    cs:__imp_GetLastError
0x1800030d1  nop     dword ptr [rax+rax+00h]
0x1800030d6  mov     ebx, eax
0x1800030d8  test    eax, eax
0x1800030da  jle     short loc_1800030E2
0x1800030dc  movzx   ebx, ax
0x1800030df  or      ebx, r14d
0x1800030e2  test    ebx, ebx
0x1800030e4  jns     loc_18000323A
0x1800030ea  mov     r9d, 12h
0x1800030f0  mov     [rsp+58h+var_38], 9Fh
0x1800030f8  mov     r8d, ebx
0x1800030fb  lea     rdx, EFS_SERVICE_START_FAILED
0x180003102  call    fnEfsLogTrace1
0x180003107  mov     rcx, rdi; lpServiceStatus
0x18000310a  call    ?CleanupService@CEfsService@@QEAAXXZ; CEfsService::CleanupService(void)
0x18000310f  jmp     loc_18000323A
0x180003114  xor     edx, edx; unsigned int
0x180003116  mov     rcx, rdi; lpServiceStatus
0x180003119  lea     r8d, [rdx+2]; unsigned int
0x18000311d  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180003122  mov     ebx, eax
0x180003124  test    eax, eax
0x180003126  js      short loc_1800030EA
0x180003128  xor     r9d, r9d; dwFlags
0x18000312b  lea     rdx, pszAlgId; "SHA256"
0x180003132  xor     r8d, r8d; pszImplementation
0x180003135  lea     rcx, g_hSha256Alg; phAlgorithm
0x18000313c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180003143  nop     dword ptr [rax+rax+00h]
0x180003148  mov     ebx, eax
0x18000314a  test    eax, eax
0x18000314c  jnz     short loc_180003160
0x18000314e  call    cs:__imp_EfsInitialize
0x180003155  nop     dword ptr [rax+rax+00h]
0x18000315a  mov     ebx, eax
0x18000315c  test    eax, eax
0x18000315e  jz      short loc_180003172
0x180003160  jle     short loc_180003168
0x180003162  movzx   ebx, ax
0x180003165  or      ebx, r14d
0x180003168  test    ebx, ebx
0x18000316a  js      loc_1800030EA
0x180003170  jmp     short loc_1800031A3
0x180003172  mov     rcx, rdi; void *
0x180003175  mov     cs:EfsServerInitialized, 1
0x18000317c  call    ?EfsRpcRegisterServer@@YAJPEAX@Z; EfsRpcRegisterServer(void *)
0x180003181  mov     ebx, eax
0x180003183  test    eax, eax
0x180003185  js      loc_1800030EA
0x18000318b  mov     r9d, 15Dh
0x180003191  lea     rdx, EFS_SERVER_READY
0x180003198  mov     r8d, 12h
0x18000319e  call    fnEfsLogTrace0
0x1800031a3  mov     rcx, rdi; this
0x1800031a6  call    ?AllowServiceStop@CEfsService@@AEAA_NXZ; CEfsService::AllowServiceStop(void)
0x1800031ab  mov     r14d, 4
0x1800031b1  movzx   edx, al; unsigned int
0x1800031b4  mov     r8d, r14d; unsigned int
0x1800031b7  mov     rcx, rdi; lpServiceStatus
0x1800031ba  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x1800031bf  mov     ebx, eax
0x1800031c1  test    eax, eax
0x1800031c3  js      loc_1800030EA
0x1800031c9  mov     rcx, rdi; this
0x1800031cc  call    ?NotifyDriverServiceReady@CEfsService@@AEAAJXZ; CEfsService::NotifyDriverServiceReady(void)
0x1800031d1  mov     ebx, eax
0x1800031d3  test    eax, eax
0x1800031d5  jns     short loc_1800031F7
0x1800031d7  lea     r9d, [r14+0Eh]
0x1800031db  mov     [rsp+58h+var_38], 8Eh
0x1800031e3  mov     r8d, eax
0x1800031e6  lea     rdx, EFS_SERVICE_INIT_NOTIFYNTFS_ERROR
0x1800031ed  call    fnEfsLogTrace1
0x1800031f2  jmp     loc_1800030EA
0x1800031f7  mov     rcx, rdi; this
0x1800031fa  call    ?AllowServiceStop@CEfsService@@AEAA_NXZ; CEfsService::AllowServiceStop(void)
0x1800031ff  movzx   edx, al
0x180003202  mov     r8d, r14d; unsigned int
0x180003205  add     edx, 1080h; unsigned int
0x18000320b  mov     rcx, rdi; lpServiceStatus
0x18000320e  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180003213  mov     ebx, eax
0x180003215  test    eax, eax
0x180003217  js      loc_1800030EA
0x18000321d  mov     rax, [rdi+28h]
0x180003221  mov     [rsi+8], rax
0x180003225  lea     rax, ?ServiceStopCallback@CEfsService@@CAJPEAX@Z; CEfsService::ServiceStopCallback(void *)
0x18000322c  mov     [rsi], rax
0x18000322f  mov     [rsi+10h], rdi
0x180003233  jmp     short loc_18000323A
0x180003235  mov     ebx, 8007000Eh
0x18000323a  mov     eax, ebx
0x18000323c  add     rsp, 38h
0x180003240  pop     r14
0x180003242  pop     rdi
0x180003243  pop     rsi
0x180003244  pop     rbx
0x180003245  retn
```
