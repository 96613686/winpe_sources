# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800122b4`
- end: `0x18001238d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011788`

## callees

- `0x1800122b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012314`
- `msvcrt!memcpy_s` at `0x18001233f`
- `msvcrt!memcpy_s` at `0x18001236c`
- `msvcrt!memcpy_s` at `0x180012314`
- `msvcrt!memcpy_s` at `0x18001233f`
- `msvcrt!memcpy_s` at `0x18001236c`

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
0x1800122b4  push    rbx
0x1800122b6  push    rsi
0x1800122b7  push    rdi
0x1800122b8  push    r12
0x1800122ba  push    r14
0x1800122bc  push    r15
0x1800122be  sub     rsp, 28h
0x1800122c2  mov     rsi, rcx
0x1800122c5  mov     rdi, r8
0x1800122c8  mov     rcx, [rdx]; Destination
0x1800122cb  mov     r12, rdx
0x1800122ce  cmp     byte ptr [rsi+2], 1
0x1800122d2  jnz     short loc_1800122F6
0x1800122d4  lea     rbx, [rcx+2]
0x1800122d8  cmp     rbx, r8
0x1800122db  ja      short loc_18001235B
0x1800122dd  movzx   eax, word ptr [rsi+4]
0x1800122e1  lea     r8, [rsp+58h+arg_0]
0x1800122e6  mov     r9d, 2
0x1800122ec  mov     [rsp+58h+arg_0], ax
0x1800122f1  mov     edx, r9d
0x1800122f4  jmp     short loc_180012314
0x1800122f6  cmp     byte ptr [rsi+2], 2
0x1800122fa  mov     rbx, rcx
0x1800122fd  jnz     short loc_18001231A
0x1800122ff  lea     rbx, [rcx+4]
0x180012303  cmp     rbx, rdi
0x180012306  ja      short loc_18001235B
0x180012308  mov     edx, 4; DestinationSize
0x18001230d  lea     r8, [rsi+4]; Source
0x180012311  mov     r9d, edx; SourceSize
0x180012314  call    cs:__imp_memcpy_s
0x18001231a  cmp     word ptr [rsi], 0
0x18001231e  jnz     short loc_18001234A
0x180012320  lea     r15, [rbx+2]
0x180012324  cmp     r15, rdi
0x180012327  ja      short loc_18001235B
0x180012329  lea     r14, [rsi+8]
0x18001232d  mov     rdx, rdi
0x180012330  sub     rdx, rbx; DestinationSize
0x180012333  mov     r8, r14; Source
0x180012336  mov     r9d, 2; SourceSize
0x18001233c  mov     rcx, rbx; Destination
0x18001233f  call    cs:__imp_memcpy_s
0x180012345  mov     rbx, r15
0x180012348  jmp     short loc_18001234E
0x18001234a  lea     r14, [rsi+8]
0x18001234e  movzx   r9d, word ptr [r14]; SourceSize
0x180012352  lea     rax, [r9+rbx]
0x180012356  cmp     rax, rdi
0x180012359  jbe     short loc_18001235F
0x18001235b  xor     al, al
0x18001235d  jmp     short loc_18001237F
0x18001235f  mov     r8, [rsi+18h]; Source
0x180012363  sub     rdi, rbx
0x180012366  mov     rdx, rdi; DestinationSize
0x180012369  mov     rcx, rbx; Destination
0x18001236c  call    cs:__imp_memcpy_s
0x180012372  movzx   ecx, word ptr [r14]
0x180012376  mov     al, 1
0x180012378  add     rcx, rbx
0x18001237b  mov     [r12], rcx
0x18001237f  add     rsp, 28h
0x180012383  pop     r15
0x180012385  pop     r14
0x180012387  pop     r12
0x180012389  pop     rdi
0x18001238a  pop     rsi
0x18001238b  pop     rbx
0x18001238c  retn
```
