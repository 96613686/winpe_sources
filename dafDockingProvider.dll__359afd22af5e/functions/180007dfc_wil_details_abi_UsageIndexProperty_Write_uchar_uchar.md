# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007dfc`
- end: `0x180007ed5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006048`

## callees

- `0x180007dfc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007e5c`
- `msvcrt!memcpy_s` at `0x180007e87`
- `msvcrt!memcpy_s` at `0x180007eb4`
- `msvcrt!memcpy_s` at `0x180007e5c`
- `msvcrt!memcpy_s` at `0x180007e87`
- `msvcrt!memcpy_s` at `0x180007eb4`

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
0x180007dfc  push    rbx
0x180007dfe  push    rsi
0x180007dff  push    rdi
0x180007e00  push    r12
0x180007e02  push    r14
0x180007e04  push    r15
0x180007e06  sub     rsp, 28h
0x180007e0a  mov     rsi, rcx
0x180007e0d  mov     rdi, r8
0x180007e10  mov     rcx, [rdx]; Destination
0x180007e13  mov     r12, rdx
0x180007e16  cmp     byte ptr [rsi+2], 1
0x180007e1a  jnz     short loc_180007E3E
0x180007e1c  lea     rbx, [rcx+2]
0x180007e20  cmp     rbx, r8
0x180007e23  ja      short loc_180007EA3
0x180007e25  movzx   eax, word ptr [rsi+4]
0x180007e29  lea     r8, [rsp+58h+arg_0]
0x180007e2e  mov     r9d, 2
0x180007e34  mov     [rsp+58h+arg_0], ax
0x180007e39  mov     edx, r9d
0x180007e3c  jmp     short loc_180007E5C
0x180007e3e  cmp     byte ptr [rsi+2], 2
0x180007e42  mov     rbx, rcx
0x180007e45  jnz     short loc_180007E62
0x180007e47  lea     rbx, [rcx+4]
0x180007e4b  cmp     rbx, rdi
0x180007e4e  ja      short loc_180007EA3
0x180007e50  mov     edx, 4; DestinationSize
0x180007e55  lea     r8, [rsi+4]; Source
0x180007e59  mov     r9d, edx; SourceSize
0x180007e5c  call    cs:__imp_memcpy_s
0x180007e62  cmp     word ptr [rsi], 0
0x180007e66  jnz     short loc_180007E92
0x180007e68  lea     r15, [rbx+2]
0x180007e6c  cmp     r15, rdi
0x180007e6f  ja      short loc_180007EA3
0x180007e71  lea     r14, [rsi+8]
0x180007e75  mov     rdx, rdi
0x180007e78  sub     rdx, rbx; DestinationSize
0x180007e7b  mov     r8, r14; Source
0x180007e7e  mov     r9d, 2; SourceSize
0x180007e84  mov     rcx, rbx; Destination
0x180007e87  call    cs:__imp_memcpy_s
0x180007e8d  mov     rbx, r15
0x180007e90  jmp     short loc_180007E96
0x180007e92  lea     r14, [rsi+8]
0x180007e96  movzx   r9d, word ptr [r14]; SourceSize
0x180007e9a  lea     rax, [r9+rbx]
0x180007e9e  cmp     rax, rdi
0x180007ea1  jbe     short loc_180007EA7
0x180007ea3  xor     al, al
0x180007ea5  jmp     short loc_180007EC7
0x180007ea7  mov     r8, [rsi+18h]; Source
0x180007eab  sub     rdi, rbx
0x180007eae  mov     rdx, rdi; DestinationSize
0x180007eb1  mov     rcx, rbx; Destination
0x180007eb4  call    cs:__imp_memcpy_s
0x180007eba  movzx   ecx, word ptr [r14]
0x180007ebe  mov     al, 1
0x180007ec0  add     rcx, rbx
0x180007ec3  mov     [r12], rcx
0x180007ec7  add     rsp, 28h
0x180007ecb  pop     r15
0x180007ecd  pop     r14
0x180007ecf  pop     r12
0x180007ed1  pop     rdi
0x180007ed2  pop     rsi
0x180007ed3  pop     rbx
0x180007ed4  retn
```
