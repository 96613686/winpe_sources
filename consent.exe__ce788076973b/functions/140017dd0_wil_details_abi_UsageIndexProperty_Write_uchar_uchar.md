# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140017dd0`
- end: `0x140017ea9`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008d1c`

## callees

- `0x140017dd0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140017e30`
- `msvcrt!memcpy_s` at `0x140017e5b`
- `msvcrt!memcpy_s` at `0x140017e88`
- `msvcrt!memcpy_s` at `0x140017e30`
- `msvcrt!memcpy_s` at `0x140017e5b`
- `msvcrt!memcpy_s` at `0x140017e88`

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
0x140017dd0  push    rbx
0x140017dd2  push    rsi
0x140017dd3  push    rdi
0x140017dd4  push    r12
0x140017dd6  push    r14
0x140017dd8  push    r15
0x140017dda  sub     rsp, 28h
0x140017dde  mov     rsi, rcx
0x140017de1  mov     rdi, r8
0x140017de4  mov     rcx, [rdx]; Destination
0x140017de7  mov     r12, rdx
0x140017dea  cmp     byte ptr [rsi+2], 1
0x140017dee  jnz     short loc_140017E12
0x140017df0  lea     rbx, [rcx+2]
0x140017df4  cmp     rbx, r8
0x140017df7  ja      short loc_140017E77
0x140017df9  movzx   eax, word ptr [rsi+4]
0x140017dfd  lea     r8, [rsp+58h+arg_0]
0x140017e02  mov     r9d, 2
0x140017e08  mov     [rsp+58h+arg_0], ax
0x140017e0d  mov     edx, r9d
0x140017e10  jmp     short loc_140017E30
0x140017e12  cmp     byte ptr [rsi+2], 2
0x140017e16  mov     rbx, rcx
0x140017e19  jnz     short loc_140017E36
0x140017e1b  lea     rbx, [rcx+4]
0x140017e1f  cmp     rbx, rdi
0x140017e22  ja      short loc_140017E77
0x140017e24  mov     edx, 4; DestinationSize
0x140017e29  lea     r8, [rsi+4]; Source
0x140017e2d  mov     r9d, edx; SourceSize
0x140017e30  call    cs:__imp_memcpy_s
0x140017e36  cmp     word ptr [rsi], 0
0x140017e3a  jnz     short loc_140017E66
0x140017e3c  lea     r15, [rbx+2]
0x140017e40  cmp     r15, rdi
0x140017e43  ja      short loc_140017E77
0x140017e45  lea     r14, [rsi+8]
0x140017e49  mov     rdx, rdi
0x140017e4c  sub     rdx, rbx; DestinationSize
0x140017e4f  mov     r8, r14; Source
0x140017e52  mov     r9d, 2; SourceSize
0x140017e58  mov     rcx, rbx; Destination
0x140017e5b  call    cs:__imp_memcpy_s
0x140017e61  mov     rbx, r15
0x140017e64  jmp     short loc_140017E6A
0x140017e66  lea     r14, [rsi+8]
0x140017e6a  movzx   r9d, word ptr [r14]; SourceSize
0x140017e6e  lea     rax, [r9+rbx]
0x140017e72  cmp     rax, rdi
0x140017e75  jbe     short loc_140017E7B
0x140017e77  xor     al, al
0x140017e79  jmp     short loc_140017E9B
0x140017e7b  mov     r8, [rsi+18h]; Source
0x140017e7f  sub     rdi, rbx
0x140017e82  mov     rdx, rdi; DestinationSize
0x140017e85  mov     rcx, rbx; Destination
0x140017e88  call    cs:__imp_memcpy_s
0x140017e8e  movzx   ecx, word ptr [r14]
0x140017e92  mov     al, 1
0x140017e94  add     rcx, rbx
0x140017e97  mov     [r12], rcx
0x140017e9b  add     rsp, 28h
0x140017e9f  pop     r15
0x140017ea1  pop     r14
0x140017ea3  pop     r12
0x140017ea5  pop     rdi
0x140017ea6  pop     rsi
0x140017ea7  pop     rbx
0x140017ea8  retn
```
