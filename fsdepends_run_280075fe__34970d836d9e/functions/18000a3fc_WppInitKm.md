# WppInitKm

- ea: `0x18000a3fc`
- end: `0x18000a489`
- name: `WppInitKm`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013078`

## callees

- `0x180001fb0`
- `0x18000a3fc`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x18000a476`
- `ntoskrnl!IoWMIRegistrationControl` at `0x18000a476`

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
0x18000a3fc  push    rbx
0x18000a3fe  sub     rsp, 30h
0x18000a402  lea     rbx, WPP_MAIN_CB
0x18000a409  cmp     cs:WPP_GLOBAL_Control, rbx
0x18000a410  jz      short loc_18000A482
0x18000a412  mov     eax, cs:WPPTraceSuite
0x18000a418  mov     cs:WPP_GLOBAL_Control, rbx
0x18000a41f  cmp     eax, 4
0x18000a422  jnz     short loc_18000A45B
0x18000a424  mov     rax, cs:pfnEtwRegisterClassicProvider
0x18000a42b  lea     rcx, [rbx+38h]
0x18000a42f  mov     qword ptr [rcx], 0
0x18000a436  lea     r8, WppClassicProviderCallback
0x18000a43d  mov     [rsp+38h+var_18], rcx
0x18000a442  mov     r9, rbx
0x18000a445  mov     rcx, [rbx+8]
0x18000a449  xor     edx, edx
0x18000a44b  call    _guard_dispatch_icall
0x18000a450  mov     rbx, [rbx+10h]
0x18000a454  test    rbx, rbx
0x18000a457  jnz     short loc_18000A424
0x18000a459  jmp     short loc_18000A482
0x18000a45b  cmp     eax, 2
0x18000a45e  jnz     short loc_18000A482
0x18000a460  lea     rax, WppTraceCallback
0x18000a467  mov     edx, 80010001h; Action
0x18000a46c  mov     rcx, rbx; DeviceObject
0x18000a46f  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x18000a476  call    cs:__imp_IoWMIRegistrationControl
0x18000a47d  nop     dword ptr [rax+rax+00h]
0x18000a482  add     rsp, 30h
0x18000a486  pop     rbx
0x18000a487  retn
```
