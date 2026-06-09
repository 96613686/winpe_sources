# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001bf9c`
- end: `0x18001c085`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800198c0`
- `0x180019d60`
- `0x180019e90`
- `0x18001c518`
- `0x18001cc34`

## callees

- `0x18001bf9c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001bfeb`
- `msvcrt!memcpy_s` at `0x18001c020`
- `msvcrt!memcpy_s` at `0x18001c04b`
- `msvcrt!memcpy_s` at `0x18001bfeb`
- `msvcrt!memcpy_s` at `0x18001c020`
- `msvcrt!memcpy_s` at `0x18001c04b`

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
0x18001bf9c  mov     rax, rsp
0x18001bf9f  mov     [rax+10h], rbx
0x18001bfa3  mov     [rax+18h], rbp
0x18001bfa7  push    rsi
0x18001bfa8  push    rdi
0x18001bfa9  push    r12
0x18001bfab  push    r14
0x18001bfad  push    r15
0x18001bfaf  sub     rsp, 20h
0x18001bfb3  xor     r15d, r15d
0x18001bfb6  mov     rsi, r8
0x18001bfb9  cmp     byte ptr [rcx+2], 1
0x18001bfbd  mov     r12, rdx
0x18001bfc0  mov     r8, [rdx]; Source
0x18001bfc3  mov     rdi, rcx
0x18001bfc6  jnz     short loc_18001BFFB
0x18001bfc8  lea     rbx, [r8+2]
0x18001bfcc  cmp     rbx, rsi
0x18001bfcf  ja      loc_18001C060
0x18001bfd5  lea     ebp, [r15+2]
0x18001bfd9  mov     [rcx+10h], r8
0x18001bfdd  mov     r9d, ebp; SourceSize
0x18001bfe0  mov     [rax+8], r15w
0x18001bfe5  mov     edx, ebp; DestinationSize
0x18001bfe7  lea     rcx, [rax+8]; Destination
0x18001bfeb  call    cs:__imp_memcpy_s
0x18001bff1  movzx   eax, [rsp+48h+arg_0]
0x18001bff6  mov     [rdi+4], eax
0x18001bff9  jmp     short loc_18001C026
0x18001bffb  mov     ebp, 2
0x18001c000  mov     rbx, r8
0x18001c003  cmp     [rcx+2], bpl
0x18001c007  jnz     short loc_18001C026
0x18001c009  lea     rbx, [r8+4]
0x18001c00d  cmp     rbx, rsi
0x18001c010  ja      short loc_18001C060
0x18001c012  lea     edx, [rbp+2]; DestinationSize
0x18001c015  mov     [rcx+10h], r8
0x18001c019  mov     r9d, edx; SourceSize
0x18001c01c  add     rcx, 4; Destination
0x18001c020  call    cs:__imp_memcpy_s
0x18001c026  movzx   eax, word ptr [rdi]
0x18001c029  lea     r14, [rdi+8]
0x18001c02d  mov     [r14], ax
0x18001c031  test    ax, ax
0x18001c034  jnz     short loc_18001C054
0x18001c036  lea     r15, [rbx+2]
0x18001c03a  cmp     r15, rsi
0x18001c03d  ja      short loc_18001C060
0x18001c03f  mov     r9, rbp; SourceSize
0x18001c042  mov     r8, rbx; Source
0x18001c045  mov     rdx, rbp; DestinationSize
0x18001c048  mov     rcx, r14; Destination
0x18001c04b  call    cs:__imp_memcpy_s
0x18001c051  mov     rbx, r15
0x18001c054  movzx   ecx, word ptr [r14]
0x18001c058  add     rcx, rbx
0x18001c05b  cmp     rcx, rsi
0x18001c05e  jbe     short loc_18001C064
0x18001c060  xor     al, al
0x18001c062  jmp     short loc_18001C06E
0x18001c064  mov     [rdi+18h], rbx
0x18001c068  mov     al, 1
0x18001c06a  mov     [r12], rcx
0x18001c06e  mov     rbx, [rsp+48h+arg_8]
0x18001c073  mov     rbp, [rsp+48h+arg_10]
0x18001c078  add     rsp, 20h
0x18001c07c  pop     r15
0x18001c07e  pop     r14
0x18001c080  pop     r12
0x18001c082  pop     rdi
0x18001c083  pop     rsi
0x18001c084  retn
```
