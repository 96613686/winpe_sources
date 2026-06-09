# InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo,std::allocator<InstalledFontFileInfo>> &)

- ea: `0x1801243d0`
- end: `0x180124665`
- name: `?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801260e0`

## callees

- `0x18011ef30`
- `0x180123484`
- `0x1801243d0`
- `0x18012466c`
- `0x18014d8b0`
- `0x1801644d0`
- `0x1801e7ba8`
- `0x1801ecd38`
- `0x1801effd8`
- `0x180212490`
- `0x18024e854`
- `0x18024eb54`
- `0x18024f3b0`

## import_xrefs

- `kernel32!GetLastError` at `0x180124588`
- `kernel32!GetLastError` at `0x180124588`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180124427`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180124427`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180124508`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18012455a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180124508`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18012455a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012463f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012465a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012463f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012465a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180124611`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180124611`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall InstalledFontFileEnumerator::TryConvertFileInfo(int a1, void *a2, const WCHAR *a3, __int64 a4)
{
  const WCHAR *v8; // rcx
  HANDLE FirstFileW; // rdx
  const WCHAR *v10; // rcx
  signed int LastError; // r14d
  struct DWrite::RefString::Data *v13; // rbx
  struct DWrite::RefString::Data *ftLastWriteTime; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[24]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  struct DWrite::RefString::Data *v18; // [rsp+70h] [rbp-90h] BYREF
  bool v19; // [rsp+78h] [rbp-88h]
  void *v20; // [rsp+80h] [rbp-80h]
  HANDLE hFindFile; // [rsp+90h] [rbp-70h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+98h] [rbp-68h] BYREF

  v20 = a2;
  if ( a2 )
  {
    EventTag::EventTag((EventTag *)&ftLastWriteTime, (const char (*)[9])"Imperson");
    if ( !ImpersonateLoggedOnUser(a2) )
      LogAndThrowLastError(ftLastWriteTime);
  }
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v8 = a3;
  else
    v8 = *(const WCHAR **)a3;
  FirstFileW = FindFirstFileW(v8, &FindFileData);
  hFindFile = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL || (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
    if ( (*((_DWORD *)a3 + 8) == 1) == (a2 == 0) )
    {
      LastError = GetLastError();
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const WCHAR **)a3;
      GetDepersonalizedFilePath(&ftLastWriteTime, a3);
      v13 = ftLastWriteTime;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      EventLogger::LogEvent<long,EventTag,unsigned int,wchar_t const *>(
        a1 + 16,
        1953394502,
        1869771365,
        LastError,
        0x656D697466LL,
        186,
        (__int64)ftLastWriteTime + 8);
      DWrite::RefString::DecrementRef(v13);
      FirstFileW = hFindFile;
    }
    if ( FirstFileW != (HANDLE)-1LL )
      FindClose(FirstFileW);
    if ( a2 )
      RevertToSelf();
    return 0;
  }
  else
  {
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v16);
    v17 = 0;
    v18 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
    v19 = 0;
    v15 = 0;
    ftLastWriteTime = (struct DWrite::RefString::Data *)FindFileData.ftLastWriteTime;
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v10 = a3;
    else
      v10 = *(const WCHAR **)a3;
    LocalFileLoader::SerializeReferenceKeyTo(v10);
    v17 = *((_DWORD *)a3 + 8);
    DWrite::RefString::operator=(&v18, a3 + 20);
    v19 = a2 != 0;
    if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
    {
      std::vector<InstalledFontFileInfo>::_Emplace_reallocate<InstalledFontFileInfo>(a4, *(_QWORD *)(a4 + 8), &v15);
    }
    else
    {
      InstalledFontFileInfo::InstalledFontFileInfo(*(_QWORD *)(a4 + 8), &v15);
      *(_QWORD *)(a4 + 8) += 56LL;
    }
    DWrite::RefString::DecrementRef(v18);
    std::vector<UninitializedSmallEnum<enum LineBreakClass,unsigned char>>::_Tidy(v16);
    if ( hFindFile != (HANDLE)-1LL )
      FindClose(hFindFile);
    if ( a2 )
      RevertToSelf();
    return 1;
  }
}

