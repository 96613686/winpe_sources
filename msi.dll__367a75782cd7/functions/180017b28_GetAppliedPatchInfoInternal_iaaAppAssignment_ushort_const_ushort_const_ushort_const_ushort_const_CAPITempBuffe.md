# GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &)

- ea: `0x180017b28`
- end: `0x180018208`
- name: `?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@@Z`
- size: `1760`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015ac0`
- `0x18001cca0`
- `0x18005d670`
- `0x18005de7c`

## callees

- `0x180015950`
- `0x180017a84`
- `0x180017b28`
- `0x180018210`
- `0x180018d10`
- `0x180022120`
- `0x1800227d0`
- `0x1800250d4`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180017cb0`
- `ADVAPI32!RegCloseKey` at `0x180017d95`
- `ADVAPI32!RegCloseKey` at `0x180017dea`
- `ADVAPI32!RegCloseKey` at `0x180017e46`
- `ADVAPI32!RegCloseKey` at `0x180017efa`
- `ADVAPI32!RegCloseKey` at `0x180017f6b`
- `ADVAPI32!RegCloseKey` at `0x180017fb5`
- `ADVAPI32!RegCloseKey` at `0x180018011`
- `ADVAPI32!RegCloseKey` at `0x180018065`
- `ADVAPI32!RegCloseKey` at `0x180017cb0`
- `ADVAPI32!RegCloseKey` at `0x180017d95`
- `ADVAPI32!RegCloseKey` at `0x180017dea`
- `ADVAPI32!RegCloseKey` at `0x180017e46`
- `ADVAPI32!RegCloseKey` at `0x180017efa`
- `ADVAPI32!RegCloseKey` at `0x180017f6b`
- `ADVAPI32!RegCloseKey` at `0x180017fb5`
- `ADVAPI32!RegCloseKey` at `0x180018011`
- `ADVAPI32!RegCloseKey` at `0x180018065`
- `KERNEL32!InitializeCriticalSection` at `0x180017b9f`
- `KERNEL32!InitializeCriticalSection` at `0x180017bc7`
- `KERNEL32!InitializeCriticalSection` at `0x180017d52`
- `KERNEL32!InitializeCriticalSection` at `0x180017eb5`
- `KERNEL32!InitializeCriticalSection` at `0x180017b9f`
- `KERNEL32!InitializeCriticalSection` at `0x180017bc7`
- `KERNEL32!InitializeCriticalSection` at `0x180017d52`
- `KERNEL32!InitializeCriticalSection` at `0x180017eb5`
- `KERNEL32!DeleteCriticalSection` at `0x180017db5`
- `KERNEL32!DeleteCriticalSection` at `0x180017e0e`
- `KERNEL32!DeleteCriticalSection` at `0x180017e66`
- `KERNEL32!DeleteCriticalSection` at `0x180017f1a`
- `KERNEL32!DeleteCriticalSection` at `0x180017f8b`
- `KERNEL32!DeleteCriticalSection` at `0x180017fd9`
- `KERNEL32!DeleteCriticalSection` at `0x180018031`
- `KERNEL32!DeleteCriticalSection` at `0x180017db5`
- `KERNEL32!DeleteCriticalSection` at `0x180017e0e`
- `KERNEL32!DeleteCriticalSection` at `0x180017e66`
- `KERNEL32!DeleteCriticalSection` at `0x180017f1a`
- `KERNEL32!DeleteCriticalSection` at `0x180017f8b`
- `KERNEL32!DeleteCriticalSection` at `0x180017fd9`
- `KERNEL32!DeleteCriticalSection` at `0x180018031`
- `KERNEL32!LeaveCriticalSection` at `0x180017cc6`
- `KERNEL32!LeaveCriticalSection` at `0x180017dab`
- `KERNEL32!LeaveCriticalSection` at `0x180017e03`
- `KERNEL32!LeaveCriticalSection` at `0x180017e5c`
- `KERNEL32!LeaveCriticalSection` at `0x180017f10`
- `KERNEL32!LeaveCriticalSection` at `0x180017f81`
- `KERNEL32!LeaveCriticalSection` at `0x180017fce`
- `KERNEL32!LeaveCriticalSection` at `0x180018027`
- `KERNEL32!LeaveCriticalSection` at `0x18001807e`
- `KERNEL32!LeaveCriticalSection` at `0x180017cc6`
- `KERNEL32!LeaveCriticalSection` at `0x180017dab`
- `KERNEL32!LeaveCriticalSection` at `0x180017e03`
- `KERNEL32!LeaveCriticalSection` at `0x180017e5c`
- `KERNEL32!LeaveCriticalSection` at `0x180017f10`
- `KERNEL32!LeaveCriticalSection` at `0x180017f81`
- `KERNEL32!LeaveCriticalSection` at `0x180017fce`
- `KERNEL32!LeaveCriticalSection` at `0x180018027`
- `KERNEL32!LeaveCriticalSection` at `0x18001807e`
- `KERNEL32!EnterCriticalSection` at `0x180017ca1`
- `KERNEL32!EnterCriticalSection` at `0x180017d86`
- `KERNEL32!EnterCriticalSection` at `0x180017dda`
- `KERNEL32!EnterCriticalSection` at `0x180017e37`
- `KERNEL32!EnterCriticalSection` at `0x180017eeb`
- `KERNEL32!EnterCriticalSection` at `0x180017f5c`
- `KERNEL32!EnterCriticalSection` at `0x180017fa5`
- `KERNEL32!EnterCriticalSection` at `0x180018002`
- `KERNEL32!EnterCriticalSection` at `0x180018055`
- `KERNEL32!EnterCriticalSection` at `0x180017ca1`
- `KERNEL32!EnterCriticalSection` at `0x180017d86`
- `KERNEL32!EnterCriticalSection` at `0x180017dda`
- `KERNEL32!EnterCriticalSection` at `0x180017e37`
- `KERNEL32!EnterCriticalSection` at `0x180017eeb`
- `KERNEL32!EnterCriticalSection` at `0x180017f5c`
- `KERNEL32!EnterCriticalSection` at `0x180017fa5`
- `KERNEL32!EnterCriticalSection` at `0x180018002`
- `KERNEL32!EnterCriticalSection` at `0x180018055`
- `KERNEL32!GlobalFree` at `0x180017c49`
- `KERNEL32!GlobalFree` at `0x180017dc4`
- `KERNEL32!GlobalFree` at `0x180017e1f`
- `KERNEL32!GlobalFree` at `0x180017e75`
- `KERNEL32!GlobalFree` at `0x180017f2a`
- `KERNEL32!GlobalFree` at `0x180017f9a`
- `KERNEL32!GlobalFree` at `0x180017fea`
- `KERNEL32!GlobalFree` at `0x180018040`
- `KERNEL32!GlobalFree` at `0x18001810c`
- `KERNEL32!GlobalFree` at `0x1800181aa`
- `KERNEL32!GlobalFree` at `0x1800181b9`
- `KERNEL32!GlobalFree` at `0x1800181cb`
- `KERNEL32!GlobalFree` at `0x180017c49`
- `KERNEL32!GlobalFree` at `0x180017dc4`
- `KERNEL32!GlobalFree` at `0x180017e1f`
- `KERNEL32!GlobalFree` at `0x180017e75`
- `KERNEL32!GlobalFree` at `0x180017f2a`
- `KERNEL32!GlobalFree` at `0x180017f9a`
- `KERNEL32!GlobalFree` at `0x180017fea`
- `KERNEL32!GlobalFree` at `0x180018040`
- `KERNEL32!GlobalFree` at `0x18001810c`
- `KERNEL32!GlobalFree` at `0x1800181aa`
- `KERNEL32!GlobalFree` at `0x1800181b9`
- `KERNEL32!GlobalFree` at `0x1800181cb`

