# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000987c`
- end: `0x180009955`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003958`

## callees

- `0x18000987c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800098dc`
- `msvcrt!memcpy_s` at `0x180009907`
- `msvcrt!memcpy_s` at `0x180009934`
- `msvcrt!memcpy_s` at `0x1800098dc`
- `msvcrt!memcpy_s` at `0x180009907`
- `msvcrt!memcpy_s` at `0x180009934`

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
0x18000987c  push    rbx
0x18000987e  push    rsi
0x18000987f  push    rdi
0x180009880  push    r12
0x180009882  push    r14
0x180009884  push    r15
0x180009886  sub     rsp, 28h
0x18000988a  mov     rsi, rcx
0x18000988d  mov     rdi, r8
0x180009890  mov     rcx, [rdx]; Destination
0x180009893  mov     r12, rdx
0x180009896  cmp     byte ptr [rsi+2], 1
0x18000989a  jnz     short loc_1800098BE
0x18000989c  lea     rbx, [rcx+2]
0x1800098a0  cmp     rbx, r8
0x1800098a3  ja      short loc_180009923
0x1800098a5  movzx   eax, word ptr [rsi+4]
0x1800098a9  lea     r8, [rsp+58h+arg_0]
0x1800098ae  mov     r9d, 2
0x1800098b4  mov     [rsp+58h+arg_0], ax
0x1800098b9  mov     edx, r9d
0x1800098bc  jmp     short loc_1800098DC
0x1800098be  cmp     byte ptr [rsi+2], 2
0x1800098c2  mov     rbx, rcx
0x1800098c5  jnz     short loc_1800098E2
0x1800098c7  lea     rbx, [rcx+4]
0x1800098cb  cmp     rbx, rdi
0x1800098ce  ja      short loc_180009923
0x1800098d0  mov     edx, 4; DestinationSize
0x1800098d5  lea     r8, [rsi+4]; Source
0x1800098d9  mov     r9d, edx; SourceSize
0x1800098dc  call    cs:__imp_memcpy_s
0x1800098e2  cmp     word ptr [rsi], 0
0x1800098e6  jnz     short loc_180009912
0x1800098e8  lea     r15, [rbx+2]
0x1800098ec  cmp     r15, rdi
0x1800098ef  ja      short loc_180009923
0x1800098f1  lea     r14, [rsi+8]
0x1800098f5  mov     rdx, rdi
0x1800098f8  sub     rdx, rbx; DestinationSize
0x1800098fb  mov     r8, r14; Source
0x1800098fe  mov     r9d, 2; SourceSize
0x180009904  mov     rcx, rbx; Destination
0x180009907  call    cs:__imp_memcpy_s
0x18000990d  mov     rbx, r15
0x180009910  jmp     short loc_180009916
0x180009912  lea     r14, [rsi+8]
0x180009916  movzx   r9d, word ptr [r14]; SourceSize
0x18000991a  lea     rax, [r9+rbx]
0x18000991e  cmp     rax, rdi
0x180009921  jbe     short loc_180009927
0x180009923  xor     al, al
0x180009925  jmp     short loc_180009947
0x180009927  mov     r8, [rsi+18h]; Source
0x18000992b  sub     rdi, rbx
0x18000992e  mov     rdx, rdi; DestinationSize
0x180009931  mov     rcx, rbx; Destination
0x180009934  call    cs:__imp_memcpy_s
0x18000993a  movzx   ecx, word ptr [r14]
0x18000993e  mov     al, 1
0x180009940  add     rcx, rbx
0x180009943  mov     [r12], rcx
0x180009947  add     rsp, 28h
0x18000994b  pop     r15
0x18000994d  pop     r14
0x18000994f  pop     r12
0x180009951  pop     rdi
0x180009952  pop     rsi
0x180009953  pop     rbx
0x180009954  retn
```
