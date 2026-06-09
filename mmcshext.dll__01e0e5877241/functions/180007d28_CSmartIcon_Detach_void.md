# CSmartIcon::Detach(void)

- ea: `0x180007d28`
- end: `0x180007d99`
- name: `?Detach@CSmartIcon@@QEAAPEAUHICON__@@XZ`
- size: `113`
- prototype: `HICON __fastcall(CSmartIcon *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002160`

## callees

- `0x180007d28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007d79`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d79`
- `USER32!DestroyIcon` at `0x180007d70`
- `USER32!DestroyIcon` at `0x180007d70`
- `USER32!CopyIcon` at `0x180007d59`
- `USER32!CopyIcon` at `0x180007d59`

## pseudocode

```c
HICON __fastcall CSmartIcon::Detach(CSmartIcon *this)
{
  __int64 v1; // rbx
  HICON v2; // rdi

  v1 = *(_QWORD *)this;
  v2 = 0;
  if ( *(_QWORD *)this )
  {
    v2 = *(HICON *)v1;
    if ( *(_DWORD *)(v1 + 8) == 1 )
      *(_QWORD *)v1 = 0;
    else
      v2 = CopyIcon(*(HICON *)v1);
    if ( (*(_DWORD *)(v1 + 8))-- == 1 )
    {
      if ( *(_QWORD *)v1 )
        DestroyIcon(*(HICON *)v1);
      operator delete((void *)v1);
    }
    *(_QWORD *)this = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180007d28  mov     [rsp+arg_8], rbx
0x180007d2d  mov     [rsp+arg_10], rsi
0x180007d32  push    rdi
0x180007d33  sub     rsp, 20h
0x180007d37  mov     rbx, [rcx]
0x180007d3a  xor     edi, edi
0x180007d3c  mov     rsi, rcx
0x180007d3f  test    rbx, rbx
0x180007d42  jz      short loc_180007D86
0x180007d44  cmp     dword ptr [rbx+8], 1
0x180007d48  mov     rdi, [rbx]
0x180007d4b  jnz     short loc_180007D56
0x180007d4d  mov     qword ptr [rbx], 0
0x180007d54  jmp     short loc_180007D62
0x180007d56  mov     rcx, rdi; hIcon
0x180007d59  call    cs:__imp_CopyIcon
0x180007d5f  mov     rdi, rax
0x180007d62  add     dword ptr [rbx+8], 0FFFFFFFFh
0x180007d66  jnz     short loc_180007D7F
0x180007d68  mov     rcx, [rbx]; hIcon
0x180007d6b  test    rcx, rcx
0x180007d6e  jz      short loc_180007D76
0x180007d70  call    cs:__imp_DestroyIcon
0x180007d76  mov     rcx, rbx
0x180007d79  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d7f  mov     qword ptr [rsi], 0
0x180007d86  mov     rbx, [rsp+28h+arg_8]
0x180007d8b  mov     rax, rdi
0x180007d8e  mov     rsi, [rsp+28h+arg_10]
0x180007d93  add     rsp, 20h
0x180007d97  pop     rdi
0x180007d98  retn
```
