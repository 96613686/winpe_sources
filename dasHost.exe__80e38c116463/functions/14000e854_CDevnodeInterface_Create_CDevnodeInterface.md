# CDevnodeInterface::Create(CDevnodeInterface * *)

- ea: `0x14000e854`
- end: `0x14000e8ad`
- name: `?Create@CDevnodeInterface@@SAJPEAPEAV1@@Z`
- size: `89`
- prototype: `__int64 __fastcall(struct CDevnodeInterface **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fd20`

## callees

- `0x14000190c`
- `0x14000e854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000e88c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000e88c`

## pseudocode

```c
__int64 __fastcall CDevnodeInterface::Create(struct CDevnodeInterface **a1)
{
  void *v2; // rbx
  unsigned int v3; // edi

  try
  {
    v3 = 0;
    v2 = operator new(0x20u);
    *(_QWORD *)v2 = &CDevnodeInterface::`vftable';
    *((_DWORD *)v2 + 2) = 1;
    *((_QWORD *)v2 + 2) = 0;
    InitializeSRWLock((PSRWLOCK)v2 + 3);
    *a1 = (struct CDevnodeInterface *)v2;
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
0x14000e854  mov     [rsp+arg_0], rbx
0x14000e859  mov     [rsp+arg_10], rsi
0x14000e85e  push    rdi
0x14000e85f  sub     rsp, 20h
0x14000e863  mov     rsi, rcx
0x14000e866  xor     edi, edi
0x14000e868  lea     ecx, [rdi+20h]; Size
0x14000e86b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e870  mov     rbx, rax
0x14000e873  lea     rax, ??_7CDevnodeInterface@@6B@; const CDevnodeInterface::`vftable'
0x14000e87a  mov     [rbx], rax
0x14000e87d  mov     dword ptr [rbx+8], 1
0x14000e884  mov     [rbx+10h], rdi
0x14000e888  lea     rcx, [rbx+18h]; SRWLock
0x14000e88c  call    cs:__imp_InitializeSRWLock
0x14000e892  mov     [rsi], rbx
0x14000e895  jmp     short loc_14000E89B
0x14000e897  mov     edi, [rsp+28h+arg_8]
0x14000e89b  mov     eax, edi
0x14000e89d  mov     rbx, [rsp+28h+arg_0]
0x14000e8a2  mov     rsi, [rsp+28h+arg_10]
0x14000e8a7  add     rsp, 20h
0x14000e8ab  pop     rdi
0x14000e8ac  retn
```
