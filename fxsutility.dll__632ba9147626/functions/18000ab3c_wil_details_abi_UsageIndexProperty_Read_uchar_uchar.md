# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000ab3c`
- end: `0x18000ac25`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800094cc`
- `0x18000b178`
- `0x18000b500`

## callees

- `0x18000ab3c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ab8b`
- `msvcrt!memcpy_s` at `0x18000abc0`
- `msvcrt!memcpy_s` at `0x18000abeb`
- `msvcrt!memcpy_s` at `0x18000ab8b`
- `msvcrt!memcpy_s` at `0x18000abc0`
- `msvcrt!memcpy_s` at `0x18000abeb`

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
0x18000ab3c  mov     rax, rsp
0x18000ab3f  mov     [rax+10h], rbx
0x18000ab43  mov     [rax+18h], rbp
0x18000ab47  push    rsi
0x18000ab48  push    rdi
0x18000ab49  push    r12
0x18000ab4b  push    r14
0x18000ab4d  push    r15
0x18000ab4f  sub     rsp, 20h
0x18000ab53  xor     r15d, r15d
0x18000ab56  mov     rsi, r8
0x18000ab59  cmp     byte ptr [rcx+2], 1
0x18000ab5d  mov     r12, rdx
0x18000ab60  mov     r8, [rdx]; Source
0x18000ab63  mov     rdi, rcx
0x18000ab66  jnz     short loc_18000AB9B
0x18000ab68  lea     rbx, [r8+2]
0x18000ab6c  cmp     rbx, rsi
0x18000ab6f  ja      loc_18000AC00
0x18000ab75  lea     ebp, [r15+2]
0x18000ab79  mov     [rcx+10h], r8
0x18000ab7d  mov     r9d, ebp; SourceSize
0x18000ab80  mov     [rax+8], r15w
0x18000ab85  mov     edx, ebp; DestinationSize
0x18000ab87  lea     rcx, [rax+8]; Destination
0x18000ab8b  call    cs:__imp_memcpy_s
0x18000ab91  movzx   eax, [rsp+48h+arg_0]
0x18000ab96  mov     [rdi+4], eax
0x18000ab99  jmp     short loc_18000ABC6
0x18000ab9b  mov     ebp, 2
0x18000aba0  mov     rbx, r8
0x18000aba3  cmp     [rcx+2], bpl
0x18000aba7  jnz     short loc_18000ABC6
0x18000aba9  lea     rbx, [r8+4]
0x18000abad  cmp     rbx, rsi
0x18000abb0  ja      short loc_18000AC00
0x18000abb2  lea     edx, [rbp+2]; DestinationSize
0x18000abb5  mov     [rcx+10h], r8
0x18000abb9  mov     r9d, edx; SourceSize
0x18000abbc  add     rcx, 4; Destination
0x18000abc0  call    cs:__imp_memcpy_s
0x18000abc6  movzx   eax, word ptr [rdi]
0x18000abc9  lea     r14, [rdi+8]
0x18000abcd  mov     [r14], ax
0x18000abd1  test    ax, ax
0x18000abd4  jnz     short loc_18000ABF4
0x18000abd6  lea     r15, [rbx+2]
0x18000abda  cmp     r15, rsi
0x18000abdd  ja      short loc_18000AC00
0x18000abdf  mov     r9, rbp; SourceSize
0x18000abe2  mov     r8, rbx; Source
0x18000abe5  mov     rdx, rbp; DestinationSize
0x18000abe8  mov     rcx, r14; Destination
0x18000abeb  call    cs:__imp_memcpy_s
0x18000abf1  mov     rbx, r15
0x18000abf4  movzx   ecx, word ptr [r14]
0x18000abf8  add     rcx, rbx
0x18000abfb  cmp     rcx, rsi
0x18000abfe  jbe     short loc_18000AC04
0x18000ac00  xor     al, al
0x18000ac02  jmp     short loc_18000AC0E
0x18000ac04  mov     [rdi+18h], rbx
0x18000ac08  mov     al, 1
0x18000ac0a  mov     [r12], rcx
0x18000ac0e  mov     rbx, [rsp+48h+arg_8]
0x18000ac13  mov     rbp, [rsp+48h+arg_10]
0x18000ac18  add     rsp, 20h
0x18000ac1c  pop     r15
0x18000ac1e  pop     r14
0x18000ac20  pop     r12
0x18000ac22  pop     rdi
0x18000ac23  pop     rsi
0x18000ac24  retn
```
