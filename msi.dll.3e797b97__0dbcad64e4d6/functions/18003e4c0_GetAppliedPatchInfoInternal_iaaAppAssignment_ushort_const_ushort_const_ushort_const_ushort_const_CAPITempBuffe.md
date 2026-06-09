# GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &)

- ea: `0x18003e4c0`
- end: `0x18003eccd`
- name: `?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@@Z`
- size: `2061`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003c1d0`
- `0x180044bb0`
- `0x18005de50`
- `0x18005e764`

## callees

- `0x180010ac0`
- `0x180011280`
- `0x180013b7c`
- `0x18003c030`
- `0x18003e40c`
- `0x18003e4c0`
- `0x18003ecd4`
- `0x18003f930`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003e660`
- `ADVAPI32!RegCloseKey` at `0x18003e75d`
- `ADVAPI32!RegCloseKey` at `0x18003e7d0`
- `ADVAPI32!RegCloseKey` at `0x18003e84a`
- `ADVAPI32!RegCloseKey` at `0x18003e922`
- `ADVAPI32!RegCloseKey` at `0x18003e9b2`
- `ADVAPI32!RegCloseKey` at `0x18003ea1a`
- `ADVAPI32!RegCloseKey` at `0x18003ea94`
- `ADVAPI32!RegCloseKey` at `0x18003eb06`
- `ADVAPI32!RegCloseKey` at `0x18003e660`
- `ADVAPI32!RegCloseKey` at `0x18003e75d`
- `ADVAPI32!RegCloseKey` at `0x18003e7d0`
- `ADVAPI32!RegCloseKey` at `0x18003e84a`
- `ADVAPI32!RegCloseKey` at `0x18003e922`
- `ADVAPI32!RegCloseKey` at `0x18003e9b2`
- `ADVAPI32!RegCloseKey` at `0x18003ea1a`
- `ADVAPI32!RegCloseKey` at `0x18003ea94`
- `ADVAPI32!RegCloseKey` at `0x18003eb06`
- `KERNEL32!InitializeCriticalSection` at `0x18003e537`
- `KERNEL32!InitializeCriticalSection` at `0x18003e565`
- `KERNEL32!InitializeCriticalSection` at `0x18003e70e`
- `KERNEL32!InitializeCriticalSection` at `0x18003e8d1`
- `KERNEL32!InitializeCriticalSection` at `0x18003e537`
- `KERNEL32!InitializeCriticalSection` at `0x18003e565`
- `KERNEL32!InitializeCriticalSection` at `0x18003e70e`
- `KERNEL32!InitializeCriticalSection` at `0x18003e8d1`
- `KERNEL32!DeleteCriticalSection` at `0x18003e789`
- `KERNEL32!DeleteCriticalSection` at `0x18003e800`
- `KERNEL32!DeleteCriticalSection` at `0x18003e876`
- `KERNEL32!DeleteCriticalSection` at `0x18003e94e`
- `KERNEL32!DeleteCriticalSection` at `0x18003e9de`
- `KERNEL32!DeleteCriticalSection` at `0x18003ea4a`
- `KERNEL32!DeleteCriticalSection` at `0x18003eac0`
- `KERNEL32!DeleteCriticalSection` at `0x18003e789`
- `KERNEL32!DeleteCriticalSection` at `0x18003e800`
- `KERNEL32!DeleteCriticalSection` at `0x18003e876`
- `KERNEL32!DeleteCriticalSection` at `0x18003e94e`
- `KERNEL32!DeleteCriticalSection` at `0x18003e9de`
- `KERNEL32!DeleteCriticalSection` at `0x18003ea4a`
- `KERNEL32!DeleteCriticalSection` at `0x18003eac0`
- `KERNEL32!LeaveCriticalSection` at `0x18003e67c`
- `KERNEL32!LeaveCriticalSection` at `0x18003e779`
- `KERNEL32!LeaveCriticalSection` at `0x18003e7ef`
- `KERNEL32!LeaveCriticalSection` at `0x18003e866`
- `KERNEL32!LeaveCriticalSection` at `0x18003e93e`
- `KERNEL32!LeaveCriticalSection` at `0x18003e9ce`
- `KERNEL32!LeaveCriticalSection` at `0x18003ea39`
- `KERNEL32!LeaveCriticalSection` at `0x18003eab0`
- `KERNEL32!LeaveCriticalSection` at `0x18003eb25`
- `KERNEL32!LeaveCriticalSection` at `0x18003e67c`
- `KERNEL32!LeaveCriticalSection` at `0x18003e779`
- `KERNEL32!LeaveCriticalSection` at `0x18003e7ef`
- `KERNEL32!LeaveCriticalSection` at `0x18003e866`
- `KERNEL32!LeaveCriticalSection` at `0x18003e93e`
- `KERNEL32!LeaveCriticalSection` at `0x18003e9ce`
- `KERNEL32!LeaveCriticalSection` at `0x18003ea39`
- `KERNEL32!LeaveCriticalSection` at `0x18003eab0`
- `KERNEL32!LeaveCriticalSection` at `0x18003eb25`
- `KERNEL32!EnterCriticalSection` at `0x18003e64b`
- `KERNEL32!EnterCriticalSection` at `0x18003e748`
- `KERNEL32!EnterCriticalSection` at `0x18003e7ba`
- `KERNEL32!EnterCriticalSection` at `0x18003e835`
- `KERNEL32!EnterCriticalSection` at `0x18003e90d`
- `KERNEL32!EnterCriticalSection` at `0x18003e99d`
- `KERNEL32!EnterCriticalSection` at `0x18003ea04`
- `KERNEL32!EnterCriticalSection` at `0x18003ea7f`
- `KERNEL32!EnterCriticalSection` at `0x18003eaf0`
- `KERNEL32!EnterCriticalSection` at `0x18003e64b`
- `KERNEL32!EnterCriticalSection` at `0x18003e748`
- `KERNEL32!EnterCriticalSection` at `0x18003e7ba`
- `KERNEL32!EnterCriticalSection` at `0x18003e835`
- `KERNEL32!EnterCriticalSection` at `0x18003e90d`
- `KERNEL32!EnterCriticalSection` at `0x18003e99d`
- `KERNEL32!EnterCriticalSection` at `0x18003ea04`
- `KERNEL32!EnterCriticalSection` at `0x18003ea7f`
- `KERNEL32!EnterCriticalSection` at `0x18003eaf0`
- `KERNEL32!GlobalFree` at `0x18003e5ed`
- `KERNEL32!GlobalFree` at `0x18003e79e`
- `KERNEL32!GlobalFree` at `0x18003e817`
- `KERNEL32!GlobalFree` at `0x18003e88b`
- `KERNEL32!GlobalFree` at `0x18003e964`
- `KERNEL32!GlobalFree` at `0x18003e9f3`
- `KERNEL32!GlobalFree` at `0x18003ea61`
- `KERNEL32!GlobalFree` at `0x18003ead5`
- `KERNEL32!GlobalFree` at `0x18003ebb9`
- `KERNEL32!GlobalFree` at `0x18003ec5d`
- `KERNEL32!GlobalFree` at `0x18003ec72`
- `KERNEL32!GlobalFree` at `0x18003ec8a`
- `KERNEL32!GlobalFree` at `0x18003e5ed`
- `KERNEL32!GlobalFree` at `0x18003e79e`
- `KERNEL32!GlobalFree` at `0x18003e817`
- `KERNEL32!GlobalFree` at `0x18003e88b`
- `KERNEL32!GlobalFree` at `0x18003e964`
- `KERNEL32!GlobalFree` at `0x18003e9f3`
- `KERNEL32!GlobalFree` at `0x18003ea61`
- `KERNEL32!GlobalFree` at `0x18003ead5`
- `KERNEL32!GlobalFree` at `0x18003ebb9`
- `KERNEL32!GlobalFree` at `0x18003ec5d`
- `KERNEL32!GlobalFree` at `0x18003ec72`
- `KERNEL32!GlobalFree` at `0x18003ec8a`

