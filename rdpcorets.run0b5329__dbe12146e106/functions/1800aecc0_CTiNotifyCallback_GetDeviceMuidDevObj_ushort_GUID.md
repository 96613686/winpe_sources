# CTiNotifyCallback::GetDeviceMuidDevObj(ushort *,_GUID *)

- ea: `0x1800aecc0`
- end: `0x1800aefb1`
- name: `?GetDeviceMuidDevObj@CTiNotifyCallback@@KAJPEAGPEAU_GUID@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800265a0`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x1800aecc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aedaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aedaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeecc`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800aef7b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800aef7b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800aed20`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800aed20`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800aeec2`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800aeec2`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800aee39`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800aee39`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1800aeda5`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1800aeda5`

## pseudocode

```c
__int64 __fastcall CTiNotifyCallback::GetDeviceMuidDevObj(unsigned __int16 *a1, struct _GUID *a2)
{
  __int64 DeviceInfoList; // rax
  __int64 v5; // rdi
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v12; // [rsp+28h] [rbp-31h]
  int v13; // [rsp+40h] [rbp-19h] BYREF
  int v14; // [rsp+44h] [rbp-15h] BYREF
  _OWORD v15[2]; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v16[3]; // [rsp+68h] [rbp+Fh] BYREF

  memset(v16, 0, sizeof(v16));
  memset(v15, 0, sizeof(v15));
  LODWORD(v16[0]) = 48;
  LODWORD(v15[0]) = 32;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v5 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_a94a9deae15032e68227e68649adf791_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_40;
  }
  if ( !(unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, a1, 0, v15) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 15;
LABEL_16:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_a94a9deae15032e68227e68649adf791_Traceguids, v8, LastError);
LABEL_17:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_39;
  }
  if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v5, v15, 0, 0, 0, v16) && GetLastError() != 122 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 16;
    goto LABEL_16;
  }
  v13 = 0;
  v14 = 0;
  if ( !(unsigned int)DevObjGetDeviceProperty(v5, v16, &PKEY_TIBUS_MUID, &v13, a2, 16, &v14, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 17;
    goto LABEL_16;
  }
  if ( v13 != 13 || (LastError = 0, v14 != 16) )
  {
    LastError = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v12) = -2147418113;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_a94a9deae15032e68227e68649adf791_Traceguids,
        v10,
        (__int64)"invalid MUID returned!",
        v12);
    }
  }
LABEL_39:
  DevObjDestroyDeviceInfoList(v5);
  if ( LastError < 0 )
LABEL_40:
    *a2 = GUID_NULL;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800aecc0  mov     [rsp-8+arg_10], rbx
