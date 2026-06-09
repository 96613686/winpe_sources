# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180022c1c`
- end: `0x180022cf2`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011d74`

## callees

- `0x1800118a4`
- `0x180022c1c`

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
0x180022c1c  push    rbx
0x180022c1e  push    rsi
0x180022c1f  push    rdi
0x180022c20  push    r12
0x180022c22  push    r14
0x180022c24  push    r15
0x180022c26  sub     rsp, 28h
0x180022c2a  mov     rsi, rcx
0x180022c2d  mov     rdi, r8
0x180022c30  mov     rcx, [rdx]; Destination
0x180022c33  mov     r12, rdx
0x180022c36  cmp     byte ptr [rsi+2], 1
0x180022c3a  jnz     short loc_180022C5E
0x180022c3c  lea     rbx, [rcx+2]
0x180022c40  cmp     rbx, r8
0x180022c43  ja      short loc_180022CC1
0x180022c45  movzx   eax, word ptr [rsi+4]
0x180022c49  lea     r8, [rsp+58h+arg_0]
0x180022c4e  mov     r9d, 2
0x180022c54  mov     [rsp+58h+arg_0], ax
0x180022c59  mov     edx, r9d
0x180022c5c  jmp     short loc_180022C7C
0x180022c5e  cmp     byte ptr [rsi+2], 2
0x180022c62  mov     rbx, rcx
0x180022c65  jnz     short loc_180022C81
0x180022c67  lea     rbx, [rcx+4]
0x180022c6b  cmp     rbx, rdi
0x180022c6e  ja      short loc_180022CC1
0x180022c70  mov     edx, 4; DestinationSize
0x180022c75  lea     r8, [rsi+4]; Source
0x180022c79  mov     r9d, edx; SourceSize
0x180022c7c  call    memcpy_s
0x180022c81  cmp     word ptr [rsi], 0
0x180022c85  jnz     short loc_180022CB0
0x180022c87  lea     r15, [rbx+2]
0x180022c8b  cmp     r15, rdi
0x180022c8e  ja      short loc_180022CC1
0x180022c90  lea     r14, [rsi+8]
0x180022c94  mov     rdx, rdi
0x180022c97  sub     rdx, rbx; DestinationSize
0x180022c9a  mov     r8, r14; Source
0x180022c9d  mov     r9d, 2; SourceSize
0x180022ca3  mov     rcx, rbx; Destination
0x180022ca6  call    memcpy_s
0x180022cab  mov     rbx, r15
0x180022cae  jmp     short loc_180022CB4
0x180022cb0  lea     r14, [rsi+8]
0x180022cb4  movzx   r9d, word ptr [r14]; SourceSize
0x180022cb8  lea     rax, [r9+rbx]
0x180022cbc  cmp     rax, rdi
0x180022cbf  jbe     short loc_180022CC5
0x180022cc1  xor     al, al
0x180022cc3  jmp     short loc_180022CE4
0x180022cc5  mov     r8, [rsi+18h]; Source
0x180022cc9  sub     rdi, rbx
0x180022ccc  mov     rdx, rdi; DestinationSize
0x180022ccf  mov     rcx, rbx; Destination
0x180022cd2  call    memcpy_s
0x180022cd7  movzx   ecx, word ptr [r14]
0x180022cdb  mov     al, 1
0x180022cdd  add     rcx, rbx
0x180022ce0  mov     [r12], rcx
0x180022ce4  add     rsp, 28h
0x180022ce8  pop     r15
0x180022cea  pop     r14
0x180022cec  pop     r12
0x180022cee  pop     rdi
0x180022cef  pop     rsi
0x180022cf0  pop     rbx
0x180022cf1  retn
```
