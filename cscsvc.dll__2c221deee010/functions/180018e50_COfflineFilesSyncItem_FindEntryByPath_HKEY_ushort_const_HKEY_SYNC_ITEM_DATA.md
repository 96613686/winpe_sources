# COfflineFilesSyncItem::_FindEntryByPath(HKEY__ *,ushort const *,HKEY__ * *,_SYNC_ITEM_DATA *)

- ea: `0x180018e50`
- end: `0x180019194`
- name: `?_FindEntryByPath@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@PEAU_SYNC_ITEM_DATA@@@Z`
- size: `836`
- prototype: `LSTATUS __fastcall(COfflineFilesSyncItem *this, HKEY, const unsigned __int16 *, HKEY *, struct _SYNC_ITEM_DATA *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180019370`
- `0x18006a390`
- `0x18006a7b0`
- `0x18006add0`

## callees

- `0x180018e50`
- `0x18001919c`
- `0x180039610`
- `0x180039fb4`
- `0x18006aff8`
- `0x18006b070`
- `0x18006b0e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018eb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018eb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018efb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018f86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019091`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800190f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018efb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018f86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019091`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800190f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f1d`

## pseudocode

```c
LSTATUS __fastcall COfflineFilesSyncItem::_FindEntryByPath(
        COfflineFilesSyncItem *this,
        HKEY a2,
        const unsigned __int16 *a3,
        HKEY *a4,
        struct _SYNC_ITEM_DATA *a5)
{
  LSTATUS result; // eax
  LSTATUS v9; // eax
  signed int v10; // ebx
  signed int EntryLastBackgroundSyncTime; // edi
  LSTATUS v12; // eax
  COfflineFilesSyncItem *v13; // rcx
  COfflineFilesSyncItem *v14; // rcx
  COfflineFilesSyncItem *v15; // rcx
  COfflineFilesSyncItem *v16; // rcx
  COfflineFilesSyncItem *v17; // rcx
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  int v20; // ecx
  __m128i v21; // xmm4
  __m128i v22; // xmm3
  __m128i v23; // xmm2
  __int128 v24; // xmm1
  HKEY v25; // rax
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  DWORD Type; // [rsp+30h] [rbp-71h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-6Dh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-69h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-61h] BYREF
  BYTE v32[16]; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 v33[16]; // [rsp+60h] [rbp-41h] BYREF
  BYTE v34[16]; // [rsp+70h] [rbp-31h] BYREF
  BYTE v35[16]; // [rsp+80h] [rbp-21h] BYREF
  __m128i v36; // [rsp+90h] [rbp-11h]
  __m128i v37; // [rsp+A0h] [rbp-1h]
  int v38; // [rsp+B0h] [rbp+Fh]

  *a4 = 0;
  hKey = 0;
  memset_0(Data, 0, 0x74u);
  result = RegOpenKeyExW(a2, a3, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    cbData = 16;
    Type = 0;
    v9 = RegQueryValueExW(hKey, L"ID", 0, &Type, Data, &cbData);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_7;
    }
    else if ( Type != 3 )
    {
LABEL_6:
      v10 = -2147024883;
LABEL_7:
      EntryLastBackgroundSyncTime = v10;
      goto LABEL_8;
    }
    cbData = 8;
    Type = 0;
    v12 = RegQueryValueExW(hKey, L"LastSyncTime", 0, &Type, v32, &cbData);
    v10 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_7;
    }
    else if ( Type != 3 )
    {
      goto LABEL_6;
    }
    EntryLastBackgroundSyncTime = COfflineFilesSyncItem::_ReadEntryLastBackgroundSyncTime(
                                    v13,
                                    hKey,
                                    (struct _FILETIME *)&v32[8]);
    if ( EntryLastBackgroundSyncTime < 0 )
      goto LABEL_8;
    EntryLastBackgroundSyncTime = COfflineFilesSyncItem::_ReadEntryLastSyncStatus(
                                    v14,
                                    hKey,
                                    (enum _SYNC_STATUS_TYPE *)v33);
    if ( EntryLastBackgroundSyncTime < 0 )
      goto LABEL_8;
    EntryLastBackgroundSyncTime = COfflineFilesSyncItem::_ReadEntryLastSyncConflictCount(
                                    v15,
                                    hKey,
                                    (unsigned int *)&v33[4]);
    if ( EntryLastBackgroundSyncTime < 0 )
      goto LABEL_8;
    cbData = 8;
    EntryLastBackgroundSyncTime = COfflineFilesSyncItem::_ReadEntryValue(
                                    v16,
                                    hKey,
                                    L"LastSuccessfulSyncTime",
                                    &v33[8],
                                    &cbData,
                                    3u);
    if ( EntryLastBackgroundSyncTime < 0 )
      goto LABEL_8;
    cbData = 8;
    EntryLastBackgroundSyncTime = COfflineFilesSyncItem::_ReadEntryValue(v17, hKey, L"LastOnlineTime", v34, &cbData, 3u);
    if ( EntryLastBackgroundSyncTime < 0 )
      goto LABEL_8;
    cbData = 8;
    Type = 0;
    v18 = RegQueryValueExW(hKey, L"LastOfflineTime", 0, &Type, &v34[8], &cbData);
    EntryLastBackgroundSyncTime = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        EntryLastBackgroundSyncTime = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      EntryLastBackgroundSyncTime = 0;
      if ( Type != 3 )
        EntryLastBackgroundSyncTime = -2147024883;
    }
    if ( EntryLastBackgroundSyncTime < 0 )
      goto LABEL_8;
    cbData = 52;
    Type = 0;
    v19 = RegQueryValueExW(hKey, L"LastMappedDriveList", 0, &Type, v35, &cbData);
    EntryLastBackgroundSyncTime = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        EntryLastBackgroundSyncTime = (unsigned __int16)v19 | 0x80070000;
      if ( EntryLastBackgroundSyncTime == -2147024894 )
      {
        EntryLastBackgroundSyncTime = 0;
        v20 = 2359332;
        v23 = _mm_shuffle_epi32(_mm_cvtsi32_si128(0x240024u), 0);
        v22 = v23;
        v21 = v23;
        goto LABEL_37;
      }
    }
    else
    {
      EntryLastBackgroundSyncTime = 0;
      if ( Type != 3 )
        EntryLastBackgroundSyncTime = -2147024883;
    }
    if ( EntryLastBackgroundSyncTime < 0 )
    {
LABEL_8:
      if ( hKey )
        RegCloseKey(hKey);
      return EntryLastBackgroundSyncTime;
    }
    v20 = v38;
    v21 = v37;
    v22 = v36;
    v23 = *(__m128i *)v35;
LABEL_37:
    v24 = *(_OWORD *)v32;
    v25 = hKey;
    *(_OWORD *)a5 = *(_OWORD *)Data;
    v26 = *(_OWORD *)v33;
    *((_OWORD *)a5 + 1) = v24;
    v27 = *(_OWORD *)v34;
    *((_OWORD *)a5 + 2) = v26;
    *((_OWORD *)a5 + 3) = v27;
    *((__m128i *)a5 + 4) = v23;
    *((__m128i *)a5 + 5) = v22;
    *((__m128i *)a5 + 6) = v21;
    *((_DWORD *)a5 + 28) = v20;
    *a4 = v25;
    return EntryLastBackgroundSyncTime;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180018e50  mov     [rsp-8+arg_0], rbx
0x180018e55  push    rbp
0x180018e56  push    rsi
0x180018e57  push    rdi
0x180018e58  push    r14
0x180018e5a  push    r15
0x180018e5c  lea     rbp, [rsp-2Fh]
0x180018e61  sub     rsp, 0D0h
0x180018e68  mov     rax, cs:__security_cookie
0x180018e6f  xor     rax, rsp
0x180018e72  mov     [rbp+4Fh+var_30], rax
0x180018e76  mov     r14, [rbp+4Fh+arg_20]
0x180018e7a  lea     rcx, [rbp+4Fh+Data]; void *
0x180018e7e  mov     rdi, r8
0x180018e81  mov     rbx, rdx
0x180018e84  xor     r15d, r15d
0x180018e87  xor     edx, edx; Val
0x180018e89  mov     r8d, 74h ; 't'; Size
0x180018e8f  mov     [r9], r15
0x180018e92  mov     [rbp+4Fh+hKey], r15
0x180018e96  mov     rsi, r9
0x180018e99  call    memset_0
0x180018e9e  lea     rax, [rbp+4Fh+hKey]
0x180018ea2  mov     r9d, 2001Fh; samDesired
0x180018ea8  xor     r8d, r8d; ulOptions
0x180018eab  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180018eb0  mov     rdx, rdi; lpSubKey
0x180018eb3  mov     rcx, rbx; hKey
0x180018eb6  call    cs:__imp_RegOpenKeyExW
0x180018ebc  test    eax, eax
0x180018ebe  jz      short loc_180018ECC
0x180018ec0  jle     short loc_180018F25
0x180018ec2  movzx   eax, ax
0x180018ec5  or      eax, 80070000h
0x180018eca  jmp     short loc_180018F25
0x180018ecc  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180018ed0  lea     rax, [rbp+4Fh+cbData]
0x180018ed4  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180018ed9  lea     r9, [rbp+4Fh+Type]; lpType
0x180018edd  lea     rax, [rbp+4Fh+Data]
0x180018ee1  mov     [rbp+4Fh+cbData], 10h
0x180018ee8  xor     r8d, r8d; lpReserved
0x180018eeb  mov     [rsp+0F0h+phkResult], rax; lpData
0x180018ef0  lea     rdx, ?s_szValueName_ID@COfflineFilesSyncItem@@0QBGB; "ID"
0x180018ef7  mov     [rbp+4Fh+Type], r15d
0x180018efb  call    cs:__imp_RegQueryValueExW
0x180018f01  mov     ebx, eax
0x180018f03  test    eax, eax
0x180018f05  jnz     short loc_180018F48
0x180018f07  cmp     [rbp+4Fh+Type], 3
0x180018f0b  jz      short loc_180018F57
0x180018f0d  mov     ebx, 8007000Dh
0x180018f12  mov     edi, ebx
0x180018f14  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180018f18  test    rcx, rcx
0x180018f1b  jz      short loc_180018F23
0x180018f1d  call    cs:__imp_RegCloseKey
0x180018f23  mov     eax, edi
0x180018f25  mov     rcx, [rbp+4Fh+var_30]
0x180018f29  xor     rcx, rsp; StackCookie
0x180018f2c  call    __security_check_cookie
0x180018f31  mov     rbx, [rsp+0F0h+arg_0]
0x180018f39  add     rsp, 0D0h
0x180018f40  pop     r15
0x180018f42  pop     r14
0x180018f44  pop     rdi
0x180018f45  pop     rsi
0x180018f46  pop     rbp
0x180018f47  retn
0x180018f48  jle     short loc_180018F53
0x180018f4a  movzx   ebx, ax
0x180018f4d  or      ebx, 80070000h
0x180018f53  test    ebx, ebx
0x180018f55  js      short loc_180018F12
0x180018f57  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180018f5b  lea     rax, [rbp+4Fh+cbData]
0x180018f5f  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180018f64  lea     r9, [rbp+4Fh+Type]; lpType
0x180018f68  lea     rax, [rbp+4Fh+var_A0]
0x180018f6c  mov     [rbp+4Fh+cbData], 8
0x180018f73  xor     r8d, r8d; lpReserved
0x180018f76  mov     [rsp+0F0h+phkResult], rax; lpData
0x180018f7b  lea     rdx, ?s_szValueName_LastSyncTime@COfflineFilesSyncItem@@0QBGB; "LastSyncTime"
0x180018f82  mov     [rbp+4Fh+Type], r15d
0x180018f86  call    cs:__imp_RegQueryValueExW
0x180018f8c  mov     ebx, eax
0x180018f8e  test    eax, eax
0x180018f90  jnz     short loc_180018F9E
0x180018f92  cmp     [rbp+4Fh+Type], 3
0x180018f96  jnz     loc_180018F0D
0x180018f9c  jmp     short loc_180018FB1
0x180018f9e  jle     short loc_180018FA9
0x180018fa0  movzx   ebx, ax
0x180018fa3  or      ebx, 80070000h
0x180018fa9  test    ebx, ebx
0x180018fab  js      loc_180018F12
0x180018fb1  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180018fb5  lea     r8, [rbp+4Fh+var_A0+8]; struct _FILETIME *
0x180018fb9  call    ?_ReadEntryLastBackgroundSyncTime@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEAU_FILETIME@@@Z; COfflineFilesSyncItem::_ReadEntryLastBackgroundSyncTime(HKEY__ *,_FILETIME *)
0x180018fbe  mov     edi, eax
0x180018fc0  test    eax, eax
0x180018fc2  js      loc_180018F14
0x180018fc8  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180018fcc  lea     r8, [rbp+4Fh+var_90]; enum _SYNC_STATUS_TYPE *
0x180018fd0  call    ?_ReadEntryLastSyncStatus@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEAW4_SYNC_STATUS_TYPE@@@Z; COfflineFilesSyncItem::_ReadEntryLastSyncStatus(HKEY__ *,_SYNC_STATUS_TYPE *)
0x180018fd5  mov     edi, eax
0x180018fd7  test    eax, eax
0x180018fd9  js      loc_180018F14
0x180018fdf  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180018fe3  lea     r8, [rbp+4Fh+var_90+4]; unsigned int *
0x180018fe7  call    ?_ReadEntryLastSyncConflictCount@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEAK@Z; COfflineFilesSyncItem::_ReadEntryLastSyncConflictCount(HKEY__ *,ulong *)
0x180018fec  mov     edi, eax
0x180018fee  test    eax, eax
0x180018ff0  js      loc_180018F14
0x180018ff6  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180018ffa  lea     rax, [rbp+4Fh+cbData]
0x180018ffe  mov     dword ptr [rsp+0F0h+lpcbData], 3; unsigned int
0x180019006  lea     r9, [rbp+4Fh+var_90+8]; unsigned __int8 *
0x18001900a  lea     r8, ?s_szValueName_LastSuccessfulSyncTime@COfflineFilesSyncItem@@0QBGB; "LastSuccessfulSyncTime"
0x180019011  mov     [rsp+0F0h+phkResult], rax; unsigned int *
0x180019016  mov     [rbp+4Fh+cbData], 8
0x18001901d  call    ?_ReadEntryValue@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEBGPEAEPEAKK@Z; COfflineFilesSyncItem::_ReadEntryValue(HKEY__ *,ushort const *,uchar *,ulong *,ulong)
0x180019022  mov     edi, eax
0x180019024  test    eax, eax
0x180019026  js      loc_180018F14
0x18001902c  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180019030  lea     rax, [rbp+4Fh+cbData]
0x180019034  mov     dword ptr [rsp+0F0h+lpcbData], 3; unsigned int
0x18001903c  lea     r9, [rbp+4Fh+var_80]; unsigned __int8 *
0x180019040  lea     r8, ?s_szValueName_LastOnlineTime@COfflineFilesSyncItem@@0QBGB; "LastOnlineTime"
0x180019047  mov     [rsp+0F0h+phkResult], rax; unsigned int *
0x18001904c  mov     [rbp+4Fh+cbData], 8
0x180019053  call    ?_ReadEntryValue@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEBGPEAEPEAKK@Z; COfflineFilesSyncItem::_ReadEntryValue(HKEY__ *,ushort const *,uchar *,ulong *,ulong)
0x180019058  mov     edi, eax
0x18001905a  test    eax, eax
0x18001905c  js      loc_180018F14
0x180019062  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180019066  lea     rax, [rbp+4Fh+cbData]
0x18001906a  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18001906f  lea     r9, [rbp+4Fh+Type]; lpType
0x180019073  lea     rax, [rbp+4Fh+var_80+8]
0x180019077  mov     [rbp+4Fh+cbData], 8
0x18001907e  xor     r8d, r8d; lpReserved
0x180019081  mov     [rsp+0F0h+phkResult], rax; lpData
0x180019086  lea     rdx, ?s_szValueName_LastOfflineTime@COfflineFilesSyncItem@@0QBGB; "LastOfflineTime"
0x18001908d  mov     [rbp+4Fh+Type], r15d
0x180019091  call    cs:__imp_RegQueryValueExW
0x180019097  mov     edi, eax
0x180019099  mov     ebx, 8007000Dh
0x18001909e  test    eax, eax
0x1800190a0  jnz     short loc_1800190AF
0x1800190a2  cmp     [rbp+4Fh+Type], 3
0x1800190a6  mov     edi, r15d
0x1800190a9  jz      short loc_1800190BA
0x1800190ab  mov     edi, ebx
0x1800190ad  jmp     short loc_1800190BA
0x1800190af  jle     short loc_1800190BA
0x1800190b1  movzx   edi, ax
0x1800190b4  or      edi, 80070000h
0x1800190ba  test    edi, edi
0x1800190bc  js      loc_180018F14
0x1800190c2  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800190c6  lea     rax, [rbp+4Fh+cbData]
0x1800190ca  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x1800190cf  lea     r9, [rbp+4Fh+Type]; lpType
0x1800190d3  lea     rax, [rbp+4Fh+var_70]
0x1800190d7  mov     [rbp+4Fh+cbData], 34h ; '4'
0x1800190de  xor     r8d, r8d; lpReserved
0x1800190e1  mov     [rsp+0F0h+phkResult], rax; lpData
0x1800190e6  lea     rdx, ?s_szValueName_LastMappedDriveList@COfflineFilesSyncItem@@0QBGB; "LastMappedDriveList"
0x1800190ed  mov     [rbp+4Fh+Type], r15d
0x1800190f1  call    cs:__imp_RegQueryValueExW
0x1800190f7  mov     edi, eax
0x1800190f9  test    eax, eax
0x1800190fb  jnz     short loc_180019161
0x1800190fd  cmp     [rbp+4Fh+Type], 3
0x180019101  mov     edi, r15d
0x180019104  jz      short loc_180019108
0x180019106  mov     edi, ebx
0x180019108  test    edi, edi
0x18001910a  js      loc_180018F14
0x180019110  mov     ecx, [rbp+4Fh+var_40]
0x180019113  movaps  xmm4, [rbp+4Fh+var_50]
0x180019117  movaps  xmm3, [rbp+4Fh+var_60]
0x18001911b  movaps  xmm2, xmmword ptr [rbp+4Fh+var_70]
0x18001911f  movaps  xmm0, xmmword ptr [rbp+4Fh+Data]
0x180019123  movaps  xmm1, xmmword ptr [rbp+4Fh+var_A0]
0x180019127  mov     rax, [rbp+4Fh+hKey]
0x18001912b  movaps  xmmword ptr [r14], xmm0
0x18001912f  movaps  xmm0, xmmword ptr [rbp+4Fh+var_90]
0x180019133  movaps  xmmword ptr [r14+10h], xmm1
0x180019138  movaps  xmm1, xmmword ptr [rbp+4Fh+var_80]
0x18001913c  movaps  xmmword ptr [r14+20h], xmm0
0x180019141  movaps  xmmword ptr [r14+30h], xmm1
0x180019146  movaps  xmmword ptr [r14+40h], xmm2
0x18001914b  movaps  xmmword ptr [r14+50h], xmm3
0x180019150  movaps  xmmword ptr [r14+60h], xmm4
0x180019155  mov     [r14+70h], ecx
0x180019159  mov     [rsi], rax
0x18001915c  jmp     loc_180018F23
0x180019161  jle     short loc_18001916C
0x180019163  movzx   edi, ax
0x180019166  or      edi, 80070000h
0x18001916c  cmp     edi, 80070002h
0x180019172  jnz     short loc_180019108
0x180019174  mov     eax, 24h ; '$'
0x180019179  mov     edi, r15d
0x18001917c  mov     ecx, eax
0x18001917e  shl     ecx, 10h
0x180019181  or      ecx, eax
0x180019183  movd    xmm2, ecx
0x180019187  pshufd  xmm2, xmm2, 0
0x18001918c  movups  xmm3, xmm2
0x18001918f  movups  xmm4, xmm2
0x180019192  jmp     short loc_18001911F
```
