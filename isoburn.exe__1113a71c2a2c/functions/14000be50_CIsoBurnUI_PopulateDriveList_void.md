# CIsoBurnUI::_PopulateDriveList(void)

- ea: `0x14000be50`
- end: `0x14000c139`
- name: `?_PopulateDriveList@CIsoBurnUI@@AEAAJXZ`
- size: `745`
- prototype: `__int64 __fastcall(CIsoBurnUI *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000ad38`

## callees

- `0x140001fa0`
- `0x14000469c`
- `0x14000b8c0`
- `0x14000b960`
- `0x14000baa0`
- `0x14000be50`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000c0cd`
- `ADVAPI32!RegCloseKey` at `0x14000c0cd`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bec0`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bec0`
- `ADVAPI32!RegEnumKeyW` at `0x14000beec`
- `ADVAPI32!RegEnumKeyW` at `0x14000beec`
- `KERNEL32!CompareStringOrdinal` at `0x14000c0a8`
- `KERNEL32!CompareStringOrdinal` at `0x14000c0a8`
- `USER32!SendDlgItemMessageW` at `0x14000c00f`
- `USER32!SendDlgItemMessageW` at `0x14000c082`
- `USER32!SendDlgItemMessageW` at `0x14000c0ff`
- `USER32!SendDlgItemMessageW` at `0x14000c00f`
- `USER32!SendDlgItemMessageW` at `0x14000c082`
- `USER32!SendDlgItemMessageW` at `0x14000c0ff`
- `SHLWAPI!SHRegGetValueW` at `0x14000bf39`
- `SHLWAPI!SHRegGetValueW` at `0x14000bfbd`
- `SHLWAPI!SHRegGetValueW` at `0x14000bf39`
- `SHLWAPI!SHRegGetValueW` at `0x14000bfbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c067`
- `COMCTL32!__imp_DPA_Create` at `0x14000be92`
- `COMCTL32!__imp_DPA_Create` at `0x14000be92`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x14000c04d`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x14000c04d`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::_PopulateDriveList(CIsoBurnUI *this)
{
  unsigned int v2; // r15d
  int v3; // edi
  DWORD v4; // r14d
  unsigned int v5; // r8d
  unsigned int v6; // r9d
  WPARAM v7; // rsi
  const WCHAR *v8; // rcx
  int *v9; // rax
  unsigned __int16 v11[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *p; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 lParam[264]; // [rsp+480h] [rbp+380h] BYREF

  hKey = 0;
  *((_QWORD *)this + 19) = DPA_Create(8);
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CD Burning\\Drives",
         0,
         0x20019u,
         &hKey) )
  {
    return 2147500037LL;
  }
  v2 = 0;
  v3 = 0;
  v4 = 0;
  while ( !RegEnumKeyW(hKey, v4, Name, 0x104u) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !SHRegGetValueW(hKey, Name, L"IsImapiDataBurnSupported", 24, 0, &pvData, &pcbData) )
    {
      if ( pvData )
      {
        String2[0] = 0;
        CIsoBurnUI::_ConstructVolumeNameFromKey(Name, String2, v5);
        v11[0] = 0;
        CIsoBurnUI::_GetDriveLetterForVolumeName(String2, v11);
        v14 = 0;
        pcbData = 4;
        SHRegGetValueW(hKey, Name, L"Drive Type", 24, 0, &v14, &pcbData);
        CIsoBurnUI::_GetDriveDisplayName(v14, v11[0], lParam, v6);
        if ( lParam[0] )
        {
          if ( *((_QWORD *)this + 19) )
          {
            v7 = SendDlgItemMessageW(*((HWND *)this + 1), 201, 0x143u, 0, (LPARAM)lParam);
            if ( v7 == -1 )
            {
              v3 = -2147467259;
              break;
            }
            p = 0;
            v3 = CoAllocString(String2, (unsigned __int16 **)&p);
            if ( v3 >= 0 )
            {
              if ( DPA_InsertPtr(*((HDPA *)this + 19), 0x7FFFFFFF, p) == -1 )
              {
                v3 = -2147024882;
                CoTaskMemFree(p);
                SendDlgItemMessageW(*((HWND *)this + 1), 201, 0x144u, v7, 0);
              }
              else
              {
                v3 = 0;
              }
            }
            v8 = (const WCHAR *)*((_QWORD *)this + 18);
            if ( v8 && CompareStringOrdinal(v8, -1, String2, -1, 1) == 2 )
              v2 = v7;
          }
        }
      }
    }
    ++v4;
    if ( v3 < 0 )
      break;
  }
  RegCloseKey(hKey);
  if ( v3 < 0 )
    return 2147500037LL;
  v9 = (int *)*((_QWORD *)this + 19);
  if ( !v9 || *v9 <= 0 )
    return 2147500037LL;
  SendDlgItemMessageW(*((HWND *)this + 1), 201, 0x14Eu, v2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000be50  mov     [rsp-8+arg_8], rbx
0x14000be55  mov     [rsp-8+arg_10], rsi
0x14000be5a  push    rbp
0x14000be5b  push    rdi
0x14000be5c  push    r12
0x14000be5e  push    r14
0x14000be60  push    r15
0x14000be62  lea     rbp, [rsp-5A0h]
0x14000be6a  sub     rsp, 6A0h
0x14000be71  mov     rax, cs:__security_cookie
0x14000be78  xor     rax, rsp
0x14000be7b  mov     [rbp+5C0h+var_30], rax
0x14000be82  xor     r12d, r12d
0x14000be85  mov     rbx, rcx
0x14000be88  mov     [rsp+6C0h+hKey], r12
0x14000be8d  lea     ecx, [r12+8]; cItemGrow
0x14000be92  call    cs:__imp_DPA_Create
0x14000be98  mov     [rbx+98h], rax
0x14000be9f  mov     r9d, 20019h; samDesired
0x14000bea5  xor     r8d, r8d; ulOptions
0x14000bea8  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000beaf  lea     rax, [rsp+6C0h+hKey]
0x14000beb4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000bebb  mov     [rsp+6C0h+phkResult], rax; phkResult
0x14000bec0  call    cs:__imp_RegOpenKeyExW
0x14000bec6  test    eax, eax
0x14000bec8  jnz     loc_14000C109
0x14000bece  mov     r15d, r12d
0x14000bed1  mov     edi, r12d
0x14000bed4  mov     r14d, r12d
0x14000bed7  mov     rcx, [rsp+6C0h+hKey]; hKey
0x14000bedc  lea     r8, [rbp+5C0h+Name]; lpName
0x14000bee3  mov     r9d, 104h; cchName
0x14000bee9  mov     edx, r14d; dwIndex
0x14000beec  call    cs:__imp_RegEnumKeyW
0x14000bef2  test    eax, eax
0x14000bef4  jnz     loc_14000C0C8
0x14000befa  mov     rcx, [rsp+6C0h+hKey]; hkey
0x14000beff  lea     rax, [rsp+6C0h+var_67C]
0x14000bf04  mov     [rsp+6C0h+pcbData], rax; pcbData
0x14000bf09  lea     r8, aIsimapidatabur; "IsImapiDataBurnSupported"
0x14000bf10  lea     rax, [rsp+6C0h+var_678]
0x14000bf15  mov     [rsp+6C0h+var_678], r12d
0x14000bf1a  mov     [rsp+6C0h+pvData], rax; pvData
0x14000bf1f  lea     rdx, [rbp+5C0h+Name]; pszSubKey
0x14000bf26  mov     r9d, 18h; srrfFlags
0x14000bf2c  mov     [rsp+6C0h+phkResult], r12; pdwType
0x14000bf31  mov     [rsp+6C0h+var_67C], 4
0x14000bf39  call    cs:__imp_SHRegGetValueW
0x14000bf3f  test    eax, eax
0x14000bf41  jnz     loc_14000C0B6
0x14000bf47  cmp     [rsp+6C0h+var_678], r12d
0x14000bf4c  jz      loc_14000C0B6
0x14000bf52  lea     rdx, [rsp+6C0h+String2]; unsigned __int16 *
0x14000bf57  mov     [rsp+6C0h+String2], r12w
0x14000bf5d  lea     rcx, [rbp+5C0h+Name]; unsigned __int16 *
0x14000bf64  call    ?_ConstructVolumeNameFromKey@CIsoBurnUI@@CAJPEBGPEAGI@Z; CIsoBurnUI::_ConstructVolumeNameFromKey(ushort const *,ushort *,uint)
0x14000bf69  lea     rdx, [rsp+6C0h+var_680]; unsigned __int16 *
0x14000bf6e  mov     [rsp+6C0h+var_680], r12w
0x14000bf74  lea     rcx, [rsp+6C0h+String2]; lpszVolumeName
0x14000bf79  call    ?_GetDriveLetterForVolumeName@CIsoBurnUI@@CAJPEBGPEAG@Z; CIsoBurnUI::_GetDriveLetterForVolumeName(ushort const *,ushort *)
0x14000bf7e  mov     rcx, [rsp+6C0h+hKey]; hkey
0x14000bf83  lea     rax, [rsp+6C0h+var_67C]
0x14000bf88  mov     [rsp+6C0h+pcbData], rax; pcbData
0x14000bf8d  lea     r8, aDriveType; "Drive Type"
0x14000bf94  lea     rax, [rsp+6C0h+var_674]
0x14000bf99  mov     [rsp+6C0h+var_674], r12d
0x14000bf9e  mov     [rsp+6C0h+pvData], rax; pvData
0x14000bfa3  lea     rdx, [rbp+5C0h+Name]; pszSubKey
0x14000bfaa  mov     r9d, 18h; srrfFlags
0x14000bfb0  mov     [rsp+6C0h+phkResult], r12; pdwType
0x14000bfb5  mov     [rsp+6C0h+var_67C], 4
0x14000bfbd  call    cs:__imp_SHRegGetValueW
0x14000bfc3  movzx   edx, [rsp+6C0h+var_680]; unsigned __int16
0x14000bfc8  lea     r8, [rbp+5C0h+lParam]; unsigned __int16 *
0x14000bfcf  mov     ecx, [rsp+6C0h+var_674]; unsigned int
0x14000bfd3  call    ?_GetDriveDisplayName@CIsoBurnUI@@CAJKGPEAGI@Z; CIsoBurnUI::_GetDriveDisplayName(ulong,ushort,ushort *,uint)
0x14000bfd8  cmp     [rbp+5C0h+lParam], r12w
0x14000bfe0  jz      loc_14000C0B6
0x14000bfe6  cmp     [rbx+98h], r12
0x14000bfed  jz      loc_14000C0B6
0x14000bff3  mov     rcx, [rbx+8]; hDlg
0x14000bff7  lea     rax, [rbp+5C0h+lParam]
0x14000bffe  mov     edx, 0C9h; nIDDlgItem
0x14000c003  mov     [rsp+6C0h+phkResult], rax; lParam
0x14000c008  xor     r9d, r9d; wParam
0x14000c00b  lea     r8d, [rdx+7Ah]; Msg
0x14000c00f  call    cs:__imp_SendDlgItemMessageW
0x14000c015  mov     rsi, rax
0x14000c018  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c01c  jz      loc_14000C0C3
0x14000c022  lea     rdx, [rsp+6C0h+p]; unsigned __int16 **
0x14000c027  mov     [rsp+6C0h+p], r12
0x14000c02c  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x14000c031  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x14000c036  mov     edi, eax
0x14000c038  test    eax, eax
0x14000c03a  js      short loc_14000C088
0x14000c03c  mov     r8, [rsp+6C0h+p]; p
0x14000c041  mov     edx, 7FFFFFFFh; i
0x14000c046  mov     rcx, [rbx+98h]; hdpa
0x14000c04d  call    cs:__imp_DPA_InsertPtr
0x14000c053  cmp     eax, 0FFFFFFFFh
0x14000c056  jz      short loc_14000C05D
0x14000c058  mov     edi, r12d
0x14000c05b  jmp     short loc_14000C088
0x14000c05d  mov     rcx, [rsp+6C0h+p]; pv
0x14000c062  mov     edi, 8007000Eh
0x14000c067  call    cs:__imp_CoTaskMemFree
0x14000c06d  mov     rcx, [rbx+8]; hDlg
0x14000c071  mov     edx, 0C9h; nIDDlgItem
0x14000c076  mov     r9, rsi; wParam
0x14000c079  mov     [rsp+6C0h+phkResult], r12; lParam
0x14000c07e  lea     r8d, [rdx+7Bh]; Msg
0x14000c082  call    cs:__imp_SendDlgItemMessageW
0x14000c088  mov     rcx, [rbx+90h]; lpString1
0x14000c08f  test    rcx, rcx
0x14000c092  jz      short loc_14000C0B6
0x14000c094  or      r9d, 0FFFFFFFFh; cchCount2
0x14000c098  mov     dword ptr [rsp+6C0h+phkResult], 1; bIgnoreCase
0x14000c0a0  or      edx, r9d; cchCount1
0x14000c0a3  lea     r8, [rsp+6C0h+String2]; lpString2
0x14000c0a8  call    cs:__imp_CompareStringOrdinal
0x14000c0ae  cmp     eax, 2
0x14000c0b1  jnz     short loc_14000C0B6
0x14000c0b3  mov     r15d, esi
0x14000c0b6  inc     r14d
0x14000c0b9  test    edi, edi
0x14000c0bb  jns     loc_14000BED7
0x14000c0c1  jmp     short loc_14000C0C8
0x14000c0c3  mov     edi, 80004005h
0x14000c0c8  mov     rcx, [rsp+6C0h+hKey]; hKey
0x14000c0cd  call    cs:__imp_RegCloseKey
0x14000c0d3  test    edi, edi
0x14000c0d5  js      short loc_14000C109
0x14000c0d7  mov     rax, [rbx+98h]
0x14000c0de  test    rax, rax
0x14000c0e1  jz      short loc_14000C109
0x14000c0e3  cmp     [rax], r12d
0x14000c0e6  jle     short loc_14000C109
0x14000c0e8  mov     rcx, [rbx+8]; hDlg
0x14000c0ec  mov     edx, 0C9h; nIDDlgItem
0x14000c0f1  mov     r9d, r15d; wParam
0x14000c0f4  mov     r8d, 14Eh; Msg
0x14000c0fa  mov     [rsp+6C0h+phkResult], r12; lParam
0x14000c0ff  call    cs:__imp_SendDlgItemMessageW
0x14000c105  xor     eax, eax
0x14000c107  jmp     short loc_14000C10E
0x14000c109  mov     eax, 80004005h
0x14000c10e  mov     rcx, [rbp+5C0h+var_30]
0x14000c115  xor     rcx, rsp; StackCookie
0x14000c118  call    __security_check_cookie
0x14000c11d  lea     r11, [rsp+6C0h+var_20]
0x14000c125  mov     rbx, [r11+38h]
0x14000c129  mov     rsi, [r11+40h]
0x14000c12d  mov     rsp, r11
0x14000c130  pop     r15
0x14000c132  pop     r14
0x14000c134  pop     r12
0x14000c136  pop     rdi
0x14000c137  pop     rbp
0x14000c138  retn
```
