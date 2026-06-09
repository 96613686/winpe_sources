# FveFsOpenRoot

- ea: `0x14006d5c0`
- end: `0x14006d718`
- name: `FveFsOpenRoot`
- size: `344`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006d41c`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14006d5c0`
- `0x1400e08f4`
- `0x1400e6538`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14006d649`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006d649`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006d660`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006d660`
- `ntoskrnl!ZwOpenFile` at `0x14006d6b8`
- `ntoskrnl!ZwOpenFile` at `0x14006d6b8`

## pseudocode

```c
__int64 __fastcall FveFsOpenRoot(PCUNICODE_STRING SourceString, PHANDLE FileHandle)
{
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 239, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
  }
  DestinationString = 0;
  appended = FveAllocateUnicodePath(&DestinationString);
  if ( appended >= 0 )
  {
    RtlCopyUnicodeString(&DestinationString, SourceString);
    appended = RtlAppendUnicodeToString(&DestinationString, L"\\");
    if ( appended >= 0 )
    {
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = ZwOpenFile(FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
      if ( appended >= 0 )
        appended = 0;
    }
  }
  FveFreeUnicodePath(&DestinationString);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      240,
      WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
      (unsigned int)appended);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14006d5c0  push    rbp
0x14006d5c2  push    rbx
0x14006d5c3  push    rsi
0x14006d5c4  push    rdi
0x14006d5c5  push    r14
0x14006d5c7  mov     rbp, rsp
0x14006d5ca  sub     rsp, 80h
0x14006d5d1  xorps   xmm0, xmm0
0x14006d5d4  xorps   xmm1, xmm1
0x14006d5d7  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14006d5db  mov     rsi, rdx
0x14006d5de  mov     rdi, rcx
0x14006d5e1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14006d5e5  xor     eax, eax
0x14006d5e7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006d5eb  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14006d5ef  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14006d5f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d5fa  lea     r14, WPP_GLOBAL_Control
0x14006d601  cmp     rcx, r14
0x14006d604  jz      short loc_14006D628
0x14006d606  mov     eax, [rcx+2Ch]
0x14006d609  test    al, 20h
0x14006d60b  jz      short loc_14006D628
0x14006d60d  cmp     byte ptr [rcx+29h], 5
0x14006d611  jb      short loc_14006D628
0x14006d613  mov     rcx, [rcx+18h]
0x14006d617  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006d61e  mov     edx, 0EFh
0x14006d623  call    WPP_SF_
0x14006d628  xorps   xmm0, xmm0
0x14006d62b  lea     rcx, [rbp+DestinationString]
0x14006d62f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14006d633  call    FveAllocateUnicodePath
0x14006d638  mov     ebx, eax
0x14006d63a  test    eax, eax
0x14006d63c  js      loc_14006D6CD
0x14006d642  mov     rdx, rdi; SourceString
0x14006d645  lea     rcx, [rbp+DestinationString]; DestinationString
0x14006d649  call    cs:__imp_RtlCopyUnicodeString
0x14006d650  nop     dword ptr [rax+rax+00h]
0x14006d655  lea     rdx, Source; "\\"
0x14006d65c  lea     rcx, [rbp+DestinationString]; Destination
0x14006d660  call    cs:__imp_RtlAppendUnicodeToString
0x14006d667  nop     dword ptr [rax+rax+00h]
0x14006d66c  mov     ebx, eax
0x14006d66e  test    eax, eax
0x14006d670  js      short loc_14006D6CD
0x14006d672  lea     rax, [rbp+DestinationString]
0x14006d676  mov     [rsp+80h+OpenOptions], 4021h; OpenOptions
0x14006d67e  xorps   xmm0, xmm0
0x14006d681  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14006d685  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14006d689  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14006d690  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14006d694  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14006d69c  mov     edx, 80h; DesiredAccess
0x14006d6a1  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14006d6a8  mov     rcx, rsi; FileHandle
0x14006d6ab  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x14006d6b3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14006d6b8  call    cs:__imp_ZwOpenFile
0x14006d6bf  nop     dword ptr [rax+rax+00h]
0x14006d6c4  mov     ebx, eax
0x14006d6c6  xor     eax, eax
0x14006d6c8  test    ebx, ebx
0x14006d6ca  cmovns  ebx, eax
0x14006d6cd  lea     rcx, [rbp+DestinationString]
0x14006d6d1  call    FveFreeUnicodePath
0x14006d6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d6dd  cmp     rcx, r14
0x14006d6e0  jz      short loc_14006D707
0x14006d6e2  mov     eax, [rcx+2Ch]
0x14006d6e5  test    al, 20h
0x14006d6e7  jz      short loc_14006D707
0x14006d6e9  cmp     byte ptr [rcx+29h], 5
0x14006d6ed  jb      short loc_14006D707
0x14006d6ef  mov     rcx, [rcx+18h]
0x14006d6f3  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006d6fa  mov     edx, 0F0h
0x14006d6ff  mov     r9d, ebx
0x14006d702  call    WPP_SF_d
0x14006d707  mov     eax, ebx
0x14006d709  add     rsp, 80h
0x14006d710  pop     r14
0x14006d712  pop     rdi
0x14006d713  pop     rsi
0x14006d714  pop     rbx
0x14006d715  pop     rbp
0x14006d716  retn
```
