# ForceNetbtRegistryRead

- ea: `0x18000cc70`
- end: `0x18000ce92`
- name: `ForceNetbtRegistryRead`
- size: `546`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800205e4`

## callees

- `0x18000cc70`
- `0x18000ce98`
- `0x18001cef0`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18000cdb9`
- `ntdll!NtDeviceIoControlFile` at `0x18000cdb9`
- `ntdll!NtCreateFile` at `0x18000cd6b`
- `ntdll!NtCreateFile` at `0x18000cd6b`
- `ntdll!RtlInitUnicodeString` at `0x18000ccf2`
- `ntdll!RtlInitUnicodeString` at `0x18000ccf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdd3`

## pseudocode

```c
__int64 __fastcall ForceNetbtRegistryRead(__int64 a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // eax
  DWORD LastError; // ebx
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t pszDest[400]; // [rsp+C0h] [rbp-40h] BYREF

  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
    WPP_SF_(1043, 16, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  StringCchPrintfW(pszDest, 0x190u, L"%s%s", L"\\Device\\NetBT_TCPIP_", a1);
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtCreateFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0, 0, 0);
  if ( v2 < 0 )
  {
    if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
      WPP_SF_D(1043, 17, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids, (unsigned int)v2);
    LastError = 110;
  }
  else
  {
    v3 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x218088u, 0, 0, 0, 0);
    if ( v3 < 0 )
    {
      if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
        WPP_SF_D(1043, 18, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids, (unsigned int)v3);
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
    }
  }
  if ( FileHandle )
    CloseHandle(FileHandle);
  if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
    WPP_SF_(1043, 19, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x18000cc70  mov     [rsp-8+arg_8], rbx
0x18000cc75  push    rbp
0x18000cc76  lea     rbp, [rsp-2F0h]
0x18000cc7e  sub     rsp, 3F0h
0x18000cc85  mov     rax, cs:__security_cookie
0x18000cc8c  xor     rax, rsp
0x18000cc8f  mov     [rbp+2F0h+var_10], rax
0x18000cc96  xorps   xmm0, xmm0
0x18000cc99  xorps   xmm1, xmm1
0x18000cc9c  xor     eax, eax
0x18000cc9e  mov     rbx, rcx
0x18000cca1  movups  xmmword ptr [rsp+3F0h+ObjectAttributes.ObjectName], xmm0
0x18000cca6  mov     [rsp+3F0h+FileHandle], rax
0x18000ccab  movups  xmmword ptr [rbp+2F0h+ObjectAttributes+1Ch], xmm0
0x18000ccaf  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x18000ccb3  movups  xmmword ptr [rbp+2F0h+IoStatusBlock], xmm1
0x18000ccb7  movups  xmmword ptr [rsp+3F0h+ObjectAttributes.Length], xmm0
0x18000ccbc  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000ccc3  jnz     loc_18000CE04
0x18000ccc9  lea     r9, aDeviceNetbtTcp; "\\Device\\NetBT_TCPIP_"
0x18000ccd0  mov     [rsp+3F0h+AllocationSize], rbx
0x18000ccd5  lea     r8, aSS; "%s%s"
0x18000ccdc  mov     edx, 190h; cchDest
0x18000cce1  lea     rcx, [rbp+2F0h+pszDest]; pszDest
0x18000cce5  call    StringCchPrintfW
0x18000ccea  lea     rdx, [rbp+2F0h+pszDest]; SourceString
0x18000ccee  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x18000ccf2  call    cs:__imp_RtlInitUnicodeString
0x18000ccf8  mov     [rsp+3F0h+EaLength], 0; EaLength
0x18000cd00  lea     rax, [rbp+2F0h+DestinationString]
0x18000cd04  mov     [rsp+3F0h+EaBuffer], 0; EaBuffer
0x18000cd0d  lea     r9, [rbp+2F0h+IoStatusBlock]; IoStatusBlock
0x18000cd11  mov     [rsp+3F0h+CreateOptions], 0; CreateOptions
0x18000cd19  lea     r8, [rsp+3F0h+ObjectAttributes]; ObjectAttributes
0x18000cd1e  mov     [rsp+3F0h+ObjectAttributes.ObjectName], rax
0x18000cd23  lea     rcx, [rsp+3F0h+FileHandle]; FileHandle
0x18000cd28  mov     eax, 3
0x18000cd2d  mov     [rsp+3F0h+ObjectAttributes.Length], 30h ; '0'
0x18000cd35  mov     [rsp+3F0h+CreateDisposition], eax; CreateDisposition
0x18000cd39  xorps   xmm0, xmm0
0x18000cd3c  mov     [rsp+3F0h+ShareAccess], eax; ShareAccess
0x18000cd40  mov     edx, 100003h; DesiredAccess
0x18000cd45  mov     [rsp+3F0h+FileAttributes], 80h; FileAttributes
0x18000cd4d  mov     [rsp+3F0h+AllocationSize], 0; AllocationSize
0x18000cd56  mov     [rsp+3F0h+ObjectAttributes.RootDirectory], 0
0x18000cd5f  mov     [rbp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000cd66  movdqu  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000cd6b  call    cs:__imp_NtCreateFile
0x18000cd71  test    eax, eax
0x18000cd73  js      loc_18000CE37
0x18000cd79  mov     rcx, [rsp+3F0h+FileHandle]; FileHandle
0x18000cd7e  lea     rax, [rbp+2F0h+IoStatusBlock]
0x18000cd82  mov     dword ptr [rsp+3F0h+EaBuffer], 0; OutputBufferLength
0x18000cd8a  xor     r9d, r9d; ApcContext
0x18000cd8d  mov     qword ptr [rsp+3F0h+CreateOptions], 0; OutputBuffer
0x18000cd96  xor     r8d, r8d; ApcRoutine
0x18000cd99  mov     [rsp+3F0h+CreateDisposition], 0; InputBufferLength
0x18000cda1  xor     edx, edx; Event
0x18000cda3  mov     qword ptr [rsp+3F0h+ShareAccess], 0; InputBuffer
0x18000cdac  mov     [rsp+3F0h+FileAttributes], 218088h; IoControlCode
0x18000cdb4  mov     [rsp+3F0h+AllocationSize], rax; IoStatusBlock
0x18000cdb9  call    cs:__imp_NtDeviceIoControlFile
0x18000cdbf  test    eax, eax
0x18000cdc1  js      loc_18000CE63
0x18000cdc7  xor     ebx, ebx
0x18000cdc9  mov     rcx, [rsp+3F0h+FileHandle]; hObject
0x18000cdce  test    rcx, rcx
0x18000cdd1  jz      short loc_18000CDD9
0x18000cdd3  call    cs:__imp_CloseHandle
0x18000cdd9  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000cde0  jnz     short loc_18000CE1F
0x18000cde2  mov     eax, ebx
0x18000cde4  mov     rcx, [rbp+2F0h+var_10]
0x18000cdeb  xor     rcx, rsp; StackCookie
0x18000cdee  call    __security_check_cookie
0x18000cdf3  mov     rbx, [rsp+3F0h+arg_8]
0x18000cdfb  add     rsp, 3F0h
0x18000ce02  pop     rbp
0x18000ce03  retn
0x18000ce04  mov     edx, 10h
0x18000ce09  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ce10  mov     ecx, 413h
0x18000ce15  call    WPP_SF_
0x18000ce1a  jmp     loc_18000CCC9
0x18000ce1f  mov     edx, 13h
0x18000ce24  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ce2b  mov     ecx, 413h
0x18000ce30  call    WPP_SF_
0x18000ce35  jmp     short loc_18000CDE2
0x18000ce37  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000ce3e  jz      short loc_18000CE59
0x18000ce40  mov     edx, 11h
0x18000ce45  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ce4c  mov     ecx, 413h
0x18000ce51  mov     r9d, eax
0x18000ce54  call    WPP_SF_D
0x18000ce59  mov     ebx, 6Eh ; 'n'
0x18000ce5e  jmp     loc_18000CDC9
0x18000ce63  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000ce6a  jz      short loc_18000CE85
0x18000ce6c  mov     edx, 12h
0x18000ce71  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ce78  mov     ecx, 413h
0x18000ce7d  mov     r9d, eax
0x18000ce80  call    WPP_SF_D
0x18000ce85  call    cs:__imp_GetLastError
0x18000ce8b  mov     ebx, eax
0x18000ce8d  jmp     loc_18000CDC9
```
