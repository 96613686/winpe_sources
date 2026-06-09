# NbtPnPPowerComplete

- ea: `0x140050ff0`
- end: `0x140051032`
- name: `NbtPnPPowerComplete`
- size: `66`
- prototype: `void __stdcall(PNET_PNP_EVENT NetEvent, NTSTATUS ProviderStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140040294`
- `0x140050ff0`

## import_xrefs

- `TDI!TdiPnPPowerComplete` at `0x140051001`
- `TDI!TdiPnPPowerComplete` at `0x140051001`

## pseudocode

```c
void __fastcall NbtPnPPowerComplete(PNET_PNP_EVENT NetEvent, NTSTATUS ProviderStatus)
{
  TdiPnPPowerComplete(TdiClientHandle, NetEvent, ProviderStatus);
  if ( (BYTE3(xmmword_140038420) & 1) != 0 )
    WPP_SF_(1048, 55, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
}

```

## disassembly

```asm
0x140050ff0  sub     rsp, 28h
0x140050ff4  mov     r8d, edx; Status
0x140050ff7  mov     rdx, rcx; PowerEvent
0x140050ffa  mov     rcx, cs:TdiClientHandle; BindingHandle
0x140051001  call    cs:__imp_TdiPnPPowerComplete
0x140051008  nop     dword ptr [rax+rax+00h]
0x14005100d  test    byte ptr cs:xmmword_140038420+3, 1
0x140051014  jz      short loc_14005102C
0x140051016  mov     edx, 37h ; '7'
0x14005101b  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x140051022  mov     ecx, 418h
0x140051027  call    WPP_SF_
0x14005102c  add     rsp, 28h
0x140051030  retn
```
