# CMVEngine::RunProvisioningCommands(ulong)

- ea: `0x18001eae0`
- end: `0x18001eee3`
- name: `?RunProvisioningCommands@CMVEngine@@UEAAJK@Z`
- size: `1027`
- prototype: `__int64 __fastcall(CMVEngine *this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800017f4`
- `0x1800098bc`
- `0x18000b5b4`
- `0x18000fcc4`
- `0x18001eae0`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001eb94`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ec7b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eccc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ed51`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ee58`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eead`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eb94`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ec7b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eccc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ed51`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ee58`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eead`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eb7a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ec61`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ecb2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ed37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ee3e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ee93`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eb7a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ec61`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ecb2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ed37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ee3e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ee93`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x18001ebd9`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x18001ebd9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001ed70`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001ed70`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001ec37`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001ec37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ece7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ece7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee88`

## string_xrefs

- `0x18001eb26`: `%windir%\system32\provlaunch.exe `

## pseudocode

```c
__int64 __fastcall CMVEngine::RunProvisioningCommands(CMVEngine *this, int a2)
{
  unsigned int v3; // r12d
  _QWORD *v4; // r14
  _QWORD *i; // rsi
  _QWORD *v7; // r15
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  const char *v10; // r9
  unsigned int LastError; // ebx
  char *hProcess; // rbx
  unsigned int v13; // ebx
  char *hThread; // rdi
  const char *v15; // r9
  unsigned int v16; // esi
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  void **v20; // rax
  DWORD v21; // [rsp+50h] [rbp-118h] BYREF
  DWORD ExitCode; // [rsp+54h] [rbp-114h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+58h] [rbp-110h] BYREF
  _QWORD *v24; // [rsp+68h] [rbp-100h] BYREF
  void **v25; // [rsp+70h] [rbp-F8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-F0h] BYREF
  _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-D8h] BYREF
  void *Src[3]; // [rsp+100h] [rbp-68h] BYREF
  unsigned __int64 v29; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = 0;
  v4 = (_QWORD *)*((_QWORD *)this + 12);
  for ( i = (_QWORD *)*v4; ; i = (_QWORD *)*i )
  {
    if ( i == v4 )
      return v3;
    v7 = i + 2;
    std::operator+<unsigned short>(Src, L"%windir%\\system32\\provlaunch.exe ");
    v8 = (const unsigned __int16 *)Src;
    if ( v29 >= 8 )
      v8 = (const unsigned __int16 *)Src[0];
    expanded_wstring::expanded_wstring((expanded_wstring *)lpCommandLine, v8);
    v9 = 0;
    while ( a2 != *((_DWORD *)qword_18004C1C0 + v9) )
    {
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= 3 )
      {
        operator delete[](lpCommandLine[0]);
        if ( v29 >= 8 )
          operator delete(Src[0]);
        return 0;
      }
    }
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    GetStartupInfoW(&StartupInfo);
    StartupInfo.dwFlags |= 1u;
    StartupInfo.wShowWindow = 0;
    if ( !CreateProcessW(0, lpCommandLine[0], 0, 0, 0, 0x8000020u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xDA2,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                    v10);
      operator delete[](lpCommandLine[0]);
      if ( v29 >= 8 )
        operator delete(Src[0]);
      return LastError;
    }
    hProcess = (char *)ProcessInformation.hProcess;
    if ( !ProcessInformation.hProcess )
    {
      v13 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xDA4,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
              v10);
      operator delete[](lpCommandLine[0]);
      if ( v29 >= 8 )
        operator delete(Src[0]);
      return v13;
    }
    hThread = (char *)ProcessInformation.hThread;
    if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) )
    {
      v16 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xDAA,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
              v15);
      if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hThread);
      if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hProcess);
      operator delete[](lpCommandLine[0]);
      if ( v29 >= 8 )
        operator delete(Src[0]);
      return v16;
    }
    ExitCode = 0;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      break;
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      v21 = GetLastError();
      if ( i[5] >= 8u )
        v7 = (_QWORD *)*v7;
      v24 = v7;
      v20 = Src;
      if ( v29 >= 8 )
        v20 = (void **)Src[0];
      v25 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)word_18004E92A,
        v18,
        v19,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v21);
    }