0x1800aecc5  push    rbp
0x1800aecc6  push    rsi
0x1800aecc7  push    rdi
0x1800aecc8  lea     rbp, [rsp-47h]
0x1800aeccd  sub     rsp, 0A0h
0x1800aecd4  mov     rax, cs:__security_cookie
0x1800aecdb  xor     rax, rsp
0x1800aecde  mov     [rbp+57h+var_18], rax
0x1800aece2  xorps   xmm0, xmm0
0x1800aece5  mov     [rsp+0B0h+var_90], 0
0x1800aecee  mov     rsi, rdx
0x1800aecf1  mov     rbx, rcx
0x1800aecf4  movups  [rbp+57h+var_48], xmm0
0x1800aecf8  xor     r9d, r9d
0x1800aecfb  xor     r8d, r8d
0x1800aecfe  movups  [rbp+57h+var_68], xmm0
0x1800aed02  xor     edx, edx
0x1800aed04  mov     dword ptr [rbp+57h+var_48], 30h ; '0'
0x1800aed0b  xor     ecx, ecx
0x1800aed0d  mov     dword ptr [rbp+57h+var_68], 20h ; ' '
0x1800aed14  movups  [rbp+57h+var_38], xmm0
0x1800aed18  movups  [rbp+57h+var_28], xmm0
0x1800aed1c  movups  [rbp+57h+var_58], xmm0
0x1800aed20  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800aed26  mov     rdi, rax
0x1800aed29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aed2d  jnz     short loc_1800AED98
0x1800aed2f  call    cs:__imp_GetLastError
0x1800aed35  mov     ebx, eax
0x1800aed37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aed3e  lea     rax, WPP_GLOBAL_Control
0x1800aed45  cmp     rcx, rax
0x1800aed48  jz      short loc_1800AED7C
0x1800aed4a  test    byte ptr [rcx+1Ch], 8
0x1800aed4e  jz      short loc_1800AED7C
0x1800aed50  cmp     byte ptr [rcx+19h], 2
0x1800aed54  jb      short loc_1800AED7C
0x1800aed56  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aed5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aed62  lea     edx, [rdi+0Fh]
0x1800aed65  mov     r9d, eax
0x1800aed68  mov     dword ptr [rsp+0B0h+var_90], ebx
0x1800aed6c  lea     r8, WPP_a94a9deae15032e68227e68649adf791_Traceguids
0x1800aed73  mov     rcx, [rcx+10h]
0x1800aed77  call    WPP_SF_Dd
0x1800aed7c  test    ebx, ebx
0x1800aed7e  jle     short loc_1800AED89
0x1800aed80  movzx   ebx, bx
0x1800aed83  or      ebx, 80070000h
0x1800aed89  test    ebx, ebx
0x1800aed8b  mov     eax, 80004005h
0x1800aed90  cmovns  ebx, eax
0x1800aed93  jmp     loc_1800AEF85
0x1800aed98  lea     r9, [rbp+57h+var_68]
0x1800aed9c  xor     r8d, r8d
0x1800aed9f  mov     rdx, rbx
0x1800aeda2  mov     rcx, rdi
0x1800aeda5  call    cs:__imp_DevObjOpenDeviceInterface
0x1800aedab  test    eax, eax
0x1800aedad  jnz     short loc_1800AEE1A
0x1800aedaf  call    cs:__imp_GetLastError
0x1800aedb5  mov     ebx, eax
0x1800aedb7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aedbe  lea     rax, WPP_GLOBAL_Control
0x1800aedc5  cmp     rcx, rax
0x1800aedc8  jz      short loc_1800AEDFE
0x1800aedca  test    byte ptr [rcx+1Ch], 8
0x1800aedce  jz      short loc_1800AEDFE
0x1800aedd0  cmp     byte ptr [rcx+19h], 2
0x1800aedd4  jb      short loc_1800AEDFE
0x1800aedd6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aeddb  mov     edx, 0Fh
0x1800aede0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aede7  lea     r8, WPP_a94a9deae15032e68227e68649adf791_Traceguids
0x1800aedee  mov     r9d, eax
0x1800aedf1  mov     dword ptr [rsp+0B0h+var_90], ebx
0x1800aedf5  mov     rcx, [rcx+10h]
0x1800aedf9  call    WPP_SF_Dd
0x1800aedfe  test    ebx, ebx
0x1800aee00  jle     short loc_1800AEE0B
0x1800aee02  movzx   ebx, bx
0x1800aee05  or      ebx, 80070000h
0x1800aee0b  test    ebx, ebx
0x1800aee0d  mov     eax, 80004005h
0x1800aee12  cmovns  ebx, eax
0x1800aee15  jmp     loc_1800AEF78
0x1800aee1a  lea     rax, [rbp+57h+var_48]
0x1800aee1e  xor     r9d, r9d
0x1800aee21  mov     [rsp+0B0h+var_88], rax
0x1800aee26  lea     rdx, [rbp+57h+var_68]
0x1800aee2a  xor     r8d, r8d
0x1800aee2d  mov     [rsp+0B0h+var_90], 0
0x1800aee36  mov     rcx, rdi
0x1800aee39  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800aee3f  test    eax, eax
0x1800aee41  jnz     short loc_1800AEE84
0x1800aee43  call    cs:__imp_GetLastError
0x1800aee49  cmp     eax, 7Ah ; 'z'
0x1800aee4c  jz      short loc_1800AEE84
0x1800aee4e  call    cs:__imp_GetLastError
0x1800aee54  mov     ebx, eax
0x1800aee56  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aee5d  lea     rax, WPP_GLOBAL_Control
0x1800aee64  cmp     rcx, rax
0x1800aee67  jz      short loc_1800AEDFE
0x1800aee69  test    byte ptr [rcx+1Ch], 8
0x1800aee6d  jz      short loc_1800AEDFE
0x1800aee6f  cmp     byte ptr [rcx+19h], 2
0x1800aee73  jb      short loc_1800AEDFE
0x1800aee75  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aee7a  mov     edx, 10h
0x1800aee7f  jmp     loc_1800AEDE0
0x1800aee84  mov     [rsp+0B0h+var_78], 0
0x1800aee8c  lea     rax, [rbp+57h+var_6C]
0x1800aee90  mov     [rsp+0B0h+var_80], rax
0x1800aee95  lea     r9, [rbp+57h+var_70]
0x1800aee99  mov     dword ptr [rsp+0B0h+var_88], 10h
0x1800aeea1  lea     r8, ?PKEY_TIBUS_MUID@@3U_tagpropertykey@@B; _tagpropertykey const PKEY_TIBUS_MUID
0x1800aeea8  lea     rdx, [rbp+57h+var_48]
0x1800aeeac  mov     [rsp+0B0h+var_90], rsi
0x1800aeeb1  mov     rcx, rdi
0x1800aeeb4  mov     [rbp+57h+var_70], 0
0x1800aeebb  mov     [rbp+57h+var_6C], 0
0x1800aeec2  call    cs:__imp_DevObjGetDeviceProperty
0x1800aeec8  test    eax, eax
0x1800aeeca  jnz     short loc_1800AEF0E
0x1800aeecc  call    cs:__imp_GetLastError
0x1800aeed2  mov     ebx, eax
0x1800aeed4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeedb  lea     rax, WPP_GLOBAL_Control
0x1800aeee2  cmp     rcx, rax
0x1800aeee5  jz      loc_1800AEDFE
0x1800aeeeb  test    byte ptr [rcx+1Ch], 8
0x1800aeeef  jz      loc_1800AEDFE
0x1800aeef5  cmp     byte ptr [rcx+19h], 2
0x1800aeef9  jb      loc_1800AEDFE
0x1800aeeff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aef04  mov     edx, 11h
0x1800aef09  jmp     loc_1800AEDE0
0x1800aef0e  cmp     [rbp+57h+var_70], 0Dh
0x1800aef12  jnz     short loc_1800AEF1C
0x1800aef14  xor     ebx, ebx
0x1800aef16  cmp     [rbp+57h+var_6C], 10h
0x1800aef1a  jz      short loc_1800AEF78
0x1800aef1c  mov     ebx, 8000FFFFh
0x1800aef21  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aef28  lea     rax, WPP_GLOBAL_Control
0x1800aef2f  cmp     rcx, rax
0x1800aef32  jz      short loc_1800AEF78
0x1800aef34  test    byte ptr [rcx+1Ch], 8
0x1800aef38  jz      short loc_1800AEF78
0x1800aef3a  cmp     byte ptr [rcx+19h], 2
0x1800aef3e  jb      short loc_1800AEF78
0x1800aef40  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aef45  lea     rcx, aInvalidMuidRet; "invalid MUID returned!"
0x1800aef4c  mov     dword ptr [rsp+0B0h+var_88], 8000FFFFh
0x1800aef54  mov     [rsp+0B0h+var_90], rcx
0x1800aef59  lea     r8, WPP_a94a9deae15032e68227e68649adf791_Traceguids
0x1800aef60  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aef67  mov     edx, 12h
0x1800aef6c  mov     r9d, eax
0x1800aef6f  mov     rcx, [rcx+10h]
0x1800aef73  call    WPP_SF_DsD
0x1800aef78  mov     rcx, rdi
0x1800aef7b  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800aef81  test    ebx, ebx
0x1800aef83  jns     short loc_1800AEF90
0x1800aef85  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800aef8c  movdqu  xmmword ptr [rsi], xmm0
0x1800aef90  mov     eax, ebx
0x1800aef92  mov     rcx, [rbp+57h+var_18]
0x1800aef96  xor     rcx, rsp; StackCookie
0x1800aef99  call    __security_check_cookie
0x1800aef9e  mov     rbx, [rsp+0B0h+arg_10]
0x1800aefa6  add     rsp, 0A0h
0x1800aefad  pop     rdi
0x1800aefae  pop     rsi
0x1800aefaf  pop     rbp
0x1800aefb0  retn
```
