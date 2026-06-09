# NptrigDeleteLock

- ea: `0x140008394`
- end: `0x1400083aa`
- name: `NptrigDeleteLock`
- size: `22`
- prototype: `void __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b080`

## import_xrefs

- `FLTMGR!FltDeletePushLock` at `0x140008398`
- `FLTMGR!FltDeletePushLock` at `0x140008398`

## pseudocode

```c
void __fastcall NptrigDeleteLock(unsigned __int64 *a1)
{
  FltDeletePushLock(a1);
}

```

## disassembly

```asm
0x140008394  sub     rsp, 28h
0x140008398  call    cs:__imp_FltDeletePushLock
0x14000839f  nop     dword ptr [rax+rax+00h]
0x1400083a4  add     rsp, 28h
0x1400083a8  retn
```