LABEL_47:
    if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hThread);
    if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hProcess);
    operator delete[](lpCommandLine[0]);
    if ( v29 >= 8 )
      operator delete(Src[0]);
  }
  if ( !ExitCode )
  {
    v3 = 0;
    goto LABEL_47;
  }
  if ( ExitCode - 3010 > 1 && ExitCode + 2147021886 > 1 )
  {
    v3 = -2147418113;
    goto LABEL_47;
  }
  if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hThread);
  if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hProcess);
  operator delete[](lpCommandLine[0]);
  if ( v29 >= 8 )
    operator delete(Src[0]);
  return 2147945410LL;
}

```

## disassembly

```asm
0x18001eae0  push    rbx
0x18001eae2  push    rsi
0x18001eae3  push    rdi
0x18001eae4  push    r12
0x18001eae6  push    r13
0x18001eae8  push    r14
0x18001eaea  push    r15
0x18001eaec  sub     rsp, 130h
0x18001eaf3  mov     rax, cs:__security_cookie
0x18001eafa  xor     rax, rsp
0x18001eafd  mov     [rsp+168h+var_48], rax
0x18001eb05  mov     r13d, edx
0x18001eb08  xor     r12d, r12d
0x18001eb0b  mov     r14, [rcx+60h]
0x18001eb0f  mov     rsi, [r14]
0x18001eb12  cmp     rsi, r14
0x18001eb15  jnz     short loc_18001EB1F
0x18001eb17  mov     eax, r12d
0x18001eb1a  jmp     loc_18001EEBF
0x18001eb1f  lea     r15, [rsi+10h]
0x18001eb23  mov     r8, r15
0x18001eb26  lea     rdx, aWindirSystem32; "%windir%\\system32\\provlaunch.exe "
0x18001eb2d  lea     rcx, [rsp+168h+Src]; Src
0x18001eb35  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18001eb3a  nop
0x18001eb3b  lea     rdx, [rsp+168h+Src]
0x18001eb43  cmp     [rsp+168h+var_50], 8
0x18001eb4c  cmovnb  rdx, [rsp+168h+Src]; unsigned __int16 *
0x18001eb55  lea     rcx, [rsp+168h+lpCommandLine]; this
0x18001eb5a  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x18001eb5f  xor     ecx, ecx
0x18001eb61  lea     rdx, qword_18004C1C0
0x18001eb68  cmp     r13d, [rdx+rcx*4]
0x18001eb6c  jz      short loc_18001EBA1
0x18001eb6e  inc     ecx
0x18001eb70  cmp     ecx, 3
0x18001eb73  jb      short loc_18001EB61
0x18001eb75  mov     rcx, [rsp+168h+lpCommandLine]
0x18001eb7a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001eb80  nop
0x18001eb81  cmp     [rsp+168h+var_50], 8
0x18001eb8a  jb      short loc_18001EB9A
0x18001eb8c  mov     rcx, [rsp+168h+Src]
0x18001eb94  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001eb9a  xor     eax, eax
0x18001eb9c  jmp     loc_18001EEBF
0x18001eba1  xorps   xmm0, xmm0
0x18001eba4  xor     eax, eax
0x18001eba6  movups  xmmword ptr [rsp+168h+ProcessInformation.hProcess], xmm0
0x18001ebab  mov     qword ptr [rsp+168h+ProcessInformation.dwProcessId], rax
0x18001ebb3  xor     edx, edx; Val
0x18001ebb5  lea     r8d, [rax+64h]; Size
0x18001ebb9  lea     rcx, [rsp+168h+StartupInfo+4]; void *
0x18001ebc1  call    memset_0
0x18001ebc6  mov     [rsp+168h+StartupInfo.cb], 68h ; 'h'
0x18001ebd1  lea     rcx, [rsp+168h+StartupInfo]; lpStartupInfo
0x18001ebd9  call    cs:__imp_GetStartupInfoW
0x18001ebdf  or      [rsp+168h+StartupInfo.dwFlags], 1
0x18001ebe7  xor     eax, eax
0x18001ebe9  mov     [rsp+168h+StartupInfo.wShowWindow], ax
0x18001ebf1  lea     rax, [rsp+168h+ProcessInformation]
0x18001ebf6  mov     [rsp+168h+lpProcessInformation], rax; lpProcessInformation
0x18001ebfb  lea     rax, [rsp+168h+StartupInfo]
0x18001ec03  mov     [rsp+168h+lpStartupInfo], rax; lpStartupInfo
0x18001ec08  mov     [rsp+168h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001ec11  mov     [rsp+168h+lpEnvironment], 0; lpEnvironment
0x18001ec1a  mov     [rsp+168h+dwCreationFlags], 8000020h; dwCreationFlags
0x18001ec22  mov     [rsp+168h+bInheritHandles], 0; bInheritHandles
0x18001ec2a  xor     r9d, r9d; lpThreadAttributes
0x18001ec2d  xor     r8d, r8d; lpProcessAttributes
0x18001ec30  mov     rdx, [rsp+168h+lpCommandLine]; lpCommandLine
0x18001ec35  xor     ecx, ecx; lpApplicationName
0x18001ec37  call    cs:__imp_CreateProcessW
0x18001ec3d  test    eax, eax
0x18001ec3f  jnz     short loc_18001EC88
0x18001ec41  mov     rcx, [rsp+168h]; this
0x18001ec49  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001ec50  mov     edx, 0DA2h; void *
0x18001ec55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ec5a  mov     ebx, eax
0x18001ec5c  mov     rcx, [rsp+168h+lpCommandLine]
0x18001ec61  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ec67  nop
0x18001ec68  cmp     [rsp+168h+var_50], 8
0x18001ec71  jb      short loc_18001EC81
0x18001ec73  mov     rcx, [rsp+168h+Src]
0x18001ec7b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ec81  mov     eax, ebx
0x18001ec83  jmp     loc_18001EEBF
0x18001ec88  mov     rbx, [rsp+168h+ProcessInformation.hProcess]
0x18001ec8d  test    rbx, rbx
0x18001ec90  jnz     short loc_18001ECD9
0x18001ec92  mov     rcx, [rsp+168h]; this
0x18001ec9a  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001eca1  mov     edx, 0DA4h; void *
0x18001eca6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ecab  mov     ebx, eax
0x18001ecad  mov     rcx, [rsp+168h+lpCommandLine]
0x18001ecb2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ecb8  nop
0x18001ecb9  cmp     [rsp+168h+var_50], 8
0x18001ecc2  jb      short loc_18001ECD2
0x18001ecc4  mov     rcx, [rsp+168h+Src]
0x18001eccc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ecd2  mov     eax, ebx
0x18001ecd4  jmp     loc_18001EEBF
0x18001ecd9  mov     rdi, [rsp+168h+ProcessInformation.hThread]
0x18001ece1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001ece4  mov     rcx, rbx; hHandle
0x18001ece7  call    cs:__imp_WaitForSingleObject
0x18001eced  test    eax, eax
0x18001ecef  jz      short loc_18001ED5E
0x18001ecf1  mov     rcx, [rsp+168h]; this
0x18001ecf9  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001ed00  mov     edx, 0DAAh; void *
0x18001ed05  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ed0a  mov     esi, eax
0x18001ed0c  lea     rcx, [rdi-1]
0x18001ed10  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ed14  ja      short loc_18001ED1F
0x18001ed16  mov     rcx, rdi; hObject
0x18001ed19  call    cs:__imp_CloseHandle
0x18001ed1f  lea     rcx, [rbx-1]
0x18001ed23  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ed27  ja      short loc_18001ED32
0x18001ed29  mov     rcx, rbx; hObject
0x18001ed2c  call    cs:__imp_CloseHandle
0x18001ed32  mov     rcx, [rsp+168h+lpCommandLine]
0x18001ed37  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ed3d  nop
0x18001ed3e  cmp     [rsp+168h+var_50], 8
0x18001ed47  jb      short loc_18001ED57
0x18001ed49  mov     rcx, [rsp+168h+Src]
0x18001ed51  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ed57  mov     eax, esi
0x18001ed59  jmp     loc_18001EEBF
0x18001ed5e  mov     [rsp+168h+ExitCode], 0
0x18001ed66  lea     rdx, [rsp+168h+ExitCode]; lpExitCode
0x18001ed6b  mov     rcx, [rsp+168h+ProcessInformation.hProcess]; hProcess
0x18001ed70  call    cs:__imp_GetExitCodeProcess
0x18001ed76  test    eax, eax
0x18001ed78  jnz     short loc_18001EDED
0x18001ed7a  mov     eax, cs:dword_18005A000
0x18001ed80  cmp     eax, 2
0x18001ed83  jbe     loc_18001EE68
0x18001ed89  call    cs:__imp_GetLastError
0x18001ed8f  mov     [rsp+168h+var_118], eax
0x18001ed93  cmp     qword ptr [r15+18h], 8
0x18001ed98  jb      short loc_18001ED9D
0x18001ed9a  mov     r15, [r15]
0x18001ed9d  mov     [rsp+168h+var_100], r15
0x18001eda2  lea     rax, [rsp+168h+Src]
0x18001edaa  cmp     [rsp+168h+var_50], 8
0x18001edb3  cmovnb  rax, [rsp+168h+Src]
0x18001edbc  mov     [rsp+168h+var_F8], rax
0x18001edc1  lea     rax, [rsp+168h+var_118]
0x18001edc6  mov     [rsp+168h+lpEnvironment], rax
0x18001edcb  lea     rax, [rsp+168h+var_100]
0x18001edd0  mov     qword ptr [rsp+168h+dwCreationFlags], rax
0x18001edd5  lea     rax, [rsp+168h+var_F8]
0x18001edda  mov     qword ptr [rsp+168h+bInheritHandles], rax
0x18001eddf  lea     rdx, word_18004E92A
0x18001ede6  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001edeb  jmp     short loc_18001EE68
0x18001eded  mov     ecx, [rsp+168h+ExitCode]
0x18001edf1  test    ecx, ecx
0x18001edf3  jz      short loc_18001EE65
0x18001edf5  lea     eax, [rcx-0BC2h]
0x18001edfb  cmp     eax, 1
0x18001edfe  jbe     short loc_18001EE13
0x18001ee00  lea     eax, [rcx+7FF8F43Eh]
0x18001ee06  cmp     eax, 1
0x18001ee09  jbe     short loc_18001EE13
0x18001ee0b  mov     r12d, 8000FFFFh
0x18001ee11  jmp     short loc_18001EE68
0x18001ee13  lea     rax, [rdi-1]
0x18001ee17  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ee1b  ja      short loc_18001EE26
0x18001ee1d  mov     rcx, rdi; hObject
0x18001ee20  call    cs:__imp_CloseHandle
0x18001ee26  lea     rax, [rbx-1]
0x18001ee2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ee2e  ja      short loc_18001EE39
0x18001ee30  mov     rcx, rbx; hObject
0x18001ee33  call    cs:__imp_CloseHandle
0x18001ee39  mov     rcx, [rsp+168h+lpCommandLine]
0x18001ee3e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ee44  nop
0x18001ee45  cmp     [rsp+168h+var_50], 8
0x18001ee4e  jb      short loc_18001EE5E
0x18001ee50  mov     rcx, [rsp+168h+Src]
0x18001ee58  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ee5e  mov     eax, 80070BC2h
0x18001ee63  jmp     short loc_18001EEBF
0x18001ee65  xor     r12d, r12d
0x18001ee68  lea     rax, [rdi-1]
0x18001ee6c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ee70  ja      short loc_18001EE7B
0x18001ee72  mov     rcx, rdi; hObject
0x18001ee75  call    cs:__imp_CloseHandle
0x18001ee7b  lea     rax, [rbx-1]
0x18001ee7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ee83  ja      short loc_18001EE8E
0x18001ee85  mov     rcx, rbx; hObject
0x18001ee88  call    cs:__imp_CloseHandle
0x18001ee8e  mov     rcx, [rsp+168h+lpCommandLine]
0x18001ee93  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ee99  nop
0x18001ee9a  cmp     [rsp+168h+var_50], 8
0x18001eea3  jb      short loc_18001EEB3
0x18001eea5  mov     rcx, [rsp+168h+Src]
0x18001eead  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001eeb3  mov     rsi, [rsi]
0x18001eeb6  jmp     loc_18001EB12
0x18001eebb  mov     eax, [rsp+168h+var_118]
0x18001eebf  mov     rcx, [rsp+168h+var_48]
0x18001eec7  xor     rcx, rsp; StackCookie
0x18001eeca  call    __security_check_cookie
0x18001eecf  add     rsp, 130h
0x18001eed6  pop     r15
0x18001eed8  pop     r14
0x18001eeda  pop     r13
0x18001eedc  pop     r12
0x18001eede  pop     rdi
0x18001eedf  pop     rsi
0x18001eee0  pop     rbx
0x18001eee1  retn
```
