# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005b44`
- end: `0x180005c40`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004340`
- `0x1800061ec`
- `0x18000658c`

## callees

- `0x180005b44`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005b93`
- `msvcrt!memcpy_s` at `0x180005bce`
- `msvcrt!memcpy_s` at `0x180005bff`
- `msvcrt!memcpy_s` at `0x180005b93`
- `msvcrt!memcpy_s` at `0x180005bce`
- `msvcrt!memcpy_s` at `0x180005bff`

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
0x180005b44  mov     rax, rsp
0x180005b47  mov     [rax+10h], rbx
0x180005b4b  mov     [rax+18h], rbp
0x180005b4f  push    rsi
0x180005b50  push    rdi
0x180005b51  push    r12
0x180005b53  push    r14
0x180005b55  push    r15
0x180005b57  sub     rsp, 20h
0x180005b5b  xor     r15d, r15d
0x180005b5e  mov     rsi, r8
0x180005b61  cmp     byte ptr [rcx+2], 1
0x180005b65  mov     r12, rdx
0x180005b68  mov     r8, [rdx]; Source
0x180005b6b  mov     rdi, rcx
0x180005b6e  jnz     short loc_180005BA9
0x180005b70  lea     rbx, [r8+2]
0x180005b74  cmp     rbx, rsi
0x180005b77  ja      loc_180005C1A
0x180005b7d  lea     ebp, [r15+2]
0x180005b81  mov     [rcx+10h], r8
0x180005b85  mov     r9d, ebp; SourceSize
0x180005b88  mov     [rax+8], r15w
0x180005b8d  mov     edx, ebp; DestinationSize
0x180005b8f  lea     rcx, [rax+8]; Destination
0x180005b93  call    cs:__imp_memcpy_s
0x180005b9a  nop     dword ptr [rax+rax+00h]
0x180005b9f  movzx   eax, [rsp+48h+arg_0]
0x180005ba4  mov     [rdi+4], eax
0x180005ba7  jmp     short loc_180005BDA
0x180005ba9  mov     ebp, 2
0x180005bae  mov     rbx, r8
0x180005bb1  cmp     [rcx+2], bpl
0x180005bb5  jnz     short loc_180005BDA
0x180005bb7  lea     rbx, [r8+4]
0x180005bbb  cmp     rbx, rsi
0x180005bbe  ja      short loc_180005C1A
0x180005bc0  lea     edx, [rbp+2]; DestinationSize
0x180005bc3  mov     [rcx+10h], r8
0x180005bc7  mov     r9d, edx; SourceSize
0x180005bca  add     rcx, 4; Destination
0x180005bce  call    cs:__imp_memcpy_s
0x180005bd5  nop     dword ptr [rax+rax+00h]
0x180005bda  movzx   eax, word ptr [rdi]
0x180005bdd  lea     r14, [rdi+8]
0x180005be1  mov     [r14], ax
0x180005be5  test    ax, ax
0x180005be8  jnz     short loc_180005C0E
0x180005bea  lea     r15, [rbx+2]
0x180005bee  cmp     r15, rsi
0x180005bf1  ja      short loc_180005C1A
0x180005bf3  mov     r9, rbp; SourceSize
0x180005bf6  mov     r8, rbx; Source
0x180005bf9  mov     rdx, rbp; DestinationSize
0x180005bfc  mov     rcx, r14; Destination
0x180005bff  call    cs:__imp_memcpy_s
0x180005c06  nop     dword ptr [rax+rax+00h]
0x180005c0b  mov     rbx, r15
0x180005c0e  movzx   ecx, word ptr [r14]
0x180005c12  add     rcx, rbx
0x180005c15  cmp     rcx, rsi
0x180005c18  jbe     short loc_180005C1E
0x180005c1a  xor     al, al
0x180005c1c  jmp     short loc_180005C28
0x180005c1e  mov     [rdi+18h], rbx
0x180005c22  mov     al, 1
0x180005c24  mov     [r12], rcx
0x180005c28  mov     rbx, [rsp+48h+arg_8]
0x180005c2d  mov     rbp, [rsp+48h+arg_10]
0x180005c32  add     rsp, 20h
0x180005c36  pop     r15
0x180005c38  pop     r14
0x180005c3a  pop     r12
0x180005c3c  pop     rdi
0x180005c3d  pop     rsi
0x180005c3e  retn
```
