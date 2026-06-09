# MupGetContainerContextFromThread

- ea: `0x14001d210`
- end: `0x14001d2b1`
- name: `MupGetContainerContextFromThread`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001ce20`

## callees

- `0x140002e74`
- `0x14001d210`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001d242`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001d242`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001d256`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001d256`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x14001d21d`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x14001d21d`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001d234`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001d234`

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
0x14001d210  mov     [rsp+arg_0], rbx
0x14001d215  push    rdi
0x14001d216  sub     rsp, 20h
0x14001d21a  mov     rdi, rcx
0x14001d21d  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x14001d224  nop     dword ptr [rax+rax+00h]
0x14001d229  test    al, al
0x14001d22b  jz      short loc_14001D29E
0x14001d22d  mov     rcx, cs:ContainerMonitor
0x14001d234  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001d23b  nop     dword ptr [rax+rax+00h]
0x14001d240  mov     ebx, eax
0x14001d242  call    cs:__imp_PsGetCurrentServerSilo
0x14001d249  nop     dword ptr [rax+rax+00h]
0x14001d24e  mov     r8, rdi
0x14001d251  mov     edx, ebx
0x14001d253  mov     rcx, rax
0x14001d256  call    cs:__imp_PsGetPermanentSiloContext
0x14001d25d  nop     dword ptr [rax+rax+00h]
0x14001d262  mov     ebx, eax
0x14001d264  test    eax, eax
0x14001d266  jz      short loc_14001D2A3
0x14001d268  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d26f  lea     rax, WPP_GLOBAL_Control
0x14001d276  cmp     rcx, rax
0x14001d279  jz      short loc_14001D2A3
0x14001d27b  test    dword ptr [rcx+2Ch], 1000000h
0x14001d282  jz      short loc_14001D2A3
0x14001d284  mov     rcx, [rcx+18h]
0x14001d288  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x14001d28f  mov     edx, 13h
0x14001d294  mov     r9d, ebx
0x14001d297  call    WPP_SF_d
0x14001d29c  jmp     short loc_14001D2A3
0x14001d29e  xor     ebx, ebx
0x14001d2a0  mov     [rdi], rbx
0x14001d2a3  mov     eax, ebx
0x14001d2a5  mov     rbx, [rsp+28h+arg_0]
0x14001d2aa  add     rsp, 20h
0x14001d2ae  pop     rdi
0x14001d2af  retn
```
