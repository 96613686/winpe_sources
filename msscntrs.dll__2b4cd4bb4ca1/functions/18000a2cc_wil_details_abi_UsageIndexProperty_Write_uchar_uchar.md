# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a2cc`
- end: `0x18000a3b4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007f38`

## callees

- `0x1800032b2`
- `0x18000a2cc`
- `0x18000ac08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a32f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a32f`

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
0x18000a2cc  push    rbx
0x18000a2ce  push    rbp
0x18000a2cf  push    rsi
0x18000a2d0  push    rdi
0x18000a2d1  push    r14
0x18000a2d3  push    r15
0x18000a2d5  sub     rsp, 28h
0x18000a2d9  mov     al, [rcx+2]
0x18000a2dc  xor     ebp, ebp
0x18000a2de  mov     r9, [rdx]
0x18000a2e1  mov     rdi, r8
0x18000a2e4  mov     r15, rdx
0x18000a2e7  mov     rsi, rcx
0x18000a2ea  cmp     al, 1
0x18000a2ec  jnz     short loc_18000A30A
0x18000a2ee  lea     rbx, [r9+2]
0x18000a2f2  cmp     rbx, r8
0x18000a2f5  ja      loc_18000A385
0x18000a2fb  test    r9, r9
0x18000a2fe  jz      short loc_18000A32F
0x18000a300  movzx   eax, word ptr [rcx+4]
0x18000a304  mov     [r9], ax
0x18000a308  jmp     short loc_18000A345
0x18000a30a  cmp     al, 2
0x18000a30c  jnz     short loc_18000A342
0x18000a30e  lea     rbx, [r9+4]
0x18000a312  cmp     rbx, rdi
0x18000a315  ja      short loc_18000A385
0x18000a317  test    r9, r9
0x18000a31a  jz      short loc_18000A32F
0x18000a31c  lea     rax, [rcx+4]
0x18000a320  test    rax, rax
0x18000a323  jz      short loc_18000A32C
0x18000a325  mov     eax, [rax]
0x18000a327  mov     [r9], eax
0x18000a32a  jmp     short loc_18000A345
0x18000a32c  mov     [r9], eax
0x18000a32f  call    cs:__imp__o__errno
0x18000a335  mov     dword ptr [rax], 16h
0x18000a33b  call    _invalid_parameter_noinfo
0x18000a340  jmp     short loc_18000A345
0x18000a342  mov     rbx, r9
0x18000a345  cmp     [rsi], bp
0x18000a348  jnz     short loc_18000A373
0x18000a34a  lea     r14, [rbx+2]
0x18000a34e  cmp     r14, rdi
0x18000a351  ja      short loc_18000A385
0x18000a353  lea     rbp, [rsi+8]
0x18000a357  mov     rdx, rdi
0x18000a35a  sub     rdx, rbx; DestinationSize
0x18000a35d  mov     r8, rbp; Source
0x18000a360  mov     r9d, 2; SourceSize
0x18000a366  mov     rcx, rbx; Destination
0x18000a369  call    memcpy_s
0x18000a36e  mov     rbx, r14
0x18000a371  jmp     short loc_18000A377
0x18000a373  lea     rbp, [rsi+8]
0x18000a377  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000a37c  lea     rax, [r9+rbx]
0x18000a380  cmp     rax, rdi
0x18000a383  jbe     short loc_18000A389
0x18000a385  xor     al, al
0x18000a387  jmp     short loc_18000A3A7
0x18000a389  mov     r8, [rsi+18h]; Source
0x18000a38d  sub     rdi, rbx
0x18000a390  mov     rdx, rdi; DestinationSize
0x18000a393  mov     rcx, rbx; Destination
0x18000a396  call    memcpy_s
0x18000a39b  movzx   ecx, word ptr [rbp+0]
0x18000a39f  mov     al, 1
0x18000a3a1  add     rcx, rbx
0x18000a3a4  mov     [r15], rcx
0x18000a3a7  add     rsp, 28h
0x18000a3ab  pop     r15
0x18000a3ad  pop     r14
0x18000a3af  pop     rdi
0x18000a3b0  pop     rsi
0x18000a3b1  pop     rbp
0x18000a3b2  pop     rbx
0x18000a3b3  retn
```
