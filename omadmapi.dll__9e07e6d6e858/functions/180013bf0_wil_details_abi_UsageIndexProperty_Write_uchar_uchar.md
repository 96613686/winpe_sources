# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180013bf0`
- end: `0x180013cdf`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `239`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010d9c`

## callees

- `0x180003d26`
- `0x18000649c`
- `0x180013bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013c53`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013c53`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x180013bf0  push    rbx
0x180013bf2  push    rbp
0x180013bf3  push    rsi
0x180013bf4  push    rdi
0x180013bf5  push    r14
0x180013bf7  push    r15
0x180013bf9  sub     rsp, 28h
0x180013bfd  mov     al, [rcx+2]
0x180013c00  xor     ebp, ebp
0x180013c02  mov     r9, [rdx]
0x180013c05  mov     rdi, r8
0x180013c08  mov     r15, rdx
0x180013c0b  mov     rsi, rcx
0x180013c0e  cmp     al, 1
0x180013c10  jnz     short loc_180013C2E
0x180013c12  lea     rbx, [r9+2]
0x180013c16  cmp     rbx, r8
0x180013c19  ja      loc_180013CAF
0x180013c1f  test    r9, r9
0x180013c22  jz      short loc_180013C53
0x180013c24  movzx   eax, word ptr [rcx+4]
0x180013c28  mov     [r9], ax
0x180013c2c  jmp     short loc_180013C6F
0x180013c2e  cmp     al, 2
0x180013c30  jnz     short loc_180013C6C
0x180013c32  lea     rbx, [r9+4]
0x180013c36  cmp     rbx, rdi
0x180013c39  ja      short loc_180013CAF
0x180013c3b  test    r9, r9
0x180013c3e  jz      short loc_180013C53
0x180013c40  lea     rax, [rcx+4]
0x180013c44  test    rax, rax
0x180013c47  jz      short loc_180013C50
0x180013c49  mov     eax, [rax]
0x180013c4b  mov     [r9], eax
0x180013c4e  jmp     short loc_180013C6F
0x180013c50  mov     [r9], eax
0x180013c53  call    cs:__imp__o__errno
0x180013c5a  nop     dword ptr [rax+rax+00h]
0x180013c5f  mov     dword ptr [rax], 16h
0x180013c65  call    _invalid_parameter_noinfo
0x180013c6a  jmp     short loc_180013C6F
0x180013c6c  mov     rbx, r9
0x180013c6f  cmp     [rsi], bp
0x180013c72  jnz     short loc_180013C9D
0x180013c74  lea     r14, [rbx+2]
0x180013c78  cmp     r14, rdi
0x180013c7b  ja      short loc_180013CAF
0x180013c7d  lea     rbp, [rsi+8]
0x180013c81  mov     rdx, rdi
0x180013c84  sub     rdx, rbx; DestinationSize
0x180013c87  mov     r8, rbp; Source
0x180013c8a  mov     r9d, 2; SourceSize
0x180013c90  mov     rcx, rbx; Destination
0x180013c93  call    memcpy_s
0x180013c98  mov     rbx, r14
0x180013c9b  jmp     short loc_180013CA1
0x180013c9d  lea     rbp, [rsi+8]
0x180013ca1  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180013ca6  lea     rax, [r9+rbx]
0x180013caa  cmp     rax, rdi
0x180013cad  jbe     short loc_180013CB3
0x180013caf  xor     al, al
0x180013cb1  jmp     short loc_180013CD1
0x180013cb3  mov     r8, [rsi+18h]; Source
0x180013cb7  sub     rdi, rbx
0x180013cba  mov     rdx, rdi; DestinationSize
0x180013cbd  mov     rcx, rbx; Destination
0x180013cc0  call    memcpy_s
0x180013cc5  movzx   ecx, word ptr [rbp+0]
0x180013cc9  mov     al, 1
0x180013ccb  add     rcx, rbx
0x180013cce  mov     [r15], rcx
0x180013cd1  add     rsp, 28h
0x180013cd5  pop     r15
0x180013cd7  pop     r14
0x180013cd9  pop     rdi
0x180013cda  pop     rsi
0x180013cdb  pop     rbp
0x180013cdc  pop     rbx
0x180013cdd  retn
```
