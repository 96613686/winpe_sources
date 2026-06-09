# StartScreenFilterp_ComparerCallback(void *,uchar)

- ea: `0x18000acf0`
- end: `0x18000b4a8`
- name: `?StartScreenFilterp_ComparerCallback@@YAXPEAXE@Z`
- size: `1976`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a480`
- `0x18000a750`
- `0x18000a7b4`
- `0x18000acf0`
- `0x18000b4b0`
- `0x18000b5f8`
- `0x18000b76c`
- `0x18000c560`
- `0x180012920`
- `0x1800212b0`
- `0x18003564c`
- `0x180038674`
- `0x18003f710`
- `0x18004e8b0`
- `0x18007a9cf`
- `0x180096d58`
- `0x1800f119c`
- `0x1800f1394`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x18000b063`
- `msvcrt!_wcslwr_s` at `0x18000b063`
- `msvcrt!wcsstr` at `0x18000b077`
- `msvcrt!wcsstr` at `0x18000b077`
- `msvcrt!_wcsicmp` at `0x18000b1a7`
- `msvcrt!_wcsicmp` at `0x18000b1a7`
- `ntdll!RtlFreeHeap` at `0x18000add2`
- `ntdll!RtlFreeHeap` at `0x18000ae24`
- `ntdll!RtlFreeHeap` at `0x18000aebe`
- `ntdll!RtlFreeHeap` at `0x18000aeee`
- `ntdll!RtlFreeHeap` at `0x18000af21`
- `ntdll!RtlFreeHeap` at `0x18000af52`
- `ntdll!RtlFreeHeap` at `0x18000add2`
- `ntdll!RtlFreeHeap` at `0x18000ae24`
- `ntdll!RtlFreeHeap` at `0x18000aebe`
- `ntdll!RtlFreeHeap` at `0x18000aeee`
- `ntdll!RtlFreeHeap` at `0x18000af21`
- `ntdll!RtlFreeHeap` at `0x18000af52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b461`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b44d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b44d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b01a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b359`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b48e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b49c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b01a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b359`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b48e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b49c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b007`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aea0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af87`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000afd0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000afd0`
- `WTSAPI32!WTSQueryUserToken` at `0x18000afb6`
- `WTSAPI32!WTSQueryUserToken` at `0x18000afb6`

## string_xrefs

- `0x18000ae64`: `StartScreenFilterp_ComparerCallback`
- `0x18000b02b`: `StartScreenFilterp_ComparerCallback`
- `0x18000b316`: `StartScreenFilterp_ComparerCallback`
- `0x18000b33c`: `StartScreenFilterp_ComparerCallback`
- `0x18000b379`: `StartScreenFilterp_ComparerCallback`
- `0x18000b309`: `Failed to get user token information from Session=%d [%d]`
- `0x18000b32f`: `Failed to get Active sessions user SID`
- `0x18000b3e3`: `Failed to mark shortcut as uninstaller [%d]`
- `0x18000b218`: `Failed to delete shortcut [%d]`
- `0x18000b2b4`: `Failed to delete shortcut [%d]`
- `0x18000b41a`: `Failed to delete shortcut [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall StartScreenFilterp_ComparerCallback(PVOID a1)
{
  HKEY v1; // r14
  HKEY v2; // r12
  __int64 v3; // rdx
  __int64 v4; // rdx
  int v5; // r8d
  const char *v6; // r9
  LSTATUS v7; // ebx
  DWORD i; // edi
  unsigned int v9; // eax
  wchar_t *v10; // rax
  unsigned int v11; // edx
  unsigned int CleansedString; // eax
  int v13; // eax
  DWORD v14; // r15d
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // esi
  unsigned __int64 j; // rdi
  __int64 v19; // rax
  const wchar_t **v20; // rdx
  LPCWSTR *v21; // rax
  int v22; // edx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  ULONG SessionId[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+80h] [rbp-80h]
  HANDLE HeapHandle[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v33; // [rsp+98h] [rbp-68h]
  __int128 v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v36[260]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v37[260]; // [rsp+2C8h] [rbp+1C8h] BYREF
  unsigned __int16 v38[260]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR ValueName[12]; // [rsp+6D8h] [rbp+5D8h] BYREF
  wchar_t String[520]; // [rsp+6F0h] [rbp+5F0h] BYREF
  unsigned __int16 v41[1040]; // [rsp+B00h] [rbp+A00h] BYREF
  unsigned __int16 v42[8]; // [rsp+1320h] [rbp+1220h] BYREF
  unsigned __int8 Sid[80]; // [rsp+1330h] [rbp+1230h] BYREF
  wchar_t String1[520]; // [rsp+1380h] [rbp+1280h] BYREF

  memset_0(String, 0, 0xC3Au);
  memset_0(v36, 0, 0x622u);
  RtlStringArray::RtlStringArray((RtlStringArray *)HeapHandle);
  RtlStringArray::RtlStringArray((RtlStringArray *)v28);
  memset_0(v36, 0, 0x622u);
  memset_0(String, 0, 0xC3Au);
  memset_0(Sid, 0, 0x44u);
  hMem = 0;
  v1 = 0;
  pullResult = 0;
  v2 = 0;
  SessionId[0] = 0;
  hObject = 0;
  RtlStringArray::Clear((RtlStringArray *)HeapHandle);
  if ( *((_QWORD *)&v34 + 1) )
    RtlFreeHeap(HeapHandle[0], 0, *((PVOID *)&v34 + 1));
  *(_OWORD *)HeapHandle = 0;
  v33 = 0;
  v34 = 0;
  v35 = 1;
  if ( (unsigned int)RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(HeapHandle, v3, 4, 4) )
  {
    v5 = 147;
    goto LABEL_8;
  }
  RtlStringArray::Clear((RtlStringArray *)v28);
  if ( *((_QWORD *)&v30 + 1) )
    RtlFreeHeap(v28[0], 0, *((PVOID *)&v30 + 1));
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 1;
  if ( (unsigned int)RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(v28, v4, 4, 4) )
  {
    v5 = 153;
LABEL_8:
    v6 = "Failed to initialize the string list [%d]";
LABEL_9:
    AslLogCallPrintf(1, (unsigned int)"StartScreenFilterp_ComparerCallback", v5, (_DWORD)v6);
    goto LABEL_10;
  }
  if ( PcaUtilityGetActiveUserSessionSid(SessionId, Sid) )
  {
    v6 = "Failed to find Active sessions [%d]";
    v5 = 163;
    goto LABEL_9;
  }
  if ( WTSQueryUserToken(SessionId[0], &hObject) )
  {
    if ( ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem) )
    {
      *(_QWORD *)SessionId = 0;
      v7 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\UFH\\ARP",
             0,
             0x20019u,
             (PHKEY)SessionId);
      if ( !v7 )
      {
        v2 = *(HKEY *)SessionId;
        v7 = 0;
      }
      RegCloseKey(HKEY_LOCAL_MACHINE);
      if ( v7 )
      {
        if ( *(_QWORD *)SessionId )
          RegCloseKey(*(HKEY *)SessionId);
        if ( v7 != 2 )
        {
          v6 = "Failed to initialize enum [%d]";
          v5 = 194;
          goto LABEL_9;
        }
      }
      else
      {
        for ( i = 0; ; ++i )
        {
          v9 = UfhRecentDataEnumArp((struct _UFH_ARP_INFO *)String, v2, i);
          if ( v9 == 259 )
            break;
          if ( v9 )
          {
            v6 = "Failed to enumerate arp items [%d]";
            v5 = 211;
            goto LABEL_9;
          }
          _wcslwr_s(String, 0x104u);
          v10 = wcsstr(String, L"wow6432");
          CleansedString = UfhGetCleansedString(String1, v11, v41, 0, hObject, v10 != 0);
          if ( CleansedString )
          {
            phkResult = CleansedString;
            AslLogCallPrintf(
              2,
              (unsigned int)"StartScreenFilterp_ComparerCallback",
              232,
              (unsigned int)"Failed to cleanse string [%d]");
          }
          else
          {
            RtlStringArray::Append((RtlStringArray *)HeapHandle, String1, 0);
            RtlStringArray::Append((RtlStringArray *)v28, v42, 0);
            memset_0(String, 0, 0xC3Au);
          }
        }
        if ( !(_QWORD)v33 )
          goto LABEL_10;
        v13 = UfhpUtilityRegOpenStoreKey(&pullResult, hMem, 1, 1, phkResult);
        if ( v13 )
        {
          if ( v13 != 2 )
            AslLogCallPrintf(
              1,
              (unsigned int)"StartScreenFilterp_ComparerCallback",
              256,
              (unsigned int)"Failed to initialize enum [%d]");
          v1 = (HKEY)pullResult;
        }
        else
        {
          v14 = 0;
          v1 = (HKEY)pullResult;
          while ( 1 )
          {
            v15 = UfhRecentDataEnumShortcut((struct _UFH_SHORTCUT_INFO *)v36, v1, v14);
            if ( v15 == 259 )
              break;
            if ( v15 )
            {
              v6 = "Failed to enumerate shortcut items [%d]";
              v5 = 271;
              goto LABEL_9;
            }
            if ( UfhGetCleansedString(String1, v16, v37, v38, hObject, 0) )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"StartScreenFilterp_ComparerCallback",
                282,
                (unsigned int)"Failed to cleanse string [%d]");
              if ( UfhRecentShortcutDeleteByIndex(ValueName, (const unsigned __int16 *)hMem) )
                AslLogCallPrintf(
                  1,
                  (unsigned int)"StartScreenFilterp_ComparerCallback",
                  290,
                  (unsigned int)"Failed to delete shortcut [%d]");
            }
            else
            {
              v17 = -1;
              for ( j = 0; j < (unsigned __int64)v33; ++j )
              {
                pullResult = 0;
                v19 = (unsigned __int64)HeapHandle[1] * j;
                if ( !is_mul_ok((unsigned __int64)HeapHandle[1], j)
                  || (v20 = (const wchar_t **)(*((_QWORD *)&v34 + 1) + v19),
                      (unsigned __int64)(*((_QWORD *)&v34 + 1) + v19) < *((_QWORD *)&v34 + 1)) )
                {
                  v20 = 0;
                }
                if ( !_wcsicmp(String1, *v20) )
                {
                  v17 = j;
                  break;
                }
              }
              if ( v17 == -1 )
              {
                ++v14;
              }
              else
              {
                if ( UfhShortcutMarkAsUninstaller(v36) )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"StartScreenFilterp_ComparerCallback",
                    305,
                    (unsigned int)"Failed to mark shortcut as uninstaller [%d]");
                if ( UfhRecentShortcutDeleteByIndex(ValueName, (const unsigned __int16 *)hMem) )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"StartScreenFilterp_ComparerCallback",
                    316,
                    (unsigned int)"Failed to delete shortcut [%d]");
                v21 = 0;
                if ( v17 < (unsigned __int64)v29 )
                {
                  pullResult = 0;
                  if ( ULongLongMult((ULONGLONG)v28[1], v17, &pullResult) < 0
                    || (v21 = (LPCWSTR *)(*((_QWORD *)&v30 + 1) + pullResult),
                        *((_QWORD *)&v30 + 1) + pullResult < *((_QWORD *)&v30 + 1)) )
                  {
                    v21 = 0;
                  }
                }
                if ( UfhRecentARPDeleteByIndex(*v21) )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"StartScreenFilterp_ComparerCallback",
                    321,
                    (unsigned int)"Failed to delete shortcut [%d]");
                RtlStringArray::Delete((RtlStringArray *)HeapHandle, v17);
                RtlStringArray::Delete((RtlStringArray *)v28, v17);
              }
              memset_0(v36, 0, 0x622u);
            }
          }
          if ( dword_1801594A0 )
          {
            EnterCriticalSection(&g_StartScreenFilterState);
            dword_1801594A0 = 0;
            LeaveCriticalSection(&g_StartScreenFilterState);
            if ( UfhResetArpShortcutData((unsigned __int16 *)hMem, v22) )
            {
              v6 = "Failed to reset recent data [%d]";
              v5 = 354;
              goto LABEL_9;
            }
          }
        }
      }
    }
    else
    {
      GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"StartScreenFilterp_ComparerCallback",
        183,
        (unsigned int)"Failed to get Active sessions user SID");
    }
  }
  else
  {
    GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"StartScreenFilterp_ComparerCallback",
      173,
      (unsigned int)"Failed to get user token information from Session=%d [%d]");
  }
