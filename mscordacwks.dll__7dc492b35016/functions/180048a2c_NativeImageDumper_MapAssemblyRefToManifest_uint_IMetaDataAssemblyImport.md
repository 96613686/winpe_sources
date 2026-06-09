# NativeImageDumper::MapAssemblyRefToManifest(uint,IMetaDataAssemblyImport *)

- ea: `0x180048a2c`
- end: `0x180048fb0`
- name: `?MapAssemblyRefToManifest@NativeImageDumper@@AEAAIIPEAUIMetaDataAssemblyImport@@@Z`
- size: `1412`
- prototype: `unsigned int __fastcall(NativeImageDumper *__hidden this, unsigned int, struct IMetaDataAssemblyImport *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800476dc`
- `0x180048870`

## callees

- `0x180042a8c`
- `0x180048a2c`
- `0x18007344c`
- `0x180076604`
- `0x1800f0d20`
- `0x1800f2940`
- `0x1801043f0`
- `0x180105e80`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180048eef`
- `KERNEL32!HeapFree` at `0x180048eef`
- `KERNEL32!GetProcessHeap` at `0x180048eda`
- `KERNEL32!GetProcessHeap` at `0x180048eda`

## string_xrefs

- `0x180048f72`: `MapAssemblyRefToManifest: found %S with version %d.%d in manifest.  Wanted version %d.%d.\n`
- `0x180048e9f`: `MapAssemblyRefToManifest could not find token for %S, Version=%d.%d, PublicKeyToken=%S\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::MapAssemblyRefToManifest(
        NativeImageDumper *this,
        unsigned int a2,
        struct IMetaDataAssemblyImport *a3)
{
  unsigned int v4; // ebx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  const wchar_t *v10; // r15
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  void *v28; // rsp
  int v29; // eax
  const wchar_t *v30; // rcx
  int v31; // r9d
  int v32; // edx
  int v33; // eax
  int v34; // eax
  int *v35; // rax
  int v36; // edx
  int v37; // ecx
  unsigned __int16 v38; // r14
  unsigned __int16 v39; // si
  unsigned __int16 v40; // bx
  void *v41; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v43; // [rsp+20h] [rbp-40h]
  __int64 v44; // [rsp+28h] [rbp-38h]
  __int64 v45; // [rsp+30h] [rbp-30h]
  unsigned int v46; // [rsp+60h] [rbp+0h] BYREF
  unsigned int v47; // [rsp+64h] [rbp+4h] BYREF
  size_t Size; // [rsp+68h] [rbp+8h] BYREF
  __int64 v49; // [rsp+70h] [rbp+10h] BYREF
  unsigned int v50; // [rsp+78h] [rbp+18h] BYREF
  void *Buf1; // [rsp+80h] [rbp+20h] BYREF
  __int128 v52; // [rsp+88h] [rbp+28h] BYREF
  __int128 v53; // [rsp+98h] [rbp+38h]
  __int128 v54; // [rsp+A8h] [rbp+48h]
  __int64 v55; // [rsp+B8h] [rbp+58h]
  _BYTE v56[4]; // [rsp+C0h] [rbp+60h] BYREF
  _BYTE v57[4]; // [rsp+C4h] [rbp+64h] BYREF
  void *Buf2; // [rsp+C8h] [rbp+68h] BYREF
  _OWORD v59[3]; // [rsp+D0h] [rbp+70h] BYREF
  __int64 v60; // [rsp+100h] [rbp+A0h]
  _BYTE v61[8]; // [rsp+108h] [rbp+A8h] BYREF
  int v62; // [rsp+110h] [rbp+B0h] BYREF
  __int64 v63; // [rsp+114h] [rbp+B4h]
  LPVOID lpMem; // [rsp+120h] [rbp+C0h]
  __int16 v65; // [rsp+128h] [rbp+C8h] BYREF

