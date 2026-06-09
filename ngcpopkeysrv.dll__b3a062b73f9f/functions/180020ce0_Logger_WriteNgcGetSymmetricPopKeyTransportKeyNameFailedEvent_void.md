# Logger::WriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent(void)

- ea: `0x180020ce0`
- end: `0x180020d54`
- name: `?WriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent@Logger@@SAJXZ`
- size: `116`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e6b0`

## callees

- `0x180004de0`
- `0x18001ce90`
- `0x180020c2c`
- `0x180020ce0`

## string_xrefs

- `0x180020d26`: `EventWriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent`
- `0x180020d2d`: `Logger::WriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent`

## pseudocode

```c
__int64 __fastcall Logger::WriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent(__int64 a1, __int64 a2, __int64 a3)
{
  ULONG v3; // eax
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
  {
    v3 = McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NgcGetSymmetricPopKeyTransportKeyNameFailedEvent,
           a3,
           1u,
           &v5);
    if ( v3 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent",
        L"EventWriteNgcGetSymmetricPopKeyTransportKeyNameFailedEvent",
        v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180020ce0  sub     rsp, 58h
0x180020ce4  mov     rax, cs:__security_cookie
0x180020ceb  xor     rax, rsp
0x180020cee  mov     [rsp+58h+var_18], rax
0x180020cf3  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x180020cfa  jz      short loc_180020D40
0x180020cfc  lea     rax, [rsp+58h+var_28]
0x180020d01  mov     r9d, 1
0x180020d07  lea     rdx, NgcGetSymmetricPopKeyTransportKeyNameFailedEvent
0x180020d0e  mov     [rsp+58h+var_38], rax
0x180020d13  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180020d1a  call    McGenEventWrite_EventWriteTransfer
0x180020d1f  test    eax, eax
0x180020d21  jz      short loc_180020D40
0x180020d23  mov     r9d, eax
0x180020d26  lea     r8, aEventwritengcg; "EventWriteNgcGetSymmetricPopKeyTranspor"...
0x180020d2d  lea     rdx, aLoggerWritengc_1; "Logger::WriteNgcGetSymmetricPopKeyTrans"...
0x180020d34  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180020d3b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180020d40  xor     eax, eax
0x180020d42  mov     rcx, [rsp+58h+var_18]
0x180020d47  xor     rcx, rsp; StackCookie
0x180020d4a  call    __security_check_cookie
0x180020d4f  add     rsp, 58h
0x180020d53  retn
```
