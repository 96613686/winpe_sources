# CTiDevice::GetSWPdoNameDevObj(ushort *,tagPROPVARIANT *)

- ea: `0x1800acc1c`
- end: `0x1800ace84`
- name: `?GetSWPdoNameDevObj@CTiDevice@@KAJPEAGPEAUtagPROPVARIANT@@@Z`
- size: `616`
- prototype: `static int(unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ac9a4`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180033da0`
- `0x18005a2f8`
- `0x1800acc1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acc7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acd24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acc7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acd24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acdc2`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800ace59`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800ace59`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1800acd1a`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1800acd1a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800acc70`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800acc70`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800acdb8`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800acdb8`

## string_xrefs

- `0x1800accc8`: `DevObjCreateDeviceInfoList failed`
- `0x1800acd72`: `DevObjOpenDeviceInfo failed`

## pseudocode

```c
__int64 __fastcall CTiDevice::GetSWPdoNameDevObj(unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  __int64 DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int inited; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v8; // eax
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  signed int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-290h]
  int v15; // [rsp+40h] [rbp-278h] BYREF
  _OWORD v16[3]; // [rsp+48h] [rbp-270h] BYREF
  unsigned __int16 Source[264]; // [rsp+80h] [rbp-238h] BYREF

  v15 = 0;
  memset(v16, 0, sizeof(v16));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    inited = LastError;
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList failed",
          inited);
      }
      return (unsigned int)inited;
    }
  }
  LODWORD(v16[0]) = 48;
  if ( !(unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v16) )
  {
    v8 = GetLastError();
    inited = v8;
    if ( v8 > 0 )
      inited = (unsigned __int16)v8 | 0x80070000;
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 20;
        v11 = "DevObjOpenDeviceInfo failed";
LABEL_28:
        LODWORD(v14) = inited;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          (unsigned int)WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids,
          v9,
          (__int64)v11,
          v14);
        goto LABEL_29;
      }
      goto LABEL_29;
    }
  }
  if ( (unsigned int)DevObjGetDeviceProperty(DeviceInfoList, v16, &DEVPKEY_Device_PDOName, &v15, Source, 520, 0, 0) )
  {
    if ( v15 != 18 )
    {
      inited = -2147024883;
      goto LABEL_24;
    }
    inited = InitPropVariantFromString(Source, a2);
  }
  else
  {
    v12 = GetLastError();
    inited = v12;
    if ( v12 > 0 )
      inited = (unsigned __int16)v12 | 0x80070000;
  }
  if ( inited >= 0 )
    goto LABEL_29;
LABEL_24:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 21;
    v11 = "failed to get pdo name";
    goto LABEL_28;
  }
LABEL_29:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800acc1c  mov     [rsp+arg_10], rbx
0x1800acc21  push    rbp
0x1800acc22  push    rsi
0x1800acc23  push    rdi
0x1800acc24  sub     rsp, 2A0h
0x1800acc2b  mov     rax, cs:__security_cookie
0x1800acc32  xor     rax, rsp
0x1800acc35  mov     [rsp+2B8h+var_28], rax
0x1800acc3d  xorps   xmm0, xmm0
0x1800acc40  mov     [rsp+2B8h+var_278], 0
0x1800acc48  mov     rbp, rdx
0x1800acc4b  mov     [rsp+2B8h+var_298], 0
0x1800acc54  mov     rsi, rcx
0x1800acc57  xor     edx, edx
0x1800acc59  xor     ecx, ecx
0x1800acc5b  xor     r9d, r9d
0x1800acc5e  xor     r8d, r8d
0x1800acc61  movups  [rsp+2B8h+var_270], xmm0
0x1800acc66  movups  [rsp+2B8h+var_260], xmm0
0x1800acc6b  movups  [rsp+2B8h+var_250], xmm0
0x1800acc70  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800acc76  mov     rdi, rax
0x1800acc79  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800acc7d  jnz     short loc_1800ACCFC
0x1800acc7f  call    cs:__imp_GetLastError
0x1800acc85  mov     ebx, eax
0x1800acc87  test    eax, eax
0x1800acc89  jle     short loc_1800ACC94
0x1800acc8b  movzx   ebx, ax
0x1800acc8e  or      ebx, 80070000h
0x1800acc94  test    ebx, ebx
0x1800acc96  jns     short loc_1800ACCFC
0x1800acc98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acc9f  lea     rax, WPP_GLOBAL_Control
0x1800acca6  cmp     rcx, rax
0x1800acca9  jz      loc_1800ACE5F
0x1800accaf  test    byte ptr [rcx+1Ch], 8
0x1800accb3  jz      loc_1800ACE5F
0x1800accb9  cmp     byte ptr [rcx+19h], 2
0x1800accbd  jb      loc_1800ACE5F
0x1800accc3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800accc8  lea     rcx, aDevobjcreatede_0; "DevObjCreateDeviceInfoList failed"
0x1800acccf  mov     dword ptr [rsp+2B8h+var_290], ebx
0x1800accd3  mov     [rsp+2B8h+var_298], rcx
0x1800accd8  lea     r8, WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids
0x1800accdf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acce6  mov     edx, 13h
0x1800acceb  mov     r9d, eax
0x1800accee  mov     rcx, [rcx+10h]
0x1800accf2  call    WPP_SF_DsD
0x1800accf7  jmp     loc_1800ACE5F
0x1800accfc  lea     rax, [rsp+2B8h+var_270]
0x1800acd01  mov     dword ptr [rsp+2B8h+var_270], 30h ; '0'
0x1800acd09  xor     r9d, r9d
0x1800acd0c  mov     [rsp+2B8h+var_298], rax
0x1800acd11  xor     r8d, r8d
0x1800acd14  mov     rdx, rsi
0x1800acd17  mov     rcx, rdi
0x1800acd1a  call    cs:__imp_DevObjOpenDeviceInfo
0x1800acd20  test    eax, eax
0x1800acd22  jnz     short loc_1800ACD7E
0x1800acd24  call    cs:__imp_GetLastError
0x1800acd2a  mov     ebx, eax
0x1800acd2c  test    eax, eax
0x1800acd2e  jle     short loc_1800ACD39
0x1800acd30  movzx   ebx, ax
0x1800acd33  or      ebx, 80070000h
0x1800acd39  test    ebx, ebx
0x1800acd3b  jns     short loc_1800ACD7E
0x1800acd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acd44  lea     rax, WPP_GLOBAL_Control
0x1800acd4b  cmp     rcx, rax
0x1800acd4e  jz      loc_1800ACE50
0x1800acd54  test    byte ptr [rcx+1Ch], 8
0x1800acd58  jz      loc_1800ACE50
0x1800acd5e  cmp     byte ptr [rcx+19h], 2
0x1800acd62  jb      loc_1800ACE50
0x1800acd68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800acd6d  mov     edx, 14h
0x1800acd72  lea     rcx, aDevobjopendevi_1; "DevObjOpenDeviceInfo failed"
0x1800acd79  jmp     loc_1800ACE2D
0x1800acd7e  mov     [rsp+2B8h+var_280], 0
0x1800acd86  lea     rax, [rsp+2B8h+Source]
0x1800acd8e  mov     [rsp+2B8h+var_288], 0
0x1800acd97  lea     r9, [rsp+2B8h+var_278]
0x1800acd9c  mov     dword ptr [rsp+2B8h+var_290], 208h
0x1800acda4  lea     r8, DEVPKEY_Device_PDOName
0x1800acdab  lea     rdx, [rsp+2B8h+var_270]
0x1800acdb0  mov     [rsp+2B8h+var_298], rax
0x1800acdb5  mov     rcx, rdi
0x1800acdb8  call    cs:__imp_DevObjGetDeviceProperty
0x1800acdbe  test    eax, eax
0x1800acdc0  jnz     short loc_1800ACDD9
0x1800acdc2  call    cs:__imp_GetLastError
0x1800acdc8  mov     ebx, eax
0x1800acdca  test    eax, eax
0x1800acdcc  jle     short loc_1800ACDF9
0x1800acdce  movzx   ebx, ax
0x1800acdd1  or      ebx, 80070000h
0x1800acdd7  jmp     short loc_1800ACDF9
0x1800acdd9  cmp     [rsp+2B8h+var_278], 12h
0x1800acdde  jz      short loc_1800ACDE7
0x1800acde0  mov     ebx, 8007000Dh
0x1800acde5  jmp     short loc_1800ACDFD
0x1800acde7  mov     rdx, rbp; struct tagPROPVARIANT *
0x1800acdea  lea     rcx, [rsp+2B8h+Source]; Source
0x1800acdf2  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x1800acdf7  mov     ebx, eax
0x1800acdf9  test    ebx, ebx
0x1800acdfb  jns     short loc_1800ACE50
0x1800acdfd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace04  lea     rax, WPP_GLOBAL_Control
0x1800ace0b  cmp     rcx, rax
0x1800ace0e  jz      short loc_1800ACE50
0x1800ace10  test    byte ptr [rcx+1Ch], 8
0x1800ace14  jz      short loc_1800ACE50
0x1800ace16  cmp     byte ptr [rcx+19h], 2
0x1800ace1a  jb      short loc_1800ACE50
0x1800ace1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ace21  mov     edx, 15h
0x1800ace26  lea     rcx, aFailedToGetPdo; "failed to get pdo name"
0x1800ace2d  mov     dword ptr [rsp+2B8h+var_290], ebx
0x1800ace31  lea     r8, WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids
0x1800ace38  mov     [rsp+2B8h+var_298], rcx
0x1800ace3d  mov     r9d, eax
0x1800ace40  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace47  mov     rcx, [rcx+10h]
0x1800ace4b  call    WPP_SF_DsD
0x1800ace50  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ace54  jz      short loc_1800ACE5F
0x1800ace56  mov     rcx, rdi
0x1800ace59  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800ace5f  mov     eax, ebx
0x1800ace61  mov     rcx, [rsp+2B8h+var_28]
0x1800ace69  xor     rcx, rsp; StackCookie
0x1800ace6c  call    __security_check_cookie
0x1800ace71  mov     rbx, [rsp+2B8h+arg_10]
0x1800ace79  add     rsp, 2A0h
0x1800ace80  pop     rdi
0x1800ace81  pop     rsi
0x1800ace82  pop     rbp
0x1800ace83  retn
```
