# Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)

- ea: `0x18000e414`
- end: `0x18000e4d9`
- name: `?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ`
- size: `197`
- prototype: `static int(unsigned int, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009050`
- `0x18002b998`
- `0x180044a9c`

## callees

- `0x18000ced0`
- `0x18000e414`
- `0x180027448`
- `0x18002a4c4`
- `0x180044bbc`

## string_xrefs

- `0x18000e464`: `Logger::WriteRegistryFailureEventEx`
- `0x18000e4a2`: `Logger::WriteRegistryFailureEventEx`
- `0x18000e49b`: `EventWriteRegistryFailureEvent`

## pseudocode

```c
__int64 Logger::WriteRegistryFailureEventEx(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3, ...)
{
  int v3; // edi
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  void *v8; // rsi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  int v11; // edi
  void *lpMem[7]; // [rsp+30h] [rbp-38h] BYREF
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  lpMem[0] = 0;
  v3 = (int)a2;
  lpMem[1] = 0;
  v5 = Logger::FormatString((unsigned __int16 **)lpMem, a3, va);
  v8 = lpMem[0];
  v9 = v5;
  if ( v5 >= 0 )
  {
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v10 = McTemplateU0qzz_EventWriteTransfer(v7, v6, a1, v3, (__int64)lpMem[0]);
      v11 = v10;
      if ( v10 )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteRegistryFailureEventEx",
          L"EventWriteRegistryFailureEvent",
          v10);
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
        else
          v9 = v11;
      }
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"Logger::WriteRegistryFailureEventEx",
      L"FormatString",
      (unsigned int)v5);
  }
  SafeFree(v8);
  return v9;
}

```

## disassembly

```asm
0x18000e414  mov     r11, rsp
0x18000e417  mov     [r11+18h], r8
0x18000e41b  mov     [r11+20h], r9
0x18000e41f  push    rbx
0x18000e420  push    rbp
0x18000e421  push    rsi
0x18000e422  push    rdi
0x18000e423  sub     rsp, 48h
0x18000e427  mov     rax, r8
0x18000e42a  mov     qword ptr [r11-38h], 0
0x18000e432  mov     rdi, rdx
0x18000e435  mov     qword ptr [r11-30h], 0
0x18000e43d  mov     ebp, ecx
0x18000e43f  lea     r8, [r11+20h]; char *
0x18000e443  mov     rdx, rax; unsigned __int16 *
0x18000e446  lea     rcx, [r11-38h]; unsigned __int16 **
0x18000e44a  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x18000e44f  mov     rsi, [rsp+68h+lpMem]
0x18000e454  mov     ebx, eax
0x18000e456  test    eax, eax
0x18000e458  jns     short loc_18000E479
0x18000e45a  mov     r9d, eax
0x18000e45d  lea     r8, aFormatstring; "FormatString"
0x18000e464  lea     rdx, aLoggerWritereg_0; "Logger::WriteRegistryFailureEventEx"
0x18000e46b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000e472  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e477  jmp     short loc_18000E4C6
0x18000e479  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18000e480  jz      short loc_18000E4C6
0x18000e482  mov     r9, rdi
0x18000e485  mov     [rsp+68h+var_48], rsi
0x18000e48a  mov     r8d, ebp
0x18000e48d  call    McTemplateU0qzz_EventWriteTransfer
0x18000e492  mov     edi, eax
0x18000e494  test    eax, eax
0x18000e496  jz      short loc_18000E4C6
0x18000e498  mov     r9d, eax
0x18000e49b  lea     r8, aEventwriteregi; "EventWriteRegistryFailureEvent"
0x18000e4a2  lea     rdx, aLoggerWritereg_0; "Logger::WriteRegistryFailureEventEx"
0x18000e4a9  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000e4b0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e4b5  test    edi, edi
0x18000e4b7  jg      short loc_18000E4BD
0x18000e4b9  mov     ebx, edi
0x18000e4bb  jmp     short loc_18000E4C6
0x18000e4bd  movzx   ebx, di
0x18000e4c0  or      ebx, 80070000h
0x18000e4c6  mov     rcx, rsi; lpMem
0x18000e4c9  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000e4ce  mov     eax, ebx
0x18000e4d0  add     rsp, 48h
0x18000e4d4  pop     rdi
0x18000e4d5  pop     rsi
0x18000e4d6  pop     rbp
0x18000e4d7  pop     rbx
0x18000e4d8  retn
```
