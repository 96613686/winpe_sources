# FxStubDriverUnloadCommon(void)

- ea: `0x140027760`
- end: `0x140027790`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `48`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400277d4`
- `0x140027940`
- `0x140027960`

## callees

- `0x140027c00`
- `0x140027d0a`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  FxStubUnbindClasses((struct _WDF_BIND_INFO *)&WdfBindInfo);
  WdfVersionUnbind_0(&DestinationString, &WdfBindInfo, WdfDriverGlobals);
}

```

## disassembly

```asm
0x140027760  sub     rsp, 28h
0x140027764  lea     rcx, WdfBindInfo; struct _WDF_BIND_INFO *
0x14002776b  call    ?FxStubUnbindClasses@@YAXPEAU_WDF_BIND_INFO@@@Z; FxStubUnbindClasses(_WDF_BIND_INFO *)
0x140027770  mov     r8, cs:WdfDriverGlobals
0x140027777  lea     rdx, WdfBindInfo
0x14002777e  lea     rcx, DestinationString
0x140027785  call    WdfVersionUnbind_0
0x14002778a  add     rsp, 28h
0x14002778e  retn
```
