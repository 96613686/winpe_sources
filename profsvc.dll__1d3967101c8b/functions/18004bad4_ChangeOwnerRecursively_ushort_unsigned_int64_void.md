# _ChangeOwnerRecursively(ushort *,unsigned __int64,void *)

- ea: `0x18004bad4`
- end: `0x18004bd63`
- name: `?_ChangeOwnerRecursively@@YAJPEAG_KPEAX@Z`
- size: `655`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003962c`
- `0x18004bad4`

## callees

- `0x1800053a0`
- `0x1800212a0`
- `0x180021980`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e648`
- `0x180036938`
- `0x18004bad4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bb92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bb92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bb81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bb81`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004bc94`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004bc94`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004bbae`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004bbae`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x18004bb15`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x18004bb15`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004bc62`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004bc62`

## string_xrefs

- `0x18004bb28`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004bb6b`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004bbc5`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004bcd3`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004bcf1`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18004bd2d`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

## pseudocode

```c
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
0x18004bad4  mov     [rsp-28h+arg_0], rbx
0x18004bad9  mov     [rsp-28h+arg_10], rsi
0x18004bade  mov     [rsp-28h+ppszEnd], rdx
0x18004bae3  push    rbp
0x18004bae4  push    rdi
0x18004bae5  push    r12
0x18004bae7  push    r14
0x18004bae9  push    r15
0x18004baeb  mov     rbp, rsp
0x18004baee  sub     rsp, 60h
0x18004baf2  mov     r12, r8
0x18004baf5  mov     r15, rcx
0x18004baf8  mov     [rbp+ppszEnd], 0
0x18004bb00  mov     [rbp+pcchRemaining], 0
0x18004bb08  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18004bb0c  lea     r8, [rbp+ppszEnd]; ppszEnd
0x18004bb10  mov     edx, 104h; cchPath
0x18004bb15  call    cs:__imp_PathCchAddBackslashEx
0x18004bb1b  mov     ebx, eax
0x18004bb1d  test    eax, eax
0x18004bb1f  jns     short loc_18004BB3E
0x18004bb21  mov     rcx, [rbp+28h]; this
0x18004bb25  mov     r9d, eax; char *
0x18004bb28  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bb2f  mov     edx, 121h; void *
0x18004bb34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb39  jmp     loc_18004BD48
0x18004bb3e  lea     rax, [rbp+ppszEnd]
0x18004bb42  mov     [rbp+var_10], rax
0x18004bb46  mov     [rbp+var_8], 1
0x18004bb4a  lea     r8, asc_180065420; "*.*"
0x18004bb51  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x18004bb55  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x18004bb59  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004bb5e  mov     ebx, eax
0x18004bb60  test    eax, eax
0x18004bb62  jns     short loc_18004BB81
0x18004bb64  mov     rcx, [rbp+28h]; this
0x18004bb68  mov     r9d, eax; char *
0x18004bb6b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bb72  mov     edx, 128h; void *
0x18004bb77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb7c  jmp     loc_18004BD16
0x18004bb81  call    cs:__imp_GetProcessHeap
0x18004bb87  mov     rcx, rax; hHeap
0x18004bb8a  xor     edx, edx; dwFlags
0x18004bb8c  mov     r8d, 250h; dwBytes
0x18004bb92  call    cs:__imp_HeapAlloc
0x18004bb98  mov     rdi, rax
0x18004bb9b  mov     [rbp+var_18], rax
0x18004bb9f  test    rax, rax
0x18004bba2  jz      loc_18004BD21
0x18004bba8  mov     rdx, rax; lpFindFileData
0x18004bbab  mov     rcx, r15; lpFileName
0x18004bbae  call    cs:__imp_FindFirstFileW
0x18004bbb4  mov     rbx, rax
0x18004bbb7  mov     [rbp+arg_18], rax
0x18004bbbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004bbbf  jnz     short loc_18004BBEF
0x18004bbc1  mov     rcx, [rbp+28h]; this
0x18004bbc5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bbcc  mov     edx, 130h; void *
0x18004bbd1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004bbd6  mov     ebx, eax
0x18004bbd8  lea     rcx, [rbp+arg_18]
0x18004bbdc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004bbe1  nop
0x18004bbe2  mov     rcx, rdi
0x18004bbe5  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004bbea  jmp     loc_18004BD16
0x18004bbef  lea     r14, [rdi+2Ch]
0x18004bbf3  lea     rdx, asc_180065428; "."
0x18004bbfa  mov     rcx, r14; unsigned __int16 *
0x18004bbfd  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18004bc02  test    eax, eax
0x18004bc04  jnz     loc_18004BC8E
0x18004bc0a  lea     rdx, asc_18006542C; ".."
0x18004bc11  mov     rcx, r14; unsigned __int16 *
0x18004bc14  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18004bc19  test    eax, eax
0x18004bc1b  jnz     short loc_18004BC8E
0x18004bc1d  mov     r8, r14; unsigned __int16 *
0x18004bc20  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x18004bc24  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x18004bc28  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004bc2d  mov     esi, eax
0x18004bc2f  test    eax, eax
0x18004bc31  js      loc_18004BCE9
0x18004bc37  mov     [rsp+60h+pSacl], 0; pSacl
0x18004bc40  mov     [rsp+60h+pDacl], 0; pDacl
0x18004bc49  mov     [rsp+60h+psidGroup], 0; int
0x18004bc52  mov     r9, r12; psidOwner
0x18004bc55  mov     eax, 1
0x18004bc5a  mov     r8d, eax; SecurityInfo
0x18004bc5d  mov     edx, eax; ObjectType
0x18004bc5f  mov     rcx, r15; pObjectName
0x18004bc62  call    cs:__imp_SetNamedSecurityInfoW
0x18004bc68  test    eax, eax
0x18004bc6a  jnz     short loc_18004BCCC
0x18004bc6c  mov     eax, [rdi]
0x18004bc6e  and     eax, 410h
0x18004bc73  cmp     eax, 10h
0x18004bc76  jnz     short loc_18004BC8E
0x18004bc78  mov     r8, r12; void *
0x18004bc7b  mov     edx, 104h; unsigned __int64
0x18004bc80  mov     rcx, r15; unsigned __int16 *
0x18004bc83  call    ?_ChangeOwnerRecursively@@YAJPEAG_KPEAX@Z; _ChangeOwnerRecursively(ushort *,unsigned __int64,void *)
0x18004bc88  mov     esi, eax
0x18004bc8a  test    eax, eax
0x18004bc8c  js      short loc_18004BCC5
0x18004bc8e  mov     rdx, rdi; lpFindFileData
0x18004bc91  mov     rcx, rbx; hFindFile
0x18004bc94  call    cs:__imp_FindNextFileW
0x18004bc9a  test    eax, eax
0x18004bc9c  jnz     loc_18004BBF3
0x18004bca2  lea     rcx, [rbp+arg_18]
0x18004bca6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004bcab  nop
0x18004bcac  mov     rcx, rdi
0x18004bcaf  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004bcb4  nop
0x18004bcb5  xor     ecx, ecx
0x18004bcb7  mov     rax, [rbp+ppszEnd]
0x18004bcbb  mov     [rax], cx
0x18004bcbe  xor     eax, eax
0x18004bcc0  jmp     loc_18004BD4A
0x18004bcc5  mov     edx, 143h
0x18004bcca  jmp     short loc_18004BCEE
0x18004bccc  mov     rcx, [rbp+28h]; this
0x18004bcd0  mov     r9d, eax; char *
0x18004bcd3  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bcda  mov     edx, 13Dh; void *
0x18004bcdf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004bce4  jmp     loc_18004BBD6
0x18004bce9  mov     edx, 13Ah; void *
0x18004bcee  mov     r9d, esi; char *
0x18004bcf1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bcf8  mov     rcx, [rbp+28h]; this
0x18004bcfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd01  nop
0x18004bd02  lea     rcx, [rbp+arg_18]
0x18004bd06  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004bd0b  nop
0x18004bd0c  mov     rcx, rdi
0x18004bd0f  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004bd14  mov     ebx, esi
0x18004bd16  xor     ecx, ecx
0x18004bd18  mov     rax, [rbp+ppszEnd]
0x18004bd1c  mov     [rax], cx
0x18004bd1f  jmp     short loc_18004BD48
0x18004bd21  mov     rcx, [rbp+28h]; this
0x18004bd25  mov     ebx, 8007000Eh
0x18004bd2a  mov     r9d, ebx; char *
0x18004bd2d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bd34  mov     edx, 12Ch; void *
0x18004bd39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd3e  nop
0x18004bd3f  xor     edx, edx
0x18004bd41  mov     rcx, [rbp+ppszEnd]
0x18004bd45  mov     [rcx], dx
0x18004bd48  mov     eax, ebx
0x18004bd4a  lea     r11, [rsp+60h+var_s0]
0x18004bd4f  mov     rbx, [r11+30h]
0x18004bd53  mov     rsi, [r11+40h]
0x18004bd57  mov     rsp, r11
0x18004bd5a  pop     r15
0x18004bd5c  pop     r14
0x18004bd5e  pop     r12
0x18004bd60  pop     rdi
0x18004bd61  pop     rbp
0x18004bd62  retn
```