## string_xrefs

- `0x180017c1e`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800180a6`: `InstallProperties`

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
  struct _RTL_CRITICAL_SECTION v15; // [rsp+40h] [rbp-C0h] BYREF
  struct _RTL_CRITICAL_SECTION v16; // [rsp+68h] [rbp-98h] BYREF
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v19[2]; // [rsp+E0h] [rbp-20h]
  HGLOBAL v20; // [rsp+F0h] [rbp-10h]
  int v21; // [rsp+F8h] [rbp-8h]
  __int16 v22; // [rsp+100h] [rbp+0h] BYREF
  struct _RTL_CRITICAL_SECTION v23; // [rsp+108h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+130h] [rbp+30h] BYREF
  struct _RTL_CRITICAL_SECTION v25; // [rsp+158h] [rbp+58h] BYREF
  HGLOBAL v26; // [rsp+940h] [rbp+840h]
  int v27; // [rsp+948h] [rbp+848h]
  unsigned __int16 v28[320]; // [rsp+950h] [rbp+850h] BYREF

  if ( a1 == 3 )
    return 87;
  if ( !a2 )
    return 1605;
  LOWORD(hKey.SpinCount) = 0;
  *(_OWORD *)&hKey.DebugInfo = 0;
  hKey.OwningThread = &hKey.SpinCount;
  LODWORD(hKey.LockSemaphore) = 1;
  InitializeCriticalSection(&CriticalSection);
  LODWORD(v15.LockSemaphore) = 1;
  *(_OWORD *)&v15.DebugInfo = 0;
  v15.OwningThread = &v15.SpinCount;
  LOWORD(v15.SpinCount) = 0;
  InitializeCriticalSection(&v16);
  v27 = 318;
  v26 = v28;
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
                             v28,
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
    if ( (int)StringCchPrintfW((unsigned __int16 *)&hMem.OwningThread, 0x400u, L"%s\\%s\\%s", v26, L"Products", a2) < 0 )
    {
      if ( hMem.LockCount > 1024 )
        GlobalFree(hMem.DebugInfo);
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      hMem.LockCount = 1024;
      if ( v27 > 318 )
        GlobalFree(v26);
      goto LABEL_19;
    }
    v10 = hMem.DebugInfo;
    EnterCriticalSection(&CriticalSection);
    if ( hKey.DebugInfo )
    {
      RegCloseKey((HKEY)hKey.DebugInfo);
      hKey.DebugInfo = 0;
      *(_WORD *)hKey.OwningThread = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    v11 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      v11 = g_samRead | 0x100;
    CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                             -2147483646,
                             v10,
                             0,
                             v11,
                             &hKey);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
  }
LABEL_16:
  if ( v27 > 318 )
    GlobalFree(v26);
  if ( CurrentUserStringSID )
    goto LABEL_19;
  EnterCriticalSection(&v16);
  if ( v15.DebugInfo )
  {
    RegCloseKey((HKEY)v15.DebugInfo);
    v15.DebugInfo = 0;
    *(_WORD *)v15.OwningThread = 0;
  }
  LeaveCriticalSection(&v16);
  v14 = g_samRead;
  if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
    v14 = g_samRead | 0x100;
  if ( (unsigned int)((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const unsigned __int16 *, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                       hKey.DebugInfo,
                       L"InstallProperties",
                       0,
                       v14,
                       &v15) )
  {
LABEL_19:
    if ( a1 != 1 || !a3 || !*a3 || IsCurrentUser(a3) )
    {
      LODWORD(hMem.LockSemaphore) = 1;
      *(_OWORD *)&hMem.DebugInfo = 0;
      hMem.OwningThread = &hMem.SpinCount;
      LOWORD(hMem.SpinCount) = 0;
      InitializeCriticalSection(&v25);
      if ( !(unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(a1, a3, (WCHAR *)L"Products", a2, &hMem, 0) )
      {
        EnterCriticalSection(&v25);
        if ( hMem.DebugInfo )
        {
          RegCloseKey((HKEY)hMem.DebugInfo);
          hMem.DebugInfo = 0;
          *(_WORD *)hMem.OwningThread = 0;
        }
        LeaveCriticalSection(&v25);
        DeleteCriticalSection(&v25);
        if ( SLODWORD(hMem.LockSemaphore) > 1 )
          GlobalFree(hMem.OwningThread);
        LODWORD(hMem.LockSemaphore) = 1;
        hMem.OwningThread = &hMem.SpinCount;
        EnterCriticalSection(&v16);
        if ( v15.DebugInfo )
        {
          RegCloseKey((HKEY)v15.DebugInfo);
          v15.DebugInfo = 0;
          *(_WORD *)v15.OwningThread = 0;
        }
        LeaveCriticalSection(&v16);
        DeleteCriticalSection(&v16);
        if ( SLODWORD(v15.LockSemaphore) > 1 )
          GlobalFree(v15.OwningThread);
        LODWORD(v15.LockSemaphore) = 1;
        v15.OwningThread = &v15.SpinCount;
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
        goto LABEL_33;
      }
      EnterCriticalSection(&v25);
      if ( hMem.DebugInfo )
      {
        RegCloseKey((HKEY)hMem.DebugInfo);
        hMem.DebugInfo = 0;
        *(_WORD *)hMem.OwningThread = 0;
      }
      LeaveCriticalSection(&v25);
      DeleteCriticalSection(&v25);
      if ( SLODWORD(hMem.LockSemaphore) > 1 )
        GlobalFree(hMem.OwningThread);
    }
    EnterCriticalSection(&v16);
    if ( v15.DebugInfo )
    {
      RegCloseKey((HKEY)v15.DebugInfo);
      v15.DebugInfo = 0;
      *(_WORD *)v15.OwningThread = 0;
    }
    LeaveCriticalSection(&v16);
    DeleteCriticalSection(&v16);
    if ( SLODWORD(v15.LockSemaphore) > 1 )
      GlobalFree(v15.OwningThread);
    LODWORD(v15.LockSemaphore) = 1;
    v15.OwningThread = &v15.SpinCount;
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
  CRegHandle::~CRegHandle(&v15);
  CRegHandle::~CRegHandle(&hKey);
LABEL_33:
  if ( !(unsigned __int8)IsPatchAppliedToProduct(a4, a2, a3, a1) )
    return 1647;
  v21 = 1;
  *(_OWORD *)v19 = 0;
  v20 = &v22;
  v22 = 0;
  InitializeCriticalSection(&v23);
  AppliedPatchInfoInternal = GetAppliedPatchInfoInternal(a1, a2, a3, a4);
  EnterCriticalSection(&v23);
  if ( v19[0] )
  {
    RegCloseKey(v19[0]);
    v19[0] = 0;
    *(_WORD *)v20 = 0;
  }
  LeaveCriticalSection(&v23);
  DeleteCriticalSection(&v23);
  if ( v21 > 1 )
    GlobalFree(v20);
  return AppliedPatchInfoInternal;
}

```

