# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180022d1c`
- end: `0x180022e05`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b170`
- `0x18002160c`
- `0x1800223e4`
- `0x1800228a4`
- `0x180023930`

## callees

- `0x180022d1c`

## import_xrefs

- `ntdll!memcpy_s` at `0x180022d6b`
- `ntdll!memcpy_s` at `0x180022da0`
- `ntdll!memcpy_s` at `0x180022dcb`
- `ntdll!memcpy_s` at `0x180022d6b`
- `ntdll!memcpy_s` at `0x180022da0`
- `ntdll!memcpy_s` at `0x180022dcb`

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
0x180022d1c  mov     rax, rsp
0x180022d1f  mov     [rax+10h], rbx
0x180022d23  mov     [rax+18h], rbp
0x180022d27  push    rsi
0x180022d28  push    rdi
0x180022d29  push    r12
0x180022d2b  push    r14
0x180022d2d  push    r15
0x180022d2f  sub     rsp, 20h
0x180022d33  xor     r15d, r15d
0x180022d36  mov     rsi, r8
0x180022d39  cmp     byte ptr [rcx+2], 1
0x180022d3d  mov     r12, rdx
0x180022d40  mov     r8, [rdx]; Source
0x180022d43  mov     rdi, rcx
0x180022d46  jnz     short loc_180022D7B
0x180022d48  lea     rbx, [r8+2]
0x180022d4c  cmp     rbx, rsi
0x180022d4f  ja      loc_180022DE0
0x180022d55  lea     ebp, [r15+2]
0x180022d59  mov     [rcx+10h], r8
0x180022d5d  mov     r9d, ebp; SourceSize
0x180022d60  mov     [rax+8], r15w
0x180022d65  mov     edx, ebp; DestinationSize
0x180022d67  lea     rcx, [rax+8]; Destination
0x180022d6b  call    cs:__imp_memcpy_s
0x180022d71  movzx   eax, [rsp+48h+arg_0]
0x180022d76  mov     [rdi+4], eax
0x180022d79  jmp     short loc_180022DA6
0x180022d7b  mov     ebp, 2
0x180022d80  mov     rbx, r8
0x180022d83  cmp     [rcx+2], bpl
0x180022d87  jnz     short loc_180022DA6
0x180022d89  lea     rbx, [r8+4]
0x180022d8d  cmp     rbx, rsi
0x180022d90  ja      short loc_180022DE0
0x180022d92  lea     edx, [rbp+2]; DestinationSize
0x180022d95  mov     [rcx+10h], r8
0x180022d99  mov     r9d, edx; SourceSize
0x180022d9c  add     rcx, 4; Destination
0x180022da0  call    cs:__imp_memcpy_s
0x180022da6  movzx   eax, word ptr [rdi]
0x180022da9  lea     r14, [rdi+8]
0x180022dad  mov     [r14], ax
0x180022db1  test    ax, ax
0x180022db4  jnz     short loc_180022DD4
0x180022db6  lea     r15, [rbx+2]
0x180022dba  cmp     r15, rsi
0x180022dbd  ja      short loc_180022DE0
0x180022dbf  mov     r9, rbp; SourceSize
0x180022dc2  mov     r8, rbx; Source
0x180022dc5  mov     rdx, rbp; DestinationSize
0x180022dc8  mov     rcx, r14; Destination
0x180022dcb  call    cs:__imp_memcpy_s
0x180022dd1  mov     rbx, r15
0x180022dd4  movzx   ecx, word ptr [r14]
0x180022dd8  add     rcx, rbx
0x180022ddb  cmp     rcx, rsi
0x180022dde  jbe     short loc_180022DE4
0x180022de0  xor     al, al
0x180022de2  jmp     short loc_180022DEE
0x180022de4  mov     [rdi+18h], rbx
0x180022de8  mov     al, 1
0x180022dea  mov     [r12], rcx
0x180022dee  mov     rbx, [rsp+48h+arg_8]
0x180022df3  mov     rbp, [rsp+48h+arg_10]
0x180022df8  add     rsp, 20h
0x180022dfc  pop     r15
0x180022dfe  pop     r14
0x180022e00  pop     r12
0x180022e02  pop     rdi
0x180022e03  pop     rsi
0x180022e04  retn
```
