# Utils::OS::StartChildProcess(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x180020c20`
- end: `0x180020f54`
- name: `?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000a7e4`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x180005e94`
- `0x180007858`
- `0x180011384`
- `0x1800113a4`
- `0x18001632c`
- `0x180020c20`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180020cae`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180020db2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180020cae`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180020db2`
- `KERNEL32!CreateProcessW` at `0x180020e3f`
- `KERNEL32!CreateProcessW` at `0x180020e3f`
- `KERNEL32!CloseHandle` at `0x180020e8b`
- `KERNEL32!CloseHandle` at `0x180020ebc`
- `KERNEL32!CloseHandle` at `0x180020e8b`
- `KERNEL32!CloseHandle` at `0x180020ebc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Utils::OS::StartChildProcess(__int64 a1)
{
  const WCHAR *v2; // rsi
  DWORD v3; // eax
  DWORD v4; // ebx
  unsigned __int64 v5; // r8
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
0x180020c20  mov     [rsp+arg_8], rbx
0x180020c25  mov     [rsp+arg_10], rsi
0x180020c2a  mov     [rsp+arg_18], rdi
0x180020c2f  push    r14
0x180020c31  sub     rsp, 110h
0x180020c38  mov     rax, cs:__security_cookie
0x180020c3f  xor     rax, rsp
0x180020c42  mov     [rsp+118h+var_18], rax
0x180020c4a  xor     r14d, r14d
0x180020c4d  cmp     [rcx+8], r14
0x180020c51  jnz     short loc_180020C7B
0x180020c53  mov     rcx, [rsp+118h]; this
0x180020c5b  mov     edi, 80070057h
0x180020c60  mov     r9d, edi; char *
0x180020c63  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x180020c6a  mov     edx, 82h; void *
0x180020c6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c74  mov     eax, edi
0x180020c76  jmp     loc_180020F29
0x180020c7b  xorps   xmm0, xmm0
0x180020c7e  movups  xmmword ptr [rsp+118h+lpDst], xmm0
0x180020c86  mov     [rsp+118h+var_28], r14
0x180020c8e  mov     [rsp+118h+var_20], 7
0x180020c9a  mov     word ptr [rsp+118h+lpDst], r14w
0x180020ca3  mov     rsi, [rcx]
0x180020ca6  xor     r8d, r8d; nSize
0x180020ca9  xor     edx, edx; lpDst
0x180020cab  mov     rcx, rsi; lpSrc
0x180020cae  call    cs:__imp_ExpandEnvironmentStringsW
0x180020cb5  nop     dword ptr [rax+rax+00h]
0x180020cba  mov     ebx, eax
0x180020cbc  test    eax, eax
0x180020cbe  jnz     short loc_180020CF6
0x180020cc0  mov     rcx, [rsp+118h]; this
0x180020cc8  mov     edi, 8000FFFFh
0x180020ccd  mov     r9d, edi; char *
0x180020cd0  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x180020cd7  mov     edx, 86h; void *
0x180020cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ce1  nop
0x180020ce2  lea     rcx, [rsp+118h+lpDst]
0x180020cea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020cef  mov     eax, edi
0x180020cf1  jmp     loc_180020F29
0x180020cf6  mov     r8, [rsp+118h+var_28]
0x180020cfe  cmp     rbx, r8
0x180020d01  ja      short loc_180020D2C
0x180020d03  lea     rax, [rsp+118h+lpDst]
0x180020d0b  cmp     [rsp+118h+var_20], 7
0x180020d14  cmova   rax, [rsp+118h+lpDst]
0x180020d1d  mov     [rsp+118h+var_28], rbx
0x180020d25  mov     [rax+rbx*2], r14w
0x180020d2a  jmp     short loc_180020D92
0x180020d2c  mov     rdx, rbx
0x180020d2f  sub     rdx, r8
0x180020d32  mov     rax, [rsp+118h+var_20]
0x180020d3a  sub     rax, r8
0x180020d3d  cmp     rdx, rax
0x180020d40  ja      short loc_180020D82
0x180020d42  mov     [rsp+118h+var_28], rbx
0x180020d4a  lea     r9, [rsp+118h+lpDst]
0x180020d52  cmp     [rsp+118h+var_20], 7
0x180020d5b  cmova   r9, [rsp+118h+lpDst]
0x180020d64  lea     rdi, [r9+r8*2]
0x180020d68  test    rdx, rdx
0x180020d6b  jz      short loc_180020D77
0x180020d6d  movzx   eax, r14w
0x180020d71  mov     rcx, rdx
0x180020d74  rep stosw
0x180020d77  lea     rax, [r8+rdx]
0x180020d7b  mov     [r9+rax*2], r14w
0x180020d80  jmp     short loc_180020D92
0x180020d82  mov     r9, rdx
0x180020d85  lea     rcx, [rsp+118h+lpDst]; Src
0x180020d8d  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180020d92  lea     rdx, [rsp+118h+lpDst]
0x180020d9a  cmp     [rsp+118h+var_20], 7
0x180020da3  cmova   rdx, [rsp+118h+lpDst]; lpDst
0x180020dac  mov     r8d, ebx; nSize
0x180020daf  mov     rcx, rsi; lpSrc
0x180020db2  call    cs:__imp_ExpandEnvironmentStringsW
0x180020db9  nop     dword ptr [rax+rax+00h]
0x180020dbe  test    eax, eax
0x180020dc0  jz      loc_180020EF2
0x180020dc6  cmp     eax, ebx
0x180020dc8  ja      loc_180020EF2
0x180020dce  xor     edx, edx; Val
0x180020dd0  lea     r8d, [rdx+64h]; Size
0x180020dd4  lea     rcx, [rsp+118h+StartupInfo+4]; void *
0x180020dd9  call    memset_0
0x180020dde  mov     [rsp+118h+StartupInfo.cb], 68h ; 'h'
0x180020de6  xorps   xmm0, xmm0
0x180020de9  xor     eax, eax
0x180020deb  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x180020df0  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x180020df5  lea     rdx, [rsp+118h+lpDst]
0x180020dfd  cmp     [rsp+118h+var_20], 7
0x180020e06  cmova   rdx, [rsp+118h+lpDst]; lpCommandLine
0x180020e0f  lea     rax, [rsp+118h+ProcessInformation]
0x180020e14  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x180020e19  lea     rax, [rsp+118h+StartupInfo]
0x180020e1e  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x180020e23  mov     [rsp+118h+lpCurrentDirectory], r14; lpCurrentDirectory
0x180020e28  mov     [rsp+118h+lpEnvironment], r14; lpEnvironment
0x180020e2d  mov     [rsp+118h+dwCreationFlags], r14d; dwCreationFlags
0x180020e32  mov     [rsp+118h+bInheritHandles], r14d; bInheritHandles
0x180020e37  xor     r9d, r9d; lpThreadAttributes
0x180020e3a  xor     r8d, r8d; lpProcessAttributes
0x180020e3d  xor     ecx, ecx; lpApplicationName
0x180020e3f  call    cs:__imp_CreateProcessW
0x180020e46  nop     dword ptr [rax+rax+00h]
0x180020e4b  test    eax, eax
0x180020e4d  jnz     short loc_180020E7E
0x180020e4f  mov     rcx, [rsp+118h]; this
0x180020e57  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x180020e5e  mov     edx, 99h; void *
0x180020e63  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020e68  mov     edi, eax
0x180020e6a  lea     rcx, [rsp+118h+lpDst]
0x180020e72  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020e77  mov     eax, edi
0x180020e79  jmp     loc_180020F29
0x180020e7e  mov     rdi, [rsp+118h]
0x180020e86  mov     rcx, [rsp+118h+ProcessInformation.hProcess]; hObject
0x180020e8b  call    cs:__imp_CloseHandle
0x180020e92  nop     dword ptr [rax+rax+00h]
0x180020e97  test    eax, eax
0x180020e99  jnz     short loc_180020EAF
0x180020e9b  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x180020ea2  mov     edx, 9Bh; void *
0x180020ea7  mov     rcx, rdi; this
0x180020eaa  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180020eaf  mov     rdi, [rsp+118h]
0x180020eb7  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x180020ebc  call    cs:__imp_CloseHandle
0x180020ec3  nop     dword ptr [rax+rax+00h]
0x180020ec8  test    eax, eax
0x180020eca  jnz     short loc_180020EE1
0x180020ecc  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x180020ed3  mov     edx, 9Ch; void *
0x180020ed8  mov     rcx, rdi; this
0x180020edb  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180020ee0  nop
0x180020ee1  lea     rcx, [rsp+118h+lpDst]
0x180020ee9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020eee  xor     eax, eax
0x180020ef0  jmp     short loc_180020F29
0x180020ef2  mov     rcx, [rsp+118h]; this
0x180020efa  mov     edi, 8000FFFFh
0x180020eff  mov     r9d, edi; char *
0x180020f02  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x180020f09  mov     edx, 8Ah; void *
0x180020f0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f13  nop
0x180020f14  lea     rcx, [rsp+118h+lpDst]
0x180020f1c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020f21  mov     eax, edi
0x180020f23  jmp     short loc_180020F29
0x180020f25  mov     eax, [rsp+118h+var_C8]
0x180020f29  mov     rcx, [rsp+118h+var_18]
0x180020f31  xor     rcx, rsp; StackCookie
0x180020f34  call    __security_check_cookie
0x180020f39  lea     r11, [rsp+118h+var_8]
0x180020f41  mov     rbx, [r11+18h]
0x180020f45  mov     rsi, [r11+20h]
0x180020f49  mov     rdi, [r11+28h]
0x180020f4d  mov     rsp, r11
0x180020f50  pop     r14
0x180020f52  retn
```
