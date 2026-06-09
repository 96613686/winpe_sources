# NgcUtils::QueryLogonCredsAvailableRegState(std::vector<uchar,std::allocator<uchar>> const &,NgcUtils::LogonCredsAvailableRegState *)

- ea: `0x180024b70`
- end: `0x180025008`
- name: `?QueryLogonCredsAvailableRegState@NgcUtils@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@PEAW4LogonCredsAvailableRegState@1@@Z`
- size: `1176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180037ef0`

## callees

- `0x180024a20`
- `0x180024b70`
- `0x18002dff0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024d0e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024e7b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024faa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024d0e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024e7b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024faa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024c5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024c5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024dc2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024fb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::QueryLogonCredsAvailableRegState(__int64 a1, unsigned int *a2)
{
  unsigned int v3; // esi
  unsigned __int64 v4; // rdx
  LPCWSTR v5; // rax
  WCHAR *v6; // rcx
  const WCHAR *v8; // rdx
  unsigned int v9; // ebx
  WCHAR *v10; // rax
  unsigned __int64 v11; // rdx
  char *v12; // rcx
  LSTATUS ValueW; // eax
  char *v14; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v16; // [rsp+44h] [rbp-35h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-31h] BYREF
  int pvData; // [rsp+4Ch] [rbp-2Dh] BYREF
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-21h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v22; // [rsp+78h] [rbp-1h]
  unsigned __int64 v23; // [rsp+80h] [rbp+7h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp+Fh] BYREF
  char *v25; // [rsp+98h] [rbp+1Fh]
  int v26; // [rsp+A0h] [rbp+27h]
  int v27; // [rsp+A4h] [rbp+2Bh]
  unsigned int *v28; // [rsp+A8h] [rbp+2Fh]
  __int64 v29; // [rsp+B0h] [rbp+37h]

  *(_OWORD *)lpSubKey = 0;
  v22 = 0;
  v23 = 7;
  LOWORD(lpSubKey[0]) = 0;
  v3 = NgcUtils::BuildFullRegKeyPath_0(a1, lpSubKey);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( v23 <= 7 )
      return v3;
    v4 = 2 * v23 + 2;
    if ( v4 < 0x1000 )
    {
      v5 = lpSubKey[0];
      goto LABEL_6;
    }
    v5 = (LPCWSTR)*((_QWORD *)lpSubKey[0] - 1);
    if ( (unsigned __int64)((char *)lpSubKey[0] - (char *)v5 - 8) <= 0x1F )
    {
      v4 = 2 * v23 + 41;
LABEL_6:
      v6 = (WCHAR *)v5;
LABEL_7:
      operator delete(v6, v4);
      return v3;
    }
LABEL_50:
    __fastfail(5u);
  }
  hKey = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v23 > 7 )
    v8 = lpSubKey[0];
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x101u, &hKey);
  if ( (v9 & 0xFFFFFFFD) != 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v16 = v9;
      v28 = &v16;
      v29 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v25 = byte_180063843;
      v26 = 41;
      v27 = 1;
      pcbData = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( (int)v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v23 <= 7 )
      return v9;
    v10 = (WCHAR *)lpSubKey[0];
    v11 = 2 * v23 + 2;
    if ( v11 >= 0x1000 )
    {
      v12 = (char *)*((_QWORD *)lpSubKey[0] - 1);
      if ( (unsigned __int64)((char *)lpSubKey[0] - v12 - 8) > 0x1F )
        goto LABEL_50;
      operator delete(v12, 2 * v23 + 41);
      return v9;
    }
LABEL_23:
    operator delete(v10, v11);
    return v9;
  }
  pvData = 0;
  if ( v9 == 2 )
    goto LABEL_41;
  pcbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"LogonCredsAvailable", 0x10u, 0, &pvData, &pcbData);
  v9 = ValueW;
  if ( !ValueW )
  {
    if ( pvData == 2 )
      *a2 = 1;
    else
      *a2 = 3 - (pvData != 0);
    goto LABEL_42;
  }
  if ( ValueW == 2 )
  {
LABEL_41:
    *a2 = 0;
LABEL_42:
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      v17 = *a2;
      v28 = &v17;
      v29 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v25 = (char *)&unk_1800637E0;
      v26 = 42;
      v27 = 1;
      pcbData = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v23 <= 7 )
      return v3;
    v5 = lpSubKey[0];
    v4 = 2 * v23 + 2;
    if ( v4 < 0x1000 )
      goto LABEL_6;
    v6 = (WCHAR *)*((_QWORD *)lpSubKey[0] - 1);
    if ( (unsigned __int64)((char *)lpSubKey[0] - (char *)v6 - 8) <= 0x1F )
    {
      v4 = 2 * v23 + 41;
      goto LABEL_7;
    }
    goto LABEL_50;
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    v16 = ValueW;
    v28 = &v16;
    v29 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    UserData.Reserved = 2;
    v25 = (char *)&unk_1800637A8;
    v26 = 44;
    v27 = 1;
    v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( (int)v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v23 <= 7 )
    return v9;
  v10 = (WCHAR *)lpSubKey[0];
  v11 = 2 * v23 + 2;
  if ( v11 < 0x1000 )
    goto LABEL_23;
  v14 = (char *)*((_QWORD *)lpSubKey[0] - 1);
  if ( (unsigned __int64)((char *)lpSubKey[0] - v14 - 8) > 0x1F )
    goto LABEL_50;
  operator delete(v14, 2 * v23 + 41);
  return v9;
}

```

