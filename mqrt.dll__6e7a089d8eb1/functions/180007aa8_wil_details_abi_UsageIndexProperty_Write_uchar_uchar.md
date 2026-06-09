# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007aa8`
- end: `0x180007b81`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000635c`

## callees

- `0x180007aa8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007b08`
- `msvcrt!memcpy_s` at `0x180007b33`
- `msvcrt!memcpy_s` at `0x180007b60`
- `msvcrt!memcpy_s` at `0x180007b08`
- `msvcrt!memcpy_s` at `0x180007b33`
- `msvcrt!memcpy_s` at `0x180007b60`

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
0x180007aa8  push    rbx
0x180007aaa  push    rsi
0x180007aab  push    rdi
0x180007aac  push    r12
0x180007aae  push    r14
0x180007ab0  push    r15
0x180007ab2  sub     rsp, 28h
0x180007ab6  mov     rsi, rcx
0x180007ab9  mov     rdi, r8
0x180007abc  mov     rcx, [rdx]; Destination
0x180007abf  mov     r12, rdx
0x180007ac2  cmp     byte ptr [rsi+2], 1
0x180007ac6  jnz     short loc_180007AEA
0x180007ac8  lea     rbx, [rcx+2]
0x180007acc  cmp     rbx, r8
0x180007acf  ja      short loc_180007B4F
0x180007ad1  movzx   eax, word ptr [rsi+4]
0x180007ad5  lea     r8, [rsp+58h+arg_0]
0x180007ada  mov     r9d, 2
0x180007ae0  mov     [rsp+58h+arg_0], ax
0x180007ae5  mov     edx, r9d
0x180007ae8  jmp     short loc_180007B08
0x180007aea  cmp     byte ptr [rsi+2], 2
0x180007aee  mov     rbx, rcx
0x180007af1  jnz     short loc_180007B0E
0x180007af3  lea     rbx, [rcx+4]
0x180007af7  cmp     rbx, rdi
0x180007afa  ja      short loc_180007B4F
0x180007afc  mov     edx, 4; DestinationSize
0x180007b01  lea     r8, [rsi+4]; Source
0x180007b05  mov     r9d, edx; SourceSize
0x180007b08  call    cs:__imp_memcpy_s
0x180007b0e  cmp     word ptr [rsi], 0
0x180007b12  jnz     short loc_180007B3E
0x180007b14  lea     r15, [rbx+2]
0x180007b18  cmp     r15, rdi
0x180007b1b  ja      short loc_180007B4F
0x180007b1d  lea     r14, [rsi+8]
0x180007b21  mov     rdx, rdi
0x180007b24  sub     rdx, rbx; DestinationSize
0x180007b27  mov     r8, r14; Source
0x180007b2a  mov     r9d, 2; SourceSize
0x180007b30  mov     rcx, rbx; Destination
0x180007b33  call    cs:__imp_memcpy_s
0x180007b39  mov     rbx, r15
0x180007b3c  jmp     short loc_180007B42
0x180007b3e  lea     r14, [rsi+8]
0x180007b42  movzx   r9d, word ptr [r14]; SourceSize
0x180007b46  lea     rax, [r9+rbx]
0x180007b4a  cmp     rax, rdi
0x180007b4d  jbe     short loc_180007B53
0x180007b4f  xor     al, al
0x180007b51  jmp     short loc_180007B73
0x180007b53  mov     r8, [rsi+18h]; Source
0x180007b57  sub     rdi, rbx
0x180007b5a  mov     rdx, rdi; DestinationSize
0x180007b5d  mov     rcx, rbx; Destination
0x180007b60  call    cs:__imp_memcpy_s
0x180007b66  movzx   ecx, word ptr [r14]
0x180007b6a  mov     al, 1
0x180007b6c  add     rcx, rbx
0x180007b6f  mov     [r12], rcx
0x180007b73  add     rsp, 28h
0x180007b77  pop     r15
0x180007b79  pop     r14
0x180007b7b  pop     r12
0x180007b7d  pop     rdi
0x180007b7e  pop     rsi
0x180007b7f  pop     rbx
0x180007b80  retn
```
