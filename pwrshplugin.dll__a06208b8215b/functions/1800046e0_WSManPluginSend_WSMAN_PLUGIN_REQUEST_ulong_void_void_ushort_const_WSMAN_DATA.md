# WSManPluginSend(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,ushort const *,_WSMAN_DATA *)

- ea: `0x1800046e0`
- end: `0x18000473c`
- name: `?WSManPluginSend@@YAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEBGPEAU_WSMAN_DATA@@@Z`
- size: `92`
- prototype: `void __fastcall(struct _WSMAN_PLUGIN_REQUEST *, unsigned int, void *, void *, unsigned __int16 *, struct _WSMAN_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002fac`
- `0x180004138`

## pseudocode

```c
void __fastcall WSManPluginSend(
        struct _WSMAN_PLUGIN_REQUEST *a1,
        unsigned int a2,
        void *a3,
        void *a4,
        unsigned __int16 *a5,
        struct _WSMAN_DATA *a6)
{
  PwrshPlugInMediator *PwrshPlugInMediator; // rax
  DWORD v11; // edi
  _QWORD *v12; // rbx
  __int64 v13; // [rsp+40h] [rbp-38h] BYREF

  try
  {
    PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
    PwrshPlugInMediator::SendOneItemToShellOrCommand(PwrshPlugInMediator, a1, a2, a3, a4, a5, a6);
  }
  catch ( PlugInException *v13 )
  {
    v11 = -2141977623;
    v12 = (_QWORD *)v13;
    if ( v13 )
    {
      v11 = *(_DWORD *)v13;
      if ( *(_QWORD *)(v13 + 8) )
      {
        operator delete[](*(void **)(v13 + 8));
        v12[1] = 0;
      }
      operator delete(v12);
    }
    ReportOperationComplete(a1, v11);
  }
}

```

## disassembly

```asm
0x1800046e0  mov     [rsp+arg_0], rcx
0x1800046e5  push    rbx
0x1800046e6  push    rsi
0x1800046e7  push    rdi
0x1800046e8  push    r14
0x1800046ea  sub     rsp, 58h
0x1800046ee  mov     rdi, r9
0x1800046f1  mov     rsi, r8
0x1800046f4  mov     r14d, edx
0x1800046f7  mov     rbx, rcx
0x1800046fa  xor     ecx, ecx; unsigned __int16 *
0x1800046fc  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004701  mov     r10, [rsp+78h+arg_28]
0x180004709  mov     [rsp+78h+var_48], r10; struct _WSMAN_DATA *
0x18000470e  mov     r8, [rsp+78h+arg_20]
0x180004716  mov     [rsp+78h+var_50], r8; unsigned __int16 *
0x18000471b  mov     [rsp+78h+var_58], rdi; void *
0x180004720  mov     r9, rsi; void *
0x180004723  mov     r8d, r14d; unsigned int
0x180004726  mov     rdx, rbx; struct _WSMAN_PLUGIN_REQUEST *
0x180004729  mov     rcx, rax; this
0x18000472c  call    ?SendOneItemToShellOrCommand@PwrshPlugInMediator@@QEAAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAX1PEBGPEAU_WSMAN_DATA@@@Z; PwrshPlugInMediator::SendOneItemToShellOrCommand(_WSMAN_PLUGIN_REQUEST *,ulong,void *,void *,ushort const *,_WSMAN_DATA *)
0x180004731  nop
0x180004732  add     rsp, 58h
0x180004736  pop     r14
0x180004738  pop     rdi
0x180004739  pop     rsi
0x18000473a  pop     rbx
0x18000473b  retn
```
