# CWMReadSample::GetLength(ulong *)

- ea: `0x180009a90`
- end: `0x180009abf`
- name: `?GetLength@CWMReadSample@@UEAAJPEAK@Z`
- size: `47`
- prototype: `__int64 __fastcall(CWMReadSample *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009a90`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMReadSample::GetLength(CWMReadSample *this, unsigned int *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 88LL))(*((_QWORD *)this + 9));
  return 0;
}

```

## disassembly

```asm
0x180009a90  push    rbx
0x180009a92  sub     rsp, 20h
0x180009a96  mov     rbx, rdx
0x180009a99  test    rdx, rdx
0x180009a9c  jnz     short loc_180009AA5
0x180009a9e  mov     eax, 80070057h
0x180009aa3  jmp     short loc_180009AB9
0x180009aa5  mov     rcx, [rcx+48h]
0x180009aa9  mov     rax, [rcx]
0x180009aac  mov     rax, [rax+58h]
0x180009ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ab5  mov     [rbx], eax
0x180009ab7  xor     eax, eax
0x180009ab9  add     rsp, 20h
0x180009abd  pop     rbx
0x180009abe  retn
```
