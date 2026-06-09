# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14001b39c`
- end: `0x14001b475`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140019cd8`

## callees

- `0x14001b39c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001b3fc`
- `msvcrt!memcpy_s` at `0x14001b427`
- `msvcrt!memcpy_s` at `0x14001b454`
- `msvcrt!memcpy_s` at `0x14001b3fc`
- `msvcrt!memcpy_s` at `0x14001b427`
- `msvcrt!memcpy_s` at `0x14001b454`

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
0x14001b39c  push    rbx
0x14001b39e  push    rsi
0x14001b39f  push    rdi
0x14001b3a0  push    r12
0x14001b3a2  push    r14
0x14001b3a4  push    r15
0x14001b3a6  sub     rsp, 28h
0x14001b3aa  mov     rsi, rcx
0x14001b3ad  mov     rdi, r8
0x14001b3b0  mov     rcx, [rdx]; Destination
0x14001b3b3  mov     r12, rdx
0x14001b3b6  cmp     byte ptr [rsi+2], 1
0x14001b3ba  jnz     short loc_14001B3DE
0x14001b3bc  lea     rbx, [rcx+2]
0x14001b3c0  cmp     rbx, r8
0x14001b3c3  ja      short loc_14001B443
0x14001b3c5  movzx   eax, word ptr [rsi+4]
0x14001b3c9  lea     r8, [rsp+58h+arg_0]
0x14001b3ce  mov     r9d, 2
0x14001b3d4  mov     [rsp+58h+arg_0], ax
0x14001b3d9  mov     edx, r9d
0x14001b3dc  jmp     short loc_14001B3FC
0x14001b3de  cmp     byte ptr [rsi+2], 2
0x14001b3e2  mov     rbx, rcx
0x14001b3e5  jnz     short loc_14001B402
0x14001b3e7  lea     rbx, [rcx+4]
0x14001b3eb  cmp     rbx, rdi
0x14001b3ee  ja      short loc_14001B443
0x14001b3f0  mov     edx, 4; DestinationSize
0x14001b3f5  lea     r8, [rsi+4]; Source
0x14001b3f9  mov     r9d, edx; SourceSize
0x14001b3fc  call    cs:__imp_memcpy_s
0x14001b402  cmp     word ptr [rsi], 0
0x14001b406  jnz     short loc_14001B432
0x14001b408  lea     r15, [rbx+2]
0x14001b40c  cmp     r15, rdi
0x14001b40f  ja      short loc_14001B443
0x14001b411  lea     r14, [rsi+8]
0x14001b415  mov     rdx, rdi
0x14001b418  sub     rdx, rbx; DestinationSize
0x14001b41b  mov     r8, r14; Source
0x14001b41e  mov     r9d, 2; SourceSize
0x14001b424  mov     rcx, rbx; Destination
0x14001b427  call    cs:__imp_memcpy_s
0x14001b42d  mov     rbx, r15
0x14001b430  jmp     short loc_14001B436
0x14001b432  lea     r14, [rsi+8]
0x14001b436  movzx   r9d, word ptr [r14]; SourceSize
0x14001b43a  lea     rax, [r9+rbx]
0x14001b43e  cmp     rax, rdi
0x14001b441  jbe     short loc_14001B447
0x14001b443  xor     al, al
0x14001b445  jmp     short loc_14001B467
0x14001b447  mov     r8, [rsi+18h]; Source
0x14001b44b  sub     rdi, rbx
0x14001b44e  mov     rdx, rdi; DestinationSize
0x14001b451  mov     rcx, rbx; Destination
0x14001b454  call    cs:__imp_memcpy_s
0x14001b45a  movzx   ecx, word ptr [r14]
0x14001b45e  mov     al, 1
0x14001b460  add     rcx, rbx
0x14001b463  mov     [r12], rcx
0x14001b467  add     rsp, 28h
0x14001b46b  pop     r15
0x14001b46d  pop     r14
0x14001b46f  pop     r12
0x14001b471  pop     rdi
0x14001b472  pop     rsi
0x14001b473  pop     rbx
0x14001b474  retn
```
