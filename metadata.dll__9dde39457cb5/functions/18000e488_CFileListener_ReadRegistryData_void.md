# CFileListener::ReadRegistryData(void)

- ea: `0x18000e488`
- end: `0x18000e6e5`
- name: `?ReadRegistryData@CFileListener@@SAJXZ`
- size: `605`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f110`

## callees

- `0x18000b5c4`
- `0x18000b644`
- `0x18000e488`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000e4fc`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e4fc`
- `ADVAPI32!RegCloseKey` at `0x18000e6a8`
- `ADVAPI32!RegCloseKey` at `0x18000e6a8`
- `KERNEL32!GetLastError` at `0x18000e4b3`
- `KERNEL32!GetLastError` at `0x18000e4b3`
- `IisRTL!?Reset@STRU@@QEAAXXZ` at `0x18000e511`
- `IisRTL!?Reset@STRU@@QEAAXXZ` at `0x18000e53f`
- `IisRTL!?Reset@STRU@@QEAAXXZ` at `0x18000e56d`
- `IisRTL!?Reset@STRU@@QEAAXXZ` at `0x18000e511`
- `IisRTL!?Reset@STRU@@QEAAXXZ` at `0x18000e53f`
- `IisRTL!?Reset@STRU@@QEAAXXZ` at `0x18000e56d`
- `IisRTL!IISInitializeCriticalSection` at `0x18000e4a9`
- `IisRTL!IISInitializeCriticalSection` at `0x18000e4a9`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000e656`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000e656`

## pseudocode

```c
__int64 CFileListener::ReadRegistryData(void)
{
  signed int LastError; // eax
  signed int RegString; // ebx
  int v2; // eax
  int v3; // eax
  unsigned int v5; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  if ( (unsigned int)IISInitializeCriticalSection(&CriticalSection) )
  {
    dword_180048758 = 1;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\InetStp", 0, 0x20019u, &hKey) )
    {
LABEL_25:
      RegString = 0;
      goto LABEL_26;
    }
    STRU::Reset((STRU *)g_struChangeNotificationDirectory);
    RegString = GetRegString(hKey, L"UNCMetabaseLocation", (struct STRU *)g_struChangeNotificationDirectory);
    if ( RegString < 0 )
      goto LABEL_26;
    STRU::Reset((STRU *)g_struUNCUserName);
    RegString = GetRegString(hKey, L"UNCMetabaseUserName", (struct STRU *)g_struUNCUserName);
    if ( RegString < 0 )
      goto LABEL_26;
    STRU::Reset((STRU *)g_struUNCPassword);
    RegString = GetRegString(hKey, L"UNCMetabasePassword", (struct STRU *)g_struUNCPassword);
    if ( RegString < 0 )
      goto LABEL_26;
    g_dwUNCRetryInterval = 60;
    RegString = GetRegDWORD(hKey, L"UNCMetabaseRetryInterval", &g_dwUNCRetryInterval);
    if ( RegString < 0 )
      goto LABEL_26;
    if ( g_dwUNCRetryInterval - 10 <= 0x15176 )
    {
      v5 = 0;
      RegString = GetRegDWORD(hKey, L"UNCMetabaseEWRMode", &v5);
      if ( RegString < 0 )
        goto LABEL_26;
      if ( v5 )
      {
        if ( v5 != 1 )
          goto LABEL_32;
        v2 = 1;
      }
      else
      {
        v2 = 0;
      }
      dword_18004875C = v2;
      v5 = 0;
      RegString = GetRegDWORD(hKey, L"AutoPublish", &v5);
      if ( RegString < 0 )
        goto LABEL_26;
      if ( v5 )
      {
        if ( v5 != 1 )
          goto LABEL_32;
        v3 = 1;
      }
      else
      {
        v3 = 0;
      }
      dword_180048764 = v3;
      v5 = !STRU::IsEmpty((STRU *)g_struChangeNotificationDirectory);
      RegString = GetRegDWORD(hKey, L"MetabaseMode", &v5);
      if ( RegString < 0 )
        goto LABEL_26;
      if ( v5 )
      {
        if ( v5 != 1 )
        {
          if ( v5 == 2 )
          {
            dword_1800480A0 = 0;
            dword_180048760 = 1;
            goto LABEL_25;
          }
          goto LABEL_32;
        }
        dword_1800480A0 = 0;
      }
      else
      {
        dword_1800480A0 = 1;
      }
      dword_180048760 = 0;
      goto LABEL_25;
    }
LABEL_32:
    RegString = -2147024809;
    goto LABEL_26;
  }
  LastError = GetLastError();
  RegString = LastError;
  if ( LastError > 0 )
    RegString = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)RegString;
}

