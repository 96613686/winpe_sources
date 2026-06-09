# CSmartIcon::Attach(HICON__ *)

- ea: `0x180007cb8`
- end: `0x180007d20`
- name: `?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z`
- size: `104`
- prototype: `void(CSmartIcon *__hidden this, HICON)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180002160`
- `0x1800074d4`
- `0x1800081ec`
- `0x18000879c`

## callees

- `0x180001140`
- `0x180007cb8`
- `0x180007da0`

## import_xrefs

- `USER32!DestroyIcon` at `0x180007d0f`
- `USER32!DestroyIcon` at `0x180007d0f`

## pseudocode

```c
void __fastcall CSmartIcon::Attach(HICON *this, HICON a2)
{
  HICON v2; // rax
  _DWORD *v5; // rax

  v2 = *this;
  if ( *this )
    v2 = *(HICON *)v2;
  if ( v2 != a2 )
  {
    CSmartIcon::Empty((CSmartIcon *)this);
    if ( a2 )
    {
      v5 = operator new(0x10u);
      if ( v5 )
      {
        *(_QWORD *)v5 = a2;
        v5[2] = 1;
        *this = (HICON)v5;
      }
      else
      {
        *this = 0;
        DestroyIcon(a2);
      }
    }
  }
}

```

## disassembly

```asm
0x180007cb8  mov     [rsp+arg_8], rbx
0x180007cbd  push    rdi
0x180007cbe  sub     rsp, 20h
0x180007cc2  mov     rax, [rcx]
0x180007cc5  mov     rbx, rdx
0x180007cc8  mov     rdi, rcx
0x180007ccb  test    rax, rax
0x180007cce  jz      short loc_180007CD3
0x180007cd0  mov     rax, [rax]
0x180007cd3  cmp     rax, rbx
0x180007cd6  jz      short loc_180007D15
0x180007cd8  call    ?Empty@CSmartIcon@@QEAAXXZ; CSmartIcon::Empty(void)
0x180007cdd  test    rbx, rbx
0x180007ce0  jz      short loc_180007D15
0x180007ce2  mov     ecx, 10h; Size
0x180007ce7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007cec  mov     [rsp+28h+arg_0], rax
0x180007cf1  test    rax, rax
0x180007cf4  jz      short loc_180007D05
0x180007cf6  mov     [rax], rbx
0x180007cf9  mov     dword ptr [rax+8], 1
0x180007d00  mov     [rdi], rax
0x180007d03  jmp     short loc_180007D15
0x180007d05  mov     rcx, rbx; hIcon
0x180007d08  mov     qword ptr [rdi], 0
0x180007d0f  call    cs:__imp_DestroyIcon
0x180007d15  mov     rbx, [rsp+28h+arg_8]
0x180007d1a  add     rsp, 20h
0x180007d1e  pop     rdi
0x180007d1f  retn
```
