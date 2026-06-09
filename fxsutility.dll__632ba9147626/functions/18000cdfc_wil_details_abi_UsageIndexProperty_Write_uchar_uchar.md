# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000cdfc`
- end: `0x18000ced5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b178`

## callees

- `0x18000cdfc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ce5c`
- `msvcrt!memcpy_s` at `0x18000ce87`
- `msvcrt!memcpy_s` at `0x18000ceb4`
- `msvcrt!memcpy_s` at `0x18000ce5c`
- `msvcrt!memcpy_s` at `0x18000ce87`
- `msvcrt!memcpy_s` at `0x18000ceb4`

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
0x18000cdfc  push    rbx
0x18000cdfe  push    rsi
0x18000cdff  push    rdi
0x18000ce00  push    r12
0x18000ce02  push    r14
0x18000ce04  push    r15
0x18000ce06  sub     rsp, 28h
0x18000ce0a  mov     rsi, rcx
0x18000ce0d  mov     rdi, r8
0x18000ce10  mov     rcx, [rdx]; Destination
0x18000ce13  mov     r12, rdx
0x18000ce16  cmp     byte ptr [rsi+2], 1
0x18000ce1a  jnz     short loc_18000CE3E
0x18000ce1c  lea     rbx, [rcx+2]
0x18000ce20  cmp     rbx, r8
0x18000ce23  ja      short loc_18000CEA3
0x18000ce25  movzx   eax, word ptr [rsi+4]
0x18000ce29  lea     r8, [rsp+58h+arg_0]
0x18000ce2e  mov     r9d, 2
0x18000ce34  mov     [rsp+58h+arg_0], ax
0x18000ce39  mov     edx, r9d
0x18000ce3c  jmp     short loc_18000CE5C
0x18000ce3e  cmp     byte ptr [rsi+2], 2
0x18000ce42  mov     rbx, rcx
0x18000ce45  jnz     short loc_18000CE62
0x18000ce47  lea     rbx, [rcx+4]
0x18000ce4b  cmp     rbx, rdi
0x18000ce4e  ja      short loc_18000CEA3
0x18000ce50  mov     edx, 4; DestinationSize
0x18000ce55  lea     r8, [rsi+4]; Source
0x18000ce59  mov     r9d, edx; SourceSize
0x18000ce5c  call    cs:__imp_memcpy_s
0x18000ce62  cmp     word ptr [rsi], 0
0x18000ce66  jnz     short loc_18000CE92
0x18000ce68  lea     r15, [rbx+2]
0x18000ce6c  cmp     r15, rdi
0x18000ce6f  ja      short loc_18000CEA3
0x18000ce71  lea     r14, [rsi+8]
0x18000ce75  mov     rdx, rdi
0x18000ce78  sub     rdx, rbx; DestinationSize
0x18000ce7b  mov     r8, r14; Source
0x18000ce7e  mov     r9d, 2; SourceSize
0x18000ce84  mov     rcx, rbx; Destination
0x18000ce87  call    cs:__imp_memcpy_s
0x18000ce8d  mov     rbx, r15
0x18000ce90  jmp     short loc_18000CE96
0x18000ce92  lea     r14, [rsi+8]
0x18000ce96  movzx   r9d, word ptr [r14]; SourceSize
0x18000ce9a  lea     rax, [r9+rbx]
0x18000ce9e  cmp     rax, rdi
0x18000cea1  jbe     short loc_18000CEA7
0x18000cea3  xor     al, al
0x18000cea5  jmp     short loc_18000CEC7
0x18000cea7  mov     r8, [rsi+18h]; Source
0x18000ceab  sub     rdi, rbx
0x18000ceae  mov     rdx, rdi; DestinationSize
0x18000ceb1  mov     rcx, rbx; Destination
0x18000ceb4  call    cs:__imp_memcpy_s
0x18000ceba  movzx   ecx, word ptr [r14]
0x18000cebe  mov     al, 1
0x18000cec0  add     rcx, rbx
0x18000cec3  mov     [r12], rcx
0x18000cec7  add     rsp, 28h
0x18000cecb  pop     r15
0x18000cecd  pop     r14
0x18000cecf  pop     r12
0x18000ced1  pop     rdi
0x18000ced2  pop     rsi
0x18000ced3  pop     rbx
0x18000ced4  retn
```
