# WppCleanupKm

- ea: `0x14000b044`
- end: `0x14000b0f1`
- name: `WppCleanupKm`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b010`
- `0x14000d078`

## callees

- `0x140004e10`
- `0x14000b044`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b081`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b081`
- `WppRecorder!WppAutoLogStop` at `0x14000b097`
- `WppRecorder!WppAutoLogStop` at `0x14000b097`

## pseudocode

```c
void __fastcall WppCleanupKm(__int64 a1)
{
  PDEVICE_OBJECT v1; // rbx

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPPTraceSuite == 4 )
    {
      while ( v1 )
      {
        if ( v1->Vpb )
        {
          ((void (*)(void))pfnEtwUnregister)();
          v1->Vpb = 0;
        }
        v1 = v1->NextDevice;
      }
    }
    else if ( WPPTraceSuite == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    WppAutoLogStop(WPP_GLOBAL_Control, a1);
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
  }
}

```

## disassembly

```asm
0x14000b044  mov     [rsp+arg_0], rbx
0x14000b049  mov     [rsp+arg_8], rsi
0x14000b04e  push    rdi
0x14000b04f  sub     rsp, 20h
0x14000b053  mov     rbx, cs:WPP_GLOBAL_Control
0x14000b05a  lea     rsi, WPP_GLOBAL_Control
0x14000b061  mov     rdi, rcx
0x14000b064  cmp     rbx, rsi
0x14000b067  jz      short loc_14000B0B8
0x14000b069  mov     eax, cs:WPPTraceSuite
0x14000b06f  cmp     eax, 4
0x14000b072  jz      short loc_14000B0EA
0x14000b074  cmp     eax, 2
0x14000b077  jnz     short loc_14000B08D
0x14000b079  mov     edx, 80000002h; Action
0x14000b07e  mov     rcx, rbx; DeviceObject
0x14000b081  call    cs:__imp_IoWMIRegistrationControl
0x14000b088  nop     dword ptr [rax+rax+00h]
0x14000b08d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b094  mov     rdx, rdi
0x14000b097  call    cs:__imp_WppAutoLogStop
0x14000b09e  nop     dword ptr [rax+rax+00h]
0x14000b0a3  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b0aa  mov     cs:WPP_GLOBAL_Control, rsi
0x14000b0b1  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b0b8  mov     rbx, [rsp+28h+arg_0]
0x14000b0bd  mov     rsi, [rsp+28h+arg_8]
0x14000b0c2  add     rsp, 20h
0x14000b0c6  pop     rdi
0x14000b0c7  retn
0x14000b0c9  mov     rcx, [rbx+38h]
0x14000b0cd  test    rcx, rcx
0x14000b0d0  jz      short loc_14000B0E6
0x14000b0d2  mov     rax, cs:pfnEtwUnregister
0x14000b0d9  call    _guard_dispatch_icall
0x14000b0de  mov     qword ptr [rbx+38h], 0
0x14000b0e6  mov     rbx, [rbx+10h]
0x14000b0ea  test    rbx, rbx
0x14000b0ed  jnz     short loc_14000B0C9
0x14000b0ef  jmp     short loc_14000B08D
```
