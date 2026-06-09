# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180022bc8`
- end: `0x180022cb1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800177b8`
- `0x180023388`
- `0x180023710`

## callees

- `0x180022bc8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180022c17`
- `msvcrt!memcpy_s` at `0x180022c4c`
- `msvcrt!memcpy_s` at `0x180022c77`
- `msvcrt!memcpy_s` at `0x180022c17`
- `msvcrt!memcpy_s` at `0x180022c4c`
- `msvcrt!memcpy_s` at `0x180022c77`

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
0x180022bc8  mov     rax, rsp
0x180022bcb  mov     [rax+10h], rbx
0x180022bcf  mov     [rax+18h], rbp
0x180022bd3  push    rsi
0x180022bd4  push    rdi
0x180022bd5  push    r12
0x180022bd7  push    r14
0x180022bd9  push    r15
0x180022bdb  sub     rsp, 20h
0x180022bdf  xor     r15d, r15d
0x180022be2  mov     rsi, r8
0x180022be5  cmp     byte ptr [rcx+2], 1
0x180022be9  mov     r12, rdx
0x180022bec  mov     r8, [rdx]; Source
0x180022bef  mov     rdi, rcx
0x180022bf2  jnz     short loc_180022C27
0x180022bf4  lea     rbx, [r8+2]
0x180022bf8  cmp     rbx, rsi
0x180022bfb  ja      loc_180022C8C
0x180022c01  lea     ebp, [r15+2]
0x180022c05  mov     [rcx+10h], r8
0x180022c09  mov     r9d, ebp; SourceSize
0x180022c0c  mov     [rax+8], r15w
0x180022c11  mov     edx, ebp; DestinationSize
0x180022c13  lea     rcx, [rax+8]; Destination
0x180022c17  call    cs:__imp_memcpy_s
0x180022c1d  movzx   eax, [rsp+48h+arg_0]
0x180022c22  mov     [rdi+4], eax
0x180022c25  jmp     short loc_180022C52
0x180022c27  mov     ebp, 2
0x180022c2c  mov     rbx, r8
0x180022c2f  cmp     [rcx+2], bpl
0x180022c33  jnz     short loc_180022C52
0x180022c35  lea     rbx, [r8+4]
0x180022c39  cmp     rbx, rsi
0x180022c3c  ja      short loc_180022C8C
0x180022c3e  lea     edx, [rbp+2]; DestinationSize
0x180022c41  mov     [rcx+10h], r8
0x180022c45  mov     r9d, edx; SourceSize
0x180022c48  add     rcx, 4; Destination
0x180022c4c  call    cs:__imp_memcpy_s
0x180022c52  movzx   eax, word ptr [rdi]
0x180022c55  lea     r14, [rdi+8]
0x180022c59  mov     [r14], ax
0x180022c5d  test    ax, ax
0x180022c60  jnz     short loc_180022C80
0x180022c62  lea     r15, [rbx+2]
0x180022c66  cmp     r15, rsi
0x180022c69  ja      short loc_180022C8C
0x180022c6b  mov     r9, rbp; SourceSize
0x180022c6e  mov     r8, rbx; Source
0x180022c71  mov     rdx, rbp; DestinationSize
0x180022c74  mov     rcx, r14; Destination
0x180022c77  call    cs:__imp_memcpy_s
0x180022c7d  mov     rbx, r15
0x180022c80  movzx   ecx, word ptr [r14]
0x180022c84  add     rcx, rbx
0x180022c87  cmp     rcx, rsi
0x180022c8a  jbe     short loc_180022C90
0x180022c8c  xor     al, al
0x180022c8e  jmp     short loc_180022C9A
0x180022c90  mov     [rdi+18h], rbx
0x180022c94  mov     al, 1
0x180022c96  mov     [r12], rcx
0x180022c9a  mov     rbx, [rsp+48h+arg_8]
0x180022c9f  mov     rbp, [rsp+48h+arg_10]
0x180022ca4  add     rsp, 20h
0x180022ca8  pop     r15
0x180022caa  pop     r14
0x180022cac  pop     r12
0x180022cae  pop     rdi
0x180022caf  pop     rsi
0x180022cb0  retn
```
