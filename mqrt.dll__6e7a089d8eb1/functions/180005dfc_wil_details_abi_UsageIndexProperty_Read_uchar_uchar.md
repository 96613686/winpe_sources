# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005dfc`
- end: `0x180005ee5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042a8`
- `0x180005058`
- `0x18000551c`
- `0x18000635c`
- `0x180006e9c`

## callees

- `0x180005dfc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005e4b`
- `msvcrt!memcpy_s` at `0x180005e80`
- `msvcrt!memcpy_s` at `0x180005eab`
- `msvcrt!memcpy_s` at `0x180005e4b`
- `msvcrt!memcpy_s` at `0x180005e80`
- `msvcrt!memcpy_s` at `0x180005eab`

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
0x180005dfc  mov     rax, rsp
0x180005dff  mov     [rax+10h], rbx
0x180005e03  mov     [rax+18h], rbp
0x180005e07  push    rsi
0x180005e08  push    rdi
0x180005e09  push    r12
0x180005e0b  push    r14
0x180005e0d  push    r15
0x180005e0f  sub     rsp, 20h
0x180005e13  xor     r15d, r15d
0x180005e16  mov     rsi, r8
0x180005e19  cmp     byte ptr [rcx+2], 1
0x180005e1d  mov     r12, rdx
0x180005e20  mov     r8, [rdx]; Source
0x180005e23  mov     rdi, rcx
0x180005e26  jnz     short loc_180005E5B
0x180005e28  lea     rbx, [r8+2]
0x180005e2c  cmp     rbx, rsi
0x180005e2f  ja      loc_180005EC0
0x180005e35  lea     ebp, [r15+2]
0x180005e39  mov     [rcx+10h], r8
0x180005e3d  mov     r9d, ebp; SourceSize
0x180005e40  mov     [rax+8], r15w
0x180005e45  mov     edx, ebp; DestinationSize
0x180005e47  lea     rcx, [rax+8]; Destination
0x180005e4b  call    cs:__imp_memcpy_s
0x180005e51  movzx   eax, [rsp+48h+arg_0]
0x180005e56  mov     [rdi+4], eax
0x180005e59  jmp     short loc_180005E86
0x180005e5b  mov     ebp, 2
0x180005e60  mov     rbx, r8
0x180005e63  cmp     [rcx+2], bpl
0x180005e67  jnz     short loc_180005E86
0x180005e69  lea     rbx, [r8+4]
0x180005e6d  cmp     rbx, rsi
0x180005e70  ja      short loc_180005EC0
0x180005e72  lea     edx, [rbp+2]; DestinationSize
0x180005e75  mov     [rcx+10h], r8
0x180005e79  mov     r9d, edx; SourceSize
0x180005e7c  add     rcx, 4; Destination
0x180005e80  call    cs:__imp_memcpy_s
0x180005e86  movzx   eax, word ptr [rdi]
0x180005e89  lea     r14, [rdi+8]
0x180005e8d  mov     [r14], ax
0x180005e91  test    ax, ax
0x180005e94  jnz     short loc_180005EB4
0x180005e96  lea     r15, [rbx+2]
0x180005e9a  cmp     r15, rsi
0x180005e9d  ja      short loc_180005EC0
0x180005e9f  mov     r9, rbp; SourceSize
0x180005ea2  mov     r8, rbx; Source
0x180005ea5  mov     rdx, rbp; DestinationSize
0x180005ea8  mov     rcx, r14; Destination
0x180005eab  call    cs:__imp_memcpy_s
0x180005eb1  mov     rbx, r15
0x180005eb4  movzx   ecx, word ptr [r14]
0x180005eb8  add     rcx, rbx
0x180005ebb  cmp     rcx, rsi
0x180005ebe  jbe     short loc_180005EC4
0x180005ec0  xor     al, al
0x180005ec2  jmp     short loc_180005ECE
0x180005ec4  mov     [rdi+18h], rbx
0x180005ec8  mov     al, 1
0x180005eca  mov     [r12], rcx
0x180005ece  mov     rbx, [rsp+48h+arg_8]
0x180005ed3  mov     rbp, [rsp+48h+arg_10]
0x180005ed8  add     rsp, 20h
0x180005edc  pop     r15
0x180005ede  pop     r14
0x180005ee0  pop     r12
0x180005ee2  pop     rdi
0x180005ee3  pop     rsi
0x180005ee4  retn
```
