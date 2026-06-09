# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001cc54`
- end: `0x18001cd3c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018304`

## callees

- `0x180002c36`
- `0x1800075ac`
- `0x18001cc54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ccb7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ccb7`

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
0x18001cc54  push    rbx
0x18001cc56  push    rbp
0x18001cc57  push    rsi
0x18001cc58  push    rdi
0x18001cc59  push    r14
0x18001cc5b  push    r15
0x18001cc5d  sub     rsp, 28h
0x18001cc61  mov     al, [rcx+2]
0x18001cc64  xor     ebp, ebp
0x18001cc66  mov     r9, [rdx]
0x18001cc69  mov     rdi, r8
0x18001cc6c  mov     r15, rdx
0x18001cc6f  mov     rsi, rcx
0x18001cc72  cmp     al, 1
0x18001cc74  jnz     short loc_18001CC92
0x18001cc76  lea     rbx, [r9+2]
0x18001cc7a  cmp     rbx, r8
0x18001cc7d  ja      loc_18001CD0D
0x18001cc83  test    r9, r9
0x18001cc86  jz      short loc_18001CCB7
0x18001cc88  movzx   eax, word ptr [rcx+4]
0x18001cc8c  mov     [r9], ax
0x18001cc90  jmp     short loc_18001CCCD
0x18001cc92  cmp     al, 2
0x18001cc94  jnz     short loc_18001CCCA
0x18001cc96  lea     rbx, [r9+4]
0x18001cc9a  cmp     rbx, rdi
0x18001cc9d  ja      short loc_18001CD0D
0x18001cc9f  test    r9, r9
0x18001cca2  jz      short loc_18001CCB7
0x18001cca4  lea     rax, [rcx+4]
0x18001cca8  test    rax, rax
0x18001ccab  jz      short loc_18001CCB4
0x18001ccad  mov     eax, [rax]
0x18001ccaf  mov     [r9], eax
0x18001ccb2  jmp     short loc_18001CCCD
0x18001ccb4  mov     [r9], eax
0x18001ccb7  call    cs:__imp__o__errno
0x18001ccbd  mov     dword ptr [rax], 16h
0x18001ccc3  call    _invalid_parameter_noinfo
0x18001ccc8  jmp     short loc_18001CCCD
0x18001ccca  mov     rbx, r9
0x18001cccd  cmp     [rsi], bp
0x18001ccd0  jnz     short loc_18001CCFB
0x18001ccd2  lea     r14, [rbx+2]
0x18001ccd6  cmp     r14, rdi
0x18001ccd9  ja      short loc_18001CD0D
0x18001ccdb  lea     rbp, [rsi+8]
0x18001ccdf  mov     rdx, rdi
0x18001cce2  sub     rdx, rbx; DestinationSize
0x18001cce5  mov     r8, rbp; Source
0x18001cce8  mov     r9d, 2; SourceSize
0x18001ccee  mov     rcx, rbx; Destination
0x18001ccf1  call    memcpy_s
0x18001ccf6  mov     rbx, r14
0x18001ccf9  jmp     short loc_18001CCFF
0x18001ccfb  lea     rbp, [rsi+8]
0x18001ccff  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18001cd04  lea     rax, [r9+rbx]
0x18001cd08  cmp     rax, rdi
0x18001cd0b  jbe     short loc_18001CD11
0x18001cd0d  xor     al, al
0x18001cd0f  jmp     short loc_18001CD2F
0x18001cd11  mov     r8, [rsi+18h]; Source
0x18001cd15  sub     rdi, rbx
0x18001cd18  mov     rdx, rdi; DestinationSize
0x18001cd1b  mov     rcx, rbx; Destination
0x18001cd1e  call    memcpy_s
0x18001cd23  movzx   ecx, word ptr [rbp+0]
0x18001cd27  mov     al, 1
0x18001cd29  add     rcx, rbx
0x18001cd2c  mov     [r15], rcx
0x18001cd2f  add     rsp, 28h
0x18001cd33  pop     r15
0x18001cd35  pop     r14
0x18001cd37  pop     rdi
0x18001cd38  pop     rsi
0x18001cd39  pop     rbp
0x18001cd3a  pop     rbx
0x18001cd3b  retn
```
