# MupGetContainerContextFromThread

- ea: `0x14001d260`
- end: `0x14001d301`
- name: `MupGetContainerContextFromThread`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001ce70`

## callees

- `0x140002e74`
- `0x14001d260`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001d292`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001d292`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001d2a6`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001d2a6`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x14001d26d`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x14001d26d`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001d284`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001d284`

## pseudocode

```c
__int64 __fastcall MupGetContainerContextFromThread(_QWORD *a1)
{
  unsigned int SiloMonitorContextSlot; // ebx
  __int64 CurrentServerSilo; // rax
  unsigned int PermanentSiloContext; // ebx

  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
  {
    SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(ContainerMonitor);
    CurrentServerSilo = PsGetCurrentServerSilo();
    PermanentSiloContext = PsGetPermanentSiloContext(CurrentServerSilo, SiloMonitorContextSlot, a1);
    if ( PermanentSiloContext
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_c898274d75623dfd801520d1a3be50ef_Traceguids,
        PermanentSiloContext);
    }
  }
  else
  {
    PermanentSiloContext = 0;
    *a1 = 0;
  }
  return PermanentSiloContext;
}

```

## disassembly

```asm
0x14001d260  mov     [rsp+arg_0], rbx
0x14001d265  push    rdi
0x14001d266  sub     rsp, 20h
0x14001d26a  mov     rdi, rcx
0x14001d26d  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x14001d274  nop     dword ptr [rax+rax+00h]
0x14001d279  test    al, al
0x14001d27b  jz      short loc_14001D2EE
0x14001d27d  mov     rcx, cs:ContainerMonitor
0x14001d284  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001d28b  nop     dword ptr [rax+rax+00h]
0x14001d290  mov     ebx, eax
0x14001d292  call    cs:__imp_PsGetCurrentServerSilo
0x14001d299  nop     dword ptr [rax+rax+00h]
0x14001d29e  mov     r8, rdi
0x14001d2a1  mov     edx, ebx
0x14001d2a3  mov     rcx, rax
0x14001d2a6  call    cs:__imp_PsGetPermanentSiloContext
0x14001d2ad  nop     dword ptr [rax+rax+00h]
0x14001d2b2  mov     ebx, eax
0x14001d2b4  test    eax, eax
0x14001d2b6  jz      short loc_14001D2F3
0x14001d2b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d2bf  lea     rax, WPP_GLOBAL_Control
0x14001d2c6  cmp     rcx, rax
0x14001d2c9  jz      short loc_14001D2F3
0x14001d2cb  test    dword ptr [rcx+2Ch], 1000000h
0x14001d2d2  jz      short loc_14001D2F3
0x14001d2d4  mov     rcx, [rcx+18h]
0x14001d2d8  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x14001d2df  mov     edx, 13h
0x14001d2e4  mov     r9d, ebx
0x14001d2e7  call    WPP_SF_d
0x14001d2ec  jmp     short loc_14001D2F3
0x14001d2ee  xor     ebx, ebx
0x14001d2f0  mov     [rdi], rbx
0x14001d2f3  mov     eax, ebx
0x14001d2f5  mov     rbx, [rsp+28h+arg_0]
0x14001d2fa  add     rsp, 20h
0x14001d2fe  pop     rdi
0x14001d2ff  retn
```
