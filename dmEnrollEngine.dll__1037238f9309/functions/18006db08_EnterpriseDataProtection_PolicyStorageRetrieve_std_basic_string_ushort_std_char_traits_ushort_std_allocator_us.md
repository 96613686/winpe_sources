# EnterpriseDataProtection::PolicyStorageRetrieve(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,bool *,bool *)

- ea: `0x18006db08`
- end: `0x18006de02`
- name: `?PolicyStorageRetrieve@EnterpriseDataProtection@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV23@PEA_N2@Z`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006d934`

## callees

- `0x18000e0d0`
- `0x180010f8c`
- `0x180011fd0`
- `0x180017f8c`
- `0x18001f95c`
- `0x18002e1a0`
- `0x18006cdc4`
- `0x18006db08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006db96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006db96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dc12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dc60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dcff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dd5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dc12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dc60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dcff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006dd5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006db62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dbbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dbd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ddc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dddc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006db62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dbbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dbd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ddc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dddc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnterpriseDataProtection::PolicyStorageRetrieve(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        bool *a4,
        bool *a5)
{
  LSTATUS v8; // edi
  HKEY v9; // rcx
  LSTATUS v11; // eax
  signed int v12; // ebx
  HKEY v13; // rcx
  bool v14; // zf
  HKEY v15; // rcx
  LSTATUS ValueW; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  HKEY v19; // rcx
  HKEY v20; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-51h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-41h] BYREF
  DWORD pdwType; // [rsp+58h] [rbp-39h] BYREF
  PVOID pvData[2]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v26; // [rsp+70h] [rbp-21h]
  int v27; // [rsp+78h] [rbp-19h] BYREF
  int v28; // [rsp+7Ch] [rbp-15h] BYREF
  _OWORD v29[2]; // [rsp+80h] [rbp-11h] BYREF

  hKey = 0;
  v8 = EEDBManager::OpenEnrollmentsHKEY(131097, &hKey);
  if ( v8 < 0 )
  {
    v9 = hKey;
    hKey = 0;
    if ( v9 )
      RegCloseKey(v9);
    return (unsigned int)v8;
  }
  hkey = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v11 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hkey);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 < 0 )
    goto LABEL_10;
  pdwType = 0;
  pcbData = 0;
  RegGetValueW(hkey, 0, L"EnterpriseDataProtectionIdsToRevoke", 2u, &pdwType, 0, &pcbData);
  *(_OWORD *)pvData = 0;
  v26 = 0;
  if ( pcbData )
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(pvData);
  ValueW = RegGetValueW(hkey, 0, L"EnterpriseDataProtectionIdsToRevoke", 2u, &pdwType, pvData[0], &pcbData);
  v12 = ValueW;
  if ( ValueW > 0 )
    v12 = (unsigned __int16)ValueW | 0x80070000;
  if ( v12 < 0 )
  {
LABEL_20:
    if ( pvData[0] )
    {
      std::_Deallocate<16>((_QWORD *)pvData[0], v26 - (unsigned __int64)pvData[0]);
      *(_OWORD *)pvData = 0;
      v26 = 0;
    }
LABEL_10:
    v13 = hkey;
    v14 = hkey == 0;
    hkey = 0;
    if ( !v14 )
      RegCloseKey(v13);
    v15 = hKey;
    hKey = 0;
    if ( v15 )
      RegCloseKey(v15);
    return (unsigned int)v12;
  }
  memset(v29, 0, sizeof(v29));
  std::wstring::_Construct<1,unsigned short const *>(
    v29,
    pvData[0],
    (unsigned __int64)((char *)pvData[1] - (char *)pvData[0]) >> 1);
  v27 = 0;
  pcbData = 4;
  v17 = RegGetValueW(hkey, 0, L"RevokeOnUnenroll", 0x10u, &pdwType, &v27, &pcbData);
  v12 = v17;
  if ( v17 > 0 )
    v12 = (unsigned __int16)v17 | 0x80070000;
  if ( v12 < 0 )
    goto LABEL_25;
  v28 = 0;
  pcbData = 4;
  v18 = RegGetValueW(hkey, 0, L"RevokeOnMDMHandoff", 0x10u, &pdwType, &v28, &pcbData);
  v12 = v18;
  if ( v18 > 0 )
    v12 = (unsigned __int16)v18 | 0x80070000;
  if ( v12 < 0 )
  {
LABEL_25:
    std::wstring::_Tidy_deallocate(v29);
    goto LABEL_20;
  }
  std::wstring::operator=(a3, v29);
  *a4 = v27 != 0;
  *a5 = v28 != 0;
  std::wstring::_Tidy_deallocate(v29);
  if ( pvData[0] )
  {
    std::_Deallocate<16>((_QWORD *)pvData[0], v26 - (unsigned __int64)pvData[0]);
    *(_OWORD *)pvData = 0;
    v26 = 0;
  }
  v19 = hkey;
  hkey = 0;
  if ( v19 )
    RegCloseKey(v19);
  v20 = hKey;
  hKey = 0;
  if ( v20 )
    RegCloseKey(v20);
  return 0;
}

