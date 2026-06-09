# CloseTransport

- ea: `0x140018620`
- end: `0x140018670`
- name: `CloseTransport`
- size: `80`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140018e08`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001863b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001863b`

## pseudocode

```c
__int64 __fastcall CloseTransport(PVOID Entry, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdx

  v3 = *(_QWORD *)(a2 + 24);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 960), Entry);
  LOBYTE(v4) = *(_BYTE *)(a2 + 112);
  TransportClose(v3 + 240, v4);
  return ClearFlags(a2 + 120, 1);
}

```

## disassembly

```asm
0x140018620  mov     [rsp+arg_0], rbx
0x140018625  push    rdi
0x140018626  sub     rsp, 20h
0x14001862a  mov     rdi, rdx
0x14001862d  mov     rdx, rcx; Entry
0x140018630  mov     rbx, [rdi+18h]
0x140018634  lea     rcx, [rbx+3C0h]; Lookaside
0x14001863b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018642  nop     dword ptr [rax+rax+00h]
0x140018647  mov     dl, [rdi+70h]
0x14001864a  lea     rcx, [rbx+0F0h]
0x140018651  call    TransportClose
0x140018656  lea     rcx, [rdi+78h]
0x14001865a  mov     edx, 1
0x14001865f  call    ClearFlags
0x140018664  mov     rbx, [rsp+28h+arg_0]
0x140018669  add     rsp, 20h
0x14001866d  pop     rdi
0x14001866e  retn
```
