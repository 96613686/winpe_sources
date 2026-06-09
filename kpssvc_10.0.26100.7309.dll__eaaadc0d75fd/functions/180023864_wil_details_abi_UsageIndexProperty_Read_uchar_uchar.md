# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180023864`
- end: `0x18002395d`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `249`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d2fc`
- `0x1800240cc`
- `0x180024484`

## callees

- `0x180023864`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800238b4`
- `msvcrt!memcpy_s` at `0x1800238ec`
- `msvcrt!memcpy_s` at `0x18002391d`
- `msvcrt!memcpy_s` at `0x1800238b4`
- `msvcrt!memcpy_s` at `0x1800238ec`
- `msvcrt!memcpy_s` at `0x18002391d`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbp
  __int16 v8; // ax
  char *v9; // rbp
  unsigned __int8 *v10; // rcx
  bool result; // al
  unsigned __int16 v12; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v12 = 0;
    memcpy_s(&v12, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v12;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    memcpy_s((char *)this + 4, 4u, v5, 4u);
  }
  v5 = v7;
LABEL_8:
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_11;
  v9 = v5 + 2;
  if ( v5 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v5, 2u);
  v5 = v9;
LABEL_11:
  v10 = (unsigned __int8 *)&v5[*((unsigned __int16 *)this + 4)];
  if ( v10 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v5;
  result = 1;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x180023864  mov     rax, rsp
0x180023867  mov     [rax+10h], rbx
0x18002386b  mov     [rax+18h], rbp
0x18002386f  push    rsi
0x180023870  push    rdi
0x180023871  push    r12
0x180023873  push    r14
0x180023875  push    r15
0x180023877  sub     rsp, 20h
0x18002387b  xor     r12d, r12d
0x18002387e  mov     rdi, r8
0x180023881  cmp     byte ptr [rcx+2], 1
0x180023885  mov     r15, rdx
0x180023888  mov     r8, [rdx]; Source
0x18002388b  mov     rbx, rcx
0x18002388e  jnz     short loc_1800238CA
0x180023890  lea     rbp, [r8+2]
0x180023894  cmp     rbp, rdi
0x180023897  ja      loc_180023938
0x18002389d  lea     esi, [r12+2]
0x1800238a2  mov     [rcx+10h], r8
0x1800238a6  mov     r9d, esi; SourceSize
0x1800238a9  mov     [rax+8], r12w
0x1800238ae  mov     edx, esi; DestinationSize
0x1800238b0  lea     rcx, [rax+8]; Destination
0x1800238b4  call    cs:__imp_memcpy_s
0x1800238bb  nop     dword ptr [rax+rax+00h]
0x1800238c0  movzx   eax, [rsp+48h+arg_0]
0x1800238c5  mov     [rbx+4], eax
0x1800238c8  jmp     short loc_1800238F8
0x1800238ca  mov     esi, 2
0x1800238cf  cmp     [rcx+2], sil
0x1800238d3  jnz     short loc_1800238FB
0x1800238d5  lea     rbp, [r8+4]
0x1800238d9  cmp     rbp, rdi
0x1800238dc  ja      short loc_180023938
0x1800238de  lea     edx, [rsi+2]; DestinationSize
0x1800238e1  mov     [rcx+10h], r8
0x1800238e5  mov     r9d, edx; SourceSize
0x1800238e8  add     rcx, 4; Destination
0x1800238ec  call    cs:__imp_memcpy_s
0x1800238f3  nop     dword ptr [rax+rax+00h]
0x1800238f8  mov     r8, rbp; Source
0x1800238fb  movzx   eax, word ptr [rbx]
0x1800238fe  lea     r14, [rbx+8]
0x180023902  mov     [r14], ax
0x180023906  test    ax, ax
0x180023909  jnz     short loc_18002392C
0x18002390b  lea     rbp, [r8+2]
0x18002390f  cmp     rbp, rdi
0x180023912  ja      short loc_180023938
0x180023914  mov     r9, rsi; SourceSize
0x180023917  mov     rdx, rsi; DestinationSize
0x18002391a  mov     rcx, r14; Destination
0x18002391d  call    cs:__imp_memcpy_s
0x180023924  nop     dword ptr [rax+rax+00h]
0x180023929  mov     r8, rbp
0x18002392c  movzx   ecx, word ptr [r14]
0x180023930  add     rcx, r8
0x180023933  cmp     rcx, rdi
0x180023936  jbe     short loc_18002393C
0x180023938  xor     al, al
0x18002393a  jmp     short loc_180023945
0x18002393c  mov     [rbx+18h], r8
0x180023940  mov     al, 1
0x180023942  mov     [r15], rcx
0x180023945  mov     rbx, [rsp+48h+arg_8]
0x18002394a  mov     rbp, [rsp+48h+arg_10]
0x18002394f  add     rsp, 20h
0x180023953  pop     r15
0x180023955  pop     r14
0x180023957  pop     r12
0x180023959  pop     rdi
0x18002395a  pop     rsi
0x18002395b  retn
```
