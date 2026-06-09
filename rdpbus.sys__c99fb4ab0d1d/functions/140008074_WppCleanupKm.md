# WppCleanupKm

- ea: `0x140008074`
- end: `0x1400080f0`
- name: `WppCleanupKm`
- size: `124`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008010`
- `0x14000b078`

## callees

- `0x140002560`
- `0x140008074`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x1400080a9`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400080a9`

## pseudocode

```c
void WppCleanupKm()
{
  PDEVICE_OBJECT v0; // rbx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPPTraceSuite == 4 )
    {
      while ( v0 )
      {
        if ( v0->Vpb )
        {
          ((void (*)(void))WPP_MAIN_CB.DeviceExtension)();
          v0->Vpb = 0;
        }
        v0 = v0->NextDevice;
      }
    }
    else if ( WPPTraceSuite == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x140008074  mov     [rsp+arg_0], rbx
0x140008079  push    rdi
0x14000807a  sub     rsp, 20h
0x14000807e  mov     rbx, cs:WPP_GLOBAL_Control
0x140008085  lea     rdi, WPP_GLOBAL_Control
0x14000808c  cmp     rbx, rdi
0x14000808f  jz      short loc_1400080BC
0x140008091  mov     eax, cs:WPPTraceSuite
0x140008097  cmp     eax, 4
0x14000809a  jz      short loc_1400080E9
0x14000809c  cmp     eax, 2
0x14000809f  jnz     short loc_1400080B5
0x1400080a1  mov     edx, 80000002h; Action
0x1400080a6  mov     rcx, rbx; DeviceObject
0x1400080a9  call    cs:__imp_IoWMIRegistrationControl
0x1400080b0  nop     dword ptr [rax+rax+00h]
0x1400080b5  mov     cs:WPP_GLOBAL_Control, rdi
0x1400080bc  mov     rbx, [rsp+28h+arg_0]
0x1400080c1  add     rsp, 20h
0x1400080c5  pop     rdi
0x1400080c6  retn
0x1400080c8  mov     rcx, [rbx+38h]
0x1400080cc  test    rcx, rcx
0x1400080cf  jz      short loc_1400080E5
0x1400080d1  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400080d8  call    _guard_dispatch_icall
0x1400080dd  mov     qword ptr [rbx+38h], 0
0x1400080e5  mov     rbx, [rbx+10h]
0x1400080e9  test    rbx, rbx
0x1400080ec  jnz     short loc_1400080C8
0x1400080ee  jmp     short loc_1400080B5
```
