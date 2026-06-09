# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000996c`
- end: `0x180009a42`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ddc`

## callees

- `0x18000996c`
- `0x18000a310`

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
0x18000996c  push    rbx
0x18000996e  push    rsi
0x18000996f  push    rdi
0x180009970  push    r12
0x180009972  push    r14
0x180009974  push    r15
0x180009976  sub     rsp, 28h
0x18000997a  mov     rsi, rcx
0x18000997d  mov     rdi, r8
0x180009980  mov     rcx, [rdx]; Destination
0x180009983  mov     r12, rdx
0x180009986  cmp     byte ptr [rsi+2], 1
0x18000998a  jnz     short loc_1800099AE
0x18000998c  lea     rbx, [rcx+2]
0x180009990  cmp     rbx, r8
0x180009993  ja      short loc_180009A11
0x180009995  movzx   eax, word ptr [rsi+4]
0x180009999  lea     r8, [rsp+58h+arg_0]
0x18000999e  mov     r9d, 2
0x1800099a4  mov     [rsp+58h+arg_0], ax
0x1800099a9  mov     edx, r9d
0x1800099ac  jmp     short loc_1800099CC
0x1800099ae  cmp     byte ptr [rsi+2], 2
0x1800099b2  mov     rbx, rcx
0x1800099b5  jnz     short loc_1800099D1
0x1800099b7  lea     rbx, [rcx+4]
0x1800099bb  cmp     rbx, rdi
0x1800099be  ja      short loc_180009A11
0x1800099c0  mov     edx, 4; DestinationSize
0x1800099c5  lea     r8, [rsi+4]; Source
0x1800099c9  mov     r9d, edx; SourceSize
0x1800099cc  call    memcpy_s
0x1800099d1  cmp     word ptr [rsi], 0
0x1800099d5  jnz     short loc_180009A00
0x1800099d7  lea     r15, [rbx+2]
0x1800099db  cmp     r15, rdi
0x1800099de  ja      short loc_180009A11
0x1800099e0  lea     r14, [rsi+8]
0x1800099e4  mov     rdx, rdi
0x1800099e7  sub     rdx, rbx; DestinationSize
0x1800099ea  mov     r8, r14; Source
0x1800099ed  mov     r9d, 2; SourceSize
0x1800099f3  mov     rcx, rbx; Destination
0x1800099f6  call    memcpy_s
0x1800099fb  mov     rbx, r15
0x1800099fe  jmp     short loc_180009A04
0x180009a00  lea     r14, [rsi+8]
0x180009a04  movzx   r9d, word ptr [r14]; SourceSize
0x180009a08  lea     rax, [r9+rbx]
0x180009a0c  cmp     rax, rdi
0x180009a0f  jbe     short loc_180009A15
0x180009a11  xor     al, al
0x180009a13  jmp     short loc_180009A34
0x180009a15  mov     r8, [rsi+18h]; Source
0x180009a19  sub     rdi, rbx
0x180009a1c  mov     rdx, rdi; DestinationSize
0x180009a1f  mov     rcx, rbx; Destination
0x180009a22  call    memcpy_s
0x180009a27  movzx   ecx, word ptr [r14]
0x180009a2b  mov     al, 1
0x180009a2d  add     rcx, rbx
0x180009a30  mov     [r12], rcx
0x180009a34  add     rsp, 28h
0x180009a38  pop     r15
0x180009a3a  pop     r14
0x180009a3c  pop     r12
0x180009a3e  pop     rdi
0x180009a3f  pop     rsi
0x180009a40  pop     rbx
0x180009a41  retn
```