## disassembly

```asm
0x180024b70  mov     [rsp-8+arg_10], rbx
0x180024b75  mov     [rsp-8+arg_18], rsi
0x180024b7a  push    rbp
0x180024b7b  push    rdi
0x180024b7c  push    r14
0x180024b7e  lea     rbp, [rsp-47h]
0x180024b83  sub     rsp, 0C0h
0x180024b8a  mov     rax, cs:__security_cookie
0x180024b91  xor     rax, rsp
0x180024b94  mov     [rbp+57h+var_18], rax
0x180024b98  mov     rdi, rdx
0x180024b9b  xorps   xmm0, xmm0
0x180024b9e  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180024ba2  xor     r14d, r14d
0x180024ba5  mov     [rbp+57h+var_58], r14
0x180024ba9  mov     [rbp+57h+var_50], 7
0x180024bb1  mov     word ptr [rbp+57h+lpSubKey], r14w
0x180024bb6  lea     rdx, [rbp+57h+lpSubKey]
0x180024bba  call    NgcUtils__BuildFullRegKeyPath_0
0x180024bbf  mov     esi, eax
0x180024bc1  test    eax, eax
0x180024bc3  jns     short loc_180024C30
0x180024bc5  mov     rdx, [rbp+57h+var_50]
0x180024bc9  cmp     rdx, 7
0x180024bcd  jbe     short loc_180024C05
0x180024bcf  mov     rcx, [rbp+57h+lpSubKey]
0x180024bd3  lea     rdx, ds:2[rdx*2]
0x180024bdb  cmp     rdx, 1000h
0x180024be2  jb      short loc_180024C2B
0x180024be4  mov     rax, [rcx-8]
0x180024be8  sub     rcx, rax
0x180024beb  sub     rcx, 8
0x180024bef  cmp     rcx, 1Fh
0x180024bf3  ja      loc_180025001
0x180024bf9  add     rdx, 27h ; '''; unsigned __int64
0x180024bfd  mov     rcx, rax; void *
0x180024c00  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024c05  mov     eax, esi
0x180024c07  mov     rcx, [rbp+57h+var_18]
0x180024c0b  xor     rcx, rsp; StackCookie
0x180024c0e  call    __security_check_cookie
0x180024c13  lea     r11, [rsp+0D0h+var_10]
0x180024c1b  mov     rbx, [r11+30h]
0x180024c1f  mov     rsi, [r11+38h]
0x180024c23  mov     rsp, r11
0x180024c26  pop     r14
0x180024c28  pop     rdi
0x180024c29  pop     rbp
0x180024c2a  retn
0x180024c2b  mov     rax, rcx
0x180024c2e  jmp     short loc_180024BFD
0x180024c30  mov     [rbp+57h+hKey], r14
0x180024c34  lea     rdx, [rbp+57h+lpSubKey]
0x180024c38  cmp     [rbp+57h+var_50], 7
0x180024c3d  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180024c42  lea     rax, [rbp+57h+hKey]
0x180024c46  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180024c4b  mov     r9d, 101h; samDesired
0x180024c51  xor     r8d, r8d; ulOptions
0x180024c54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024c5b  call    cs:__imp_RegOpenKeyExW
0x180024c61  mov     ebx, eax
0x180024c63  test    eax, 0FFFFFFFDh
0x180024c68  jz      loc_180024D84
0x180024c6e  mov     eax, cs:dword_18006E000
0x180024c74  cmp     eax, 2
0x180024c77  jbe     loc_180024D14
0x180024c7d  mov     [rbp+57h+var_8C], ebx
0x180024c80  lea     rax, [rbp+57h+var_8C]
0x180024c84  mov     [rbp+57h+var_28], rax
0x180024c88  mov     [rbp+57h+var_20], 4
0x180024c90  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180024c97  movzx   eax, cs:word_180063839
0x180024c9e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180024ca1  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x180024ca5  mov     rax, cs:off_18006E008
0x180024cac  mov     [rbp+57h+var_48.Ptr], rax
0x180024cb0  movzx   eax, word ptr [rax]
0x180024cb3  mov     [rbp+57h+var_48.Size], eax
0x180024cb6  mov     dword ptr [rbp+57h+var_48.0Ch], 2
0x180024cbd  lea     rax, byte_180063843
0x180024cc4  mov     [rbp+57h+var_38], rax
0x180024cc8  mov     [rbp+57h+var_30], 29h ; ')'
0x180024ccf  mov     [rbp+57h+var_2C], 1
0x180024cd6  lea     rax, _TraceLoggingMetadataEnd
0x180024cdd  lea     rcx, _TraceLoggingMetadata
0x180024ce4  sub     eax, ecx
0x180024ce6  mov     [rbp+57h+var_90], eax
0x180024ce9  mov     eax, [rbp+57h+var_90]
0x180024cec  lea     rax, [rbp+57h+var_48]
0x180024cf0  mov     [rsp+0D0h+UserData], rax; UserData
0x180024cf5  mov     dword ptr [rsp+0D0h+phkResult], 3; UserDataCount
0x180024cfd  xor     r9d, r9d; RelatedActivityId
0x180024d00  xor     r8d, r8d; ActivityId
0x180024d03  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180024d07  mov     rcx, cs:RegHandle; RegHandle
0x180024d0e  call    cs:__imp_EventWriteTransfer
0x180024d14  test    ebx, ebx
0x180024d16  jle     short loc_180024D21
0x180024d18  movzx   ebx, bx
0x180024d1b  or      ebx, 80070000h
0x180024d21  mov     rcx, [rbp+57h+hKey]; hKey
0x180024d25  test    rcx, rcx
0x180024d28  jz      short loc_180024D31
0x180024d2a  call    cs:__imp_RegCloseKey
0x180024d30  nop
0x180024d31  mov     rdx, [rbp+57h+var_50]
0x180024d35  cmp     rdx, 7
0x180024d39  jbe     short loc_180024D7D
0x180024d3b  mov     rax, [rbp+57h+lpSubKey]
0x180024d3f  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180024d47  cmp     rdx, 1000h
0x180024d4e  jb      short loc_180024D75
0x180024d50  mov     rcx, [rax-8]; void *
0x180024d54  sub     rax, rcx
0x180024d57  sub     rax, 8
0x180024d5b  cmp     rax, 1Fh
0x180024d5f  ja      loc_180025001
0x180024d65  add     rdx, 27h ; '''; unsigned __int64
0x180024d69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024d6e  mov     eax, ebx
0x180024d70  jmp     loc_180024C07
0x180024d75  mov     rcx, rax; void *
0x180024d78  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024d7d  mov     eax, ebx
0x180024d7f  jmp     loc_180024C07
0x180024d84  mov     [rbp+57h+pvData], r14d
0x180024d88  cmp     ebx, 2
0x180024d8b  jz      loc_180024F05
0x180024d91  mov     [rbp+57h+var_90], 4
0x180024d98  lea     rax, [rbp+57h+var_90]
0x180024d9c  mov     [rsp+0D0h+pcbData], rax; pcbData
0x180024da1  lea     rax, [rbp+57h+pvData]
0x180024da5  mov     [rsp+0D0h+UserData], rax; pvData
0x180024daa  mov     [rsp+0D0h+phkResult], r14; pdwType
0x180024daf  mov     r9d, 10h; dwFlags
0x180024db5  lea     r8, aLogoncredsavai; "LogonCredsAvailable"
0x180024dbc  xor     edx, edx; lpSubKey
0x180024dbe  mov     rcx, [rbp+57h+hKey]; hkey
0x180024dc2  call    cs:__imp_RegGetValueW
0x180024dc8  mov     ebx, eax
0x180024dca  test    eax, eax
0x180024dcc  jz      loc_180024EEA
0x180024dd2  cmp     eax, 2
0x180024dd5  jz      loc_180024F05
0x180024ddb  mov     eax, cs:dword_18006E000
0x180024de1  cmp     eax, 2
0x180024de4  jbe     loc_180024E81
0x180024dea  mov     [rbp+57h+var_8C], ebx
0x180024ded  lea     rax, [rbp+57h+var_8C]
0x180024df1  mov     [rbp+57h+var_28], rax
0x180024df5  mov     [rbp+57h+var_20], 4
0x180024dfd  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180024e04  movzx   eax, cs:word_18006379E
0x180024e0b  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180024e0e  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x180024e12  mov     rax, cs:off_18006E008
0x180024e19  mov     [rbp+57h+var_48.Ptr], rax
0x180024e1d  movzx   eax, word ptr [rax]
0x180024e20  mov     [rbp+57h+var_48.Size], eax
0x180024e23  mov     dword ptr [rbp+57h+var_48.0Ch], 2
0x180024e2a  lea     rax, unk_1800637A8
0x180024e31  mov     [rbp+57h+var_38], rax
0x180024e35  mov     [rbp+57h+var_30], 2Ch ; ','
0x180024e3c  mov     [rbp+57h+var_2C], 1
0x180024e43  lea     rax, _TraceLoggingMetadataEnd
0x180024e4a  lea     rcx, _TraceLoggingMetadata
0x180024e51  sub     eax, ecx
0x180024e53  mov     [rbp+57h+var_88], eax
0x180024e56  mov     eax, [rbp+57h+var_88]
0x180024e59  lea     rax, [rbp+57h+var_48]
0x180024e5d  mov     [rsp+0D0h+UserData], rax; UserData
0x180024e62  mov     dword ptr [rsp+0D0h+phkResult], 3; UserDataCount
0x180024e6a  xor     r9d, r9d; RelatedActivityId
0x180024e6d  xor     r8d, r8d; ActivityId
0x180024e70  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180024e74  mov     rcx, cs:RegHandle; RegHandle
0x180024e7b  call    cs:__imp_EventWriteTransfer
0x180024e81  test    ebx, ebx
0x180024e83  jle     short loc_180024E8E
0x180024e85  movzx   ebx, bx
0x180024e88  or      ebx, 80070000h
0x180024e8e  mov     rcx, [rbp+57h+hKey]; hKey
0x180024e92  test    rcx, rcx
0x180024e95  jz      short loc_180024E9E
0x180024e97  call    cs:__imp_RegCloseKey
0x180024e9d  nop
0x180024e9e  mov     rdx, [rbp+57h+var_50]
0x180024ea2  cmp     rdx, 7
0x180024ea6  jbe     loc_180024D7D
0x180024eac  mov     rax, [rbp+57h+lpSubKey]
0x180024eb0  lea     rdx, ds:2[rdx*2]
0x180024eb8  cmp     rdx, 1000h
0x180024ebf  jb      loc_180024D75
0x180024ec5  mov     rcx, [rax-8]; void *
0x180024ec9  sub     rax, rcx
0x180024ecc  sub     rax, 8
0x180024ed0  cmp     rax, 1Fh
0x180024ed4  ja      loc_180025001
0x180024eda  add     rdx, 27h ; '''; unsigned __int64
0x180024ede  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024ee3  mov     eax, ebx
0x180024ee5  jmp     loc_180024C07
0x180024eea  mov     eax, [rbp+57h+pvData]
0x180024eed  cmp     eax, 2
0x180024ef0  jnz     short loc_180024EFA
0x180024ef2  mov     dword ptr [rdi], 1
0x180024ef8  jmp     short loc_180024F08
0x180024efa  neg     eax
0x180024efc  sbb     eax, eax
0x180024efe  add     eax, 3
0x180024f01  mov     [rdi], eax
0x180024f03  jmp     short loc_180024F08
0x180024f05  mov     [rdi], r14d
0x180024f08  mov     eax, cs:dword_18006E000
0x180024f0e  cmp     eax, 4
0x180024f11  jbe     loc_180024FB0
0x180024f17  mov     eax, [rdi]
0x180024f19  mov     [rbp+57h+var_88], eax
0x180024f1c  lea     rax, [rbp+57h+var_88]
0x180024f20  mov     [rbp+57h+var_28], rax
0x180024f24  mov     [rbp+57h+var_20], 4
0x180024f2c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180024f33  movzx   eax, cs:word_1800637D6
0x180024f3a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180024f3d  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x180024f41  mov     rax, cs:off_18006E008
0x180024f48  mov     [rbp+57h+var_48.Ptr], rax
0x180024f4c  movzx   eax, word ptr [rax]
0x180024f4f  mov     [rbp+57h+var_48.Size], eax
0x180024f52  mov     dword ptr [rbp+57h+var_48.0Ch], 2
0x180024f59  lea     rax, unk_1800637E0
0x180024f60  mov     [rbp+57h+var_38], rax
0x180024f64  mov     [rbp+57h+var_30], 2Ah ; '*'
0x180024f6b  mov     [rbp+57h+var_2C], 1
0x180024f72  lea     rax, _TraceLoggingMetadataEnd
0x180024f79  lea     rcx, _TraceLoggingMetadata
0x180024f80  sub     eax, ecx
0x180024f82  mov     [rbp+57h+var_90], eax
0x180024f85  mov     eax, [rbp+57h+var_90]
0x180024f88  lea     rax, [rbp+57h+var_48]
0x180024f8c  mov     [rsp+0D0h+UserData], rax; UserData
0x180024f91  mov     dword ptr [rsp+0D0h+phkResult], 3; UserDataCount
0x180024f99  xor     r9d, r9d; RelatedActivityId
0x180024f9c  xor     r8d, r8d; ActivityId
0x180024f9f  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180024fa3  mov     rcx, cs:RegHandle; RegHandle
0x180024faa  call    cs:__imp_EventWriteTransfer
0x180024fb0  mov     rcx, [rbp+57h+hKey]; hKey
0x180024fb4  test    rcx, rcx
0x180024fb7  jz      short loc_180024FC0
0x180024fb9  call    cs:__imp_RegCloseKey
0x180024fbf  nop
0x180024fc0  mov     rdx, [rbp+57h+var_50]
0x180024fc4  cmp     rdx, 7
0x180024fc8  jbe     loc_180024C05
0x180024fce  mov     rax, [rbp+57h+lpSubKey]
0x180024fd2  lea     rdx, ds:2[rdx*2]
0x180024fda  cmp     rdx, 1000h
0x180024fe1  jb      loc_180024BFD
0x180024fe7  mov     rcx, [rax-8]
0x180024feb  sub     rax, rcx
0x180024fee  sub     rax, 8
0x180024ff2  cmp     rax, 1Fh
0x180024ff6  ja      short loc_180025001
0x180024ff8  add     rdx, 27h ; '''
0x180024ffc  jmp     loc_180024C00
0x180025001  mov     ecx, 5
0x180025006  int     29h; Win8: RtlFailFast(ecx)
```
