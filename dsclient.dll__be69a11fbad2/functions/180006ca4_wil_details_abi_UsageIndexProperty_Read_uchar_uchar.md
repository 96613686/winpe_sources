# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006ca4`
- end: `0x180006d8d`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005438`
- `0x180006088`
- `0x180006518`
- `0x180007334`
- `0x180007d34`

## callees

- `0x180006ca4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006cf3`
- `msvcrt!memcpy_s` at `0x180006d28`
- `msvcrt!memcpy_s` at `0x180006d53`
- `msvcrt!memcpy_s` at `0x180006cf3`
- `msvcrt!memcpy_s` at `0x180006d28`
- `msvcrt!memcpy_s` at `0x180006d53`

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
0x180006ca4  mov     rax, rsp
0x180006ca7  mov     [rax+10h], rbx
0x180006cab  mov     [rax+18h], rbp
0x180006caf  push    rsi
0x180006cb0  push    rdi
0x180006cb1  push    r12
0x180006cb3  push    r14
0x180006cb5  push    r15
0x180006cb7  sub     rsp, 20h
0x180006cbb  xor     r15d, r15d
0x180006cbe  mov     rsi, r8
0x180006cc1  cmp     byte ptr [rcx+2], 1
0x180006cc5  mov     r12, rdx
0x180006cc8  mov     r8, [rdx]; Source
0x180006ccb  mov     rdi, rcx
0x180006cce  jnz     short loc_180006D03
0x180006cd0  lea     rbx, [r8+2]
0x180006cd4  cmp     rbx, rsi
0x180006cd7  ja      loc_180006D68
0x180006cdd  lea     ebp, [r15+2]
0x180006ce1  mov     [rcx+10h], r8
0x180006ce5  mov     r9d, ebp; SourceSize
0x180006ce8  mov     [rax+8], r15w
0x180006ced  mov     edx, ebp; DestinationSize
0x180006cef  lea     rcx, [rax+8]; Destination
0x180006cf3  call    cs:__imp_memcpy_s
0x180006cf9  movzx   eax, [rsp+48h+arg_0]
0x180006cfe  mov     [rdi+4], eax
0x180006d01  jmp     short loc_180006D2E
0x180006d03  mov     ebp, 2
0x180006d08  mov     rbx, r8
0x180006d0b  cmp     [rcx+2], bpl
0x180006d0f  jnz     short loc_180006D2E
0x180006d11  lea     rbx, [r8+4]
0x180006d15  cmp     rbx, rsi
0x180006d18  ja      short loc_180006D68
0x180006d1a  lea     edx, [rbp+2]; DestinationSize
0x180006d1d  mov     [rcx+10h], r8
0x180006d21  mov     r9d, edx; SourceSize
0x180006d24  add     rcx, 4; Destination
0x180006d28  call    cs:__imp_memcpy_s
0x180006d2e  movzx   eax, word ptr [rdi]
0x180006d31  lea     r14, [rdi+8]
0x180006d35  mov     [r14], ax
0x180006d39  test    ax, ax
0x180006d3c  jnz     short loc_180006D5C
0x180006d3e  lea     r15, [rbx+2]
0x180006d42  cmp     r15, rsi
0x180006d45  ja      short loc_180006D68
0x180006d47  mov     r9, rbp; SourceSize
0x180006d4a  mov     r8, rbx; Source
0x180006d4d  mov     rdx, rbp; DestinationSize
0x180006d50  mov     rcx, r14; Destination
0x180006d53  call    cs:__imp_memcpy_s
0x180006d59  mov     rbx, r15
0x180006d5c  movzx   ecx, word ptr [r14]
0x180006d60  add     rcx, rbx
0x180006d63  cmp     rcx, rsi
0x180006d66  jbe     short loc_180006D6C
0x180006d68  xor     al, al
0x180006d6a  jmp     short loc_180006D76
0x180006d6c  mov     [rdi+18h], rbx
0x180006d70  mov     al, 1
0x180006d72  mov     [r12], rcx
0x180006d76  mov     rbx, [rsp+48h+arg_8]
0x180006d7b  mov     rbp, [rsp+48h+arg_10]
0x180006d80  add     rsp, 20h
0x180006d84  pop     r15
0x180006d86  pop     r14
0x180006d88  pop     r12
0x180006d8a  pop     rdi
0x180006d8b  pop     rsi
0x180006d8c  retn
```
