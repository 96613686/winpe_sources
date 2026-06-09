# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007518`
- end: `0x1800075f1`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005dd4`

## callees

- `0x180007518`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007578`
- `msvcrt!memcpy_s` at `0x1800075a3`
- `msvcrt!memcpy_s` at `0x1800075d0`
- `msvcrt!memcpy_s` at `0x180007578`
- `msvcrt!memcpy_s` at `0x1800075a3`
- `msvcrt!memcpy_s` at `0x1800075d0`

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
0x180007518  push    rbx
0x18000751a  push    rsi
0x18000751b  push    rdi
0x18000751c  push    r12
0x18000751e  push    r14
0x180007520  push    r15
0x180007522  sub     rsp, 28h
0x180007526  mov     rsi, rcx
0x180007529  mov     rdi, r8
0x18000752c  mov     rcx, [rdx]; Destination
0x18000752f  mov     r12, rdx
0x180007532  cmp     byte ptr [rsi+2], 1
0x180007536  jnz     short loc_18000755A
0x180007538  lea     rbx, [rcx+2]
0x18000753c  cmp     rbx, r8
0x18000753f  ja      short loc_1800075BF
0x180007541  movzx   eax, word ptr [rsi+4]
0x180007545  lea     r8, [rsp+58h+arg_0]
0x18000754a  mov     r9d, 2
0x180007550  mov     [rsp+58h+arg_0], ax
0x180007555  mov     edx, r9d
0x180007558  jmp     short loc_180007578
0x18000755a  cmp     byte ptr [rsi+2], 2
0x18000755e  mov     rbx, rcx
0x180007561  jnz     short loc_18000757E
0x180007563  lea     rbx, [rcx+4]
0x180007567  cmp     rbx, rdi
0x18000756a  ja      short loc_1800075BF
0x18000756c  mov     edx, 4; DestinationSize
0x180007571  lea     r8, [rsi+4]; Source
0x180007575  mov     r9d, edx; SourceSize
0x180007578  call    cs:__imp_memcpy_s
0x18000757e  cmp     word ptr [rsi], 0
0x180007582  jnz     short loc_1800075AE
0x180007584  lea     r15, [rbx+2]
0x180007588  cmp     r15, rdi
0x18000758b  ja      short loc_1800075BF
0x18000758d  lea     r14, [rsi+8]
0x180007591  mov     rdx, rdi
0x180007594  sub     rdx, rbx; DestinationSize
0x180007597  mov     r8, r14; Source
0x18000759a  mov     r9d, 2; SourceSize
0x1800075a0  mov     rcx, rbx; Destination
0x1800075a3  call    cs:__imp_memcpy_s
0x1800075a9  mov     rbx, r15
0x1800075ac  jmp     short loc_1800075B2
0x1800075ae  lea     r14, [rsi+8]
0x1800075b2  movzx   r9d, word ptr [r14]; SourceSize
0x1800075b6  lea     rax, [r9+rbx]
0x1800075ba  cmp     rax, rdi
0x1800075bd  jbe     short loc_1800075C3
0x1800075bf  xor     al, al
0x1800075c1  jmp     short loc_1800075E3
0x1800075c3  mov     r8, [rsi+18h]; Source
0x1800075c7  sub     rdi, rbx
0x1800075ca  mov     rdx, rdi; DestinationSize
0x1800075cd  mov     rcx, rbx; Destination
0x1800075d0  call    cs:__imp_memcpy_s
0x1800075d6  movzx   ecx, word ptr [r14]
0x1800075da  mov     al, 1
0x1800075dc  add     rcx, rbx
0x1800075df  mov     [r12], rcx
0x1800075e3  add     rsp, 28h
0x1800075e7  pop     r15
0x1800075e9  pop     r14
0x1800075eb  pop     r12
0x1800075ed  pop     rdi
0x1800075ee  pop     rsi
0x1800075ef  pop     rbx
0x1800075f0  retn
```
