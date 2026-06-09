# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a5fc`
- end: `0x18000a6e2`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087e4`
- `0x1800098c8`
- `0x180009d48`
- `0x18000ac18`
- `0x18000b85c`

## callees

- `0x18000a5fc`
- `0x18000e6e8`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x18000a5fc  mov     rax, rsp
0x18000a5ff  mov     [rax+10h], rbx
0x18000a603  mov     [rax+18h], rbp
0x18000a607  push    rsi
0x18000a608  push    rdi
0x18000a609  push    r12
0x18000a60b  push    r14
0x18000a60d  push    r15
0x18000a60f  sub     rsp, 20h
0x18000a613  xor     r15d, r15d
0x18000a616  mov     rsi, r8
0x18000a619  cmp     byte ptr [rcx+2], 1
0x18000a61d  mov     r12, rdx
0x18000a620  mov     r8, [rdx]; Source
0x18000a623  mov     rdi, rcx
0x18000a626  jnz     short loc_18000A65A
0x18000a628  lea     rbx, [r8+2]
0x18000a62c  cmp     rbx, rsi
0x18000a62f  ja      loc_18000A6BD
0x18000a635  lea     ebp, [r15+2]
0x18000a639  mov     [rcx+10h], r8
0x18000a63d  mov     r9d, ebp; SourceSize
0x18000a640  mov     [rax+8], r15w
0x18000a645  mov     edx, ebp; DestinationSize
0x18000a647  lea     rcx, [rax+8]; Destination
0x18000a64b  call    memcpy_s
0x18000a650  movzx   eax, [rsp+48h+arg_0]
0x18000a655  mov     [rdi+4], eax
0x18000a658  jmp     short loc_18000A684
0x18000a65a  mov     ebp, 2
0x18000a65f  mov     rbx, r8
0x18000a662  cmp     [rcx+2], bpl
0x18000a666  jnz     short loc_18000A684
0x18000a668  lea     rbx, [r8+4]
0x18000a66c  cmp     rbx, rsi
0x18000a66f  ja      short loc_18000A6BD
0x18000a671  lea     edx, [rbp+2]; DestinationSize
0x18000a674  mov     [rcx+10h], r8
0x18000a678  mov     r9d, edx; SourceSize
0x18000a67b  add     rcx, 4; Destination
0x18000a67f  call    memcpy_s
0x18000a684  movzx   eax, word ptr [rdi]
0x18000a687  lea     r14, [rdi+8]
0x18000a68b  mov     [r14], ax
0x18000a68f  test    ax, ax
0x18000a692  jnz     short loc_18000A6B1
0x18000a694  lea     r15, [rbx+2]
0x18000a698  cmp     r15, rsi
0x18000a69b  ja      short loc_18000A6BD
0x18000a69d  mov     r9, rbp; SourceSize
0x18000a6a0  mov     r8, rbx; Source
0x18000a6a3  mov     rdx, rbp; DestinationSize
0x18000a6a6  mov     rcx, r14; Destination
0x18000a6a9  call    memcpy_s
0x18000a6ae  mov     rbx, r15
0x18000a6b1  movzx   ecx, word ptr [r14]
0x18000a6b5  add     rcx, rbx
0x18000a6b8  cmp     rcx, rsi
0x18000a6bb  jbe     short loc_18000A6C1
0x18000a6bd  xor     al, al
0x18000a6bf  jmp     short loc_18000A6CB
0x18000a6c1  mov     [rdi+18h], rbx
0x18000a6c5  mov     al, 1
0x18000a6c7  mov     [r12], rcx
0x18000a6cb  mov     rbx, [rsp+48h+arg_8]
0x18000a6d0  mov     rbp, [rsp+48h+arg_10]
0x18000a6d5  add     rsp, 20h
0x18000a6d9  pop     r15
0x18000a6db  pop     r14
0x18000a6dd  pop     r12
0x18000a6df  pop     rdi
0x18000a6e0  pop     rsi
0x18000a6e1  retn
```
