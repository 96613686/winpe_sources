# InitMMIOOpen

- ea: `0x1800031c4`
- end: `0x180003201`
- name: `InitMMIOOpen`
- size: `61`
- prototype: `HTASK __fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180001558`
- `0x180002320`
- `0x1800040dc`
- `0x180004318`
- `0x180004508`

## callees

- `0x180005c29`

## import_xrefs

- `WINMM!mciGetCreatorTask` at `0x1800031ec`
- `WINMM!mciGetCreatorTask` at `0x1800031ec`

## pseudocode

```c
HTASK __fastcall InitMMIOOpen(__int64 a1, _QWORD *a2)
{
  HTASK result; // rax

  memset_0(a2, 0, 0x64u);
  a2[1] = *(_QWORD *)(a1 + 96);
  result = mciGetCreatorTask(*(_DWORD *)a1);
  *(_QWORD *)((char *)a2 + 20) = result;
  return result;
}

```

## disassembly

```asm
0x1800031c4  mov     [rsp+arg_0], rbx
0x1800031c9  push    rdi
0x1800031ca  sub     rsp, 20h
0x1800031ce  mov     rdi, rdx
0x1800031d1  mov     rbx, rcx
0x1800031d4  xor     edx, edx; Val
0x1800031d6  mov     rcx, rdi; void *
0x1800031d9  lea     r8d, [rdx+64h]; Size
0x1800031dd  call    memset_0
0x1800031e2  mov     rax, [rbx+60h]
0x1800031e6  mov     [rdi+8], rax
0x1800031ea  mov     ecx, [rbx]; mciId
0x1800031ec  call    cs:__imp_mciGetCreatorTask
0x1800031f2  mov     rbx, [rsp+28h+arg_0]
0x1800031f7  mov     [rdi+14h], rax
0x1800031fb  add     rsp, 20h
0x1800031ff  pop     rdi
0x180003200  retn
```
