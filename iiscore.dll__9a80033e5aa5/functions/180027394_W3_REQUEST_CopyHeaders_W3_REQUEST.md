# W3_REQUEST::CopyHeaders(W3_REQUEST *)

- ea: `0x180027394`
- end: `0x1800274e4`
- name: `?CopyHeaders@W3_REQUEST@@QEAAJPEAV1@@Z`
- size: `336`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, struct W3_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002701c`

## callees

- `0x180027394`
- `0x180034382`
- `0x18003439a`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027480`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027480`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18002746c`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18002746c`

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
0x180027394  push    rbx
0x180027396  push    rbp
0x180027397  push    rsi
0x180027398  push    rdi
0x180027399  push    r14
0x18002739b  sub     rsp, 20h
0x18002739f  xor     r14d, r14d
0x1800273a2  mov     rbx, rcx
0x1800273a5  test    rdx, rdx
0x1800273a8  jnz     short loc_1800273D9
0x1800273aa  mov     rcx, [rcx+28h]
0x1800273ae  mov     r8d, 2B0h; Size
0x1800273b4  add     rcx, 78h ; 'x'; void *
0x1800273b8  call    memset_0
0x1800273bd  mov     rax, [rbx+28h]
0x1800273c1  mov     [rax+358h], r14
0x1800273c8  mov     rcx, [rbx+28h]
0x1800273cc  mov     [rcx+350h], r14w
0x1800273d4  jmp     loc_1800274D7
0x1800273d9  inc     dword ptr [rdx+30h]
0x1800273dc  mov     rbp, r14
0x1800273df  mov     rdi, [rdx+28h]
0x1800273e3  mov     edx, 5
0x1800273e8  mov     rax, [rcx+28h]
0x1800273ec  add     rax, 98h
0x1800273f2  lea     r8d, [rdx+7Bh]
0x1800273f6  lea     rcx, [rdi+98h]
0x1800273fd  movups  xmm0, xmmword ptr [rcx]
0x180027400  movups  xmmword ptr [rax], xmm0
0x180027403  movups  xmm1, xmmword ptr [rcx+10h]
0x180027407  movups  xmmword ptr [rax+10h], xmm1
0x18002740b  movups  xmm0, xmmword ptr [rcx+20h]
0x18002740f  movups  xmmword ptr [rax+20h], xmm0
0x180027413  movups  xmm1, xmmword ptr [rcx+30h]
0x180027417  movups  xmmword ptr [rax+30h], xmm1
0x18002741b  movups  xmm0, xmmword ptr [rcx+40h]
0x18002741f  movups  xmmword ptr [rax+40h], xmm0
0x180027423  movups  xmm1, xmmword ptr [rcx+50h]
0x180027427  movups  xmmword ptr [rax+50h], xmm1
0x18002742b  movups  xmm0, xmmword ptr [rcx+60h]
0x18002742f  movups  xmmword ptr [rax+60h], xmm0
0x180027433  movups  xmm1, xmmword ptr [rcx+70h]
0x180027437  add     rcx, r8
0x18002743a  movups  xmmword ptr [rax+70h], xmm1
0x18002743e  add     rax, r8
0x180027441  sub     rdx, 1
0x180027445  jnz     short loc_1800273FD
0x180027447  movups  xmm0, xmmword ptr [rcx]
0x18002744a  movups  xmmword ptr [rax], xmm0
0x18002744d  movzx   esi, word ptr [rdi+78h]
0x180027451  test    si, si
0x180027454  jz      short loc_1800274A0
0x180027456  lea     edx, [rsi+rsi*2]
0x180027459  mov     r8d, 200h
0x18002745f  lea     rbp, [rbx+0A8h]
0x180027466  shl     edx, 3
0x180027469  mov     rcx, rbp
0x18002746c  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180027472  test    al, al
0x180027474  jnz     short loc_18002747D
0x180027476  mov     eax, 80070008h
0x18002747b  jmp     short loc_1800274D9
0x18002747d  mov     rcx, rbp
0x180027480  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027486  mov     rdx, [rdi+80h]; Src
0x18002748d  lea     r8, [rsi+rsi*2]
0x180027491  shl     r8, 3; Size
0x180027495  mov     rcx, rax; void *
0x180027498  mov     rbp, rax
0x18002749b  call    memcpy_0
0x1800274a0  mov     rcx, [rbx+28h]
0x1800274a4  mov     [rcx+78h], si
0x1800274a8  mov     rcx, [rbx+28h]
0x1800274ac  mov     [rcx+80h], rbp
0x1800274b3  mov     rcx, [rbx+28h]
0x1800274b7  mov     rax, [rdi+358h]
0x1800274be  mov     [rcx+358h], rax
0x1800274c5  mov     rcx, [rbx+28h]
0x1800274c9  movzx   eax, word ptr [rdi+350h]
0x1800274d0  mov     [rcx+350h], ax
0x1800274d7  xor     eax, eax
0x1800274d9  add     rsp, 20h
0x1800274dd  pop     r14
0x1800274df  pop     rdi
0x1800274e0  pop     rsi
0x1800274e1  pop     rbp
0x1800274e2  pop     rbx
0x1800274e3  retn
```
