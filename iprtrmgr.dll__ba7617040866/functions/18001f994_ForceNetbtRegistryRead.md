# ForceNetbtRegistryRead

- ea: `0x18001f994`
- end: `0x18001fbbf`
- name: `ForceNetbtRegistryRead`
- size: `555`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f378`
- `0x180021220`

## callees

- `0x18000ac60`
- `0x18001f994`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18001faa3`
- `ntdll!NtCreateFile` at `0x18001faa3`
- `ntdll!RtlInitUnicodeString` at `0x18001fa3f`
- `ntdll!RtlInitUnicodeString` at `0x18001fa3f`
- `ntdll!NtDeviceIoControlFile` at `0x18001fb22`
- `ntdll!NtDeviceIoControlFile` at `0x18001fb22`
- `KERNEL32!CloseHandle` at `0x18001fb74`
- `KERNEL32!CloseHandle` at `0x18001fb74`

## string_xrefs

- `0x18001f9fa`: `ForceNetbtRegistryRead`
- `0x18001fabc`: `ForceNetbtRegistryRead: Couldnt create NETBT driver handle. NtStatus %x`
- `0x18001fb3b`: `ForceNetbtRegistryRead: Failed IOCTL call to NETBT, status %x`
- `0x18001fb83`: `Leaving: ForceNetbtRegistryRead`

## pseudocode

```c
__int64 ForceNetbtRegistryRead()
{
  unsigned int v0; // ebx
  NTSTATUS v1; // eax
  NTSTATUS v2; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  int v8; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v9[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v0 = 0;
  FileHandle = 0;
  v8 = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(v9, 0, sizeof(v9));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"Entered: %ws", L"ForceNetbtRegistryRead");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v8);
  }
  RtlInitUnicodeString(&DestinationString, L"\\Device\\NetBt_Wins_Export");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtCreateFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0, 0, 0);
  if ( v1 >= 0 )
  {
    v2 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x218088u, 0, 0, 0, 0);
    if ( v2 < 0 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"ForceNetbtRegistryRead: Failed IOCTL call to NETBT, status %x", (unsigned int)v2);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v8);
      }
      v0 = 635;
    }
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(
        &v8,
        L"ForceNetbtRegistryRead: Couldnt create NETBT driver handle. NtStatus %x",
        (unsigned int)v1);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v8);
    }
    v0 = 110;
  }
  CloseHandle(FileHandle);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: ForceNetbtRegistryRead");
  return v0;
}

```

## disassembly

