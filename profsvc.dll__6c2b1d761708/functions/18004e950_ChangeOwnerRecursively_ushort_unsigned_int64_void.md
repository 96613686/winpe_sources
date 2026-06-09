# _ChangeOwnerRecursively(ushort *,unsigned __int64,void *)

- ea: `0x18004e950`
- end: `0x18004ec04`
- name: `?_ChangeOwnerRecursively@@YAJPEAG_KPEAX@Z`
- size: `692`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031e70`
- `0x18004e950`

## callees

- `0x18000b060`
- `0x180024260`
- `0x180024540`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x18003701c`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ea1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ea1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea03`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004eb2e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004eb2e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004ea3c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004ea3c`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x18004e991`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x18004e991`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004eaf6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004eaf6`

## string_xrefs

- `0x18004e9aa`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004e9ed`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004ea59`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004eb73`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004eb91`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004ebcd`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _ChangeOwnerRecursively(unsigned __int16 *a1, __int64 a2, void *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  HANDLE ProcessHeap; // rax
  struct _WIN32_FIND_DATAW *v9; // rax
  struct _WIN32_FIND_DATAW *v10; // rdi
  HANDLE FirstFileW; // rbx
  const char *v12; // r9
  int LastError; // eax
  int v14; // esi
  DWORD v15; // eax
  __int64 v17; // rdx
  unsigned int psidGroup; // [rsp+20h] [rbp-40h]
  size_t pcchRemaining[3]; // [rsp+40h] [rbp-20h] BYREF
  char v20; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  PWSTR ppszEnd; // [rsp+98h] [rbp+38h] BYREF
  HANDLE v23; // [rsp+A8h] [rbp+48h] BYREF

  ppszEnd = 0;
  pcchRemaining[0] = 0;
  v5 = PathCchAddBackslashEx(a1, 0x104u, &ppszEnd, pcchRemaining);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)v5,
      psidGroup);
    return v6;
  }
  pcchRemaining[2] = (size_t)&ppszEnd;
  v20 = 1;
  v7 = StringCchCopyW(ppszEnd, pcchRemaining[0], L"*.*");
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)v7,
      psidGroup);
    goto LABEL_21;
  }
  ProcessHeap = GetProcessHeap();
  v9 = (struct _WIN32_FIND_DATAW *)HeapAlloc(ProcessHeap, 0, 0x250u);
  v10 = v9;
  pcchRemaining[1] = (size_t)v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)0x8007000ELL,
      psidGroup);
    *ppszEnd = 0;
    return v6;
  }
  FirstFileW = FindFirstFileW(a1, v9);
  v23 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x130,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
                  v12);
LABEL_8:
    v6 = LastError;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v23);
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v10);
    goto LABEL_21;
  }
  while ( 1 )
  {
    if ( StringIsEqual(v10->cFileName, L".") || StringIsEqual(v10->cFileName, L"..") )
      goto LABEL_15;
    v14 = StringCchCopyW(ppszEnd, pcchRemaining[0], v10->cFileName);
    if ( v14 < 0 )
      break;
    v15 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 1u, a3, 0, 0, 0);
    if ( v15 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x13D,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
                    (const char *)v15,
                    psidGroup);
      goto LABEL_8;
    }
    if ( (v10->dwFileAttributes & 0x410) == 0x10 )
    {
      v14 = _ChangeOwnerRecursively(a1, 0x104u, a3);
      if ( v14 < 0 )
      {
        v17 = 323;
        goto LABEL_20;
      }
    }
LABEL_15:
    if ( !FindNextFileW(FirstFileW, v10) )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v23);
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v10);
      *ppszEnd = 0;
      return 0;
    }
  }
  v17 = 314;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
    (const char *)(unsigned int)v14,
    psidGroup);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v23);
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v10);
  v6 = v14;
LABEL_21:
  *ppszEnd = 0;
  return v6;
}

