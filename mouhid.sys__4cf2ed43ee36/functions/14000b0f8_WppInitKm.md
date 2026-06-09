# WppInitKm

- ea: `0x14000b0f8`
- end: `0x14000b1b8`
- name: `WppInitKm`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d078`

## callees

- `0x140004e10`
- `0x14000b0f8`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b182`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b182`
- `WppRecorder!WppAutoLogStart` at `0x14000b19b`
- `WppRecorder!WppAutoLogStart` at `0x14000b19b`

## pseudocode

```c
void __fastcall WppInitKm(__int64 a1, __int64 a2)
{
  struct _DEVICE_OBJECT *v4; // rbx
  void (__fastcall *v5)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *); // rax

  if ( WPP_GLOBAL_Control != &WPP_MAIN_CB )
  {
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    if ( WPPTraceSuite == 4 )
    {
      v4 = &WPP_MAIN_CB;
      do
      {
        v5 = (void (__fastcall *)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *))pfnEtwRegisterClassicProvider;
        v4->Vpb = 0;
        v5(v4->DriverObject, 0, WppClassicProviderCallback, v4, &v4->Vpb);
        v4 = v4->NextDevice;
      }
      while ( v4 );
    }
    else if ( WPPTraceSuite == 2 )
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = WppTraceCallback;
      IoWMIRegistrationControl(&WPP_MAIN_CB, 0x80010001);
    }
    WppAutoLogStart(WPP_GLOBAL_Control, a1, a2);
    WPP_RECORDER_INITIALIZED = &WPP_MAIN_CB;
  }
}

```

## disassembly

```asm
0x14000b0f8  push    rbx
0x14000b0fa  push    rbp
0x14000b0fb  push    rsi
0x14000b0fc  push    rdi
0x14000b0fd  sub     rsp, 38h
0x14000b101  lea     rbp, WPP_MAIN_CB
0x14000b108  mov     rdi, rdx
0x14000b10b  cmp     cs:WPP_GLOBAL_Control, rbp
0x14000b112  mov     rsi, rcx
0x14000b115  jz      loc_14000B1AE
0x14000b11b  mov     eax, cs:WPPTraceSuite
0x14000b121  mov     cs:WPP_GLOBAL_Control, rbp
0x14000b128  cmp     eax, 4
0x14000b12b  jnz     short loc_14000B167
0x14000b12d  mov     rbx, rbp
0x14000b130  mov     rax, cs:pfnEtwRegisterClassicProvider
0x14000b137  lea     rcx, [rbx+38h]
0x14000b13b  mov     qword ptr [rcx], 0
0x14000b142  lea     r8, WppClassicProviderCallback
0x14000b149  mov     [rsp+58h+var_38], rcx
0x14000b14e  mov     r9, rbx
0x14000b151  mov     rcx, [rbx+8]
0x14000b155  xor     edx, edx
0x14000b157  call    _guard_dispatch_icall
0x14000b15c  mov     rbx, [rbx+10h]
0x14000b160  test    rbx, rbx
0x14000b163  jnz     short loc_14000B130
0x14000b165  jmp     short loc_14000B18E
0x14000b167  cmp     eax, 2
0x14000b16a  jnz     short loc_14000B18E
0x14000b16c  lea     rax, WppTraceCallback
0x14000b173  mov     edx, 80010001h; Action
0x14000b178  mov     rcx, rbp; DeviceObject
0x14000b17b  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x14000b182  call    cs:__imp_IoWMIRegistrationControl
0x14000b189  nop     dword ptr [rax+rax+00h]
0x14000b18e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b195  mov     r8, rdi
0x14000b198  mov     rdx, rsi
0x14000b19b  call    cs:__imp_WppAutoLogStart
0x14000b1a2  nop     dword ptr [rax+rax+00h]
0x14000b1a7  mov     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000b1ae  add     rsp, 38h
0x14000b1b2  pop     rdi
0x14000b1b3  pop     rsi
0x14000b1b4  pop     rbp
0x14000b1b5  pop     rbx
0x14000b1b6  retn
```
