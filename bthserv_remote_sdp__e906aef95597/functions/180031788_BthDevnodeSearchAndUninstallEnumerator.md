# BthDevnodeSearchAndUninstallEnumerator

- ea: `0x180031788`
- end: `0x180031a31`
- name: `BthDevnodeSearchAndUninstallEnumerator`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027c48`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180031788`
- `0x180031a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003183c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003183c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031990`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031990`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031939`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031939`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031957`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031957`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180031888`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180031888`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800317ce`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800317ce`
- `DEVOBJ!DevObjGetClassDevs` at `0x180031822`
- `DEVOBJ!DevObjGetClassDevs` at `0x180031822`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800319d3`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800319d3`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800318bb`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800318bb`

## pseudocode

```c
__int64 __fastcall BthDevnodeSearchAndUninstallEnumerator(__int64 a1, const WCHAR *a2)
{
  __int64 DeviceInfoList; // rdi
  signed int LastError; // eax
  int v5; // ebx
  signed int v6; // eax
  unsigned int v7; // r14d
  HKEY v8; // r15
  signed int v9; // eax
  LSTATUS Value; // eax
  unsigned int v11; // esi
  signed int v13; // eax
  _BYTE Type[64]; // [rsp+38h] [rbp-99h] BYREF
  WCHAR Data[64]; // [rsp+78h] [rbp-59h] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_40;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_40:
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, L"bthenum", 4, 0, 0) )
    {
      v5 = 0;
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
    v7 = 0;
    while ( v5 >= 0 )
    {
      memset(&Type[8], 0, 48);
      *(_DWORD *)&Type[8] = 48;
      if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, v7, &Type[8]) )
      {
        v8 = (HKEY)DevObjOpenDevRegKey(DeviceInfoList, &Type[8], 1);
        if ( v8 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          v9 = GetLastError();
          v5 = v9;
          if ( v9 > 0 )
            v5 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v5 = 0;
        }
        if ( v5 >= 0 )
        {
          *(_DWORD *)Type = 0;
          memset_0(Data, 0, 0x7Cu);
          *(_DWORD *)&Type[4] = 124;
          Value = RegQueryValueExW(v8, L"Bluetooth_UniqueID", 0, (LPDWORD)Type, (LPBYTE)Data, (LPDWORD)&Type[4]);
          v11 = Value;
          if ( Value > 0 )
            v11 = (unsigned __int16)Value | 0x80070000;
          RegCloseKey(v8);
          v5 = 0;
          if ( v11 != -536870389 )
            v5 = v11;
          if ( v5 >= 0 && *(_DWORD *)Type == 1 && CompareStringOrdinal(a2, -1, Data, -1, 1) == 2 )
            v5 = BthDevnodeUninstallDevice(DeviceInfoList, (__int64)&Type[8]);
        }
      }
      else
      {
        v13 = GetLastError();
        v5 = v13;
        if ( v13 > 0 )
          v5 = (unsigned __int16)v13 | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
      }
      ++v7;
    }
    if ( v5 == -2147024637 )
      v5 = 0;
    if ( DeviceInfoList != -1 )
      DevObjDestroyDeviceInfoList(DeviceInfoList);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031788  mov     rax, rsp
