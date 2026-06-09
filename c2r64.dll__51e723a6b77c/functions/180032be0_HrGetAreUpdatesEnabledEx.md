# HrGetAreUpdatesEnabledEx

- ea: `0x180032be0`
- end: `0x180032e28`
- name: `HrGetAreUpdatesEnabledEx`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004f9d0`

## callees

- `0x180008f14`
- `0x18000aa64`
- `0x180016020`
- `0x180018e90`
- `0x180032be0`
- `0x180032e28`
- `0x180032ec0`
- `0x18003e690`
- `0x1800409e0`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032da5`
- `KERNEL32!GetLastError` at `0x180032da5`
- `KERNEL32!CompareStringEx` at `0x180032d46`
- `KERNEL32!CompareStringEx` at `0x180032d9b`
- `KERNEL32!CompareStringEx` at `0x180032d46`
- `KERNEL32!CompareStringEx` at `0x180032d9b`

## string_xrefs

- `0x180032cc6`: `HrGetAreUpdatesEnabled: Failed: HR=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrGetAreUpdatesEnabledEx(_DWORD *a1, int a2)
{
  __int64 *RpcClient; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // r14d
  int v8; // edi
  unsigned __int64 v9; // rsi
  int cchCount2; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  DWORD LastError; // eax
  unsigned int v17; // [rsp+58h] [rbp-B0h] BYREF
  int v18; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-A0h] BYREF
  const WCHAR *v20; // [rsp+70h] [rbp-98h] BYREF
  WCHAR *v21; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v22[7]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v23[2]; // [rsp+B8h] [rbp-50h] BYREF
  int pExceptionObject; // [rsp+C8h] [rbp-40h] BYREF
  __int16 v25; // [rsp+CCh] [rbp-3Ch]
  DWORD v26; // [rsp+2CCh] [rbp+1C4h]
  __int16 v27; // [rsp+2D0h] [rbp+1C8h]
  __int16 v28; // [rsp+3D0h] [rbp+2C8h]
  int v29; // [rsp+450h] [rbp+348h]
  WCHAR String1[264]; // [rsp+458h] [rbp+350h] BYREF

  LogLineFormat<31>();
  memset(String1, 0, 0x208u);
  LODWORD(v19) = a2;
  v18 = 260;
  v21 = String1;
  v20 = &LocaleName;
  v17 = 9;
  v22[0] = &g_apiClient;
  v22[1] = &v17;
  v22[2] = &v20;
  v22[3] = &v21;
  v22[4] = &v18;
  v22[5] = &v19;
  v22[6] = v23;
  RpcClient = C2RClientWrapper::get_RpcClient((__int64)&g_apiClient, v23);
  v7 = sub_180018E90(RpcClient, v22);
  v17 = v7;
  v8 = 0;
  if ( v7 >= 0 )
  {
    v9 = -1;
    if ( String1[0] )
    {
      do
        ++v9;
      while ( String1[v9] );
      cchCount2 = OcfxInt32FromSize_t(5u);
      v11 = OcfxInt32FromSize_t(v9);
      v12 = CompareStringEx(&LocaleName, 1u, String1, v11, L"False", cchCount2, 0, 0, 0);
      if ( !v12 )
      {
        v13 = OcfxInt32FromSize_t(5u);
        v14 = OcfxInt32FromSize_t(v9);
        v12 = CompareStringEx(L"en-US", 1u, String1, v14, L"False", v13, 0, 0, 0);
        if ( !v12 )
        {
          LastError = GetLastError();
          pExceptionObject = 15;
          v26 = LastError;
          v29 = 808464432;
          v28 = 0;
          v27 = 0;
          v25 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      LODWORD(v9) = v12 - 2;
    }
    LOBYTE(v8) = (_DWORD)v9 != 0;
    *a1 = v8;
    LogLineFormat<51,int>(v6, v5, a1);
  }
  else
  {
    LogLineFormat<42,long>(v6, L"HrGetAreUpdatesEnabled: Failed: HR=0x%08x", &v17);
    return v17;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032be0  mov     rax, rsp
0x180032be3  mov     [rax+10h], rbx
0x180032be7  mov     [rax+18h], rsi
0x180032beb  mov     [rax+20h], rdi
0x180032bef  push    rbp
0x180032bf0  push    r14
0x180032bf2  push    r15
0x180032bf4  lea     rbp, [rax-588h]
0x180032bfb  sub     rsp, 670h
0x180032c02  mov     rax, cs:__security_cookie
0x180032c09  xor     rax, rsp
0x180032c0c  mov     [rbp+580h+var_20], rax
0x180032c13  mov     ebx, edx
0x180032c15  mov     r15, rcx
0x180032c18  call    ??$LogLineFormat@$0BP@@@YAXW4Severity@Logging@Mso@@AEAY0BP@$$CB_W@Z; LogLineFormat<31>(Mso::Logging::Severity,wchar_t const (&)[31])
0x180032c1d  xor     edx, edx; Val
0x180032c1f  mov     r8d, 208h; Size
0x180032c25  lea     rcx, [rbp+580h+String1]; void *
0x180032c2c  call    memset
0x180032c31  mov     dword ptr [rsp+680h+var_620], ebx
0x180032c35  mov     [rsp+680h+var_628], 104h
0x180032c3d  lea     rax, [rbp+580h+String1]
0x180032c44  mov     [rsp+680h+var_610], rax
0x180032c49  lea     rax, LocaleName
0x180032c50  mov     [rsp+680h+var_618], rax
0x180032c55  mov     [rsp+680h+var_630], 9
0x180032c5d  lea     rcx, ?g_apiClient@@3VC2RClientWrapper@@A; C2RClientWrapper g_apiClient
0x180032c64  mov     [rsp+680h+var_608], rcx
0x180032c69  lea     rax, [rsp+680h+var_630]
0x180032c6e  mov     [rbp+580h+var_600], rax
0x180032c72  lea     rax, [rsp+680h+var_618]
0x180032c77  mov     [rbp+580h+var_5F8], rax
0x180032c7b  lea     rax, [rsp+680h+var_610]
0x180032c80  mov     [rbp+580h+var_5F0], rax
0x180032c84  lea     rax, [rsp+680h+var_628]
0x180032c89  mov     [rbp+580h+var_5E8], rax
0x180032c8d  lea     rax, [rsp+680h+var_620]
0x180032c92  mov     [rbp+580h+var_5E0], rax
0x180032c96  lea     rax, [rbp+580h+var_5D0]
0x180032c9a  mov     [rbp+580h+var_5D8], rax
0x180032c9e  lea     rdx, [rbp+580h+var_5D0]
0x180032ca2  call    ?get_RpcClient@C2RClientWrapper@@AEAA?AV?$shared_ptr@VORpcClient@@@std@@XZ; C2RClientWrapper::get_RpcClient(void)
0x180032ca7  lea     rdx, [rsp+680h+var_608]
0x180032cac  mov     rcx, rax
0x180032caf  call    sub_180018E90
0x180032cb4  mov     r14d, eax
0x180032cb7  mov     [rsp+680h+var_630], eax
0x180032cbb  xor     edi, edi
0x180032cbd  test    eax, eax
0x180032cbf  jns     short loc_180032CDC
0x180032cc1  lea     r8, [rsp+680h+var_630]
0x180032cc6  lea     rdx, aHrgetareupdate_17; "HrGetAreUpdatesEnabled: Failed: HR=0x%0"...
0x180032ccd  call    ??$LogLineFormat@$0CK@J@@YAXW4Severity@Logging@Mso@@AEAY0CK@$$CB_WAEBJ@Z; LogLineFormat<42,long>(Mso::Logging::Severity,wchar_t const (&)[42],long const &)
0x180032cd2  mov     r14d, [rsp+680h+var_630]
0x180032cd7  jmp     loc_180032DF9
0x180032cdc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180032ce0  cmp     di, [rbp+580h+String1]
0x180032ce7  jz      loc_180032DE8
0x180032ced  lea     rax, [rbp+580h+String1]
0x180032cf4  inc     rsi
0x180032cf7  cmp     [rax+rsi*2], di
0x180032cfb  jnz     short loc_180032CF4
0x180032cfd  mov     ecx, 5; unsigned __int64
0x180032d02  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180032d07  mov     ebx, eax
0x180032d09  mov     rcx, rsi; unsigned __int64
0x180032d0c  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180032d11  mov     [rsp+680h+lParam], rdi; lParam
0x180032d16  mov     [rsp+680h+lpReserved], rdi; lpReserved
0x180032d1b  mov     [rsp+680h+lpVersionInformation], rdi; lpVersionInformation
0x180032d20  mov     [rsp+680h+cchCount2], ebx; cchCount2
0x180032d24  lea     rcx, aFalse_2; "False"
0x180032d2b  mov     [rsp+680h+lpString2], rcx; lpString2
0x180032d30  mov     r9d, eax; cchCount1
0x180032d33  lea     r8, [rbp+580h+String1]; lpString1
0x180032d3a  mov     edx, 1; dwCmpFlags
0x180032d3f  lea     rcx, LocaleName; lpLocaleName
0x180032d46  call    cs:__imp_CompareStringEx
0x180032d4c  test    eax, eax
0x180032d4e  jnz     loc_180032DE5
0x180032d54  lea     ecx, [rax+5]; unsigned __int64
0x180032d57  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180032d5c  mov     ebx, eax
0x180032d5e  mov     rcx, rsi; unsigned __int64
0x180032d61  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180032d66  mov     [rsp+680h+lParam], rdi; lParam
0x180032d6b  mov     [rsp+680h+lpReserved], rdi; lpReserved
0x180032d70  mov     [rsp+680h+lpVersionInformation], rdi; lpVersionInformation
0x180032d75  mov     [rsp+680h+cchCount2], ebx; cchCount2
0x180032d79  lea     rcx, aFalse_2; "False"
0x180032d80  mov     [rsp+680h+lpString2], rcx; lpString2
0x180032d85  mov     r9d, eax; cchCount1
0x180032d88  lea     r8, [rbp+580h+String1]; lpString1
0x180032d8f  mov     edx, 1; dwCmpFlags
0x180032d94  lea     rcx, aEnUs; "en-US"
0x180032d9b  call    cs:__imp_CompareStringEx
0x180032da1  test    eax, eax
0x180032da3  jnz     short loc_180032DE5
0x180032da5  call    cs:__imp_GetLastError
0x180032dab  mov     [rbp+580h+pExceptionObject], 0Fh
0x180032db2  mov     [rbp+580h+var_3BC], eax
0x180032db8  mov     [rbp+580h+var_238], 30303030h
0x180032dc2  mov     [rbp+580h+var_2B8], di
0x180032dc9  mov     [rbp+580h+var_3B8], di
0x180032dd0  mov     [rbp+580h+var_5BC], di
0x180032dd4  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180032ddb  lea     rcx, [rbp+580h+pExceptionObject]; pExceptionObject
0x180032ddf  call    _CxxThrowException
0x180032de5  lea     esi, [rax-2]
0x180032de8  test    esi, esi
0x180032dea  setnz   dil
0x180032dee  mov     [r15], edi
0x180032df1  mov     r8, r15
0x180032df4  call    ??$LogLineFormat@$0DD@H@@YAXW4Severity@Logging@Mso@@AEAY0DD@$$CB_WAEBH@Z; LogLineFormat<51,int>(Mso::Logging::Severity,wchar_t const (&)[51],int const &)
0x180032df9  mov     eax, r14d
0x180032dfc  mov     rcx, [rbp+580h+var_20]
0x180032e03  xor     rcx, rsp; StackCookie
0x180032e06  call    __security_check_cookie
0x180032e0b  lea     r11, [rsp+680h+var_10]
0x180032e13  mov     rbx, [r11+28h]
0x180032e17  mov     rsi, [r11+30h]
0x180032e1b  mov     rdi, [r11+38h]
0x180032e1f  mov     rsp, r11
0x180032e22  pop     r15
0x180032e24  pop     r14
0x180032e26  pop     rbp
0x180032e27  retn
```
