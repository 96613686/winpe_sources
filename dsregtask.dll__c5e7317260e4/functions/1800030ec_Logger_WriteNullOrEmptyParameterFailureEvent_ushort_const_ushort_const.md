# Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)

- ea: `0x1800030ec`
- end: `0x180003142`
- name: `?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z`
- size: `86`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003454`
- `0x1800035d8`

## callees

- `0x180003000`
- `0x1800030ec`
- `0x180003394`

## string_xrefs

- `0x18000310f`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180003116`: `Logger::WriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall Logger::WriteNullOrEmptyParameterFailureEvent(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  int v3; // ebx

  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v2 = McTemplateU0zz_EventWriteTransfer(a1, a2, a1, a2);
    v3 = v2;
    if ( v2 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v2);
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800030ec  push    rbx
0x1800030ee  sub     rsp, 20h
0x1800030f2  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800030f9  jz      short loc_180003138
0x1800030fb  mov     r9, rdx
0x1800030fe  mov     r8, rcx
0x180003101  call    McTemplateU0zz_EventWriteTransfer
0x180003106  mov     ebx, eax
0x180003108  test    eax, eax
0x18000310a  jz      short loc_18000313A
0x18000310c  mov     r9d, eax
0x18000310f  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180003116  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000311d  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180003124  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180003129  test    ebx, ebx
0x18000312b  jle     short loc_18000313A
0x18000312d  movzx   ebx, bx
0x180003130  or      ebx, 80070000h
0x180003136  jmp     short loc_18000313A
0x180003138  xor     ebx, ebx
0x18000313a  mov     eax, ebx
0x18000313c  add     rsp, 20h
0x180003140  pop     rbx
0x180003141  retn
```
