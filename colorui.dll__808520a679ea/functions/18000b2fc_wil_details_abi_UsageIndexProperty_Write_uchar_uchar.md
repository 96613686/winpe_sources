# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000b2fc`
- end: `0x18000b3d5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800081d0`

## callees

- `0x18000b2fc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b35c`
- `msvcrt!memcpy_s` at `0x18000b387`
- `msvcrt!memcpy_s` at `0x18000b3b4`
- `msvcrt!memcpy_s` at `0x18000b35c`
- `msvcrt!memcpy_s` at `0x18000b387`
- `msvcrt!memcpy_s` at `0x18000b3b4`

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
0x18000b2fc  push    rbx
0x18000b2fe  push    rsi
0x18000b2ff  push    rdi
0x18000b300  push    r12
0x18000b302  push    r14
0x18000b304  push    r15
0x18000b306  sub     rsp, 28h
0x18000b30a  mov     rsi, rcx
0x18000b30d  mov     rdi, r8
0x18000b310  mov     rcx, [rdx]; Destination
0x18000b313  mov     r12, rdx
0x18000b316  cmp     byte ptr [rsi+2], 1
0x18000b31a  jnz     short loc_18000B33E
0x18000b31c  lea     rbx, [rcx+2]
0x18000b320  cmp     rbx, r8
0x18000b323  ja      short loc_18000B3A3
0x18000b325  movzx   eax, word ptr [rsi+4]
0x18000b329  lea     r8, [rsp+58h+arg_0]
0x18000b32e  mov     r9d, 2
0x18000b334  mov     [rsp+58h+arg_0], ax
0x18000b339  mov     edx, r9d
0x18000b33c  jmp     short loc_18000B35C
0x18000b33e  cmp     byte ptr [rsi+2], 2
0x18000b342  mov     rbx, rcx
0x18000b345  jnz     short loc_18000B362
0x18000b347  lea     rbx, [rcx+4]
0x18000b34b  cmp     rbx, rdi
0x18000b34e  ja      short loc_18000B3A3
0x18000b350  mov     edx, 4; DestinationSize
0x18000b355  lea     r8, [rsi+4]; Source
0x18000b359  mov     r9d, edx; SourceSize
0x18000b35c  call    cs:__imp_memcpy_s
0x18000b362  cmp     word ptr [rsi], 0
0x18000b366  jnz     short loc_18000B392
0x18000b368  lea     r15, [rbx+2]
0x18000b36c  cmp     r15, rdi
0x18000b36f  ja      short loc_18000B3A3
0x18000b371  lea     r14, [rsi+8]
0x18000b375  mov     rdx, rdi
0x18000b378  sub     rdx, rbx; DestinationSize
0x18000b37b  mov     r8, r14; Source
0x18000b37e  mov     r9d, 2; SourceSize
0x18000b384  mov     rcx, rbx; Destination
0x18000b387  call    cs:__imp_memcpy_s
0x18000b38d  mov     rbx, r15
0x18000b390  jmp     short loc_18000B396
0x18000b392  lea     r14, [rsi+8]
0x18000b396  movzx   r9d, word ptr [r14]; SourceSize
0x18000b39a  lea     rax, [r9+rbx]
0x18000b39e  cmp     rax, rdi
0x18000b3a1  jbe     short loc_18000B3A7
0x18000b3a3  xor     al, al
0x18000b3a5  jmp     short loc_18000B3C7
0x18000b3a7  mov     r8, [rsi+18h]; Source
0x18000b3ab  sub     rdi, rbx
0x18000b3ae  mov     rdx, rdi; DestinationSize
0x18000b3b1  mov     rcx, rbx; Destination
0x18000b3b4  call    cs:__imp_memcpy_s
0x18000b3ba  movzx   ecx, word ptr [r14]
0x18000b3be  mov     al, 1
0x18000b3c0  add     rcx, rbx
0x18000b3c3  mov     [r12], rcx
0x18000b3c7  add     rsp, 28h
0x18000b3cb  pop     r15
0x18000b3cd  pop     r14
0x18000b3cf  pop     r12
0x18000b3d1  pop     rdi
0x18000b3d2  pop     rsi
0x18000b3d3  pop     rbx
0x18000b3d4  retn
```
