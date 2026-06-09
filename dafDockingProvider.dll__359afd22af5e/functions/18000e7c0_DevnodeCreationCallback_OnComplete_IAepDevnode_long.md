# DevnodeCreationCallback::OnComplete(IAepDevnode *,long)

- ea: `0x18000e7c0`
- end: `0x18000e7c9`
- name: `?OnComplete@DevnodeCreationCallback@@UEAAJPEAUIAepDevnode@@J@Z`
- size: `9`
- prototype: `__int64 __fastcall(DockCache ***this, struct IAepDevnode *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e7d0`

## pseudocode

```c
__int64 __fastcall DevnodeCreationCallback::OnComplete(DockCache ***this, struct IAepDevnode *a2, int a3)
{
  return CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated(this[2], a2, a3);
}

```

## disassembly

```asm
0x18000e7c0  mov     rcx, [rcx+10h]; this
0x18000e7c4  jmp     ?OnDevnodeCreated@CWiGigDAFProviderDevnodeManagement@@QEAAJPEAUIAepDevnode@@J@Z; CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated(IAepDevnode *,long)
```
