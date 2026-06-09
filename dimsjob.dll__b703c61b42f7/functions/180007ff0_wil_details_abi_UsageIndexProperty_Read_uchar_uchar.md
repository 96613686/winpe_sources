# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180007ff0`
- end: `0x1800080d9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003958`
- `0x180006250`
- `0x180007050`
- `0x1800074e4`
- `0x180008dfc`

## callees

- `0x180007ff0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000803f`
- `msvcrt!memcpy_s` at `0x180008074`
- `msvcrt!memcpy_s` at `0x18000809f`
- `msvcrt!memcpy_s` at `0x18000803f`
- `msvcrt!memcpy_s` at `0x180008074`
- `msvcrt!memcpy_s` at `0x18000809f`

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
0x180007ff0  mov     rax, rsp
0x180007ff3  mov     [rax+10h], rbx
0x180007ff7  mov     [rax+18h], rbp
0x180007ffb  push    rsi
0x180007ffc  push    rdi
0x180007ffd  push    r12
0x180007fff  push    r14
0x180008001  push    r15
0x180008003  sub     rsp, 20h
0x180008007  xor     r15d, r15d
0x18000800a  mov     rsi, r8
0x18000800d  cmp     byte ptr [rcx+2], 1
0x180008011  mov     r12, rdx
0x180008014  mov     r8, [rdx]; Source
0x180008017  mov     rdi, rcx
0x18000801a  jnz     short loc_18000804F
0x18000801c  lea     rbx, [r8+2]
0x180008020  cmp     rbx, rsi
0x180008023  ja      loc_1800080B4
0x180008029  lea     ebp, [r15+2]
0x18000802d  mov     [rcx+10h], r8
0x180008031  mov     r9d, ebp; SourceSize
0x180008034  mov     [rax+8], r15w
0x180008039  mov     edx, ebp; DestinationSize
0x18000803b  lea     rcx, [rax+8]; Destination
0x18000803f  call    cs:__imp_memcpy_s
0x180008045  movzx   eax, [rsp+48h+arg_0]
0x18000804a  mov     [rdi+4], eax
0x18000804d  jmp     short loc_18000807A
0x18000804f  mov     ebp, 2
0x180008054  mov     rbx, r8
0x180008057  cmp     [rcx+2], bpl
0x18000805b  jnz     short loc_18000807A
0x18000805d  lea     rbx, [r8+4]
0x180008061  cmp     rbx, rsi
0x180008064  ja      short loc_1800080B4
0x180008066  lea     edx, [rbp+2]; DestinationSize
0x180008069  mov     [rcx+10h], r8
0x18000806d  mov     r9d, edx; SourceSize
0x180008070  add     rcx, 4; Destination
0x180008074  call    cs:__imp_memcpy_s
0x18000807a  movzx   eax, word ptr [rdi]
0x18000807d  lea     r14, [rdi+8]
0x180008081  mov     [r14], ax
0x180008085  test    ax, ax
0x180008088  jnz     short loc_1800080A8
0x18000808a  lea     r15, [rbx+2]
0x18000808e  cmp     r15, rsi
0x180008091  ja      short loc_1800080B4
0x180008093  mov     r9, rbp; SourceSize
0x180008096  mov     r8, rbx; Source
0x180008099  mov     rdx, rbp; DestinationSize
0x18000809c  mov     rcx, r14; Destination
0x18000809f  call    cs:__imp_memcpy_s
0x1800080a5  mov     rbx, r15
0x1800080a8  movzx   ecx, word ptr [r14]
0x1800080ac  add     rcx, rbx
0x1800080af  cmp     rcx, rsi
0x1800080b2  jbe     short loc_1800080B8
0x1800080b4  xor     al, al
0x1800080b6  jmp     short loc_1800080C2
0x1800080b8  mov     [rdi+18h], rbx
0x1800080bc  mov     al, 1
0x1800080be  mov     [r12], rcx
0x1800080c2  mov     rbx, [rsp+48h+arg_8]
0x1800080c7  mov     rbp, [rsp+48h+arg_10]
0x1800080cc  add     rsp, 20h
0x1800080d0  pop     r15
0x1800080d2  pop     r14
0x1800080d4  pop     r12
0x1800080d6  pop     rdi
0x1800080d7  pop     rsi
0x1800080d8  retn
```
