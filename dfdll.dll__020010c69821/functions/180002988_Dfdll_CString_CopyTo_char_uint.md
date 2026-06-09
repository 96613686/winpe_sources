# Dfdll::CString::CopyTo(char *,uint &)

- ea: `0x180002988`
- end: `0x180002af7`
- name: `?CopyTo@CString@Dfdll@@QEAAJPEADAEAI@Z`
- size: `367`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180006180`
- `0x1800072e0`

## callees

- `0x180002988`
- `0x180002e44`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CString::CopyTo(Dfdll::CString *this, char *a2, unsigned int *a3)
{
  char *v4; // rdi
  unsigned int ANSIString; // ebx
  const struct std::nothrow_t *v6; // rdx
  unsigned int v7; // r8d
  struct std::nothrow_t *v8; // rdx
  unsigned __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r9
  signed __int64 v12; // r10
  char v13; // al
  char *v14; // rax
  void **v16; // [rsp+20h] [rbp-20h] BYREF
  struct std::nothrow_t *v17; // [rsp+28h] [rbp-18h]
  unsigned int v18; // [rsp+30h] [rbp-10h]

  v4 = a2;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v17 = 0;
  v18 = 0;
  v16 = &Dfdll::CBuffer<unsigned char>::`vftable';
  ANSIString = Dfdll::CString::GetANSIString(this, &v16);
  if ( (ANSIString & 0x80000000) != 0 )
  {
    v16 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v17 )
      operator delete(v17, v6);
    return ANSIString;
  }
  v7 = v18;
  if ( v18 > *a3 )
  {
    *a3 = v18;
    ANSIString = -2147024774;
    v16 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v17 )
      operator delete(v17, v6);
    return ANSIString;
  }
  v8 = v17;
  if ( !v18 && *a3 )
  {
    *v4 = 0;
    *a3 = 1;
    goto LABEL_31;
  }
  v9 = v18 - 1;
  v10 = *a3;
  if ( (unsigned __int64)(v10 - 1) > 0x7FFFFFFE )
  {
    ANSIString = -2147024809;
    if ( *a3 )
    {
      *v4 = 0;
      goto LABEL_25;
    }
  }
  else
  {
    if ( v9 > 0x7FFFFFFE )
    {
      *v4 = 0;
      ANSIString = -2147024809;
      goto LABEL_25;
    }
    v11 = v9 - v10;
    v12 = v17 - (struct std::nothrow_t *)v4;
    do
    {
      if ( !(v11 + v10) )
        break;
      v13 = v4[v12];
      if ( !v13 )
        break;
      *v4++ = v13;
      --v10;
    }
    while ( v10 );
    v14 = v4 - 1;
    if ( v10 )
      v14 = v4;
    *v14 = 0;
    ANSIString = v10 == 0 ? 0x8007007A : 0;
  }
  if ( (ANSIString & 0x80000000) == 0 )
  {
    *a3 = v7;
LABEL_31:
    ANSIString = 0;
    v16 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v8 )
      operator delete(v8, v8);
    return ANSIString;
  }
LABEL_25:
  v16 = &Dfdll::CBuffer<unsigned char>::`vftable';
  if ( v8 )
    operator delete(v8, v8);
  return ANSIString;
}

```

## disassembly

