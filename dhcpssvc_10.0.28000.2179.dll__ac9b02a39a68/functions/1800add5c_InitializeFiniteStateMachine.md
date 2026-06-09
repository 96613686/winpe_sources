# InitializeFiniteStateMachine

- ea: `0x1800add5c`
- end: `0x1800aded3`
- name: `InitializeFiniteStateMachine`
- size: `375`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800a1004`

## callees

- `0x18000282c`
- `0x18001c45c`
- `0x1800adc70`
- `0x1800add5c`

## import_xrefs

- `msvcrt!printf` at `0x1800ade0d`
- `msvcrt!printf` at `0x1800ade0d`
- `WS2_32!WSACloseEvent` at `0x1800ade83`
- `WS2_32!WSACloseEvent` at `0x1800ade83`
- `WS2_32!WSACreateEvent` at `0x1800add7d`
- `WS2_32!WSACreateEvent` at `0x1800add7d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800add95`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ade35`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ade93`
- `WS2_32!__imp_WSAGetLastError` at `0x1800add95`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ade35`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ade93`
- `KERNEL32!WaitForSingleObject` at `0x1800ade25`
- `KERNEL32!WaitForSingleObject` at `0x1800ade25`
- `KERNEL32!GetLastError` at `0x1800addf6`
- `KERNEL32!GetLastError` at `0x1800addf6`
- `KERNEL32!CreateThread` at `0x1800addde`
- `KERNEL32!CreateThread` at `0x1800addde`

## string_xrefs

- `0x1800adda7`: `WSACreateEvent`
- `0x1800adea5`: `WSACloseEvent`
- `0x1800ade04`: `CreateThread(RaiseEventsInLoop): %ld\n`

## pseudocode

```c
__int64 __fastcall InitializeFiniteStateMachine(DWORD *lpParameter)
{
  DWORD Error; // ebx
  HANDLE Thread; // rax
  unsigned int v5; // eax

  Error = 0;
  if ( !lpParameter )
    return 87;
  InitializeFOHandlesAndEvents();
  gFsmInitEvent = WSACreateEvent();
  if ( gFsmInitEvent )
  {
    Thread = CreateThread(0, 0, FiniteStateMachine, lpParameter, 0, lpParameter + 17);
    *((_QWORD *)lpParameter + 28) = Thread;
    if ( Thread )
    {
      if ( WaitForSingleObject(gFsmInitEvent, 0xFFFFFFFF) )
      {
        Error = WSAGetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids, Error);
        }
      }
    }
    else
    {
      Error = GetLastError();
      printf("CreateThread(RaiseEventsInLoop): %ld\n", Error);
    }
  }
  else
  {
    Error = WSAGetLastError();
    DhcpPrintFOErrorEx(Error, "InitializeFiniteStateMachine", "WSACreateEvent", 4960);
  }
  if ( gFsmInitEvent )
  {
    if ( !WSACloseEvent(gFsmInitEvent) )
    {
      v5 = WSAGetLastError();
      DhcpPrintFOErrorEx(v5, "InitializeFiniteStateMachine", "WSACloseEvent", 4985);
    }
    gFsmInitEvent = 0;
  }
  return Error;
}

