# TSDeleteKernelContext

- ea: `0x140022a00`
- end: `0x140022a42`
- name: `TSDeleteKernelContext`
- size: `66`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140022a00`
- `0x140022f20`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x140022a10`
- `ntoskrnl!MmIsUserAddress` at `0x140022a10`

## pseudocode

```c
__int64 __fastcall TSDeleteKernelContext(_QWORD *P, _QWORD *a2)
{
  if ( (unsigned __int8)MmIsUserAddress() )
  {
    *a2 = P;
  }
  else
  {
    *a2 = P[1];
    TSKFreeContext(P);
  }
  return 0;
}

```

## disassembly

```asm
0x140022a00  mov     [rsp+arg_0], rbx
0x140022a05  push    rdi
0x140022a06  sub     rsp, 20h
0x140022a0a  mov     rdi, rdx
0x140022a0d  mov     rbx, rcx
0x140022a10  call    cs:__imp_MmIsUserAddress
0x140022a17  nop     dword ptr [rax+rax+00h]
0x140022a1c  test    al, al
0x140022a1e  jz      short loc_140022A25
0x140022a20  mov     [rdi], rbx
0x140022a23  jmp     short loc_140022A34
0x140022a25  mov     rax, [rbx+8]
0x140022a29  mov     rcx, rbx; P
0x140022a2c  mov     [rdi], rax
0x140022a2f  call    TSKFreeContext
0x140022a34  mov     rbx, [rsp+28h+arg_0]
0x140022a39  xor     eax, eax
0x140022a3b  add     rsp, 20h
0x140022a3f  pop     rdi
0x140022a40  retn
```
