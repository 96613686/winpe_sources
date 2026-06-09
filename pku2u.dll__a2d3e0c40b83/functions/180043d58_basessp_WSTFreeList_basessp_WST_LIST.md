# basessp::WSTFreeList(basessp::_WST_LIST *)

- ea: `0x180043d58`
- end: `0x180043d70`
- name: `?WSTFreeList@basessp@@YAXPEAU_WST_LIST@1@@Z`
- size: `24`
- prototype: `void __fastcall(basessp *__hidden this, struct basessp::_WST_LIST *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002f40c`

## callees

- `0x180043d58`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180043d65`
- `ntdll!RtlDeleteCriticalSection` at `0x180043d65`

## pseudocode

```c
void __fastcall basessp::WSTFreeList(basessp *this, struct basessp::_WST_LIST *a2)
{
  if ( *(basessp **)this == this )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180043d58  sub     rsp, 28h
0x180043d5c  cmp     [rcx], rcx
0x180043d5f  jnz     short loc_180043D6B
0x180043d61  add     rcx, 10h; CriticalSection
0x180043d65  call    cs:__imp_RtlDeleteCriticalSection
0x180043d6b  add     rsp, 28h
0x180043d6f  retn
```
