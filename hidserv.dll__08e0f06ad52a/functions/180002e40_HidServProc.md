# HidServProc

- ea: `0x180002e40`
- end: `0x1800030cd`
- name: `HidServProc`
- size: `653`
- prototype: `LRESULT __fastcall(HWND hWnd, __int64, WPARAM, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x1800026b4`
- `0x1800027bc`
- `0x180002e40`
- `0x18000351c`
- `0x180003594`
- `0x180004a50`
- `0x180006460`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002f30`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003060`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002f30`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003060`
- `KERNEL32!CloseHandle` at `0x180002f3d`
- `KERNEL32!CloseHandle` at `0x180002f3d`
- `KERNEL32!SetEvent` at `0x180002f5d`
- `KERNEL32!SetEvent` at `0x180002f5d`
- `KERNEL32!FreeLibrary` at `0x180002eef`
- `KERNEL32!FreeLibrary` at `0x180002eef`
- `USER32!UnregisterDeviceNotification` at `0x180002efc`
- `USER32!UnregisterDeviceNotification` at `0x180002efc`
- `USER32!PostMessageW` at `0x180002f74`
- `USER32!PostMessageW` at `0x180002f74`
- `USER32!DefWindowProcW` at `0x180002f99`
- `USER32!DefWindowProcW` at `0x180002f99`

## pseudocode

```c
LRESULT __fastcall HidServProc(HWND hWnd, __int64 a2, WPARAM a3, __int64 a4)
{
  UINT v6; // esi
  __int64 v8; // rcx
  UINT v9; // edx
  SERVICE_STATUS_HANDLE v11; // rcx

  v6 = a2;
  if ( (unsigned int)a2 > 0x219 )
  {
    switch ( (_DWORD)a2 )
    {
      case 0x2B1:
        switch ( a3 )
        {
          case 1uLL:
            SessionId = a4;
            break;
          case 2uLL:
            if ( SessionId == (_DWORD)a4 )
              SessionId = 0;
            return 0;
          case 7uLL:
            if ( SessionId == (_DWORD)a4 )
              IsSessionLocked = 1;
            return 0;
          default:
            if ( a3 != 8 || SessionId != (_DWORD)a4 )
              return 0;
            break;
        }
        IsSessionLocked = 0;
        return 0;
      case 0x812D:
        HidServSetPnP(1);
        v11 = hService;
        ServiceStatus.dwControlsAccepted = 133;
        if ( !hService )
          return 0;
        ServiceStatus.dwCurrentState = 4;
        break;
      case 0x812E:
        HidServSetPnP(0);
        v11 = hService;
        ServiceStatus.dwControlsAccepted = 0;
        if ( !hService )
          return 0;
        ServiceStatus.dwCurrentState = 1;
        break;
      case 0x8136:
        if ( PnpEnabled )
          RebuildHidDeviceList((__int64)hWnd, a2, a3, a4);
        return 0;
      case 0x813A:
        HidServUpdate((unsigned int)a3, (unsigned int)a4);
        return 0;
      default:
        goto LABEL_34;
    }
    SetServiceStatus(v11, &ServiceStatus);
    return 0;
  }
  switch ( (_DWORD)a2 )
  {
    case 0x219:
      DeviceChangeHandler(a3, a4);
      v9 = 537;
      return DefWindowProcW(hWnd, v9, a3, a4);
    case 1:
      HidKeyboardSettingsChange(11);
      v9 = 1;
      return DefWindowProcW(hWnd, v9, a3, a4);
    case 0x10:
      if ( WinStaDll )
        FreeLibrary(WinStaDll);
      UnregisterDeviceNotification(hNotifyArrival);
      HidServSetPnP(0);
      ServiceStatus.dwControlsAccepted = 0;
      if ( hService )
      {
        ServiceStatus.dwCurrentState = 1;
        SetServiceStatus(hService, &ServiceStatus);
      }
      CloseHandle(hMutexOOC);
      if ( InputThreadEnabled )
      {
        InputThreadEnabled = 0;
        SetEvent(hInputEvent);
      }
      PostMessageW(hWndHidServ, 0x12u, 0, 0);
      v9 = 16;
      return DefWindowProcW(hWnd, v9, a3, a4);
    case 0x1A:
      HidKeyboardSettingsChange(a3);
LABEL_34:
      v9 = v6;
      return DefWindowProcW(hWnd, v9, a3, a4);
    case 0x113:
      VolumeTimerHandler(a3);
      return 0;
  }
  if ( (_DWORD)a2 != 536 )
    goto LABEL_34;
  if ( !(_DWORD)a3 )
    goto LABEL_15;
  if ( (_DWORD)a3 == 2 )
  {
LABEL_13:
    v8 = 1;
LABEL_16:
    HidServSetPnP(v8);
    return 0;
  }
  if ( (_DWORD)a3 != 4 )
  {
    if ( (_DWORD)a3 != 7 && (_DWORD)a3 != 18 )
      return 0;
    goto LABEL_13;
  }
  if ( PnpEnabled )
  {
LABEL_15:
    v8 = 0;
    goto LABEL_16;
  }
  return 0;
}

```

