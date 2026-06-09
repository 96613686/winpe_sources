# GetAppliedPatchInfo(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &)

- ea: `0x18005de50`
- end: `0x18005e75c`
- name: `?GetAppliedPatchInfo@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@@Z`
- size: `2316`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005acec`

## callees

- `0x180010ac0`
- `0x180011280`
- `0x180013b7c`
- `0x18003c030`
- `0x18003e40c`
- `0x18003e4c0`
- `0x18005de50`
- `0x18005e764`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18005e159`
- `ADVAPI32!RegCloseKey` at `0x18005e25c`
- `ADVAPI32!RegCloseKey` at `0x18005e2d9`
- `ADVAPI32!RegCloseKey` at `0x18005e35d`
- `ADVAPI32!RegCloseKey` at `0x18005e400`
- `ADVAPI32!RegCloseKey` at `0x18005e46e`
- `ADVAPI32!RegCloseKey` at `0x18005e4f2`
- `ADVAPI32!RegCloseKey` at `0x18005e56a`
- `ADVAPI32!RegCloseKey` at `0x18005e159`
- `ADVAPI32!RegCloseKey` at `0x18005e25c`
- `ADVAPI32!RegCloseKey` at `0x18005e2d9`
- `ADVAPI32!RegCloseKey` at `0x18005e35d`
- `ADVAPI32!RegCloseKey` at `0x18005e400`
- `ADVAPI32!RegCloseKey` at `0x18005e46e`
- `ADVAPI32!RegCloseKey` at `0x18005e4f2`
- `ADVAPI32!RegCloseKey` at `0x18005e56a`
- `KERNEL32!InitializeCriticalSection` at `0x18005e037`
- `KERNEL32!InitializeCriticalSection` at `0x18005e06a`
- `KERNEL32!InitializeCriticalSection` at `0x18005e20d`
- `KERNEL32!InitializeCriticalSection` at `0x18005e037`
- `KERNEL32!InitializeCriticalSection` at `0x18005e06a`
- `KERNEL32!InitializeCriticalSection` at `0x18005e20d`
- `KERNEL32!DeleteCriticalSection` at `0x18005e28d`
- `KERNEL32!DeleteCriticalSection` at `0x18005e30e`
- `KERNEL32!DeleteCriticalSection` at `0x18005e38e`
- `KERNEL32!DeleteCriticalSection` at `0x18005e431`
- `KERNEL32!DeleteCriticalSection` at `0x18005e4a3`
- `KERNEL32!DeleteCriticalSection` at `0x18005e523`
- `KERNEL32!DeleteCriticalSection` at `0x18005e28d`
- `KERNEL32!DeleteCriticalSection` at `0x18005e30e`
- `KERNEL32!DeleteCriticalSection` at `0x18005e38e`
- `KERNEL32!DeleteCriticalSection` at `0x18005e431`
- `KERNEL32!DeleteCriticalSection` at `0x18005e4a3`
- `KERNEL32!DeleteCriticalSection` at `0x18005e523`
- `KERNEL32!LeaveCriticalSection` at `0x18005e17a`
- `KERNEL32!LeaveCriticalSection` at `0x18005e27d`
- `KERNEL32!LeaveCriticalSection` at `0x18005e2fd`
- `KERNEL32!LeaveCriticalSection` at `0x18005e37e`
- `KERNEL32!LeaveCriticalSection` at `0x18005e421`
- `KERNEL32!LeaveCriticalSection` at `0x18005e492`
- `KERNEL32!LeaveCriticalSection` at `0x18005e513`
- `KERNEL32!LeaveCriticalSection` at `0x18005e58e`
- `KERNEL32!LeaveCriticalSection` at `0x18005e17a`
- `KERNEL32!LeaveCriticalSection` at `0x18005e27d`
- `KERNEL32!LeaveCriticalSection` at `0x18005e2fd`
- `KERNEL32!LeaveCriticalSection` at `0x18005e37e`
- `KERNEL32!LeaveCriticalSection` at `0x18005e421`
- `KERNEL32!LeaveCriticalSection` at `0x18005e492`
- `KERNEL32!LeaveCriticalSection` at `0x18005e513`
- `KERNEL32!LeaveCriticalSection` at `0x18005e58e`
- `KERNEL32!EnterCriticalSection` at `0x18005e144`
- `KERNEL32!EnterCriticalSection` at `0x18005e247`
- `KERNEL32!EnterCriticalSection` at `0x18005e2c3`
- `KERNEL32!EnterCriticalSection` at `0x18005e348`
- `KERNEL32!EnterCriticalSection` at `0x18005e3eb`
- `KERNEL32!EnterCriticalSection` at `0x18005e458`
- `KERNEL32!EnterCriticalSection` at `0x18005e4dd`
- `KERNEL32!EnterCriticalSection` at `0x18005e554`
- `KERNEL32!EnterCriticalSection` at `0x18005e144`
- `KERNEL32!EnterCriticalSection` at `0x18005e247`
- `KERNEL32!EnterCriticalSection` at `0x18005e2c3`
- `KERNEL32!EnterCriticalSection` at `0x18005e348`
- `KERNEL32!EnterCriticalSection` at `0x18005e3eb`
- `KERNEL32!EnterCriticalSection` at `0x18005e458`
- `KERNEL32!EnterCriticalSection` at `0x18005e4dd`
- `KERNEL32!EnterCriticalSection` at `0x18005e554`
- `KERNEL32!GlobalFree` at `0x18005e0e4`
- `KERNEL32!GlobalFree` at `0x18005e2a3`
- `KERNEL32!GlobalFree` at `0x18005e326`
- `KERNEL32!GlobalFree` at `0x18005e447`
- `KERNEL32!GlobalFree` at `0x18005e4bb`
- `KERNEL32!GlobalFree` at `0x18005e539`
- `KERNEL32!GlobalFree` at `0x18005e625`
- `KERNEL32!GlobalFree` at `0x18005e6d6`
- `KERNEL32!GlobalFree` at `0x18005e6eb`
- `KERNEL32!GlobalFree` at `0x18005e703`
- `KERNEL32!GlobalFree` at `0x18005e741`
- `KERNEL32!GlobalFree` at `0x18005e0e4`
- `KERNEL32!GlobalFree` at `0x18005e2a3`
- `KERNEL32!GlobalFree` at `0x18005e326`
- `KERNEL32!GlobalFree` at `0x18005e447`
- `KERNEL32!GlobalFree` at `0x18005e4bb`
- `KERNEL32!GlobalFree` at `0x18005e539`
- `KERNEL32!GlobalFree` at `0x18005e625`
- `KERNEL32!GlobalFree` at `0x18005e6d6`
- `KERNEL32!GlobalFree` at `0x18005e6eb`
- `KERNEL32!GlobalFree` at `0x18005e703`
- `KERNEL32!GlobalFree` at `0x18005e741`

