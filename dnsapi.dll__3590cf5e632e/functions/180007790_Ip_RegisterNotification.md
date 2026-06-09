# Ip_RegisterNotification

- ea: `0x180007790`
- end: `0x180007990`
- name: `Ip_RegisterNotification`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000673c`

## callees

- `0x180007790`
- `0x18008b5f0`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000790b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000792b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000790b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000792b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000788f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000788f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007832`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007832`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800077e4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800077e4`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180007863`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180007863`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180007967`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180007967`

## pseudocode

```c
__int64 Ip_RegisterNotification()
{
  DWORD LastError; // ebx
  HANDLE EventW; // rdi
  unsigned int v3; // eax
  DWORD v4; // eax
  HANDLE NotificationHandle; // [rsp+30h] [rbp-48h] BYREF
  HMODULE phModule; // [rsp+38h] [rbp-40h] BYREF

  LastError = 0;
  NotificationHandle = 0;
  phModule = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 35, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids);
  if ( g_DnsIsCache )
    goto LABEL_6;
  if ( g_hAddressChange )
  {
    ResetEvent(g_hAddressChange);
    goto LABEL_6;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
LABEL_6:
    if ( NotificationHandle )
      CancelMibChangeNotify2(NotificationHandle);
    goto LABEL_8;
  }
  v3 = NotifyUnicastIpAddressChange(0, Ip_NotifyAddressChange, 0, 0, &NotificationHandle);
  LastError = v3;
  if ( v3 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 36, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, v3);
    CloseHandle(EventW);
    goto LABEL_6;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 37, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids);
  if ( !GetModuleHandleExW(5u, (LPCWSTR)Ip_RegisterNotification, &phModule) && (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v4 = GetLastError();
    WPP_SF_d(1035, 38, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, v4);
  }
  g_hAddressNotify = NotificationHandle;
  g_hAddressChange = EventW;
  NotificationHandle = 0;
LABEL_8:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 39, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180007790  push    rbx
0x180007792  push    rdi
0x180007793  push    r14
0x180007795  push    r15
0x180007797  sub     rsp, 58h
0x18000779b  mov     rax, cs:__security_cookie
0x1800077a2  xor     rax, rsp
0x1800077a5  mov     [rsp+78h+var_38], rax
0x1800077aa  xor     ebx, ebx
0x1800077ac  mov     [rsp+78h+var_48], rbx
0x1800077b1  mov     [rsp+78h+phModule], rbx
0x1800077b6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800077bd  lea     r15, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x1800077c4  mov     r14d, 40Bh
0x1800077ca  jnz     loc_1800078E1
0x1800077d0  cmp     cs:g_DnsIsCache, ebx
0x1800077d6  jnz     short loc_1800077F0
0x1800077d8  mov     rcx, cs:g_hAddressChange; hEvent
0x1800077df  test    rcx, rcx
0x1800077e2  jz      short loc_180007826
0x1800077e4  call    cs:__imp_ResetEvent
0x1800077eb  nop     dword ptr [rax+rax+00h]
0x1800077f0  mov     rcx, [rsp+78h+var_48]; NotificationHandle
0x1800077f5  test    rcx, rcx
0x1800077f8  jnz     loc_180007967
0x1800077fe  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180007805  jnz     loc_180007978
0x18000780b  mov     eax, ebx
0x18000780d  mov     rcx, [rsp+78h+var_38]
0x180007812  xor     rcx, rsp; StackCookie
0x180007815  call    __security_check_cookie
0x18000781a  add     rsp, 58h
0x18000781e  pop     r15
0x180007820  pop     r14
0x180007822  pop     rdi
0x180007823  pop     rbx
0x180007824  retn
0x180007826  xor     r9d, r9d; lpName
0x180007829  xor     r8d, r8d; bInitialState
0x18000782c  xor     ecx, ecx; lpEventAttributes
0x18000782e  lea     edx, [r9+1]; bManualReset
0x180007832  call    cs:__imp_CreateEventW
0x180007839  nop     dword ptr [rax+rax+00h]
0x18000783e  mov     rdi, rax
0x180007841  test    rax, rax
0x180007844  jz      loc_18000790B
0x18000784a  lea     rax, [rsp+78h+var_48]
0x18000784f  xor     ecx, ecx; Family
0x180007851  xor     r9d, r9d; InitialNotification
0x180007854  mov     [rsp+78h+NotificationHandle], rax; NotificationHandle
0x180007859  xor     r8d, r8d; CallerContext
0x18000785c  lea     rdx, Ip_NotifyAddressChange; Callback
0x180007863  call    cs:__imp_NotifyUnicastIpAddressChange
0x18000786a  nop     dword ptr [rax+rax+00h]
0x18000786f  mov     ebx, eax
0x180007871  test    eax, eax
0x180007873  jnz     short loc_1800078C0
0x180007875  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000787c  jnz     short loc_1800078F6
0x18000787e  lea     r8, [rsp+78h+phModule]; phModule
0x180007883  mov     ecx, 5; dwFlags
0x180007888  lea     rdx, Ip_RegisterNotification; lpModuleName
0x18000788f  call    cs:__imp_GetModuleHandleExW
0x180007896  nop     dword ptr [rax+rax+00h]
0x18000789b  test    eax, eax
0x18000789d  jz      short loc_18000791E
0x18000789f  mov     rax, [rsp+78h+var_48]
0x1800078a4  mov     cs:g_hAddressNotify, rax
0x1800078ab  mov     cs:g_hAddressChange, rdi
0x1800078b2  mov     [rsp+78h+var_48], 0
0x1800078bb  jmp     loc_1800077FE
0x1800078c0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800078c7  jnz     loc_18000794F
0x1800078cd  mov     rcx, rdi; hObject
0x1800078d0  call    cs:__imp_CloseHandle
0x1800078d7  nop     dword ptr [rax+rax+00h]
0x1800078dc  jmp     loc_1800077F0
0x1800078e1  mov     edx, 23h ; '#'
0x1800078e6  mov     ecx, r14d
0x1800078e9  mov     r8, r15
0x1800078ec  call    WPP_SF_
0x1800078f1  jmp     loc_1800077D0
0x1800078f6  mov     edx, 25h ; '%'
0x1800078fb  mov     ecx, r14d
0x1800078fe  mov     r8, r15
0x180007901  call    WPP_SF_
0x180007906  jmp     loc_18000787E
0x18000790b  call    cs:__imp_GetLastError
0x180007912  nop     dword ptr [rax+rax+00h]
0x180007917  mov     ebx, eax
0x180007919  jmp     loc_1800077F0
0x18000791e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180007925  jz      loc_18000789F
0x18000792b  call    cs:__imp_GetLastError
0x180007932  nop     dword ptr [rax+rax+00h]
0x180007937  mov     edx, 26h ; '&'
0x18000793c  mov     ecx, r14d
0x18000793f  mov     r9d, eax
0x180007942  mov     r8, r15
0x180007945  call    WPP_SF_d
0x18000794a  jmp     loc_18000789F
0x18000794f  mov     edx, 24h ; '$'
0x180007954  mov     ecx, r14d
0x180007957  mov     r9d, eax
0x18000795a  mov     r8, r15
0x18000795d  call    WPP_SF_d
0x180007962  jmp     loc_1800078CD
0x180007967  call    cs:__imp_CancelMibChangeNotify2
0x18000796e  nop     dword ptr [rax+rax+00h]
0x180007973  jmp     loc_1800077FE
0x180007978  mov     edx, 27h ; '''
0x18000797d  mov     ecx, r14d
0x180007980  mov     r9d, ebx
0x180007983  mov     r8, r15
0x180007986  call    WPP_SF_d
0x18000798b  jmp     loc_18000780B
```
