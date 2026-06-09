# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000ed3c`
- end: `0x14000ee25`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140014dfc`
- `0x140016774`
- `0x1400168a4`
- `0x14001795c`

## callees

- `0x14000ed3c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000ed8b`
- `msvcrt!memcpy_s` at `0x14000edc0`
- `msvcrt!memcpy_s` at `0x14000edeb`
- `msvcrt!memcpy_s` at `0x14000ed8b`
- `msvcrt!memcpy_s` at `0x14000edc0`
- `msvcrt!memcpy_s` at `0x14000edeb`

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
0x14000ed3c  mov     rax, rsp
0x14000ed3f  mov     [rax+10h], rbx
0x14000ed43  mov     [rax+18h], rbp
0x14000ed47  push    rsi
0x14000ed48  push    rdi
0x14000ed49  push    r12
0x14000ed4b  push    r14
0x14000ed4d  push    r15
0x14000ed4f  sub     rsp, 20h
0x14000ed53  xor     r15d, r15d
0x14000ed56  mov     rsi, r8
0x14000ed59  cmp     byte ptr [rcx+2], 1
0x14000ed5d  mov     r12, rdx
0x14000ed60  mov     r8, [rdx]; Source
0x14000ed63  mov     rdi, rcx
0x14000ed66  jnz     short loc_14000ED9B
0x14000ed68  lea     rbx, [r8+2]
0x14000ed6c  cmp     rbx, rsi
0x14000ed6f  ja      loc_14000EE00
0x14000ed75  lea     ebp, [r15+2]
0x14000ed79  mov     [rcx+10h], r8
0x14000ed7d  mov     r9d, ebp; SourceSize
0x14000ed80  mov     [rax+8], r15w
0x14000ed85  mov     edx, ebp; DestinationSize
0x14000ed87  lea     rcx, [rax+8]; Destination
0x14000ed8b  call    cs:__imp_memcpy_s
0x14000ed91  movzx   eax, [rsp+48h+arg_0]
0x14000ed96  mov     [rdi+4], eax
0x14000ed99  jmp     short loc_14000EDC6
0x14000ed9b  mov     ebp, 2
0x14000eda0  mov     rbx, r8
0x14000eda3  cmp     [rcx+2], bpl
0x14000eda7  jnz     short loc_14000EDC6
0x14000eda9  lea     rbx, [r8+4]
0x14000edad  cmp     rbx, rsi
0x14000edb0  ja      short loc_14000EE00
0x14000edb2  lea     edx, [rbp+2]; DestinationSize
0x14000edb5  mov     [rcx+10h], r8
0x14000edb9  mov     r9d, edx; SourceSize
0x14000edbc  add     rcx, 4; Destination
0x14000edc0  call    cs:__imp_memcpy_s
0x14000edc6  movzx   eax, word ptr [rdi]
0x14000edc9  lea     r14, [rdi+8]
0x14000edcd  mov     [r14], ax
0x14000edd1  test    ax, ax
0x14000edd4  jnz     short loc_14000EDF4
0x14000edd6  lea     r15, [rbx+2]
0x14000edda  cmp     r15, rsi
0x14000eddd  ja      short loc_14000EE00
0x14000eddf  mov     r9, rbp; SourceSize
0x14000ede2  mov     r8, rbx; Source
0x14000ede5  mov     rdx, rbp; DestinationSize
0x14000ede8  mov     rcx, r14; Destination
0x14000edeb  call    cs:__imp_memcpy_s
0x14000edf1  mov     rbx, r15
0x14000edf4  movzx   ecx, word ptr [r14]
0x14000edf8  add     rcx, rbx
0x14000edfb  cmp     rcx, rsi
0x14000edfe  jbe     short loc_14000EE04
0x14000ee00  xor     al, al
0x14000ee02  jmp     short loc_14000EE0E
0x14000ee04  mov     [rdi+18h], rbx
0x14000ee08  mov     al, 1
0x14000ee0a  mov     [r12], rcx
0x14000ee0e  mov     rbx, [rsp+48h+arg_8]
0x14000ee13  mov     rbp, [rsp+48h+arg_10]
0x14000ee18  add     rsp, 20h
0x14000ee1c  pop     r15
0x14000ee1e  pop     r14
0x14000ee20  pop     r12
0x14000ee22  pop     rdi
0x14000ee23  pop     rsi
0x14000ee24  retn
```
