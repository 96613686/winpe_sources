# CJobCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000cf80`
- end: `0x18000cfee`
- name: `?CreateInstance@CJobCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `110`
- prototype: `__int64 __fastcall(CJobCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000865c`
- `0x18000cf80`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CJobCF::CreateInstance(CJobCF *this, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  struct CJob *v6; // rax
  struct CJob *v7; // rbx
  int v9; // esi

  v6 = CJob::Create();
  v7 = v6;
  if ( v6 )
  {
    v9 = (**(__int64 (__fastcall ***)(struct CJob *, const struct _GUID *, void **))v6)(v6, a3, a4);
    if ( v9 < 0 )
      *a4 = 0;
    (*(void (__fastcall **)(struct CJob *))(*(_QWORD *)v7 + 16LL))(v7);
    return (unsigned int)v9;
  }
  else
  {
    *a4 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000cf80  mov     [rsp+arg_0], rbx
0x18000cf85  mov     [rsp+arg_8], rsi
0x18000cf8a  push    rdi
0x18000cf8b  sub     rsp, 20h
0x18000cf8f  mov     rdi, r9
0x18000cf92  mov     rsi, r8
0x18000cf95  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x18000cf9a  mov     rbx, rax
0x18000cf9d  test    rax, rax
0x18000cfa0  jnz     short loc_18000CFAC
0x18000cfa2  mov     [rdi], rax
0x18000cfa5  mov     eax, 8007000Eh
0x18000cfaa  jmp     short loc_18000CFDE
0x18000cfac  mov     rax, [rax]
0x18000cfaf  mov     r8, rdi
0x18000cfb2  mov     rdx, rsi
0x18000cfb5  mov     rcx, rbx
0x18000cfb8  mov     rax, [rax]
0x18000cfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc0  mov     esi, eax
0x18000cfc2  test    eax, eax
0x18000cfc4  jns     short loc_18000CFCD
0x18000cfc6  mov     qword ptr [rdi], 0
0x18000cfcd  mov     rcx, [rbx]
0x18000cfd0  mov     rax, [rcx+10h]
0x18000cfd4  mov     rcx, rbx
0x18000cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfdc  mov     eax, esi
0x18000cfde  mov     rbx, [rsp+28h+arg_0]
0x18000cfe3  mov     rsi, [rsp+28h+arg_8]
0x18000cfe8  add     rsp, 20h
0x18000cfec  pop     rdi
0x18000cfed  retn
```
