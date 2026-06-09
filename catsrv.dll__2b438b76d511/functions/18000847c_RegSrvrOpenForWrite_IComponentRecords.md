# RegSrvrOpenForWrite(IComponentRecords * *)

- ea: `0x18000847c`
- end: `0x180008835`
- name: `?RegSrvrOpenForWrite@@YAJPEAPEAUIComponentRecords@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(struct IComponentRecords **)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180016450`
- `0x180039b60`

## callees

- `0x180001284`
- `0x18000847c`
- `0x180009ee0`
- `0x18000ae48`
- `0x18000ae78`
- `0x18000af70`
- `0x18000b230`
- `0x1800235ec`
- `0x180032d20`
- `0x180055502`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!OpenComponentLibraryEx` at `0x1800086bf`
- `CLBCatQ!OpenComponentLibraryEx` at `0x1800086bf`
- `CLBCatQ!SetupOpen` at `0x180008504`
- `CLBCatQ!SetupOpen` at `0x180008504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008608`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000877f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000877f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800085fe`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800085fe`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800086f1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800086f1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800086d5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800086d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegSrvrOpenForWrite(struct IComponentRecords **a1)
{
  signed int TransactionID; // ebx
  int v3; // r9d
  int v4; // r8d
  int i; // edi
  signed int LastError; // eax
  int j; // edi
  DWORD FileAttributesW; // eax
  int v9; // edi
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  struct BOID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  struct BOID *p_Buf1; // [rsp+68h] [rbp-98h]
  _BYTE v19[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h]
  WCHAR ExistingFileName[262]; // [rsp+84h] [rbp-7Ch] BYREF
  WCHAR NewFileName[264]; // [rsp+290h] [rbp+190h] BYREF

  v12 = 0;
  v13 = 0;
  v14 = 0;
  memset_0(v19, 0, 0x220u);
  Buf1 = 0;
  TransactionID = _GetTransactionID(&Buf1);
  if ( TransactionID >= 0 )
  {
    if ( dword_180072D18 )
    {
      if ( (unsigned int)SetupOpen() )
        goto LABEL_8;
      if ( !TransactionID )
      {
        if ( !(unsigned int)IsCallFromMsi() && memcmp_0(&Buf1, &g_txUOW, 0x10u) )
        {
          TransactionID = -2147168238;
LABEL_11:
          CImpersonate::~CImpersonate((CImpersonate *)&v12);
          return (unsigned int)TransactionID;
        }
LABEL_8:
        *a1 = (struct IComponentRecords *)qword_180072D28;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180072D28 + 8LL))(qword_180072D28);
        TransactionID = 0;
        goto LABEL_11;
      }
      if ( TransactionID == 1 )
      {
        TransactionID = -2147418113;
        goto LABEL_11;
      }
    }
    TransactionID = CImpersonate::SuspendImpersonation((CImpersonate *)&v12);
    if ( TransactionID >= 0 )
    {
      v4 = 0;
      dword_180072D18 = 1;
      for ( i = 0; i < 2; ++i )
      {
        TransactionID = RegGetLatestVersion(&dword_180072FEC, (struct REGAPI_DBINFO *)v19, v4, v3);
        if ( TransactionID < 0 )
          goto LABEL_34;
        qword_180072D20 = v20;
        StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", &dword_180072FEC, L"_RegDBWrt.clb");
        if ( CopyFileW(ExistingFileName, NewFileName, 0) )
          break;
        LastError = GetLastError();
        TransactionID = LastError;
        if ( LastError > 0 )
          TransactionID = (unsigned __int16)LastError | 0x80070000;
        if ( TransactionID != -2147024894 || i == 1 )
          goto LABEL_34;
        v4 = 1;
      }
      if ( !g_pICrmLogControl
        || (*(_DWORD *)Buf1.rgb = 0,
            *(_QWORD *)&Buf1.rgb[8] = qword_180072D20,
            v17 = 16,
            p_Buf1 = &Buf1,
            TransactionID = ((__int64 (__fastcall *)(struct ICrmLogControl *, int *, __int64))g_pICrmLogControl->lpVtbl->WriteLogRecord)(
                              g_pICrmLogControl,
                              &v17,
                              1),
            TransactionID >= 0)
        && (TransactionID = ((__int64 (__fastcall *)(struct ICrmLogControl *))g_pICrmLogControl->lpVtbl->ForceLog)(g_pICrmLogControl),
            TransactionID >= 0) )
      {
        for ( j = 0; j < 2; ++j )
        {
          TransactionID = OpenComponentLibraryEx(NewFileName, 66307, &qword_180072D28);
          if ( TransactionID != -2147024891 )
            break;
          FileAttributesW = GetFileAttributesW(NewFileName);
          if ( FileAttributesW == -1
            || (FileAttributesW & 1) == 0
            || !SetFileAttributesW(NewFileName, FileAttributesW & 0xFFFFFFFE) )
          {
            goto LABEL_34;
          }
        }
        if ( TransactionID >= 0 )
        {
          TransactionID = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)qword_180072D28 + 360LL))(
                            qword_180072D28,
                            &COMRegSchemaBlob);
          if ( TransactionID >= 0 )
          {
            *a1 = (struct IComponentRecords *)qword_180072D28;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180072D28 + 8LL))(qword_180072D28);
          }
        }
      }
    }
  }
LABEL_34:
  v9 = 0;
  v10 = v12;
  if ( v12 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
    SetThreadToken(0, 0);
    v10 = v12;
  }
  if ( (v13 & 1) != 0 )
  {
    v9 = CImpersonate::ResumeImpersonation((CImpersonate *)&v12);
    v10 = v12;
  }
  if ( TransactionID < 0 )
    goto LABEL_41;
  if ( v9 < 0 )
  {
    TransactionID = v9;
LABEL_41:
    if ( qword_180072D28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180072D28 + 16LL))(qword_180072D28);
      qword_180072D28 = 0;
      v10 = v12;
    }
    dword_180072D18 = 0;
    *a1 = 0;
  }
  v15 = 0;
  if ( (v13 & 1) != 0 || v10 )
    CImpersonate::Cleanup((CImpersonate *)&v12, &v15);
  return (unsigned int)TransactionID;
}

```

