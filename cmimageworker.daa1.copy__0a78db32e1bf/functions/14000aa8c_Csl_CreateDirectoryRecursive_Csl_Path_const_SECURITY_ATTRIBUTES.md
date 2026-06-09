# Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)

- ea: `0x14000aa8c`
- end: `0x14000aca1`
- name: `?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(Csl *__hidden this, const struct Path *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140006188`
- `0x14000aa8c`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000a910`
- `0x14000aa8c`
- `0x14000bd50`
- `0x14000c668`
- `0x14000c6a4`
- `0x14000c70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aaba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000aaa6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000abfd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000aaa6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000abfd`

## string_xrefs

- `0x14000aaf4`: `Failed to create directory at path '%ws'`
- `0x14000ac73`: `'%ws' has no parent path`
- `0x14000ac10`: `Failed to create directory at path '%ws' after creating parent directory`

## pseudocode

```c
__int64 __fastcall Csl::CreateDirectoryRecursive(LPCWSTR *this, const struct Path *a2, struct _SECURITY_ATTRIBUTES *a3)
{
  DWORD LastError; // eax
  LPCWSTR v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  char v9; // al
  struct _SECURITY_ATTRIBUTES *v10; // r8
  unsigned int v11; // ebx
  void *v12; // rcx
  bool v13; // zf
  int DirectoryRecursive; // eax
  unsigned int v15; // edi
  unsigned int LastErrorMsg; // eax
  int v17; // [rsp+20h] [rbp-40h]
  _QWORD v18[2]; // [rsp+30h] [rbp-30h] BYREF
  void *v19[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v20[8]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( CreateDirectoryW(*this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 183 )
    return 0;
  if ( LastError != 3 )
  {
    if ( LastError )
      return wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0x25D,
               (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
               (const char *)LastError,
               (unsigned int)"Failed to create directory at path '%ws'",
               (const char *)*this);
    return 0;
  }
  v6 = *this;
  v7 = this[1] - *this;
  if ( !v7
    || ((v18[0] = this, v18[1] = v7, v8 = Csl::Path::Iterator::operator--(v18), this != *(LPCWSTR **)v8)
     || *(_QWORD *)(v8 + 8)
      ? (v9 = 1)
      : (v9 = 0),
        !v9) )
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x80070057LL,
      (int)"'%ws' has no parent path",
      (const char *)v6);
    return v11;
  }
  v19[0] = v20;
  v19[1] = v20;
  v20[0] = 0;
  if ( !Csl::Path::GetParentPath((Csl::Path *)this, (struct Path *)v19) )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v17);
    v12 = v19[0];
    v13 = v19[0] == v20;
    goto LABEL_14;
  }
  DirectoryRecursive = Csl::CreateDirectoryRecursive((Csl *)v19, 0, v10);
  v15 = DirectoryRecursive;
  if ( DirectoryRecursive >= 0 )
  {
    if ( !CreateDirectoryW(*this, 0) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x26E,
                       (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                       "Failed to create directory at path '%ws' after creating parent directory",
                       (const char *)*this);
      v12 = v19[0];
      v11 = LastErrorMsg;
      v13 = v19[0] == v20;
LABEL_14:
      if ( !v13 )
        operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
      return v11;
    }
    if ( v19[0] != v20 )
      operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x269,
    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
    (const char *)(unsigned int)DirectoryRecursive,
    v17);
  if ( v19[0] != v20 )
    operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
  return v15;
}

