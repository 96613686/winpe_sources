# StopMcMisc

- ea: `0x18003adf0`
- end: `0x18003aeed`
- name: `StopMcMisc`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003ab6c`
- `0x180050b74`

## callees

- `0x18000ac60`
- `0x18003adf0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x18003ae51`
- `WS2_32!__imp_closesocket` at `0x18003ae51`
- `WS2_32!__imp_WSAGetLastError` at `0x18003ae6c`
- `WS2_32!__imp_WSAGetLastError` at `0x18003ae6c`

## string_xrefs

- `0x18003aebb`: `StopMcMisc() complete`

## pseudocode

```c
unsigned int StopMcMisc()
{
  unsigned int result; // eax
  unsigned int Error; // eax
  int v2; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v3[2044]; // [rsp+34h] [rbp-814h] BYREF

  v2 = 0;
  result = (unsigned int)memset_0(v3, 0, sizeof(v3));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    result = McTemplateU0z_EventWriteTransfer(
               &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
               (const EVENT_DESCRIPTOR *)RasRtrmgrTraceInfo,
               L"StopMcMisc() initiated");
  if ( McMiscSocket != -1 )
  {
    result = closesocket(McMiscSocket);
    if ( result == -1 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v2) = 0;
      Error = WSAGetLastError();
      result = FormatRRASErrorString(&v2, L"error %d closing socket", Error);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        result = McTemplateU0z_EventWriteTransfer(
                   &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                   (const EVENT_DESCRIPTOR *)RasRtrMgrTraceError,
                   (const wchar_t *)&v2);
    }
    McMiscSocket = -1;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    return McTemplateU0z_EventWriteTransfer(
             &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
             (const EVENT_DESCRIPTOR *)RasRtrmgrTraceInfo,
             L"StopMcMisc() complete");
  return result;
}

```

## disassembly

```asm
0x18003adf0  sub     rsp, 848h
0x18003adf7  mov     rax, cs:__security_cookie
0x18003adfe  xor     rax, rsp
0x18003ae01  mov     [rsp+848h+var_18], rax
0x18003ae09  xor     eax, eax
0x18003ae0b  lea     rcx, [rsp+848h+var_814]; void *
0x18003ae10  xor     edx, edx; Val
0x18003ae12  mov     [rsp+848h+var_818], eax
0x18003ae16  mov     r8d, 7FCh; Size
0x18003ae1c  call    memset_0
0x18003ae21  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003ae28  jz      short loc_18003AE44
0x18003ae2a  lea     r8, aStopmcmiscInit; "StopMcMisc() initiated"
0x18003ae31  lea     rdx, RasRtrmgrTraceInfo
0x18003ae38  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ae3f  call    McTemplateU0z_EventWriteTransfer
0x18003ae44  mov     rcx, cs:McMiscSocket; s
0x18003ae4b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003ae4f  jz      short loc_18003AEB2
0x18003ae51  call    cs:__imp_closesocket
0x18003ae57  cmp     eax, 0FFFFFFFFh
0x18003ae5a  jnz     short loc_18003AEA7
0x18003ae5c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003ae63  jz      short loc_18003AEA7
0x18003ae65  xor     eax, eax
0x18003ae67  mov     word ptr [rsp+848h+var_818], ax
0x18003ae6c  call    cs:__imp_WSAGetLastError
0x18003ae72  mov     r8d, eax
0x18003ae75  lea     rdx, aErrorDClosingS; "error %d closing socket"
0x18003ae7c  lea     rcx, [rsp+848h+var_818]
0x18003ae81  call    FormatRRASErrorString
0x18003ae86  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003ae8d  jz      short loc_18003AEA7
0x18003ae8f  lea     r8, [rsp+848h+var_818]
0x18003ae94  lea     rdx, RasRtrMgrTraceError
0x18003ae9b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003aea2  call    McTemplateU0z_EventWriteTransfer
0x18003aea7  mov     cs:McMiscSocket, 0FFFFFFFFFFFFFFFFh
0x18003aeb2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003aeb9  jz      short loc_18003AED5
0x18003aebb  lea     r8, aStopmcmiscComp; "StopMcMisc() complete"
0x18003aec2  lea     rdx, RasRtrmgrTraceInfo
0x18003aec9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003aed0  call    McTemplateU0z_EventWriteTransfer
0x18003aed5  mov     rcx, [rsp+848h+var_18]
0x18003aedd  xor     rcx, rsp; StackCookie
0x18003aee0  call    __security_check_cookie
0x18003aee5  add     rsp, 848h
0x18003aeec  retn
```
