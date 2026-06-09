# COfflineFilesSyncItem::_CreateEntry(HKEY__ *,ushort const *,_GUID const &,HKEY__ * *)

- ea: `0x18006abe8`
- end: `0x18006adc8`
- name: `?_CreateEntry@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEBGAEBU_GUID@@PEAPEAU2@@Z`
- size: `480`
- prototype: `__int64 __fastcall(COfflineFilesSyncItem *this, HKEY, const unsigned __int16 *, const BYTE *, HKEY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006a390`

## callees

- `0x18006abe8`
- `0x18006b154`
- `0x18006b1a4`
- `0x18006b1f4`
- `0x18006b244`
- `0x18006b294`
- `0x18006b2e0`
- `0x18006b32c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ace2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ace2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006acc2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006acc2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ac88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ac88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006acfc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006acfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006ac2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006ac38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006ac2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006ac38`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncItem::_CreateEntry(
        COfflineFilesSyncItem *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        HKEY *a5)
{
  HKEY *v8; // rsi
  LSTATUS v9; // eax
  signed int SyncStatus; // ebx
  LSTATUS v11; // eax
  COfflineFilesSyncItem *v12; // rcx
  HKEY v13; // rcx
  COfflineFilesSyncItem *v15; // rcx
  COfflineFilesSyncItem *v16; // rcx
  COfflineFilesSyncItem *v17; // rcx
  COfflineFilesSyncItem *v18; // rcx
  COfflineFilesSyncItem *v19; // rcx
  COfflineFilesSyncItem *v20; // rcx
  int v21; // [rsp+58h] [rbp-11h] BYREF
  unsigned int v22; // [rsp+5Ch] [rbp-Dh] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  struct _FILETIME v24; // [rsp+68h] [rbp-1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+7h] BYREF
  struct _FILETIME v26; // [rsp+78h] [rbp+Fh] BYREF
  struct _FILETIME v27; // [rsp+80h] [rbp+17h] BYREF
  struct _FILETIME v28; // [rsp+88h] [rbp+1Fh] BYREF
  COfflineFilesSyncItem *dwDisposition; // [rsp+C8h] [rbp+5Fh] BYREF

  dwDisposition = this;
  v24 = 0;
  v26 = 0;
  v28 = 0;
  SystemTimeAsFileTime = 0;
  v27 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  GetSystemTimeAsFileTime(&v27);
  v8 = a5;
  v21 = 1;
  v22 = 0;
  *a5 = 0;
  LODWORD(dwDisposition) = 0;
  hKey = 0;
  v9 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x2001Fu, 0, &hKey, (LPDWORD)&dwDisposition);
  SyncStatus = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    return (unsigned int)SyncStatus;
  }
  v11 = RegSetValueExW(hKey, L"ID", 0, 3u, a4, 0x10u);
  SyncStatus = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      SyncStatus = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    SyncStatus = COfflineFilesSyncItem::_SetEntryLastSyncTime(v12, hKey, &v24);
    if ( SyncStatus >= 0 )
    {
      SyncStatus = COfflineFilesSyncItem::_SetEntryLastBackgroundSyncTime(v15, hKey, &SystemTimeAsFileTime);
      if ( SyncStatus >= 0 )
      {
        SyncStatus = COfflineFilesSyncItem::_SetEntryLastSyncStatus(v16, hKey, (const enum _SYNC_STATUS_TYPE *)&v21);
        if ( SyncStatus >= 0 )
        {
          SyncStatus = COfflineFilesSyncItem::_SetEntryLastSyncConflictCount(v17, hKey, &v22);
          if ( SyncStatus >= 0 )
          {
            SyncStatus = COfflineFilesSyncItem::_SetEntryLastSuccessfulSyncTime(v18, hKey, &v26);
            if ( SyncStatus >= 0 )
            {
              SyncStatus = COfflineFilesSyncItem::_SetEntryLastOnlineTime(v19, hKey, &v27);
              if ( SyncStatus >= 0 )
              {
                SyncStatus = COfflineFilesSyncItem::_SetEntryLastOfflineTime(v20, hKey, &v28);
                if ( SyncStatus >= 0 )
                {
                  v13 = 0;
                  *v8 = hKey;
                  hKey = 0;
                  goto LABEL_8;
                }
              }
            }
          }
        }
      }
    }
  }
  v13 = hKey;
