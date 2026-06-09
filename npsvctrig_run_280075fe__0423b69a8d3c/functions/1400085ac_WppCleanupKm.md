# WppCleanupKm

- ea: `0x1400085ac`
- end: `0x140008628`
- name: `WppCleanupKm`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008250`
- `0x14000b080`

## callees

- `0x140001b80`
- `0x1400085ac`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x1400085e1`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400085e1`

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
          ((void (*)(void))pfnEtwUnregister)();
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
0x1400085ac  mov     [rsp+arg_0], rbx
0x1400085b1  push    rdi
0x1400085b2  sub     rsp, 20h
0x1400085b6  mov     rbx, cs:WPP_GLOBAL_Control
0x1400085bd  lea     rdi, WPP_GLOBAL_Control
0x1400085c4  cmp     rbx, rdi
0x1400085c7  jz      short loc_1400085F4
0x1400085c9  mov     eax, cs:WPPTraceSuite
0x1400085cf  cmp     eax, 4
0x1400085d2  jz      short loc_140008621
0x1400085d4  cmp     eax, 2
0x1400085d7  jnz     short loc_1400085ED
0x1400085d9  mov     edx, 80000002h; Action
0x1400085de  mov     rcx, rbx; DeviceObject
0x1400085e1  call    cs:__imp_IoWMIRegistrationControl
0x1400085e8  nop     dword ptr [rax+rax+00h]
0x1400085ed  mov     cs:WPP_GLOBAL_Control, rdi
0x1400085f4  mov     rbx, [rsp+28h+arg_0]
0x1400085f9  add     rsp, 20h
0x1400085fd  pop     rdi
0x1400085fe  retn
0x140008600  mov     rcx, [rbx+38h]
0x140008604  test    rcx, rcx
0x140008607  jz      short loc_14000861D
0x140008609  mov     rax, cs:pfnEtwUnregister
0x140008610  call    _guard_dispatch_icall
0x140008615  mov     qword ptr [rbx+38h], 0
0x14000861d  mov     rbx, [rbx+10h]
0x140008621  test    rbx, rbx
0x140008624  jnz     short loc_140008600
0x140008626  jmp     short loc_1400085ED
```
