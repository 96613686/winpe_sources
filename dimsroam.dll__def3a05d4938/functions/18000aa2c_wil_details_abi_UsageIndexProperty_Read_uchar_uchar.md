# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000aa2c`
- end: `0x18000ab15`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000930c`
- `0x18000b060`
- `0x18000b3e8`

## callees

- `0x18000aa2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aa7b`
- `msvcrt!memcpy_s` at `0x18000aab0`
- `msvcrt!memcpy_s` at `0x18000aadb`
- `msvcrt!memcpy_s` at `0x18000aa7b`
- `msvcrt!memcpy_s` at `0x18000aab0`
- `msvcrt!memcpy_s` at `0x18000aadb`

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
0x18000aa2c  mov     rax, rsp
0x18000aa2f  mov     [rax+10h], rbx
0x18000aa33  mov     [rax+18h], rbp
0x18000aa37  push    rsi
0x18000aa38  push    rdi
0x18000aa39  push    r12
0x18000aa3b  push    r14
0x18000aa3d  push    r15
0x18000aa3f  sub     rsp, 20h
0x18000aa43  xor     r15d, r15d
0x18000aa46  mov     rsi, r8
0x18000aa49  cmp     byte ptr [rcx+2], 1
0x18000aa4d  mov     r12, rdx
0x18000aa50  mov     r8, [rdx]; Source
0x18000aa53  mov     rdi, rcx
0x18000aa56  jnz     short loc_18000AA8B
0x18000aa58  lea     rbx, [r8+2]
0x18000aa5c  cmp     rbx, rsi
0x18000aa5f  ja      loc_18000AAF0
0x18000aa65  lea     ebp, [r15+2]
0x18000aa69  mov     [rcx+10h], r8
0x18000aa6d  mov     r9d, ebp; SourceSize
0x18000aa70  mov     [rax+8], r15w
0x18000aa75  mov     edx, ebp; DestinationSize
0x18000aa77  lea     rcx, [rax+8]; Destination
0x18000aa7b  call    cs:__imp_memcpy_s
0x18000aa81  movzx   eax, [rsp+48h+arg_0]
0x18000aa86  mov     [rdi+4], eax
0x18000aa89  jmp     short loc_18000AAB6
0x18000aa8b  mov     ebp, 2
0x18000aa90  mov     rbx, r8
0x18000aa93  cmp     [rcx+2], bpl
0x18000aa97  jnz     short loc_18000AAB6
0x18000aa99  lea     rbx, [r8+4]
0x18000aa9d  cmp     rbx, rsi
0x18000aaa0  ja      short loc_18000AAF0
0x18000aaa2  lea     edx, [rbp+2]; DestinationSize
0x18000aaa5  mov     [rcx+10h], r8
0x18000aaa9  mov     r9d, edx; SourceSize
0x18000aaac  add     rcx, 4; Destination
0x18000aab0  call    cs:__imp_memcpy_s
0x18000aab6  movzx   eax, word ptr [rdi]
0x18000aab9  lea     r14, [rdi+8]
0x18000aabd  mov     [r14], ax
0x18000aac1  test    ax, ax
0x18000aac4  jnz     short loc_18000AAE4
0x18000aac6  lea     r15, [rbx+2]
0x18000aaca  cmp     r15, rsi
0x18000aacd  ja      short loc_18000AAF0
0x18000aacf  mov     r9, rbp; SourceSize
0x18000aad2  mov     r8, rbx; Source
0x18000aad5  mov     rdx, rbp; DestinationSize
0x18000aad8  mov     rcx, r14; Destination
0x18000aadb  call    cs:__imp_memcpy_s
0x18000aae1  mov     rbx, r15
0x18000aae4  movzx   ecx, word ptr [r14]
0x18000aae8  add     rcx, rbx
0x18000aaeb  cmp     rcx, rsi
0x18000aaee  jbe     short loc_18000AAF4
0x18000aaf0  xor     al, al
0x18000aaf2  jmp     short loc_18000AAFE
0x18000aaf4  mov     [rdi+18h], rbx
0x18000aaf8  mov     al, 1
0x18000aafa  mov     [r12], rcx
0x18000aafe  mov     rbx, [rsp+48h+arg_8]
0x18000ab03  mov     rbp, [rsp+48h+arg_10]
0x18000ab08  add     rsp, 20h
0x18000ab0c  pop     r15
0x18000ab0e  pop     r14
0x18000ab10  pop     r12
0x18000ab12  pop     rdi
0x18000ab13  pop     rsi
0x18000ab14  retn
```
