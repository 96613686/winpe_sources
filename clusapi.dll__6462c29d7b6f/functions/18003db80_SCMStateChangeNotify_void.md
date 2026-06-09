# SCMStateChangeNotify(void *)

- ea: `0x18003db80`
- end: `0x18003dd32`
- name: `?SCMStateChangeNotify@@YAXPEAX@Z`
- size: `434`
- prototype: `void __fastcall(PSERVICE_NOTIFYW pNotifyBuffer)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180028f30`
- `0x18003db80`
- `0x18006ebd8`
- `0x18006ed20`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003dce5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003dce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcef`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18003dc70`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18003dc70`

## string_xrefs

- `0x18003dbf2`: `Win32 exit code = %u, service exit code = %u`
- `0x18003dc8d`: `Repost of NotifyServiceStatusChange failed for node %ws: status = %u`
- `0x18003dcc0`: `Signalling services started event`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SCMStateChangeNotify(PSERVICE_NOTIFYW pNotifyBuffer)
{
  SC_HANDLE *pContext; // rdi
  __int64 v3; // rax
  DWORD dwWin32ExitCode; // eax
  DWORD v5; // ebx
  __int64 v6; // rax
  DWORD LastError; // ebx
  __int64 v8; // rax
  __int64 v9; // [rsp+28h] [rbp-60h]
  DWORD dwNotificationStatus; // [rsp+30h] [rbp-58h]
  __int64 v11; // [rsp+30h] [rbp-58h]
  DWORD dwNotificationTriggered; // [rsp+38h] [rbp-50h]
  DWORD dwCurrentState; // [rsp+40h] [rbp-48h]
  void *TokenHandle[7]; // [rsp+50h] [rbp-38h] BYREF

  pContext = (SC_HANDLE *)pNotifyBuffer->pContext;
  v3 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(pContext + 6);
  dwCurrentState = pNotifyBuffer->ServiceStatus.dwCurrentState;
  dwNotificationTriggered = pNotifyBuffer->dwNotificationTriggered;
  dwNotificationStatus = pNotifyBuffer->dwNotificationStatus;
  TraceMsg(
    4,
    0,
    L"SCMStateChangeNotify",
    926,
    L"SCM state change for node %ws: notify status = %u, trigger mask = %08X, SCM state = %u",
    v3,
    dwNotificationStatus,
    dwNotificationTriggered,
    dwCurrentState);
  if ( pNotifyBuffer->ServiceStatus.dwCurrentState == 1 )
  {
    LODWORD(v11) = pNotifyBuffer->ServiceStatus.dwServiceSpecificExitCode;
    LODWORD(v9) = pNotifyBuffer->ServiceStatus.dwWin32ExitCode;
    TraceMsg(3, 0, L"SCMStateChangeNotify", 932, L"Win32 exit code = %u, service exit code = %u", v9, v11);
  }
  if ( !pNotifyBuffer->dwNotificationStatus
    && (pNotifyBuffer->ServiceStatus.dwCurrentState == 4 || pNotifyBuffer->ServiceStatus.dwCurrentState == 1) )
  {
    --*((_DWORD *)*pContext + 2);
    if ( pNotifyBuffer->ServiceStatus.dwCurrentState == 4 )
    {
      *((_DWORD *)*pContext + 3) = 0;
    }
    else if ( pNotifyBuffer->ServiceStatus.dwCurrentState == 1 )
    {
      dwWin32ExitCode = pNotifyBuffer->ServiceStatus.dwWin32ExitCode;
      if ( dwWin32ExitCode == 1066 )
        dwWin32ExitCode = pNotifyBuffer->ServiceStatus.dwServiceSpecificExitCode;
      *((_DWORD *)*pContext + 3) = dwWin32ExitCode;
    }
  }
  else
  {
    CRevertToken::CRevertToken(TokenHandle);
    v5 = NotifyServiceStatusChangeW(pContext[16], 9u, pNotifyBuffer);
    if ( v5 )
    {
      v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(pContext + 6);
      LODWORD(v11) = v5;
      TraceMsg(
        2,
        0,
        L"SCMStateChangeNotify",
        972,
        L"Repost of NotifyServiceStatusChange failed for node %ws: status = %u",
        v6,
        v11);
    }
    CRevertToken::~CRevertToken((CRevertToken *)TokenHandle);
  }
  if ( !*((_DWORD *)*pContext + 2) )
  {
    TraceMsg(4, 0, L"SCMStateChangeNotify", 978, L"Signalling services started event");
    if ( !SetEvent(*(HANDLE *)*pContext) )
    {
      LastError = GetLastError();
      v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(pContext + 6);
      LODWORD(v11) = LastError;
      TraceMsg(2, 0, L"SCMStateChangeNotify", 981, L"SetEvent failed for node %ws: %u", v8, v11);
    }
  }
}

```

