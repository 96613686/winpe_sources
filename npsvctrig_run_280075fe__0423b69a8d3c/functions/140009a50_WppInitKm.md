# WppInitKm

- ea: `0x140009a50`
- end: `0x140009aeb`
- name: `WppInitKm`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b080`

## callees

- `0x140001b80`
- `0x140009a50`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x140009ad8`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140009ad8`

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
0x140009a50  push    rbx
0x140009a52  sub     rsp, 30h
0x140009a56  lea     rbx, WPP_MAIN_CB
0x140009a5d  cmp     cs:WPP_GLOBAL_Control, rbx
0x140009a64  jz      short loc_140009AE4
0x140009a66  mov     eax, cs:WPPTraceSuite
0x140009a6c  mov     cs:WPP_GLOBAL_Control, rbx
0x140009a73  cmp     eax, 4
0x140009a76  jnz     short loc_140009ABD
0x140009a78  mov     [rsp+38h+arg_0], rdi
0x140009a7d  xor     edi, edi
0x140009a7f  nop
0x140009a80  mov     rax, cs:pfnEtwRegisterClassicProvider
0x140009a87  lea     rcx, [rbx+38h]
0x140009a8b  mov     [rcx], rdi
0x140009a8e  lea     r8, WppClassicProviderCallback
0x140009a95  mov     [rsp+38h+var_18], rcx
0x140009a9a  mov     r9, rbx
0x140009a9d  mov     rcx, [rbx+8]
0x140009aa1  xor     edx, edx
0x140009aa3  call    _guard_dispatch_icall
0x140009aa8  mov     rbx, [rbx+10h]
0x140009aac  test    rbx, rbx
0x140009aaf  jnz     short loc_140009A80
0x140009ab1  mov     rdi, [rsp+38h+arg_0]
0x140009ab6  add     rsp, 30h
0x140009aba  pop     rbx
0x140009abb  retn
0x140009abd  cmp     eax, 2
0x140009ac0  jnz     short loc_140009AE4
0x140009ac2  lea     rax, WppTraceCallback
0x140009ac9  mov     edx, 80010001h; Action
0x140009ace  mov     rcx, rbx; DeviceObject
0x140009ad1  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x140009ad8  call    cs:__imp_IoWMIRegistrationControl
0x140009adf  nop     dword ptr [rax+rax+00h]
0x140009ae4  add     rsp, 30h
0x140009ae8  pop     rbx
0x140009ae9  retn
```
