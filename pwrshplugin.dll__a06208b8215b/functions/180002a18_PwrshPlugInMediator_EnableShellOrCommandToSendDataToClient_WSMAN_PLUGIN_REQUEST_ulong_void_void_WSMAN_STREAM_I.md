# PwrshPlugInMediator::EnableShellOrCommandToSendDataToClient(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,_WSMAN_STREAM_ID_SET *)

- ea: `0x180002a18`
- end: `0x180002a82`
- name: `?EnableShellOrCommandToSendDataToClient@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEAU_WSMAN_STREAM_ID_SET@@@Z`
- size: `106`
- prototype: `void __fastcall(void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, struct _WSMAN_STREAM_ID_SET *), struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, struct _WSMAN_STREAM_ID_SET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800045f0`

## callees

- `0x180002a18`
- `0x180004050`
- `0x18000b010`

## string_xrefs

- `0x180002a29`: `WSManPluginReceive`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::EnableShellOrCommandToSendDataToClient(
        void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, struct _WSMAN_STREAM_ID_SET *),
        struct _WSMAN_PLUGIN_REQUEST *a2,
        __int64 a3,
        void *a4,
        void *a5,
        struct _WSMAN_STREAM_ID_SET *a6)
{
  if ( a2 )
  {
    if ( this[6] )
      this[6]((PwrshPlugInMediator *)this, a2, a3, a4, a5, a6);
    else
      PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, a2, 0x805403EB, a4, a5, a6);
  }
  else
  {
    PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, 0, 0x805403EA, L"WSManPluginReceive", a5, a6);
  }
}

```

## disassembly

```asm
0x180002a18  mov     [rsp+arg_8], rdx
0x180002a1d  sub     rsp, 58h
0x180002a21  mov     rax, rcx
0x180002a24  test    rdx, rdx
0x180002a27  jnz     short loc_180002A3F
0x180002a29  lea     r9, aWsmanpluginrec_0; "WSManPluginReceive"
0x180002a30  mov     r8d, 805403EAh; unsigned int
0x180002a36  add     rsp, 58h
0x180002a3a  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180002a3f  cmp     qword ptr [rcx+30h], 0
0x180002a44  jnz     short loc_180002A55
0x180002a46  mov     r8d, 805403EBh; unsigned int
0x180002a4c  add     rsp, 58h
0x180002a50  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180002a55  mov     rcx, [rsp+58h+arg_28]
0x180002a5d  mov     [rsp+58h+var_30], rcx
0x180002a62  mov     rcx, [rsp+58h+arg_20]
0x180002a6a  mov     [rsp+58h+var_38], rcx
0x180002a6f  mov     rcx, rax
0x180002a72  mov     rax, [rax+30h]
0x180002a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a7b  jmp     short $+2
0x180002a7d  add     rsp, 58h
0x180002a81  retn
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
