# WSManPluginCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,ushort const *,_WSMAN_COMMAND_ARG_SET *)

- ea: `0x180004530`
- end: `0x18000457f`
- name: `?WSManPluginCommand@@YAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAXPEBGPEAU_WSMAN_COMMAND_ARG_SET@@@Z`
- size: `79`
- prototype: `void __fastcall(struct _WSMAN_PLUGIN_REQUEST *, unsigned int, void *, const unsigned __int16 *, struct _WSMAN_COMMAND_ARG_SET *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002560`
- `0x180002fac`

## pseudocode

```c
void __fastcall WSManPluginCommand(
        struct _WSMAN_PLUGIN_REQUEST *a1,
        unsigned int a2,
        void *a3,
        const unsigned __int16 *a4,
        struct _WSMAN_COMMAND_ARG_SET *a5)
{
  PwrshPlugInMediator *PwrshPlugInMediator; // rax
  DWORD v10; // edi
  _QWORD *v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF

  try
  {
    PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
    PwrshPlugInMediator::CreateCommand(PwrshPlugInMediator, a1, a2, a3, a4, a5);
  }
  catch ( PlugInException *v12 )
  {
    v10 = 1101;
    v11 = (_QWORD *)v12;
    if ( v12 )
    {
      v10 = *(_DWORD *)v12;
      if ( *(_QWORD *)(v12 + 8) )
      {
        operator delete[](*(void **)(v12 + 8));
        v11[1] = 0;
      }
      operator delete(v11);
    }
    ReportOperationComplete(a1, v10);
  }
}

```

## disassembly

```asm
0x180004530  mov     [rsp+arg_0], rcx
0x180004535  push    rbx
0x180004536  push    rsi
0x180004537  push    rdi
0x180004538  push    r14
0x18000453a  sub     rsp, 48h
0x18000453e  mov     rdi, r9
0x180004541  mov     rsi, r8
0x180004544  mov     r14d, edx
0x180004547  mov     rbx, rcx
0x18000454a  xor     ecx, ecx; unsigned __int16 *
0x18000454c  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004551  mov     r10, [rsp+68h+arg_20]
0x180004559  mov     [rsp+68h+var_40], r10; struct _WSMAN_COMMAND_ARG_SET *
0x18000455e  mov     [rsp+68h+var_48], rdi; unsigned __int16 *
0x180004563  mov     r9, rsi; void *
0x180004566  mov     r8d, r14d; unsigned int
0x180004569  mov     rdx, rbx; struct _WSMAN_PLUGIN_REQUEST *
0x18000456c  mov     rcx, rax; this
0x18000456f  call    ?CreateCommand@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAXPEBGPEAU_WSMAN_COMMAND_ARG_SET@@@Z; PwrshPlugInMediator::CreateCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,ushort const *,_WSMAN_COMMAND_ARG_SET *)
0x180004574  nop
0x180004575  add     rsp, 48h
0x180004579  pop     r14
0x18000457b  pop     rdi
0x18000457c  pop     rsi
0x18000457d  pop     rbx
0x18000457e  retn
```
