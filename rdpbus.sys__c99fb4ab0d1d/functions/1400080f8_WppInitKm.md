# WppInitKm

- ea: `0x1400080f8`
- end: `0x140008185`
- name: `WppInitKm`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b078`

## callees

- `0x140002560`
- `0x1400080f8`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x140008172`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140008172`

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
0x1400080f8  push    rbx
0x1400080fa  sub     rsp, 30h
0x1400080fe  lea     rbx, WPP_MAIN_CB
0x140008105  cmp     cs:WPP_GLOBAL_Control, rbx
0x14000810c  jz      short loc_14000817E
0x14000810e  mov     eax, cs:WPPTraceSuite
0x140008114  mov     cs:WPP_GLOBAL_Control, rbx
0x14000811b  cmp     eax, 4
0x14000811e  jnz     short loc_140008157
0x140008120  mov     rax, cs:pfnEtwRegisterClassicProvider
0x140008127  lea     rcx, [rbx+38h]
0x14000812b  mov     qword ptr [rcx], 0
0x140008132  lea     r8, WppClassicProviderCallback
0x140008139  mov     [rsp+38h+var_18], rcx
0x14000813e  mov     r9, rbx
0x140008141  mov     rcx, [rbx+8]
0x140008145  xor     edx, edx
0x140008147  call    _guard_dispatch_icall
0x14000814c  mov     rbx, [rbx+10h]
0x140008150  test    rbx, rbx
0x140008153  jnz     short loc_140008120
0x140008155  jmp     short loc_14000817E
0x140008157  cmp     eax, 2
0x14000815a  jnz     short loc_14000817E
0x14000815c  lea     rax, WppTraceCallback
0x140008163  mov     edx, 80010001h; Action
0x140008168  mov     rcx, rbx; DeviceObject
0x14000816b  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x140008172  call    cs:__imp_IoWMIRegistrationControl
0x140008179  nop     dword ptr [rax+rax+00h]
0x14000817e  add     rsp, 30h
0x140008182  pop     rbx
0x140008183  retn
```
