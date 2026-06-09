# PwrshPlugInMediator::CreateShell(PwrshPlugIn *,_WSMAN_PLUGIN_REQUEST *,ulong,_WSMAN_SHELL_STARTUP_INFO_V10 *,_WSMAN_DATA *)

- ea: `0x180002980`
- end: `0x180002a0f`
- name: `?CreateShell@PwrshPlugInMediator@@QEAAXPEAVPwrshPlugIn@@PEAU_WSMAN_PLUGIN_REQUEST@@KPEAU_WSMAN_SHELL_STARTUP_INFO_V10@@PEAU_WSMAN_DATA@@@Z`
- size: `143`
- prototype: `void __fastcall(PwrshPlugInMediator *this, struct PwrshPlugIn *, struct _WSMAN_PLUGIN_REQUEST *, unsigned int, struct _WSMAN_SHELL_STARTUP_INFO_V10 *, struct _WSMAN_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004750`

## callees

- `0x180002980`
- `0x180004050`
- `0x18000b010`

## import_xrefs

- `WsmSvc!WSManPluginOperationComplete` at `0x180009a8f`
- `WsmSvc!WSManPluginOperationComplete` at `0x180009a8f`

## string_xrefs

- `0x1800029f5`: `WSManPluginShell`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::CreateShell(
        PwrshPlugInMediator *this,
        struct PwrshPlugIn *a2,
        struct _WSMAN_PLUGIN_REQUEST *a3,
        unsigned int a4,
        struct _WSMAN_SHELL_STARTUP_INFO_V10 *a5,
        struct _WSMAN_DATA *a6)
{
  if ( a2 && a3 && a5 && a3->operationInfo )
  {
    if ( *((_QWORD *)this + 1) )
      (*((void (__fastcall **)(PwrshPlugInMediator *, struct _WSMAN_PLUGIN_REQUEST *, _QWORD, _QWORD, struct _WSMAN_SHELL_STARTUP_INFO_V10 *, struct _WSMAN_DATA *))this
       + 1))(
        this,
        a3,
        a4,
        *((_QWORD *)a2 + 1),
        a5,
        a6);
    else
      PwrshPlugInMediator::ReportError(this, a3, 0x805403EB);
  }
  else
  {
    PwrshPlugInMediator::ReportError(this, a3, 0x805403EA, L"WSManPluginShell");
  }
}

```

## disassembly

```asm
0x180002980  mov     [rsp+arg_10], r8
0x180002985  sub     rsp, 58h
0x180002989  mov     r11d, r9d
0x18000298c  mov     rax, r8
0x18000298f  mov     r10, rcx
0x180002992  test    rdx, rdx
0x180002995  jz      short loc_1800029F5
0x180002997  test    rax, rax
0x18000299a  jz      short loc_1800029F5
0x18000299c  mov     r8, [rsp+58h+arg_20]
0x1800029a4  test    r8, r8
0x1800029a7  jz      short loc_1800029F5
0x1800029a9  cmp     qword ptr [rax+18h], 0
0x1800029ae  jz      short loc_1800029F5
0x1800029b0  cmp     qword ptr [rcx+8], 0
0x1800029b5  jnz     short loc_1800029C9
0x1800029b7  mov     r8d, 805403EBh; unsigned int
0x1800029bd  mov     rdx, rax; struct _WSMAN_PLUGIN_REQUEST *
0x1800029c0  add     rsp, 58h
0x1800029c4  jmp     ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x1800029c9  mov     rcx, [rsp+58h+arg_28]
0x1800029d1  mov     [rsp+58h+var_30], rcx
0x1800029d6  mov     [rsp+58h+var_38], r8
0x1800029db  mov     r9, [rdx+8]
0x1800029df  mov     r8d, r11d
0x1800029e2  mov     rdx, rax
0x1800029e5  mov     rcx, r10
0x1800029e8  mov     rax, [r10+8]
0x1800029ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f1  jmp     short loc_180002A0A
0x1800029f3  jmp     short loc_180002A0A
0x1800029f5  lea     r9, aWsmanpluginshe_1; "WSManPluginShell"
0x1800029fc  mov     r8d, 805403EAh; unsigned int
0x180002a02  mov     rdx, rax; struct _WSMAN_PLUGIN_REQUEST *
0x180002a05  call    ?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ; PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)
0x180002a0a  add     rsp, 58h
0x180002a0e  retn
0x180009a71  push    rbp
0x180009a73  sub     rsp, 40h
0x180009a77  mov     rbp, rdx
0x180009a7a  mov     rax, [rcx]
0x180009a7d  mov     ecx, [rax]
0x180009a7f  mov     [rbp+40h], ecx
0x180009a82  xor     r9d, r9d; extendedInformation
0x180009a85  mov     r8d, [rbp+40h]; errorCode
0x180009a89  xor     edx, edx; flags
0x180009a8b  mov     rcx, [rbp+70h]; requestDetails
0x180009a8f  call    cs:__imp_WSManPluginOperationComplete
0x180009a95  mov     dword ptr [rbp+48h], 0FFFFFFFFh
0x180009a9c  mov     eax, [rbp+48h]
0x180009a9f  add     rsp, 40h
0x180009aa3  pop     rbp
0x180009aa4  retn
```
