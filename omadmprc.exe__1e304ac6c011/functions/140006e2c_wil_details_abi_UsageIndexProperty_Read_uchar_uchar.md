# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140006e2c`
- end: `0x140006f28`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004f44`
- `0x140007684`
- `0x140007a24`

## callees

- `0x140006e2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006e7b`
- `msvcrt!memcpy_s` at `0x140006eb6`
- `msvcrt!memcpy_s` at `0x140006ee7`
- `msvcrt!memcpy_s` at `0x140006e7b`
- `msvcrt!memcpy_s` at `0x140006eb6`
- `msvcrt!memcpy_s` at `0x140006ee7`

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
0x140006e2c  mov     rax, rsp
0x140006e2f  mov     [rax+10h], rbx
0x140006e33  mov     [rax+18h], rbp
0x140006e37  push    rsi
0x140006e38  push    rdi
0x140006e39  push    r12
0x140006e3b  push    r14
0x140006e3d  push    r15
0x140006e3f  sub     rsp, 20h
0x140006e43  xor     r15d, r15d
0x140006e46  mov     rsi, r8
0x140006e49  cmp     byte ptr [rcx+2], 1
0x140006e4d  mov     r12, rdx
0x140006e50  mov     r8, [rdx]; Source
0x140006e53  mov     rdi, rcx
0x140006e56  jnz     short loc_140006E91
0x140006e58  lea     rbx, [r8+2]
0x140006e5c  cmp     rbx, rsi
0x140006e5f  ja      loc_140006F02
0x140006e65  lea     ebp, [r15+2]
0x140006e69  mov     [rcx+10h], r8
0x140006e6d  mov     r9d, ebp; SourceSize
0x140006e70  mov     [rax+8], r15w
0x140006e75  mov     edx, ebp; DestinationSize
0x140006e77  lea     rcx, [rax+8]; Destination
0x140006e7b  call    cs:__imp_memcpy_s
0x140006e82  nop     dword ptr [rax+rax+00h]
0x140006e87  movzx   eax, [rsp+48h+arg_0]
0x140006e8c  mov     [rdi+4], eax
0x140006e8f  jmp     short loc_140006EC2
0x140006e91  mov     ebp, 2
0x140006e96  mov     rbx, r8
0x140006e99  cmp     [rcx+2], bpl
0x140006e9d  jnz     short loc_140006EC2
0x140006e9f  lea     rbx, [r8+4]
0x140006ea3  cmp     rbx, rsi
0x140006ea6  ja      short loc_140006F02
0x140006ea8  lea     edx, [rbp+2]; DestinationSize
0x140006eab  mov     [rcx+10h], r8
0x140006eaf  mov     r9d, edx; SourceSize
0x140006eb2  add     rcx, 4; Destination
0x140006eb6  call    cs:__imp_memcpy_s
0x140006ebd  nop     dword ptr [rax+rax+00h]
0x140006ec2  movzx   eax, word ptr [rdi]
0x140006ec5  lea     r14, [rdi+8]
0x140006ec9  mov     [r14], ax
0x140006ecd  test    ax, ax
0x140006ed0  jnz     short loc_140006EF6
0x140006ed2  lea     r15, [rbx+2]
0x140006ed6  cmp     r15, rsi
0x140006ed9  ja      short loc_140006F02
0x140006edb  mov     r9, rbp; SourceSize
0x140006ede  mov     r8, rbx; Source
0x140006ee1  mov     rdx, rbp; DestinationSize
0x140006ee4  mov     rcx, r14; Destination
0x140006ee7  call    cs:__imp_memcpy_s
0x140006eee  nop     dword ptr [rax+rax+00h]
0x140006ef3  mov     rbx, r15
0x140006ef6  movzx   ecx, word ptr [r14]
0x140006efa  add     rcx, rbx
0x140006efd  cmp     rcx, rsi
0x140006f00  jbe     short loc_140006F06
0x140006f02  xor     al, al
0x140006f04  jmp     short loc_140006F10
0x140006f06  mov     [rdi+18h], rbx
0x140006f0a  mov     al, 1
0x140006f0c  mov     [r12], rcx
0x140006f10  mov     rbx, [rsp+48h+arg_8]
0x140006f15  mov     rbp, [rsp+48h+arg_10]
0x140006f1a  add     rsp, 20h
0x140006f1e  pop     r15
0x140006f20  pop     r14
0x140006f22  pop     r12
0x140006f24  pop     rdi
0x140006f25  pop     rsi
0x140006f26  retn
```
