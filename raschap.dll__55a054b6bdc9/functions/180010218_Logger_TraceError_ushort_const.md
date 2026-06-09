# Logger::TraceError(ushort const *,...)

- ea: `0x180010218`
- end: `0x180010296`
- name: `?TraceError@Logger@@SAJPEBGZZ`
- size: `126`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `22`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003530`
- `0x18000fdf0`
- `0x18000febc`
- `0x18000ff18`
- `0x180010048`
- `0x180013084`
- `0x1800240ec`
- `0x1800241c0`
- `0x180024398`
- `0x180024618`
- `0x1800246a0`
- `0x180024834`
- `0x1800249d4`
- `0x180024a28`
- `0x180024c04`
- `0x180024ea8`
- `0x180025030`
- `0x1800251e8`
- `0x18002572c`
- `0x18002594c`
- `0x180025bd4`
- `0x180025c90`

## callees

- `0x180010218`
- `0x180010320`
- `0x1800252e0`
- `0x1800255ec`

## pseudocode

```c
__int64 Logger::TraceError(const unsigned __int16 *a1, ...)
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
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x20) != 0 )
        v1 = McTemplateU0z_EventWriteTransfer(
               (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
               (const EVENT_DESCRIPTOR *)ErrorDebugEvent,
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
0x180010218  mov     rax, rsp
0x18001021b  mov     [rax+8], rcx
0x18001021f  mov     [rax+10h], rdx
0x180010223  mov     [rax+18h], r8
0x180010227  mov     [rax+20h], r9
0x18001022b  push    rbx
0x18001022c  sub     rsp, 30h
0x180010230  xor     ebx, ebx
0x180010232  mov     qword ptr [rax-18h], 0
0x18001023a  cmp     cs:UserDeviceRegistrationEventProvider_Context, rbx
0x180010241  lea     r8, [rax+10h]; char *
0x180010245  mov     [rax-18h], rbx
0x180010249  jz      short loc_180010284
0x18001024b  mov     rdx, rcx; unsigned __int16 *
0x18001024e  lea     rcx, [rax-18h]; unsigned __int16 **
0x180010252  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x180010257  mov     ebx, eax
0x180010259  test    eax, eax
0x18001025b  js      short loc_180010284
0x18001025d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 20h
0x180010264  jz      short loc_180010282
0x180010266  mov     r8, [rsp+38h+var_18]
0x18001026b  lea     rdx, ErrorDebugEvent
0x180010272  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180010279  call    McTemplateU0z_EventWriteTransfer
0x18001027e  mov     ebx, eax
0x180010280  jmp     short loc_180010284
0x180010282  xor     ebx, ebx
0x180010284  mov     rcx, [rsp+38h+var_18]; void *
0x180010289  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18001028e  mov     eax, ebx
0x180010290  add     rsp, 30h
0x180010294  pop     rbx
0x180010295  retn
```
