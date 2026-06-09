# wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)

- ea: `0x14000fb20`
- end: `0x14000fb40`
- name: `??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001e278`
- `0x14001e2b6`

## callees

- `0x14000fb20`
- `0x140010080`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x14000fb20  sub     rsp, 28h
0x14000fb24  mov     rax, [rcx]
0x14000fb27  mov     qword ptr [rcx], 0
0x14000fb2e  test    rax, rax
0x14000fb31  jz      short loc_14000FB3B
0x14000fb33  mov     rcx, rax; Block
0x14000fb36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000fb3b  add     rsp, 28h
0x14000fb3f  retn
```
