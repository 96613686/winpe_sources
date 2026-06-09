# Mso::OfficeWebServiceApi::ServiceCacheRecord::WriteData(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uchar const *,unsigned __int64)

- ea: `0x18001d44c`
- end: `0x18001d704`
- name: `?WriteData@ServiceCacheRecord@OfficeWebServiceApi@Mso@@CA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBE_K@Z`
- size: `696`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180088ab4`

## callees

- `0x18000adf0`
- `0x18001c13c`
- `0x18001d44c`
- `0x18001d704`
- `0x18003aa1c`
- `0x18003e690`
- `0x180052e28`
- `0x180089158`
- `0x1800c94e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d4d9`
- `KERNEL32!GetLastError` at `0x18001d5f8`
- `KERNEL32!GetLastError` at `0x18001d4d9`
- `KERNEL32!GetLastError` at `0x18001d5f8`
- `KERNEL32!CloseHandle` at `0x18001d6b3`
- `KERNEL32!CloseHandle` at `0x18001d6b3`
- `KERNEL32!WriteFile` at `0x18001d6d7`
- `KERNEL32!WriteFile` at `0x18001d6d7`

## string_xrefs

- `0x18001d64a`: `Failed to open cache file`
- `0x18001d47a`: `[ServiceCacheRecord] WriteData`
- `0x18001d528`: `Failed to create a directory for cache file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::OfficeWebServiceApi::ServiceCacheRecord::WriteData(
        const WCHAR *lpFileName,
        LPCVOID lpBuffer,
        __int64 nNumberOfBytesToWrite)
{
  LPCWSTR v5; // rdi
  void *FileW; // rbx
  DWORD LastError; // eax
  const wchar_t *v8; // rcx
  int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v13; // rax
  DWORD v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-89h] BYREF
  void *v19; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-79h] BYREF
  void **v21; // [rsp+60h] [rbp-69h] BYREF
  const char *v22; // [rsp+68h] [rbp-61h]
  const wchar_t *v23; // [rsp+70h] [rbp-59h]
  _BYTE v24[24]; // [rsp+78h] [rbp-51h] BYREF
  __int64 v25; // [rsp+90h] [rbp-39h]
  __int64 v26; // [rsp+98h] [rbp-31h]
  _QWORD v27[3]; // [rsp+A0h] [rbp-29h] BYREF
  __int16 v28; // [rsp+B8h] [rbp-11h]
  __int128 v29; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v30; // [rsp+D0h] [rbp+7h]
  __int64 v31; // [rsp+D8h] [rbp+Fh]

  v5 = lpFileName;
  v20[0] = "[ServiceCacheRecord] WriteData";
  if ( !*((_QWORD *)lpFileName + 2) || !lpBuffer || !nNumberOfBytesToWrite )
    return 0;
  if ( *((_QWORD *)lpFileName + 3) > 7u )
    lpFileName = *(const WCHAR **)lpFileName;
  FileW = (void *)MsoCreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 128);
  v19 = FileW;
  LastError = GetLastError();
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && LastError == 3 )
  {
    v8 = v5;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v8 = *(const wchar_t **)v5;
    if ( !(unsigned int)MsoFEnsureDirectory(v8) )
    {
      v21 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
      v22 = "Message";
      v23 = L"Failed to create a directory for cache file";
      *(_WORD *)v24 = 4;
      *(_OWORD *)&v24[8] = 0;
      v25 = 0;
      v26 = 7;
      *(_WORD *)&v24[8] = 0;
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        22046926,
        823,
        10,
        v9,
        (__int64)v20,
        (__int64)&v21);
      std::wstring::~wstring(&v24[8]);
LABEL_12:
      std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v19, v10, v11);
      return 0;
    }
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(LPCWSTR *)v5;
    v13 = MsoCreateFileW(v5, 0x40000000u, 0, 0, 2u, 128);
    std::unique_ptr<void *,Mso::Win::HandleDeleter>::reset(&v19, v13);
    FileW = v19;
  }
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v14 = GetLastError();
    v22 = "LastError";
    LODWORD(v23) = v14;
    WORD2(v23) = 4;
    memset(v24, 0, sizeof(v24));
    v25 = 7;
    *(_WORD *)v24 = 0;
    v21 = &Mso::Http::Logging::Structured::WindowsEnabledHttpProtocol::`vftable';
    v27[0] = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    v27[1] = "Message";
    v27[2] = L"Failed to open cache file";
    v28 = 4;
    v29 = 0;
    v30 = 0;
    v31 = 7;
    LOWORD(v29) = 0;
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredGetLastError>(
      8713409,
      v15,
      v16,
      v17,
      (__int64)v20,
      (__int64)v27,
      (__int64)&v21);
    std::wstring::~wstring(&v29);
    std::wstring::~wstring(v24);
    if ( FileW )
    {
      if ( FileW != (void *)-1LL )
        CloseHandle(FileW);
    }
    return 0;
  }
  NumberOfBytesWritten = 0;
  if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
    || NumberOfBytesWritten != nNumberOfBytesToWrite )
  {
    goto LABEL_12;
  }
  std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v19, v10, v11);
  return 1;
}

```

