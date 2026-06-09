# CCertTypeInfo::_UpdateDSCache(ulong,CCertTypeInfo *)

- ea: `0x1800056f0`
- end: `0x1800058e4`
- name: `?_UpdateDSCache@CCertTypeInfo@@KAJKPEAV1@@Z`
- size: `500`
- prototype: `__int64 __fastcall(char, struct CCertTypeInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a630`
- `0x18000a920`

## callees

- `0x180003be0`
- `0x1800056f0`
- `0x180005d90`
- `0x180008400`
- `0x180008610`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005807`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000588c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005807`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000588c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005838`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800058b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800058ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005838`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800058b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800058ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180005734`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180005734`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000578e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000578e`

## string_xrefs

- `0x18000576e`: `Software\Microsoft\Cryptography\CertificateTemplateCache`
- `0x18000579d`: `Software\Microsoft\Cryptography\CertificateTemplateCache`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_UpdateDSCache(char a1, struct CCertTypeInfo *a2)
{
  HKEY v3; // rcx
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  bool v8; // cc
  HKEY v9; // rcx
  DWORD dwDisposition; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  dwDisposition = 0;
  SystemTimeAsFileTime = 0;
  phkResult = 0;
  if ( (a1 & 0x20) != 0 )
  {
    v3 = HKEY_LOCAL_MACHINE;
  }
  else
  {
    v4 = RegOpenCurrentUser(0xF003Fu, &phkResult);
    v5 = v4;
    if ( v4 )
    {
      CSPrintErrorLineFile(0x13F0328u, v4);
      goto LABEL_8;
    }
    v3 = phkResult;
  }
  v6 = RegCreateKeyExW(
         v3,
         L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache",
         0,
         (LPWSTR)&Class,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  v5 = v6;
  if ( v6 )
    CSPrintErrorLineFileData2(L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache", 0x14E0328u, v6, 0);
LABEL_8:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
  {
    if ( v5 <= 0 )
      goto LABEL_24;
    v5 = (unsigned __int16)v5;
    goto LABEL_13;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v7 = RegSetValueExW(hKey, L"TimestampAfter", 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
  v5 = v7;
  v8 = v7 <= 0;
  if ( v7 )
    goto LABEL_15;
  v5 = _DeleteAllKey(hKey);
  if ( !v5 )
  {
    RegDeleteValueW(hKey, L"Timestamp");
    while ( a2 )
    {
      if ( *((_DWORD *)a2 + 42) == 1 )
      {
        v5 = CCertTypeInfo::_BaseUpdateToReg(a2, hKey);
        if ( v5 )
          goto LABEL_24;
      }
      a2 = (struct CCertTypeInfo *)*((_QWORD *)a2 + 19);
    }
    v7 = RegSetValueExW(hKey, L"Timestamp", 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
    v5 = v7;
    v8 = v7 <= 0;
    if ( v7 )
    {
LABEL_15:
      if ( !v8 )
      {
        v5 = (unsigned __int16)v7;
LABEL_13:
        v5 |= 0x80070000;
      }
    }
  }
LABEL_24:
  v9 = hKey;
  if ( hKey )
  {
    if ( v5 )
    {
      RegDeleteValueW(hKey, L"TimestampAfter");
      _DeleteAllKey(hKey);
      RegDeleteValueW(hKey, L"Timestamp");
      v9 = hKey;
    }
    RegCloseKey(v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800056f0  push    rbp
0x1800056f2  push    rbx
0x1800056f3  push    rdi
0x1800056f4  mov     rbp, rsp
0x1800056f7  sub     rsp, 50h
0x1800056fb  mov     [rbp+hKey], 0
0x180005703  mov     rdi, rdx
0x180005706  mov     [rbp+dwDisposition], 0
0x18000570d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005715  mov     [rbp+phkResult], 0
0x18000571d  test    cl, 20h
0x180005720  jz      short loc_18000572B
0x180005722  mov     rcx, 0FFFFFFFF80000002h
0x180005729  jmp     short loc_180005752
0x18000572b  lea     rdx, [rbp+phkResult]; phkResult
0x18000572f  mov     ecx, 0F003Fh; samDesired
0x180005734  call    cs:__imp_RegOpenCurrentUser
0x18000573a  mov     ebx, eax
0x18000573c  test    eax, eax
0x18000573e  jz      short loc_18000574E
0x180005740  mov     edx, eax; int
0x180005742  mov     ecx, 13F0328h; unsigned int
0x180005747  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000574c  jmp     short loc_1800057B1
0x18000574e  mov     rcx, [rbp+phkResult]; hKey
0x180005752  lea     rax, [rbp+dwDisposition]
0x180005756  xor     r8d, r8d; Reserved
0x180005759  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18000575e  lea     r9, Class; lpClass
0x180005765  lea     rax, [rbp+hKey]
0x180005769  mov     [rsp+50h+var_18], rax; phkResult
0x18000576e  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x180005775  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000577e  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180005786  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18000578e  call    cs:__imp_RegCreateKeyExW
0x180005794  mov     ebx, eax
0x180005796  test    eax, eax
0x180005798  jz      short loc_1800057B1
0x18000579a  xor     r9d, r9d; int
0x18000579d  lea     rcx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x1800057a4  mov     r8d, eax; int
0x1800057a7  mov     edx, 14E0328h; unsigned int
0x1800057ac  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800057b1  mov     rcx, [rbp+phkResult]; hKey
0x1800057b5  test    rcx, rcx
0x1800057b8  jz      short loc_1800057C0
0x1800057ba  call    cs:__imp_RegCloseKey
0x1800057c0  test    ebx, ebx
0x1800057c2  jz      short loc_1800057D8
0x1800057c4  jle     loc_18000589C
0x1800057ca  movzx   ebx, bx
0x1800057cd  or      ebx, 80070000h
0x1800057d3  jmp     loc_18000589C
0x1800057d8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800057dc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800057e2  mov     rcx, [rbp+hKey]; hKey
0x1800057e6  lea     rax, [rbp+SystemTimeAsFileTime]
0x1800057ea  mov     [rsp+50h+samDesired], 8; cbData
0x1800057f2  lea     rdx, aTimestampafter; "TimestampAfter"
0x1800057f9  mov     r9d, 3; dwType
0x1800057ff  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180005804  xor     r8d, r8d; Reserved
0x180005807  call    cs:__imp_RegSetValueExW
0x18000580d  mov     ebx, eax
0x18000580f  test    eax, eax
0x180005811  jz      short loc_18000581E
0x180005813  jle     loc_18000589C
0x180005819  movzx   ebx, ax
0x18000581c  jmp     short loc_1800057CD
0x18000581e  mov     rcx, [rbp+hKey]; hKey
0x180005822  call    ?_DeleteAllKey@@YAJPEAUHKEY__@@@Z; _DeleteAllKey(HKEY__ *)
0x180005827  mov     ebx, eax
0x180005829  test    eax, eax
0x18000582b  jnz     short loc_18000589C
0x18000582d  mov     rcx, [rbp+hKey]; hKey
0x180005831  lea     rdx, aTimestamp; "Timestamp"
0x180005838  call    cs:__imp_RegDeleteValueW
0x18000583e  test    rdi, rdi
0x180005841  jz      short loc_180005867
0x180005843  cmp     dword ptr [rdi+0A8h], 1
0x18000584a  jnz     short loc_18000585E
0x18000584c  mov     rdx, [rbp+hKey]; hKey
0x180005850  mov     rcx, rdi; this
0x180005853  call    ?_BaseUpdateToReg@CCertTypeInfo@@IEAAJPEAUHKEY__@@@Z; CCertTypeInfo::_BaseUpdateToReg(HKEY__ *)
0x180005858  mov     ebx, eax
0x18000585a  test    eax, eax
0x18000585c  jnz     short loc_18000589C
0x18000585e  mov     rdi, [rdi+98h]
0x180005865  jmp     short loc_18000583E
0x180005867  mov     rcx, [rbp+hKey]; hKey
0x18000586b  lea     rax, [rbp+SystemTimeAsFileTime]
0x18000586f  mov     [rsp+50h+samDesired], 8; cbData
0x180005877  lea     rdx, aTimestamp; "Timestamp"
0x18000587e  mov     r9d, 3; dwType
0x180005884  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180005889  xor     r8d, r8d; Reserved
0x18000588c  call    cs:__imp_RegSetValueExW
0x180005892  mov     ebx, eax
0x180005894  test    eax, eax
0x180005896  jnz     loc_180005813
0x18000589c  mov     rcx, [rbp+hKey]; hKey
0x1800058a0  test    rcx, rcx
0x1800058a3  jz      short loc_1800058DA
0x1800058a5  test    ebx, ebx
0x1800058a7  jz      short loc_1800058D4
0x1800058a9  lea     rdx, aTimestampafter; "TimestampAfter"
0x1800058b0  call    cs:__imp_RegDeleteValueW
0x1800058b6  mov     rcx, [rbp+hKey]; hKey
0x1800058ba  call    ?_DeleteAllKey@@YAJPEAUHKEY__@@@Z; _DeleteAllKey(HKEY__ *)
0x1800058bf  mov     rcx, [rbp+hKey]; hKey
0x1800058c3  lea     rdx, aTimestamp; "Timestamp"
0x1800058ca  call    cs:__imp_RegDeleteValueW
0x1800058d0  mov     rcx, [rbp+hKey]; hKey
0x1800058d4  call    cs:__imp_RegCloseKey
0x1800058da  mov     eax, ebx
0x1800058dc  add     rsp, 50h
0x1800058e0  pop     rdi
0x1800058e1  pop     rbx
0x1800058e2  pop     rbp
0x1800058e3  retn
```
