# WppInitKm

- ea: `0x14000a1a4`
- end: `0x14000a231`
- name: `WppInitKm`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c078`

## callees

- `0x140003e00`
- `0x14000a1a4`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a21e`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a21e`

## pseudocode

```c
void WppInitKm()
{
  struct _DEVICE_OBJECT *v0; // rbx
  void (__fastcall *v1)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *); // rax

  v0 = &WPP_MAIN_CB;
  if ( WPP_GLOBAL_Control != &WPP_MAIN_CB )
  {
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    if ( WPPTraceSuite == 4 )
    {
      do
      {
        v1 = (void (__fastcall *)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *))pfnEtwRegisterClassicProvider;
        v0->Vpb = 0;
        v1(v0->DriverObject, 0, WppClassicProviderCallback, v0, &v0->Vpb);
        v0 = v0->NextDevice;
      }
      while ( v0 );
    }
    else if ( WPPTraceSuite == 2 )
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = &WppTraceCallback;
      IoWMIRegistrationControl(&WPP_MAIN_CB, 0x80010001);
    }
  }
}

```

## disassembly

```asm
0x14000a1a4  push    rbx
0x14000a1a6  sub     rsp, 30h
0x14000a1aa  lea     rbx, WPP_MAIN_CB
0x14000a1b1  cmp     cs:WPP_GLOBAL_Control, rbx
0x14000a1b8  jz      short loc_14000A22A
0x14000a1ba  mov     eax, cs:WPPTraceSuite
0x14000a1c0  mov     cs:WPP_GLOBAL_Control, rbx
0x14000a1c7  cmp     eax, 4
0x14000a1ca  jnz     short loc_14000A203
0x14000a1cc  mov     rax, cs:pfnEtwRegisterClassicProvider
0x14000a1d3  lea     rcx, [rbx+38h]
0x14000a1d7  mov     qword ptr [rcx], 0
0x14000a1de  lea     r8, WppClassicProviderCallback
0x14000a1e5  mov     [rsp+38h+var_18], rcx
0x14000a1ea  mov     r9, rbx
0x14000a1ed  mov     rcx, [rbx+8]
0x14000a1f1  xor     edx, edx
0x14000a1f3  call    _guard_dispatch_icall
0x14000a1f8  mov     rbx, [rbx+10h]
0x14000a1fc  test    rbx, rbx
0x14000a1ff  jnz     short loc_14000A1CC
0x14000a201  jmp     short loc_14000A22A
0x14000a203  cmp     eax, 2
0x14000a206  jnz     short loc_14000A22A
0x14000a208  lea     rax, WppTraceCallback
0x14000a20f  mov     edx, 80010001h; Action
0x14000a214  mov     rcx, rbx; DeviceObject
0x14000a217  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x14000a21e  call    cs:__imp_IoWMIRegistrationControl
0x14000a225  nop     dword ptr [rax+rax+00h]
0x14000a22a  add     rsp, 30h
0x14000a22e  pop     rbx
0x14000a22f  retn
```