```

## disassembly

```asm
0x1800add5c  mov     [rsp+arg_0], rbx
0x1800add61  push    rdi
0x1800add62  sub     rsp, 30h
0x1800add66  xor     ebx, ebx
0x1800add68  mov     rdi, rcx
0x1800add6b  test    rcx, rcx
0x1800add6e  jnz     short loc_1800ADD78
0x1800add70  lea     eax, [rcx+57h]
0x1800add73  jmp     loc_1800ADEC7
0x1800add78  call    InitializeFOHandlesAndEvents
0x1800add7d  call    cs:__imp_WSACreateEvent
0x1800add84  nop     dword ptr [rax+rax+00h]
0x1800add89  mov     cs:gFsmInitEvent, rax
0x1800add90  test    rax, rax
0x1800add93  jnz     short loc_1800ADDC3
0x1800add95  call    cs:__imp_WSAGetLastError
0x1800add9c  nop     dword ptr [rax+rax+00h]
0x1800adda1  mov     r9d, 1360h
0x1800adda7  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800addae  mov     ecx, eax
0x1800addb0  lea     rdx, aInitializefini; "InitializeFiniteStateMachine"
0x1800addb7  mov     ebx, eax
0x1800addb9  call    DhcpPrintFOErrorEx
0x1800addbe  jmp     loc_1800ADE77
0x1800addc3  lea     rax, [rdi+44h]
0x1800addc7  mov     r9, rdi; lpParameter
0x1800addca  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800addcf  lea     r8, FiniteStateMachine; lpStartAddress
0x1800addd6  xor     edx, edx; dwStackSize
0x1800addd8  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1800adddc  xor     ecx, ecx; lpThreadAttributes
0x1800addde  call    cs:__imp_CreateThread
0x1800adde5  nop     dword ptr [rax+rax+00h]
0x1800addea  mov     [rdi+0E0h], rax
0x1800addf1  test    rax, rax
0x1800addf4  jnz     short loc_1800ADE1B
0x1800addf6  call    cs:__imp_GetLastError
0x1800addfd  nop     dword ptr [rax+rax+00h]
0x1800ade02  mov     edx, eax
0x1800ade04  lea     rcx, aCreatethreadRa; "CreateThread(RaiseEventsInLoop): %ld\n"
0x1800ade0b  mov     ebx, eax
0x1800ade0d  call    cs:__imp_printf
0x1800ade14  nop     dword ptr [rax+rax+00h]
0x1800ade19  jmp     short loc_1800ADE77
0x1800ade1b  mov     rcx, cs:gFsmInitEvent; hHandle
0x1800ade22  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800ade25  call    cs:__imp_WaitForSingleObject
0x1800ade2c  nop     dword ptr [rax+rax+00h]
0x1800ade31  test    eax, eax
0x1800ade33  jz      short loc_1800ADE77
0x1800ade35  call    cs:__imp_WSAGetLastError
0x1800ade3c  nop     dword ptr [rax+rax+00h]
0x1800ade41  mov     ebx, eax
0x1800ade43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ade4a  lea     rax, WPP_GLOBAL_Control
0x1800ade51  cmp     rcx, rax
0x1800ade54  jz      short loc_1800ADE77
0x1800ade56  test    dword ptr [rcx+1Ch], 800000h
0x1800ade5d  jz      short loc_1800ADE77
0x1800ade5f  mov     rcx, [rcx+10h]
0x1800ade63  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800ade6a  mov     edx, 0D2h
0x1800ade6f  mov     r9d, ebx
0x1800ade72  call    WPP_SF_D
0x1800ade77  mov     rcx, cs:gFsmInitEvent; hEvent
0x1800ade7e  test    rcx, rcx
0x1800ade81  jz      short loc_1800ADEC5
0x1800ade83  call    cs:__imp_WSACloseEvent
0x1800ade8a  nop     dword ptr [rax+rax+00h]
0x1800ade8f  test    eax, eax
0x1800ade91  jnz     short loc_1800ADEBA
0x1800ade93  call    cs:__imp_WSAGetLastError
0x1800ade9a  nop     dword ptr [rax+rax+00h]
0x1800ade9f  mov     r9d, 1379h
0x1800adea5  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800adeac  mov     ecx, eax
0x1800adeae  lea     rdx, aInitializefini; "InitializeFiniteStateMachine"
0x1800adeb5  call    DhcpPrintFOErrorEx
0x1800adeba  mov     cs:gFsmInitEvent, 0
0x1800adec5  mov     eax, ebx
0x1800adec7  mov     rbx, [rsp+38h+arg_0]
0x1800adecc  add     rsp, 30h
0x1800aded0  pop     rdi
0x1800aded1  retn
```
