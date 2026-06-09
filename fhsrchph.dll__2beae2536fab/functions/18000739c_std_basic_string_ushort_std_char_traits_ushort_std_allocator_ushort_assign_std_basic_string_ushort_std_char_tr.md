# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x18000739c`
- end: `0x180007436`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z`
- size: `154`
- prototype: `void **__fastcall(void **, void **Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006dc0`
- `0x180007178`

## callees

- `0x18000739c`
- `0x18000ab22`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800073bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800073bb`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, void **Src)
{
  if ( a1 != Src )
  {
    if ( (unsigned __int64)a1[3] >= 8 )
      operator delete(*a1);
    a1[3] = (void *)7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    if ( (unsigned __int64)Src[3] >= 8 )
    {
      *a1 = *Src;
      *Src = 0;
    }
    else
    {
      memmove_0(a1, Src, 2LL * (_QWORD)Src[2] + 2);
    }
    a1[2] = Src[2];
    a1[3] = Src[3];
    Src[3] = (void *)7;
    Src[2] = 0;
    *(_WORD *)Src = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000739c  mov     [rsp+arg_0], rbx
0x1800073a1  push    rdi
0x1800073a2  sub     rsp, 20h
0x1800073a6  mov     rdi, rdx
0x1800073a9  mov     rbx, rcx
0x1800073ac  cmp     rcx, rdx
0x1800073af  jz      short loc_180007428
0x1800073b1  cmp     qword ptr [rcx+18h], 8
0x1800073b6  jb      short loc_1800073C1
0x1800073b8  mov     rcx, [rcx]
0x1800073bb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800073c1  xor     eax, eax
0x1800073c3  mov     qword ptr [rbx+18h], 7
0x1800073cb  mov     qword ptr [rbx+10h], 0
0x1800073d3  mov     [rbx], ax
0x1800073d6  cmp     qword ptr [rdi+18h], 8
0x1800073db  jnb     short loc_1800073F6
0x1800073dd  mov     r8, [rdi+10h]
0x1800073e1  mov     rdx, rdi; Src
0x1800073e4  mov     rcx, rbx; void *
0x1800073e7  lea     r8, ds:2[r8*2]; Size
0x1800073ef  call    memmove_0
0x1800073f4  jmp     short loc_180007403
0x1800073f6  mov     rax, [rdi]
0x1800073f9  mov     [rbx], rax
0x1800073fc  mov     qword ptr [rdi], 0
0x180007403  mov     rax, [rdi+10h]
0x180007407  mov     [rbx+10h], rax
0x18000740b  mov     rax, [rdi+18h]
0x18000740f  mov     [rbx+18h], rax
0x180007413  xor     eax, eax
0x180007415  mov     qword ptr [rdi+18h], 7
0x18000741d  mov     qword ptr [rdi+10h], 0
0x180007425  mov     [rdi], ax
0x180007428  mov     rax, rbx
0x18000742b  mov     rbx, [rsp+28h+arg_0]
0x180007430  add     rsp, 20h
0x180007434  pop     rdi
0x180007435  retn
```
