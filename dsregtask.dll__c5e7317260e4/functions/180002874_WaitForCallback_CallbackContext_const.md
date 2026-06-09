# WaitForCallback(CallbackContext const &)

- ea: `0x180002874`
- end: `0x1800029bc`
- name: `?WaitForCallback@@YAJAEBUCallbackContext@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(const struct CallbackContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000273c`

## callees

- `0x180002874`
- `0x180003000`
- `0x180003074`
- `0x1800030b0`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180002920`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180002920`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180002905`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180002905`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1800028fa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1800028fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002949`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800028ab`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800028ab`

## string_xrefs

- `0x1800029a3`: `%s: Complete event has been signaled`
- `0x180002985`: `%s: Timed out waiting for completion event`

## pseudocode

```c
__int64 __fastcall WaitForCallback(const struct CallbackContext *a1)
{
  const HANDLE *v1; // rbx
  unsigned int v2; // edi
  DWORD v3; // eax
  __int64 LastError; // rbx
  MSG Msg; // [rsp+30h] [rbp-38h] BYREF

  v1 = (const HANDLE *)((char *)a1 + 8);
  memset(&Msg, 0, sizeof(Msg));
  v2 = 0;
  while ( 1 )
  {
    v3 = MsgWaitForMultipleObjects(1u, v1, 0, 0xFFFFFFFF, 0x1CBFu);
    if ( !v3 )
    {
      Logger::TraceVerbose(L"%s: Complete event has been signaled", L"WaitForCallback");
      return v2;
    }
    if ( v3 != 1 )
      break;
    while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      if ( Msg.message == 18 )
      {
        Logger::TraceWarning(
          L"%s: Got WM_QUIT message while waiting for callback. Aborting with ERROR_CANCELLED...",
          L"WaitForCallback");
        LOWORD(v2) = 1223;
        return (unsigned __int16)v2 | 0x80070000;
      }
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
  }
  if ( v3 == 258 )
  {
    LOWORD(v2) = 1460;
    Logger::TraceError(L"%s: Timed out waiting for completion event", L"WaitForCallback");
    return (unsigned __int16)v2 | 0x80070000;
  }
  if ( v3 != -1 )
  {
    Logger::TraceError(L"%s: MsgWaitForMultipleObjects returned 0x%08x", L"WaitForCallback", v3);
    LOWORD(v2) = 1359;
    return (unsigned __int16)v2 | 0x80070000;
  }
  LastError = GetLastError();
  Logger::TraceError(L"%s: MsgWaitForMultipleObjects failed with error code: 0x%08x", L"WaitForCallback", LastError);
  if ( !(_DWORD)LastError )
    LODWORD(LastError) = 1359;
  v2 = LastError;
  if ( (int)LastError > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x180002874  mov     rax, rsp
0x180002877  mov     [rax+8], rbx
0x18000287b  push    rdi
0x18000287c  sub     rsp, 60h
0x180002880  xorps   xmm0, xmm0
0x180002883  lea     rbx, [rcx+8]
0x180002887  movups  xmmword ptr [rax-38h], xmm0
0x18000288b  xor     edi, edi
0x18000288d  movups  xmmword ptr [rax-28h], xmm0
0x180002891  movups  xmmword ptr [rax-18h], xmm0
0x180002895  xor     r8d, r8d; fWaitAll
0x180002898  mov     [rsp+68h+dwWakeMask], 1CBFh; dwWakeMask
0x1800028a0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800028a4  mov     rdx, rbx; pHandles
0x1800028a7  lea     ecx, [r8+1]; nCount
0x1800028ab  call    cs:__imp_MsgWaitForMultipleObjects
0x1800028b1  test    eax, eax
0x1800028b3  jz      loc_18000299C
0x1800028b9  cmp     eax, 1
0x1800028bc  jz      short loc_18000290B
0x1800028be  cmp     eax, 102h
0x1800028c3  jz      loc_180002979
0x1800028c9  cmp     eax, 0FFFFFFFFh
0x1800028cc  jz      short loc_180002949
0x1800028ce  mov     r8d, eax
0x1800028d1  lea     rdx, aWaitforcallbac; "WaitForCallback"
0x1800028d8  lea     rcx, aSMsgwaitformul_0; "%s: MsgWaitForMultipleObjects returned "...
0x1800028df  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800028e4  mov     edi, 54Fh
0x1800028e9  jmp     loc_180002991
0x1800028ee  cmp     [rsp+68h+Msg.message], 12h
0x1800028f3  jz      short loc_18000292F
0x1800028f5  lea     rcx, [rsp+68h+Msg]; lpMsg
0x1800028fa  call    cs:__imp_TranslateMessage
0x180002900  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180002905  call    cs:__imp_DispatchMessageW
0x18000290b  xor     r9d, r9d; wMsgFilterMax
0x18000290e  mov     [rsp+68h+dwWakeMask], 1; wRemoveMsg
0x180002916  xor     r8d, r8d; wMsgFilterMin
0x180002919  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18000291e  xor     edx, edx; hWnd
0x180002920  call    cs:__imp_PeekMessageW
0x180002926  test    eax, eax
0x180002928  jnz     short loc_1800028EE
0x18000292a  jmp     loc_180002895
0x18000292f  lea     rdx, aWaitforcallbac; "WaitForCallback"
0x180002936  lea     rcx, aSGotWmQuitMess; "%s: Got WM_QUIT message while waiting f"...
0x18000293d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180002942  mov     edi, 4C7h
0x180002947  jmp     short loc_180002991
0x180002949  call    cs:__imp_GetLastError
0x18000294f  mov     r8d, eax
0x180002952  lea     rdx, aWaitforcallbac; "WaitForCallback"
0x180002959  lea     rcx, aSMsgwaitformul; "%s: MsgWaitForMultipleObjects failed wi"...
0x180002960  mov     ebx, eax
0x180002962  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180002967  mov     edi, 54Fh
0x18000296c  test    ebx, ebx
0x18000296e  cmovz   ebx, edi
0x180002971  mov     edi, ebx
0x180002973  test    ebx, ebx
0x180002975  jg      short loc_180002991
0x180002977  jmp     short loc_1800029AF
0x180002979  lea     rdx, aWaitforcallbac; "WaitForCallback"
0x180002980  mov     edi, 5B4h
0x180002985  lea     rcx, aSTimedOutWaiti; "%s: Timed out waiting for completion ev"...
0x18000298c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180002991  movzx   edi, di
0x180002994  or      edi, 80070000h
0x18000299a  jmp     short loc_1800029AF
0x18000299c  lea     rdx, aWaitforcallbac; "WaitForCallback"
0x1800029a3  lea     rcx, aSCompleteEvent; "%s: Complete event has been signaled"
0x1800029aa  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800029af  mov     rbx, [rsp+68h+arg_0]
0x1800029b4  mov     eax, edi
0x1800029b6  add     rsp, 60h
0x1800029ba  pop     rdi
0x1800029bb  retn
```
