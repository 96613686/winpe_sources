# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180014fbc`
- end: `0x180015095`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e338`

## callees

- `0x180014fbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001501c`
- `msvcrt!memcpy_s` at `0x180015047`
- `msvcrt!memcpy_s` at `0x180015074`
- `msvcrt!memcpy_s` at `0x18001501c`
- `msvcrt!memcpy_s` at `0x180015047`
- `msvcrt!memcpy_s` at `0x180015074`

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
0x180014fbc  push    rbx
0x180014fbe  push    rsi
0x180014fbf  push    rdi
0x180014fc0  push    r12
0x180014fc2  push    r14
0x180014fc4  push    r15
0x180014fc6  sub     rsp, 28h
0x180014fca  mov     rsi, rcx
0x180014fcd  mov     rdi, r8
0x180014fd0  mov     rcx, [rdx]; Destination
0x180014fd3  mov     r12, rdx
0x180014fd6  cmp     byte ptr [rsi+2], 1
0x180014fda  jnz     short loc_180014FFE
0x180014fdc  lea     rbx, [rcx+2]
0x180014fe0  cmp     rbx, r8
0x180014fe3  ja      short loc_180015063
0x180014fe5  movzx   eax, word ptr [rsi+4]
0x180014fe9  lea     r8, [rsp+58h+arg_0]
0x180014fee  mov     r9d, 2
0x180014ff4  mov     [rsp+58h+arg_0], ax
0x180014ff9  mov     edx, r9d
0x180014ffc  jmp     short loc_18001501C
0x180014ffe  cmp     byte ptr [rsi+2], 2
0x180015002  mov     rbx, rcx
0x180015005  jnz     short loc_180015022
0x180015007  lea     rbx, [rcx+4]
0x18001500b  cmp     rbx, rdi
0x18001500e  ja      short loc_180015063
0x180015010  mov     edx, 4; DestinationSize
0x180015015  lea     r8, [rsi+4]; Source
0x180015019  mov     r9d, edx; SourceSize
0x18001501c  call    cs:__imp_memcpy_s
0x180015022  cmp     word ptr [rsi], 0
0x180015026  jnz     short loc_180015052
0x180015028  lea     r15, [rbx+2]
0x18001502c  cmp     r15, rdi
0x18001502f  ja      short loc_180015063
0x180015031  lea     r14, [rsi+8]
0x180015035  mov     rdx, rdi
0x180015038  sub     rdx, rbx; DestinationSize
0x18001503b  mov     r8, r14; Source
0x18001503e  mov     r9d, 2; SourceSize
0x180015044  mov     rcx, rbx; Destination
0x180015047  call    cs:__imp_memcpy_s
0x18001504d  mov     rbx, r15
0x180015050  jmp     short loc_180015056
0x180015052  lea     r14, [rsi+8]
0x180015056  movzx   r9d, word ptr [r14]; SourceSize
0x18001505a  lea     rax, [r9+rbx]
0x18001505e  cmp     rax, rdi
0x180015061  jbe     short loc_180015067
0x180015063  xor     al, al
0x180015065  jmp     short loc_180015087
0x180015067  mov     r8, [rsi+18h]; Source
0x18001506b  sub     rdi, rbx
0x18001506e  mov     rdx, rdi; DestinationSize
0x180015071  mov     rcx, rbx; Destination
0x180015074  call    cs:__imp_memcpy_s
0x18001507a  movzx   ecx, word ptr [r14]
0x18001507e  mov     al, 1
0x180015080  add     rcx, rbx
0x180015083  mov     [r12], rcx
0x180015087  add     rsp, 28h
0x18001508b  pop     r15
0x18001508d  pop     r14
0x18001508f  pop     r12
0x180015091  pop     rdi
0x180015092  pop     rsi
0x180015093  pop     rbx
0x180015094  retn
```
