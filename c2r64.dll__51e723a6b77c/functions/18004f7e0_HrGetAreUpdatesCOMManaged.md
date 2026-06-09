# HrGetAreUpdatesCOMManaged

- ea: `0x18004f7e0`
- end: `0x18004f9cd`
- name: `HrGetAreUpdatesCOMManaged`
- size: `493`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008f14`
- `0x180016c74`
- `0x180017658`
- `0x180018e28`
- `0x1800315e0`
- `0x18003e690`
- `0x1800409e0`
- `0x18004f7e0`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f94d`
- `KERNEL32!GetLastError` at `0x18004f94d`
- `KERNEL32!CompareStringEx` at `0x18004f8ee`
- `KERNEL32!CompareStringEx` at `0x18004f943`
- `KERNEL32!CompareStringEx` at `0x18004f8ee`
- `KERNEL32!CompareStringEx` at `0x18004f943`

## string_xrefs

- `0x18004f80c`: `HrGetAreUpdatesCOMManaged`
- `0x18004f86e`: `HrGetAreUpdatesCOMManaged`

## pseudocode

```c
__int64 __fastcall HrGetAreUpdatesCOMManaged(_DWORD *a1, __int64 a2)
{
  int v2; // ebx
  int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // r14d
  unsigned __int64 v9; // rsi
  int cchCount2; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int v16[4]; // [rsp+50h] [rbp-B0h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v18; // [rsp+64h] [rbp-9Ch]
  DWORD LastError; // [rsp+264h] [rbp+164h]
  __int16 v20; // [rsp+268h] [rbp+168h]
  __int16 v21; // [rsp+368h] [rbp+268h]
  int v22; // [rsp+3E8h] [rbp+2E8h]
  WCHAR String1[264]; // [rsp+3F0h] [rbp+2F0h] BYREF

  v2 = a2;
  LogLineFormat<11,wchar_t [26]>(a1, a2, L"HrGetAreUpdatesCOMManaged");
  memset(String1, 0, 0x208u);
  v4 = 0;
  v16[0] = C2RClientWrapper::GetClickToRunDataEx(&g_apiClient, 12, &LocaleName, String1, 260, v2);
  v8 = v16[0];
  if ( v16[0] >= 0 )
  {
    v9 = -1;
    if ( String1[0] )
    {
      do
        ++v9;
      while ( String1[v9] );
      cchCount2 = OcfxInt32FromSize_t(4u);
      v11 = OcfxInt32FromSize_t(v9);
      v12 = CompareStringEx(&LocaleName, 1u, String1, v11, L"True", cchCount2, 0, 0, 0);
      if ( !v12 )
      {
        v13 = OcfxInt32FromSize_t(4u);
        v14 = OcfxInt32FromSize_t(v9);
        v12 = CompareStringEx(L"en-US", 1u, String1, v14, L"True", v13, 0, 0, 0);
        if ( !v12 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v22 = 808464432;
          v21 = 0;
          v20 = 0;
          v18 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      LODWORD(v9) = v12 - 2;
    }
    LOBYTE(v4) = (_DWORD)v9 == 0;
    *a1 = v4;
    LogLineFormat<34,wchar_t [26],int>(v6, v5, v7, a1);
  }
  else
  {
    LogLineFormat<22,wchar_t [26],long>(v6, v5, L"HrGetAreUpdatesCOMManaged", v16);
    return (unsigned int)v16[0];
  }
  return v8;
}

```

## disassembly