```

## disassembly

```asm
0x18004e950  mov     [rsp-28h+arg_0], rbx
0x18004e955  mov     [rsp-28h+arg_10], rsi
0x18004e95a  mov     [rsp-28h+ppszEnd], rdx
0x18004e95f  push    rbp
0x18004e960  push    rdi
0x18004e961  push    r12
0x18004e963  push    r14
0x18004e965  push    r15
0x18004e967  mov     rbp, rsp
0x18004e96a  sub     rsp, 60h
0x18004e96e  mov     r12, r8
0x18004e971  mov     r15, rcx
0x18004e974  mov     [rbp+ppszEnd], 0
0x18004e97c  mov     [rbp+pcchRemaining], 0
0x18004e984  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18004e988  lea     r8, [rbp+ppszEnd]; ppszEnd
0x18004e98c  mov     edx, 104h; cchPath
0x18004e991  call    cs:__imp_PathCchAddBackslashEx
0x18004e998  nop     dword ptr [rax+rax+00h]
0x18004e99d  mov     ebx, eax
0x18004e99f  test    eax, eax
0x18004e9a1  jns     short loc_18004E9C0
0x18004e9a3  mov     rcx, [rbp+28h]; this
0x18004e9a7  mov     r9d, eax; char *
0x18004e9aa  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e9b1  mov     edx, 121h; void *
0x18004e9b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e9bb  jmp     loc_18004EBE8
0x18004e9c0  lea     rax, [rbp+ppszEnd]
0x18004e9c4  mov     [rbp+var_10], rax
0x18004e9c8  mov     [rbp+var_8], 1
0x18004e9cc  lea     r8, asc_1800683A8; "*.*"
0x18004e9d3  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x18004e9d7  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x18004e9db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004e9e0  mov     ebx, eax
0x18004e9e2  test    eax, eax
0x18004e9e4  jns     short loc_18004EA03
0x18004e9e6  mov     rcx, [rbp+28h]; this
0x18004e9ea  mov     r9d, eax; char *
0x18004e9ed  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e9f4  mov     edx, 128h; void *
0x18004e9f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e9fe  jmp     loc_18004EBB6
0x18004ea03  call    cs:__imp_GetProcessHeap
0x18004ea0a  nop     dword ptr [rax+rax+00h]
0x18004ea0f  mov     rcx, rax; hHeap
0x18004ea12  xor     edx, edx; dwFlags
0x18004ea14  mov     r8d, 250h; dwBytes
0x18004ea1a  call    cs:__imp_HeapAlloc
0x18004ea21  nop     dword ptr [rax+rax+00h]
0x18004ea26  mov     rdi, rax
0x18004ea29  mov     [rbp+var_18], rax
0x18004ea2d  test    rax, rax
0x18004ea30  jz      loc_18004EBC1
0x18004ea36  mov     rdx, rax; lpFindFileData
0x18004ea39  mov     rcx, r15; lpFileName
0x18004ea3c  call    cs:__imp_FindFirstFileW
0x18004ea43  nop     dword ptr [rax+rax+00h]
0x18004ea48  mov     rbx, rax
0x18004ea4b  mov     [rbp+arg_18], rax
0x18004ea4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004ea53  jnz     short loc_18004EA83
0x18004ea55  mov     rcx, [rbp+28h]; this
0x18004ea59  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004ea60  mov     edx, 130h; void *
0x18004ea65  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ea6a  mov     ebx, eax
0x18004ea6c  lea     rcx, [rbp+arg_18]
0x18004ea70  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004ea75  nop
0x18004ea76  mov     rcx, rdi
0x18004ea79  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004ea7e  jmp     loc_18004EBB6
0x18004ea83  lea     r14, [rdi+2Ch]
0x18004ea87  lea     rdx, asc_1800683B0; "."
0x18004ea8e  mov     rcx, r14; unsigned __int16 *
0x18004ea91  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18004ea96  test    eax, eax
0x18004ea98  jnz     loc_18004EB28
0x18004ea9e  lea     rdx, asc_1800683B4; ".."
0x18004eaa5  mov     rcx, r14; unsigned __int16 *
0x18004eaa8  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18004eaad  test    eax, eax
0x18004eaaf  jnz     short loc_18004EB28
0x18004eab1  mov     r8, r14; unsigned __int16 *
0x18004eab4  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x18004eab8  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x18004eabc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004eac1  mov     esi, eax
0x18004eac3  test    eax, eax
0x18004eac5  js      loc_18004EB89
0x18004eacb  mov     [rsp+60h+pSacl], 0; pSacl
0x18004ead4  mov     [rsp+60h+pDacl], 0; pDacl
0x18004eadd  mov     [rsp+60h+psidGroup], 0; int
0x18004eae6  mov     r9, r12; psidOwner
0x18004eae9  mov     eax, 1
0x18004eaee  mov     r8d, eax; SecurityInfo
0x18004eaf1  mov     edx, eax; ObjectType
0x18004eaf3  mov     rcx, r15; pObjectName
0x18004eaf6  call    cs:__imp_SetNamedSecurityInfoW
0x18004eafd  nop     dword ptr [rax+rax+00h]
0x18004eb02  test    eax, eax
0x18004eb04  jnz     short loc_18004EB6C
0x18004eb06  mov     eax, [rdi]
0x18004eb08  and     eax, 410h
0x18004eb0d  cmp     eax, 10h
0x18004eb10  jnz     short loc_18004EB28
0x18004eb12  mov     r8, r12; void *
0x18004eb15  mov     edx, 104h; unsigned __int64
0x18004eb1a  mov     rcx, r15; unsigned __int16 *
0x18004eb1d  call    ?_ChangeOwnerRecursively@@YAJPEAG_KPEAX@Z; _ChangeOwnerRecursively(ushort *,unsigned __int64,void *)
0x18004eb22  mov     esi, eax
0x18004eb24  test    eax, eax
0x18004eb26  js      short loc_18004EB65
0x18004eb28  mov     rdx, rdi; lpFindFileData
0x18004eb2b  mov     rcx, rbx; hFindFile
0x18004eb2e  call    cs:__imp_FindNextFileW
0x18004eb35  nop     dword ptr [rax+rax+00h]
0x18004eb3a  test    eax, eax
0x18004eb3c  jnz     loc_18004EA87
0x18004eb42  lea     rcx, [rbp+arg_18]
0x18004eb46  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004eb4b  nop
0x18004eb4c  mov     rcx, rdi
0x18004eb4f  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004eb54  nop
0x18004eb55  xor     ecx, ecx
0x18004eb57  mov     rax, [rbp+ppszEnd]
0x18004eb5b  mov     [rax], cx
0x18004eb5e  xor     eax, eax
0x18004eb60  jmp     loc_18004EBEA
0x18004eb65  mov     edx, 143h
0x18004eb6a  jmp     short loc_18004EB8E
0x18004eb6c  mov     rcx, [rbp+28h]; this
0x18004eb70  mov     r9d, eax; char *
0x18004eb73  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004eb7a  mov     edx, 13Dh; void *
0x18004eb7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004eb84  jmp     loc_18004EA6A
0x18004eb89  mov     edx, 13Ah; void *
0x18004eb8e  mov     r9d, esi; char *
0x18004eb91  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004eb98  mov     rcx, [rbp+28h]; this
0x18004eb9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eba1  nop
0x18004eba2  lea     rcx, [rbp+arg_18]
0x18004eba6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004ebab  nop
0x18004ebac  mov     rcx, rdi
0x18004ebaf  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004ebb4  mov     ebx, esi
0x18004ebb6  xor     ecx, ecx
0x18004ebb8  mov     rax, [rbp+ppszEnd]
0x18004ebbc  mov     [rax], cx
0x18004ebbf  jmp     short loc_18004EBE8
0x18004ebc1  mov     rcx, [rbp+28h]; this
0x18004ebc5  mov     ebx, 8007000Eh
0x18004ebca  mov     r9d, ebx; char *
0x18004ebcd  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004ebd4  mov     edx, 12Ch; void *
0x18004ebd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ebde  nop
0x18004ebdf  xor     edx, edx
0x18004ebe1  mov     rcx, [rbp+ppszEnd]
0x18004ebe5  mov     [rcx], dx
0x18004ebe8  mov     eax, ebx
0x18004ebea  lea     r11, [rsp+60h+var_s0]
0x18004ebef  mov     rbx, [r11+30h]
0x18004ebf3  mov     rsi, [r11+40h]
0x18004ebf7  mov     rsp, r11
0x18004ebfa  pop     r15
0x18004ebfc  pop     r14
0x18004ebfe  pop     r12
0x18004ec00  pop     rdi
0x18004ec01  pop     rbp
0x18004ec02  retn
```
