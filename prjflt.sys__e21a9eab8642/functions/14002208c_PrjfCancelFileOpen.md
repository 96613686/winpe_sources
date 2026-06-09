# PrjfCancelFileOpen

- ea: `0x14002208c`
- end: `0x1400220c8`
- name: `PrjfCancelFileOpen`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400220d0`
- `0x140022320`
- `0x140029f60`

## import_xrefs

- `FLTMGR!FltCancelFileOpen` at `0x1400220a5`
- `FLTMGR!FltCancelFileOpen` at `0x1400220a5`

## pseudocode

```c
void __fastcall PrjfCancelFileOpen(__int64 a1, struct _FLT_INSTANCE *a2, struct _FILE_OBJECT *a3, int a4)
{
  FltCancelFileOpen(a2, a3);
  *(_DWORD *)(a1 + 24) = a4;
  *(_QWORD *)(a1 + 32) = 0;
}

```

## disassembly

```asm
0x14002208c  mov     [rsp+arg_0], rbx
0x140022091  push    rdi
0x140022092  sub     rsp, 20h
0x140022096  mov     rax, rdx
0x140022099  mov     rbx, rcx
0x14002209c  mov     rcx, rax; Instance
0x14002209f  mov     rdx, r8; FileObject
0x1400220a2  mov     edi, r9d
0x1400220a5  call    cs:__imp_FltCancelFileOpen
0x1400220ac  nop     dword ptr [rax+rax+00h]
0x1400220b1  mov     [rbx+18h], edi
0x1400220b4  mov     qword ptr [rbx+20h], 0
0x1400220bc  mov     rbx, [rsp+28h+arg_0]
0x1400220c1  add     rsp, 20h
0x1400220c5  pop     rdi
0x1400220c6  retn
```
