# SEHWrap_TextStoreBase<BasicDocTraitsAnchor>::RetrieveRequestedAttrs(ulong,TS_ATTRVAL *,ulong *)

- ea: `0x18000aff8`
- end: `0x18000b01a`
- name: `?RetrieveRequestedAttrs@?$SEHWrap_TextStoreBase@VBasicDocTraitsAnchor@@@@QEAAJKPEAUTS_ATTRVAL@@PEAK@Z`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180006208`
- `0x180007810`
- `0x18000ab80`
- `0x18000b040`

## callees

- `0x180008930`
- `0x18000aff8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SEHWrap_TextStoreBase<BasicDocTraitsAnchor>::RetrieveRequestedAttrs(_QWORD *a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 152LL))(*a1);
}

```

## disassembly

```asm
0x18000aff8  sub     rsp, 38h
0x18000affc  mov     rcx, [rcx]
0x18000afff  mov     rax, [rcx]
0x18000b002  mov     rax, [rax+98h]
0x18000b009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00e  jmp     short loc_18000B015
0x18000b010  mov     eax, 80004005h
0x18000b015  add     rsp, 38h
0x18000b019  retn
0x1800137a4  push    rbp
0x1800137a6  sub     rsp, 30h
0x1800137aa  mov     rbp, rdx
0x1800137ad  mov     rcx, [rcx]
0x1800137b0  mov     ecx, [rcx]; unsigned int
0x1800137b2  lea     rdx, aRetrievereques; "RetrieveRequestedAttrs"
0x1800137b9  call    ?HandleException@@YAXKPEBG@Z; HandleException(ulong,ushort const *)
0x1800137be  mov     eax, 1
0x1800137c3  add     rsp, 30h
0x1800137c7  pop     rbp
0x1800137c8  retn
```
