# WSManPluginReceive(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,_WSMAN_STREAM_ID_SET *)

- ea: `0x1800045f0`
- end: `0x18000463f`
- name: `?WSManPluginReceive@@YAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEAU_WSMAN_STREAM_ID_SET@@@Z`
- size: `79`
- prototype: `void __fastcall(struct _WSMAN_PLUGIN_REQUEST *, unsigned int, void *, void *, struct _WSMAN_STREAM_ID_SET *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a18`
- `0x180002fac`

## pseudocode

```c
void __fastcall WSManPluginReceive(
        struct _WSMAN_PLUGIN_REQUEST *a1,
        unsigned int a2,
        void *a3,
        void *a4,
        struct _WSMAN_STREAM_ID_SET *a5)
{
  PwrshPlugInMediator *PwrshPlugInMediator; // rax

  PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
  PwrshPlugInMediator::EnableShellOrCommandToSendDataToClient(PwrshPlugInMediator, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800045f0  mov     [rsp+arg_0], rcx
0x1800045f5  push    rbx
0x1800045f6  push    rsi
0x1800045f7  push    rdi
0x1800045f8  push    r14
0x1800045fa  sub     rsp, 48h
0x1800045fe  mov     rdi, r9
0x180004601  mov     rsi, r8
0x180004604  mov     r14d, edx
0x180004607  mov     rbx, rcx
0x18000460a  xor     ecx, ecx; unsigned __int16 *
0x18000460c  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004611  mov     r10, [rsp+68h+arg_20]
0x180004619  mov     [rsp+68h+var_40], r10; struct _WSMAN_STREAM_ID_SET *
0x18000461e  mov     [rsp+68h+var_48], rdi; void *
0x180004623  mov     r9, rsi; void *
0x180004626  mov     r8d, r14d; unsigned int
0x180004629  mov     rdx, rbx; struct _WSMAN_PLUGIN_REQUEST *
0x18000462c  mov     rcx, rax; this
0x18000462f  call    ?EnableShellOrCommandToSendDataToClient@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEAU_WSMAN_STREAM_ID_SET@@@Z; PwrshPlugInMediator::EnableShellOrCommandToSendDataToClient(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,_WSMAN_STREAM_ID_SET *)
0x180004634  nop
0x180004635  add     rsp, 48h
0x180004639  pop     r14
0x18000463b  pop     rdi
0x18000463c  pop     rsi
0x18000463d  pop     rbx
0x18000463e  retn
```
