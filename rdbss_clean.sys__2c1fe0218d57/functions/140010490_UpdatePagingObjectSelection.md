# UpdatePagingObjectSelection

- ea: `0x140010490`
- end: `0x1400104e5`
- name: `UpdatePagingObjectSelection`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140004180`

## callees

- `0x140010490`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400104b1`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400104b1`

## pseudocode

```c
__int64 __fastcall UpdatePagingObjectSelection(__int64 a1, __int64 a2, __int64 a3)
{
  void *v5; // rcx
  __int64 v7; // rcx
  __int64 result; // rax

  v5 = *(void **)(a1 + 8);
  if ( v5 )
    ObDereferenceObjectDeferDelete(v5);
  v7 = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(a1 + 8) = a3;
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(v7 + 120);
  result = *(unsigned int *)(v7 + 124);
  *(_DWORD *)(a1 + 20) = result;
  return result;
}

```

## disassembly

```asm
0x140010490  mov     [rsp+arg_0], rbx
0x140010495  mov     [rsp+arg_8], rsi
0x14001049a  push    rdi
0x14001049b  sub     rsp, 20h
0x14001049f  mov     rbx, rcx
0x1400104a2  mov     rsi, r8
0x1400104a5  mov     rcx, [rcx+8]; Object
0x1400104a9  mov     rdi, rdx
0x1400104ac  test    rcx, rcx
0x1400104af  jz      short loc_1400104BD
0x1400104b1  call    cs:__imp_ObDereferenceObjectDeferDelete
0x1400104b8  nop     dword ptr [rax+rax+00h]
0x1400104bd  mov     rcx, [rdi+20h]
0x1400104c1  mov     [rbx+8], rsi
0x1400104c5  mov     rsi, [rsp+28h+arg_8]
0x1400104ca  mov     [rbx], rdi
0x1400104cd  mov     eax, [rcx+78h]
0x1400104d0  mov     [rbx+10h], eax
0x1400104d3  mov     eax, [rcx+7Ch]
0x1400104d6  mov     [rbx+14h], eax
0x1400104d9  mov     rbx, [rsp+28h+arg_0]
0x1400104de  add     rsp, 20h
0x1400104e2  pop     rdi
0x1400104e3  retn
```
