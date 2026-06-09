# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140019730`
- end: `0x140019819`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140017e10`
- `0x140018b6c`
- `0x140018fec`
- `0x140019cd8`
- `0x14001a9fc`

## callees

- `0x140019730`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001977f`
- `msvcrt!memcpy_s` at `0x1400197b4`
- `msvcrt!memcpy_s` at `0x1400197df`
- `msvcrt!memcpy_s` at `0x14001977f`
- `msvcrt!memcpy_s` at `0x1400197b4`
- `msvcrt!memcpy_s` at `0x1400197df`

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
0x140019730  mov     rax, rsp
0x140019733  mov     [rax+10h], rbx
0x140019737  mov     [rax+18h], rbp
0x14001973b  push    rsi
0x14001973c  push    rdi
0x14001973d  push    r12
0x14001973f  push    r14
0x140019741  push    r15
0x140019743  sub     rsp, 20h
0x140019747  xor     r15d, r15d
0x14001974a  mov     rsi, r8
0x14001974d  cmp     byte ptr [rcx+2], 1
0x140019751  mov     r12, rdx
0x140019754  mov     r8, [rdx]; Source
0x140019757  mov     rdi, rcx
0x14001975a  jnz     short loc_14001978F
0x14001975c  lea     rbx, [r8+2]
0x140019760  cmp     rbx, rsi
0x140019763  ja      loc_1400197F4
0x140019769  lea     ebp, [r15+2]
0x14001976d  mov     [rcx+10h], r8
0x140019771  mov     r9d, ebp; SourceSize
0x140019774  mov     [rax+8], r15w
0x140019779  mov     edx, ebp; DestinationSize
0x14001977b  lea     rcx, [rax+8]; Destination
0x14001977f  call    cs:__imp_memcpy_s
0x140019785  movzx   eax, [rsp+48h+arg_0]
0x14001978a  mov     [rdi+4], eax
0x14001978d  jmp     short loc_1400197BA
0x14001978f  mov     ebp, 2
0x140019794  mov     rbx, r8
0x140019797  cmp     [rcx+2], bpl
0x14001979b  jnz     short loc_1400197BA
0x14001979d  lea     rbx, [r8+4]
0x1400197a1  cmp     rbx, rsi
0x1400197a4  ja      short loc_1400197F4
0x1400197a6  lea     edx, [rbp+2]; DestinationSize
0x1400197a9  mov     [rcx+10h], r8
0x1400197ad  mov     r9d, edx; SourceSize
0x1400197b0  add     rcx, 4; Destination
0x1400197b4  call    cs:__imp_memcpy_s
0x1400197ba  movzx   eax, word ptr [rdi]
0x1400197bd  lea     r14, [rdi+8]
0x1400197c1  mov     [r14], ax
0x1400197c5  test    ax, ax
0x1400197c8  jnz     short loc_1400197E8
0x1400197ca  lea     r15, [rbx+2]
0x1400197ce  cmp     r15, rsi
0x1400197d1  ja      short loc_1400197F4
0x1400197d3  mov     r9, rbp; SourceSize
0x1400197d6  mov     r8, rbx; Source
0x1400197d9  mov     rdx, rbp; DestinationSize
0x1400197dc  mov     rcx, r14; Destination
0x1400197df  call    cs:__imp_memcpy_s
0x1400197e5  mov     rbx, r15
0x1400197e8  movzx   ecx, word ptr [r14]
0x1400197ec  add     rcx, rbx
0x1400197ef  cmp     rcx, rsi
0x1400197f2  jbe     short loc_1400197F8
0x1400197f4  xor     al, al
0x1400197f6  jmp     short loc_140019802
0x1400197f8  mov     [rdi+18h], rbx
0x1400197fc  mov     al, 1
0x1400197fe  mov     [r12], rcx
0x140019802  mov     rbx, [rsp+48h+arg_8]
0x140019807  mov     rbp, [rsp+48h+arg_10]
0x14001980c  add     rsp, 20h
0x140019810  pop     r15
0x140019812  pop     r14
0x140019814  pop     r12
0x140019816  pop     rdi
0x140019817  pop     rsi
0x140019818  retn
```
