# WriteBackupPublicKeyToStorage(void *,void *,ushort *,uchar *,ulong)

- ea: `0x1800278c4`
- end: `0x180027f0e`
- name: `?WriteBackupPublicKeyToStorage@@YAKPEAX0PEAGPEAEK@Z`
- size: `1610`
- prototype: `unsigned int __usercall@<eax>(HANDLE Token@<rcx>, PSID Sid@<rdx>, unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180024f38`

## callees

- `0x180001184`
- `0x1800060e0`
- `0x180007f10`
- `0x1800123e8`
- `0x18001467c`
- `0x18001d810`
- `0x180023d84`
- `0x1800278c4`
- `0x180029818`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180027a6e`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180027a6e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027edc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d3b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027a0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027ecb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027ecb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027ab4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027ab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027eb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027eb5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027c90`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027d1f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027c90`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027d1f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180027c11`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180027c11`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180027e63`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180027e8d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180027e63`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180027e8d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800279d5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800279d5`

## string_xrefs

- `0x180027974`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027a95`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027b24`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027bd8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027c42`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027cc1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027d53`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027dc6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall WriteBackupPublicKeyToStorage(
        HANDLE Token,
        PSID Sid,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  HANDLE v7; // r13
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  DWORD LastError; // eax
  HANDLE FileMappingW; // r12
  char *v15; // r14
  char *v16; // rsi
  UCHAR *v17; // r15
  __time64_t v18; // rdi
  DWORD v19; // edi
  __int64 v20; // r9
  __int64 v21; // rcx
  HANDLE v22; // rbx
  UCHAR *v23; // rax
  DWORD v24; // eax
  size_t v25; // rbx
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  char *v29; // rax
  size_t v30; // r8
  char *v31; // rcx
  void *v32; // rdx
  char *v33; // rax
  unsigned int v34; // r13d
  __int64 v35; // r9
  DWORD dwMaximumSizeLow; // [rsp+30h] [rbp-2F8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-2F4h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-2F0h] BYREF
  int v39; // [rsp+40h] [rbp-2E8h] BYREF
  HANDLE v40; // [rsp+48h] [rbp-2E0h]
  unsigned int v41; // [rsp+50h] [rbp-2D8h]
  DWORD v42; // [rsp+54h] [rbp-2D4h]
  HLOCAL hMem; // [rsp+58h] [rbp-2D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+60h] [rbp-2C8h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-2C4h] BYREF
  void *Src; // [rsp+68h] [rbp-2C0h]
  HANDLE v47; // [rsp+70h] [rbp-2B8h]
  char *v48; // [rsp+78h] [rbp-2B0h]
  char *v49; // [rsp+80h] [rbp-2A8h]
  UCHAR *v50; // [rsp+88h] [rbp-2A0h]
  unsigned __int16 *v51; // [rsp+90h] [rbp-298h]
  HANDLE v52; // [rsp+98h] [rbp-290h]
  unsigned __int16 v53[3]; // [rsp+A0h] [rbp-288h] BYREF
  WCHAR ReferencedDomainName[21]; // [rsp+A6h] [rbp-282h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-258h] BYREF

  Src = a4;
  v51 = a3;
  v40 = Token;
  v52 = Token;
  v41 = Size;
  cchName = 257;
  cchReferencedDomainName = 19;
  v7 = 0;
  hFile = 0;
  peUse = 0;
  hMem = 0;
  dwMaximumSizeLow = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
  {
    v8 = StringCchCopyW(v53, 0x13u, L"BK-");
    if ( v8 )
    {
      v9 = (unsigned __int16)v8;
      v10 = 1345;
LABEL_4:
      v11 = v9;
LABEL_5:
      DebugTraceError(v11, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v10);
      return v9;
    }
  }
  else if ( (unsigned int)StringCchCopyW(v53, 0x13u, L"BK-") )
  {
    v10 = 1359;
    v9 = 122;
    goto LABEL_4;
  }
  cchReferencedDomainName -= 3;
  if ( !LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v10 = 1375;
LABEL_10:
    v9 = LastError;
    v11 = LastError;
    goto LABEL_5;
  }
  cchReferencedDomainName += 3;
  if ( Token && !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v10 = 1390;
    goto LABEL_10;
  }
  FileMappingW = 0;
  v47 = 0;
  v15 = 0;
  v48 = 0;
  v16 = 0;
  v49 = 0;
  v17 = 0;
  v50 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
  {
    v18 = _time64(0);
    if ( v18 == -1 )
    {
      v19 = 31;
      v20 = 1405;
      v21 = 31;
LABEL_17:
      DebugTraceError(v21, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v20);
LABEL_18:
      v22 = v40;
      goto LABEL_40;
    }
    LODWORD(v7) = Size + 8;
    v23 = (UCHAR *)LocalAlloc(0, Size + 8);
    v17 = v23;
    v50 = v23;
    if ( !v23 )
    {
      v19 = 14;
LABEL_21:
      v7 = hFile;
      goto LABEL_18;
    }
    memcpy_0(v23, Src, Size);
    *(_QWORD *)&v17[Size] = v18;
    v22 = v40;
    v24 = LogonCredGenerateSignature((__int64)v40, v17, (ULONG)v7, 0, (unsigned int **)&hMem, &dwMaximumSizeLow);
    v19 = v24;
    if ( v24 )
    {
      DebugTraceError(v24, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1438);
      v7 = hFile;
      goto LABEL_40;
    }
    v39 = 8;
    v25 = dwMaximumSizeLow;
    v26 = (_DWORD)v7 + dwMaximumSizeLow + 16;
  }
  else
  {
    v27 = LogonCredGenerateSignature((__int64)Token, (UCHAR *)Src, Size, 0, (unsigned int **)&hMem, &dwMaximumSizeLow);
    v19 = v27;
    if ( v27 )
    {
      v20 = 1461;
      v21 = v27;
      goto LABEL_17;
    }
    v39 = 0;
    v25 = dwMaximumSizeLow;
    v26 = dwMaximumSizeLow + v41 + 12;
  }
  dwMaximumSizeLow = v26;
  v28 = OpenFileInStorageArea(0, 0xC0000000, v51, v53, &hFile);
  v19 = v28;
  if ( v28 )
  {
    DebugTraceError(v28, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1478);
    goto LABEL_21;
  }
  FileMappingW = CreateFileMappingW(hFile, 0, 4u, 0, dwMaximumSizeLow, 0);
  v47 = FileMappingW;
  if ( FileMappingW )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
    {
      v29 = (char *)MapViewOfFile(FileMappingW, 2u, 0, 0, dwMaximumSizeLow);
      v15 = v29;
      v48 = v29;
      if ( !v29 )
      {
        v19 = GetLastError();
        v42 = v19;
        DebugTraceError(v19, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1511);
        v7 = hFile;
        v22 = v40;
        goto LABEL_40;
      }
      *(_DWORD *)v29 = 2;
      *((_DWORD *)v29 + 1) = v41;
      *((_DWORD *)v29 + 2) = v39;
      *((_DWORD *)v29 + 3) = v25;
      memcpy_0(v29 + 16, hMem, v25);
      v30 = (unsigned int)v7;
      v31 = v15 + 16;
      v32 = v17;
    }
    else
    {
      v33 = (char *)MapViewOfFile(FileMappingW, 2u, 0, 0, dwMaximumSizeLow);
      v16 = v33;
      v49 = v33;
      if ( !v33 )
      {
        v19 = GetLastError();
        v42 = v19;
        DebugTraceError(v19, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1534);
        v7 = hFile;
        v22 = v40;
        goto LABEL_40;
      }
      *(_DWORD *)v33 = 1;
      *((_DWORD *)v33 + 2) = v25;
      v34 = v41;
      *((_DWORD *)v33 + 1) = v41;
      memcpy_0(v33 + 12, hMem, v25);
      v30 = v34;
      v31 = v16 + 12;
      v32 = Src;
    }
    memcpy_0(&v31[v25], v32, v30);
    v7 = hFile;
    v22 = v40;
    goto LABEL_40;
  }
  v19 = GetLastError();
  v42 = v19;
  DebugTraceError(v19, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1496);
  v7 = hFile;
  v22 = v40;
