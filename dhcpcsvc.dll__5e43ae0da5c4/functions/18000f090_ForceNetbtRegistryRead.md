# ForceNetbtRegistryRead

- ea: `0x18000f090`
- end: `0x18000f297`
- name: `ForceNetbtRegistryRead`
- size: `519`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dbe0`

## callees

- `0x1800048c0`
- `0x18000d510`
- `0x18000f090`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000f122`
- `ntdll!RtlInitUnicodeString` at `0x18000f122`
- `ntdll!NtDeviceIoControlFile` at `0x18000f20e`
- `ntdll!NtDeviceIoControlFile` at `0x18000f20e`
- `ntdll!NtCreateFile` at `0x18000f19b`
- `ntdll!NtCreateFile` at `0x18000f19b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000f23a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000f23a`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x18000f250`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x18000f250`

## pseudocode

```c
__int64 __fastcall ForceNetbtRegistryRead(__int64 a1)
{
  NTSTATUS v2; // eax
  DWORD LastError; // ebx
  NTSTATUS v4; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t pszDest[400]; // [rsp+C0h] [rbp-40h] BYREF

  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
    WPP_SF_(1043, 16, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  StringCchPrintfW(pszDest, 0x190u, L"%s%s", L"\\Device\\NetBT_TCPIP_", a1);
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtCreateFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0, 0, 0);
  if ( v2 >= 0 )
  {
    v4 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x218088u, 0, 0, 0, 0);
    if ( v4 >= 0 )
    {
      LastError = 0;
    }
    else
    {
      if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
        WPP_SF_d(1043, 18, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids, (unsigned int)v4);
      LastError = GetLastError();
    }
  }
  else
  {
    if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
      WPP_SF_d(1043, 17, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids, (unsigned int)v2);
    LastError = 110;
  }
  if ( FileHandle )
    CloseHandle(FileHandle);
  if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
    WPP_SF_(1043, 19, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x18000f090  mov     [rsp-8+arg_8], rbx
0x18000f095  push    rbp
0x18000f096  lea     rbp, [rsp-2F0h]
0x18000f09e  sub     rsp, 3F0h
0x18000f0a5  mov     rax, cs:__security_cookie
0x18000f0ac  xor     rax, rsp
0x18000f0af  mov     [rbp+2F0h+var_10], rax
0x18000f0b6  xorps   xmm0, xmm0
0x18000f0b9  xorps   xmm1, xmm1
0x18000f0bc  xor     eax, eax
0x18000f0be  mov     rbx, rcx
0x18000f0c1  movups  xmmword ptr [rsp+3F0h+ObjectAttributes.ObjectName], xmm0
0x18000f0c6  mov     [rsp+3F0h+FileHandle], rax
0x18000f0cb  movups  xmmword ptr [rbp+2F0h+ObjectAttributes+1Ch], xmm0
0x18000f0cf  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x18000f0d3  movups  xmmword ptr [rbp+2F0h+IoStatusBlock], xmm1
0x18000f0d7  movups  xmmword ptr [rsp+3F0h+ObjectAttributes.Length], xmm0
0x18000f0dc  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000f0e3  jz      short loc_18000F0F9
0x18000f0e5  lea     edx, [rax+10h]
0x18000f0e8  mov     ecx, 413h
0x18000f0ed  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000f0f4  call    WPP_SF_
0x18000f0f9  lea     r9, aDeviceNetbtTcp; "\\Device\\NetBT_TCPIP_"
0x18000f100  mov     [rsp+3F0h+AllocationSize], rbx
0x18000f105  lea     r8, aSS; "%s%s"
0x18000f10c  mov     edx, 190h; cchDest
0x18000f111  lea     rcx, [rbp+2F0h+pszDest]; pszDest
0x18000f115  call    StringCchPrintfW
0x18000f11a  lea     rdx, [rbp+2F0h+pszDest]; SourceString
0x18000f11e  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x18000f122  call    cs:__imp_RtlInitUnicodeString
0x18000f128  mov     [rsp+3F0h+EaLength], 0; EaLength
0x18000f130  lea     rax, [rbp+2F0h+DestinationString]
0x18000f134  mov     [rsp+3F0h+EaBuffer], 0; EaBuffer
0x18000f13d  lea     r9, [rbp+2F0h+IoStatusBlock]; IoStatusBlock
0x18000f141  mov     [rsp+3F0h+CreateOptions], 0; CreateOptions
0x18000f149  lea     r8, [rsp+3F0h+ObjectAttributes]; ObjectAttributes
0x18000f14e  mov     [rsp+3F0h+ObjectAttributes.ObjectName], rax
0x18000f153  lea     rcx, [rsp+3F0h+FileHandle]; FileHandle
0x18000f158  mov     eax, 3
0x18000f15d  mov     [rsp+3F0h+ObjectAttributes.Length], 30h ; '0'
0x18000f165  mov     [rsp+3F0h+CreateDisposition], eax; CreateDisposition
0x18000f169  xorps   xmm0, xmm0
0x18000f16c  mov     [rsp+3F0h+ShareAccess], eax; ShareAccess
0x18000f170  mov     edx, 100003h; DesiredAccess
0x18000f175  mov     [rsp+3F0h+FileAttributes], 80h; FileAttributes
0x18000f17d  mov     [rsp+3F0h+AllocationSize], 0; AllocationSize
0x18000f186  mov     [rsp+3F0h+ObjectAttributes.RootDirectory], 0
0x18000f18f  mov     [rbp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000f196  movdqu  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f19b  call    cs:__imp_NtCreateFile
0x18000f1a1  test    eax, eax
0x18000f1a3  jns     short loc_18000F1CE
0x18000f1a5  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000f1ac  jz      short loc_18000F1C7
0x18000f1ae  mov     edx, 11h
0x18000f1b3  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000f1ba  mov     ecx, 413h
0x18000f1bf  mov     r9d, eax
0x18000f1c2  call    WPP_SF_d
0x18000f1c7  mov     ebx, 6Eh ; 'n'
0x18000f1cc  jmp     short loc_18000F246
0x18000f1ce  mov     rcx, [rsp+3F0h+FileHandle]; FileHandle
0x18000f1d3  lea     rax, [rbp+2F0h+IoStatusBlock]
0x18000f1d7  mov     dword ptr [rsp+3F0h+EaBuffer], 0; OutputBufferLength
0x18000f1df  xor     r9d, r9d; ApcContext
0x18000f1e2  mov     qword ptr [rsp+3F0h+CreateOptions], 0; OutputBuffer
0x18000f1eb  xor     r8d, r8d; ApcRoutine
0x18000f1ee  mov     [rsp+3F0h+CreateDisposition], 0; InputBufferLength
0x18000f1f6  xor     edx, edx; Event
0x18000f1f8  mov     qword ptr [rsp+3F0h+ShareAccess], 0; InputBuffer
0x18000f201  mov     [rsp+3F0h+FileAttributes], 218088h; IoControlCode
0x18000f209  mov     [rsp+3F0h+AllocationSize], rax; IoStatusBlock
0x18000f20e  call    cs:__imp_NtDeviceIoControlFile
0x18000f214  test    eax, eax
0x18000f216  jns     short loc_18000F244
0x18000f218  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000f21f  jz      short loc_18000F23A
0x18000f221  mov     edx, 12h
0x18000f226  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000f22d  mov     ecx, 413h
0x18000f232  mov     r9d, eax
0x18000f235  call    WPP_SF_d
0x18000f23a  call    cs:__imp_GetLastError
0x18000f240  mov     ebx, eax
0x18000f242  jmp     short loc_18000F246
0x18000f244  xor     ebx, ebx
0x18000f246  mov     rcx, [rsp+3F0h+FileHandle]; hObject
0x18000f24b  test    rcx, rcx
0x18000f24e  jz      short loc_18000F256
0x18000f250  call    cs:__imp_CloseHandle
0x18000f256  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000f25d  jz      short loc_18000F275
0x18000f25f  mov     edx, 13h
0x18000f264  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000f26b  mov     ecx, 413h
0x18000f270  call    WPP_SF_
0x18000f275  mov     eax, ebx
0x18000f277  mov     rcx, [rbp+2F0h+var_10]
0x18000f27e  xor     rcx, rsp; StackCookie
0x18000f281  call    __security_check_cookie
0x18000f286  mov     rbx, [rsp+3F0h+arg_8]
0x18000f28e  add     rsp, 3F0h
0x18000f295  pop     rbp
0x18000f296  retn
```
