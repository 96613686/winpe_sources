# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180026278`
- end: `0x180026381`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `265`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800240cc`

## callees

- `0x180026278`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800262e6`
- `msvcrt!memcpy_s` at `0x18002631a`
- `msvcrt!memcpy_s` at `0x18002634d`
- `msvcrt!memcpy_s` at `0x1800262e6`
- `msvcrt!memcpy_s` at `0x18002631a`
- `msvcrt!memcpy_s` at `0x18002634d`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v4; // rbx
  char *v7; // r14
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v4, v10, v8, v9);
  v4 = v7;
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v4 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v4, a3 - v4, (char *)this + 8, 2u);
      v4 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v4[v12] > a3 )
    return 0;
  memcpy_s(v4, a3 - v4, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v4[*v11];
  return result;
}

```

## disassembly

```asm
0x180026278  mov     r11, rsp
0x18002627b  mov     [r11+10h], rbx
0x18002627f  mov     [r11+18h], rsi
0x180026283  mov     [r11+20h], rdi
0x180026287  push    r12
0x180026289  push    r14
0x18002628b  push    r15
0x18002628d  sub     rsp, 20h
0x180026291  cmp     byte ptr [rcx+2], 1
0x180026295  mov     rdi, r8
0x180026298  mov     rbx, [rdx]
0x18002629b  mov     r12, rdx
0x18002629e  mov     rsi, rcx
0x1800262a1  jnz     short loc_1800262C8
0x1800262a3  lea     r14, [rbx+2]
0x1800262a7  cmp     r14, r8
0x1800262aa  ja      loc_18002633C
0x1800262b0  movzx   eax, word ptr [rcx+4]
0x1800262b4  lea     r8, [r11+8]
0x1800262b8  mov     r9d, 2
0x1800262be  mov     [rsp+38h+arg_0], ax
0x1800262c3  mov     edx, r9d
0x1800262c6  jmp     short loc_1800262E3
0x1800262c8  cmp     byte ptr [rcx+2], 2
0x1800262cc  jnz     short loc_1800262F5
0x1800262ce  lea     r14, [rbx+4]
0x1800262d2  cmp     r14, rdi
0x1800262d5  ja      short loc_18002633C
0x1800262d7  mov     edx, 4; DestinationSize
0x1800262dc  lea     r8, [rcx+4]; Source
0x1800262e0  mov     r9d, edx; SourceSize
0x1800262e3  mov     rcx, rbx; Destination
0x1800262e6  call    cs:__imp_memcpy_s
0x1800262ed  nop     dword ptr [rax+rax+00h]
0x1800262f2  mov     rbx, r14
0x1800262f5  cmp     word ptr [rsi], 0
0x1800262f9  jnz     short loc_18002632B
0x1800262fb  lea     r15, [rbx+2]
0x1800262ff  cmp     r15, rdi
0x180026302  ja      short loc_18002633C
0x180026304  lea     r14, [rsi+8]
0x180026308  mov     rdx, rdi
0x18002630b  sub     rdx, rbx; DestinationSize
0x18002630e  mov     r8, r14; Source
0x180026311  mov     r9d, 2; SourceSize
0x180026317  mov     rcx, rbx; Destination
0x18002631a  call    cs:__imp_memcpy_s
0x180026321  nop     dword ptr [rax+rax+00h]
0x180026326  mov     rbx, r15
0x180026329  jmp     short loc_18002632F
0x18002632b  lea     r14, [rsi+8]
0x18002632f  movzx   r9d, word ptr [r14]; SourceSize
0x180026333  lea     rax, [r9+rbx]
0x180026337  cmp     rax, rdi
0x18002633a  jbe     short loc_180026340
0x18002633c  xor     al, al
0x18002633e  jmp     short loc_180026366
0x180026340  mov     r8, [rsi+18h]; Source
0x180026344  sub     rdi, rbx
0x180026347  mov     rdx, rdi; DestinationSize
0x18002634a  mov     rcx, rbx; Destination
0x18002634d  call    cs:__imp_memcpy_s
0x180026354  nop     dword ptr [rax+rax+00h]
0x180026359  movzx   ecx, word ptr [r14]
0x18002635d  mov     al, 1
0x18002635f  add     rcx, rbx
0x180026362  mov     [r12], rcx
0x180026366  mov     rbx, [rsp+38h+arg_8]
0x18002636b  mov     rsi, [rsp+38h+arg_10]
0x180026370  mov     rdi, [rsp+38h+arg_18]
0x180026375  add     rsp, 20h
0x180026379  pop     r15
0x18002637b  pop     r14
0x18002637d  pop     r12
0x18002637f  retn
```
