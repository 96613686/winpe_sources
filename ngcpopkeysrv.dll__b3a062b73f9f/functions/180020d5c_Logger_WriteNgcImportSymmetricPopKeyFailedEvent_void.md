# Logger::WriteNgcImportSymmetricPopKeyFailedEvent(void)

- ea: `0x180020d5c`
- end: `0x180020dd0`
- name: `?WriteNgcImportSymmetricPopKeyFailedEvent@Logger@@SAJXZ`
- size: `116`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e2b4`

## callees

- `0x180004de0`
- `0x18001ce90`
- `0x180020c2c`
- `0x180020d5c`

## string_xrefs

- `0x180020da9`: `Logger::WriteNgcImportSymmetricPopKeyFailedEvent`
- `0x180020da2`: `EventWriteNgcImportSymmetricPopKeyFailedEvent`

## pseudocode

```c
__int64 __fastcall Logger::WriteNgcImportSymmetricPopKeyFailedEvent(__int64 a1, __int64 a2, __int64 a3)
{
  ULONG v3; // eax
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
  {
    v3 = McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NgcImportSymmetricPopKeyFailedEvent,
           a3,
           1u,
           &v5);
    if ( v3 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNgcImportSymmetricPopKeyFailedEvent",
        L"EventWriteNgcImportSymmetricPopKeyFailedEvent",
        v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180020d5c  sub     rsp, 58h
0x180020d60  mov     rax, cs:__security_cookie
0x180020d67  xor     rax, rsp
0x180020d6a  mov     [rsp+58h+var_18], rax
0x180020d6f  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x180020d76  jz      short loc_180020DBC
0x180020d78  lea     rax, [rsp+58h+var_28]
0x180020d7d  mov     r9d, 1
0x180020d83  lea     rdx, NgcImportSymmetricPopKeyFailedEvent
0x180020d8a  mov     [rsp+58h+var_38], rax
0x180020d8f  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180020d96  call    McGenEventWrite_EventWriteTransfer
0x180020d9b  test    eax, eax
0x180020d9d  jz      short loc_180020DBC
0x180020d9f  mov     r9d, eax
0x180020da2  lea     r8, aEventwritengci; "EventWriteNgcImportSymmetricPopKeyFaile"...
0x180020da9  lea     rdx, aLoggerWritengc; "Logger::WriteNgcImportSymmetricPopKeyFa"...
0x180020db0  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180020db7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180020dbc  xor     eax, eax
0x180020dbe  mov     rcx, [rsp+58h+var_18]
0x180020dc3  xor     rcx, rsp; StackCookie
0x180020dc6  call    __security_check_cookie
0x180020dcb  add     rsp, 58h
0x180020dcf  retn
```