## disassembly

```asm
0x18003db80  push    rbx
0x18003db82  push    rbp
0x18003db83  push    rsi
0x18003db84  push    rdi
0x18003db85  push    r15
0x18003db87  sub     rsp, 60h
0x18003db8b  mov     rbx, rcx
0x18003db8e  mov     rdi, [rcx+10h]
0x18003db92  lea     rbp, [rdi+30h]
0x18003db96  mov     rcx, rbp
0x18003db99  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003db9e  mov     edx, [rbx+20h]
0x18003dba1  mov     [rsp+88h+var_48], edx
0x18003dba5  mov     edx, [rbx+40h]
0x18003dba8  mov     [rsp+88h+var_50], edx
0x18003dbac  mov     edx, [rbx+18h]
0x18003dbaf  mov     dword ptr [rsp+88h+var_58], edx
0x18003dbb3  mov     [rsp+88h+var_60], rax
0x18003dbb8  lea     rax, aScmStateChange; "SCM state change for node %ws: notify s"...
0x18003dbbf  mov     [rsp+88h+var_68], rax
0x18003dbc4  mov     r9d, 39Eh
0x18003dbca  lea     r15, aScmstatechange; "SCMStateChangeNotify"
0x18003dbd1  mov     r8, r15
0x18003dbd4  xor     edx, edx
0x18003dbd6  lea     ecx, [rdx+4]
0x18003dbd9  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003dbde  cmp     dword ptr [rbx+20h], 1
0x18003dbe2  jnz     short loc_18003DC11
0x18003dbe4  mov     eax, [rbx+2Ch]
0x18003dbe7  mov     dword ptr [rsp+88h+var_58], eax
0x18003dbeb  mov     eax, [rbx+28h]
0x18003dbee  mov     dword ptr [rsp+88h+var_60], eax
0x18003dbf2  lea     rax, aWin32ExitCodeU; "Win32 exit code = %u, service exit code"...
0x18003dbf9  mov     [rsp+88h+var_68], rax
0x18003dbfe  mov     r9d, 3A4h
0x18003dc04  mov     r8, r15
0x18003dc07  xor     edx, edx
0x18003dc09  lea     ecx, [rdx+3]
0x18003dc0c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003dc11  cmp     dword ptr [rbx+18h], 0
0x18003dc15  jnz     short loc_18003DC56
0x18003dc17  cmp     dword ptr [rbx+20h], 4
0x18003dc1b  jz      short loc_18003DC23
0x18003dc1d  cmp     dword ptr [rbx+20h], 1
0x18003dc21  jnz     short loc_18003DC56
0x18003dc23  mov     rax, [rdi]
0x18003dc26  dec     dword ptr [rax+8]
0x18003dc29  cmp     dword ptr [rbx+20h], 4
0x18003dc2d  jnz     short loc_18003DC3B
0x18003dc2f  mov     rax, [rdi]
0x18003dc32  mov     dword ptr [rax+0Ch], 0
0x18003dc39  jmp     short loc_18003DCB7
0x18003dc3b  cmp     dword ptr [rbx+20h], 1
0x18003dc3f  jnz     short loc_18003DCB7
0x18003dc41  mov     eax, [rbx+28h]
0x18003dc44  mov     rcx, [rdi]
0x18003dc47  cmp     eax, 42Ah
0x18003dc4c  jnz     short loc_18003DC51
0x18003dc4e  mov     eax, [rbx+2Ch]
0x18003dc51  mov     [rcx+0Ch], eax
0x18003dc54  jmp     short loc_18003DCB7
0x18003dc56  lea     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x18003dc5b  call    ??0CRevertToken@@QEAA@XZ; CRevertToken::CRevertToken(void)
0x18003dc60  nop
0x18003dc61  mov     r8, rbx; pNotifyBuffer
0x18003dc64  mov     edx, 9; dwNotifyMask
0x18003dc69  mov     rcx, [rdi+80h]; hService
0x18003dc70  call    cs:__imp_NotifyServiceStatusChangeW
0x18003dc76  mov     ebx, eax
0x18003dc78  test    eax, eax
0x18003dc7a  jz      short loc_18003DCAD
0x18003dc7c  mov     rcx, rbp
0x18003dc7f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003dc84  mov     dword ptr [rsp+88h+var_58], ebx
0x18003dc88  mov     [rsp+88h+var_60], rax
0x18003dc8d  lea     rax, aRepostOfNotify; "Repost of NotifyServiceStatusChange fai"...
0x18003dc94  mov     [rsp+88h+var_68], rax
0x18003dc99  mov     r9d, 3CCh
0x18003dc9f  mov     r8, r15
0x18003dca2  xor     edx, edx
0x18003dca4  lea     ecx, [rdx+2]
0x18003dca7  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003dcac  nop
0x18003dcad  lea     rcx, [rsp+88h+TokenHandle]; this
0x18003dcb2  call    ??1CRevertToken@@QEAA@XZ; CRevertToken::~CRevertToken(void)
0x18003dcb7  mov     rax, [rdi]
0x18003dcba  cmp     dword ptr [rax+8], 0
0x18003dcbe  jnz     short loc_18003DD27
0x18003dcc0  lea     rax, aSignallingServ; "Signalling services started event"
0x18003dcc7  mov     [rsp+88h+var_68], rax
0x18003dccc  mov     r9d, 3D2h
0x18003dcd2  mov     r8, r15
0x18003dcd5  xor     edx, edx
0x18003dcd7  lea     ecx, [rdx+4]
0x18003dcda  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003dcdf  mov     rcx, [rdi]
0x18003dce2  mov     rcx, [rcx]; hEvent
0x18003dce5  call    cs:__imp_SetEvent
0x18003dceb  test    eax, eax
0x18003dced  jnz     short loc_18003DD27
0x18003dcef  call    cs:__imp_GetLastError
0x18003dcf5  mov     ebx, eax
0x18003dcf7  mov     rcx, rbp
0x18003dcfa  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003dcff  mov     dword ptr [rsp+88h+var_58], ebx
0x18003dd03  mov     [rsp+88h+var_60], rax
0x18003dd08  lea     rax, aSeteventFailed; "SetEvent failed for node %ws: %u"
0x18003dd0f  mov     [rsp+88h+var_68], rax
0x18003dd14  mov     r9d, 3D5h
0x18003dd1a  mov     r8, r15
0x18003dd1d  xor     edx, edx
0x18003dd1f  lea     ecx, [rdx+2]
0x18003dd22  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003dd27  add     rsp, 60h
0x18003dd2b  pop     r15
0x18003dd2d  pop     rdi
0x18003dd2e  pop     rsi
0x18003dd2f  pop     rbp
0x18003dd30  pop     rbx
0x18003dd31  retn
```
