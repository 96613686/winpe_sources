# IsProductInstalledOrAdvertised(ushort const *,ushort const *,iaaAppAssignment)

- ea: `0x180010b58`
- end: `0x18001126f`
- name: `?IsProductInstalledOrAdvertised@@YA_NPEBG0W4iaaAppAssignment@@@Z`
- size: `1815`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180044bb0`
- `0x1800e3c4c`

## callees

- `0x180010ac0`
- `0x180010b58`
- `0x180011280`
- `0x180013b7c`
- `0x18003c030`
- `0x18003e40c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180010ced`
- `ADVAPI32!RegCloseKey` at `0x180010de7`
- `ADVAPI32!RegCloseKey` at `0x180010e5c`
- `ADVAPI32!RegCloseKey` at `0x180010ed8`
- `ADVAPI32!RegCloseKey` at `0x180010f69`
- `ADVAPI32!RegCloseKey` at `0x180010fd2`
- `ADVAPI32!RegCloseKey` at `0x18001104e`
- `ADVAPI32!RegCloseKey` at `0x1800110be`
- `ADVAPI32!RegCloseKey` at `0x180010ced`
- `ADVAPI32!RegCloseKey` at `0x180010de7`
- `ADVAPI32!RegCloseKey` at `0x180010e5c`
- `ADVAPI32!RegCloseKey` at `0x180010ed8`
- `ADVAPI32!RegCloseKey` at `0x180010f69`
- `ADVAPI32!RegCloseKey` at `0x180010fd2`
- `ADVAPI32!RegCloseKey` at `0x18001104e`
- `ADVAPI32!RegCloseKey` at `0x1800110be`
- `KERNEL32!InitializeCriticalSection` at `0x180010bbe`
- `KERNEL32!InitializeCriticalSection` at `0x180010bed`
- `KERNEL32!InitializeCriticalSection` at `0x180010d9c`
- `KERNEL32!InitializeCriticalSection` at `0x180010bbe`
- `KERNEL32!InitializeCriticalSection` at `0x180010bed`
- `KERNEL32!InitializeCriticalSection` at `0x180010d9c`
- `KERNEL32!DeleteCriticalSection` at `0x180010e13`
- `KERNEL32!DeleteCriticalSection` at `0x180010e8c`
- `KERNEL32!DeleteCriticalSection` at `0x180010f04`
- `KERNEL32!DeleteCriticalSection` at `0x180010f95`
- `KERNEL32!DeleteCriticalSection` at `0x180011002`
- `KERNEL32!DeleteCriticalSection` at `0x18001107a`
- `KERNEL32!DeleteCriticalSection` at `0x180010e13`
- `KERNEL32!DeleteCriticalSection` at `0x180010e8c`
- `KERNEL32!DeleteCriticalSection` at `0x180010f04`
- `KERNEL32!DeleteCriticalSection` at `0x180010f95`
- `KERNEL32!DeleteCriticalSection` at `0x180011002`
- `KERNEL32!DeleteCriticalSection` at `0x18001107a`
- `KERNEL32!LeaveCriticalSection` at `0x180010d09`
- `KERNEL32!LeaveCriticalSection` at `0x180010e03`
- `KERNEL32!LeaveCriticalSection` at `0x180010e7b`
- `KERNEL32!LeaveCriticalSection` at `0x180010ef4`
- `KERNEL32!LeaveCriticalSection` at `0x180010f85`
- `KERNEL32!LeaveCriticalSection` at `0x180010ff1`
- `KERNEL32!LeaveCriticalSection` at `0x18001106a`
- `KERNEL32!LeaveCriticalSection` at `0x1800110dd`
- `KERNEL32!LeaveCriticalSection` at `0x180010d09`
- `KERNEL32!LeaveCriticalSection` at `0x180010e03`
- `KERNEL32!LeaveCriticalSection` at `0x180010e7b`
- `KERNEL32!LeaveCriticalSection` at `0x180010ef4`
- `KERNEL32!LeaveCriticalSection` at `0x180010f85`
- `KERNEL32!LeaveCriticalSection` at `0x180010ff1`
- `KERNEL32!LeaveCriticalSection` at `0x18001106a`
- `KERNEL32!LeaveCriticalSection` at `0x1800110dd`
- `KERNEL32!EnterCriticalSection` at `0x180010cd8`
- `KERNEL32!EnterCriticalSection` at `0x180010dd2`
- `KERNEL32!EnterCriticalSection` at `0x180010e46`
- `KERNEL32!EnterCriticalSection` at `0x180010ec3`
- `KERNEL32!EnterCriticalSection` at `0x180010f54`
- `KERNEL32!EnterCriticalSection` at `0x180010fbc`
- `KERNEL32!EnterCriticalSection` at `0x180011039`
- `KERNEL32!EnterCriticalSection` at `0x1800110a8`
- `KERNEL32!EnterCriticalSection` at `0x180010cd8`
- `KERNEL32!EnterCriticalSection` at `0x180010dd2`
- `KERNEL32!EnterCriticalSection` at `0x180010e46`
- `KERNEL32!EnterCriticalSection` at `0x180010ec3`
- `KERNEL32!EnterCriticalSection` at `0x180010f54`
- `KERNEL32!EnterCriticalSection` at `0x180010fbc`
- `KERNEL32!EnterCriticalSection` at `0x180011039`
- `KERNEL32!EnterCriticalSection` at `0x1800110a8`
- `KERNEL32!GlobalFree` at `0x180010c77`
- `KERNEL32!GlobalFree` at `0x180010e29`
- `KERNEL32!GlobalFree` at `0x180010ea4`
- `KERNEL32!GlobalFree` at `0x180010f1a`
- `KERNEL32!GlobalFree` at `0x180010fab`
- `KERNEL32!GlobalFree` at `0x18001101a`
- `KERNEL32!GlobalFree` at `0x180011090`
- `KERNEL32!GlobalFree` at `0x18001116e`
- `KERNEL32!GlobalFree` at `0x180011209`
- `KERNEL32!GlobalFree` at `0x18001121e`
- `KERNEL32!GlobalFree` at `0x180011236`
- `KERNEL32!GlobalFree` at `0x180010c77`
- `KERNEL32!GlobalFree` at `0x180010e29`
- `KERNEL32!GlobalFree` at `0x180010ea4`
- `KERNEL32!GlobalFree` at `0x180010f1a`
- `KERNEL32!GlobalFree` at `0x180010fab`
- `KERNEL32!GlobalFree` at `0x18001101a`
- `KERNEL32!GlobalFree` at `0x180011090`
- `KERNEL32!GlobalFree` at `0x18001116e`
- `KERNEL32!GlobalFree` at `0x180011209`
- `KERNEL32!GlobalFree` at `0x18001121e`
- `KERNEL32!GlobalFree` at `0x180011236`

## string_xrefs

- `0x180010c4c`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18001110b`: `InstallProperties`

