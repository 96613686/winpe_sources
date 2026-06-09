# SEHWrap_TextStoreBase<BasicDocTraitsAnchor>::RequestAttrsAtPosition(IAnchor *,ulong,_GUID const *,ulong)

- ea: `0x18000aa60`
- end: `0x18000aa92`
- name: `?RequestAttrsAtPosition@?$SEHWrap_TextStoreBase@VBasicDocTraitsAnchor@@@@QEAAJPEAUIAnchor@@KPEBU_GUID@@K@Z`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007810`
- `0x18000aac0`
- `0x18000ab80`

## callees

- `0x180008930`
- `0x18000aa60`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SEHWrap_TextStoreBase<BasicDocTraitsAnchor>::RequestAttrsAtPosition(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, int))(*(_QWORD *)*a1 + 128LL))(
           *a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000aa60  sub     rsp, 38h
0x18000aa64  mov     r10, r9
0x18000aa67  mov     rcx, [rcx]
0x18000aa6a  mov     rax, [rcx]
0x18000aa6d  mov     r9d, [rsp+38h+arg_20]
0x18000aa72  mov     [rsp+38h+var_18], r9d
0x18000aa77  mov     r9, r10
0x18000aa7a  mov     rax, [rax+80h]
0x18000aa81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa86  jmp     short loc_18000AA8D
0x18000aa88  mov     eax, 80004005h
0x18000aa8d  add     rsp, 38h
0x18000aa91  retn
0x1800136e2  push    rbp
0x1800136e4  sub     rsp, 30h
0x1800136e8  mov     rbp, rdx
0x1800136eb  mov     rcx, [rcx]
0x1800136ee  mov     ecx, [rcx]; unsigned int
0x1800136f0  lea     rdx, aRequestattrsat; "RequestAttrsAtPosition"
0x1800136f7  call    ?HandleException@@YAXKPEBG@Z; HandleException(ulong,ushort const *)
0x1800136fc  mov     eax, 1
0x180013701  add     rsp, 30h
0x180013705  pop     rbp
0x180013706  retn
```
