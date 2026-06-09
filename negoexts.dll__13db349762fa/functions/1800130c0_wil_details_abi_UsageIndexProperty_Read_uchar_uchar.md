# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800130c0`
- end: `0x1800131a9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e338`
- `0x180011258`
- `0x180012454`
- `0x1800128f8`
- `0x180014090`

## callees

- `0x1800130c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001310f`
- `msvcrt!memcpy_s` at `0x180013144`
- `msvcrt!memcpy_s` at `0x18001316f`
- `msvcrt!memcpy_s` at `0x18001310f`
- `msvcrt!memcpy_s` at `0x180013144`
- `msvcrt!memcpy_s` at `0x18001316f`

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
0x1800130c0  mov     rax, rsp
0x1800130c3  mov     [rax+10h], rbx
0x1800130c7  mov     [rax+18h], rbp
0x1800130cb  push    rsi
0x1800130cc  push    rdi
0x1800130cd  push    r12
0x1800130cf  push    r14
0x1800130d1  push    r15
0x1800130d3  sub     rsp, 20h
0x1800130d7  xor     r15d, r15d
0x1800130da  mov     rsi, r8
0x1800130dd  cmp     byte ptr [rcx+2], 1
0x1800130e1  mov     r12, rdx
0x1800130e4  mov     r8, [rdx]; Source
0x1800130e7  mov     rdi, rcx
0x1800130ea  jnz     short loc_18001311F
0x1800130ec  lea     rbx, [r8+2]
0x1800130f0  cmp     rbx, rsi
0x1800130f3  ja      loc_180013184
0x1800130f9  lea     ebp, [r15+2]
0x1800130fd  mov     [rcx+10h], r8
0x180013101  mov     r9d, ebp; SourceSize
0x180013104  mov     [rax+8], r15w
0x180013109  mov     edx, ebp; DestinationSize
0x18001310b  lea     rcx, [rax+8]; Destination
0x18001310f  call    cs:__imp_memcpy_s
0x180013115  movzx   eax, [rsp+48h+arg_0]
0x18001311a  mov     [rdi+4], eax
0x18001311d  jmp     short loc_18001314A
0x18001311f  mov     ebp, 2
0x180013124  mov     rbx, r8
0x180013127  cmp     [rcx+2], bpl
0x18001312b  jnz     short loc_18001314A
0x18001312d  lea     rbx, [r8+4]
0x180013131  cmp     rbx, rsi
0x180013134  ja      short loc_180013184
0x180013136  lea     edx, [rbp+2]; DestinationSize
0x180013139  mov     [rcx+10h], r8
0x18001313d  mov     r9d, edx; SourceSize
0x180013140  add     rcx, 4; Destination
0x180013144  call    cs:__imp_memcpy_s
0x18001314a  movzx   eax, word ptr [rdi]
0x18001314d  lea     r14, [rdi+8]
0x180013151  mov     [r14], ax
0x180013155  test    ax, ax
0x180013158  jnz     short loc_180013178
0x18001315a  lea     r15, [rbx+2]
0x18001315e  cmp     r15, rsi
0x180013161  ja      short loc_180013184
0x180013163  mov     r9, rbp; SourceSize
0x180013166  mov     r8, rbx; Source
0x180013169  mov     rdx, rbp; DestinationSize
0x18001316c  mov     rcx, r14; Destination
0x18001316f  call    cs:__imp_memcpy_s
0x180013175  mov     rbx, r15
0x180013178  movzx   ecx, word ptr [r14]
0x18001317c  add     rcx, rbx
0x18001317f  cmp     rcx, rsi
0x180013182  jbe     short loc_180013188
0x180013184  xor     al, al
0x180013186  jmp     short loc_180013192
0x180013188  mov     [rdi+18h], rbx
0x18001318c  mov     al, 1
0x18001318e  mov     [r12], rcx
0x180013192  mov     rbx, [rsp+48h+arg_8]
0x180013197  mov     rbp, [rsp+48h+arg_10]
0x18001319c  add     rsp, 20h
0x1800131a0  pop     r15
0x1800131a2  pop     r14
0x1800131a4  pop     r12
0x1800131a6  pop     rdi
0x1800131a7  pop     rsi
0x1800131a8  retn
```
