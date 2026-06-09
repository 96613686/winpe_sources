# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180008dcc`
- end: `0x180008eb4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006be8`

## callees

- `0x18000214a`
- `0x180008dcc`
- `0x180009458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e2f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e2f`

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
0x180008dcc  push    rbx
0x180008dce  push    rbp
0x180008dcf  push    rsi
0x180008dd0  push    rdi
0x180008dd1  push    r14
0x180008dd3  push    r15
0x180008dd5  sub     rsp, 28h
0x180008dd9  mov     al, [rcx+2]
0x180008ddc  xor     ebp, ebp
0x180008dde  mov     r9, [rdx]
0x180008de1  mov     rdi, r8
0x180008de4  mov     r15, rdx
0x180008de7  mov     rsi, rcx
0x180008dea  cmp     al, 1
0x180008dec  jnz     short loc_180008E0A
0x180008dee  lea     rbx, [r9+2]
0x180008df2  cmp     rbx, r8
0x180008df5  ja      loc_180008E85
0x180008dfb  test    r9, r9
0x180008dfe  jz      short loc_180008E2F
0x180008e00  movzx   eax, word ptr [rcx+4]
0x180008e04  mov     [r9], ax
0x180008e08  jmp     short loc_180008E45
0x180008e0a  cmp     al, 2
0x180008e0c  jnz     short loc_180008E42
0x180008e0e  lea     rbx, [r9+4]
0x180008e12  cmp     rbx, rdi
0x180008e15  ja      short loc_180008E85
0x180008e17  test    r9, r9
0x180008e1a  jz      short loc_180008E2F
0x180008e1c  lea     rax, [rcx+4]
0x180008e20  test    rax, rax
0x180008e23  jz      short loc_180008E2C
0x180008e25  mov     eax, [rax]
0x180008e27  mov     [r9], eax
0x180008e2a  jmp     short loc_180008E45
0x180008e2c  mov     [r9], eax
0x180008e2f  call    cs:__imp__o__errno
0x180008e35  mov     dword ptr [rax], 16h
0x180008e3b  call    _invalid_parameter_noinfo
0x180008e40  jmp     short loc_180008E45
0x180008e42  mov     rbx, r9
0x180008e45  cmp     [rsi], bp
0x180008e48  jnz     short loc_180008E73
0x180008e4a  lea     r14, [rbx+2]
0x180008e4e  cmp     r14, rdi
0x180008e51  ja      short loc_180008E85
0x180008e53  lea     rbp, [rsi+8]
0x180008e57  mov     rdx, rdi
0x180008e5a  sub     rdx, rbx; DestinationSize
0x180008e5d  mov     r8, rbp; Source
0x180008e60  mov     r9d, 2; SourceSize
0x180008e66  mov     rcx, rbx; Destination
0x180008e69  call    memcpy_s
0x180008e6e  mov     rbx, r14
0x180008e71  jmp     short loc_180008E77
0x180008e73  lea     rbp, [rsi+8]
0x180008e77  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180008e7c  lea     rax, [r9+rbx]
0x180008e80  cmp     rax, rdi
0x180008e83  jbe     short loc_180008E89
0x180008e85  xor     al, al
0x180008e87  jmp     short loc_180008EA7
0x180008e89  mov     r8, [rsi+18h]; Source
0x180008e8d  sub     rdi, rbx
0x180008e90  mov     rdx, rdi; DestinationSize
0x180008e93  mov     rcx, rbx; Destination
0x180008e96  call    memcpy_s
0x180008e9b  movzx   ecx, word ptr [rbp+0]
0x180008e9f  mov     al, 1
0x180008ea1  add     rcx, rbx
0x180008ea4  mov     [r15], rcx
0x180008ea7  add     rsp, 28h
0x180008eab  pop     r15
0x180008ead  pop     r14
0x180008eaf  pop     rdi
0x180008eb0  pop     rsi
0x180008eb1  pop     rbp
0x180008eb2  pop     rbx
0x180008eb3  retn
```
