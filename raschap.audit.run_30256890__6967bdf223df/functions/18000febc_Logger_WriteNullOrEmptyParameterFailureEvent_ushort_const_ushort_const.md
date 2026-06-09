# Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)

- ea: `0x18000febc`
- end: `0x18000ff12`
- name: `?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z`
- size: `86`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ff18`
- `0x180013084`
- `0x180024398`
- `0x1800246a0`
- `0x180024834`
- `0x180024a28`
- `0x180024c04`
- `0x180024ea8`
- `0x180025030`
- `0x18002572c`
- `0x18002594c`
- `0x180025bd4`
- `0x180025c90`

## callees

- `0x18000febc`
- `0x180010218`
- `0x18002566c`

## string_xrefs

- `0x18000fee6`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000fedf`: `EventWriteNullOrEmptyParameterFailureEvent`

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
0x18000febc  push    rbx
0x18000febe  sub     rsp, 20h
0x18000fec2  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000fec9  jz      short loc_18000FF08
0x18000fecb  mov     r9, rdx
0x18000fece  mov     r8, rcx
0x18000fed1  call    McTemplateU0zz_EventWriteTransfer
0x18000fed6  mov     ebx, eax
0x18000fed8  test    eax, eax
0x18000feda  jz      short loc_18000FF0A
0x18000fedc  mov     r9d, eax
0x18000fedf  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000fee6  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000feed  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000fef4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000fef9  test    ebx, ebx
0x18000fefb  jle     short loc_18000FF0A
0x18000fefd  movzx   ebx, bx
0x18000ff00  or      ebx, 80070000h
0x18000ff06  jmp     short loc_18000FF0A
0x18000ff08  xor     ebx, ebx
0x18000ff0a  mov     eax, ebx
0x18000ff0c  add     rsp, 20h
0x18000ff10  pop     rbx
0x18000ff11  retn
```
