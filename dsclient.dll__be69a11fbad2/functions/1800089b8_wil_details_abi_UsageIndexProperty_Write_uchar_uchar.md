# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800089b8`
- end: `0x180008a91`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007334`

## callees

- `0x1800089b8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008a18`
- `msvcrt!memcpy_s` at `0x180008a43`
- `msvcrt!memcpy_s` at `0x180008a70`
- `msvcrt!memcpy_s` at `0x180008a18`
- `msvcrt!memcpy_s` at `0x180008a43`
- `msvcrt!memcpy_s` at `0x180008a70`

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
0x1800089b8  push    rbx
0x1800089ba  push    rsi
0x1800089bb  push    rdi
0x1800089bc  push    r12
0x1800089be  push    r14
0x1800089c0  push    r15
0x1800089c2  sub     rsp, 28h
0x1800089c6  mov     rsi, rcx
0x1800089c9  mov     rdi, r8
0x1800089cc  mov     rcx, [rdx]; Destination
0x1800089cf  mov     r12, rdx
0x1800089d2  cmp     byte ptr [rsi+2], 1
0x1800089d6  jnz     short loc_1800089FA
0x1800089d8  lea     rbx, [rcx+2]
0x1800089dc  cmp     rbx, r8
0x1800089df  ja      short loc_180008A5F
0x1800089e1  movzx   eax, word ptr [rsi+4]
0x1800089e5  lea     r8, [rsp+58h+arg_0]
0x1800089ea  mov     r9d, 2
0x1800089f0  mov     [rsp+58h+arg_0], ax
0x1800089f5  mov     edx, r9d
0x1800089f8  jmp     short loc_180008A18
0x1800089fa  cmp     byte ptr [rsi+2], 2
0x1800089fe  mov     rbx, rcx
0x180008a01  jnz     short loc_180008A1E
0x180008a03  lea     rbx, [rcx+4]
0x180008a07  cmp     rbx, rdi
0x180008a0a  ja      short loc_180008A5F
0x180008a0c  mov     edx, 4; DestinationSize
0x180008a11  lea     r8, [rsi+4]; Source
0x180008a15  mov     r9d, edx; SourceSize
0x180008a18  call    cs:__imp_memcpy_s
0x180008a1e  cmp     word ptr [rsi], 0
0x180008a22  jnz     short loc_180008A4E
0x180008a24  lea     r15, [rbx+2]
0x180008a28  cmp     r15, rdi
0x180008a2b  ja      short loc_180008A5F
0x180008a2d  lea     r14, [rsi+8]
0x180008a31  mov     rdx, rdi
0x180008a34  sub     rdx, rbx; DestinationSize
0x180008a37  mov     r8, r14; Source
0x180008a3a  mov     r9d, 2; SourceSize
0x180008a40  mov     rcx, rbx; Destination
0x180008a43  call    cs:__imp_memcpy_s
0x180008a49  mov     rbx, r15
0x180008a4c  jmp     short loc_180008A52
0x180008a4e  lea     r14, [rsi+8]
0x180008a52  movzx   r9d, word ptr [r14]; SourceSize
0x180008a56  lea     rax, [r9+rbx]
0x180008a5a  cmp     rax, rdi
0x180008a5d  jbe     short loc_180008A63
0x180008a5f  xor     al, al
0x180008a61  jmp     short loc_180008A83
0x180008a63  mov     r8, [rsi+18h]; Source
0x180008a67  sub     rdi, rbx
0x180008a6a  mov     rdx, rdi; DestinationSize
0x180008a6d  mov     rcx, rbx; Destination
0x180008a70  call    cs:__imp_memcpy_s
0x180008a76  movzx   ecx, word ptr [r14]
0x180008a7a  mov     al, 1
0x180008a7c  add     rcx, rbx
0x180008a7f  mov     [r12], rcx
0x180008a83  add     rsp, 28h
0x180008a87  pop     r15
0x180008a89  pop     r14
0x180008a8b  pop     r12
0x180008a8d  pop     rdi
0x180008a8e  pop     rsi
0x180008a8f  pop     rbx
0x180008a90  retn
```
