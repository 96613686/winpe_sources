# CTaskHandler::MaintenanceModeWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong)

- ea: `0x180006520`
- end: `0x180006570`
- name: `?MaintenanceModeWaitCallback@CTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `80`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD **Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea4`
- `0x180006520`
- `0x18000b010`

## pseudocode

```c
void __fastcall CTaskHandler::MaintenanceModeWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD **Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids);
  (*(void (__fastcall **)(_QWORD *, _QWORD, PTP_WAIT, __int64))(*Context[8] + 32LL))(Context[8], 0, Wait, WaitResult);
}

```

## disassembly

```asm
0x180006520  push    rbx
0x180006522  sub     rsp, 20h
0x180006526  mov     rbx, rdx
0x180006529  lea     rax, WPP_GLOBAL_Control
0x180006530  mov     rcx, cs:WPP_GLOBAL_Control
0x180006537  cmp     rcx, rax
0x18000653a  jz      short loc_180006557
0x18000653c  test    byte ptr [rcx+1Ch], 8
0x180006540  jz      short loc_180006557
0x180006542  mov     edx, 17h
0x180006547  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x18000654e  mov     rcx, [rcx+10h]
0x180006552  call    WPP_SF_
0x180006557  mov     rcx, [rbx+40h]
0x18000655b  mov     rax, [rcx]
0x18000655e  xor     edx, edx
0x180006560  mov     rax, [rax+20h]
0x180006564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006569  nop
0x18000656a  add     rsp, 20h
0x18000656e  pop     rbx
0x18000656f  retn
```