0x18003178b  mov     [rax+8], rbx
0x18003178f  mov     [rax+18h], rsi
0x180031793  mov     [rax+20h], rdi
0x180031797  push    rbp
0x180031798  push    r12
0x18003179a  push    r13
0x18003179c  push    r14
0x18003179e  push    r15
0x1800317a0  lea     rbp, [rax-5Fh]
0x1800317a4  sub     rsp, 100h
0x1800317ab  mov     rax, cs:__security_cookie
0x1800317b2  xor     rax, rsp
0x1800317b5  mov     [rbp+57h+var_30], rax
0x1800317b9  mov     r12, rdx
0x1800317bc  xor     r13d, r13d
0x1800317bf  xor     edx, edx
0x1800317c1  mov     [rsp+120h+lpData], r13
0x1800317c6  xor     r9d, r9d
0x1800317c9  xor     r8d, r8d
0x1800317cc  xor     ecx, ecx
0x1800317ce  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800317d5  nop     dword ptr [rax+rax+00h]
0x1800317da  mov     rdi, rax
0x1800317dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800317e1  jnz     short loc_180031806
0x1800317e3  call    cs:__imp_GetLastError
0x1800317ea  nop     dword ptr [rax+rax+00h]
0x1800317ef  mov     ebx, eax
0x1800317f1  test    eax, eax
0x1800317f3  jle     short loc_1800317FE
0x1800317f5  movzx   ebx, ax
0x1800317f8  or      ebx, 80070000h
0x1800317fe  test    ebx, ebx
0x180031800  js      loc_1800319DF
0x180031806  mov     [rsp+120h+lpcbData], r13
0x18003180b  lea     r8, aBthenum; "bthenum"
0x180031812  mov     r9d, 4
0x180031818  mov     [rsp+120h+lpData], r13
0x18003181d  xor     edx, edx
0x18003181f  mov     rcx, rdi
0x180031822  call    cs:__imp_DevObjGetClassDevs
0x180031829  nop     dword ptr [rax+rax+00h]
0x18003182e  mov     esi, 80004005h
0x180031833  test    eax, eax
0x180031835  jz      short loc_18003183C
0x180031837  mov     ebx, r13d
0x18003183a  jmp     short loc_18003185C
0x18003183c  call    cs:__imp_GetLastError
0x180031843  nop     dword ptr [rax+rax+00h]
0x180031848  mov     ebx, eax
0x18003184a  test    eax, eax
0x18003184c  jle     short loc_180031857
0x18003184e  movzx   ebx, ax
0x180031851  or      ebx, 80070000h
0x180031857  test    ebx, ebx
0x180031859  cmovns  ebx, esi
0x18003185c  mov     r14d, r13d
0x18003185f  jmp     loc_1800319B8
0x180031864  xorps   xmm0, xmm0
0x180031867  lea     r8, [rsp+120h+Type+8]
0x18003186c  movups  xmmword ptr [rsp+120h+Type+8], xmm0
0x180031871  mov     edx, r14d
0x180031874  mov     [rsp+120h+Type+8], 30h ; '0'
0x18003187c  mov     rcx, rdi
0x18003187f  movups  [rsp+120h+var_E0+8], xmm0
0x180031884  movups  [rbp+57h+var_C8], xmm0
0x180031888  call    cs:__imp_DevObjEnumDeviceInfo
0x18003188f  nop     dword ptr [rax+rax+00h]
0x180031894  test    eax, eax
0x180031896  jz      loc_180031A0F
0x18003189c  xor     r9d, r9d
0x18003189f  mov     dword ptr [rsp+120h+lpcbData], 20019h
0x1800318a7  lea     rdx, [rsp+120h+Type+8]
0x1800318ac  mov     dword ptr [rsp+120h+lpData], 1
0x1800318b4  mov     rcx, rdi
0x1800318b7  lea     r8d, [r9+1]
0x1800318bb  call    cs:__imp_DevObjOpenDevRegKey
0x1800318c2  nop     dword ptr [rax+rax+00h]
0x1800318c7  mov     r15, rax
0x1800318ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800318ce  jnz     short loc_1800318ED
0x1800318d0  call    cs:__imp_GetLastError
0x1800318d7  nop     dword ptr [rax+rax+00h]
0x1800318dc  mov     ebx, eax
0x1800318de  test    eax, eax
0x1800318e0  jle     short loc_1800318F0
0x1800318e2  movzx   ebx, ax
0x1800318e5  or      ebx, 80070000h
0x1800318eb  jmp     short loc_1800318F0
0x1800318ed  mov     ebx, r13d
0x1800318f0  test    ebx, ebx
0x1800318f2  js      loc_1800319B5
0x1800318f8  mov     ebx, 7Ch ; '|'
0x1800318fd  mov     [rsp+120h+Type], r13d
0x180031902  mov     r8d, ebx; Size
0x180031905  lea     rcx, [rbp+57h+Data]; void *
0x180031909  xor     edx, edx; Val
0x18003190b  call    memset_0
0x180031910  lea     rax, [rsp+120h+Type+4]
0x180031915  mov     [rsp+120h+Type+4], ebx
0x180031919  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18003191e  lea     r9, [rsp+120h+Type]; lpType
0x180031923  lea     rax, [rbp+57h+Data]
0x180031927  xor     r8d, r8d; lpReserved
0x18003192a  lea     rdx, aBluetoothUniqu; "Bluetooth_UniqueID"
0x180031931  mov     [rsp+120h+lpData], rax; lpData
0x180031936  mov     rcx, r15; hKey
0x180031939  call    cs:__imp_RegQueryValueExW
0x180031940  nop     dword ptr [rax+rax+00h]
0x180031945  mov     esi, eax
0x180031947  test    eax, eax
0x180031949  jle     short loc_180031954
0x18003194b  movzx   esi, ax
0x18003194e  or      esi, 80070000h
0x180031954  mov     rcx, r15; hKey
0x180031957  call    cs:__imp_RegCloseKey
0x18003195e  nop     dword ptr [rax+rax+00h]
0x180031963  cmp     esi, 0E000020Bh
0x180031969  mov     ebx, r13d
0x18003196c  cmovnz  ebx, esi
0x18003196f  test    ebx, ebx
0x180031971  js      short loc_1800319B0
0x180031973  cmp     [rsp+120h+Type], 1
0x180031978  jnz     short loc_1800319B0
0x18003197a  or      r9d, 0FFFFFFFFh; cchCount2
0x18003197e  mov     dword ptr [rsp+120h+lpData], 1; bIgnoreCase
0x180031986  or      edx, r9d; cchCount1
0x180031989  lea     r8, [rbp+57h+Data]; lpString2
0x18003198d  mov     rcx, r12; lpString1
0x180031990  call    cs:__imp_CompareStringOrdinal
0x180031997  nop     dword ptr [rax+rax+00h]
0x18003199c  cmp     eax, 2
0x18003199f  jnz     short loc_1800319B0
0x1800319a1  lea     rdx, [rsp+120h+Type+8]
0x1800319a6  mov     rcx, rdi
0x1800319a9  call    BthDevnodeUninstallDevice
0x1800319ae  mov     ebx, eax
0x1800319b0  mov     esi, 80004005h
0x1800319b5  inc     r14d
0x1800319b8  test    ebx, ebx
0x1800319ba  jns     loc_180031864
0x1800319c0  cmp     ebx, 80070103h
0x1800319c6  cmovz   ebx, r13d
0x1800319ca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800319ce  jz      short loc_1800319DF
0x1800319d0  mov     rcx, rdi
0x1800319d3  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800319da  nop     dword ptr [rax+rax+00h]
0x1800319df  mov     eax, ebx
0x1800319e1  mov     rcx, [rbp+57h+var_30]
0x1800319e5  xor     rcx, rsp; StackCookie
0x1800319e8  call    __security_check_cookie
0x1800319ed  lea     r11, [rsp+120h+var_20]
0x1800319f5  mov     rbx, [r11+30h]
0x1800319f9  mov     rsi, [r11+40h]
0x1800319fd  mov     rdi, [r11+48h]
0x180031a01  mov     rsp, r11
0x180031a04  pop     r15
0x180031a06  pop     r14
0x180031a08  pop     r13
0x180031a0a  pop     r12
0x180031a0c  pop     rbp
0x180031a0d  retn
0x180031a0f  call    cs:__imp_GetLastError
0x180031a16  nop     dword ptr [rax+rax+00h]
0x180031a1b  mov     ebx, eax
0x180031a1d  test    eax, eax
0x180031a1f  jle     short loc_180031A2A
0x180031a21  movzx   ebx, ax
0x180031a24  or      ebx, 80070000h
0x180031a2a  test    ebx, ebx
0x180031a2c  cmovns  ebx, esi
0x180031a2f  jmp     short loc_1800319B5
```
