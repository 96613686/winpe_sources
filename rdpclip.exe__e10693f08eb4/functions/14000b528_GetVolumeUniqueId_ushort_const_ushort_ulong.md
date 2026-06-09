# GetVolumeUniqueId(ushort const *,ushort * *,ulong *)

- ea: `0x14000b528`
- end: `0x14000b776`
- name: `?GetVolumeUniqueId@@YAJPEBGPEAPEAGPEAK@Z`
- size: `590`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000abe4`

## callees

- `0x1400028b4`
- `0x1400028f4`
- `0x14000b528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6b2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b64c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b6a8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b64c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b6a8`
- `ntdll!NtCreateFile` at `0x14000b5dc`
- `ntdll!NtCreateFile` at `0x14000b5dc`
- `ntdll!RtlNtStatusToDosError` at `0x14000b5ea`
- `ntdll!RtlNtStatusToDosError` at `0x14000b5ea`
- `ntdll!NtClose` at `0x14000b744`
- `ntdll!NtClose` at `0x14000b744`
- `ntdll!RtlInitUnicodeString` at `0x14000b579`
- `ntdll!RtlInitUnicodeString` at `0x14000b579`
- `CRYPT32!CryptBinaryToStringW` at `0x14000b6d6`
- `CRYPT32!CryptBinaryToStringW` at `0x14000b723`
- `CRYPT32!CryptBinaryToStringW` at `0x14000b6d6`
- `CRYPT32!CryptBinaryToStringW` at `0x14000b723`

## pseudocode

```c
__int64 __fastcall GetVolumeUniqueId(PCWSTR SourceString, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned __int16 *v5; // rsi
  int v6; // eax
  BYTE *v7; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD BytesReturned; // [rsp+60h] [rbp-39h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  DWORD pcchString; // [rsp+118h] [rbp+7Fh] BYREF

  BytesReturned = 0;
  pcchString = 0;
  FileHandle = (void *)-1LL;
  v5 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
  if ( v6 < 0 )
  {
    v7 = 0;
    LastError = RtlNtStatusToDosError(v6);
LABEL_3:
    v9 = LastError;
    goto LABEL_4;
  }
  v7 = (BYTE *)operator new(4u);
  if ( !v7 )
    goto LABEL_7;
  if ( DeviceIoControl(FileHandle, 0x4D0000u, 0, 0, v7, 4u, &BytesReturned, 0)
    || (LastError = GetLastError(), v9 = LastError, LastError == 234) )
  {
    v10 = *(unsigned __int16 *)v7 + 4;
    operator delete(v7);
    v7 = (BYTE *)operator new(v10);
    if ( v7 )
    {
      if ( DeviceIoControl(FileHandle, 0x4D0000u, 0, 0, v7, v10, &BytesReturned, 0)
        && CryptBinaryToStringW(v7 + 2, *(unsigned __int16 *)v7, 0x40000001u, 0, &pcchString) )
      {
        v5 = (unsigned __int16 *)operator new(saturated_mul(pcchString, 2u));
        if ( !v5 )
          goto LABEL_7;
        if ( CryptBinaryToStringW(v7 + 2, *(unsigned __int16 *)v7, 0x40000001u, v5, &pcchString) )
        {
          v11 = pcchString;
          v9 = 0;
          *a2 = v5;
          v5 = 0;
          *a3 = v11;
          goto LABEL_17;
        }
      }
      LastError = GetLastError();
      goto LABEL_3;
    }
LABEL_7:
    v9 = -2147024882;
    goto LABEL_17;
  }
LABEL_4:
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_17:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( v7 )
    operator delete(v7);
  if ( v5 )
    operator delete(v5);
  return v9;
}

