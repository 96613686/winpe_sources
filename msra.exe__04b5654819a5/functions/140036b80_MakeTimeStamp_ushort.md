# MakeTimeStamp(ushort * *)

- ea: `0x140036b80`
- end: `0x140036dbf`
- name: `?MakeTimeStamp@@YAJPEAPEAG@Z`
- size: `575`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000a350`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140034ce4`
- `0x1400365f8`
- `0x140036b80`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x140036bf2`
- `KERNEL32!GetLocalTime` at `0x140036bf2`
- `OLEAUT32!__imp_SysAllocString` at `0x140036c43`
- `OLEAUT32!__imp_SysAllocString` at `0x140036d2c`
- `OLEAUT32!__imp_SysAllocString` at `0x140036c43`
- `OLEAUT32!__imp_SysAllocString` at `0x140036d2c`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d12`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d89`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d12`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d89`

## string_xrefs

- `0x140036c71`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x140036c9f`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x140036d5a`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall MakeTimeStamp(unsigned __int16 **a1)
{
  signed int v2; // eax
  CEventLogger *v3; // rcx
  unsigned int v4; // ebx
  CEventLogger *v5; // rcx
  CEventLogger *v6; // rcx
  OLECHAR *v7; // rdi
  signed int DateAsBSTR; // eax
  CEventLogger *v9; // rcx
  OLECHAR *v10; // rsi
  signed int v11; // eax
  CEventLogger *v12; // rcx
  unsigned __int16 *v13; // rax
  CEventLogger *v14; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR psz[1024]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR v19[1024]; // [rsp+850h] [rbp+750h] BYREF

  bstrString = 0;
  memset_0(v19, 0, sizeof(v19));
  memset_0(psz, 0, sizeof(psz));
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v2 = StringCchPrintfW(psz, 0x400u, L"%02d%02d%02d", SystemTime.wHour, SystemTime.wMinute, SystemTime.wSecond);
  v4 = v2;
  if ( v2 < 0 )
  {
    CEventLogger::LogError(
      v3,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x1D3u,
      L"GetTimeAsBSTR",
      v2);
LABEL_5:
    CEventLogger::LogError(
      v5,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x22Au,
      L"MakeTimeStamp",
      v4);
    return v4;
  }
  v7 = SysAllocString(psz);
  if ( !v7 )
  {
    v4 = -2147024882;
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x1D7u,
      L"GetTimeAsBSTR",
      0x8007000E);
    goto LABEL_5;
  }
  DateAsBSTR = GetDateAsBSTR(&bstrString);
  v10 = bstrString;
  v4 = DateAsBSTR;
  if ( DateAsBSTR >= 0 )
  {
    v11 = StringCchPrintfW(v19, 0x400u, L"%s%s", v7, bstrString);
    v4 = v11;
    if ( v11 >= 0 )
    {
      if ( *a1 )
      {
        SysFreeString(*a1);
        *a1 = 0;
      }
      v13 = SysAllocString(v19);
      *a1 = v13;
      if ( !v13 )
      {
        v4 = -2147024882;
        CEventLogger::LogError(
          v14,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
          0x239u,
          L"MakeTimeStamp",
          0x8007000E);
      }
    }
    else
    {
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
        0x235u,
        L"MakeTimeStamp",
        v11);
    }
  }
  else
  {
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x22Bu,
      L"MakeTimeStamp",
      DateAsBSTR);
  }
  if ( v10 )
    SysFreeString(v10);
  SysFreeString(v7);
  return v4;
}

```

## disassembly

