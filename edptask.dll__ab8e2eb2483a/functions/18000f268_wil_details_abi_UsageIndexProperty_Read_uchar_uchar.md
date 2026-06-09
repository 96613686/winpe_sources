# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000f268`
- end: `0x18000f351`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008654`
- `0x18000fa28`
- `0x18000fdb0`

## callees

- `0x18000f268`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f2b7`
- `msvcrt!memcpy_s` at `0x18000f2ec`
- `msvcrt!memcpy_s` at `0x18000f317`
- `msvcrt!memcpy_s` at `0x18000f2b7`
- `msvcrt!memcpy_s` at `0x18000f2ec`
- `msvcrt!memcpy_s` at `0x18000f317`

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
0x18000f268  mov     rax, rsp
0x18000f26b  mov     [rax+10h], rbx
0x18000f26f  mov     [rax+18h], rbp
0x18000f273  push    rsi
0x18000f274  push    rdi
0x18000f275  push    r12
0x18000f277  push    r14
0x18000f279  push    r15
0x18000f27b  sub     rsp, 20h
0x18000f27f  xor     r15d, r15d
0x18000f282  mov     rsi, r8
0x18000f285  cmp     byte ptr [rcx+2], 1
0x18000f289  mov     r12, rdx
0x18000f28c  mov     r8, [rdx]; Source
0x18000f28f  mov     rdi, rcx
0x18000f292  jnz     short loc_18000F2C7
0x18000f294  lea     rbx, [r8+2]
0x18000f298  cmp     rbx, rsi
0x18000f29b  ja      loc_18000F32C
0x18000f2a1  lea     ebp, [r15+2]
0x18000f2a5  mov     [rcx+10h], r8
0x18000f2a9  mov     r9d, ebp; SourceSize
0x18000f2ac  mov     [rax+8], r15w
0x18000f2b1  mov     edx, ebp; DestinationSize
0x18000f2b3  lea     rcx, [rax+8]; Destination
0x18000f2b7  call    cs:__imp_memcpy_s
0x18000f2bd  movzx   eax, [rsp+48h+arg_0]
0x18000f2c2  mov     [rdi+4], eax
0x18000f2c5  jmp     short loc_18000F2F2
0x18000f2c7  mov     ebp, 2
0x18000f2cc  mov     rbx, r8
0x18000f2cf  cmp     [rcx+2], bpl
0x18000f2d3  jnz     short loc_18000F2F2
0x18000f2d5  lea     rbx, [r8+4]
0x18000f2d9  cmp     rbx, rsi
0x18000f2dc  ja      short loc_18000F32C
0x18000f2de  lea     edx, [rbp+2]; DestinationSize
0x18000f2e1  mov     [rcx+10h], r8
0x18000f2e5  mov     r9d, edx; SourceSize
0x18000f2e8  add     rcx, 4; Destination
0x18000f2ec  call    cs:__imp_memcpy_s
0x18000f2f2  movzx   eax, word ptr [rdi]
0x18000f2f5  lea     r14, [rdi+8]
0x18000f2f9  mov     [r14], ax
0x18000f2fd  test    ax, ax
0x18000f300  jnz     short loc_18000F320
0x18000f302  lea     r15, [rbx+2]
0x18000f306  cmp     r15, rsi
0x18000f309  ja      short loc_18000F32C
0x18000f30b  mov     r9, rbp; SourceSize
0x18000f30e  mov     r8, rbx; Source
0x18000f311  mov     rdx, rbp; DestinationSize
0x18000f314  mov     rcx, r14; Destination
0x18000f317  call    cs:__imp_memcpy_s
0x18000f31d  mov     rbx, r15
0x18000f320  movzx   ecx, word ptr [r14]
0x18000f324  add     rcx, rbx
0x18000f327  cmp     rcx, rsi
0x18000f32a  jbe     short loc_18000F330
0x18000f32c  xor     al, al
0x18000f32e  jmp     short loc_18000F33A
0x18000f330  mov     [rdi+18h], rbx
0x18000f334  mov     al, 1
0x18000f336  mov     [r12], rcx
0x18000f33a  mov     rbx, [rsp+48h+arg_8]
0x18000f33f  mov     rbp, [rsp+48h+arg_10]
0x18000f344  add     rsp, 20h
0x18000f348  pop     r15
0x18000f34a  pop     r14
0x18000f34c  pop     r12
0x18000f34e  pop     rdi
0x18000f34f  pop     rsi
0x18000f350  retn
```
