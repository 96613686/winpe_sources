# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000d864`
- end: `0x14000d93a`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009ae0`

## callees

- `0x14000d864`
- `0x14000eff0`

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
0x14000d864  push    rbx
0x14000d866  push    rsi
0x14000d867  push    rdi
0x14000d868  push    r12
0x14000d86a  push    r14
0x14000d86c  push    r15
0x14000d86e  sub     rsp, 28h
0x14000d872  mov     rsi, rcx
0x14000d875  mov     rdi, r8
0x14000d878  mov     rcx, [rdx]; Destination
0x14000d87b  mov     r12, rdx
0x14000d87e  cmp     byte ptr [rsi+2], 1
0x14000d882  jnz     short loc_14000D8A6
0x14000d884  lea     rbx, [rcx+2]
0x14000d888  cmp     rbx, r8
0x14000d88b  ja      short loc_14000D909
0x14000d88d  movzx   eax, word ptr [rsi+4]
0x14000d891  lea     r8, [rsp+58h+arg_0]
0x14000d896  mov     r9d, 2
0x14000d89c  mov     [rsp+58h+arg_0], ax
0x14000d8a1  mov     edx, r9d
0x14000d8a4  jmp     short loc_14000D8C4
0x14000d8a6  cmp     byte ptr [rsi+2], 2
0x14000d8aa  mov     rbx, rcx
0x14000d8ad  jnz     short loc_14000D8C9
0x14000d8af  lea     rbx, [rcx+4]
0x14000d8b3  cmp     rbx, rdi
0x14000d8b6  ja      short loc_14000D909
0x14000d8b8  mov     edx, 4; DestinationSize
0x14000d8bd  lea     r8, [rsi+4]; Source
0x14000d8c1  mov     r9d, edx; SourceSize
0x14000d8c4  call    memcpy_s
0x14000d8c9  cmp     word ptr [rsi], 0
0x14000d8cd  jnz     short loc_14000D8F8
0x14000d8cf  lea     r15, [rbx+2]
0x14000d8d3  cmp     r15, rdi
0x14000d8d6  ja      short loc_14000D909
0x14000d8d8  lea     r14, [rsi+8]
0x14000d8dc  mov     rdx, rdi
0x14000d8df  sub     rdx, rbx; DestinationSize
0x14000d8e2  mov     r8, r14; Source
0x14000d8e5  mov     r9d, 2; SourceSize
0x14000d8eb  mov     rcx, rbx; Destination
0x14000d8ee  call    memcpy_s
0x14000d8f3  mov     rbx, r15
0x14000d8f6  jmp     short loc_14000D8FC
0x14000d8f8  lea     r14, [rsi+8]
0x14000d8fc  movzx   r9d, word ptr [r14]; SourceSize
0x14000d900  lea     rax, [r9+rbx]
0x14000d904  cmp     rax, rdi
0x14000d907  jbe     short loc_14000D90D
0x14000d909  xor     al, al
0x14000d90b  jmp     short loc_14000D92C
0x14000d90d  mov     r8, [rsi+18h]; Source
0x14000d911  sub     rdi, rbx
0x14000d914  mov     rdx, rdi; DestinationSize
0x14000d917  mov     rcx, rbx; Destination
0x14000d91a  call    memcpy_s
0x14000d91f  movzx   ecx, word ptr [r14]
0x14000d923  mov     al, 1
0x14000d925  add     rcx, rbx
0x14000d928  mov     [r12], rcx
0x14000d92c  add     rsp, 28h
0x14000d930  pop     r15
0x14000d932  pop     r14
0x14000d934  pop     r12
0x14000d936  pop     rdi
0x14000d937  pop     rsi
0x14000d938  pop     rbx
0x14000d939  retn
```
