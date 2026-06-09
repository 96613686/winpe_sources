# CPackage::Save(IStorage *,int)

- ea: `0x180006af0`
- end: `0x180006ca4`
- name: `?Save@CPackage@@UEAAJPEAUIStorage@@H@Z`
- size: `436`
- prototype: `__int64 __fastcall(CPackage *this, struct IStorage *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006af0`
- `0x180007934`
- `0x18000a074`
- `0x18000e010`

## import_xrefs

- `ole32!WriteFmtUserTypeStg` at `0x180006c11`
- `ole32!WriteFmtUserTypeStg` at `0x180006c11`
- `ole32!WriteClassStg` at `0x180006b41`
- `ole32!WriteClassStg` at `0x180006b41`

## pseudocode

```c
__int64 __fastcall CPackage::Save(CPackage *this, struct IStorage *a2, int a3)
{
  bool v4; // zf
  HRESULT v7; // ebx
  __int64 v8; // rax
  char *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rbp
  struct IStream *v13; // [rsp+80h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 17) == 1;
  v13 = 0;
  if ( !v4 && a3 )
    return (unsigned int)-2147418113;
  if ( !a2 && !a3 )
    return (unsigned int)-2147467261;
  v7 = WriteClassStg(a2, &CLSID_OldPackage);
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( *((_DWORD *)this + 16) == 3 )
  {
    v8 = *((_QWORD *)this + 9);
    if ( !v8 || !*(_WORD *)(v8 + 72) )
      goto LABEL_11;
  }
  v9 = (char *)this - 40;
  if ( *((_DWORD *)this + 16) == 3 )
    CPackage::CreateTempFile((CPackage *)((char *)this - 40));
  if ( a3 )
  {
    if ( !*((_DWORD *)this + 28) )
    {
LABEL_11:
      v7 = 0;
LABEL_28:
      *((_DWORD *)this + 17) = 2;
      return (unsigned int)v7;
    }
    v7 = ((__int64 (__fastcall *)(struct IStorage *, __int128 *, __int64, _QWORD, _DWORD, struct IStream **))a2->lpVtbl->CreateStream)(
           a2,
           &xmmword_1800104C8,
           4114,
           0,
           0,
           &v13);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(struct IStorage *, __int128 *, __int64, _QWORD, _DWORD, struct IStream **))a2->lpVtbl->CreateStream)(
           a2,
           &xmmword_1800104C8,
           4114,
           0,
           0,
           &v13);
    if ( v7 < 0 )
      return (unsigned int)v7;
    WriteFmtUserTypeStg(a2, *((_WORD *)this + 26), (LPOLESTR)L"OLE Package");
  }
  if ( *((_DWORD *)this + 22) || *((_DWORD *)v9 + 26) == 1 )
  {
    v7 = CPackage::PackageWriteToStream((CPackage *)((char *)this - 40), v13);
  }
  else if ( *((_DWORD *)v9 + 26) == 3 )
  {
    v10 = *((_QWORD *)this + 9);
    v11 = *(_QWORD *)(v10 + 592);
    if ( !v11 )
      *(_QWORD *)(v10 + 592) = v10 + 72;
    v7 = CPackage::PackageWriteToStream((CPackage *)((char *)this - 40), v13);
    *(_QWORD *)(*((_QWORD *)this + 9) + 592LL) = v11;
  }
  ((void (__fastcall *)(struct IStream *))v13->lpVtbl->Release)(v13);
  if ( v7 >= 0 )
    goto LABEL_28;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006af0  mov     rax, rsp
0x180006af3  push    rbx
0x180006af4  push    rbp
0x180006af5  push    rsi
0x180006af6  push    rdi
0x180006af7  push    r14
0x180006af9  push    r15
0x180006afb  sub     rsp, 48h
0x180006aff  xor     r15d, r15d
0x180006b02  mov     ebp, r8d
0x180006b05  cmp     dword ptr [rcx+44h], 1
0x180006b09  mov     r14, rdx
0x180006b0c  mov     rdi, rcx
0x180006b0f  mov     [rax+8], r15
0x180006b13  jz      short loc_180006B24
0x180006b15  test    r8d, r8d
0x180006b18  jz      short loc_180006B24
0x180006b1a  mov     ebx, 8000FFFFh
0x180006b1f  jmp     loc_180006C95
0x180006b24  test    r14, r14
0x180006b27  jnz     short loc_180006B37
0x180006b29  test    ebp, ebp
0x180006b2b  jnz     short loc_180006B37
0x180006b2d  mov     ebx, 80004003h
0x180006b32  jmp     loc_180006C95
0x180006b37  lea     rdx, CLSID_OldPackage; rclsid
0x180006b3e  mov     rcx, r14; pStg
0x180006b41  call    cs:__imp_WriteClassStg
0x180006b47  mov     ebx, eax
0x180006b49  test    eax, eax
0x180006b4b  js      loc_180006C95
0x180006b51  cmp     dword ptr [rdi+40h], 3
0x180006b55  jnz     short loc_180006B6F
0x180006b57  mov     rax, [rdi+48h]
0x180006b5b  test    rax, rax
0x180006b5e  jz      short loc_180006B67
0x180006b60  cmp     [rax+48h], r15w
0x180006b65  jnz     short loc_180006B6F
0x180006b67  mov     ebx, r15d
0x180006b6a  jmp     loc_180006C8E
0x180006b6f  lea     rsi, [rdi-28h]
0x180006b73  cmp     dword ptr [rsi+68h], 3
0x180006b77  jnz     short loc_180006B81
0x180006b79  mov     rcx, rsi; this
0x180006b7c  call    ?CreateTempFile@CPackage@@IEAAJ_N@Z; CPackage::CreateTempFile(bool)
0x180006b81  test    ebp, ebp
0x180006b83  jz      short loc_180006BC8
0x180006b85  cmp     [rdi+70h], r15d
0x180006b89  jz      short loc_180006B67
0x180006b8b  mov     rax, [r14]
0x180006b8e  lea     rcx, [rsp+78h+arg_0]
0x180006b96  mov     [rsp+78h+var_50], rcx
0x180006b9b  lea     rdx, xmmword_1800104C8
0x180006ba2  xor     r9d, r9d
0x180006ba5  mov     [rsp+78h+var_58], r15d
0x180006baa  mov     r8d, 1012h
0x180006bb0  mov     rcx, r14
0x180006bb3  mov     rax, [rax+18h]
0x180006bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bbc  mov     ebx, eax
0x180006bbe  test    eax, eax
0x180006bc0  js      loc_180006C95
0x180006bc6  jmp     short loc_180006C17
0x180006bc8  mov     rax, [r14]
0x180006bcb  lea     rcx, [rsp+78h+arg_0]
0x180006bd3  mov     [rsp+78h+var_50], rcx
0x180006bd8  lea     rdx, xmmword_1800104C8
0x180006bdf  xor     r9d, r9d
0x180006be2  mov     [rsp+78h+var_58], r15d
0x180006be7  mov     r8d, 1012h
0x180006bed  mov     rcx, r14
0x180006bf0  mov     rax, [rax+18h]
0x180006bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf9  mov     ebx, eax
0x180006bfb  test    eax, eax
0x180006bfd  js      loc_180006C95
0x180006c03  movzx   edx, word ptr [rdi+34h]; cf
0x180006c07  lea     r8, szUserType; "OLE Package"
0x180006c0e  mov     rcx, r14; pstg
0x180006c11  call    cs:__imp_WriteFmtUserTypeStg
0x180006c17  cmp     [rdi+58h], r15d
0x180006c1b  jnz     short loc_180006C64
0x180006c1d  mov     ecx, [rsi+68h]
0x180006c20  sub     ecx, 1
0x180006c23  jz      short loc_180006C64
0x180006c25  cmp     ecx, 2
0x180006c28  jnz     short loc_180006C76
0x180006c2a  mov     rcx, [rdi+48h]
0x180006c2e  mov     rbp, [rcx+250h]
0x180006c35  test    rbp, rbp
0x180006c38  jnz     short loc_180006C45
0x180006c3a  lea     rax, [rcx+48h]
0x180006c3e  mov     [rcx+250h], rax
0x180006c45  mov     rdx, [rsp+78h+arg_0]; struct IStream *
0x180006c4d  mov     rcx, rsi; this
0x180006c50  call    ?PackageWriteToStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::PackageWriteToStream(IStream *)
0x180006c55  mov     ebx, eax
0x180006c57  mov     rax, [rdi+48h]
0x180006c5b  mov     [rax+250h], rbp
0x180006c62  jmp     short loc_180006C76
0x180006c64  mov     rdx, [rsp+78h+arg_0]; struct IStream *
0x180006c6c  mov     rcx, rsi; this
0x180006c6f  call    ?PackageWriteToStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::PackageWriteToStream(IStream *)
0x180006c74  mov     ebx, eax
0x180006c76  mov     rcx, [rsp+78h+arg_0]
0x180006c7e  mov     rax, [rcx]
0x180006c81  mov     rax, [rax+10h]
0x180006c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8a  test    ebx, ebx
0x180006c8c  js      short loc_180006C95
0x180006c8e  mov     dword ptr [rdi+44h], 2
0x180006c95  mov     eax, ebx
0x180006c97  add     rsp, 48h
0x180006c9b  pop     r15
0x180006c9d  pop     r14
0x180006c9f  pop     rdi
0x180006ca0  pop     rsi
0x180006ca1  pop     rbp
0x180006ca2  pop     rbx
0x180006ca3  retn
```
