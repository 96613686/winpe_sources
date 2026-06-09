# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180020dc8`
- end: `0x180020ec4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180016dd4`
- `0x1800213f4`
- `0x180021794`

## callees

- `0x180020dc8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180020e17`
- `msvcrt!memcpy_s` at `0x180020e52`
- `msvcrt!memcpy_s` at `0x180020e83`
- `msvcrt!memcpy_s` at `0x180020e17`
- `msvcrt!memcpy_s` at `0x180020e52`
- `msvcrt!memcpy_s` at `0x180020e83`

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
0x180020dc8  mov     rax, rsp
0x180020dcb  mov     [rax+10h], rbx
0x180020dcf  mov     [rax+18h], rbp
0x180020dd3  push    rsi
0x180020dd4  push    rdi
0x180020dd5  push    r12
0x180020dd7  push    r14
0x180020dd9  push    r15
0x180020ddb  sub     rsp, 20h
0x180020ddf  xor     r15d, r15d
0x180020de2  mov     rsi, r8
0x180020de5  cmp     byte ptr [rcx+2], 1
0x180020de9  mov     r12, rdx
0x180020dec  mov     r8, [rdx]; Source
0x180020def  mov     rdi, rcx
0x180020df2  jnz     short loc_180020E2D
0x180020df4  lea     rbx, [r8+2]
0x180020df8  cmp     rbx, rsi
0x180020dfb  ja      loc_180020E9E
0x180020e01  lea     ebp, [r15+2]
0x180020e05  mov     [rcx+10h], r8
0x180020e09  mov     r9d, ebp; SourceSize
0x180020e0c  mov     [rax+8], r15w
0x180020e11  mov     edx, ebp; DestinationSize
0x180020e13  lea     rcx, [rax+8]; Destination
0x180020e17  call    cs:__imp_memcpy_s
0x180020e1e  nop     dword ptr [rax+rax+00h]
0x180020e23  movzx   eax, [rsp+48h+arg_0]
0x180020e28  mov     [rdi+4], eax
0x180020e2b  jmp     short loc_180020E5E
0x180020e2d  mov     ebp, 2
0x180020e32  mov     rbx, r8
0x180020e35  cmp     [rcx+2], bpl
0x180020e39  jnz     short loc_180020E5E
0x180020e3b  lea     rbx, [r8+4]
0x180020e3f  cmp     rbx, rsi
0x180020e42  ja      short loc_180020E9E
0x180020e44  lea     edx, [rbp+2]; DestinationSize
0x180020e47  mov     [rcx+10h], r8
0x180020e4b  mov     r9d, edx; SourceSize
0x180020e4e  add     rcx, 4; Destination
0x180020e52  call    cs:__imp_memcpy_s
0x180020e59  nop     dword ptr [rax+rax+00h]
0x180020e5e  movzx   eax, word ptr [rdi]
0x180020e61  lea     r14, [rdi+8]
0x180020e65  mov     [r14], ax
0x180020e69  test    ax, ax
0x180020e6c  jnz     short loc_180020E92
0x180020e6e  lea     r15, [rbx+2]
0x180020e72  cmp     r15, rsi
0x180020e75  ja      short loc_180020E9E
0x180020e77  mov     r9, rbp; SourceSize
0x180020e7a  mov     r8, rbx; Source
0x180020e7d  mov     rdx, rbp; DestinationSize
0x180020e80  mov     rcx, r14; Destination
0x180020e83  call    cs:__imp_memcpy_s
0x180020e8a  nop     dword ptr [rax+rax+00h]
0x180020e8f  mov     rbx, r15
0x180020e92  movzx   ecx, word ptr [r14]
0x180020e96  add     rcx, rbx
0x180020e99  cmp     rcx, rsi
0x180020e9c  jbe     short loc_180020EA2
0x180020e9e  xor     al, al
0x180020ea0  jmp     short loc_180020EAC
0x180020ea2  mov     [rdi+18h], rbx
0x180020ea6  mov     al, 1
0x180020ea8  mov     [r12], rcx
0x180020eac  mov     rbx, [rsp+48h+arg_8]
0x180020eb1  mov     rbp, [rsp+48h+arg_10]
0x180020eb6  add     rsp, 20h
0x180020eba  pop     r15
0x180020ebc  pop     r14
0x180020ebe  pop     r12
0x180020ec0  pop     rdi
0x180020ec1  pop     rsi
0x180020ec2  retn
```
