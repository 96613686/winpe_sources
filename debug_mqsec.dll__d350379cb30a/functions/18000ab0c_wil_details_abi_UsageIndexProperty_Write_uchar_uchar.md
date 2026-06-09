# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000ab0c`
- end: `0x18000abe5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009288`

## callees

- `0x18000ab0c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ab6c`
- `msvcrt!memcpy_s` at `0x18000ab97`
- `msvcrt!memcpy_s` at `0x18000abc4`
- `msvcrt!memcpy_s` at `0x18000ab6c`
- `msvcrt!memcpy_s` at `0x18000ab97`
- `msvcrt!memcpy_s` at `0x18000abc4`

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
0x18000ab0c  push    rbx
0x18000ab0e  push    rsi
0x18000ab0f  push    rdi
0x18000ab10  push    r12
0x18000ab12  push    r14
0x18000ab14  push    r15
0x18000ab16  sub     rsp, 28h
0x18000ab1a  mov     rsi, rcx
0x18000ab1d  mov     rdi, r8
0x18000ab20  mov     rcx, [rdx]; Destination
0x18000ab23  mov     r12, rdx
0x18000ab26  cmp     byte ptr [rsi+2], 1
0x18000ab2a  jnz     short loc_18000AB4E
0x18000ab2c  lea     rbx, [rcx+2]
0x18000ab30  cmp     rbx, r8
0x18000ab33  ja      short loc_18000ABB3
0x18000ab35  movzx   eax, word ptr [rsi+4]
0x18000ab39  lea     r8, [rsp+58h+arg_0]
0x18000ab3e  mov     r9d, 2
0x18000ab44  mov     [rsp+58h+arg_0], ax
0x18000ab49  mov     edx, r9d
0x18000ab4c  jmp     short loc_18000AB6C
0x18000ab4e  cmp     byte ptr [rsi+2], 2
0x18000ab52  mov     rbx, rcx
0x18000ab55  jnz     short loc_18000AB72
0x18000ab57  lea     rbx, [rcx+4]
0x18000ab5b  cmp     rbx, rdi
0x18000ab5e  ja      short loc_18000ABB3
0x18000ab60  mov     edx, 4; DestinationSize
0x18000ab65  lea     r8, [rsi+4]; Source
0x18000ab69  mov     r9d, edx; SourceSize
0x18000ab6c  call    cs:__imp_memcpy_s
0x18000ab72  cmp     word ptr [rsi], 0
0x18000ab76  jnz     short loc_18000ABA2
0x18000ab78  lea     r15, [rbx+2]
0x18000ab7c  cmp     r15, rdi
0x18000ab7f  ja      short loc_18000ABB3
0x18000ab81  lea     r14, [rsi+8]
0x18000ab85  mov     rdx, rdi
0x18000ab88  sub     rdx, rbx; DestinationSize
0x18000ab8b  mov     r8, r14; Source
0x18000ab8e  mov     r9d, 2; SourceSize
0x18000ab94  mov     rcx, rbx; Destination
0x18000ab97  call    cs:__imp_memcpy_s
0x18000ab9d  mov     rbx, r15
0x18000aba0  jmp     short loc_18000ABA6
0x18000aba2  lea     r14, [rsi+8]
0x18000aba6  movzx   r9d, word ptr [r14]; SourceSize
0x18000abaa  lea     rax, [r9+rbx]
0x18000abae  cmp     rax, rdi
0x18000abb1  jbe     short loc_18000ABB7
0x18000abb3  xor     al, al
0x18000abb5  jmp     short loc_18000ABD7
0x18000abb7  mov     r8, [rsi+18h]; Source
0x18000abbb  sub     rdi, rbx
0x18000abbe  mov     rdx, rdi; DestinationSize
0x18000abc1  mov     rcx, rbx; Destination
0x18000abc4  call    cs:__imp_memcpy_s
0x18000abca  movzx   ecx, word ptr [r14]
0x18000abce  mov     al, 1
0x18000abd0  add     rcx, rbx
0x18000abd3  mov     [r12], rcx
0x18000abd7  add     rsp, 28h
0x18000abdb  pop     r15
0x18000abdd  pop     r14
0x18000abdf  pop     r12
0x18000abe1  pop     rdi
0x18000abe2  pop     rsi
0x18000abe3  pop     rbx
0x18000abe4  retn
```
