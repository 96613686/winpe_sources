# MyCreateFile

- ea: `0x1800107a4`
- end: `0x180010aca`
- name: `MyCreateFile`
- size: `806`
- prototype: `__int64 __fastcall(int, const WCHAR *, int, DWORD, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180010530`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x1800107a4`
- `0x1800110b8`
- `0x1800127f8`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010959`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a07`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800108ff`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800108ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001080b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010943`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001080b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010943`

## string_xrefs

- `0x18001096b`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180010a43`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180010a6a`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180010a9a`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall MyCreateFile(
        int a1,
        const WCHAR *a2,
        int a3,
        DWORD a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        _QWORD *a7)
{
  HANDLE FileW; // rax
  DWORD v11; // ebx
  int v12; // edx
  int v13; // r8d
  PVOID *v14; // rcx
  char v15; // si
  char v16; // r14
  DWORD LastError; // esi
  WINBOOL pfResult; // [rsp+48h] [rbp-38h] BYREF
  HANDLE ClientToken; // [rsp+50h] [rbp-30h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+58h] [rbp-28h] BYREF
  __int64 v23; // [rsp+6Ch] [rbp-14h]
  int v24; // [rsp+74h] [rbp-Ch]

  ClientToken = 0;
  pfResult = 0;
  FileW = CreateFileW(a2, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v11 = 0;
LABEL_3:
    *a7 = FileW;
    return v11;
  }
  LastError = GetLastError();
  if ( !a1 )
  {
    v11 = LastError;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v13,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        175);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_6;
  }
  v11 = OpenCallerToken(8u);
  if ( !v11 )
  {
    v11 = 0;
    *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
    v23 = 0;
    v24 = 0;
    RequiredPrivileges.Privilege[0].Luid = (LUID)17LL;
    if ( a3 >= 0 )
      RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
    RequiredPrivileges.Privilege[0].Attributes = 2;
    if ( PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
    {
      if ( pfResult )
      {
        v15 = a4;
        v16 = dwCreationDisposition;
        FileW = CreateFileW(a2, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes | 0x2000000, 0);
        if ( FileW != (HANDLE)-1LL )
          goto LABEL_3;
        v11 = GetLastError();
        DebugTraceError(v11, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 673);
        v14 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_7;
      }
      v11 = LastError;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_6:
        v15 = a4;
        v16 = dwCreationDisposition;
LABEL_7:
        if ( !v11 )
          return v11;
        goto LABEL_18;
      }
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v13,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        168);
    }
    else
    {
      v11 = GetLastError();
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v13,
        (unsigned int)"dwReturn",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        145);
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  v15 = a4;
  v16 = dwCreationDisposition;
LABEL_18:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    WPP_SF_SDDD((unsigned int)v14[2], v12, v13, (_DWORD)a2, a3, v15, v16);
  return v11;
}

```

## disassembly