## disassembly

```asm
0x18001d44c  push    rbp
0x18001d44e  push    rbx
0x18001d44f  push    rsi
0x18001d450  push    rdi
0x18001d451  push    r12
0x18001d453  push    r14
0x18001d455  push    r15
0x18001d457  lea     rbp, [rsp-27h]
0x18001d45c  sub     rsp, 0F0h
0x18001d463  mov     rax, cs:__security_cookie
0x18001d46a  xor     rax, rsp
0x18001d46d  mov     [rbp+57h+var_40], rax
0x18001d471  mov     rsi, r8
0x18001d474  mov     r14, rdx
0x18001d477  mov     rdi, rcx
0x18001d47a  lea     rax, aServicecachere_0; "[ServiceCacheRecord] WriteData"
0x18001d481  mov     [rbp+57h+var_D0], rax
0x18001d485  xor     r15d, r15d
0x18001d488  cmp     [rcx+10h], r15
0x18001d48c  jz      loc_18001D58A
0x18001d492  test    rdx, rdx
0x18001d495  jz      loc_18001D58A
0x18001d49b  test    r8, r8
0x18001d49e  jz      loc_18001D58A
0x18001d4a4  lea     r12d, [r15+7]
0x18001d4a8  cmp     [rcx+18h], r12
0x18001d4ac  jbe     short loc_18001D4B1
0x18001d4ae  mov     rcx, [rcx]; lpFileName
0x18001d4b1  mov     [rsp+120h+var_F8], 80h; int
0x18001d4b9  mov     dword ptr [rsp+120h+lpOverlapped], 2; DWORD
0x18001d4c1  xor     r9d, r9d; lpSecurityAttributes
0x18001d4c4  xor     r8d, r8d; dwShareMode
0x18001d4c7  mov     edx, 40000000h; dwDesiredAccess
0x18001d4cc  call    MsoCreateFileW
0x18001d4d1  mov     rbx, rax
0x18001d4d4  mov     [rsp+120h+var_D8], rax
0x18001d4d9  call    cs:__imp_GetLastError
0x18001d4df  lea     rcx, [rbx+1]
0x18001d4e3  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001d4ea  jnz     loc_18001D5E8
0x18001d4f0  cmp     eax, 3
0x18001d4f3  jnz     loc_18001D5E8
0x18001d4f9  mov     rcx, rdi
0x18001d4fc  cmp     [rdi+18h], r12
0x18001d500  jbe     short loc_18001D505
0x18001d502  mov     rcx, [rdi]; Source
0x18001d505  call    ?MsoFEnsureDirectory@@YAHPEB_W@Z; MsoFEnsureDirectory(wchar_t const *)
0x18001d50a  test    eax, eax
0x18001d50c  jnz     loc_18001D5AA
0x18001d512  lea     rcx, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x18001d519  mov     [rbp+57h+var_C0], rcx
0x18001d51d  lea     rcx, aMessage; "Message"
0x18001d524  mov     [rbp+57h+var_B8], rcx
0x18001d528  lea     rax, aFailedToCreate; "Failed to create a directory for cache "...
0x18001d52f  mov     [rbp+57h+var_B0], rax
0x18001d533  mov     eax, 4
0x18001d538  mov     word ptr [rbp+57h+var_A8], ax
0x18001d53c  xorps   xmm0, xmm0
0x18001d53f  movups  [rbp+57h+var_A8+8], xmm0
0x18001d543  mov     [rbp+57h+var_90], r15
0x18001d547  mov     [rbp+57h+var_88], r12
0x18001d54b  mov     word ptr [rbp+57h+var_A8+8], r15w
0x18001d550  lea     rax, [rbp+57h+var_C0]
0x18001d554  mov     qword ptr [rsp+120h+var_F8], rax
0x18001d559  lea     rax, [rbp+57h+var_D0]
0x18001d55d  mov     [rsp+120h+lpOverlapped], rax
0x18001d562  mov     edx, 337h
0x18001d567  mov     ecx, 15068CEh
0x18001d56c  mov     r8d, 0Ah
0x18001d572  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x18001d577  lea     rcx, [rbp+57h+var_A8+8]; void *
0x18001d57b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d580  lea     rcx, [rsp+120h+var_D8]
0x18001d585  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x18001d58a  xor     al, al
0x18001d58c  mov     rcx, [rbp+57h+var_40]
0x18001d590  xor     rcx, rsp; StackCookie
0x18001d593  call    __security_check_cookie
0x18001d598  add     rsp, 0F0h
0x18001d59f  pop     r15
0x18001d5a1  pop     r14
0x18001d5a3  pop     r12
0x18001d5a5  pop     rdi
0x18001d5a6  pop     rsi
0x18001d5a7  pop     rbx
0x18001d5a8  pop     rbp
0x18001d5a9  retn
0x18001d5aa  cmp     [rdi+18h], r12
0x18001d5ae  jbe     short loc_18001D5B3
0x18001d5b0  mov     rdi, [rdi]
0x18001d5b3  mov     [rsp+120h+var_F8], 80h; int
0x18001d5bb  mov     dword ptr [rsp+120h+lpOverlapped], 2; DWORD
0x18001d5c3  xor     r9d, r9d; lpSecurityAttributes
0x18001d5c6  xor     r8d, r8d; dwShareMode
0x18001d5c9  mov     edx, 40000000h; dwDesiredAccess
0x18001d5ce  mov     rcx, rdi; lpFileName
0x18001d5d1  call    MsoCreateFileW
0x18001d5d6  mov     rdx, rax
0x18001d5d9  lea     rcx, [rsp+120h+var_D8]
0x18001d5de  call    ?reset@?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAAXPEAX@Z; std::unique_ptr<void *,Mso::Win::HandleDeleter>::reset(void *)
0x18001d5e3  mov     rbx, [rsp+120h+var_D8]
0x18001d5e8  lea     rax, [rbx+1]
0x18001d5ec  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001d5f2  jnz     loc_18001D6BF
0x18001d5f8  call    cs:__imp_GetLastError
0x18001d5fe  lea     rcx, aLasterror; "LastError"
0x18001d605  mov     [rbp+57h+var_B8], rcx
0x18001d609  mov     dword ptr [rbp+57h+var_B0], eax
0x18001d60c  mov     eax, 4
0x18001d611  mov     word ptr [rbp+57h+var_B0+4], ax
0x18001d615  xorps   xmm0, xmm0
0x18001d618  movups  [rbp+57h+var_A8], xmm0
0x18001d61c  mov     [rbp+57h+var_98], r15
0x18001d620  mov     [rbp+57h+var_90], r12
0x18001d624  mov     word ptr [rbp+57h+var_A8], r15w
0x18001d629  lea     rcx, ??_7WindowsEnabledHttpProtocol@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::WindowsEnabledHttpProtocol::`vftable'
0x18001d630  mov     [rbp+57h+var_C0], rcx
0x18001d634  lea     rcx, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x18001d63b  mov     [rbp+57h+var_80], rcx
0x18001d63f  lea     rcx, aMessage; "Message"
0x18001d646  mov     [rbp+57h+var_78], rcx
0x18001d64a  lea     rcx, aFailedToOpenCa; "Failed to open cache file"
0x18001d651  mov     [rbp+57h+var_70], rcx
0x18001d655  mov     [rbp+57h+var_68], ax
0x18001d659  movups  [rbp+57h+var_60], xmm0
0x18001d65d  mov     [rbp+57h+var_50], r15
0x18001d661  mov     [rbp+57h+var_48], r12
0x18001d665  mov     word ptr [rbp+57h+var_60], r15w
0x18001d66a  lea     rax, [rbp+57h+var_C0]
0x18001d66e  mov     [rsp+120h+var_F0], rax
0x18001d673  lea     rax, [rbp+57h+var_80]
0x18001d677  mov     qword ptr [rsp+120h+var_F8], rax
0x18001d67c  lea     rax, [rbp+57h+var_D0]
0x18001d680  mov     [rsp+120h+lpOverlapped], rax
0x18001d685  mov     ecx, 84F4C1h
0x18001d68a  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@UClassifiedStructuredGetLastError@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAUClassifiedStructuredGetLastError@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredGetLastError>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredGetLastError &&)
0x18001d68f  lea     rcx, [rbp+57h+var_60]; void *
0x18001d693  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d698  lea     rcx, [rbp+57h+var_A8]; void *
0x18001d69c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d6a1  test    rbx, rbx
0x18001d6a4  jz      loc_18001D58A
0x18001d6aa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001d6ae  jz      short loc_18001D6BA
0x18001d6b0  mov     rcx, rbx; hObject
0x18001d6b3  call    cs:__imp_CloseHandle
0x18001d6b9  nop
0x18001d6ba  jmp     loc_18001D58A
0x18001d6bf  mov     [rsp+120h+NumberOfBytesWritten], r15d
0x18001d6c4  mov     [rsp+120h+lpOverlapped], r15; lpOverlapped
0x18001d6c9  lea     r9, [rsp+120h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001d6ce  mov     r8d, esi; nNumberOfBytesToWrite
0x18001d6d1  mov     rdx, r14; lpBuffer
0x18001d6d4  mov     rcx, rbx; hFile
0x18001d6d7  call    cs:__imp_WriteFile
0x18001d6dd  test    eax, eax
0x18001d6df  jz      loc_18001D580
0x18001d6e5  mov     eax, [rsp+120h+NumberOfBytesWritten]
0x18001d6e9  cmp     rax, rsi
0x18001d6ec  jnz     loc_18001D580
0x18001d6f2  lea     rcx, [rsp+120h+var_D8]
0x18001d6f7  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x18001d6fc  mov     al, 1
0x18001d6fe  jmp     loc_18001D58C
```
