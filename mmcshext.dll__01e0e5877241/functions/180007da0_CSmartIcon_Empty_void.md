# CSmartIcon::Empty(void)

- ea: `0x180007da0`
- end: `0x180007de4`
- name: `?Empty@CSmartIcon@@QEAAXXZ`
- size: `68`
- prototype: `void __fastcall(CSmartIcon *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002160`
- `0x1800074d4`
- `0x180007c70`
- `0x180007c7c`
- `0x180007cb8`
- `0x180007e14`
- `0x1800081ec`
- `0x18000ad7c`

## callees

- `0x180007da0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007dcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007dcc`
- `USER32!DestroyIcon` at `0x180007dc3`
- `USER32!DestroyIcon` at `0x180007dc3`

## pseudocode

```c
void __fastcall CSmartIcon::Empty(CSmartIcon *this)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    if ( (*(_DWORD *)(v1 + 8))-- == 1 )
    {
      if ( *(_QWORD *)v1 )
        DestroyIcon(*(HICON *)v1);
      operator delete((void *)v1);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180007da0  mov     [rsp+arg_8], rbx
0x180007da5  push    rdi
0x180007da6  sub     rsp, 20h
0x180007daa  mov     rbx, [rcx]
0x180007dad  mov     rdi, rcx
0x180007db0  test    rbx, rbx
0x180007db3  jz      short loc_180007DD9
0x180007db5  add     dword ptr [rbx+8], 0FFFFFFFFh
0x180007db9  jnz     short loc_180007DD2
0x180007dbb  mov     rcx, [rbx]; hIcon
0x180007dbe  test    rcx, rcx
0x180007dc1  jz      short loc_180007DC9
0x180007dc3  call    cs:__imp_DestroyIcon
0x180007dc9  mov     rcx, rbx
0x180007dcc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007dd2  mov     qword ptr [rdi], 0
0x180007dd9  mov     rbx, [rsp+28h+arg_8]
0x180007dde  add     rsp, 20h
0x180007de2  pop     rdi
0x180007de3  retn
```
