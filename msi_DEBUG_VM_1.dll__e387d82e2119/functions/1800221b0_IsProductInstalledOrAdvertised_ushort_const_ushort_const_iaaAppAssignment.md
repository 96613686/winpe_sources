# IsProductInstalledOrAdvertised(ushort const *,ushort const *,iaaAppAssignment)

- ea: `0x1800221b0`
- end: `0x1800227be`
- name: `?IsProductInstalledOrAdvertised@@YA_NPEBG0W4iaaAppAssignment@@@Z`
- size: `1550`
- prototype: `bool __high(const unsigned __int16 *, const unsigned __int16 *, enum iaaAppAssignment)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cca0`
- `0x180046dbc`

## callees

- `0x180015950`
- `0x180017a84`
- `0x180022120`
- `0x1800221b0`
- `0x1800227d0`
- `0x1800250d4`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002232d`
- `ADVAPI32!RegCloseKey` at `0x18002240f`
- `ADVAPI32!RegCloseKey` at `0x180022466`
- `ADVAPI32!RegCloseKey` at `0x1800224c4`
- `ADVAPI32!RegCloseKey` at `0x180022536`
- `ADVAPI32!RegCloseKey` at `0x180022581`
- `ADVAPI32!RegCloseKey` at `0x1800225df`
- `ADVAPI32!RegCloseKey` at `0x180022631`
- `ADVAPI32!RegCloseKey` at `0x18002232d`
- `ADVAPI32!RegCloseKey` at `0x18002240f`
- `ADVAPI32!RegCloseKey` at `0x180022466`
- `ADVAPI32!RegCloseKey` at `0x1800224c4`
- `ADVAPI32!RegCloseKey` at `0x180022536`
- `ADVAPI32!RegCloseKey` at `0x180022581`
- `ADVAPI32!RegCloseKey` at `0x1800225df`
- `ADVAPI32!RegCloseKey` at `0x180022631`
- `KERNEL32!InitializeCriticalSection` at `0x180022216`
- `KERNEL32!InitializeCriticalSection` at `0x18002223f`
- `KERNEL32!InitializeCriticalSection` at `0x1800223d0`
- `KERNEL32!InitializeCriticalSection` at `0x180022216`
- `KERNEL32!InitializeCriticalSection` at `0x18002223f`
- `KERNEL32!InitializeCriticalSection` at `0x1800223d0`
- `KERNEL32!DeleteCriticalSection` at `0x18002242f`
- `KERNEL32!DeleteCriticalSection` at `0x18002248a`
- `KERNEL32!DeleteCriticalSection` at `0x1800224e4`
- `KERNEL32!DeleteCriticalSection` at `0x180022556`
- `KERNEL32!DeleteCriticalSection` at `0x1800225a5`
- `KERNEL32!DeleteCriticalSection` at `0x1800225ff`
- `KERNEL32!DeleteCriticalSection` at `0x18002242f`
- `KERNEL32!DeleteCriticalSection` at `0x18002248a`
- `KERNEL32!DeleteCriticalSection` at `0x1800224e4`
- `KERNEL32!DeleteCriticalSection` at `0x180022556`
- `KERNEL32!DeleteCriticalSection` at `0x1800225a5`
- `KERNEL32!DeleteCriticalSection` at `0x1800225ff`
- `KERNEL32!LeaveCriticalSection` at `0x180022343`
- `KERNEL32!LeaveCriticalSection` at `0x180022425`
- `KERNEL32!LeaveCriticalSection` at `0x18002247f`
- `KERNEL32!LeaveCriticalSection` at `0x1800224da`
- `KERNEL32!LeaveCriticalSection` at `0x18002254c`
- `KERNEL32!LeaveCriticalSection` at `0x18002259a`
- `KERNEL32!LeaveCriticalSection` at `0x1800225f5`
- `KERNEL32!LeaveCriticalSection` at `0x18002264a`
- `KERNEL32!LeaveCriticalSection` at `0x180022343`
- `KERNEL32!LeaveCriticalSection` at `0x180022425`
- `KERNEL32!LeaveCriticalSection` at `0x18002247f`
- `KERNEL32!LeaveCriticalSection` at `0x1800224da`
- `KERNEL32!LeaveCriticalSection` at `0x18002254c`
- `KERNEL32!LeaveCriticalSection` at `0x18002259a`
- `KERNEL32!LeaveCriticalSection` at `0x1800225f5`
- `KERNEL32!LeaveCriticalSection` at `0x18002264a`
- `KERNEL32!EnterCriticalSection` at `0x18002231e`
- `KERNEL32!EnterCriticalSection` at `0x180022400`
- `KERNEL32!EnterCriticalSection` at `0x180022456`
- `KERNEL32!EnterCriticalSection` at `0x1800224b5`
- `KERNEL32!EnterCriticalSection` at `0x180022527`
- `KERNEL32!EnterCriticalSection` at `0x180022571`
- `KERNEL32!EnterCriticalSection` at `0x1800225d0`
- `KERNEL32!EnterCriticalSection` at `0x180022621`
- `KERNEL32!EnterCriticalSection` at `0x18002231e`
- `KERNEL32!EnterCriticalSection` at `0x180022400`
- `KERNEL32!EnterCriticalSection` at `0x180022456`
- `KERNEL32!EnterCriticalSection` at `0x1800224b5`
- `KERNEL32!EnterCriticalSection` at `0x180022527`
- `KERNEL32!EnterCriticalSection` at `0x180022571`
- `KERNEL32!EnterCriticalSection` at `0x1800225d0`
- `KERNEL32!EnterCriticalSection` at `0x180022621`
- `KERNEL32!GlobalFree` at `0x1800222c3`
- `KERNEL32!GlobalFree` at `0x18002243f`
- `KERNEL32!GlobalFree` at `0x18002249c`
- `KERNEL32!GlobalFree` at `0x1800224f4`
- `KERNEL32!GlobalFree` at `0x180022566`
- `KERNEL32!GlobalFree` at `0x1800225b7`
- `KERNEL32!GlobalFree` at `0x18002260f`
- `KERNEL32!GlobalFree` at `0x1800226d5`
- `KERNEL32!GlobalFree` at `0x18002276a`
- `KERNEL32!GlobalFree` at `0x180022779`
- `KERNEL32!GlobalFree` at `0x18002278b`
- `KERNEL32!GlobalFree` at `0x1800222c3`
- `KERNEL32!GlobalFree` at `0x18002243f`
- `KERNEL32!GlobalFree` at `0x18002249c`
- `KERNEL32!GlobalFree` at `0x1800224f4`
- `KERNEL32!GlobalFree` at `0x180022566`
- `KERNEL32!GlobalFree` at `0x1800225b7`
- `KERNEL32!GlobalFree` at `0x18002260f`
- `KERNEL32!GlobalFree` at `0x1800226d5`
- `KERNEL32!GlobalFree` at `0x18002276a`
- `KERNEL32!GlobalFree` at `0x180022779`
- `KERNEL32!GlobalFree` at `0x18002278b`

## string_xrefs

- `0x180022298`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x180022672`: `InstallProperties`

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
0x1800221b0  mov     [rsp-8+arg_10], rbx
0x1800221b5  push    rbp
0x1800221b6  push    rsi
0x1800221b7  push    rdi
0x1800221b8  push    r12
0x1800221ba  push    r13
0x1800221bc  push    r14
0x1800221be  push    r15
0x1800221c0  lea     rbp, [rsp-0A80h]
0x1800221c8  sub     rsp, 0B80h
0x1800221cf  mov     rax, cs:__security_cookie
0x1800221d6  xor     rax, rsp
0x1800221d9  mov     [rbp+0AB0h+var_40], rax
0x1800221e0  xor     r15d, r15d
0x1800221e3  mov     esi, r8d
0x1800221e6  mov     rdi, rdx
0x1800221e9  mov     r14, rcx
0x1800221ec  test    rcx, rcx
0x1800221ef  jz      loc_180022615
0x1800221f5  xorps   xmm0, xmm0
0x1800221f8  mov     [rbp+0AB0h+var_B10], r15w
0x1800221fd  lea     rax, [rbp+0AB0h+var_B10]
0x180022201  movdqa  xmmword ptr [rbp+0AB0h+hKey], xmm0
0x180022206  lea     r12d, [r15+1]
0x18002220a  mov     [rbp+0AB0h+var_B20], rax
0x18002220e  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180022212  mov     [rbp+0AB0h+var_B18], r12d
0x180022216  call    cs:__imp_InitializeCriticalSection
0x18002221c  xorps   xmm0, xmm0
0x18002221f  mov     [rsp+0BB0h+var_B68], r12d
0x180022224  lea     rax, [rsp+0BB0h+var_B60]
0x180022229  movdqa  xmmword ptr [rsp+0BB0h+var_B80], xmm0
0x18002222f  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180022234  mov     [rsp+0BB0h+var_B70], rax
0x180022239  mov     [rsp+0BB0h+var_B60], r15w
0x18002223f  call    cs:__imp_InitializeCriticalSection
0x180022245  mov     [rbp+0AB0h+var_2C8], 13Eh
0x18002224f  lea     rax, [rbp+0AB0h+var_2C0]
0x180022256  mov     [rbp+0AB0h+var_2D0], rax
0x18002225d  lea     rax, [rbp+0AB0h+var_AD0]
0x180022261  mov     [rbp+0AB0h+hMem], rax
0x180022265  lea     r13d, [r15+40h]
0x180022269  mov     dword ptr [rbp+0AB0h+hMem+8], r13d
0x18002226d  mov     edx, r15d
0x180022270  mov     ecx, esi
0x180022272  test    esi, esi
0x180022274  jz      loc_1800226E0
0x18002227a  sub     ecx, r12d
0x18002227d  jz      loc_1800226E0
0x180022283  sub     ecx, r12d
0x180022286  jnz     loc_180022753
0x18002228c  lea     rdx, aS1518; "S-1-5-18"
0x180022293  mov     [rsp+0BB0h+var_B90], rdx
0x180022298  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002229f  mov     edx, 13Eh; unsigned __int64
0x1800222a4  lea     r8, aSS_0; "%s\\%s"
0x1800222ab  lea     rcx, [rbp+0AB0h+var_2C0]; unsigned __int16 *
0x1800222b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800222b7  mov     ebx, eax
0x1800222b9  cmp     dword ptr [rbp+0AB0h+hMem+8], r13d
0x1800222bd  jle     short loc_1800222C9
0x1800222bf  mov     rcx, [rbp+0AB0h+hMem]; hMem
0x1800222c3  call    cs:__imp_GlobalFree
0x1800222c9  test    ebx, ebx
0x1800222cb  jnz     loc_18002238B
0x1800222d1  mov     r9, [rbp+0AB0h+var_2D0]
0x1800222d8  lea     rax, [rbp+0AB0h+var_AD0]
0x1800222dc  mov     r13d, 400h
0x1800222e2  mov     [rsp+0BB0h+var_B88], r14
0x1800222e7  lea     rbx, aProducts; "Products"
0x1800222ee  mov     dword ptr [rbp+0AB0h+hMem+8], r13d
0x1800222f2  mov     edx, r13d; unsigned __int64
0x1800222f5  mov     [rbp+0AB0h+hMem], rax
0x1800222f9  lea     r8, aSSS; "%s\\%s\\%s"
0x180022300  mov     [rsp+0BB0h+var_B90], rbx
0x180022305  lea     rcx, [rbp+0AB0h+var_AD0]; unsigned __int16 *
0x180022309  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002230e  test    eax, eax
0x180022310  js      loc_1800226A8
0x180022316  mov     rbx, [rbp+0AB0h+hMem]
0x18002231a  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18002231e  call    cs:__imp_EnterCriticalSection
0x180022324  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x180022328  test    rcx, rcx
0x18002232b  jz      short loc_18002233F
0x18002232d  call    cs:__imp_RegCloseKey
0x180022333  mov     rax, [rbp+0AB0h+var_B20]
0x180022337  mov     [rbp+0AB0h+hKey], r15
0x18002233b  mov     [rax], r15w
0x18002233f  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180022343  call    cs:__imp_LeaveCriticalSection
0x180022349  cmp     cs:?g_fWoW@@3_NA, r15b; bool g_fWoW
0x180022350  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180022357  jz      loc_180022705
0x18002235d  lea     rax, [rbp+0AB0h+hKey]
0x180022361  xor     r8d, r8d
0x180022364  mov     [rsp+0BB0h+var_B90], rax
0x180022369  mov     rdx, rbx
0x18002236c  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180022373  mov     rcx, 0FFFFFFFF80000002h
0x18002237a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002237f  mov     ebx, eax
0x180022381  cmp     dword ptr [rbp+0AB0h+hMem+8], r13d
0x180022385  jg      loc_180022775
0x18002238b  cmp     [rbp+0AB0h+var_2C8], 13Eh
0x180022395  jg      loc_180022784
0x18002239b  test    ebx, ebx
0x18002239d  jz      loc_18002261C
0x1800223a3  lea     rbx, aProducts; "Products"
0x1800223aa  cmp     esi, r12d
0x1800223ad  jz      loc_180022796
0x1800223b3  xorps   xmm0, xmm0
0x1800223b6  mov     [rbp+0AB0h+var_AC8], r12d
0x1800223ba  lea     rax, [rbp+0AB0h+var_AC0]
0x1800223be  movdqa  xmmword ptr [rbp+0AB0h+hMem], xmm0
0x1800223c3  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x1800223c7  mov     [rbp+0AB0h+var_AD0], rax
0x1800223cb  mov     [rbp+0AB0h+var_AC0], r15w
0x1800223d0  call    cs:__imp_InitializeCriticalSection
0x1800223d6  lea     rax, [rbp+0AB0h+hMem]
0x1800223da  mov     byte ptr [rsp+0BB0h+var_B88], r15b
0x1800223df  mov     r9, r14
0x1800223e2  mov     [rsp+0BB0h+var_B90], rax
0x1800223e7  mov     r8, rbx
0x1800223ea  mov     rdx, rdi
0x1800223ed  mov     ecx, esi
0x1800223ef  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x1800223f4  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x1800223f8  test    eax, eax
0x1800223fa  jnz     loc_180022527
0x180022400  call    cs:__imp_EnterCriticalSection
0x180022406  mov     rcx, [rbp+0AB0h+hMem]; hKey
0x18002240a  test    rcx, rcx
0x18002240d  jz      short loc_180022421
0x18002240f  call    cs:__imp_RegCloseKey
0x180022415  mov     rax, [rbp+0AB0h+var_AD0]
0x180022419  mov     [rbp+0AB0h+hMem], r15
0x18002241d  mov     [rax], r15w
0x180022421  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180022425  call    cs:__imp_LeaveCriticalSection
0x18002242b  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x18002242f  call    cs:__imp_DeleteCriticalSection
0x180022435  cmp     [rbp+0AB0h+var_AC8], r12d
0x180022439  jle     short loc_180022445
0x18002243b  mov     rcx, [rbp+0AB0h+var_AD0]; hMem
0x18002243f  call    cs:__imp_GlobalFree
0x180022445  lea     rax, [rbp+0AB0h+var_AC0]
0x180022449  mov     [rbp+0AB0h+var_AC8], r12d
0x18002244d  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180022452  mov     [rbp+0AB0h+var_AD0], rax
0x180022456  call    cs:__imp_EnterCriticalSection
0x18002245c  mov     rcx, [rsp+0BB0h+var_B80]; hKey
0x180022461  test    rcx, rcx
0x180022464  jz      short loc_18002247A
0x180022466  call    cs:__imp_RegCloseKey
0x18002246c  mov     rax, [rsp+0BB0h+var_B70]
0x180022471  mov     [rsp+0BB0h+var_B80], r15
0x180022476  mov     [rax], r15w
0x18002247a  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x18002247f  call    cs:__imp_LeaveCriticalSection
0x180022485  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x18002248a  call    cs:__imp_DeleteCriticalSection
0x180022490  cmp     [rsp+0BB0h+var_B68], r12d
0x180022495  jle     short loc_1800224A2
0x180022497  mov     rcx, [rsp+0BB0h+var_B70]; hMem
0x18002249c  call    cs:__imp_GlobalFree
0x1800224a2  lea     rax, [rsp+0BB0h+var_B60]
0x1800224a7  mov     [rsp+0BB0h+var_B68], r12d
0x1800224ac  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800224b0  mov     [rsp+0BB0h+var_B70], rax
0x1800224b5  call    cs:__imp_EnterCriticalSection
0x1800224bb  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x1800224bf  test    rcx, rcx
0x1800224c2  jz      short loc_1800224D6
0x1800224c4  call    cs:__imp_RegCloseKey
0x1800224ca  mov     rax, [rbp+0AB0h+var_B20]
0x1800224ce  mov     [rbp+0AB0h+hKey], r15
0x1800224d2  mov     [rax], r15w
0x1800224d6  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800224da  call    cs:__imp_LeaveCriticalSection
0x1800224e0  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800224e4  call    cs:__imp_DeleteCriticalSection
0x1800224ea  cmp     [rbp+0AB0h+var_B18], r12d
0x1800224ee  jle     short loc_1800224FA
0x1800224f0  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x1800224f4  call    cs:__imp_GlobalFree
0x1800224fa  mov     al, r12b
0x1800224fd  mov     rcx, [rbp+0AB0h+var_40]
0x180022504  xor     rcx, rsp; StackCookie
0x180022507  call    __security_check_cookie
0x18002250c  mov     rbx, [rsp+0BB0h+arg_10]
0x180022514  add     rsp, 0B80h
0x18002251b  pop     r15
0x18002251d  pop     r14
0x18002251f  pop     r13
0x180022521  pop     r12
0x180022523  pop     rdi
0x180022524  pop     rsi
0x180022525  pop     rbp
0x180022526  retn
0x180022527  call    cs:__imp_EnterCriticalSection
0x18002252d  mov     rcx, [rbp+0AB0h+hMem]; hKey
0x180022531  test    rcx, rcx
0x180022534  jz      short loc_180022548
0x180022536  call    cs:__imp_RegCloseKey
0x18002253c  mov     rax, [rbp+0AB0h+var_AD0]
0x180022540  mov     [rbp+0AB0h+hMem], r15
0x180022544  mov     [rax], r15w
0x180022548  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x18002254c  call    cs:__imp_LeaveCriticalSection
0x180022552  lea     rcx, [rbp+0AB0h+var_AB8]; lpCriticalSection
0x180022556  call    cs:__imp_DeleteCriticalSection
0x18002255c  cmp     [rbp+0AB0h+var_AC8], r12d
0x180022560  jle     short loc_18002256C
0x180022562  mov     rcx, [rbp+0AB0h+var_AD0]; hMem
0x180022566  call    cs:__imp_GlobalFree
0x18002256c  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180022571  call    cs:__imp_EnterCriticalSection
0x180022577  mov     rcx, [rsp+0BB0h+var_B80]; hKey
0x18002257c  test    rcx, rcx
0x18002257f  jz      short loc_180022595
0x180022581  call    cs:__imp_RegCloseKey
0x180022587  mov     rax, [rsp+0BB0h+var_B70]
0x18002258c  mov     [rsp+0BB0h+var_B80], r15
0x180022591  mov     [rax], r15w
0x180022595  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x18002259a  call    cs:__imp_LeaveCriticalSection
0x1800225a0  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x1800225a5  call    cs:__imp_DeleteCriticalSection
0x1800225ab  cmp     [rsp+0BB0h+var_B68], r12d
0x1800225b0  jle     short loc_1800225BD
0x1800225b2  mov     rcx, [rsp+0BB0h+var_B70]; hMem
0x1800225b7  call    cs:__imp_GlobalFree
0x1800225bd  lea     rax, [rsp+0BB0h+var_B60]
0x1800225c2  mov     [rsp+0BB0h+var_B68], r12d
0x1800225c7  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800225cb  mov     [rsp+0BB0h+var_B70], rax
0x1800225d0  call    cs:__imp_EnterCriticalSection
0x1800225d6  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x1800225da  test    rcx, rcx
0x1800225dd  jz      short loc_1800225F1
0x1800225df  call    cs:__imp_RegCloseKey
0x1800225e5  mov     rax, [rbp+0AB0h+var_B20]
0x1800225e9  mov     [rbp+0AB0h+hKey], r15
0x1800225ed  mov     [rax], r15w
0x1800225f1  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800225f5  call    cs:__imp_LeaveCriticalSection
0x1800225fb  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800225ff  call    cs:__imp_DeleteCriticalSection
0x180022605  cmp     [rbp+0AB0h+var_B18], r12d
0x180022609  jle     short loc_180022615
0x18002260b  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x18002260f  call    cs:__imp_GlobalFree
0x180022615  xor     al, al
0x180022617  jmp     loc_1800224FD
0x18002261c  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x180022621  call    cs:__imp_EnterCriticalSection
0x180022627  mov     rcx, [rsp+0BB0h+var_B80]; hKey
0x18002262c  test    rcx, rcx
0x18002262f  jz      short loc_180022645
0x180022631  call    cs:__imp_RegCloseKey
0x180022637  mov     rax, [rsp+0BB0h+var_B70]
0x18002263c  mov     [rsp+0BB0h+var_B80], r15
0x180022641  mov     [rax], r15w
0x180022645  lea     rcx, [rsp+0BB0h+var_B58]; lpCriticalSection
0x18002264a  call    cs:__imp_LeaveCriticalSection
0x180022650  cmp     cs:?g_fWoW@@3_NA, r15b; bool g_fWoW
0x180022657  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18002265e  jz      loc_180022730
0x180022664  mov     rcx, [rbp+0AB0h+hKey]
0x180022668  lea     rax, [rsp+0BB0h+var_B80]
0x18002266d  mov     [rsp+0BB0h+var_B90], rax
0x180022672  lea     rdx, aInstallpropert; "InstallProperties"
0x180022679  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180022680  xor     r8d, r8d
0x180022683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022688  test    eax, eax
0x18002268a  jnz     loc_1800223A3
0x180022690  lea     rcx, [rsp+0BB0h+var_B80]; this
0x180022695  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18002269a  lea     rcx, [rbp+0AB0h+hKey]; this
0x18002269e  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x1800226a3  jmp     loc_1800224FA
0x1800226a8  cmp     dword ptr [rbp+0AB0h+hMem+8], r13d
0x1800226ac  jg      loc_180022766
0x1800226b2  cmp     [rbp+0AB0h+var_2C8], 13Eh
0x1800226bc  lea     rax, [rbp+0AB0h+var_AD0]
0x1800226c0  mov     [rbp+0AB0h+hMem], rax
0x1800226c4  mov     dword ptr [rbp+0AB0h+hMem+8], r13d
0x1800226c8  jle     loc_1800223AA
0x1800226ce  mov     rcx, [rbp+0AB0h+var_2D0]; hMem
0x1800226d5  call    cs:__imp_GlobalFree
0x1800226db  jmp     loc_1800223AA
0x1800226e0  test    rdi, rdi
0x1800226e3  jnz     short loc_180022728
0x1800226e5  lea     rcx, [rbp+0AB0h+hMem]
0x1800226e9  mov     dword ptr [rbp+0AB0h+hMem+0Ch], r13d
0x1800226ed  call    ?GetCurrentUserStringSID@@YAKAEAV?$CAPITempBufferRef@G@@@Z; GetCurrentUserStringSID(CAPITempBufferRef<ushort> &)
0x1800226f2  mov     ebx, eax
0x1800226f4  test    eax, eax
  ... truncated ...
```
