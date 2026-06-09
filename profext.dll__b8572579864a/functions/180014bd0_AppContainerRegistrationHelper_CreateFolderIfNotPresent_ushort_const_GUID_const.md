# AppContainerRegistrationHelper::CreateFolderIfNotPresent(ushort const *,_GUID const *)

- ea: `0x180014bd0`
- end: `0x180014d55`
- name: `?CreateFolderIfNotPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009860`

## callees

- `0x1800040c0`
- `0x1800044e0`
- `0x18000a3e4`
- `0x18000a540`
- `0x18000a7a4`
- `0x18000ee08`
- `0x180014bd0`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014c3d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c51`

## string_xrefs

- `0x180014c0d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014c7a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014d20`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::CreateFolderIfNotPresent(char *a1, const struct _GUID *a2)
{
  int v2; // esi
  int IsFileOrFolderPresent; // eax
  unsigned int v5; // edi
  signed int LastError; // eax
  unsigned int v8; // eax
  char *v9; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF
  char *v12; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  v2 = (int)a2;
  IsFileOrFolderPresent = AppContainerRegistrationHelper::IsFileOrFolderPresent(a1, a2, (int *)&v11);
  v5 = IsFileOrFolderPresent;
  if ( IsFileOrFolderPresent < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x414,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsFileOrFolderPresent,
      (int)"Folder %ls",
      a1);
    return v5;
  }
  if ( !v11 && !CreateDirectoryW((LPCWSTR)a1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0x41A,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
           (const char *)(unsigned int)LastError,
           (__int64)"Folder %ls",
           a1);
    AppContainerRegistrationHelper::LogFailureWithContext(
      &AppModelAppContainerCreateFolderFailure,
      (unsigned __int16 *)a1,
      v5,
      0);
    if ( (unsigned int)dword_180031038 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
      {
        v11 = v5;
        v12 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180031038,
          (unsigned int)&unk_18002B140,
          v2,
          0,
          (__int64)&v12,
          (__int64)&v11);
      }
    }
    v8 = AppContainerRegistrationHelper::ReportACLsOfParentFolderIfNeeded(v5, (const unsigned __int16 *)a1);
    LODWORD(v9) = v5;
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x420,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v8,
      (__int64)"Hr 0x%0x for %ls.",
      v9,
      a1);
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180014bd0  mov     rax, rsp
0x180014bd3  mov     [rax+8], rbx
0x180014bd7  mov     [rax+10h], rsi
0x180014bdb  push    rdi
0x180014bdc  sub     rsp, 40h
0x180014be0  lea     r8, [rax+18h]; int *
0x180014be4  mov     dword ptr [rax+18h], 0
0x180014beb  mov     rsi, rdx
0x180014bee  mov     rbx, rcx
0x180014bf1  call    ?IsFileOrFolderPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFileOrFolderPresent(ushort const *,_GUID const *,int *)
0x180014bf6  mov     edi, eax
0x180014bf8  test    eax, eax
0x180014bfa  jns     short loc_180014C2D
0x180014bfc  mov     rcx, [rsp+48h]; this
0x180014c01  lea     rdx, aFolderLs; "Folder %ls"
0x180014c08  mov     [rsp+48h+var_20], rbx; char *
0x180014c0d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014c14  mov     [rsp+48h+var_28], rdx; int
0x180014c19  mov     r9d, eax; char *
0x180014c1c  mov     edx, 414h; void *
0x180014c21  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014c26  mov     eax, edi
0x180014c28  jmp     loc_180014D44
0x180014c2d  cmp     [rsp+48h+arg_10], 0
0x180014c32  jnz     loc_180014D42
0x180014c38  xor     edx, edx; lpSecurityAttributes
0x180014c3a  mov     rcx, rbx; lpPathName
0x180014c3d  call    cs:__imp_CreateDirectoryW
0x180014c44  nop     dword ptr [rax+rax+00h]
0x180014c49  test    eax, eax
0x180014c4b  jnz     loc_180014D42
0x180014c51  call    cs:__imp_GetLastError
0x180014c58  nop     dword ptr [rax+rax+00h]
0x180014c5d  test    eax, eax
0x180014c5f  jle     short loc_180014C69
0x180014c61  movzx   eax, ax
0x180014c64  or      eax, 80070000h
0x180014c69  mov     rcx, [rsp+48h]; this
0x180014c6e  lea     rdx, aFolderLs; "Folder %ls"
0x180014c75  mov     [rsp+48h+var_20], rbx; char *
0x180014c7a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014c81  mov     [rsp+48h+var_28], rdx; __int64
0x180014c86  mov     r9d, eax; char *
0x180014c89  mov     edx, 41Ah; void *
0x180014c8e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014c93  xor     r9d, r9d; struct _GUID *
0x180014c96  lea     rcx, AppModelAppContainerCreateFolderFailure; struct _EVENT_DESCRIPTOR *
0x180014c9d  mov     r8d, eax; int
0x180014ca0  mov     rdx, rbx; unsigned __int16 *
0x180014ca3  mov     edi, eax
0x180014ca5  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x180014caa  mov     ecx, cs:dword_180031038
0x180014cb0  cmp     ecx, 5
0x180014cb3  jbe     short loc_180014D05
0x180014cb5  mov     rdx, 400000000000h
0x180014cbf  lea     rcx, dword_180031038
0x180014cc6  call    _tlgKeywordOn
0x180014ccb  test    al, al
0x180014ccd  jz      short loc_180014D05
0x180014ccf  lea     rax, [rsp+48h+arg_10]
0x180014cd4  mov     [rsp+48h+arg_10], edi
0x180014cd8  mov     [rsp+48h+var_20], rax
0x180014cdd  lea     rdx, unk_18002B140
0x180014ce4  lea     rax, [rsp+48h+arg_18]
0x180014ce9  mov     [rsp+48h+arg_18], rbx
0x180014cee  xor     r9d, r9d
0x180014cf1  mov     [rsp+48h+var_28], rax
0x180014cf6  mov     r8, rsi
0x180014cf9  lea     rcx, dword_180031038
0x180014d00  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014d05  mov     rdx, rbx; unsigned __int16 *
0x180014d08  mov     ecx, edi; int
0x180014d0a  call    ?ReportACLsOfParentFolderIfNeeded@AppContainerRegistrationHelper@@CAJJPEBG@Z; AppContainerRegistrationHelper::ReportACLsOfParentFolderIfNeeded(long,ushort const *)
0x180014d0f  mov     rcx, [rsp+48h]; this
0x180014d14  lea     rdx, aHr0x0xForLs; "Hr 0x%0x for %ls."
0x180014d1b  mov     [rsp+48h+var_18], rbx
0x180014d20  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014d27  mov     dword ptr [rsp+48h+var_20], edi; char *
0x180014d2b  mov     r9d, eax; char *
0x180014d2e  mov     [rsp+48h+var_28], rdx; __int64
0x180014d33  mov     edx, 420h; void *
0x180014d38  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014d3d  jmp     loc_180014C26
0x180014d42  xor     eax, eax
0x180014d44  mov     rbx, [rsp+48h+arg_0]
0x180014d49  mov     rsi, [rsp+48h+arg_8]
0x180014d4e  add     rsp, 40h
0x180014d52  pop     rdi
0x180014d53  retn
```