## disassembly

```asm
0x180017b28  mov     [rsp-8+arg_0], rbx
0x180017b2d  push    rbp
0x180017b2e  push    rsi
0x180017b2f  push    rdi
0x180017b30  push    r12
0x180017b32  push    r13
0x180017b34  push    r14
0x180017b36  push    r15
0x180017b38  lea     rbp, [rsp-0AE0h]
0x180017b40  sub     rsp, 0BE0h
0x180017b47  mov     rax, cs:__security_cookie
0x180017b4e  xor     rax, rsp
0x180017b51  mov     [rbp+0B10h+var_40], rax
0x180017b58  mov     r12, [rbp+0B10h+arg_28]
0x180017b5f  mov     r15, r9
0x180017b62  mov     rdi, r8
0x180017b65  mov     r14, rdx
0x180017b68  mov     esi, ecx
0x180017b6a  cmp     ecx, 3
0x180017b6d  jz      loc_18001819C
0x180017b73  xor     r13d, r13d
0x180017b76  test    rdx, rdx
0x180017b79  jz      loc_180018046
0x180017b7f  xorps   xmm0, xmm0
0x180017b82  mov     [rbp+0B10h+var_B60], r13w
0x180017b87  lea     rax, [rbp+0B10h+var_B60]
0x180017b8b  movdqa  xmmword ptr [rbp+0B10h+hKey], xmm0
0x180017b90  lea     ebx, [r13+1]
0x180017b94  mov     [rbp+0B10h+var_B70], rax
0x180017b98  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017b9c  mov     [rbp+0B10h+var_B68], ebx
0x180017b9f  call    cs:__imp_InitializeCriticalSection
0x180017ba5  xorps   xmm0, xmm0
0x180017ba8  mov     [rsp+0C10h+var_BB8], ebx
0x180017bac  lea     rax, [rsp+0C10h+var_BB0]
0x180017bb1  movdqa  xmmword ptr [rsp+0C10h+var_BD0], xmm0
0x180017bb7  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017bbc  mov     [rsp+0C10h+var_BC0], rax
0x180017bc1  mov     [rsp+0C10h+var_BB0], r13w
0x180017bc7  call    cs:__imp_InitializeCriticalSection
0x180017bcd  mov     [rbp+0B10h+var_2C8], 13Eh
0x180017bd7  lea     rax, [rbp+0B10h+var_2C0]
0x180017bde  mov     [rbp+0B10h+var_2D0], rax
0x180017be5  lea     rax, [rbp+0B10h+var_AD0]
0x180017be9  mov     [rbp+0B10h+hMem], rax
0x180017bed  lea     r8d, [r13+40h]
0x180017bf1  mov     dword ptr [rbp+0B10h+hMem+8], r8d
0x180017bf5  mov     edx, r13d
0x180017bf8  mov     ecx, esi
0x180017bfa  test    esi, esi
0x180017bfc  jz      loc_180018117
0x180017c02  sub     ecx, ebx
0x180017c04  jz      loc_180018117
0x180017c0a  sub     ecx, ebx
0x180017c0c  jnz     loc_18001818A
0x180017c12  lea     rdx, aS1518; "S-1-5-18"
0x180017c19  mov     [rsp+0C10h+var_BF0], rdx
0x180017c1e  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180017c25  mov     edx, 13Eh; unsigned __int64
0x180017c2a  lea     r8, aSS_0; "%s\\%s"
0x180017c31  lea     rcx, [rbp+0B10h+var_2C0]; unsigned __int16 *
0x180017c38  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017c3d  mov     ebx, eax
0x180017c3f  cmp     dword ptr [rbp+0B10h+hMem+8], 40h ; '@'
0x180017c43  jle     short loc_180017C4F
0x180017c45  mov     rcx, [rbp+0B10h+hMem]; hMem
0x180017c49  call    cs:__imp_GlobalFree
0x180017c4f  test    ebx, ebx
0x180017c51  jnz     loc_180017D11
0x180017c57  mov     r9, [rbp+0B10h+var_2D0]
0x180017c5e  lea     rax, [rbp+0B10h+var_AD0]
0x180017c62  mov     [rbp+0B10h+hMem], rax
0x180017c66  lea     r8, aSSS; "%s\\%s\\%s"
0x180017c6d  mov     ebx, 400h
0x180017c72  mov     [rsp+0C10h+var_BE8], r14
0x180017c77  lea     rax, aProducts; "Products"
0x180017c7e  mov     dword ptr [rbp+0B10h+hMem+8], ebx
0x180017c81  mov     edx, ebx; unsigned __int64
0x180017c83  mov     [rsp+0C10h+var_BF0], rax
0x180017c88  lea     rcx, [rbp+0B10h+var_AD0]; unsigned __int16 *
0x180017c8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017c91  test    eax, eax
0x180017c93  js      loc_1800180E1
0x180017c99  mov     rbx, [rbp+0B10h+hMem]
0x180017c9d  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017ca1  call    cs:__imp_EnterCriticalSection
0x180017ca7  mov     rcx, [rbp+0B10h+hKey]; hKey
0x180017cab  test    rcx, rcx
0x180017cae  jz      short loc_180017CC2
0x180017cb0  call    cs:__imp_RegCloseKey
0x180017cb6  mov     rax, [rbp+0B10h+var_B70]
0x180017cba  mov     [rbp+0B10h+hKey], r13
0x180017cbe  mov     [rax], r13w
0x180017cc2  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017cc6  call    cs:__imp_LeaveCriticalSection
0x180017ccc  cmp     cs:?g_fWoW@@3_NA, r13b; bool g_fWoW
0x180017cd3  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180017cda  jz      loc_18001813C
0x180017ce0  lea     rax, [rbp+0B10h+hKey]
0x180017ce4  xor     r8d, r8d
0x180017ce7  mov     [rsp+0C10h+var_BF0], rax
0x180017cec  mov     rdx, rbx
0x180017cef  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180017cf6  mov     rcx, 0FFFFFFFF80000002h
0x180017cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d02  cmp     dword ptr [rbp+0B10h+hMem+8], 400h
0x180017d09  mov     ebx, eax
0x180017d0b  jg      loc_1800181B5
0x180017d11  cmp     [rbp+0B10h+var_2C8], 13Eh
0x180017d1b  jg      loc_1800181C4
0x180017d21  test    ebx, ebx
0x180017d23  jz      loc_180018050
0x180017d29  mov     ebx, 1
0x180017d2e  cmp     esi, ebx
0x180017d30  jz      loc_1800181D6
0x180017d36  xorps   xmm0, xmm0
0x180017d39  mov     [rbp+0B10h+var_AC8], ebx
0x180017d3c  lea     rax, [rbp+0B10h+var_AC0]
0x180017d40  movdqa  xmmword ptr [rbp+0B10h+hMem], xmm0
0x180017d45  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x180017d49  mov     [rbp+0B10h+var_AD0], rax
0x180017d4d  mov     [rbp+0B10h+var_AC0], r13w
0x180017d52  call    cs:__imp_InitializeCriticalSection
0x180017d58  lea     rax, [rbp+0B10h+hMem]
0x180017d5c  mov     byte ptr [rsp+0C10h+var_BE8], r13b
0x180017d61  mov     r9, r14
0x180017d64  mov     [rsp+0C10h+var_BF0], rax
0x180017d69  lea     r8, aProducts; "Products"
0x180017d70  mov     rdx, rdi
0x180017d73  mov     ecx, esi
0x180017d75  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x180017d7a  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x180017d7e  test    eax, eax
0x180017d80  jnz     loc_180017F5C
0x180017d86  call    cs:__imp_EnterCriticalSection
0x180017d8c  mov     rcx, [rbp+0B10h+hMem]; hKey
0x180017d90  test    rcx, rcx
0x180017d93  jz      short loc_180017DA7
0x180017d95  call    cs:__imp_RegCloseKey
0x180017d9b  mov     rax, [rbp+0B10h+var_AD0]
0x180017d9f  mov     [rbp+0B10h+hMem], r13
0x180017da3  mov     [rax], r13w
0x180017da7  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x180017dab  call    cs:__imp_LeaveCriticalSection
0x180017db1  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x180017db5  call    cs:__imp_DeleteCriticalSection
0x180017dbb  cmp     [rbp+0B10h+var_AC8], ebx
0x180017dbe  jle     short loc_180017DCA
0x180017dc0  mov     rcx, [rbp+0B10h+var_AD0]; hMem
0x180017dc4  call    cs:__imp_GlobalFree
0x180017dca  lea     rax, [rbp+0B10h+var_AC0]
0x180017dce  mov     [rbp+0B10h+var_AC8], ebx
0x180017dd1  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017dd6  mov     [rbp+0B10h+var_AD0], rax
0x180017dda  call    cs:__imp_EnterCriticalSection
0x180017de0  mov     rcx, [rsp+0C10h+var_BD0]; hKey
0x180017de5  test    rcx, rcx
0x180017de8  jz      short loc_180017DFE
0x180017dea  call    cs:__imp_RegCloseKey
0x180017df0  mov     rax, [rsp+0C10h+var_BC0]
0x180017df5  mov     [rsp+0C10h+var_BD0], r13
0x180017dfa  mov     [rax], r13w
0x180017dfe  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017e03  call    cs:__imp_LeaveCriticalSection
0x180017e09  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017e0e  call    cs:__imp_DeleteCriticalSection
0x180017e14  cmp     [rsp+0C10h+var_BB8], ebx
0x180017e18  jle     short loc_180017E25
0x180017e1a  mov     rcx, [rsp+0C10h+var_BC0]; hMem
0x180017e1f  call    cs:__imp_GlobalFree
0x180017e25  lea     rax, [rsp+0C10h+var_BB0]
0x180017e2a  mov     [rsp+0C10h+var_BB8], ebx
0x180017e2e  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017e32  mov     [rsp+0C10h+var_BC0], rax
0x180017e37  call    cs:__imp_EnterCriticalSection
0x180017e3d  mov     rcx, [rbp+0B10h+hKey]; hKey
0x180017e41  test    rcx, rcx
0x180017e44  jz      short loc_180017E58
0x180017e46  call    cs:__imp_RegCloseKey
0x180017e4c  mov     rax, [rbp+0B10h+var_B70]
0x180017e50  mov     [rbp+0B10h+hKey], r13
0x180017e54  mov     [rax], r13w
0x180017e58  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017e5c  call    cs:__imp_LeaveCriticalSection
0x180017e62  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017e66  call    cs:__imp_DeleteCriticalSection
0x180017e6c  cmp     [rbp+0B10h+var_B68], ebx
0x180017e6f  jle     short loc_180017E7B
0x180017e71  mov     rcx, [rbp+0B10h+var_B70]; hMem
0x180017e75  call    cs:__imp_GlobalFree
0x180017e7b  mov     r9d, esi
0x180017e7e  mov     byte ptr [rsp+0C10h+var_BF0], r13b
0x180017e83  mov     r8, rdi
0x180017e86  mov     rdx, r14
0x180017e89  mov     rcx, r15
0x180017e8c  call    ?IsPatchAppliedToProduct@@YA_NPEBG00W4iaaAppAssignment@@_N@Z; IsPatchAppliedToProduct(ushort const *,ushort const *,ushort const *,iaaAppAssignment,bool)
0x180017e91  test    al, al
0x180017e93  jz      loc_1800181FE
0x180017e99  xorps   xmm0, xmm0
0x180017e9c  mov     [rbp+0B10h+var_B18], ebx
0x180017e9f  lea     rax, [rbp+0B10h+var_B10]
0x180017ea3  movdqa  xmmword ptr [rbp+0B10h+var_B30], xmm0
0x180017ea8  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x180017eac  mov     [rbp+0B10h+var_B20], rax
0x180017eb0  mov     [rbp+0B10h+var_B10], r13w
0x180017eb5  call    cs:__imp_InitializeCriticalSection
0x180017ebb  lea     rax, [rbp+0B10h+var_B30]
0x180017ebf  mov     r9, r15
0x180017ec2  mov     [rsp+0C10h+var_BE0], rax
0x180017ec7  mov     r8, rdi
0x180017eca  mov     rax, [rbp+0B10h+arg_20]
0x180017ed1  mov     rdx, r14
0x180017ed4  mov     [rsp+0C10h+var_BE8], r12
0x180017ed9  mov     ecx, esi
0x180017edb  mov     [rsp+0C10h+var_BF0], rax
0x180017ee0  call    ?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@AEAVCRegHandle@@@Z; GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &,CRegHandle &)
0x180017ee5  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x180017ee9  mov     ebx, eax
0x180017eeb  call    cs:__imp_EnterCriticalSection
0x180017ef1  mov     rcx, [rbp+0B10h+var_B30]; hKey
0x180017ef5  test    rcx, rcx
0x180017ef8  jz      short loc_180017F0C
0x180017efa  call    cs:__imp_RegCloseKey
0x180017f00  mov     rcx, [rbp+0B10h+var_B20]
0x180017f04  mov     [rbp+0B10h+var_B30], r13
0x180017f08  mov     [rcx], r13w
0x180017f0c  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x180017f10  call    cs:__imp_LeaveCriticalSection
0x180017f16  lea     rcx, [rbp+0B10h+var_B08]; lpCriticalSection
0x180017f1a  call    cs:__imp_DeleteCriticalSection
0x180017f20  cmp     [rbp+0B10h+var_B18], 1
0x180017f24  jle     short loc_180017F30
0x180017f26  mov     rcx, [rbp+0B10h+var_B20]; hMem
0x180017f2a  call    cs:__imp_GlobalFree
0x180017f30  mov     eax, ebx
0x180017f32  mov     rcx, [rbp+0B10h+var_40]
0x180017f39  xor     rcx, rsp; StackCookie
0x180017f3c  call    __security_check_cookie
0x180017f41  mov     rbx, [rsp+0C10h+arg_0]
0x180017f49  add     rsp, 0BE0h
0x180017f50  pop     r15
0x180017f52  pop     r14
0x180017f54  pop     r13
0x180017f56  pop     r12
0x180017f58  pop     rdi
0x180017f59  pop     rsi
0x180017f5a  pop     rbp
0x180017f5b  retn
0x180017f5c  call    cs:__imp_EnterCriticalSection
0x180017f62  mov     rcx, [rbp+0B10h+hMem]; hKey
0x180017f66  test    rcx, rcx
0x180017f69  jz      short loc_180017F7D
0x180017f6b  call    cs:__imp_RegCloseKey
0x180017f71  mov     rax, [rbp+0B10h+var_AD0]
0x180017f75  mov     [rbp+0B10h+hMem], r13
0x180017f79  mov     [rax], r13w
0x180017f7d  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x180017f81  call    cs:__imp_LeaveCriticalSection
0x180017f87  lea     rcx, [rbp+0B10h+var_AB8]; lpCriticalSection
0x180017f8b  call    cs:__imp_DeleteCriticalSection
0x180017f91  cmp     [rbp+0B10h+var_AC8], ebx
0x180017f94  jle     short loc_180017FA0
0x180017f96  mov     rcx, [rbp+0B10h+var_AD0]; hMem
0x180017f9a  call    cs:__imp_GlobalFree
0x180017fa0  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017fa5  call    cs:__imp_EnterCriticalSection
0x180017fab  mov     rcx, [rsp+0C10h+var_BD0]; hKey
0x180017fb0  test    rcx, rcx
0x180017fb3  jz      short loc_180017FC9
0x180017fb5  call    cs:__imp_RegCloseKey
0x180017fbb  mov     rax, [rsp+0C10h+var_BC0]
0x180017fc0  mov     [rsp+0C10h+var_BD0], r13
0x180017fc5  mov     [rax], r13w
0x180017fc9  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017fce  call    cs:__imp_LeaveCriticalSection
0x180017fd4  lea     rcx, [rsp+0C10h+var_BA8]; lpCriticalSection
0x180017fd9  call    cs:__imp_DeleteCriticalSection
0x180017fdf  cmp     [rsp+0C10h+var_BB8], ebx
0x180017fe3  jle     short loc_180017FF0
0x180017fe5  mov     rcx, [rsp+0C10h+var_BC0]; hMem
0x180017fea  call    cs:__imp_GlobalFree
0x180017ff0  lea     rax, [rsp+0C10h+var_BB0]
0x180017ff5  mov     [rsp+0C10h+var_BB8], ebx
0x180017ff9  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180017ffd  mov     [rsp+0C10h+var_BC0], rax
0x180018002  call    cs:__imp_EnterCriticalSection
0x180018008  mov     rcx, [rbp+0B10h+hKey]; hKey
0x18001800c  test    rcx, rcx
0x18001800f  jz      short loc_180018023
0x180018011  call    cs:__imp_RegCloseKey
0x180018017  mov     rax, [rbp+0B10h+var_B70]
0x18001801b  mov     [rbp+0B10h+hKey], r13
0x18001801f  mov     [rax], r13w
0x180018023  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180018027  call    cs:__imp_LeaveCriticalSection
0x18001802d  lea     rcx, [rbp+0B10h+CriticalSection]; lpCriticalSection
0x180018031  call    cs:__imp_DeleteCriticalSection
0x180018037  cmp     [rbp+0B10h+var_B68], ebx
0x18001803a  jle     short loc_180018046
0x18001803c  mov     rcx, [rbp+0B10h+var_B70]; hMem
  ... truncated ...
```
