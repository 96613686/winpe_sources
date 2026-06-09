# Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)

- ea: `0x180027278`
- end: `0x1800272ce`
- name: `?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z`
- size: `86`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006780`
- `0x180007070`
- `0x180008ad0`
- `0x180009a70`
- `0x180009f5c`
- `0x18000bfc0`
- `0x18000dde0`
- `0x18000f520`
- `0x180010dd0`
- `0x180015b10`
- `0x180015d54`
- `0x180025788`
- `0x18002aee4`
- `0x18002bcdc`
- `0x18002c96c`
- `0x180044364`
- `0x180044870`
- `0x180044ec0`
- `0x180045e7c`
- `0x1800461d8`
- `0x180046728`

## callees

- `0x180027278`
- `0x1800272d4`
- `0x180027448`

## string_xrefs

- `0x1800272a2`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18002729b`: `EventWriteNullOrEmptyParameterFailureEvent`

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
0x180027278  push    rbx
0x18002727a  sub     rsp, 20h
0x18002727e  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180027285  jz      short loc_1800272C4
0x180027287  mov     r9, rdx
0x18002728a  mov     r8, rcx
0x18002728d  call    McTemplateU0zz_EventWriteTransfer
0x180027292  mov     ebx, eax
0x180027294  test    eax, eax
0x180027296  jz      short loc_1800272C6
0x180027298  mov     r9d, eax
0x18002729b  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x1800272a2  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x1800272a9  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800272b0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800272b5  test    ebx, ebx
0x1800272b7  jle     short loc_1800272C6
0x1800272b9  movzx   ebx, bx
0x1800272bc  or      ebx, 80070000h
0x1800272c2  jmp     short loc_1800272C6
0x1800272c4  xor     ebx, ebx
0x1800272c6  mov     eax, ebx
0x1800272c8  add     rsp, 20h
0x1800272cc  pop     rbx
0x1800272cd  retn
```