```

## disassembly

```asm
0x18000e488  mov     [rsp-8+arg_10], rbx
0x18000e48d  mov     [rsp-8+arg_18], rsi
0x18000e492  push    rbp
0x18000e493  mov     rbp, rsp
0x18000e496  sub     rsp, 30h
0x18000e49a  lea     rcx, CriticalSection
0x18000e4a1  mov     [rbp+hKey], 0
0x18000e4a9  call    cs:__imp_IISInitializeCriticalSection
0x18000e4af  test    eax, eax
0x18000e4b1  jnz     short loc_18000E4D1
0x18000e4b3  call    cs:__imp_GetLastError
0x18000e4b9  mov     ebx, eax
0x18000e4bb  test    eax, eax
0x18000e4bd  jle     loc_18000E69F
0x18000e4c3  movzx   ebx, ax
0x18000e4c6  or      ebx, 80070000h
0x18000e4cc  jmp     loc_18000E69F
0x18000e4d1  lea     rax, [rbp+hKey]
0x18000e4d5  mov     esi, 1
0x18000e4da  mov     r9d, 20019h; samDesired
0x18000e4e0  mov     cs:dword_180048758, esi
0x18000e4e6  xor     r8d, r8d; ulOptions
0x18000e4e9  mov     [rsp+30h+phkResult], rax; phkResult
0x18000e4ee  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\InetStp"
0x18000e4f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e4fc  call    cs:__imp_RegOpenKeyExW
0x18000e502  test    eax, eax
0x18000e504  jnz     loc_18000E69D
0x18000e50a  lea     rcx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; STRU g_struChangeNotificationDirectory
0x18000e511  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000e517  mov     rcx, [rbp+hKey]; hKey
0x18000e51b  lea     r8, ?g_struChangeNotificationDirectory@@3VSTRU@@A; struct STRU *
0x18000e522  lea     rdx, aUncmetabaseloc; "UNCMetabaseLocation"
0x18000e529  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAVSTRU@@@Z; GetRegString(HKEY__ *,ushort const *,STRU *)
0x18000e52e  mov     ebx, eax
0x18000e530  test    eax, eax
0x18000e532  js      loc_18000E69F
0x18000e538  lea     rcx, ?g_struUNCUserName@@3VSTRU@@A; STRU g_struUNCUserName
0x18000e53f  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000e545  mov     rcx, [rbp+hKey]; hKey
0x18000e549  lea     r8, ?g_struUNCUserName@@3VSTRU@@A; struct STRU *
0x18000e550  lea     rdx, aUncmetabaseuse; "UNCMetabaseUserName"
0x18000e557  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAVSTRU@@@Z; GetRegString(HKEY__ *,ushort const *,STRU *)
0x18000e55c  mov     ebx, eax
0x18000e55e  test    eax, eax
0x18000e560  js      loc_18000E69F
0x18000e566  lea     rcx, ?g_struUNCPassword@@3VSTRU@@A; STRU g_struUNCPassword
0x18000e56d  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000e573  mov     rcx, [rbp+hKey]; hKey
0x18000e577  lea     r8, ?g_struUNCPassword@@3VSTRU@@A; struct STRU *
0x18000e57e  lea     rdx, aUncmetabasepas; "UNCMetabasePassword"
0x18000e585  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAVSTRU@@@Z; GetRegString(HKEY__ *,ushort const *,STRU *)
0x18000e58a  mov     ebx, eax
0x18000e58c  test    eax, eax
0x18000e58e  js      loc_18000E69F
0x18000e594  mov     rcx, [rbp+hKey]; HKEY
0x18000e598  lea     r8, ?g_dwUNCRetryInterval@@3KA; unsigned int *
0x18000e59f  lea     rdx, aUncmetabaseret; "UNCMetabaseRetryInterval"
0x18000e5a6  mov     cs:?g_dwUNCRetryInterval@@3KA, 3Ch ; '<'; ulong g_dwUNCRetryInterval
0x18000e5b0  call    ?GetRegDWORD@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18000e5b5  mov     ebx, eax
0x18000e5b7  test    eax, eax
0x18000e5b9  js      loc_18000E69F
0x18000e5bf  mov     eax, cs:?g_dwUNCRetryInterval@@3KA; ulong g_dwUNCRetryInterval
0x18000e5c5  add     eax, 0FFFFFFF6h
0x18000e5c8  cmp     eax, 15176h
0x18000e5cd  ja      loc_18000E6DE
0x18000e5d3  mov     rcx, [rbp+hKey]; HKEY
0x18000e5d7  lea     r8, [rbp+arg_0]; unsigned int *
0x18000e5db  lea     rdx, aUncmetabaseewr; "UNCMetabaseEWRMode"
0x18000e5e2  mov     [rbp+arg_0], 0
0x18000e5e9  call    ?GetRegDWORD@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18000e5ee  mov     ebx, eax
0x18000e5f0  test    eax, eax
0x18000e5f2  js      loc_18000E69F
0x18000e5f8  mov     eax, [rbp+arg_0]
0x18000e5fb  test    eax, eax
0x18000e5fd  jz      short loc_18000E60B
0x18000e5ff  cmp     eax, esi
0x18000e601  jnz     loc_18000E6DE
0x18000e607  mov     eax, esi
0x18000e609  jmp     short loc_18000E60D
0x18000e60b  xor     eax, eax
0x18000e60d  mov     rcx, [rbp+hKey]; HKEY
0x18000e611  lea     r8, [rbp+arg_0]; unsigned int *
0x18000e615  lea     rdx, aAutopublish; "AutoPublish"
0x18000e61c  mov     cs:dword_18004875C, eax
0x18000e622  mov     [rbp+arg_0], 0
0x18000e629  call    ?GetRegDWORD@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18000e62e  mov     ebx, eax
0x18000e630  test    eax, eax
0x18000e632  js      short loc_18000E69F
0x18000e634  mov     eax, [rbp+arg_0]
0x18000e637  test    eax, eax
0x18000e639  jz      short loc_18000E647
0x18000e63b  cmp     eax, esi
0x18000e63d  jnz     loc_18000E6DE
0x18000e643  mov     eax, esi
0x18000e645  jmp     short loc_18000E649
0x18000e647  xor     eax, eax
0x18000e649  lea     rcx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; STRU g_struChangeNotificationDirectory
0x18000e650  mov     cs:dword_180048764, eax
0x18000e656  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000e65c  mov     rcx, [rbp+hKey]; HKEY
0x18000e660  lea     r8, [rbp+arg_0]; unsigned int *
0x18000e664  movzx   eax, al
0x18000e667  lea     rdx, aMetabasemode; "MetabaseMode"
0x18000e66e  xor     eax, esi
0x18000e670  mov     [rbp+arg_0], eax
0x18000e673  call    ?GetRegDWORD@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18000e678  mov     ebx, eax
0x18000e67a  test    eax, eax
0x18000e67c  js      short loc_18000E69F
0x18000e67e  mov     eax, [rbp+arg_0]
0x18000e681  test    eax, eax
0x18000e683  jz      short loc_18000E6CC
0x18000e685  sub     eax, esi
0x18000e687  jz      short loc_18000E6C0
0x18000e689  cmp     eax, esi
0x18000e68b  jnz     short loc_18000E6DE
0x18000e68d  mov     cs:dword_1800480A0, 0
0x18000e697  mov     cs:dword_180048760, esi
0x18000e69d  xor     ebx, ebx
0x18000e69f  mov     rcx, [rbp+hKey]; hKey
0x18000e6a3  test    rcx, rcx
0x18000e6a6  jz      short loc_18000E6AE
0x18000e6a8  call    cs:__imp_RegCloseKey
0x18000e6ae  mov     rsi, [rsp+30h+arg_18]
0x18000e6b3  mov     eax, ebx
0x18000e6b5  mov     rbx, [rsp+30h+arg_10]
0x18000e6ba  add     rsp, 30h
0x18000e6be  pop     rbp
0x18000e6bf  retn
0x18000e6c0  mov     cs:dword_1800480A0, 0
0x18000e6ca  jmp     short loc_18000E6D2
0x18000e6cc  mov     cs:dword_1800480A0, esi
0x18000e6d2  mov     cs:dword_180048760, 0
0x18000e6dc  jmp     short loc_18000E69D
0x18000e6de  mov     ebx, 80070057h
0x18000e6e3  jmp     short loc_18000E69F
```
