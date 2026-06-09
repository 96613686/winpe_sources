# Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)

- ea: `0x14000507c`
- end: `0x1400050d2`
- name: `?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z`
- size: `86`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003850`
- `0x140004a20`

## callees

- `0x140004f90`
- `0x14000507c`
- `0x140005324`

## string_xrefs

- `0x14000509f`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x1400050a6`: `Logger::WriteNullOrEmptyParameterFailureEvent`

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
0x14000507c  push    rbx
0x14000507e  sub     rsp, 20h
0x140005082  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x140005089  jz      short loc_1400050C8
0x14000508b  mov     r9, rdx
0x14000508e  mov     r8, rcx
0x140005091  call    McTemplateU0zz_EventWriteTransfer
0x140005096  mov     ebx, eax
0x140005098  test    eax, eax
0x14000509a  jz      short loc_1400050CA
0x14000509c  mov     r9d, eax
0x14000509f  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x1400050a6  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x1400050ad  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1400050b4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1400050b9  test    ebx, ebx
0x1400050bb  jle     short loc_1400050CA
0x1400050bd  movzx   ebx, bx
0x1400050c0  or      ebx, 80070000h
0x1400050c6  jmp     short loc_1400050CA
0x1400050c8  xor     ebx, ebx
0x1400050ca  mov     eax, ebx
0x1400050cc  add     rsp, 20h
0x1400050d0  pop     rbx
0x1400050d1  retn
```
