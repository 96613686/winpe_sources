# WSManPluginSignal(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,ushort const *)

- ea: `0x180004900`
- end: `0x18000494f`
- name: `?WSManPluginSignal@@YAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEBG@Z`
- size: `79`
- prototype: `void __fastcall(struct _WSMAN_PLUGIN_REQUEST *, unsigned int, void *, void *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002fac`
- `0x1800041b8`

## pseudocode

```c
void __fastcall WSManPluginSignal(
        struct _WSMAN_PLUGIN_REQUEST *a1,
        unsigned int a2,
        void *a3,
        void *a4,
        unsigned __int16 *a5)
{
  PwrshPlugInMediator *PwrshPlugInMediator; // rax

  PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
  PwrshPlugInMediator::SignalShellOrCmd(PwrshPlugInMediator, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180004900  mov     [rsp+arg_0], rcx
0x180004905  push    rbx
0x180004906  push    rsi
0x180004907  push    rdi
0x180004908  push    r14
0x18000490a  sub     rsp, 48h
0x18000490e  mov     rdi, r9
0x180004911  mov     rsi, r8
0x180004914  mov     r14d, edx
0x180004917  mov     rbx, rcx
0x18000491a  xor     ecx, ecx; unsigned __int16 *
0x18000491c  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004921  mov     r10, [rsp+68h+arg_20]
0x180004929  mov     [rsp+68h+var_40], r10; unsigned __int16 *
0x18000492e  mov     [rsp+68h+var_48], rdi; void *
0x180004933  mov     r9, rsi; void *
0x180004936  mov     r8d, r14d; unsigned int
0x180004939  mov     rdx, rbx; struct _WSMAN_PLUGIN_REQUEST *
0x18000493c  mov     rcx, rax; this
0x18000493f  call    ?SignalShellOrCmd@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEBG@Z; PwrshPlugInMediator::SignalShellOrCmd(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,ushort const *)
0x180004944  nop
0x180004945  add     rsp, 48h
0x180004949  pop     r14
0x18000494b  pop     rdi
0x18000494c  pop     rsi
0x18000494d  pop     rbx
0x18000494e  retn
```