```asm
0x140036b80  mov     [rsp-8+arg_8], rbx
0x140036b85  mov     [rsp-8+arg_10], rsi
0x140036b8a  push    rbp
0x140036b8b  push    rdi
0x140036b8c  push    r14
0x140036b8e  lea     rbp, [rsp-0F60h]
0x140036b96  mov     eax, 1060h
0x140036b9b  call    _alloca_probe
0x140036ba0  sub     rsp, rax
0x140036ba3  mov     rax, cs:__security_cookie
0x140036baa  xor     rax, rsp
0x140036bad  mov     [rbp+0F70h+var_20], rax
0x140036bb4  mov     r14, rcx
0x140036bb7  mov     [rsp+1070h+bstrString], 0
0x140036bc0  mov     ebx, 800h
0x140036bc5  lea     rcx, [rbp+0F70h+var_820]; void *
0x140036bcc  mov     r8d, ebx; Size
0x140036bcf  xor     edx, edx; Val
0x140036bd1  call    memset_0
0x140036bd6  mov     r8d, ebx; Size
0x140036bd9  lea     rcx, [rsp+1070h+psz]; void *
0x140036bde  xor     edx, edx; Val
0x140036be0  call    memset_0
0x140036be5  xorps   xmm0, xmm0
0x140036be8  lea     rcx, [rsp+1070h+SystemTime]; lpSystemTime
0x140036bed  movups  xmmword ptr [rsp+1070h+SystemTime.wYear], xmm0
0x140036bf2  call    cs:__imp_GetLocalTime
0x140036bf9  nop     dword ptr [rax+rax+00h]
0x140036bfe  movzx   ecx, [rsp+1070h+SystemTime.wMinute]
0x140036c03  lea     r8, a02d02d02d; "%02d%02d%02d"
0x140036c0a  movzx   eax, [rsp+1070h+SystemTime.wSecond]
0x140036c0f  mov     edx, 400h; unsigned __int64
0x140036c14  movzx   r9d, [rsp+1070h+SystemTime.wHour]
0x140036c1a  mov     [rsp+1070h+var_1048], eax
0x140036c1e  mov     dword ptr [rsp+1070h+var_1050], ecx
0x140036c22  lea     rcx, [rsp+1070h+psz]; unsigned __int16 *
0x140036c27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140036c2c  mov     ebx, eax
0x140036c2e  test    eax, eax
0x140036c30  jns     short loc_140036C3E
0x140036c32  mov     [rsp+1070h+var_1048], eax
0x140036c36  mov     r9d, 1D3h
0x140036c3c  jmp     short loc_140036C6A
0x140036c3e  lea     rcx, [rsp+1070h+psz]; psz
0x140036c43  call    cs:__imp_SysAllocString
0x140036c4a  nop     dword ptr [rax+rax+00h]
0x140036c4f  mov     rdi, rax
0x140036c52  test    rax, rax
0x140036c55  jnz     short loc_140036CB7
0x140036c57  mov     ebx, 8007000Eh
0x140036c5c  mov     [rsp+1070h+var_1048], 8007000Eh; unsigned int
0x140036c64  mov     r9d, 1D7h; unsigned int
0x140036c6a  lea     rax, aGettimeasbstr; "GetTimeAsBSTR"
0x140036c71  lea     r8, aBaseDiagnosisR_33; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x140036c78  mov     [rsp+1070h+var_1050], rax; unsigned __int16 *
0x140036c7d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140036c84  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140036c89  lea     rax, aMaketimestamp; "MakeTimeStamp"
0x140036c90  mov     [rsp+1070h+var_1048], ebx; unsigned int
0x140036c94  mov     r9d, 22Ah; unsigned int
0x140036c9a  mov     [rsp+1070h+var_1050], rax; unsigned __int16 *
0x140036c9f  lea     r8, aBaseDiagnosisR_33; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x140036ca6  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140036cad  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140036cb2  jmp     loc_140036D95
0x140036cb7  lea     rcx, [rsp+1070h+bstrString]; unsigned __int16 **
0x140036cbc  call    ?GetDateAsBSTR@@YAJPEAPEAG@Z; GetDateAsBSTR(ushort * *)
0x140036cc1  mov     rsi, [rsp+1070h+bstrString]
0x140036cc6  mov     ebx, eax
0x140036cc8  test    eax, eax
0x140036cca  jns     short loc_140036CD8
0x140036ccc  mov     [rsp+1070h+var_1048], eax
0x140036cd0  mov     r9d, 22Bh
0x140036cd6  jmp     short loc_140036D53
0x140036cd8  mov     r9, rdi
0x140036cdb  mov     [rsp+1070h+var_1050], rsi
0x140036ce0  lea     r8, aSS_0; "%s%s"
0x140036ce7  mov     edx, 400h; unsigned __int64
0x140036cec  lea     rcx, [rbp+0F70h+var_820]; unsigned __int16 *
0x140036cf3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140036cf8  mov     ebx, eax
0x140036cfa  test    eax, eax
0x140036cfc  jns     short loc_140036D0A
0x140036cfe  mov     [rsp+1070h+var_1048], eax
0x140036d02  mov     r9d, 235h
0x140036d08  jmp     short loc_140036D53
0x140036d0a  mov     rcx, [r14]; bstrString
0x140036d0d  test    rcx, rcx
0x140036d10  jz      short loc_140036D25
0x140036d12  call    cs:__imp_SysFreeString
0x140036d19  nop     dword ptr [rax+rax+00h]
0x140036d1e  mov     qword ptr [r14], 0
0x140036d25  lea     rcx, [rbp+0F70h+var_820]; psz
0x140036d2c  call    cs:__imp_SysAllocString
0x140036d33  nop     dword ptr [rax+rax+00h]
0x140036d38  mov     [r14], rax
0x140036d3b  test    rax, rax
0x140036d3e  jnz     short loc_140036D72
0x140036d40  mov     ebx, 8007000Eh
0x140036d45  mov     [rsp+1070h+var_1048], 8007000Eh; unsigned int
0x140036d4d  mov     r9d, 239h; unsigned int
0x140036d53  lea     rax, aMaketimestamp; "MakeTimeStamp"
0x140036d5a  lea     r8, aBaseDiagnosisR_33; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x140036d61  mov     [rsp+1070h+var_1050], rax; unsigned __int16 *
0x140036d66  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140036d6d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140036d72  test    rsi, rsi
0x140036d75  jz      short loc_140036D86
0x140036d77  mov     rcx, rsi; bstrString
0x140036d7a  call    cs:__imp_SysFreeString
0x140036d81  nop     dword ptr [rax+rax+00h]
0x140036d86  mov     rcx, rdi; bstrString
0x140036d89  call    cs:__imp_SysFreeString
0x140036d90  nop     dword ptr [rax+rax+00h]
0x140036d95  mov     eax, ebx
0x140036d97  mov     rcx, [rbp+0F70h+var_20]
0x140036d9e  xor     rcx, rsp; StackCookie
0x140036da1  call    __security_check_cookie
0x140036da6  lea     r11, [rsp+1070h+var_10]
0x140036dae  mov     rbx, [r11+28h]
0x140036db2  mov     rsi, [r11+30h]
0x140036db6  mov     rsp, r11
0x140036db9  pop     r14
0x140036dbb  pop     rdi
0x140036dbc  pop     rbp
0x140036dbd  retn
```
