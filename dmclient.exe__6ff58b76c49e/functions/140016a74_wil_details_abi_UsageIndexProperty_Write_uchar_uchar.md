# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140016a74`
- end: `0x140016b4d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400151e4`

## callees

- `0x140016a74`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140016ad4`
- `msvcrt!memcpy_s` at `0x140016aff`
- `msvcrt!memcpy_s` at `0x140016b2c`
- `msvcrt!memcpy_s` at `0x140016ad4`
- `msvcrt!memcpy_s` at `0x140016aff`
- `msvcrt!memcpy_s` at `0x140016b2c`

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
0x140016a74  push    rbx
0x140016a76  push    rsi
0x140016a77  push    rdi
0x140016a78  push    r12
0x140016a7a  push    r14
0x140016a7c  push    r15
0x140016a7e  sub     rsp, 28h
0x140016a82  mov     rsi, rcx
0x140016a85  mov     rdi, r8
0x140016a88  mov     rcx, [rdx]; Destination
0x140016a8b  mov     r12, rdx
0x140016a8e  cmp     byte ptr [rsi+2], 1
0x140016a92  jnz     short loc_140016AB6
0x140016a94  lea     rbx, [rcx+2]
0x140016a98  cmp     rbx, r8
0x140016a9b  ja      short loc_140016B1B
0x140016a9d  movzx   eax, word ptr [rsi+4]
0x140016aa1  lea     r8, [rsp+58h+arg_0]
0x140016aa6  mov     r9d, 2
0x140016aac  mov     [rsp+58h+arg_0], ax
0x140016ab1  mov     edx, r9d
0x140016ab4  jmp     short loc_140016AD4
0x140016ab6  cmp     byte ptr [rsi+2], 2
0x140016aba  mov     rbx, rcx
0x140016abd  jnz     short loc_140016ADA
0x140016abf  lea     rbx, [rcx+4]
0x140016ac3  cmp     rbx, rdi
0x140016ac6  ja      short loc_140016B1B
0x140016ac8  mov     edx, 4; DestinationSize
0x140016acd  lea     r8, [rsi+4]; Source
0x140016ad1  mov     r9d, edx; SourceSize
0x140016ad4  call    cs:__imp_memcpy_s
0x140016ada  cmp     word ptr [rsi], 0
0x140016ade  jnz     short loc_140016B0A
0x140016ae0  lea     r15, [rbx+2]
0x140016ae4  cmp     r15, rdi
0x140016ae7  ja      short loc_140016B1B
0x140016ae9  lea     r14, [rsi+8]
0x140016aed  mov     rdx, rdi
0x140016af0  sub     rdx, rbx; DestinationSize
0x140016af3  mov     r8, r14; Source
0x140016af6  mov     r9d, 2; SourceSize
0x140016afc  mov     rcx, rbx; Destination
0x140016aff  call    cs:__imp_memcpy_s
0x140016b05  mov     rbx, r15
0x140016b08  jmp     short loc_140016B0E
0x140016b0a  lea     r14, [rsi+8]
0x140016b0e  movzx   r9d, word ptr [r14]; SourceSize
0x140016b12  lea     rax, [r9+rbx]
0x140016b16  cmp     rax, rdi
0x140016b19  jbe     short loc_140016B1F
0x140016b1b  xor     al, al
0x140016b1d  jmp     short loc_140016B3F
0x140016b1f  mov     r8, [rsi+18h]; Source
0x140016b23  sub     rdi, rbx
0x140016b26  mov     rdx, rdi; DestinationSize
0x140016b29  mov     rcx, rbx; Destination
0x140016b2c  call    cs:__imp_memcpy_s
0x140016b32  movzx   ecx, word ptr [r14]
0x140016b36  mov     al, 1
0x140016b38  add     rcx, rbx
0x140016b3b  mov     [r12], rcx
0x140016b3f  add     rsp, 28h
0x140016b43  pop     r15
0x140016b45  pop     r14
0x140016b47  pop     r12
0x140016b49  pop     rdi
0x140016b4a  pop     rsi
0x140016b4b  pop     rbx
0x140016b4c  retn
```
