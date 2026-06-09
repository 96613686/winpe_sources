# MSAFD_SockThreadInitialize

- ea: `0x180005f78`
- end: `0x1800060cd`
- name: `MSAFD_SockThreadInitialize`
- size: `341`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180004480`
- `0x180004700`
- `0x180005810`
- `0x1800060e0`
- `0x180007080`
- `0x180008320`
- `0x18000c130`
- `0x18000cc50`
- `0x180030880`
- `0x18004a690`

## callees

- `0x180004558`
- `0x180005f78`
- `0x1800239e4`
- `0x180038104`
- `0x180038118`
- `0x18003ae8c`
- `0x18003aec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005fcf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005fcf`
- `ntdll!NtCreateEvent` at `0x180005fa9`
- `ntdll!NtCreateEvent` at `0x180005fa9`
- `ntdll!NtClose` at `0x180006032`
- `ntdll!NtClose` at `0x180006032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060a0`

## pseudocode

```c
__int64 MSAFD_SockThreadInitialize()
{
  NTSTATUS v0; // eax
  _QWORD *WinsockThreadData; // rax
  _QWORD *v2; // rbx
  __int64 result; // rax
  DWORD LastError; // eax
  __int64 v5; // rcx
  void *EventHandle; // [rsp+40h] [rbp+8h] BYREF

  EventHandle = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_q(1025, 42, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, NtCurrentTeb());
  v0 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
  if ( v0 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 43, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, (unsigned int)v0);
  }
  else
  {
    WinsockThreadData = (_QWORD *)AllocateWinsockThreadData();
    v2 = WinsockThreadData;
    if ( WinsockThreadData )
    {
      if ( TlsSetValue(MSAFD_SockTlsSlot, WinsockThreadData) )
      {
        v2[3] = -1;
        v2[2] = EventHandle;
        result = 1;
        *((_DWORD *)v2 + 10) = 0;
        v2[6] = 0;
        v2[7] = 0;
        return result;
      }
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_l(v5, 45, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, LastError);
      }
      FreeWinsockThreadData(v2);
    }
    else if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_(1025, 44, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids);
    }
    NtClose(EventHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x180005f78  push    rbx
0x180005f7a  sub     rsp, 30h
0x180005f7e  mov     [rsp+38h+EventHandle], 0
0x180005f87  test    byte ptr cs:xmmword_180063D60, 2
0x180005f8e  jnz     loc_180006040
0x180005f94  xor     r9d, r9d; EventType
0x180005f97  mov     [rsp+38h+InitialState], 0; InitialState
0x180005f9c  xor     r8d, r8d; ObjectAttributes
0x180005f9f  lea     rcx, [rsp+38h+EventHandle]; EventHandle
0x180005fa4  mov     edx, 1F0003h; DesiredAccess
0x180005fa9  call    cs:__imp_NtCreateEvent
0x180005fb0  nop     dword ptr [rax+rax+00h]
0x180005fb5  test    eax, eax
0x180005fb7  js      short loc_180006017
0x180005fb9  call    AllocateWinsockThreadData
0x180005fbe  mov     rbx, rax
0x180005fc1  test    rax, rax
0x180005fc4  jz      short loc_180006024
0x180005fc6  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180005fcc  mov     rdx, rax; lpTlsValue
0x180005fcf  call    cs:__imp_TlsSetValue
0x180005fd6  nop     dword ptr [rax+rax+00h]
0x180005fdb  test    eax, eax
0x180005fdd  jz      loc_180006097
0x180005fe3  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180005feb  mov     rax, [rsp+38h+EventHandle]
0x180005ff0  mov     [rbx+10h], rax
0x180005ff4  mov     eax, 1
0x180005ff9  mov     dword ptr [rbx+28h], 0
0x180006000  mov     qword ptr [rbx+30h], 0
0x180006008  mov     qword ptr [rbx+38h], 0
0x180006010  add     rsp, 30h
0x180006014  pop     rbx
0x180006015  retn
0x180006017  test    byte ptr cs:xmmword_180063D60, 2
0x18000601e  jnz     short loc_180006064
0x180006020  xor     eax, eax
0x180006022  jmp     short loc_180006010
0x180006024  test    byte ptr cs:xmmword_180063D60, 2
0x18000602b  jnz     short loc_18000607F
0x18000602d  mov     rcx, [rsp+38h+EventHandle]; Handle
0x180006032  call    cs:__imp_NtClose
0x180006039  nop     dword ptr [rax+rax+00h]
0x18000603e  jmp     short loc_180006020
0x180006040  mov     r9, gs:30h
0x180006049  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x180006050  mov     edx, 2Ah ; '*'
0x180006055  mov     ecx, 401h
0x18000605a  call    WPP_SF_q
0x18000605f  jmp     loc_180005F94
0x180006064  mov     edx, 2Bh ; '+'
0x180006069  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x180006070  mov     ecx, 401h
0x180006075  mov     r9d, eax
0x180006078  call    WPP_SF_d
0x18000607d  jmp     short loc_180006020
0x18000607f  mov     edx, 2Ch ; ','
0x180006084  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x18000608b  mov     ecx, 401h
0x180006090  call    WPP_SF_
0x180006095  jmp     short loc_18000602D
0x180006097  test    byte ptr cs:xmmword_180063D60, 2
0x18000609e  jz      short loc_1800060C0
0x1800060a0  call    cs:__imp_GetLastError
0x1800060a7  nop     dword ptr [rax+rax+00h]
0x1800060ac  mov     edx, 2Dh ; '-'
0x1800060b1  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x1800060b8  mov     r9d, eax
0x1800060bb  call    WPP_SF_l
0x1800060c0  mov     rcx, rbx
0x1800060c3  call    FreeWinsockThreadData
0x1800060c8  jmp     loc_18000602D
```
