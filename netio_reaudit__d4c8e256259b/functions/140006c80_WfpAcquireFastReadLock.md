# WfpAcquireFastReadLock

- ea: `0x140006c80`
- end: `0x140006d0f`
- name: `WfpAcquireFastReadLock`
- size: `143`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140005b60`
- `0x1400068d0`
- `0x14000bb9c`
- `0x14001d5dc`
- `0x140039a00`
- `0x14004eed4`
- `0x14004f7b0`

## callees

- `0x140006c80`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006cca`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006cca`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006c95`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006c95`
- `NDIS!NdisAcquireRWLockRead` at `0x140006cad`
- `NDIS!NdisAcquireRWLockRead` at `0x140006cad`

## pseudocode

```c
void __fastcall WfpAcquireFastReadLock(PNDIS_RW_LOCK_EX *a1, struct _LOCK_STATE_EX *a2)
{
  KIRQL CurrentIrql; // bl
  __int64 v5; // rdx

  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead(*a1, a2, 0);
  if ( CurrentIrql != 2 )
  {
    if ( gWfpPerProContext )
    {
      v5 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v5 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v5 = 4;
    }
  }
}

```

## disassembly

```asm
0x140006c80  mov     [rsp+arg_0], rbx
0x140006c85  mov     [rsp+arg_8], rsi
0x140006c8a  push    rdi
0x140006c8b  sub     rsp, 20h
0x140006c8f  mov     rdi, rdx
0x140006c92  mov     rsi, rcx
0x140006c95  call    cs:__imp_KeGetCurrentIrql
0x140006c9c  nop     dword ptr [rax+rax+00h]
0x140006ca1  mov     rcx, [rsi]; Lock
0x140006ca4  xor     r8d, r8d; Flags
0x140006ca7  mov     rdx, rdi; LockState
0x140006caa  movzx   ebx, al
0x140006cad  call    cs:__imp_NdisAcquireRWLockRead
0x140006cb4  nop     dword ptr [rax+rax+00h]
0x140006cb9  cmp     bl, 2
0x140006cbc  jz      short loc_140006CFE
0x140006cbe  cmp     cs:gWfpPerProContext, 0
0x140006cc6  jz      short loc_140006CFE
0x140006cc8  xor     ecx, ecx; ProcNumber
0x140006cca  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140006cd1  nop     dword ptr [rax+rax+00h]
0x140006cd6  imul    eax, cs:gWfpPerProContextSize
0x140006cdd  mov     ecx, eax
0x140006cdf  mov     rax, cs:gWfpPerProContext
0x140006ce6  mov     rdx, [rcx+rax]
0x140006cea  mov     rax, ds:0FFFFF78000000008h
0x140006cf4  mov     [rdx+8], rax
0x140006cf8  mov     dword ptr [rdx], 4
0x140006cfe  mov     rbx, [rsp+28h+arg_0]
0x140006d03  mov     rsi, [rsp+28h+arg_8]
0x140006d08  add     rsp, 20h
0x140006d0c  pop     rdi
0x140006d0d  retn
```
