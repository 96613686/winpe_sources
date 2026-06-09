# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180009d34`
- end: `0x180009e0a`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800035a4`

## callees

- `0x180003404`
- `0x180009d34`

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
0x180009d34  push    rbx
0x180009d36  push    rsi
0x180009d37  push    rdi
0x180009d38  push    r12
0x180009d3a  push    r14
0x180009d3c  push    r15
0x180009d3e  sub     rsp, 28h
0x180009d42  mov     rsi, rcx
0x180009d45  mov     rdi, r8
0x180009d48  mov     rcx, [rdx]; Destination
0x180009d4b  mov     r12, rdx
0x180009d4e  cmp     byte ptr [rsi+2], 1
0x180009d52  jnz     short loc_180009D76
0x180009d54  lea     rbx, [rcx+2]
0x180009d58  cmp     rbx, r8
0x180009d5b  ja      short loc_180009DD9
0x180009d5d  movzx   eax, word ptr [rsi+4]
0x180009d61  lea     r8, [rsp+58h+arg_0]
0x180009d66  mov     r9d, 2
0x180009d6c  mov     [rsp+58h+arg_0], ax
0x180009d71  mov     edx, r9d
0x180009d74  jmp     short loc_180009D94
0x180009d76  cmp     byte ptr [rsi+2], 2
0x180009d7a  mov     rbx, rcx
0x180009d7d  jnz     short loc_180009D99
0x180009d7f  lea     rbx, [rcx+4]
0x180009d83  cmp     rbx, rdi
0x180009d86  ja      short loc_180009DD9
0x180009d88  mov     edx, 4; DestinationSize
0x180009d8d  lea     r8, [rsi+4]; Source
0x180009d91  mov     r9d, edx; SourceSize
0x180009d94  call    memcpy_s
0x180009d99  cmp     word ptr [rsi], 0
0x180009d9d  jnz     short loc_180009DC8
0x180009d9f  lea     r15, [rbx+2]
0x180009da3  cmp     r15, rdi
0x180009da6  ja      short loc_180009DD9
0x180009da8  lea     r14, [rsi+8]
0x180009dac  mov     rdx, rdi
0x180009daf  sub     rdx, rbx; DestinationSize
0x180009db2  mov     r8, r14; Source
0x180009db5  mov     r9d, 2; SourceSize
0x180009dbb  mov     rcx, rbx; Destination
0x180009dbe  call    memcpy_s
0x180009dc3  mov     rbx, r15
0x180009dc6  jmp     short loc_180009DCC
0x180009dc8  lea     r14, [rsi+8]
0x180009dcc  movzx   r9d, word ptr [r14]; SourceSize
0x180009dd0  lea     rax, [r9+rbx]
0x180009dd4  cmp     rax, rdi
0x180009dd7  jbe     short loc_180009DDD
0x180009dd9  xor     al, al
0x180009ddb  jmp     short loc_180009DFC
0x180009ddd  mov     r8, [rsi+18h]; Source
0x180009de1  sub     rdi, rbx
0x180009de4  mov     rdx, rdi; DestinationSize
0x180009de7  mov     rcx, rbx; Destination
0x180009dea  call    memcpy_s
0x180009def  movzx   ecx, word ptr [r14]
0x180009df3  mov     al, 1
0x180009df5  add     rcx, rbx
0x180009df8  mov     [r12], rcx
0x180009dfc  add     rsp, 28h
0x180009e00  pop     r15
0x180009e02  pop     r14
0x180009e04  pop     r12
0x180009e06  pop     rdi
0x180009e07  pop     rsi
0x180009e08  pop     rbx
0x180009e09  retn
```
