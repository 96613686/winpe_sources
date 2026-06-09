# IsDeviceInDeviceIDsList

- ea: `0x18000892c`
- end: `0x180008bb8`
- name: `IsDeviceInDeviceIDsList`
- size: `652`
- prototype: `__int64 __fastcall(int, int, int, int, STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008d80`

## callees

- `0x180003b40`
- `0x180003cf8`
- `0x1800040d8`
- `0x18000859c`
- `0x18000892c`
- `0x18000a1a0`
- `0x18000a230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b07`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180008afd`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180008afd`
- `KERNEL32!HeapFree` at `0x180008b8e`
- `KERNEL32!HeapFree` at `0x180008b8e`

## string_xrefs

- `0x1800089c0`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180008a1d`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180008a76`: `Software\Policies\Microsoft\Windows\DeviceInstall`

## pseudocode

```c
__int64 __fastcall IsDeviceInDeviceIDsList(
        void *a1,
        struct _SP_DEVINFO_DATA *a2,
        __int64 a3,
        int *a4,
        STRSAFE_LPWSTR pszDest)
{
  unsigned int v6; // r13d
  unsigned int v7; // esi
  int PolicyListStrings; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  int PolicyValue; // eax
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // edi
  const DEVPROPKEY *v15; // r8
  unsigned __int64 v16; // r14
  DWORD LastError; // eax
  bool v18; // zf
  const WCHAR *v19; // rcx
  STRSAFE_LPWSTR *v20; // r9
  size_t *PropertyBuffer; // [rsp+20h] [rbp-E0h]
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+50h] [rbp-B0h] BYREF
  PSP_DEVINFO_DATA DeviceInfoData; // [rsp+58h] [rbp-A8h]
  HDEVINFO DeviceInfoSet; // [rsp+60h] [rbp-A0h]
  _BYTE v28[4096]; // [rsp+70h] [rbp-90h] BYREF

  DeviceInfoData = a2;
  DeviceInfoSet = a1;
  v6 = a3;
  lpMem = 0;
  v7 = 0;
  pszSrc = 0;
  PropertyType = 0;
  if ( pszDest )
    *pszDest = 0;
  if ( (_DWORD)a3 )
  {
    if ( dword_1800117D4 && dword_1800117D0
      || (PolicyListStrings = pSetupGetPolicyListStrings(
                                (__int64)a1,
                                L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                                a3,
                                L"DenyDeviceIDs",
                                (wchar_t **)&lpMem),
          PolicyListStrings == 2) )
    {
      dword_1800117D4 = 1;
      dword_1800117D0 = 1;
      goto LABEL_34;
    }
    if ( !PolicyListStrings )
    {
      dword_1800117D4 = 1;
      if ( a4 )
      {
        if ( dword_1800117C4 )
        {
          v12 = dword_1800117C0;
        }
        else
        {
          PolicyValue = pSetupGetPolicyValue(
                          v9,
                          L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                          v10,
                          L"DenyDeviceIDsRetroactive",
                          0,
                          1u);
          dword_1800117C4 = 1;
          v12 = PolicyValue == 1;
          dword_1800117C0 = v12;
        }
        *a4 = v12;
      }
      goto LABEL_20;
    }
  }
  else
  {
    if ( dword_1800117CC && dword_1800117C8
      || (v13 = pSetupGetPolicyListStrings(
                  (__int64)a1,
                  L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                  a3,
                  L"AllowDeviceIDs",
                  (wchar_t **)&lpMem),
          v13 == 2) )
    {
      dword_1800117CC = 1;
      dword_1800117C8 = 1;
      goto LABEL_34;
    }
    if ( !v13 )
    {
      dword_1800117CC = 1;
LABEL_20:
      v14 = 0;
      while ( 1 )
      {
        v15 = &DEVPKEY_Device_HardwareIds;
        v16 = (unsigned __int64)v14 << 11;
        if ( v14 )
          v15 = &DEVPKEY_Device_CompatibleIds;
        if ( SetupDiGetDevicePropertyW(DeviceInfoSet, DeviceInfoData, v15, &PropertyType, &v28[v16], 0x800u, 0, 0) )
        {
          v18 = PropertyType == 8210;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError == 1168 )
          {
            *(_WORD *)&v28[v16] = 0;
            goto LABEL_30;
          }
          v18 = LastError == 0;
        }
        if ( !v18 )
          break;
        v19 = (const WCHAR *)lpMem;
        *(_DWORD *)&v28[2048 * (unsigned __int64)v14 + 2044] = 0;
        if ( (unsigned int)IsAnyStringInList(v19, (LPCWCH)&v28[v16], &pszSrc) )
        {
          v7 = 1;
          StringCchCopyExW(pszDest, 0xC8u, pszSrc, v20, PropertyBuffer, 0x100u);
          goto LABEL_34;
        }
LABEL_30:
        if ( ++v14 >= 2 )
          goto LABEL_34;
      }
    }
  }
  v7 = v6;
LABEL_34:
  if ( lpMem )
    HeapFree(hHeap, 0, lpMem);
  return v7;
}

```

