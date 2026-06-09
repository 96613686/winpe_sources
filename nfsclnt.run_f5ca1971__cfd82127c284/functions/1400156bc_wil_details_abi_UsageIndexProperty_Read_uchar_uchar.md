# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1400156bc`
- end: `0x1400157a5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140013f9c`
- `0x140015cf0`
- `0x140016078`

## callees

- `0x1400156bc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001570b`
- `msvcrt!memcpy_s` at `0x140015740`
- `msvcrt!memcpy_s` at `0x14001576b`
- `msvcrt!memcpy_s` at `0x14001570b`
- `msvcrt!memcpy_s` at `0x140015740`
- `msvcrt!memcpy_s` at `0x14001576b`

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
0x1400156bc  mov     rax, rsp
0x1400156bf  mov     [rax+10h], rbx
0x1400156c3  mov     [rax+18h], rbp
0x1400156c7  push    rsi
0x1400156c8  push    rdi
0x1400156c9  push    r12
0x1400156cb  push    r14
0x1400156cd  push    r15
0x1400156cf  sub     rsp, 20h
0x1400156d3  xor     r15d, r15d
0x1400156d6  mov     rsi, r8
0x1400156d9  cmp     byte ptr [rcx+2], 1
0x1400156dd  mov     r12, rdx
0x1400156e0  mov     r8, [rdx]; Source
0x1400156e3  mov     rdi, rcx
0x1400156e6  jnz     short loc_14001571B
0x1400156e8  lea     rbx, [r8+2]
0x1400156ec  cmp     rbx, rsi
0x1400156ef  ja      loc_140015780
0x1400156f5  lea     ebp, [r15+2]
0x1400156f9  mov     [rcx+10h], r8
0x1400156fd  mov     r9d, ebp; SourceSize
0x140015700  mov     [rax+8], r15w
0x140015705  mov     edx, ebp; DestinationSize
0x140015707  lea     rcx, [rax+8]; Destination
0x14001570b  call    cs:__imp_memcpy_s
0x140015711  movzx   eax, [rsp+48h+arg_0]
0x140015716  mov     [rdi+4], eax
0x140015719  jmp     short loc_140015746
0x14001571b  mov     ebp, 2
0x140015720  mov     rbx, r8
0x140015723  cmp     [rcx+2], bpl
0x140015727  jnz     short loc_140015746
0x140015729  lea     rbx, [r8+4]
0x14001572d  cmp     rbx, rsi
0x140015730  ja      short loc_140015780
0x140015732  lea     edx, [rbp+2]; DestinationSize
0x140015735  mov     [rcx+10h], r8
0x140015739  mov     r9d, edx; SourceSize
0x14001573c  add     rcx, 4; Destination
0x140015740  call    cs:__imp_memcpy_s
0x140015746  movzx   eax, word ptr [rdi]
0x140015749  lea     r14, [rdi+8]
0x14001574d  mov     [r14], ax
0x140015751  test    ax, ax
0x140015754  jnz     short loc_140015774
0x140015756  lea     r15, [rbx+2]
0x14001575a  cmp     r15, rsi
0x14001575d  ja      short loc_140015780
0x14001575f  mov     r9, rbp; SourceSize
0x140015762  mov     r8, rbx; Source
0x140015765  mov     rdx, rbp; DestinationSize
0x140015768  mov     rcx, r14; Destination
0x14001576b  call    cs:__imp_memcpy_s
0x140015771  mov     rbx, r15
0x140015774  movzx   ecx, word ptr [r14]
0x140015778  add     rcx, rbx
0x14001577b  cmp     rcx, rsi
0x14001577e  jbe     short loc_140015784
0x140015780  xor     al, al
0x140015782  jmp     short loc_14001578E
0x140015784  mov     [rdi+18h], rbx
0x140015788  mov     al, 1
0x14001578a  mov     [r12], rcx
0x14001578e  mov     rbx, [rsp+48h+arg_8]
0x140015793  mov     rbp, [rsp+48h+arg_10]
0x140015798  add     rsp, 20h
0x14001579c  pop     r15
0x14001579e  pop     r14
0x1400157a0  pop     r12
0x1400157a2  pop     rdi
0x1400157a3  pop     rsi
0x1400157a4  retn
```