  v4 = a2;
  if ( (a2 & 0xFF000000) == 0x20000000 )
    return v4;
  v47 = 0;
  v49 = 0;
  v7 = *(_QWORD *)a3;
  while ( 1 )
  {
    v46 = 0;
    v8 = (*(__int64 (__fastcall **)(struct IMetaDataAssemblyImport *, __int64 *, size_t *, __int64, unsigned int *))(v7 + 64))(
           a3,
           &v49,
           &Size,
           1,
           &v46);
    if ( v8 < 0 )
      ThrowHR(v8);
    v7 = *(_QWORD *)a3;
    if ( !v46 )
      break;
    ++v47;
  }
  (*(void (__fastcall **)(struct IMetaDataAssemblyImport *, __int64))(v7 + 120))(a3, v49);
  if ( (v4 & 0xFFFFFF) > v47 )
    return v4 - v47 - 1;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IMetaDataAssemblyImport *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, char *, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3 + 32LL))(
         a3,
         v4,
         0,
         0,
         0,
         0,
         (char *)&Size + 4,
         &v52,
         0,
         0,
         0);
  if ( v9 < 0 )
    ThrowHR(v9);
  v10 = 0;
  if ( HIDWORD(Size) )
  {
    v11 = 2LL * HIDWORD(Size);
    v12 = v11 + 15;
    if ( v11 + 15 < v11 )
      v12 = 0xFFFFFFFFFFFFFF0LL;
    v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
    v14 = alloca(v13);
    v15 = alloca(v13);
    v10 = (const wchar_t *)&v46;
  }
  if ( (_DWORD)v53 )
  {
    v16 = 2LL * (unsigned int)v53;
    v17 = v16 + 15;
    if ( v16 + 15 < v16 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
    v19 = alloca(v18);
    v20 = alloca(v18);
    *((_QWORD *)&v52 + 1) = &v46;
  }
  if ( (_DWORD)v54 )
  {
    v21 = 4LL * (unsigned int)v54;
    v22 = v21 + 15;
    if ( v21 + 15 < v21 )
      v22 = 0xFFFFFFFFFFFFFF0LL;
    v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
    v24 = alloca(v23);
    v25 = alloca(v23);
    *((_QWORD *)&v53 + 1) = &v46;
  }
  if ( (_DWORD)v55 )
  {
    v26 = 12LL * (unsigned int)v55;
    v27 = v26 + 15;
    if ( v26 + 15 < v26 )
      v27 = 0xFFFFFFFFFFFFFF0LL;
    v28 = alloca(v27 & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)&v54 + 1) = &v46;
  }
  v29 = (*(__int64 (__fastcall **)(struct IMetaDataAssemblyImport *, _QWORD, void **, unsigned int *, const wchar_t *, _DWORD, _QWORD, __int128 *, _BYTE *, _BYTE *, _BYTE *))(*(_QWORD *)a3 + 32LL))(
          a3,
          v4,
          &Buf1,
          &v50,
          v10,
          HIDWORD(Size),
          0,
          &v52,
          v61,
          v57,
          v56);
  if ( v29 < 0 )
    ThrowHR(v29);
  v30 = v10;
  do
  {
    v31 = *(const wchar_t *)((char *)v30 + *((_QWORD *)this + 14) - (_QWORD)v10);
    v32 = *v30 - v31;
    if ( v32 )
      break;
    ++v30;
  }
  while ( v31 );
  if ( v32 )
  {
    v4 = 587202560;
    v49 = 0;
    while ( 1 )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *, __int64, unsigned int *))(**((_QWORD **)this + 32)
                                                                                                  + 64LL))(
              *((_QWORD *)this + 32),
              &v49,
              &v46,
              1,
              &v47);
      if ( v33 < 0 )
        ThrowHR(v33);
      if ( !v47 )
        break;
      Size = 0x8000000000LL;
      memset(v59, 0, sizeof(v59));
      v60 = 0;
      v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void **, size_t *, int *, int, char *, _OWORD *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 32) + 32LL))(
              *((_QWORD *)this + 32),
              v46,
              &Buf2,
              &Size,
              &v62,
              128,
              (char *)&Size + 4,
              v59,
              0,
              0,
              0);
      if ( v34 < 0 )
        ThrowHR(v34);
      v35 = &v62;
      do
      {
        v36 = *(unsigned __int16 *)((char *)v35 + (char *)v10 - (char *)&v62);
        v37 = *(unsigned __int16 *)v35 - v36;
        if ( v37 )
          break;
        v35 = (int *)((char *)v35 + 2);
      }
      while ( v36 );
      if ( !v37 )
      {
        if ( v50 == (_DWORD)Size && !memcmp(Buf1, Buf2, (unsigned int)Size) )
        {
          v38 = v59[0];
          v39 = v52;
          v40 = WORD1(v52);
          if ( LODWORD(v59[0]) == (_DWORD)v52 )
            goto LABEL_44;
        }
        else
        {
          v40 = WORD1(v52);
          v39 = v52;
          v38 = v59[0];
        }
        if ( !wcscmp(v10, L"mscorlib") )
          goto LABEL_44;
        if ( v39 != 255 || v40 != 255 || DWORD1(v52) != 16711935 )
        {
          LODWORD(v45) = v40;
          LODWORD(v44) = v39;
          LODWORD(v43) = WORD1(v59[0]);
          (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
            *((_QWORD *)this + 17),
            "MapAssemblyRefToManifest: found %S with version %d.%d in manifest.  Wanted version %d.%d.\n",
            v10,
            v38,
            v43,
            v44,
            v45);
LABEL_44:
          v4 = v46;
          break;
        }
        v4 = v46;
      }
    }
    (*(void (__fastcall **)(struct IMetaDataAssemblyImport *, __int64))(*(_QWORD *)a3 + 120LL))(a3, v49);
    if ( v4 == 587202560 )
    {
      v63 = 128;
      lpMem = &v65;
      v62 = 2;
      v65 = 0;
      appendByteArray((struct SString *)&v62, (const unsigned __int8 *)Buf1, v50);
      SString::ConvertToUnicode((SString *)&v62);
      LODWORD(v43) = WORD1(v52);
      (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
        *((_QWORD *)this + 17),
        "MapAssemblyRefToManifest could not find token for %S, Version=%d.%d, PublicKeyToken=%S\n",
        v10,
        (unsigned __int16)v52,
        v43,
        lpMem);
      if ( (v63 & 0x800000000LL) != 0 )
      {
        v41 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v41);
        }
      }
    }
    return v4;
  }
  return 0x20000000;
}

