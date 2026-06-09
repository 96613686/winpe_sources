# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180011b1c`
- end: `0x180011bf5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fa28`

## callees

- `0x180011b1c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011b7c`
- `msvcrt!memcpy_s` at `0x180011ba7`
- `msvcrt!memcpy_s` at `0x180011bd4`
- `msvcrt!memcpy_s` at `0x180011b7c`
- `msvcrt!memcpy_s` at `0x180011ba7`
- `msvcrt!memcpy_s` at `0x180011bd4`

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
0x180011b1c  push    rbx
0x180011b1e  push    rsi
0x180011b1f  push    rdi
0x180011b20  push    r12
0x180011b22  push    r14
0x180011b24  push    r15
0x180011b26  sub     rsp, 28h
0x180011b2a  mov     rsi, rcx
0x180011b2d  mov     rdi, r8
0x180011b30  mov     rcx, [rdx]; Destination
0x180011b33  mov     r12, rdx
0x180011b36  cmp     byte ptr [rsi+2], 1
0x180011b3a  jnz     short loc_180011B5E
0x180011b3c  lea     rbx, [rcx+2]
0x180011b40  cmp     rbx, r8
0x180011b43  ja      short loc_180011BC3
0x180011b45  movzx   eax, word ptr [rsi+4]
0x180011b49  lea     r8, [rsp+58h+arg_0]
0x180011b4e  mov     r9d, 2
0x180011b54  mov     [rsp+58h+arg_0], ax
0x180011b59  mov     edx, r9d
0x180011b5c  jmp     short loc_180011B7C
0x180011b5e  cmp     byte ptr [rsi+2], 2
0x180011b62  mov     rbx, rcx
0x180011b65  jnz     short loc_180011B82
0x180011b67  lea     rbx, [rcx+4]
0x180011b6b  cmp     rbx, rdi
0x180011b6e  ja      short loc_180011BC3
0x180011b70  mov     edx, 4; DestinationSize
0x180011b75  lea     r8, [rsi+4]; Source
0x180011b79  mov     r9d, edx; SourceSize
0x180011b7c  call    cs:__imp_memcpy_s
0x180011b82  cmp     word ptr [rsi], 0
0x180011b86  jnz     short loc_180011BB2
0x180011b88  lea     r15, [rbx+2]
0x180011b8c  cmp     r15, rdi
0x180011b8f  ja      short loc_180011BC3
0x180011b91  lea     r14, [rsi+8]
0x180011b95  mov     rdx, rdi
0x180011b98  sub     rdx, rbx; DestinationSize
0x180011b9b  mov     r8, r14; Source
0x180011b9e  mov     r9d, 2; SourceSize
0x180011ba4  mov     rcx, rbx; Destination
0x180011ba7  call    cs:__imp_memcpy_s
0x180011bad  mov     rbx, r15
0x180011bb0  jmp     short loc_180011BB6
0x180011bb2  lea     r14, [rsi+8]
0x180011bb6  movzx   r9d, word ptr [r14]; SourceSize
0x180011bba  lea     rax, [r9+rbx]
0x180011bbe  cmp     rax, rdi
0x180011bc1  jbe     short loc_180011BC7
0x180011bc3  xor     al, al
0x180011bc5  jmp     short loc_180011BE7
0x180011bc7  mov     r8, [rsi+18h]; Source
0x180011bcb  sub     rdi, rbx
0x180011bce  mov     rdx, rdi; DestinationSize
0x180011bd1  mov     rcx, rbx; Destination
0x180011bd4  call    cs:__imp_memcpy_s
0x180011bda  movzx   ecx, word ptr [r14]
0x180011bde  mov     al, 1
0x180011be0  add     rcx, rbx
0x180011be3  mov     [r12], rcx
0x180011be7  add     rsp, 28h
0x180011beb  pop     r15
0x180011bed  pop     r14
0x180011bef  pop     r12
0x180011bf1  pop     rdi
0x180011bf2  pop     rsi
0x180011bf3  pop     rbx
0x180011bf4  retn
```
