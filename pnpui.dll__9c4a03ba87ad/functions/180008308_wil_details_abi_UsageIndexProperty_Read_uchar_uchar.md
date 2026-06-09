# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180008308`
- end: `0x1800083f1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c58`
- `0x180008b24`
- `0x180008eac`

## callees

- `0x180008308`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008357`
- `msvcrt!memcpy_s` at `0x18000838c`
- `msvcrt!memcpy_s` at `0x1800083b7`
- `msvcrt!memcpy_s` at `0x180008357`
- `msvcrt!memcpy_s` at `0x18000838c`
- `msvcrt!memcpy_s` at `0x1800083b7`

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
0x180008308  mov     rax, rsp
0x18000830b  mov     [rax+10h], rbx
0x18000830f  mov     [rax+18h], rbp
0x180008313  push    rsi
0x180008314  push    rdi
0x180008315  push    r12
0x180008317  push    r14
0x180008319  push    r15
0x18000831b  sub     rsp, 20h
0x18000831f  xor     r15d, r15d
0x180008322  mov     rsi, r8
0x180008325  cmp     byte ptr [rcx+2], 1
0x180008329  mov     r12, rdx
0x18000832c  mov     r8, [rdx]; Source
0x18000832f  mov     rdi, rcx
0x180008332  jnz     short loc_180008367
0x180008334  lea     rbx, [r8+2]
0x180008338  cmp     rbx, rsi
0x18000833b  ja      loc_1800083CC
0x180008341  lea     ebp, [r15+2]
0x180008345  mov     [rcx+10h], r8
0x180008349  mov     r9d, ebp; SourceSize
0x18000834c  mov     [rax+8], r15w
0x180008351  mov     edx, ebp; DestinationSize
0x180008353  lea     rcx, [rax+8]; Destination
0x180008357  call    cs:__imp_memcpy_s
0x18000835d  movzx   eax, [rsp+48h+arg_0]
0x180008362  mov     [rdi+4], eax
0x180008365  jmp     short loc_180008392
0x180008367  mov     ebp, 2
0x18000836c  mov     rbx, r8
0x18000836f  cmp     [rcx+2], bpl
0x180008373  jnz     short loc_180008392
0x180008375  lea     rbx, [r8+4]
0x180008379  cmp     rbx, rsi
0x18000837c  ja      short loc_1800083CC
0x18000837e  lea     edx, [rbp+2]; DestinationSize
0x180008381  mov     [rcx+10h], r8
0x180008385  mov     r9d, edx; SourceSize
0x180008388  add     rcx, 4; Destination
0x18000838c  call    cs:__imp_memcpy_s
0x180008392  movzx   eax, word ptr [rdi]
0x180008395  lea     r14, [rdi+8]
0x180008399  mov     [r14], ax
0x18000839d  test    ax, ax
0x1800083a0  jnz     short loc_1800083C0
0x1800083a2  lea     r15, [rbx+2]
0x1800083a6  cmp     r15, rsi
0x1800083a9  ja      short loc_1800083CC
0x1800083ab  mov     r9, rbp; SourceSize
0x1800083ae  mov     r8, rbx; Source
0x1800083b1  mov     rdx, rbp; DestinationSize
0x1800083b4  mov     rcx, r14; Destination
0x1800083b7  call    cs:__imp_memcpy_s
0x1800083bd  mov     rbx, r15
0x1800083c0  movzx   ecx, word ptr [r14]
0x1800083c4  add     rcx, rbx
0x1800083c7  cmp     rcx, rsi
0x1800083ca  jbe     short loc_1800083D0
0x1800083cc  xor     al, al
0x1800083ce  jmp     short loc_1800083DA
0x1800083d0  mov     [rdi+18h], rbx
0x1800083d4  mov     al, 1
0x1800083d6  mov     [r12], rcx
0x1800083da  mov     rbx, [rsp+48h+arg_8]
0x1800083df  mov     rbp, [rsp+48h+arg_10]
0x1800083e4  add     rsp, 20h
0x1800083e8  pop     r15
0x1800083ea  pop     r14
0x1800083ec  pop     r12
0x1800083ee  pop     rdi
0x1800083ef  pop     rsi
0x1800083f0  retn
```
