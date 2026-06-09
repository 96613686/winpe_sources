# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c95c`
- end: `0x18000ca35`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b060`

## callees

- `0x18000c95c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c9bc`
- `msvcrt!memcpy_s` at `0x18000c9e7`
- `msvcrt!memcpy_s` at `0x18000ca14`
- `msvcrt!memcpy_s` at `0x18000c9bc`
- `msvcrt!memcpy_s` at `0x18000c9e7`
- `msvcrt!memcpy_s` at `0x18000ca14`

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
0x18000c95c  push    rbx
0x18000c95e  push    rsi
0x18000c95f  push    rdi
0x18000c960  push    r12
0x18000c962  push    r14
0x18000c964  push    r15
0x18000c966  sub     rsp, 28h
0x18000c96a  mov     rsi, rcx
0x18000c96d  mov     rdi, r8
0x18000c970  mov     rcx, [rdx]; Destination
0x18000c973  mov     r12, rdx
0x18000c976  cmp     byte ptr [rsi+2], 1
0x18000c97a  jnz     short loc_18000C99E
0x18000c97c  lea     rbx, [rcx+2]
0x18000c980  cmp     rbx, r8
0x18000c983  ja      short loc_18000CA03
0x18000c985  movzx   eax, word ptr [rsi+4]
0x18000c989  lea     r8, [rsp+58h+arg_0]
0x18000c98e  mov     r9d, 2
0x18000c994  mov     [rsp+58h+arg_0], ax
0x18000c999  mov     edx, r9d
0x18000c99c  jmp     short loc_18000C9BC
0x18000c99e  cmp     byte ptr [rsi+2], 2
0x18000c9a2  mov     rbx, rcx
0x18000c9a5  jnz     short loc_18000C9C2
0x18000c9a7  lea     rbx, [rcx+4]
0x18000c9ab  cmp     rbx, rdi
0x18000c9ae  ja      short loc_18000CA03
0x18000c9b0  mov     edx, 4; DestinationSize
0x18000c9b5  lea     r8, [rsi+4]; Source
0x18000c9b9  mov     r9d, edx; SourceSize
0x18000c9bc  call    cs:__imp_memcpy_s
0x18000c9c2  cmp     word ptr [rsi], 0
0x18000c9c6  jnz     short loc_18000C9F2
0x18000c9c8  lea     r15, [rbx+2]
0x18000c9cc  cmp     r15, rdi
0x18000c9cf  ja      short loc_18000CA03
0x18000c9d1  lea     r14, [rsi+8]
0x18000c9d5  mov     rdx, rdi
0x18000c9d8  sub     rdx, rbx; DestinationSize
0x18000c9db  mov     r8, r14; Source
0x18000c9de  mov     r9d, 2; SourceSize
0x18000c9e4  mov     rcx, rbx; Destination
0x18000c9e7  call    cs:__imp_memcpy_s
0x18000c9ed  mov     rbx, r15
0x18000c9f0  jmp     short loc_18000C9F6
0x18000c9f2  lea     r14, [rsi+8]
0x18000c9f6  movzx   r9d, word ptr [r14]; SourceSize
0x18000c9fa  lea     rax, [r9+rbx]
0x18000c9fe  cmp     rax, rdi
0x18000ca01  jbe     short loc_18000CA07
0x18000ca03  xor     al, al
0x18000ca05  jmp     short loc_18000CA27
0x18000ca07  mov     r8, [rsi+18h]; Source
0x18000ca0b  sub     rdi, rbx
0x18000ca0e  mov     rdx, rdi; DestinationSize
0x18000ca11  mov     rcx, rbx; Destination
0x18000ca14  call    cs:__imp_memcpy_s
0x18000ca1a  movzx   ecx, word ptr [r14]
0x18000ca1e  mov     al, 1
0x18000ca20  add     rcx, rbx
0x18000ca23  mov     [r12], rcx
0x18000ca27  add     rsp, 28h
0x18000ca2b  pop     r15
0x18000ca2d  pop     r14
0x18000ca2f  pop     r12
0x18000ca31  pop     rdi
0x18000ca32  pop     rsi
0x18000ca33  pop     rbx
0x18000ca34  retn
```
