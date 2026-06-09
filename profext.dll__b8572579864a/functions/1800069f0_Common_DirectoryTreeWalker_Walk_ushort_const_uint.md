# Common::DirectoryTreeWalker::Walk(ushort const *,uint)

- ea: `0x1800069f0`
- end: `0x18000705f`
- name: `?Walk@DirectoryTreeWalker@Common@@QEAAJPEBGI@Z`
- size: `1647`
- prototype: `__int64 __fastcall(__int64 **this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180006938`

## callees

- `0x1800069f0`
- `0x180007068`
- `0x180007098`
- `0x1800071c0`
- `0x180007374`
- `0x1800075c4`
- `0x180007740`
- `0x180010e8c`
- `0x1800227f2`
- `0x180022830`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006a97`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006af5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006c16`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cab`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006f57`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000700c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007042`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a97`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006af5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006c16`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cab`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006f57`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000700c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007042`

## pseudocode

```c
__int64 __fastcall Common::DirectoryTreeWalker::Walk(__int64 **this, const unsigned __int16 *a2, int a3)
{
  unsigned int v5; // ebx
  int v6; // esi
  const struct _WIN32_FIND_DATAW *cFileName; // rdx
  unsigned int Handle; // r14d
  unsigned int appended; // esi
  __int64 *v11; // rax
  struct _WIN32_FIND_DATAW *v12; // rbx
  void *v13; // r15
  unsigned __int16 *v14; // r8
  unsigned __int64 v15; // rdx
  __int64 *v16; // rax
  struct _WIN32_FIND_DATAW *v17; // rbx
  int v18; // esi
  __int64 *v19; // rcx
  __int64 *v20; // rax
  WCHAR v21; // ax
  unsigned __int16 *v22; // r8
  unsigned __int64 v23; // rdx
  unsigned int v24; // ebx
  struct _WIN32_FIND_DATAW *v25; // rcx
  __int64 *v26; // rcx
  __int64 *v27; // rdx
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *); // rax
  unsigned int v29; // eax
  __int64 *v30; // rcx
  __int64 *v31; // rdx
  __int64 (__fastcall *v32)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *); // rax
  unsigned int v33; // eax
  unsigned int v34; // ebx
  unsigned __int16 *v35; // r8
  unsigned __int64 v36; // rdx
  int v37; // ecx
  int v38; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW *v39; // [rsp+38h] [rbp-C8h] BYREF
  void *v40; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall *v41)(__int64); // [rsp+48h] [rbp-B8h]
  __int64 *v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall *v44)(__int64); // [rsp+60h] [rbp-A0h]
  __int64 *v45; // [rsp+68h] [rbp-98h]
  struct _WIN32_FIND_DATAW v46; // [rsp+70h] [rbp-90h] BYREF

  v41 = (void (__fastcall *)(__int64))this[9];
  v42 = this[6];
  v40 = 0;
  v39 = 0;
  v5 = Common::DirectoryTreeWalker::InitializePath((Common::DirectoryTreeWalker *)this, a2);
  if ( v5 )
  {
    operator delete(0);
    return v5;
  }
  v6 = 0;
  v38 = 0;
  *((_DWORD *)this + 8) = a3;
  if ( (a3 & 2) != 0 && (a3 & 1) == 0 )
  {
    memset_0(&v46, 0, sizeof(v46));
    v30 = this[6];
    v31 = this[1];
    v44 = (void (__fastcall *)(__int64))this[9];
    v32 = (__int64 (__fastcall *)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *))this[7];
    v43 = 0;
    v45 = v30;
    v33 = v32((__int64)v30, (__int64)v31, &v43, &v46);
    v34 = v33;
    if ( v33 - 2 > 1 )
    {
      v38 = 0;
      if ( v33
        || (v34 = Common::DirectoryTreeWalker::Visit(
                    (Common::DirectoryTreeWalker *)this,
                    (unsigned __int64)this[2],
                    (unsigned __int16 *)this[1],
                    &v46,
                    &v38)) != 0 )
      {
        anonymous_namespace_::FindFileHandle::Close(&v43);
        operator delete(0);
        anonymous_namespace_::FindFileHandle::Close(&v40);
        return v34;
      }
      if ( v38 )
        v6 = v38;
      v38 = v6;
    }
    anonymous_namespace_::FindFileHandle::Close(&v43);
  }
  Handle = Common::DirectoryTreeWalker::GetFirstFindHandle((Common::DirectoryTreeWalker *)this, &v40, &v39);
  if ( Handle )
  {
    operator delete(v39);
    if ( v40 )
      v41((__int64)v42);
    return Handle;
  }
  v12 = v39;
  v13 = v40;
  while ( 1 )
  {
    if ( Common::IsDirectoryReparsePointOpaque((Common *)v12, cFileName) || (v12->dwFileAttributes & 0x10) == 0 )
    {
      v14 = (unsigned __int16 *)this[1];
      v15 = (unsigned __int64)this[2];
      LODWORD(v39) = 0;
      appended = Common::DirectoryTreeWalker::Visit((Common::DirectoryTreeWalker *)this, v15, v14, v12, (int *)&v39);
      if ( !appended )
      {
        Handle = (unsigned int)v39;
        v6 = v38;
LABEL_17:
        switch ( Handle )
        {
          case 0u:
            goto LABEL_26;
          case 0x12u:
            goto LABEL_28;
          case 3u:
            goto LABEL_27;
        }
        if ( !v6 )
          v38 = Handle;
LABEL_41:
        Handle = ((__int64 (__fastcall *)(__int64 *, void *, struct _WIN32_FIND_DATAW *))this[8])(this[6], v13, v12);
        goto LABEL_27;
      }
LABEL_53:
      operator delete(v12);
      if ( v13 )
        ((void (__fastcall *)(__int64 *, void *))v41)(v42, v13);
      return appended;
    }
    cFileName = (const struct _WIN32_FIND_DATAW *)v12->cFileName;
    if ( v12->cFileName[0] == 46 )
    {
      v21 = v12->cFileName[1];
      if ( !v21 || v21 == 46 && !v12->cFileName[2] )
        goto LABEL_17;
    }
    appended = Common::DirectoryTreeWalker::AppendNameToDirPath(
                 (Common::DirectoryTreeWalker *)this,
                 (const unsigned __int16 *)cFileName);
    if ( appended )
      goto LABEL_53;
    if ( (a3 & 2) != 0 )
    {
      v35 = (unsigned __int16 *)this[1];
      v36 = (unsigned __int64)this[2];
      LODWORD(v39) = 0;
      appended = Common::DirectoryTreeWalker::Visit((Common::DirectoryTreeWalker *)this, v36, v35, v12, (int *)&v39);
      if ( appended )
      {
        operator delete(v12);
        anonymous_namespace_::FindFileHandle::Close(&v40);
        return appended;
      }
      if ( (_DWORD)v39 && (_DWORD)v39 != 3 )
      {
        v37 = v38;
        if ( !v38 )
          v37 = (int)v39;
        v38 = v37;
      }
    }
    v11 = (__int64 *)operator new(0x18u);
    if ( !v11 )
    {
      operator delete(v12);
      anonymous_namespace_::FindFileHandle::Close(&v40);
      return 14;
    }
    *v11 = (__int64)*this;
    v11[1] = (__int64)v13;
    v11[2] = (__int64)v12;
    *this = v11;
    v39 = 0;
    v40 = 0;
    v29 = Common::DirectoryTreeWalker::GetFirstFindHandle((Common::DirectoryTreeWalker *)this, &v40, &v39);
    Handle = v29;
    if ( v29 == 2 )
      break;
    if ( v29 )
    {
      if ( v29 == 3 )
      {
        v13 = v40;
        v12 = v39;
        goto LABEL_28;
      }
      v25 = v39;
LABEL_62:
      operator delete(v25);
      anonymous_namespace_::FindFileHandle::Close(&v40);
      return Handle;
    }
    v13 = v40;
    v12 = v39;
LABEL_87:
    v6 = v38;
  }
  v13 = v40;
  Handle = 18;
  v12 = v39;
  while ( 1 )
  {
LABEL_28:
    operator delete(v12);
    if ( v13 )
    {
      ((void (__fastcall *)(__int64 *, void *))v41)(v42, v13);
      v40 = 0;
    }
    if ( Handle != 18 && Handle != 3 )
      goto LABEL_61;
    v17 = (struct _WIN32_FIND_DATAW *)*this;
    if ( *this )
    {
      v18 = 0;
      goto LABEL_33;
    }
    v18 = 1;
    if ( (a3 & 3) != 0 )
      break;
LABEL_33:
    memset_0(&v46, 0, sizeof(v46));
    if ( v18 )
    {
      v26 = this[6];
      v27 = this[1];
      v17 = 0;
      v44 = (void (__fastcall *)(__int64))this[9];
      v28 = (__int64 (__fastcall *)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *))this[7];
      v43 = 0;
      v45 = v26;
      Handle = v28((__int64)v26, (__int64)v27, &v43, &v46);
      if ( Handle - 2 > 1 )
      {
        if ( Handle )
        {
          anonymous_namespace_::FindFileHandle::Close(&v43);
LABEL_61:
          v25 = 0;
          goto LABEL_62;
        }
        v17 = &v46;
      }
      if ( v43 )
        v44((__int64)v45);
    }
    else if ( v17 )
    {
      v17 = *(struct _WIN32_FIND_DATAW **)&v17->ftLastAccessTime.dwHighDateTime;
    }
    if ( Handle - 2 <= 1 || (a3 & 2) != 0 )
    {
      Handle = 0;
    }
    else
    {
      v22 = (unsigned __int16 *)this[1];
      v23 = (unsigned __int64)this[2];
      LODWORD(v39) = 0;
      v24 = Common::DirectoryTreeWalker::Visit((Common::DirectoryTreeWalker *)this, v23, v22, v17, (int *)&v39);
      if ( v24 )
        goto LABEL_95;
      Handle = (unsigned int)v39;
      if ( (_DWORD)v39 && (_DWORD)v39 != 3 && !v38 )
        v38 = (int)v39;
    }
    if ( v18 )
      break;
    v19 = *this;
    v13 = (void *)(*this)[1];
    v20 = (__int64 *)**this;
    v12 = (struct _WIN32_FIND_DATAW *)(*this)[2];
    v40 = v13;
    *this = v20;
    operator delete(v19);
    v16 = this[2];
    while ( 1 )
    {
      v16 = (__int64 *)((char *)v16 - 1);
      if ( !v16 )
        break;
      cFileName = (const struct _WIN32_FIND_DATAW *)((char *)this[1] + 2 * (_QWORD)v16);
      if ( LOWORD(cFileName->dwFileAttributes) == 92 )
      {
        LOWORD(cFileName->dwFileAttributes) = 0;
        break;
      }
    }
    this[2] = v16;
LABEL_26:
    if ( Handle != 18 && Handle != 3 )
      goto LABEL_41;
LABEL_27:
    if ( !Handle )
      goto LABEL_87;
  }
  v24 = v38;
  if ( !v38 )
  {
    if ( Handle == 18 || Handle == 3 )
      Handle = 0;
    goto LABEL_61;
  }
LABEL_95:
  operator delete(0);
  anonymous_namespace_::FindFileHandle::Close(&v40);
  return v24;
}

```

