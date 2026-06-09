# SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a300`
- end: `0x18000a31e`
- name: `?QueryInterface@?$SEHWrap_IUnknown@UITextStoreACP@@@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a330`
- `0x18000c250`
- `0x18000c4a0`

## callees

- `0x180008930`
- `0x18000a300`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(_QWORD *a1)
{
  return (**(__int64 (__fastcall ***)(_QWORD))*a1)(*a1);
}

```

## disassembly

```asm
0x18000a300  sub     rsp, 28h
0x18000a304  mov     rcx, [rcx]
0x18000a307  mov     rax, [rcx]
0x18000a30a  mov     rax, [rax]
0x18000a30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a312  jmp     short loc_18000A319
0x18000a314  mov     eax, 80004005h
0x18000a319  add     rsp, 28h
0x18000a31d  retn
0x180013678  push    rbp
0x18001367a  sub     rsp, 20h
0x18001367e  mov     rbp, rdx
0x180013681  mov     rcx, [rcx]
0x180013684  mov     ecx, [rcx]; unsigned int
0x180013686  lea     rdx, aQueryinterface; "QueryInterface"
0x18001368d  call    ?HandleException@@YAXKPEBG@Z; HandleException(ulong,ushort const *)
0x180013692  mov     eax, 1
0x180013697  add     rsp, 20h
0x18001369b  pop     rbp
0x18001369c  retn
```
