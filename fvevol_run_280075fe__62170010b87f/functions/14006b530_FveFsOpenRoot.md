# FveFsOpenRoot

- ea: `0x14006b530`
- end: `0x14006b688`
- name: `FveFsOpenRoot`
- size: `344`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006b38c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14006b530`
- `0x1400de1d4`
- `0x1400e3a5c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14006b5b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006b5b9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006b5d0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006b5d0`
- `ntoskrnl!ZwOpenFile` at `0x14006b628`
- `ntoskrnl!ZwOpenFile` at `0x14006b628`

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
0x14006b530  push    rbp
0x14006b532  push    rbx
0x14006b533  push    rsi
0x14006b534  push    rdi
0x14006b535  push    r14
0x14006b537  mov     rbp, rsp
0x14006b53a  sub     rsp, 80h
0x14006b541  xorps   xmm0, xmm0
0x14006b544  xorps   xmm1, xmm1
0x14006b547  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14006b54b  mov     rsi, rdx
0x14006b54e  mov     rdi, rcx
0x14006b551  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14006b555  xor     eax, eax
0x14006b557  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006b55b  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14006b55f  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14006b563  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b56a  lea     r14, WPP_GLOBAL_Control
0x14006b571  cmp     rcx, r14
0x14006b574  jz      short loc_14006B598
0x14006b576  mov     eax, [rcx+2Ch]
0x14006b579  test    al, 20h
0x14006b57b  jz      short loc_14006B598
0x14006b57d  cmp     byte ptr [rcx+29h], 5
0x14006b581  jb      short loc_14006B598
0x14006b583  mov     rcx, [rcx+18h]
0x14006b587  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006b58e  mov     edx, 0EFh
0x14006b593  call    WPP_SF_
0x14006b598  xorps   xmm0, xmm0
0x14006b59b  lea     rcx, [rbp+DestinationString]
0x14006b59f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14006b5a3  call    FveAllocateUnicodePath
0x14006b5a8  mov     ebx, eax
0x14006b5aa  test    eax, eax
0x14006b5ac  js      loc_14006B63D
0x14006b5b2  mov     rdx, rdi; SourceString
0x14006b5b5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14006b5b9  call    cs:__imp_RtlCopyUnicodeString
0x14006b5c0  nop     dword ptr [rax+rax+00h]
0x14006b5c5  lea     rdx, Source; "\\"
0x14006b5cc  lea     rcx, [rbp+DestinationString]; Destination
0x14006b5d0  call    cs:__imp_RtlAppendUnicodeToString
0x14006b5d7  nop     dword ptr [rax+rax+00h]
0x14006b5dc  mov     ebx, eax
0x14006b5de  test    eax, eax
0x14006b5e0  js      short loc_14006B63D
0x14006b5e2  lea     rax, [rbp+DestinationString]
0x14006b5e6  mov     [rsp+80h+OpenOptions], 4021h; OpenOptions
0x14006b5ee  xorps   xmm0, xmm0
0x14006b5f1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14006b5f5  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14006b5f9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14006b600  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14006b604  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14006b60c  mov     edx, 80h; DesiredAccess
0x14006b611  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14006b618  mov     rcx, rsi; FileHandle
0x14006b61b  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x14006b623  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14006b628  call    cs:__imp_ZwOpenFile
0x14006b62f  nop     dword ptr [rax+rax+00h]
0x14006b634  mov     ebx, eax
0x14006b636  xor     eax, eax
0x14006b638  test    ebx, ebx
0x14006b63a  cmovns  ebx, eax
0x14006b63d  lea     rcx, [rbp+DestinationString]
0x14006b641  call    FveFreeUnicodePath
0x14006b646  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b64d  cmp     rcx, r14
0x14006b650  jz      short loc_14006B677
0x14006b652  mov     eax, [rcx+2Ch]
0x14006b655  test    al, 20h
0x14006b657  jz      short loc_14006B677
0x14006b659  cmp     byte ptr [rcx+29h], 5
0x14006b65d  jb      short loc_14006B677
0x14006b65f  mov     rcx, [rcx+18h]
0x14006b663  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006b66a  mov     edx, 0F0h
0x14006b66f  mov     r9d, ebx
0x14006b672  call    WPP_SF_d
0x14006b677  mov     eax, ebx
0x14006b679  add     rsp, 80h
0x14006b680  pop     r14
0x14006b682  pop     rdi
0x14006b683  pop     rsi
0x14006b684  pop     rbx
0x14006b685  pop     rbp
0x14006b686  retn
```
