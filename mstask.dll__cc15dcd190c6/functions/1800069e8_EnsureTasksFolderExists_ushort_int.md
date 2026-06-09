# EnsureTasksFolderExists(ushort *,int)

- ea: `0x1800069e8`
- end: `0x180006b95`
- name: `?EnsureTasksFolderExists@@YAJPEAGH@Z`
- size: `429`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006550`

## callees

- `0x1800069e8`
- `0x18000beb8`
- `0x18000cc18`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b28`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180006a43`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180006a43`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006a10`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006a10`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180006b1e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180006b1e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006af6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b74`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006a79`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006a79`

## pseudocode

```c
__int64 __fastcall EnsureTasksFolderExists(unsigned __int16 *a1)
{
  signed int DesktopIni; // ebx
  const WCHAR *v4; // rcx
  unsigned int v5; // ecx
  signed int LastError; // eax
  int v7; // eax
  signed int v8; // eax
  unsigned int v9; // ecx
  signed int v10; // eax
  int v11; // eax
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-D8h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-D0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+16Ah] [rbp+6Ah]

  DesktopIni = 0;
  if ( GetFileAttributesW(a1) == -1 )
  {
    SecurityDescriptor = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
      return 2147500037LL;
    v4 = L"D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;AU)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)S:(AU;SAFAOICI;FWDCSDWDWO;;;WD)(AU;SAFAO"
          "ICI;FWDCSDWDWO;;;AN)";
    if ( v16 != 1 )
      v4 = L"D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;BO)(A;;0x1200ab;;;SO)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)S:(AU;SAFAOICI;FWDCS"
            "DWDWO;;;WD)(AU;SAFAOICI;FWDCSDWDWO;;;AN)";
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0) )
      goto LABEL_10;
    LastError = GetLastError();
    DesktopIni = LastError;
    if ( LastError > 0 )
      DesktopIni = (unsigned __int16)LastError | 0x80070000;
    if ( DesktopIni >= 0 )
    {
LABEL_10:
      v12 = 0;
      v7 = EnablePrivilege(v5, 1, &v12);
      if ( v7 > 0 )
      {
        DesktopIni = (unsigned __int16)v7 | 0x80070000;
      }
      else if ( v7 )
      {
        DesktopIni = v7;
      }
      if ( DesktopIni >= 0 )
      {
        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
        *(_QWORD *)&SecurityAttributes.nLength = 24;
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
        if ( CreateDirectoryW(a1, &SecurityAttributes) )
          goto LABEL_22;
        v8 = GetLastError();
        DesktopIni = v8;
        if ( v8 > 0 )
          DesktopIni = (unsigned __int16)v8 | 0x80070000;
        if ( DesktopIni >= 0 )
        {
LABEL_22:
          if ( SetFileAttributesW(a1, 4u) )
            goto LABEL_23;
          v10 = GetLastError();
          DesktopIni = v10;
          if ( v10 > 0 )
            DesktopIni = (unsigned __int16)v10 | 0x80070000;
          if ( DesktopIni >= 0 )
LABEL_23:
            DesktopIni = CreateDesktopIni(a1);
        }
        if ( !v12 )
        {
          v11 = EnablePrivilege(v9, 0, 0);
          if ( v11 )
          {
            if ( DesktopIni >= 0 )
            {
              if ( v11 > 0 )
                DesktopIni = (unsigned __int16)v11 | 0x80070000;
              else
                DesktopIni = v11;
            }
          }
        }
      }
      LocalFree(SecurityDescriptor);
    }
  }
  return (unsigned int)DesktopIni;
}

