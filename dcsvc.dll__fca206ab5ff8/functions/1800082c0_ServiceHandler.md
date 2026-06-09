# ServiceHandler

- ea: `0x1800082c0`
- end: `0x180008385`
- name: `ServiceHandler`
- size: `197`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, __int64 lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001cf0`
- `0x1800082c0`
- `0x18000947c`
- `0x18000a850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000835f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000835f`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, __int64 lpEventData, LPVOID lpContext)
{
  unsigned int v4; // edi
  DWORD v6; // ebx
  DWORD v8; // [rsp+30h] [rbp-58h] BYREF
  DWORD dwCurrentState; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-48h] BYREF
  DWORD *v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  DWORD *p_dwCurrentState; // [rsp+60h] [rbp-28h]
  __int64 v14; // [rsp+68h] [rbp-20h]

  v4 = 0;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
  {
    dwCurrentState = ServiceStatus.dwCurrentState;
    v8 = dwControl;
    v11 = &v8;
    p_dwCurrentState = &dwCurrentState;
    v12 = 4;
    v14 = 4;
    McGenEventWrite_EventWriteTransfer(
      4,
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticDcSvcServiceHandlerInvoked,
      lpEventData,
      3u,
      &v10);
  }
  v6 = dwControl - 1;
  if ( v6 )
  {
    if ( v6 == 31 && ServiceStatus.dwCurrentState == 3 )
      return 1115;
  }
  else
  {
    SvcEngUpdateServiceStatus(3, 0, 0);
    if ( hEvent )
      SetEvent(hEvent);
  }
  return v4;
}

```

## disassembly

```asm
0x1800082c0  mov     r11, rsp
0x1800082c3  mov     [r11+8], rbx
0x1800082c7  push    rdi
0x1800082c8  sub     rsp, 80h
0x1800082cf  mov     rax, cs:__security_cookie
0x1800082d6  xor     rax, rsp
0x1800082d9  mov     [rsp+88h+var_18], rax
0x1800082de  xor     edi, edi
0x1800082e0  mov     ebx, ecx
0x1800082e2  lea     ecx, [rdi+4]
0x1800082e5  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, cl
0x1800082eb  jz      short loc_18000832B
0x1800082ed  mov     eax, cs:ServiceStatus.dwCurrentState
0x1800082f3  lea     r9d, [rdi+3]
0x1800082f7  mov     [rsp+88h+var_50], eax
0x1800082fb  lea     rdx, EnterpriseDiagnosticDcSvcServiceHandlerInvoked
0x180008302  lea     rax, [r11-58h]
0x180008306  mov     [rsp+88h+var_58], ebx
0x18000830a  mov     [r11-38h], rax
0x18000830e  lea     rax, [r11-50h]
0x180008312  mov     [r11-28h], rax
0x180008316  lea     rax, [r11-48h]
0x18000831a  mov     [r11-68h], rax
0x18000831e  mov     [r11-30h], rcx
0x180008322  mov     [r11-20h], rcx
0x180008326  call    McGenEventWrite_EventWriteTransfer
0x18000832b  sub     ebx, 1
0x18000832e  jz      short loc_180008346
0x180008330  cmp     ebx, 1Fh
0x180008333  jnz     short loc_180008365
0x180008335  cmp     cs:ServiceStatus.dwCurrentState, 3
0x18000833c  mov     eax, 45Bh
0x180008341  cmovz   edi, eax
0x180008344  jmp     short loc_180008365
0x180008346  xor     edx, edx; unsigned int
0x180008348  xor     r8d, r8d; unsigned int
0x18000834b  lea     ecx, [rdx+3]; unsigned int
0x18000834e  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180008353  mov     rcx, cs:hEvent; hEvent
0x18000835a  test    rcx, rcx
0x18000835d  jz      short loc_180008365
0x18000835f  call    cs:__imp_SetEvent
0x180008365  mov     eax, edi
0x180008367  mov     rcx, [rsp+88h+var_18]
0x18000836c  xor     rcx, rsp; StackCookie
0x18000836f  call    __security_check_cookie
0x180008374  mov     rbx, [rsp+88h+arg_0]
0x18000837c  add     rsp, 80h
0x180008383  pop     rdi
0x180008384  retn
```
