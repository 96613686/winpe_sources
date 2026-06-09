# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800079a8`
- end: `0x180007a91`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000567c`
- `0x1800081d0`
- `0x180008558`

## callees

- `0x1800079a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800079f7`
- `msvcrt!memcpy_s` at `0x180007a2c`
- `msvcrt!memcpy_s` at `0x180007a57`
- `msvcrt!memcpy_s` at `0x1800079f7`
- `msvcrt!memcpy_s` at `0x180007a2c`
- `msvcrt!memcpy_s` at `0x180007a57`

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
0x1800079a8  mov     rax, rsp
0x1800079ab  mov     [rax+10h], rbx
0x1800079af  mov     [rax+18h], rbp
0x1800079b3  push    rsi
0x1800079b4  push    rdi
0x1800079b5  push    r12
0x1800079b7  push    r14
0x1800079b9  push    r15
0x1800079bb  sub     rsp, 20h
0x1800079bf  xor     r15d, r15d
0x1800079c2  mov     rsi, r8
0x1800079c5  cmp     byte ptr [rcx+2], 1
0x1800079c9  mov     r12, rdx
0x1800079cc  mov     r8, [rdx]; Source
0x1800079cf  mov     rdi, rcx
0x1800079d2  jnz     short loc_180007A07
0x1800079d4  lea     rbx, [r8+2]
0x1800079d8  cmp     rbx, rsi
0x1800079db  ja      loc_180007A6C
0x1800079e1  lea     ebp, [r15+2]
0x1800079e5  mov     [rcx+10h], r8
0x1800079e9  mov     r9d, ebp; SourceSize
0x1800079ec  mov     [rax+8], r15w
0x1800079f1  mov     edx, ebp; DestinationSize
0x1800079f3  lea     rcx, [rax+8]; Destination
0x1800079f7  call    cs:__imp_memcpy_s
0x1800079fd  movzx   eax, [rsp+48h+arg_0]
0x180007a02  mov     [rdi+4], eax
0x180007a05  jmp     short loc_180007A32
0x180007a07  mov     ebp, 2
0x180007a0c  mov     rbx, r8
0x180007a0f  cmp     [rcx+2], bpl
0x180007a13  jnz     short loc_180007A32
0x180007a15  lea     rbx, [r8+4]
0x180007a19  cmp     rbx, rsi
0x180007a1c  ja      short loc_180007A6C
0x180007a1e  lea     edx, [rbp+2]; DestinationSize
0x180007a21  mov     [rcx+10h], r8
0x180007a25  mov     r9d, edx; SourceSize
0x180007a28  add     rcx, 4; Destination
0x180007a2c  call    cs:__imp_memcpy_s
0x180007a32  movzx   eax, word ptr [rdi]
0x180007a35  lea     r14, [rdi+8]
0x180007a39  mov     [r14], ax
0x180007a3d  test    ax, ax
0x180007a40  jnz     short loc_180007A60
0x180007a42  lea     r15, [rbx+2]
0x180007a46  cmp     r15, rsi
0x180007a49  ja      short loc_180007A6C
0x180007a4b  mov     r9, rbp; SourceSize
0x180007a4e  mov     r8, rbx; Source
0x180007a51  mov     rdx, rbp; DestinationSize
0x180007a54  mov     rcx, r14; Destination
0x180007a57  call    cs:__imp_memcpy_s
0x180007a5d  mov     rbx, r15
0x180007a60  movzx   ecx, word ptr [r14]
0x180007a64  add     rcx, rbx
0x180007a67  cmp     rcx, rsi
0x180007a6a  jbe     short loc_180007A70
0x180007a6c  xor     al, al
0x180007a6e  jmp     short loc_180007A7A
0x180007a70  mov     [rdi+18h], rbx
0x180007a74  mov     al, 1
0x180007a76  mov     [r12], rcx
0x180007a7a  mov     rbx, [rsp+48h+arg_8]
0x180007a7f  mov     rbp, [rsp+48h+arg_10]
0x180007a84  add     rsp, 20h
0x180007a88  pop     r15
0x180007a8a  pop     r14
0x180007a8c  pop     r12
0x180007a8e  pop     rdi
0x180007a8f  pop     rsi
0x180007a90  retn
```
