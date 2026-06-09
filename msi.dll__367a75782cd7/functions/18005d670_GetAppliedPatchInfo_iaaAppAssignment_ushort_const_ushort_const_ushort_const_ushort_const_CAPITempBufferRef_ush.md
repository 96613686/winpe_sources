# GetAppliedPatchInfo(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &)

- ea: `0x18005d670`
- end: `0x18005de74`
- name: `?GetAppliedPatchInfo@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@@Z`
- size: `2052`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005a51c`

## callees

- `0x180015950`
- `0x180017a84`
- `0x180017b28`
- `0x180022120`
- `0x1800227d0`
- `0x1800250d4`
- `0x18005d670`
- `0x18005de7c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18005d961`
- `ADVAPI32!RegCloseKey` at `0x18005da4c`
- `ADVAPI32!RegCloseKey` at `0x18005daab`
- `ADVAPI32!RegCloseKey` at `0x18005db11`
- `ADVAPI32!RegCloseKey` at `0x18005db9c`
- `ADVAPI32!RegCloseKey` at `0x18005dbec`
- `ADVAPI32!RegCloseKey` at `0x18005dc52`
- `ADVAPI32!RegCloseKey` at `0x18005dcac`
- `ADVAPI32!RegCloseKey` at `0x18005d961`
- `ADVAPI32!RegCloseKey` at `0x18005da4c`
- `ADVAPI32!RegCloseKey` at `0x18005daab`
- `ADVAPI32!RegCloseKey` at `0x18005db11`
- `ADVAPI32!RegCloseKey` at `0x18005db9c`
- `ADVAPI32!RegCloseKey` at `0x18005dbec`
- `ADVAPI32!RegCloseKey` at `0x18005dc52`
- `ADVAPI32!RegCloseKey` at `0x18005dcac`
- `KERNEL32!InitializeCriticalSection` at `0x18005d857`
- `KERNEL32!InitializeCriticalSection` at `0x18005d884`
- `KERNEL32!InitializeCriticalSection` at `0x18005da09`
- `KERNEL32!InitializeCriticalSection` at `0x18005d857`
- `KERNEL32!InitializeCriticalSection` at `0x18005d884`
- `KERNEL32!InitializeCriticalSection` at `0x18005da09`
- `KERNEL32!DeleteCriticalSection` at `0x18005da71`
- `KERNEL32!DeleteCriticalSection` at `0x18005dad4`
- `KERNEL32!DeleteCriticalSection` at `0x18005db36`
- `KERNEL32!DeleteCriticalSection` at `0x18005dbc1`
- `KERNEL32!DeleteCriticalSection` at `0x18005dc15`
- `KERNEL32!DeleteCriticalSection` at `0x18005dc77`
- `KERNEL32!DeleteCriticalSection` at `0x18005da71`
- `KERNEL32!DeleteCriticalSection` at `0x18005dad4`
- `KERNEL32!DeleteCriticalSection` at `0x18005db36`
- `KERNEL32!DeleteCriticalSection` at `0x18005dbc1`
- `KERNEL32!DeleteCriticalSection` at `0x18005dc15`
- `KERNEL32!DeleteCriticalSection` at `0x18005dc77`
- `KERNEL32!LeaveCriticalSection` at `0x18005d97c`
- `KERNEL32!LeaveCriticalSection` at `0x18005da67`
- `KERNEL32!LeaveCriticalSection` at `0x18005dac9`
- `KERNEL32!LeaveCriticalSection` at `0x18005db2c`
- `KERNEL32!LeaveCriticalSection` at `0x18005dbb7`
- `KERNEL32!LeaveCriticalSection` at `0x18005dc0a`
- `KERNEL32!LeaveCriticalSection` at `0x18005dc6d`
- `KERNEL32!LeaveCriticalSection` at `0x18005dcca`
- `KERNEL32!LeaveCriticalSection` at `0x18005d97c`
- `KERNEL32!LeaveCriticalSection` at `0x18005da67`
- `KERNEL32!LeaveCriticalSection` at `0x18005dac9`
- `KERNEL32!LeaveCriticalSection` at `0x18005db2c`
- `KERNEL32!LeaveCriticalSection` at `0x18005dbb7`
- `KERNEL32!LeaveCriticalSection` at `0x18005dc0a`
- `KERNEL32!LeaveCriticalSection` at `0x18005dc6d`
- `KERNEL32!LeaveCriticalSection` at `0x18005dcca`
- `KERNEL32!EnterCriticalSection` at `0x18005d952`
- `KERNEL32!EnterCriticalSection` at `0x18005da3d`
- `KERNEL32!EnterCriticalSection` at `0x18005da9b`
- `KERNEL32!EnterCriticalSection` at `0x18005db02`
- `KERNEL32!EnterCriticalSection` at `0x18005db8d`
- `KERNEL32!EnterCriticalSection` at `0x18005dbdc`
- `KERNEL32!EnterCriticalSection` at `0x18005dc43`
- `KERNEL32!EnterCriticalSection` at `0x18005dc9c`
- `KERNEL32!EnterCriticalSection` at `0x18005d952`
- `KERNEL32!EnterCriticalSection` at `0x18005da3d`
- `KERNEL32!EnterCriticalSection` at `0x18005da9b`
- `KERNEL32!EnterCriticalSection` at `0x18005db02`
- `KERNEL32!EnterCriticalSection` at `0x18005db8d`
- `KERNEL32!EnterCriticalSection` at `0x18005dbdc`
- `KERNEL32!EnterCriticalSection` at `0x18005dc43`
- `KERNEL32!EnterCriticalSection` at `0x18005dc9c`
- `KERNEL32!GlobalFree` at `0x18005d8f8`
- `KERNEL32!GlobalFree` at `0x18005da81`
- `KERNEL32!GlobalFree` at `0x18005dae6`
- `KERNEL32!GlobalFree` at `0x18005dbd1`
- `KERNEL32!GlobalFree` at `0x18005dc27`
- `KERNEL32!GlobalFree` at `0x18005dc87`
- `KERNEL32!GlobalFree` at `0x18005dd5b`
- `KERNEL32!GlobalFree` at `0x18005de06`
- `KERNEL32!GlobalFree` at `0x18005de15`
- `KERNEL32!GlobalFree` at `0x18005de27`
- `KERNEL32!GlobalFree` at `0x18005de5f`
- `KERNEL32!GlobalFree` at `0x18005d8f8`
- `KERNEL32!GlobalFree` at `0x18005da81`
- `KERNEL32!GlobalFree` at `0x18005dae6`
- `KERNEL32!GlobalFree` at `0x18005dbd1`
- `KERNEL32!GlobalFree` at `0x18005dc27`
- `KERNEL32!GlobalFree` at `0x18005dc87`
- `KERNEL32!GlobalFree` at `0x18005dd5b`
- `KERNEL32!GlobalFree` at `0x18005de06`
- `KERNEL32!GlobalFree` at `0x18005de15`
- `KERNEL32!GlobalFree` at `0x18005de27`
- `KERNEL32!GlobalFree` at `0x18005de5f`

## string_xrefs

- `0x18005d782`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18005d8cd`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18005dcf2`: `InstallProperties`

## pseudocode

```c
__int64 __fastcall GetAppliedPatchInfo(unsigned int a1, _WORD *a2, wchar_t *a3, _WORD *a4, __int64 a5)
{
  int v9; // eax
  __int64 v10; // rcx
  __int64 *v12; // rdx
  unsigned int v13; // r9d
  __int64 *v14; // r8
  WCHAR *v15; // r10
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  __int16 *v19; // r9
  unsigned int v20; // r8d
  __int64 v21; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int CurrentUserStringSID; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v24; // rbx
  __int64 v25; // r9
  __int64 v26; // r9
  struct _RTL_CRITICAL_SECTION v27; // [rsp+30h] [rbp-D0h] BYREF
  struct _RTL_CRITICAL_SECTION v28; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+A8h] [rbp-58h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_CRITICAL_SECTION v32; // [rsp+F8h] [rbp-8h] BYREF
  HGLOBAL v33; // [rsp+8E0h] [rbp+7E0h]
  int v34; // [rsp+8E8h] [rbp+7E8h]
  unsigned __int16 v35[320]; // [rsp+8F0h] [rbp+7F0h] BYREF
  WCHAR v36; // [rsp+B70h] [rbp+A70h] BYREF
  __int128 v37; // [rsp+B72h] [rbp+A72h]
  __int128 v38; // [rsp+B82h] [rbp+A82h]
  __int128 v39; // [rsp+B92h] [rbp+A92h]
  __int128 v40; // [rsp+BA2h] [rbp+AA2h]
  __int16 v41; // [rsp+BC0h] [rbp+AC0h] BYREF
  __int128 v42; // [rsp+BC2h] [rbp+AC2h]
  __int128 v43; // [rsp+BD2h] [rbp+AD2h]
  __int128 v44; // [rsp+BE2h] [rbp+AE2h]
  __int128 v45; // [rsp+BF2h] [rbp+AF2h]

  if ( !a2 || !a4 || !a5 || a1 == 3 )
    return 87;
  v9 = 0;
  v36 = 0;
  v37 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  while ( v9 < 38 )
  {
    v10 = v9++;
    if ( !a2[v10] )
      return 87;
  }
  if ( *a2 != 123 || a2[37] != 125 )
    return 87;
  v12 = qword_18026F6C0;
  v13 = 0;
  v14 = qword_18026F6C0;
  v15 = &v36;
  while ( v14 < (__int64 *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData" )
  {
    if ( v13 >= 0x21 )
      return 87;
    v16 = *(unsigned __int8 *)v14;
    v14 = (__int64 *)((char *)v14 + 1);
    *v15++ = a2[v16];
    ++v13;
  }
  if ( v13 >= 0x21 )
    return 87;
  *v15 = 0;
  v17 = 0;
  while ( v17 < 38 )
  {
    v18 = v17++;
    if ( !a4[v18] )
      return 87;
  }
  if ( *a4 != 123 || a4[37] != 125 )
    return 87;
  v19 = &v41;
  v20 = 0;
  while ( v12 < (__int64 *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData" )
  {
    if ( v20 >= 0x21 )
      return 87;
    v21 = *(unsigned __int8 *)v12;
    v12 = (__int64 *)((char *)v12 + 1);
    *v19++ = a4[v21];
    ++v20;
  }
  if ( v20 >= 0x21 )
    return 87;
  LODWORD(hKey.LockSemaphore) = 1;
  *v19 = 0;
  hKey.OwningThread = &hKey.SpinCount;
  LOWORD(hKey.SpinCount) = 0;
  *(_OWORD *)&hKey.DebugInfo = 0;
  InitializeCriticalSection(&CriticalSection);
  LODWORD(v27.LockSemaphore) = 1;
  v27.OwningThread = &v27.SpinCount;
  LOWORD(v27.SpinCount) = 0;
  *(_OWORD *)&v27.DebugInfo = 0;
  InitializeCriticalSection(&v28);
  v34 = 318;
  v33 = v35;
  hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
  hMem.LockCount = 64;
  if ( a1 == 2 )
  {
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"S-1-5-18";
    goto LABEL_29;
  }
  DebugInfo = 0;
  if ( a1 > 1 )
  {
    if ( a1 == 3 )
    {
      CurrentUserStringSID = 2;
      goto LABEL_38;
    }
LABEL_29:
    CurrentUserStringSID = StringCchPrintfW(
                             v35,
                             0x13Eu,
                             L"%s\\%s",
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                             DebugInfo);
    if ( hMem.LockCount <= 64 )
      goto LABEL_31;
    goto LABEL_30;
  }
  if ( a3 )
  {
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)a3;
    goto LABEL_29;
  }
  hMem.RecursionCount = 64;
  CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
  if ( !CurrentUserStringSID )
  {
    DebugInfo = hMem.DebugInfo;
    goto LABEL_29;
  }
  if ( hMem.LockCount > 64 )
LABEL_30:
    GlobalFree(hMem.DebugInfo);
LABEL_31:
  if ( !CurrentUserStringSID )
  {
    hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
    hMem.LockCount = 1024;
    if ( (int)StringCchPrintfW((unsigned __int16 *)&hMem.OwningThread, 0x400u, L"%s\\%s\\%s", v33, L"Products", &v36) < 0 )
    {
      if ( hMem.LockCount > 1024 )
        GlobalFree(hMem.DebugInfo);
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      hMem.LockCount = 1024;
      if ( v34 > 318 )
        GlobalFree(v33);
      goto LABEL_41;
    }
    v24 = hMem.DebugInfo;
    EnterCriticalSection(&CriticalSection);
    if ( hKey.DebugInfo )
    {
      RegCloseKey((HKEY)hKey.DebugInfo);
      hKey.DebugInfo = 0;
      *(_WORD *)hKey.OwningThread = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    v25 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      LODWORD(v25) = g_samRead | 0x100;
    CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                             -2147483646,
                             v24,
                             0,
                             v25,
                             &hKey);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
  }
LABEL_38:
  if ( v34 > 318 )
    GlobalFree(v33);
  if ( !CurrentUserStringSID )
  {
    EnterCriticalSection(&v28);
    if ( v27.DebugInfo )
    {
      RegCloseKey((HKEY)v27.DebugInfo);
      v27.DebugInfo = 0;
      *(_WORD *)v27.OwningThread = 0;
    }
    LeaveCriticalSection(&v28);
    v26 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      LODWORD(v26) = g_samRead | 0x100;
    if ( !(unsigned int)((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const unsigned __int16 *, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                          hKey.DebugInfo,
                          L"InstallProperties",
                          0,
                          v26,
                          &v27) )
    {
      CRegHandle::~CRegHandle(&v27);
      CRegHandle::~CRegHandle(&hKey);
LABEL_55:
      if ( (unsigned __int8)PatchWasRoamed(a1, &v36, a3, &v41) )
        return 1647;
      else
        return GetAppliedPatchInfoInternal(a1, &v36, a3, (__int64)&v41);
    }
  }
LABEL_41:
  if ( a1 != 1 || !a3 || !*a3 || IsCurrentUser(a3) )
  {
    LODWORD(hMem.LockSemaphore) = 1;
    hMem.OwningThread = &hMem.SpinCount;
    LOWORD(hMem.SpinCount) = 0;
    *(_OWORD *)&hMem.DebugInfo = 0;
    InitializeCriticalSection(&v32);
    if ( !(unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(a1, a3, (WCHAR *)L"Products", &v36, &hMem, 0) )
    {
      EnterCriticalSection(&v32);
      if ( hMem.DebugInfo )
      {
        RegCloseKey((HKEY)hMem.DebugInfo);
        hMem.DebugInfo = 0;
        *(_WORD *)hMem.OwningThread = 0;
      }
      LeaveCriticalSection(&v32);
      DeleteCriticalSection(&v32);
      if ( SLODWORD(hMem.LockSemaphore) > 1 )
        GlobalFree(hMem.OwningThread);
      LODWORD(hMem.LockSemaphore) = 1;
      hMem.OwningThread = &hMem.SpinCount;
      EnterCriticalSection(&v28);
      if ( v27.DebugInfo )
      {
        RegCloseKey((HKEY)v27.DebugInfo);
        v27.DebugInfo = 0;
        *(_WORD *)v27.OwningThread = 0;
      }
      LeaveCriticalSection(&v28);
      DeleteCriticalSection(&v28);
      if ( SLODWORD(v27.LockSemaphore) > 1 )
        GlobalFree(v27.OwningThread);
      LODWORD(v27.LockSemaphore) = 1;
      v27.OwningThread = &v27.SpinCount;
      EnterCriticalSection(&CriticalSection);
      if ( hKey.DebugInfo )
      {
        RegCloseKey((HKEY)hKey.DebugInfo);
        hKey.DebugInfo = 0;
        *(_WORD *)hKey.OwningThread = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      DeleteCriticalSection(&CriticalSection);
      if ( SLODWORD(hKey.LockSemaphore) > 1 )
        GlobalFree(hKey.OwningThread);
      goto LABEL_55;
    }
    EnterCriticalSection(&v32);
    if ( hMem.DebugInfo )
    {
      RegCloseKey((HKEY)hMem.DebugInfo);
      hMem.DebugInfo = 0;
      *(_WORD *)hMem.OwningThread = 0;
    }
    LeaveCriticalSection(&v32);
    DeleteCriticalSection(&v32);
    if ( SLODWORD(hMem.LockSemaphore) > 1 )
      GlobalFree(hMem.OwningThread);
  }
  EnterCriticalSection(&v28);
  if ( v27.DebugInfo )
  {
    RegCloseKey((HKEY)v27.DebugInfo);
    v27.DebugInfo = 0;
    *(_WORD *)v27.OwningThread = 0;
  }
  LeaveCriticalSection(&v28);
  DeleteCriticalSection(&v28);
  if ( SLODWORD(v27.LockSemaphore) > 1 )
    GlobalFree(v27.OwningThread);
  LODWORD(v27.LockSemaphore) = 1;
  v27.OwningThread = &v27.SpinCount;
  EnterCriticalSection(&CriticalSection);
  if ( hKey.DebugInfo )
  {
    RegCloseKey((HKEY)hKey.DebugInfo);
    hKey.DebugInfo = 0;
    *(_WORD *)hKey.OwningThread = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( SLODWORD(hKey.LockSemaphore) > 1 )
    GlobalFree(hKey.OwningThread);
  return 1605;
}

```

## disassembly

```asm
0x18005d670  mov     [rsp-8+arg_0], rbx
0x18005d675  mov     [rsp-8+arg_8], rsi
0x18005d67a  push    rbp
0x18005d67b  push    rdi
0x18005d67c  push    r12
0x18005d67e  push    r14
0x18005d680  push    r15
0x18005d682  lea     rbp, [rsp-0B20h]
0x18005d68a  sub     rsp, 0C20h
0x18005d691  mov     rax, cs:__security_cookie
0x18005d698  xor     rax, rsp
0x18005d69b  mov     [rbp+0B40h+var_30], rax
0x18005d6a2  mov     r15, [rbp+0B40h+arg_28]
0x18005d6a9  mov     rbx, r9
0x18005d6ac  mov     r14, r8
0x18005d6af  mov     r11, rdx
0x18005d6b2  mov     esi, ecx
0x18005d6b4  test    rdx, rdx
0x18005d6b7  jz      short loc_18005D731
0x18005d6b9  test    rbx, rbx
0x18005d6bc  jz      short loc_18005D731
0x18005d6be  mov     rdi, [rbp+0B40h+arg_20]
0x18005d6c5  test    rdi, rdi
0x18005d6c8  jz      short loc_18005D731
0x18005d6ca  cmp     ecx, 3
0x18005d6cd  jz      short loc_18005D731
0x18005d6cf  xorps   xmm0, xmm0
0x18005d6d2  xor     eax, eax
0x18005d6d4  mov     [rbp+0B40h+var_D0], ax
0x18005d6db  movups  [rbp+0B40h+var_CE], xmm0
0x18005d6e2  mov     [rbp+0B40h+var_80], ax
0x18005d6e9  movups  [rbp+0B40h+var_BE], xmm0
0x18005d6f0  movups  [rbp+0B40h+var_AE], xmm0
0x18005d6f7  movups  [rbp+0B40h+var_9E], xmm0
0x18005d6fe  movups  [rbp+0B40h+var_7E], xmm0
0x18005d705  movups  [rbp+0B40h+var_6E], xmm0
0x18005d70c  movups  [rbp+0B40h+var_5E], xmm0
0x18005d713  movups  [rbp+0B40h+var_4E], xmm0
0x18005d71a  nop     word ptr [rax+rax+00h]
0x18005d720  cmp     eax, 26h ; '&'
0x18005d723  jge     short loc_18005D761
0x18005d725  movsxd  rcx, eax
0x18005d728  inc     eax
0x18005d72a  cmp     word ptr [rdx+rcx*2], 0
0x18005d72f  jnz     short loc_18005D720
0x18005d731  mov     eax, 57h ; 'W'
0x18005d736  mov     rcx, [rbp+0B40h+var_30]
0x18005d73d  xor     rcx, rsp; StackCookie
0x18005d740  call    __security_check_cookie
0x18005d745  lea     r11, [rsp+0C40h+var_20]
0x18005d74d  mov     rbx, [r11+30h]
0x18005d751  mov     rsi, [r11+38h]
0x18005d755  mov     rsp, r11
0x18005d758  pop     r15
0x18005d75a  pop     r14
0x18005d75c  pop     r12
0x18005d75e  pop     rdi
0x18005d75f  pop     rbp
0x18005d760  retn
0x18005d761  cmp     word ptr [rdx], 7Bh ; '{'
0x18005d765  jnz     short loc_18005D731
0x18005d767  cmp     word ptr [rdx+4Ah], 7Dh ; '}'
0x18005d76c  jnz     short loc_18005D731
0x18005d76e  lea     rdx, qword_18026F6C0
0x18005d775  xor     r9d, r9d
0x18005d778  mov     r8, rdx
0x18005d77b  lea     r10, [rbp+0B40h+var_D0]
0x18005d782  lea     r12, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d789  nop     dword ptr [rax+00000000h]
0x18005d790  cmp     r8, r12
0x18005d793  jnb     short loc_18005D7B4
0x18005d795  cmp     r9d, 21h ; '!'
0x18005d799  jnb     short loc_18005D731
0x18005d79b  movzx   eax, byte ptr [r8]
0x18005d79f  inc     r8
0x18005d7a2  movzx   ecx, word ptr [r11+rax*2]
0x18005d7a7  mov     [r10], cx
0x18005d7ab  add     r10, 2
0x18005d7af  inc     r9d
0x18005d7b2  jmp     short loc_18005D790
0x18005d7b4  cmp     r9d, 21h ; '!'
0x18005d7b8  jnb     loc_18005D731
0x18005d7be  xor     eax, eax
0x18005d7c0  mov     [r10], ax
0x18005d7c4  xor     ecx, ecx
0x18005d7c6  cmp     ecx, 26h ; '&'
0x18005d7c9  jge     short loc_18005D7DC
0x18005d7cb  movsxd  rax, ecx
0x18005d7ce  inc     ecx
0x18005d7d0  cmp     word ptr [rbx+rax*2], 0
0x18005d7d5  jnz     short loc_18005D7C6
0x18005d7d7  jmp     loc_18005D731
0x18005d7dc  cmp     word ptr [rbx], 7Bh ; '{'
0x18005d7e0  jnz     loc_18005D731
0x18005d7e6  cmp     word ptr [rbx+4Ah], 7Dh ; '}'
0x18005d7eb  jnz     loc_18005D731
0x18005d7f1  lea     r9, [rbp+0B40h+var_80]
0x18005d7f8  xor     r8d, r8d
0x18005d7fb  nop     dword ptr [rax+rax+00h]
0x18005d800  cmp     rdx, r12
0x18005d803  jnb     short loc_18005D826
0x18005d805  cmp     r8d, 21h ; '!'
0x18005d809  jnb     loc_18005D731
0x18005d80f  movzx   eax, byte ptr [rdx]
0x18005d812  inc     rdx
0x18005d815  movzx   ecx, word ptr [rbx+rax*2]
0x18005d819  mov     [r9], cx
0x18005d81d  add     r9, 2
0x18005d821  inc     r8d
0x18005d824  jmp     short loc_18005D800
0x18005d826  cmp     r8d, 21h ; '!'
0x18005d82a  jnb     loc_18005D731
0x18005d830  xor     eax, eax
0x18005d832  mov     [rbp+0B40h+var_BA8], 1
0x18005d839  mov     [r9], ax
0x18005d83d  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005d841  lea     rax, [rbp+0B40h+var_BA0]
0x18005d845  xorps   xmm0, xmm0
0x18005d848  mov     [rbp+0B40h+var_BB0], rax
0x18005d84c  xor     eax, eax
0x18005d84e  mov     [rbp+0B40h+var_BA0], ax
0x18005d852  movdqa  xmmword ptr [rbp+0B40h+hKey], xmm0
0x18005d857  call    cs:__imp_InitializeCriticalSection
0x18005d85d  lea     rax, [rsp+0C40h+var_BF0]
0x18005d862  mov     [rsp+0C40h+var_BF8], 1
0x18005d86a  mov     [rsp+0C40h+var_C00], rax
0x18005d86f  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005d874  xor     eax, eax
0x18005d876  xorps   xmm0, xmm0
0x18005d879  mov     [rsp+0C40h+var_BF0], ax
0x18005d87e  movdqa  xmmword ptr [rsp+0C40h+var_C10], xmm0
0x18005d884  call    cs:__imp_InitializeCriticalSection
0x18005d88a  mov     [rbp+0B40h+var_358], 13Eh
0x18005d894  lea     rax, [rbp+0B40h+var_350]
0x18005d89b  mov     [rbp+0B40h+var_360], rax
0x18005d8a2  lea     rax, [rbp+0B40h+var_B60]
0x18005d8a6  mov     [rbp+0B40h+hMem], rax
0x18005d8aa  lea     r12, aProducts; "Products"
0x18005d8b1  mov     dword ptr [rbp+0B40h+hMem+8], 40h ; '@'
0x18005d8b8  cmp     esi, 2
0x18005d8bb  jnz     loc_18005DD66
0x18005d8c1  lea     rcx, aS1518; "S-1-5-18"
0x18005d8c8  mov     [rsp+0C40h+var_C20], rcx
0x18005d8cd  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d8d4  lea     rcx, [rbp+0B40h+var_350]; unsigned __int16 *
0x18005d8db  mov     edx, 13Eh; unsigned __int64
0x18005d8e0  lea     r8, aSS_0; "%s\\%s"
0x18005d8e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d8ec  cmp     dword ptr [rbp+0B40h+hMem+8], 40h ; '@'
0x18005d8f0  mov     ebx, eax
0x18005d8f2  jle     short loc_18005D8FE
0x18005d8f4  mov     rcx, [rbp+0B40h+hMem]; hMem
0x18005d8f8  call    cs:__imp_GlobalFree
0x18005d8fe  test    ebx, ebx
0x18005d900  jnz     loc_18005D9C7
0x18005d906  mov     r9, [rbp+0B40h+var_360]
0x18005d90d  lea     rax, [rbp+0B40h+var_B60]
0x18005d911  mov     [rbp+0B40h+hMem], rax
0x18005d915  lea     r8, aSSS; "%s\\%s\\%s"
0x18005d91c  lea     rax, [rbp+0B40h+var_D0]
0x18005d923  mov     dword ptr [rbp+0B40h+hMem+8], 400h
0x18005d92a  mov     [rsp+0C40h+var_C18], rax
0x18005d92f  lea     rcx, [rbp+0B40h+var_B60]; unsigned __int16 *
0x18005d933  mov     edx, 400h; unsigned __int64
0x18005d938  mov     [rsp+0C40h+var_C20], r12
0x18005d93d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d942  test    eax, eax
0x18005d944  js      loc_18005DD28
0x18005d94a  mov     rbx, [rbp+0B40h+hMem]
0x18005d94e  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005d952  call    cs:__imp_EnterCriticalSection
0x18005d958  mov     rcx, [rbp+0B40h+hKey]; hKey
0x18005d95c  test    rcx, rcx
0x18005d95f  jz      short loc_18005D978
0x18005d961  call    cs:__imp_RegCloseKey
0x18005d967  mov     rax, [rbp+0B40h+var_BB0]
0x18005d96b  xor     ecx, ecx
0x18005d96d  mov     [rbp+0B40h+hKey], 0
0x18005d975  mov     [rax], cx
0x18005d978  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005d97c  call    cs:__imp_LeaveCriticalSection
0x18005d982  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18005d989  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18005d990  jz      loc_18005DD97
0x18005d996  lea     rax, [rbp+0B40h+hKey]
0x18005d99a  xor     r8d, r8d
0x18005d99d  mov     [rsp+0C40h+var_C20], rax
0x18005d9a2  mov     rdx, rbx
0x18005d9a5  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18005d9ac  mov     rcx, 0FFFFFFFF80000002h
0x18005d9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9b8  cmp     dword ptr [rbp+0B40h+hMem+8], 400h
0x18005d9bf  mov     ebx, eax
0x18005d9c1  jg      loc_18005DE11
0x18005d9c7  cmp     [rbp+0B40h+var_358], 13Eh
0x18005d9d1  jg      loc_18005DE20
0x18005d9d7  test    ebx, ebx
0x18005d9d9  jz      loc_18005DC97
0x18005d9df  cmp     esi, 1
0x18005d9e2  jz      loc_18005DE32
0x18005d9e8  lea     rax, [rbp+0B40h+var_B50]
0x18005d9ec  mov     [rbp+0B40h+var_B58], 1
0x18005d9f3  mov     [rbp+0B40h+var_B60], rax
0x18005d9f7  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005d9fb  xor     eax, eax
0x18005d9fd  xorps   xmm0, xmm0
0x18005da00  mov     [rbp+0B40h+var_B50], ax
0x18005da04  movdqa  xmmword ptr [rbp+0B40h+hMem], xmm0
0x18005da09  call    cs:__imp_InitializeCriticalSection
0x18005da0f  lea     rax, [rbp+0B40h+hMem]
0x18005da13  mov     byte ptr [rsp+0C40h+var_C18], 0
0x18005da18  lea     r9, [rbp+0B40h+var_D0]
0x18005da1f  mov     [rsp+0C40h+var_C20], rax
0x18005da24  mov     r8, r12
0x18005da27  mov     rdx, r14
0x18005da2a  mov     ecx, esi
0x18005da2c  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18005da31  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005da35  test    eax, eax
0x18005da37  jnz     loc_18005DB8D
0x18005da3d  call    cs:__imp_EnterCriticalSection
0x18005da43  mov     rcx, [rbp+0B40h+hMem]; hKey
0x18005da47  test    rcx, rcx
0x18005da4a  jz      short loc_18005DA63
0x18005da4c  call    cs:__imp_RegCloseKey
0x18005da52  mov     rax, [rbp+0B40h+var_B60]
0x18005da56  xor     ecx, ecx
0x18005da58  mov     [rbp+0B40h+hMem], 0
0x18005da60  mov     [rax], cx
0x18005da63  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005da67  call    cs:__imp_LeaveCriticalSection
0x18005da6d  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005da71  call    cs:__imp_DeleteCriticalSection
0x18005da77  cmp     [rbp+0B40h+var_B58], 1
0x18005da7b  jle     short loc_18005DA87
0x18005da7d  mov     rcx, [rbp+0B40h+var_B60]; hMem
0x18005da81  call    cs:__imp_GlobalFree
0x18005da87  lea     rax, [rbp+0B40h+var_B50]
0x18005da8b  mov     [rbp+0B40h+var_B58], 1
0x18005da92  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005da97  mov     [rbp+0B40h+var_B60], rax
0x18005da9b  call    cs:__imp_EnterCriticalSection
0x18005daa1  mov     rcx, [rsp+0C40h+var_C10]; hKey
0x18005daa6  test    rcx, rcx
0x18005daa9  jz      short loc_18005DAC4
0x18005daab  call    cs:__imp_RegCloseKey
0x18005dab1  mov     rax, [rsp+0C40h+var_C00]
0x18005dab6  xor     ecx, ecx
0x18005dab8  mov     [rsp+0C40h+var_C10], 0
0x18005dac1  mov     [rax], cx
0x18005dac4  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005dac9  call    cs:__imp_LeaveCriticalSection
0x18005dacf  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005dad4  call    cs:__imp_DeleteCriticalSection
0x18005dada  cmp     [rsp+0C40h+var_BF8], 1
0x18005dadf  jle     short loc_18005DAEC
0x18005dae1  mov     rcx, [rsp+0C40h+var_C00]; hMem
0x18005dae6  call    cs:__imp_GlobalFree
0x18005daec  lea     rax, [rsp+0C40h+var_BF0]
0x18005daf1  mov     [rsp+0C40h+var_BF8], 1
0x18005daf9  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005dafd  mov     [rsp+0C40h+var_C00], rax
0x18005db02  call    cs:__imp_EnterCriticalSection
0x18005db08  mov     rcx, [rbp+0B40h+hKey]; hKey
0x18005db0c  test    rcx, rcx
0x18005db0f  jz      short loc_18005DB28
0x18005db11  call    cs:__imp_RegCloseKey
0x18005db17  mov     rax, [rbp+0B40h+var_BB0]
0x18005db1b  xor     ecx, ecx
0x18005db1d  mov     [rbp+0B40h+hKey], 0
0x18005db25  mov     [rax], cx
0x18005db28  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005db2c  call    cs:__imp_LeaveCriticalSection
0x18005db32  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005db36  call    cs:__imp_DeleteCriticalSection
0x18005db3c  cmp     [rbp+0B40h+var_BA8], 1
0x18005db40  jg      loc_18005DE5B
0x18005db46  lea     r9, [rbp+0B40h+var_80]
0x18005db4d  mov     r8, r14
0x18005db50  lea     rdx, [rbp+0B40h+var_D0]
0x18005db57  mov     ecx, esi
0x18005db59  call    ?PatchWasRoamed@@YA_NW4iaaAppAssignment@@PEBG11@Z; PatchWasRoamed(iaaAppAssignment,ushort const *,ushort const *,ushort const *)
0x18005db5e  test    al, al
0x18005db60  jnz     loc_18005DE6A
0x18005db66  mov     [rsp+0C40h+var_C18], r15
0x18005db6b  lea     r9, [rbp+0B40h+var_80]
0x18005db72  mov     r8, r14
0x18005db75  mov     [rsp+0C40h+var_C20], rdi
0x18005db7a  lea     rdx, [rbp+0B40h+var_D0]
0x18005db81  mov     ecx, esi
0x18005db83  call    ?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@@Z; GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &)
0x18005db88  jmp     loc_18005D736
0x18005db8d  call    cs:__imp_EnterCriticalSection
0x18005db93  mov     rcx, [rbp+0B40h+hMem]; hKey
0x18005db97  test    rcx, rcx
0x18005db9a  jz      short loc_18005DBB3
0x18005db9c  call    cs:__imp_RegCloseKey
0x18005dba2  mov     rax, [rbp+0B40h+var_B60]
0x18005dba6  xor     ecx, ecx
0x18005dba8  mov     [rbp+0B40h+hMem], 0
  ... truncated ...
```
