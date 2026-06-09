# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180011258`
- end: `0x180011341`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180010ad0`
- `0x180010d00`
- `0x180010e40`
- `0x180011788`
- `0x180011d58`

## callees

- `0x180011258`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800112a7`
- `msvcrt!memcpy_s` at `0x1800112dc`
- `msvcrt!memcpy_s` at `0x180011307`
- `msvcrt!memcpy_s` at `0x1800112a7`
- `msvcrt!memcpy_s` at `0x1800112dc`
- `msvcrt!memcpy_s` at `0x180011307`

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
0x180011258  mov     rax, rsp
0x18001125b  mov     [rax+10h], rbx
0x18001125f  mov     [rax+18h], rbp
0x180011263  push    rsi
0x180011264  push    rdi
0x180011265  push    r12
0x180011267  push    r14
0x180011269  push    r15
0x18001126b  sub     rsp, 20h
0x18001126f  xor     r15d, r15d
0x180011272  mov     rsi, r8
0x180011275  cmp     byte ptr [rcx+2], 1
0x180011279  mov     r12, rdx
0x18001127c  mov     r8, [rdx]; Source
0x18001127f  mov     rdi, rcx
0x180011282  jnz     short loc_1800112B7
0x180011284  lea     rbx, [r8+2]
0x180011288  cmp     rbx, rsi
0x18001128b  ja      loc_18001131C
0x180011291  lea     ebp, [r15+2]
0x180011295  mov     [rcx+10h], r8
0x180011299  mov     r9d, ebp; SourceSize
0x18001129c  mov     [rax+8], r15w
0x1800112a1  mov     edx, ebp; DestinationSize
0x1800112a3  lea     rcx, [rax+8]; Destination
0x1800112a7  call    cs:__imp_memcpy_s
0x1800112ad  movzx   eax, [rsp+48h+arg_0]
0x1800112b2  mov     [rdi+4], eax
0x1800112b5  jmp     short loc_1800112E2
0x1800112b7  mov     ebp, 2
0x1800112bc  mov     rbx, r8
0x1800112bf  cmp     [rcx+2], bpl
0x1800112c3  jnz     short loc_1800112E2
0x1800112c5  lea     rbx, [r8+4]
0x1800112c9  cmp     rbx, rsi
0x1800112cc  ja      short loc_18001131C
0x1800112ce  lea     edx, [rbp+2]; DestinationSize
0x1800112d1  mov     [rcx+10h], r8
0x1800112d5  mov     r9d, edx; SourceSize
0x1800112d8  add     rcx, 4; Destination
0x1800112dc  call    cs:__imp_memcpy_s
0x1800112e2  movzx   eax, word ptr [rdi]
0x1800112e5  lea     r14, [rdi+8]
0x1800112e9  mov     [r14], ax
0x1800112ed  test    ax, ax
0x1800112f0  jnz     short loc_180011310
0x1800112f2  lea     r15, [rbx+2]
0x1800112f6  cmp     r15, rsi
0x1800112f9  ja      short loc_18001131C
0x1800112fb  mov     r9, rbp; SourceSize
0x1800112fe  mov     r8, rbx; Source
0x180011301  mov     rdx, rbp; DestinationSize
0x180011304  mov     rcx, r14; Destination
0x180011307  call    cs:__imp_memcpy_s
0x18001130d  mov     rbx, r15
0x180011310  movzx   ecx, word ptr [r14]
0x180011314  add     rcx, rbx
0x180011317  cmp     rcx, rsi
0x18001131a  jbe     short loc_180011320
0x18001131c  xor     al, al
0x18001131e  jmp     short loc_18001132A
0x180011320  mov     [rdi+18h], rbx
0x180011324  mov     al, 1
0x180011326  mov     [r12], rcx
0x18001132a  mov     rbx, [rsp+48h+arg_8]
0x18001132f  mov     rbp, [rsp+48h+arg_10]
0x180011334  add     rsp, 20h
0x180011338  pop     r15
0x18001133a  pop     r14
0x18001133c  pop     r12
0x18001133e  pop     rdi
0x18001133f  pop     rsi
0x180011340  retn
```
