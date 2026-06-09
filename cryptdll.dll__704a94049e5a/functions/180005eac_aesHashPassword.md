# aesHashPassword

- ea: `0x180005eac`
- end: `0x180005fae`
- name: `aesHashPassword`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005ac0`
- `0x180005b00`

## callees

- `0x1800027a0`
- `0x180004c40`
- `0x1800058c0`
- `0x180005eac`
- `0x180006530`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f82`

## pseudocode

```c
__int64 __fastcall aesHashPassword(__int64 a1, __int64 a2, int a3, ULONG a4, char *a5)
{
  int v8; // ebx
  HLOCAL v9; // rdi
  ULONGLONG v11; // [rsp+20h] [rbp-51h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-31h] BYREF
  HLOCAL v13[2]; // [rsp+50h] [rbp-21h] BYREF
  __m128i si128; // [rsp+60h] [rbp-11h] BYREF
  UCHAR v15[32]; // [rsp+70h] [rbp-1h] BYREF

  *(_OWORD *)hMem = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_OWORD *)v13 = 0;
  v8 = aesUtf8StringFromUnicodeString(a1, hMem);
  if ( v8 < 0 || (v8 = aesUtf8StringFromUnicodeString(a2, v13), v8 < 0) )
  {
    v9 = v13[1];
  }
  else
  {
    v9 = v13[1];
    LODWORD(v11) = a3;
    v8 = PBKDF2((PUCHAR)hMem[1], LOWORD(hMem[0]), (PUCHAR)v13[1], LOWORD(v13[0]), v11, a4, v15);
    if ( v8 >= 0 )
      v8 = aesDR((UCHAR *)&si128, v15, a4, a5);
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005eac  mov     [rsp-8+arg_10], rbx
0x180005eb1  push    rbp
0x180005eb2  push    rdi
0x180005eb3  push    r12
0x180005eb5  push    r14
0x180005eb7  push    r15
0x180005eb9  lea     rbp, [rsp-2Fh]
0x180005ebe  sub     rsp, 0A0h
0x180005ec5  mov     rax, cs:__security_cookie
0x180005ecc  xor     rax, rsp
0x180005ecf  mov     [rbp+4Fh+var_30], rax
0x180005ed3  mov     r15, [rbp+4Fh+arg_20]
0x180005ed7  xorps   xmm0, xmm0
0x180005eda  movups  xmmword ptr [rbp+4Fh+hMem], xmm0
0x180005ede  mov     rdi, rdx
0x180005ee1  lea     rdx, [rbp+4Fh+hMem]
0x180005ee5  movdqa  xmm0, cs:__xmm@932b13932b5b9b7b736f72656272656b
0x180005eed  xorps   xmm1, xmm1
0x180005ef0  movdqu  [rbp+4Fh+var_60], xmm0
0x180005ef5  mov     r14d, r9d
0x180005ef8  mov     r12d, r8d
0x180005efb  movups  xmmword ptr [rbp+4Fh+var_70], xmm1
0x180005eff  call    aesUtf8StringFromUnicodeString
0x180005f04  mov     ebx, eax
0x180005f06  test    eax, eax
0x180005f08  js      short loc_180005F65
0x180005f0a  lea     rdx, [rbp+4Fh+var_70]
0x180005f0e  mov     rcx, rdi
0x180005f11  call    aesUtf8StringFromUnicodeString
0x180005f16  mov     ebx, eax
0x180005f18  test    eax, eax
0x180005f1a  js      short loc_180005F65
0x180005f1c  mov     rdi, [rbp+4Fh+var_70+8]
0x180005f20  lea     rax, [rbp+4Fh+var_50]
0x180005f24  movzx   r9d, word ptr [rbp+4Fh+var_70]; cbSalt
0x180005f29  mov     r8, rdi; pbSalt
0x180005f2c  movzx   edx, word ptr [rbp+4Fh+hMem]; cbPassword
0x180005f30  mov     rcx, [rbp+4Fh+hMem+8]; pbPassword
0x180005f34  mov     [rsp+0C0h+var_90], rax; PUCHAR
0x180005f39  mov     [rsp+0C0h+var_98], r14d; ULONG
0x180005f3e  mov     dword ptr [rsp+0C0h+var_A0], r12d; ULONGLONG
0x180005f43  call    PBKDF2
0x180005f48  mov     ebx, eax
0x180005f4a  test    eax, eax
0x180005f4c  js      short loc_180005F69
0x180005f4e  mov     r9, r15
0x180005f51  lea     rdx, [rbp+4Fh+var_50]
0x180005f55  mov     r8d, r14d
0x180005f58  lea     rcx, [rbp+4Fh+var_60]
0x180005f5c  call    aesDR
0x180005f61  mov     ebx, eax
0x180005f63  jmp     short loc_180005F69
0x180005f65  mov     rdi, [rbp+4Fh+var_70+8]
0x180005f69  cmp     [rbp+4Fh+hMem+8], 0
0x180005f6e  jz      short loc_180005F7A
0x180005f70  mov     rcx, [rbp+4Fh+hMem+8]; hMem
0x180005f74  call    cs:__imp_LocalFree
0x180005f7a  test    rdi, rdi
0x180005f7d  jz      short loc_180005F88
0x180005f7f  mov     rcx, rdi; hMem
0x180005f82  call    cs:__imp_LocalFree
0x180005f88  mov     eax, ebx
0x180005f8a  mov     rcx, [rbp+4Fh+var_30]
0x180005f8e  xor     rcx, rsp; StackCookie
0x180005f91  call    __security_check_cookie
0x180005f96  mov     rbx, [rsp+0C0h+arg_10]
0x180005f9e  add     rsp, 0A0h
0x180005fa5  pop     r15
0x180005fa7  pop     r14
0x180005fa9  pop     r12
0x180005fab  pop     rdi
0x180005fac  pop     rbp
0x180005fad  retn
```