## string_xrefs

- `0x18003e5c2`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18003eb53`: `InstallProperties`

## pseudocode

```c
__int64 __fastcall GetAppliedPatchInfoInternal(unsigned int a1, const WCHAR *a2, wchar_t *a3, __int64 a4)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  int CurrentUserStringSID; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v10; // rbx
  __int64 v11; // r9
  unsigned int AppliedPatchInfoInternal; // ebx
  __int64 v14; // r9
  HKEY v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  HGLOBAL v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  __int16 v18; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTL_CRITICAL_SECTION v19; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+90h] [rbp-70h] BYREF
  HGLOBAL v21; // [rsp+A0h] [rbp-60h]
  int v22; // [rsp+A8h] [rbp-58h]
  __int16 v23; // [rsp+B0h] [rbp-50h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v25[2]; // [rsp+E0h] [rbp-20h]
  HGLOBAL v26; // [rsp+F0h] [rbp-10h]
  int v27; // [rsp+F8h] [rbp-8h]
  __int16 v28; // [rsp+100h] [rbp+0h] BYREF
  struct _RTL_CRITICAL_SECTION v29; // [rsp+108h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+130h] [rbp+30h] BYREF
  struct _RTL_CRITICAL_SECTION v31; // [rsp+158h] [rbp+58h] BYREF
  HGLOBAL v32; // [rsp+940h] [rbp+840h]
  int v33; // [rsp+948h] [rbp+848h]
  unsigned __int16 v34[320]; // [rsp+950h] [rbp+850h] BYREF

  if ( a1 == 3 )
    return 87;
  if ( !a2 )
    return 1605;
  v23 = 0;
  *(_OWORD *)hKey = 0;
  v21 = &v23;
  v22 = 1;
  InitializeCriticalSection(&CriticalSection);
  v17 = 1;
  *(_OWORD *)v15 = 0;
  v16 = &v18;
  v18 = 0;
  InitializeCriticalSection(&v19);
  v33 = 318;
  v32 = v34;
  hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
  hMem.LockCount = 64;
  DebugInfo = 0;
  if ( a1 >= 2 )
  {
    if ( a1 == 2 )
    {
      DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"S-1-5-18";
    }
    else if ( a1 == 3 )
    {
      CurrentUserStringSID = 2;
      goto LABEL_16;
    }
    goto LABEL_6;
  }
  if ( a3 )
  {
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)a3;
    goto LABEL_6;
  }
  hMem.RecursionCount = 64;
  CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
  if ( !CurrentUserStringSID )
  {
    DebugInfo = hMem.DebugInfo;
LABEL_6:
    CurrentUserStringSID = StringCchPrintfW(
                             v34,
                             0x13Eu,
                             L"%s\\%s",
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                             DebugInfo);
  }
  if ( hMem.LockCount > 64 )
    GlobalFree(hMem.DebugInfo);
  if ( !CurrentUserStringSID )
  {
    hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
    hMem.LockCount = 1024;
    if ( (int)StringCchPrintfW((unsigned __int16 *)&hMem.OwningThread, 0x400u, L"%s\\%s\\%s", v32, L"Products", a2) < 0 )
    {
      if ( hMem.LockCount > 1024 )
        GlobalFree(hMem.DebugInfo);
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      hMem.LockCount = 1024;
      if ( v33 > 318 )
        GlobalFree(v32);
      goto LABEL_19;
    }
    v10 = hMem.DebugInfo;
    EnterCriticalSection(&CriticalSection);
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
      *(_WORD *)v21 = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    v11 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      v11 = g_samRead | 0x100;
    CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                             -2147483646,
                             v10,
                             0,
                             v11,
                             hKey);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
  }
