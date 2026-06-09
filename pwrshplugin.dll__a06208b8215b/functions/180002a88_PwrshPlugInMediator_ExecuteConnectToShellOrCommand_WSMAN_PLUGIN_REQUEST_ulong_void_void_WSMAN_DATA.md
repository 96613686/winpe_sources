# PwrshPlugInMediator::ExecuteConnectToShellOrCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,_WSMAN_DATA *)

- ea: `0x180002a88`
- end: `0x180002af2`
- name: `?ExecuteConnectToShellOrCommand@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEAU_WSMAN_DATA@@@Z`
- size: `106`
- prototype: `void __fastcall(void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, struct _WSMAN_DATA *), struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, struct _WSMAN_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004590`

## callees

- `0x180002a88`
- `0x180004050`
- `0x18000b010`

## string_xrefs

- `0x180002a99`: `WSManPluginConnect`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::ExecuteConnectToShellOrCommand(
        void (__fastcall **this)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, __int64, void *, void *, struct _WSMAN_DATA *),
        struct _WSMAN_PLUGIN_REQUEST *a2,
        __int64 a3,
        void *a4,
        void *a5,
        struct _WSMAN_DATA *a6)
{
  if ( a2 )
  {
    if ( this[8] )
      this[8]((PwrshPlugInMediator *)this, a2, a3, a4, a5, a6);
    else
      PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, a2, 0x805403F1, a4, a5, a6);
  }
  else
  {
    PwrshPlugInMediator::ReportError((PwrshPlugInMediator *)this, 0, 0x805403EA, L"WSManPluginConnect", a5, a6);
  }
}

```

## disassembly

```asm
0x180002a88  mov     [rsp+arg_8], rdx
0x180002a8d  sub     rsp, 58h
0x180002a91  mov     rax, rcx
0x180002a94  test    rdx, rdx
0x180002a97  jnz     short loc_180002AAF
0x180002a99  lea     r9, aWsmanplugincon_0; "WSManPluginConnect"
0x180002aa0  mov     r8d, 805403EAh; unsigned int
0x180002aa6  add     rsp, 58h
0x180002aaa  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180002aaf  cmp     qword ptr [rcx+40h], 0
0x180002ab4  jnz     short loc_180002AC5
0x180002ab6  mov     r8d, 805403F1h; unsigned int
0x180002abc  add     rsp, 58h
0x180002ac0  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180002ac5  mov     rcx, [rsp+58h+arg_28]
0x180002acd  mov     [rsp+58h+var_30], rcx
0x180002ad2  mov     rcx, [rsp+58h+arg_20]
0x180002ada  mov     [rsp+58h+var_38], rcx
0x180002adf  mov     rcx, rax
0x180002ae2  mov     rax, [rax+40h]
0x180002ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aeb  jmp     short $+2
0x180002aed  add     rsp, 58h
0x180002af1  retn
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