LABEL_40:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x200000000000LL) )
    {
      v39 = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18004C260,
        (int)byte_1800449D1,
        0,
        v35,
        (__int64)&v39);
    }
    if ( v15 )
      UnmapViewOfFile(v15);
    if ( v17 )
      LocalFree(v17);
  }
  else if ( v16 )
  {
    UnmapViewOfFile(v16);
  }
  if ( FileMappingW )
    CloseHandle(FileMappingW);
  if ( v7 )
    CloseHandle(v7);
  if ( hMem )
    LocalFree(hMem);
  if ( v22 )
    RevertToSelf();
  return v19;
}

```

## disassembly

```asm
0x1800278c4  push    rbx
0x1800278c6  push    rsi
0x1800278c7  push    rdi
0x1800278c8  push    r12
0x1800278ca  push    r13
0x1800278cc  push    r14
0x1800278ce  push    r15
0x1800278d0  sub     rsp, 2F0h
0x1800278d7  mov     rax, cs:__security_cookie
0x1800278de  xor     rax, rsp
0x1800278e1  mov     [rsp+328h+var_48], rax
0x1800278e9  mov     [rsp+328h+Src], r9
0x1800278ee  mov     [rsp+328h+var_298], r8
0x1800278f6  mov     rsi, rdx
0x1800278f9  mov     rdi, rcx
0x1800278fc  mov     [rsp+328h+var_2E0], rcx
0x180027901  mov     [rsp+328h+var_290], rcx
0x180027909  mov     ebx, dword ptr [rsp+328h+Size]
0x180027910  mov     dword ptr [rsp+328h+var_2D8], ebx
0x180027914  mov     [rsp+328h+cchName], 101h
0x18002791c  mov     r14d, 13h
0x180027922  mov     [rsp+328h+var_2F4], r14d
0x180027927  xor     r13d, r13d
0x18002792a  mov     [rsp+328h+hFile], r13
0x18002792f  mov     [rsp+328h+var_2C8], r13d
0x180027934  mov     [rsp+328h+hMem], r13
0x180027939  mov     [rsp+328h+dwMaximumSizeLow], r13d
0x18002793e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180027945  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x18002794a  lea     r8, aBk; "BK-"
0x180027951  mov     edx, r14d; unsigned __int64
0x180027954  lea     rcx, [rsp+328h+var_288]; unsigned __int16 *
0x18002795c  test    al, al
0x18002795e  jz      short loc_18002798E
0x180027960  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027965  test    eax, eax
0x180027967  jz      short loc_1800279A4
0x180027969  movzx   ebx, ax
0x18002796c  mov     r9d, 541h
0x180027972  mov     ecx, ebx
0x180027974  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002797b  lea     rdx, aDwlasterror; "dwLastError"
0x180027982  call    DebugTraceError
0x180027987  mov     eax, ebx
0x180027989  jmp     loc_180027EEA
0x18002798e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027993  test    eax, eax
0x180027995  jz      short loc_1800279A4
0x180027997  mov     r9d, 54Fh
0x18002799d  mov     ebx, 7Ah ; 'z'
0x1800279a2  jmp     short loc_180027972
0x1800279a4  add     [rsp+328h+var_2F4], 0FFFFFFFDh
0x1800279a9  lea     rax, [rsp+328h+var_2C8]
0x1800279ae  mov     [rsp+328h+peUse], rax; peUse
0x1800279b3  lea     rax, [rsp+328h+var_2F4]
0x1800279b8  mov     [rsp+328h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800279bd  lea     r9, [rsp+328h+ReferencedDomainName]; ReferencedDomainName
0x1800279c5  lea     r8, [rsp+328h+cchName]; cchName
0x1800279ca  lea     rdx, [rsp+328h+Name]; Name
0x1800279d2  mov     rcx, rsi; Sid
0x1800279d5  call    cs:__imp_LookupAccountSidLocalW
0x1800279dc  nop     dword ptr [rax+rax+00h]
0x1800279e1  test    eax, eax
0x1800279e3  jnz     short loc_180027A00
0x1800279e5  call    cs:__imp_GetLastError
0x1800279ec  nop     dword ptr [rax+rax+00h]
0x1800279f1  mov     r9d, 55Fh
0x1800279f7  mov     ebx, eax
0x1800279f9  mov     ecx, eax
0x1800279fb  jmp     loc_180027974
0x180027a00  add     [rsp+328h+var_2F4], 3
0x180027a05  test    rdi, rdi
0x180027a08  jz      short loc_180027A33
0x180027a0a  mov     rdx, rdi; Token
0x180027a0d  xor     ecx, ecx; Thread
0x180027a0f  call    cs:__imp_SetThreadToken
0x180027a16  nop     dword ptr [rax+rax+00h]
0x180027a1b  test    eax, eax
0x180027a1d  jnz     short loc_180027A33
0x180027a1f  call    cs:__imp_GetLastError
0x180027a26  nop     dword ptr [rax+rax+00h]
0x180027a2b  mov     r9d, 56Eh
0x180027a31  jmp     short loc_1800279F7
0x180027a33  xor     r12d, r12d
0x180027a36  mov     [rsp+328h+var_2B8], r12
0x180027a3b  xor     r14d, r14d
0x180027a3e  mov     [rsp+328h+var_2B0], r14
0x180027a43  xor     esi, esi
0x180027a45  mov     [rsp+328h+var_2A8], rsi
0x180027a4d  xor     r15d, r15d
0x180027a50  mov     [rsp+328h+var_2A0], r15
0x180027a58  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180027a5f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x180027a64  test    al, al
0x180027a66  jz      loc_180027B57
0x180027a6c  xor     ecx, ecx; Time
0x180027a6e  call    cs:__imp__time64
0x180027a75  nop     dword ptr [rax+rax+00h]
0x180027a7a  mov     rdi, rax
0x180027a7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027a81  jnz     short loc_180027AAB
0x180027a83  lea     edi, [rsi+1Fh]
0x180027a86  mov     r9d, 57Dh
0x180027a8c  mov     ecx, edi
0x180027a8e  lea     rdx, aDwlasterror; "dwLastError"
0x180027a95  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027a9c  call    DebugTraceError
0x180027aa1  mov     rbx, [rsp+328h+var_2E0]
0x180027aa6  jmp     loc_180027E02
0x180027aab  lea     r13d, [rbx+8]
0x180027aaf  mov     edx, r13d; uBytes
0x180027ab2  xor     ecx, ecx; uFlags
0x180027ab4  call    cs:__imp_LocalAlloc
0x180027abb  nop     dword ptr [rax+rax+00h]
0x180027ac0  mov     r15, rax
0x180027ac3  mov     [rsp+328h+var_2A0], rax
0x180027acb  test    rax, rax
0x180027ace  jnz     short loc_180027ADA
0x180027ad0  lea     edi, [rax+0Eh]
0x180027ad3  mov     r13, [rsp+328h+hFile]
0x180027ad8  jmp     short loc_180027AA1
0x180027ada  mov     r8, rbx; Size
0x180027add  mov     rdx, [rsp+328h+Src]; Src
0x180027ae2  mov     rcx, r15; void *
0x180027ae5  call    memcpy_0
0x180027aea  mov     [rbx+r15], rdi
0x180027aee  lea     rax, [rsp+328h+dwMaximumSizeLow]
0x180027af3  mov     [rsp+328h+peUse], rax
0x180027af8  lea     rax, [rsp+328h+hMem]
0x180027afd  mov     [rsp+328h+cchReferencedDomainName], rax
0x180027b02  xor     r9d, r9d
0x180027b05  mov     r8d, r13d
0x180027b08  mov     rdx, r15
0x180027b0b  mov     rbx, [rsp+328h+var_2E0]
0x180027b10  mov     rcx, rbx
0x180027b13  call    LogonCredGenerateSignature
0x180027b18  mov     edi, eax
0x180027b1a  test    eax, eax
0x180027b1c  jz      short loc_180027B43
0x180027b1e  mov     r9d, 59Eh
0x180027b24  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027b2b  lea     rdx, aDwlasterror; "dwLastError"
0x180027b32  mov     ecx, eax
0x180027b34  call    DebugTraceError
0x180027b39  mov     r13, [rsp+328h+hFile]
0x180027b3e  jmp     loc_180027E02
0x180027b43  mov     [rsp+328h+var_2E8], 8
0x180027b4b  mov     ebx, [rsp+328h+dwMaximumSizeLow]
0x180027b4f  lea     eax, [rbx+10h]
0x180027b52  add     eax, r13d
0x180027b55  jmp     short loc_180027BA2
0x180027b57  lea     rax, [rsp+328h+dwMaximumSizeLow]
0x180027b5c  mov     [rsp+328h+peUse], rax
0x180027b61  lea     rax, [rsp+328h+hMem]
0x180027b66  mov     [rsp+328h+cchReferencedDomainName], rax
0x180027b6b  xor     r9d, r9d
0x180027b6e  mov     r8d, ebx
0x180027b71  mov     rdx, [rsp+328h+Src]
0x180027b76  mov     rcx, rdi
0x180027b79  call    LogonCredGenerateSignature
0x180027b7e  mov     edi, eax
0x180027b80  test    eax, eax
0x180027b82  jz      short loc_180027B91
0x180027b84  mov     r9d, 5B5h
0x180027b8a  mov     ecx, eax
0x180027b8c  jmp     loc_180027A8E
0x180027b91  mov     [rsp+328h+var_2E8], esi
0x180027b95  mov     ebx, [rsp+328h+dwMaximumSizeLow]
0x180027b99  mov     eax, dword ptr [rsp+328h+var_2D8]
0x180027b9d  add     eax, 0Ch
0x180027ba0  add     eax, ebx
0x180027ba2  mov     [rsp+328h+dwMaximumSizeLow], eax
0x180027ba6  lea     rax, [rsp+328h+hFile]
0x180027bab  mov     [rsp+328h+cchReferencedDomainName], rax; void **
0x180027bb0  lea     r9, [rsp+328h+var_288]; unsigned __int16 *
0x180027bb8  mov     r8, [rsp+328h+var_298]; unsigned __int16 *
0x180027bc0  mov     edx, 0C0000000h; unsigned int
0x180027bc5  xor     ecx, ecx; void *
0x180027bc7  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x180027bcc  mov     edi, eax
0x180027bce  test    eax, eax
0x180027bd0  jz      short loc_180027BF2
0x180027bd2  mov     r9d, 5C6h
0x180027bd8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027bdf  lea     rdx, aDwlasterror; "dwLastError"
0x180027be6  mov     ecx, eax
0x180027be8  call    DebugTraceError
0x180027bed  jmp     loc_180027AD3
0x180027bf2  mov     [rsp+328h+peUse], 0; lpName
0x180027bfb  mov     eax, [rsp+328h+dwMaximumSizeLow]
0x180027bff  mov     dword ptr [rsp+328h+cchReferencedDomainName], eax; dwMaximumSizeLow
0x180027c03  xor     r9d, r9d; dwMaximumSizeHigh
0x180027c06  xor     edx, edx; lpFileMappingAttributes
0x180027c08  lea     r8d, [r9+4]; flProtect
0x180027c0c  mov     rcx, [rsp+328h+hFile]; hFile
0x180027c11  call    cs:__imp_CreateFileMappingW
0x180027c18  nop     dword ptr [rax+rax+00h]
0x180027c1d  mov     r12, rax
0x180027c20  mov     [rsp+328h+var_2B8], rax
0x180027c25  test    rax, rax
0x180027c28  jnz     short loc_180027C66
0x180027c2a  call    cs:__imp_GetLastError
0x180027c31  nop     dword ptr [rax+rax+00h]
0x180027c36  mov     edi, eax
0x180027c38  mov     dword ptr [rsp+328h+var_2D8+4], eax
0x180027c3c  mov     r9d, 5D8h
0x180027c42  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027c49  lea     rdx, aDwlasterror; "dwLastError"
0x180027c50  mov     ecx, eax
0x180027c52  call    DebugTraceError
0x180027c57  mov     r13, [rsp+328h+hFile]
0x180027c5c  mov     rbx, [rsp+328h+var_2E0]
0x180027c61  jmp     loc_180027E02
0x180027c66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180027c6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x180027c72  xor     r9d, r9d; dwFileOffsetLow
0x180027c75  xor     r8d, r8d; dwFileOffsetHigh
0x180027c78  lea     edx, [r9+2]; dwDesiredAccess
0x180027c7c  mov     rcx, r12; hFileMappingObject
0x180027c7f  test    al, al
0x180027c81  mov     eax, [rsp+328h+dwMaximumSizeLow]
0x180027c85  mov     [rsp+328h+cchReferencedDomainName], rax; dwNumberOfBytesToMap
0x180027c8a  jz      loc_180027D1F
0x180027c90  call    cs:__imp_MapViewOfFile
0x180027c97  nop     dword ptr [rax+rax+00h]
0x180027c9c  mov     r14, rax
0x180027c9f  mov     [rsp+328h+var_2B0], rax
0x180027ca4  test    rax, rax
0x180027ca7  jnz     short loc_180027CE5
0x180027ca9  call    cs:__imp_GetLastError
0x180027cb0  nop     dword ptr [rax+rax+00h]
0x180027cb5  mov     edi, eax
0x180027cb7  mov     dword ptr [rsp+328h+var_2D8+4], eax
0x180027cbb  mov     r9d, 5E7h
0x180027cc1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027cc8  lea     rdx, aDwlasterror; "dwLastError"
0x180027ccf  mov     ecx, eax
0x180027cd1  call    DebugTraceError
0x180027cd6  mov     r13, [rsp+328h+hFile]
0x180027cdb  mov     rbx, [rsp+328h+var_2E0]
0x180027ce0  jmp     loc_180027E02
0x180027ce5  mov     dword ptr [rax], 2
0x180027ceb  mov     eax, dword ptr [rsp+328h+var_2D8]
0x180027cef  mov     [r14+4], eax
0x180027cf3  mov     eax, [rsp+328h+var_2E8]
0x180027cf7  mov     [r14+8], eax
0x180027cfb  mov     [r14+0Ch], ebx
0x180027cff  lea     rcx, [r14+10h]; void *
0x180027d03  mov     r8, rbx; Size
0x180027d06  mov     rdx, [rsp+328h+hMem]; Src
0x180027d0b  call    memcpy_0
0x180027d10  mov     r8d, r13d
0x180027d13  lea     rcx, [r14+10h]
0x180027d17  mov     rdx, r15
0x180027d1a  jmp     loc_180027DA6
0x180027d1f  call    cs:__imp_MapViewOfFile
0x180027d26  nop     dword ptr [rax+rax+00h]
0x180027d2b  mov     rsi, rax
0x180027d2e  mov     [rsp+328h+var_2A8], rax
0x180027d36  test    rax, rax
0x180027d39  jnz     short loc_180027D77
0x180027d3b  call    cs:__imp_GetLastError
0x180027d42  nop     dword ptr [rax+rax+00h]
0x180027d47  mov     edi, eax
0x180027d49  mov     dword ptr [rsp+328h+var_2D8+4], eax
0x180027d4d  mov     r9d, 5FEh
0x180027d53  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027d5a  lea     rdx, aDwlasterror; "dwLastError"
0x180027d61  mov     ecx, eax
0x180027d63  call    DebugTraceError
0x180027d68  mov     r13, [rsp+328h+hFile]
0x180027d6d  mov     rbx, [rsp+328h+var_2E0]
0x180027d72  jmp     loc_180027E02
0x180027d77  mov     dword ptr [rax], 1
0x180027d7d  mov     [rax+8], ebx
0x180027d80  mov     r13d, dword ptr [rsp+328h+var_2D8]
0x180027d85  mov     [rax+4], r13d
0x180027d89  lea     rcx, [rax+0Ch]; void *
0x180027d8d  mov     r8, rbx; Size
0x180027d90  mov     rdx, [rsp+328h+hMem]; Src
0x180027d95  call    memcpy_0
0x180027d9a  mov     r8d, r13d; Size
0x180027d9d  lea     rcx, [rsi+0Ch]
0x180027da1  mov     rdx, [rsp+328h+Src]; Src
0x180027da6  add     rcx, rbx; void *
0x180027da9  call    memcpy_0
0x180027dae  mov     r13, [rsp+328h+hFile]
0x180027db3  mov     rbx, [rsp+328h+var_2E0]
0x180027db8  jmp     short loc_180027E02
0x180027dba  mov     edi, eax
0x180027dbc  mov     dword ptr [rsp+328h+var_2D8+4], eax
0x180027dc0  mov     r9d, 616h
0x180027dc6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027dcd  lea     rdx, aDwlasterror; "dwLastError"
0x180027dd4  mov     ecx, eax
0x180027dd6  call    DebugTraceError
0x180027ddb  mov     r12, [rsp+328h+var_2B8]
0x180027de0  mov     r14, [rsp+328h+var_2B0]
0x180027de5  mov     rsi, [rsp+328h+var_2A8]
0x180027ded  mov     r15, [rsp+328h+var_2A0]
  ... truncated ...
```
