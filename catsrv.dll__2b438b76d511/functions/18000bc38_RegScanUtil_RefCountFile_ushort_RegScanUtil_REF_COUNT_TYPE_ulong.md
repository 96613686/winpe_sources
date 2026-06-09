# RegScanUtil::RefCountFile(ushort *,RegScanUtil::REF_COUNT_TYPE,ulong)

- ea: `0x18000bc38`
- end: `0x18000be20`
- name: `?RefCountFile@RegScanUtil@@CAJPEAGW4REF_COUNT_TYPE@1@K@Z`
- size: `488`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018958`

## callees

- `0x180009098`
- `0x18000bc38`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bd2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bd2b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bdd7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bdd7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bdb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bdb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bdf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bdf3`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18000bc8b`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18000bcc8`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18000bc8b`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18000bcc8`

## string_xrefs

- `0x18000bcfe`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`
- `0x18000bd59`: `hkeySharedDlls`
- `0x18000bd6c`: `com\complus\src\comcat\regscan\regscanutil.cpp`

## pseudocode

```c
__int64 __fastcall RegScanUtil::RefCountFile(const WCHAR *a1)
{
  WCHAR *v2; // rdi
  DWORD LongPathNameW; // eax
  DWORD v4; // r8d
  unsigned __int64 v5; // rdx
  __int64 v6; // rax
  void *v7; // rsp
  signed int LastError; // eax
  bool v9; // zf
  LSTATUS v10; // eax
  bool v11; // zf
  HKEY v12; // rcx
  WCHAR szLongPath[2]; // [rsp+50h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp+4h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+10h] BYREF
  int v18; // [rsp+68h] [rbp+18h] BYREF
  __int16 v19; // [rsp+6Ch] [rbp+1Ch]
  int v20; // [rsp+70h] [rbp+20h]
  const unsigned __int16 *v21; // [rsp+78h] [rbp+28h]
  __int64 v22; // [rsp+80h] [rbp+30h]
  __int64 v23; // [rsp+88h] [rbp+38h]
  int v24; // [rsp+90h] [rbp+40h]
  int v25; // [rsp+94h] [rbp+44h]

  hKey = 0;
  cbData = 4;
  *(_DWORD *)szLongPath = 0;
  Type = 0;
  if ( a1 )
  {
    v2 = 0;
    LongPathNameW = GetLongPathNameW(a1, 0, 0);
    v4 = LongPathNameW;
    if ( LongPathNameW )
    {
      v5 = 2LL * (LongPathNameW + 1);
      v6 = v5 + 15;
      if ( v5 + 15 < v5 )
        v6 = 0xFFFFFFFFFFFFFF0LL;
      v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
      v2 = szLongPath;
      if ( GetLongPathNameW(a1, szLongPath, v4) )
        goto LABEL_9;
    }
    LastError = GetLastError();
    v9 = LastError == 0;
    if ( LastError > 0 )
      v9 = 0;
    if ( v9 )
    {
LABEL_9:
      v10 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls",
              0,
              0,
              0,
              0x2001Bu,
              0,
              &hKey,
              0);
      v11 = v10 == 0;
      if ( v10 > 0 )
        v11 = 0;
      if ( v11 )
      {
        v12 = hKey;
        if ( !hKey )
        {
          v18 = 0;
          v22 = 0;
          v23 = 0;
          v19 = 21;
          v20 = -1073605930;
          v21 = L"hkeySharedDlls";
          v25 = 1;
          v24 = 1;
          CError::WriteToLog(
            (CError *)&v18,
            L"com\\complus\\src\\comcat\\regscan\\regscanutil.cpp",
            0x8Cu,
            L"hkeySharedDlls");
          v12 = hKey;
        }
        if ( (RegQueryValueExW(v12, v2, 0, &Type, (LPBYTE)szLongPath, &cbData) & 0xFFFFFFFD) == 0 )
        {
          v9 = (*(_DWORD *)szLongPath)++ == -1;
          Type = 4;
          cbData = 4;
          if ( v9 )
            RegDeleteValueW(hKey, v2);
          else
            RegSetValueExW(hKey, v2, 0, 4u, (const BYTE *)szLongPath, 4u);
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bc38  push    rbp
0x18000bc3a  push    rbx
0x18000bc3b  push    rdi
0x18000bc3c  push    r14
0x18000bc3e  sub     rsp, 0A8h
0x18000bc45  lea     rbp, [rsp+50h]
0x18000bc4a  mov     rax, cs:__security_cookie
0x18000bc51  xor     rax, rbp
0x18000bc54  mov     [rbp+70h+var_28], rax
0x18000bc58  mov     [rbp+70h+hKey], 0
0x18000bc60  mov     r14d, 4
0x18000bc66  mov     [rbp+70h+cbData], r14d
0x18000bc6a  mov     rbx, rcx
0x18000bc6d  mov     dword ptr [rbp+70h+szLongPath], 0
0x18000bc74  mov     [rbp+70h+Type], 0
0x18000bc7b  test    rcx, rcx
0x18000bc7e  jz      loc_18000BE08
0x18000bc84  xor     edi, edi
0x18000bc86  xor     r8d, r8d; cchBuffer
0x18000bc89  xor     edx, edx; lpszLongPath
0x18000bc8b  call    cs:__imp_GetLongPathNameW
0x18000bc91  mov     r8d, eax
0x18000bc94  test    eax, eax
0x18000bc96  jz      short loc_18000BCD2
0x18000bc98  lea     edx, [rax+1]
0x18000bc9b  add     rdx, rdx
0x18000bc9e  lea     rax, [rdx+0Fh]
0x18000bca2  cmp     rax, rdx
0x18000bca5  ja      short loc_18000BCB1
0x18000bca7  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000bcb1  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000bcb5  call    _alloca_probe
0x18000bcba  sub     rsp, rax
0x18000bcbd  mov     rcx, rbx; lpszShortPath
0x18000bcc0  lea     rdi, [rsp+0C0h+szLongPath]
0x18000bcc5  mov     rdx, rdi; lpszLongPath
0x18000bcc8  call    cs:__imp_GetLongPathNameW
0x18000bcce  test    eax, eax
0x18000bcd0  jnz     short loc_18000BCEC
0x18000bcd2  call    cs:__imp_GetLastError
0x18000bcd8  test    eax, eax
0x18000bcda  jle     short loc_18000BCE6
0x18000bcdc  movzx   eax, ax
0x18000bcdf  or      eax, 80070000h
0x18000bce4  test    eax, eax
0x18000bce6  jnz     loc_18000BDF9
0x18000bcec  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x18000bcf5  lea     rax, [rbp+70h+hKey]
0x18000bcf9  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000bcfe  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000bd05  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000bd0e  xor     r9d, r9d; lpClass
0x18000bd11  mov     [rsp+0C0h+samDesired], 2001Bh; samDesired
0x18000bd19  xor     r8d, r8d; Reserved
0x18000bd1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bd23  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x18000bd2b  call    cs:__imp_RegCreateKeyExW
0x18000bd31  test    eax, eax
0x18000bd33  jle     short loc_18000BD3F
0x18000bd35  movzx   eax, ax
0x18000bd38  or      eax, 80070000h
0x18000bd3d  test    eax, eax
0x18000bd3f  jnz     loc_18000BDF9
0x18000bd45  mov     rcx, [rbp+70h+hKey]
0x18000bd49  mov     ebx, 1
0x18000bd4e  test    rcx, rcx
0x18000bd51  jnz     short loc_18000BD95
0x18000bd53  lea     eax, [rbx+14h]
0x18000bd56  mov     [rbp+70h+var_58], ecx
0x18000bd59  lea     r9, aHkeyshareddlls; "hkeySharedDlls"
0x18000bd60  mov     [rbp+70h+var_40], rcx
0x18000bd64  mov     [rbp+70h+var_38], rcx
0x18000bd68  lea     r8d, [rax+77h]; unsigned int
0x18000bd6c  lea     rdx, aComComplusSrcC_2; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18000bd73  mov     [rbp+70h+var_54], ax
0x18000bd77  lea     rcx, [rbp+70h+var_58]; this
0x18000bd7b  mov     [rbp+70h+var_50], 0C00212D6h
0x18000bd82  mov     [rbp+70h+var_48], r9
0x18000bd86  mov     [rbp+70h+var_2C], ebx
0x18000bd89  mov     [rbp+70h+var_30], ebx
0x18000bd8c  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000bd91  mov     rcx, [rbp+70h+hKey]; hKey
0x18000bd95  lea     rax, [rbp+70h+cbData]
0x18000bd99  xor     r8d, r8d; lpReserved
0x18000bd9c  mov     qword ptr [rsp+0C0h+samDesired], rax; lpcbData
0x18000bda1  lea     r9, [rbp+70h+Type]; lpType
0x18000bda5  lea     rax, [rbp+70h+szLongPath]
0x18000bda9  mov     rdx, rdi; lpValueName
0x18000bdac  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18000bdb1  call    cs:__imp_RegQueryValueExW
0x18000bdb7  test    eax, 0FFFFFFFDh
0x18000bdbc  jnz     short loc_18000BDF9
0x18000bdbe  mov     eax, dword ptr [rbp+70h+szLongPath]
0x18000bdc1  mov     rdx, rdi; lpValueName
0x18000bdc4  mov     rcx, [rbp+70h+hKey]; hKey
0x18000bdc8  add     eax, ebx
0x18000bdca  mov     dword ptr [rbp+70h+szLongPath], eax
0x18000bdcd  mov     [rbp+70h+Type], r14d
0x18000bdd1  mov     [rbp+70h+cbData], r14d
0x18000bdd5  jnz     short loc_18000BDDF
0x18000bdd7  call    cs:__imp_RegDeleteValueW
0x18000bddd  jmp     short loc_18000BDF9
0x18000bddf  lea     rax, [rbp+70h+szLongPath]
0x18000bde3  mov     [rsp+0C0h+samDesired], r14d; cbData
0x18000bde8  mov     r9d, r14d; dwType
0x18000bdeb  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18000bdf0  xor     r8d, r8d; Reserved
0x18000bdf3  call    cs:__imp_RegSetValueExW
0x18000bdf9  mov     rcx, [rbp+70h+hKey]; hKey
0x18000bdfd  test    rcx, rcx
0x18000be00  jz      short loc_18000BE08
0x18000be02  call    cs:__imp_RegCloseKey
0x18000be08  xor     eax, eax
0x18000be0a  mov     rcx, [rbp+70h+var_28]
0x18000be0e  xor     rcx, rbp; StackCookie
0x18000be11  call    __security_check_cookie
0x18000be16  lea     rsp, [rbp+58h]
0x18000be1a  pop     r14
0x18000be1c  pop     rdi
0x18000be1d  pop     rbx
0x18000be1e  pop     rbp
0x18000be1f  retn
```
