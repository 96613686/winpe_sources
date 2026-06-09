# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000b798`
- end: `0x14000b86e`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ee0`

## callees

- `0x14000b798`
- `0x14000bebc`

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
0x14000b798  push    rbx
0x14000b79a  push    rsi
0x14000b79b  push    rdi
0x14000b79c  push    r12
0x14000b79e  push    r14
0x14000b7a0  push    r15
0x14000b7a2  sub     rsp, 28h
0x14000b7a6  mov     rsi, rcx
0x14000b7a9  mov     rdi, r8
0x14000b7ac  mov     rcx, [rdx]; Destination
0x14000b7af  mov     r12, rdx
0x14000b7b2  cmp     byte ptr [rsi+2], 1
0x14000b7b6  jnz     short loc_14000B7DA
0x14000b7b8  lea     rbx, [rcx+2]
0x14000b7bc  cmp     rbx, r8
0x14000b7bf  ja      short loc_14000B83D
0x14000b7c1  movzx   eax, word ptr [rsi+4]
0x14000b7c5  lea     r8, [rsp+58h+arg_0]
0x14000b7ca  mov     r9d, 2
0x14000b7d0  mov     [rsp+58h+arg_0], ax
0x14000b7d5  mov     edx, r9d
0x14000b7d8  jmp     short loc_14000B7F8
0x14000b7da  cmp     byte ptr [rsi+2], 2
0x14000b7de  mov     rbx, rcx
0x14000b7e1  jnz     short loc_14000B7FD
0x14000b7e3  lea     rbx, [rcx+4]
0x14000b7e7  cmp     rbx, rdi
0x14000b7ea  ja      short loc_14000B83D
0x14000b7ec  mov     edx, 4; DestinationSize
0x14000b7f1  lea     r8, [rsi+4]; Source
0x14000b7f5  mov     r9d, edx; SourceSize
0x14000b7f8  call    memcpy_s
0x14000b7fd  cmp     word ptr [rsi], 0
0x14000b801  jnz     short loc_14000B82C
0x14000b803  lea     r15, [rbx+2]
0x14000b807  cmp     r15, rdi
0x14000b80a  ja      short loc_14000B83D
0x14000b80c  lea     r14, [rsi+8]
0x14000b810  mov     rdx, rdi
0x14000b813  sub     rdx, rbx; DestinationSize
0x14000b816  mov     r8, r14; Source
0x14000b819  mov     r9d, 2; SourceSize
0x14000b81f  mov     rcx, rbx; Destination
0x14000b822  call    memcpy_s
0x14000b827  mov     rbx, r15
0x14000b82a  jmp     short loc_14000B830
0x14000b82c  lea     r14, [rsi+8]
0x14000b830  movzx   r9d, word ptr [r14]; SourceSize
0x14000b834  lea     rax, [r9+rbx]
0x14000b838  cmp     rax, rdi
0x14000b83b  jbe     short loc_14000B841
0x14000b83d  xor     al, al
0x14000b83f  jmp     short loc_14000B860
0x14000b841  mov     r8, [rsi+18h]; Source
0x14000b845  sub     rdi, rbx
0x14000b848  mov     rdx, rdi; DestinationSize
0x14000b84b  mov     rcx, rbx; Destination
0x14000b84e  call    memcpy_s
0x14000b853  movzx   ecx, word ptr [r14]
0x14000b857  mov     al, 1
0x14000b859  add     rcx, rbx
0x14000b85c  mov     [r12], rcx
0x14000b860  add     rsp, 28h
0x14000b864  pop     r15
0x14000b866  pop     r14
0x14000b868  pop     r12
0x14000b86a  pop     rdi
0x14000b86b  pop     rsi
0x14000b86c  pop     rbx
0x14000b86d  retn
```
