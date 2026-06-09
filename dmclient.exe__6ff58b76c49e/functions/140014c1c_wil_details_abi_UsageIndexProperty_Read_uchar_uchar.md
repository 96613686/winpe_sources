# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140014c1c`
- end: `0x140014d05`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400138b8`
- `0x1400151e4`
- `0x14001556c`

## callees

- `0x140014c1c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140014c6b`
- `msvcrt!memcpy_s` at `0x140014ca0`
- `msvcrt!memcpy_s` at `0x140014ccb`
- `msvcrt!memcpy_s` at `0x140014c6b`
- `msvcrt!memcpy_s` at `0x140014ca0`
- `msvcrt!memcpy_s` at `0x140014ccb`

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
0x140014c1c  mov     rax, rsp
0x140014c1f  mov     [rax+10h], rbx
0x140014c23  mov     [rax+18h], rbp
0x140014c27  push    rsi
0x140014c28  push    rdi
0x140014c29  push    r12
0x140014c2b  push    r14
0x140014c2d  push    r15
0x140014c2f  sub     rsp, 20h
0x140014c33  xor     r15d, r15d
0x140014c36  mov     rsi, r8
0x140014c39  cmp     byte ptr [rcx+2], 1
0x140014c3d  mov     r12, rdx
0x140014c40  mov     r8, [rdx]; Source
0x140014c43  mov     rdi, rcx
0x140014c46  jnz     short loc_140014C7B
0x140014c48  lea     rbx, [r8+2]
0x140014c4c  cmp     rbx, rsi
0x140014c4f  ja      loc_140014CE0
0x140014c55  lea     ebp, [r15+2]
0x140014c59  mov     [rcx+10h], r8
0x140014c5d  mov     r9d, ebp; SourceSize
0x140014c60  mov     [rax+8], r15w
0x140014c65  mov     edx, ebp; DestinationSize
0x140014c67  lea     rcx, [rax+8]; Destination
0x140014c6b  call    cs:__imp_memcpy_s
0x140014c71  movzx   eax, [rsp+48h+arg_0]
0x140014c76  mov     [rdi+4], eax
0x140014c79  jmp     short loc_140014CA6
0x140014c7b  mov     ebp, 2
0x140014c80  mov     rbx, r8
0x140014c83  cmp     [rcx+2], bpl
0x140014c87  jnz     short loc_140014CA6
0x140014c89  lea     rbx, [r8+4]
0x140014c8d  cmp     rbx, rsi
0x140014c90  ja      short loc_140014CE0
0x140014c92  lea     edx, [rbp+2]; DestinationSize
0x140014c95  mov     [rcx+10h], r8
0x140014c99  mov     r9d, edx; SourceSize
0x140014c9c  add     rcx, 4; Destination
0x140014ca0  call    cs:__imp_memcpy_s
0x140014ca6  movzx   eax, word ptr [rdi]
0x140014ca9  lea     r14, [rdi+8]
0x140014cad  mov     [r14], ax
0x140014cb1  test    ax, ax
0x140014cb4  jnz     short loc_140014CD4
0x140014cb6  lea     r15, [rbx+2]
0x140014cba  cmp     r15, rsi
0x140014cbd  ja      short loc_140014CE0
0x140014cbf  mov     r9, rbp; SourceSize
0x140014cc2  mov     r8, rbx; Source
0x140014cc5  mov     rdx, rbp; DestinationSize
0x140014cc8  mov     rcx, r14; Destination
0x140014ccb  call    cs:__imp_memcpy_s
0x140014cd1  mov     rbx, r15
0x140014cd4  movzx   ecx, word ptr [r14]
0x140014cd8  add     rcx, rbx
0x140014cdb  cmp     rcx, rsi
0x140014cde  jbe     short loc_140014CE4
0x140014ce0  xor     al, al
0x140014ce2  jmp     short loc_140014CEE
0x140014ce4  mov     [rdi+18h], rbx
0x140014ce8  mov     al, 1
0x140014cea  mov     [r12], rcx
0x140014cee  mov     rbx, [rsp+48h+arg_8]
0x140014cf3  mov     rbp, [rsp+48h+arg_10]
0x140014cf8  add     rsp, 20h
0x140014cfc  pop     r15
0x140014cfe  pop     r14
0x140014d00  pop     r12
0x140014d02  pop     rdi
0x140014d03  pop     rsi
0x140014d04  retn
```
