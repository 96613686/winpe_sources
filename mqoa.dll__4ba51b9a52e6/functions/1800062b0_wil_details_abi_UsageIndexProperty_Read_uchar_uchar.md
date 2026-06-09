# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800062b0`
- end: `0x180006399`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000438c`
- `0x180005300`
- `0x1800057b8`
- `0x180006858`
- `0x18000746c`

## callees

- `0x1800062b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800062ff`
- `msvcrt!memcpy_s` at `0x180006334`
- `msvcrt!memcpy_s` at `0x18000635f`
- `msvcrt!memcpy_s` at `0x1800062ff`
- `msvcrt!memcpy_s` at `0x180006334`
- `msvcrt!memcpy_s` at `0x18000635f`

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
0x1800062b0  mov     rax, rsp
0x1800062b3  mov     [rax+10h], rbx
0x1800062b7  mov     [rax+18h], rbp
0x1800062bb  push    rsi
0x1800062bc  push    rdi
0x1800062bd  push    r12
0x1800062bf  push    r14
0x1800062c1  push    r15
0x1800062c3  sub     rsp, 20h
0x1800062c7  xor     r15d, r15d
0x1800062ca  mov     rsi, r8
0x1800062cd  cmp     byte ptr [rcx+2], 1
0x1800062d1  mov     r12, rdx
0x1800062d4  mov     r8, [rdx]; Source
0x1800062d7  mov     rdi, rcx
0x1800062da  jnz     short loc_18000630F
0x1800062dc  lea     rbx, [r8+2]
0x1800062e0  cmp     rbx, rsi
0x1800062e3  ja      loc_180006374
0x1800062e9  lea     ebp, [r15+2]
0x1800062ed  mov     [rcx+10h], r8
0x1800062f1  mov     r9d, ebp; SourceSize
0x1800062f4  mov     [rax+8], r15w
0x1800062f9  mov     edx, ebp; DestinationSize
0x1800062fb  lea     rcx, [rax+8]; Destination
0x1800062ff  call    cs:__imp_memcpy_s
0x180006305  movzx   eax, [rsp+48h+arg_0]
0x18000630a  mov     [rdi+4], eax
0x18000630d  jmp     short loc_18000633A
0x18000630f  mov     ebp, 2
0x180006314  mov     rbx, r8
0x180006317  cmp     [rcx+2], bpl
0x18000631b  jnz     short loc_18000633A
0x18000631d  lea     rbx, [r8+4]
0x180006321  cmp     rbx, rsi
0x180006324  ja      short loc_180006374
0x180006326  lea     edx, [rbp+2]; DestinationSize
0x180006329  mov     [rcx+10h], r8
0x18000632d  mov     r9d, edx; SourceSize
0x180006330  add     rcx, 4; Destination
0x180006334  call    cs:__imp_memcpy_s
0x18000633a  movzx   eax, word ptr [rdi]
0x18000633d  lea     r14, [rdi+8]
0x180006341  mov     [r14], ax
0x180006345  test    ax, ax
0x180006348  jnz     short loc_180006368
0x18000634a  lea     r15, [rbx+2]
0x18000634e  cmp     r15, rsi
0x180006351  ja      short loc_180006374
0x180006353  mov     r9, rbp; SourceSize
0x180006356  mov     r8, rbx; Source
0x180006359  mov     rdx, rbp; DestinationSize
0x18000635c  mov     rcx, r14; Destination
0x18000635f  call    cs:__imp_memcpy_s
0x180006365  mov     rbx, r15
0x180006368  movzx   ecx, word ptr [r14]
0x18000636c  add     rcx, rbx
0x18000636f  cmp     rcx, rsi
0x180006372  jbe     short loc_180006378
0x180006374  xor     al, al
0x180006376  jmp     short loc_180006382
0x180006378  mov     [rdi+18h], rbx
0x18000637c  mov     al, 1
0x18000637e  mov     [r12], rcx
0x180006382  mov     rbx, [rsp+48h+arg_8]
0x180006387  mov     rbp, [rsp+48h+arg_10]
0x18000638c  add     rsp, 20h
0x180006390  pop     r15
0x180006392  pop     r14
0x180006394  pop     r12
0x180006396  pop     rdi
0x180006397  pop     rsi
0x180006398  retn
```
