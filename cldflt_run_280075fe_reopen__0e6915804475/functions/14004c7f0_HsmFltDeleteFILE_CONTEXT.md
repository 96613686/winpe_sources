# HsmFltDeleteFILE_CONTEXT

- ea: `0x14004c7f0`
- end: `0x14004c842`
- name: `HsmFltDeleteFILE_CONTEXT`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x14001e220`
- `0x14004c7f0`
- `0x14004c848`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14004c81a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004c81a`
- `FLTMGR!FltReleaseContext` at `0x14004c82f`
- `FLTMGR!FltReleaseContext` at `0x14004c82f`

## pseudocode

```c
void __fastcall HsmFltDeleteFILE_CONTEXT(__int64 a1)
{
  void *v2; // rcx

  if ( *(_QWORD *)(a1 + 8) )
    ((void (*)(void))qword_140029700)();
  HsmpUninitializePropertyContext(a1);
  ExDeleteResourceLite((PERESOURCE)(a1 + 120));
  v2 = *(void **)(a1 + 16);
  if ( v2 )
    FltReleaseContext(v2);
}

```

## disassembly

```asm
0x14004c7f0  push    rbx
0x14004c7f2  sub     rsp, 20h
0x14004c7f6  mov     rbx, rcx
0x14004c7f9  mov     rcx, [rcx+8]
0x14004c7fd  test    rcx, rcx
0x14004c800  jz      short loc_14004C80E
0x14004c802  mov     rax, cs:qword_140029700
0x14004c809  call    _guard_dispatch_icall
0x14004c80e  mov     rcx, rbx
0x14004c811  call    HsmpUninitializePropertyContext
0x14004c816  lea     rcx, [rbx+78h]; Resource
0x14004c81a  call    cs:__imp_ExDeleteResourceLite
0x14004c821  nop     dword ptr [rax+rax+00h]
0x14004c826  mov     rcx, [rbx+10h]; Context
0x14004c82a  test    rcx, rcx
0x14004c82d  jz      short loc_14004C83B
0x14004c82f  call    cs:__imp_FltReleaseContext
0x14004c836  nop     dword ptr [rax+rax+00h]
0x14004c83b  add     rsp, 20h
0x14004c83f  pop     rbx
0x14004c840  retn
```
