# HandleDoubleQuote

- ea: `0x180001e10`
- end: `0x18000203c`
- name: `HandleDoubleQuote`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d88`

## callees

- `0x180001e10`
- `0x180002044`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fe2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fe2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002018`

## pseudocode

```c
__int64 __fastcall HandleDoubleQuote(
        unsigned int a1,
        const unsigned __int16 **a2,
        const unsigned __int16 **a3,
        HLOCAL *a4)
{
  _WORD *v4; // rax
  unsigned __int16 *v7; // rsi
  __int64 v8; // rdi
  signed int v9; // ebx
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // rbp
  __int64 v13; // r13
  unsigned __int64 v14; // rax
  int v15; // r15d
  unsigned __int64 v16; // rdi
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // r8
  unsigned __int16 *v23; // rdi
  unsigned __int64 i; // rcx
  const unsigned __int16 *v25; // rax
  unsigned __int64 v28; // [rsp+78h] [rbp+20h]

  v4 = *a4;
  v7 = 0;
  if ( *a4 )
  {
    v8 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v8;
    }
    while ( v8 );
    v9 = v8 == 0 ? 0x80070057 : 0;
    v10 = (0x7FFFFFFF - v8) & ((unsigned __int128)-(__int128)(unsigned __int64)v8 >> 64);
    if ( !v8 )
      goto LABEL_38;
  }
  else
  {
    v10 = 0;
  }
  v11 = (unsigned int)(*a2 - *a3) - a1;
  if ( (unsigned int)v11 > 0x7FFFFFFF )
  {
LABEL_9:
    v9 = -2147467259;
    goto LABEL_38;
  }
  v12 = v11 + v10;
  v28 = (unsigned int)(*a2 - *a3) - a1;
  if ( v11 + v10 < v10 )
    goto LABEL_37;
  v13 = a1 >> 1;
  v14 = v13 + v12;
  if ( v13 + v12 < v12 )
    goto LABEL_37;
  v15 = a1 & 1;
  if ( (a1 & 1) == 0 )
    goto LABEL_15;
  if ( v14 + 1 < v14 )
  {
LABEL_37:
    v9 = -2147024362;
    goto LABEL_38;
  }
  ++v14;
LABEL_15:
  v16 = v14 + 1;
  if ( v14 + 1 < v14 )
    goto LABEL_37;
  if ( v16 > 0x7FFFFFFF )
    goto LABEL_9;
  v7 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v16));
  if ( v7 )
  {
    v17 = (unsigned __int16 *)*a4;
    if ( !*a4 )
      goto LABEL_28;
    if ( !v16 )
    {
      v9 = -2147024809;
      goto LABEL_38;
    }
    v18 = 2147483646;
    v19 = v16;
    v20 = v7;
    do
    {
      if ( !v18 )
        break;
      if ( !*v17 )
        break;
      *v20++ = *v17++;
      --v18;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    v9 = v19 == 0 ? 0x8007007A : 0;
    if ( v19 )
      v21 = v20;
    *v21 = 0;
    if ( v19 )
    {
LABEL_28:
      v9 = StringCchCatNW(v7, v16, *a3, v28);
      if ( v9 >= 0 )
      {
        v22 = &v7[v12];
        if ( (_DWORD)v13 )
        {
          v23 = &v7[v12];
          v22 += v13;
          for ( i = (unsigned __int64)(2 * v13) >> 1; i; --i )
            *v23++ = 92;
        }
        if ( v15 )
        {
          *v22 = 34;
          ++*a2;
        }
        LocalFree(*a4);
        v25 = *a2;
        *a4 = v7;
        v7 = 0;
        *a3 = v25;
      }
    }
  }
  else
  {
    v9 = -2147024882;
  }
LABEL_38:
  LocalFree(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001e10  mov     [rsp+arg_0], rbx
0x180001e15  mov     [rsp+arg_10], r8
0x180001e1a  push    rbp
0x180001e1b  push    rsi
0x180001e1c  push    rdi
0x180001e1d  push    r12
0x180001e1f  push    r13
0x180001e21  push    r14
0x180001e23  push    r15
0x180001e25  sub     rsp, 20h
0x180001e29  mov     rax, [r9]
0x180001e2c  xor     ebx, ebx
0x180001e2e  mov     r12, r9
0x180001e31  mov     r14, rdx
0x180001e34  mov     r15d, ecx
0x180001e37  mov     esi, ebx
0x180001e39  mov     r10d, 7FFFFFFFh
0x180001e3f  test    rax, rax
0x180001e42  jz      short loc_180001E83
0x180001e44  mov     edi, r10d
0x180001e47  cmp     [rax], bx
0x180001e4a  jz      short loc_180001E56
0x180001e4c  add     rax, 2
0x180001e50  sub     rdi, 1
0x180001e54  jnz     short loc_180001E47
0x180001e56  mov     rax, rdi
0x180001e59  mov     rcx, r10
0x180001e5c  neg     rax
0x180001e5f  mov     rax, rdi
0x180001e62  sbb     ebx, ebx
0x180001e64  sub     rcx, rdi
0x180001e67  not     ebx
0x180001e69  and     ebx, 80070057h
0x180001e6f  neg     rax
0x180001e72  sbb     rdx, rdx
0x180001e75  and     rdx, rcx
0x180001e78  test    rdi, rdi
0x180001e7b  jz      loc_180002015
0x180001e81  jmp     short loc_180001E86
0x180001e83  mov     rdx, rbx
0x180001e86  mov     rax, [r14]
0x180001e89  sub     rax, [r8]
0x180001e8c  sar     rax, 1
0x180001e8f  sub     eax, r15d
0x180001e92  cmp     eax, r10d
0x180001e95  jbe     short loc_180001EA1
0x180001e97  mov     ebx, 80004005h
0x180001e9c  jmp     loc_180002015
0x180001ea1  lea     rbp, [rax+rdx]
0x180001ea5  mov     [rsp+58h+arg_18], rax
0x180001eaa  cmp     rbp, rdx
0x180001ead  jb      loc_180002010
0x180001eb3  mov     r13d, r15d
0x180001eb6  mov     rax, rbp
0x180001eb9  shr     r13d, 1
0x180001ebc  add     rax, r13
0x180001ebf  cmp     rax, rbp
0x180001ec2  jb      loc_180002010
0x180001ec8  and     r15d, 1
0x180001ecc  jz      short loc_180001EDE
0x180001ece  lea     rcx, [rax+1]
0x180001ed2  cmp     rcx, rax
0x180001ed5  jb      loc_180002010
0x180001edb  mov     rax, rcx
0x180001ede  lea     rdi, [rax+1]
0x180001ee2  cmp     rdi, rax
0x180001ee5  jb      loc_180002010
0x180001eeb  cmp     rdi, r10
0x180001eee  ja      short loc_180001E97
0x180001ef0  test    edi, edi
0x180001ef2  js      loc_180002009
0x180001ef8  lea     edx, [rdi+rdi]; uBytes
0x180001efb  mov     ecx, 40h ; '@'; uFlags
0x180001f00  call    cs:__imp_LocalAlloc
0x180001f07  nop     dword ptr [rax+rax+00h]
0x180001f0c  mov     rsi, rax
0x180001f0f  test    rax, rax
0x180001f12  jnz     short loc_180001F1E
0x180001f14  mov     ebx, 8007000Eh
0x180001f19  jmp     loc_180002015
0x180001f1e  mov     rax, [r12]
0x180001f22  test    rax, rax
0x180001f25  jz      short loc_180001F87
0x180001f27  test    rdi, rdi
0x180001f2a  jz      loc_180002002
0x180001f30  mov     ecx, 7FFFFFFEh
0x180001f35  mov     rdx, rdi
0x180001f38  mov     r8, rsi
0x180001f3b  test    rcx, rcx
0x180001f3e  jz      short loc_180001F5F
0x180001f40  movzx   r9d, word ptr [rax]
0x180001f44  test    r9w, r9w
0x180001f48  jz      short loc_180001F5F
0x180001f4a  mov     [r8], r9w
0x180001f4e  add     rax, 2
0x180001f52  add     r8, 2
0x180001f56  dec     rcx
0x180001f59  sub     rdx, 1
0x180001f5d  jnz     short loc_180001F3B
0x180001f5f  mov     rax, rdx
0x180001f62  lea     rcx, [r8-2]
0x180001f66  neg     rax
0x180001f69  sbb     ebx, ebx
0x180001f6b  xor     r9d, r9d
0x180001f6e  not     ebx
0x180001f70  and     ebx, 8007007Ah
0x180001f76  test    rdx, rdx
0x180001f79  cmovnz  rcx, r8
0x180001f7d  mov     [rcx], r9w
0x180001f81  jz      loc_180002015
0x180001f87  mov     rax, [rsp+58h+arg_10]
0x180001f8c  mov     rdx, rdi; unsigned __int64
0x180001f8f  mov     r9, [rsp+58h+arg_18]; unsigned __int64
0x180001f94  mov     rcx, rsi; unsigned __int16 *
0x180001f97  mov     r8, [rax]; unsigned __int16 *
0x180001f9a  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180001f9f  xor     edi, edi
0x180001fa1  mov     ebx, eax
0x180001fa3  test    eax, eax
0x180001fa5  js      short loc_180002015
0x180001fa7  lea     r8, [rsi+rbp*2]
0x180001fab  test    r13d, r13d
0x180001fae  jz      short loc_180001FCF
0x180001fb0  lea     eax, [rdi+5Ch]
0x180001fb3  mov     rdi, r8
0x180001fb6  lea     rdx, ds:0[r13*2]
0x180001fbe  movzx   eax, ax
0x180001fc1  mov     rcx, rdx
0x180001fc4  add     r8, rdx
0x180001fc7  shr     rcx, 1
0x180001fca  rep stosw
0x180001fcd  xor     edi, edi
0x180001fcf  test    r15d, r15d
0x180001fd2  jz      short loc_180001FDE
0x180001fd4  mov     word ptr [r8], 22h ; '"'
0x180001fda  add     qword ptr [r14], 2
0x180001fde  mov     rcx, [r12]; hMem
0x180001fe2  call    cs:__imp_LocalFree
0x180001fe9  nop     dword ptr [rax+rax+00h]
0x180001fee  mov     rcx, [rsp+58h+arg_10]
0x180001ff3  mov     rax, [r14]
0x180001ff6  mov     [r12], rsi
0x180001ffa  mov     rsi, rdi
0x180001ffd  mov     [rcx], rax
0x180002000  jmp     short loc_180002015
0x180002002  mov     ebx, 80070057h
0x180002007  jmp     short loc_180002015
0x180002009  mov     ebx, 82AA0003h
0x18000200e  jmp     short loc_180002015
0x180002010  mov     ebx, 80070216h
0x180002015  mov     rcx, rsi; hMem
0x180002018  call    cs:__imp_LocalFree
0x18000201f  nop     dword ptr [rax+rax+00h]
0x180002024  mov     eax, ebx
0x180002026  mov     rbx, [rsp+58h+arg_0]
0x18000202b  add     rsp, 20h
0x18000202f  pop     r15
0x180002031  pop     r14
0x180002033  pop     r13
0x180002035  pop     r12
0x180002037  pop     rdi
0x180002038  pop     rsi
0x180002039  pop     rbp
0x18000203a  retn
```
