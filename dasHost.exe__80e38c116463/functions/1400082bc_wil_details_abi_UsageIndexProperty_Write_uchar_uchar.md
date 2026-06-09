# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1400082bc`
- end: `0x1400083a4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400060f8`

## callees

- `0x14000202e`
- `0x1400082bc`
- `0x140008948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000831f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000831f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x1400082bc  push    rbx
0x1400082be  push    rbp
0x1400082bf  push    rsi
0x1400082c0  push    rdi
0x1400082c1  push    r14
0x1400082c3  push    r15
0x1400082c5  sub     rsp, 28h
0x1400082c9  mov     al, [rcx+2]
0x1400082cc  xor     ebp, ebp
0x1400082ce  mov     r9, [rdx]
0x1400082d1  mov     rdi, r8
0x1400082d4  mov     r15, rdx
0x1400082d7  mov     rsi, rcx
0x1400082da  cmp     al, 1
0x1400082dc  jnz     short loc_1400082FA
0x1400082de  lea     rbx, [r9+2]
0x1400082e2  cmp     rbx, r8
0x1400082e5  ja      loc_140008375
0x1400082eb  test    r9, r9
0x1400082ee  jz      short loc_14000831F
0x1400082f0  movzx   eax, word ptr [rcx+4]
0x1400082f4  mov     [r9], ax
0x1400082f8  jmp     short loc_140008335
0x1400082fa  cmp     al, 2
0x1400082fc  jnz     short loc_140008332
0x1400082fe  lea     rbx, [r9+4]
0x140008302  cmp     rbx, rdi
0x140008305  ja      short loc_140008375
0x140008307  test    r9, r9
0x14000830a  jz      short loc_14000831F
0x14000830c  lea     rax, [rcx+4]
0x140008310  test    rax, rax
0x140008313  jz      short loc_14000831C
0x140008315  mov     eax, [rax]
0x140008317  mov     [r9], eax
0x14000831a  jmp     short loc_140008335
0x14000831c  mov     [r9], eax
0x14000831f  call    cs:__imp__o__errno
0x140008325  mov     dword ptr [rax], 16h
0x14000832b  call    _invalid_parameter_noinfo
0x140008330  jmp     short loc_140008335
0x140008332  mov     rbx, r9
0x140008335  cmp     [rsi], bp
0x140008338  jnz     short loc_140008363
0x14000833a  lea     r14, [rbx+2]
0x14000833e  cmp     r14, rdi
0x140008341  ja      short loc_140008375
0x140008343  lea     rbp, [rsi+8]
0x140008347  mov     rdx, rdi
0x14000834a  sub     rdx, rbx; DestinationSize
0x14000834d  mov     r8, rbp; Source
0x140008350  mov     r9d, 2; SourceSize
0x140008356  mov     rcx, rbx; Destination
0x140008359  call    memcpy_s
0x14000835e  mov     rbx, r14
0x140008361  jmp     short loc_140008367
0x140008363  lea     rbp, [rsi+8]
0x140008367  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000836c  lea     rax, [r9+rbx]
0x140008370  cmp     rax, rdi
0x140008373  jbe     short loc_140008379
0x140008375  xor     al, al
0x140008377  jmp     short loc_140008397
0x140008379  mov     r8, [rsi+18h]; Source
0x14000837d  sub     rdi, rbx
0x140008380  mov     rdx, rdi; DestinationSize
0x140008383  mov     rcx, rbx; Destination
0x140008386  call    memcpy_s
0x14000838b  movzx   ecx, word ptr [rbp+0]
0x14000838f  mov     al, 1
0x140008391  add     rcx, rbx
0x140008394  mov     [r15], rcx
0x140008397  add     rsp, 28h
0x14000839b  pop     r15
0x14000839d  pop     r14
0x14000839f  pop     rdi
0x1400083a0  pop     rsi
0x1400083a1  pop     rbp
0x1400083a2  pop     rbx
0x1400083a3  retn
```
