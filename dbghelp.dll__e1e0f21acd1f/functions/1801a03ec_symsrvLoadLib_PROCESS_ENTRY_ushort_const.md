# symsrvLoadLib(_PROCESS_ENTRY *,ushort const *)

- ea: `0x1801a03ec`
- end: `0x1801a082d`
- name: `?symsrvLoadLib@@YA_NPEAU_PROCESS_ENTRY@@PEBG@Z`
- size: `1089`
- prototype: `bool __fastcall(struct _PROCESS_ENTRY *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x18019e7f0`
- `0x1801a01e4`

## callees

- `0x180005650`
- `0x18000dfac`
- `0x180019c4c`
- `0x180021374`
- `0x180022d28`
- `0x180027430`
- `0x18019e96c`
- `0x1801a03ec`
- `0x1801a0834`
- `0x1801a089c`
- `0x1801a08d4`
- `0x1801a360c`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0444`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a07b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a07d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0444`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a07b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a07d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a0423`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a0423`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a0439`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a0459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a07b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a07e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a0439`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a0459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a07b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a07e2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a06be`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a06be`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x1801a072d`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x1801a072d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1801a07c3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1801a07c3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0495`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a04b9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a04d4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a04ef`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a050a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0525`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0540`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a055b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0576`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0591`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a05ac`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a05c7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0608`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0649`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a079c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0495`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a04b9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a04d4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a04ef`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a050a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0525`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0540`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a055b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0576`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0591`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a05ac`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a05c7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0608`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a0649`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a079c`

## string_xrefs

- `0x1801a05eb`: `Unable to find the SymbolServerGetOptionData() function in symsrv.dll. You should upgrade the symsrv.dll binary.\n`
- `0x1801a062c`: `Unable to find the SymbolServerWEx() function in symsrv.dll. You should upgrade the symsrv.dll binary.\n`
- `0x1801a066d`: `Unable to find the SymbolServerPingWEx() function in symsrv.dll. You should upgrade the symsrv.dll binary.\n`
- `0x1801a0795`: `SymbolServerEnableNegativeAuthCacheFeature`

## pseudocode

