# CMmIStream::Open(IStream *)

- ea: `0x18000e47c`
- end: `0x18000e4e1`
- name: `?Open@CMmIStream@@QEAAXPEAUIStream@@@Z`
- size: `101`
- prototype: `void __fastcall(CMmIStream *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e344`

## callees

- `0x18000e47c`
- `0x180013500`
- `0x180025010`

## pseudocode

```c
void __fastcall CMmIStream::Open(CMmIStream *this, struct IStream *a2)
{
  int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_QWORD *)this + 1) = a2;
  ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  v4 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64))a2->lpVtbl->Stat)(a2, (char *)this + 24, 1);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmistrm.cxx",
      (const char *)(unsigned int)v4,
      v5);
}

```

## disassembly

```asm
0x18000e47c  mov     [rsp+arg_0], rbx
0x18000e481  push    rdi; int
0x18000e482  sub     rsp, 20h
0x18000e486  mov     [rcx+8], rdx
0x18000e48a  mov     rbx, rcx
0x18000e48d  mov     rax, [rdx]
0x18000e490  mov     rcx, rdx
0x18000e493  mov     rdi, rdx
0x18000e496  mov     rax, [rax+8]
0x18000e49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e49f  mov     rax, [rdi]
0x18000e4a2  lea     rdx, [rbx+18h]
0x18000e4a6  mov     r8d, 1
0x18000e4ac  mov     rcx, rdi
0x18000e4af  mov     rax, [rax+60h]
0x18000e4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b8  test    eax, eax
0x18000e4ba  js      short loc_18000E4C7
0x18000e4bc  mov     rbx, [rsp+28h+arg_0]
0x18000e4c1  add     rsp, 20h
0x18000e4c5  pop     rdi
0x18000e4c6  retn
0x18000e4c7  mov     rcx, [rsp+28h]; this
0x18000e4cc  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000e4d3  mov     r9d, eax; char *
0x18000e4d6  mov     edx, 5Ah ; 'Z'; void *
0x18000e4db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
