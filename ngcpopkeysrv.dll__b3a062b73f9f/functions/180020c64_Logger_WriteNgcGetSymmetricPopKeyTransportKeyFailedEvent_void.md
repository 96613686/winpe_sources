# Logger::WriteNgcGetSymmetricPopKeyTransportKeyFailedEvent(void)

- ea: `0x180020c64`
- end: `0x180020cd8`
- name: `?WriteNgcGetSymmetricPopKeyTransportKeyFailedEvent@Logger@@SAJXZ`
- size: `116`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000edb4`

## callees

- `0x180004de0`
- `0x18001ce90`
- `0x180020c2c`
- `0x180020c64`

## string_xrefs

- `0x180020cb1`: `Logger::WriteNgcGetSymmetricPopKeyTransportKeyFailedEvent`
- `0x180020caa`: `EventWriteNgcGetSymmetricPopKeyTransportKeyFailedEvent`

## pseudocode

```c
__int64 __fastcall Logger::WriteNgcGetSymmetricPopKeyTransportKeyFailedEvent(__int64 a1, __int64 a2, __int64 a3)
{
  ULONG v3; // eax
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
  {
    v3 = McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NgcGetSymmetricPopKeyTransportKeyFailedEvent,
           a3,
           1u,
           &v5);
    if ( v3 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNgcGetSymmetricPopKeyTransportKeyFailedEvent",
        L"EventWriteNgcGetSymmetricPopKeyTransportKeyFailedEvent",
        v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180020c64  sub     rsp, 58h
0x180020c68  mov     rax, cs:__security_cookie
0x180020c6f  xor     rax, rsp
0x180020c72  mov     [rsp+58h+var_18], rax
0x180020c77  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x180020c7e  jz      short loc_180020CC4
0x180020c80  lea     rax, [rsp+58h+var_28]
0x180020c85  mov     r9d, 1
0x180020c8b  lea     rdx, NgcGetSymmetricPopKeyTransportKeyFailedEvent
0x180020c92  mov     [rsp+58h+var_38], rax
0x180020c97  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180020c9e  call    McGenEventWrite_EventWriteTransfer
0x180020ca3  test    eax, eax
0x180020ca5  jz      short loc_180020CC4
0x180020ca7  mov     r9d, eax
0x180020caa  lea     r8, aEventwritengcg_0; "EventWriteNgcGetSymmetricPopKeyTranspor"...
0x180020cb1  lea     rdx, aLoggerWritengc_0; "Logger::WriteNgcGetSymmetricPopKeyTrans"...
0x180020cb8  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180020cbf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180020cc4  xor     eax, eax
0x180020cc6  mov     rcx, [rsp+58h+var_18]
0x180020ccb  xor     rcx, rsp; StackCookie
0x180020cce  call    __security_check_cookie
0x180020cd3  add     rsp, 58h
0x180020cd7  retn
```
