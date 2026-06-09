# KernelResource::~KernelResource(void)

- ea: `0x140002bbc`
- end: `0x140002bf0`
- name: `??1KernelResource@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(KernelResource *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b90`
- `0x140006080`
- `0x14001b0e8`
- `0x14001bcb0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140002bd3`
- `ntoskrnl!ExDeleteResourceLite` at `0x140002bd3`

## pseudocode

```c
void __fastcall KernelResource::~KernelResource(KernelResource *this)
{
  *(_QWORD *)this = &KernelResource::`vftable';
  ExDeleteResourceLite((PERESOURCE)((char *)this + 16));
  *(_QWORD *)this = &TopObj::`vftable';
}

```

## disassembly

```asm
0x140002bbc  push    rbx
0x140002bbe  sub     rsp, 20h
0x140002bc2  lea     rax, ??_7KernelResource@@6B@; const KernelResource::`vftable'
0x140002bc9  mov     rbx, rcx
0x140002bcc  mov     [rcx], rax
0x140002bcf  add     rcx, 10h; Resource
0x140002bd3  call    cs:__imp_ExDeleteResourceLite
0x140002bda  nop     dword ptr [rax+rax+00h]
0x140002bdf  lea     rax, ??_7TopObj@@6B@; const TopObj::`vftable'
0x140002be6  mov     [rbx], rax
0x140002be9  add     rsp, 20h
0x140002bed  pop     rbx
0x140002bee  retn
```
