# WSManPluginConnect(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,_WSMAN_DATA *)

- ea: `0x180004590`
- end: `0x1800045df`
- name: `?WSManPluginConnect@@YAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEAU_WSMAN_DATA@@@Z`
- size: `79`
- prototype: `void __fastcall(struct _WSMAN_PLUGIN_REQUEST *, unsigned int, void *, void *, struct _WSMAN_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002a88`
- `0x180002fac`

## pseudocode

```c
void __fastcall WSManPluginConnect(
        struct _WSMAN_PLUGIN_REQUEST *a1,
        unsigned int a2,
        void *a3,
        void *a4,
        struct _WSMAN_DATA *a5)
{
  PwrshPlugInMediator *PwrshPlugInMediator; // rax
  DWORD v10; // edi
  _QWORD *v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF

  try
  {
    PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
    PwrshPlugInMediator::ExecuteConnectToShellOrCommand(PwrshPlugInMediator, a1, a2, a3, a4, a5);
  }
  catch ( PlugInException *v12 )
  {
    v10 = -2141977623;
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
0x180004590  mov     [rsp+arg_0], rcx
0x180004595  push    rbx
0x180004596  push    rsi
0x180004597  push    rdi
0x180004598  push    r14
0x18000459a  sub     rsp, 48h
0x18000459e  mov     rdi, r9
0x1800045a1  mov     rsi, r8
0x1800045a4  mov     r14d, edx
0x1800045a7  mov     rbx, rcx
0x1800045aa  xor     ecx, ecx; unsigned __int16 *
0x1800045ac  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x1800045b1  mov     r10, [rsp+68h+arg_20]
0x1800045b9  mov     [rsp+68h+var_40], r10; struct _WSMAN_DATA *
0x1800045be  mov     [rsp+68h+var_48], rdi; void *
0x1800045c3  mov     r9, rsi; void *
0x1800045c6  mov     r8d, r14d; unsigned int
0x1800045c9  mov     rdx, rbx; struct _WSMAN_PLUGIN_REQUEST *
0x1800045cc  mov     rcx, rax; this
0x1800045cf  call    ?ExecuteConnectToShellOrCommand@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEAU_WSMAN_DATA@@@Z; PwrshPlugInMediator::ExecuteConnectToShellOrCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,_WSMAN_DATA *)
0x1800045d4  nop
0x1800045d5  add     rsp, 48h
0x1800045d9  pop     r14
0x1800045db  pop     rdi
0x1800045dc  pop     rsi
0x1800045dd  pop     rbx
0x1800045de  retn
```
