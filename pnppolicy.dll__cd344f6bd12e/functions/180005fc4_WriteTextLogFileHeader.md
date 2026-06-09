# WriteTextLogFileHeader

- ea: `0x180005fc4`
- end: `0x1800060f7`
- name: `WriteTextLogFileHeader`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x1800052c4`

## callees

- `0x1800044e0`
- `0x180005fc4`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x180006014`
- `ntdll!RtlGetVersion` at `0x18000602b`
- `ntdll!RtlGetVersion` at `0x180006014`
- `ntdll!RtlGetVersion` at `0x18000602b`
- `KERNEL32!WriteFile` at `0x1800060d1`
- `KERNEL32!WriteFile` at `0x1800060d1`

## string_xrefs

- `0x180006088`: `[Device Install Log]\n     OS Version = %d.%d.%d\n     Service Pack = %d.%d\n     Suite = 0x%04x\n     ProductType = %d\n     Architecture = %s\n\n[BeginLog]\n`

## pseudocode

```c
HRESULT __fastcall WriteTextLogFileHeader(HANDLE hFile)
{
  HRESULT result; // eax
  __int64 v3; // r8
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v6; // [rsp+184h] [rbp+84h]
  unsigned __int16 v7; // [rsp+186h] [rbp+86h]
  unsigned __int16 v8; // [rsp+188h] [rbp+88h]
  unsigned __int8 v9; // [rsp+18Ah] [rbp+8Ah]
  char pszDest[256]; // [rsp+190h] [rbp+90h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) >= 0
    || (VersionInformation.dwOSVersionInfoSize = 276, result = RtlGetVersion(&VersionInformation), result >= 0) )
  {
    result = StringCchPrintfA(
               pszDest,
               0xFFu,
               "[Device Install Log]\r\n"
               "     OS Version = %d.%d.%d\r\n"
               "     Service Pack = %d.%d\r\n"
               "     Suite = 0x%04x\r\n"
               "     ProductType = %d\r\n"
               "     Architecture = %s\r\n"
               "\r\n"
               "[BeginLog]\r\n",
               VersionInformation.dwMajorVersion,
               VersionInformation.dwMinorVersion,
               VersionInformation.dwBuildNumber,
               v6,
               v7,
               v8,
               v9,
               "amd64");
    if ( result >= 0 )
    {
      v3 = -1;
      do
        ++v3;
      while ( pszDest[v3] );
      return WriteFile(hFile, pszDest, v3, &NumberOfBytesWritten, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005fc4  mov     [rsp-8+arg_8], rbx
0x180005fc9  push    rbp
0x180005fca  lea     rbp, [rsp-1A0h]
0x180005fd2  sub     rsp, 2A0h
0x180005fd9  mov     rax, cs:__security_cookie
0x180005fe0  xor     rax, rsp
0x180005fe3  mov     [rbp+1A0h+var_10], rax
0x180005fea  mov     rbx, rcx
0x180005fed  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x180005ff5  lea     rcx, [rsp+2A0h+VersionInformation.dwMajorVersion]; void *
0x180005ffa  xor     edx, edx; Val
0x180005ffc  mov     r8d, 118h; Size
0x180006002  call    memset_0
0x180006007  lea     rcx, [rsp+2A0h+VersionInformation]; lpVersionInformation
0x18000600c  mov     [rsp+2A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180006014  call    cs:__imp_RtlGetVersion
0x18000601a  test    eax, eax
0x18000601c  jns     short loc_180006039
0x18000601e  lea     rcx, [rsp+2A0h+VersionInformation]; lpVersionInformation
0x180006023  mov     [rsp+2A0h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000602b  call    cs:__imp_RtlGetVersion
0x180006031  test    eax, eax
0x180006033  js      loc_1800060D7
0x180006039  movzx   eax, [rbp+1A0h+var_116]
0x180006040  lea     r9, aAmd64; "amd64"
0x180006047  movzx   ecx, [rbp+1A0h+var_118]
0x18000604e  movzx   edx, [rbp+1A0h+var_11A]
0x180006055  movzx   r8d, [rbp+1A0h+var_11C]
0x18000605d  mov     [rsp+2A0h+var_250], r9
0x180006062  mov     r9d, [rsp+2A0h+VersionInformation.dwMajorVersion]
0x180006067  mov     [rsp+2A0h+var_258], eax
0x18000606b  mov     eax, [rsp+2A0h+VersionInformation.dwBuildNumber]
0x18000606f  mov     [rsp+2A0h+var_260], ecx
0x180006073  lea     rcx, [rbp+1A0h+pszDest]; pszDest
0x18000607a  mov     [rsp+2A0h+var_268], edx
0x18000607e  mov     edx, 0FFh; cchDest
0x180006083  mov     [rsp+2A0h+var_270], r8d
0x180006088  lea     r8, aDeviceInstallL; "[Device Install Log]\r\n     OS Version"...
0x18000608f  mov     [rsp+2A0h+var_278], eax
0x180006093  mov     eax, [rsp+2A0h+VersionInformation.dwMinorVersion]
0x180006097  mov     dword ptr [rsp+2A0h+lpOverlapped], eax
0x18000609b  call    StringCchPrintfA
0x1800060a0  test    eax, eax
0x1800060a2  js      short loc_1800060D7
0x1800060a4  lea     rax, [rbp+1A0h+pszDest]
0x1800060ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800060af  inc     r8; nNumberOfBytesToWrite
0x1800060b2  cmp     byte ptr [rax+r8], 0
0x1800060b7  jnz     short loc_1800060AF
0x1800060b9  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800060be  mov     [rsp+2A0h+lpOverlapped], 0; lpOverlapped
0x1800060c7  lea     rdx, [rbp+1A0h+pszDest]; lpBuffer
0x1800060ce  mov     rcx, rbx; hFile
0x1800060d1  call    cs:__imp_WriteFile
0x1800060d7  mov     rcx, [rbp+1A0h+var_10]
0x1800060de  xor     rcx, rsp; StackCookie
0x1800060e1  call    __security_check_cookie
0x1800060e6  mov     rbx, [rsp+2A0h+arg_8]
0x1800060ee  add     rsp, 2A0h
0x1800060f5  pop     rbp
0x1800060f6  retn
```
