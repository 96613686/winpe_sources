# ServiceHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180011c70`
- end: `0x180011ea9`
- name: `?ServiceHandlerEx@@YAKKKPEAX0@Z`
- size: `569`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005134`
- `0x1800056c4`
- `0x18000def0`
- `0x180011594`
- `0x180011c70`
- `0x180045d7c`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180011db8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180011db8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011dcc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011dcc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011d17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011e59`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011d17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011e59`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011e4a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011e4a`
- `iashlpr!ConfigureIas` at `0x180011dc6`
- `iashlpr!ConfigureIas` at `0x180011dc6`

## string_xrefs

- `0x180011df3`: `Service control stop or shutdown called`
- `0x180011d9a`: `Received Remote Access Policy change control message`

## pseudocode

```c
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  CDimInterfaceTable *v7; // rcx
  int v8; // edi
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  int v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  DWORD v15; // ebx
  int v16; // ebx
  GUID ActivityId; // [rsp+28h] [rbp-30h] BYREF

  ActivityId = 0;
  v8 = SetRasServerActivityId(&ActivityId);
  if ( dwControl > 8 )
  {
    v13 = dwControl - 9;
    if ( !v13 )
      goto LABEL_36;
    v14 = v13 - 1;
    if ( !v14 )
      goto LABEL_36;
    v15 = v14 - 1;
    if ( !v15 )
    {
      if ( (((_DWORD)qword_180070F24 - 1) & 0xFFFFFFFD) != 0 )
        CDimInterfaceTable::ServiceControlDeviceEvent(v7, dwEventType, lpEventData);
      goto LABEL_36;
    }
    v16 = v15 - 4;
    if ( v16 )
    {
      if ( v16 != 113 )
      {
LABEL_19:
        if ( v8 )
          ReSetActivityId(&ActivityId);
        return 120;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasDimTraceAdminInfo,
          L"Received Remote Access Policy change control message");
      if ( CoInitializeEx(0, 0) >= 0 )
      {
        ConfigureIas();
        CoUninitialize();
      }
      goto LABEL_36;
    }
    goto LABEL_26;
  }
  if ( dwControl == 8 )
    goto LABEL_36;
  v9 = dwControl - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 2;
        if ( v12 )
        {
          if ( v12 != 2 )
            goto LABEL_19;
          goto LABEL_36;
        }
        goto LABEL_26;
      }
      if ( (unsigned int)(qword_180070F24 - 4) <= 1 )
        goto LABEL_36;
      qword_180070F34 = 0;
      LODWORD(qword_180070F24) = 4;
    }
    else
    {
      if ( (unsigned int)(qword_180070F24 - 6) <= 1 )
        goto LABEL_36;
      LODWORD(qword_180070F24) = 7;
      qword_180070F34 = 0x30D4000000000LL;
    }
    HIDWORD(qword_180070F24) = 7;
    SetEvent(gblhEventDDMServiceState);
    goto LABEL_36;
  }
LABEL_26:
  if ( (((_DWORD)qword_180070F24 - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDimTraceAdminInfo,
        L"Service control stop or shutdown called");
    qword_180070F24 = 3;
    qword_180070F34 = 0x30D4000000001LL;
    DimAnnounceServiceStatus();
    while ( (gbldwDIMComponentsLoaded & 0x10) == 0 )
    {
      if ( (gbldwDIMComponentsLoaded & 0x20) != 0 )
        goto LABEL_37;
      Sleep(0x3E8u);
    }
    SetEvent(gblhEventTerminateDIM);
    goto LABEL_37;
  }
LABEL_36:
  DimAnnounceServiceStatus();
LABEL_37:
  if ( v8 )
    ReSetActivityId(&ActivityId);
  return 0;
}

```

## disassembly

