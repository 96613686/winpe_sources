# ACpSetMsgIdProperty

- ea: `0x14000da30`
- end: `0x14000da86`
- name: `ACpSetMsgIdProperty`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc20`

## callees

- `0x14000da30`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14000da55`
- `ntoskrnl!ProbeForWrite` at `0x14000da55`

## pseudocode

```c
__int64 __fastcall ACpSetMsgIdProperty(__int64 a1, __int64 a2)
{
  volatile void **v4; // rcx
  __int64 v5; // rcx

  v4 = *(volatile void ***)(a1 + 8);
  if ( v4 )
  {
    ProbeForWrite(*v4, 0x14u, 1u);
    v5 = **(_QWORD **)(a1 + 8);
    *(_OWORD *)v5 = *(_OWORD *)a2;
    *(_DWORD *)(v5 + 16) = *(_DWORD *)(a2 + 16);
  }
  return 0;
}

```

## disassembly

```asm
0x14000da30  mov     [rsp+arg_0], rbx
0x14000da35  push    rdi
0x14000da36  sub     rsp, 20h
0x14000da3a  mov     rdi, rdx
0x14000da3d  mov     rbx, rcx
0x14000da40  mov     rcx, [rcx+8]
0x14000da44  test    rcx, rcx
0x14000da47  jz      short loc_14000DA78
0x14000da49  mov     edx, 14h; Length
0x14000da4e  lea     r8d, [rdx-13h]; Alignment
0x14000da52  mov     rcx, [rcx]; Address
0x14000da55  call    cs:__imp_ProbeForWrite
0x14000da5c  nop     dword ptr [rax+rax+00h]
0x14000da61  mov     rax, [rbx+8]
0x14000da65  mov     rcx, [rax]
0x14000da68  movaps  xmm0, xmmword ptr [rdi]
0x14000da6b  movups  xmmword ptr [rcx], xmm0
0x14000da6e  mov     eax, [rdi+10h]
0x14000da71  mov     [rcx+10h], eax
0x14000da74  jmp     short loc_14000DA78
0x14000da76  jmp     short loc_14000DA7A
0x14000da78  xor     eax, eax
0x14000da7a  mov     rbx, [rsp+28h+arg_0]
0x14000da7f  add     rsp, 20h
0x14000da83  pop     rdi
0x14000da84  retn
```
