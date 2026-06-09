# Logger::WriteGetPersistedStateLocationFailureEvent(long,ushort const *,ushort const *,int)

- ea: `0x1800270c8`
- end: `0x180027127`
- name: `?WriteGetPersistedStateLocationFailureEvent@Logger@@SAJJPEBG0H@Z`
- size: `95`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b1a0`

## callees

- `0x1800270c8`
- `0x180027448`
- `0x180044ad4`

## string_xrefs

- `0x1800270fb`: `Logger::WriteGetPersistedStateLocationFailureEvent`
- `0x1800270f4`: `EventWriteGetPersistedStateLocationFailureEvent`
- `0x1800270d7`: `LocationTypeRegistry`

## pseudocode

```c
__int64 __fastcall Logger::WriteGetPersistedStateLocationFailureEvent(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned int v4; // eax
  int v5; // ebx

  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v4 = McTemplateU0dzzdz_EventWriteTransfer(a1, (_DWORD)a2, a1, a4);
    v5 = v4;
    if ( v4 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteGetPersistedStateLocationFailureEvent",
        L"EventWriteGetPersistedStateLocationFailureEvent",
        v4);
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800270c8  push    rbx
0x1800270ca  sub     rsp, 40h
0x1800270ce  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800270d5  jz      short loc_18002711D
0x1800270d7  lea     rax, aLocationtypere; "LocationTypeRegistry"
0x1800270de  mov     r8d, ecx
0x1800270e1  mov     [rsp+48h+var_18], rax
0x1800270e6  call    McTemplateU0dzzdz_EventWriteTransfer
0x1800270eb  mov     ebx, eax
0x1800270ed  test    eax, eax
0x1800270ef  jz      short loc_18002711F
0x1800270f1  mov     r9d, eax
0x1800270f4  lea     r8, aEventwritegetp; "EventWriteGetPersistedStateLocationFail"...
0x1800270fb  lea     rdx, aLoggerWriteget; "Logger::WriteGetPersistedStateLocationF"...
0x180027102  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180027109  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002710e  test    ebx, ebx
0x180027110  jle     short loc_18002711F
0x180027112  movzx   ebx, bx
0x180027115  or      ebx, 80070000h
0x18002711b  jmp     short loc_18002711F
0x18002711d  xor     ebx, ebx
0x18002711f  mov     eax, ebx
0x180027121  add     rsp, 40h
0x180027125  pop     rbx
0x180027126  retn
```
