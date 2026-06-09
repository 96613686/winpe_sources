# Utils::OS::StartChildProcess(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18001f6ec`
- end: `0x18001fa08`
- name: `?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000a6d4`

## callees

- `0x180002e50`
- `0x180003940`
- `0x180005fa4`
- `0x180007818`
- `0x1800109b4`
- `0x1800109d4`
- `0x180015648`
- `0x18001f6ec`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001f777`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001f875`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001f777`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001f875`
- `KERNEL32!CreateProcessW` at `0x18001f90a`
- `KERNEL32!CreateProcessW` at `0x18001f90a`
- `KERNEL32!CloseHandle` at `0x18001f950`
- `KERNEL32!CloseHandle` at `0x18001f97b`
- `KERNEL32!CloseHandle` at `0x18001f950`
- `KERNEL32!CloseHandle` at `0x18001f97b`

## pseudocode

```c
__int64 __fastcall Utils::OS::StartChildProcess(__int64 a1)
{
  const WCHAR *v2; // rsi
  DWORD v3; // eax
  DWORD v4; // ebx
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  _WORD *v7; // rdi
  unsigned __int64 i; // rcx
  WCHAR *v9; // rdx
  DWORD v10; // eax
  WCHAR *v11; // rdx
  const char *v12; // r9
  unsigned int LastError; // edi
  const char *v14; // r9
  const char *v15; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-F8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-C0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-A8h] BYREF
  LPWSTR lpDst[2]; // [rsp+E0h] [rbp-38h] BYREF
  unsigned __int64 v20; // [rsp+F0h] [rbp-28h]
  unsigned __int64 v21; // [rsp+F8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( *(_QWORD *)(a1 + 8) )
  {
    *(_OWORD *)lpDst = 0;
    v20 = 0;
    v21 = 7;
    LOWORD(lpDst[0]) = 0;
    v2 = *(const WCHAR **)a1;
    v3 = ExpandEnvironmentStringsW(*(LPCWSTR *)a1, 0, 0);
    v4 = v3;
    if ( v3 )
    {
      v5 = v20;
      if ( v3 > v20 )
      {
        v6 = v3 - v20;
        if ( v6 > v21 - v20 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpDst);
        }
        else
        {
          v20 = v3;
          v7 = (_WORD *)lpDst + v5;
          if ( v6 )
          {
            for ( i = v3 - v5; i; --i )
              *v7++ = 0;
          }
          *((_WORD *)lpDst + v3) = 0;
        }
      }
      else
      {
        v20 = v3;
        *((_WORD *)lpDst + v3) = 0;
      }
      v9 = (WCHAR *)lpDst;
      if ( v21 > 7 )
        v9 = lpDst[0];
      v10 = ExpandEnvironmentStringsW(v2, v9, v4);
      if ( v10 && v10 <= v4 )
      {
        memset_0(&StartupInfo.cb + 1, 0, 0x64u);
        StartupInfo.cb = 104;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        v11 = (WCHAR *)lpDst;
        if ( v21 > 7 )
          v11 = lpDst[0];
        if ( CreateProcessW(0, v11, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          if ( !CloseHandle(ProcessInformation.hProcess) )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x9B,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
              v14);
          if ( !CloseHandle(ProcessInformation.hThread) )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x9C,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
              v15);
          std::wstring::~wstring(lpDst);
          return 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x99,
                        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
                        v12);
          std::wstring::~wstring(lpDst);
          return LastError;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
          (const char *)0x8000FFFFLL,
          bInheritHandles);
        std::wstring::~wstring(lpDst);
        return 2147549183LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
        (const char *)0x8000FFFFLL,
        bInheritHandles);
      std::wstring::~wstring(lpDst);
      return 2147549183LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
      (const char *)0x80070057LL,
      bInheritHandles);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001f6ec  mov     [rsp+arg_8], rbx
0x18001f6f1  mov     [rsp+arg_10], rsi
0x18001f6f6  push    rdi
0x18001f6f7  sub     rsp, 110h
0x18001f6fe  mov     rax, cs:__security_cookie
0x18001f705  xor     rax, rsp
0x18001f708  mov     [rsp+118h+var_18], rax
0x18001f710  cmp     qword ptr [rcx+8], 0
0x18001f715  jnz     short loc_18001F73F
0x18001f717  mov     rcx, [rsp+118h]; this
0x18001f71f  mov     edi, 80070057h
0x18001f724  mov     r9d, edi; char *
0x18001f727  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18001f72e  mov     edx, 82h; void *
0x18001f733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f738  mov     eax, edi
0x18001f73a  jmp     loc_18001F9E2
0x18001f73f  xorps   xmm0, xmm0
0x18001f742  movups  xmmword ptr [rsp+118h+lpDst], xmm0
0x18001f74a  mov     [rsp+118h+var_28], 0
0x18001f756  mov     [rsp+118h+var_20], 7
0x18001f762  xor     eax, eax
0x18001f764  mov     word ptr [rsp+118h+lpDst], ax
0x18001f76c  mov     rsi, [rcx]
0x18001f76f  xor     r8d, r8d; nSize
0x18001f772  xor     edx, edx; lpDst
0x18001f774  mov     rcx, rsi; lpSrc
0x18001f777  call    cs:__imp_ExpandEnvironmentStringsW
0x18001f77d  mov     ebx, eax
0x18001f77f  test    eax, eax
0x18001f781  jnz     short loc_18001F7B9
0x18001f783  mov     rcx, [rsp+118h]; this
0x18001f78b  mov     edi, 8000FFFFh
0x18001f790  mov     r9d, edi; char *
0x18001f793  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18001f79a  mov     edx, 86h; void *
0x18001f79f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7a4  nop
0x18001f7a5  lea     rcx, [rsp+118h+lpDst]
0x18001f7ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f7b2  mov     eax, edi
0x18001f7b4  jmp     loc_18001F9E2
0x18001f7b9  mov     rcx, [rsp+118h+var_28]
0x18001f7c1  cmp     rbx, rcx
0x18001f7c4  ja      short loc_18001F7F0
0x18001f7c6  mov     [rsp+118h+var_28], rbx
0x18001f7ce  lea     rcx, [rsp+118h+lpDst]
0x18001f7d6  cmp     [rsp+118h+var_20], 7
0x18001f7df  cmova   rcx, [rsp+118h+lpDst]
0x18001f7e8  xor     eax, eax
0x18001f7ea  mov     [rcx+rbx*2], ax
0x18001f7ee  jmp     short loc_18001F855
0x18001f7f0  mov     rdx, rbx
0x18001f7f3  sub     rdx, rcx
0x18001f7f6  mov     rax, [rsp+118h+var_20]
0x18001f7fe  sub     rax, rcx
0x18001f801  cmp     rdx, rax
0x18001f804  ja      short loc_18001F845
0x18001f806  mov     [rsp+118h+var_28], rbx
0x18001f80e  lea     r9, [rsp+118h+lpDst]
0x18001f816  cmp     [rsp+118h+var_20], 7
0x18001f81f  cmova   r9, [rsp+118h+lpDst]
0x18001f828  lea     rdi, [r9+rcx*2]
0x18001f82c  test    rdx, rdx
0x18001f82f  jz      short loc_18001F83C
0x18001f831  xor     eax, eax
0x18001f833  movzx   eax, ax
0x18001f836  mov     rcx, rdx
0x18001f839  rep stosw
0x18001f83c  xor     eax, eax
0x18001f83e  mov     [r9+rbx*2], ax
0x18001f843  jmp     short loc_18001F855
0x18001f845  mov     r9, rdx
0x18001f848  lea     rcx, [rsp+118h+lpDst]; Src
0x18001f850  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18001f855  lea     rdx, [rsp+118h+lpDst]
0x18001f85d  cmp     [rsp+118h+var_20], 7
0x18001f866  cmova   rdx, [rsp+118h+lpDst]; lpDst
0x18001f86f  mov     r8d, ebx; nSize
0x18001f872  mov     rcx, rsi; lpSrc
0x18001f875  call    cs:__imp_ExpandEnvironmentStringsW
0x18001f87b  test    eax, eax
0x18001f87d  jz      loc_18001F9AB
0x18001f883  cmp     eax, ebx
0x18001f885  ja      loc_18001F9AB
0x18001f88b  xor     edx, edx; Val
0x18001f88d  lea     r8d, [rdx+64h]; Size
0x18001f891  lea     rcx, [rsp+118h+StartupInfo+4]; void *
0x18001f896  call    memset_0
0x18001f89b  mov     [rsp+118h+StartupInfo.cb], 68h ; 'h'
0x18001f8a3  xorps   xmm0, xmm0
0x18001f8a6  xor     eax, eax
0x18001f8a8  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x18001f8ad  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x18001f8b2  lea     rdx, [rsp+118h+lpDst]
0x18001f8ba  cmp     [rsp+118h+var_20], 7
0x18001f8c3  cmova   rdx, [rsp+118h+lpDst]; lpCommandLine
0x18001f8cc  lea     rax, [rsp+118h+ProcessInformation]
0x18001f8d1  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x18001f8d6  lea     rax, [rsp+118h+StartupInfo]
0x18001f8db  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x18001f8e0  mov     [rsp+118h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001f8e9  mov     [rsp+118h+lpEnvironment], 0; lpEnvironment
0x18001f8f2  mov     [rsp+118h+dwCreationFlags], 0; dwCreationFlags
0x18001f8fa  mov     [rsp+118h+bInheritHandles], 0; bInheritHandles
0x18001f902  xor     r9d, r9d; lpThreadAttributes
0x18001f905  xor     r8d, r8d; lpProcessAttributes
0x18001f908  xor     ecx, ecx; lpApplicationName
0x18001f90a  call    cs:__imp_CreateProcessW
0x18001f910  test    eax, eax
0x18001f912  jnz     short loc_18001F943
0x18001f914  mov     rcx, [rsp+118h]; this
0x18001f91c  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18001f923  mov     edx, 99h; void *
0x18001f928  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f92d  mov     edi, eax
0x18001f92f  lea     rcx, [rsp+118h+lpDst]
0x18001f937  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f93c  mov     eax, edi
0x18001f93e  jmp     loc_18001F9E2
0x18001f943  mov     rdi, [rsp+118h]
0x18001f94b  mov     rcx, [rsp+118h+ProcessInformation.hProcess]; hObject
0x18001f950  call    cs:__imp_CloseHandle
0x18001f956  test    eax, eax
0x18001f958  jnz     short loc_18001F96E
0x18001f95a  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18001f961  mov     edx, 9Bh; void *
0x18001f966  mov     rcx, rdi; this
0x18001f969  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001f96e  mov     rdi, [rsp+118h]
0x18001f976  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x18001f97b  call    cs:__imp_CloseHandle
0x18001f981  test    eax, eax
0x18001f983  jnz     short loc_18001F99A
0x18001f985  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18001f98c  mov     edx, 9Ch; void *
0x18001f991  mov     rcx, rdi; this
0x18001f994  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001f999  nop
0x18001f99a  lea     rcx, [rsp+118h+lpDst]
0x18001f9a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f9a7  xor     eax, eax
0x18001f9a9  jmp     short loc_18001F9E2
0x18001f9ab  mov     rcx, [rsp+118h]; this
0x18001f9b3  mov     edi, 8000FFFFh
0x18001f9b8  mov     r9d, edi; char *
0x18001f9bb  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18001f9c2  mov     edx, 8Ah; void *
0x18001f9c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9cc  nop
0x18001f9cd  lea     rcx, [rsp+118h+lpDst]
0x18001f9d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f9da  mov     eax, edi
0x18001f9dc  jmp     short loc_18001F9E2
0x18001f9de  mov     eax, [rsp+118h+var_C8]
0x18001f9e2  mov     rcx, [rsp+118h+var_18]
0x18001f9ea  xor     rcx, rsp; StackCookie
0x18001f9ed  call    __security_check_cookie
0x18001f9f2  lea     r11, [rsp+118h+var_8]
0x18001f9fa  mov     rbx, [r11+18h]
0x18001f9fe  mov     rsi, [r11+20h]
0x18001fa02  mov     rsp, r11
0x18001fa05  pop     rdi
0x18001fa06  retn
```
