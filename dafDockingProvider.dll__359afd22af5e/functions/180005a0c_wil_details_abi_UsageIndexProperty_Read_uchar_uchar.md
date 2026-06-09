# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005a0c`
- end: `0x180005af5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000439c`
- `0x180006048`
- `0x1800063d0`

## callees

- `0x180005a0c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005a5b`
- `msvcrt!memcpy_s` at `0x180005a90`
- `msvcrt!memcpy_s` at `0x180005abb`
- `msvcrt!memcpy_s` at `0x180005a5b`
- `msvcrt!memcpy_s` at `0x180005a90`
- `msvcrt!memcpy_s` at `0x180005abb`

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
0x180005a0c  mov     rax, rsp
0x180005a0f  mov     [rax+10h], rbx
0x180005a13  mov     [rax+18h], rbp
0x180005a17  push    rsi
0x180005a18  push    rdi
0x180005a19  push    r12
0x180005a1b  push    r14
0x180005a1d  push    r15
0x180005a1f  sub     rsp, 20h
0x180005a23  xor     r15d, r15d
0x180005a26  mov     rsi, r8
0x180005a29  cmp     byte ptr [rcx+2], 1
0x180005a2d  mov     r12, rdx
0x180005a30  mov     r8, [rdx]; Source
0x180005a33  mov     rdi, rcx
0x180005a36  jnz     short loc_180005A6B
0x180005a38  lea     rbx, [r8+2]
0x180005a3c  cmp     rbx, rsi
0x180005a3f  ja      loc_180005AD0
0x180005a45  lea     ebp, [r15+2]
0x180005a49  mov     [rcx+10h], r8
0x180005a4d  mov     r9d, ebp; SourceSize
0x180005a50  mov     [rax+8], r15w
0x180005a55  mov     edx, ebp; DestinationSize
0x180005a57  lea     rcx, [rax+8]; Destination
0x180005a5b  call    cs:__imp_memcpy_s
0x180005a61  movzx   eax, [rsp+48h+arg_0]
0x180005a66  mov     [rdi+4], eax
0x180005a69  jmp     short loc_180005A96
0x180005a6b  mov     ebp, 2
0x180005a70  mov     rbx, r8
0x180005a73  cmp     [rcx+2], bpl
0x180005a77  jnz     short loc_180005A96
0x180005a79  lea     rbx, [r8+4]
0x180005a7d  cmp     rbx, rsi
0x180005a80  ja      short loc_180005AD0
0x180005a82  lea     edx, [rbp+2]; DestinationSize
0x180005a85  mov     [rcx+10h], r8
0x180005a89  mov     r9d, edx; SourceSize
0x180005a8c  add     rcx, 4; Destination
0x180005a90  call    cs:__imp_memcpy_s
0x180005a96  movzx   eax, word ptr [rdi]
0x180005a99  lea     r14, [rdi+8]
0x180005a9d  mov     [r14], ax
0x180005aa1  test    ax, ax
0x180005aa4  jnz     short loc_180005AC4
0x180005aa6  lea     r15, [rbx+2]
0x180005aaa  cmp     r15, rsi
0x180005aad  ja      short loc_180005AD0
0x180005aaf  mov     r9, rbp; SourceSize
0x180005ab2  mov     r8, rbx; Source
0x180005ab5  mov     rdx, rbp; DestinationSize
0x180005ab8  mov     rcx, r14; Destination
0x180005abb  call    cs:__imp_memcpy_s
0x180005ac1  mov     rbx, r15
0x180005ac4  movzx   ecx, word ptr [r14]
0x180005ac8  add     rcx, rbx
0x180005acb  cmp     rcx, rsi
0x180005ace  jbe     short loc_180005AD4
0x180005ad0  xor     al, al
0x180005ad2  jmp     short loc_180005ADE
0x180005ad4  mov     [rdi+18h], rbx
0x180005ad8  mov     al, 1
0x180005ada  mov     [r12], rcx
0x180005ade  mov     rbx, [rsp+48h+arg_8]
0x180005ae3  mov     rbp, [rsp+48h+arg_10]
0x180005ae8  add     rsp, 20h
0x180005aec  pop     r15
0x180005aee  pop     r14
0x180005af0  pop     r12
0x180005af2  pop     rdi
0x180005af3  pop     rsi
0x180005af4  retn
```