```c
char __fastcall symsrvLoadLib(struct _PROCESS_ENTRY *a1, const unsigned __int16 *a2)
{
  unsigned int ExtendedOption; // esi
  HMODULE DLL; // rax
  void *v7; // rcx
  int v8; // eax
  FARPROC ProcAddress; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  EnterCriticalSection(&CriticalSection);
  if ( hLibModule == (HMODULE)-1LL )
  {
    LeaveCriticalSection(&CriticalSection);
    SetLastError(0x7Eu);
    return 0;
  }
  if ( hLibModule )
  {
    LeaveCriticalSection(&CriticalSection);
    return 1;
  }
  ExtendedOption = SymGetExtendedOption((IMAGEHLP_EXTENDED_OPTIONS)5);
  DLL = LoadDLL(a2);
  hLibModule = DLL;
  if ( !DLL )
  {
LABEL_40:
    hLibModule = (HMODULE)-1LL;
    SetLastError(0x7Eu);
    LeaveCriticalSection(&CriticalSection);
    if ( (unsigned int)spew() )
      _pwprint(a1, L"%s load failure\n", a2);
    return 0;
  }
  qword_1802AF8C0 = (__int64)GetProcAddress(DLL, "SymbolServerW");
  if ( !qword_1802AF8C0 )
  {
    FreeLibrary(hLibModule);
    goto LABEL_40;
  }
  qword_1802AF8C8 = (__int64)GetProcAddress(hLibModule, "SymbolServerClose");
  qword_1802AF8D0 = (__int64)GetProcAddress(hLibModule, "SymbolServerSetOptionsW");
  qword_1802AF8D8 = (__int64)GetProcAddress(hLibModule, "SymbolServerPingW");
  qword_1802AF8E0 = (__int64)GetProcAddress(hLibModule, "SymbolServerDeltaNameW");
  qword_1802AF8E8 = (__int64)GetProcAddress(hLibModule, "SymbolServerGetSupplementW");
  qword_1802AF8F0 = (__int64)GetProcAddress(hLibModule, "SymbolServerStoreSupplementW");
  qword_1802AF8F8 = (__int64)GetProcAddress(hLibModule, "SymbolServerGetIndexStringW");
  qword_1802AF900 = (__int64)GetProcAddress(hLibModule, "SymbolServerStoreFileW");
  qword_1802AF908 = (__int64)GetProcAddress(hLibModule, "SymbolServerIsStoreW");
  qword_1802AF910 = (__int64)GetProcAddress(hLibModule, "SymbolServerGetOptions");
  qword_1802AF918 = (__int64)GetProcAddress(hLibModule, "SymbolServerGetOptionData");
  if ( !qword_1802AF918 && IsInternalPackage() && (unsigned int)spew() )
    _pwprint(
      a1,
      L"Unable to find the SymbolServerGetOptionData() function in symsrv.dll. You should upgrade the symsrv.dll binary.\n");
  qword_1802B1C40 = (__int64)GetProcAddress(hLibModule, "SymbolServerWEx");
  if ( !qword_1802B1C40 && IsInternalPackage() && (unsigned int)spew() )
    _pwprint(
      a1,
      L"Unable to find the SymbolServerWEx() function in symsrv.dll. You should upgrade the symsrv.dll binary.\n");
  qword_1802B1C48 = (__int64)GetProcAddress(hLibModule, "SymbolServerPingWEx");
  if ( !qword_1802B1C48 && IsInternalPackage() && (unsigned int)spew() )
    _pwprint(
      a1,
      L"Unable to find the SymbolServerPingWEx() function in symsrv.dll. You should upgrade the symsrv.dll binary.\n");
  symsrvSetOptions(0x100u, 8u);
  symsrvSetService();
  symsrvSetPrompts();
  symsrvSetCallback();
  memset_0(Buffer, 0, 0x20Au);
  if ( GetEnvironmentVariableW(L"_NT_SYMBOL_PROXY", Buffer, 0x105u) )
    symsrvSetOptions(0x40000u, (unsigned __int64)Buffer);
  if ( word_1802B0BBA )
  {
    symsrvSetOptions(0x2000u, (unsigned __int64)&word_1802B0BBA);
  }
  else
  {
    if ( a1 )
      v7 = (void *)*((_QWORD *)a1 + 6);
    else
      v7 = 0;
    SetHomeDirectory(v7, &dir, 1);
  }
  v8 = dword_1802AF9CC;
  if ( dword_1802AF9CC < 0 )
  {
    if ( !SetEnvironmentVariableA("SYMSRV_DBGOUT", "1") && (unsigned int)spew() )
      _pwprint(a1, L"Unable to set the SYMSRV_DBGOUT environment variable.\n");
    symsrvSetOptions(0x10000000u, 1u);
    v8 = dword_1802AF9CC;
  }
  if ( (v8 & 0x20000000) != 0 )
  {
    symsrvSetOptions(0x8000000u, 1u);
    v8 = dword_1802AF9CC;
  }
  if ( (v8 & 0x10000000) != 0 )
    symsrvSetOptions(0x4000000u, 1u);
  ProcAddress = GetProcAddress(hLibModule, "SymbolServerEnableNegativeAuthCacheFeature");
  if ( ProcAddress )
    ((void (__fastcall *)(_QWORD))ProcAddress)(ExtendedOption);
  SetLastError(0);
  LeaveCriticalSection(&CriticalSection);
  return 1;
}

```

## disassembly