```

## disassembly

```asm
0x18006db08  push    rbp
0x18006db0a  push    rbx
0x18006db0b  push    rsi
0x18006db0c  push    rdi
0x18006db0d  push    r12
0x18006db0f  push    r14
0x18006db11  push    r15
0x18006db13  lea     rbp, [rsp-1Fh]
0x18006db18  sub     rsp, 0B0h
0x18006db1f  mov     rax, cs:__security_cookie
0x18006db26  xor     rax, rsp
0x18006db29  mov     [rbp+4Fh+var_40], rax
0x18006db2d  mov     r14, r9
0x18006db30  mov     rsi, r8
0x18006db33  mov     rbx, rdx
0x18006db36  mov     r15, [rbp+4Fh+arg_20]
0x18006db3a  xor     r12d, r12d
0x18006db3d  mov     [rbp+4Fh+hKey], r12
0x18006db41  lea     rdx, [rbp+4Fh+hKey]; HKEY *
0x18006db45  mov     ecx, 20019h; unsigned int
0x18006db4a  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18006db4f  mov     edi, eax
0x18006db51  test    eax, eax
0x18006db53  jns     short loc_18006DB6F
0x18006db55  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006db59  mov     [rbp+4Fh+hKey], r12
0x18006db5d  test    rcx, rcx
0x18006db60  jz      short loc_18006DB68
0x18006db62  call    cs:__imp_RegCloseKey
0x18006db68  mov     eax, edi
0x18006db6a  jmp     loc_18006DDE4
0x18006db6f  mov     [rbp+4Fh+hkey], r12
0x18006db73  cmp     qword ptr [rbx+18h], 7
0x18006db78  jbe     short loc_18006DB7D
0x18006db7a  mov     rbx, [rbx]
0x18006db7d  lea     rax, [rbp+4Fh+hkey]
0x18006db81  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18006db86  mov     r9d, 20019h; samDesired
0x18006db8c  xor     r8d, r8d; ulOptions
0x18006db8f  mov     rdx, rbx; lpSubKey
0x18006db92  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006db96  call    cs:__imp_RegOpenKeyExW
0x18006db9c  mov     ebx, eax
0x18006db9e  mov     edi, 80070000h
0x18006dba3  test    eax, eax
0x18006dba5  jle     short loc_18006DBAC
0x18006dba7  movzx   ebx, ax
0x18006dbaa  or      ebx, edi
0x18006dbac  test    ebx, ebx
0x18006dbae  jns     short loc_18006DBDE
0x18006dbb0  mov     rcx, [rbp+4Fh+hkey]; hKey
0x18006dbb4  test    rcx, rcx
0x18006dbb7  mov     [rbp+4Fh+hkey], r12
0x18006dbbb  jz      short loc_18006DBC4
0x18006dbbd  call    cs:__imp_RegCloseKey
0x18006dbc3  nop
0x18006dbc4  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006dbc8  mov     [rbp+4Fh+hKey], r12
0x18006dbcc  test    rcx, rcx
0x18006dbcf  jz      short loc_18006DBD7
0x18006dbd1  call    cs:__imp_RegCloseKey
0x18006dbd7  mov     eax, ebx
0x18006dbd9  jmp     loc_18006DDE4
0x18006dbde  mov     [rbp+4Fh+pdwType], r12d
0x18006dbe2  mov     [rbp+4Fh+var_A0], r12d
0x18006dbe6  lea     rax, [rbp+4Fh+var_A0]
0x18006dbea  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18006dbef  mov     [rsp+0E0h+pvData], r12; pvData
0x18006dbf4  lea     rax, [rbp+4Fh+pdwType]
0x18006dbf8  mov     [rsp+0E0h+phkResult], rax; pdwType
0x18006dbfd  mov     ebx, 2
0x18006dc02  mov     r9d, ebx; dwFlags
0x18006dc05  lea     r8, aEnterprisedata; "EnterpriseDataProtectionIdsToRevoke"
0x18006dc0c  xor     edx, edx; lpSubKey
0x18006dc0e  mov     rcx, [rbp+4Fh+hkey]; hkey
0x18006dc12  call    cs:__imp_RegGetValueW
0x18006dc18  xorps   xmm0, xmm0
0x18006dc1b  movdqu  xmmword ptr [rbp+4Fh+var_80], xmm0
0x18006dc20  mov     [rbp+4Fh+var_70], r12
0x18006dc24  mov     edx, [rbp+4Fh+var_A0]
0x18006dc27  test    rdx, rdx
0x18006dc2a  jz      short loc_18006DC35
0x18006dc2c  lea     rcx, [rbp+4Fh+var_80]
0x18006dc30  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006dc35  mov     rax, [rbp+4Fh+var_80]
0x18006dc39  lea     rcx, [rbp+4Fh+var_A0]
0x18006dc3d  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x18006dc42  mov     [rsp+0E0h+pvData], rax; pvData
0x18006dc47  lea     rax, [rbp+4Fh+pdwType]
0x18006dc4b  mov     [rsp+0E0h+phkResult], rax; pdwType
0x18006dc50  mov     r9d, ebx; dwFlags
0x18006dc53  lea     r8, aEnterprisedata; "EnterpriseDataProtectionIdsToRevoke"
0x18006dc5a  xor     edx, edx; lpSubKey
0x18006dc5c  mov     rcx, [rbp+4Fh+hkey]; hkey
0x18006dc60  call    cs:__imp_RegGetValueW
0x18006dc66  mov     ebx, eax
0x18006dc68  test    eax, eax
0x18006dc6a  jle     short loc_18006DC71
0x18006dc6c  movzx   ebx, ax
0x18006dc6f  or      ebx, edi
0x18006dc71  test    ebx, ebx
0x18006dc73  jns     short loc_18006DC9F
0x18006dc75  mov     rcx, [rbp+4Fh+var_80]
0x18006dc79  test    rcx, rcx
0x18006dc7c  jz      loc_18006DBB0
0x18006dc82  mov     rdx, [rbp+4Fh+var_70]
0x18006dc86  sub     rdx, rcx
0x18006dc89  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006dc8e  xorps   xmm0, xmm0
0x18006dc91  movdqu  xmmword ptr [rbp+4Fh+var_80], xmm0
0x18006dc96  mov     [rbp+4Fh+var_70], r12
0x18006dc9a  jmp     loc_18006DBB0
0x18006dc9f  xorps   xmm0, xmm0
0x18006dca2  movups  [rbp+4Fh+var_60], xmm0
0x18006dca6  xorps   xmm1, xmm1
0x18006dca9  movdqu  [rbp+4Fh+var_50], xmm1
0x18006dcae  mov     r8, [rbp+4Fh+var_80+8]
0x18006dcb2  mov     rdx, [rbp+4Fh+var_80]
0x18006dcb6  sub     r8, rdx
0x18006dcb9  shr     r8, 1
0x18006dcbc  lea     rcx, [rbp+4Fh+var_60]
0x18006dcc0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006dcc5  nop
0x18006dcc6  mov     [rbp+4Fh+var_68], r12d
0x18006dcca  mov     [rbp+4Fh+var_A0], 4
0x18006dcd1  lea     rax, [rbp+4Fh+var_A0]
0x18006dcd5  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18006dcda  lea     rax, [rbp+4Fh+var_68]
0x18006dcde  mov     [rsp+0E0h+pvData], rax; pvData
0x18006dce3  lea     rax, [rbp+4Fh+pdwType]
0x18006dce7  mov     [rsp+0E0h+phkResult], rax; pdwType
0x18006dcec  mov     r9d, 10h; dwFlags
0x18006dcf2  lea     r8, aRevokeonunenro_0; "RevokeOnUnenroll"
0x18006dcf9  xor     edx, edx; lpSubKey
0x18006dcfb  mov     rcx, [rbp+4Fh+hkey]; hkey
0x18006dcff  call    cs:__imp_RegGetValueW
0x18006dd05  mov     ebx, eax
0x18006dd07  test    eax, eax
0x18006dd09  jle     short loc_18006DD10
0x18006dd0b  movzx   ebx, ax
0x18006dd0e  or      ebx, edi
0x18006dd10  test    ebx, ebx
0x18006dd12  jns     short loc_18006DD22
0x18006dd14  lea     rcx, [rbp+4Fh+var_60]
0x18006dd18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dd1d  jmp     loc_18006DC75
0x18006dd22  mov     [rbp+4Fh+var_64], r12d
0x18006dd26  mov     [rbp+4Fh+var_A0], 4
0x18006dd2d  lea     rax, [rbp+4Fh+var_A0]
0x18006dd31  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18006dd36  lea     rax, [rbp+4Fh+var_64]
0x18006dd3a  mov     [rsp+0E0h+pvData], rax; pvData
0x18006dd3f  lea     rax, [rbp+4Fh+pdwType]
0x18006dd43  mov     [rsp+0E0h+phkResult], rax; pdwType
0x18006dd48  mov     r9d, 10h; dwFlags
0x18006dd4e  lea     r8, aRevokeonmdmhan_0; "RevokeOnMDMHandoff"
0x18006dd55  xor     edx, edx; lpSubKey
0x18006dd57  mov     rcx, [rbp+4Fh+hkey]; hkey
0x18006dd5b  call    cs:__imp_RegGetValueW
0x18006dd61  mov     ebx, eax
0x18006dd63  test    eax, eax
0x18006dd65  jle     short loc_18006DD6C
0x18006dd67  movzx   ebx, ax
0x18006dd6a  or      ebx, edi
0x18006dd6c  test    ebx, ebx
0x18006dd6e  js      short loc_18006DD14
0x18006dd70  lea     rdx, [rbp+4Fh+var_60]
0x18006dd74  mov     rcx, rsi
0x18006dd77  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006dd7c  cmp     [rbp+4Fh+var_68], r12d
0x18006dd80  setnz   al
0x18006dd83  mov     [r14], al
0x18006dd86  cmp     [rbp+4Fh+var_64], r12d
0x18006dd8a  setnz   al
0x18006dd8d  mov     [r15], al
0x18006dd90  lea     rcx, [rbp+4Fh+var_60]
0x18006dd94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dd99  nop
0x18006dd9a  mov     rcx, [rbp+4Fh+var_80]
0x18006dd9e  test    rcx, rcx
0x18006dda1  jz      short loc_18006DDBB
0x18006dda3  mov     rdx, [rbp+4Fh+var_70]
0x18006dda7  sub     rdx, rcx
0x18006ddaa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006ddaf  xorps   xmm0, xmm0
0x18006ddb2  movdqu  xmmword ptr [rbp+4Fh+var_80], xmm0
0x18006ddb7  mov     [rbp+4Fh+var_70], r12
0x18006ddbb  mov     rcx, [rbp+4Fh+hkey]; hKey
0x18006ddbf  mov     [rbp+4Fh+hkey], r12
0x18006ddc3  test    rcx, rcx
0x18006ddc6  jz      short loc_18006DDCF
0x18006ddc8  call    cs:__imp_RegCloseKey
0x18006ddce  nop
0x18006ddcf  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006ddd3  mov     [rbp+4Fh+hKey], r12
0x18006ddd7  test    rcx, rcx
0x18006ddda  jz      short loc_18006DDE2
0x18006dddc  call    cs:__imp_RegCloseKey
0x18006dde2  xor     eax, eax
0x18006dde4  mov     rcx, [rbp+4Fh+var_40]
0x18006dde8  xor     rcx, rsp; StackCookie
0x18006ddeb  call    __security_check_cookie
0x18006ddf0  add     rsp, 0B0h
0x18006ddf7  pop     r15
0x18006ddf9  pop     r14
0x18006ddfb  pop     r12
0x18006ddfd  pop     rdi
0x18006ddfe  pop     rsi
0x18006ddff  pop     rbx
0x18006de00  pop     rbp
0x18006de01  retn
```