```asm
0x180011c70  mov     [rsp+arg_0], rbx
0x180011c75  push    rbp
0x180011c76  push    rsi
0x180011c77  push    rdi
0x180011c78  sub     rsp, 40h
0x180011c7c  mov     rax, cs:__security_cookie
0x180011c83  xor     rax, rsp
0x180011c86  mov     [rsp+58h+var_20], rax
0x180011c8b  mov     ebx, ecx
0x180011c8d  xorps   xmm0, xmm0
0x180011c90  lea     rcx, [rsp+58h+ActivityId]; ActivityId
0x180011c95  mov     rbp, r8
0x180011c98  movups  xmmword ptr [rsp+58h+ActivityId.Data1], xmm0
0x180011c9d  mov     esi, edx
0x180011c9f  call    SetRasServerActivityId
0x180011ca4  mov     edi, eax
0x180011ca6  cmp     ebx, 8
0x180011ca9  ja      loc_180011D54
0x180011caf  jz      loc_180011E7A
0x180011cb5  sub     ebx, 1
0x180011cb8  jz      loc_180011DD7
0x180011cbe  sub     ebx, 1
0x180011cc1  jz      short loc_180011D22
0x180011cc3  sub     ebx, 1
0x180011cc6  jz      short loc_180011CDF
0x180011cc8  sub     ebx, 2
0x180011ccb  jz      loc_180011DD7
0x180011cd1  cmp     ebx, 2
0x180011cd4  jz      loc_180011E7A
0x180011cda  jmp     loc_180011D79
0x180011cdf  mov     eax, dword ptr cs:qword_180070F24
0x180011ce5  add     eax, 0FFFFFFFCh
0x180011ce8  cmp     eax, 1
0x180011ceb  jbe     loc_180011E7A
0x180011cf1  mov     cs:qword_180070F34, 0
0x180011cfc  mov     dword ptr cs:qword_180070F24, 4
0x180011d06  mov     rcx, cs:?gblhEventDDMServiceState@@3PEAXEA; hEvent
0x180011d0d  mov     dword ptr cs:qword_180070F24+4, 7
0x180011d17  call    cs:__imp_SetEvent
0x180011d1d  jmp     loc_180011E7A
0x180011d22  mov     eax, dword ptr cs:qword_180070F24
0x180011d28  add     eax, 0FFFFFFFAh
0x180011d2b  cmp     eax, 1
0x180011d2e  jbe     loc_180011E7A
0x180011d34  mov     dword ptr cs:qword_180070F24, 7
0x180011d3e  mov     dword ptr cs:qword_180070F34, 0
0x180011d48  mov     dword ptr cs:qword_180070F34+4, 30D40h
0x180011d52  jmp     short loc_180011D06
0x180011d54  sub     ebx, 9
0x180011d57  jz      loc_180011E7A
0x180011d5d  sub     ebx, 1
0x180011d60  jz      loc_180011E7A
0x180011d66  sub     ebx, 1
0x180011d69  jz      loc_180011E61
0x180011d6f  sub     ebx, 4
0x180011d72  jz      short loc_180011DD7
0x180011d74  cmp     ebx, 71h ; 'q'
0x180011d77  jz      short loc_180011D91
0x180011d79  test    edi, edi
0x180011d7b  jz      short loc_180011D87
0x180011d7d  lea     rcx, [rsp+58h+ActivityId]; ActivityId
0x180011d82  call    ReSetActivityId
0x180011d87  mov     eax, 78h ; 'x'
0x180011d8c  jmp     loc_180011E8F
0x180011d91  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180011d98  jz      short loc_180011DB4
0x180011d9a  lea     r8, aReceivedRemote; "Received Remote Access Policy change co"...
0x180011da1  lea     rdx, RasDimTraceAdminInfo
0x180011da8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011daf  call    McTemplateU0z_EventWriteTransfer
0x180011db4  xor     edx, edx; dwCoInit
0x180011db6  xor     ecx, ecx; pvReserved
0x180011db8  call    cs:__imp_CoInitializeEx
0x180011dbe  test    eax, eax
0x180011dc0  js      loc_180011E7A
0x180011dc6  call    cs:__imp_ConfigureIas
0x180011dcc  call    cs:__imp_CoUninitialize
0x180011dd2  jmp     loc_180011E7A
0x180011dd7  mov     eax, dword ptr cs:qword_180070F24
0x180011ddd  dec     eax
0x180011ddf  test    eax, 0FFFFFFFDh
0x180011de4  jz      loc_180011E7A
0x180011dea  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180011df1  jz      short loc_180011E0D
0x180011df3  lea     r8, aServiceControl; "Service control stop or shutdown called"
0x180011dfa  lea     rdx, RasDimTraceAdminInfo
0x180011e01  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011e08  call    McTemplateU0z_EventWriteTransfer
0x180011e0d  mov     cs:qword_180070F24, 3
0x180011e18  mov     dword ptr cs:qword_180070F34, 1
0x180011e22  mov     dword ptr cs:qword_180070F34+4, 30D40h
0x180011e2c  call    ?DimAnnounceServiceStatus@@YAXXZ; DimAnnounceServiceStatus(void)
0x180011e31  mov     eax, cs:?gbldwDIMComponentsLoaded@@3KA; ulong gbldwDIMComponentsLoaded
0x180011e37  test    al, 10h
0x180011e39  jnz     short loc_180011E52
0x180011e3b  mov     eax, cs:?gbldwDIMComponentsLoaded@@3KA; ulong gbldwDIMComponentsLoaded
0x180011e41  test    al, 20h
0x180011e43  jnz     short loc_180011E7F
0x180011e45  mov     ecx, 3E8h; dwMilliseconds
0x180011e4a  call    cs:__imp_Sleep
0x180011e50  jmp     short loc_180011E31
0x180011e52  mov     rcx, cs:?gblhEventTerminateDIM@@3PEAXEA; hEvent
0x180011e59  call    cs:__imp_SetEvent
0x180011e5f  jmp     short loc_180011E7F
0x180011e61  mov     eax, dword ptr cs:qword_180070F24
0x180011e67  dec     eax
0x180011e69  test    eax, 0FFFFFFFDh
0x180011e6e  jz      short loc_180011E7A
0x180011e70  mov     r8, rbp; void *
0x180011e73  mov     edx, esi; unsigned int
0x180011e75  call    ?ServiceControlDeviceEvent@CDimInterfaceTable@@QEAAXKPEAX@Z; CDimInterfaceTable::ServiceControlDeviceEvent(ulong,void *)
0x180011e7a  call    ?DimAnnounceServiceStatus@@YAXXZ; DimAnnounceServiceStatus(void)
0x180011e7f  test    edi, edi
0x180011e81  jz      short loc_180011E8D
0x180011e83  lea     rcx, [rsp+58h+ActivityId]; ActivityId
0x180011e88  call    ReSetActivityId
0x180011e8d  xor     eax, eax
0x180011e8f  mov     rcx, [rsp+58h+var_20]
0x180011e94  xor     rcx, rsp; StackCookie
0x180011e97  call    __security_check_cookie
0x180011e9c  mov     rbx, [rsp+58h+arg_0]
0x180011ea1  add     rsp, 40h
0x180011ea5  pop     rdi
0x180011ea6  pop     rsi
0x180011ea7  pop     rbp
0x180011ea8  retn
```
