# HrGetAreUpdatesFromAdminSourceEx

- ea: `0x18004f9f0`
- end: `0x18004fbd6`
- name: `HrGetAreUpdatesFromAdminSourceEx`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004f9e0`

## callees

- `0x180008f14`
- `0x180018e28`
- `0x18003e690`
- `0x1800409e0`
- `0x18004d998`
- `0x18004df64`
- `0x18004e4d8`
- `0x18004f9f0`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004fb56`
- `KERNEL32!GetLastError` at `0x18004fb56`
- `KERNEL32!CompareStringEx` at `0x18004faf7`
- `KERNEL32!CompareStringEx` at `0x18004fb4c`
- `KERNEL32!CompareStringEx` at `0x18004faf7`
- `KERNEL32!CompareStringEx` at `0x18004fb4c`

## string_xrefs

- `0x18004fa45`: `updatesfromadminsource`
- `0x18004fa77`: `HrGetAreUpdatesFromAdminSource: Failed: HR=0x%08x`

## pseudocode

```c
__int64 __fastcall HrGetAreUpdatesFromAdminSourceEx(_DWORD *a1, int a2)
{
  int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // r14d
  unsigned __int64 v8; // rsi
  int cchCount2; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  int v15[4]; // [rsp+50h] [rbp-B0h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v17; // [rsp+64h] [rbp-9Ch]
  DWORD LastError; // [rsp+264h] [rbp+164h]
  __int16 v19; // [rsp+268h] [rbp+168h]
  __int16 v20; // [rsp+368h] [rbp+268h]
  int v21; // [rsp+3E8h] [rbp+2E8h]
  WCHAR String1[264]; // [rsp+3F0h] [rbp+2F0h] BYREF

  LogLineFormat<39>();
  memset(String1, 0, 0x208u);
  v4 = 0;
  v15[0] = C2RClientWrapper::GetClickToRunDataEx(&g_apiClient, 2, L"updatesfromadminsource", String1, 260, a2);
  v7 = v15[0];
  if ( v15[0] >= 0 )
  {
    v8 = -1;
    if ( String1[0] )
    {
      do
        ++v8;
      while ( String1[v8] );
      cchCount2 = OcfxInt32FromSize_t(4u);
      v10 = OcfxInt32FromSize_t(v8);
      v11 = CompareStringEx(&LocaleName, 1u, String1, v10, L"True", cchCount2, 0, 0, 0);
      if ( !v11 )
      {
        v12 = OcfxInt32FromSize_t(4u);
        v13 = OcfxInt32FromSize_t(v8);
        v11 = CompareStringEx(L"en-US", 1u, String1, v13, L"True", v12, 0, 0, 0);
        if ( !v11 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v21 = 808464432;
          v20 = 0;
          v19 = 0;
          v17 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      LODWORD(v8) = v11 - 2;
    }
    LOBYTE(v4) = (_DWORD)v8 == 0;
    *a1 = v4;
    LogLineFormat<67,int>(v6, v5, a1);
  }
  else
  {
    LogLineFormat<50,long>(v6, L"HrGetAreUpdatesFromAdminSource: Failed: HR=0x%08x", v15);
    return (unsigned int)v15[0];
  }
  return v7;
}

```

## disassembly

