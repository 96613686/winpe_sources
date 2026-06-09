# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18002e14c`
- end: `0x18002e225`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c1e8`

## callees

- `0x18002e14c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002e1ac`
- `msvcrt!memcpy_s` at `0x18002e1d7`
- `msvcrt!memcpy_s` at `0x18002e204`
- `msvcrt!memcpy_s` at `0x18002e1ac`
- `msvcrt!memcpy_s` at `0x18002e1d7`
- `msvcrt!memcpy_s` at `0x18002e204`

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
0x18002e14c  push    rbx
0x18002e14e  push    rsi
0x18002e14f  push    rdi
0x18002e150  push    r12
0x18002e152  push    r14
0x18002e154  push    r15
0x18002e156  sub     rsp, 28h
0x18002e15a  mov     rsi, rcx
0x18002e15d  mov     rdi, r8
0x18002e160  mov     rcx, [rdx]; Destination
0x18002e163  mov     r12, rdx
0x18002e166  cmp     byte ptr [rsi+2], 1
0x18002e16a  jnz     short loc_18002E18E
0x18002e16c  lea     rbx, [rcx+2]
0x18002e170  cmp     rbx, r8
0x18002e173  ja      short loc_18002E1F3
0x18002e175  movzx   eax, word ptr [rsi+4]
0x18002e179  lea     r8, [rsp+58h+arg_0]
0x18002e17e  mov     r9d, 2
0x18002e184  mov     [rsp+58h+arg_0], ax
0x18002e189  mov     edx, r9d
0x18002e18c  jmp     short loc_18002E1AC
0x18002e18e  cmp     byte ptr [rsi+2], 2
0x18002e192  mov     rbx, rcx
0x18002e195  jnz     short loc_18002E1B2
0x18002e197  lea     rbx, [rcx+4]
0x18002e19b  cmp     rbx, rdi
0x18002e19e  ja      short loc_18002E1F3
0x18002e1a0  mov     edx, 4; DestinationSize
0x18002e1a5  lea     r8, [rsi+4]; Source
0x18002e1a9  mov     r9d, edx; SourceSize
0x18002e1ac  call    cs:__imp_memcpy_s
0x18002e1b2  cmp     word ptr [rsi], 0
0x18002e1b6  jnz     short loc_18002E1E2
0x18002e1b8  lea     r15, [rbx+2]
0x18002e1bc  cmp     r15, rdi
0x18002e1bf  ja      short loc_18002E1F3
0x18002e1c1  lea     r14, [rsi+8]
0x18002e1c5  mov     rdx, rdi
0x18002e1c8  sub     rdx, rbx; DestinationSize
0x18002e1cb  mov     r8, r14; Source
0x18002e1ce  mov     r9d, 2; SourceSize
0x18002e1d4  mov     rcx, rbx; Destination
0x18002e1d7  call    cs:__imp_memcpy_s
0x18002e1dd  mov     rbx, r15
0x18002e1e0  jmp     short loc_18002E1E6
0x18002e1e2  lea     r14, [rsi+8]
0x18002e1e6  movzx   r9d, word ptr [r14]; SourceSize
0x18002e1ea  lea     rax, [r9+rbx]
0x18002e1ee  cmp     rax, rdi
0x18002e1f1  jbe     short loc_18002E1F7
0x18002e1f3  xor     al, al
0x18002e1f5  jmp     short loc_18002E217
0x18002e1f7  mov     r8, [rsi+18h]; Source
0x18002e1fb  sub     rdi, rbx
0x18002e1fe  mov     rdx, rdi; DestinationSize
0x18002e201  mov     rcx, rbx; Destination
0x18002e204  call    cs:__imp_memcpy_s
0x18002e20a  movzx   ecx, word ptr [r14]
0x18002e20e  mov     al, 1
0x18002e210  add     rcx, rbx
0x18002e213  mov     [r12], rcx
0x18002e217  add     rsp, 28h
0x18002e21b  pop     r15
0x18002e21d  pop     r14
0x18002e21f  pop     r12
0x18002e221  pop     rdi
0x18002e222  pop     rsi
0x18002e223  pop     rbx
0x18002e224  retn
```
