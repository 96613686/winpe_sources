# CDevnode::Create(CDevnode * *)

- ea: `0x14000e454`
- end: `0x14000e4b0`
- name: `?Create@CDevnode@@SAJPEAPEAV1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(struct CDevnode **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f370`

## callees

- `0x14000190c`
- `0x14000e454`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000e48f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000e48f`

## pseudocode

```c
__int64 __fastcall CDevnode::Create(struct CDevnode **a1)
{
  void *v2; // rbx
  unsigned int v3; // edi

  try
  {
    v3 = 0;
    *a1 = 0;
    v2 = operator new(0x20u);
    *(_QWORD *)v2 = &CDevnode::`vftable';
    *((_DWORD *)v2 + 2) = 1;
    *((_QWORD *)v2 + 2) = 0;
    InitializeSRWLock((PSRWLOCK)v2 + 3);
    *a1 = (struct CDevnode *)v2;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  v3 = 0;
}

```

## disassembly

```asm
0x14000e454  mov     [rsp+arg_8], rbx
0x14000e459  mov     [rsp+arg_10], rsi
0x14000e45e  push    rdi
0x14000e45f  sub     rsp, 20h
0x14000e463  mov     rsi, rcx
0x14000e466  xor     edi, edi
0x14000e468  mov     [rcx], rdi
0x14000e46b  lea     ecx, [rdi+20h]; Size
0x14000e46e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e473  mov     rbx, rax
0x14000e476  lea     rax, ??_7CDevnode@@6B@; const CDevnode::`vftable'
0x14000e47d  mov     [rbx], rax
0x14000e480  mov     dword ptr [rbx+8], 1
0x14000e487  mov     [rbx+10h], rdi
0x14000e48b  lea     rcx, [rbx+18h]; SRWLock
0x14000e48f  call    cs:__imp_InitializeSRWLock
0x14000e495  mov     [rsi], rbx
0x14000e498  jmp     short loc_14000E49E
0x14000e49a  mov     edi, [rsp+28h+arg_0]
0x14000e49e  mov     eax, edi
0x14000e4a0  mov     rbx, [rsp+28h+arg_8]
0x14000e4a5  mov     rsi, [rsp+28h+arg_10]
0x14000e4aa  add     rsp, 20h
0x14000e4ae  pop     rdi
0x14000e4af  retn
```
