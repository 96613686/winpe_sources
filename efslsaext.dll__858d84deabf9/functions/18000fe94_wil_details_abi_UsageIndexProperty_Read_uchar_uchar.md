# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000fe94`
- end: `0x18000ff7d`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e3dc`
- `0x180010454`
- `0x1800107dc`

## callees

- `0x18000fe94`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000fee3`
- `msvcrt!memcpy_s` at `0x18000ff18`
- `msvcrt!memcpy_s` at `0x18000ff43`
- `msvcrt!memcpy_s` at `0x18000fee3`
- `msvcrt!memcpy_s` at `0x18000ff18`
- `msvcrt!memcpy_s` at `0x18000ff43`

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
0x18000fe94  mov     rax, rsp
0x18000fe97  mov     [rax+10h], rbx
0x18000fe9b  mov     [rax+18h], rbp
0x18000fe9f  push    rsi
0x18000fea0  push    rdi
0x18000fea1  push    r12
0x18000fea3  push    r14
0x18000fea5  push    r15
0x18000fea7  sub     rsp, 20h
0x18000feab  xor     r15d, r15d
0x18000feae  mov     rsi, r8
0x18000feb1  cmp     byte ptr [rcx+2], 1
0x18000feb5  mov     r12, rdx
0x18000feb8  mov     r8, [rdx]; Source
0x18000febb  mov     rdi, rcx
0x18000febe  jnz     short loc_18000FEF3
0x18000fec0  lea     rbx, [r8+2]
0x18000fec4  cmp     rbx, rsi
0x18000fec7  ja      loc_18000FF58
0x18000fecd  lea     ebp, [r15+2]
0x18000fed1  mov     [rcx+10h], r8
0x18000fed5  mov     r9d, ebp; SourceSize
0x18000fed8  mov     [rax+8], r15w
0x18000fedd  mov     edx, ebp; DestinationSize
0x18000fedf  lea     rcx, [rax+8]; Destination
0x18000fee3  call    cs:__imp_memcpy_s
0x18000fee9  movzx   eax, [rsp+48h+arg_0]
0x18000feee  mov     [rdi+4], eax
0x18000fef1  jmp     short loc_18000FF1E
0x18000fef3  mov     ebp, 2
0x18000fef8  mov     rbx, r8
0x18000fefb  cmp     [rcx+2], bpl
0x18000feff  jnz     short loc_18000FF1E
0x18000ff01  lea     rbx, [r8+4]
0x18000ff05  cmp     rbx, rsi
0x18000ff08  ja      short loc_18000FF58
0x18000ff0a  lea     edx, [rbp+2]; DestinationSize
0x18000ff0d  mov     [rcx+10h], r8
0x18000ff11  mov     r9d, edx; SourceSize
0x18000ff14  add     rcx, 4; Destination
0x18000ff18  call    cs:__imp_memcpy_s
0x18000ff1e  movzx   eax, word ptr [rdi]
0x18000ff21  lea     r14, [rdi+8]
0x18000ff25  mov     [r14], ax
0x18000ff29  test    ax, ax
0x18000ff2c  jnz     short loc_18000FF4C
0x18000ff2e  lea     r15, [rbx+2]
0x18000ff32  cmp     r15, rsi
0x18000ff35  ja      short loc_18000FF58
0x18000ff37  mov     r9, rbp; SourceSize
0x18000ff3a  mov     r8, rbx; Source
0x18000ff3d  mov     rdx, rbp; DestinationSize
0x18000ff40  mov     rcx, r14; Destination
0x18000ff43  call    cs:__imp_memcpy_s
0x18000ff49  mov     rbx, r15
0x18000ff4c  movzx   ecx, word ptr [r14]
0x18000ff50  add     rcx, rbx
0x18000ff53  cmp     rcx, rsi
0x18000ff56  jbe     short loc_18000FF5C
0x18000ff58  xor     al, al
0x18000ff5a  jmp     short loc_18000FF66
0x18000ff5c  mov     [rdi+18h], rbx
0x18000ff60  mov     al, 1
0x18000ff62  mov     [r12], rcx
0x18000ff66  mov     rbx, [rsp+48h+arg_8]
0x18000ff6b  mov     rbp, [rsp+48h+arg_10]
0x18000ff70  add     rsp, 20h
0x18000ff74  pop     r15
0x18000ff76  pop     r14
0x18000ff78  pop     r12
0x18000ff7a  pop     rdi
0x18000ff7b  pop     rsi
0x18000ff7c  retn
```
