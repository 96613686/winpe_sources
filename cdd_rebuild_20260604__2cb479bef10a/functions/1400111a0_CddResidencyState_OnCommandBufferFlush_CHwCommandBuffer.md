# CddResidencyState::OnCommandBufferFlush(CHwCommandBuffer *)

- ea: `0x1400111a0`
- end: `0x1400111b9`
- name: `?OnCommandBufferFlush@CddResidencyState@@QEAAXPEAVCHwCommandBuffer@@@Z`
- size: `25`
- prototype: `void __fastcall(CddResidencyState *__hidden this, struct CHwCommandBuffer *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010c2c`
- `0x140011220`

## callees

- `0x1400372d0`

## pseudocode

```c
void __fastcall CddResidencyState::OnCommandBufferFlush(CddResidencyState *this, struct CHwCommandBuffer *a2)
{
  (*(void (__fastcall **)(_QWORD, struct CHwCommandBuffer *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, a2);
}

```

## disassembly

```asm
0x1400111a0  sub     rsp, 28h
0x1400111a4  mov     rcx, [rcx]
0x1400111a7  mov     rax, [rcx]
0x1400111aa  mov     rax, [rax+8]
0x1400111ae  call    _guard_dispatch_icall
0x1400111b3  add     rsp, 28h
0x1400111b7  retn
```
