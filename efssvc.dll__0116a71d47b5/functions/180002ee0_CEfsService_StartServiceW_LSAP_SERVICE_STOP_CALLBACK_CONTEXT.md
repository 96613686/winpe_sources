# CEfsService::StartServiceW(_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)

- ea: `0x180002ee0`
- end: `0x180003144`
- name: `?StartServiceW@CEfsService@@SAJPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180003240`

## callees

- `0x180001854`
- `0x180002c00`
- `0x180002c60`
- `0x180002d6c`
- `0x180002ee0`
- `0x1800031f4`
- `0x18000326c`
- `0x18000356c`
- `0x180003604`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002f9a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fde`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fcf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fcf`
- `ntdll!EtwEventUnregister` at `0x180002f6f`
- `ntdll!EtwEventUnregister` at `0x180002f6f`
- `ntdll!EtwEventRegister` at `0x180002f44`
- `ntdll!EtwEventRegister` at `0x180002f44`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000304a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000304a`
- `EFSCORE!EfsInitialize` at `0x180003056`
- `EFSCORE!EfsInitialize` at `0x180003056`

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
  int v13; // eax
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
0x180002ee0  push    rbx
0x180002ee2  push    rsi
0x180002ee3  push    rdi
0x180002ee4  push    r14
0x180002ee6  sub     rsp, 38h
0x180002eea  mov     rsi, rcx
0x180002eed  mov     ecx, 40h ; '@'; Size
0x180002ef2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ef7  mov     rdi, rax
0x180002efa  test    rax, rax
0x180002efd  jz      loc_180003133
0x180002f03  mov     qword ptr [rax+20h], 0
0x180002f0b  lea     r9, [rsp+58h+arg_8]
0x180002f10  mov     qword ptr [rax+28h], 0
0x180002f18  lea     rcx, EFS_PUBLISHER
0x180002f1f  mov     qword ptr [rax+30h], 0
0x180002f27  xorps   xmm0, xmm0
0x180002f2a  mov     dword ptr [rax+38h], 0FFFFFFFFh
0x180002f31  xor     r8d, r8d
0x180002f34  xor     eax, eax
0x180002f36  xor     edx, edx
0x180002f38  movups  xmmword ptr [rdi], xmm0
0x180002f3b  mov     [rsp+58h+arg_8], rax
0x180002f40  movups  xmmword ptr [rdi+0Ch], xmm0
0x180002f44  call    cs:__imp_EtwEventRegister
0x180002f4a  mov     ebx, eax
0x180002f4c  test    eax, eax
0x180002f4e  jnz     short loc_180002F65
0x180002f50  mov     rax, [rsp+58h+arg_8]
0x180002f55  xor     ecx, ecx
0x180002f57  mov     cs:g_hPublisher, rax
0x180002f5e  mov     [rsp+58h+arg_8], rcx
0x180002f63  jmp     short loc_180002F6A
0x180002f65  mov     rcx, [rsp+58h+arg_8]
0x180002f6a  test    rcx, rcx
0x180002f6d  jz      short loc_180002F75
0x180002f6f  call    cs:__imp_EtwEventUnregister
0x180002f75  mov     r14d, 80070000h
0x180002f7b  test    ebx, ebx
0x180002f7d  jle     short loc_180002F87
0x180002f7f  movzx   ebx, bx
0x180002f82  or      ebx, r14d
0x180002f85  test    ebx, ebx
0x180002f87  js      short loc_180002FF8
0x180002f89  mov     r8, rdi; lpContext
0x180002f8c  lea     rdx, ?SvcCtrlHandler@CEfsService@@CAKKKPEAX0@Z; lpHandlerProc
0x180002f93  lea     rcx, ServiceName; "EFS"
0x180002f9a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002fa0  mov     [rdi+20h], rax
0x180002fa4  test    rax, rax
0x180002fa7  jz      short loc_180002FDE
0x180002fa9  xor     edx, edx; unsigned int
0x180002fab  mov     dword ptr [rdi], 20h ; ' '
0x180002fb1  mov     rcx, rdi; lpServiceStatus
0x180002fb4  lea     r8d, [rdx+2]; unsigned int
0x180002fb8  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002fbd  mov     ebx, eax
0x180002fbf  test    eax, eax
0x180002fc1  js      short loc_180002FF8
0x180002fc3  xor     r9d, r9d; lpName
0x180002fc6  xor     r8d, r8d; bInitialState
0x180002fc9  xor     ecx, ecx; lpEventAttributes
0x180002fcb  lea     edx, [r9+1]; bManualReset
0x180002fcf  call    cs:__imp_CreateEventW
0x180002fd5  mov     [rdi+28h], rax
0x180002fd9  test    rax, rax
0x180002fdc  jnz     short loc_180003022
0x180002fde  call    cs:__imp_GetLastError
0x180002fe4  mov     ebx, eax
0x180002fe6  test    eax, eax
0x180002fe8  jle     short loc_180002FF0
0x180002fea  movzx   ebx, ax
0x180002fed  or      ebx, r14d
0x180002ff0  test    ebx, ebx
0x180002ff2  jns     loc_180003138
0x180002ff8  mov     r9d, 12h
0x180002ffe  mov     [rsp+58h+var_38], 9Fh
0x180003006  mov     r8d, ebx
0x180003009  lea     rdx, EFS_SERVICE_START_FAILED
0x180003010  call    fnEfsLogTrace1
0x180003015  mov     rcx, rdi; lpServiceStatus
0x180003018  call    ?CleanupService@CEfsService@@QEAAXXZ; CEfsService::CleanupService(void)
0x18000301d  jmp     loc_180003138
0x180003022  xor     edx, edx; unsigned int
0x180003024  mov     rcx, rdi; lpServiceStatus
0x180003027  lea     r8d, [rdx+2]; unsigned int
0x18000302b  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180003030  mov     ebx, eax
0x180003032  test    eax, eax
0x180003034  js      short loc_180002FF8
0x180003036  xor     r9d, r9d; dwFlags
0x180003039  lea     rdx, pszAlgId; "SHA256"
0x180003040  xor     r8d, r8d; pszImplementation
0x180003043  lea     rcx, g_hSha256Alg; phAlgorithm
0x18000304a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180003050  mov     ebx, eax
0x180003052  test    eax, eax
0x180003054  jnz     short loc_180003062
0x180003056  call    cs:__imp_EfsInitialize
0x18000305c  mov     ebx, eax
0x18000305e  test    eax, eax
0x180003060  jz      short loc_180003070
0x180003062  jle     short loc_18000306A
0x180003064  movzx   ebx, ax
0x180003067  or      ebx, r14d
0x18000306a  test    ebx, ebx
0x18000306c  js      short loc_180002FF8
0x18000306e  jmp     short loc_1800030A1
0x180003070  mov     rcx, rdi; void *
0x180003073  mov     cs:EfsServerInitialized, 1
0x18000307a  call    ?EfsRpcRegisterServer@@YAJPEAX@Z; EfsRpcRegisterServer(void *)
0x18000307f  mov     ebx, eax
0x180003081  test    eax, eax
0x180003083  js      loc_180002FF8
0x180003089  mov     r9d, 15Dh
0x18000308f  lea     rdx, EFS_SERVER_READY
0x180003096  mov     r8d, 12h
0x18000309c  call    fnEfsLogTrace0
0x1800030a1  mov     rcx, rdi; this
0x1800030a4  call    ?AllowServiceStop@CEfsService@@AEAA_NXZ; CEfsService::AllowServiceStop(void)
0x1800030a9  mov     r14d, 4
0x1800030af  movzx   edx, al; unsigned int
0x1800030b2  mov     r8d, r14d; unsigned int
0x1800030b5  mov     rcx, rdi; lpServiceStatus
0x1800030b8  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x1800030bd  mov     ebx, eax
0x1800030bf  test    eax, eax
0x1800030c1  js      loc_180002FF8
0x1800030c7  mov     rcx, rdi; this
0x1800030ca  call    ?NotifyDriverServiceReady@CEfsService@@AEAAJXZ; CEfsService::NotifyDriverServiceReady(void)
0x1800030cf  mov     ebx, eax
0x1800030d1  test    eax, eax
0x1800030d3  jns     short loc_1800030F5
0x1800030d5  lea     r9d, [r14+0Eh]
0x1800030d9  mov     [rsp+58h+var_38], 8Eh
0x1800030e1  mov     r8d, eax
0x1800030e4  lea     rdx, EFS_SERVICE_INIT_NOTIFYNTFS_ERROR
0x1800030eb  call    fnEfsLogTrace1
0x1800030f0  jmp     loc_180002FF8
0x1800030f5  mov     rcx, rdi; this
0x1800030f8  call    ?AllowServiceStop@CEfsService@@AEAA_NXZ; CEfsService::AllowServiceStop(void)
0x1800030fd  movzx   edx, al
0x180003100  mov     r8d, r14d; unsigned int
0x180003103  add     edx, 1080h; unsigned int
0x180003109  mov     rcx, rdi; lpServiceStatus
0x18000310c  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180003111  mov     ebx, eax
0x180003113  test    eax, eax
0x180003115  js      loc_180002FF8
0x18000311b  mov     rax, [rdi+28h]
0x18000311f  mov     [rsi+8], rax
0x180003123  lea     rax, ?ServiceStopCallback@CEfsService@@CAJPEAX@Z; CEfsService::ServiceStopCallback(void *)
0x18000312a  mov     [rsi], rax
0x18000312d  mov     [rsi+10h], rdi
0x180003131  jmp     short loc_180003138
0x180003133  mov     ebx, 8007000Eh
0x180003138  mov     eax, ebx
0x18000313a  add     rsp, 38h
0x18000313e  pop     r14
0x180003140  pop     rdi
0x180003141  pop     rsi
0x180003142  pop     rbx
0x180003143  retn
```
