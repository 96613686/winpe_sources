# OProcess::StartCore(bool,OHandle const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool,bool)

- ea: `0x180024d80`
- end: `0x180024fdb`
- name: `?StartCore@OProcess@@AEAAK_NAEBVOHandle@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@200@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024c10`

## callees

- `0x180003980`
- `0x180006e00`
- `0x18000adf0`
- `0x18000b6e0`
- `0x18001acdc`
- `0x180024d80`
- `0x180027798`
- `0x18003e690`
- `0x1800409e0`
- `0x180135e08`
- `0x180135f78`
- `0x18013670c`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180024eba`
- `KERNEL32!GetCurrentProcess` at `0x180024eba`
- `KERNEL32!GetLastError` at `0x180024f56`
- `KERNEL32!GetLastError` at `0x180024f5c`
- `KERNEL32!GetLastError` at `0x180024f56`
- `KERNEL32!GetLastError` at `0x180024f5c`
- `KERNEL32!CloseHandle` at `0x180024fa3`
- `KERNEL32!CloseHandle` at `0x180024fa3`
- `KERNEL32!CreateProcessW` at `0x180024f4c`
- `KERNEL32!CreateProcessW` at `0x180024f4c`
- `KERNEL32!GetPriorityClass` at `0x180024ec3`
- `KERNEL32!GetPriorityClass` at `0x180024ec3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OProcess::StartCore(__int64 a1, __int64 a2, __int64 a3, const WCHAR *a4, __int64 a5)
{
  _QWORD *v7; // rdi
  HANDLE CurrentProcess; // rax
  DWORD dwCreationFlags; // r8d
  const WCHAR *lpCurrentDirectory; // rcx
  WCHAR *v11; // rdx
  const WCHAR *v12; // rax
  DWORD LastError; // eax
  int v14; // r8d
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v20; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v21; // [rsp+F8h] [rbp-8h]
  _OWORD v22[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v23[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+140h] [rbp+40h] BYREF

  if ( *(_QWORD *)(a1 + 8) != -1 && !OProcess::get_HasExited((OProcess *)a1) )
  {
    OException::OException(pExceptionObject);
    throw (OException *)pExceptionObject;
  }
  *(_OWORD *)lpCommandLine = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(lpCommandLine[0]) = 0;
  v7 = (_QWORD *)(a5 + 16);
  if ( !*((_QWORD *)a4 + 2) )
    goto LABEL_27;
  if ( !*v7 )
    goto LABEL_10;
  if ( *(_WORD *)std::wstring::operator[](a5, 0) == 32 )
  {
LABEL_27:
    if ( *v7 )
      std::wstring::operator=(lpCommandLine, a5);
  }
  else
  {
    v22[0] = 0;
    v22[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v22[0]) = 0;
    OPath::GetFileName(a4, v22);
    OString::Format<std::wstring,std::wstring>(v23, L"%s %s", v22, a5);
    std::wstring::operator=(lpCommandLine);
    std::wstring::~wstring(v23);
    std::wstring::~wstring(v22);
  }
LABEL_10:
  memset(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  CurrentProcess = GetCurrentProcess();
  dwCreationFlags = GetPriorityClass(CurrentProcess) | 0x8000000;
  if ( *(_QWORD *)(a1 + 40) )
  {
    lpCurrentDirectory = (const WCHAR *)(a1 + 24);
    if ( *(_QWORD *)(a1 + 48) > 7u )
      lpCurrentDirectory = *(const WCHAR **)lpCurrentDirectory;
  }
  else
  {
    lpCurrentDirectory = 0;
  }
  if ( v20 )
  {
    v11 = (WCHAR *)lpCommandLine;
    if ( v21 > 7 )
      v11 = lpCommandLine[0];
  }
  else
  {
    v11 = 0;
  }
  if ( *((_QWORD *)a4 + 2) )
  {
    v12 = a4;
    if ( *((_QWORD *)a4 + 3) > 7u )
      v12 = *(const WCHAR **)a4;
  }
  else
  {
    v12 = 0;
  }
  if ( !CreateProcessW(v12, v11, 0, 0, 0, dwCreationFlags, 0, lpCurrentDirectory, &StartupInfo, &ProcessInformation) )
  {
    GetLastError();
    LastError = GetLastError();
    OException::OException((unsigned int)pExceptionObject, 808464432, v14, LastError, bInheritHandles, (__int64)a4, a5);
    throw (OException *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 8) = ProcessInformation.hProcess;
  *(_DWORD *)(a1 + 16) = 259;
  CloseHandle(ProcessInformation.hThread);
  std::wstring::~wstring(lpCommandLine);
  return 0;
}

```

## disassembly

```asm
0x180024d80  mov     [rsp-8+arg_8], rbx
0x180024d85  push    rbp
0x180024d86  push    rsi
0x180024d87  push    rdi
0x180024d88  push    r14
0x180024d8a  push    r15
0x180024d8c  lea     rbp, [rsp-3E0h]
0x180024d94  sub     rsp, 4E0h
0x180024d9b  mov     rax, cs:__security_cookie
0x180024da2  xor     rax, rsp
0x180024da5  mov     [rbp+400h+var_30], rax
0x180024dac  mov     rbx, r9
0x180024daf  mov     rsi, rcx
0x180024db2  mov     r14, [rbp+400h+arg_20]
0x180024db9  xor     r15d, r15d
0x180024dbc  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180024dc1  jz      short loc_180024DE6
0x180024dc3  call    ?get_HasExited@OProcess@@QEAA_NXZ; OProcess::get_HasExited(void)
0x180024dc8  test    al, al
0x180024dca  jnz     short loc_180024DE6
0x180024dcc  lea     rcx, [rbp+400h+pExceptionObject]
0x180024dd0  call    ??$?0$0EM@@OException@@QEAA@W4exceptionType@et@@AEAY0EM@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[76])
0x180024dd5  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180024ddc  lea     rcx, [rbp+400h+pExceptionObject]; pExceptionObject
0x180024de0  call    _CxxThrowException
0x180024de6  xorps   xmm0, xmm0
0x180024de9  movups  xmmword ptr [rbp+400h+lpCommandLine], xmm0
0x180024ded  mov     [rbp+400h+var_410], r15
0x180024df1  mov     [rbp+400h+var_408], 7
0x180024df9  mov     word ptr [rbp+400h+lpCommandLine], r15w
0x180024dfe  lea     rdi, [r14+10h]
0x180024e02  cmp     [rbx+10h], r15
0x180024e06  jz      short loc_180024E82
0x180024e08  cmp     [rdi], r15
0x180024e0b  jz      loc_180024E93
0x180024e11  xor     edx, edx
0x180024e13  mov     rcx, r14
0x180024e16  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAAEB_W_K@Z; std::wstring::operator[](unsigned __int64)
0x180024e1b  mov     ecx, 20h ; ' '
0x180024e20  cmp     cx, [rax]
0x180024e23  jz      short loc_180024E82
0x180024e25  xorps   xmm0, xmm0
0x180024e28  movups  [rbp+400h+var_400], xmm0
0x180024e2c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180024e34  movdqu  [rbp+400h+var_3F0], xmm1
0x180024e39  mov     word ptr [rbp+400h+var_400], r15w
0x180024e3e  lea     rdx, [rbp+400h+var_400]
0x180024e42  mov     rcx, rbx
0x180024e45  call    ?GetFileName@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; OPath::GetFileName(std::wstring const &,std::wstring &)
0x180024e4a  mov     r9, r14
0x180024e4d  lea     r8, [rbp+400h+var_400]
0x180024e51  lea     rdx, aSS_2; "%s %s"
0x180024e58  lea     rcx, [rbp+400h+var_3E0]
0x180024e5c  call    ??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@OString@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBV12@1@Z; OString::Format<std::wstring,std::wstring>(wchar_t const *,std::wstring const &,std::wstring const &)
0x180024e61  mov     rdx, rax
0x180024e64  lea     rcx, [rbp+400h+lpCommandLine]
0x180024e68  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180024e6d  lea     rcx, [rbp+400h+var_3E0]; void *
0x180024e71  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024e76  nop
0x180024e77  lea     rcx, [rbp+400h+var_400]; void *
0x180024e7b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024e80  jmp     short loc_180024E93
0x180024e82  cmp     [rdi], r15
0x180024e85  jz      short loc_180024E93
0x180024e87  mov     rdx, r14
0x180024e8a  lea     rcx, [rbp+400h+lpCommandLine]
0x180024e8e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180024e93  xor     edx, edx; Val
0x180024e95  lea     r8d, [rdx+64h]; Size
0x180024e99  lea     rcx, [rsp+500h+StartupInfo+4]; void *
0x180024e9e  call    memset
0x180024ea3  mov     [rsp+500h+StartupInfo.cb], 68h ; 'h'
0x180024eab  xorps   xmm0, xmm0
0x180024eae  xor     eax, eax
0x180024eb0  movups  xmmword ptr [rsp+500h+ProcessInformation.hProcess], xmm0
0x180024eb5  mov     qword ptr [rsp+500h+ProcessInformation.dwProcessId], rax
0x180024eba  call    cs:__imp_GetCurrentProcess
0x180024ec0  mov     rcx, rax; hProcess
0x180024ec3  call    cs:__imp_GetPriorityClass
0x180024ec9  mov     r8d, eax
0x180024ecc  bts     r8d, 1Bh
0x180024ed1  cmp     [rsi+28h], r15
0x180024ed5  jnz     short loc_180024EDC
0x180024ed7  mov     rcx, r15
0x180024eda  jmp     short loc_180024EEA
0x180024edc  lea     rcx, [rsi+18h]
0x180024ee0  cmp     qword ptr [rcx+18h], 7
0x180024ee5  jbe     short loc_180024EEA
0x180024ee7  mov     rcx, [rcx]
0x180024eea  cmp     [rbp+400h+var_410], r15
0x180024eee  jnz     short loc_180024EF5
0x180024ef0  mov     rdx, r15
0x180024ef3  jmp     short loc_180024F03
0x180024ef5  lea     rdx, [rbp+400h+lpCommandLine]
0x180024ef9  cmp     [rbp+400h+var_408], 7
0x180024efe  cmova   rdx, [rbp+400h+lpCommandLine]; lpCommandLine
0x180024f03  cmp     [rbx+10h], r15
0x180024f07  jnz     short loc_180024F0E
0x180024f09  mov     rax, r15
0x180024f0c  jmp     short loc_180024F1B
0x180024f0e  mov     rax, rbx
0x180024f11  cmp     qword ptr [rbx+18h], 7
0x180024f16  jbe     short loc_180024F1B
0x180024f18  mov     rax, [rbx]
0x180024f1b  lea     r9, [rsp+500h+ProcessInformation]
0x180024f20  mov     [rsp+500h+lpProcessInformation], r9; lpProcessInformation
0x180024f25  lea     r9, [rsp+500h+StartupInfo]
0x180024f2a  mov     [rsp+500h+lpStartupInfo], r9; lpStartupInfo
0x180024f2f  mov     [rsp+500h+lpCurrentDirectory], rcx; lpCurrentDirectory
0x180024f34  mov     [rsp+500h+lpEnvironment], r15; lpEnvironment
0x180024f39  mov     [rsp+500h+dwCreationFlags], r8d; dwCreationFlags
0x180024f3e  mov     [rsp+500h+bInheritHandles], r15d; bInheritHandles
0x180024f43  xor     r9d, r9d; lpThreadAttributes
0x180024f46  xor     r8d, r8d; lpProcessAttributes
0x180024f49  mov     rcx, rax; lpApplicationName
0x180024f4c  call    cs:__imp_CreateProcessW
0x180024f52  test    eax, eax
0x180024f54  jnz     short loc_180024F8E
0x180024f56  call    cs:__imp_GetLastError
0x180024f5c  call    cs:__imp_GetLastError
0x180024f62  mov     [rsp+500h+lpEnvironment], r14
0x180024f67  mov     qword ptr [rsp+500h+dwCreationFlags], rbx
0x180024f6c  mov     r9d, eax
0x180024f6f  mov     edx, 30303030h
0x180024f74  lea     rcx, [rbp+400h+pExceptionObject]
0x180024f78  call    ??$?0$0DD@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@@OException@@QEAA@Utag_t@0@W4exceptionType@et@@IAEAY0DD@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@3@Z; OException::OException(OException::tag_t,et::exceptionType,uint,wchar_t const (&)[51],std::wstring const &,std::wstring const &)
0x180024f7d  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180024f84  lea     rcx, [rbp+400h+pExceptionObject]; pExceptionObject
0x180024f88  call    _CxxThrowException
0x180024f8e  mov     rax, [rsp+500h+ProcessInformation.hProcess]
0x180024f93  mov     [rsi+8], rax
0x180024f97  mov     dword ptr [rsi+10h], 103h
0x180024f9e  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x180024fa3  call    cs:__imp_CloseHandle
0x180024fa9  nop
0x180024faa  lea     rcx, [rbp+400h+lpCommandLine]; void *
0x180024fae  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024fb3  xor     eax, eax
0x180024fb5  mov     rcx, [rbp+400h+var_30]
0x180024fbc  xor     rcx, rsp; StackCookie
0x180024fbf  call    __security_check_cookie
0x180024fc4  mov     rbx, [rsp+500h+arg_8]
0x180024fcc  add     rsp, 4E0h
0x180024fd3  pop     r15
0x180024fd5  pop     r14
0x180024fd7  pop     rdi
0x180024fd8  pop     rsi
0x180024fd9  pop     rbp
0x180024fda  retn
```
