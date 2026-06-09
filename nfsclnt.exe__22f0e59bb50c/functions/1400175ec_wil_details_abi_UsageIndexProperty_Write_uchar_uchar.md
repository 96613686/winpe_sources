# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1400175ec`
- end: `0x1400176c5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015cf0`

## callees

- `0x1400175ec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001764c`
- `msvcrt!memcpy_s` at `0x140017677`
- `msvcrt!memcpy_s` at `0x1400176a4`
- `msvcrt!memcpy_s` at `0x14001764c`
- `msvcrt!memcpy_s` at `0x140017677`
- `msvcrt!memcpy_s` at `0x1400176a4`

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
0x1400175ec  push    rbx
0x1400175ee  push    rsi
0x1400175ef  push    rdi
0x1400175f0  push    r12
0x1400175f2  push    r14
0x1400175f4  push    r15
0x1400175f6  sub     rsp, 28h
0x1400175fa  mov     rsi, rcx
0x1400175fd  mov     rdi, r8
0x140017600  mov     rcx, [rdx]; Destination
0x140017603  mov     r12, rdx
0x140017606  cmp     byte ptr [rsi+2], 1
0x14001760a  jnz     short loc_14001762E
0x14001760c  lea     rbx, [rcx+2]
0x140017610  cmp     rbx, r8
0x140017613  ja      short loc_140017693
0x140017615  movzx   eax, word ptr [rsi+4]
0x140017619  lea     r8, [rsp+58h+arg_0]
0x14001761e  mov     r9d, 2
0x140017624  mov     [rsp+58h+arg_0], ax
0x140017629  mov     edx, r9d
0x14001762c  jmp     short loc_14001764C
0x14001762e  cmp     byte ptr [rsi+2], 2
0x140017632  mov     rbx, rcx
0x140017635  jnz     short loc_140017652
0x140017637  lea     rbx, [rcx+4]
0x14001763b  cmp     rbx, rdi
0x14001763e  ja      short loc_140017693
0x140017640  mov     edx, 4; DestinationSize
0x140017645  lea     r8, [rsi+4]; Source
0x140017649  mov     r9d, edx; SourceSize
0x14001764c  call    cs:__imp_memcpy_s
0x140017652  cmp     word ptr [rsi], 0
0x140017656  jnz     short loc_140017682
0x140017658  lea     r15, [rbx+2]
0x14001765c  cmp     r15, rdi
0x14001765f  ja      short loc_140017693
0x140017661  lea     r14, [rsi+8]
0x140017665  mov     rdx, rdi
0x140017668  sub     rdx, rbx; DestinationSize
0x14001766b  mov     r8, r14; Source
0x14001766e  mov     r9d, 2; SourceSize
0x140017674  mov     rcx, rbx; Destination
0x140017677  call    cs:__imp_memcpy_s
0x14001767d  mov     rbx, r15
0x140017680  jmp     short loc_140017686
0x140017682  lea     r14, [rsi+8]
0x140017686  movzx   r9d, word ptr [r14]; SourceSize
0x14001768a  lea     rax, [r9+rbx]
0x14001768e  cmp     rax, rdi
0x140017691  jbe     short loc_140017697
0x140017693  xor     al, al
0x140017695  jmp     short loc_1400176B7
0x140017697  mov     r8, [rsi+18h]; Source
0x14001769b  sub     rdi, rbx
0x14001769e  mov     rdx, rdi; DestinationSize
0x1400176a1  mov     rcx, rbx; Destination
0x1400176a4  call    cs:__imp_memcpy_s
0x1400176aa  movzx   ecx, word ptr [r14]
0x1400176ae  mov     al, 1
0x1400176b0  add     rcx, rbx
0x1400176b3  mov     [r12], rcx
0x1400176b7  add     rsp, 28h
0x1400176bb  pop     r15
0x1400176bd  pop     r14
0x1400176bf  pop     r12
0x1400176c1  pop     rdi
0x1400176c2  pop     rsi
0x1400176c3  pop     rbx
0x1400176c4  retn
```
