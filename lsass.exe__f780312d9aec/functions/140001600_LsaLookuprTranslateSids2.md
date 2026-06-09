# LsaLookuprTranslateSids2

- ea: `0x140001600`
- end: `0x14000165e`
- name: `LsaLookuprTranslateSids2`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001600`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall LsaLookuprTranslateSids2(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, __int64, __int64, __int64, int, int); // rax

  if ( gLsapLookupExtension
    && (v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int64, int, int))(gLsapLookupExtension + 16)) != 0 )
  {
    return v7(a1, a2, a3, a4, a5, a6, a7);
  }
  else
  {
    return 3221225474LL;
  }
}

```

## disassembly

```asm
0x140001600  push    rbx
0x140001602  sub     rsp, 40h
0x140001606  mov     rax, cs:gLsapLookupExtension
0x14000160d  mov     r10, r9
0x140001610  mov     r11, rdx
0x140001613  mov     rbx, rcx
0x140001616  test    rax, rax
0x140001619  jz      short loc_140001657
0x14000161b  mov     rax, [rax+10h]
0x14000161f  test    rax, rax
0x140001622  jz      short loc_140001657
0x140001624  mov     r9d, [rsp+48h+arg_30]
0x14000162c  mov     edx, [rsp+48h+arg_28]
0x140001630  mov     rcx, [rsp+48h+arg_20]
0x140001635  mov     [rsp+48h+var_18], r9d
0x14000163a  mov     r9, r10
0x14000163d  mov     [rsp+48h+var_20], edx
0x140001641  mov     rdx, r11
0x140001644  mov     [rsp+48h+var_28], rcx
0x140001649  mov     rcx, rbx
0x14000164c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001651  add     rsp, 40h
0x140001655  pop     rbx
0x140001656  retn
0x140001657  mov     eax, 0C0000002h
0x14000165c  jmp     short loc_140001651
```