## disassembly

```asm
0x180002e40  push    rbx
0x180002e42  push    rbp
0x180002e43  push    rsi
0x180002e44  push    rdi
0x180002e45  sub     rsp, 28h
0x180002e49  mov     rdi, r9
0x180002e4c  mov     rbx, r8
0x180002e4f  mov     esi, edx
0x180002e51  mov     rbp, rcx
0x180002e54  cmp     edx, 219h
0x180002e5a  ja      loc_180002FB6
0x180002e60  jz      loc_180002FA4
0x180002e66  mov     eax, edx
0x180002e68  sub     eax, 1
0x180002e6b  jz      loc_180002F81
0x180002e71  sub     eax, 0Fh
0x180002e74  jz      short loc_180002EE3
0x180002e76  sub     eax, 0Ah
0x180002e79  jz      short loc_180002ED6
0x180002e7b  sub     eax, 0F9h
0x180002e80  jz      short loc_180002EC9
0x180002e82  cmp     eax, 105h
0x180002e87  jnz     loc_180002FD9
0x180002e8d  test    ebx, ebx
0x180002e8f  jz      short loc_180002EBD
0x180002e91  cmp     ebx, 2
0x180002e94  jz      short loc_180002EA9
0x180002e96  cmp     ebx, 4
0x180002e99  jz      short loc_180002EB0
0x180002e9b  cmp     ebx, 7
0x180002e9e  jz      short loc_180002EA9
0x180002ea0  cmp     ebx, 12h
0x180002ea3  jnz     loc_1800030C2
0x180002ea9  mov     ecx, 1
0x180002eae  jmp     short loc_180002EBF
0x180002eb0  cmp     cs:PnpEnabled, 0
0x180002eb7  jz      loc_1800030C2
0x180002ebd  xor     ecx, ecx
0x180002ebf  call    HidServSetPnP
0x180002ec4  jmp     loc_1800030C2
0x180002ec9  mov     rcx, rbx
0x180002ecc  call    VolumeTimerHandler
0x180002ed1  jmp     loc_1800030C2
0x180002ed6  mov     rcx, rbx
0x180002ed9  call    HidKeyboardSettingsChange
0x180002ede  jmp     loc_180002FD9
0x180002ee3  mov     rcx, cs:WinStaDll; hLibModule
0x180002eea  test    rcx, rcx
0x180002eed  jz      short loc_180002EF5
0x180002eef  call    cs:__imp_FreeLibrary
0x180002ef5  mov     rcx, cs:hNotifyArrival; Handle
0x180002efc  call    cs:__imp_UnregisterDeviceNotification
0x180002f02  xor     ecx, ecx
0x180002f04  call    HidServSetPnP
0x180002f09  mov     rcx, cs:hService; hServiceStatus
0x180002f10  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x180002f1a  test    rcx, rcx
0x180002f1d  jz      short loc_180002F36
0x180002f1f  lea     rdx, ServiceStatus; lpServiceStatus
0x180002f26  mov     cs:ServiceStatus.dwCurrentState, 1
0x180002f30  call    cs:__imp_SetServiceStatus
0x180002f36  mov     rcx, cs:hMutexOOC; hObject
0x180002f3d  call    cs:__imp_CloseHandle
0x180002f43  cmp     cs:InputThreadEnabled, 0
0x180002f4a  jz      short loc_180002F63
0x180002f4c  mov     rcx, cs:hInputEvent; hEvent
0x180002f53  mov     cs:InputThreadEnabled, 0
0x180002f5d  call    cs:__imp_SetEvent
0x180002f63  mov     rcx, cs:hWndHidServ; hWnd
0x180002f6a  xor     r9d, r9d; lParam
0x180002f6d  xor     r8d, r8d; wParam
0x180002f70  lea     edx, [r9+12h]; Msg
0x180002f74  call    cs:__imp_PostMessageW
0x180002f7a  mov     edx, 10h
0x180002f7f  jmp     short loc_180002F90
0x180002f81  mov     ecx, 0Bh
0x180002f86  call    HidKeyboardSettingsChange
0x180002f8b  mov     edx, 1; Msg
0x180002f90  mov     r8, rbx; wParam
0x180002f93  mov     r9, rdi; lParam
0x180002f96  mov     rcx, rbp; hWnd
0x180002f99  call    cs:__imp_DefWindowProcW
0x180002f9f  jmp     loc_1800030C4
0x180002fa4  mov     rdx, rdi
0x180002fa7  mov     rcx, rbx
0x180002faa  call    DeviceChangeHandler
0x180002faf  mov     edx, 219h
0x180002fb4  jmp     short loc_180002F90
0x180002fb6  mov     eax, esi
0x180002fb8  sub     eax, 2B1h
0x180002fbd  jz      loc_180003068
0x180002fc3  sub     eax, 7E7Ch
0x180002fc8  jz      short loc_18000302F
0x180002fca  sub     eax, 1
0x180002fcd  jz      short loc_180003002
0x180002fcf  sub     eax, 8
0x180002fd2  jz      short loc_180002FEB
0x180002fd4  cmp     eax, 4
0x180002fd7  jz      short loc_180002FDD
0x180002fd9  mov     edx, esi
0x180002fdb  jmp     short loc_180002F90
0x180002fdd  mov     edx, edi
0x180002fdf  mov     ecx, ebx
0x180002fe1  call    HidServUpdate
0x180002fe6  jmp     loc_1800030C2
0x180002feb  cmp     cs:PnpEnabled, 0
0x180002ff2  jz      loc_1800030C2
0x180002ff8  call    RebuildHidDeviceList
0x180002ffd  jmp     loc_1800030C2
0x180003002  xor     ecx, ecx
0x180003004  call    HidServSetPnP
0x180003009  mov     rcx, cs:hService
0x180003010  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18000301a  test    rcx, rcx
0x18000301d  jz      loc_1800030C2
0x180003023  mov     cs:ServiceStatus.dwCurrentState, 1
0x18000302d  jmp     short loc_180003059
0x18000302f  mov     ecx, 1
0x180003034  call    HidServSetPnP
0x180003039  mov     rcx, cs:hService; hServiceStatus
0x180003040  mov     cs:ServiceStatus.dwControlsAccepted, 85h
0x18000304a  test    rcx, rcx
0x18000304d  jz      short loc_1800030C2
0x18000304f  mov     cs:ServiceStatus.dwCurrentState, 4
0x180003059  lea     rdx, ServiceStatus; lpServiceStatus
0x180003060  call    cs:__imp_SetServiceStatus
0x180003066  jmp     short loc_1800030C2
0x180003068  sub     rbx, 1
0x18000306c  jz      short loc_1800030B2
0x18000306e  sub     rbx, 1
0x180003072  jz      short loc_18000309E
0x180003074  sub     rbx, 5
0x180003078  jz      short loc_18000308A
0x18000307a  cmp     rbx, 1
0x18000307e  jnz     short loc_1800030C2
0x180003080  cmp     cs:SessionId, edi
0x180003086  jnz     short loc_1800030C2
0x180003088  jmp     short loc_1800030B8
0x18000308a  cmp     cs:SessionId, edi
0x180003090  jnz     short loc_1800030C2
0x180003092  mov     cs:IsSessionLocked, 1
0x18000309c  jmp     short loc_1800030C2
0x18000309e  cmp     cs:SessionId, edi
0x1800030a4  jnz     short loc_1800030C2
0x1800030a6  mov     cs:SessionId, 0
0x1800030b0  jmp     short loc_1800030C2
0x1800030b2  mov     cs:SessionId, edi
0x1800030b8  mov     cs:IsSessionLocked, 0
0x1800030c2  xor     eax, eax
0x1800030c4  add     rsp, 28h
0x1800030c8  pop     rdi
0x1800030c9  pop     rsi
0x1800030ca  pop     rbp
0x1800030cb  pop     rbx
0x1800030cc  retn
```