LABEL_10:
  if ( hMem )
    LocalFree(hMem);
  if ( v1 )
    RegCloseKey(v1);
  if ( v2 )
    RegCloseKey(v2);
  if ( hObject )
    CloseHandle(hObject);
  RtlStringArray::Clear((RtlStringArray *)HeapHandle);
  if ( *((_QWORD *)&v34 + 1) )
    RtlFreeHeap(HeapHandle[0], 0, *((PVOID *)&v34 + 1));
  *(_OWORD *)HeapHandle = 0;
  v33 = 0;
  v34 = 0;
  RtlStringArray::Clear((RtlStringArray *)v28);
  if ( *((_QWORD *)&v30 + 1) )
    RtlFreeHeap(v28[0], 0, *((PVOID *)&v30 + 1));
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v30 = 0;
  RtlStringArray::Clear((RtlStringArray *)v28);
  if ( *((_QWORD *)&v30 + 1) )
    RtlFreeHeap(v28[0], 0, *((PVOID *)&v30 + 1));
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v30 = 0;
  RtlStringArray::Clear((RtlStringArray *)HeapHandle);
  if ( *((_QWORD *)&v34 + 1) )
    RtlFreeHeap(HeapHandle[0], 0, *((PVOID *)&v34 + 1));
}

```

## disassembly

```asm
0x18000acf0  push    rbp
0x18000acf2  push    rbx
0x18000acf3  push    rsi
0x18000acf4  push    rdi
0x18000acf5  push    r12
0x18000acf7  push    r13
0x18000acf9  push    r14
0x18000acfb  push    r15
0x18000acfd  lea     rbp, [rsp-16A8h]
0x18000ad05  mov     eax, 17A8h
0x18000ad0a  call    _alloca_probe
0x18000ad0f  sub     rsp, rax
0x18000ad12  mov     rax, cs:__security_cookie
0x18000ad19  xor     rax, rsp
0x18000ad1c  mov     [rbp+16E0h+var_50], rax
0x18000ad23  mov     r15d, 0C3Ah
0x18000ad29  mov     r8d, r15d; Size
0x18000ad2c  xor     edx, edx; Val
0x18000ad2e  lea     rcx, [rbp+16E0h+String]; void *
0x18000ad35  call    memset_0
0x18000ad3a  mov     ebx, 622h
0x18000ad3f  mov     r8d, ebx; Size
0x18000ad42  xor     edx, edx; Val
0x18000ad44  lea     rcx, [rbp+16E0h+var_1720]; void *
0x18000ad48  call    memset_0
0x18000ad4d  xor     r13d, r13d
0x18000ad50  mov     [rsp+17E0h+hMem], r13
0x18000ad55  mov     [rsp+17E0h+hObject], r13
0x18000ad5a  lea     rcx, [rbp+16E0h+HeapHandle]; this
0x18000ad5e  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18000ad63  nop
0x18000ad64  lea     rcx, [rsp+17E0h+var_1790]; this
0x18000ad69  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18000ad6e  nop
0x18000ad6f  mov     r8d, ebx; Size
0x18000ad72  xor     edx, edx; Val
0x18000ad74  lea     rcx, [rbp+16E0h+var_1720]; void *
0x18000ad78  call    memset_0
0x18000ad7d  mov     r8d, r15d; Size
0x18000ad80  xor     edx, edx; Val
0x18000ad82  lea     rcx, [rbp+16E0h+String]; void *
0x18000ad89  call    memset_0
0x18000ad8e  xor     edx, edx; Val
0x18000ad90  lea     r8d, [r13+44h]; Size
0x18000ad94  lea     rcx, [rbp+16E0h+Sid]; void *
0x18000ad9b  call    memset_0
0x18000ada0  mov     [rsp+17E0h+hMem], r13
0x18000ada5  mov     r14d, r13d
0x18000ada8  mov     [rsp+17E0h+pullResult], r13
0x18000adad  mov     r12d, r13d
0x18000adb0  mov     [rsp+17E0h+SessionId], r13d
0x18000adb5  mov     [rsp+17E0h+hObject], r13
0x18000adba  lea     rcx, [rbp+16E0h+HeapHandle]; this
0x18000adbe  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000adc3  mov     r8, [rbp+16E0h+P]; P
0x18000adc7  test    r8, r8
0x18000adca  jz      short loc_18000ADD8
0x18000adcc  xor     edx, edx; Flags
0x18000adce  mov     rcx, [rbp+16E0h+HeapHandle]; HeapHandle
0x18000add2  call    cs:__imp_RtlFreeHeap
0x18000add8  xorps   xmm0, xmm0
0x18000addb  movups  xmmword ptr [rbp+16E0h+HeapHandle], xmm0
0x18000addf  movups  [rbp+16E0h+var_1748], xmm0
0x18000ade3  movups  xmmword ptr [rbp-58h], xmm0
0x18000ade7  mov     esi, 1
0x18000adec  mov     [rbp+16E0h+var_1728], esi
0x18000adef  lea     ebx, [rsi+3]
0x18000adf2  mov     r9d, ebx
0x18000adf5  mov     r8d, ebx
0x18000adf8  lea     rcx, [rbp+16E0h+HeapHandle]
0x18000adfc  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x18000ae01  test    eax, eax
0x18000ae03  jnz     loc_18000AF7C
0x18000ae09  lea     rcx, [rsp+17E0h+var_1790]; this
0x18000ae0e  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000ae13  mov     r8, [rsp+17E0h+var_1768]; P
0x18000ae18  test    r8, r8
0x18000ae1b  jz      short loc_18000AE2A
0x18000ae1d  xor     edx, edx; Flags
0x18000ae1f  mov     rcx, [rsp+17E0h+var_1790]; HeapHandle
0x18000ae24  call    cs:__imp_RtlFreeHeap
0x18000ae2a  xorps   xmm0, xmm0
0x18000ae2d  movups  xmmword ptr [rsp+17E0h+var_1790], xmm0
0x18000ae32  movups  [rsp+17E0h+var_1780], xmm0
0x18000ae37  movups  xmmword ptr [rsp+70h], xmm0
0x18000ae3c  mov     [rbp+16E0h+var_1760], esi
0x18000ae3f  mov     r9, rbx
0x18000ae42  mov     r8, rbx
0x18000ae45  lea     rcx, [rsp+17E0h+var_1790]
0x18000ae4a  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x18000ae4f  test    eax, eax
0x18000ae51  jz      loc_18000AF92
0x18000ae57  mov     r8d, 99h
0x18000ae5d  lea     r9, aFailedToInitia_12; "Failed to initialize the string list [%"...
0x18000ae64  lea     rdx, aStartscreenfil_4; "StartScreenFilterp_ComparerCallback"
0x18000ae6b  mov     dword ptr [rsp+17E0h+phkResult], eax
0x18000ae6f  mov     ecx, esi
0x18000ae71  call    AslLogCallPrintf
0x18000ae76  mov     rcx, [rsp+17E0h+hMem]; hMem
0x18000ae7b  test    rcx, rcx
0x18000ae7e  jnz     loc_18000AF87
0x18000ae84  test    r14, r14
0x18000ae87  jnz     loc_18000B48B
0x18000ae8d  test    r12, r12
0x18000ae90  jnz     loc_18000B499
0x18000ae96  mov     rcx, [rsp+17E0h+hObject]; hObject
0x18000ae9b  test    rcx, rcx
0x18000ae9e  jz      short loc_18000AEA6
0x18000aea0  call    cs:__imp_CloseHandle
0x18000aea6  lea     rcx, [rbp+16E0h+HeapHandle]; this
0x18000aeaa  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000aeaf  mov     r8, [rbp+16E0h+P]; P
0x18000aeb3  test    r8, r8
0x18000aeb6  jz      short loc_18000AEC4
0x18000aeb8  xor     edx, edx; Flags
0x18000aeba  mov     rcx, [rbp+16E0h+HeapHandle]; HeapHandle
0x18000aebe  call    cs:__imp_RtlFreeHeap
0x18000aec4  xorps   xmm0, xmm0
0x18000aec7  movups  xmmword ptr [rbp+16E0h+HeapHandle], xmm0
0x18000aecb  movups  [rbp+16E0h+var_1748], xmm0
0x18000aecf  movups  xmmword ptr [rbp-58h], xmm0
0x18000aed3  lea     rcx, [rsp+17E0h+var_1790]; this
0x18000aed8  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000aedd  mov     r8, [rsp+17E0h+var_1768]; P
0x18000aee2  test    r8, r8
0x18000aee5  jz      short loc_18000AEF4
0x18000aee7  xor     edx, edx; Flags
0x18000aee9  mov     rcx, [rsp+17E0h+var_1790]; HeapHandle
0x18000aeee  call    cs:__imp_RtlFreeHeap
0x18000aef4  xorps   xmm0, xmm0
0x18000aef7  movups  xmmword ptr [rsp+17E0h+var_1790], xmm0
0x18000aefc  movups  [rsp+17E0h+var_1780], xmm0
0x18000af01  movups  xmmword ptr [rsp+70h], xmm0
0x18000af06  lea     rcx, [rsp+17E0h+var_1790]; this
0x18000af0b  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000af10  mov     r8, [rsp+17E0h+var_1768]; P
0x18000af15  test    r8, r8
0x18000af18  jz      short loc_18000AF28
0x18000af1a  xor     edx, edx; Flags
0x18000af1c  mov     rcx, [rsp+17E0h+var_1790]; HeapHandle
0x18000af21  call    cs:__imp_RtlFreeHeap
0x18000af27  nop
0x18000af28  xorps   xmm0, xmm0
0x18000af2b  movups  xmmword ptr [rsp+17E0h+var_1790], xmm0
0x18000af30  movups  [rsp+17E0h+var_1780], xmm0
0x18000af35  movups  xmmword ptr [rsp+70h], xmm0
0x18000af3a  lea     rcx, [rbp+16E0h+HeapHandle]; this
0x18000af3e  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000af43  mov     r8, [rbp+16E0h+P]; P
0x18000af47  test    r8, r8
0x18000af4a  jz      short loc_18000AF59
0x18000af4c  xor     edx, edx; Flags
0x18000af4e  mov     rcx, [rbp+16E0h+HeapHandle]; HeapHandle
0x18000af52  call    cs:__imp_RtlFreeHeap
0x18000af58  nop
0x18000af59  mov     rcx, [rbp+16E0h+var_50]
0x18000af60  xor     rcx, rsp; StackCookie
0x18000af63  call    __security_check_cookie
0x18000af68  add     rsp, 17A8h
0x18000af6f  pop     r15
0x18000af71  pop     r14
0x18000af73  pop     r13
0x18000af75  pop     r12
0x18000af77  pop     rdi
0x18000af78  pop     rsi
0x18000af79  pop     rbx
0x18000af7a  pop     rbp
0x18000af7b  retn
0x18000af7c  mov     r8d, 93h
0x18000af82  jmp     loc_18000AE5D
0x18000af87  call    cs:__imp_LocalFree
0x18000af8d  jmp     loc_18000AE84
0x18000af92  lea     rdx, [rbp+16E0h+Sid]; unsigned __int8 *
0x18000af99  lea     rcx, [rsp+17E0h+SessionId]; unsigned int *
0x18000af9e  call    ?PcaUtilityGetActiveUserSessionSid@@YAKPEAKPEAE@Z; PcaUtilityGetActiveUserSessionSid(ulong *,uchar *)
0x18000afa3  test    eax, eax
0x18000afa5  jnz     loc_18000B2E9
0x18000afab  lea     rdx, [rsp+17E0h+hObject]; phToken
0x18000afb0  mov     ebx, [rsp+17E0h+SessionId]
0x18000afb4  mov     ecx, ebx; SessionId
0x18000afb6  call    cs:__imp_WTSQueryUserToken
0x18000afbc  test    eax, eax
0x18000afbe  jz      loc_18000B2FB
0x18000afc4  lea     rdx, [rsp+17E0h+hMem]; StringSid
0x18000afc9  lea     rcx, [rbp+16E0h+Sid]; Sid
0x18000afd0  call    cs:__imp_ConvertSidToStringSidW
0x18000afd6  test    eax, eax
0x18000afd8  jz      loc_18000B329
0x18000afde  mov     qword ptr [rsp+17E0h+SessionId], r13
0x18000afe3  lea     rax, [rsp+17E0h+SessionId]
0x18000afe8  mov     [rsp+17E0h+phkResult], rax; phkResult
0x18000afed  mov     r9d, 20019h; samDesired
0x18000aff3  xor     r8d, r8d; ulOptions
0x18000aff6  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000affd  mov     rdi, 0FFFFFFFF80000002h
0x18000b004  mov     rcx, rdi; hKey
0x18000b007  call    cs:__imp_RegOpenKeyExW
0x18000b00d  mov     ebx, eax
0x18000b00f  test    eax, eax
0x18000b011  jz      loc_18000B249
0x18000b017  mov     rcx, rdi; hKey
0x18000b01a  call    cs:__imp_RegCloseKey
0x18000b020  test    ebx, ebx
0x18000b022  jnz     loc_18000B34F
0x18000b028  mov     edi, r13d
0x18000b02b  lea     rbx, aStartscreenfil_4; "StartScreenFilterp_ComparerCallback"
0x18000b032  mov     r8d, edi; dwIndex
0x18000b035  mov     rdx, r12; hKey
0x18000b038  lea     rcx, [rbp+16E0h+String]; struct _UFH_ARP_INFO *
0x18000b03f  call    ?UfhRecentDataEnumArp@@YAKPEAU_UFH_ARP_INFO@@PEAUHKEY__@@K@Z; UfhRecentDataEnumArp(_UFH_ARP_INFO *,HKEY__ *,ulong)
0x18000b044  cmp     eax, 103h
0x18000b049  jz      loc_18000B0F1
0x18000b04f  test    eax, eax
0x18000b051  jnz     loc_18000B234
0x18000b057  mov     edx, 104h; SizeInWords
0x18000b05c  lea     rcx, [rbp+16E0h+String]; String
0x18000b063  call    cs:__imp__wcslwr_s
0x18000b069  lea     rdx, aWow6432; "wow6432"
0x18000b070  lea     rcx, [rbp+16E0h+String]; Str
0x18000b077  call    cs:__imp_wcsstr
0x18000b07d  mov     ecx, r13d
0x18000b080  test    rax, rax
0x18000b083  setnz   cl
0x18000b086  mov     [rsp+17E0h+var_17B8], ecx; int
0x18000b08a  mov     rax, [rsp+17E0h+hObject]
0x18000b08f  mov     [rsp+17E0h+phkResult], rax; void *
0x18000b094  xor     r9d, r9d; unsigned __int16 *
0x18000b097  lea     r8, [rbp+16E0h+var_CE0]; unsigned __int16 *
0x18000b09e  lea     rcx, [rbp+16E0h+String1]; unsigned __int16 *
0x18000b0a5  call    ?UfhGetCleansedString@@YAKPEAGK00PEAXH@Z; UfhGetCleansedString(ushort *,ulong,ushort *,ushort *,void *,int)
0x18000b0aa  test    eax, eax
0x18000b0ac  jnz     loc_18000B385
0x18000b0b2  xor     r8d, r8d; unsigned __int64
0x18000b0b5  lea     rdx, [rbp+16E0h+String1]; unsigned __int16 *
0x18000b0bc  lea     rcx, [rbp+16E0h+HeapHandle]; this
0x18000b0c0  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000b0c5  xor     r8d, r8d; unsigned __int64
0x18000b0c8  lea     rdx, [rbp+16E0h+var_4C0]; unsigned __int16 *
0x18000b0cf  lea     rcx, [rsp+17E0h+var_1790]; this
0x18000b0d4  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000b0d9  mov     r8, r15; Size
0x18000b0dc  xor     edx, edx; Val
0x18000b0de  lea     rcx, [rbp+16E0h+String]; void *
0x18000b0e5  call    memset_0
0x18000b0ea  add     edi, esi
0x18000b0ec  jmp     loc_18000B032
0x18000b0f1  cmp     qword ptr [rbp+16E0h+var_1748], r13
0x18000b0f5  jz      loc_18000AE76
0x18000b0fb  mov     r9d, esi
0x18000b0fe  mov     r8d, esi
0x18000b101  mov     rdx, [rsp+17E0h+hMem]
0x18000b106  lea     rcx, [rsp+17E0h+pullResult]
0x18000b10b  call    ?UfhpUtilityRegOpenStoreKey@@YAKPEAPEAUHKEY__@@PEAGW4_UFH_DATA_TYPE@@H@Z; UfhpUtilityRegOpenStoreKey(HKEY__ * *,ushort *,_UFH_DATA_TYPE,int)
0x18000b110  test    eax, eax
0x18000b112  jnz     loc_18000B3A8
0x18000b118  mov     r15d, r13d
0x18000b11b  mov     r14, [rsp+17E0h+pullResult]
0x18000b120  mov     r8d, r15d; dwIndex
0x18000b123  mov     rdx, r14; hKey
0x18000b126  lea     rcx, [rbp+16E0h+var_1720]; struct _UFH_SHORTCUT_INFO *
0x18000b12a  call    ?UfhRecentDataEnumShortcut@@YAKPEAU_UFH_SHORTCUT_INFO@@PEAUHKEY__@@K@Z; UfhRecentDataEnumShortcut(_UFH_SHORTCUT_INFO *,HKEY__ *,ulong)
0x18000b12f  cmp     eax, 103h
0x18000b134  jz      loc_18000B439
0x18000b13a  test    eax, eax
0x18000b13c  jnz     loc_18000B256
0x18000b142  mov     [rsp+17E0h+var_17B8], r13d; int
0x18000b147  mov     rax, [rsp+17E0h+hObject]
0x18000b14c  mov     [rsp+17E0h+phkResult], rax; void *
0x18000b151  lea     r9, [rbp+16E0h+var_1310]; unsigned __int16 *
0x18000b158  lea     r8, [rbp+16E0h+var_1518]; unsigned __int16 *
0x18000b15f  lea     rcx, [rbp+16E0h+String1]; unsigned __int16 *
0x18000b166  call    ?UfhGetCleansedString@@YAKPEAGK00PEAXH@Z; UfhGetCleansedString(ushort *,ulong,ushort *,ushort *,void *,int)
0x18000b16b  test    eax, eax
0x18000b16d  jnz     short loc_18000B1E0
0x18000b16f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b173  mov     rdi, r13
0x18000b176  cmp     rdi, qword ptr [rbp+16E0h+var_1748]
0x18000b17a  jnb     short loc_18000B1B9
0x18000b17c  mov     [rsp+17E0h+pullResult], r13
0x18000b181  mov     rax, rdi
0x18000b184  mul     [rbp+16E0h+HeapHandle+8]
0x18000b188  test    rdx, rdx
0x18000b18b  jnz     short loc_18000B19A
0x18000b18d  mov     rcx, [rbp+16E0h+P]
0x18000b191  lea     rdx, [rcx+rax]
0x18000b195  cmp     rdx, rcx
0x18000b198  jnb     short loc_18000B19D
0x18000b19a  mov     rdx, r13
0x18000b19d  mov     rdx, [rdx]; String2
0x18000b1a0  lea     rcx, [rbp+16E0h+String1]; String1
0x18000b1a7  call    cs:__imp__wcsicmp
0x18000b1ad  test    eax, eax
0x18000b1af  jz      short loc_18000B1B6
0x18000b1b1  inc     rdi
0x18000b1b4  jmp     short loc_18000B176
0x18000b1b6  mov     rsi, rdi
0x18000b1b9  cmp     esi, 0FFFFFFFFh
0x18000b1bc  jnz     loc_18000B3D2
0x18000b1c2  mov     esi, 1
0x18000b1c7  add     r15d, esi
  ... truncated ...
```
