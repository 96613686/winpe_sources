# HsmFltDeleteFILE_CONTEXT

- ea: `0x14004c8e0`
- end: `0x14004c932`
- name: `HsmFltDeleteFILE_CONTEXT`
- size: `82`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x14001e2a0`
- `0x14004c8e0`
- `0x14004c938`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14004c90a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004c90a`
- `FLTMGR!FltReleaseContext` at `0x14004c91f`
- `FLTMGR!FltReleaseContext` at `0x14004c91f`

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
0x14004c8e0  push    rbx
0x14004c8e2  sub     rsp, 20h
0x14004c8e6  mov     rbx, rcx
0x14004c8e9  mov     rcx, [rcx+8]
0x14004c8ed  test    rcx, rcx
0x14004c8f0  jz      short loc_14004C8FE
0x14004c8f2  mov     rax, cs:qword_140029700
0x14004c8f9  call    _guard_dispatch_icall
0x14004c8fe  mov     rcx, rbx
0x14004c901  call    HsmpUninitializePropertyContext
0x14004c906  lea     rcx, [rbx+78h]; Resource
0x14004c90a  call    cs:__imp_ExDeleteResourceLite
0x14004c911  nop     dword ptr [rax+rax+00h]
0x14004c916  mov     rcx, [rbx+10h]; Context
0x14004c91a  test    rcx, rcx
0x14004c91d  jz      short loc_14004C92B
0x14004c91f  call    cs:__imp_FltReleaseContext
0x14004c926  nop     dword ptr [rax+rax+00h]
0x14004c92b  add     rsp, 20h
0x14004c92f  pop     rbx
0x14004c930  retn
```
