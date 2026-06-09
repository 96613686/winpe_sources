# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a03c`
- end: `0x18000a124`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800073e8`

## callees

- `0x180002666`
- `0x18000a03c`
- `0x18000a8b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a09f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a09f`

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
0x18000a03c  push    rbx
0x18000a03e  push    rbp
0x18000a03f  push    rsi
0x18000a040  push    rdi
0x18000a041  push    r14
0x18000a043  push    r15
0x18000a045  sub     rsp, 28h
0x18000a049  mov     al, [rcx+2]
0x18000a04c  xor     ebp, ebp
0x18000a04e  mov     r9, [rdx]
0x18000a051  mov     rdi, r8
0x18000a054  mov     r15, rdx
0x18000a057  mov     rsi, rcx
0x18000a05a  cmp     al, 1
0x18000a05c  jnz     short loc_18000A07A
0x18000a05e  lea     rbx, [r9+2]
0x18000a062  cmp     rbx, r8
0x18000a065  ja      loc_18000A0F5
0x18000a06b  test    r9, r9
0x18000a06e  jz      short loc_18000A09F
0x18000a070  movzx   eax, word ptr [rcx+4]
0x18000a074  mov     [r9], ax
0x18000a078  jmp     short loc_18000A0B5
0x18000a07a  cmp     al, 2
0x18000a07c  jnz     short loc_18000A0B2
0x18000a07e  lea     rbx, [r9+4]
0x18000a082  cmp     rbx, rdi
0x18000a085  ja      short loc_18000A0F5
0x18000a087  test    r9, r9
0x18000a08a  jz      short loc_18000A09F
0x18000a08c  lea     rax, [rcx+4]
0x18000a090  test    rax, rax
0x18000a093  jz      short loc_18000A09C
0x18000a095  mov     eax, [rax]
0x18000a097  mov     [r9], eax
0x18000a09a  jmp     short loc_18000A0B5
0x18000a09c  mov     [r9], eax
0x18000a09f  call    cs:__imp__o__errno
0x18000a0a5  mov     dword ptr [rax], 16h
0x18000a0ab  call    _invalid_parameter_noinfo
0x18000a0b0  jmp     short loc_18000A0B5
0x18000a0b2  mov     rbx, r9
0x18000a0b5  cmp     [rsi], bp
0x18000a0b8  jnz     short loc_18000A0E3
0x18000a0ba  lea     r14, [rbx+2]
0x18000a0be  cmp     r14, rdi
0x18000a0c1  ja      short loc_18000A0F5
0x18000a0c3  lea     rbp, [rsi+8]
0x18000a0c7  mov     rdx, rdi
0x18000a0ca  sub     rdx, rbx; DestinationSize
0x18000a0cd  mov     r8, rbp; Source
0x18000a0d0  mov     r9d, 2; SourceSize
0x18000a0d6  mov     rcx, rbx; Destination
0x18000a0d9  call    memcpy_s
0x18000a0de  mov     rbx, r14
0x18000a0e1  jmp     short loc_18000A0E7
0x18000a0e3  lea     rbp, [rsi+8]
0x18000a0e7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000a0ec  lea     rax, [r9+rbx]
0x18000a0f0  cmp     rax, rdi
0x18000a0f3  jbe     short loc_18000A0F9
0x18000a0f5  xor     al, al
0x18000a0f7  jmp     short loc_18000A117
0x18000a0f9  mov     r8, [rsi+18h]; Source
0x18000a0fd  sub     rdi, rbx
0x18000a100  mov     rdx, rdi; DestinationSize
0x18000a103  mov     rcx, rbx; Destination
0x18000a106  call    memcpy_s
0x18000a10b  movzx   ecx, word ptr [rbp+0]
0x18000a10f  mov     al, 1
0x18000a111  add     rcx, rbx
0x18000a114  mov     [r15], rcx
0x18000a117  add     rsp, 28h
0x18000a11b  pop     r15
0x18000a11d  pop     r14
0x18000a11f  pop     rdi
0x18000a120  pop     rsi
0x18000a121  pop     rbp
0x18000a122  pop     rbx
0x18000a123  retn
```
