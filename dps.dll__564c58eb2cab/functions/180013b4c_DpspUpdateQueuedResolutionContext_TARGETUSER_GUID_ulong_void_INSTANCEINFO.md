# DpspUpdateQueuedResolutionContext(__TARGETUSER *,_GUID *,ulong,void *,INSTANCEINFO * *)

- ea: `0x180013b4c`
- end: `0x180013e61`
- name: `?DpspUpdateQueuedResolutionContext@@YAJPEAU__TARGETUSER@@PEAU_GUID@@KPEAXPEAPEAUINSTANCEINFO@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(struct __TARGETUSER *, struct _GUID *, int, void *, struct INSTANCEINFO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001010`
- `0x1800013a0`
- `0x180003020`
- `0x1800067b8`
- `0x180008ea0`
- `0x180009090`
- `0x18000a856`
- `0x180012d2c`
- `0x180013b4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013be7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013be7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013d28`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013d28`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013d74`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013d74`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013cd6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013cee`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013cd6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013cee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013dba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013dba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013c93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013c93`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013ca2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013ca2`

## string_xrefs

- `0x180013ba1`: `DpspUpdateQueuedResolutionContext`
- `0x180013c2b`: `DpspUpdateQueuedResolutionContext`

## pseudocode

```c
__int64 __fastcall DpspUpdateQueuedResolutionContext(
        struct __TARGETUSER *a1,
        struct _GUID *a2,
        int a3,
        void *a4,
        struct INSTANCEINFO **a5)
{
  int v9; // r8d
  unsigned int Args; // ebx
  struct INSTANCEINFO **v11; // r14
  struct _RTL_CRITICAL_SECTION *v12; // rbp
  int InstanceForUser; // eax
  struct INSTANCEINFO *v14; // rdi
  __int64 v15; // rax
  struct INSTANCEINFO **v16; // rcx
  PSID v17; // rcx
  size_t LengthSid; // rbx
  void *v19; // rax
  signed int LastError; // eax
  char *v21; // rcx
  int ResolutionSession; // eax
  __int64 v23; // rsi
  int v24; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+38h] [rbp-30h] BYREF
  struct INSTANCEINFO *v28; // [rsp+70h] [rbp+8h] BYREF

  v28 = 0;
  v27 = 0;
  SystemTimeAsFileTime = 0;
  if ( !a1 )
  {
    v9 = 286;
LABEL_3:
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspUpdateQueuedResolutionContext",
      v9,
      (int)L"Error = %d",
      87);
    return Args;
  }
  if ( !a2 )
  {
    v9 = 287;
    goto LABEL_3;
  }
  v11 = a5;
  if ( !a5 )
  {
    v9 = 288;
    goto LABEL_3;
  }
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  InstanceForUser = DpspGetInstanceForUser(a1, a2, 1u, &v28);
  v14 = v28;
  Args = InstanceForUser;
  if ( InstanceForUser < 0 )
  {
    LeaveCriticalSection(v12);
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspUpdateQueuedResolutionContext",
      299,
      (int)L"Error = %d",
      Args);
    goto LABEL_37;
  }
  if ( !v28 )
  {
    LeaveCriticalSection(v12);
    return Args;
  }
  v15 = *(_QWORD *)v28;
  if ( *(struct INSTANCEINFO **)(*(_QWORD *)v28 + 8LL) != v28
    || (v16 = (struct INSTANCEINFO **)*((_QWORD *)v28 + 1), *v16 != v28) )
  {
    __fastfail(3u);
  }
  *v16 = (struct INSTANCEINFO *)v15;
  *(_QWORD *)(v15 + 8) = v16;
  --*((_DWORD *)a1 + 22);
  LeaveCriticalSection(v12);
  _InterlockedAnd((volatile signed __int32 *)v14 + 26, 0xFFFFFFBF);
  if ( (*((_BYTE *)v14 + 92) & 0x20) == 0
    || (GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
        CompareFileTime((const FILETIME *)v14 + 15, &SystemTimeAsFileTime) > 0) )
  {
    *((_DWORD *)v14 + 27) = a3;
    if ( EqualSid(*((PSID *)v14 + 96), g_pAdminSid) || EqualSid(*((PSID *)v14 + 96), g_pEveryoneSid) )
    {
      v17 = (PSID)*((_QWORD *)v14 + 96);
      if ( v17 != g_pAdminSid && v17 != g_pEveryoneSid )
      {
        WdipFree(v17);
        *((_QWORD *)v14 + 96) = 0;
      }
      LengthSid = GetLengthSid(a4);
      v19 = (void *)WdipAlloc(LengthSid);
      *((_QWORD *)v14 + 96) = v19;
      if ( !v19 )
      {
        Args = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
          (int)L"DpspUpdateQueuedResolutionContext",
          358,
          (int)L"Error = %d",
          14);
        goto LABEL_37;
      }
      memset_0(v19, 0, LengthSid);
      if ( !CopySid(LengthSid, *((PSID *)v14 + 96), a4) )
      {
        LastError = GetLastError();
        Args = LastError;
        if ( LastError > 0 )
          Args = (unsigned __int16)LastError | 0x80070000;
        if ( (Args & 0x80000000) != 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
            (int)L"DpspUpdateQueuedResolutionContext",
            365,
            (int)L"Error = %d",
            Args);
          goto LABEL_37;
        }
      }
    }
    v21 = (char *)*((_QWORD *)v14 + 100);
    if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v21);
      *((_QWORD *)v14 + 100) = 0;
    }
    ResolutionSession = DpspGetResolutionSession(v14, &v27);
    Args = ResolutionSession;
    if ( ResolutionSession >= 0 )
    {
      v23 = v27;
      v24 = DpspAddDMToTraversedList(v14, v27);
      Args = v24;
      if ( v24 >= 0 )
      {
        *((_QWORD *)v14 + 101) = v23;
        *v11 = v14;
      }
      else
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
          (int)L"DpspUpdateQueuedResolutionContext",
          376,
          (int)L"Error = %d",
          v24);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspUpdateQueuedResolutionContext",
        372,
        (int)L"Error = %d",
        ResolutionSession);
    }
    goto LABEL_37;
  }
  Args = -2147022965;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
    (int)L"DpspUpdateQueuedResolutionContext",
    328,
    (int)L"Error = %d",
    139);
LABEL_37:
  if ( v14 && (Args & 0x80000000) != 0 )
    DpspCloseInstance(v14, 4, 15, Args);
  return Args;
}

```