```

## disassembly

```asm
0x14000b528  push    rbp
0x14000b52a  push    rbx
0x14000b52b  push    rsi
0x14000b52c  push    rdi
0x14000b52d  push    r14
0x14000b52f  push    r15
0x14000b531  lea     rbp, [rsp-2Fh]
0x14000b536  sub     rsp, 0C8h
0x14000b53d  xorps   xmm0, xmm0
0x14000b540  mov     [rbp+57h+BytesReturned], 0
0x14000b547  mov     r15, rdx
0x14000b54a  mov     [rbp+57h+pcchString], 0
0x14000b551  mov     rdx, rcx; SourceString
0x14000b554  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14000b55c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000b560  mov     r14, r8
0x14000b563  xor     esi, esi
0x14000b565  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000b569  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000b56d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b571  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000b575  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000b579  call    cs:__imp_RtlInitUnicodeString
0x14000b57f  mov     [rsp+0F0h+EaLength], esi; EaLength
0x14000b583  lea     rax, [rbp+57h+DestinationString]
0x14000b587  mov     [rsp+0F0h+EaBuffer], rsi; EaBuffer
0x14000b58c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000b590  mov     [rsp+0F0h+CreateOptions], 20h ; ' '; CreateOptions
0x14000b598  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000b59c  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x14000b5a4  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000b5a8  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x14000b5b0  xorps   xmm0, xmm0
0x14000b5b3  mov     [rsp+0F0h+FileAttributes], esi; FileAttributes
0x14000b5b7  mov     edx, 100080h; DesiredAccess
0x14000b5bc  mov     [rsp+0F0h+AllocationSize], rsi; AllocationSize
0x14000b5c1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000b5c8  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000b5cc  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14000b5d3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000b5d7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b5dc  call    cs:__imp_NtCreateFile
0x14000b5e2  test    eax, eax
0x14000b5e4  jns     short loc_14000B608
0x14000b5e6  xor     edi, edi
0x14000b5e8  mov     ecx, eax; Status
0x14000b5ea  call    cs:__imp_RtlNtStatusToDosError
0x14000b5f0  mov     ebx, eax
0x14000b5f2  test    eax, eax
0x14000b5f4  jle     loc_14000B73A
0x14000b5fa  movzx   ebx, ax
0x14000b5fd  or      ebx, 80070000h
0x14000b603  jmp     loc_14000B73A
0x14000b608  mov     ebx, 4
0x14000b60d  mov     ecx, ebx; Size
0x14000b60f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b614  mov     rdi, rax
0x14000b617  test    rax, rax
0x14000b61a  jnz     short loc_14000B626
0x14000b61c  mov     ebx, 8007000Eh
0x14000b621  jmp     loc_14000B73A
0x14000b626  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x14000b62a  lea     rax, [rbp+57h+BytesReturned]
0x14000b62e  mov     qword ptr [rsp+0F0h+CreateDisposition], rsi; lpOverlapped
0x14000b633  xor     r9d, r9d; nInBufferSize
0x14000b636  mov     qword ptr [rsp+0F0h+ShareAccess], rax; lpBytesReturned
0x14000b63b  xor     r8d, r8d; lpInBuffer
0x14000b63e  mov     [rsp+0F0h+FileAttributes], ebx; nOutBufferSize
0x14000b642  mov     edx, 4D0000h; dwIoControlCode
0x14000b647  mov     [rsp+0F0h+AllocationSize], rdi; lpOutBuffer
0x14000b64c  call    cs:__imp_DeviceIoControl
0x14000b652  test    eax, eax
0x14000b654  jnz     short loc_14000B665
0x14000b656  call    cs:__imp_GetLastError
0x14000b65c  mov     ebx, eax
0x14000b65e  cmp     eax, 0EAh
0x14000b663  jnz     short loc_14000B5F2
0x14000b665  movzx   ebx, word ptr [rdi]
0x14000b668  mov     rcx, rdi; Block
0x14000b66b  add     ebx, 4
0x14000b66e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b673  mov     ecx, ebx; Size
0x14000b675  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b67a  mov     rdi, rax
0x14000b67d  test    rax, rax
0x14000b680  jz      short loc_14000B61C
0x14000b682  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x14000b686  lea     rax, [rbp+57h+BytesReturned]
0x14000b68a  mov     qword ptr [rsp+0F0h+CreateDisposition], rsi; lpOverlapped
0x14000b68f  xor     r9d, r9d; nInBufferSize
0x14000b692  mov     qword ptr [rsp+0F0h+ShareAccess], rax; lpBytesReturned
0x14000b697  xor     r8d, r8d; lpInBuffer
0x14000b69a  mov     [rsp+0F0h+FileAttributes], ebx; nOutBufferSize
0x14000b69e  mov     edx, 4D0000h; dwIoControlCode
0x14000b6a3  mov     [rsp+0F0h+AllocationSize], rdi; lpOutBuffer
0x14000b6a8  call    cs:__imp_DeviceIoControl
0x14000b6ae  test    eax, eax
0x14000b6b0  jnz     short loc_14000B6BD
0x14000b6b2  call    cs:__imp_GetLastError
0x14000b6b8  jmp     loc_14000B5F0
0x14000b6bd  movzx   edx, word ptr [rdi]; cbBinary
0x14000b6c0  lea     rax, [rbp+57h+pcchString]
0x14000b6c4  xor     r9d, r9d; pszString
0x14000b6c7  mov     [rsp+0F0h+AllocationSize], rax; pcchString
0x14000b6cc  mov     r8d, 40000001h; dwFlags
0x14000b6d2  lea     rcx, [rdi+2]; pbBinary
0x14000b6d6  call    cs:__imp_CryptBinaryToStringW
0x14000b6dc  test    eax, eax
0x14000b6de  jz      short loc_14000B6B2
0x14000b6e0  mov     ecx, [rbp+57h+pcchString]
0x14000b6e3  mov     eax, 2
0x14000b6e8  mul     rcx
0x14000b6eb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000b6f2  cmovb   rax, rcx
0x14000b6f6  mov     rcx, rax; Size
0x14000b6f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b6fe  mov     rsi, rax
0x14000b701  test    rax, rax
0x14000b704  jz      loc_14000B61C
0x14000b70a  movzx   edx, word ptr [rdi]; cbBinary
0x14000b70d  lea     rax, [rbp+57h+pcchString]
0x14000b711  mov     r9, rsi; pszString
0x14000b714  mov     [rsp+0F0h+AllocationSize], rax; pcchString
0x14000b719  mov     r8d, 40000001h; dwFlags
0x14000b71f  lea     rcx, [rdi+2]; pbBinary
0x14000b723  call    cs:__imp_CryptBinaryToStringW
0x14000b729  test    eax, eax
0x14000b72b  jz      short loc_14000B6B2
0x14000b72d  mov     eax, [rbp+57h+pcchString]
0x14000b730  xor     ebx, ebx
0x14000b732  mov     [r15], rsi
0x14000b735  xor     esi, esi
0x14000b737  mov     [r14], eax
0x14000b73a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000b73e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000b742  jz      short loc_14000B74A
0x14000b744  call    cs:__imp_NtClose
0x14000b74a  test    rdi, rdi
0x14000b74d  jz      short loc_14000B757
0x14000b74f  mov     rcx, rdi; Block
0x14000b752  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b757  test    rsi, rsi
0x14000b75a  jz      short loc_14000B764
0x14000b75c  mov     rcx, rsi; Block
0x14000b75f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b764  mov     eax, ebx
0x14000b766  add     rsp, 0C8h
0x14000b76d  pop     r15
0x14000b76f  pop     r14
0x14000b771  pop     rdi
0x14000b772  pop     rsi
0x14000b773  pop     rbx
0x14000b774  pop     rbp
0x14000b775  retn
```
