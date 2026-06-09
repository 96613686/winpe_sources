# utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)

- ea: `0x140008f90`
- end: `0x140009007`
- name: `?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006188`
- `0x14000ae14`
- `0x14000b2ec`
- `0x14000ca50`
- `0x14000d81c`
- `0x14000dd3c`
- `0x140018320`
- `0x1400187e4`
- `0x140018d5c`
- `0x140019e40`
- `0x14001bb2c`
- `0x14001dd28`
- `0x140021628`
- `0x140021b64`
- `0x140021d08`
- `0x1400223dc`

## callees

- `0x140002344`
- `0x140008f90`

## pseudocode

```c
void __fastcall utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(__int64 a1)
{
  _QWORD *v1; // rdi
  __int64 v3; // rbx
  __int64 v4; // rbx
  char *v5; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    v4 = v3 >> 5;
    while ( v4 )
    {
      --v4;
      v5 = (char *)v1[4 * v4];
      if ( v5 != (char *)&v1[4 * v4 + 2] )
        operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    }
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x140008f90  mov     [rsp+arg_0], rbx
0x140008f95  mov     [rsp+arg_8], rsi
0x140008f9a  push    rdi
0x140008f9b  sub     rsp, 20h
0x140008f9f  mov     rdi, [rcx]
0x140008fa2  mov     rsi, rcx
0x140008fa5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140008fa9  jz      short loc_140008FF6
0x140008fab  mov     rbx, [rcx+8]
0x140008faf  sub     rbx, rdi
0x140008fb2  mov     [rcx+8], rdi
0x140008fb6  sar     rbx, 5
0x140008fba  jmp     short loc_140008FE2
0x140008fbc  dec     rbx
0x140008fbf  mov     rax, rbx
0x140008fc2  shl     rax, 5
0x140008fc6  mov     rcx, [rax+rdi]; void *
0x140008fca  add     rax, 10h
0x140008fce  add     rax, rdi
0x140008fd1  cmp     rcx, rax
0x140008fd4  jz      short loc_140008FE2
0x140008fd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008fdd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008fe2  test    rbx, rbx
0x140008fe5  jnz     short loc_140008FBC
0x140008fe7  mov     rcx, [rsi]; void *
0x140008fea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008ff1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008ff6  mov     rbx, [rsp+28h+arg_0]
0x140008ffb  mov     rsi, [rsp+28h+arg_8]
0x140009000  add     rsp, 20h
0x140009004  pop     rdi
0x140009005  retn
```
