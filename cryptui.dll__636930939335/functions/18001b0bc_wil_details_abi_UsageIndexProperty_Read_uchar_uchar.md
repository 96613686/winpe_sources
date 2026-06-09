# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001b0bc`
- end: `0x18001b1a5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180017d34`
- `0x18001a324`
- `0x18001a7d4`
- `0x18001b6ac`
- `0x18001c1dc`

## callees

- `0x18001b0bc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001b10b`
- `msvcrt!memcpy_s` at `0x18001b140`
- `msvcrt!memcpy_s` at `0x18001b16b`
- `msvcrt!memcpy_s` at `0x18001b10b`
- `msvcrt!memcpy_s` at `0x18001b140`
- `msvcrt!memcpy_s` at `0x18001b16b`

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
0x18001b0bc  mov     rax, rsp
0x18001b0bf  mov     [rax+10h], rbx
0x18001b0c3  mov     [rax+18h], rbp
0x18001b0c7  push    rsi
0x18001b0c8  push    rdi
0x18001b0c9  push    r12
0x18001b0cb  push    r14
0x18001b0cd  push    r15
0x18001b0cf  sub     rsp, 20h
0x18001b0d3  xor     r15d, r15d
0x18001b0d6  mov     rsi, r8
0x18001b0d9  cmp     byte ptr [rcx+2], 1
0x18001b0dd  mov     r12, rdx
0x18001b0e0  mov     r8, [rdx]; Source
0x18001b0e3  mov     rdi, rcx
0x18001b0e6  jnz     short loc_18001B11B
0x18001b0e8  lea     rbx, [r8+2]
0x18001b0ec  cmp     rbx, rsi
0x18001b0ef  ja      loc_18001B180
0x18001b0f5  lea     ebp, [r15+2]
0x18001b0f9  mov     [rcx+10h], r8
0x18001b0fd  mov     r9d, ebp; SourceSize
0x18001b100  mov     [rax+8], r15w
0x18001b105  mov     edx, ebp; DestinationSize
0x18001b107  lea     rcx, [rax+8]; Destination
0x18001b10b  call    cs:__imp_memcpy_s
0x18001b111  movzx   eax, [rsp+48h+arg_0]
0x18001b116  mov     [rdi+4], eax
0x18001b119  jmp     short loc_18001B146
0x18001b11b  mov     ebp, 2
0x18001b120  mov     rbx, r8
0x18001b123  cmp     [rcx+2], bpl
0x18001b127  jnz     short loc_18001B146
0x18001b129  lea     rbx, [r8+4]
0x18001b12d  cmp     rbx, rsi
0x18001b130  ja      short loc_18001B180
0x18001b132  lea     edx, [rbp+2]; DestinationSize
0x18001b135  mov     [rcx+10h], r8
0x18001b139  mov     r9d, edx; SourceSize
0x18001b13c  add     rcx, 4; Destination
0x18001b140  call    cs:__imp_memcpy_s
0x18001b146  movzx   eax, word ptr [rdi]
0x18001b149  lea     r14, [rdi+8]
0x18001b14d  mov     [r14], ax
0x18001b151  test    ax, ax
0x18001b154  jnz     short loc_18001B174
0x18001b156  lea     r15, [rbx+2]
0x18001b15a  cmp     r15, rsi
0x18001b15d  ja      short loc_18001B180
0x18001b15f  mov     r9, rbp; SourceSize
0x18001b162  mov     r8, rbx; Source
0x18001b165  mov     rdx, rbp; DestinationSize
0x18001b168  mov     rcx, r14; Destination
0x18001b16b  call    cs:__imp_memcpy_s
0x18001b171  mov     rbx, r15
0x18001b174  movzx   ecx, word ptr [r14]
0x18001b178  add     rcx, rbx
0x18001b17b  cmp     rcx, rsi
0x18001b17e  jbe     short loc_18001B184
0x18001b180  xor     al, al
0x18001b182  jmp     short loc_18001B18E
0x18001b184  mov     [rdi+18h], rbx
0x18001b188  mov     al, 1
0x18001b18a  mov     [r12], rcx
0x18001b18e  mov     rbx, [rsp+48h+arg_8]
0x18001b193  mov     rbp, [rsp+48h+arg_10]
0x18001b198  add     rsp, 20h
0x18001b19c  pop     r15
0x18001b19e  pop     r14
0x18001b1a0  pop     r12
0x18001b1a2  pop     rdi
0x18001b1a3  pop     rsi
0x18001b1a4  retn
```
