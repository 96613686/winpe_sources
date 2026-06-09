# ServiceControlHandler

- ea: `0x18000e930`
- end: `0x18000eaf5`
- name: `ServiceControlHandler`
- size: `453`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009580`
- `0x18000e930`
- `0x18000eafc`
- `0x18001cef0`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea91`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ea7e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ea7e`

## pseudocode

```c
__int64 __fastcall ServiceControlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx
  int v8; // ecx
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD LastError; // eax
  char v13[16]; // [rsp+30h] [rbp-28h] BYREF

  v4 = 0;
  v5 = dwControl - 1;
  if ( !v5 )
  {
LABEL_17:
    if ( !DhcpGlobalIsShuttingDown && (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 13, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
    goto LABEL_20;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    DhcpGlobalServiceStatus.dwCurrentState = 7;
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_7;
    v10 = 16;
LABEL_10:
    v11 = 1028;
    goto LABEL_11;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    DhcpGlobalServiceStatus.dwCurrentState = 4;
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_7;
    v10 = 17;
    goto LABEL_10;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_7;
    v10 = 18;
    goto LABEL_10;
  }
  if ( v8 != 1 )
  {
    v4 = 120;
    if ( (xmmword_1800616A0 & 2) == 0 )
    {
LABEL_7:
      UpdateStatus();
      return v4;
    }
    v10 = 19;
    v11 = 1025;
LABEL_11:
    WPP_SF_(v11, v10, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
    goto LABEL_7;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 12, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  DhcpGlobalIsShuttingDown = 1;
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(
      v8,
      (unsigned int)ServiceReceivesShutdownNotification,
      (_DWORD)lpEventData,
      1,
      (__int64)v13);
    goto LABEL_17;
  }
LABEL_20:
  if ( DhcpGlobalServiceStatus.dwCurrentState != 4 )
    goto LABEL_7;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 14, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  DhcpGlobalServiceStatus.dwCurrentState = 3;
  DhcpGlobalServiceStatus.dwCheckPoint = 0;
  UpdateStatus();
  if ( !SetEvent(DhcpGlobalTerminateEvent) && (xmmword_1800616A0 & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_D(1025, 15, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e930  mov     [rsp+arg_0], rbx
0x18000e935  mov     [rsp+arg_8], rbp
0x18000e93a  push    rsi
0x18000e93b  sub     rsp, 50h
0x18000e93f  mov     rax, cs:__security_cookie
0x18000e946  xor     rax, rsp
0x18000e949  mov     [rsp+58h+var_18], rax
0x18000e94e  xor     ebx, ebx
0x18000e950  lea     rsi, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18000e957  mov     ebp, 404h
0x18000e95c  sub     ecx, 1
0x18000e95f  jz      loc_18000EA1D
0x18000e965  sub     ecx, 1
0x18000e968  jz      loc_18000EAD4
0x18000e96e  sub     ecx, 1
0x18000e971  jz      loc_18000EAB3
0x18000e977  sub     ecx, 1
0x18000e97a  jz      short loc_18000E9B3
0x18000e97c  cmp     ecx, 1
0x18000e97f  jz      short loc_18000E9D9
0x18000e981  mov     ebx, 78h ; 'x'
0x18000e986  test    byte ptr cs:xmmword_1800616A0, 2
0x18000e98d  jnz     short loc_18000E9CD
0x18000e98f  call    UpdateStatus
0x18000e994  mov     eax, ebx
0x18000e996  mov     rcx, [rsp+58h+var_18]
0x18000e99b  xor     rcx, rsp; StackCookie
0x18000e99e  call    __security_check_cookie
0x18000e9a3  mov     rbx, [rsp+58h+arg_0]
0x18000e9a8  mov     rbp, [rsp+58h+arg_8]
0x18000e9ad  add     rsp, 50h
0x18000e9b1  pop     rsi
0x18000e9b2  retn
0x18000e9b3  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000e9ba  jz      short loc_18000E98F
0x18000e9bc  mov     edx, 12h
0x18000e9c1  mov     ecx, ebp
0x18000e9c3  mov     r8, rsi
0x18000e9c6  call    WPP_SF_
0x18000e9cb  jmp     short loc_18000E98F
0x18000e9cd  mov     edx, 13h
0x18000e9d2  mov     ecx, 401h
0x18000e9d7  jmp     short loc_18000E9C3
0x18000e9d9  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000e9e0  jz      short loc_18000E9F1
0x18000e9e2  mov     edx, 0Ch
0x18000e9e7  mov     ecx, ebp
0x18000e9e9  mov     r8, rsi
0x18000e9ec  call    WPP_SF_
0x18000e9f1  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 20h
0x18000e9f8  mov     r9d, 1
0x18000e9fe  mov     cs:DhcpGlobalIsShuttingDown, r9d
0x18000ea05  jz      short loc_18000EA3D
0x18000ea07  lea     rax, [rsp+58h+var_28]
0x18000ea0c  lea     rdx, ServiceReceivesShutdownNotification
0x18000ea13  mov     [rsp+58h+var_38], rax
0x18000ea18  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ea1d  cmp     cs:DhcpGlobalIsShuttingDown, ebx
0x18000ea23  jnz     short loc_18000EA3D
0x18000ea25  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000ea2c  jz      short loc_18000EA3D
0x18000ea2e  mov     edx, 0Dh
0x18000ea33  mov     ecx, ebp
0x18000ea35  mov     r8, rsi
0x18000ea38  call    WPP_SF_
0x18000ea3d  cmp     cs:DhcpGlobalServiceStatus.dwCurrentState, 4
0x18000ea44  jnz     loc_18000E98F
0x18000ea4a  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000ea51  jz      short loc_18000EA62
0x18000ea53  mov     edx, 0Eh
0x18000ea58  mov     ecx, ebp
0x18000ea5a  mov     r8, rsi
0x18000ea5d  call    WPP_SF_
0x18000ea62  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 3
0x18000ea6c  mov     cs:DhcpGlobalServiceStatus.dwCheckPoint, ebx
0x18000ea72  call    UpdateStatus
0x18000ea77  mov     rcx, cs:DhcpGlobalTerminateEvent; hEvent
0x18000ea7e  call    cs:__imp_SetEvent
0x18000ea84  test    eax, eax
0x18000ea86  jnz     short loc_18000EAAC
0x18000ea88  test    byte ptr cs:xmmword_1800616A0, 2
0x18000ea8f  jz      short loc_18000EAAC
0x18000ea91  call    cs:__imp_GetLastError
0x18000ea97  mov     edx, 0Fh
0x18000ea9c  mov     ecx, 401h
0x18000eaa1  mov     r9d, eax
0x18000eaa4  mov     r8, rsi
0x18000eaa7  call    WPP_SF_D
0x18000eaac  xor     eax, eax
0x18000eaae  jmp     loc_18000E996
0x18000eab3  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 4
0x18000eabd  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000eac4  jz      loc_18000E98F
0x18000eaca  mov     edx, 11h
0x18000eacf  jmp     loc_18000E9C1
0x18000ead4  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 7
0x18000eade  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000eae5  jz      loc_18000E98F
0x18000eaeb  mov     edx, 10h
0x18000eaf0  jmp     loc_18000E9C1
```
