# wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)

- ea: `0x14000da5c`
- end: `0x14000da84`
- name: `??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140015cc7`
- `0x140015cd9`
- `0x140015fff`
- `0x140016011`
- `0x1400160ba`

## callees

- `0x14000da5c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000da72`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000da72`

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
0x14000da5c  sub     rsp, 28h
0x14000da60  mov     rax, [rcx]
0x14000da63  mov     qword ptr [rcx], 0
0x14000da6a  test    rax, rax
0x14000da6d  jz      short loc_14000DA7E
0x14000da6f  mov     rcx, rax
0x14000da72  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000da79  nop     dword ptr [rax+rax+00h]
0x14000da7e  add     rsp, 28h
0x14000da82  retn
```