```asm
0x18004f9f0  mov     [rsp-8+arg_10], rbx
0x18004f9f5  push    rbp
0x18004f9f6  push    rsi
0x18004f9f7  push    rdi
0x18004f9f8  push    r14
0x18004f9fa  push    r15
0x18004f9fc  lea     rbp, [rsp-510h]
0x18004fa04  sub     rsp, 610h
0x18004fa0b  mov     rax, cs:__security_cookie
0x18004fa12  xor     rax, rsp
0x18004fa15  mov     [rbp+530h+var_30], rax
0x18004fa1c  mov     ebx, edx
0x18004fa1e  mov     r15, rcx
0x18004fa21  call    ??$LogLineFormat@$0CH@@@YAXW4Severity@Logging@Mso@@AEAY0CH@$$CB_W@Z; LogLineFormat<39>(Mso::Logging::Severity,wchar_t const (&)[39])
0x18004fa26  xor     edx, edx; Val
0x18004fa28  lea     rcx, [rbp+530h+String1]; void *
0x18004fa2f  mov     r8d, 208h; Size
0x18004fa35  call    memset
0x18004fa3a  lea     r9, [rbp+530h+String1]
0x18004fa41  mov     [rsp+630h+cchCount2], ebx
0x18004fa45  lea     r8, aUpdatesfromadm_0; "updatesfromadminsource"
0x18004fa4c  mov     dword ptr [rsp+630h+lpString2], 104h
0x18004fa54  mov     edx, 2
0x18004fa59  lea     rcx, ?g_apiClient@@3VC2RClientWrapper@@A; C2RClientWrapper g_apiClient
0x18004fa60  call    ?GetClickToRunDataEx@C2RClientWrapper@@AEAAJW4ClickToRunDataType@@PEB_WPEA_WKK@Z; C2RClientWrapper::GetClickToRunDataEx(ClickToRunDataType,wchar_t const *,wchar_t *,ulong,ulong)
0x18004fa65  xor     edi, edi
0x18004fa67  mov     [rsp+630h+var_5E0], eax
0x18004fa6b  mov     r14d, eax
0x18004fa6e  test    eax, eax
0x18004fa70  jns     short loc_18004FA8D
0x18004fa72  lea     r8, [rsp+630h+var_5E0]
0x18004fa77  lea     rdx, aHrgetareupdate_29; "HrGetAreUpdatesFromAdminSource: Failed:"...
0x18004fa7e  call    ??$LogLineFormat@$0DC@J@@YAXW4Severity@Logging@Mso@@AEAY0DC@$$CB_WAEBJ@Z; LogLineFormat<50,long>(Mso::Logging::Severity,wchar_t const (&)[50],long const &)
0x18004fa83  mov     r14d, [rsp+630h+var_5E0]
0x18004fa88  jmp     loc_18004FBAD
0x18004fa8d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004fa91  cmp     di, [rbp+530h+String1]
0x18004fa98  jz      loc_18004FB9C
0x18004fa9e  lea     rax, [rbp+530h+String1]
0x18004faa5  inc     rsi
0x18004faa8  cmp     [rax+rsi*2], di
0x18004faac  jnz     short loc_18004FAA5
0x18004faae  mov     ecx, 4; unsigned __int64
0x18004fab3  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004fab8  mov     rcx, rsi; unsigned __int64
0x18004fabb  mov     ebx, eax
0x18004fabd  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004fac2  mov     [rsp+630h+lParam], rdi; lParam
0x18004fac7  lea     rcx, String2; "True"
0x18004face  mov     [rsp+630h+lpReserved], rdi; lpReserved
0x18004fad3  lea     r8, [rbp+530h+String1]; lpString1
0x18004fada  mov     [rsp+630h+lpVersionInformation], rdi; lpVersionInformation
0x18004fadf  mov     r9d, eax; cchCount1
0x18004fae2  mov     [rsp+630h+cchCount2], ebx; cchCount2
0x18004fae6  mov     edx, 1; dwCmpFlags
0x18004faeb  mov     [rsp+630h+lpString2], rcx; lpString2
0x18004faf0  lea     rcx, LocaleName; lpLocaleName
0x18004faf7  call    cs:__imp_CompareStringEx
0x18004fafd  test    eax, eax
0x18004faff  jnz     loc_18004FB99
0x18004fb05  lea     ecx, [rax+4]; unsigned __int64
0x18004fb08  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004fb0d  mov     rcx, rsi; unsigned __int64
0x18004fb10  mov     ebx, eax
0x18004fb12  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18004fb17  mov     [rsp+630h+lParam], rdi; lParam
0x18004fb1c  lea     rcx, String2; "True"
0x18004fb23  mov     [rsp+630h+lpReserved], rdi; lpReserved
0x18004fb28  lea     r8, [rbp+530h+String1]; lpString1
0x18004fb2f  mov     [rsp+630h+lpVersionInformation], rdi; lpVersionInformation
0x18004fb34  mov     r9d, eax; cchCount1
0x18004fb37  mov     [rsp+630h+cchCount2], ebx; cchCount2
0x18004fb3b  mov     edx, 1; dwCmpFlags
0x18004fb40  mov     [rsp+630h+lpString2], rcx; lpString2
0x18004fb45  lea     rcx, aEnUs; "en-US"
0x18004fb4c  call    cs:__imp_CompareStringEx
0x18004fb52  test    eax, eax
0x18004fb54  jnz     short loc_18004FB99
0x18004fb56  call    cs:__imp_GetLastError
0x18004fb5c  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18004fb63  mov     [rsp+630h+pExceptionObject], 0Fh
0x18004fb6b  lea     rcx, [rsp+630h+pExceptionObject]; pExceptionObject
0x18004fb70  mov     [rbp+530h+var_3CC], eax
0x18004fb76  mov     [rbp+530h+var_248], 30303030h
0x18004fb80  mov     [rbp+530h+var_2C8], di
0x18004fb87  mov     [rbp+530h+var_3C8], di
0x18004fb8e  mov     [rsp+630h+var_5CC], di
0x18004fb93  call    _CxxThrowException
0x18004fb99  lea     esi, [rax-2]
0x18004fb9c  test    esi, esi
0x18004fb9e  mov     r8, r15
0x18004fba1  setz    dil
0x18004fba5  mov     [r15], edi
0x18004fba8  call    ??$LogLineFormat@$0ED@H@@YAXW4Severity@Logging@Mso@@AEAY0ED@$$CB_WAEBH@Z; LogLineFormat<67,int>(Mso::Logging::Severity,wchar_t const (&)[67],int const &)
0x18004fbad  mov     eax, r14d
0x18004fbb0  mov     rcx, [rbp+530h+var_30]
0x18004fbb7  xor     rcx, rsp; StackCookie
0x18004fbba  call    __security_check_cookie
0x18004fbbf  mov     rbx, [rsp+630h+arg_10]
0x18004fbc7  add     rsp, 610h
0x18004fbce  pop     r15
0x18004fbd0  pop     r14
0x18004fbd2  pop     rdi
0x18004fbd3  pop     rsi
0x18004fbd4  pop     rbp
0x18004fbd5  retn
```