```asm
0x18004f7e0  mov     [rsp-8+arg_10], rbx
0x18004f7e5  push    rbp
0x18004f7e6  push    rsi
0x18004f7e7  push    rdi
0x18004f7e8  push    r14
0x18004f7ea  push    r15
0x18004f7ec  lea     rbp, [rsp-510h]
0x18004f7f4  sub     rsp, 610h
0x18004f7fb  mov     rax, cs:__security_cookie
0x18004f802  xor     rax, rsp
0x18004f805  mov     [rbp+530h+var_30], rax
0x18004f80c  lea     r8, aHrgetareupdate_15; "HrGetAreUpdatesCOMManaged"
0x18004f813  mov     ebx, edx
0x18004f815  mov     r15, rcx
0x18004f818  call    ??$LogLineFormat@$0L@$$BY0BK@_W@@YAXW4Severity@Logging@Mso@@AEAY0L@$$CB_WAEAY0BK@$$CB_W@Z; LogLineFormat<11,wchar_t [26]>(Mso::Logging::Severity,wchar_t const (&)[11],wchar_t const (&)[26])
0x18004f81d  xor     edx, edx; Val
0x18004f81f  lea     rcx, [rbp+530h+String1]; void *
0x18004f826  mov     r8d, 208h; Size
0x18004f82c  call    memset
0x18004f831  lea     r9, [rbp+530h+String1]
0x18004f838  mov     [rsp+630h+cchCount2], ebx
0x18004f83c  lea     r8, LocaleName
0x18004f843  mov     dword ptr [rsp+630h+lpString2], 104h
0x18004f84b  mov     edx, 0Ch
0x18004f850  lea     rcx, ?g_apiClient@@3VC2RClientWrapper@@A; C2RClientWrapper g_apiClient
0x18004f857  call    ?GetClickToRunDataEx@C2RClientWrapper@@AEAAJW4ClickToRunDataType@@PEB_WPEA_WKK@Z; C2RClientWrapper::GetClickToRunDataEx(ClickToRunDataType,wchar_t const *,wchar_t *,ulong,ulong)
0x18004f85c  xor     edi, edi
0x18004f85e  mov     [rsp+630h+var_5E0], eax
0x18004f862  mov     r14d, eax
0x18004f865  test    eax, eax
0x18004f867  jns     short loc_18004F884
0x18004f869  lea     r9, [rsp+630h+var_5E0]
0x18004f86e  lea     r8, aHrgetareupdate_15; "HrGetAreUpdatesCOMManaged"
0x18004f875  call    ??$LogLineFormat@$0BG@$$BY0BK@_WJ@@YAXW4Severity@Logging@Mso@@AEAY0BG@$$CB_WAEAY0BK@$$CB_WAEBJ@Z; LogLineFormat<22,wchar_t [26],long>(Mso::Logging::Severity,wchar_t const (&)[22],wchar_t const (&)[26],long const &)
0x18004f87a  mov     r14d, [rsp+630h+var_5E0]
0x18004f87f  jmp     loc_18004F9A4
0x18004f884  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004f888  cmp     di, [rbp+530h+String1]
0x18004f88f  jz      loc_18004F993
0x18004f895  lea     rax, [rbp+530h+String1]
0x18004f89c  inc     rsi
0x18004f89f  cmp     [rax+rsi*2], di
0x18004f8a3  jnz     short loc_18004F89C
0x18004f8a5  mov     ecx, 4; unsigned __int64
0x18004f8aa  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004f8af  mov     rcx, rsi; unsigned __int64
0x18004f8b2  mov     ebx, eax
0x18004f8b4  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004f8b9  mov     [rsp+630h+lParam], rdi; lParam
0x18004f8be  lea     rcx, String2; "True"
0x18004f8c5  mov     [rsp+630h+lpReserved], rdi; lpReserved
0x18004f8ca  lea     r8, [rbp+530h+String1]; lpString1
0x18004f8d1  mov     [rsp+630h+lpVersionInformation], rdi; lpVersionInformation
0x18004f8d6  mov     r9d, eax; cchCount1
0x18004f8d9  mov     [rsp+630h+cchCount2], ebx; cchCount2
0x18004f8dd  mov     edx, 1; dwCmpFlags
0x18004f8e2  mov     [rsp+630h+lpString2], rcx; lpString2
0x18004f8e7  lea     rcx, LocaleName; lpLocaleName
0x18004f8ee  call    cs:__imp_CompareStringEx
0x18004f8f4  test    eax, eax
0x18004f8f6  jnz     loc_18004F990
0x18004f8fc  lea     ecx, [rax+4]; unsigned __int64
0x18004f8ff  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004f904  mov     rcx, rsi; unsigned __int64
0x18004f907  mov     ebx, eax
0x18004f909  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004f90e  mov     [rsp+630h+lParam], rdi; lParam
0x18004f913  lea     rcx, String2; "True"
0x18004f91a  mov     [rsp+630h+lpReserved], rdi; lpReserved
0x18004f91f  lea     r8, [rbp+530h+String1]; lpString1
0x18004f926  mov     [rsp+630h+lpVersionInformation], rdi; lpVersionInformation
0x18004f92b  mov     r9d, eax; cchCount1
0x18004f92e  mov     [rsp+630h+cchCount2], ebx; cchCount2
0x18004f932  mov     edx, 1; dwCmpFlags
0x18004f937  mov     [rsp+630h+lpString2], rcx; lpString2
0x18004f93c  lea     rcx, aEnUs; "en-US"
0x18004f943  call    cs:__imp_CompareStringEx
0x18004f949  test    eax, eax
0x18004f94b  jnz     short loc_18004F990
0x18004f94d  call    cs:__imp_GetLastError
0x18004f953  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18004f95a  mov     [rsp+630h+pExceptionObject], 0Fh
0x18004f962  lea     rcx, [rsp+630h+pExceptionObject]; pExceptionObject
0x18004f967  mov     [rbp+530h+var_3CC], eax
0x18004f96d  mov     [rbp+530h+var_248], 30303030h
0x18004f977  mov     [rbp+530h+var_2C8], di
0x18004f97e  mov     [rbp+530h+var_3C8], di
0x18004f985  mov     [rsp+630h+var_5CC], di
0x18004f98a  call    _CxxThrowException
0x18004f990  lea     esi, [rax-2]
0x18004f993  test    esi, esi
0x18004f995  mov     r9, r15
0x18004f998  setz    dil
0x18004f99c  mov     [r15], edi
0x18004f99f  call    ??$LogLineFormat@$0CC@$$BY0BK@_WH@@YAXW4Severity@Logging@Mso@@AEAY0CC@$$CB_WAEAY0BK@$$CB_WAEBH@Z; LogLineFormat<34,wchar_t [26],int>(Mso::Logging::Severity,wchar_t const (&)[34],wchar_t const (&)[26],int const &)
0x18004f9a4  mov     eax, r14d
0x18004f9a7  mov     rcx, [rbp+530h+var_30]
0x18004f9ae  xor     rcx, rsp; StackCookie
0x18004f9b1  call    __security_check_cookie
0x18004f9b6  mov     rbx, [rsp+630h+arg_10]
0x18004f9be  add     rsp, 610h
0x18004f9c5  pop     r15
0x18004f9c7  pop     r14
0x18004f9c9  pop     rdi
0x18004f9ca  pop     rsi
0x18004f9cb  pop     rbp
0x18004f9cc  retn
```
