# CPackage::EmbedReadFromStream(IStream *)

- ea: `0x180007cf8`
- end: `0x1800080a0`
- name: `?EmbedReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `936`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180009fa0`

## callees

- `0x1800079ac`
- `0x180007cf8`
- `0x1800095e0`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000abf0`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000802f`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000802f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007db4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007db4`

## pseudocode

```c
__int64 __fastcall CPackage::EmbedReadFromStream(CPackage *this, struct IStream *a2)
{
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v5; // rcx
  const WCHAR *v6; // rcx
  _DWORD *v7; // rax
  __int64 v8; // rcx
  struct IStreamVtbl *v9; // rax
  struct IStreamVtbl *v10; // rax
  int v11; // esi
  int v12; // eax
  __int64 result; // rax
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  CHAR pszSrc[272]; // [rsp+50h] [rbp-B0h] BYREF

  lpVtbl = a2->lpVtbl;
  v16 = 0;
  v17 = 0;
  ((void (__fastcall *)(struct IStream *, unsigned int *, __int64, int *))lpVtbl->Read)(a2, &v16, 4, &v17);
  if ( v16 >= 0x104 )
    return 2147500037LL;
  ((void (__fastcall *)(struct IStream *, CHAR *, _QWORD, int *))a2->lpVtbl->Read)(a2, pszSrc, v16, &v17);
  ((void (__fastcall *)(struct IStream *, unsigned int *, __int64, int *))a2->lpVtbl->Read)(a2, &v16, 4, &v17);
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
  {
    v6 = *(const WCHAR **)(v5 + 592);
    if ( v6 )
    {
      DeleteFileW(v6);
      operator delete(*(void **)(*((_QWORD *)this + 14) + 592LL));
    }
    operator delete(*((void **)this + 14));
  }
  v7 = operator new(0x270u);
  *((_QWORD *)this + 14) = v7;
  if ( !v7 )
    return 2147942414LL;
  *v7 = 64;
  v8 = *((_QWORD *)this + 14);
  v18 = 0;
  *(_DWORD *)(v8 + 68) = v16;
  *(_DWORD *)(*((_QWORD *)this + 14) + 64LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 14) + 616LL) = 1;
  v9 = a2->lpVtbl;
  v19 = 0;
  if ( ((int (__fastcall *)(struct IStream *, _QWORD, __int64, __int64 *))v9->Seek)(a2, 0, 1, &v19) < 0 )
    return 2147500037LL;
  LODWORD(v18) = v16;
  if ( ((int (__fastcall *)(struct IStream *, __int64, __int64))a2->lpVtbl->Seek)(a2, v18, 1) < 0 )
    return 2147500037LL;
  v10 = a2->lpVtbl;
  v14 = 0;
  v15 = 0;
  v11 = 0;
  if ( ((int (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))v10->Read)(a2, &v15, 4, &v14) >= 0 )
  {
    if ( v14 )
    {
      if ( v15 - 1 <= 0x102 )
      {
        v11 = 1;
        ((void (__fastcall *)(struct IStream *, __int64, _QWORD, unsigned int *))a2->lpVtbl->Read)(
          a2,
          *((_QWORD *)this + 14) + 72LL,
          2 * v15,
          &v14);
        *(_WORD *)(*((_QWORD *)this + 14) + 2 * ((unsigned __int64)v14 >> 1) + 72) = 0;
        if ( ((int (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))a2->lpVtbl->Read)(
               a2,
               &v15,
               4,
               &v14) >= 0
          && v14 == 4
          && v15 - 1 <= 0x102 )
        {
          v12 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, unsigned int *))a2->lpVtbl->Read)(
                  a2,
                  *((_QWORD *)this + 12) + 528LL,
                  2 * v15,
                  &v14);
          *(_WORD *)(*((_QWORD *)this + 12) + 2LL * v15 + 528) = 0;
          if ( v12 >= 0
            && 2LL * v15 == v14
            && ((int (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))a2->lpVtbl->Read)(
                 a2,
                 &v15,
                 4,
                 &v14) >= 0
            && v14 == 4
            && v15 < 0x104 )
          {
            ((void (__fastcall *)(struct IStream *, __int64, _QWORD, unsigned int *))a2->lpVtbl->Read)(
              a2,
              *((_QWORD *)this + 12) + 8LL,
              2 * v15,
              &v14);
            *(_WORD *)(*((_QWORD *)this + 12) + 2LL * v15 + 8) = 0;
          }
        }
      }
    }
  }
  LODWORD(v18) = v19;
  if ( ((int (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, v18, 0, 0) < 0 )
    return 2147500037LL;
  if ( !v11 )
    SHAnsiToUnicode(pszSrc, (PWSTR)(*((_QWORD *)this + 14) + 72LL), 260);
  result = CPackage::CreateTempFileName(this);
  if ( (int)result >= 0 )
  {
    if ( CopyStreamToFile(
           a2,
           *(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL),
           *(_DWORD *)(*((_QWORD *)this + 14) + 68LL)) >= 0 )
    {
      MarkFileUnsafe(*(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL));
      return 0;
    }
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007cf8  mov     [rsp-8+arg_10], rbx
0x180007cfd  mov     [rsp-8+arg_18], rsi
0x180007d02  push    rbp
0x180007d03  push    rdi
0x180007d04  push    r15
0x180007d06  lea     rbp, [rsp-70h]
0x180007d0b  sub     rsp, 170h
0x180007d12  mov     rax, cs:__security_cookie
0x180007d19  xor     rax, rsp
0x180007d1c  mov     [rbp+80h+var_20], rax
0x180007d20  mov     rax, [rdx]
0x180007d23  lea     r9, [rsp+180h+var_144]
0x180007d28  mov     rbx, rdx
0x180007d2b  mov     [rsp+180h+var_148], 0
0x180007d33  mov     rdi, rcx
0x180007d36  mov     [rsp+180h+var_144], 0
0x180007d3e  mov     r15d, 4
0x180007d44  lea     rdx, [rsp+180h+var_148]
0x180007d49  mov     rax, [rax+18h]
0x180007d4d  mov     r8d, r15d
0x180007d50  mov     rcx, rbx
0x180007d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d58  mov     r8d, [rsp+180h+var_148]
0x180007d5d  cmp     r8d, 104h
0x180007d64  jnb     loc_180008077
0x180007d6a  mov     rax, [rbx]
0x180007d6d  lea     r9, [rsp+180h+var_144]
0x180007d72  lea     rdx, [rsp+180h+pszSrc]
0x180007d77  mov     rcx, rbx
0x180007d7a  mov     rax, [rax+18h]
0x180007d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d83  mov     rax, [rbx]
0x180007d86  lea     r9, [rsp+180h+var_144]
0x180007d8b  mov     r8d, r15d
0x180007d8e  lea     rdx, [rsp+180h+var_148]
0x180007d93  mov     rcx, rbx
0x180007d96  mov     rax, [rax+18h]
0x180007d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9f  mov     rcx, [rdi+70h]
0x180007da3  test    rcx, rcx
0x180007da6  jz      short loc_180007DD3
0x180007da8  mov     rcx, [rcx+250h]; lpFileName
0x180007daf  test    rcx, rcx
0x180007db2  jz      short loc_180007DCA
0x180007db4  call    cs:__imp_DeleteFileW
0x180007dba  mov     rcx, [rdi+70h]
0x180007dbe  mov     rcx, [rcx+250h]; lpMem
0x180007dc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007dca  mov     rcx, [rdi+70h]; lpMem
0x180007dce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007dd3  mov     ecx, 270h; unsigned __int64
0x180007dd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ddd  mov     [rdi+70h], rax
0x180007de1  test    rax, rax
0x180007de4  jz      loc_180008070
0x180007dea  mov     dword ptr [rax], 40h ; '@'
0x180007df0  lea     r9, [rsp+180h+var_138]
0x180007df5  mov     rcx, [rdi+70h]
0x180007df9  mov     r8d, 1
0x180007dff  mov     eax, [rsp+180h+var_148]
0x180007e03  mov     [rsp+180h+var_140], 0
0x180007e0c  mov     rdx, [rsp+180h+var_140]
0x180007e11  mov     [rcx+44h], eax
0x180007e14  mov     rcx, rbx
0x180007e17  mov     rax, [rdi+70h]
0x180007e1b  mov     dword ptr [rax+40h], 0
0x180007e22  mov     rax, [rdi+70h]
0x180007e26  mov     dword ptr [rax+268h], 1
0x180007e30  mov     rax, [rbx]
0x180007e33  mov     [rsp+180h+var_138], 0
0x180007e3c  mov     rax, [rax+28h]
0x180007e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e45  test    eax, eax
0x180007e47  js      loc_180008077
0x180007e4d  mov     eax, [rsp+180h+var_148]
0x180007e51  xor     r9d, r9d
0x180007e54  mov     dword ptr [rsp+180h+var_140], eax
0x180007e58  mov     rcx, rbx
0x180007e5b  mov     rax, [rbx]
0x180007e5e  mov     rdx, [rsp+180h+var_140]
0x180007e63  lea     r8d, [r9+1]
0x180007e67  mov     rax, [rax+28h]
0x180007e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e70  test    eax, eax
0x180007e72  js      loc_180008077
0x180007e78  mov     rax, [rbx]
0x180007e7b  lea     r9, [rsp+180h+var_150]
0x180007e80  mov     r8d, r15d
0x180007e83  mov     [rsp+180h+var_150], 0
0x180007e8b  lea     rdx, [rsp+180h+var_14C]
0x180007e90  mov     [rsp+180h+var_14C], 0
0x180007e98  mov     rcx, rbx
0x180007e9b  xor     esi, esi
0x180007e9d  mov     rax, [rax+18h]
0x180007ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea6  test    eax, eax
0x180007ea8  js      loc_180007FF2
0x180007eae  cmp     [rsp+180h+var_150], esi
0x180007eb2  jz      loc_180007FF2
0x180007eb8  mov     r8d, [rsp+180h+var_14C]
0x180007ebd  lea     eax, [r8-1]
0x180007ec1  cmp     eax, 102h
0x180007ec6  ja      loc_180007FF2
0x180007ecc  mov     rax, [rbx]
0x180007ecf  lea     r9, [rsp+180h+var_150]
0x180007ed4  mov     rdx, [rdi+70h]
0x180007ed8  add     r8d, r8d
0x180007edb  add     rdx, 48h ; 'H'
0x180007edf  mov     rcx, rbx
0x180007ee2  mov     esi, 1
0x180007ee7  mov     rax, [rax+18h]
0x180007eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ef0  mov     edx, [rsp+180h+var_150]
0x180007ef4  lea     r9, [rsp+180h+var_150]
0x180007ef9  mov     rcx, [rdi+70h]
0x180007efd  xor     eax, eax
0x180007eff  shr     rdx, 1
0x180007f02  mov     r8d, r15d
0x180007f05  mov     [rcx+rdx*2+48h], ax
0x180007f0a  lea     rdx, [rsp+180h+var_14C]
0x180007f0f  mov     rax, [rbx]
0x180007f12  mov     rcx, rbx
0x180007f15  mov     rax, [rax+18h]
0x180007f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1e  test    eax, eax
0x180007f20  js      loc_180007FF2
0x180007f26  cmp     [rsp+180h+var_150], r15d
0x180007f2b  jnz     loc_180007FF2
0x180007f31  mov     r8d, [rsp+180h+var_14C]
0x180007f36  lea     eax, [r8-1]
0x180007f3a  cmp     eax, 102h
0x180007f3f  ja      loc_180007FF2
0x180007f45  mov     rax, [rbx]
0x180007f48  lea     r9, [rsp+180h+var_150]
0x180007f4d  mov     rdx, [rdi+60h]
0x180007f51  add     r8d, r8d
0x180007f54  add     rdx, 210h
0x180007f5b  mov     rcx, rbx
0x180007f5e  mov     rax, [rax+18h]
0x180007f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f67  mov     r8d, [rsp+180h+var_14C]
0x180007f6c  xor     ecx, ecx
0x180007f6e  mov     rdx, [rdi+60h]
0x180007f72  mov     [rdx+r8*2+210h], cx
0x180007f7b  test    eax, eax
0x180007f7d  js      short loc_180007FF2
0x180007f7f  mov     ecx, [rsp+180h+var_14C]
0x180007f83  mov     eax, [rsp+180h+var_150]
0x180007f87  add     rcx, rcx
0x180007f8a  cmp     rcx, rax
0x180007f8d  jnz     short loc_180007FF2
0x180007f8f  mov     rax, [rbx]
0x180007f92  lea     r9, [rsp+180h+var_150]
0x180007f97  mov     r8d, r15d
0x180007f9a  lea     rdx, [rsp+180h+var_14C]
0x180007f9f  mov     rcx, rbx
0x180007fa2  mov     rax, [rax+18h]
0x180007fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fab  test    eax, eax
0x180007fad  js      short loc_180007FF2
0x180007faf  cmp     [rsp+180h+var_150], r15d
0x180007fb4  jnz     short loc_180007FF2
0x180007fb6  mov     r8d, [rsp+180h+var_14C]
0x180007fbb  cmp     r8d, 104h
0x180007fc2  jnb     short loc_180007FF2
0x180007fc4  mov     rax, [rbx]
0x180007fc7  lea     r9, [rsp+180h+var_150]
0x180007fcc  mov     rdx, [rdi+60h]
0x180007fd0  add     r8d, r8d
0x180007fd3  add     rdx, 8
0x180007fd7  mov     rcx, rbx
0x180007fda  mov     rax, [rax+18h]
0x180007fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe3  mov     edx, [rsp+180h+var_14C]
0x180007fe7  xor     eax, eax
0x180007fe9  mov     rcx, [rdi+60h]
0x180007fed  mov     [rcx+rdx*2+8], ax
0x180007ff2  mov     eax, dword ptr [rsp+180h+var_138]
0x180007ff6  xor     r9d, r9d
0x180007ff9  mov     dword ptr [rsp+180h+var_140], eax
0x180007ffd  xor     r8d, r8d
0x180008000  mov     rax, [rbx]
0x180008003  mov     rcx, rbx
0x180008006  mov     rdx, [rsp+180h+var_140]
0x18000800b  mov     rax, [rax+28h]
0x18000800f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008014  test    eax, eax
0x180008016  js      short loc_180008077
0x180008018  test    esi, esi
0x18000801a  jnz     short loc_180008035
0x18000801c  mov     rdx, [rdi+70h]
0x180008020  lea     rcx, [rsp+180h+pszSrc]; pszSrc
0x180008025  add     rdx, 48h ; 'H'; pwszDst
0x180008029  mov     r8d, 104h; cwchBuf
0x18000802f  call    cs:__imp_SHAnsiToUnicode
0x180008035  mov     rcx, rdi; this
0x180008038  call    ?CreateTempFileName@CPackage@@IEAAJXZ; CPackage::CreateTempFileName(void)
0x18000803d  test    eax, eax
0x18000803f  js      short loc_18000807C
0x180008041  mov     rdx, [rdi+70h]
0x180008045  mov     rcx, rbx; struct IStream *
0x180008048  mov     r8d, [rdx+44h]; unsigned int
0x18000804c  mov     rdx, [rdx+250h]; unsigned __int16 *
0x180008053  call    ?CopyStreamToFile@@YAJPEAUIStream@@PEBGK@Z; CopyStreamToFile(IStream *,ushort const *,ulong)
0x180008058  test    eax, eax
0x18000805a  js      short loc_180008077
0x18000805c  mov     rcx, [rdi+70h]
0x180008060  mov     rcx, [rcx+250h]; unsigned __int16 *
0x180008067  call    ?MarkFileUnsafe@@YAJPEBG@Z; MarkFileUnsafe(ushort const *)
0x18000806c  xor     eax, eax
0x18000806e  jmp     short loc_18000807C
0x180008070  mov     eax, 8007000Eh
0x180008075  jmp     short loc_18000807C
0x180008077  mov     eax, 80004005h
0x18000807c  mov     rcx, [rbp+80h+var_20]
0x180008080  xor     rcx, rsp; StackCookie
0x180008083  call    __security_check_cookie
0x180008088  lea     r11, [rsp+180h+var_10]
0x180008090  mov     rbx, [r11+30h]
0x180008094  mov     rsi, [r11+38h]
0x180008098  mov     rsp, r11
0x18000809b  pop     r15
0x18000809d  pop     rdi
0x18000809e  pop     rbp
0x18000809f  retn
```
