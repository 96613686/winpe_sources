# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18002bbc4`
- end: `0x18002bcad`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180028d24`
- `0x18002ad48`
- `0x18002b1ec`
- `0x18002c1e8`
- `0x18002d504`

## callees

- `0x18002bbc4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002bc13`
- `msvcrt!memcpy_s` at `0x18002bc48`
- `msvcrt!memcpy_s` at `0x18002bc73`
- `msvcrt!memcpy_s` at `0x18002bc13`
- `msvcrt!memcpy_s` at `0x18002bc48`
- `msvcrt!memcpy_s` at `0x18002bc73`

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
0x18002bbc4  mov     rax, rsp
0x18002bbc7  mov     [rax+10h], rbx
0x18002bbcb  mov     [rax+18h], rbp
0x18002bbcf  push    rsi
0x18002bbd0  push    rdi
0x18002bbd1  push    r12
0x18002bbd3  push    r14
0x18002bbd5  push    r15
0x18002bbd7  sub     rsp, 20h
0x18002bbdb  xor     r15d, r15d
0x18002bbde  mov     rsi, r8
0x18002bbe1  cmp     byte ptr [rcx+2], 1
0x18002bbe5  mov     r12, rdx
0x18002bbe8  mov     r8, [rdx]; Source
0x18002bbeb  mov     rdi, rcx
0x18002bbee  jnz     short loc_18002BC23
0x18002bbf0  lea     rbx, [r8+2]
0x18002bbf4  cmp     rbx, rsi
0x18002bbf7  ja      loc_18002BC88
0x18002bbfd  lea     ebp, [r15+2]
0x18002bc01  mov     [rcx+10h], r8
0x18002bc05  mov     r9d, ebp; SourceSize
0x18002bc08  mov     [rax+8], r15w
0x18002bc0d  mov     edx, ebp; DestinationSize
0x18002bc0f  lea     rcx, [rax+8]; Destination
0x18002bc13  call    cs:__imp_memcpy_s
0x18002bc19  movzx   eax, [rsp+48h+arg_0]
0x18002bc1e  mov     [rdi+4], eax
0x18002bc21  jmp     short loc_18002BC4E
0x18002bc23  mov     ebp, 2
0x18002bc28  mov     rbx, r8
0x18002bc2b  cmp     [rcx+2], bpl
0x18002bc2f  jnz     short loc_18002BC4E
0x18002bc31  lea     rbx, [r8+4]
0x18002bc35  cmp     rbx, rsi
0x18002bc38  ja      short loc_18002BC88
0x18002bc3a  lea     edx, [rbp+2]; DestinationSize
0x18002bc3d  mov     [rcx+10h], r8
0x18002bc41  mov     r9d, edx; SourceSize
0x18002bc44  add     rcx, 4; Destination
0x18002bc48  call    cs:__imp_memcpy_s
0x18002bc4e  movzx   eax, word ptr [rdi]
0x18002bc51  lea     r14, [rdi+8]
0x18002bc55  mov     [r14], ax
0x18002bc59  test    ax, ax
0x18002bc5c  jnz     short loc_18002BC7C
0x18002bc5e  lea     r15, [rbx+2]
0x18002bc62  cmp     r15, rsi
0x18002bc65  ja      short loc_18002BC88
0x18002bc67  mov     r9, rbp; SourceSize
0x18002bc6a  mov     r8, rbx; Source
0x18002bc6d  mov     rdx, rbp; DestinationSize
0x18002bc70  mov     rcx, r14; Destination
0x18002bc73  call    cs:__imp_memcpy_s
0x18002bc79  mov     rbx, r15
0x18002bc7c  movzx   ecx, word ptr [r14]
0x18002bc80  add     rcx, rbx
0x18002bc83  cmp     rcx, rsi
0x18002bc86  jbe     short loc_18002BC8C
0x18002bc88  xor     al, al
0x18002bc8a  jmp     short loc_18002BC96
0x18002bc8c  mov     [rdi+18h], rbx
0x18002bc90  mov     al, 1
0x18002bc92  mov     [r12], rcx
0x18002bc96  mov     rbx, [rsp+48h+arg_8]
0x18002bc9b  mov     rbp, [rsp+48h+arg_10]
0x18002bca0  add     rsp, 20h
0x18002bca4  pop     r15
0x18002bca6  pop     r14
0x18002bca8  pop     r12
0x18002bcaa  pop     rdi
0x18002bcab  pop     rsi
0x18002bcac  retn
```