```asm
0x1800107a4  mov     [rsp-38h+arg_0], rbx
0x1800107a9  push    rbp
0x1800107aa  push    rsi
0x1800107ab  push    rdi
0x1800107ac  push    r12
0x1800107ae  push    r13
0x1800107b0  push    r14
0x1800107b2  push    r15
0x1800107b4  mov     rbp, rsp
0x1800107b7  sub     rsp, 80h
0x1800107be  mov     rax, cs:__security_cookie
0x1800107c5  xor     rax, rsp
0x1800107c8  mov     [rbp+var_8], rax
0x1800107cc  mov     r14d, [rbp+arg_28]
0x1800107d0  mov     eax, r9d
0x1800107d3  mov     r12, [rbp+arg_30]
0x1800107d7  xor     edi, edi
0x1800107d9  mov     ebx, ecx
0x1800107db  mov     [rsp+80h+hTemplateFile], rdi; hTemplateFile
0x1800107e0  mov     ecx, [rbp+arg_20]
0x1800107e3  mov     r15d, r8d
0x1800107e6  mov     r13, rdx
0x1800107e9  mov     [rbp+var_3C], ecx
0x1800107ec  mov     [rsp+80h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800107f1  xor     r9d, r9d; lpSecurityAttributes
0x1800107f4  mov     [rsp+80h+dwCreationDisposition], ecx; dwCreationDisposition
0x1800107f8  mov     r8d, eax; dwShareMode
0x1800107fb  mov     rcx, r13; lpFileName
0x1800107fe  mov     [rbp+dwShareMode], eax
0x180010801  mov     edx, r15d; dwDesiredAccess
0x180010804  mov     [rbp+ClientToken], rdi
0x180010808  mov     [rbp+pfResult], edi
0x18001080b  call    cs:__imp_CreateFileW
0x180010812  nop     dword ptr [rax+rax+00h]
0x180010817  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001081b  jz      short loc_180010892
0x18001081d  xor     ebx, ebx
0x18001081f  mov     [r12], rax
0x180010823  jmp     short loc_18001085F
0x180010825  call    cs:__imp_GetLastError
0x18001082c  nop     dword ptr [rax+rax+00h]
0x180010831  mov     ebx, eax
0x180010833  mov     rcx, cs:WPP_GLOBAL_Control
0x18001083a  lea     r12, WPP_GLOBAL_Control
0x180010841  cmp     rcx, r12
0x180010844  jz      short loc_180010850
0x180010846  test    byte ptr [rcx+1Ch], 1
0x18001084a  jnz     loc_180010A62
0x180010850  mov     esi, [rbp+dwShareMode]
0x180010853  mov     r14d, [rbp+var_3C]
0x180010857  test    ebx, ebx
0x180010859  jnz     loc_1800109AE
0x18001085f  test    rdi, rdi
0x180010862  jnz     loc_180010A04
0x180010868  mov     eax, ebx
0x18001086a  mov     rcx, [rbp+var_8]
0x18001086e  xor     rcx, rsp; StackCookie
0x180010871  call    __security_check_cookie
0x180010876  mov     rbx, [rsp+80h+arg_0]
0x18001087e  add     rsp, 80h
0x180010885  pop     r15
0x180010887  pop     r14
0x180010889  pop     r13
0x18001088b  pop     r12
0x18001088d  pop     rdi
0x18001088e  pop     rsi
0x18001088f  pop     rbp
0x180010890  retn
0x180010892  call    cs:__imp_GetLastError
0x180010899  nop     dword ptr [rax+rax+00h]
0x18001089e  mov     esi, eax
0x1800108a0  lea     rax, WPP_GLOBAL_Control
0x1800108a7  test    ebx, ebx
0x1800108a9  jz      loc_1800109E0
0x1800108af  lea     rdx, [rbp+ClientToken]
0x1800108b3  mov     ecx, 8; DesiredAccess
0x1800108b8  call    OpenCallerToken
0x1800108bd  mov     ebx, eax
0x1800108bf  test    eax, eax
0x1800108c1  jnz     loc_180010995
0x1800108c7  xor     ebx, ebx
0x1800108c9  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1800108d1  mov     [rbp+var_14], rbx
0x1800108d5  mov     [rbp+var_C], ebx
0x1800108d8  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 11h
0x1800108e0  test    r15d, r15d
0x1800108e3  jns     loc_180010A55
0x1800108e9  mov     rdi, [rbp+ClientToken]
0x1800108ed  lea     r8, [rbp+pfResult]; pfResult
0x1800108f1  mov     rcx, rdi; ClientToken
0x1800108f4  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x1800108fb  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800108ff  call    cs:__imp_PrivilegeCheck
0x180010906  nop     dword ptr [rax+rax+00h]
0x18001090b  test    eax, eax
0x18001090d  jz      loc_180010825
0x180010913  cmp     [rbp+pfResult], ebx
0x180010916  jz      loc_180010A18
0x18001091c  mov     esi, [rbp+dwShareMode]
0x18001091f  bts     r14d, 19h
0x180010924  mov     [rsp+80h+hTemplateFile], rbx; hTemplateFile
0x180010929  xor     r9d, r9d; lpSecurityAttributes
0x18001092c  mov     [rsp+80h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180010931  mov     r8d, esi; dwShareMode
0x180010934  mov     r14d, [rbp+var_3C]
0x180010938  mov     edx, r15d; dwDesiredAccess
0x18001093b  mov     rcx, r13; lpFileName
0x18001093e  mov     [rsp+80h+dwCreationDisposition], r14d; dwCreationDisposition
0x180010943  call    cs:__imp_CreateFileW
0x18001094a  nop     dword ptr [rax+rax+00h]
0x18001094f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010953  jnz     loc_18001081F
0x180010959  call    cs:__imp_GetLastError
0x180010960  nop     dword ptr [rax+rax+00h]
0x180010965  mov     r9d, 2A1h
0x18001096b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010972  mov     ecx, eax
0x180010974  lea     rdx, aDwreturn; "dwReturn"
0x18001097b  mov     ebx, eax
0x18001097d  call    DebugTraceError
0x180010982  mov     rcx, cs:WPP_GLOBAL_Control
0x180010989  lea     r12, WPP_GLOBAL_Control
0x180010990  jmp     loc_180010857
0x180010995  mov     rdi, [rbp+ClientToken]
0x180010999  lea     r12, WPP_GLOBAL_Control
0x1800109a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109a7  mov     esi, [rbp+dwShareMode]
0x1800109aa  mov     r14d, [rbp+var_3C]
0x1800109ae  cmp     rcx, r12
0x1800109b1  jz      loc_18001085F
0x1800109b7  test    byte ptr [rcx+1Ch], 1
0x1800109bb  jz      loc_18001085F
0x1800109c1  mov     rcx, [rcx+10h]
0x1800109c5  mov     r9, r13
0x1800109c8  mov     dword ptr [rsp+80h+hTemplateFile], r14d
0x1800109cd  mov     [rsp+80h+dwFlagsAndAttributes], esi
0x1800109d1  mov     [rsp+80h+dwCreationDisposition], r15d
0x1800109d6  call    WPP_SF_SDDD
0x1800109db  jmp     loc_18001085F
0x1800109e0  mov     ebx, esi
0x1800109e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109e9  cmp     rcx, rax
0x1800109ec  jz      short loc_1800109F8
0x1800109ee  test    byte ptr [rcx+1Ch], 1
0x1800109f2  jnz     loc_180010A96
0x1800109f8  lea     r12, WPP_GLOBAL_Control
0x1800109ff  jmp     loc_180010850
0x180010a04  mov     rcx, rdi; hObject
0x180010a07  call    cs:__imp_CloseHandle
0x180010a0e  nop     dword ptr [rax+rax+00h]
0x180010a13  jmp     loc_180010868
0x180010a18  mov     ebx, esi
0x180010a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a21  lea     r12, WPP_GLOBAL_Control
0x180010a28  cmp     rcx, r12
0x180010a2b  jz      loc_180010850
0x180010a31  test    byte ptr [rcx+1Ch], 1
0x180010a35  jz      loc_180010850
0x180010a3b  mov     dword ptr [rsp+80h+hTemplateFile], 2A8h
0x180010a43  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a4a  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x180010a4f  mov     [rsp+80h+dwCreationDisposition], esi
0x180010a53  jmp     short loc_180010A7A
0x180010a55  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x180010a5d  jmp     loc_1800108E9
0x180010a62  mov     dword ptr [rsp+80h+hTemplateFile], 291h
0x180010a6a  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a71  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x180010a76  mov     [rsp+80h+dwCreationDisposition], ebx
0x180010a7a  mov     rcx, [rcx+10h]
0x180010a7e  lea     r9, aDwreturn; "dwReturn"
0x180010a85  call    WPP_SF_sDsd
0x180010a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a91  jmp     loc_180010850
0x180010a96  mov     rcx, [rcx+10h]
0x180010a9a  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010aa1  mov     dword ptr [rsp+80h+hTemplateFile], 2AFh
0x180010aa9  lea     r9, aDwreturn; "dwReturn"
0x180010ab0  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x180010ab5  mov     [rsp+80h+dwCreationDisposition], esi
0x180010ab9  call    WPP_SF_sDsd
0x180010abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ac5  jmp     loc_1800109F8
```
