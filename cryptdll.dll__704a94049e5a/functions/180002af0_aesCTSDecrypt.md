# aesCTSDecrypt

- ea: `0x180002af0`
- end: `0x180002d6f`
- name: `aesCTSDecrypt`
- size: `639`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbIV)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180001450`
- `0x1800029b0`
- `0x180005c20`

## callees

- `0x180002af0`
- `0x180004c40`
- `0x1800054be`
- `0x180008415`

## import_xrefs

- `bcrypt!BCryptDecrypt` at `0x180002bf6`
- `bcrypt!BCryptDecrypt` at `0x180002c67`
- `bcrypt!BCryptDecrypt` at `0x180002d18`
- `bcrypt!BCryptDecrypt` at `0x180002d5c`
- `bcrypt!BCryptDecrypt` at `0x180002bf6`
- `bcrypt!BCryptDecrypt` at `0x180002c67`
- `bcrypt!BCryptDecrypt` at `0x180002d18`
- `bcrypt!BCryptDecrypt` at `0x180002d5c`

## pseudocode

```c
int __fastcall aesCTSDecrypt(BCRYPT_KEY_HANDLE hKey, PUCHAR pbIV, unsigned int a3, UCHAR *a4)
{
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned int v9; // edi
  size_t v10; // r13
  UCHAR *v11; // rdi
  int result; // eax
  int v13; // edi
  ULONG pcbResult; // [rsp+58h] [rbp-39h] BYREF
  size_t Size; // [rsp+60h] [rbp-31h]
  UCHAR *v16; // [rsp+68h] [rbp-29h]
  UCHAR pbInput[16]; // [rsp+70h] [rbp-21h] BYREF
  UCHAR pbOutput[16]; // [rsp+80h] [rbp-11h] BYREF
  UCHAR v19[16]; // [rsp+90h] [rbp-1h] BYREF

  *(_OWORD *)v19 = 0;
  *(_OWORD *)pbInput = 0;
  *(_OWORD *)pbOutput = 0;
  if ( a3 < 0x10 )
    return -1073741811;
  if ( a3 == 16 )
  {
    pcbResult = 16;
    *(_OWORD *)pbIV = 0;
    return BCryptDecrypt(hKey, a4, 0x10u, 0, pbIV, 0x10u, a4, 0x10u, &pcbResult, 0);
  }
  else
  {
    v7 = (a3 + 15) >> 4;
    v8 = a3 & 0xF;
    v9 = 16;
    if ( v8 )
      v9 = v8;
    if ( v7 <= 2
      || (pcbResult = 16 * v7 - 32,
          result = BCryptDecrypt(hKey, a4, pcbResult, 0, pbIV, 0x10u, a4, pcbResult, &pcbResult, 0),
          result >= 0) )
    {
      v16 = &a4[16 * v7 - 32];
      memcpy_0(pbInput, v16, v9 + 16);
      v10 = v9;
      Size = 16 - v9;
      v11 = &pbOutput[v9];
      memset_0(v11, 0, (unsigned int)Size);
      pcbResult = 16;
      result = BCryptDecrypt(hKey, pbInput, 0x10u, 0, v19, 0x10u, pbInput, 0x10u, &pcbResult, 0);
      if ( result >= 0 )
      {
        *(__m128 *)pbInput = _mm_xor_ps(
                               (__m128)_mm_loadu_si128((const __m128i *)pbInput),
                               (__m128)_mm_loadu_si128((const __m128i *)pbOutput));
        memcpy_0(v11, &pbInput[v10], Size);
        pcbResult = 16;
        result = BCryptDecrypt(hKey, pbOutput, 0x10u, 0, pbIV, 0x10u, pbOutput, 0x10u, &pcbResult, 0);
        v13 = result;
        if ( result >= 0 )
        {
          *(_OWORD *)v16 = *(_OWORD *)pbOutput;
          memcpy_0(&a4[16 * v7 - 16], pbInput, v10);
          return v13;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002af0  mov     r11, rsp
0x180002af3  push    rbp
0x180002af4  push    r12
0x180002af6  push    r14
0x180002af8  push    r15
0x180002afa  lea     rbp, [r11-5Fh]
0x180002afe  sub     rsp, 0C8h
0x180002b05  mov     rax, cs:__security_cookie
0x180002b0c  xor     rax, rsp
0x180002b0f  mov     [rbp+57h+var_48], rax
0x180002b13  xorps   xmm1, xmm1
0x180002b16  xorps   xmm0, xmm0
0x180002b19  mov     r15, r9
0x180002b1c  mov     r12, rdx
0x180002b1f  mov     r14, rcx
0x180002b22  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180002b26  movups  xmmword ptr [rbp+57h+pbInput], xmm1
0x180002b2a  movups  xmmword ptr [rbp+57h+var_68], xmm1
0x180002b2e  cmp     r8d, 10h
0x180002b32  jb      loc_180002CD2
0x180002b38  mov     [r11-30h], rsi
0x180002b3c  jz      loc_180002CD9
0x180002b42  mov     [r11-28h], rbx
0x180002b46  lea     ebx, [r8+0Fh]
0x180002b4a  shr     ebx, 4
0x180002b4d  and     r8d, 0Fh
0x180002b51  mov     [r11-38h], rdi
0x180002b55  mov     edi, 10h
0x180002b5a  cmovnz  edi, r8d
0x180002b5e  xor     esi, esi
0x180002b60  cmp     ebx, 2
0x180002b63  ja      loc_180002D23
0x180002b69  lea     ecx, [rbx-2]
0x180002b6c  mov     [rsp+0E0h+var_38], r13
0x180002b74  shl     ecx, 4
0x180002b77  lea     r8d, [rdi+10h]; Size
0x180002b7b  add     rcx, r15
0x180002b7e  mov     [rbp+57h+var_80], rcx
0x180002b82  mov     rdx, rcx; Src
0x180002b85  lea     rcx, [rbp+57h+pbInput]; void *
0x180002b89  call    memcpy_0
0x180002b8e  mov     eax, 10h
0x180002b93  mov     r13d, edi
0x180002b96  sub     eax, edi
0x180002b98  xor     edx, edx; Val
0x180002b9a  lea     rdi, [rbp+57h+var_68]
0x180002b9e  mov     [rbp+57h+Size], rax
0x180002ba2  add     rdi, r13
0x180002ba5  mov     r8d, eax; Size
0x180002ba8  mov     rcx, rdi; void *
0x180002bab  call    memset_0
0x180002bb0  mov     [rsp+48h], esi; dwFlags
0x180002bb4  lea     rax, [rbp+57h+var_90]
0x180002bb8  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180002bbd  lea     rdx, [rbp+57h+pbInput]; pbInput
0x180002bc1  mov     [rsp+0E0h+cbOutput], 10h; cbOutput
0x180002bc9  lea     rax, [rbp+57h+pbInput]
0x180002bcd  mov     [rsp+0E0h+pbOutput], rax; pbOutput
0x180002bd2  xor     r9d, r9d; pPaddingInfo
0x180002bd5  lea     rax, [rbp+57h+var_58]
0x180002bd9  mov     [rsp+0E0h+cbIV], 10h; cbIV
0x180002be1  mov     r8d, 10h; cbInput
0x180002be7  mov     [rsp+0E0h+pbIV], rax; pbIV
0x180002bec  mov     rcx, r14; hKey
0x180002bef  mov     [rbp+57h+var_90], 10h
0x180002bf6  call    cs:__imp_BCryptDecrypt
0x180002bfc  test    eax, eax
0x180002bfe  js      short loc_180002C73
0x180002c00  movdqu  xmm1, xmmword ptr [rbp+57h+pbInput]
0x180002c05  mov     r8, [rbp+57h+Size]; Size
0x180002c09  lea     rdx, [rbp+57h+pbInput]
0x180002c0d  movdqu  xmm0, xmmword ptr [rbp+57h+var_68]
0x180002c12  add     rdx, r13; Src
0x180002c15  mov     rcx, rdi; void *
0x180002c18  xorps   xmm1, xmm0
0x180002c1b  movdqu  xmmword ptr [rbp+57h+pbInput], xmm1
0x180002c20  call    memcpy_0
0x180002c25  mov     [rsp+48h], esi; dwFlags
0x180002c29  lea     rax, [rbp+57h+var_90]
0x180002c2d  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180002c32  lea     rdx, [rbp+57h+var_68]; pbInput
0x180002c36  mov     [rsp+0E0h+cbOutput], 10h; cbOutput
0x180002c3e  lea     rax, [rbp+57h+var_68]
0x180002c42  mov     [rsp+0E0h+pbOutput], rax; pbOutput
0x180002c47  xor     r9d, r9d; pPaddingInfo
0x180002c4a  mov     [rsp+0E0h+cbIV], 10h; cbIV
0x180002c52  mov     r8d, 10h; cbInput
0x180002c58  mov     rcx, r14; hKey
0x180002c5b  mov     [rsp+0E0h+pbIV], r12; pbIV
0x180002c60  mov     [rbp+57h+var_90], 10h
0x180002c67  call    cs:__imp_BCryptDecrypt
0x180002c6d  mov     edi, eax
0x180002c6f  test    eax, eax
0x180002c71  jns     short loc_180002CAE
0x180002c73  mov     r13, [rsp+0E0h+var_38]
0x180002c7b  mov     rbx, [rsp+0C0h]
0x180002c83  mov     rdi, [rsp+0E0h+var_30]
0x180002c8b  mov     rsi, [rsp+0E0h+var_28]
0x180002c93  mov     rcx, [rbp+57h+var_48]
0x180002c97  xor     rcx, rsp; StackCookie
0x180002c9a  call    __security_check_cookie
0x180002c9f  add     rsp, 0C8h
0x180002ca6  pop     r15
0x180002ca8  pop     r14
0x180002caa  pop     r12
0x180002cac  pop     rbp
0x180002cad  retn
0x180002cae  mov     rax, [rbp+57h+var_80]
0x180002cb2  lea     rdx, [rbp+57h+pbInput]; Src
0x180002cb6  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x180002cba  shl     ebx, 4
0x180002cbd  mov     r8, r13; Size
0x180002cc0  movups  xmmword ptr [rax], xmm0
0x180002cc3  lea     ecx, [rbx-10h]
0x180002cc6  add     rcx, r15; void *
0x180002cc9  call    memcpy_0
0x180002cce  mov     eax, edi
0x180002cd0  jmp     short loc_180002C73
0x180002cd2  mov     eax, 0C000000Dh
0x180002cd7  jmp     short loc_180002C93
0x180002cd9  xor     esi, esi
0x180002cdb  mov     [rbp+57h+var_90], 10h
0x180002ce2  mov     [rsp+48h], esi; dwFlags
0x180002ce6  lea     rax, [rbp+57h+var_90]
0x180002cea  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180002cef  xor     r9d, r9d; pPaddingInfo
0x180002cf2  mov     [rsp+0E0h+cbOutput], 10h; cbOutput
0x180002cfa  mov     r8d, 10h; cbInput
0x180002d00  mov     [rsp+0E0h+pbOutput], r15; pbOutput
0x180002d05  movups  xmmword ptr [rdx], xmm0
0x180002d08  mov     [rsp+0E0h+cbIV], 10h; cbIV
0x180002d10  mov     rdx, r15; pbInput
0x180002d13  mov     [rsp+0E0h+pbIV], r12; pbIV
0x180002d18  call    cs:__imp_BCryptDecrypt
0x180002d1e  jmp     loc_180002C8B
0x180002d23  mov     [rsp+48h], esi; dwFlags
0x180002d27  lea     rax, [rbp+57h+var_90]
0x180002d2b  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180002d30  mov     r8d, ebx
0x180002d33  shl     r8d, 4
0x180002d37  xor     r9d, r9d; pPaddingInfo
0x180002d3a  add     r8d, 0FFFFFFE0h; cbInput
0x180002d3e  mov     rdx, r15; pbInput
0x180002d41  mov     [rsp+0E0h+cbOutput], r8d; cbOutput
0x180002d46  mov     [rsp+0E0h+pbOutput], r15; pbOutput
0x180002d4b  mov     [rsp+0E0h+cbIV], 10h; cbIV
0x180002d53  mov     [rsp+0E0h+pbIV], r12; pbIV
0x180002d58  mov     [rbp+57h+var_90], r8d
0x180002d5c  call    cs:__imp_BCryptDecrypt
0x180002d62  test    eax, eax
0x180002d64  js      loc_180002C7B
0x180002d6a  jmp     loc_180002B69
```
