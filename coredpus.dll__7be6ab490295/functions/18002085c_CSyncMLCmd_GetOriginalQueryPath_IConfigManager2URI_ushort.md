# CSyncMLCmd::GetOriginalQueryPath(IConfigManager2URI *,ushort * *)

- ea: `0x18002085c`
- end: `0x1800208e7`
- name: `?GetOriginalQueryPath@CSyncMLCmd@@IEBAJPEAUIConfigManager2URI@@PEAPEAG@Z`
- size: `139`
- prototype: `__int64 __fastcall(CSyncMLCmd *__hidden this, struct IConfigManager2URI *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bf60`
- `0x18001fee0`

## callees

- `0x18002085c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLCmd::GetOriginalQueryPath(
        CSyncMLCmd *this,
        __int64 (__fastcall ***a2)(struct IConfigManager2URI *, GUID *, CSyncMLCmd **),
        unsigned __int16 **a3)
{
  __int64 (__fastcall **v5)(struct IConfigManager2URI *, GUID *, CSyncMLCmd **); // rax
  int v6; // ebx
  CSyncMLCmd *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = this;
  *a3 = 0;
  if ( !a2 )
    return 2147549183LL;
  v5 = *a2;
  v7 = 0;
  v6 = (*v5)((struct IConfigManager2URI *)a2, &GUID_e8e62e9d_37fc_47a0_846a_29781dfa97d9, &v7);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(CSyncMLCmd *, unsigned __int16 **))(*(_QWORD *)v7 + 24LL))(v7, a3);
  if ( v7 )
    (*(void (__fastcall **)(CSyncMLCmd *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002085c  mov     [rsp+arg_8], rbx
0x180020861  mov     [rsp+arg_0], rcx
0x180020866  push    rdi
0x180020867  sub     rsp, 20h
0x18002086b  mov     qword ptr [r8], 0
0x180020872  mov     rdi, r8
0x180020875  mov     r9, rdx
0x180020878  test    rdx, rdx
0x18002087b  jnz     short loc_180020884
0x18002087d  mov     eax, 8000FFFFh
0x180020882  jmp     short loc_1800208DB
0x180020884  mov     rax, [rdx]
0x180020887  lea     r8, [rsp+28h+arg_0]
0x18002088c  lea     rdx, _GUID_e8e62e9d_37fc_47a0_846a_29781dfa97d9
0x180020893  mov     [rsp+28h+arg_0], 0
0x18002089c  mov     rcx, r9
0x18002089f  mov     rax, [rax]
0x1800208a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a7  mov     ebx, eax
0x1800208a9  test    eax, eax
0x1800208ab  js      short loc_1800208C3
0x1800208ad  mov     rcx, [rsp+28h+arg_0]
0x1800208b2  mov     rdx, rdi
0x1800208b5  mov     rax, [rcx]
0x1800208b8  mov     rax, [rax+18h]
0x1800208bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208c1  mov     ebx, eax
0x1800208c3  mov     rcx, [rsp+28h+arg_0]
0x1800208c8  test    rcx, rcx
0x1800208cb  jz      short loc_1800208D9
0x1800208cd  mov     rax, [rcx]
0x1800208d0  mov     rax, [rax+10h]
0x1800208d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208d9  mov     eax, ebx
0x1800208db  mov     rbx, [rsp+28h+arg_8]
0x1800208e0  add     rsp, 20h
0x1800208e4  pop     rdi
0x1800208e5  retn
```
