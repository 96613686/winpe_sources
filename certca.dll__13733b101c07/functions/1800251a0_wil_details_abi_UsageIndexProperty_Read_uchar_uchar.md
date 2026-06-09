# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800251a0`
- end: `0x180025289`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180023ee4`
- `0x1800246b4`
- `0x180024af0`
- `0x180025720`
- `0x180026004`

## callees

- `0x1800251a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800251ef`
- `msvcrt!memcpy_s` at `0x180025224`
- `msvcrt!memcpy_s` at `0x18002524f`
- `msvcrt!memcpy_s` at `0x1800251ef`
- `msvcrt!memcpy_s` at `0x180025224`
- `msvcrt!memcpy_s` at `0x18002524f`

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
0x1800251a0  mov     rax, rsp
0x1800251a3  mov     [rax+10h], rbx
0x1800251a7  mov     [rax+18h], rbp
0x1800251ab  push    rsi
0x1800251ac  push    rdi
0x1800251ad  push    r12
0x1800251af  push    r14
0x1800251b1  push    r15
0x1800251b3  sub     rsp, 20h
0x1800251b7  xor     r15d, r15d
0x1800251ba  mov     rsi, r8
0x1800251bd  cmp     byte ptr [rcx+2], 1
0x1800251c1  mov     r12, rdx
0x1800251c4  mov     r8, [rdx]; Source
0x1800251c7  mov     rdi, rcx
0x1800251ca  jnz     short loc_1800251FF
0x1800251cc  lea     rbx, [r8+2]
0x1800251d0  cmp     rbx, rsi
0x1800251d3  ja      loc_180025264
0x1800251d9  lea     ebp, [r15+2]
0x1800251dd  mov     [rcx+10h], r8
0x1800251e1  mov     r9d, ebp; SourceSize
0x1800251e4  mov     [rax+8], r15w
0x1800251e9  mov     edx, ebp; DestinationSize
0x1800251eb  lea     rcx, [rax+8]; Destination
0x1800251ef  call    cs:__imp_memcpy_s
0x1800251f5  movzx   eax, [rsp+48h+arg_0]
0x1800251fa  mov     [rdi+4], eax
0x1800251fd  jmp     short loc_18002522A
0x1800251ff  mov     ebp, 2
0x180025204  mov     rbx, r8
0x180025207  cmp     [rcx+2], bpl
0x18002520b  jnz     short loc_18002522A
0x18002520d  lea     rbx, [r8+4]
0x180025211  cmp     rbx, rsi
0x180025214  ja      short loc_180025264
0x180025216  lea     edx, [rbp+2]; DestinationSize
0x180025219  mov     [rcx+10h], r8
0x18002521d  mov     r9d, edx; SourceSize
0x180025220  add     rcx, 4; Destination
0x180025224  call    cs:__imp_memcpy_s
0x18002522a  movzx   eax, word ptr [rdi]
0x18002522d  lea     r14, [rdi+8]
0x180025231  mov     [r14], ax
0x180025235  test    ax, ax
0x180025238  jnz     short loc_180025258
0x18002523a  lea     r15, [rbx+2]
0x18002523e  cmp     r15, rsi
0x180025241  ja      short loc_180025264
0x180025243  mov     r9, rbp; SourceSize
0x180025246  mov     r8, rbx; Source
0x180025249  mov     rdx, rbp; DestinationSize
0x18002524c  mov     rcx, r14; Destination
0x18002524f  call    cs:__imp_memcpy_s
0x180025255  mov     rbx, r15
0x180025258  movzx   ecx, word ptr [r14]
0x18002525c  add     rcx, rbx
0x18002525f  cmp     rcx, rsi
0x180025262  jbe     short loc_180025268
0x180025264  xor     al, al
0x180025266  jmp     short loc_180025272
0x180025268  mov     [rdi+18h], rbx
0x18002526c  mov     al, 1
0x18002526e  mov     [r12], rcx
0x180025272  mov     rbx, [rsp+48h+arg_8]
0x180025277  mov     rbp, [rsp+48h+arg_10]
0x18002527c  add     rsp, 20h
0x180025280  pop     r15
0x180025282  pop     r14
0x180025284  pop     r12
0x180025286  pop     rdi
0x180025287  pop     rsi
0x180025288  retn
```
