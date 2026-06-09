# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007d08`
- end: `0x180007df8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800061ec`

## callees

- `0x180007d08`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007d6c`
- `msvcrt!memcpy_s` at `0x180007d9d`
- `msvcrt!memcpy_s` at `0x180007dd0`
- `msvcrt!memcpy_s` at `0x180007d6c`
- `msvcrt!memcpy_s` at `0x180007d9d`
- `msvcrt!memcpy_s` at `0x180007dd0`

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
0x180007d08  push    rbx
0x180007d0a  push    rsi
0x180007d0b  push    rdi
0x180007d0c  push    r12
0x180007d0e  push    r14
0x180007d10  push    r15
0x180007d12  sub     rsp, 28h
0x180007d16  mov     rsi, rcx
0x180007d19  mov     rdi, r8
0x180007d1c  mov     rcx, [rdx]; Destination
0x180007d1f  mov     r12, rdx
0x180007d22  cmp     byte ptr [rsi+2], 1
0x180007d26  jnz     short loc_180007D4E
0x180007d28  lea     rbx, [rcx+2]
0x180007d2c  cmp     rbx, r8
0x180007d2f  ja      loc_180007DBF
0x180007d35  movzx   eax, word ptr [rsi+4]
0x180007d39  lea     r8, [rsp+58h+arg_0]
0x180007d3e  mov     r9d, 2
0x180007d44  mov     [rsp+58h+arg_0], ax
0x180007d49  mov     edx, r9d
0x180007d4c  jmp     short loc_180007D6C
0x180007d4e  cmp     byte ptr [rsi+2], 2
0x180007d52  mov     rbx, rcx
0x180007d55  jnz     short loc_180007D78
0x180007d57  lea     rbx, [rcx+4]
0x180007d5b  cmp     rbx, rdi
0x180007d5e  ja      short loc_180007DBF
0x180007d60  mov     edx, 4; DestinationSize
0x180007d65  lea     r8, [rsi+4]; Source
0x180007d69  mov     r9d, edx; SourceSize
0x180007d6c  call    cs:__imp_memcpy_s
0x180007d73  nop     dword ptr [rax+rax+00h]
0x180007d78  cmp     word ptr [rsi], 0
0x180007d7c  jnz     short loc_180007DAE
0x180007d7e  lea     r15, [rbx+2]
0x180007d82  cmp     r15, rdi
0x180007d85  ja      short loc_180007DBF
0x180007d87  lea     r14, [rsi+8]
0x180007d8b  mov     rdx, rdi
0x180007d8e  sub     rdx, rbx; DestinationSize
0x180007d91  mov     r8, r14; Source
0x180007d94  mov     r9d, 2; SourceSize
0x180007d9a  mov     rcx, rbx; Destination
0x180007d9d  call    cs:__imp_memcpy_s
0x180007da4  nop     dword ptr [rax+rax+00h]
0x180007da9  mov     rbx, r15
0x180007dac  jmp     short loc_180007DB2
0x180007dae  lea     r14, [rsi+8]
0x180007db2  movzx   r9d, word ptr [r14]; SourceSize
0x180007db6  lea     rax, [r9+rbx]
0x180007dba  cmp     rax, rdi
0x180007dbd  jbe     short loc_180007DC3
0x180007dbf  xor     al, al
0x180007dc1  jmp     short loc_180007DE9
0x180007dc3  mov     r8, [rsi+18h]; Source
0x180007dc7  sub     rdi, rbx
0x180007dca  mov     rdx, rdi; DestinationSize
0x180007dcd  mov     rcx, rbx; Destination
0x180007dd0  call    cs:__imp_memcpy_s
0x180007dd7  nop     dword ptr [rax+rax+00h]
0x180007ddc  movzx   ecx, word ptr [r14]
0x180007de0  mov     al, 1
0x180007de2  add     rcx, rbx
0x180007de5  mov     [r12], rcx
0x180007de9  add     rsp, 28h
0x180007ded  pop     r15
0x180007def  pop     r14
0x180007df1  pop     r12
0x180007df3  pop     rdi
0x180007df4  pop     rsi
0x180007df5  pop     rbx
0x180007df6  retn
```