## string_xrefs

- `0x18005e0b9`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18005e5bc`: `InstallProperties`

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
  HKEY v27[2]; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+48h] [rbp-B8h]
  __int16 v30; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_CRITICAL_SECTION v31; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  HGLOBAL v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+98h] [rbp-68h]
  __int16 v35; // [rsp+A0h] [rbp-60h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+A8h] [rbp-58h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_CRITICAL_SECTION v38; // [rsp+F8h] [rbp-8h] BYREF
  HGLOBAL v39; // [rsp+8E0h] [rbp+7E0h]
  int v40; // [rsp+8E8h] [rbp+7E8h]
  unsigned __int16 v41[320]; // [rsp+8F0h] [rbp+7F0h] BYREF
  WCHAR v42; // [rsp+B70h] [rbp+A70h] BYREF
  __int128 v43; // [rsp+B72h] [rbp+A72h]
  __int128 v44; // [rsp+B82h] [rbp+A82h]
  __int128 v45; // [rsp+B92h] [rbp+A92h]
  __int128 v46; // [rsp+BA2h] [rbp+AA2h]
  __int16 v47; // [rsp+BC0h] [rbp+AC0h] BYREF
  __int128 v48; // [rsp+BC2h] [rbp+AC2h]
  __int128 v49; // [rsp+BD2h] [rbp+AD2h]
  __int128 v50; // [rsp+BE2h] [rbp+AE2h]
  __int128 v51; // [rsp+BF2h] [rbp+AF2h]

  if ( !a2 || !a4 || !a5 || a1 == 3 )
    return 87;
  v9 = 0;
  v42 = 0;
  v43 = 0;
  v47 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  while ( v9 < 38 )
  {
    v10 = v9++;
    if ( !a2[v10] )
      return 87;
  }
  if ( *a2 != 123 || a2[37] != 125 )
    return 87;
  v12 = qword_1802796B8;
  v13 = 0;
  v14 = qword_1802796B8;
  v15 = &v42;
  while ( v14 < &qword_1802796D8 )
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
  v19 = &v47;
  v20 = 0;
  while ( v12 < &qword_1802796D8 )
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
  v34 = 1;
  *v19 = 0;
  v33 = &v35;
  v35 = 0;
  *(_OWORD *)hKey = 0;
  InitializeCriticalSection(&CriticalSection);
  v29 = 1;
  v28 = &v30;
  v30 = 0;
  *(_OWORD *)v27 = 0;
  InitializeCriticalSection(&v31);
  v40 = 318;
  v39 = v41;
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
                             v41,
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
    if ( (int)StringCchPrintfW((unsigned __int16 *)&hMem.OwningThread, 0x400u, L"%s\\%s\\%s", v39, L"Products", &v42) < 0 )
    {
      if ( hMem.LockCount > 1024 )
        GlobalFree(hMem.DebugInfo);
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      hMem.LockCount = 1024;
      if ( v40 > 318 )
        GlobalFree(v39);
      goto LABEL_41;
    }
    v24 = hMem.DebugInfo;
    EnterCriticalSection(&CriticalSection);
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
      *(_WORD *)v33 = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    v25 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      LODWORD(v25) = g_samRead | 0x100;
    CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                             -2147483646,
                             v24,
                             0,
                             v25,
                             hKey);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
  }
LABEL_38:
  if ( v40 > 318 )
    GlobalFree(v39);
  if ( !CurrentUserStringSID )
  {
    EnterCriticalSection(&v31);
    if ( v27[0] )
    {
      RegCloseKey(v27[0]);
      v27[0] = 0;
      *(_WORD *)v28 = 0;
    }
    LeaveCriticalSection(&v31);
    v26 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      LODWORD(v26) = g_samRead | 0x100;
    if ( !(unsigned int)((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                          hKey[0],
                          L"InstallProperties",
                          0,
                          v26,
                          v27) )
    {
      CRegHandle::~CRegHandle((CRegHandle *)v27);
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
LABEL_55:
      if ( (unsigned __int8)PatchWasRoamed(a1, &v42, a3, &v47) )
        return 1647;
      else
        return GetAppliedPatchInfoInternal(a1, &v42, a3, (__int64)&v47);
    }
  }
LABEL_41:
  if ( a1 != 1 || !a3 || !*a3 || IsCurrentUser(a3) )
  {
    LODWORD(hMem.LockSemaphore) = 1;
    hMem.OwningThread = &hMem.SpinCount;
    LOWORD(hMem.SpinCount) = 0;
    *(_OWORD *)&hMem.DebugInfo = 0;
    InitializeCriticalSection(&v38);
    if ( !(unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(a1, a3, (WCHAR *)L"Products", &v42, &hMem, 0) )
    {
      EnterCriticalSection(&v38);
      if ( hMem.DebugInfo )
      {
        RegCloseKey((HKEY)hMem.DebugInfo);
        hMem.DebugInfo = 0;
        *(_WORD *)hMem.OwningThread = 0;
      }
      LeaveCriticalSection(&v38);
      DeleteCriticalSection(&v38);
      if ( SLODWORD(hMem.LockSemaphore) > 1 )
        GlobalFree(hMem.OwningThread);
      LODWORD(hMem.LockSemaphore) = 1;
      hMem.OwningThread = &hMem.SpinCount;
      EnterCriticalSection(&v31);
      if ( v27[0] )
      {
        RegCloseKey(v27[0]);
        v27[0] = 0;
        *(_WORD *)v28 = 0;
      }
      LeaveCriticalSection(&v31);
      DeleteCriticalSection(&v31);
      if ( v29 > 1 )
        GlobalFree(v28);
      v29 = 1;
      v28 = &v30;
      EnterCriticalSection(&CriticalSection);
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
        *(_WORD *)v33 = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      DeleteCriticalSection(&CriticalSection);
      if ( v34 > 1 )
        GlobalFree(v33);
      goto LABEL_55;
    }
    EnterCriticalSection(&v38);
    if ( hMem.DebugInfo )
    {
      RegCloseKey((HKEY)hMem.DebugInfo);
      hMem.DebugInfo = 0;
      *(_WORD *)hMem.OwningThread = 0;
    }
    LeaveCriticalSection(&v38);
    DeleteCriticalSection(&v38);
    if ( SLODWORD(hMem.LockSemaphore) > 1 )
      GlobalFree(hMem.OwningThread);
  }
  EnterCriticalSection(&v31);
  if ( v27[0] )
  {
    RegCloseKey(v27[0]);
    v27[0] = 0;
    *(_WORD *)v28 = 0;
  }
  LeaveCriticalSection(&v31);
  DeleteCriticalSection(&v31);
  if ( v29 > 1 )
    GlobalFree(v28);
  v29 = 1;
  v28 = &v30;
  EnterCriticalSection(&CriticalSection);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    *(_WORD *)v33 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( v34 > 1 )
    GlobalFree(v33);
  return 1605;
}

```

