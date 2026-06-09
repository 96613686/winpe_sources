# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a48c`
- end: `0x18000a565`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b24`

## callees

- `0x18000a48c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a4ec`
- `msvcrt!memcpy_s` at `0x18000a517`
- `msvcrt!memcpy_s` at `0x18000a544`
- `msvcrt!memcpy_s` at `0x18000a4ec`
- `msvcrt!memcpy_s` at `0x18000a517`
- `msvcrt!memcpy_s` at `0x18000a544`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x18000a48c  push    rbx
0x18000a48e  push    rsi
0x18000a48f  push    rdi
0x18000a490  push    r12
0x18000a492  push    r14
0x18000a494  push    r15
0x18000a496  sub     rsp, 28h
0x18000a49a  mov     rsi, rcx
0x18000a49d  mov     rdi, r8
0x18000a4a0  mov     rcx, [rdx]; Destination
0x18000a4a3  mov     r12, rdx
0x18000a4a6  cmp     byte ptr [rsi+2], 1
0x18000a4aa  jnz     short loc_18000A4CE
0x18000a4ac  lea     rbx, [rcx+2]
0x18000a4b0  cmp     rbx, r8
0x18000a4b3  ja      short loc_18000A533
0x18000a4b5  movzx   eax, word ptr [rsi+4]
0x18000a4b9  lea     r8, [rsp+58h+arg_0]
0x18000a4be  mov     r9d, 2
0x18000a4c4  mov     [rsp+58h+arg_0], ax
0x18000a4c9  mov     edx, r9d
0x18000a4cc  jmp     short loc_18000A4EC
0x18000a4ce  cmp     byte ptr [rsi+2], 2
0x18000a4d2  mov     rbx, rcx
0x18000a4d5  jnz     short loc_18000A4F2
0x18000a4d7  lea     rbx, [rcx+4]
0x18000a4db  cmp     rbx, rdi
0x18000a4de  ja      short loc_18000A533
0x18000a4e0  mov     edx, 4; DestinationSize
0x18000a4e5  lea     r8, [rsi+4]; Source
0x18000a4e9  mov     r9d, edx; SourceSize
0x18000a4ec  call    cs:__imp_memcpy_s
0x18000a4f2  cmp     word ptr [rsi], 0
0x18000a4f6  jnz     short loc_18000A522
0x18000a4f8  lea     r15, [rbx+2]
0x18000a4fc  cmp     r15, rdi
0x18000a4ff  ja      short loc_18000A533
0x18000a501  lea     r14, [rsi+8]
0x18000a505  mov     rdx, rdi
0x18000a508  sub     rdx, rbx; DestinationSize
0x18000a50b  mov     r8, r14; Source
0x18000a50e  mov     r9d, 2; SourceSize
0x18000a514  mov     rcx, rbx; Destination
0x18000a517  call    cs:__imp_memcpy_s
0x18000a51d  mov     rbx, r15
0x18000a520  jmp     short loc_18000A526
0x18000a522  lea     r14, [rsi+8]
0x18000a526  movzx   r9d, word ptr [r14]; SourceSize
0x18000a52a  lea     rax, [r9+rbx]
0x18000a52e  cmp     rax, rdi
0x18000a531  jbe     short loc_18000A537
0x18000a533  xor     al, al
0x18000a535  jmp     short loc_18000A557
0x18000a537  mov     r8, [rsi+18h]; Source
0x18000a53b  sub     rdi, rbx
0x18000a53e  mov     rdx, rdi; DestinationSize
0x18000a541  mov     rcx, rbx; Destination
0x18000a544  call    cs:__imp_memcpy_s
0x18000a54a  movzx   ecx, word ptr [r14]
0x18000a54e  mov     al, 1
0x18000a550  add     rcx, rbx
0x18000a553  mov     [r12], rcx
0x18000a557  add     rsp, 28h
0x18000a55b  pop     r15
0x18000a55d  pop     r14
0x18000a55f  pop     r12
0x18000a561  pop     rdi
0x18000a562  pop     rsi
0x18000a563  pop     rbx
0x18000a564  retn
```
