# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140016ee0`
- end: `0x140016fdc`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140016538`
- `0x14001750c`
- `0x1400178ac`

## callees

- `0x140016ee0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140016f2f`
- `msvcrt!memcpy_s` at `0x140016f6a`
- `msvcrt!memcpy_s` at `0x140016f9b`
- `msvcrt!memcpy_s` at `0x140016f2f`
- `msvcrt!memcpy_s` at `0x140016f6a`
- `msvcrt!memcpy_s` at `0x140016f9b`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x140016ee0  mov     rax, rsp
0x140016ee3  mov     [rax+10h], rbx
0x140016ee7  mov     [rax+18h], rbp
0x140016eeb  push    rsi
0x140016eec  push    rdi
0x140016eed  push    r12
0x140016eef  push    r14
0x140016ef1  push    r15
0x140016ef3  sub     rsp, 20h
0x140016ef7  xor     r15d, r15d
0x140016efa  mov     rsi, r8
0x140016efd  cmp     byte ptr [rcx+2], 1
0x140016f01  mov     r12, rdx
0x140016f04  mov     r8, [rdx]; Source
0x140016f07  mov     rdi, rcx
0x140016f0a  jnz     short loc_140016F45
0x140016f0c  lea     rbx, [r8+2]
0x140016f10  cmp     rbx, rsi
0x140016f13  ja      loc_140016FB6
0x140016f19  lea     ebp, [r15+2]
0x140016f1d  mov     [rcx+10h], r8
0x140016f21  mov     r9d, ebp; SourceSize
0x140016f24  mov     [rax+8], r15w
0x140016f29  mov     edx, ebp; DestinationSize
0x140016f2b  lea     rcx, [rax+8]; Destination
0x140016f2f  call    cs:__imp_memcpy_s
0x140016f36  nop     dword ptr [rax+rax+00h]
0x140016f3b  movzx   eax, [rsp+48h+arg_0]
0x140016f40  mov     [rdi+4], eax
0x140016f43  jmp     short loc_140016F76
0x140016f45  mov     ebp, 2
0x140016f4a  mov     rbx, r8
0x140016f4d  cmp     [rcx+2], bpl
0x140016f51  jnz     short loc_140016F76
0x140016f53  lea     rbx, [r8+4]
0x140016f57  cmp     rbx, rsi
0x140016f5a  ja      short loc_140016FB6
0x140016f5c  lea     edx, [rbp+2]; DestinationSize
0x140016f5f  mov     [rcx+10h], r8
0x140016f63  mov     r9d, edx; SourceSize
0x140016f66  add     rcx, 4; Destination
0x140016f6a  call    cs:__imp_memcpy_s
0x140016f71  nop     dword ptr [rax+rax+00h]
0x140016f76  movzx   eax, word ptr [rdi]
0x140016f79  lea     r14, [rdi+8]
0x140016f7d  mov     [r14], ax
0x140016f81  test    ax, ax
0x140016f84  jnz     short loc_140016FAA
0x140016f86  lea     r15, [rbx+2]
0x140016f8a  cmp     r15, rsi
0x140016f8d  ja      short loc_140016FB6
0x140016f8f  mov     r9, rbp; SourceSize
0x140016f92  mov     r8, rbx; Source
0x140016f95  mov     rdx, rbp; DestinationSize
0x140016f98  mov     rcx, r14; Destination
0x140016f9b  call    cs:__imp_memcpy_s
0x140016fa2  nop     dword ptr [rax+rax+00h]
0x140016fa7  mov     rbx, r15
0x140016faa  movzx   ecx, word ptr [r14]
0x140016fae  add     rcx, rbx
0x140016fb1  cmp     rcx, rsi
0x140016fb4  jbe     short loc_140016FBA
0x140016fb6  xor     al, al
0x140016fb8  jmp     short loc_140016FC4
0x140016fba  mov     [rdi+18h], rbx
0x140016fbe  mov     al, 1
0x140016fc0  mov     [r12], rcx
0x140016fc4  mov     rbx, [rsp+48h+arg_8]
0x140016fc9  mov     rbp, [rsp+48h+arg_10]
0x140016fce  add     rsp, 20h
0x140016fd2  pop     r15
0x140016fd4  pop     r14
0x140016fd6  pop     r12
0x140016fd8  pop     rdi
0x140016fd9  pop     rsi
0x140016fda  retn
```
