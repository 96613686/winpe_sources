# WppCleanupKm

- ea: `0x14000e818`
- end: `0x14000e894`
- name: `WppCleanupKm`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e0ec`
- `0x14000e760`

## callees

- `0x140005ef0`
- `0x14000e818`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000e84d`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000e84d`

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
0x14000e818  mov     [rsp+arg_0], rbx
0x14000e81d  push    rdi
0x14000e81e  sub     rsp, 20h
0x14000e822  mov     rbx, cs:WPP_GLOBAL_Control
0x14000e829  lea     rdi, WPP_GLOBAL_Control
0x14000e830  cmp     rbx, rdi
0x14000e833  jz      short loc_14000E860
0x14000e835  mov     eax, cs:WPPTraceSuite
0x14000e83b  cmp     eax, 4
0x14000e83e  jz      short loc_14000E88D
0x14000e840  cmp     eax, 2
0x14000e843  jnz     short loc_14000E859
0x14000e845  mov     edx, 80000002h; Action
0x14000e84a  mov     rcx, rbx; DeviceObject
0x14000e84d  call    cs:__imp_IoWMIRegistrationControl
0x14000e854  nop     dword ptr [rax+rax+00h]
0x14000e859  mov     cs:WPP_GLOBAL_Control, rdi
0x14000e860  mov     rbx, [rsp+28h+arg_0]
0x14000e865  add     rsp, 20h
0x14000e869  pop     rdi
0x14000e86a  retn
0x14000e86c  mov     rcx, [rbx+38h]
0x14000e870  test    rcx, rcx
0x14000e873  jz      short loc_14000E889
0x14000e875  mov     rax, cs:pfnEtwUnregister
0x14000e87c  call    _guard_dispatch_icall
0x14000e881  mov     qword ptr [rbx+38h], 0
0x14000e889  mov     rbx, [rbx+10h]
0x14000e88d  test    rbx, rbx
0x14000e890  jnz     short loc_14000E86C
0x14000e892  jmp     short loc_14000E859
```
