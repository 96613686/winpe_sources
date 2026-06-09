# DoNGen_Legacy(NGenOptionsParser *,ushort const *,long (*)(void * *,_NGenOptions *),long (*)(void *,ushort const *,bool,bool),int (*)(void *,ushort const *),long (*)(void *))

- ea: `0x140007bac`
- end: `0x140007f1b`
- name: `?DoNGen_Legacy@@YAHPEAVNGenOptionsParser@@PEBGP6AJPEAPEAXPEAU_NGenOptions@@@ZP6AJPEAX1_N6@ZP6AH51@ZP6AJ5@Z@Z`
- size: `879`
- prototype: `__int64 __fastcall(struct NGenOptionsParser *, const unsigned __int16 *, __int64 (__fastcall *)(__int64 *, int *), int (*)(void *, const unsigned __int16 *, bool, bool), int (*)(void *, const unsigned __int16 *), int (*)(void *))`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140009104`

## callees

- `0x140006e3c`
- `0x140006fb8`
- `0x140007bac`
- `0x14000e708`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x140007cbc`
- `KERNEL32!GetCurrentDirectoryW` at `0x140007cbc`
- `KERNEL32!GetFileAttributesW` at `0x140007d2d`
- `KERNEL32!GetFileAttributesW` at `0x140007d2d`
- `KERNEL32!GetFullPathNameW` at `0x140007c87`
- `KERNEL32!GetFullPathNameW` at `0x140007d5c`
- `KERNEL32!GetFullPathNameW` at `0x140007c87`
- `KERNEL32!GetFullPathNameW` at `0x140007d5c`

## string_xrefs

- `0x140007c9a`: `Filename and path are too long.\n`
- `0x140007f05`: `Filename and path are too long.\n`
- `0x140007e11`: `Error reading fusion cache for %s\n`
- `0x140007e83`: `No matched entries in the cache.\n`

## pseudocode