```asm
0x180002988  mov     rax, rsp
0x18000298b  mov     [rax+8], rbx
0x18000298f  mov     [rax+10h], rsi
0x180002993  mov     [rax+18h], rdi
0x180002997  mov     [rax+20h], r15
0x18000299b  push    rbp
0x18000299c  mov     rbp, rsp
0x18000299f  sub     rsp, 40h
0x1800029a3  mov     rsi, r8
0x1800029a6  mov     rdi, rdx
0x1800029a9  test    rdx, rdx
0x1800029ac  jnz     short loc_1800029B8
0x1800029ae  mov     ebx, 80070057h
0x1800029b3  jmp     loc_180002ADB
0x1800029b8  and     [rbp+var_18], 0
0x1800029bd  and     [rbp+var_10], 0
0x1800029c1  lea     r15, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x1800029c8  mov     [rbp+var_20], r15
0x1800029cc  lea     rdx, [rbp+var_20]
0x1800029d0  call    ?GetANSIString@CString@Dfdll@@QEAAJAEAV?$CBuffer@D@2@@Z; Dfdll::CString::GetANSIString(Dfdll::CBuffer<char> &)
0x1800029d5  mov     ebx, eax
0x1800029d7  test    eax, eax
0x1800029d9  jns     short loc_1800029F3
0x1800029db  mov     [rbp+var_20], r15
0x1800029df  mov     rcx, [rbp+var_18]; void *
0x1800029e3  test    rcx, rcx
0x1800029e6  jz      short loc_1800029EE
0x1800029e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800029ed  nop
0x1800029ee  jmp     loc_180002ADB
0x1800029f3  mov     r8d, [rbp+var_10]
0x1800029f7  cmp     r8d, [rsi]
0x1800029fa  jbe     short loc_180002A1C
0x1800029fc  mov     [rsi], r8d
0x1800029ff  mov     ebx, 8007007Ah
0x180002a04  mov     [rbp+var_20], r15
0x180002a08  mov     rcx, [rbp+var_18]; void *
0x180002a0c  test    rcx, rcx
0x180002a0f  jz      short loc_180002A17
0x180002a11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002a16  nop
0x180002a17  jmp     loc_180002ADB
0x180002a1c  mov     rdx, [rbp+var_18]; struct std::nothrow_t *
0x180002a20  test    r8d, r8d
0x180002a23  jnz     short loc_180002A38
0x180002a25  cmp     [rsi], r8d
0x180002a28  jbe     short loc_180002A38
0x180002a2a  mov     [rdi], r8b
0x180002a2d  mov     dword ptr [rsi], 1
0x180002a33  jmp     loc_180002AC7
0x180002a38  lea     r9d, [r8-1]
0x180002a3c  mov     ecx, [rsi]
0x180002a3e  lea     rax, [rcx-1]
0x180002a42  mov     r10d, 7FFFFFFEh
0x180002a48  cmp     rax, r10
0x180002a4b  ja      short loc_180002AB5
0x180002a4d  cmp     r9, r10
0x180002a50  jbe     short loc_180002A5C
0x180002a52  mov     byte ptr [rdi], 0
0x180002a55  mov     ebx, 80070057h
0x180002a5a  jmp     short loc_180002AA1
0x180002a5c  sub     r9, rcx
0x180002a5f  mov     r10, rdx
0x180002a62  sub     r10, rdi
0x180002a65  lea     rax, [r9+rcx]
0x180002a69  test    rax, rax
0x180002a6c  jz      short loc_180002A81
0x180002a6e  mov     al, [r10+rdi]
0x180002a72  test    al, al
0x180002a74  jz      short loc_180002A81
0x180002a76  mov     [rdi], al
0x180002a78  inc     rdi
0x180002a7b  sub     rcx, 1
0x180002a7f  jnz     short loc_180002A65
0x180002a81  lea     rax, [rdi-1]
0x180002a85  test    rcx, rcx
0x180002a88  cmovnz  rax, rdi
0x180002a8c  mov     byte ptr [rax], 0
0x180002a8f  neg     rcx
0x180002a92  sbb     eax, eax
0x180002a94  not     eax
0x180002a96  mov     ebx, 8007007Ah
0x180002a9b  and     ebx, eax
0x180002a9d  test    ebx, ebx
0x180002a9f  jns     short loc_180002AC4
0x180002aa1  mov     [rbp+var_20], r15
0x180002aa5  test    rdx, rdx
0x180002aa8  jz      short loc_180002AB3
0x180002aaa  mov     rcx, rdx; void *
0x180002aad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002ab2  nop
0x180002ab3  jmp     short loc_180002ADB
0x180002ab5  mov     ebx, 80070057h
0x180002aba  test    rcx, rcx
0x180002abd  jz      short loc_180002A9D
0x180002abf  mov     byte ptr [rdi], 0
0x180002ac2  jmp     short loc_180002AA1
0x180002ac4  mov     [rsi], r8d
0x180002ac7  xor     ebx, ebx
0x180002ac9  mov     [rbp+var_20], r15
0x180002acd  test    rdx, rdx
0x180002ad0  jz      short loc_180002ADB
0x180002ad2  mov     rcx, rdx; void *
0x180002ad5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002ada  nop
0x180002adb  mov     eax, ebx
0x180002add  mov     rbx, [rsp+40h+arg_0]
0x180002ae2  mov     rsi, [rsp+40h+arg_8]
0x180002ae7  mov     rdi, [rsp+40h+arg_10]
0x180002aec  mov     r15, [rsp+40h+arg_18]
0x180002af1  add     rsp, 40h
0x180002af5  pop     rbp
0x180002af6  retn
```
