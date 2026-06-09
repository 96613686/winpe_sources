# DhcpDeRegisterParamChange

- ea: `0x1800031c0`
- end: `0x180003200`
- name: `DhcpDeRegisterParamChange`
- size: `64`
- prototype: `DWORD __stdcall(DWORD Flags, LPVOID Reserved, LPVOID Event)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800031c0`
- `0x180003d50`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800031df`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800031df`

## pseudocode

```c
DWORD __stdcall DhcpDeRegisterParamChange(DWORD Flags, LPVOID Reserved, LPVOID Event)
{
  LPWSTR CommandLineW; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 124, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  return DhcpDeRegisterParameterChangeNotification(Event, (__int64)Reserved, (__int64)Event);
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  sub     rsp, 20h
0x1800031c6  mov     rbx, r8
0x1800031c9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800031d0  jnz     short loc_1800031DF
0x1800031d2  mov     rcx, rbx; hObject
0x1800031d5  add     rsp, 20h
0x1800031d9  pop     rbx
0x1800031da  jmp     DhcpDeRegisterParameterChangeNotification
0x1800031df  call    cs:__imp_GetCommandLineW
0x1800031e5  mov     edx, 7Ch ; '|'
0x1800031ea  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800031f1  mov     r9, rax
0x1800031f4  mov     ecx, 404h
0x1800031f9  call    WPP_SF_S
0x1800031fe  jmp     short loc_1800031D2
```