```c
__int64 __fastcall DoNGen_Legacy(
        struct NGenOptionsParser *a1,
        const unsigned __int16 *a2,
        __int64 (__fastcall *a3)(__int64 *, int *),
        int (*a4)(void *, const unsigned __int16 *, bool, bool),
        int (*a5)(void *, const unsigned __int16 *),
        int (*a6)(void *))
{
  int (*v6)(void *); // r14
  unsigned int v10; // r13d
  int v12; // eax
  __int64 v13; // rdx
  _WORD *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r9
  unsigned int v17; // r12d
  __int64 v18; // r14
  __int64 v19; // rcx
  DWORD FileAttributesW; // eax
  WCHAR *v21; // rdx
  BOOL v22; // r14d
  unsigned int v23; // r12d
  int (*v24)(void *, const unsigned __int16 *, bool, bool); // r13
  __int64 v25; // r15
  int v26; // eax
  bool v27; // si
  int v28; // eax
  int v29; // eax
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v31; // [rsp+38h] [rbp-C8h] BYREF
  int (*v32)(void *); // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  char v34; // [rsp+54h] [rbp-ACh]
  char v35; // [rsp+55h] [rbp-ABh]
  char v36; // [rsp+56h] [rbp-AAh]
  char v37; // [rsp+57h] [rbp-A9h]
  WCHAR *v38; // [rsp+58h] [rbp-A8h]
  char v39; // [rsp+60h] [rbp-A0h]
  __int16 v40; // [rsp+61h] [rbp-9Fh]
  int v41; // [rsp+63h] [rbp-9Dh]
  char v42; // [rsp+67h] [rbp-99h]
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int16 v46; // [rsp+80h] [rbp-80h]
  char v47; // [rsp+82h] [rbp-7Eh]
  char v48; // [rsp+83h] [rbp-7Dh]
  int v49; // [rsp+84h] [rbp-7Ch]
  __int64 v50; // [rsp+88h] [rbp-78h]
  LPWSTR FilePart; // [rsp+90h] [rbp-70h] BYREF
  int (*v52)(void *, const unsigned __int16 *, bool, bool); // [rsp+98h] [rbp-68h]
  int (*v53)(void *, const unsigned __int16 *); // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v55[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v6 = a6;
  v53 = a5;
  v34 = *((_BYTE *)a1 + 26);
  v10 = 0;
  v35 = *((_BYTE *)a1 + 27);
  v36 = *((_BYTE *)a1 + 28);
  v37 = *((_BYTE *)a1 + 30);
  v39 = *((_BYTE *)a1 + 29);
  v48 = *((_BYTE *)a1 + 33);
  v49 = *((_DWORD *)a1 + 9);
  v52 = a4;
  v32 = a6;
  LODWORD(v31) = 0;
  v41 = 0;
  v42 = 0;
  v50 = 0;
  v33 = 64;
  v40 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  if ( a2 && *a2 )
  {
    FilePart = 0;
    if ( GetFullPathNameW(a2, 0x105u, Buffer, &FilePart) - 1 > 0x104 )
    {
      Output("Filename and path are too long.\n");
      return -1;
    }
  }
  else if ( !GetCurrentDirectoryW(0x104u, Buffer) )
  {
    ThrowLastError();
  }
  v38 = Buffer;
  v30 = -1;
  v12 = a3(&v30, &v33);
  v15 = v30;
  v16 = 0;
  if ( v12 >= 0 && v30 != -1 )
  {
    if ( *((_BYTE *)a1 + 24) )
    {
      if ( !*((_BYTE *)a1 + 32) )
        goto LABEL_19;
    }
    else if ( !*((_BYTE *)a1 + 32) )
    {
      goto LABEL_10;
    }
    if ( !*((_BYTE *)a1 + 30) )
    {
      Output("\nDeleting native images:\n");
      v15 = v30;
      v16 = 0;
    }
LABEL_19:
    v22 = 0;
    if ( *((_QWORD *)a1 + 1) && ((v14 = **(_WORD ***)a1, *v14 != 42) || v14[1]) )
    {
      v23 = 0;
      v24 = v52;
      v25 = 0;
      while ( 1 )
      {
        LOBYTE(v14) = *((_BYTE *)a1 + 24) || !*((_BYTE *)a1 + 30) && *((_BYTE *)a1 + 32);
        LOBYTE(v16) = *((_BYTE *)a1 + 32);
        v26 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *, __int64))v24)(
                v15,
                *(_QWORD *)(*(_QWORD *)a1 + 8 * v25),
                v14,
                v16);
        v16 = 0;
        if ( v26 >= 0 )
        {
          if ( !v26 )
            v22 = 1;
        }
        else
        {
          Outputf(L"Error reading fusion cache for %s\n", *(_QWORD *)(*(_QWORD *)a1 + 8 * v25), v14, 0);
          v16 = 0;
        }
        v25 = ++v23;
        if ( (unsigned __int64)v23 >= *((_QWORD *)a1 + 1) )
          break;
        v15 = v30;
      }
      v10 = (unsigned int)v31;
    }
    else
    {
      v27 = *((_BYTE *)a1 + 24) || !*((_BYTE *)a1 + 30) && *((_BYTE *)a1 + 32);
      LOBYTE(v16) = *((_BYTE *)a1 + 32);
      LOBYTE(v14) = v27;
      v28 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *, __int64))a4)(v15, 0, v14, v16);
      v16 = 0;
      v22 = v28 == 0;
    }
    if ( !v22 )
    {
      Output("No matched entries in the cache.\n");
      v10 = -1;
    }
LABEL_44:
    v6 = v32;
    v15 = v30;
    goto LABEL_45;
  }
LABEL_10:
  v17 = 0;
  if ( *((_QWORD *)a1 + 1) )
  {
    v18 = 0;
    while ( 1 )
    {
      v19 = *(_QWORD *)a1;
      v31 = 0;
      FileAttributesW = GetFileAttributesW(*(LPCWSTR *)(v19 + 8 * v18));
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
      {
        v21 = *(WCHAR **)(*(_QWORD *)a1 + 8 * v18);
      }
      else
      {
        if ( GetFullPathNameW(*(LPCWSTR *)(*(_QWORD *)a1 + 8 * v18), 0x105u, v55, &v31) - 1 > 0x104 )
        {
          Output("Filename and path are too long.\n");
          return 0xFFFFFFFFLL;
        }
        v21 = v55;
      }
      v31 = v21;
      v29 = ((__int64 (__fastcall *)(__int64))v53)(v30);
      v16 = 0;
      if ( !v29 )
        v10 = -1;
      v18 = ++v17;
      if ( (unsigned __int64)v17 >= *((_QWORD *)a1 + 1) )
        goto LABEL_44;
    }
  }
LABEL_45:
  if ( v15 != -1 )
    ((void (__fastcall *)(__int64, __int64, _WORD *, __int64))v6)(v15, v13, v14, v16);
  return v10;
}

```

