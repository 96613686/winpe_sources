# MountHiddenSessionVolumes(DRIVE_TARGET *)

- ea: `0x14000b77c`
- end: `0x14000bb70`
- name: `?MountHiddenSessionVolumes@@YAJPEAUDRIVE_TARGET@@@Z`
- size: `1012`
- prototype: `__int64 __fastcall(struct DRIVE_TARGET *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000bfa4`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x14000abe4`
- `0x14000b204`
- `0x14000b77c`
- `0x14000c778`
- `0x14000cae0`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b7e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ba58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b7e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ba58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bac7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14000b7db`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14000b7db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000b7cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000b7cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bb4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bb4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b8e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bb34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b8e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bb34`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000b935`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000b9a0`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000b935`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000b9a0`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14000b908`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14000b908`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14000bb3d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14000bb3d`
- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x14000b868`
- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x14000b868`

## pseudocode

```c
__int64 __fastcall MountHiddenSessionVolumes(struct DRIVE_TARGET *a1)
{
  DWORD CurrentProcessId; // eax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v4; // r8
  __int64 v5; // rdx
  void *ClassDeviceInfoList; // r15
  _DWORD *v7; // rsi
  unsigned int i; // r14d
  signed int v9; // eax
  _DWORD *v10; // rax
  struct DRIVE_TARGET *v11; // rcx
  int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  signed int v16; // eax
  unsigned int v17; // eax
  signed int v18; // eax
  __int64 v20; // [rsp+28h] [rbp-51h]
  SIZE_T cb; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  __int128 v23; // [rsp+40h] [rbp-39h] BYREF
  __int128 v24; // [rsp+50h] [rbp-29h]
  __int128 v25; // [rsp+60h] [rbp-19h] BYREF
  __int128 v26; // [rsp+70h] [rbp-9h]
  __int128 v27; // [rsp+80h] [rbp+7h]

  cb = 0;
  hKey = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, (DWORD *)&cb + 1) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 22;
LABEL_6:
      WPP_SF_DL(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v4, CurrentThreadActivityIdPrefix, LastError);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  GetDriveLetterCacheKey(HIDWORD(cb), &hKey);
  ClassDeviceInfoList = (void *)DevObjCreateClassDeviceInfoList(&GUID_DEVINTERFACE_HIDDEN_VOLUME, 0, 16);
  if ( ClassDeviceInfoList == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 23;
      goto LABEL_6;
    }
LABEL_7:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_53;
  }
  v7 = 0;
  for ( i = 0; ; ++i )
  {
    LODWORD(cb) = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    if ( v7 )
      CoTaskMemFree(v7);
    LODWORD(v23) = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(ClassDeviceInfoList, 0, &GUID_DEVINTERFACE_HIDDEN_VOLUME, i, &v23) )
      break;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(ClassDeviceInfoList, &v23, 0, 0, &cb, 0) )
    {
      v9 = GetLastError();
      LastError = v9;
      if ( v9 != 122 )
      {
        if ( v9 > 0 )
          LastError = (unsigned __int16)v9 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 25;
LABEL_48:
          WPP_SF_DdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            &WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
            v14,
            i,
            LastError);
          goto LABEL_52;
        }
        goto LABEL_52;
      }
    }
    v10 = CoTaskMemAlloc((unsigned int)cb);
    v7 = v10;
    if ( !v10 )
    {
      LastError = -2147024882;
      goto LABEL_52;
    }
    memset_0(v10, 0, (unsigned int)cb);
    *v7 = 8;
    LODWORD(v25) = 48;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(ClassDeviceInfoList, &v23, v7, (unsigned int)cb, 0, &v25) )
    {
      v16 = GetLastError();
      LastError = v16;
      if ( v16 > 0 )
        LastError = (unsigned __int16)v16 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
          v17,
          i,
          LastError);
      }
      CoTaskMemFree(v7);
      goto LABEL_52;
    }
    v12 = CheckDeviceInterface(v11, ClassDeviceInfoList, hKey, (struct _DO_DEVINFO_DATA *)&v25);
    if ( v12 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v20) = v12;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
        v13,
        (__int64)"CheckDevice failed",
        v20);
    }
  }
  v18 = GetLastError();
  LastError = v18;
  if ( v18 == 259 )
  {
    LastError = 0;
    goto LABEL_52;
  }
  if ( v18 > 0 )
    LastError = (unsigned __int16)v18 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 24;
    goto LABEL_48;
  }
LABEL_52:
  DevObjDestroyDeviceInfoList(ClassDeviceInfoList);
LABEL_53:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000b77c  push    rbp
0x14000b77e  push    rbx
0x14000b77f  push    rsi
0x14000b780  push    rdi
0x14000b781  push    r14
0x14000b783  push    r15
0x14000b785  lea     rbp, [rsp-2Fh]
0x14000b78a  sub     rsp, 0A8h
0x14000b791  mov     rax, cs:__security_cookie
0x14000b798  xor     rax, rsp
0x14000b79b  mov     [rbp+57h+var_40], rax
0x14000b79f  xorps   xmm1, xmm1
0x14000b7a2  mov     dword ptr [rbp+57h+cb], 0
0x14000b7a9  xorps   xmm0, xmm0
0x14000b7ac  mov     [rbp+57h+hKey], 0
0x14000b7b4  movups  [rbp+57h+var_90], xmm0
0x14000b7b8  mov     dword ptr [rbp+57h+cb+4], 0
0x14000b7bf  movups  [rbp+57h+var_80], xmm0
0x14000b7c3  movups  [rbp+57h+var_70], xmm1
0x14000b7c7  movups  [rbp+57h+var_60], xmm1
0x14000b7cb  movups  [rbp+57h+var_50], xmm1
0x14000b7cf  call    cs:__imp_GetCurrentProcessId
0x14000b7d5  mov     ecx, eax; dwProcessId
0x14000b7d7  lea     rdx, [rbp+57h+cb+4]; pSessionId
0x14000b7db  call    cs:__imp_ProcessIdToSessionId
0x14000b7e1  test    eax, eax
0x14000b7e3  jnz     short loc_14000B843
0x14000b7e5  call    cs:__imp_GetLastError
0x14000b7eb  mov     ebx, eax
0x14000b7ed  mov     rax, cs:WPP_GLOBAL_Control
0x14000b7f4  lea     rdi, WPP_GLOBAL_Control
0x14000b7fb  cmp     rax, rdi
0x14000b7fe  jz      short loc_14000B82D
0x14000b800  test    byte ptr [rax+1Ch], 1
0x14000b804  jz      short loc_14000B82D
0x14000b806  cmp     byte ptr [rax+19h], 2
0x14000b80a  jb      short loc_14000B82D
0x14000b80c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000b811  mov     edx, 16h
0x14000b816  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b81d  mov     r9d, eax
0x14000b820  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x14000b824  mov     rcx, [rcx+10h]
0x14000b828  call    WPP_SF_DL
0x14000b82d  test    ebx, ebx
0x14000b82f  jle     loc_14000BB43
0x14000b835  movzx   ebx, bx
0x14000b838  or      ebx, 80070000h
0x14000b83e  jmp     loc_14000BB43
0x14000b843  mov     ecx, dword ptr [rbp+57h+cb+4]; unsigned int
0x14000b846  lea     rdx, [rbp+57h+hKey]; HKEY *
0x14000b84a  call    ?GetDriveLetterCacheKey@@YAJKPEAPEAUHKEY__@@@Z; GetDriveLetterCacheKey(ulong,HKEY__ * *)
0x14000b84f  xor     r9d, r9d
0x14000b852  mov     [rsp+0D0h+var_B0], 0
0x14000b85b  xor     edx, edx
0x14000b85d  lea     rcx, GUID_DEVINTERFACE_HIDDEN_VOLUME
0x14000b864  lea     r8d, [r9+10h]
0x14000b868  call    cs:__imp_DevObjCreateClassDeviceInfoList
0x14000b86e  mov     r15, rax
0x14000b871  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b875  jnz     short loc_14000B8AC
0x14000b877  call    cs:__imp_GetLastError
0x14000b87d  mov     ebx, eax
0x14000b87f  mov     rax, cs:WPP_GLOBAL_Control
0x14000b886  lea     rdi, WPP_GLOBAL_Control
0x14000b88d  cmp     rax, rdi
0x14000b890  jz      short loc_14000B82D
0x14000b892  test    byte ptr [rax+1Ch], 1
0x14000b896  jz      short loc_14000B82D
0x14000b898  cmp     byte ptr [rax+19h], 2
0x14000b89c  jb      short loc_14000B82D
0x14000b89e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000b8a3  lea     edx, [r15+18h]
0x14000b8a7  jmp     loc_14000B816
0x14000b8ac  xor     esi, esi
0x14000b8ae  lea     rdi, WPP_GLOBAL_Control
0x14000b8b5  xor     r14d, r14d
0x14000b8b8  mov     dword ptr [rbp+57h+cb], 0
0x14000b8bf  xorps   xmm1, xmm1
0x14000b8c2  xorps   xmm0, xmm0
0x14000b8c5  movups  [rbp+57h+var_90], xmm0
0x14000b8c9  movups  [rbp+57h+var_80], xmm0
0x14000b8cd  movups  [rbp+57h+var_70], xmm1
0x14000b8d1  movups  [rbp+57h+var_60], xmm1
0x14000b8d5  movups  [rbp+57h+var_50], xmm1
0x14000b8d9  test    rsi, rsi
0x14000b8dc  jz      short loc_14000B8E9
0x14000b8de  mov     rcx, rsi; pv
0x14000b8e1  call    cs:__imp_CoTaskMemFree
0x14000b8e7  xor     esi, esi
0x14000b8e9  lea     rax, [rbp+57h+var_90]
0x14000b8ed  mov     dword ptr [rbp+57h+var_90], 20h ; ' '
0x14000b8f4  mov     r9d, r14d
0x14000b8f7  mov     [rsp+0D0h+var_B0], rax
0x14000b8fc  lea     r8, GUID_DEVINTERFACE_HIDDEN_VOLUME
0x14000b903  xor     edx, edx
0x14000b905  mov     rcx, r15
0x14000b908  call    cs:__imp_DevObjEnumDeviceInterfaces
0x14000b90e  test    eax, eax
0x14000b910  jz      loc_14000BAC7
0x14000b916  lea     rax, [rbp+57h+cb]
0x14000b91a  mov     [rsp+0D0h+var_A8], 0
0x14000b923  xor     r9d, r9d
0x14000b926  mov     [rsp+0D0h+var_B0], rax
0x14000b92b  xor     r8d, r8d
0x14000b92e  lea     rdx, [rbp+57h+var_90]
0x14000b932  mov     rcx, r15
0x14000b935  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x14000b93b  test    eax, eax
0x14000b93d  jnz     short loc_14000B950
0x14000b93f  call    cs:__imp_GetLastError
0x14000b945  mov     ebx, eax
0x14000b947  cmp     eax, 7Ah ; 'z'
0x14000b94a  jnz     loc_14000BA18
0x14000b950  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x14000b953  call    cs:__imp_CoTaskMemAlloc
0x14000b959  mov     rsi, rax
0x14000b95c  test    rax, rax
0x14000b95f  jz      loc_14000BAC0
0x14000b965  mov     r8d, dword ptr [rbp+57h+cb]; Size
0x14000b969  xor     edx, edx; Val
0x14000b96b  mov     rcx, rax; void *
0x14000b96e  call    memset_0
0x14000b973  mov     dword ptr [rsi], 8
0x14000b979  lea     rax, [rbp+57h+var_70]
0x14000b97d  mov     r9d, dword ptr [rbp+57h+cb]
0x14000b981  lea     rdx, [rbp+57h+var_90]
0x14000b985  mov     [rsp+0D0h+var_A8], rax
0x14000b98a  mov     r8, rsi
0x14000b98d  mov     rcx, r15
0x14000b990  mov     [rsp+0D0h+var_B0], 0
0x14000b999  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x14000b9a0  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x14000b9a6  test    eax, eax
0x14000b9a8  jz      loc_14000BA58
0x14000b9ae  mov     r8, [rbp+57h+hKey]; HKEY
0x14000b9b2  lea     r9, [rbp+57h+var_70]; struct _DO_DEVINFO_DATA *
0x14000b9b6  mov     rdx, r15; void *
0x14000b9b9  call    ?CheckDeviceInterface@@YAJPEAUDRIVE_TARGET@@PEAXPEAUHKEY__@@PEAU_DO_DEVINFO_DATA@@@Z; CheckDeviceInterface(DRIVE_TARGET *,void *,HKEY__ *,_DO_DEVINFO_DATA *)
0x14000b9be  mov     ebx, eax
0x14000b9c0  test    eax, eax
0x14000b9c2  jns     short loc_14000BA10
0x14000b9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9cb  cmp     rcx, rdi
0x14000b9ce  jz      short loc_14000BA10
0x14000b9d0  test    byte ptr [rcx+1Ch], 8
0x14000b9d4  jz      short loc_14000BA10
0x14000b9d6  cmp     byte ptr [rcx+19h], 2
0x14000b9da  jb      short loc_14000BA10
0x14000b9dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000b9e1  lea     rcx, aCheckdeviceFai; "CheckDevice failed"
0x14000b9e8  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x14000b9ec  mov     [rsp+0D0h+var_B0], rcx
0x14000b9f1  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000b9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9ff  mov     edx, 1Bh
0x14000ba04  mov     r9d, eax
0x14000ba07  mov     rcx, [rcx+10h]
0x14000ba0b  call    WPP_SF_DsD
0x14000ba10  inc     r14d
0x14000ba13  jmp     loc_14000B8B8
0x14000ba18  test    eax, eax
0x14000ba1a  jle     short loc_14000BA25
0x14000ba1c  movzx   ebx, ax
0x14000ba1f  or      ebx, 80070000h
0x14000ba25  mov     rax, cs:WPP_GLOBAL_Control
0x14000ba2c  cmp     rax, rdi
0x14000ba2f  jz      loc_14000BB2C
0x14000ba35  test    byte ptr [rax+1Ch], 1
0x14000ba39  jz      loc_14000BB2C
0x14000ba3f  cmp     byte ptr [rax+19h], 2
0x14000ba43  jb      loc_14000BB2C
0x14000ba49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ba4e  mov     edx, 19h
0x14000ba53  jmp     loc_14000BB05
0x14000ba58  call    cs:__imp_GetLastError
0x14000ba5e  mov     ebx, eax
0x14000ba60  test    eax, eax
0x14000ba62  jle     short loc_14000BA6D
0x14000ba64  movzx   ebx, ax
0x14000ba67  or      ebx, 80070000h
0x14000ba6d  mov     rax, cs:WPP_GLOBAL_Control
0x14000ba74  cmp     rax, rdi
0x14000ba77  jz      loc_14000BB31
0x14000ba7d  test    byte ptr [rax+1Ch], 1
0x14000ba81  jz      loc_14000BB31
0x14000ba87  cmp     byte ptr [rax+19h], 2
0x14000ba8b  jb      loc_14000BB31
0x14000ba91  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ba96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ba9d  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000baa4  mov     edx, 1Ah
0x14000baa9  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x14000baad  mov     r9d, eax
0x14000bab0  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x14000bab5  mov     rcx, [rcx+10h]
0x14000bab9  call    WPP_SF_DdD
0x14000babe  jmp     short loc_14000BB31
0x14000bac0  mov     ebx, 8007000Eh
0x14000bac5  jmp     short loc_14000BB3A
0x14000bac7  call    cs:__imp_GetLastError
0x14000bacd  mov     ebx, eax
0x14000bacf  cmp     eax, 103h
0x14000bad4  jz      short loc_14000BB2A
0x14000bad6  test    eax, eax
0x14000bad8  jle     short loc_14000BAE3
0x14000bada  movzx   ebx, ax
0x14000badd  or      ebx, 80070000h
0x14000bae3  mov     rax, cs:WPP_GLOBAL_Control
0x14000baea  cmp     rax, rdi
0x14000baed  jz      short loc_14000BB2C
0x14000baef  test    byte ptr [rax+1Ch], 1
0x14000baf3  jz      short loc_14000BB2C
0x14000baf5  cmp     byte ptr [rax+19h], 2
0x14000baf9  jb      short loc_14000BB2C
0x14000bafb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bb00  mov     edx, 18h
0x14000bb05  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb0c  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000bb13  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x14000bb17  mov     r9d, eax
0x14000bb1a  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x14000bb1f  mov     rcx, [rcx+10h]
0x14000bb23  call    WPP_SF_DdD
0x14000bb28  jmp     short loc_14000BB2C
0x14000bb2a  xor     ebx, ebx
0x14000bb2c  test    rsi, rsi
0x14000bb2f  jz      short loc_14000BB3A
0x14000bb31  mov     rcx, rsi; pv
0x14000bb34  call    cs:__imp_CoTaskMemFree
0x14000bb3a  mov     rcx, r15
0x14000bb3d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14000bb43  mov     rcx, [rbp+57h+hKey]; hKey
0x14000bb47  test    rcx, rcx
0x14000bb4a  jz      short loc_14000BB52
0x14000bb4c  call    cs:__imp_RegCloseKey
0x14000bb52  mov     eax, ebx
0x14000bb54  mov     rcx, [rbp+57h+var_40]
0x14000bb58  xor     rcx, rsp; StackCookie
0x14000bb5b  call    __security_check_cookie
0x14000bb60  add     rsp, 0A8h
0x14000bb67  pop     r15
0x14000bb69  pop     r14
0x14000bb6b  pop     rdi
0x14000bb6c  pop     rsi
0x14000bb6d  pop     rbx
0x14000bb6e  pop     rbp
0x14000bb6f  retn
```