```asm
0x1801a03ec  mov     [rsp+arg_10], rbx
0x1801a03f1  mov     [rsp+arg_18], rbp
0x1801a03f6  push    rsi
0x1801a03f7  push    rdi
0x1801a03f8  push    r14
0x1801a03fa  sub     rsp, 240h
0x1801a0401  mov     rax, cs:__security_cookie
0x1801a0408  xor     rax, rsp
0x1801a040b  mov     [rsp+258h+var_28], rax
0x1801a0413  mov     rdi, rcx
0x1801a0416  lea     r14, CriticalSection
0x1801a041d  mov     rcx, r14; lpCriticalSection
0x1801a0420  mov     rbx, rdx
0x1801a0423  call    cs:__imp_EnterCriticalSection
0x1801a0429  mov     rax, cs:hLibModule
0x1801a0430  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a0434  jnz     short loc_1801A044F
0x1801a0436  mov     rcx, r14; lpCriticalSection
0x1801a0439  call    cs:__imp_LeaveCriticalSection
0x1801a043f  mov     ecx, 7Eh ; '~'; dwErrCode
0x1801a0444  call    cs:__imp_SetLastError
0x1801a044a  jmp     loc_1801A0803
0x1801a044f  xor     ebp, ebp
0x1801a0451  test    rax, rax
0x1801a0454  jz      short loc_1801A0467
0x1801a0456  mov     rcx, r14; lpCriticalSection
0x1801a0459  call    cs:__imp_LeaveCriticalSection
0x1801a045f  lea     eax, [rbp+1]
0x1801a0462  jmp     loc_1801A0805
0x1801a0467  mov     ecx, 5; option
0x1801a046c  call    SymGetExtendedOption
0x1801a0471  mov     rcx, rbx; unsigned __int16 *
0x1801a0474  mov     esi, eax
0x1801a0476  call    ?LoadDLL@@YAPEAUHINSTANCE__@@PEBG@Z; LoadDLL(ushort const *)
0x1801a047b  mov     cs:hLibModule, rax
0x1801a0482  test    rax, rax
0x1801a0485  jz      loc_1801A07C9
0x1801a048b  lea     rdx, aSymbolserverw; "SymbolServerW"
0x1801a0492  mov     rcx, rax; hModule
0x1801a0495  call    cs:__imp_GetProcAddress
0x1801a049b  mov     rcx, cs:hLibModule; hLibModule
0x1801a04a2  mov     cs:qword_1802AF8C0, rax
0x1801a04a9  test    rax, rax
0x1801a04ac  jz      loc_1801A07C3
0x1801a04b2  lea     rdx, aSymbolservercl; "SymbolServerClose"
0x1801a04b9  call    cs:__imp_GetProcAddress
0x1801a04bf  mov     rcx, cs:hLibModule; hModule
0x1801a04c6  lea     rdx, aSymbolserverse; "SymbolServerSetOptionsW"
0x1801a04cd  mov     cs:qword_1802AF8C8, rax
0x1801a04d4  call    cs:__imp_GetProcAddress
0x1801a04da  mov     rcx, cs:hLibModule; hModule
0x1801a04e1  lea     rdx, aSymbolserverpi; "SymbolServerPingW"
0x1801a04e8  mov     cs:qword_1802AF8D0, rax
0x1801a04ef  call    cs:__imp_GetProcAddress
0x1801a04f5  mov     rcx, cs:hLibModule; hModule
0x1801a04fc  lea     rdx, aSymbolserverde; "SymbolServerDeltaNameW"
0x1801a0503  mov     cs:qword_1802AF8D8, rax
0x1801a050a  call    cs:__imp_GetProcAddress
0x1801a0510  mov     rcx, cs:hLibModule; hModule
0x1801a0517  lea     rdx, aSymbolserverge_1; "SymbolServerGetSupplementW"
0x1801a051e  mov     cs:qword_1802AF8E0, rax
0x1801a0525  call    cs:__imp_GetProcAddress
0x1801a052b  mov     rcx, cs:hLibModule; hModule
0x1801a0532  lea     rdx, aSymbolserverst_0; "SymbolServerStoreSupplementW"
0x1801a0539  mov     cs:qword_1802AF8E8, rax
0x1801a0540  call    cs:__imp_GetProcAddress
0x1801a0546  mov     rcx, cs:hLibModule; hModule
0x1801a054d  lea     rdx, aSymbolserverge_4; "SymbolServerGetIndexStringW"
0x1801a0554  mov     cs:qword_1802AF8F0, rax
0x1801a055b  call    cs:__imp_GetProcAddress
0x1801a0561  mov     rcx, cs:hLibModule; hModule
0x1801a0568  lea     rdx, aSymbolserverst; "SymbolServerStoreFileW"
0x1801a056f  mov     cs:qword_1802AF8F8, rax
0x1801a0576  call    cs:__imp_GetProcAddress
0x1801a057c  mov     rcx, cs:hLibModule; hModule
0x1801a0583  lea     rdx, aSymbolserveris_0; "SymbolServerIsStoreW"
0x1801a058a  mov     cs:qword_1802AF900, rax
0x1801a0591  call    cs:__imp_GetProcAddress
0x1801a0597  mov     rcx, cs:hLibModule; hModule
0x1801a059e  lea     rdx, aSymbolserverge_2; "SymbolServerGetOptions"
0x1801a05a5  mov     cs:qword_1802AF908, rax
0x1801a05ac  call    cs:__imp_GetProcAddress
0x1801a05b2  mov     rcx, cs:hLibModule; hModule
0x1801a05b9  lea     rdx, aSymbolserverge; "SymbolServerGetOptionData"
0x1801a05c0  mov     cs:qword_1802AF910, rax
0x1801a05c7  call    cs:__imp_GetProcAddress
0x1801a05cd  mov     cs:qword_1802AF918, rax
0x1801a05d4  test    rax, rax
0x1801a05d7  jnz     short loc_1801A05FA
0x1801a05d9  call    ?IsInternalPackage@@YA_NXZ; IsInternalPackage(void)
0x1801a05de  test    al, al
0x1801a05e0  jz      short loc_1801A05FA
0x1801a05e2  call    ?spew@@YAHXZ; spew(void)
0x1801a05e7  test    eax, eax
0x1801a05e9  jz      short loc_1801A05FA
0x1801a05eb  lea     rdx, aUnableToFindTh_0; "Unable to find the SymbolServerGetOptio"...
0x1801a05f2  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1801a05f5  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a05fa  mov     rcx, cs:hLibModule; hModule
0x1801a0601  lea     rdx, aSymbolserverwe; "SymbolServerWEx"
0x1801a0608  call    cs:__imp_GetProcAddress
0x1801a060e  mov     cs:qword_1802B1C40, rax
0x1801a0615  test    rax, rax
0x1801a0618  jnz     short loc_1801A063B
0x1801a061a  call    ?IsInternalPackage@@YA_NXZ; IsInternalPackage(void)
0x1801a061f  test    al, al
0x1801a0621  jz      short loc_1801A063B
0x1801a0623  call    ?spew@@YAHXZ; spew(void)
0x1801a0628  test    eax, eax
0x1801a062a  jz      short loc_1801A063B
0x1801a062c  lea     rdx, aUnableToFindTh_1; "Unable to find the SymbolServerWEx() fu"...
0x1801a0633  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1801a0636  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a063b  mov     rcx, cs:hLibModule; hModule
0x1801a0642  lea     rdx, aSymbolserverpi_0; "SymbolServerPingWEx"
0x1801a0649  call    cs:__imp_GetProcAddress
0x1801a064f  mov     cs:qword_1802B1C48, rax
0x1801a0656  test    rax, rax
0x1801a0659  jnz     short loc_1801A067C
0x1801a065b  call    ?IsInternalPackage@@YA_NXZ; IsInternalPackage(void)
0x1801a0660  test    al, al
0x1801a0662  jz      short loc_1801A067C
0x1801a0664  call    ?spew@@YAHXZ; spew(void)
0x1801a0669  test    eax, eax
0x1801a066b  jz      short loc_1801A067C
0x1801a066d  lea     rdx, aUnableToFindTh; "Unable to find the SymbolServerPingWEx("...
0x1801a0674  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1801a0677  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a067c  mov     edx, 8; unsigned __int64
0x1801a0681  mov     ecx, 100h; unsigned __int64
0x1801a0686  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a068b  call    ?symsrvSetService@@YAXXZ; symsrvSetService(void)
0x1801a0690  call    ?symsrvSetPrompts@@YAXXZ; symsrvSetPrompts(void)
0x1801a0695  call    ?symsrvSetCallback@@YAHXZ; symsrvSetCallback(void)
0x1801a069a  xor     edx, edx; Val
0x1801a069c  lea     rcx, [rsp+258h+Buffer]; void *
0x1801a06a1  mov     r8d, 20Ah; Size
0x1801a06a7  call    memset_0
0x1801a06ac  mov     r8d, 105h; nSize
0x1801a06b2  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x1801a06b7  lea     rcx, aNtSymbolProxy; "_NT_SYMBOL_PROXY"
0x1801a06be  call    cs:__imp_GetEnvironmentVariableW
0x1801a06c4  test    eax, eax
0x1801a06c6  jz      short loc_1801A06D7
0x1801a06c8  lea     rdx, [rsp+258h+Buffer]; unsigned __int64
0x1801a06cd  mov     ecx, 40000h; unsigned __int64
0x1801a06d2  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a06d7  cmp     cs:word_1802B0BBA, bp
0x1801a06de  mov     ebx, 1
0x1801a06e3  jz      short loc_1801A06F8
0x1801a06e5  lea     rdx, word_1802B0BBA; unsigned __int64
0x1801a06ec  mov     ecx, 2000h; unsigned __int64
0x1801a06f1  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a06f6  jmp     short loc_1801A0715
0x1801a06f8  test    rdi, rdi
0x1801a06fb  jz      short loc_1801A0703
0x1801a06fd  mov     rcx, [rdi+30h]
0x1801a0701  jmp     short loc_1801A0706
0x1801a0703  mov     rcx, rbp; void *
0x1801a0706  mov     r8d, ebx; int
0x1801a0709  lea     rdx, dir; unsigned __int16 *
0x1801a0710  call    ?SetHomeDirectory@@YAPEAGPEAXPEBGH@Z; SetHomeDirectory(void *,ushort const *,int)
0x1801a0715  mov     eax, cs:dword_1802AF9CC
0x1801a071b  test    eax, eax
0x1801a071d  jns     short loc_1801A0762
0x1801a071f  lea     rdx, Value; "1"
0x1801a0726  lea     rcx, aSymsrvDbgout; "SYMSRV_DBGOUT"
0x1801a072d  call    cs:__imp_SetEnvironmentVariableA
0x1801a0733  test    eax, eax
0x1801a0735  jnz     short loc_1801A074F
0x1801a0737  call    ?spew@@YAHXZ; spew(void)
0x1801a073c  test    eax, eax
0x1801a073e  jz      short loc_1801A074F
0x1801a0740  lea     rdx, aUnableToSetThe; "Unable to set the SYMSRV_DBGOUT environ"...
0x1801a0747  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1801a074a  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a074f  mov     rdx, rbx; unsigned __int64
0x1801a0752  mov     ecx, 10000000h; unsigned __int64
0x1801a0757  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a075c  mov     eax, cs:dword_1802AF9CC
0x1801a0762  bt      eax, 1Dh
0x1801a0766  jnb     short loc_1801A077B
0x1801a0768  mov     rdx, rbx; unsigned __int64
0x1801a076b  mov     ecx, 8000000h; unsigned __int64
0x1801a0770  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a0775  mov     eax, cs:dword_1802AF9CC
0x1801a077b  bt      eax, 1Ch
0x1801a077f  jnb     short loc_1801A078E
0x1801a0781  mov     rdx, rbx; unsigned __int64
0x1801a0784  mov     ecx, 4000000h; unsigned __int64
0x1801a0789  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a078e  mov     rcx, cs:hLibModule; hModule
0x1801a0795  lea     rdx, aSymbolserveren; "SymbolServerEnableNegativeAuthCacheFeat"...
0x1801a079c  call    cs:__imp_GetProcAddress
0x1801a07a2  test    rax, rax
0x1801a07a5  jz      short loc_1801A07AE
0x1801a07a7  mov     ecx, esi
0x1801a07a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a07ae  xor     ecx, ecx; dwErrCode
0x1801a07b0  call    cs:__imp_SetLastError
0x1801a07b6  mov     rcx, r14; lpCriticalSection
0x1801a07b9  call    cs:__imp_LeaveCriticalSection
0x1801a07bf  mov     al, bl
0x1801a07c1  jmp     short loc_1801A0805
0x1801a07c3  call    cs:__imp_FreeLibrary
0x1801a07c9  mov     ecx, 7Eh ; '~'; dwErrCode
0x1801a07ce  mov     cs:hLibModule, 0FFFFFFFFFFFFFFFFh
0x1801a07d9  call    cs:__imp_SetLastError
0x1801a07df  mov     rcx, r14; lpCriticalSection
0x1801a07e2  call    cs:__imp_LeaveCriticalSection
0x1801a07e8  call    ?spew@@YAHXZ; spew(void)
0x1801a07ed  test    eax, eax
0x1801a07ef  jz      short loc_1801A0803
0x1801a07f1  mov     r8, rbx
0x1801a07f4  lea     rdx, aSLoadFailure; "%s load failure\n"
0x1801a07fb  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1801a07fe  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a0803  xor     al, al
0x1801a0805  mov     rcx, [rsp+258h+var_28]
0x1801a080d  xor     rcx, rsp; StackCookie
0x1801a0810  call    __security_check_cookie
0x1801a0815  lea     r11, [rsp+258h+var_18]
0x1801a081d  mov     rbx, [r11+30h]
0x1801a0821  mov     rbp, [r11+38h]
0x1801a0825  mov     rsp, r11
0x1801a0828  pop     r14
0x1801a082a  pop     rdi
0x1801a082b  pop     rsi
0x1801a082c  retn
```
