# InitializeRedirector

- ea: `0x140005af8`
- end: `0x140005d70`
- name: `InitializeRedirector`
- size: `632`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000664c`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140005af8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005b78`
- `KERNEL32!GetLastError` at `0x140005b78`
- `KERNEL32!CreateEventW` at `0x140005b6a`
- `KERNEL32!CreateEventW` at `0x140005b6a`
- `KERNEL32!WaitForSingleObject` at `0x140005ca3`
- `KERNEL32!WaitForSingleObject` at `0x140005ca3`
- `KERNEL32!CloseHandle` at `0x140005cde`
- `KERNEL32!CloseHandle` at `0x140005d2d`
- `KERNEL32!CloseHandle` at `0x140005cde`
- `KERNEL32!CloseHandle` at `0x140005d2d`
- `ntdll!RtlInitUnicodeString` at `0x140005bb1`
- `ntdll!RtlInitUnicodeString` at `0x140005bb1`
- `ntdll!NtOpenFile` at `0x140005bf9`
- `ntdll!NtOpenFile` at `0x140005bf9`
- `ntdll!NtFsControlFile` at `0x140005c90`
- `ntdll!NtFsControlFile` at `0x140005c90`
- `ntdll!NtClose` at `0x140005d3f`
- `ntdll!NtClose` at `0x140005d3f`
- `ntdll!RtlNtStatusToDosError` at `0x140005d56`
- `ntdll!RtlNtStatusToDosError` at `0x140005d56`

## pseudocode