## pseudocode

```c
char __fastcall IsProductInstalledOrAdvertised(const WCHAR *a1, wchar_t *a2, unsigned int a3)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  int CurrentUserStringSID; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v8; // rbx
  __int64 v9; // r9
  __int64 v11; // r9
  HKEY v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  __int16 v15; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_CRITICAL_SECTION v16; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  HGLOBAL v18; // [rsp+90h] [rbp-70h]
  int v19; // [rsp+98h] [rbp-68h]
  __int16 v20; // [rsp+A0h] [rbp-60h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+A8h] [rbp-58h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_CRITICAL_SECTION v23; // [rsp+F8h] [rbp-8h] BYREF
  HGLOBAL v24; // [rsp+8E0h] [rbp+7E0h]
  int v25; // [rsp+8E8h] [rbp+7E8h]
  unsigned __int16 v26[320]; // [rsp+8F0h] [rbp+7F0h] BYREF

  if ( !a1 )
    return 0;
  v20 = 0;
  *(_OWORD *)hKey = 0;
  v18 = &v20;
  v19 = 1;
  InitializeCriticalSection(&CriticalSection);
  v14 = 1;
  *(_OWORD *)v12 = 0;
  v13 = &v15;
  v15 = 0;
  InitializeCriticalSection(&v16);
  v25 = 318;
  v24 = v26;
  hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
  hMem.LockCount = 64;
  DebugInfo = 0;
  if ( a3 >= 2 )
  {
    if ( a3 == 2 )
    {
      DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"S-1-5-18";
    }
    else if ( a3 == 3 )
    {
      CurrentUserStringSID = 2;
      goto LABEL_15;
    }
    goto LABEL_5;
  }
  if ( a2 )
  {
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)a2;
    goto LABEL_5;
  }
  hMem.RecursionCount = 64;
  CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
  if ( !CurrentUserStringSID )
  {
    DebugInfo = hMem.DebugInfo;
LABEL_5:
    CurrentUserStringSID = StringCchPrintfW(
                             v26,
                             0x13Eu,
                             L"%s\\%s",
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                             DebugInfo);
  }
  if ( hMem.LockCount > 64 )
    GlobalFree(hMem.DebugInfo);
  if ( CurrentUserStringSID )
  {
LABEL_15:
    if ( v25 > 318 )
      GlobalFree(v24);
    if ( !CurrentUserStringSID )
    {
      EnterCriticalSection(&v16);
      if ( v12[0] )
      {
        RegCloseKey(v12[0]);
        v12[0] = 0;
        *(_WORD *)v13 = 0;
      }
      LeaveCriticalSection(&v16);
      v11 = g_samRead;
      if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
        v11 = g_samRead | 0x100;
      if ( !(unsigned int)((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                            hKey[0],
                            L"InstallProperties",
                            0,
                            v11,
                            v12) )
      {
        CRegHandle::~CRegHandle((CRegHandle *)v12);
        CRegHandle::~CRegHandle((CRegHandle *)hKey);
        return 1;
      }
    }
    goto LABEL_18;
  }
  hMem.LockCount = 1024;
  hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
  if ( (int)StringCchPrintfW((unsigned __int16 *)&hMem.OwningThread, 0x400u, L"%s\\%s\\%s", v24, L"Products", a1) >= 0 )
  {
    v8 = hMem.DebugInfo;
    EnterCriticalSection(&CriticalSection);
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
      *(_WORD *)v18 = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    v9 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      v9 = g_samRead | 0x100;
    CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                             -2147483646,
                             v8,
                             0,
                             v9,
                             hKey);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
    goto LABEL_15;
  }
  if ( hMem.LockCount > 1024 )
    GlobalFree(hMem.DebugInfo);
  hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
  hMem.LockCount = 1024;
  if ( v25 > 318 )
    GlobalFree(v24);
LABEL_18:
  if ( a3 != 1 || !a2 || !*a2 || IsCurrentUser(a2) )
  {
    LODWORD(hMem.LockSemaphore) = 1;
    *(_OWORD *)&hMem.DebugInfo = 0;
    hMem.OwningThread = &hMem.SpinCount;
    LOWORD(hMem.SpinCount) = 0;
    InitializeCriticalSection(&v23);
    if ( !(unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(a3, a2, (WCHAR *)L"Products", a1, &hMem, 0) )
    {
      EnterCriticalSection(&v23);
      if ( hMem.DebugInfo )
      {
        RegCloseKey((HKEY)hMem.DebugInfo);
        hMem.DebugInfo = 0;
        *(_WORD *)hMem.OwningThread = 0;
      }
      LeaveCriticalSection(&v23);
      DeleteCriticalSection(&v23);
      if ( SLODWORD(hMem.LockSemaphore) > 1 )
        GlobalFree(hMem.OwningThread);
      LODWORD(hMem.LockSemaphore) = 1;
      hMem.OwningThread = &hMem.SpinCount;
      EnterCriticalSection(&v16);
      if ( v12[0] )
      {
        RegCloseKey(v12[0]);
        v12[0] = 0;
        *(_WORD *)v13 = 0;
      }
      LeaveCriticalSection(&v16);
      DeleteCriticalSection(&v16);
      if ( v14 > 1 )
        GlobalFree(v13);
      v14 = 1;
      v13 = &v15;
      EnterCriticalSection(&CriticalSection);
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
        *(_WORD *)v18 = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      DeleteCriticalSection(&CriticalSection);
      if ( v19 > 1 )
        GlobalFree(v18);
      return 1;
    }
    EnterCriticalSection(&v23);
    if ( hMem.DebugInfo )
    {
      RegCloseKey((HKEY)hMem.DebugInfo);
      hMem.DebugInfo = 0;
      *(_WORD *)hMem.OwningThread = 0;
    }
    LeaveCriticalSection(&v23);
    DeleteCriticalSection(&v23);
    if ( SLODWORD(hMem.LockSemaphore) > 1 )
      GlobalFree(hMem.OwningThread);
  }
  EnterCriticalSection(&v16);
  if ( v12[0] )
  {
    RegCloseKey(v12[0]);
    v12[0] = 0;
    *(_WORD *)v13 = 0;
  }
  LeaveCriticalSection(&v16);
  DeleteCriticalSection(&v16);
  if ( v14 > 1 )
    GlobalFree(v13);
  v14 = 1;
  v13 = &v15;
  EnterCriticalSection(&CriticalSection);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    *(_WORD *)v18 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( v19 > 1 )
    GlobalFree(v18);
  return 0;
}

```

