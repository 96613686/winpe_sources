# FxStubDriverUnloadCommon(void)

- ea: `0x1400050cc`
- end: `0x1400050fc`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `48`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005144`
- `0x1400052c0`

## callees

- `0x140005454`

## import_xrefs

- `WDFLDR!WdfVersionUnbind` at `0x1400050ea`
- `WDFLDR!WdfVersionUnbind` at `0x1400050ea`

## pseudocode

```c
void __fastcall FxStubDriverUnloadCommon(struct _WDF_BIND_INFO *a1)
{
  FxStubUnbindClasses(a1);
  WdfVersionUnbind(&DestinationString, &WdfBindInfo, WdfDriverGlobals);
}

```

## disassembly

```asm
0x1400050cc  sub     rsp, 28h
0x1400050d0  call    ?FxStubUnbindClasses@@YAXPEAU_WDF_BIND_INFO@@@Z; FxStubUnbindClasses(_WDF_BIND_INFO *)
0x1400050d5  mov     r8, cs:WdfDriverGlobals
0x1400050dc  lea     rdx, WdfBindInfo
0x1400050e3  lea     rcx, DestinationString
0x1400050ea  call    cs:__imp_WdfVersionUnbind
0x1400050f1  nop     dword ptr [rax+rax+00h]
0x1400050f6  add     rsp, 28h
0x1400050fa  retn
```