LABEL_8:
  if ( v13 )
  {
    RegCloseKey(v13);
    hKey = 0;
  }
  if ( SyncStatus < 0 )
    RegDeleteKeyExW(a2, a3, 0, 0);
  return (unsigned int)SyncStatus;
}

```

## disassembly

```asm
0x18006abe8  mov     rax, rsp
0x18006abeb  mov     [rax+10h], rbx
0x18006abef  mov     [rax+18h], rsi
0x18006abf3  mov     [rax+8], rcx
0x18006abf7  push    rbp
0x18006abf8  push    rdi
0x18006abf9  push    r12
0x18006abfb  push    r14
0x18006abfd  push    r15
0x18006abff  lea     rbp, [rax-57h]
0x18006ac03  sub     rsp, 90h
0x18006ac0a  xor     r12d, r12d
0x18006ac0d  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006ac11  mov     qword ptr [rbp+4Fh+var_50.dwLowDateTime], r12
0x18006ac15  mov     rdi, r9
0x18006ac18  mov     qword ptr [rbp+4Fh+var_40.dwLowDateTime], r12
0x18006ac1c  mov     r14, r8
0x18006ac1f  mov     qword ptr [rbp+4Fh+var_30.dwLowDateTime], r12
0x18006ac23  mov     r15, rdx
0x18006ac26  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], r12
0x18006ac2a  mov     qword ptr [rbp+4Fh+var_38.dwLowDateTime], r12
0x18006ac2e  call    cs:__imp_GetSystemTimeAsFileTime
0x18006ac34  lea     rcx, [rbp+4Fh+var_38]; lpSystemTimeAsFileTime
0x18006ac38  call    cs:__imp_GetSystemTimeAsFileTime
0x18006ac3e  mov     rsi, [rbp+4Fh+arg_20]
0x18006ac42  lea     rax, [rbp+4Fh+dwDisposition]
0x18006ac46  mov     [rsp+0B0h+lpdwDisposition], rax; lpdwDisposition
0x18006ac4b  xor     r9d, r9d; lpClass
0x18006ac4e  lea     rax, [rbp+4Fh+hKey]
0x18006ac52  mov     [rbp+4Fh+var_60], 1
0x18006ac59  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18006ac5e  xor     r8d, r8d; Reserved
0x18006ac61  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18006ac66  mov     rdx, r14; lpSubKey
0x18006ac69  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18006ac71  mov     rcx, r15; hKey
0x18006ac74  mov     [rsp+0B0h+dwOptions], r12d; dwOptions
0x18006ac79  mov     [rbp+4Fh+var_5C], r12d
0x18006ac7d  mov     [rsi], r12
0x18006ac80  mov     dword ptr [rbp+4Fh+dwDisposition], r12d
0x18006ac84  mov     [rbp+4Fh+hKey], r12
0x18006ac88  call    cs:__imp_RegCreateKeyExW
0x18006ac8e  mov     ebx, eax
0x18006ac90  test    eax, eax
0x18006ac92  jz      short loc_18006ACA1
0x18006ac94  jle     short loc_18006AD02
0x18006ac96  movzx   ebx, ax
0x18006ac99  or      ebx, 80070000h
0x18006ac9f  jmp     short loc_18006AD02
0x18006aca1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006aca5  lea     rdx, ?s_szValueName_ID@COfflineFilesSyncItem@@0QBGB; "ID"
0x18006acac  mov     [rsp+0B0h+samDesired], 10h; cbData
0x18006acb4  mov     r9d, 3; dwType
0x18006acba  xor     r8d, r8d; Reserved
0x18006acbd  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x18006acc2  call    cs:__imp_RegSetValueExW
0x18006acc8  mov     ebx, eax
0x18006acca  test    eax, eax
0x18006accc  jz      short loc_18006AD20
0x18006acce  jle     short loc_18006ACD9
0x18006acd0  movzx   ebx, ax
0x18006acd3  or      ebx, 80070000h
0x18006acd9  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006acdd  test    rcx, rcx
0x18006ace0  jz      short loc_18006ACEC
0x18006ace2  call    cs:__imp_RegCloseKey
0x18006ace8  mov     [rbp+4Fh+hKey], r12
0x18006acec  test    ebx, ebx
0x18006acee  jns     short loc_18006AD02
0x18006acf0  xor     r9d, r9d; Reserved
0x18006acf3  xor     r8d, r8d; samDesired
0x18006acf6  mov     rdx, r14; lpSubKey
0x18006acf9  mov     rcx, r15; hKey
0x18006acfc  call    cs:__imp_RegDeleteKeyExW
0x18006ad02  lea     r11, [rsp+0B0h+var_20]
0x18006ad0a  mov     eax, ebx
0x18006ad0c  mov     rbx, [r11+38h]
0x18006ad10  mov     rsi, [r11+40h]
0x18006ad14  mov     rsp, r11
0x18006ad17  pop     r15
0x18006ad19  pop     r14
0x18006ad1b  pop     r12
0x18006ad1d  pop     rdi
0x18006ad1e  pop     rbp
0x18006ad1f  retn
0x18006ad20  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ad24  lea     r8, [rbp+4Fh+var_50]; struct _FILETIME *
0x18006ad28  call    ?_SetEntryLastSyncTime@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBU_FILETIME@@@Z; COfflineFilesSyncItem::_SetEntryLastSyncTime(HKEY__ *,_FILETIME const &)
0x18006ad2d  mov     ebx, eax
0x18006ad2f  test    eax, eax
0x18006ad31  js      short loc_18006ACD9
0x18006ad33  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ad37  lea     r8, [rbp+4Fh+SystemTimeAsFileTime]; struct _FILETIME *
0x18006ad3b  call    ?_SetEntryLastBackgroundSyncTime@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBU_FILETIME@@@Z; COfflineFilesSyncItem::_SetEntryLastBackgroundSyncTime(HKEY__ *,_FILETIME const &)
0x18006ad40  mov     ebx, eax
0x18006ad42  test    eax, eax
0x18006ad44  js      short loc_18006ACD9
0x18006ad46  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ad4a  lea     r8, [rbp+4Fh+var_60]; enum _SYNC_STATUS_TYPE *
0x18006ad4e  call    ?_SetEntryLastSyncStatus@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBW4_SYNC_STATUS_TYPE@@@Z; COfflineFilesSyncItem::_SetEntryLastSyncStatus(HKEY__ *,_SYNC_STATUS_TYPE const &)
0x18006ad53  mov     ebx, eax
0x18006ad55  test    eax, eax
0x18006ad57  js      short loc_18006ACD9
0x18006ad59  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ad5d  lea     r8, [rbp+4Fh+var_5C]; unsigned int *
0x18006ad61  call    ?_SetEntryLastSyncConflictCount@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBK@Z; COfflineFilesSyncItem::_SetEntryLastSyncConflictCount(HKEY__ *,ulong const &)
0x18006ad66  mov     ebx, eax
0x18006ad68  test    eax, eax
0x18006ad6a  js      loc_18006ACD9
0x18006ad70  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ad74  lea     r8, [rbp+4Fh+var_40]; struct _FILETIME *
0x18006ad78  call    ?_SetEntryLastSuccessfulSyncTime@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBU_FILETIME@@@Z; COfflineFilesSyncItem::_SetEntryLastSuccessfulSyncTime(HKEY__ *,_FILETIME const &)
0x18006ad7d  mov     ebx, eax
0x18006ad7f  test    eax, eax
0x18006ad81  js      loc_18006ACD9
0x18006ad87  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ad8b  lea     r8, [rbp+4Fh+var_38]; struct _FILETIME *
0x18006ad8f  call    ?_SetEntryLastOnlineTime@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBU_FILETIME@@@Z; COfflineFilesSyncItem::_SetEntryLastOnlineTime(HKEY__ *,_FILETIME const &)
0x18006ad94  mov     ebx, eax
0x18006ad96  test    eax, eax
0x18006ad98  js      loc_18006ACD9
0x18006ad9e  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18006ada2  lea     r8, [rbp+4Fh+var_30]; struct _FILETIME *
0x18006ada6  call    ?_SetEntryLastOfflineTime@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@AEBU_FILETIME@@@Z; COfflineFilesSyncItem::_SetEntryLastOfflineTime(HKEY__ *,_FILETIME const &)
0x18006adab  mov     ebx, eax
0x18006adad  test    eax, eax
0x18006adaf  js      loc_18006ACD9
0x18006adb5  mov     rax, [rbp+4Fh+hKey]
0x18006adb9  mov     rcx, r12
0x18006adbc  mov     [rsi], rax
0x18006adbf  mov     [rbp+4Fh+hKey], rcx
0x18006adc3  jmp     loc_18006ACDD
```