```asm
0x18001f994  mov     [rsp-8+arg_0], rbx
0x18001f999  push    rbp
0x18001f99a  lea     rbp, [rsp-7D0h]
0x18001f9a2  sub     rsp, 8D0h
0x18001f9a9  mov     rax, cs:__security_cookie
0x18001f9b0  xor     rax, rsp
0x18001f9b3  mov     [rbp+7D0h+var_10], rax
0x18001f9ba  xorps   xmm0, xmm0
0x18001f9bd  lea     rcx, [rbp+7D0h+var_80C]; void *
0x18001f9c1  xorps   xmm1, xmm1
0x18001f9c4  xor     ebx, ebx
0x18001f9c6  movups  xmmword ptr [rbp+7D0h+ObjectAttributes.ObjectName], xmm0
0x18001f9ca  xor     eax, eax
0x18001f9cc  mov     [rsp+8D0h+FileHandle], rbx
0x18001f9d1  xor     edx, edx; Val
0x18001f9d3  mov     [rbp+7D0h+var_810], ebx
0x18001f9d6  mov     r8d, 7FCh; Size
0x18001f9dc  movups  xmmword ptr [rbp+7D0h+ObjectAttributes+1Ch], xmm0
0x18001f9e0  movups  xmmword ptr [rbp+7D0h+DestinationString.Length], xmm0
0x18001f9e4  movups  xmmword ptr [rbp+7D0h+IoStatusBlock], xmm1
0x18001f9e8  movups  xmmword ptr [rsp+8D0h+ObjectAttributes.Length], xmm0
0x18001f9ed  call    memset_0
0x18001f9f2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001f9f8  jge     short loc_18001FA34
0x18001f9fa  lea     r8, aForcenetbtregi_0; "ForceNetbtRegistryRead"
0x18001fa01  mov     word ptr [rbp+7D0h+var_810], bx
0x18001fa05  lea     rdx, aEnteredWs; "Entered: %ws"
0x18001fa0c  lea     rcx, [rbp+7D0h+var_810]
0x18001fa10  call    FormatRRASErrorString
0x18001fa15  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001fa1b  jge     short loc_18001FA34
0x18001fa1d  lea     r8, [rbp+7D0h+var_810]
0x18001fa21  lea     rdx, RasRtrmgrTraceInfo
0x18001fa28  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fa2f  call    McTemplateU0z_EventWriteTransfer
0x18001fa34  lea     rdx, SourceString; "\\Device\\NetBt_Wins_Export"
0x18001fa3b  lea     rcx, [rbp+7D0h+DestinationString]; DestinationString
0x18001fa3f  call    cs:__imp_RtlInitUnicodeString
0x18001fa45  mov     [rsp+8D0h+EaLength], ebx; EaLength
0x18001fa49  lea     rax, [rbp+7D0h+DestinationString]
0x18001fa4d  mov     [rsp+8D0h+EaBuffer], rbx; EaBuffer
0x18001fa52  lea     r9, [rbp+7D0h+IoStatusBlock]; IoStatusBlock
0x18001fa56  mov     [rsp+8D0h+CreateOptions], ebx; CreateOptions
0x18001fa5a  lea     r8, [rsp+8D0h+ObjectAttributes]; ObjectAttributes
0x18001fa5f  mov     [rbp+7D0h+ObjectAttributes.ObjectName], rax
0x18001fa63  lea     rcx, [rsp+8D0h+FileHandle]; FileHandle
0x18001fa68  mov     eax, 3
0x18001fa6d  mov     [rsp+8D0h+ObjectAttributes.Length], 30h ; '0'
0x18001fa75  mov     [rsp+8D0h+CreateDisposition], eax; CreateDisposition
0x18001fa79  xorps   xmm0, xmm0
0x18001fa7c  mov     [rsp+8D0h+ShareAccess], eax; ShareAccess
0x18001fa80  mov     edx, 100003h; DesiredAccess
0x18001fa85  mov     [rsp+8D0h+FileAttributes], 80h; FileAttributes
0x18001fa8d  mov     [rsp+8D0h+AllocationSize], rbx; AllocationSize
0x18001fa92  mov     [rsp+8D0h+ObjectAttributes.RootDirectory], rbx
0x18001fa97  mov     [rbp+7D0h+ObjectAttributes.Attributes], 40h ; '@'
0x18001fa9e  movdqu  xmmword ptr [rbp+7D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001faa3  call    cs:__imp_NtCreateFile
0x18001faa9  test    eax, eax
0x18001faab  jns     short loc_18001FAF2
0x18001faad  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001fab3  jge     short loc_18001FAEB
0x18001fab5  mov     r8d, eax
0x18001fab8  mov     word ptr [rbp+7D0h+var_810], bx
0x18001fabc  lea     rdx, aForcenetbtregi; "ForceNetbtRegistryRead: Couldnt create "...
0x18001fac3  lea     rcx, [rbp+7D0h+var_810]
0x18001fac7  call    FormatRRASErrorString
0x18001facc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001fad2  jge     short loc_18001FAEB
0x18001fad4  lea     r8, [rbp+7D0h+var_810]
0x18001fad8  lea     rdx, RasRtrmgrTraceInfo
0x18001fadf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fae6  call    McTemplateU0z_EventWriteTransfer
0x18001faeb  mov     ebx, 6Eh ; 'n'
0x18001faf0  jmp     short loc_18001FB6F
0x18001faf2  mov     rcx, [rsp+8D0h+FileHandle]; FileHandle
0x18001faf7  lea     rax, [rbp+7D0h+IoStatusBlock]
0x18001fafb  mov     dword ptr [rsp+8D0h+EaBuffer], ebx; OutputBufferLength
0x18001faff  xor     r9d, r9d; ApcContext
0x18001fb02  mov     qword ptr [rsp+8D0h+CreateOptions], rbx; OutputBuffer
0x18001fb07  xor     r8d, r8d; ApcRoutine
0x18001fb0a  mov     [rsp+8D0h+CreateDisposition], ebx; InputBufferLength
0x18001fb0e  xor     edx, edx; Event
0x18001fb10  mov     qword ptr [rsp+8D0h+ShareAccess], rbx; InputBuffer
0x18001fb15  mov     [rsp+8D0h+FileAttributes], 218088h; IoControlCode
0x18001fb1d  mov     [rsp+8D0h+AllocationSize], rax; IoStatusBlock
0x18001fb22  call    cs:__imp_NtDeviceIoControlFile
0x18001fb28  test    eax, eax
0x18001fb2a  jns     short loc_18001FB6F
0x18001fb2c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001fb32  jge     short loc_18001FB6A
0x18001fb34  mov     r8d, eax
0x18001fb37  mov     word ptr [rbp+7D0h+var_810], bx
0x18001fb3b  lea     rdx, aForcenetbtregi_1; "ForceNetbtRegistryRead: Failed IOCTL ca"...
0x18001fb42  lea     rcx, [rbp+7D0h+var_810]
0x18001fb46  call    FormatRRASErrorString
0x18001fb4b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001fb51  jge     short loc_18001FB6A
0x18001fb53  lea     r8, [rbp+7D0h+var_810]
0x18001fb57  lea     rdx, RasRtrmgrTraceInfo
0x18001fb5e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fb65  call    McTemplateU0z_EventWriteTransfer
0x18001fb6a  mov     ebx, 27Bh
0x18001fb6f  mov     rcx, [rsp+8D0h+FileHandle]; hObject
0x18001fb74  call    cs:__imp_CloseHandle
0x18001fb7a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001fb81  jz      short loc_18001FB9D
0x18001fb83  lea     r8, aLeavingForcene; "Leaving: ForceNetbtRegistryRead"
0x18001fb8a  lea     rdx, RasRtrmgrTraceInfo
0x18001fb91  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fb98  call    McTemplateU0z_EventWriteTransfer
0x18001fb9d  mov     eax, ebx
0x18001fb9f  mov     rcx, [rbp+7D0h+var_10]
0x18001fba6  xor     rcx, rsp; StackCookie
0x18001fba9  call    __security_check_cookie
0x18001fbae  mov     rbx, [rsp+8D0h+arg_0]
0x18001fbb6  add     rsp, 8D0h
0x18001fbbd  pop     rbp
0x18001fbbe  retn
```