```

## disassembly

```asm
0x14000aa8c  mov     [rsp-8+arg_0], rbx
0x14000aa91  mov     [rsp-8+arg_8], rdi
0x14000aa96  push    rbp
0x14000aa97  mov     rbp, rsp
0x14000aa9a  sub     rsp, 60h
0x14000aa9e  mov     rbx, rcx
0x14000aaa1  xor     edx, edx; lpSecurityAttributes
0x14000aaa3  mov     rcx, [rcx]; lpPathName
0x14000aaa6  call    cs:__imp_CreateDirectoryW
0x14000aaad  nop     dword ptr [rax+rax+00h]
0x14000aab2  test    eax, eax
0x14000aab4  jnz     loc_14000AC5C
0x14000aaba  call    cs:__imp_GetLastError
0x14000aac1  nop     dword ptr [rax+rax+00h]
0x14000aac6  cmp     eax, 0B7h
0x14000aacb  jz      loc_14000AC5C
0x14000aad1  cmp     eax, 3
0x14000aad4  jz      short loc_14000AB0F
0x14000aad6  test    eax, eax
0x14000aad8  jz      loc_14000AC5C
0x14000aade  mov     rdx, [rbx]
0x14000aae1  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000aae8  mov     rcx, [rbp+8]; this
0x14000aaec  mov     r9d, eax; char *
0x14000aaef  mov     [rsp+60h+var_38], rdx; char *
0x14000aaf4  lea     rdx, aFailedToCreate_0; "Failed to create directory at path '%ws"...
0x14000aafb  mov     [rsp+60h+var_40], rdx; unsigned int
0x14000ab00  mov     edx, 25Dh; void *
0x14000ab05  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x14000ab0a  jmp     loc_14000AC5E
0x14000ab0f  mov     rdi, [rbx]
0x14000ab12  mov     rax, [rbx+8]
0x14000ab16  sub     rax, rdi
0x14000ab19  sar     rax, 1
0x14000ab1c  jz      loc_14000AC6F
0x14000ab22  lea     rcx, [rbp+var_30]
0x14000ab26  mov     [rbp+var_30], rbx
0x14000ab2a  mov     [rbp+var_28], rax
0x14000ab2e  call    ??FIterator@Path@Csl@@QEAAAEAV012@XZ; Csl::Path::Iterator::operator--(void)
0x14000ab33  cmp     rbx, [rax]
0x14000ab36  jnz     short loc_14000AB43
0x14000ab38  cmp     qword ptr [rax+8], 0
0x14000ab3d  jnz     short loc_14000AB43
0x14000ab3f  xor     al, al
0x14000ab41  jmp     short loc_14000AB45
0x14000ab43  mov     al, 1
0x14000ab45  test    al, al
0x14000ab47  jz      loc_14000AC6F
0x14000ab4d  lea     rax, [rbp+var_10]
0x14000ab51  mov     rcx, rbx; this
0x14000ab54  mov     [rbp+var_20], rax
0x14000ab58  lea     rdx, [rbp+var_20]; struct Path *
0x14000ab5c  lea     rax, [rbp+var_10]
0x14000ab60  mov     [rbp+var_18], rax
0x14000ab64  xor     eax, eax
0x14000ab66  mov     [rbp+var_10], ax
0x14000ab6a  call    ?GetParentPath@Path@Csl@@QEBA_NAEAV12@@Z; Csl::Path::GetParentPath(Csl::Path &)
0x14000ab6f  test    al, al
0x14000ab71  jnz     short loc_14000ABB2
0x14000ab73  mov     rcx, [rbp+8]; this
0x14000ab77  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000ab7e  mov     ebx, 8007000Eh
0x14000ab83  mov     edx, 267h; void *
0x14000ab88  mov     r9d, ebx; char *
0x14000ab8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ab90  mov     rcx, [rbp+var_20]; void *
0x14000ab94  lea     rdx, [rbp+var_10]
0x14000ab98  cmp     rcx, rdx
0x14000ab9b  jz      loc_14000AC9D
0x14000aba1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000aba8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000abad  jmp     loc_14000AC9D
0x14000abb2  xor     edx, edx; struct Path *
0x14000abb4  lea     rcx, [rbp+var_20]; this
0x14000abb8  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x14000abbd  mov     edi, eax
0x14000abbf  test    eax, eax
0x14000abc1  jns     short loc_14000ABF8
0x14000abc3  mov     rcx, [rbp+8]; this
0x14000abc7  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000abce  mov     r9d, eax; char *
0x14000abd1  mov     edx, 269h; void *
0x14000abd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000abdb  mov     rcx, [rbp+var_20]; void *
0x14000abdf  lea     rax, [rbp+var_10]
0x14000abe3  cmp     rcx, rax
0x14000abe6  jz      short loc_14000ABF4
0x14000abe8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000abef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000abf4  mov     eax, edi
0x14000abf6  jmp     short loc_14000AC5E
0x14000abf8  mov     rcx, [rbx]; lpPathName
0x14000abfb  xor     edx, edx; lpSecurityAttributes
0x14000abfd  call    cs:__imp_CreateDirectoryW
0x14000ac04  nop     dword ptr [rax+rax+00h]
0x14000ac09  test    eax, eax
0x14000ac0b  jnz     short loc_14000AC43
0x14000ac0d  mov     rax, [rbx]
0x14000ac10  lea     r9, aFailedToCreate; "Failed to create directory at path '%ws"...
0x14000ac17  mov     rcx, [rbp+8]; this
0x14000ac1b  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000ac22  mov     edx, 26Eh; void *
0x14000ac27  mov     [rsp+60h+var_40], rax; char *
0x14000ac2c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000ac31  mov     rcx, [rbp+var_20]
0x14000ac35  mov     ebx, eax
0x14000ac37  lea     rax, [rbp+var_10]
0x14000ac3b  cmp     rcx, rax
0x14000ac3e  jmp     loc_14000AB9B
0x14000ac43  mov     rcx, [rbp+var_20]; void *
0x14000ac47  lea     rax, [rbp+var_10]
0x14000ac4b  cmp     rcx, rax
0x14000ac4e  jz      short loc_14000AC5C
0x14000ac50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000ac57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ac5c  xor     eax, eax
0x14000ac5e  mov     rbx, [rsp+60h+arg_0]
0x14000ac63  mov     rdi, [rsp+60h+arg_8]
0x14000ac68  add     rsp, 60h
0x14000ac6c  pop     rbp
0x14000ac6d  retn
0x14000ac6f  mov     rcx, [rbp+8]; this
0x14000ac73  lea     rax, aWsHasNoParentP; "'%ws' has no parent path"
0x14000ac7a  mov     ebx, 80070057h
0x14000ac7f  mov     [rsp+60h+var_38], rdi; char *
0x14000ac84  mov     r9d, ebx; char *
0x14000ac87  mov     [rsp+60h+var_40], rax; int
0x14000ac8c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000ac93  mov     edx, 264h; void *
0x14000ac98  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000ac9d  mov     eax, ebx
0x14000ac9f  jmp     short loc_14000AC5E
```