## disassembly

```asm
0x180010b58  mov     [rsp-8+arg_10], rbx
0x180010b5d  push    rbp
0x180010b5e  push    rsi
0x180010b5f  push    rdi
0x180010b60  push    r12
0x180010b62  push    r13
0x180010b64  push    r14
0x180010b66  push    r15
0x180010b68  lea     rbp, [rsp-0A80h]
0x180010b70  sub     rsp, 0B80h
0x180010b77  mov     rax, cs:__security_cookie
0x180010b7e  xor     rax, rsp
0x180010b81  mov     [rbp+0AB0h+var_40], rax
0x180010b88  xor     r15d, r15d
0x180010b8b  mov     esi, r8d
0x180010b8e  mov     rdi, rdx
0x180010b91  mov     r14, rcx
0x180010b94  test    rcx, rcx
0x180010b97  jz      loc_18001109C
0x180010b9d  xorps   xmm0, xmm0
0x180010ba0  mov     [rbp+0AB0h+var_B10], r15w
0x180010ba5  lea     rax, [rbp+0AB0h+var_B10]
0x180010ba9  movdqa  xmmword ptr [rbp+0AB0h+hKey], xmm0
0x180010bae  lea     r12d, [r15+1]
0x180010bb2  mov     [rbp+0AB0h+var_B20], rax
0x180010bb6  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180010bba  mov     [rbp+0AB0h+var_B18], r12d
0x180010bbe  call    cs:__imp_InitializeCriticalSection
0x180010bc5  nop     dword ptr [rax+rax+00h]
0x180010bca  xorps   xmm0, xmm0
0x180010bcd  mov     [rsp+0BB0h+var_B68], r12d
0x180010bd2  lea     rax, [rsp+0BB0h+var_B60]
0x180010bd7  movdqa  xmmword ptr [rsp+0BB0h+var_B80], xmm0
0x180010bdd  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180010be2  mov     [rsp+0BB0h+var_B70], rax
0x180010be7  mov     [rsp+0BB0h+var_B60], r15w
0x180010bed  call    cs:__imp_InitializeCriticalSection
0x180010bf4  nop     dword ptr [rax+rax+00h]
0x180010bf9  mov     [rbp+0AB0h+var_2C8], 13Eh
0x180010c03  lea     rax, [rbp+0AB0h+var_2C0]
0x180010c0a  mov     [rbp+0AB0h+var_2D0], rax
0x180010c11  lea     rax, [rbp+0AB0h+var_AD0]
0x180010c15  mov     [rbp+0AB0h+hMem], rax
0x180010c19  lea     r13d, [r15+40h]
0x180010c1d  mov     dword ptr [rbp+0AB0h+hMem+8], r13d
0x180010c21  mov     edx, r15d
0x180010c24  mov     ecx, esi
0x180010c26  test    esi, esi
0x180010c28  jz      loc_18001117F
0x180010c2e  sub     ecx, r12d
0x180010c31  jz      loc_18001117F
0x180010c37  sub     ecx, r12d
0x180010c3a  jnz     loc_1800111F2
0x180010c40  lea     rdx, aS1518_0; "S-1-5-18"
0x180010c47  mov     [rsp+0BB0h+var_B90], rdx
0x180010c4c  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180010c53  mov     edx, 13Eh; unsigned __int64
0x180010c58  lea     r8, aSS_0; "%s\\%s"
0x180010c5f  lea     rcx, [rbp+0AB0h+var_2C0]; unsigned __int16 *
0x180010c66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010c6b  mov     ebx, eax
0x180010c6d  cmp     dword ptr [rbp+0AB0h+hMem+8], r13d
0x180010c71  jle     short loc_180010C83
0x180010c73  mov     rcx, [rbp+0AB0h+hMem]; hMem
0x180010c77  call    cs:__imp_GlobalFree
0x180010c7e  nop     dword ptr [rax+rax+00h]
0x180010c83  test    ebx, ebx
0x180010c85  jnz     loc_180010D57
0x180010c8b  mov     r9, [rbp+0AB0h+var_2D0]
0x180010c92  lea     rax, [rbp+0AB0h+var_AD0]
0x180010c96  mov     r13d, 400h
0x180010c9c  mov     [rsp+0BB0h+var_B88], r14
0x180010ca1  lea     rbx, aProducts; "Products"
0x180010ca8  mov     dword ptr [rbp+0AB0h+hMem+8], r13d
0x180010cac  mov     edx, r13d; unsigned __int64
0x180010caf  mov     [rbp+0AB0h+hMem], rax
0x180010cb3  lea     r8, aSSS; "%s\\%s\\%s"
0x180010cba  mov     [rsp+0BB0h+var_B90], rbx
0x180010cbf  lea     rcx, [rbp+0AB0h+var_AD0]; unsigned __int16 *
0x180010cc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010cc8  test    eax, eax
0x180010cca  js      loc_180011141
0x180010cd0  mov     rbx, [rbp+0AB0h+hMem]
0x180010cd4  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180010cd8  call    cs:__imp_EnterCriticalSection
0x180010cdf  nop     dword ptr [rax+rax+00h]
0x180010ce4  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x180010ce8  test    rcx, rcx
0x180010ceb  jz      short loc_180010D05
0x180010ced  call    cs:__imp_RegCloseKey
0x180010cf4  nop     dword ptr [rax+rax+00h]
0x180010cf9  mov     rax, [rbp+0AB0h+var_B20]
0x180010cfd  mov     [rbp+0AB0h+hKey], r15
0x180010d01  mov     [rax], r15w
0x180010d05  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180010d09  call    cs:__imp_LeaveCriticalSection
0x180010d10  nop     dword ptr [rax+rax+00h]
0x180010d15  cmp     cs:?g_fWoW@@3_NA, r15b; bool g_fWoW
0x180010d1c  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180010d23  jz      loc_1800111A4
0x180010d29  lea     rax, [rbp+0AB0h+hKey]
0x180010d2d  xor     r8d, r8d
0x180010d30  mov     [rsp+0BB0h+var_B90], rax
0x180010d35  mov     rdx, rbx
0x180010d38  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180010d3f  mov     rcx, 0FFFFFFFF80000002h
0x180010d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d4b  mov     ebx, eax
0x180010d4d  cmp     dword ptr [rbp+0AB0h+hMem+8], r13d
0x180010d51  jg      loc_18001121A
0x180010d57  cmp     [rbp+0AB0h+var_2C8], 13Eh
0x180010d61  jg      loc_18001122F
0x180010d67  test    ebx, ebx
0x180010d69  jz      loc_1800110A3
0x180010d6f  lea     rbx, aProducts; "Products"
0x180010d76  cmp     esi, r12d
0x180010d79  jz      loc_180011247
0x180010d7f  xorps   xmm0, xmm0
0x180010d82  mov     [rbp+0AB0h+var_AC8], r12d
0x180010d86  lea     rax, [rbp+0AB0h+var_AC0]
0x180010d8a  movdqa  xmmword ptr [rbp+0AB0h+hMem], xmm0
0x180010d8f  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180010d93  mov     [rbp+0AB0h+var_AD0], rax
0x180010d97  mov     [rbp+0AB0h+var_AC0], r15w
0x180010d9c  call    cs:__imp_InitializeCriticalSection
0x180010da3  nop     dword ptr [rax+rax+00h]
0x180010da8  lea     rax, [rbp+0AB0h+hMem]
0x180010dac  mov     byte ptr [rsp+0BB0h+var_B88], r15b
0x180010db1  mov     r9, r14
0x180010db4  mov     [rsp+0BB0h+var_B90], rax
0x180010db9  mov     r8, rbx
0x180010dbc  mov     rdx, rdi
0x180010dbf  mov     ecx, esi
0x180010dc1  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x180010dc6  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180010dca  test    eax, eax
0x180010dcc  jnz     loc_180010F54
0x180010dd2  call    cs:__imp_EnterCriticalSection
0x180010dd9  nop     dword ptr [rax+rax+00h]
0x180010dde  mov     rcx, [rbp+0AB0h+hMem]; hKey
0x180010de2  test    rcx, rcx
0x180010de5  jz      short loc_180010DFF
0x180010de7  call    cs:__imp_RegCloseKey
0x180010dee  nop     dword ptr [rax+rax+00h]
0x180010df3  mov     rax, [rbp+0AB0h+var_AD0]
0x180010df7  mov     [rbp+0AB0h+hMem], r15
0x180010dfb  mov     [rax], r15w
0x180010dff  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180010e03  call    cs:__imp_LeaveCriticalSection
0x180010e0a  nop     dword ptr [rax+rax+00h]
0x180010e0f  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180010e13  call    cs:__imp_DeleteCriticalSection
0x180010e1a  nop     dword ptr [rax+rax+00h]
0x180010e1f  cmp     [rbp+0AB0h+var_AC8], r12d
0x180010e23  jle     short loc_180010E35
0x180010e25  mov     rcx, [rbp+0AB0h+var_AD0]; hMem
0x180010e29  call    cs:__imp_GlobalFree
0x180010e30  nop     dword ptr [rax+rax+00h]
0x180010e35  lea     rax, [rbp+0AB0h+var_AC0]
0x180010e39  mov     [rbp+0AB0h+var_AC8], r12d
0x180010e3d  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180010e42  mov     [rbp+0AB0h+var_AD0], rax
0x180010e46  call    cs:__imp_EnterCriticalSection
0x180010e4d  nop     dword ptr [rax+rax+00h]
0x180010e52  mov     rcx, [rsp+0BB0h+var_B80]; hKey
0x180010e57  test    rcx, rcx
0x180010e5a  jz      short loc_180010E76
0x180010e5c  call    cs:__imp_RegCloseKey
0x180010e63  nop     dword ptr [rax+rax+00h]
0x180010e68  mov     rax, [rsp+0BB0h+var_B70]
0x180010e6d  mov     [rsp+0BB0h+var_B80], r15
0x180010e72  mov     [rax], r15w
0x180010e76  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180010e7b  call    cs:__imp_LeaveCriticalSection
0x180010e82  nop     dword ptr [rax+rax+00h]
0x180010e87  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180010e8c  call    cs:__imp_DeleteCriticalSection
0x180010e93  nop     dword ptr [rax+rax+00h]
0x180010e98  cmp     [rsp+0BB0h+var_B68], r12d
0x180010e9d  jle     short loc_180010EB0
0x180010e9f  mov     rcx, [rsp+0BB0h+var_B70]; hMem
0x180010ea4  call    cs:__imp_GlobalFree
0x180010eab  nop     dword ptr [rax+rax+00h]
0x180010eb0  lea     rax, [rsp+0BB0h+var_B60]
0x180010eb5  mov     [rsp+0BB0h+var_B68], r12d
0x180010eba  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180010ebe  mov     [rsp+0BB0h+var_B70], rax
0x180010ec3  call    cs:__imp_EnterCriticalSection
0x180010eca  nop     dword ptr [rax+rax+00h]
0x180010ecf  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x180010ed3  test    rcx, rcx
0x180010ed6  jz      short loc_180010EF0
0x180010ed8  call    cs:__imp_RegCloseKey
0x180010edf  nop     dword ptr [rax+rax+00h]
0x180010ee4  mov     rax, [rbp+0AB0h+var_B20]
0x180010ee8  mov     [rbp+0AB0h+hKey], r15
0x180010eec  mov     [rax], r15w
0x180010ef0  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180010ef4  call    cs:__imp_LeaveCriticalSection
0x180010efb  nop     dword ptr [rax+rax+00h]
0x180010f00  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180010f04  call    cs:__imp_DeleteCriticalSection
0x180010f0b  nop     dword ptr [rax+rax+00h]
0x180010f10  cmp     [rbp+0AB0h+var_B18], r12d
0x180010f14  jle     short loc_180010F26
0x180010f16  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x180010f1a  call    cs:__imp_GlobalFree
0x180010f21  nop     dword ptr [rax+rax+00h]
0x180010f26  mov     al, r12b
0x180010f29  mov     rcx, [rbp+0AB0h+var_40]
0x180010f30  xor     rcx, rsp; StackCookie
0x180010f33  call    __security_check_cookie
0x180010f38  mov     rbx, [rsp+0BB0h+arg_10]
0x180010f40  add     rsp, 0B80h
0x180010f47  pop     r15
0x180010f49  pop     r14
0x180010f4b  pop     r13
0x180010f4d  pop     r12
0x180010f4f  pop     rdi
0x180010f50  pop     rsi
0x180010f51  pop     rbp
0x180010f52  retn
0x180010f54  call    cs:__imp_EnterCriticalSection
0x180010f5b  nop     dword ptr [rax+rax+00h]
0x180010f60  mov     rcx, [rbp+0AB0h+hMem]; hKey
0x180010f64  test    rcx, rcx
0x180010f67  jz      short loc_180010F81
0x180010f69  call    cs:__imp_RegCloseKey
0x180010f70  nop     dword ptr [rax+rax+00h]
0x180010f75  mov     rax, [rbp+0AB0h+var_AD0]
0x180010f79  mov     [rbp+0AB0h+hMem], r15
0x180010f7d  mov     [rax], r15w
0x180010f81  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180010f85  call    cs:__imp_LeaveCriticalSection
0x180010f8c  nop     dword ptr [rax+rax+00h]
0x180010f91  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180010f95  call    cs:__imp_DeleteCriticalSection
0x180010f9c  nop     dword ptr [rax+rax+00h]
0x180010fa1  cmp     [rbp+0AB0h+var_AC8], r12d
0x180010fa5  jle     short loc_180010FB7
0x180010fa7  mov     rcx, [rbp+0AB0h+var_AD0]; hMem
0x180010fab  call    cs:__imp_GlobalFree
0x180010fb2  nop     dword ptr [rax+rax+00h]
0x180010fb7  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180010fbc  call    cs:__imp_EnterCriticalSection
0x180010fc3  nop     dword ptr [rax+rax+00h]
0x180010fc8  mov     rcx, [rsp+0BB0h+var_B80]; hKey
0x180010fcd  test    rcx, rcx
0x180010fd0  jz      short loc_180010FEC
0x180010fd2  call    cs:__imp_RegCloseKey
0x180010fd9  nop     dword ptr [rax+rax+00h]
0x180010fde  mov     rax, [rsp+0BB0h+var_B70]
0x180010fe3  mov     [rsp+0BB0h+var_B80], r15
0x180010fe8  mov     [rax], r15w
0x180010fec  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180010ff1  call    cs:__imp_LeaveCriticalSection
0x180010ff8  nop     dword ptr [rax+rax+00h]
0x180010ffd  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180011002  call    cs:__imp_DeleteCriticalSection
0x180011009  nop     dword ptr [rax+rax+00h]
0x18001100e  cmp     [rsp+0BB0h+var_B68], r12d
0x180011013  jle     short loc_180011026
0x180011015  mov     rcx, [rsp+0BB0h+var_B70]; hMem
0x18001101a  call    cs:__imp_GlobalFree
0x180011021  nop     dword ptr [rax+rax+00h]
0x180011026  lea     rax, [rsp+0BB0h+var_B60]
0x18001102b  mov     [rsp+0BB0h+var_B68], r12d
0x180011030  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180011034  mov     [rsp+0BB0h+var_B70], rax
0x180011039  call    cs:__imp_EnterCriticalSection
0x180011040  nop     dword ptr [rax+rax+00h]
0x180011045  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x180011049  test    rcx, rcx
0x18001104c  jz      short loc_180011066
0x18001104e  call    cs:__imp_RegCloseKey
0x180011055  nop     dword ptr [rax+rax+00h]
0x18001105a  mov     rax, [rbp+0AB0h+var_B20]
0x18001105e  mov     [rbp+0AB0h+hKey], r15
0x180011062  mov     [rax], r15w
0x180011066  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18001106a  call    cs:__imp_LeaveCriticalSection
0x180011071  nop     dword ptr [rax+rax+00h]
0x180011076  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18001107a  call    cs:__imp_DeleteCriticalSection
0x180011081  nop     dword ptr [rax+rax+00h]
0x180011086  cmp     [rbp+0AB0h+var_B18], r12d
0x18001108a  jle     short loc_18001109C
0x18001108c  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x180011090  call    cs:__imp_GlobalFree
0x180011097  nop     dword ptr [rax+rax+00h]
0x18001109c  xor     al, al
0x18001109e  jmp     loc_180010F29
0x1800110a3  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x1800110a8  call    cs:__imp_EnterCriticalSection
0x1800110af  nop     dword ptr [rax+rax+00h]
0x1800110b4  mov     rcx, [rsp+0BB0h+var_B80]; hKey
0x1800110b9  test    rcx, rcx
0x1800110bc  jz      short loc_1800110D8
0x1800110be  call    cs:__imp_RegCloseKey
0x1800110c5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
