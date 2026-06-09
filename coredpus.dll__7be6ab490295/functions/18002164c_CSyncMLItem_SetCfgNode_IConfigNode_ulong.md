# CSyncMLItem::SetCfgNode(IConfigNode *,ulong)

- ea: `0x18002164c`
- end: `0x1800216b2`
- name: `?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z`
- size: `102`
- prototype: `__int64 __fastcall(CSyncMLItem *__hidden this, struct IConfigNode *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bc70`
- `0x18001ef60`
- `0x18001f290`
- `0x18001f5a0`
- `0x18001f7a0`

## callees

- `0x18002164c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::SetCfgNode(CSyncMLItem *this, struct IConfigNode *a2, unsigned int a3)
{
  __int64 v5; // rsi
  __int64 v6; // rcx

  _mm_lfence();
  v5 = a3;
  v6 = *((_QWORD *)this + a3 + 6);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + v5 + 6) = 0;
  }
  if ( a2 )
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)this + v5 + 6) = a2;
  return 0;
}

```

## disassembly

```asm
0x18002164c  mov     [rsp+arg_0], rbx
0x180021651  mov     [rsp+arg_8], rsi
0x180021656  push    rdi
0x180021657  sub     rsp, 20h
0x18002165b  mov     rbx, rdx
0x18002165e  mov     rdi, rcx
0x180021661  lfence
0x180021664  mov     esi, r8d
0x180021667  mov     rcx, [rcx+rsi*8+30h]
0x18002166c  test    rcx, rcx
0x18002166f  jz      short loc_180021686
0x180021671  mov     rax, [rcx]
0x180021674  mov     rax, [rax+10h]
0x180021678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002167d  mov     qword ptr [rdi+rsi*8+30h], 0
0x180021686  test    rbx, rbx
0x180021689  jz      short loc_18002169A
0x18002168b  mov     rax, [rbx]
0x18002168e  mov     rcx, rbx
0x180021691  mov     rax, [rax+8]
0x180021695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002169a  mov     [rdi+rsi*8+30h], rbx
0x18002169f  xor     eax, eax
0x1800216a1  mov     rbx, [rsp+28h+arg_0]
0x1800216a6  mov     rsi, [rsp+28h+arg_8]
0x1800216ab  add     rsp, 20h
0x1800216af  pop     rdi
0x1800216b0  retn
```
