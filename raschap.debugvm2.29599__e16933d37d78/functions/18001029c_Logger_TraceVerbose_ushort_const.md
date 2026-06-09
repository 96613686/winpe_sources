# Logger::TraceVerbose(ushort const *,...)

- ea: `0x18001029c`
- end: `0x18001031a`
- name: `?TraceVerbose@Logger@@SAJPEBGZZ`
- size: `126`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003530`
- `0x18000f8b8`
- `0x180010048`
- `0x180013084`
- `0x1800246a0`
- `0x180024a28`
- `0x180024c04`
- `0x18002572c`
- `0x18002594c`
- `0x180025bd4`
- `0x180025c90`

## callees

- `0x18001029c`
- `0x180010320`
- `0x1800252e0`
- `0x1800255ec`

## pseudocode

```c
__int64 Logger::TraceVerbose(const unsigned __int16 *a1, ...)
{
  signed int v1; // ebx
  void *v3; // [rsp+20h] [rbp-18h] BYREF
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  v1 = 0;
  v3 = 0;
  if ( UserDeviceRegistrationEventProvider_Context )
  {
    v1 = Logger::FormatString((unsigned __int16 **)&v3, a1, va);
    if ( v1 >= 0 )
    {
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x40) != 0 )
        v1 = McTemplateU0z_EventWriteTransfer(
               (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
               (const EVENT_DESCRIPTOR *)VerboseDebugEvent,
               (const wchar_t *)v3);
      else
        v1 = 0;
    }
  }
  SafeFree(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001029c  mov     rax, rsp
0x18001029f  mov     [rax+8], rcx
0x1800102a3  mov     [rax+10h], rdx
0x1800102a7  mov     [rax+18h], r8
0x1800102ab  mov     [rax+20h], r9
0x1800102af  push    rbx
0x1800102b0  sub     rsp, 30h
0x1800102b4  xor     ebx, ebx
0x1800102b6  mov     qword ptr [rax-18h], 0
0x1800102be  cmp     cs:UserDeviceRegistrationEventProvider_Context, rbx
0x1800102c5  lea     r8, [rax+10h]; char *
0x1800102c9  mov     [rax-18h], rbx
0x1800102cd  jz      short loc_180010308
0x1800102cf  mov     rdx, rcx; unsigned __int16 *
0x1800102d2  lea     rcx, [rax-18h]; unsigned __int16 **
0x1800102d6  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x1800102db  mov     ebx, eax
0x1800102dd  test    eax, eax
0x1800102df  js      short loc_180010308
0x1800102e1  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 40h
0x1800102e8  jz      short loc_180010306
0x1800102ea  mov     r8, [rsp+38h+var_18]
0x1800102ef  lea     rdx, VerboseDebugEvent
0x1800102f6  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x1800102fd  call    McTemplateU0z_EventWriteTransfer
0x180010302  mov     ebx, eax
0x180010304  jmp     short loc_180010308
0x180010306  xor     ebx, ebx
0x180010308  mov     rcx, [rsp+38h+var_18]; void *
0x18001030d  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180010312  mov     eax, ebx
0x180010314  add     rsp, 30h
0x180010318  pop     rbx
0x180010319  retn
```