LABEL_16:
  if ( v33 > 318 )
    GlobalFree(v32);
  if ( CurrentUserStringSID )
    goto LABEL_19;
  EnterCriticalSection(&v19);
  if ( v15[0] )
  {
    RegCloseKey(v15[0]);
    v15[0] = 0;
    *(_WORD *)v16 = 0;
  }
  LeaveCriticalSection(&v19);
  v14 = g_samRead;
  if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
    v14 = g_samRead | 0x100;
  if ( (unsigned int)((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                       hKey[0],
                       L"InstallProperties",
                       0,
                       v14,
                       v15) )
  {
LABEL_19:
    if ( a1 != 1 || !a3 || !*a3 || IsCurrentUser(a3) )
    {
      LODWORD(hMem.LockSemaphore) = 1;
      *(_OWORD *)&hMem.DebugInfo = 0;
      hMem.OwningThread = &hMem.SpinCount;
      LOWORD(hMem.SpinCount) = 0;
      InitializeCriticalSection(&v31);
      if ( !(unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(a1, a3, (WCHAR *)L"Products", a2, &hMem, 0) )
      {
        EnterCriticalSection(&v31);
        if ( hMem.DebugInfo )
        {
          RegCloseKey((HKEY)hMem.DebugInfo);
          hMem.DebugInfo = 0;
          *(_WORD *)hMem.OwningThread = 0;
        }
        LeaveCriticalSection(&v31);
        DeleteCriticalSection(&v31);
        if ( SLODWORD(hMem.LockSemaphore) > 1 )
          GlobalFree(hMem.OwningThread);
        LODWORD(hMem.LockSemaphore) = 1;
        hMem.OwningThread = &hMem.SpinCount;
        EnterCriticalSection(&v19);
        if ( v15[0] )
        {
          RegCloseKey(v15[0]);
          v15[0] = 0;
          *(_WORD *)v16 = 0;
        }
        LeaveCriticalSection(&v19);
        DeleteCriticalSection(&v19);
        if ( v17 > 1 )
          GlobalFree(v16);
        v17 = 1;
        v16 = &v18;
        EnterCriticalSection(&CriticalSection);
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
          *(_WORD *)v21 = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        DeleteCriticalSection(&CriticalSection);
        if ( v22 > 1 )
          GlobalFree(v21);
        goto LABEL_33;
      }
      EnterCriticalSection(&v31);
      if ( hMem.DebugInfo )
      {
        RegCloseKey((HKEY)hMem.DebugInfo);
        hMem.DebugInfo = 0;
        *(_WORD *)hMem.OwningThread = 0;
      }
      LeaveCriticalSection(&v31);
      DeleteCriticalSection(&v31);
      if ( SLODWORD(hMem.LockSemaphore) > 1 )
        GlobalFree(hMem.OwningThread);
    }
    EnterCriticalSection(&v19);
    if ( v15[0] )
    {
      RegCloseKey(v15[0]);
      v15[0] = 0;
      *(_WORD *)v16 = 0;
    }
    LeaveCriticalSection(&v19);
    DeleteCriticalSection(&v19);
    if ( v17 > 1 )
      GlobalFree(v16);
    v17 = 1;
    v16 = &v18;
    EnterCriticalSection(&CriticalSection);
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
      *(_WORD *)v21 = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    if ( v22 > 1 )
      GlobalFree(v21);
    return 1605;
  }
  CRegHandle::~CRegHandle((CRegHandle *)v15);
  CRegHandle::~CRegHandle((CRegHandle *)hKey);
LABEL_33:
  if ( !(unsigned __int8)IsPatchAppliedToProduct(a4, a2, a3, a1) )
    return 1647;
  v27 = 1;
  *(_OWORD *)v25 = 0;
  v26 = &v28;
  v28 = 0;
  InitializeCriticalSection(&v29);
  AppliedPatchInfoInternal = GetAppliedPatchInfoInternal(a1, a2, a3, a4);
  EnterCriticalSection(&v29);
  if ( v25[0] )
  {
    RegCloseKey(v25[0]);
    v25[0] = 0;
    *(_WORD *)v26 = 0;
  }
  LeaveCriticalSection(&v29);
  DeleteCriticalSection(&v29);
  if ( v27 > 1 )
    GlobalFree(v26);
  return AppliedPatchInfoInternal;
}

```

## disassembly

```asm
0x18003e4c0  mov     [rsp-8+arg_0], rbx
0x18003e4c5  push    rbp
0x18003e4c6  push    rsi
0x18003e4c7  push    rdi
0x18003e4c8  push    r12
0x18003e4ca  push    r13
0x18003e4cc  push    r14
0x18003e4ce  push    r15
0x18003e4d0  lea     rbp, [rsp-0AE0h]
0x18003e4d8  sub     rsp, 0BE0h
0x18003e4df  mov     rax, cs:__security_cookie
0x18003e4e6  xor     rax, rsp
0x18003e4e9  mov     [rbp+0B10h+var_40], rax
0x18003e4f0  mov     r12, [rbp+0B10h+arg_28]
0x18003e4f7  mov     r15, r9
0x18003e4fa  mov     rdi, r8
0x18003e4fd  mov     r14, rdx
0x18003e500  mov     esi, ecx
0x18003e502  cmp     ecx, 3
0x18003e505  jz      loc_18003EC4F
0x18003e50b  xor     r13d, r13d
0x18003e50e  test    rdx, rdx
0x18003e511  jz      loc_18003EAE1
0x18003e517  xorps   xmm0, xmm0
0x18003e51a  mov     [rbp+0B10h+var_B60], r13w
0x18003e51f  lea     rax, [rbp+0B10h+var_B60]
0x18003e523  movdqa  xmmword ptr [rbp+0B10h+hKey], xmm0
0x18003e528  lea     ebx, [r13+1]
0x18003e52c  mov     [rbp+0B10h+var_B70], rax
0x18003e530  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x18003e534  mov     [rbp+0B10h+var_B68], ebx
0x18003e537  call    cs:__imp_InitializeCriticalSection
0x18003e53e  nop     dword ptr [rax+rax+00h]
0x18003e543  xorps   xmm0, xmm0
0x18003e546  mov     [rsp+0C10h+var_BB8], ebx
0x18003e54a  lea     rax, [rsp+0C10h+var_BB0]
0x18003e54f  movdqa  xmmword ptr [rsp+0C10h+var_BD0], xmm0
0x18003e555  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x18003e55a  mov     [rsp+0C10h+var_BC0], rax
0x18003e55f  mov     [rsp+0C10h+var_BB0], r13w
0x18003e565  call    cs:__imp_InitializeCriticalSection
0x18003e56c  nop     dword ptr [rax+rax+00h]
0x18003e571  mov     [rbp+0B10h+var_2C8], 13Eh
0x18003e57b  lea     rax, [rbp+0B10h+var_2C0]
0x18003e582  mov     [rbp+0B10h+var_2D0], rax
0x18003e589  lea     rax, [rbp+0B10h+var_AD0]
0x18003e58d  mov     [rbp+0B10h+hMem], rax
0x18003e591  lea     r8d, [r13+40h]
0x18003e595  mov     dword ptr [rbp+0B10h+hMem+8], r8d
0x18003e599  mov     edx, r13d
0x18003e59c  mov     ecx, esi
0x18003e59e  test    esi, esi
0x18003e5a0  jz      loc_18003EBCA
0x18003e5a6  sub     ecx, ebx
0x18003e5a8  jz      loc_18003EBCA
0x18003e5ae  sub     ecx, ebx
0x18003e5b0  jnz     loc_18003EC3D
0x18003e5b6  lea     rdx, aS1518_0; "S-1-5-18"
0x18003e5bd  mov     [rsp+0C10h+var_BF0], rdx
0x18003e5c2  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e5c9  mov     edx, 13Eh; unsigned __int64
0x18003e5ce  lea     r8, aSS_0; "%s\\%s"
0x18003e5d5  lea     rcx, [rbp+0B10h+var_2C0]; unsigned __int16 *
0x18003e5dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e5e1  mov     ebx, eax
0x18003e5e3  cmp     dword ptr [rbp+0B10h+hMem+8], 40h ; '@'
0x18003e5e7  jle     short loc_18003E5F9
0x18003e5e9  mov     rcx, [rbp+0B10h+hMem]; hMem
0x18003e5ed  call    cs:__imp_GlobalFree
0x18003e5f4  nop     dword ptr [rax+rax+00h]
0x18003e5f9  test    ebx, ebx
0x18003e5fb  jnz     loc_18003E6CD
0x18003e601  mov     r9, [rbp+0B10h+var_2D0]
0x18003e608  lea     rax, [rbp+0B10h+var_AD0]
0x18003e60c  mov     [rbp+0B10h+hMem], rax
0x18003e610  lea     r8, aSSS; "%s\\%s\\%s"
0x18003e617  mov     ebx, 400h
0x18003e61c  mov     [rsp+0C10h+var_BE8], r14
0x18003e621  lea     rax, aProducts; "Products"
0x18003e628  mov     dword ptr [rbp+0B10h+hMem+8], ebx
0x18003e62b  mov     edx, ebx; unsigned __int64
0x18003e62d  mov     [rsp+0C10h+var_BF0], rax
0x18003e632  lea     rcx, [rbp+0B10h+var_AD0]; unsigned __int16 *
0x18003e636  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e63b  test    eax, eax
0x18003e63d  js      loc_18003EB8E
0x18003e643  mov     rbx, [rbp+0B10h+hMem]
0x18003e647  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x18003e64b  call    cs:__imp_EnterCriticalSection
0x18003e652  nop     dword ptr [rax+rax+00h]
0x18003e657  mov     rcx, [rbp+0B10h+hKey]; hKey
0x18003e65b  test    rcx, rcx
0x18003e65e  jz      short loc_18003E678
0x18003e660  call    cs:__imp_RegCloseKey
0x18003e667  nop     dword ptr [rax+rax+00h]
0x18003e66c  mov     rax, [rbp+0B10h+var_B70]
0x18003e670  mov     [rbp+0B10h+hKey], r13
0x18003e674  mov     [rax], r13w
0x18003e678  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x18003e67c  call    cs:__imp_LeaveCriticalSection
0x18003e683  nop     dword ptr [rax+rax+00h]
0x18003e688  cmp     cs:?g_fWoW@@3_NA, r13b; bool g_fWoW
0x18003e68f  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18003e696  jz      loc_18003EBEF
0x18003e69c  lea     rax, [rbp+0B10h+hKey]
0x18003e6a0  xor     r8d, r8d
0x18003e6a3  mov     [rsp+0C10h+var_BF0], rax
0x18003e6a8  mov     rdx, rbx
0x18003e6ab  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003e6b2  mov     rcx, 0FFFFFFFF80000002h
0x18003e6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6be  cmp     dword ptr [rbp+0B10h+hMem+8], 400h
0x18003e6c5  mov     ebx, eax
0x18003e6c7  jg      loc_18003EC6E
0x18003e6cd  cmp     [rbp+0B10h+var_2C8], 13Eh
0x18003e6d7  jg      loc_18003EC83
0x18003e6dd  test    ebx, ebx
0x18003e6df  jz      loc_18003EAEB
0x18003e6e5  mov     ebx, 1
0x18003e6ea  cmp     esi, ebx
0x18003e6ec  jz      loc_18003EC9B
0x18003e6f2  xorps   xmm0, xmm0
0x18003e6f5  mov     [rbp+0B10h+var_AC8], ebx
0x18003e6f8  lea     rax, [rbp+0B10h+var_AC0]
0x18003e6fc  movdqa  xmmword ptr [rbp+0B10h+hMem], xmm0
0x18003e701  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x18003e705  mov     [rbp+0B10h+var_AD0], rax
0x18003e709  mov     [rbp+0B10h+var_AC0], r13w
0x18003e70e  call    cs:__imp_InitializeCriticalSection
0x18003e715  nop     dword ptr [rax+rax+00h]
0x18003e71a  lea     rax, [rbp+0B10h+hMem]
0x18003e71e  mov     byte ptr [rsp+0C10h+var_BE8], r13b
0x18003e723  mov     r9, r14
0x18003e726  mov     [rsp+0C10h+var_BF0], rax
0x18003e72b  lea     r8, aProducts; "Products"
0x18003e732  mov     rdx, rdi
0x18003e735  mov     ecx, esi
0x18003e737  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18003e73c  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x18003e740  test    eax, eax
0x18003e742  jnz     loc_18003E99D
0x18003e748  call    cs:__imp_EnterCriticalSection
0x18003e74f  nop     dword ptr [rax+rax+00h]
0x18003e754  mov     rcx, [rbp+0B10h+hMem]; hKey
0x18003e758  test    rcx, rcx
0x18003e75b  jz      short loc_18003E775
0x18003e75d  call    cs:__imp_RegCloseKey
0x18003e764  nop     dword ptr [rax+rax+00h]
0x18003e769  mov     rax, [rbp+0B10h+var_AD0]
0x18003e76d  mov     [rbp+0B10h+hMem], r13
0x18003e771  mov     [rax], r13w
0x18003e775  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x18003e779  call    cs:__imp_LeaveCriticalSection
0x18003e780  nop     dword ptr [rax+rax+00h]
0x18003e785  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x18003e789  call    cs:__imp_DeleteCriticalSection
0x18003e790  nop     dword ptr [rax+rax+00h]
0x18003e795  cmp     [rbp+0B10h+var_AC8], ebx
0x18003e798  jle     short loc_18003E7AA
0x18003e79a  mov     rcx, [rbp+0B10h+var_AD0]; hMem
0x18003e79e  call    cs:__imp_GlobalFree
0x18003e7a5  nop     dword ptr [rax+rax+00h]
0x18003e7aa  lea     rax, [rbp+0B10h+var_AC0]
0x18003e7ae  mov     [rbp+0B10h+var_AC8], ebx
0x18003e7b1  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x18003e7b6  mov     [rbp+0B10h+var_AD0], rax
0x18003e7ba  call    cs:__imp_EnterCriticalSection
0x18003e7c1  nop     dword ptr [rax+rax+00h]
0x18003e7c6  mov     rcx, [rsp+0C10h+var_BD0]; hKey
0x18003e7cb  test    rcx, rcx
0x18003e7ce  jz      short loc_18003E7EA
0x18003e7d0  call    cs:__imp_RegCloseKey
0x18003e7d7  nop     dword ptr [rax+rax+00h]
0x18003e7dc  mov     rax, [rsp+0C10h+var_BC0]
0x18003e7e1  mov     [rsp+0C10h+var_BD0], r13
0x18003e7e6  mov     [rax], r13w
0x18003e7ea  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x18003e7ef  call    cs:__imp_LeaveCriticalSection
0x18003e7f6  nop     dword ptr [rax+rax+00h]
0x18003e7fb  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x18003e800  call    cs:__imp_DeleteCriticalSection
0x18003e807  nop     dword ptr [rax+rax+00h]
0x18003e80c  cmp     [rsp+0C10h+var_BB8], ebx
0x18003e810  jle     short loc_18003E823
0x18003e812  mov     rcx, [rsp+0C10h+var_BC0]; hMem
0x18003e817  call    cs:__imp_GlobalFree
0x18003e81e  nop     dword ptr [rax+rax+00h]
0x18003e823  lea     rax, [rsp+0C10h+var_BB0]
0x18003e828  mov     [rsp+0C10h+var_BB8], ebx
0x18003e82c  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x18003e830  mov     [rsp+0C10h+var_BC0], rax
0x18003e835  call    cs:__imp_EnterCriticalSection
0x18003e83c  nop     dword ptr [rax+rax+00h]
0x18003e841  mov     rcx, [rbp+0B10h+hKey]; hKey
0x18003e845  test    rcx, rcx
0x18003e848  jz      short loc_18003E862
0x18003e84a  call    cs:__imp_RegCloseKey
0x18003e851  nop     dword ptr [rax+rax+00h]
0x18003e856  mov     rax, [rbp+0B10h+var_B70]
0x18003e85a  mov     [rbp+0B10h+hKey], r13
0x18003e85e  mov     [rax], r13w
0x18003e862  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x18003e866  call    cs:__imp_LeaveCriticalSection
0x18003e86d  nop     dword ptr [rax+rax+00h]
0x18003e872  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x18003e876  call    cs:__imp_DeleteCriticalSection
0x18003e87d  nop     dword ptr [rax+rax+00h]
0x18003e882  cmp     [rbp+0B10h+var_B68], ebx
0x18003e885  jle     short loc_18003E897
0x18003e887  mov     rcx, [rbp+0B10h+var_B70]; hMem
0x18003e88b  call    cs:__imp_GlobalFree
0x18003e892  nop     dword ptr [rax+rax+00h]
0x18003e897  mov     r9d, esi
0x18003e89a  mov     byte ptr [rsp+0C10h+var_BF0], r13b
0x18003e89f  mov     r8, rdi
0x18003e8a2  mov     rdx, r14
0x18003e8a5  mov     rcx, r15
0x18003e8a8  call    ?IsPatchAppliedToProduct@@YA_NPEBG00W4iaaAppAssignment@@_N@Z; IsPatchAppliedToProduct(ushort const *,ushort const *,ushort const *,iaaAppAssignment,bool)
0x18003e8ad  test    al, al
0x18003e8af  jz      loc_18003ECC3
0x18003e8b5  xorps   xmm0, xmm0
0x18003e8b8  mov     [rbp+0B10h+var_B18], ebx
0x18003e8bb  lea     rax, [rbp+0B10h+var_B10]
0x18003e8bf  movdqa  xmmword ptr [rbp+0B10h+var_B30], xmm0
0x18003e8c4  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x18003e8c8  mov     [rbp+0B10h+var_B20], rax
0x18003e8cc  mov     [rbp+0B10h+var_B10], r13w
0x18003e8d1  call    cs:__imp_InitializeCriticalSection
0x18003e8d8  nop     dword ptr [rax+rax+00h]
0x18003e8dd  lea     rax, [rbp+0B10h+var_B30]
0x18003e8e1  mov     r9, r15
0x18003e8e4  mov     [rsp+0C10h+var_BE0], rax
0x18003e8e9  mov     r8, rdi
0x18003e8ec  mov     rax, [rbp+0B10h+arg_20]
0x18003e8f3  mov     rdx, r14
0x18003e8f6  mov     [rsp+0C10h+var_BE8], r12
0x18003e8fb  mov     ecx, esi
0x18003e8fd  mov     [rsp+0C10h+var_BF0], rax
0x18003e902  call    ?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@AEAVCRegHandle@@@Z; GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &,CRegHandle &)
0x18003e907  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x18003e90b  mov     ebx, eax
0x18003e90d  call    cs:__imp_EnterCriticalSection
0x18003e914  nop     dword ptr [rax+rax+00h]
0x18003e919  mov     rcx, [rbp+0B10h+var_B30]; hKey
0x18003e91d  test    rcx, rcx
0x18003e920  jz      short loc_18003E93A
0x18003e922  call    cs:__imp_RegCloseKey
0x18003e929  nop     dword ptr [rax+rax+00h]
0x18003e92e  mov     rcx, [rbp+0B10h+var_B20]
0x18003e932  mov     [rbp+0B10h+var_B30], r13
0x18003e936  mov     [rcx], r13w
0x18003e93a  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x18003e93e  call    cs:__imp_LeaveCriticalSection
0x18003e945  nop     dword ptr [rax+rax+00h]
0x18003e94a  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x18003e94e  call    cs:__imp_DeleteCriticalSection
0x18003e955  nop     dword ptr [rax+rax+00h]
0x18003e95a  cmp     [rbp+0B10h+var_B18], 1
0x18003e95e  jle     short loc_18003E970
0x18003e960  mov     rcx, [rbp+0B10h+var_B20]; hMem
0x18003e964  call    cs:__imp_GlobalFree
0x18003e96b  nop     dword ptr [rax+rax+00h]
0x18003e970  mov     eax, ebx
0x18003e972  mov     rcx, [rbp+0B10h+var_40]
0x18003e979  xor     rcx, rsp; StackCookie
0x18003e97c  call    __security_check_cookie
0x18003e981  mov     rbx, [rsp+0C10h+arg_0]
0x18003e989  add     rsp, 0BE0h
0x18003e990  pop     r15
0x18003e992  pop     r14
0x18003e994  pop     r13
0x18003e996  pop     r12
0x18003e998  pop     rdi
0x18003e999  pop     rsi
0x18003e99a  pop     rbp
0x18003e99b  retn
0x18003e99d  call    cs:__imp_EnterCriticalSection
0x18003e9a4  nop     dword ptr [rax+rax+00h]
0x18003e9a9  mov     rcx, [rbp+0B10h+hMem]; hKey
0x18003e9ad  test    rcx, rcx
0x18003e9b0  jz      short loc_18003E9CA
0x18003e9b2  call    cs:__imp_RegCloseKey
0x18003e9b9  nop     dword ptr [rax+rax+00h]
0x18003e9be  mov     rax, [rbp+0B10h+var_AD0]
0x18003e9c2  mov     [rbp+0B10h+hMem], r13
0x18003e9c6  mov     [rax], r13w
0x18003e9ca  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x18003e9ce  call    cs:__imp_LeaveCriticalSection
0x18003e9d5  nop     dword ptr [rax+rax+00h]
0x18003e9da  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x18003e9de  call    cs:__imp_DeleteCriticalSection
0x18003e9e5  nop     dword ptr [rax+rax+00h]
0x18003e9ea  cmp     [rbp+0B10h+var_AC8], ebx
0x18003e9ed  jle     short loc_18003E9FF
0x18003e9ef  mov     rcx, [rbp+0B10h+var_AD0]; hMem
0x18003e9f3  call    cs:__imp_GlobalFree
0x18003e9fa  nop     dword ptr [rax+rax+00h]
0x18003e9ff  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x18003ea04  call    cs:__imp_EnterCriticalSection
0x18003ea0b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
