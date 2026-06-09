# basessp::WSTFreeList(basessp::_WST_LIST *)

- ea: `0x18001e1c0`
- end: `0x18001e1d8`
- name: `?WSTFreeList@basessp@@YAXPEAU_WST_LIST@1@@Z`
- size: `24`
- prototype: `void __fastcall(basessp *__hidden this, struct basessp::_WST_LIST *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800190c8`

## callees

- `0x18001e1c0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18001e1cd`
- `ntdll!RtlDeleteCriticalSection` at `0x18001e1cd`

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
0x18001e1c0  sub     rsp, 28h
0x18001e1c4  cmp     [rcx], rcx
0x18001e1c7  jnz     short loc_18001E1D3
0x18001e1c9  add     rcx, 10h; CriticalSection
0x18001e1cd  call    cs:__imp_RtlDeleteCriticalSection
0x18001e1d3  add     rsp, 28h
0x18001e1d7  retn
```