```

## disassembly

```asm
0x1801243d0  mov     [rsp-8+arg_8], rbx
0x1801243d5  push    rbp
0x1801243d6  push    rsi
0x1801243d7  push    rdi
0x1801243d8  push    r14
0x1801243da  push    r15
0x1801243dc  lea     rbp, [rsp-200h]
0x1801243e4  sub     rsp, 300h
0x1801243eb  mov     rax, cs:__security_cookie
0x1801243f2  xor     rax, rsp
0x1801243f5  mov     [rbp+220h+var_30], rax
0x1801243fc  mov     rdi, r9
0x1801243ff  mov     rbx, r8
0x180124402  mov     rsi, rdx
0x180124405  mov     r15, rcx
0x180124408  mov     [rbp+220h+var_2A0], rdx
0x18012440c  test    rdx, rdx
0x18012440f  jnz     loc_1801245FD
0x180124415  cmp     qword ptr [rbx+18h], 7
0x18012441a  jbe     loc_18012456E
0x180124420  mov     rcx, [rbx]; lpFileName
0x180124423  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x180124427  call    cs:__imp_FindFirstFileW
0x18012442d  mov     rdx, rax
0x180124430  mov     [rbp+220h+hFindFile], rax
0x180124434  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180124438  jz      loc_180124540
0x18012443e  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x180124442  jnz     loc_180124540
0x180124448  lea     rcx, [rsp+320h+var_2D0]; void *
0x18012444d  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180124452  mov     [rsp+320h+var_2B8], 0
0x18012445a  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180124461  mov     [rsp+320h+var_2B0], rax
0x180124466  mov     [rsp+320h+var_2A8], 0
0x18012446b  mov     [rsp+320h+var_2D8], 0
0x180124474  mov     eax, [rbp+220h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x180124477  mov     dword ptr [rsp+320h+var_2E0+4], eax
0x18012447b  mov     eax, [rbp+220h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18012447e  mov     dword ptr [rsp+320h+var_2E0], eax
0x180124482  mov     rax, [rsp+320h+var_2E0]
0x180124487  mov     [rsp+320h+var_2E0], rax
0x18012448c  cmp     qword ptr [rbx+18h], 7
0x180124491  jbe     loc_180124576
0x180124497  mov     rcx, [rbx]; lpString2
0x18012449a  lea     r9, [rsp+320h+var_2D0]
0x18012449f  xor     r8d, r8d
0x1801244a2  lea     rdx, [rsp+320h+var_2E0]
0x1801244a7  call    ?SerializeReferenceKeyTo@LocalFileLoader@@SAXPEB_WPEBVDateTime@@0AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; LocalFileLoader::SerializeReferenceKeyTo(wchar_t const *,DateTime const *,wchar_t const *,std::vector<uchar> &)
0x1801244ac  mov     eax, [rbx+20h]
0x1801244af  mov     [rsp+320h+var_2B8], eax
0x1801244b3  lea     rdx, [rbx+28h]
0x1801244b7  lea     rcx, [rsp+320h+var_2B0]
0x1801244bc  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x1801244c1  test    rsi, rsi
0x1801244c4  setnz   [rsp+320h+var_2A8]
0x1801244c9  mov     rax, [rdi+8]
0x1801244cd  cmp     rax, [rdi+10h]
0x1801244d1  jz      loc_18012462A
0x1801244d7  lea     rdx, [rsp+320h+var_2D8]
0x1801244dc  mov     rcx, rax
0x1801244df  call    ??0InstalledFontFileInfo@@QEAA@$$QEAU0@@Z; InstalledFontFileInfo::InstalledFontFileInfo(InstalledFontFileInfo &&)
0x1801244e4  add     qword ptr [rdi+8], 38h ; '8'
0x1801244e9  mov     rcx, [rsp+320h+var_2B0]; struct DWrite::RefString::Data *
0x1801244ee  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801244f3  lea     rcx, [rsp+320h+var_2D0]
0x1801244f8  call    ?_Tidy@?$vector@U?$UninitializedSmallEnum@W4LineBreakClass@@E@@V?$allocator@U?$UninitializedSmallEnum@W4LineBreakClass@@E@@@std@@@std@@AEAAXXZ; std::vector<UninitializedSmallEnum<LineBreakClass,uchar>>::_Tidy(void)
0x1801244fd  nop
0x1801244fe  mov     rcx, [rbp+220h+hFindFile]; hFindFile
0x180124502  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180124506  jz      short loc_18012450F
0x180124508  call    cs:__imp_FindClose
0x18012450e  nop
0x18012450f  test    rsi, rsi
0x180124512  jnz     loc_18012463F
0x180124518  mov     al, 1
0x18012451a  mov     rcx, [rbp+220h+var_30]
0x180124521  xor     rcx, rsp; StackCookie
0x180124524  call    __security_check_cookie
0x180124529  mov     rbx, [rsp+320h+arg_8]
0x180124531  add     rsp, 300h
0x180124538  pop     r15
0x18012453a  pop     r14
0x18012453c  pop     rdi
0x18012453d  pop     rsi
0x18012453e  pop     rbp
0x18012453f  retn
0x180124540  cmp     dword ptr [rbx+20h], 1
0x180124544  setz    cl
0x180124547  test    rsi, rsi
0x18012454a  setz    al
0x18012454d  cmp     cl, al
0x18012454f  jz      short loc_18012457E
0x180124551  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180124555  jz      short loc_180124561
0x180124557  mov     rcx, rdx; hFindFile
0x18012455a  call    cs:__imp_FindClose
0x180124560  nop
0x180124561  test    rsi, rsi
0x180124564  jnz     loc_18012465A
0x18012456a  xor     al, al
0x18012456c  jmp     short loc_18012451A
0x18012456e  mov     rcx, rbx
0x180124571  jmp     loc_180124423
0x180124576  mov     rcx, rbx
0x180124579  jmp     loc_18012449A
0x18012457e  mov     rdi, 656D697466h
0x180124588  call    cs:__imp_GetLastError
0x18012458e  mov     r14d, eax
0x180124591  cmp     qword ptr [rbx+18h], 7
0x180124596  jbe     short loc_18012459B
0x180124598  mov     rbx, [rbx]
0x18012459b  mov     rdx, rbx
0x18012459e  lea     rcx, [rsp+320h+var_2E0]
0x1801245a3  call    ?GetDepersonalizedFilePath@@YA?AVRefString@DWrite@@PEB_W@Z; GetDepersonalizedFilePath(wchar_t const *)
0x1801245a8  mov     rbx, [rsp+320h+var_2E0]
0x1801245ad  lea     rax, [rbx+8]
0x1801245b1  test    r14d, r14d
0x1801245b4  jg      loc_18012464A
0x1801245ba  mov     rdx, 6D756E45746E6F46h
0x1801245c4  mov     r8, 726F727265h
0x1801245ce  lea     rcx, [r15+10h]
0x1801245d2  mov     [rsp+320h+var_2F0], rax
0x1801245d7  mov     [rsp+320h+var_2F8], 0BAh
0x1801245df  mov     [rsp+320h+var_300], rdi
0x1801245e4  mov     r9d, r14d
0x1801245e7  call    ??$LogEvent@JVEventTag@@IPEB_W@EventLogger@@QEBAXVEventTag@@0J0IPEB_W@Z; EventLogger::LogEvent<long,EventTag,uint,wchar_t const *>(EventTag,EventTag,long,EventTag,uint,wchar_t const *)
0x1801245ec  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1801245ef  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801245f4  mov     rdx, [rbp+220h+hFindFile]
0x1801245f8  jmp     loc_180124551
0x1801245fd  lea     rdx, aImperson; "Imperson"
0x180124604  lea     rcx, [rsp+320h+var_2E0]; this
0x180124609  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x18012460e  mov     rcx, rsi; hToken
0x180124611  call    cs:__imp_ImpersonateLoggedOnUser
0x180124617  test    eax, eax
0x180124619  jnz     loc_180124415
0x18012461f  mov     rcx, [rsp+320h+var_2E0]
0x180124624  call    ?LogAndThrowLastError@@YAXVEventTag@@I@Z; LogAndThrowLastError(EventTag,uint)
0x18012462a  lea     r8, [rsp+320h+var_2D8]
0x18012462f  mov     rdx, rax
0x180124632  mov     rcx, rdi
0x180124635  call    ??$_Emplace_reallocate@UInstalledFontFileInfo@@@?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@AEAAPEAUInstalledFontFileInfo@@QEAU2@$$QEAU2@@Z; std::vector<InstalledFontFileInfo>::_Emplace_reallocate<InstalledFontFileInfo>(InstalledFontFileInfo * const,InstalledFontFileInfo &&)
0x18012463a  jmp     loc_1801244E9
0x18012463f  call    cs:__imp_RevertToSelf
0x180124645  jmp     loc_180124518
0x18012464a  movzx   r14d, r14w
0x18012464e  or      r14d, 80070000h
0x180124655  jmp     loc_1801245BA
0x18012465a  call    cs:__imp_RevertToSelf
0x180124660  jmp     loc_18012456A
```
