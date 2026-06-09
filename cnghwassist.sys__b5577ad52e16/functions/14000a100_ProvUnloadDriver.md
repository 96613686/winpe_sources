# ProvUnloadDriver

- ea: `0x14000a100`
- end: `0x14000a19e`
- name: `ProvUnloadDriver`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003e00`
- `0x14000a100`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a13e`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a13e`
- `ntoskrnl!IoDeleteDevice` at `0x14000a159`
- `ntoskrnl!IoDeleteDevice` at `0x14000a159`

## pseudocode

```c
void __fastcall ProvUnloadDriver(__int64 a1)
{
  PDEVICE_OBJECT v1; // rbx
  struct _DEVICE_OBJECT *v2; // rdi

  v1 = WPP_GLOBAL_Control;
  v2 = *(struct _DEVICE_OBJECT **)(a1 + 8);
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
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
  }
  if ( v2 )
    IoDeleteDevice(v2);
}

```

## disassembly

```asm
0x14000a100  mov     [rsp+arg_0], rbx
0x14000a105  mov     [rsp+arg_8], rsi
0x14000a10a  push    rdi
0x14000a10b  sub     rsp, 20h
0x14000a10f  mov     rbx, cs:WPP_GLOBAL_Control
0x14000a116  lea     rsi, WPP_GLOBAL_Control
0x14000a11d  mov     rdi, [rcx+8]
0x14000a121  cmp     rbx, rsi
0x14000a124  jz      short loc_14000A151
0x14000a126  mov     eax, cs:WPPTraceSuite
0x14000a12c  cmp     eax, 4
0x14000a12f  jz      short loc_14000A197
0x14000a131  cmp     eax, 2
0x14000a134  jnz     short loc_14000A14A
0x14000a136  mov     edx, 80000002h; Action
0x14000a13b  mov     rcx, rbx; DeviceObject
0x14000a13e  call    cs:__imp_IoWMIRegistrationControl
0x14000a145  nop     dword ptr [rax+rax+00h]
0x14000a14a  mov     cs:WPP_GLOBAL_Control, rsi
0x14000a151  test    rdi, rdi
0x14000a154  jz      short loc_14000A165
0x14000a156  mov     rcx, rdi; DeviceObject
0x14000a159  call    cs:__imp_IoDeleteDevice
0x14000a160  nop     dword ptr [rax+rax+00h]
0x14000a165  mov     rbx, [rsp+28h+arg_0]
0x14000a16a  mov     rsi, [rsp+28h+arg_8]
0x14000a16f  add     rsp, 20h
0x14000a173  pop     rdi
0x14000a174  retn
0x14000a176  mov     rcx, [rbx+38h]
0x14000a17a  test    rcx, rcx
0x14000a17d  jz      short loc_14000A193
0x14000a17f  mov     rax, cs:pfnEtwUnregister
0x14000a186  call    _guard_dispatch_icall
0x14000a18b  mov     qword ptr [rbx+38h], 0
0x14000a193  mov     rbx, [rbx+10h]
0x14000a197  test    rbx, rbx
0x14000a19a  jnz     short loc_14000A176
0x14000a19c  jmp     short loc_14000A14A
```