## disassembly

```asm
0x18000892c  push    rbp
0x18000892e  push    rsi
0x18000892f  push    rdi
0x180008930  push    r12
0x180008932  push    r13
0x180008934  push    r14
0x180008936  push    r15
0x180008938  lea     rbp, [rsp-0F80h]
0x180008940  mov     eax, 1080h
0x180008945  call    _alloca_probe
0x18000894a  sub     rsp, rax
0x18000894d  mov     rax, cs:__security_cookie
0x180008954  xor     rax, rsp
0x180008957  mov     [rbp+0FB0h+var_40], rax
0x18000895e  mov     r12, [rbp+0FB0h+pszDest]
0x180008965  xor     r14d, r14d
0x180008968  mov     [rsp+10B0h+DeviceInfoData], rdx
0x18000896d  mov     rdi, r9
0x180008970  mov     [rsp+10B0h+DeviceInfoSet], rcx
0x180008975  mov     r13d, r8d
0x180008978  mov     [rsp+10B0h+lpMem], r14
0x18000897d  mov     esi, r14d
0x180008980  mov     [rsp+10B0h+pszSrc], r14
0x180008985  mov     [rsp+10B0h+PropertyType], r14d
0x18000898a  test    r12, r12
0x18000898d  jz      short loc_180008994
0x18000898f  mov     [r12], r14w
0x180008994  test    r13d, r13d
0x180008997  jz      loc_180008A53
0x18000899d  cmp     cs:dword_1800117D4, r14d
0x1800089a4  jz      short loc_1800089AF
0x1800089a6  cmp     cs:dword_1800117D0, r14d
0x1800089ad  jnz     short loc_1800089D1
0x1800089af  lea     rax, [rsp+10B0h+lpMem]
0x1800089b4  lea     r9, aDenydeviceids; "DenyDeviceIDs"
0x1800089bb  mov     [rsp+10B0h+PropertyBuffer], rax
0x1800089c0  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800089c7  call    pSetupGetPolicyListStrings
0x1800089cc  cmp     eax, 2
0x1800089cf  jnz     short loc_1800089EA
0x1800089d1  mov     cs:dword_1800117D4, 1
0x1800089db  mov     cs:dword_1800117D0, 1
0x1800089e5  jmp     loc_180008B7B
0x1800089ea  test    eax, eax
0x1800089ec  jnz     loc_180008B78
0x1800089f2  mov     cs:dword_1800117D4, 1
0x1800089fc  test    rdi, rdi
0x1800089ff  jz      loc_180008AB2
0x180008a05  cmp     cs:dword_1800117C4, r14d
0x180008a0c  jnz     short loc_180008A49
0x180008a0e  mov     [rsp+10B0h+PropertyBufferSize], 1
0x180008a16  lea     r9, aDenydeviceidsr; "DenyDeviceIDsRetroactive"
0x180008a1d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008a24  mov     dword ptr [rsp+10B0h+PropertyBuffer], r14d
0x180008a29  call    pSetupGetPolicyValue
0x180008a2e  mov     ecx, r14d
0x180008a31  mov     cs:dword_1800117C4, 1
0x180008a3b  cmp     eax, 1
0x180008a3e  setz    cl
0x180008a41  mov     cs:dword_1800117C0, ecx
0x180008a47  jmp     short loc_180008A4F
0x180008a49  mov     ecx, cs:dword_1800117C0
0x180008a4f  mov     [rdi], ecx
0x180008a51  jmp     short loc_180008AB2
0x180008a53  cmp     cs:dword_1800117CC, r14d
0x180008a5a  jz      short loc_180008A65
0x180008a5c  cmp     cs:dword_1800117C8, r14d
0x180008a63  jnz     short loc_180008A87
0x180008a65  lea     rax, [rsp+10B0h+lpMem]
0x180008a6a  lea     r9, aAllowdeviceids; "AllowDeviceIDs"
0x180008a71  mov     [rsp+10B0h+PropertyBuffer], rax
0x180008a76  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008a7d  call    pSetupGetPolicyListStrings
0x180008a82  cmp     eax, 2
0x180008a85  jnz     short loc_180008AA0
0x180008a87  mov     cs:dword_1800117CC, 1
0x180008a91  mov     cs:dword_1800117C8, 1
0x180008a9b  jmp     loc_180008B7B
0x180008aa0  test    eax, eax
0x180008aa2  jnz     loc_180008B78
0x180008aa8  mov     cs:dword_1800117CC, 1
0x180008ab2  mov     edi, r14d
0x180008ab5  mov     rdx, [rsp+10B0h+DeviceInfoData]; DeviceInfoData
0x180008aba  lea     rax, DEVPKEY_Device_CompatibleIds
0x180008ac1  mov     rcx, [rsp+10B0h+DeviceInfoSet]; DeviceInfoSet
0x180008ac6  lea     r15, [rsp+10B0h+var_1040]
0x180008acb  mov     [rsp+10B0h+Flags], esi; Flags
0x180008acf  lea     r8, DEVPKEY_Device_HardwareIds
0x180008ad6  mov     [rsp+10B0h+RequiredSize], rsi; RequiredSize
0x180008adb  lea     r9, [rsp+10B0h+PropertyType]; PropertyType
0x180008ae0  mov     r14d, edi
0x180008ae3  shl     r14, 0Bh
0x180008ae7  add     r15, r14
0x180008aea  mov     [rsp+10B0h+PropertyBufferSize], 800h; PropertyBufferSize
0x180008af2  test    edi, edi
0x180008af4  mov     [rsp+10B0h+PropertyBuffer], r15; pcchRemaining
0x180008af9  cmovnz  r8, rax; PropertyKey
0x180008afd  call    cs:__imp_SetupDiGetDevicePropertyW
0x180008b03  test    eax, eax
0x180008b05  jnz     short loc_180008B20
0x180008b07  call    cs:__imp_GetLastError
0x180008b0d  cmp     eax, 490h
0x180008b12  jnz     short loc_180008B1C
0x180008b14  xor     eax, eax
0x180008b16  mov     [r15], ax
0x180008b1a  jmp     short loc_180008B4A
0x180008b1c  test    eax, eax
0x180008b1e  jmp     short loc_180008B28
0x180008b20  cmp     [rsp+10B0h+PropertyType], 2012h
0x180008b28  jnz     short loc_180008B78
0x180008b2a  mov     rcx, [rsp+10B0h+lpMem]; lpString1
0x180008b2f  lea     r8, [rsp+10B0h+pszSrc]
0x180008b34  xor     eax, eax
0x180008b36  mov     rdx, r15; lpString2
0x180008b39  mov     [rbp+r14+0FB0h+var_844], eax
0x180008b41  call    IsAnyStringInList
0x180008b46  test    eax, eax
0x180008b48  jnz     short loc_180008B57
0x180008b4a  inc     edi
0x180008b4c  cmp     edi, 2
0x180008b4f  jb      loc_180008AB5
0x180008b55  jmp     short loc_180008B7B
0x180008b57  mov     r8, [rsp+10B0h+pszSrc]; pszSrc
0x180008b5c  mov     edx, 0C8h; cchDest
0x180008b61  mov     rcx, r12; pszDest
0x180008b64  mov     [rsp+10B0h+PropertyBufferSize], 100h; dwFlags
0x180008b6c  mov     esi, 1
0x180008b71  call    StringCchCopyExW
0x180008b76  jmp     short loc_180008B7B
0x180008b78  mov     esi, r13d
0x180008b7b  mov     r8, [rsp+10B0h+lpMem]; lpMem
0x180008b80  test    r8, r8
0x180008b83  jz      short loc_180008B94
0x180008b85  mov     rcx, cs:hHeap; hHeap
0x180008b8c  xor     edx, edx; dwFlags
0x180008b8e  call    cs:__imp_HeapFree
0x180008b94  mov     eax, esi
0x180008b96  mov     rcx, [rbp+0FB0h+var_40]
0x180008b9d  xor     rcx, rsp; StackCookie
0x180008ba0  call    __security_check_cookie
0x180008ba5  add     rsp, 1080h
0x180008bac  pop     r15
0x180008bae  pop     r14
0x180008bb0  pop     r13
0x180008bb2  pop     r12
0x180008bb4  pop     rdi
0x180008bb5  pop     rsi
0x180008bb6  pop     rbp
0x180008bb7  retn
```
