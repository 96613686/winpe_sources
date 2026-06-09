# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001a48c`
- end: `0x18001a562`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018cc8`

## callees

- `0x18001a48c`
- `0x18001aea4`

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
0x18001a48c  push    rbx
0x18001a48e  push    rsi
0x18001a48f  push    rdi
0x18001a490  push    r12
0x18001a492  push    r14
0x18001a494  push    r15
0x18001a496  sub     rsp, 28h
0x18001a49a  mov     rsi, rcx
0x18001a49d  mov     rdi, r8
0x18001a4a0  mov     rcx, [rdx]; Destination
0x18001a4a3  mov     r12, rdx
0x18001a4a6  cmp     byte ptr [rsi+2], 1
0x18001a4aa  jnz     short loc_18001A4CE
0x18001a4ac  lea     rbx, [rcx+2]
0x18001a4b0  cmp     rbx, r8
0x18001a4b3  ja      short loc_18001A531
0x18001a4b5  movzx   eax, word ptr [rsi+4]
0x18001a4b9  lea     r8, [rsp+58h+arg_0]
0x18001a4be  mov     r9d, 2
0x18001a4c4  mov     [rsp+58h+arg_0], ax
0x18001a4c9  mov     edx, r9d
0x18001a4cc  jmp     short loc_18001A4EC
0x18001a4ce  cmp     byte ptr [rsi+2], 2
0x18001a4d2  mov     rbx, rcx
0x18001a4d5  jnz     short loc_18001A4F1
0x18001a4d7  lea     rbx, [rcx+4]
0x18001a4db  cmp     rbx, rdi
0x18001a4de  ja      short loc_18001A531
0x18001a4e0  mov     edx, 4; DestinationSize
0x18001a4e5  lea     r8, [rsi+4]; Source
0x18001a4e9  mov     r9d, edx; SourceSize
0x18001a4ec  call    memcpy_s
0x18001a4f1  cmp     word ptr [rsi], 0
0x18001a4f5  jnz     short loc_18001A520
0x18001a4f7  lea     r15, [rbx+2]
0x18001a4fb  cmp     r15, rdi
0x18001a4fe  ja      short loc_18001A531
0x18001a500  lea     r14, [rsi+8]
0x18001a504  mov     rdx, rdi
0x18001a507  sub     rdx, rbx; DestinationSize
0x18001a50a  mov     r8, r14; Source
0x18001a50d  mov     r9d, 2; SourceSize
0x18001a513  mov     rcx, rbx; Destination
0x18001a516  call    memcpy_s
0x18001a51b  mov     rbx, r15
0x18001a51e  jmp     short loc_18001A524
0x18001a520  lea     r14, [rsi+8]
0x18001a524  movzx   r9d, word ptr [r14]; SourceSize
0x18001a528  lea     rax, [r9+rbx]
0x18001a52c  cmp     rax, rdi
0x18001a52f  jbe     short loc_18001A535
0x18001a531  xor     al, al
0x18001a533  jmp     short loc_18001A554
0x18001a535  mov     r8, [rsi+18h]; Source
0x18001a539  sub     rdi, rbx
0x18001a53c  mov     rdx, rdi; DestinationSize
0x18001a53f  mov     rcx, rbx; Destination
0x18001a542  call    memcpy_s
0x18001a547  movzx   ecx, word ptr [r14]
0x18001a54b  mov     al, 1
0x18001a54d  add     rcx, rbx
0x18001a550  mov     [r12], rcx
0x18001a554  add     rsp, 28h
0x18001a558  pop     r15
0x18001a55a  pop     r14
0x18001a55c  pop     r12
0x18001a55e  pop     rdi
0x18001a55f  pop     rsi
0x18001a560  pop     rbx
0x18001a561  retn
```
