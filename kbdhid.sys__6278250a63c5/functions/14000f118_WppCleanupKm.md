# WppCleanupKm

- ea: `0x14000f118`
- end: `0x14000f1c5`
- name: `WppCleanupKm`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f0e0`
- `0x140011168`

## callees

- `0x140007170`
- `0x14000f118`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000f155`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000f155`
- `WppRecorder!WppAutoLogStop` at `0x14000f16b`
- `WppRecorder!WppAutoLogStop` at `0x14000f16b`

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
0x14000f118  mov     [rsp+arg_0], rbx
0x14000f11d  mov     [rsp+arg_8], rsi
0x14000f122  push    rdi
0x14000f123  sub     rsp, 20h
0x14000f127  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f12e  lea     rsi, WPP_GLOBAL_Control
0x14000f135  mov     rdi, rcx
0x14000f138  cmp     rbx, rsi
0x14000f13b  jz      short loc_14000F18C
0x14000f13d  mov     eax, cs:WPPTraceSuite
0x14000f143  cmp     eax, 4
0x14000f146  jz      short loc_14000F1BE
0x14000f148  cmp     eax, 2
0x14000f14b  jnz     short loc_14000F161
0x14000f14d  mov     edx, 80000002h; Action
0x14000f152  mov     rcx, rbx; DeviceObject
0x14000f155  call    cs:__imp_IoWMIRegistrationControl
0x14000f15c  nop     dword ptr [rax+rax+00h]
0x14000f161  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f168  mov     rdx, rdi
0x14000f16b  call    cs:__imp_WppAutoLogStop
0x14000f172  nop     dword ptr [rax+rax+00h]
0x14000f177  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f17e  mov     cs:WPP_GLOBAL_Control, rsi
0x14000f185  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f18c  mov     rbx, [rsp+28h+arg_0]
0x14000f191  mov     rsi, [rsp+28h+arg_8]
0x14000f196  add     rsp, 20h
0x14000f19a  pop     rdi
0x14000f19b  retn
0x14000f19d  mov     rcx, [rbx+38h]
0x14000f1a1  test    rcx, rcx
0x14000f1a4  jz      short loc_14000F1BA
0x14000f1a6  mov     rax, cs:pfnEtwUnregister
0x14000f1ad  call    _guard_dispatch_icall
0x14000f1b2  mov     qword ptr [rbx+38h], 0
0x14000f1ba  mov     rbx, [rbx+10h]
0x14000f1be  test    rbx, rbx
0x14000f1c1  jnz     short loc_14000F19D
0x14000f1c3  jmp     short loc_14000F161
```
