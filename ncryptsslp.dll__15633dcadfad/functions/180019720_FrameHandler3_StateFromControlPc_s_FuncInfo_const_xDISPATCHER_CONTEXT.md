# __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)

- ea: `0x180019720`
- end: `0x180019728`
- name: `?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(const struct _s_FuncInfo *, struct _xDISPATCHER_CONTEXT *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180018f58`
- `0x180018f88`
- `0x180018ffc`
- `0x1800190d4`
- `0x18001aa9c`

## callees

- `0x180019730`

## pseudocode

```c
__int64 __fastcall __FrameHandler3::StateFromControlPc(const struct _s_FuncInfo *a1, struct _xDISPATCHER_CONTEXT *a2)
{
  return __FrameHandler3::StateFromIp(a1, a2, a2->ControlPc);
}

```

## disassembly

```asm
0x180019720  mov     r8, [rdx]; unsigned __int64
0x180019723  jmp     ?StateFromIp@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@_K@Z; __FrameHandler3::StateFromIp(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *,unsigned __int64)
```
