# NptrigDestroyFilterInstance

- ea: `0x1400083b0`
- end: `0x1400083cd`
- name: `NptrigDestroyFilterInstance`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `FLTMGR!FltDeletePushLock` at `0x1400083bb`
- `FLTMGR!FltDeletePushLock` at `0x1400083bb`

## pseudocode

```c
void __fastcall NptrigDestroyFilterInstance(__int64 a1)
{
  FltDeletePushLock((PULONG_PTR)(a1 + 152));
}

```

## disassembly

```asm
0x1400083b0  sub     rsp, 28h
0x1400083b4  add     rcx, 98h; PushLock
0x1400083bb  call    cs:__imp_FltDeletePushLock
0x1400083c2  nop     dword ptr [rax+rax+00h]
0x1400083c7  add     rsp, 28h
0x1400083cb  retn
```
