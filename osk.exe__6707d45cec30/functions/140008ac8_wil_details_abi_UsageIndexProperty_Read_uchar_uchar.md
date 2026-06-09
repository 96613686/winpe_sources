# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140008ac8`
- end: `0x140008bb1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000613c`
- `0x140007188`
- `0x140007738`
- `0x140009108`
- `0x140009d74`

## callees

- `0x140008ac8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008b17`
- `msvcrt!memcpy_s` at `0x140008b4c`
- `msvcrt!memcpy_s` at `0x140008b77`
- `msvcrt!memcpy_s` at `0x140008b17`
- `msvcrt!memcpy_s` at `0x140008b4c`
- `msvcrt!memcpy_s` at `0x140008b77`

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
0x140008ac8  mov     rax, rsp
0x140008acb  mov     [rax+10h], rbx
0x140008acf  mov     [rax+18h], rbp
0x140008ad3  push    rsi
0x140008ad4  push    rdi
0x140008ad5  push    r12
0x140008ad7  push    r14
0x140008ad9  push    r15
0x140008adb  sub     rsp, 20h
0x140008adf  xor     r15d, r15d
0x140008ae2  mov     rsi, r8
0x140008ae5  cmp     byte ptr [rcx+2], 1
0x140008ae9  mov     r12, rdx
0x140008aec  mov     r8, [rdx]; Source
0x140008aef  mov     rdi, rcx
0x140008af2  jnz     short loc_140008B27
0x140008af4  lea     rbx, [r8+2]
0x140008af8  cmp     rbx, rsi
0x140008afb  ja      loc_140008B8C
0x140008b01  lea     ebp, [r15+2]
0x140008b05  mov     [rcx+10h], r8
0x140008b09  mov     r9d, ebp; SourceSize
0x140008b0c  mov     [rax+8], r15w
0x140008b11  mov     edx, ebp; DestinationSize
0x140008b13  lea     rcx, [rax+8]; Destination
0x140008b17  call    cs:__imp_memcpy_s
0x140008b1d  movzx   eax, [rsp+48h+arg_0]
0x140008b22  mov     [rdi+4], eax
0x140008b25  jmp     short loc_140008B52
0x140008b27  mov     ebp, 2
0x140008b2c  mov     rbx, r8
0x140008b2f  cmp     [rcx+2], bpl
0x140008b33  jnz     short loc_140008B52
0x140008b35  lea     rbx, [r8+4]
0x140008b39  cmp     rbx, rsi
0x140008b3c  ja      short loc_140008B8C
0x140008b3e  lea     edx, [rbp+2]; DestinationSize
0x140008b41  mov     [rcx+10h], r8
0x140008b45  mov     r9d, edx; SourceSize
0x140008b48  add     rcx, 4; Destination
0x140008b4c  call    cs:__imp_memcpy_s
0x140008b52  movzx   eax, word ptr [rdi]
0x140008b55  lea     r14, [rdi+8]
0x140008b59  mov     [r14], ax
0x140008b5d  test    ax, ax
0x140008b60  jnz     short loc_140008B80
0x140008b62  lea     r15, [rbx+2]
0x140008b66  cmp     r15, rsi
0x140008b69  ja      short loc_140008B8C
0x140008b6b  mov     r9, rbp; SourceSize
0x140008b6e  mov     r8, rbx; Source
0x140008b71  mov     rdx, rbp; DestinationSize
0x140008b74  mov     rcx, r14; Destination
0x140008b77  call    cs:__imp_memcpy_s
0x140008b7d  mov     rbx, r15
0x140008b80  movzx   ecx, word ptr [r14]
0x140008b84  add     rcx, rbx
0x140008b87  cmp     rcx, rsi
0x140008b8a  jbe     short loc_140008B90
0x140008b8c  xor     al, al
0x140008b8e  jmp     short loc_140008B9A
0x140008b90  mov     [rdi+18h], rbx
0x140008b94  mov     al, 1
0x140008b96  mov     [r12], rcx
0x140008b9a  mov     rbx, [rsp+48h+arg_8]
0x140008b9f  mov     rbp, [rsp+48h+arg_10]
0x140008ba4  add     rsp, 20h
0x140008ba8  pop     r15
0x140008baa  pop     r14
0x140008bac  pop     r12
0x140008bae  pop     rdi
0x140008baf  pop     rsi
0x140008bb0  retn
```
