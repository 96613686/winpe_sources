# Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)

- ea: `0x18000fdf0`
- end: `0x18000feb5`
- name: `?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ`
- size: `197`
- prototype: `static int(unsigned int, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800254dc`

## callees

- `0x18000fdf0`
- `0x180010218`
- `0x180010320`
- `0x1800252e0`
- `0x180025514`

## string_xrefs

- `0x18000fe77`: `EventWriteRegistryFailureEvent`
- `0x18000fe40`: `Logger::WriteRegistryFailureEventEx`
- `0x18000fe7e`: `Logger::WriteRegistryFailureEventEx`

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
  void *v13[7]; // [rsp+30h] [rbp-38h] BYREF
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  v13[0] = 0;
  v3 = (int)a2;
  v13[1] = 0;
  v5 = Logger::FormatString((unsigned __int16 **)v13, a3, va);
  v8 = v13[0];
  v9 = v5;
  if ( v5 >= 0 )
  {
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v10 = McTemplateU0qzz_EventWriteTransfer(v7, v6, a1, v3, (__int64)v13[0]);
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
0x18000fdf0  mov     r11, rsp
0x18000fdf3  mov     [r11+18h], r8
0x18000fdf7  mov     [r11+20h], r9
0x18000fdfb  push    rbx
0x18000fdfc  push    rbp
0x18000fdfd  push    rsi
0x18000fdfe  push    rdi
0x18000fdff  sub     rsp, 48h
0x18000fe03  mov     rax, r8
0x18000fe06  mov     qword ptr [r11-38h], 0
0x18000fe0e  mov     rdi, rdx
0x18000fe11  mov     qword ptr [r11-30h], 0
0x18000fe19  mov     ebp, ecx
0x18000fe1b  lea     r8, [r11+20h]; char *
0x18000fe1f  mov     rdx, rax; unsigned __int16 *
0x18000fe22  lea     rcx, [r11-38h]; unsigned __int16 **
0x18000fe26  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x18000fe2b  mov     rsi, [rsp+68h+var_38]
0x18000fe30  mov     ebx, eax
0x18000fe32  test    eax, eax
0x18000fe34  jns     short loc_18000FE55
0x18000fe36  mov     r9d, eax
0x18000fe39  lea     r8, aFormatstring; "FormatString"
0x18000fe40  lea     rdx, aLoggerWritereg; "Logger::WriteRegistryFailureEventEx"
0x18000fe47  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18000fe4e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000fe53  jmp     short loc_18000FEA2
0x18000fe55  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18000fe5c  jz      short loc_18000FEA2
0x18000fe5e  mov     r9, rdi
0x18000fe61  mov     [rsp+68h+var_48], rsi
0x18000fe66  mov     r8d, ebp
0x18000fe69  call    McTemplateU0qzz_EventWriteTransfer
0x18000fe6e  mov     edi, eax
0x18000fe70  test    eax, eax
0x18000fe72  jz      short loc_18000FEA2
0x18000fe74  mov     r9d, eax
0x18000fe77  lea     r8, aEventwriteregi; "EventWriteRegistryFailureEvent"
0x18000fe7e  lea     rdx, aLoggerWritereg; "Logger::WriteRegistryFailureEventEx"
0x18000fe85  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000fe8c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000fe91  test    edi, edi
0x18000fe93  jg      short loc_18000FE99
0x18000fe95  mov     ebx, edi
0x18000fe97  jmp     short loc_18000FEA2
0x18000fe99  movzx   ebx, di
0x18000fe9c  or      ebx, 80070000h
0x18000fea2  mov     rcx, rsi; void *
0x18000fea5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000feaa  mov     eax, ebx
0x18000feac  add     rsp, 48h
0x18000feb0  pop     rdi
0x18000feb1  pop     rsi
0x18000feb2  pop     rbp
0x18000feb3  pop     rbx
0x18000feb4  retn
```