## disassembly

```asm
0x18005de50  mov     [rsp-8+arg_0], rbx
0x18005de55  mov     [rsp-8+arg_8], rsi
0x18005de5a  push    rbp
0x18005de5b  push    rdi
0x18005de5c  push    r12
0x18005de5e  push    r14
0x18005de60  push    r15
0x18005de62  lea     rbp, [rsp-0B20h]
0x18005de6a  sub     rsp, 0C20h
0x18005de71  mov     rax, cs:__security_cookie
0x18005de78  xor     rax, rsp
0x18005de7b  mov     [rbp+0B40h+var_30], rax
0x18005de82  mov     r15, [rbp+0B40h+arg_28]
0x18005de89  mov     rbx, r9
0x18005de8c  mov     r14, r8
0x18005de8f  mov     r11, rdx
0x18005de92  mov     esi, ecx
0x18005de94  test    rdx, rdx
0x18005de97  jz      short loc_18005DF11
0x18005de99  test    rbx, rbx
0x18005de9c  jz      short loc_18005DF11
0x18005de9e  mov     rdi, [rbp+0B40h+arg_20]
0x18005dea5  test    rdi, rdi
0x18005dea8  jz      short loc_18005DF11
0x18005deaa  cmp     ecx, 3
0x18005dead  jz      short loc_18005DF11
0x18005deaf  xorps   xmm0, xmm0
0x18005deb2  xor     eax, eax
0x18005deb4  mov     [rbp+0B40h+var_D0], ax
0x18005debb  movups  [rbp+0B40h+var_CE], xmm0
0x18005dec2  mov     [rbp+0B40h+var_80], ax
0x18005dec9  movups  [rbp+0B40h+var_BE], xmm0
0x18005ded0  movups  [rbp+0B40h+var_AE], xmm0
0x18005ded7  movups  [rbp+0B40h+var_9E], xmm0
0x18005dede  movups  [rbp+0B40h+var_7E], xmm0
0x18005dee5  movups  [rbp+0B40h+var_6E], xmm0
0x18005deec  movups  [rbp+0B40h+var_5E], xmm0
0x18005def3  movups  [rbp+0B40h+var_4E], xmm0
0x18005defa  nop     word ptr [rax+rax+00h]
0x18005df00  cmp     eax, 26h ; '&'
0x18005df03  jge     short loc_18005DF42
0x18005df05  movsxd  rcx, eax
0x18005df08  inc     eax
0x18005df0a  cmp     word ptr [rdx+rcx*2], 0
0x18005df0f  jnz     short loc_18005DF00
0x18005df11  mov     eax, 57h ; 'W'
0x18005df16  mov     rcx, [rbp+0B40h+var_30]
0x18005df1d  xor     rcx, rsp; StackCookie
0x18005df20  call    __security_check_cookie
0x18005df25  lea     r11, [rsp+0C40h+var_20]
0x18005df2d  mov     rbx, [r11+30h]
0x18005df31  mov     rsi, [r11+38h]
0x18005df35  mov     rsp, r11
0x18005df38  pop     r15
0x18005df3a  pop     r14
0x18005df3c  pop     r12
0x18005df3e  pop     rdi
0x18005df3f  pop     rbp
0x18005df40  retn
0x18005df42  cmp     word ptr [rdx], 7Bh ; '{'
0x18005df46  jnz     short loc_18005DF11
0x18005df48  cmp     word ptr [rdx+4Ah], 7Dh ; '}'
0x18005df4d  jnz     short loc_18005DF11
0x18005df4f  lea     rdx, qword_1802796B8
0x18005df56  xor     r9d, r9d
0x18005df59  mov     r8, rdx
0x18005df5c  lea     r10, [rbp+0B40h+var_D0]
0x18005df63  lea     r12, qword_1802796D8
0x18005df6a  nop     word ptr [rax+rax+00h]
0x18005df70  cmp     r8, r12
0x18005df73  jnb     short loc_18005DF94
0x18005df75  cmp     r9d, 21h ; '!'
0x18005df79  jnb     short loc_18005DF11
0x18005df7b  movzx   eax, byte ptr [r8]
0x18005df7f  inc     r8
0x18005df82  movzx   ecx, word ptr [r11+rax*2]
0x18005df87  mov     [r10], cx
0x18005df8b  add     r10, 2
0x18005df8f  inc     r9d
0x18005df92  jmp     short loc_18005DF70
0x18005df94  cmp     r9d, 21h ; '!'
0x18005df98  jnb     loc_18005DF11
0x18005df9e  xor     eax, eax
0x18005dfa0  mov     [r10], ax
0x18005dfa4  xor     ecx, ecx
0x18005dfa6  cmp     ecx, 26h ; '&'
0x18005dfa9  jge     short loc_18005DFBC
0x18005dfab  movsxd  rax, ecx
0x18005dfae  inc     ecx
0x18005dfb0  cmp     word ptr [rbx+rax*2], 0
0x18005dfb5  jnz     short loc_18005DFA6
0x18005dfb7  jmp     loc_18005DF11
0x18005dfbc  cmp     word ptr [rbx], 7Bh ; '{'
0x18005dfc0  jnz     loc_18005DF11
0x18005dfc6  cmp     word ptr [rbx+4Ah], 7Dh ; '}'
0x18005dfcb  jnz     loc_18005DF11
0x18005dfd1  lea     r9, [rbp+0B40h+var_80]
0x18005dfd8  xor     r8d, r8d
0x18005dfdb  nop     dword ptr [rax+rax+00h]
0x18005dfe0  cmp     rdx, r12
0x18005dfe3  jnb     short loc_18005E006
0x18005dfe5  cmp     r8d, 21h ; '!'
0x18005dfe9  jnb     loc_18005DF11
0x18005dfef  movzx   eax, byte ptr [rdx]
0x18005dff2  inc     rdx
0x18005dff5  movzx   ecx, word ptr [rbx+rax*2]
0x18005dff9  mov     [r9], cx
0x18005dffd  add     r9, 2
0x18005e001  inc     r8d
0x18005e004  jmp     short loc_18005DFE0
0x18005e006  cmp     r8d, 21h ; '!'
0x18005e00a  jnb     loc_18005DF11
0x18005e010  xor     eax, eax
0x18005e012  mov     [rbp+0B40h+var_BA8], 1
0x18005e019  mov     [r9], ax
0x18005e01d  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005e021  lea     rax, [rbp+0B40h+var_BA0]
0x18005e025  xorps   xmm0, xmm0
0x18005e028  mov     [rbp+0B40h+var_BB0], rax
0x18005e02c  xor     eax, eax
0x18005e02e  mov     [rbp+0B40h+var_BA0], ax
0x18005e032  movdqa  xmmword ptr [rbp+0B40h+hKey], xmm0
0x18005e037  call    cs:__imp_InitializeCriticalSection
0x18005e03e  nop     dword ptr [rax+rax+00h]
0x18005e043  lea     rax, [rsp+0C40h+var_BF0]
0x18005e048  mov     [rsp+0C40h+var_BF8], 1
0x18005e050  mov     [rsp+0C40h+var_C00], rax
0x18005e055  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005e05a  xor     eax, eax
0x18005e05c  xorps   xmm0, xmm0
0x18005e05f  mov     [rsp+0C40h+var_BF0], ax
0x18005e064  movdqa  xmmword ptr [rsp+0C40h+var_C10], xmm0
0x18005e06a  call    cs:__imp_InitializeCriticalSection
0x18005e071  nop     dword ptr [rax+rax+00h]
0x18005e076  mov     [rbp+0B40h+var_358], 13Eh
0x18005e080  lea     rax, [rbp+0B40h+var_350]
0x18005e087  mov     [rbp+0B40h+var_360], rax
0x18005e08e  lea     rax, [rbp+0B40h+var_B60]
0x18005e092  mov     [rbp+0B40h+hMem], rax
0x18005e096  lea     r12, aProducts; "Products"
0x18005e09d  mov     dword ptr [rbp+0B40h+hMem+8], 40h ; '@'
0x18005e0a4  cmp     esi, 2
0x18005e0a7  jnz     loc_18005E636
0x18005e0ad  lea     rcx, aS1518_0; "S-1-5-18"
0x18005e0b4  mov     [rsp+0C40h+var_C20], rcx
0x18005e0b9  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005e0c0  lea     rcx, [rbp+0B40h+var_350]; unsigned __int16 *
0x18005e0c7  mov     edx, 13Eh; unsigned __int64
0x18005e0cc  lea     r8, aSS_0; "%s\\%s"
0x18005e0d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e0d8  cmp     dword ptr [rbp+0B40h+hMem+8], 40h ; '@'
0x18005e0dc  mov     ebx, eax
0x18005e0de  jle     short loc_18005E0F0
0x18005e0e0  mov     rcx, [rbp+0B40h+hMem]; hMem
0x18005e0e4  call    cs:__imp_GlobalFree
0x18005e0eb  nop     dword ptr [rax+rax+00h]
0x18005e0f0  test    ebx, ebx
0x18005e0f2  jnz     loc_18005E1CB
0x18005e0f8  mov     r9, [rbp+0B40h+var_360]
0x18005e0ff  lea     rax, [rbp+0B40h+var_B60]
0x18005e103  mov     [rbp+0B40h+hMem], rax
0x18005e107  lea     r8, aSSS; "%s\\%s\\%s"
0x18005e10e  lea     rax, [rbp+0B40h+var_D0]
0x18005e115  mov     dword ptr [rbp+0B40h+hMem+8], 400h
0x18005e11c  mov     [rsp+0C40h+var_C18], rax
0x18005e121  lea     rcx, [rbp+0B40h+var_B60]; unsigned __int16 *
0x18005e125  mov     edx, 400h; unsigned __int64
0x18005e12a  mov     [rsp+0C40h+var_C20], r12
0x18005e12f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e134  test    eax, eax
0x18005e136  js      loc_18005E5F2
0x18005e13c  mov     rbx, [rbp+0B40h+hMem]
0x18005e140  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005e144  call    cs:__imp_EnterCriticalSection
0x18005e14b  nop     dword ptr [rax+rax+00h]
0x18005e150  mov     rcx, [rbp+0B40h+hKey]; hKey
0x18005e154  test    rcx, rcx
0x18005e157  jz      short loc_18005E176
0x18005e159  call    cs:__imp_RegCloseKey
0x18005e160  nop     dword ptr [rax+rax+00h]
0x18005e165  mov     rax, [rbp+0B40h+var_BB0]
0x18005e169  xor     ecx, ecx
0x18005e16b  mov     [rbp+0B40h+hKey], 0
0x18005e173  mov     [rax], cx
0x18005e176  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005e17a  call    cs:__imp_LeaveCriticalSection
0x18005e181  nop     dword ptr [rax+rax+00h]
0x18005e186  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18005e18d  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18005e194  jz      loc_18005E667
0x18005e19a  lea     rax, [rbp+0B40h+hKey]
0x18005e19e  xor     r8d, r8d
0x18005e1a1  mov     [rsp+0C40h+var_C20], rax
0x18005e1a6  mov     rdx, rbx
0x18005e1a9  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18005e1b0  mov     rcx, 0FFFFFFFF80000002h
0x18005e1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1bc  cmp     dword ptr [rbp+0B40h+hMem+8], 400h
0x18005e1c3  mov     ebx, eax
0x18005e1c5  jg      loc_18005E6E7
0x18005e1cb  cmp     [rbp+0B40h+var_358], 13Eh
0x18005e1d5  jg      loc_18005E6FC
0x18005e1db  test    ebx, ebx
0x18005e1dd  jz      loc_18005E54F
0x18005e1e3  cmp     esi, 1
0x18005e1e6  jz      loc_18005E714
0x18005e1ec  lea     rax, [rbp+0B40h+var_B50]
0x18005e1f0  mov     [rbp+0B40h+var_B58], 1
0x18005e1f7  mov     [rbp+0B40h+var_B60], rax
0x18005e1fb  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005e1ff  xor     eax, eax
0x18005e201  xorps   xmm0, xmm0
0x18005e204  mov     [rbp+0B40h+var_B50], ax
0x18005e208  movdqa  xmmword ptr [rbp+0B40h+hMem], xmm0
0x18005e20d  call    cs:__imp_InitializeCriticalSection
0x18005e214  nop     dword ptr [rax+rax+00h]
0x18005e219  lea     rax, [rbp+0B40h+hMem]
0x18005e21d  mov     byte ptr [rsp+0C40h+var_C18], 0
0x18005e222  lea     r9, [rbp+0B40h+var_D0]
0x18005e229  mov     [rsp+0C40h+var_C20], rax
0x18005e22e  mov     r8, r12
0x18005e231  mov     rdx, r14
0x18005e234  mov     ecx, esi
0x18005e236  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18005e23b  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005e23f  test    eax, eax
0x18005e241  jnz     loc_18005E3EB
0x18005e247  call    cs:__imp_EnterCriticalSection
0x18005e24e  nop     dword ptr [rax+rax+00h]
0x18005e253  mov     rcx, [rbp+0B40h+hMem]; hKey
0x18005e257  test    rcx, rcx
0x18005e25a  jz      short loc_18005E279
0x18005e25c  call    cs:__imp_RegCloseKey
0x18005e263  nop     dword ptr [rax+rax+00h]
0x18005e268  mov     rax, [rbp+0B40h+var_B60]
0x18005e26c  xor     ecx, ecx
0x18005e26e  mov     [rbp+0B40h+hMem], 0
0x18005e276  mov     [rax], cx
0x18005e279  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005e27d  call    cs:__imp_LeaveCriticalSection
0x18005e284  nop     dword ptr [rax+rax+00h]
0x18005e289  lea     rcx, [rbp+0B40h+var_B48]; lpCriticalSection
0x18005e28d  call    cs:__imp_DeleteCriticalSection
0x18005e294  nop     dword ptr [rax+rax+00h]
0x18005e299  cmp     [rbp+0B40h+var_B58], 1
0x18005e29d  jle     short loc_18005E2AF
0x18005e29f  mov     rcx, [rbp+0B40h+var_B60]; hMem
0x18005e2a3  call    cs:__imp_GlobalFree
0x18005e2aa  nop     dword ptr [rax+rax+00h]
0x18005e2af  lea     rax, [rbp+0B40h+var_B50]
0x18005e2b3  mov     [rbp+0B40h+var_B58], 1
0x18005e2ba  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005e2bf  mov     [rbp+0B40h+var_B60], rax
0x18005e2c3  call    cs:__imp_EnterCriticalSection
0x18005e2ca  nop     dword ptr [rax+rax+00h]
0x18005e2cf  mov     rcx, [rsp+0C40h+var_C10]; hKey
0x18005e2d4  test    rcx, rcx
0x18005e2d7  jz      short loc_18005E2F8
0x18005e2d9  call    cs:__imp_RegCloseKey
0x18005e2e0  nop     dword ptr [rax+rax+00h]
0x18005e2e5  mov     rax, [rsp+0C40h+var_C00]
0x18005e2ea  xor     ecx, ecx
0x18005e2ec  mov     [rsp+0C40h+var_C10], 0
0x18005e2f5  mov     [rax], cx
0x18005e2f8  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005e2fd  call    cs:__imp_LeaveCriticalSection
0x18005e304  nop     dword ptr [rax+rax+00h]
0x18005e309  lea     rcx, [rsp+0C40h+var_BE8]; lpCriticalSection
0x18005e30e  call    cs:__imp_DeleteCriticalSection
0x18005e315  nop     dword ptr [rax+rax+00h]
0x18005e31a  cmp     [rsp+0C40h+var_BF8], 1
0x18005e31f  jle     short loc_18005E332
0x18005e321  mov     rcx, [rsp+0C40h+var_C00]; hMem
0x18005e326  call    cs:__imp_GlobalFree
0x18005e32d  nop     dword ptr [rax+rax+00h]
0x18005e332  lea     rax, [rsp+0C40h+var_BF0]
0x18005e337  mov     [rsp+0C40h+var_BF8], 1
0x18005e33f  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005e343  mov     [rsp+0C40h+var_C00], rax
0x18005e348  call    cs:__imp_EnterCriticalSection
0x18005e34f  nop     dword ptr [rax+rax+00h]
0x18005e354  mov     rcx, [rbp+0B40h+hKey]; hKey
0x18005e358  test    rcx, rcx
0x18005e35b  jz      short loc_18005E37A
0x18005e35d  call    cs:__imp_RegCloseKey
0x18005e364  nop     dword ptr [rax+rax+00h]
0x18005e369  mov     rax, [rbp+0B40h+var_BB0]
0x18005e36d  xor     ecx, ecx
0x18005e36f  mov     [rbp+0B40h+hKey], 0
0x18005e377  mov     [rax], cx
0x18005e37a  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005e37e  call    cs:__imp_LeaveCriticalSection
0x18005e385  nop     dword ptr [rax+rax+00h]
0x18005e38a  lea     rcx, [rbp+0B40h+CriticalSection]; lpCriticalSection
0x18005e38e  call    cs:__imp_DeleteCriticalSection
0x18005e395  nop     dword ptr [rax+rax+00h]
0x18005e39a  cmp     [rbp+0B40h+var_BA8], 1
0x18005e39e  jg      loc_18005E73D
0x18005e3a4  lea     r9, [rbp+0B40h+var_80]
0x18005e3ab  mov     r8, r14
  ... truncated ...
```