```

## disassembly

```asm
0x1800069e8  push    rbp
0x1800069ea  push    rbx
0x1800069eb  push    rdi
0x1800069ec  push    r14
0x1800069ee  lea     rbp, [rsp-88h]
0x1800069f6  sub     rsp, 188h
0x1800069fd  mov     rax, cs:__security_cookie
0x180006a04  xor     rax, rsp
0x180006a07  mov     [rbp+0A0h+var_30], rax
0x180006a0b  mov     rdi, rcx
0x180006a0e  xor     ebx, ebx
0x180006a10  call    cs:__imp_GetFileAttributesW
0x180006a16  cmp     eax, 0FFFFFFFFh
0x180006a19  jnz     loc_180006B7A
0x180006a1f  xor     edx, edx; Val
0x180006a21  mov     [rsp+1A0h+SecurityDescriptor], rbx
0x180006a26  mov     r8d, 118h; Size
0x180006a2c  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x180006a31  call    memset_0
0x180006a36  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x180006a3b  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180006a43  call    cs:__imp_GetVersionExW
0x180006a49  test    eax, eax
0x180006a4b  jnz     short loc_180006A57
0x180006a4d  mov     eax, 80004005h
0x180006a52  jmp     loc_180006B7C
0x180006a57  cmp     [rbp+0A0h+var_36], 1
0x180006a5b  lea     rax, StringSecurityDescriptor; "D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;BO)"...
0x180006a62  lea     rcx, aDPAOiciioFaCoA_0; "D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;AU)"...
0x180006a69  cmovnz  rcx, rax; StringSecurityDescriptor
0x180006a6d  lea     r8, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x180006a72  xor     r9d, r9d; SecurityDescriptorSize
0x180006a75  lea     edx, [r9+1]; StringSDRevision
0x180006a79  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006a7f  mov     r14d, 80070000h
0x180006a85  test    eax, eax
0x180006a87  jnz     short loc_180006AA3
0x180006a89  call    cs:__imp_GetLastError
0x180006a8f  mov     ebx, eax
0x180006a91  test    eax, eax
0x180006a93  jle     short loc_180006A9B
0x180006a95  movzx   ebx, ax
0x180006a98  or      ebx, r14d
0x180006a9b  test    ebx, ebx
0x180006a9d  js      loc_180006B7A
0x180006aa3  lea     r8, [rsp+1A0h+var_180]; int *
0x180006aa8  mov     [rsp+1A0h+var_180], 0
0x180006ab0  mov     edx, 1; int
0x180006ab5  call    ?EnablePrivilege@@YAKKHPEAH@Z; EnablePrivilege(ulong,int,int *)
0x180006aba  test    eax, eax
0x180006abc  jg      short loc_180006AC4
0x180006abe  jz      short loc_180006ACA
0x180006ac0  mov     ebx, eax
0x180006ac2  jmp     short loc_180006ACA
0x180006ac4  movzx   ebx, ax
0x180006ac7  or      ebx, r14d
0x180006aca  test    ebx, ebx
0x180006acc  js      loc_180006B6F
0x180006ad2  mov     rax, [rsp+1A0h+SecurityDescriptor]
0x180006ad7  lea     rdx, [rsp+1A0h+SecurityAttributes]; lpSecurityAttributes
0x180006adc  mov     rcx, rdi; lpPathName
0x180006adf  mov     [rsp+1A0h+SecurityAttributes.lpSecurityDescriptor], rax
0x180006ae4  mov     qword ptr [rsp+1A0h+SecurityAttributes.nLength], 18h
0x180006aed  mov     qword ptr [rsp+1A0h+SecurityAttributes.bInheritHandle], 0
0x180006af6  call    cs:__imp_CreateDirectoryW
0x180006afc  test    eax, eax
0x180006afe  jnz     short loc_180006B16
0x180006b00  call    cs:__imp_GetLastError
0x180006b06  mov     ebx, eax
0x180006b08  test    eax, eax
0x180006b0a  jle     short loc_180006B12
0x180006b0c  movzx   ebx, ax
0x180006b0f  or      ebx, r14d
0x180006b12  test    ebx, ebx
0x180006b14  js      short loc_180006B48
0x180006b16  mov     edx, 4; dwFileAttributes
0x180006b1b  mov     rcx, rdi; lpFileName
0x180006b1e  call    cs:__imp_SetFileAttributesW
0x180006b24  test    eax, eax
0x180006b26  jnz     short loc_180006B3E
0x180006b28  call    cs:__imp_GetLastError
0x180006b2e  mov     ebx, eax
0x180006b30  test    eax, eax
0x180006b32  jle     short loc_180006B3A
0x180006b34  movzx   ebx, ax
0x180006b37  or      ebx, r14d
0x180006b3a  test    ebx, ebx
0x180006b3c  js      short loc_180006B48
0x180006b3e  mov     rcx, rdi; unsigned __int16 *
0x180006b41  call    ?CreateDesktopIni@@YAJPEBG@Z; CreateDesktopIni(ushort const *)
0x180006b46  mov     ebx, eax
0x180006b48  cmp     [rsp+1A0h+var_180], 0
0x180006b4d  jnz     short loc_180006B6F
0x180006b4f  xor     r8d, r8d; int *
0x180006b52  xor     edx, edx; int
0x180006b54  call    ?EnablePrivilege@@YAKKHPEAH@Z; EnablePrivilege(ulong,int,int *)
0x180006b59  test    eax, eax
0x180006b5b  jz      short loc_180006B6F
0x180006b5d  test    ebx, ebx
0x180006b5f  js      short loc_180006B6F
0x180006b61  test    eax, eax
0x180006b63  jg      short loc_180006B69
0x180006b65  mov     ebx, eax
0x180006b67  jmp     short loc_180006B6F
0x180006b69  movzx   ebx, ax
0x180006b6c  or      ebx, r14d
0x180006b6f  mov     rcx, [rsp+1A0h+SecurityDescriptor]; hMem
0x180006b74  call    cs:__imp_LocalFree
0x180006b7a  mov     eax, ebx
0x180006b7c  mov     rcx, [rbp+0A0h+var_30]
0x180006b80  xor     rcx, rsp; StackCookie
0x180006b83  call    __security_check_cookie
0x180006b88  add     rsp, 188h
0x180006b8f  pop     r14
0x180006b91  pop     rdi
0x180006b92  pop     rbx
0x180006b93  pop     rbp
0x180006b94  retn
```