```c
ULONG InitializeRedirector()
{
  HANDLE EventW; // rsi
  DWORD v2; // ebx
  unsigned int v3; // eax
  int Status; // edi
  _BYTE *v5; // rcx
  __int64 v6; // rdx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
  hDevice = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return GetLastError();
  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\MRxNfs");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenFile(&hDevice, 0x100002u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  Status = v3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e7926938627732e63f903c41c3c41751_Traceguids, v3);
    v5 = WPP_GLOBAL_Control;
  }
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
  {
    if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || (v5[28] & 2) == 0 )
      goto LABEL_34;
    v6 = 13;
    goto LABEL_33;
  }
  if ( v5 != (_BYTE *)&WPP_GLOBAL_Control && (v5[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)v5 + 2), 14, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
  if ( NtFsControlFile(hDevice, EventW, 0, 0, &IoStatusBlock, 0x148940u, 0, 0, 0, 0) != 259
    || (v2 = WaitForSingleObject(EventW, 0xFFFFFFFF), Status = -1073741823, v2 != -1) )
  {
    Status = IoStatusBlock.Status;
  }
  if ( v2 != -1 )
    v2 = 0;
  if ( Status < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v6 = 15;
LABEL_33:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_e7926938627732e63f903c41c3c41751_Traceguids, (unsigned int)Status);
LABEL_34:
    CloseHandle(EventW);
    if ( hDevice )
      NtClose(hDevice);
    hDevice = 0;
    if ( !v2 )
      return RtlNtStatusToDosError(Status);
    return v2;
  }
  CloseHandle(EventW);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140005af8  push    rbp
0x140005afa  push    rbx
0x140005afb  push    rsi
0x140005afc  push    rdi
0x140005afd  push    r12
0x140005aff  push    r15
0x140005b01  lea     rbp, [rsp-2Fh]
0x140005b06  sub     rsp, 0A8h
0x140005b0d  xorps   xmm0, xmm0
0x140005b10  xor     eax, eax
0x140005b12  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140005b16  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140005b1a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140005b1e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140005b22  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140005b26  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b2d  lea     r15, WPP_GLOBAL_Control
0x140005b34  lea     r12, WPP_e7926938627732e63f903c41c3c41751_Traceguids
0x140005b3b  cmp     rcx, r15
0x140005b3e  jz      short loc_140005B55
0x140005b40  test    byte ptr [rcx+1Ch], 1
0x140005b44  jz      short loc_140005B55
0x140005b46  mov     rcx, [rcx+10h]
0x140005b4a  lea     edx, [rax+0Ah]
0x140005b4d  mov     r8, r12
0x140005b50  call    WPP_SF_
0x140005b55  xor     r9d, r9d; lpName
0x140005b58  mov     cs:hDevice, 0
0x140005b63  xor     r8d, r8d; bInitialState
0x140005b66  xor     edx, edx; bManualReset
0x140005b68  xor     ecx, ecx; lpEventAttributes
0x140005b6a  call    cs:__imp_CreateEventW
0x140005b70  mov     rsi, rax
0x140005b73  test    rax, rax
0x140005b76  jnz     short loc_140005B83
0x140005b78  call    cs:__imp_GetLastError
0x140005b7e  jmp     loc_140005D60
0x140005b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b8a  xor     ebx, ebx
0x140005b8c  cmp     rcx, r15
0x140005b8f  jz      short loc_140005BA6
0x140005b91  test    byte ptr [rcx+1Ch], 8
0x140005b95  jz      short loc_140005BA6
0x140005b97  mov     rcx, [rcx+10h]
0x140005b9b  lea     edx, [rbx+0Bh]
0x140005b9e  mov     r8, r12
0x140005ba1  call    WPP_SF_
0x140005ba6  lea     rdx, aDeviceMrxnfs; "\\Device\\MRxNfs"
0x140005bad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005bb1  call    cs:__imp_RtlInitUnicodeString
0x140005bb7  lea     rax, [rbp+57h+DestinationString]
0x140005bbb  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x140005bc3  xorps   xmm0, xmm0
0x140005bc6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140005bca  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140005bce  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140005bd5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140005bd9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140005bdd  mov     edx, 100002h; DesiredAccess
0x140005be2  mov     [rbp+57h+ObjectAttributes.Attributes], ebx
0x140005be5  lea     rcx, hDevice; FileHandle
0x140005bec  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x140005bf4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140005bf9  call    cs:__imp_NtOpenFile
0x140005bff  mov     edi, eax
0x140005c01  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c08  cmp     rcx, r15
0x140005c0b  jz      short loc_140005C2E
0x140005c0d  test    byte ptr [rcx+1Ch], 8
0x140005c11  jz      short loc_140005C2E
0x140005c13  mov     rcx, [rcx+10h]
0x140005c17  mov     edx, 0Ch
0x140005c1c  mov     r9d, eax
0x140005c1f  mov     r8, r12
0x140005c22  call    WPP_SF_d
0x140005c27  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c2e  test    edi, edi
0x140005c30  js      loc_140005D0B
0x140005c36  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x140005c39  test    edi, edi
0x140005c3b  js      loc_140005D0B
0x140005c41  cmp     rcx, r15
0x140005c44  jz      short loc_140005C5D
0x140005c46  test    byte ptr [rcx+1Ch], 8
0x140005c4a  jz      short loc_140005C5D
0x140005c4c  mov     rcx, [rcx+10h]
0x140005c50  mov     edx, 0Eh
0x140005c55  mov     r8, r12
0x140005c58  call    WPP_SF_
0x140005c5d  mov     rcx, cs:hDevice; FileHandle
0x140005c64  lea     rax, [rbp+57h+IoStatusBlock]
0x140005c68  mov     [rsp+0D0h+OutputBufferLength], ebx; OutputBufferLength
0x140005c6c  xor     r9d, r9d; ApcContext
0x140005c6f  mov     [rsp+0D0h+OutputBuffer], rbx; OutputBuffer
0x140005c74  xor     r8d, r8d; ApcRoutine
0x140005c77  mov     [rsp+0D0h+InputBufferLength], ebx; InputBufferLength
0x140005c7b  mov     rdx, rsi; Event
0x140005c7e  mov     [rsp+0D0h+InputBuffer], rbx; InputBuffer
0x140005c83  mov     [rsp+0D0h+OpenOptions], 148940h; FsControlCode
0x140005c8b  mov     qword ptr [rsp+0D0h+ShareAccess], rax; IoStatusBlock
0x140005c90  call    cs:__imp_NtFsControlFile
0x140005c96  cmp     eax, 103h
0x140005c9b  jnz     short loc_140005CB5
0x140005c9d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005ca0  mov     rcx, rsi; hHandle
0x140005ca3  call    cs:__imp_WaitForSingleObject
0x140005ca9  mov     ebx, eax
0x140005cab  mov     edi, 0C0000001h
0x140005cb0  cmp     eax, 0FFFFFFFFh
0x140005cb3  jz      short loc_140005CB8
0x140005cb5  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x140005cb8  xor     eax, eax
0x140005cba  cmp     ebx, 0FFFFFFFFh
0x140005cbd  cmovnz  ebx, eax
0x140005cc0  test    edi, edi
0x140005cc2  jns     short loc_140005CDB
0x140005cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ccb  cmp     rcx, r15
0x140005cce  jz      short loc_140005D2A
0x140005cd0  test    byte ptr [rcx+1Ch], 2
0x140005cd4  jz      short loc_140005D2A
0x140005cd6  lea     edx, [rax+0Fh]
0x140005cd9  jmp     short loc_140005D1B
0x140005cdb  mov     rcx, rsi; hObject
0x140005cde  call    cs:__imp_CloseHandle
0x140005ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ceb  cmp     rcx, r15
0x140005cee  jz      short loc_140005D07
0x140005cf0  test    byte ptr [rcx+1Ch], 1
0x140005cf4  jz      short loc_140005D07
0x140005cf6  mov     rcx, [rcx+10h]
0x140005cfa  mov     edx, 10h
0x140005cff  mov     r8, r12
0x140005d02  call    WPP_SF_
0x140005d07  xor     eax, eax
0x140005d09  jmp     short loc_140005D60
0x140005d0b  cmp     rcx, r15
0x140005d0e  jz      short loc_140005D2A
0x140005d10  test    byte ptr [rcx+1Ch], 2
0x140005d14  jz      short loc_140005D2A
0x140005d16  mov     edx, 0Dh
0x140005d1b  mov     rcx, [rcx+10h]
0x140005d1f  mov     r9d, edi
0x140005d22  mov     r8, r12
0x140005d25  call    WPP_SF_d
0x140005d2a  mov     rcx, rsi; hObject
0x140005d2d  call    cs:__imp_CloseHandle
0x140005d33  mov     rcx, cs:hDevice; Handle
0x140005d3a  test    rcx, rcx
0x140005d3d  jz      short loc_140005D45
0x140005d3f  call    cs:__imp_NtClose
0x140005d45  mov     cs:hDevice, 0
0x140005d50  test    ebx, ebx
0x140005d52  jnz     short loc_140005D5E
0x140005d54  mov     ecx, edi; Status
0x140005d56  call    cs:__imp_RtlNtStatusToDosError
0x140005d5c  mov     ebx, eax
0x140005d5e  mov     eax, ebx
0x140005d60  add     rsp, 0A8h
0x140005d67  pop     r15
0x140005d69  pop     r12
0x140005d6b  pop     rdi
0x140005d6c  pop     rsi
0x140005d6d  pop     rbx
0x140005d6e  pop     rbp
0x140005d6f  retn
```
