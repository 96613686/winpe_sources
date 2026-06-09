# MountSingleVolume(DRIVE_TARGET *,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x14000bb78`
- end: `0x14000bf9c`
- name: `?MountSingleVolume@@YAJPEAUDRIVE_TARGET@@PEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(struct DRIVE_TARGET *, struct _DEV_BROADCAST_DEVICEINTERFACE_W *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c5b0`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x14000abe4`
- `0x14000b204`
- `0x14000bb78`
- `0x14000c778`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000be80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000be80`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14000bbdc`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14000bbdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000bbd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000bbd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bf70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bf70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000be22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000be22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bf52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bf52`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000bda7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000be76`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000bda7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x14000be76`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14000bf61`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14000bf61`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x14000bd05`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x14000bd05`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14000bc63`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14000bc63`

## string_xrefs

- `0x14000bcbc`: `DevObjCreateDeviceInfoList FAILED`
- `0x14000bd54`: `SetupDiOpenDeviceInterface FAILED`

## pseudocode

```c
__int64 __fastcall MountSingleVolume(struct DRIVE_TARGET *a1, struct _DEV_BROADCAST_DEVICEINTERFACE_W *a2)
{
  DWORD CurrentProcessId; // eax
  signed int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // r8
  void *DeviceInfoList; // rsi
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v10; // eax
  unsigned int v11; // eax
  signed int v12; // eax
  unsigned int v13; // eax
  _DWORD *v14; // rax
  _DWORD *v15; // r14
  struct DRIVE_TARGET *v16; // rcx
  signed int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v21; // [rsp+28h] [rbp-31h]
  SIZE_T cb; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v24[2]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v25[3]; // [rsp+60h] [rbp+7h] BYREF

  cb = 0;
  memset(v25, 0, sizeof(v25));
  hKey = 0;
  memset(v24, 0, sizeof(v24));
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, (DWORD *)&cb + 1) )
  {
    GetDriveLetterCacheKey(HIDWORD(cb), &hKey);
    DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    if ( DeviceInfoList != (void *)-1LL )
      goto LABEL_16;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList FAILED",
          v4);
      }
    }
    else
    {
LABEL_16:
      LODWORD(v24[0]) = 32;
      if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, a2->dbcc_name, 0, v24) )
        goto LABEL_54;
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_54:
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v24, 0, 0, &cb, 0)
          || (v12 = GetLastError(), v4 = v12, v12 == 122) )
        {
          v14 = CoTaskMemAlloc((unsigned int)cb);
          v15 = v14;
          if ( v14 )
          {
            memset_0(v14, 0, (unsigned int)cb);
            *v15 = 8;
            LODWORD(v25[0]) = 48;
            if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v24, v15, (unsigned int)cb, 0, v25) )
            {
              v4 = CheckDeviceInterface(v16, DeviceInfoList, hKey, (struct _DO_DEVINFO_DATA *)v25);
              if ( v4 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v19 = RdpWppGetCurrentThreadActivityIdPrefix();
                LODWORD(v21) = v4;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33,
                  (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
                  v19,
                  (__int64)"CheckDevice failed",
                  v21);
              }
            }
            else
            {
              v17 = GetLastError();
              v4 = v17;
              if ( v17 > 0 )
                v4 = (unsigned __int16)v17 | 0x80070000;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v18 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  &WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
                  v18,
                  v4);
              }
            }
            CoTaskMemFree(v15);
          }
          else
          {
            v4 = -2147024882;
          }
        }
        else
        {
          if ( v12 > 0 )
            v4 = (unsigned __int16)v12 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
              v13,
              v4);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
          v11,
          (__int64)"SetupDiOpenDeviceInterface FAILED",
          v4);
      }
      if ( DeviceInfoList != (void *)-1LL )
        DevObjDestroyDeviceInfoList(DeviceInfoList);
    }
  }
  else
  {
    v4 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DL(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v6, v5, v4);
    }
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000bb78  mov     [rsp-8+arg_0], rbx
0x14000bb7d  mov     [rsp-8+arg_10], rsi
0x14000bb82  push    rbp
0x14000bb83  push    rdi
0x14000bb84  push    r14
0x14000bb86  lea     rbp, [rsp-47h]
0x14000bb8b  sub     rsp, 0A0h
0x14000bb92  mov     rax, cs:__security_cookie
0x14000bb99  xor     rax, rsp
0x14000bb9c  mov     [rbp+57h+var_20], rax
0x14000bba0  xorps   xmm0, xmm0
0x14000bba3  mov     dword ptr [rbp+57h+cb], 0
0x14000bbaa  movups  [rbp+57h+var_50], xmm0
0x14000bbae  mov     r14, rdx
0x14000bbb1  mov     dword ptr [rbp+57h+cb+4], 0
0x14000bbb8  movups  [rbp+57h+var_40], xmm0
0x14000bbbc  mov     [rbp+57h+hKey], 0
0x14000bbc4  movups  [rbp+57h+var_30], xmm0
0x14000bbc8  movups  [rbp+57h+var_70], xmm0
0x14000bbcc  movups  [rbp+57h+var_60], xmm0
0x14000bbd0  call    cs:__imp_GetCurrentProcessId
0x14000bbd6  mov     ecx, eax; dwProcessId
0x14000bbd8  lea     rdx, [rbp+57h+cb+4]; pSessionId
0x14000bbdc  call    cs:__imp_ProcessIdToSessionId
0x14000bbe2  test    eax, eax
0x14000bbe4  jnz     short loc_14000BC44
0x14000bbe6  call    cs:__imp_GetLastError
0x14000bbec  mov     ebx, eax
0x14000bbee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbf5  lea     rax, WPP_GLOBAL_Control
0x14000bbfc  cmp     rcx, rax
0x14000bbff  jz      short loc_14000BC2E
0x14000bc01  test    byte ptr [rcx+1Ch], 1
0x14000bc05  jz      short loc_14000BC2E
0x14000bc07  cmp     byte ptr [rcx+19h], 2
0x14000bc0b  jb      short loc_14000BC2E
0x14000bc0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bc12  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc19  mov     edx, 1Ch
0x14000bc1e  mov     r9d, eax
0x14000bc21  mov     dword ptr [rsp+0B0h+var_90], ebx
0x14000bc25  mov     rcx, [rcx+10h]
0x14000bc29  call    WPP_SF_DL
0x14000bc2e  test    ebx, ebx
0x14000bc30  jle     loc_14000BF67
0x14000bc36  movzx   ebx, bx
0x14000bc39  or      ebx, 80070000h
0x14000bc3f  jmp     loc_14000BF67
0x14000bc44  mov     ecx, dword ptr [rbp+57h+cb+4]; unsigned int
0x14000bc47  lea     rdx, [rbp+57h+hKey]; HKEY *
0x14000bc4b  call    ?GetDriveLetterCacheKey@@YAJKPEAPEAUHKEY__@@@Z; GetDriveLetterCacheKey(ulong,HKEY__ * *)
0x14000bc50  xor     r9d, r9d
0x14000bc53  mov     [rsp+0B0h+var_90], 0
0x14000bc5c  xor     r8d, r8d
0x14000bc5f  xor     edx, edx
0x14000bc61  xor     ecx, ecx
0x14000bc63  call    cs:__imp_DevObjCreateDeviceInfoList
0x14000bc69  mov     rsi, rax
0x14000bc6c  mov     edi, 80070000h
0x14000bc71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bc75  jnz     short loc_14000BCF0
0x14000bc77  call    cs:__imp_GetLastError
0x14000bc7d  mov     ebx, eax
0x14000bc7f  test    eax, eax
0x14000bc81  jle     short loc_14000BC88
0x14000bc83  movzx   ebx, ax
0x14000bc86  or      ebx, edi
0x14000bc88  test    ebx, ebx
0x14000bc8a  jns     short loc_14000BCF0
0x14000bc8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc93  lea     rax, WPP_GLOBAL_Control
0x14000bc9a  cmp     rcx, rax
0x14000bc9d  jz      loc_14000BF67
0x14000bca3  test    byte ptr [rcx+1Ch], 8
0x14000bca7  jz      loc_14000BF67
0x14000bcad  cmp     byte ptr [rcx+19h], 2
0x14000bcb1  jb      loc_14000BF67
0x14000bcb7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bcbc  lea     rcx, aDevobjcreatede_0; "DevObjCreateDeviceInfoList FAILED"
0x14000bcc3  mov     dword ptr [rsp+0B0h+var_88], ebx
0x14000bcc7  mov     [rsp+0B0h+var_90], rcx
0x14000bccc  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000bcd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcda  mov     edx, 1Dh
0x14000bcdf  mov     r9d, eax
0x14000bce2  mov     rcx, [rcx+10h]
0x14000bce6  call    WPP_SF_DsD
0x14000bceb  jmp     loc_14000BF67
0x14000bcf0  lea     rdx, [r14+1Ch]
0x14000bcf4  mov     dword ptr [rbp+57h+var_70], 20h ; ' '
0x14000bcfb  lea     r9, [rbp+57h+var_70]
0x14000bcff  xor     r8d, r8d
0x14000bd02  mov     rcx, rsi
0x14000bd05  call    cs:__imp_DevObjOpenDeviceInterface
0x14000bd0b  test    eax, eax
0x14000bd0d  jnz     short loc_14000BD88
0x14000bd0f  call    cs:__imp_GetLastError
0x14000bd15  mov     ebx, eax
0x14000bd17  test    eax, eax
0x14000bd19  jle     short loc_14000BD20
0x14000bd1b  movzx   ebx, ax
0x14000bd1e  or      ebx, edi
0x14000bd20  test    ebx, ebx
0x14000bd22  jns     short loc_14000BD88
0x14000bd24  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd2b  lea     rax, WPP_GLOBAL_Control
0x14000bd32  cmp     rcx, rax
0x14000bd35  jz      loc_14000BF58
0x14000bd3b  test    byte ptr [rcx+1Ch], 8
0x14000bd3f  jz      loc_14000BF58
0x14000bd45  cmp     byte ptr [rcx+19h], 2
0x14000bd49  jb      loc_14000BF58
0x14000bd4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bd54  lea     rcx, aSetupdiopendev; "SetupDiOpenDeviceInterface FAILED"
0x14000bd5b  mov     dword ptr [rsp+0B0h+var_88], ebx
0x14000bd5f  mov     [rsp+0B0h+var_90], rcx
0x14000bd64  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000bd6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd72  mov     edx, 1Eh
0x14000bd77  mov     r9d, eax
0x14000bd7a  mov     rcx, [rcx+10h]
0x14000bd7e  call    WPP_SF_DsD
0x14000bd83  jmp     loc_14000BF58
0x14000bd88  lea     rax, [rbp+57h+cb]
0x14000bd8c  mov     [rsp+0B0h+var_88], 0
0x14000bd95  xor     r9d, r9d
0x14000bd98  mov     [rsp+0B0h+var_90], rax
0x14000bd9d  xor     r8d, r8d
0x14000bda0  lea     rdx, [rbp+57h+var_70]
0x14000bda4  mov     rcx, rsi
0x14000bda7  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x14000bdad  test    eax, eax
0x14000bdaf  jnz     short loc_14000BE1F
0x14000bdb1  call    cs:__imp_GetLastError
0x14000bdb7  mov     ebx, eax
0x14000bdb9  cmp     eax, 7Ah ; 'z'
0x14000bdbc  jz      short loc_14000BE1F
0x14000bdbe  test    eax, eax
0x14000bdc0  jle     short loc_14000BDC7
0x14000bdc2  movzx   ebx, ax
0x14000bdc5  or      ebx, edi
0x14000bdc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdce  lea     rax, WPP_GLOBAL_Control
0x14000bdd5  cmp     rcx, rax
0x14000bdd8  jz      loc_14000BF58
0x14000bdde  test    byte ptr [rcx+1Ch], 1
0x14000bde2  jz      loc_14000BF58
0x14000bde8  cmp     byte ptr [rcx+19h], 2
0x14000bdec  jb      loc_14000BF58
0x14000bdf2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bdf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdfe  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000be05  mov     edx, 1Fh
0x14000be0a  mov     dword ptr [rsp+0B0h+var_90], ebx
0x14000be0e  mov     r9d, eax
0x14000be11  mov     rcx, [rcx+10h]
0x14000be15  call    WPP_SF_Dd
0x14000be1a  jmp     loc_14000BF58
0x14000be1f  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x14000be22  call    cs:__imp_CoTaskMemAlloc
0x14000be28  mov     r14, rax
0x14000be2b  test    rax, rax
0x14000be2e  jnz     short loc_14000BE3A
0x14000be30  mov     ebx, 8007000Eh
0x14000be35  jmp     loc_14000BF58
0x14000be3a  mov     r8d, dword ptr [rbp+57h+cb]; Size
0x14000be3e  xor     edx, edx; Val
0x14000be40  mov     rcx, r14; void *
0x14000be43  call    memset_0
0x14000be48  mov     dword ptr [r14], 8
0x14000be4f  lea     rax, [rbp+57h+var_50]
0x14000be53  mov     r9d, dword ptr [rbp+57h+cb]
0x14000be57  lea     rdx, [rbp+57h+var_70]
0x14000be5b  mov     [rsp+0B0h+var_88], rax
0x14000be60  mov     r8, r14
0x14000be63  mov     rcx, rsi
0x14000be66  mov     [rsp+0B0h+var_90], 0
0x14000be6f  mov     dword ptr [rbp+57h+var_50], 30h ; '0'
0x14000be76  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x14000be7c  test    eax, eax
0x14000be7e  jnz     short loc_14000BEE6
0x14000be80  call    cs:__imp_GetLastError
0x14000be86  mov     ebx, eax
0x14000be88  test    eax, eax
0x14000be8a  jle     short loc_14000BE91
0x14000be8c  movzx   ebx, ax
0x14000be8f  or      ebx, edi
0x14000be91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be98  lea     rax, WPP_GLOBAL_Control
0x14000be9f  cmp     rcx, rax
0x14000bea2  jz      loc_14000BF4F
0x14000bea8  test    byte ptr [rcx+1Ch], 1
0x14000beac  jz      loc_14000BF4F
0x14000beb2  cmp     byte ptr [rcx+19h], 2
0x14000beb6  jb      loc_14000BF4F
0x14000bebc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bec1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bec8  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000becf  mov     edx, 20h ; ' '
0x14000bed4  mov     dword ptr [rsp+0B0h+var_90], ebx
0x14000bed8  mov     r9d, eax
0x14000bedb  mov     rcx, [rcx+10h]
0x14000bedf  call    WPP_SF_Dd
0x14000bee4  jmp     short loc_14000BF4F
0x14000bee6  mov     r8, [rbp+57h+hKey]; HKEY
0x14000beea  lea     r9, [rbp+57h+var_50]; struct _DO_DEVINFO_DATA *
0x14000beee  mov     rdx, rsi; void *
0x14000bef1  call    ?CheckDeviceInterface@@YAJPEAUDRIVE_TARGET@@PEAXPEAUHKEY__@@PEAU_DO_DEVINFO_DATA@@@Z; CheckDeviceInterface(DRIVE_TARGET *,void *,HKEY__ *,_DO_DEVINFO_DATA *)
0x14000bef6  mov     ebx, eax
0x14000bef8  test    eax, eax
0x14000befa  jns     short loc_14000BF4F
0x14000befc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf03  lea     rax, WPP_GLOBAL_Control
0x14000bf0a  cmp     rcx, rax
0x14000bf0d  jz      short loc_14000BF4F
0x14000bf0f  test    byte ptr [rcx+1Ch], 8
0x14000bf13  jz      short loc_14000BF4F
0x14000bf15  cmp     byte ptr [rcx+19h], 2
0x14000bf19  jb      short loc_14000BF4F
0x14000bf1b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000bf20  lea     rcx, aCheckdeviceFai; "CheckDevice failed"
0x14000bf27  mov     dword ptr [rsp+0B0h+var_88], ebx
0x14000bf2b  mov     [rsp+0B0h+var_90], rcx
0x14000bf30  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000bf37  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf3e  mov     edx, 21h ; '!'
0x14000bf43  mov     r9d, eax
0x14000bf46  mov     rcx, [rcx+10h]
0x14000bf4a  call    WPP_SF_DsD
0x14000bf4f  mov     rcx, r14; pv
0x14000bf52  call    cs:__imp_CoTaskMemFree
0x14000bf58  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000bf5c  jz      short loc_14000BF67
0x14000bf5e  mov     rcx, rsi
0x14000bf61  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14000bf67  mov     rcx, [rbp+57h+hKey]; hKey
0x14000bf6b  test    rcx, rcx
0x14000bf6e  jz      short loc_14000BF76
0x14000bf70  call    cs:__imp_RegCloseKey
0x14000bf76  mov     eax, ebx
0x14000bf78  mov     rcx, [rbp+57h+var_20]
0x14000bf7c  xor     rcx, rsp; StackCookie
0x14000bf7f  call    __security_check_cookie
0x14000bf84  lea     r11, [rsp+0B0h+var_10]
0x14000bf8c  mov     rbx, [r11+20h]
0x14000bf90  mov     rsi, [r11+30h]
0x14000bf94  mov     rsp, r11
0x14000bf97  pop     r14
0x14000bf99  pop     rdi
0x14000bf9a  pop     rbp
0x14000bf9b  retn
```