## disassembly

```asm
0x180013b4c  mov     rax, rsp
0x180013b4f  mov     [rax+10h], rbx
0x180013b53  mov     [rax+18h], rbp
0x180013b57  push    rsi
0x180013b58  push    rdi
0x180013b59  push    r12
0x180013b5b  push    r14
0x180013b5d  push    r15
0x180013b5f  sub     rsp, 40h
0x180013b63  mov     qword ptr [rax+8], 0
0x180013b6b  mov     r12, r9
0x180013b6e  mov     qword ptr [rax-30h], 0
0x180013b76  mov     r15d, r8d
0x180013b79  mov     qword ptr [rax-38h], 0
0x180013b81  mov     rbx, rdx
0x180013b84  mov     rsi, rcx
0x180013b87  test    rcx, rcx
0x180013b8a  jnz     short loc_180013BBE
0x180013b8c  mov     r8d, 11Eh; int
0x180013b92  lea     r9, aErrorD; "Error = %d"
0x180013b99  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x180013ba1  lea     rdx, aDpspupdatequeu; "DpspUpdateQueuedResolutionContext"
0x180013ba8  mov     ebx, 80070057h
0x180013bad  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180013bb4  call    WdipTraceError
0x180013bb9  jmp     loc_180013E3F
0x180013bbe  test    rbx, rbx
0x180013bc1  jnz     short loc_180013BCB
0x180013bc3  mov     r8d, 11Fh
0x180013bc9  jmp     short loc_180013B92
0x180013bcb  mov     r14, [rsp+68h+arg_20]
0x180013bd3  test    r14, r14
0x180013bd6  jnz     short loc_180013BE0
0x180013bd8  mov     r8d, 120h
0x180013bde  jmp     short loc_180013B92
0x180013be0  lea     rbp, [rcx+10h]
0x180013be4  mov     rcx, rbp; lpCriticalSection
0x180013be7  call    cs:__imp_EnterCriticalSection
0x180013bed  lea     r9, [rsp+68h+arg_0]; struct INSTANCEINFO **
0x180013bf2  mov     r8d, 1; unsigned int
0x180013bf8  mov     rdx, rbx; struct _GUID *
0x180013bfb  mov     rcx, rsi; struct __TARGETUSER *
0x180013bfe  call    ?DpspGetInstanceForUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@KPEAPEAUINSTANCEINFO@@@Z; DpspGetInstanceForUser(__TARGETUSER *,_GUID *,ulong,INSTANCEINFO * *)
0x180013c03  mov     rdi, [rsp+68h+arg_0]
0x180013c08  mov     ebx, eax
0x180013c0a  test    eax, eax
0x180013c0c  jns     short loc_180013C43
0x180013c0e  mov     rcx, rbp; lpCriticalSection
0x180013c11  call    cs:__imp_LeaveCriticalSection
0x180013c17  movzx   ecx, bx
0x180013c1a  mov     r8d, 12Bh; int
0x180013c20  mov     dword ptr [rsp+68h+Args], ecx; Args
0x180013c24  lea     r9, aErrorD; "Error = %d"
0x180013c2b  lea     rdx, aDpspupdatequeu; "DpspUpdateQueuedResolutionContext"
0x180013c32  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180013c39  call    WdipTraceError
0x180013c3e  jmp     loc_180013E22
0x180013c43  test    rdi, rdi
0x180013c46  jnz     short loc_180013C56
0x180013c48  mov     rcx, rbp; lpCriticalSection
0x180013c4b  call    cs:__imp_LeaveCriticalSection
0x180013c51  jmp     loc_180013E3F
0x180013c56  mov     rax, [rdi]
0x180013c59  cmp     [rax+8], rdi
0x180013c5d  jnz     loc_180013E5A
0x180013c63  mov     rcx, [rdi+8]
0x180013c67  cmp     [rcx], rdi
0x180013c6a  jnz     loc_180013E5A
0x180013c70  mov     [rcx], rax
0x180013c73  mov     [rax+8], rcx
0x180013c77  mov     rcx, rbp; lpCriticalSection
0x180013c7a  dec     dword ptr [rsi+58h]
0x180013c7d  call    cs:__imp_LeaveCriticalSection
0x180013c83  lock and dword ptr [rdi+68h], 0FFFFFFBFh
0x180013c88  test    byte ptr [rdi+5Ch], 20h
0x180013c8c  jz      short loc_180013CC4
0x180013c8e  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013c93  call    cs:__imp_GetSystemTimeAsFileTime
0x180013c99  lea     rcx, [rdi+78h]; lpFileTime1
0x180013c9d  lea     rdx, [rsp+68h+SystemTimeAsFileTime]; lpFileTime2
0x180013ca2  call    cs:__imp_CompareFileTime
0x180013ca8  test    eax, eax
0x180013caa  jg      short loc_180013CC4
0x180013cac  mov     ebx, 8007078Bh
0x180013cb1  mov     dword ptr [rsp+68h+Args], 78Bh
0x180013cb9  mov     r8d, 148h
0x180013cbf  jmp     loc_180013C24
0x180013cc4  mov     [rdi+6Ch], r15d
0x180013cc8  mov     rdx, cs:g_pAdminSid; pSid2
0x180013ccf  mov     rcx, [rdi+300h]; pSid1
0x180013cd6  call    cs:__imp_EqualSid
0x180013cdc  test    eax, eax
0x180013cde  jnz     short loc_180013CFC
0x180013ce0  mov     rdx, cs:g_pEveryoneSid; pSid2
0x180013ce7  mov     rcx, [rdi+300h]; pSid1
0x180013cee  call    cs:__imp_EqualSid
0x180013cf4  test    eax, eax
0x180013cf6  jz      loc_180013DA9
0x180013cfc  mov     rcx, [rdi+300h]
0x180013d03  cmp     rcx, cs:g_pAdminSid
0x180013d0a  jz      short loc_180013D25
0x180013d0c  cmp     rcx, cs:g_pEveryoneSid
0x180013d13  jz      short loc_180013D25
0x180013d15  call    WdipFree
0x180013d1a  mov     qword ptr [rdi+300h], 0
0x180013d25  mov     rcx, r12; pSid
0x180013d28  call    cs:__imp_GetLengthSid
0x180013d2e  mov     ecx, eax
0x180013d30  mov     ebx, eax
0x180013d32  call    WdipAlloc
0x180013d37  mov     [rdi+300h], rax
0x180013d3e  test    rax, rax
0x180013d41  jnz     short loc_180013D5B
0x180013d43  mov     ebx, 8007000Eh
0x180013d48  mov     dword ptr [rsp+68h+Args], 0Eh
0x180013d50  mov     r8d, 166h
0x180013d56  jmp     loc_180013C24
0x180013d5b  mov     r8, rbx; Size
0x180013d5e  xor     edx, edx; Val
0x180013d60  mov     rcx, rax; void *
0x180013d63  call    memset_0
0x180013d68  mov     rdx, [rdi+300h]; pDestinationSid
0x180013d6f  mov     r8, r12; pSourceSid
0x180013d72  mov     ecx, ebx; nDestinationSidLength
0x180013d74  call    cs:__imp_CopySid
0x180013d7a  test    eax, eax
0x180013d7c  jnz     short loc_180013DA9
0x180013d7e  call    cs:__imp_GetLastError
0x180013d84  mov     ebx, eax
0x180013d86  test    eax, eax
0x180013d88  jle     short loc_180013D93
0x180013d8a  movzx   ebx, ax
0x180013d8d  or      ebx, 80070000h
0x180013d93  test    ebx, ebx
0x180013d95  jns     short loc_180013DA9
0x180013d97  movzx   eax, bx
0x180013d9a  mov     r8d, 16Dh
0x180013da0  mov     dword ptr [rsp+68h+Args], eax
0x180013da4  jmp     loc_180013C24
0x180013da9  mov     rcx, [rdi+320h]; hObject
0x180013db0  lea     rax, [rcx-1]
0x180013db4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013db8  ja      short loc_180013DCB
0x180013dba  call    cs:__imp_CloseHandle
0x180013dc0  mov     qword ptr [rdi+320h], 0
0x180013dcb  lea     rdx, [rsp+68h+var_30]
0x180013dd0  mov     rcx, rdi
0x180013dd3  call    DpspGetResolutionSession
0x180013dd8  mov     ebx, eax
0x180013dda  test    eax, eax
0x180013ddc  jns     short loc_180013DF0
0x180013dde  movzx   eax, ax
0x180013de1  mov     r8d, 174h
0x180013de7  mov     dword ptr [rsp+68h+Args], eax
0x180013deb  jmp     loc_180013C24
0x180013df0  mov     rsi, [rsp+68h+var_30]
0x180013df5  mov     rcx, rdi
0x180013df8  mov     rdx, rsi
0x180013dfb  call    DpspAddDMToTraversedList
0x180013e00  mov     ebx, eax
0x180013e02  test    eax, eax
0x180013e04  jns     short loc_180013E18
0x180013e06  movzx   eax, ax
0x180013e09  mov     r8d, 178h
0x180013e0f  mov     dword ptr [rsp+68h+Args], eax
0x180013e13  jmp     loc_180013C24
0x180013e18  mov     [rdi+328h], rsi
0x180013e1f  mov     [r14], rdi
0x180013e22  test    rdi, rdi
0x180013e25  jz      short loc_180013E3F
0x180013e27  test    ebx, ebx
0x180013e29  jns     short loc_180013E3F
0x180013e2b  mov     edx, 4
0x180013e30  mov     r9d, ebx
0x180013e33  mov     rcx, rdi
0x180013e36  lea     r8d, [rdx+0Bh]
0x180013e3a  call    DpspCloseInstance
0x180013e3f  lea     r11, [rsp+68h+var_28]
0x180013e44  mov     eax, ebx
0x180013e46  mov     rbx, [r11+38h]
0x180013e4a  mov     rbp, [r11+40h]
0x180013e4e  mov     rsp, r11
0x180013e51  pop     r15
0x180013e53  pop     r14
0x180013e55  pop     r12
0x180013e57  pop     rdi
0x180013e58  pop     rsi
0x180013e59  retn
0x180013e5a  mov     ecx, 3
0x180013e5f  int     29h; Win8: RtlFailFast(ecx)
```
