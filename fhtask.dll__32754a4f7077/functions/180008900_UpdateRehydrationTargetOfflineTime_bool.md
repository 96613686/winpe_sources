# UpdateRehydrationTargetOfflineTime(bool *)

- ea: `0x180008900`
- end: `0x180008b51`
- name: `?UpdateRehydrationTargetOfflineTime@@YAXPEA_N@Z`
- size: `593`
- prototype: `void __fastcall(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x1800067a0`
- `0x180008900`
- `0x180009464`
- `0x1800094cc`
- `0x180009a00`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180008a11`
- `ADVAPI32!RegGetValueW` at `0x180008a11`
- `ADVAPI32!RegCloseKey` at `0x180008b32`
- `ADVAPI32!RegCloseKey` at `0x180008b32`
- `ADVAPI32!RegCreateKeyExW` at `0x180008996`
- `ADVAPI32!RegCreateKeyExW` at `0x180008996`
- `ADVAPI32!RegSetValueExW` at `0x180008aeb`
- `ADVAPI32!RegSetValueExW` at `0x180008aeb`
- `KERNEL32!SystemTimeToFileTime` at `0x180008a2b`
- `KERNEL32!SystemTimeToFileTime` at `0x180008a2b`
- `KERNEL32!GetSystemTime` at `0x180008a1d`
- `KERNEL32!GetSystemTime` at `0x180008a1d`
- `KERNEL32!GetLastError` at `0x180008a35`
- `KERNEL32!GetLastError` at `0x180008a35`

## pseudocode

```c
void __fastcall UpdateRehydrationTargetOfflineTime(bool *a1)
{
  __int64 v2; // r8
  LSTATUS ValueW; // edi
  signed int LastError; // eax
  __int64 v5; // r9
  int v6; // r8d
  DWORD pcbData; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  struct _FILETIME FileTime; // [rsp+60h] [rbp+7h] BYREF
  __int64 pvData; // [rsp+68h] [rbp+Fh] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp+17h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+78h] [rbp+1Fh] BYREF

  *a1 = 0;
  hKey = 0;
  pvData = 0;
  pcbData = 8;
  FileTime = 0;
  SystemTime = 0;
  *(_QWORD *)Data = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        v2,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory");
  }
  else
  {
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
               L"RehydrationTargetOfflineSinceTime",
               0x20000040u,
               0,
               &pvData,
               &pcbData);
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      *(struct _FILETIME *)Data = FileTime;
      if ( ValueW || !pvData )
      {
        if ( RegSetValueExW(hKey, L"RehydrationTargetOfflineSinceTime", 0, 0xBu, Data, 8u)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            v6,
            (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
            (__int64)L"RehydrationTargetOfflineSinceTime");
        }
      }
      else
      {
        *a1 = (*(_QWORD *)&FileTime - pvData) / 0x989680uLL >= 0x93A80;
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = (unsigned int)LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v5);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180008900  push    rbp
0x180008902  push    rbx
0x180008903  push    rdi
0x180008904  push    r15
0x180008906  lea     rbp, [rsp-3Fh]
0x18000890b  sub     rsp, 98h
0x180008912  mov     rax, cs:__security_cookie
0x180008919  xor     rax, rsp
0x18000891c  mov     [rbp+57h+var_28], rax
0x180008920  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180008929  lea     rax, [rbp+57h+hKey]
0x18000892d  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180008932  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008939  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180008942  mov     rbx, rcx
0x180008945  xorps   xmm0, xmm0
0x180008948  mov     byte ptr [rcx], 0
0x18000894b  mov     rdi, 0FFFFFFFF80000001h
0x180008952  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18000895a  xor     r9d, r9d; lpClass
0x18000895d  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x180008965  xor     r8d, r8d; Reserved
0x180008968  mov     [rbp+57h+hKey], 0
0x180008970  mov     rcx, rdi; hKey
0x180008973  mov     [rbp+57h+pvData], 0
0x18000897b  mov     [rbp+57h+pcbData], 8
0x180008982  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18000898a  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000898e  mov     qword ptr [rbp+57h+Data], 0
0x180008996  call    cs:__imp_RegCreateKeyExW
0x18000899c  test    eax, eax
0x18000899e  jz      short loc_1800089DC
0x1800089a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089a7  lea     rax, WPP_GLOBAL_Control
0x1800089ae  cmp     rcx, rax
0x1800089b1  jz      loc_180008B29
0x1800089b7  mov     al, 1
0x1800089b9  test    [rcx+1Ch], al
0x1800089bc  jz      loc_180008B29
0x1800089c2  mov     rcx, [rcx+10h]
0x1800089c6  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800089cd  mov     edx, 11h
0x1800089d2  call    WPP_SF_S
0x1800089d7  jmp     loc_180008B29
0x1800089dc  lea     rax, [rbp+57h+pcbData]
0x1800089e0  mov     r9d, 20000040h; dwFlags
0x1800089e6  mov     [rsp+0B0h+lpSecurityAttributes], rax; pcbData
0x1800089eb  lea     r15, ValueName; "RehydrationTargetOfflineSinceTime"
0x1800089f2  lea     rax, [rbp+57h+pvData]
0x1800089f6  mov     r8, r15; lpValue
0x1800089f9  mov     qword ptr [rsp+0B0h+samDesired], rax; pvData
0x1800089fe  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008a05  mov     rcx, rdi; hkey
0x180008a08  mov     qword ptr [rsp+0B0h+dwOptions], 0; pdwType
0x180008a11  call    cs:__imp_RegGetValueW
0x180008a17  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180008a1b  mov     edi, eax
0x180008a1d  call    cs:__imp_GetSystemTime
0x180008a23  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180008a27  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180008a2b  call    cs:__imp_SystemTimeToFileTime
0x180008a31  test    eax, eax
0x180008a33  jnz     short loc_180008A89
0x180008a35  call    cs:__imp_GetLastError
0x180008a3b  mov     r9d, eax
0x180008a3e  test    eax, eax
0x180008a40  jle     short loc_180008A4D
0x180008a42  movzx   r9d, ax
0x180008a46  or      r9d, 80070000h
0x180008a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a54  lea     rax, WPP_GLOBAL_Control
0x180008a5b  cmp     rcx, rax
0x180008a5e  jz      loc_180008B29
0x180008a64  mov     al, 1
0x180008a66  test    [rcx+1Ch], al
0x180008a69  jz      loc_180008B29
0x180008a6f  mov     rcx, [rcx+10h]
0x180008a73  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180008a7a  mov     edx, 12h
0x180008a7f  call    WPP_SF_d
0x180008a84  jmp     loc_180008B29
0x180008a89  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180008a8d  mov     qword ptr [rbp+57h+Data], rcx
0x180008a91  test    edi, edi
0x180008a93  jnz     short loc_180008ACA
0x180008a95  mov     rax, [rbp+57h+pvData]
0x180008a99  test    rax, rax
0x180008a9c  jz      short loc_180008ACA
0x180008a9e  sub     rcx, rax
0x180008aa1  mov     rax, 0D6BF94D5E57A42BDh
0x180008aab  mul     rcx
0x180008aae  shr     rdx, 17h
0x180008ab2  test    rdx, rdx
0x180008ab5  jle     short loc_180008AC4
0x180008ab7  cmp     rdx, 93A80h
0x180008abe  jb      short loc_180008AC4
0x180008ac0  mov     al, 1
0x180008ac2  jmp     short loc_180008AC6
0x180008ac4  xor     al, al
0x180008ac6  mov     [rbx], al
0x180008ac8  jmp     short loc_180008B29
0x180008aca  mov     rcx, [rbp+57h+hKey]; hKey
0x180008ace  lea     rax, [rbp+57h+Data]
0x180008ad2  mov     [rsp+0B0h+samDesired], 8; cbData
0x180008ada  mov     r9d, 0Bh; dwType
0x180008ae0  xor     r8d, r8d; Reserved
0x180008ae3  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x180008ae8  mov     rdx, r15; lpValueName
0x180008aeb  call    cs:__imp_RegSetValueExW
0x180008af1  test    eax, eax
0x180008af3  jz      short loc_180008B29
0x180008af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008afc  lea     rax, WPP_GLOBAL_Control
0x180008b03  cmp     rcx, rax
0x180008b06  jz      short loc_180008B29
0x180008b08  mov     al, 1
0x180008b0a  test    [rcx+1Ch], al
0x180008b0d  jz      short loc_180008B29
0x180008b0f  mov     rcx, [rcx+10h]
0x180008b13  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008b1a  mov     edx, 13h
0x180008b1f  mov     qword ptr [rsp+0B0h+dwOptions], r15
0x180008b24  call    WPP_SF_SS
0x180008b29  mov     rcx, [rbp+57h+hKey]; hKey
0x180008b2d  test    rcx, rcx
0x180008b30  jz      short loc_180008B38
0x180008b32  call    cs:__imp_RegCloseKey
0x180008b38  mov     rcx, [rbp+57h+var_28]
0x180008b3c  xor     rcx, rsp; StackCookie
0x180008b3f  call    __security_check_cookie
0x180008b44  add     rsp, 98h
0x180008b4b  pop     r15
0x180008b4d  pop     rdi
0x180008b4e  pop     rbx
0x180008b4f  pop     rbp
0x180008b50  retn
```
