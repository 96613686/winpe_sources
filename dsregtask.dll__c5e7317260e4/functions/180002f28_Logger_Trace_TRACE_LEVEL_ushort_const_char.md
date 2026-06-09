# Logger::Trace(_TRACE_LEVEL,ushort const *,char *)

- ea: `0x180002f28`
- end: `0x180002ffa`
- name: `?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z`
- size: `210`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, va_list)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003000`
- `0x18000303c`
- `0x180003074`
- `0x1800030b0`

## callees

- `0x180002dd8`
- `0x180002f28`
- `0x180003314`
- `0x1800035a0`

## pseudocode

```c
__int64 __fastcall Logger::Trace(int a1, const unsigned __int16 *a2, va_list a3)
{
  int v3; // ebx
  int v5; // edi
  int v6; // edi
  int v7; // edi
  __int64 *v8; // rdx
  unsigned __int16 *v10; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  v10 = 0;
  if ( UserDeviceRegistrationEventProvider_Context )
  {
    v3 = Logger::FormatString(&v10, a2, a3);
    if ( v3 >= 0 )
    {
      if ( !a1 )
      {
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 8) != 0 )
        {
          v8 = InformationDebugEvent;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      v5 = a1 - 1;
      if ( !v5 )
      {
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x10) != 0 )
        {
          v8 = WarningDebugEvent;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      v6 = v5 - 1;
      if ( !v6 )
      {
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x20) != 0 )
        {
          v8 = ErrorDebugEvent;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      v7 = v6 - 1;
      if ( !v7 )
      {
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x40) != 0 )
        {
          v8 = VerboseDebugEvent;
          goto LABEL_18;
        }
LABEL_19:
        v3 = 0;
        goto LABEL_20;
      }
      if ( v7 == 1 )
      {
        if ( Microsoft_Windows_User_Device_RegistrationEnableBits < 0 )
        {
          v8 = CriticalDebugEvent;
LABEL_18:
          v3 = McTemplateU0z_EventWriteTransfer(&UserDeviceRegistrationEventProvider_Context, v8, v10);
          goto LABEL_20;
        }
        goto LABEL_19;
      }
    }
  }
LABEL_20:
  SafeFree(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002f28  mov     [rsp+arg_0], rbx
0x180002f2d  push    rdi
0x180002f2e  sub     rsp, 20h
0x180002f32  xor     ebx, ebx
0x180002f34  mov     edi, ecx
0x180002f36  cmp     cs:UserDeviceRegistrationEventProvider_Context, rbx
0x180002f3d  mov     [rsp+28h+arg_18], rbx
0x180002f42  jz      loc_180002FE3
0x180002f48  lea     rcx, [rsp+28h+arg_18]; unsigned __int16 **
0x180002f4d  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x180002f52  mov     ebx, eax
0x180002f54  test    eax, eax
0x180002f56  js      loc_180002FE3
0x180002f5c  test    edi, edi
0x180002f5e  jz      short loc_180002FBC
0x180002f60  sub     edi, 1
0x180002f63  jz      short loc_180002FAA
0x180002f65  sub     edi, 1
0x180002f68  jz      short loc_180002F98
0x180002f6a  sub     edi, 1
0x180002f6d  jz      short loc_180002F86
0x180002f6f  cmp     edi, 1
0x180002f72  jnz     short loc_180002FE3
0x180002f74  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 80h
0x180002f7b  jz      short loc_180002FE1
0x180002f7d  lea     rdx, CriticalDebugEvent
0x180002f84  jmp     short loc_180002FCC
0x180002f86  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 40h
0x180002f8d  jz      short loc_180002FE1
0x180002f8f  lea     rdx, VerboseDebugEvent
0x180002f96  jmp     short loc_180002FCC
0x180002f98  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 20h
0x180002f9f  jz      short loc_180002FE1
0x180002fa1  lea     rdx, ErrorDebugEvent
0x180002fa8  jmp     short loc_180002FCC
0x180002faa  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 10h
0x180002fb1  jz      short loc_180002FE1
0x180002fb3  lea     rdx, WarningDebugEvent
0x180002fba  jmp     short loc_180002FCC
0x180002fbc  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 8
0x180002fc3  jz      short loc_180002FE1
0x180002fc5  lea     rdx, InformationDebugEvent
0x180002fcc  mov     r8, [rsp+28h+arg_18]
0x180002fd1  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180002fd8  call    McTemplateU0z_EventWriteTransfer
0x180002fdd  mov     ebx, eax
0x180002fdf  jmp     short loc_180002FE3
0x180002fe1  xor     ebx, ebx
0x180002fe3  mov     rcx, [rsp+28h+arg_18]; void *
0x180002fe8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180002fed  mov     eax, ebx
0x180002fef  mov     rbx, [rsp+28h+arg_0]
0x180002ff4  add     rsp, 20h
0x180002ff8  pop     rdi
0x180002ff9  retn
```
