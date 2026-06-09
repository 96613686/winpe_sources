# InitializeFiniteStateMachine

- ea: `0x1800ad008`
- end: `0x1800ad17c`
- name: `InitializeFiniteStateMachine`
- size: `372`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800a032c`

## callees

- `0x180002854`
- `0x18001ceb4`
- `0x1800acf1c`
- `0x1800ad008`

## import_xrefs

- `msvcrt!printf` at `0x1800ad0b9`
- `msvcrt!printf` at `0x1800ad0b9`
- `WS2_32!WSACloseEvent` at `0x1800ad12f`
- `WS2_32!WSACloseEvent` at `0x1800ad12f`
- `WS2_32!WSACreateEvent` at `0x1800ad029`
- `WS2_32!WSACreateEvent` at `0x1800ad029`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ad041`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ad0e1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ad13f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ad041`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ad0e1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ad13f`
- `KERNEL32!WaitForSingleObject` at `0x1800ad0d1`
- `KERNEL32!WaitForSingleObject` at `0x1800ad0d1`
- `KERNEL32!CreateThread` at `0x1800ad08a`
- `KERNEL32!CreateThread` at `0x1800ad08a`
- `KERNEL32!GetLastError` at `0x1800ad0a2`
- `KERNEL32!GetLastError` at `0x1800ad0a2`

## string_xrefs

- `0x1800ad053`: `WSACreateEvent`
- `0x1800ad151`: `WSACloseEvent`
- `0x1800ad0b0`: `CreateThread(RaiseEventsInLoop): %ld\n`

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
0x1800ad008  mov     [rsp+arg_0], rbx
0x1800ad00d  push    rdi
0x1800ad00e  sub     rsp, 30h
0x1800ad012  xor     ebx, ebx
0x1800ad014  mov     rdi, rcx
0x1800ad017  test    rcx, rcx
0x1800ad01a  jnz     short loc_1800AD024
0x1800ad01c  lea     eax, [rcx+57h]
0x1800ad01f  jmp     loc_1800AD170
0x1800ad024  call    InitializeFOHandlesAndEvents
0x1800ad029  call    cs:__imp_WSACreateEvent
0x1800ad030  nop     dword ptr [rax+rax+00h]
0x1800ad035  mov     cs:gFsmInitEvent, rax
0x1800ad03c  test    rax, rax
0x1800ad03f  jnz     short loc_1800AD06F
0x1800ad041  call    cs:__imp_WSAGetLastError
0x1800ad048  nop     dword ptr [rax+rax+00h]
0x1800ad04d  mov     r9d, 1360h
0x1800ad053  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800ad05a  mov     ecx, eax
0x1800ad05c  lea     rdx, aInitializefini; "InitializeFiniteStateMachine"
0x1800ad063  mov     ebx, eax
0x1800ad065  call    DhcpPrintFOErrorEx
0x1800ad06a  jmp     loc_1800AD123
0x1800ad06f  lea     rax, [rdi+44h]
0x1800ad073  mov     r9, rdi; lpParameter
0x1800ad076  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800ad07b  lea     r8, FiniteStateMachine; lpStartAddress
0x1800ad082  and     [rsp+38h+var_18], ebx
0x1800ad086  xor     edx, edx; dwStackSize
0x1800ad088  xor     ecx, ecx; lpThreadAttributes
0x1800ad08a  call    cs:__imp_CreateThread
0x1800ad091  nop     dword ptr [rax+rax+00h]
0x1800ad096  mov     [rdi+0E0h], rax
0x1800ad09d  test    rax, rax
0x1800ad0a0  jnz     short loc_1800AD0C7
0x1800ad0a2  call    cs:__imp_GetLastError
0x1800ad0a9  nop     dword ptr [rax+rax+00h]
0x1800ad0ae  mov     edx, eax
0x1800ad0b0  lea     rcx, aCreatethreadRa; "CreateThread(RaiseEventsInLoop): %ld\n"
0x1800ad0b7  mov     ebx, eax
0x1800ad0b9  call    cs:__imp_printf
0x1800ad0c0  nop     dword ptr [rax+rax+00h]
0x1800ad0c5  jmp     short loc_1800AD123
0x1800ad0c7  mov     rcx, cs:gFsmInitEvent; hHandle
0x1800ad0ce  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800ad0d1  call    cs:__imp_WaitForSingleObject
0x1800ad0d8  nop     dword ptr [rax+rax+00h]
0x1800ad0dd  test    eax, eax
0x1800ad0df  jz      short loc_1800AD123
0x1800ad0e1  call    cs:__imp_WSAGetLastError
0x1800ad0e8  nop     dword ptr [rax+rax+00h]
0x1800ad0ed  mov     ebx, eax
0x1800ad0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad0f6  lea     rax, WPP_GLOBAL_Control
0x1800ad0fd  cmp     rcx, rax
0x1800ad100  jz      short loc_1800AD123
0x1800ad102  test    dword ptr [rcx+1Ch], 800000h
0x1800ad109  jz      short loc_1800AD123
0x1800ad10b  mov     rcx, [rcx+10h]
0x1800ad10f  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800ad116  mov     edx, 0D2h
0x1800ad11b  mov     r9d, ebx
0x1800ad11e  call    WPP_SF_D
0x1800ad123  mov     rcx, cs:gFsmInitEvent; hEvent
0x1800ad12a  test    rcx, rcx
0x1800ad12d  jz      short loc_1800AD16E
0x1800ad12f  call    cs:__imp_WSACloseEvent
0x1800ad136  nop     dword ptr [rax+rax+00h]
0x1800ad13b  test    eax, eax
0x1800ad13d  jnz     short loc_1800AD166
0x1800ad13f  call    cs:__imp_WSAGetLastError
0x1800ad146  nop     dword ptr [rax+rax+00h]
0x1800ad14b  mov     r9d, 1379h
0x1800ad151  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ad158  mov     ecx, eax
0x1800ad15a  lea     rdx, aInitializefini; "InitializeFiniteStateMachine"
0x1800ad161  call    DhcpPrintFOErrorEx
0x1800ad166  and     cs:gFsmInitEvent, 0
0x1800ad16e  mov     eax, ebx
0x1800ad170  mov     rbx, [rsp+38h+arg_0]
0x1800ad175  add     rsp, 30h
0x1800ad179  pop     rdi
0x1800ad17a  retn
```
