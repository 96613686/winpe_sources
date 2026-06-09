# basessp::BaseSSP::WSTAllocate(unsigned __int64)

- ea: `0x1800027e4`
- end: `0x180002856`
- name: `?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z`
- size: `114`
- prototype: `void *(basessp::BaseSSP *__hidden this, unsigned __int64)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011b4`
- `0x1800012dc`
- `0x180001400`
- `0x180001414`
- `0x180002470`
- `0x180002694`
- `0x180004404`
- `0x1800063e4`
- `0x18000676c`
- `0x180006a48`
- `0x1800070d0`
- `0x180008e60`
- `0x180009c98`
- `0x18000a29c`
- `0x18000bf1c`
- `0x18000d388`
- `0x180016f70`
- `0x180018964`
- `0x180019eec`
- `0x18001a020`
- `0x18001b9b0`
- `0x18001d71c`
- `0x18001d92c`
- `0x18001db40`
- `0x18001dc88`

## callees

- `0x1800027e4`
- `0x18001ecee`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTAllocate(basessp::BaseSSP *this, size_t a2)
{
  void *v4; // rdi
  void *v5; // rax

  if ( a2 > 0xFFFFFFFF )
    return 0;
  if ( *((_DWORD *)this + 52) == 1 )
    return (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)this + 30) + 384LL))((unsigned int)a2);
  v5 = (void *)(**((__int64 (__fastcall ***)(_QWORD))this + 31))((unsigned int)a2);
  v4 = v5;
  if ( v5 )
    memset_0(v5, 0, a2);
  return (__int64)v4;
}

```

## disassembly

```asm
0x1800027e4  mov     [rsp+arg_0], rbx
0x1800027e9  push    rdi
0x1800027ea  sub     rsp, 20h
0x1800027ee  mov     rbx, rdx
0x1800027f1  mov     eax, 0FFFFFFFFh
0x1800027f6  cmp     rdx, rax
0x1800027f9  jbe     short loc_1800027FF
0x1800027fb  xor     eax, eax
0x1800027fd  jmp     short loc_18000284B
0x1800027ff  cmp     dword ptr [rcx+0D0h], 1
0x180002806  jnz     short loc_180002822
0x180002808  mov     rax, [rcx+0F0h]
0x18000280f  mov     ecx, ebx
0x180002811  mov     rax, [rax+180h]
0x180002818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000281d  mov     rdi, rax
0x180002820  jmp     short loc_180002848
0x180002822  mov     rax, [rcx+0F8h]
0x180002829  mov     ecx, ebx
0x18000282b  mov     rax, [rax]
0x18000282e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002833  mov     rdi, rax
0x180002836  test    rax, rax
0x180002839  jz      short loc_180002848
0x18000283b  mov     r8, rbx; Size
0x18000283e  xor     edx, edx; Val
0x180002840  mov     rcx, rax; void *
0x180002843  call    memset_0
0x180002848  mov     rax, rdi
0x18000284b  mov     rbx, [rsp+28h+arg_0]
0x180002850  add     rsp, 20h
0x180002854  pop     rdi
0x180002855  retn
```