## disassembly

```asm
0x140007bac  push    rbp
0x140007bae  push    rbx
0x140007baf  push    rsi
0x140007bb0  push    rdi
0x140007bb1  push    r12
0x140007bb3  push    r13
0x140007bb5  push    r14
0x140007bb7  push    r15
0x140007bb9  lea     rbp, [rsp-3E8h]
0x140007bc1  sub     rsp, 4E8h
0x140007bc8  mov     rax, cs:__security_cookie
0x140007bcf  xor     rax, rsp
0x140007bd2  mov     [rbp+420h+var_50], rax
0x140007bd9  mov     rax, [rbp+420h+arg_20]
0x140007be0  xor     edi, edi
0x140007be2  mov     r14, [rbp+420h+arg_28]
0x140007be9  mov     r12, r9
0x140007bec  mov     [rbp+420h+var_480], rax
0x140007bf0  mov     rsi, r8
0x140007bf3  mov     al, [rcx+1Ah]
0x140007bf6  mov     r10, rdx
0x140007bf9  mov     [rsp+520h+var_4CC], al
0x140007bfd  mov     rbx, rcx
0x140007c00  mov     al, [rcx+1Bh]
0x140007c03  mov     r13d, edi
0x140007c06  mov     [rsp+520h+var_4CB], al
0x140007c0a  mov     al, [rcx+1Ch]
0x140007c0d  mov     [rsp+520h+var_4CA], al
0x140007c11  mov     al, [rcx+1Eh]
0x140007c14  mov     [rsp+520h+var_4C9], al
0x140007c18  mov     al, [rcx+1Dh]
0x140007c1b  mov     [rsp+520h+var_4C0], al
0x140007c1f  mov     al, [rcx+21h]
0x140007c22  mov     [rbp+420h+var_49D], al
0x140007c25  mov     eax, [rcx+24h]
0x140007c28  mov     [rbp+420h+var_49C], eax
0x140007c2b  mov     [rbp+420h+var_488], r9
0x140007c2f  mov     [rsp+520h+var_4E0], r14
0x140007c34  mov     dword ptr [rsp+520h+var_4E8], edi
0x140007c38  mov     [rsp+520h+var_4BD], edi
0x140007c3c  mov     [rsp+520h+var_4B9], dil
0x140007c41  mov     [rbp+420h+var_498], rdi
0x140007c45  mov     [rsp+520h+var_4D0], 40h ; '@'
0x140007c4d  mov     [rsp+520h+var_4BF], di
0x140007c52  mov     [rsp+520h+var_4B8], rdi
0x140007c57  mov     [rsp+520h+var_4B0], rdi
0x140007c5c  mov     [rsp+520h+var_4A8], rdi
0x140007c61  mov     [rbp+420h+var_4A0], di
0x140007c65  mov     [rbp+420h+var_49E], dil
0x140007c69  test    rdx, rdx
0x140007c6c  jz      short loc_140007CAF
0x140007c6e  cmp     [rdx], di
0x140007c71  jz      short loc_140007CAF
0x140007c73  lea     r9, [rbp+420h+FilePart]; lpFilePart
0x140007c77  mov     [rbp+420h+FilePart], rdi
0x140007c7b  lea     r8, [rbp+420h+Buffer]; lpBuffer
0x140007c7f  mov     edx, 105h; nBufferLength
0x140007c84  mov     rcx, r10; lpFileName
0x140007c87  call    cs:__imp_GetFullPathNameW
0x140007c8d  dec     eax
0x140007c8f  mov     r15d, 104h
0x140007c95  cmp     eax, r15d
0x140007c98  jbe     short loc_140007CCA
0x140007c9a  lea     rcx, aFilenameAndPat; "Filename and path are too long.\n"
0x140007ca1  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140007ca6  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007caa  jmp     loc_140007EAD
0x140007caf  mov     r15d, 104h
0x140007cb5  lea     rdx, [rbp+420h+Buffer]; lpBuffer
0x140007cb9  mov     ecx, r15d; nBufferLength
0x140007cbc  call    cs:__imp_GetCurrentDirectoryW
0x140007cc2  test    eax, eax
0x140007cc4  jz      loc_140007F15
0x140007cca  lea     rax, [rbp+420h+Buffer]
0x140007cce  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007cd2  mov     [rsp+520h+var_4C8], rax
0x140007cd7  lea     rdx, [rsp+520h+var_4D0]
0x140007cdc  mov     rax, rsi
0x140007cdf  mov     [rsp+520h+var_4F0], rdi
0x140007ce4  lea     rcx, [rsp+520h+var_4F0]
0x140007ce9  call    cs:__guard_dispatch_icall_fptr
0x140007cef  mov     rcx, [rsp+520h+var_4F0]
0x140007cf4  xor     r9d, r9d
0x140007cf7  test    eax, eax
0x140007cf9  js      short loc_140007D0C
0x140007cfb  cmp     rcx, rdi
0x140007cfe  jz      short loc_140007D0C
0x140007d00  cmp     [rbx+18h], r9b
0x140007d04  jnz     short loc_140007D79
0x140007d06  cmp     [rbx+20h], r9b
0x140007d0a  jnz     short loc_140007D7F
0x140007d0c  mov     r12d, r9d
0x140007d0f  cmp     [rbx+8], r9
0x140007d13  jbe     loc_140007E9C
0x140007d19  mov     r14, r9
0x140007d1c  mov     esi, 1
0x140007d21  mov     rcx, [rbx]
0x140007d24  mov     [rsp+520h+var_4E8], r9
0x140007d29  mov     rcx, [rcx+r14*8]; lpFileName
0x140007d2d  call    cs:__imp_GetFileAttributesW
0x140007d33  cmp     eax, 0FFFFFFFFh
0x140007d36  jz      loc_140007ED0
0x140007d3c  test    al, 10h
0x140007d3e  jnz     loc_140007ED0
0x140007d44  mov     rcx, [rbx]
0x140007d47  lea     r9, [rsp+520h+var_4E8]; lpFilePart
0x140007d4c  lea     r8, [rbp+420h+var_260]; lpBuffer
0x140007d53  mov     edx, 105h; nBufferLength
0x140007d58  mov     rcx, [rcx+r14*8]; lpFileName
0x140007d5c  call    cs:__imp_GetFullPathNameW
0x140007d62  dec     eax
0x140007d64  cmp     eax, r15d
0x140007d67  ja      loc_140007F05
0x140007d6d  lea     rdx, [rbp+420h+var_260]
0x140007d74  jmp     loc_140007ED7
0x140007d79  cmp     [rbx+20h], r9b
0x140007d7d  jz      short loc_140007D99
0x140007d7f  cmp     [rbx+1Eh], r9b
0x140007d83  jnz     short loc_140007D99
0x140007d85  lea     rcx, aDeletingNative; "\nDeleting native images:\n"
0x140007d8c  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140007d91  mov     rcx, [rsp+520h+var_4F0]
0x140007d96  xor     r9d, r9d
0x140007d99  mov     rdx, [rbx+8]
0x140007d9d  mov     r14d, r9d
0x140007da0  test    rdx, rdx
0x140007da3  jz      loc_140007E44
0x140007da9  mov     rax, [rbx]
0x140007dac  mov     r8, [rax]
0x140007daf  cmp     word ptr [r8], 2Ah ; '*'
0x140007db4  jnz     short loc_140007DC1
0x140007db6  cmp     [r8+2], r9w
0x140007dbb  jz      loc_140007E44
0x140007dc1  mov     r12d, r9d
0x140007dc4  test    rdx, rdx
0x140007dc7  jz      loc_140007E83
0x140007dcd  mov     r13, [rbp+420h+var_488]
0x140007dd1  mov     r15, r9
0x140007dd4  mov     esi, 1
0x140007dd9  cmp     [rbx+18h], r9b
0x140007ddd  jnz     short loc_140007DF0
0x140007ddf  cmp     [rbx+1Eh], r9b
0x140007de3  jnz     short loc_140007DEB
0x140007de5  cmp     [rbx+20h], r9b
0x140007de9  jnz     short loc_140007DF0
0x140007deb  mov     r8b, r9b
0x140007dee  jmp     short loc_140007DF3
0x140007df0  mov     r8b, sil
0x140007df3  mov     rdx, [rbx]
0x140007df6  mov     rax, r13
0x140007df9  mov     r9b, [rbx+20h]
0x140007dfd  mov     rdx, [rdx+r15*8]
0x140007e01  call    cs:__guard_dispatch_icall_fptr
0x140007e07  xor     r9d, r9d
0x140007e0a  test    eax, eax
0x140007e0c  jns     short loc_140007E26
0x140007e0e  mov     rdx, [rbx]
0x140007e11  lea     rcx, aErrorReadingFu; "Error reading fusion cache for %s\n"
0x140007e18  mov     rdx, [rdx+r15*8]
0x140007e1c  call    ?Outputf@@YAXPEAGZZ; Outputf(ushort *,...)
0x140007e21  xor     r9d, r9d
0x140007e24  jmp     short loc_140007E2A
0x140007e26  cmovz   r14d, esi
0x140007e2a  add     r12d, esi
0x140007e2d  mov     r15d, r12d
0x140007e30  cmp     r15, [rbx+8]
0x140007e34  jnb     short loc_140007E3D
0x140007e36  mov     rcx, [rsp+520h+var_4F0]
0x140007e3b  jmp     short loc_140007DD9
0x140007e3d  mov     r13d, dword ptr [rsp+520h+var_4E8]
0x140007e42  jmp     short loc_140007E7E
0x140007e44  cmp     [rbx+18h], r9b
0x140007e48  jnz     short loc_140007E5B
0x140007e4a  cmp     [rbx+1Eh], r9b
0x140007e4e  jnz     short loc_140007E56
0x140007e50  cmp     [rbx+20h], r9b
0x140007e54  jnz     short loc_140007E5B
0x140007e56  mov     sil, r9b
0x140007e59  jmp     short loc_140007E60
0x140007e5b  mov     esi, 1
0x140007e60  mov     r9b, [rbx+20h]
0x140007e64  mov     r8b, sil
0x140007e67  xor     edx, edx
0x140007e69  mov     rax, r12
0x140007e6c  call    cs:__guard_dispatch_icall_fptr
0x140007e72  xor     r9d, r9d
0x140007e75  test    eax, eax
0x140007e77  mov     r14d, r9d
0x140007e7a  setz    r14b
0x140007e7e  test    r14d, r14d
0x140007e81  jnz     short loc_140007E92
0x140007e83  lea     rcx, aNoMatchedEntri; "No matched entries in the cache.\n"
0x140007e8a  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140007e8f  mov     r13d, edi
0x140007e92  mov     r14, [rsp+520h+var_4E0]
0x140007e97  mov     rcx, [rsp+520h+var_4F0]
0x140007e9c  cmp     rcx, rdi
0x140007e9f  jz      short loc_140007EAA
0x140007ea1  mov     rax, r14
0x140007ea4  call    cs:__guard_dispatch_icall_fptr
0x140007eaa  mov     eax, r13d
0x140007ead  mov     rcx, [rbp+420h+var_50]
0x140007eb4  xor     rcx, rsp; StackCookie
0x140007eb7  call    __security_check_cookie
0x140007ebc  add     rsp, 4E8h
0x140007ec3  pop     r15
0x140007ec5  pop     r14
0x140007ec7  pop     r13
0x140007ec9  pop     r12
0x140007ecb  pop     rdi
0x140007ecc  pop     rsi
0x140007ecd  pop     rbx
0x140007ece  pop     rbp
0x140007ecf  retn
0x140007ed0  mov     rax, [rbx]
0x140007ed3  mov     rdx, [rax+r14*8]
0x140007ed7  mov     rcx, [rsp+520h+var_4F0]
0x140007edc  mov     rax, [rbp+420h+var_480]
0x140007ee0  mov     [rsp+520h+var_4E8], rdx
0x140007ee5  call    cs:__guard_dispatch_icall_fptr
0x140007eeb  xor     r9d, r9d
0x140007eee  test    eax, eax
0x140007ef0  cmovz   r13d, edi
0x140007ef4  add     r12d, esi
0x140007ef7  mov     r14d, r12d
0x140007efa  cmp     r14, [rbx+8]
0x140007efe  jnb     short loc_140007E92
0x140007f00  jmp     loc_140007D21
0x140007f05  lea     rcx, aFilenameAndPat; "Filename and path are too long.\n"
0x140007f0c  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140007f11  mov     eax, edi
0x140007f13  jmp     short loc_140007EAD
0x140007f15  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
```