## disassembly

```asm
0x18000847c  mov     [rsp-8+arg_8], rbx
0x180008481  mov     [rsp-8+arg_10], rsi
0x180008486  push    rbp
0x180008487  push    rdi
0x180008488  push    r15
0x18000848a  lea     rbp, [rsp-3B0h]
0x180008492  sub     rsp, 4B0h
0x180008499  mov     rax, cs:__security_cookie
0x1800084a0  xor     rax, rsp
0x1800084a3  mov     [rbp+3C0h+var_20], rax
0x1800084aa  mov     rsi, rcx
0x1800084ad  mov     [rsp+4C0h+var_490], 0
0x1800084b6  mov     [rsp+4C0h+var_488], 0
0x1800084be  mov     [rsp+4C0h+var_480], 0
0x1800084c7  xor     edx, edx; Val
0x1800084c9  mov     r8d, 220h; Size
0x1800084cf  lea     rcx, [rsp+4C0h+var_450]; void *
0x1800084d4  call    memset_0
0x1800084d9  xorps   xmm0, xmm0
0x1800084dc  movups  [rsp+4C0h+Buf1], xmm0
0x1800084e1  lea     rcx, [rsp+4C0h+Buf1]; struct BOID *
0x1800084e6  call    ?_GetTransactionID@@YAJPEAUBOID@@@Z; _GetTransactionID(BOID *)
0x1800084eb  mov     ebx, eax
0x1800084ed  mov     r15d, 1
0x1800084f3  test    eax, eax
0x1800084f5  js      loc_180008747
0x1800084fb  cmp     cs:dword_180072D18, 0
0x180008502  jz      short loc_180008575
0x180008504  call    cs:__imp_SetupOpen
0x18000850a  test    eax, eax
0x18000850c  jnz     short loc_18000853B
0x18000850e  test    ebx, ebx
0x180008510  jnz     short loc_18000855C
0x180008512  call    ?IsCallFromMsi@@YAHXZ; IsCallFromMsi(void)
0x180008517  test    eax, eax
0x180008519  jnz     short loc_18000853B
0x18000851b  lea     r8d, [r15+0Fh]; Size
0x18000851f  lea     rdx, ?g_txUOW@@3UBOID@@A; Buf2
0x180008526  lea     rcx, [rsp+4C0h+Buf1]; Buf1
0x18000852b  call    memcmp_0
0x180008530  test    eax, eax
0x180008532  jz      short loc_18000853B
0x180008534  mov     ebx, 8004D012h
0x180008539  jmp     short loc_180008566
0x18000853b  mov     rax, cs:qword_180072D28
0x180008542  mov     [rsi], rax
0x180008545  mov     rcx, cs:qword_180072D28
0x18000854c  mov     rax, [rcx]
0x18000854f  mov     rax, [rax+8]
0x180008553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008558  xor     ebx, ebx
0x18000855a  jmp     short loc_180008566
0x18000855c  cmp     ebx, r15d
0x18000855f  jnz     short loc_180008575
0x180008561  mov     ebx, 8000FFFFh
0x180008566  lea     rcx, [rsp+4C0h+var_490]; this
0x18000856b  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180008570  jmp     loc_18000880C
0x180008575  lea     rcx, [rsp+4C0h+var_490]; this
0x18000857a  call    ?SuspendImpersonation@CImpersonate@@QEAAJXZ; CImpersonate::SuspendImpersonation(void)
0x18000857f  mov     ebx, eax
0x180008581  test    eax, eax
0x180008583  js      loc_180008747
0x180008589  xor     r8d, r8d; int
0x18000858c  mov     cs:dword_180072D18, r15d
0x180008593  xor     edi, edi
0x180008595  cmp     edi, 2
0x180008598  jge     loc_18000863D
0x18000859e  lea     rdx, [rsp+4C0h+var_450]; struct REGAPI_DBINFO *
0x1800085a3  lea     rcx, dword_180072FEC; unsigned __int16 *
0x1800085aa  call    ?RegGetLatestVersion@@YAJPEBGPEAUREGAPI_DBINFO@@HH@Z; RegGetLatestVersion(ushort const *,REGAPI_DBINFO *,int,int)
0x1800085af  mov     ebx, eax
0x1800085b1  test    eax, eax
0x1800085b3  js      loc_180008747
0x1800085b9  mov     rax, [rsp+4C0h+var_448]
0x1800085be  mov     cs:qword_180072D20, rax
0x1800085c5  lea     rax, aRegdbwrtClb; "_RegDBWrt.clb"
0x1800085cc  mov     [rsp+4C0h+var_4A0], rax
0x1800085d1  lea     r9, dword_180072FEC
0x1800085d8  lea     r8, aSS; "%s\\%s"
0x1800085df  mov     edx, 104h; unsigned __int64
0x1800085e4  lea     rcx, [rbp+3C0h+NewFileName]; unsigned __int16 *
0x1800085eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800085f0  xor     r8d, r8d; bFailIfExists
0x1800085f3  lea     rdx, [rbp+3C0h+NewFileName]; lpNewFileName
0x1800085fa  lea     rcx, [rbp+3C0h+ExistingFileName]; lpExistingFileName
0x1800085fe  call    cs:__imp_CopyFileW
0x180008604  test    eax, eax
0x180008606  jnz     short loc_18000863D
0x180008608  call    cs:__imp_GetLastError
0x18000860e  mov     ebx, eax
0x180008610  test    eax, eax
0x180008612  jle     short loc_18000861D
0x180008614  movzx   ebx, ax
0x180008617  or      ebx, 80070000h
0x18000861d  cmp     ebx, 80070002h
0x180008623  jnz     loc_180008747
0x180008629  cmp     edi, r15d
0x18000862c  jz      loc_180008747
0x180008632  mov     r8d, r15d
0x180008635  add     edi, r15d
0x180008638  jmp     loc_180008595
0x18000863d  mov     rcx, cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA; ICrmLogControl * g_pICrmLogControl
0x180008644  test    rcx, rcx
0x180008647  jz      short loc_1800086AA
0x180008649  mov     dword ptr [rsp+4C0h+Buf1], 0
0x180008651  mov     rax, cs:qword_180072D20
0x180008658  mov     qword ptr [rsp+4C0h+Buf1+8], rax
0x18000865d  mov     [rsp+4C0h+var_460], 10h
0x180008665  lea     rax, [rsp+4C0h+Buf1]
0x18000866a  mov     [rsp+4C0h+var_458], rax
0x18000866f  mov     rax, [rcx]
0x180008672  mov     r8d, r15d
0x180008675  lea     rdx, [rsp+4C0h+var_460]
0x18000867a  mov     rax, [rax+48h]
0x18000867e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008683  mov     ebx, eax
0x180008685  test    eax, eax
0x180008687  js      loc_180008747
0x18000868d  mov     rcx, cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA; ICrmLogControl * g_pICrmLogControl
0x180008694  mov     rax, [rcx]
0x180008697  mov     rax, [rax+30h]
0x18000869b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a0  mov     ebx, eax
0x1800086a2  test    eax, eax
0x1800086a4  js      loc_180008747
0x1800086aa  xor     edi, edi
0x1800086ac  lea     r8, qword_180072D28
0x1800086b3  mov     edx, 10303h
0x1800086b8  lea     rcx, [rbp+3C0h+NewFileName]
0x1800086bf  call    cs:__imp_OpenComponentLibraryEx
0x1800086c5  mov     ebx, eax
0x1800086c7  cmp     eax, 80070005h
0x1800086cc  jnz     short loc_180008703
0x1800086ce  lea     rcx, [rbp+3C0h+NewFileName]; lpFileName
0x1800086d5  call    cs:__imp_GetFileAttributesW
0x1800086db  cmp     eax, 0FFFFFFFFh
0x1800086de  jz      short loc_180008747
0x1800086e0  test    r15b, al
0x1800086e3  jz      short loc_180008747
0x1800086e5  and     eax, 0FFFFFFFEh
0x1800086e8  mov     edx, eax; dwFileAttributes
0x1800086ea  lea     rcx, [rbp+3C0h+NewFileName]; lpFileName
0x1800086f1  call    cs:__imp_SetFileAttributesW
0x1800086f7  test    eax, eax
0x1800086f9  jz      short loc_180008747
0x1800086fb  add     edi, r15d
0x1800086fe  cmp     edi, 2
0x180008701  jl      short loc_1800086AC
0x180008703  test    ebx, ebx
0x180008705  js      short loc_180008747
0x180008707  mov     rcx, cs:qword_180072D28
0x18000870e  mov     rax, [rcx]
0x180008711  lea     rdx, ?COMRegSchemaBlob@@3U_tagCOMPLIBSCHEMABLOB@@B; _tagCOMPLIBSCHEMABLOB const COMRegSchemaBlob
0x180008718  mov     rax, [rax+168h]
0x18000871f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008724  mov     ebx, eax
0x180008726  test    eax, eax
0x180008728  js      short loc_180008747
0x18000872a  mov     rax, cs:qword_180072D28
0x180008731  mov     [rsi], rax
0x180008734  mov     rcx, cs:qword_180072D28
0x18000873b  mov     rax, [rcx]
0x18000873e  mov     rax, [rax+8]
0x180008742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008747  xor     edi, edi
0x180008749  mov     rcx, [rsp+4C0h+var_490]
0x18000874e  test    rcx, rcx
0x180008751  jz      short loc_18000878A
0x180008753  mov     rax, [rcx]
0x180008756  mov     rax, [rax+28h]
0x18000875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875f  mov     edi, eax
0x180008761  mov     rcx, [rsp+4C0h+var_490]
0x180008766  mov     rdx, [rcx]
0x180008769  mov     rax, [rdx+10h]
0x18000876d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008772  mov     [rsp+4C0h+var_490], 0
0x18000877b  xor     edx, edx; Token
0x18000877d  xor     ecx, ecx; Thread
0x18000877f  call    cs:__imp_SetThreadToken
0x180008785  mov     rcx, [rsp+4C0h+var_490]
0x18000878a  test    byte ptr [rsp+4C0h+var_488], r15b
0x18000878f  jz      short loc_1800087A2
0x180008791  lea     rcx, [rsp+4C0h+var_490]; this
0x180008796  call    ?ResumeImpersonation@CImpersonate@@QEAAJXZ; CImpersonate::ResumeImpersonation(void)
0x18000879b  mov     edi, eax
0x18000879d  mov     rcx, [rsp+4C0h+var_490]
0x1800087a2  test    ebx, ebx
0x1800087a4  js      short loc_1800087AC
0x1800087a6  test    edi, edi
0x1800087a8  jns     short loc_1800087E8
0x1800087aa  mov     ebx, edi
0x1800087ac  mov     rdx, cs:qword_180072D28
0x1800087b3  test    rdx, rdx
0x1800087b6  jz      short loc_1800087D7
0x1800087b8  mov     rax, [rdx]
0x1800087bb  mov     rcx, rdx
0x1800087be  mov     rax, [rax+10h]
0x1800087c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c7  mov     cs:qword_180072D28, 0
0x1800087d2  mov     rcx, [rsp+4C0h+var_490]
0x1800087d7  mov     cs:dword_180072D18, 0
0x1800087e1  mov     qword ptr [rsi], 0
0x1800087e8  mov     [rsp+4C0h+var_478], 0
0x1800087f0  test    byte ptr [rsp+4C0h+var_488], r15b
0x1800087f5  jnz     short loc_1800087FC
0x1800087f7  test    rcx, rcx
0x1800087fa  jz      short loc_18000880C
0x1800087fc  lea     rdx, [rsp+4C0h+var_478]; int *
0x180008801  lea     rcx, [rsp+4C0h+var_490]; this
0x180008806  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x18000880b  nop
0x18000880c  mov     eax, ebx
0x18000880e  mov     rcx, [rbp+3C0h+var_20]
0x180008815  xor     rcx, rsp; StackCookie
0x180008818  call    __security_check_cookie
0x18000881d  lea     r11, [rsp+4C0h+var_10]
0x180008825  mov     rbx, [r11+28h]
0x180008829  mov     rsi, [r11+30h]
0x18000882d  mov     rsp, r11
0x180008830  pop     r15
0x180008832  pop     rdi
0x180008833  pop     rbp
0x180008834  retn
```
