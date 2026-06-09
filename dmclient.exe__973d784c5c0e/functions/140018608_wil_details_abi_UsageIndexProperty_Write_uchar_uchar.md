# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140018608`
- end: `0x1400186f8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001750c`

## callees

- `0x140018608`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001866c`
- `msvcrt!memcpy_s` at `0x14001869d`
- `msvcrt!memcpy_s` at `0x1400186d0`
- `msvcrt!memcpy_s` at `0x14001866c`
- `msvcrt!memcpy_s` at `0x14001869d`
- `msvcrt!memcpy_s` at `0x1400186d0`

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
0x140018608  push    rbx
0x14001860a  push    rsi
0x14001860b  push    rdi
0x14001860c  push    r12
0x14001860e  push    r14
0x140018610  push    r15
0x140018612  sub     rsp, 28h
0x140018616  mov     rsi, rcx
0x140018619  mov     rdi, r8
0x14001861c  mov     rcx, [rdx]; Destination
0x14001861f  mov     r12, rdx
0x140018622  cmp     byte ptr [rsi+2], 1
0x140018626  jnz     short loc_14001864E
0x140018628  lea     rbx, [rcx+2]
0x14001862c  cmp     rbx, r8
0x14001862f  ja      loc_1400186BF
0x140018635  movzx   eax, word ptr [rsi+4]
0x140018639  lea     r8, [rsp+58h+arg_0]
0x14001863e  mov     r9d, 2
0x140018644  mov     [rsp+58h+arg_0], ax
0x140018649  mov     edx, r9d
0x14001864c  jmp     short loc_14001866C
0x14001864e  cmp     byte ptr [rsi+2], 2
0x140018652  mov     rbx, rcx
0x140018655  jnz     short loc_140018678
0x140018657  lea     rbx, [rcx+4]
0x14001865b  cmp     rbx, rdi
0x14001865e  ja      short loc_1400186BF
0x140018660  mov     edx, 4; DestinationSize
0x140018665  lea     r8, [rsi+4]; Source
0x140018669  mov     r9d, edx; SourceSize
0x14001866c  call    cs:__imp_memcpy_s
0x140018673  nop     dword ptr [rax+rax+00h]
0x140018678  cmp     word ptr [rsi], 0
0x14001867c  jnz     short loc_1400186AE
0x14001867e  lea     r15, [rbx+2]
0x140018682  cmp     r15, rdi
0x140018685  ja      short loc_1400186BF
0x140018687  lea     r14, [rsi+8]
0x14001868b  mov     rdx, rdi
0x14001868e  sub     rdx, rbx; DestinationSize
0x140018691  mov     r8, r14; Source
0x140018694  mov     r9d, 2; SourceSize
0x14001869a  mov     rcx, rbx; Destination
0x14001869d  call    cs:__imp_memcpy_s
0x1400186a4  nop     dword ptr [rax+rax+00h]
0x1400186a9  mov     rbx, r15
0x1400186ac  jmp     short loc_1400186B2
0x1400186ae  lea     r14, [rsi+8]
0x1400186b2  movzx   r9d, word ptr [r14]; SourceSize
0x1400186b6  lea     rax, [r9+rbx]
0x1400186ba  cmp     rax, rdi
0x1400186bd  jbe     short loc_1400186C3
0x1400186bf  xor     al, al
0x1400186c1  jmp     short loc_1400186E9
0x1400186c3  mov     r8, [rsi+18h]; Source
0x1400186c7  sub     rdi, rbx
0x1400186ca  mov     rdx, rdi; DestinationSize
0x1400186cd  mov     rcx, rbx; Destination
0x1400186d0  call    cs:__imp_memcpy_s
0x1400186d7  nop     dword ptr [rax+rax+00h]
0x1400186dc  movzx   ecx, word ptr [r14]
0x1400186e0  mov     al, 1
0x1400186e2  add     rcx, rbx
0x1400186e5  mov     [r12], rcx
0x1400186e9  add     rsp, 28h
0x1400186ed  pop     r15
0x1400186ef  pop     r14
0x1400186f1  pop     r12
0x1400186f3  pop     rdi
0x1400186f4  pop     rsi
0x1400186f5  pop     rbx
0x1400186f6  retn
```
