# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001495c`
- end: `0x180014a42`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f2e4`
- `0x180012d18`
- `0x1800145c8`
- `0x1800146fc`
- `0x18001523c`

## callees

- `0x18000f160`
- `0x18001495c`

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
0x18001495c  mov     rax, rsp
0x18001495f  mov     [rax+10h], rbx
0x180014963  mov     [rax+18h], rbp
0x180014967  push    rsi
0x180014968  push    rdi
0x180014969  push    r12
0x18001496b  push    r14
0x18001496d  push    r15
0x18001496f  sub     rsp, 20h
0x180014973  xor     r15d, r15d
0x180014976  mov     rsi, r8
0x180014979  cmp     byte ptr [rcx+2], 1
0x18001497d  mov     r12, rdx
0x180014980  mov     r8, [rdx]; Source
0x180014983  mov     rdi, rcx
0x180014986  jnz     short loc_1800149BA
0x180014988  lea     rbx, [r8+2]
0x18001498c  cmp     rbx, rsi
0x18001498f  ja      loc_180014A1D
0x180014995  lea     ebp, [r15+2]
0x180014999  mov     [rcx+10h], r8
0x18001499d  mov     r9d, ebp; SourceSize
0x1800149a0  mov     [rax+8], r15w
0x1800149a5  mov     edx, ebp; DestinationSize
0x1800149a7  lea     rcx, [rax+8]; Destination
0x1800149ab  call    memcpy_s
0x1800149b0  movzx   eax, [rsp+48h+arg_0]
0x1800149b5  mov     [rdi+4], eax
0x1800149b8  jmp     short loc_1800149E4
0x1800149ba  mov     ebp, 2
0x1800149bf  mov     rbx, r8
0x1800149c2  cmp     [rcx+2], bpl
0x1800149c6  jnz     short loc_1800149E4
0x1800149c8  lea     rbx, [r8+4]
0x1800149cc  cmp     rbx, rsi
0x1800149cf  ja      short loc_180014A1D
0x1800149d1  lea     edx, [rbp+2]; DestinationSize
0x1800149d4  mov     [rcx+10h], r8
0x1800149d8  mov     r9d, edx; SourceSize
0x1800149db  add     rcx, 4; Destination
0x1800149df  call    memcpy_s
0x1800149e4  movzx   eax, word ptr [rdi]
0x1800149e7  lea     r14, [rdi+8]
0x1800149eb  mov     [r14], ax
0x1800149ef  test    ax, ax
0x1800149f2  jnz     short loc_180014A11
0x1800149f4  lea     r15, [rbx+2]
0x1800149f8  cmp     r15, rsi
0x1800149fb  ja      short loc_180014A1D
0x1800149fd  mov     r9, rbp; SourceSize
0x180014a00  mov     r8, rbx; Source
0x180014a03  mov     rdx, rbp; DestinationSize
0x180014a06  mov     rcx, r14; Destination
0x180014a09  call    memcpy_s
0x180014a0e  mov     rbx, r15
0x180014a11  movzx   ecx, word ptr [r14]
0x180014a15  add     rcx, rbx
0x180014a18  cmp     rcx, rsi
0x180014a1b  jbe     short loc_180014A21
0x180014a1d  xor     al, al
0x180014a1f  jmp     short loc_180014A2B
0x180014a21  mov     [rdi+18h], rbx
0x180014a25  mov     al, 1
0x180014a27  mov     [r12], rcx
0x180014a2b  mov     rbx, [rsp+48h+arg_8]
0x180014a30  mov     rbp, [rsp+48h+arg_10]
0x180014a35  add     rsp, 20h
0x180014a39  pop     r15
0x180014a3b  pop     r14
0x180014a3d  pop     r12
0x180014a3f  pop     rdi
0x180014a40  pop     rsi
0x180014a41  retn
```
