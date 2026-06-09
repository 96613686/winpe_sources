# STRING_QUEUE::InsertHead(STRU &)

- ea: `0x1800051c0`
- end: `0x180005246`
- name: `?InsertHead@STRING_QUEUE@@QEAAJAEAVSTRU@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(STRING_QUEUE *__hidden this, struct STRU *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004d70`
- `0x180008120`

## callees

- `0x180005190`
- `0x1800051c0`
- `0x180005460`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800051fd`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800051fd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800051f0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800051f0`

## pseudocode

```c
__int64 __fastcall STRING_QUEUE::InsertHead(STRING_QUEUE *this, struct STRU *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  unsigned int v6; // edx
  int v7; // edi
  __int64 v8; // rax
  __int64 result; // rax

  v4 = operator new(0x48u);
  v5 = v4;
  if ( !v4 )
    return 2147942408LL;
  STRU::STRU((STRU *)(v4 + 2));
  v7 = STRU::Copy((STRU *)(v5 + 2), a2);
  if ( v7 < 0 )
  {
    STRING_QUEUE_ITEM::`scalar deleting destructor'((STRING_QUEUE_ITEM *)v5, v6);
    return (unsigned int)v7;
  }
  else
  {
    v8 = *(_QWORD *)this;
    if ( *(STRING_QUEUE **)(*(_QWORD *)this + 8LL) != this )
      __fastfail(3u);
    *v5 = v8;
    v5[1] = this;
    *(_QWORD *)(v8 + 8) = v5;
    result = 0;
    *(_QWORD *)this = v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800051c0  mov     [rsp+arg_8], rbx
0x1800051c5  mov     [rsp+arg_10], rbp
0x1800051ca  push    rsi
0x1800051cb  sub     rsp, 20h
0x1800051cf  mov     rsi, rcx
0x1800051d2  mov     rbp, rdx
0x1800051d5  mov     ecx, 48h ; 'H'; Size
0x1800051da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800051df  mov     rbx, rax
0x1800051e2  test    rax, rax
0x1800051e5  jz      short loc_18000523F
0x1800051e7  lea     rcx, [rax+10h]
0x1800051eb  mov     [rsp+28h+arg_0], rdi
0x1800051f0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800051f6  mov     rdx, rbp
0x1800051f9  lea     rcx, [rbx+10h]
0x1800051fd  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180005203  mov     edi, eax
0x180005205  test    eax, eax
0x180005207  js      loc_180007502
0x18000520d  mov     rax, [rsi]
0x180005210  cmp     [rax+8], rsi
0x180005214  jnz     loc_180007511
0x18000521a  mov     [rbx], rax
0x18000521d  mov     [rbx+8], rsi
0x180005221  mov     [rax+8], rbx
0x180005225  xor     eax, eax
0x180005227  mov     [rsi], rbx
0x18000522a  mov     rdi, [rsp+28h+arg_0]
0x18000522f  mov     rbx, [rsp+28h+arg_8]
0x180005234  mov     rbp, [rsp+28h+arg_10]
0x180005239  add     rsp, 20h
0x18000523d  pop     rsi
0x18000523e  retn
0x18000523f  mov     eax, 80070008h
0x180005244  jmp     short loc_18000522F
0x180007502  mov     rcx, rbx; this
0x180007505  call    ??_GSTRING_QUEUE_ITEM@@QEAAPEAXI@Z; STRING_QUEUE_ITEM::`scalar deleting destructor'(uint)
0x18000750a  mov     eax, edi
0x18000750c  jmp     loc_18000522A
0x180007511  mov     ecx, 3
0x180007516  int     29h; Win8: RtlFailFast(ecx)
```
