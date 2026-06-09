# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140009c18`
- end: `0x140009d08`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007684`

## callees

- `0x140009c18`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140009c7c`
- `msvcrt!memcpy_s` at `0x140009cad`
- `msvcrt!memcpy_s` at `0x140009ce0`
- `msvcrt!memcpy_s` at `0x140009c7c`
- `msvcrt!memcpy_s` at `0x140009cad`
- `msvcrt!memcpy_s` at `0x140009ce0`

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
0x140009c18  push    rbx
0x140009c1a  push    rsi
0x140009c1b  push    rdi
0x140009c1c  push    r12
0x140009c1e  push    r14
0x140009c20  push    r15
0x140009c22  sub     rsp, 28h
0x140009c26  mov     rsi, rcx
0x140009c29  mov     rdi, r8
0x140009c2c  mov     rcx, [rdx]; Destination
0x140009c2f  mov     r12, rdx
0x140009c32  cmp     byte ptr [rsi+2], 1
0x140009c36  jnz     short loc_140009C5E
0x140009c38  lea     rbx, [rcx+2]
0x140009c3c  cmp     rbx, r8
0x140009c3f  ja      loc_140009CCF
0x140009c45  movzx   eax, word ptr [rsi+4]
0x140009c49  lea     r8, [rsp+58h+arg_0]
0x140009c4e  mov     r9d, 2
0x140009c54  mov     [rsp+58h+arg_0], ax
0x140009c59  mov     edx, r9d
0x140009c5c  jmp     short loc_140009C7C
0x140009c5e  cmp     byte ptr [rsi+2], 2
0x140009c62  mov     rbx, rcx
0x140009c65  jnz     short loc_140009C88
0x140009c67  lea     rbx, [rcx+4]
0x140009c6b  cmp     rbx, rdi
0x140009c6e  ja      short loc_140009CCF
0x140009c70  mov     edx, 4; DestinationSize
0x140009c75  lea     r8, [rsi+4]; Source
0x140009c79  mov     r9d, edx; SourceSize
0x140009c7c  call    cs:__imp_memcpy_s
0x140009c83  nop     dword ptr [rax+rax+00h]
0x140009c88  cmp     word ptr [rsi], 0
0x140009c8c  jnz     short loc_140009CBE
0x140009c8e  lea     r15, [rbx+2]
0x140009c92  cmp     r15, rdi
0x140009c95  ja      short loc_140009CCF
0x140009c97  lea     r14, [rsi+8]
0x140009c9b  mov     rdx, rdi
0x140009c9e  sub     rdx, rbx; DestinationSize
0x140009ca1  mov     r8, r14; Source
0x140009ca4  mov     r9d, 2; SourceSize
0x140009caa  mov     rcx, rbx; Destination
0x140009cad  call    cs:__imp_memcpy_s
0x140009cb4  nop     dword ptr [rax+rax+00h]
0x140009cb9  mov     rbx, r15
0x140009cbc  jmp     short loc_140009CC2
0x140009cbe  lea     r14, [rsi+8]
0x140009cc2  movzx   r9d, word ptr [r14]; SourceSize
0x140009cc6  lea     rax, [r9+rbx]
0x140009cca  cmp     rax, rdi
0x140009ccd  jbe     short loc_140009CD3
0x140009ccf  xor     al, al
0x140009cd1  jmp     short loc_140009CF9
0x140009cd3  mov     r8, [rsi+18h]; Source
0x140009cd7  sub     rdi, rbx
0x140009cda  mov     rdx, rdi; DestinationSize
0x140009cdd  mov     rcx, rbx; Destination
0x140009ce0  call    cs:__imp_memcpy_s
0x140009ce7  nop     dword ptr [rax+rax+00h]
0x140009cec  movzx   ecx, word ptr [r14]
0x140009cf0  mov     al, 1
0x140009cf2  add     rcx, rbx
0x140009cf5  mov     [r12], rcx
0x140009cf9  add     rsp, 28h
0x140009cfd  pop     r15
0x140009cff  pop     r14
0x140009d01  pop     r12
0x140009d03  pop     rdi
0x140009d04  pop     rsi
0x140009d05  pop     rbx
0x140009d06  retn
```
