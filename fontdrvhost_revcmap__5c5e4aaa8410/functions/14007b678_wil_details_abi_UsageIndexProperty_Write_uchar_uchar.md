# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14007b678`
- end: `0x14007b74e`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140075778`

## callees

- `0x14007b678`
- `0x14007bed8`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x14007b678  push    rbx
0x14007b67a  push    rsi
0x14007b67b  push    rdi
0x14007b67c  push    r12
0x14007b67e  push    r14
0x14007b680  push    r15
0x14007b682  sub     rsp, 28h
0x14007b686  mov     rsi, rcx
0x14007b689  mov     rdi, r8
0x14007b68c  mov     rcx, [rdx]; Destination
0x14007b68f  mov     r12, rdx
0x14007b692  cmp     byte ptr [rsi+2], 1
0x14007b696  jnz     short loc_14007B6BA
0x14007b698  lea     rbx, [rcx+2]
0x14007b69c  cmp     rbx, r8
0x14007b69f  ja      short loc_14007B71D
0x14007b6a1  movzx   eax, word ptr [rsi+4]
0x14007b6a5  lea     r8, [rsp+58h+arg_0]
0x14007b6aa  mov     r9d, 2
0x14007b6b0  mov     [rsp+58h+arg_0], ax
0x14007b6b5  mov     edx, r9d
0x14007b6b8  jmp     short loc_14007B6D8
0x14007b6ba  cmp     byte ptr [rsi+2], 2
0x14007b6be  mov     rbx, rcx
0x14007b6c1  jnz     short loc_14007B6DD
0x14007b6c3  lea     rbx, [rcx+4]
0x14007b6c7  cmp     rbx, rdi
0x14007b6ca  ja      short loc_14007B71D
0x14007b6cc  mov     edx, 4; DestinationSize
0x14007b6d1  lea     r8, [rsi+4]; Source
0x14007b6d5  mov     r9d, edx; SourceSize
0x14007b6d8  call    memcpy_s
0x14007b6dd  cmp     word ptr [rsi], 0
0x14007b6e1  jnz     short loc_14007B70C
0x14007b6e3  lea     r15, [rbx+2]
0x14007b6e7  cmp     r15, rdi
0x14007b6ea  ja      short loc_14007B71D
0x14007b6ec  lea     r14, [rsi+8]
0x14007b6f0  mov     rdx, rdi
0x14007b6f3  sub     rdx, rbx; DestinationSize
0x14007b6f6  mov     r8, r14; Source
0x14007b6f9  mov     r9d, 2; SourceSize
0x14007b6ff  mov     rcx, rbx; Destination
0x14007b702  call    memcpy_s
0x14007b707  mov     rbx, r15
0x14007b70a  jmp     short loc_14007B710
0x14007b70c  lea     r14, [rsi+8]
0x14007b710  movzx   r9d, word ptr [r14]; SourceSize
0x14007b714  lea     rax, [r9+rbx]
0x14007b718  cmp     rax, rdi
0x14007b71b  jbe     short loc_14007B721
0x14007b71d  xor     al, al
0x14007b71f  jmp     short loc_14007B740
0x14007b721  mov     r8, [rsi+18h]; Source
0x14007b725  sub     rdi, rbx
0x14007b728  mov     rdx, rdi; DestinationSize
0x14007b72b  mov     rcx, rbx; Destination
0x14007b72e  call    memcpy_s
0x14007b733  movzx   ecx, word ptr [r14]
0x14007b737  mov     al, 1
0x14007b739  add     rcx, rbx
0x14007b73c  mov     [r12], rcx
0x14007b740  add     rsp, 28h
0x14007b744  pop     r15
0x14007b746  pop     r14
0x14007b748  pop     r12
0x14007b74a  pop     rdi
0x14007b74b  pop     rsi
0x14007b74c  pop     rbx
0x14007b74d  retn
```
