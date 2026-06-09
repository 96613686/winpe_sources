# W3_REQUEST::CopyHeaders(W3_REQUEST *)

- ea: `0x180029428`
- end: `0x180029585`
- name: `?CopyHeaders@W3_REQUEST@@QEAAJPEAV1@@Z`
- size: `349`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, struct W3_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002910c`

## callees

- `0x180029428`
- `0x180037722`
- `0x18003773a`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002951a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002951a`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180029500`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180029500`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::CopyHeaders(W3_REQUEST *this, struct W3_REQUEST *a2)
{
  void *Ptr; // rbp
  __int64 v4; // rdi
  __int64 v5; // rdx
  _OWORD *v6; // rax
  _OWORD *v7; // rcx
  __int128 v8; // xmm1
  __int64 v9; // rsi

  if ( a2 )
  {
    ++*((_DWORD *)a2 + 12);
    Ptr = 0;
    v4 = *((_QWORD *)a2 + 5);
    v5 = 5;
    v6 = (_OWORD *)(*((_QWORD *)this + 5) + 152LL);
    v7 = (_OWORD *)(v4 + 152);
    do
    {
      *v6 = *v7;
      v6[1] = v7[1];
      v6[2] = v7[2];
      v6[3] = v7[3];
      v6[4] = v7[4];
      v6[5] = v7[5];
      v6[6] = v7[6];
      v8 = v7[7];
      v7 += 8;
      v6[7] = v8;
      v6 += 8;
      --v5;
    }
    while ( v5 );
    *v6 = *v7;
    v9 = *(unsigned __int16 *)(v4 + 120);
    if ( (_WORD)v9 )
    {
      if ( !BUFFER::Resize((W3_REQUEST *)((char *)this + 168), 24 * v9, 0x200u) )
        return 2147942408LL;
      Ptr = BUFFER::QueryPtr((W3_REQUEST *)((char *)this + 168));
      memcpy_0(Ptr, *(const void **)(v4 + 128), 24 * v9);
    }
    *(_WORD *)(*((_QWORD *)this + 5) + 120LL) = v9;
    *(_QWORD *)(*((_QWORD *)this + 5) + 128LL) = Ptr;
    *(_QWORD *)(*((_QWORD *)this + 5) + 856LL) = *(_QWORD *)(v4 + 856);
    *(_WORD *)(*((_QWORD *)this + 5) + 848LL) = *(_WORD *)(v4 + 848);
  }
  else
  {
    memset_0((void *)(*((_QWORD *)this + 5) + 120LL), 0, 0x2B0u);
    *(_QWORD *)(*((_QWORD *)this + 5) + 856LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 848LL) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180029428  push    rbx
0x18002942a  push    rbp
0x18002942b  push    rsi
0x18002942c  push    rdi
0x18002942d  push    r14
0x18002942f  sub     rsp, 20h
0x180029433  xor     r14d, r14d
0x180029436  mov     rbx, rcx
0x180029439  test    rdx, rdx
0x18002943c  jnz     short loc_18002946D
0x18002943e  mov     rcx, [rcx+28h]
0x180029442  mov     r8d, 2B0h; Size
0x180029448  add     rcx, 78h ; 'x'; void *
0x18002944c  call    memset_0
0x180029451  mov     rax, [rbx+28h]
0x180029455  mov     [rax+358h], r14
0x18002945c  mov     rcx, [rbx+28h]
0x180029460  mov     [rcx+350h], r14w
0x180029468  jmp     loc_180029577
0x18002946d  inc     dword ptr [rdx+30h]
0x180029470  mov     rbp, r14
0x180029473  mov     rdi, [rdx+28h]
0x180029477  mov     edx, 5
0x18002947c  mov     rax, [rcx+28h]
0x180029480  add     rax, 98h
0x180029486  lea     r8d, [rdx+7Bh]
0x18002948a  lea     rcx, [rdi+98h]
0x180029491  movups  xmm0, xmmword ptr [rcx]
0x180029494  movups  xmmword ptr [rax], xmm0
0x180029497  movups  xmm1, xmmword ptr [rcx+10h]
0x18002949b  movups  xmmword ptr [rax+10h], xmm1
0x18002949f  movups  xmm0, xmmword ptr [rcx+20h]
0x1800294a3  movups  xmmword ptr [rax+20h], xmm0
0x1800294a7  movups  xmm1, xmmword ptr [rcx+30h]
0x1800294ab  movups  xmmword ptr [rax+30h], xmm1
0x1800294af  movups  xmm0, xmmword ptr [rcx+40h]
0x1800294b3  movups  xmmword ptr [rax+40h], xmm0
0x1800294b7  movups  xmm1, xmmword ptr [rcx+50h]
0x1800294bb  movups  xmmword ptr [rax+50h], xmm1
0x1800294bf  movups  xmm0, xmmword ptr [rcx+60h]
0x1800294c3  movups  xmmword ptr [rax+60h], xmm0
0x1800294c7  movups  xmm1, xmmword ptr [rcx+70h]
0x1800294cb  add     rcx, r8
0x1800294ce  movups  xmmword ptr [rax+70h], xmm1
0x1800294d2  add     rax, r8
0x1800294d5  sub     rdx, 1
0x1800294d9  jnz     short loc_180029491
0x1800294db  movups  xmm0, xmmword ptr [rcx]
0x1800294de  movups  xmmword ptr [rax], xmm0
0x1800294e1  movzx   esi, word ptr [rdi+78h]
0x1800294e5  test    si, si
0x1800294e8  jz      short loc_180029540
0x1800294ea  lea     edx, [rsi+rsi*2]
0x1800294ed  mov     r8d, 200h
0x1800294f3  lea     rbp, [rbx+0A8h]
0x1800294fa  shl     edx, 3
0x1800294fd  mov     rcx, rbp
0x180029500  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180029507  nop     dword ptr [rax+rax+00h]
0x18002950c  test    al, al
0x18002950e  jnz     short loc_180029517
0x180029510  mov     eax, 80070008h
0x180029515  jmp     short loc_180029579
0x180029517  mov     rcx, rbp
0x18002951a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180029521  nop     dword ptr [rax+rax+00h]
0x180029526  mov     rdx, [rdi+80h]; Src
0x18002952d  lea     r8, [rsi+rsi*2]
0x180029531  shl     r8, 3; Size
0x180029535  mov     rcx, rax; void *
0x180029538  mov     rbp, rax
0x18002953b  call    memcpy_0
0x180029540  mov     rcx, [rbx+28h]
0x180029544  mov     [rcx+78h], si
0x180029548  mov     rcx, [rbx+28h]
0x18002954c  mov     [rcx+80h], rbp
0x180029553  mov     rcx, [rbx+28h]
0x180029557  mov     rax, [rdi+358h]
0x18002955e  mov     [rcx+358h], rax
0x180029565  mov     rcx, [rbx+28h]
0x180029569  movzx   eax, word ptr [rdi+350h]
0x180029570  mov     [rcx+350h], ax
0x180029577  xor     eax, eax
0x180029579  add     rsp, 20h
0x18002957d  pop     r14
0x18002957f  pop     rdi
0x180029580  pop     rsi
0x180029581  pop     rbp
0x180029582  pop     rbx
0x180029583  retn
```
