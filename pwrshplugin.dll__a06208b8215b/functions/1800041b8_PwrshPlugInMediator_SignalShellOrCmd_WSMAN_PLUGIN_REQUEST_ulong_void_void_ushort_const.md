# PwrshPlugInMediator::SignalShellOrCmd(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,ushort const *)

- ea: `0x1800041b8`
- end: `0x180004222`
- name: `?SignalShellOrCmd@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEBG@Z`
- size: `106`
- prototype: `void __fastcall(void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, const unsigned __int16 *), struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004900`

## callees

- `0x180004050`
- `0x1800041b8`
- `0x18000b010`

## import_xrefs

- `WsmSvc!WSManPluginOperationComplete` at `0x180009a54`
- `WsmSvc!WSManPluginOperationComplete` at `0x180009a54`

## string_xrefs

- `0x1800041c9`: `WSManPluginSignal`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::SignalShellOrCmd(
        void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, const unsigned __int16 *),
        struct _WSMAN_PLUGIN_REQUEST *a2,
        __int64 a3,
        void *a4,
        void *a5,
        const unsigned __int16 *a6)
{
  if ( a2 )
  {
    if ( this[7] )
      this[7]((PwrshPlugInMediator *)this, a2, a3, a4, a5, a6);
    else
      PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, a2, 0x805403EB, a4, a5, a6);
  }
  else
  {
    PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, 0, 0x805403EA, L"WSManPluginSignal", a5, a6);
  }
}

```

## disassembly

```asm
0x1800041b8  mov     [rsp+arg_8], rdx
0x1800041bd  sub     rsp, 58h
0x1800041c1  mov     rax, rcx
0x1800041c4  test    rdx, rdx
0x1800041c7  jnz     short loc_1800041DF
0x1800041c9  lea     r9, aWsmanpluginsig_1; "WSManPluginSignal"
0x1800041d0  mov     r8d, 805403EAh; unsigned int
0x1800041d6  add     rsp, 58h
0x1800041da  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x1800041df  cmp     qword ptr [rcx+38h], 0
0x1800041e4  jnz     short loc_1800041F5
0x1800041e6  mov     r8d, 805403EBh; unsigned int
0x1800041ec  add     rsp, 58h
0x1800041f0  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x1800041f5  mov     rcx, [rsp+58h+arg_28]
0x1800041fd  mov     [rsp+58h+var_30], rcx
0x180004202  mov     rcx, [rsp+58h+arg_20]
0x18000420a  mov     [rsp+58h+var_38], rcx
0x18000420f  mov     rcx, rax
0x180004212  mov     rax, [rax+38h]
0x180004216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000421b  jmp     short $+2
0x18000421d  add     rsp, 58h
0x180004221  retn
0x180009a36  push    rbp
0x180009a38  sub     rsp, 40h
0x180009a3c  mov     rbp, rdx
0x180009a3f  mov     rax, [rcx]
0x180009a42  mov     ecx, [rax]
0x180009a44  mov     [rbp+40h], ecx
0x180009a47  xor     r9d, r9d; extendedInformation
0x180009a4a  mov     r8d, [rbp+40h]; errorCode
0x180009a4e  xor     edx, edx; flags
0x180009a50  mov     rcx, [rbp+68h]; requestDetails
0x180009a54  call    cs:__imp_WSManPluginOperationComplete
0x180009a5a  mov     dword ptr [rbp+48h], 0FFFFFFFFh
0x180009a61  mov     eax, [rbp+48h]
0x180009a64  add     rsp, 40h
0x180009a68  pop     rbp
0x180009a69  retn
```
