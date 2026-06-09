# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180011484`
- end: `0x18001155d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010454`

## callees

- `0x180011484`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800114e4`
- `msvcrt!memcpy_s` at `0x18001150f`
- `msvcrt!memcpy_s` at `0x18001153c`
- `msvcrt!memcpy_s` at `0x1800114e4`
- `msvcrt!memcpy_s` at `0x18001150f`
- `msvcrt!memcpy_s` at `0x18001153c`

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
0x180011484  push    rbx
0x180011486  push    rsi
0x180011487  push    rdi
0x180011488  push    r12
0x18001148a  push    r14
0x18001148c  push    r15
0x18001148e  sub     rsp, 28h
0x180011492  mov     rsi, rcx
0x180011495  mov     rdi, r8
0x180011498  mov     rcx, [rdx]; Destination
0x18001149b  mov     r12, rdx
0x18001149e  cmp     byte ptr [rsi+2], 1
0x1800114a2  jnz     short loc_1800114C6
0x1800114a4  lea     rbx, [rcx+2]
0x1800114a8  cmp     rbx, r8
0x1800114ab  ja      short loc_18001152B
0x1800114ad  movzx   eax, word ptr [rsi+4]
0x1800114b1  lea     r8, [rsp+58h+arg_0]
0x1800114b6  mov     r9d, 2
0x1800114bc  mov     [rsp+58h+arg_0], ax
0x1800114c1  mov     edx, r9d
0x1800114c4  jmp     short loc_1800114E4
0x1800114c6  cmp     byte ptr [rsi+2], 2
0x1800114ca  mov     rbx, rcx
0x1800114cd  jnz     short loc_1800114EA
0x1800114cf  lea     rbx, [rcx+4]
0x1800114d3  cmp     rbx, rdi
0x1800114d6  ja      short loc_18001152B
0x1800114d8  mov     edx, 4; DestinationSize
0x1800114dd  lea     r8, [rsi+4]; Source
0x1800114e1  mov     r9d, edx; SourceSize
0x1800114e4  call    cs:__imp_memcpy_s
0x1800114ea  cmp     word ptr [rsi], 0
0x1800114ee  jnz     short loc_18001151A
0x1800114f0  lea     r15, [rbx+2]
0x1800114f4  cmp     r15, rdi
0x1800114f7  ja      short loc_18001152B
0x1800114f9  lea     r14, [rsi+8]
0x1800114fd  mov     rdx, rdi
0x180011500  sub     rdx, rbx; DestinationSize
0x180011503  mov     r8, r14; Source
0x180011506  mov     r9d, 2; SourceSize
0x18001150c  mov     rcx, rbx; Destination
0x18001150f  call    cs:__imp_memcpy_s
0x180011515  mov     rbx, r15
0x180011518  jmp     short loc_18001151E
0x18001151a  lea     r14, [rsi+8]
0x18001151e  movzx   r9d, word ptr [r14]; SourceSize
0x180011522  lea     rax, [r9+rbx]
0x180011526  cmp     rax, rdi
0x180011529  jbe     short loc_18001152F
0x18001152b  xor     al, al
0x18001152d  jmp     short loc_18001154F
0x18001152f  mov     r8, [rsi+18h]; Source
0x180011533  sub     rdi, rbx
0x180011536  mov     rdx, rdi; DestinationSize
0x180011539  mov     rcx, rbx; Destination
0x18001153c  call    cs:__imp_memcpy_s
0x180011542  movzx   ecx, word ptr [r14]
0x180011546  mov     al, 1
0x180011548  add     rcx, rbx
0x18001154b  mov     [r12], rcx
0x18001154f  add     rsp, 28h
0x180011553  pop     r15
0x180011555  pop     r14
0x180011557  pop     r12
0x180011559  pop     rdi
0x18001155a  pop     rsi
0x18001155b  pop     rbx
0x18001155c  retn
```
