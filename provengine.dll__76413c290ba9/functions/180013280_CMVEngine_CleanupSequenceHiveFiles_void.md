# CMVEngine::CleanupSequenceHiveFiles(void)

- ea: `0x180013280`
- end: `0x18001350e`
- name: `?CleanupSequenceHiveFiles@CMVEngine@@AEAAJXZ`
- size: `654`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180020190`

## callees

- `0x1800018ec`
- `0x1800098bc`
- `0x18000b030`
- `0x180013280`
- `0x180021f40`
- `0x1800382e0`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001339c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800134a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800134de`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001339c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800134a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800134de`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001342e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001342e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800132c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800132c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013414`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800134c7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800134c7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001340a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001340a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001335d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001335d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800134b1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800134b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CMVEngine::CleanupSequenceHiveFiles(CMVEngine *this)
{
  HKEY v2; // rsi
  DWORD LastError; // ebx
  char *v4; // rsi
  unsigned __int64 v5; // r8
  const WCHAR *v6; // rcx
  __int64 *FirstFileW; // rbx
  const char *v8; // r9
  unsigned int v9; // ebx
  unsigned __int64 v11; // r8
  DWORD i; // edi
  const WCHAR *v13; // rcx
  signed int v14; // ecx
  __int64 v15; // r9
  __int64 *v16; // rax
  signed int v17; // [rsp+30h] [rbp-2E8h] BYREF
  __int64 *v18[2]; // [rsp+38h] [rbp-2E0h] BYREF
  LPCWSTR Src[3]; // [rsp+48h] [rbp-2D0h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-2B8h]
  LPCWSTR lpFileName[3]; // [rsp+68h] [rbp-2B0h] BYREF
  unsigned __int64 v22; // [rsp+80h] [rbp-298h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-288h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v2 = (HKEY)*((_QWORD *)this + 22);
  if ( !v2 )
    return 0;
  LastError = GetLastError();
  RegCloseKey(v2);
  SetLastError(LastError);
  *((_QWORD *)this + 22) = 0;
  v4 = *(char **)ProvisioningPaths::GetProgramDataProvisioningFolderPath();
  v22 = 7;
  lpFileName[2] = 0;
  LOWORD(lpFileName[0]) = 0;
  if ( *(_WORD *)v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&v4[2 * v5] );
  }
  else
  {
    v5 = 0;
  }
  std::wstring::assign(lpFileName, v4, v5);
  std::wstring::append((const void **)lpFileName, (char *)L"*Sequence.dat*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = (const WCHAR *)lpFileName;
  if ( v22 >= 8 )
    v6 = lpFileName[0];
  FirstFileW = (__int64 *)FindFirstFileW(v6, &FindFileData);
  v18[1] = FirstFileW;
  if ( FirstFileW == (__int64 *)-1LL )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x775,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
           v8);
    if ( v22 >= 8 )
      operator delete((void *)lpFileName[0]);
    return v9;
  }
  else
  {
    do
    {
      v20 = 7;
      Src[2] = 0;
      LOWORD(Src[0]) = 0;
      if ( *(_WORD *)v4 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v4[2 * v11] );
      }
      else
      {
        v11 = 0;
      }
      std::wstring::assign(Src, v4, v11);
      std::wstring::append((const void **)Src, (char *)FindFileData.cFileName);
      for ( i = 0; ; Sleep(i) )
      {
        v13 = (const WCHAR *)Src;
        if ( v20 >= 8 )
          v13 = Src[0];
        if ( DeleteFileW(v13) )
          break;
        v14 = GetLastError();
        if ( v14 != 32 || i >= 0xEA60 )
        {
          if ( (unsigned int)dword_18005A000 > 3 )
          {
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0x80070000;
            v17 = v14;
            v16 = (__int64 *)Src;
            if ( v20 >= 8 )
              v16 = (__int64 *)Src[0];
            v18[0] = v16;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (__int64)&dword_18005A000,
              (__int64)&dword_18004EA74,
              0,
              v15,
              v18,
              (__int64)&v17);
          }
          break;
        }
        i += 100;
      }
      if ( v20 >= 8 )
        operator delete((void *)Src[0]);
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( FirstFileW )
      FindClose(FirstFileW);
    if ( v22 >= 8 )
      operator delete((void *)lpFileName[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x180013280  push    rbx
0x180013282  push    rsi
0x180013283  push    rdi
0x180013284  push    r14
0x180013286  sub     rsp, 2F8h
0x18001328d  mov     rax, cs:__security_cookie
0x180013294  xor     rax, rsp
0x180013297  mov     [rsp+318h+var_38], rax
0x18001329f  mov     rdi, rcx
0x1800132a2  mov     rsi, [rcx+0B0h]
0x1800132a9  xor     r14d, r14d
0x1800132ac  test    rsi, rsi
0x1800132af  jz      loc_1800134E8
0x1800132b5  call    cs:__imp_GetLastError
0x1800132bb  mov     ebx, eax
0x1800132bd  mov     rcx, rsi; hKey
0x1800132c0  call    cs:__imp_RegCloseKey
0x1800132c6  mov     ecx, ebx; dwErrCode
0x1800132c8  call    cs:__imp_SetLastError
0x1800132ce  mov     [rdi+0B0h], r14
0x1800132d5  call    ?GetProgramDataProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)
0x1800132da  mov     rsi, [rax]
0x1800132dd  mov     [rsp+318h+var_298], 7
0x1800132e9  mov     [rsp+318h+var_2A0], r14
0x1800132ee  mov     word ptr [rsp+318h+lpFileName], r14w
0x1800132f4  cmp     [rsi], r14w
0x1800132f8  jnz     short loc_1800132FF
0x1800132fa  mov     r8d, r14d
0x1800132fd  jmp     short loc_18001330D
0x1800132ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013303  inc     r8
0x180013306  cmp     [rsi+r8*2], r14w
0x18001330b  jnz     short loc_180013303
0x18001330d  mov     rdx, rsi; Src
0x180013310  lea     rcx, [rsp+318h+lpFileName]; void *
0x180013315  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001331a  nop
0x18001331b  lea     rdx, aSequenceDat; "*Sequence.dat*"
0x180013322  lea     rcx, [rsp+318h+lpFileName]; Src
0x180013327  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001332c  xor     edx, edx; Val
0x18001332e  mov     r8d, 250h; Size
0x180013334  lea     rcx, [rsp+318h+FindFileData]; void *
0x18001333c  call    memset_0
0x180013341  lea     rcx, [rsp+318h+lpFileName]
0x180013346  cmp     [rsp+318h+var_298], 8
0x18001334f  cmovnb  rcx, [rsp+318h+lpFileName]; lpFileName
0x180013355  lea     rdx, [rsp+318h+FindFileData]; lpFindFileData
0x18001335d  call    cs:__imp_FindFirstFileW
0x180013363  mov     rbx, rax
0x180013366  mov     [rsp+318h+var_2D8], rax
0x18001336b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001336f  jnz     short loc_1800133A9
0x180013371  mov     rcx, [rsp+318h]; this
0x180013379  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180013380  mov     edx, 775h; void *
0x180013385  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001338a  mov     ebx, eax
0x18001338c  cmp     [rsp+318h+var_298], 8
0x180013395  jb      short loc_1800133A2
0x180013397  mov     rcx, [rsp+318h+lpFileName]
0x18001339c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800133a2  mov     eax, ebx
0x1800133a4  jmp     loc_1800134F0
0x1800133a9  mov     [rsp+318h+var_2B8], 7
0x1800133b2  mov     [rsp+318h+var_2C0], r14
0x1800133b7  mov     word ptr [rsp+318h+Src], r14w
0x1800133bd  cmp     [rsi], r14w
0x1800133c1  jnz     short loc_1800133C8
0x1800133c3  mov     r8, r14
0x1800133c6  jmp     short loc_1800133D6
0x1800133c8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800133cc  inc     r8
0x1800133cf  cmp     [rsi+r8*2], r14w
0x1800133d4  jnz     short loc_1800133CC
0x1800133d6  mov     rdx, rsi; Src
0x1800133d9  lea     rcx, [rsp+318h+Src]; void *
0x1800133de  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800133e3  nop
0x1800133e4  lea     rdx, [rsp+318h+FindFileData.cFileName]; void *
0x1800133ec  lea     rcx, [rsp+318h+Src]; Src
0x1800133f1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800133f6  mov     edi, r14d
0x1800133f9  lea     rcx, [rsp+318h+Src]
0x1800133fe  cmp     [rsp+318h+var_2B8], 8
0x180013404  cmovnb  rcx, [rsp+318h+Src]; lpFileName
0x18001340a  call    cs:__imp_DeleteFileW
0x180013410  test    eax, eax
0x180013412  jnz     short loc_180013493
0x180013414  call    cs:__imp_GetLastError
0x18001341a  mov     ecx, eax
0x18001341c  cmp     eax, 20h ; ' '
0x18001341f  jnz     short loc_180013436
0x180013421  cmp     edi, 0EA60h
0x180013427  jnb     short loc_180013436
0x180013429  add     edi, 64h ; 'd'
0x18001342c  mov     ecx, edi; dwMilliseconds
0x18001342e  call    cs:__imp_Sleep
0x180013434  jmp     short loc_1800133F9
0x180013436  mov     eax, cs:dword_18005A000
0x18001343c  cmp     eax, 3
0x18001343f  jbe     short loc_180013493
0x180013441  test    ecx, ecx
0x180013443  jle     short loc_18001344E
0x180013445  movzx   ecx, cx
0x180013448  or      ecx, 80070000h
0x18001344e  mov     [rsp+318h+var_2E8], ecx
0x180013452  lea     rax, [rsp+318h+Src]
0x180013457  cmp     [rsp+318h+var_2B8], 8
0x18001345d  cmovnb  rax, [rsp+318h+Src]
0x180013463  mov     [rsp+318h+var_2E0], rax
0x180013468  lea     rax, [rsp+318h+var_2E8]
0x18001346d  mov     [rsp+318h+var_2F0], rax
0x180013472  lea     rax, [rsp+318h+var_2E0]
0x180013477  mov     [rsp+318h+var_2F8], rax
0x18001347c  xor     r8d, r8d
0x18001347f  lea     rdx, dword_18004EA74
0x180013486  lea     rcx, dword_18005A000
0x18001348d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013492  nop
0x180013493  cmp     [rsp+318h+var_2B8], 8
0x180013499  jb      short loc_1800134A6
0x18001349b  mov     rcx, [rsp+318h+Src]
0x1800134a0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800134a6  lea     rdx, [rsp+318h+FindFileData]; lpFindFileData
0x1800134ae  mov     rcx, rbx; hFindFile
0x1800134b1  call    cs:__imp_FindNextFileW
0x1800134b7  test    eax, eax
0x1800134b9  jnz     loc_1800133A9
0x1800134bf  test    rbx, rbx
0x1800134c2  jz      short loc_1800134CE
0x1800134c4  mov     rcx, rbx; hFindFile
0x1800134c7  call    cs:__imp_FindClose
0x1800134cd  nop
0x1800134ce  cmp     [rsp+318h+var_298], 8
0x1800134d7  jb      short loc_1800134E4
0x1800134d9  mov     rcx, [rsp+318h+lpFileName]
0x1800134de  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800134e4  xor     eax, eax
0x1800134e6  jmp     short loc_1800134F0
0x1800134e8  xor     eax, eax
0x1800134ea  jmp     short loc_1800134F0
0x1800134ec  mov     eax, [rsp+318h+var_2E8]
0x1800134f0  mov     rcx, [rsp+318h+var_38]
0x1800134f8  xor     rcx, rsp; StackCookie
0x1800134fb  call    __security_check_cookie
0x180013500  add     rsp, 2F8h
0x180013507  pop     r14
0x180013509  pop     rdi
0x18001350a  pop     rsi
0x18001350b  pop     rbx
0x18001350c  retn
```
