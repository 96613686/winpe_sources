# PwrshPlugInMediator::CreateCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,ushort const *,_WSMAN_COMMAND_ARG_SET *)

- ea: `0x180002560`
- end: `0x1800025ca`
- name: `?CreateCommand@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAXPEBGPEAU_WSMAN_COMMAND_ARG_SET@@@Z`
- size: `106`
- prototype: `void __fastcall(void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, const unsigned __int16 *, struct _WSMAN_COMMAND_ARG_SET *), struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, const unsigned __int16 *, struct _WSMAN_COMMAND_ARG_SET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004530`

## callees

- `0x180002560`
- `0x180004050`
- `0x18000b010`

## string_xrefs

- `0x180002571`: `WSManPluginCommand`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::CreateCommand(
        void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, const unsigned __int16 *, struct _WSMAN_COMMAND_ARG_SET *),
        struct _WSMAN_PLUGIN_REQUEST *a2,
        __int64 a3,
        void *a4,
        const unsigned __int16 *a5,
        struct _WSMAN_COMMAND_ARG_SET *a6)
{
  if ( a2 )
  {
    if ( this[3] )
      this[3]((PwrshPlugInMediator *)this, a2, a3, a4, a5, a6);
    else
      PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, a2, 0x805403EB, a4, a5, a6);
  }
  else
  {
    PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, 0, 0x805403EA, L"WSManPluginCommand", a5, a6);
  }
}

```

## disassembly

```asm
0x180002560  mov     [rsp+arg_8], rdx
0x180002565  sub     rsp, 58h
0x180002569  mov     rax, rcx
0x18000256c  test    rdx, rdx
0x18000256f  jnz     short loc_180002587
0x180002571  lea     r9, aWsmanplugincom_1; "WSManPluginCommand"
0x180002578  mov     r8d, 805403EAh; unsigned int
0x18000257e  add     rsp, 58h
0x180002582  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180002587  cmp     qword ptr [rcx+18h], 0
0x18000258c  jnz     short loc_18000259D
0x18000258e  mov     r8d, 805403EBh; unsigned int
0x180002594  add     rsp, 58h
0x180002598  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x18000259d  mov     rcx, [rsp+58h+arg_28]
0x1800025a5  mov     [rsp+58h+var_30], rcx
0x1800025aa  mov     rcx, [rsp+58h+arg_20]
0x1800025b2  mov     [rsp+58h+var_38], rcx
0x1800025b7  mov     rcx, rax
0x1800025ba  mov     rax, [rax+18h]
0x1800025be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c3  jmp     short $+2
0x1800025c5  add     rsp, 58h
0x1800025c9  retn
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
