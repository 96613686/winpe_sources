# CDXGIBaseAdapter::LoadUMD(_KMTUMDVERSION,HINSTANCE__ * *)

- ea: `0x1800062e0`
- end: `0x180006605`
- name: `?LoadUMD@CDXGIBaseAdapter@@UEAAJW4_KMTUMDVERSION@@PEAPEAUHINSTANCE__@@@Z`
- size: `805`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800062e0`
- `0x180006770`
- `0x1800067c8`
- `0x1800068d0`
- `0x18000c6b0`
- `0x18000cb70`
- `0x180075fa0`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800063c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006556`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800063c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006556`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800064e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800064e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000658c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000658c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e7`

## string_xrefs

- `0x18000649c`: `QAI for KMTQAITYPE_CHECKDRIVERUPDATESTATUS failed.`
- `0x1800064b1`: `Device removed while querying UMD filename.`
- `0x18000659c`: `LoadLibraryExW failed, file name will be logged.`
- `0x1800064ea`: `Failed loading the UMD while driver update is in progress.`

## pseudocode

```c
__int64 __fastcall CDXGIBaseAdapter::LoadUMD(__int64 a1, int a2, HMODULE *a3)
{
  __int64 (__fastcall *v6)(int *); // rax
  int v7; // eax
  int v8; // eax
  CModule *v9; // rcx
  bool v10; // r9
  unsigned int v11; // ebx
  const char *v12; // r8
  unsigned int v13; // edx
  unsigned int v15; // ebx
  __int64 v16; // rcx
  HMODULE Library; // rsi
  __int64 (__fastcall *v18)(int *); // rax
  signed int v19; // eax
  CModule *v20; // rcx
  bool v21; // r9
  int v22; // ebx
  bool v23; // di
  __int64 v24; // rcx
  CModule *v25; // rcx
  bool v26; // r9
  signed int LastError; // eax
  CModule *v28; // rcx
  bool v29; // r9
  int v30; // edi
  __int64 v31; // rcx
  bool v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33; // [rsp+24h] [rbp-DCh] BYREF
  int v34; // [rsp+28h] [rbp-D8h] BYREF
  int v35; // [rsp+2Ch] [rbp-D4h]
  int *v36; // [rsp+30h] [rbp-D0h]
  __int64 v37; // [rsp+38h] [rbp-C8h]
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR LibFileName[262]; // [rsp+44h] [rbp-BCh] BYREF

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  memset_0(LibFileName, 0, 0x208u);
  v34 = *(_DWORD *)(a1 + 44);
  v36 = &v38;
  v6 = *(__int64 (__fastcall **)(int *))(a1 + 136);
  v38 = a2;
  v35 = 1;
  v37 = 524;
  v7 = v6(&v34);
  v8 = NTStatusToHResult(v7);
  v11 = v8;
  if ( v8 == -2005530512 )
  {
    v11 = -2005270523;
    v12 = "Device removed while querying UMD filename.";
    v13 = -2005270523;
    goto LABEL_6;
  }
  if ( v8 == -2147024809 )
    return (unsigned int)-2005270524;
  if ( v8 < 0 )
  {
    v12 = "Unexpected error while querying UMD filename.";
    v13 = v8;
LABEL_6:
    CModule::RecordJournalImpl(v9, v13, v12, v10);
    return v11;
  }
  v23 = 0;
  LibFileName[259] = 0;
  v32 = 0;
  if ( *(_DWORD *)(a1 + 572) == -1 )
  {
    v15 = -1;
  }
  else
  {
    v15 = 6;
    if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v9, "(", 6);
  }
  Library = LoadLibraryExW(LibFileName, 0, 8u);
  if ( Library || GetLastError() == 87 && (Library = LoadLibraryExW(LibFileName, 0, 0)) != 0 )
  {
    if ( v15 != -1 && (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v16, EventProfileStop, v15);
    v34 = *(_DWORD *)(a1 + 44);
    v36 = &v33;
    v18 = *(__int64 (__fastcall **)(int *))(a1 + 136);
    v33 = 0;
    v35 = 11;
    v37 = 4;
    v19 = v18(&v34);
    v22 = v19;
    if ( v19 < 0 )
      CModule::RecordJournalImpl(v20, v19, "QAI for KMTQAITYPE_CHECKDRIVERUPDATESTATUS failed.", v21);
    else
      v23 = v33 != 0;
    if ( v22 >= 0 && !v23 )
    {
      *a3 = Library;
      return 0;
    }
    CModule::RecordJournalImpl(v20, 0x887A0005, "Driver upgrade in progress.", v21);
    FreeLibrary(Library);
    return 2289696773LL;
  }
  if ( (int)CDXGIBaseAdapter::IsDriverUpdateInProgress((CDXGIBaseAdapter *)(a1 - 176), &v32) < 0 || v32 )
  {
    CModule::RecordJournalImpl(v25, 0x887A0005, "Failed loading the UMD while driver update is in progress.", v26);
    if ( v15 != -1 && (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v24, EventProfileStop, v15);
    return 2289696773LL;
  }
  LastError = GetLastError();
  v30 = LastError;
  if ( LastError > 0 )
    v30 = (unsigned __int16)LastError | 0x80070000;
  if ( v30 < 0 )
    CModule::RecordJournalImpl(v28, v30, "LoadLibraryExW failed, file name will be logged.", v29);
  RecordHRESULTAlwaysLongWideMessage(v30, LibFileName);
  if ( v15 != -1 && (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v31, EventProfileStop, v15);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1800062e0  push    rbp
0x1800062e2  push    rbx
0x1800062e3  push    rsi
0x1800062e4  push    rdi
0x1800062e5  push    r13
0x1800062e7  push    r14
0x1800062e9  push    r15
0x1800062eb  lea     rbp, [rsp-160h]
0x1800062f3  sub     rsp, 260h
0x1800062fa  mov     rax, cs:__security_cookie
0x180006301  xor     rax, rsp
0x180006304  mov     [rbp+190h+var_40], rax
0x18000630b  mov     r15, r8
0x18000630e  mov     ebx, edx
0x180006310  mov     r14, rcx
0x180006313  test    r8, r8
0x180006316  jz      loc_1800064C2
0x18000631c  mov     qword ptr [r8], 0
0x180006323  lea     rcx, [rsp+290h+LibFileName]; void *
0x180006328  mov     r8d, 208h; Size
0x18000632e  xor     edx, edx; Val
0x180006330  call    memset_0
0x180006335  mov     eax, [r14+2Ch]
0x180006339  lea     rcx, [rsp+290h+var_268]
0x18000633e  mov     [rsp+290h+var_268], eax
0x180006342  lea     rax, [rsp+290h+var_250]
0x180006347  mov     [rsp+290h+var_260], rax
0x18000634c  mov     rax, [r14+88h]
0x180006353  mov     [rsp+290h+var_250], ebx
0x180006357  mov     [rsp+290h+var_264], 1
0x18000635f  mov     [rsp+290h+var_258], 20Ch
0x180006368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636d  mov     ecx, eax; int
0x18000636f  call    ?NTStatusToHResult@@YAJJ@Z; NTStatusToHResult(long)
0x180006374  mov     ebx, eax
0x180006376  cmp     eax, 88760870h
0x18000637b  jz      loc_1800064AC
0x180006381  cmp     eax, 80070057h
0x180006386  jz      loc_1800065FB
0x18000638c  test    eax, eax
0x18000638e  jns     loc_180006524
0x180006394  lea     r8, aUnexpectedErro; "Unexpected error while querying UMD fil"...
0x18000639b  mov     edx, eax; unsigned int
0x18000639d  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800063a2  mov     eax, ebx
0x1800063a4  jmp     loc_180006453
0x1800063a9  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x1800063b0  mov     ebx, 6
0x1800063b5  jnz     loc_180006474
0x1800063bb  xor     edx, edx; hFile
0x1800063bd  lea     rcx, [rsp+290h+LibFileName]; lpLibFileName
0x1800063c2  lea     r8d, [rdx+8]; dwFlags
0x1800063c6  call    cs:__imp_LoadLibraryExW
0x1800063cc  mov     rsi, rax
0x1800063cf  test    rax, rax
0x1800063d2  jz      loc_1800065E7
0x1800063d8  cmp     ebx, 0FFFFFFFFh
0x1800063db  jz      short loc_1800063EA
0x1800063dd  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x1800063e4  jnz     loc_180006488
0x1800063ea  mov     eax, [r14+2Ch]
0x1800063ee  lea     rcx, [rsp+290h+var_268]
0x1800063f3  mov     [rsp+290h+var_268], eax
0x1800063f7  lea     rax, [rsp+290h+var_26C]
0x1800063fc  mov     [rsp+290h+var_260], rax
0x180006401  mov     rax, [r14+88h]
0x180006408  mov     [rsp+290h+var_26C], 0
0x180006410  mov     [rsp+290h+var_264], 0Bh
0x180006418  mov     [rsp+290h+var_258], 4
0x180006421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006426  mov     ebx, eax
0x180006428  test    eax, eax
0x18000642a  js      short loc_18000649C
0x18000642c  cmp     [rsp+290h+var_26C], 0
0x180006431  mov     eax, 1
0x180006436  movzx   edi, dil
0x18000643a  cmovnz  edi, eax
0x18000643d  or      ebx, 10000000h
0x180006443  jl      loc_1800064C9
0x180006449  test    dil, dil
0x18000644c  jnz     short loc_1800064C9
0x18000644e  mov     [r15], rsi
0x180006451  xor     eax, eax
0x180006453  mov     rcx, [rbp+190h+var_40]
0x18000645a  xor     rcx, rsp; StackCookie
0x18000645d  call    __security_check_cookie
0x180006462  add     rsp, 260h
0x180006469  pop     r15
0x18000646b  pop     r14
0x18000646d  pop     r13
0x18000646f  pop     rdi
0x180006470  pop     rsi
0x180006471  pop     rbx
0x180006472  pop     rbp
0x180006473  retn
0x180006474  mov     r8d, ebx
0x180006477  lea     rdx, EventProfileStart; "("
0x18000647e  call    McTemplateU0q_EtwEventWriteTransfer
0x180006483  jmp     loc_1800063BB
0x180006488  mov     r8d, ebx
0x18000648b  lea     rdx, EventProfileStop
0x180006492  call    McTemplateU0q_EtwEventWriteTransfer
0x180006497  jmp     loc_1800063EA
0x18000649c  lea     r8, aQaiForKmtqaity; "QAI for KMTQAITYPE_CHECKDRIVERUPDATESTA"...
0x1800064a3  mov     edx, ebx; unsigned int
0x1800064a5  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800064aa  jmp     short loc_18000643D
0x1800064ac  mov     ebx, 887A0005h
0x1800064b1  lea     r8, aDeviceRemovedW; "Device removed while querying UMD filen"...
0x1800064b8  mov     edx, 887A0005h
0x1800064bd  jmp     loc_18000639D
0x1800064c2  mov     eax, 80004003h
0x1800064c7  jmp     short loc_180006453
0x1800064c9  lea     r8, aDriverUpgradeI; "Driver upgrade in progress."
0x1800064d0  mov     edx, 887A0005h; unsigned int
0x1800064d5  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800064da  test    rsi, rsi
0x1800064dd  jz      short loc_180006509
0x1800064df  mov     rcx, rsi; hLibModule
0x1800064e2  call    cs:__imp_FreeLibrary
0x1800064e8  jmp     short loc_180006509
0x1800064ea  lea     r8, aFailedLoadingT; "Failed loading the UMD while driver upd"...
0x1800064f1  mov     edx, 887A0005h; unsigned int
0x1800064f6  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800064fb  cmp     ebx, 0FFFFFFFFh
0x1800064fe  jz      short loc_180006509
0x180006500  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x180006507  jnz     short loc_180006513
0x180006509  mov     eax, 887A0005h
0x18000650e  jmp     loc_180006453
0x180006513  mov     r8d, ebx
0x180006516  lea     rdx, EventProfileStop
0x18000651d  call    McTemplateU0q_EtwEventWriteTransfer
0x180006522  jmp     short loc_180006509
0x180006524  xor     eax, eax
0x180006526  xor     dil, dil
0x180006529  mov     [rbp+190h+var_46], ax
0x180006530  or      eax, 0FFFFFFFFh
0x180006533  mov     [rsp+290h+var_270], dil
0x180006538  cmp     [r14+23Ch], eax
0x18000653f  jnz     loc_1800063A9
0x180006545  mov     ebx, eax
0x180006547  jmp     loc_1800063BB
0x18000654c  xor     r8d, r8d; dwFlags
0x18000654f  lea     rcx, [rsp+290h+LibFileName]; lpLibFileName
0x180006554  xor     edx, edx; hFile
0x180006556  call    cs:__imp_LoadLibraryExW
0x18000655c  mov     rsi, rax
0x18000655f  test    rax, rax
0x180006562  jnz     loc_1800063D8
0x180006568  lea     rdx, [rsp+290h+var_270]; bool *
0x18000656d  lea     rcx, [r14-0B0h]; this
0x180006574  call    ?IsDriverUpdateInProgress@CDXGIBaseAdapter@@QEAAJAEA_N@Z; CDXGIBaseAdapter::IsDriverUpdateInProgress(bool &)
0x180006579  test    eax, eax
0x18000657b  js      loc_1800064EA
0x180006581  cmp     [rsp+290h+var_270], dil
0x180006586  jnz     loc_1800064EA
0x18000658c  call    cs:__imp_GetLastError
0x180006592  mov     edi, eax
0x180006594  test    eax, eax
0x180006596  jg      short loc_1800065DC
0x180006598  test    edi, edi
0x18000659a  jns     short loc_1800065AA
0x18000659c  lea     r8, aLoadlibraryexw; "LoadLibraryExW failed, file name will b"...
0x1800065a3  mov     edx, edi; unsigned int
0x1800065a5  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800065aa  lea     rdx, [rsp+290h+LibFileName]; unsigned __int16 *
0x1800065af  mov     ecx, edi; unsigned int
0x1800065b1  call    ?RecordHRESULTAlwaysLongWideMessage@@YAJJPEBG@Z; RecordHRESULTAlwaysLongWideMessage(long,ushort const *)
0x1800065b6  cmp     ebx, 0FFFFFFFFh
0x1800065b9  jz      short loc_1800065C4
0x1800065bb  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x1800065c2  jnz     short loc_1800065CB
0x1800065c4  mov     eax, edi
0x1800065c6  jmp     loc_180006453
0x1800065cb  mov     r8d, ebx
0x1800065ce  lea     rdx, EventProfileStop
0x1800065d5  call    McTemplateU0q_EtwEventWriteTransfer
0x1800065da  jmp     short loc_1800065C4
0x1800065dc  movzx   edi, ax
0x1800065df  or      edi, 80070000h
0x1800065e5  jmp     short loc_180006598
0x1800065e7  call    cs:__imp_GetLastError
0x1800065ed  cmp     eax, 57h ; 'W'
0x1800065f0  jnz     loc_180006568
0x1800065f6  jmp     loc_18000654C
0x1800065fb  mov     ebx, 887A0004h
0x180006600  jmp     loc_1800063A2
```