## disassembly

```asm
0x1800069f0  push    rbp
0x1800069f2  push    rbx
0x1800069f3  push    rdi
0x1800069f4  push    r13
0x1800069f6  push    r14
0x1800069f8  lea     rbp, [rsp-1E0h]
0x180006a00  sub     rsp, 2E0h
0x180006a07  mov     rax, cs:__security_cookie
0x180006a0e  xor     rax, rsp
0x180006a11  mov     [rbp+200h+var_40], rax
0x180006a18  mov     rax, [rcx+48h]
0x180006a1c  xor     r14d, r14d
0x180006a1f  mov     [rsp+300h+var_2B8], rax
0x180006a24  mov     r13d, r8d
0x180006a27  mov     rax, [rcx+30h]
0x180006a2b  mov     rdi, rcx
0x180006a2e  mov     [rsp+300h+var_2B0], rax
0x180006a33  mov     [rsp+300h+var_2C0], r14
0x180006a38  mov     [rsp+300h+var_2C8], r14
0x180006a3d  call    ?InitializePath@DirectoryTreeWalker@Common@@AEAAJPEBG@Z; Common::DirectoryTreeWalker::InitializePath(ushort const *)
0x180006a42  mov     ebx, eax
0x180006a44  test    eax, eax
0x180006a46  jnz     loc_180006B47
0x180006a4c  mov     [rsp+300h+arg_10], rsi
0x180006a54  mov     esi, r14d
0x180006a57  mov     [rsp+300h+var_28], r12
0x180006a5f  mov     r12d, r13d
0x180006a62  mov     [rsp+300h+var_2D0], r14d
0x180006a67  mov     [rdi+20h], r13d
0x180006a6b  and     r12d, 2
0x180006a6f  jnz     loc_180006EAD
0x180006a75  lea     r8, [rsp+300h+var_2C8]; struct _WIN32_FIND_DATAW **
0x180006a7a  mov     rcx, rdi; this
0x180006a7d  lea     rdx, [rsp+300h+var_2C0]; void **
0x180006a82  call    ?GetFirstFindHandle@DirectoryTreeWalker@Common@@AEAAJPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; Common::DirectoryTreeWalker::GetFirstFindHandle(void * *,_WIN32_FIND_DATAW * *)
0x180006a87  mov     r14d, eax
0x180006a8a  test    eax, eax
0x180006a8c  jz      loc_180006B59
0x180006a92  mov     rcx, [rsp+300h+var_2C8]
0x180006a97  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006a9e  nop     dword ptr [rax+rax+00h]
0x180006aa3  mov     rdx, [rsp+300h+var_2C0]
0x180006aa8  test    rdx, rdx
0x180006aab  jz      short loc_180006ABC
0x180006aad  mov     rcx, [rsp+300h+var_2B0]
0x180006ab2  mov     rax, [rsp+300h+var_2B8]
0x180006ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006abc  mov     eax, r14d
0x180006abf  jmp     short loc_180006B18
0x180006ac1  mov     rcx, rdi; this
0x180006ac4  call    ?AppendNameToDirPath@DirectoryTreeWalker@Common@@AEAAJPEBG@Z; Common::DirectoryTreeWalker::AppendNameToDirPath(ushort const *)
0x180006ac9  mov     esi, eax
0x180006acb  test    eax, eax
0x180006acd  jnz     loc_180006D7C
0x180006ad3  xor     r14d, r14d
0x180006ad6  test    r12d, r12d
0x180006ad9  jnz     loc_180006F74
0x180006adf  mov     ecx, 18h; Size
0x180006ae4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ae9  test    rax, rax
0x180006aec  jnz     loc_180006E54
0x180006af2  mov     rcx, rbx
0x180006af5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006afc  nop     dword ptr [rax+rax+00h]
0x180006b01  lea     rcx, [rsp+300h+var_2C0]
0x180006b06  call    _anonymous_namespace___FindFileHandle__Close
0x180006b0b  mov     eax, 0Eh
0x180006b10  mov     r15, [rsp+300h+var_30]
0x180006b18  mov     rsi, [rsp+300h+arg_10]
0x180006b20  mov     r12, [rsp+300h+var_28]
0x180006b28  mov     rcx, [rbp+200h+var_40]
0x180006b2f  xor     rcx, rsp; StackCookie
0x180006b32  call    __security_check_cookie
0x180006b37  add     rsp, 2E0h
0x180006b3e  pop     r14
0x180006b40  pop     r13
0x180006b42  pop     rdi
0x180006b43  pop     rbx
0x180006b44  pop     rbp
0x180006b45  retn
0x180006b47  xor     ecx, ecx
0x180006b49  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b50  nop     dword ptr [rax+rax+00h]
0x180006b55  mov     eax, ebx
0x180006b57  jmp     short loc_180006B28
0x180006b59  mov     rbx, [rsp+300h+var_2C8]
0x180006b5e  mov     [rsp+300h+var_30], r15
0x180006b66  mov     r15, [rsp+300h+var_2C0]
0x180006b6b  nop     dword ptr [rax+rax+00h]
0x180006b70  mov     rcx, rbx; this
0x180006b73  call    ?IsDirectoryReparsePointOpaque@Common@@YA_NAEBU_WIN32_FIND_DATAW@@@Z; Common::IsDirectoryReparsePointOpaque(_WIN32_FIND_DATAW const &)
0x180006b78  test    al, al
0x180006b7a  jnz     short loc_180006B85
0x180006b7c  test    byte ptr [rbx], 10h
0x180006b7f  jnz     loc_180006CE5
0x180006b85  mov     r8, [rdi+8]; unsigned __int16 *
0x180006b89  lea     rax, [rsp+300h+var_2C8]
0x180006b8e  mov     rdx, [rdi+10h]; unsigned __int64
0x180006b92  mov     r9, rbx; struct _WIN32_FIND_DATAW *
0x180006b95  mov     rcx, rdi; this
0x180006b98  mov     [rsp+300h+var_2E0], rax; int *
0x180006b9d  mov     dword ptr [rsp+300h+var_2C8], 0
0x180006ba5  call    ?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z; Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)
0x180006baa  mov     esi, eax
0x180006bac  test    eax, eax
0x180006bae  jnz     loc_180006D7C
0x180006bb4  mov     r14d, dword ptr [rsp+300h+var_2C8]
0x180006bb9  mov     esi, [rsp+300h+var_2D0]
0x180006bbd  test    r14d, r14d
0x180006bc0  jz      short loc_180006C00
0x180006bc2  cmp     r14d, 12h
0x180006bc6  jz      short loc_180006C13
0x180006bc8  cmp     r14d, 3
0x180006bcc  jz      short loc_180006C0A
0x180006bce  test    esi, esi
0x180006bd0  jnz     loc_180006CCA
0x180006bd6  mov     [rsp+300h+var_2D0], r14d
0x180006bdb  jmp     loc_180006CCA
0x180006be0  dec     rax
0x180006be3  test    rax, rax
0x180006be6  jz      short loc_180006BFC
0x180006be8  mov     rcx, [rdi+8]
0x180006bec  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x180006bf1  lea     rdx, [rcx+rax*2]
0x180006bf5  jnz     short loc_180006BE0
0x180006bf7  xor     ecx, ecx
0x180006bf9  mov     [rdx], cx
0x180006bfc  mov     [rdi+10h], rax
0x180006c00  cmp     r14d, 12h
0x180006c04  jnz     loc_180006CC0
0x180006c0a  test    r14d, r14d
0x180006c0d  jz      loc_180006FE2
0x180006c13  mov     rcx, rbx
0x180006c16  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006c1d  nop     dword ptr [rax+rax+00h]
0x180006c22  test    r15, r15
0x180006c25  jz      short loc_180006C42
0x180006c27  mov     rcx, [rsp+300h+var_2B0]
0x180006c2c  mov     rdx, r15
0x180006c2f  mov     rax, [rsp+300h+var_2B8]
0x180006c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c39  mov     [rsp+300h+var_2C0], 0
0x180006c42  cmp     r14d, 12h
0x180006c46  jnz     loc_180006FEB
0x180006c4c  mov     rbx, [rdi]
0x180006c4f  test    rbx, rbx
0x180006c52  jz      loc_180006DA9
0x180006c58  xor     esi, esi
0x180006c5a  xor     edx, edx; Val
0x180006c5c  lea     rcx, [rsp+300h+var_290]; void *
0x180006c61  mov     r8d, 250h; Size
0x180006c67  call    memset_0
0x180006c6c  test    esi, esi
0x180006c6e  jnz     loc_180006DF3
0x180006c74  test    rbx, rbx
0x180006c77  jz      short loc_180006C7D
0x180006c79  mov     rbx, [rbx+10h]
0x180006c7d  lea     eax, [r14-2]
0x180006c81  cmp     eax, 1
0x180006c84  ja      loc_180006D1B
0x180006c8a  xor     r14d, r14d
0x180006c8d  test    esi, esi
0x180006c8f  jnz     loc_180006DB8
0x180006c95  mov     rcx, [rdi]
0x180006c98  mov     r15, [rcx+8]
0x180006c9c  mov     rax, [rcx]
0x180006c9f  mov     rbx, [rcx+10h]
0x180006ca3  mov     [rsp+300h+var_2C0], r15
0x180006ca8  mov     [rdi], rax
0x180006cab  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006cb2  nop     dword ptr [rax+rax+00h]
0x180006cb7  mov     rax, [rdi+10h]
0x180006cbb  jmp     loc_180006BE0
0x180006cc0  cmp     r14d, 3
0x180006cc4  jz      loc_180006C0A
0x180006cca  mov     rcx, [rdi+30h]
0x180006cce  mov     r8, rbx
0x180006cd1  mov     rax, [rdi+40h]
0x180006cd5  mov     rdx, r15
0x180006cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdd  mov     r14d, eax
0x180006ce0  jmp     loc_180006C0A
0x180006ce5  cmp     word ptr [rbx+2Ch], 2Eh ; '.'
0x180006cea  lea     rdx, [rbx+2Ch]; unsigned __int16 *
0x180006cee  jnz     loc_180006AC1
0x180006cf4  movzx   eax, word ptr [rdx+2]
0x180006cf8  test    ax, ax
0x180006cfb  jz      loc_180006BBD
0x180006d01  cmp     ax, 2Eh ; '.'
0x180006d05  jnz     loc_180006AC1
0x180006d0b  cmp     word ptr [rdx+4], 0
0x180006d10  jz      loc_180006BBD
0x180006d16  jmp     loc_180006AC1
0x180006d1b  test    r12d, r12d
0x180006d1e  jnz     loc_180006C8A
0x180006d24  mov     r8, [rdi+8]; unsigned __int16 *
0x180006d28  lea     rax, [rsp+300h+var_2C8]
0x180006d2d  mov     rdx, [rdi+10h]; unsigned __int64
0x180006d31  mov     r9, rbx; struct _WIN32_FIND_DATAW *
0x180006d34  mov     rcx, rdi; this
0x180006d37  mov     [rsp+300h+var_2E0], rax; int *
0x180006d3c  mov     dword ptr [rsp+300h+var_2C8], r12d
0x180006d41  call    ?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z; Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)
0x180006d46  mov     ebx, eax
0x180006d48  test    eax, eax
0x180006d4a  jnz     loc_180007040
0x180006d50  mov     r14d, dword ptr [rsp+300h+var_2C8]
0x180006d55  test    r14d, r14d
0x180006d58  jz      loc_180006C8D
0x180006d5e  cmp     r14d, 3
0x180006d62  jz      loc_180006C8D
0x180006d68  cmp     [rsp+300h+var_2D0], eax
0x180006d6c  jnz     loc_180006C8D
0x180006d72  mov     [rsp+300h+var_2D0], r14d
0x180006d77  jmp     loc_180006C8D
0x180006d7c  mov     rcx, rbx
0x180006d7f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006d86  nop     dword ptr [rax+rax+00h]
0x180006d8b  test    r15, r15
0x180006d8e  jz      short loc_180006DA2
0x180006d90  mov     rcx, [rsp+300h+var_2B0]
0x180006d95  mov     rdx, r15
0x180006d98  mov     rax, [rsp+300h+var_2B8]
0x180006d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da2  mov     eax, esi
0x180006da4  jmp     loc_180006B10
0x180006da9  mov     esi, 1
0x180006dae  test    r13b, 3
0x180006db2  jz      loc_180006C5A
0x180006db8  mov     ebx, [rsp+300h+var_2D0]
0x180006dbc  test    ebx, ebx
0x180006dbe  jnz     loc_180007040
0x180006dc4  cmp     r14d, 12h
0x180006dc8  jz      short loc_180006DD0
0x180006dca  cmp     r14d, 3
0x180006dce  jnz     short loc_180006DD3
0x180006dd0  xor     r14d, r14d
0x180006dd3  xor     ecx, ecx
0x180006dd5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006ddc  nop     dword ptr [rax+rax+00h]
0x180006de1  lea     rcx, [rsp+300h+var_2C0]
0x180006de6  call    _anonymous_namespace___FindFileHandle__Close
0x180006deb  mov     eax, r14d
0x180006dee  jmp     loc_180006B10
0x180006df3  mov     rax, [rdi+48h]
0x180006df7  lea     r9, [rsp+300h+var_290]
0x180006dfc  mov     rcx, [rdi+30h]
0x180006e00  lea     r8, [rsp+300h+var_2A8]
0x180006e05  mov     rdx, [rdi+8]
0x180006e09  xor     ebx, ebx
0x180006e0b  mov     [rsp+300h+var_2A0], rax
0x180006e10  mov     rax, [rdi+38h]
0x180006e14  mov     [rsp+300h+var_2A8], rbx
0x180006e19  mov     [rsp+300h+var_298], rcx
0x180006e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e23  mov     r14d, eax
0x180006e26  add     eax, 0FFFFFFFEh
0x180006e29  cmp     eax, 1
0x180006e2c  ja      loc_180006FFA
0x180006e32  mov     rdx, [rsp+300h+var_2A8]
0x180006e37  test    rdx, rdx
0x180006e3a  jz      loc_180006C7D
0x180006e40  mov     rcx, [rsp+300h+var_298]
0x180006e45  mov     rax, [rsp+300h+var_2A0]
0x180006e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4f  jmp     loc_180006C7D
0x180006e54  mov     rcx, [rdi]
0x180006e57  lea     r8, [rsp+300h+var_2C8]; struct _WIN32_FIND_DATAW **
0x180006e5c  mov     [rax], rcx
0x180006e5f  lea     rdx, [rsp+300h+var_2C0]; void **
0x180006e64  mov     [rax+8], r15
0x180006e68  mov     rcx, rdi; this
0x180006e6b  mov     [rax+10h], rbx
0x180006e6f  mov     [rdi], rax
0x180006e72  mov     [rsp+300h+var_2C8], r14
0x180006e77  mov     [rsp+300h+var_2C0], r14
0x180006e7c  call    ?GetFirstFindHandle@DirectoryTreeWalker@Common@@AEAAJPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; Common::DirectoryTreeWalker::GetFirstFindHandle(void * *,_WIN32_FIND_DATAW * *)
0x180006e81  mov     r14d, eax
0x180006e84  cmp     eax, 2
0x180006e87  jz      loc_180006FC3
0x180006e8d  test    eax, eax
0x180006e8f  jz      loc_180006FD8
0x180006e95  cmp     eax, 3
0x180006e98  jnz     loc_180007027
0x180006e9e  mov     r15, [rsp+300h+var_2C0]
0x180006ea3  mov     rbx, [rsp+300h+var_2C8]
0x180006ea8  jmp     loc_180006C13
0x180006ead  test    r13b, 1
0x180006eb1  jnz     loc_180006A75
0x180006eb7  xor     edx, edx; Val
0x180006eb9  lea     rcx, [rsp+300h+var_290]; void *
0x180006ebe  mov     r8d, 250h; Size
0x180006ec4  call    memset_0
0x180006ec9  mov     rax, [rdi+48h]
0x180006ecd  lea     r9, [rsp+300h+var_290]
0x180006ed2  mov     rcx, [rdi+30h]
0x180006ed6  lea     r8, [rsp+300h+var_2A8]
0x180006edb  mov     rdx, [rdi+8]
0x180006edf  mov     [rsp+300h+var_2A0], rax
0x180006ee4  mov     rax, [rdi+38h]
  ... truncated ...
```