```

## disassembly

```asm
0x180048a2c  push    rbp
0x180048a2e  push    rsi
0x180048a2f  push    rdi
0x180048a30  push    r12
0x180048a32  push    r13
0x180048a34  push    r14
0x180048a36  push    r15
0x180048a38  sub     rsp, 220h
0x180048a3f  lea     rbp, [rsp+60h]
0x180048a44  mov     [rbp+1F0h+arg_18], rbx
0x180048a4b  mov     rax, cs:__security_cookie
0x180048a52  xor     rax, rbp
0x180048a55  mov     [rbp+1F0h+var_40], rax
0x180048a5c  mov     rdi, r8
0x180048a5f  mov     ebx, edx
0x180048a61  mov     r13, rcx
0x180048a64  and     edx, 0FF000000h
0x180048a6a  mov     esi, 20000000h
0x180048a6f  cmp     edx, esi
0x180048a71  jnz     short loc_180048A9E
0x180048a73  mov     eax, ebx
0x180048a75  mov     rcx, [rbp+1F0h+var_40]
0x180048a7c  xor     rcx, rbp; StackCookie
0x180048a7f  call    __security_check_cookie
0x180048a84  mov     rbx, [rbp+1F0h+arg_18]
0x180048a8b  lea     rsp, [rbp+1C0h]
0x180048a92  pop     r15
0x180048a94  pop     r14
0x180048a96  pop     r13
0x180048a98  pop     r12
0x180048a9a  pop     rdi
0x180048a9b  pop     rsi
0x180048a9c  pop     rbp
0x180048a9d  retn
0x180048a9e  xor     r12d, r12d
0x180048aa1  mov     [rbp+1F0h+var_1EC], r12d
0x180048aa5  mov     [rbp+1F0h+var_1E0], r12
0x180048aa9  mov     rax, [r8]
0x180048aac  lea     r14d, [r12+1]
0x180048ab1  jmp     short loc_180048AC0
0x180048ab3  mov     rax, [rdi]
0x180048ab6  cmp     [rbp+1F0h+var_1F0], r12d
0x180048aba  jz      short loc_180048AEF
0x180048abc  add     [rbp+1F0h+var_1EC], r14d
0x180048ac0  lea     rcx, [rbp+1F0h+var_1F0]
0x180048ac4  mov     [rsp+250h+var_230], rcx
0x180048ac9  mov     [rbp+1F0h+var_1F0], r12d
0x180048acd  mov     r9d, r14d
0x180048ad0  lea     r8, [rbp+1F0h+Size]
0x180048ad4  lea     rdx, [rbp+1F0h+var_1E0]
0x180048ad8  mov     rcx, rdi
0x180048adb  mov     rax, [rax+40h]
0x180048adf  call    cs:__guard_dispatch_icall_fptr
0x180048ae5  test    eax, eax
0x180048ae7  js      loc_180048F90
0x180048aed  jmp     short loc_180048AB3
0x180048aef  mov     rdx, [rbp+1F0h+var_1E0]
0x180048af3  mov     rcx, rdi
0x180048af6  mov     rax, [rax+78h]
0x180048afa  call    cs:__guard_dispatch_icall_fptr
0x180048b00  mov     eax, ebx
0x180048b02  and     eax, 0FFFFFFh
0x180048b07  cmp     eax, [rbp+1F0h+var_1EC]
0x180048b0a  jbe     short loc_180048B17
0x180048b0c  sub     ebx, [rbp+1F0h+var_1EC]
0x180048b0f  sub     ebx, r14d
0x180048b12  jmp     loc_180048A73
0x180048b17  xorps   xmm0, xmm0
0x180048b1a  xor     eax, eax
0x180048b1c  movups  [rbp+1F0h+var_1C8], xmm0
0x180048b20  movups  [rbp+1F0h+var_1B8], xmm0
0x180048b24  movups  [rbp+1F0h+var_1A8], xmm0
0x180048b28  mov     [rbp+1F0h+var_198], rax
0x180048b2c  mov     rax, [rdi]
0x180048b2f  mov     [rsp+250h+var_200], r12
0x180048b34  mov     [rsp+250h+var_208], r12
0x180048b39  mov     [rsp+250h+var_210], r12
0x180048b3e  lea     rcx, [rbp+1F0h+var_1C8]
0x180048b42  mov     [rsp+250h+var_218], rcx
0x180048b47  lea     rcx, [rbp+1F0h+Size+4]
0x180048b4b  mov     [rsp+250h+var_220], rcx
0x180048b50  mov     dword ptr [rsp+250h+var_228], r12d
0x180048b55  mov     [rsp+250h+var_230], r12
0x180048b5a  xor     r9d, r9d
0x180048b5d  xor     r8d, r8d
0x180048b60  mov     edx, ebx
0x180048b62  mov     rcx, rdi
0x180048b65  mov     rax, [rax+20h]
0x180048b69  call    cs:__guard_dispatch_icall_fptr
0x180048b6f  test    eax, eax
0x180048b71  js      loc_180048FA0
0x180048b77  mov     r15, r12
0x180048b7a  mov     r8, 0FFFFFFFFFFFFFF0h
0x180048b84  mov     edx, dword ptr [rbp+1F0h+Size+4]
0x180048b87  test    edx, edx
0x180048b89  jz      short loc_180048BB0
0x180048b8b  mov     eax, edx
0x180048b8d  add     rax, rax
0x180048b90  lea     rcx, [rax+0Fh]
0x180048b94  cmp     rcx, rax
0x180048b97  ja      short loc_180048B9C
0x180048b99  mov     rcx, r8
0x180048b9c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180048ba0  mov     rax, rcx
0x180048ba3  call    _alloca_probe
0x180048ba8  sub     rsp, rcx
0x180048bab  lea     r15, [rsp+250h+var_1F0]
0x180048bb0  mov     eax, dword ptr [rbp+1F0h+var_1B8]
0x180048bb3  test    eax, eax
0x180048bb5  jz      short loc_180048BDE
0x180048bb7  add     rax, rax
0x180048bba  lea     rcx, [rax+0Fh]
0x180048bbe  cmp     rcx, rax
0x180048bc1  ja      short loc_180048BC6
0x180048bc3  mov     rcx, r8
0x180048bc6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180048bca  mov     rax, rcx
0x180048bcd  call    _alloca_probe
0x180048bd2  sub     rsp, rcx
0x180048bd5  lea     rax, [rsp+250h+var_1F0]
0x180048bda  mov     qword ptr [rbp+1F0h+var_1C8+8], rax
0x180048bde  mov     eax, dword ptr [rbp+1F0h+var_1A8]
0x180048be1  test    eax, eax
0x180048be3  jz      short loc_180048C0D
0x180048be5  shl     rax, 2
0x180048be9  lea     rcx, [rax+0Fh]
0x180048bed  cmp     rcx, rax
0x180048bf0  ja      short loc_180048BF5
0x180048bf2  mov     rcx, r8
0x180048bf5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180048bf9  mov     rax, rcx
0x180048bfc  call    _alloca_probe
0x180048c01  sub     rsp, rcx
0x180048c04  lea     rax, [rsp+250h+var_1F0]
0x180048c09  mov     qword ptr [rbp+1F0h+var_1B8+8], rax
0x180048c0d  mov     rax, [rbp+1F0h+var_198]
0x180048c11  test    eax, eax
0x180048c13  jz      short loc_180048C40
0x180048c15  mov     eax, eax
0x180048c17  lea     rcx, [rax+rax*2]
0x180048c1b  shl     rcx, 2
0x180048c1f  lea     rax, [rcx+0Fh]
0x180048c23  cmp     rax, rcx
0x180048c26  ja      short loc_180048C2B
0x180048c28  mov     rax, r8
0x180048c2b  and     rax, 0FFFFFFFFFFFFFFF0h
0x180048c2f  call    _alloca_probe
0x180048c34  sub     rsp, rax
0x180048c37  lea     rax, [rsp+250h+var_1F0]
0x180048c3c  mov     qword ptr [rbp+1F0h+var_1A8+8], rax
0x180048c40  mov     rax, [rdi]
0x180048c43  lea     rcx, [rbp+1F0h+var_190]
0x180048c47  mov     [rsp+250h+var_200], rcx
0x180048c4c  lea     rcx, [rbp+1F0h+var_18C]
0x180048c50  mov     [rsp+250h+var_208], rcx
0x180048c55  lea     rcx, [rbp+1F0h+var_148]
0x180048c5c  mov     [rsp+250h+var_210], rcx
0x180048c61  lea     rcx, [rbp+1F0h+var_1C8]
0x180048c65  mov     [rsp+250h+var_218], rcx
0x180048c6a  mov     [rsp+250h+var_220], r12
0x180048c6f  mov     dword ptr [rsp+250h+var_228], edx
0x180048c73  mov     [rsp+250h+var_230], r15
0x180048c78  lea     r9, [rbp+1F0h+var_1D8]
0x180048c7c  lea     r8, [rbp+1F0h+Buf1]
0x180048c80  mov     edx, ebx
0x180048c82  mov     rcx, rdi
0x180048c85  mov     rax, [rax+20h]
0x180048c89  call    cs:__guard_dispatch_icall_fptr
0x180048c8f  test    eax, eax
0x180048c91  js      loc_180048FA8
0x180048c97  mov     rcx, r15
0x180048c9a  mov     r8, [r13+70h]
0x180048c9e  sub     r8, r15
0x180048ca1  movzx   edx, word ptr [rcx]
0x180048ca4  movzx   r9d, word ptr [rcx+r8]
0x180048ca9  sub     edx, r9d
0x180048cac  jnz     short loc_180048CB7
0x180048cae  add     rcx, 2
0x180048cb2  test    r9d, r9d
0x180048cb5  jnz     short loc_180048CA1
0x180048cb7  test    edx, edx
0x180048cb9  jnz     short loc_180048CC2
0x180048cbb  mov     eax, esi
0x180048cbd  jmp     loc_180048A75
0x180048cc2  mov     ebx, 23000000h
0x180048cc7  mov     [rbp+1F0h+var_1E0], r12
0x180048ccb  lea     rdx, [rbp+1F0h+var_1EC]
0x180048ccf  mov     rcx, [r13+100h]
0x180048cd6  mov     [rsp+250h+var_230], rdx
0x180048cdb  mov     rax, [rcx]
0x180048cde  mov     r9d, r14d
0x180048ce1  lea     r8, [rbp+1F0h+var_1F0]
0x180048ce5  lea     rdx, [rbp+1F0h+var_1E0]
0x180048ce9  mov     rax, [rax+40h]
0x180048ced  call    cs:__guard_dispatch_icall_fptr
0x180048cf3  test    eax, eax
0x180048cf5  js      loc_180048F98
0x180048cfb  cmp     [rbp+1F0h+var_1EC], r12d
0x180048cff  jz      loc_180048DFB
0x180048d05  mov     dword ptr [rbp+1F0h+Size], r12d
0x180048d09  mov     dword ptr [rbp+1F0h+Size+4], 80h
0x180048d10  xorps   xmm0, xmm0
0x180048d13  xor     eax, eax
0x180048d15  movups  [rbp+1F0h+var_180], xmm0
0x180048d19  movups  [rbp+1F0h+var_170], xmm0
0x180048d20  movups  [rbp+1F0h+var_160], xmm0
0x180048d27  mov     [rbp+1F0h+var_150], rax
0x180048d2e  mov     rcx, [r13+100h]
0x180048d35  mov     rax, [rcx]
0x180048d38  mov     [rsp+250h+var_200], r12
0x180048d3d  mov     [rsp+250h+var_208], r12
0x180048d42  mov     [rsp+250h+var_210], r12
0x180048d47  lea     rdx, [rbp+1F0h+var_180]
0x180048d4b  mov     [rsp+250h+var_218], rdx
0x180048d50  lea     rdx, [rbp+1F0h+Size+4]
0x180048d54  mov     [rsp+250h+var_220], rdx
0x180048d59  mov     dword ptr [rsp+250h+var_228], 80h
0x180048d61  lea     rdx, [rbp+1F0h+var_140]
0x180048d68  mov     [rsp+250h+var_230], rdx
0x180048d6d  lea     r9, [rbp+1F0h+Size]
0x180048d71  lea     r8, [rbp+1F0h+Buf2]
0x180048d75  mov     edx, [rbp+1F0h+var_1F0]
0x180048d78  mov     rax, [rax+20h]
0x180048d7c  call    cs:__guard_dispatch_icall_fptr
0x180048d82  test    eax, eax
0x180048d84  js      loc_180048F88
0x180048d8a  lea     rax, [rbp+1F0h+var_140]
0x180048d91  mov     r8, r15
0x180048d94  sub     r8, rax
0x180048d97  movzx   ecx, word ptr [rax]
0x180048d9a  movzx   edx, word ptr [rax+r8]
0x180048d9f  sub     ecx, edx
0x180048da1  jnz     short loc_180048DAB
0x180048da3  add     rax, 2
0x180048da7  test    edx, edx
0x180048da9  jnz     short loc_180048D97
0x180048dab  test    ecx, ecx
0x180048dad  jnz     loc_180048CCB
0x180048db3  mov     eax, dword ptr [rbp+1F0h+Size]
0x180048db6  cmp     [rbp+1F0h+var_1D8], eax
0x180048db9  jnz     loc_180048EFA
0x180048dbf  mov     r8d, eax; Size
0x180048dc2  mov     rdx, [rbp+1F0h+Buf2]; Buf2
0x180048dc6  mov     rcx, [rbp+1F0h+Buf1]; Buf1
0x180048dca  call    memcmp
0x180048dcf  test    eax, eax
0x180048dd1  jnz     loc_180048EFA
0x180048dd7  movzx   r14d, word ptr [rbp+1F0h+var_180]
0x180048ddc  movzx   esi, word ptr [rbp+1F0h+var_1C8]
0x180048de0  movzx   ebx, word ptr [rbp+1F0h+var_1C8+2]
0x180048de4  cmp     r14w, si
0x180048de8  jnz     loc_180048F07
0x180048dee  cmp     word ptr [rbp+1F0h+var_180+2], bx
0x180048df2  jnz     loc_180048F07
0x180048df8  mov     ebx, [rbp+1F0h+var_1F0]
0x180048dfb  mov     rax, [rdi]
0x180048dfe  mov     rdx, [rbp+1F0h+var_1E0]
0x180048e02  mov     rcx, rdi
0x180048e05  mov     rax, [rax+78h]
0x180048e09  call    cs:__guard_dispatch_icall_fptr
0x180048e0f  cmp     ebx, 23000000h
0x180048e15  jnz     loc_180048A73
0x180048e1b  mov     [rbp+1F0h+var_140], r12
0x180048e22  mov     [rbp+1F0h+var_140+4], 80h
0x180048e2d  mov     [rbp+1F0h+lpMem], r12
0x180048e34  lea     rax, [rbp+1F0h+var_128]
0x180048e3b  mov     [rbp+1F0h+lpMem], rax
0x180048e42  mov     dword ptr [rbp+1F0h+var_140], 2
0x180048e4c  mov     rax, [rbp+1F0h+lpMem]
0x180048e53  mov     [rax], r12w
0x180048e57  mov     r8d, [rbp+1F0h+var_1D8]; unsigned int
0x180048e5b  mov     rdx, [rbp+1F0h+Buf1]; unsigned __int8 *
0x180048e5f  lea     rcx, [rbp+1F0h+var_140]; struct SString *
0x180048e66  call    ?appendByteArray@@YAXAEAVSString@@PEBEK@Z; appendByteArray(SString &,uchar const *,ulong)
0x180048e6b  lea     rcx, [rbp+1F0h+var_140]; this
0x180048e72  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180048e77  mov     rcx, [r13+88h]
0x180048e7e  mov     rax, [rcx]
0x180048e81  movzx   r10d, word ptr [rbp+1F0h+var_1C8+2]
0x180048e86  movzx   r9d, word ptr [rbp+1F0h+var_1C8]
0x180048e8b  mov     rdx, [rbp+1F0h+lpMem]
0x180048e92  mov     [rsp+250h+var_228], rdx
0x180048e97  mov     dword ptr [rsp+250h+var_230], r10d
0x180048e9c  mov     r8, r15
0x180048e9f  lea     rdx, aMapassemblyref; "MapAssemblyRefToManifest could not find"...
0x180048ea6  mov     rax, [rax+18h]
0x180048eaa  call    cs:__guard_dispatch_icall_fptr
0x180048eb0  nop
0x180048eb1  test    [rbp+1F0h+var_138], 8
0x180048eb8  jz      loc_180048A73
0x180048ebe  mov     rdi, [rbp+1F0h+lpMem]
0x180048ec5  test    rdi, rdi
0x180048ec8  jz      loc_180048A73
0x180048ece  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180048ed5  test    rax, rax
0x180048ed8  jnz     short loc_180048EE7
0x180048eda  call    cs:__imp_GetProcessHeap
0x180048ee0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180048ee7  mov     r8, rdi; lpMem
0x180048eea  xor     edx, edx; dwFlags
  ... truncated ...
```
