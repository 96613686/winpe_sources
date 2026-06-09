# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800158cc`
- end: `0x1800159a2`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f2e4`

## callees

- `0x18000f160`
- `0x1800158cc`

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
0x1800158cc  push    rbx
0x1800158ce  push    rsi
0x1800158cf  push    rdi
0x1800158d0  push    r12
0x1800158d2  push    r14
0x1800158d4  push    r15
0x1800158d6  sub     rsp, 28h
0x1800158da  mov     rsi, rcx
0x1800158dd  mov     rdi, r8
0x1800158e0  mov     rcx, [rdx]; Destination
0x1800158e3  mov     r12, rdx
0x1800158e6  cmp     byte ptr [rsi+2], 1
0x1800158ea  jnz     short loc_18001590E
0x1800158ec  lea     rbx, [rcx+2]
0x1800158f0  cmp     rbx, r8
0x1800158f3  ja      short loc_180015971
0x1800158f5  movzx   eax, word ptr [rsi+4]
0x1800158f9  lea     r8, [rsp+58h+arg_0]
0x1800158fe  mov     r9d, 2
0x180015904  mov     [rsp+58h+arg_0], ax
0x180015909  mov     edx, r9d
0x18001590c  jmp     short loc_18001592C
0x18001590e  cmp     byte ptr [rsi+2], 2
0x180015912  mov     rbx, rcx
0x180015915  jnz     short loc_180015931
0x180015917  lea     rbx, [rcx+4]
0x18001591b  cmp     rbx, rdi
0x18001591e  ja      short loc_180015971
0x180015920  mov     edx, 4; DestinationSize
0x180015925  lea     r8, [rsi+4]; Source
0x180015929  mov     r9d, edx; SourceSize
0x18001592c  call    memcpy_s
0x180015931  cmp     word ptr [rsi], 0
0x180015935  jnz     short loc_180015960
0x180015937  lea     r15, [rbx+2]
0x18001593b  cmp     r15, rdi
0x18001593e  ja      short loc_180015971
0x180015940  lea     r14, [rsi+8]
0x180015944  mov     rdx, rdi
0x180015947  sub     rdx, rbx; DestinationSize
0x18001594a  mov     r8, r14; Source
0x18001594d  mov     r9d, 2; SourceSize
0x180015953  mov     rcx, rbx; Destination
0x180015956  call    memcpy_s
0x18001595b  mov     rbx, r15
0x18001595e  jmp     short loc_180015964
0x180015960  lea     r14, [rsi+8]
0x180015964  movzx   r9d, word ptr [r14]; SourceSize
0x180015968  lea     rax, [r9+rbx]
0x18001596c  cmp     rax, rdi
0x18001596f  jbe     short loc_180015975
0x180015971  xor     al, al
0x180015973  jmp     short loc_180015994
0x180015975  mov     r8, [rsi+18h]; Source
0x180015979  sub     rdi, rbx
0x18001597c  mov     rdx, rdi; DestinationSize
0x18001597f  mov     rcx, rbx; Destination
0x180015982  call    memcpy_s
0x180015987  movzx   ecx, word ptr [r14]
0x18001598b  mov     al, 1
0x18001598d  add     rcx, rbx
0x180015990  mov     [r12], rcx
0x180015994  add     rsp, 28h
0x180015998  pop     r15
0x18001599a  pop     r14
0x18001599c  pop     r12
0x18001599e  pop     rdi
0x18001599f  pop     rsi
0x1800159a0  pop     rbx
0x1800159a1  retn
```
