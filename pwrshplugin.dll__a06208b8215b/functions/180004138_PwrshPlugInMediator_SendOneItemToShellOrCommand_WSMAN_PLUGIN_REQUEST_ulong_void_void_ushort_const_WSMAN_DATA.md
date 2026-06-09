# PwrshPlugInMediator::SendOneItemToShellOrCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,ushort const *,_WSMAN_DATA *)

- ea: `0x180004138`
- end: `0x1800041af`
- name: `?SendOneItemToShellOrCommand@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEBGPEAU_WSMAN_DATA@@@Z`
- size: `119`
- prototype: `void __fastcall(void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, const unsigned __int16 *, struct _WSMAN_DATA *), struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, const unsigned __int16 *, struct _WSMAN_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800046e0`

## callees

- `0x180004050`
- `0x180004138`
- `0x18000b010`

## string_xrefs

- `0x180004149`: `WSManPluginSend`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::SendOneItemToShellOrCommand(
        void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, const unsigned __int16 *, struct _WSMAN_DATA *),
        struct _WSMAN_PLUGIN_REQUEST *a2,
        __int64 a3,
        void *a4,
        void *a5,
        const unsigned __int16 *a6,
        struct _WSMAN_DATA *a7)
{
  if ( a2 )
  {
    if ( this[5] )
      this[5]((PwrshPlugInMediator *)this, a2, a3, a4, a5, a6, a7);
    else
      PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, a2, 0x805403EB, a4, a5, a6);
  }
  else
  {
    PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, 0, 0x805403EA, L"WSManPluginSend", a5, a6);
  }
}

```

## disassembly

```asm
0x180004138  mov     [rsp+arg_8], rdx
0x18000413d  sub     rsp, 58h
0x180004141  mov     rax, rcx
0x180004144  test    rdx, rdx
0x180004147  jnz     short loc_18000415F
0x180004149  lea     r9, aWsmanpluginsen_0; "WSManPluginSend"
0x180004150  mov     r8d, 805403EAh; unsigned int
0x180004156  add     rsp, 58h
0x18000415a  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x18000415f  cmp     qword ptr [rcx+28h], 0
0x180004164  jnz     short loc_180004175
0x180004166  mov     r8d, 805403EBh; unsigned int
0x18000416c  add     rsp, 58h
0x180004170  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180004175  mov     rcx, [rsp+58h+arg_30]
0x18000417d  mov     [rsp+58h+var_28], rcx
0x180004182  mov     rcx, [rsp+58h+arg_28]
0x18000418a  mov     [rsp+58h+var_30], rcx
0x18000418f  mov     rcx, [rsp+58h+arg_20]
0x180004197  mov     [rsp+58h+var_38], rcx
0x18000419c  mov     rcx, rax
0x18000419f  mov     rax, [rax+28h]
0x1800041a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a8  jmp     short $+2
0x1800041aa  add     rsp, 58h
0x1800041ae  retn
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
