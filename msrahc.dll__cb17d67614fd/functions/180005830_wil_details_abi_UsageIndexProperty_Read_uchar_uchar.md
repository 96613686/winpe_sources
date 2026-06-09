# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005830`
- end: `0x180005919`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f14`
- `0x180004cd8`
- `0x18000517c`
- `0x180005dd4`
- `0x180006960`

## callees

- `0x180005830`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000587f`
- `msvcrt!memcpy_s` at `0x1800058b4`
- `msvcrt!memcpy_s` at `0x1800058df`
- `msvcrt!memcpy_s` at `0x18000587f`
- `msvcrt!memcpy_s` at `0x1800058b4`
- `msvcrt!memcpy_s` at `0x1800058df`

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
0x180005830  mov     rax, rsp
0x180005833  mov     [rax+10h], rbx
0x180005837  mov     [rax+18h], rbp
0x18000583b  push    rsi
0x18000583c  push    rdi
0x18000583d  push    r12
0x18000583f  push    r14
0x180005841  push    r15
0x180005843  sub     rsp, 20h
0x180005847  xor     r15d, r15d
0x18000584a  mov     rsi, r8
0x18000584d  cmp     byte ptr [rcx+2], 1
0x180005851  mov     r12, rdx
0x180005854  mov     r8, [rdx]; Source
0x180005857  mov     rdi, rcx
0x18000585a  jnz     short loc_18000588F
0x18000585c  lea     rbx, [r8+2]
0x180005860  cmp     rbx, rsi
0x180005863  ja      loc_1800058F4
0x180005869  lea     ebp, [r15+2]
0x18000586d  mov     [rcx+10h], r8
0x180005871  mov     r9d, ebp; SourceSize
0x180005874  mov     [rax+8], r15w
0x180005879  mov     edx, ebp; DestinationSize
0x18000587b  lea     rcx, [rax+8]; Destination
0x18000587f  call    cs:__imp_memcpy_s
0x180005885  movzx   eax, [rsp+48h+arg_0]
0x18000588a  mov     [rdi+4], eax
0x18000588d  jmp     short loc_1800058BA
0x18000588f  mov     ebp, 2
0x180005894  mov     rbx, r8
0x180005897  cmp     [rcx+2], bpl
0x18000589b  jnz     short loc_1800058BA
0x18000589d  lea     rbx, [r8+4]
0x1800058a1  cmp     rbx, rsi
0x1800058a4  ja      short loc_1800058F4
0x1800058a6  lea     edx, [rbp+2]; DestinationSize
0x1800058a9  mov     [rcx+10h], r8
0x1800058ad  mov     r9d, edx; SourceSize
0x1800058b0  add     rcx, 4; Destination
0x1800058b4  call    cs:__imp_memcpy_s
0x1800058ba  movzx   eax, word ptr [rdi]
0x1800058bd  lea     r14, [rdi+8]
0x1800058c1  mov     [r14], ax
0x1800058c5  test    ax, ax
0x1800058c8  jnz     short loc_1800058E8
0x1800058ca  lea     r15, [rbx+2]
0x1800058ce  cmp     r15, rsi
0x1800058d1  ja      short loc_1800058F4
0x1800058d3  mov     r9, rbp; SourceSize
0x1800058d6  mov     r8, rbx; Source
0x1800058d9  mov     rdx, rbp; DestinationSize
0x1800058dc  mov     rcx, r14; Destination
0x1800058df  call    cs:__imp_memcpy_s
0x1800058e5  mov     rbx, r15
0x1800058e8  movzx   ecx, word ptr [r14]
0x1800058ec  add     rcx, rbx
0x1800058ef  cmp     rcx, rsi
0x1800058f2  jbe     short loc_1800058F8
0x1800058f4  xor     al, al
0x1800058f6  jmp     short loc_180005902
0x1800058f8  mov     [rdi+18h], rbx
0x1800058fc  mov     al, 1
0x1800058fe  mov     [r12], rcx
0x180005902  mov     rbx, [rsp+48h+arg_8]
0x180005907  mov     rbp, [rsp+48h+arg_10]
0x18000590c  add     rsp, 20h
0x180005910  pop     r15
0x180005912  pop     r14
0x180005914  pop     r12
0x180005916  pop     rdi
0x180005917  pop     rsi
0x180005918  retn
```
