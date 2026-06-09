# GetVolumeDeviceName(ushort const *,ushort * *,long *)

- ea: `0x14000b2f0`
- end: `0x14000b521`
- name: `?GetVolumeDeviceName@@YAJPEBGPEAPEAGPEAJ@Z`
- size: `561`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000abe4`

## callees

- `0x1400028b4`
- `0x1400028f4`
- `0x1400030d3`
- `0x14000b2f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000b4c4`
- `msvcrt!memcpy_s` at `0x14000b4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b4e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b4e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b41c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b476`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b41c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b476`
- `ntdll!NtCreateFile` at `0x14000b3a8`
- `ntdll!NtCreateFile` at `0x14000b3a8`
- `ntdll!RtlNtStatusToDosError` at `0x14000b3b6`
- `ntdll!RtlNtStatusToDosError` at `0x14000b3b6`
- `ntdll!RtlInitUnicodeString` at `0x14000b345`
- `ntdll!RtlInitUnicodeString` at `0x14000b345`

## pseudocode

```c
__int64 __fastcall GetVolumeDeviceName(PCWSTR SourceString, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned __int16 *v3; // rsi
  int v6; // eax
  unsigned __int16 *v7; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  DWORD v10; // ebx
  unsigned int v11; // r14d
  unsigned __int16 *v12; // rax
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  DWORD BytesReturned; // [rsp+E8h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF

  FileHandle = (void *)-1LL;
  v3 = 0;
  *a2 = 0;
  BytesReturned = 0;
  *a3 = 0;
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
  v7 = (unsigned __int16 *)operator new(4u);
  if ( !v7 )
    goto LABEL_7;
  if ( DeviceIoControl(FileHandle, 0x4D0008u, 0, 0, v7, 4u, &BytesReturned, 0)
    || (LastError = GetLastError(), v9 = LastError, LastError == 234) )
  {
    v10 = *v7 + 4;
    operator delete(v7);
    v7 = (unsigned __int16 *)operator new(v10);
    if ( v7 )
    {
      if ( DeviceIoControl(FileHandle, 0x4D0008u, 0, 0, v7, v10, &BytesReturned, 0) )
      {
        v11 = *v7 + 2;
        v12 = (unsigned __int16 *)operator new(v11);
        v3 = v12;
        if ( !v12 )
          goto LABEL_7;
        memset_0(v12, 0, v11);
        if ( !memcpy_s(v3, v11, v7 + 1, *v7) )
        {
          v9 = 0;
          *a2 = v3;
          v3 = 0;
          *a3 = v11;
          goto LABEL_16;
        }
      }
      LastError = GetLastError();
      goto LABEL_3;
    }
LABEL_7:
    v9 = -2147024882;
    goto LABEL_16;
  }
LABEL_4:
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_16:
  if ( FileHandle != (void *)-1LL )
    CloseHandle(FileHandle);
  if ( v3 )
    operator delete(v3);
  if ( v7 )
    operator delete(v7);
  return v9;
}

```

## disassembly

```asm
0x14000b2f0  mov     [rsp-8+arg_0], rbx
0x14000b2f5  mov     [rsp-8+arg_18], rsi
0x14000b2fa  push    rbp
0x14000b2fb  push    rdi
0x14000b2fc  push    r12
0x14000b2fe  push    r14
0x14000b300  push    r15
0x14000b302  lea     rbp, [rsp-37h]
0x14000b307  sub     rsp, 0B0h
0x14000b30e  xorps   xmm0, xmm0
0x14000b311  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14000b319  xor     esi, esi
0x14000b31b  mov     r12, rdx
0x14000b31e  mov     [rdx], rsi
0x14000b321  mov     r15, r8
0x14000b324  mov     rdx, rcx; SourceString
0x14000b327  mov     [rbp+57h+BytesReturned], esi
0x14000b32a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000b32e  mov     [r8], esi
0x14000b331  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000b335  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000b339  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b33d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000b341  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000b345  call    cs:__imp_RtlInitUnicodeString
0x14000b34b  mov     [rsp+0D0h+EaLength], esi; EaLength
0x14000b34f  lea     rax, [rbp+57h+DestinationString]
0x14000b353  mov     [rsp+0D0h+EaBuffer], rsi; EaBuffer
0x14000b358  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000b35c  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x14000b364  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000b368  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x14000b370  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000b374  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x14000b37c  xorps   xmm0, xmm0
0x14000b37f  mov     [rsp+0D0h+FileAttributes], esi; FileAttributes
0x14000b383  mov     edx, 100080h; DesiredAccess
0x14000b388  mov     [rsp+0D0h+AllocationSize], rsi; AllocationSize
0x14000b38d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000b394  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000b398  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14000b39f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000b3a3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b3a8  call    cs:__imp_NtCreateFile
0x14000b3ae  test    eax, eax
0x14000b3b0  jns     short loc_14000B3D4
0x14000b3b2  xor     edi, edi
0x14000b3b4  mov     ecx, eax; Status
0x14000b3b6  call    cs:__imp_RtlNtStatusToDosError
0x14000b3bc  mov     ebx, eax
0x14000b3be  test    eax, eax
0x14000b3c0  jle     loc_14000B4D9
0x14000b3c6  movzx   ebx, ax
0x14000b3c9  or      ebx, 80070000h
0x14000b3cf  jmp     loc_14000B4D9
0x14000b3d4  mov     ebx, 4
0x14000b3d9  mov     ecx, ebx; Size
0x14000b3db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b3e0  mov     rdi, rax
0x14000b3e3  test    rax, rax
0x14000b3e6  jnz     short loc_14000B3F2
0x14000b3e8  mov     ebx, 8007000Eh
0x14000b3ed  jmp     loc_14000B4D9
0x14000b3f2  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x14000b3f6  lea     rax, [rbp+57h+BytesReturned]
0x14000b3fa  mov     qword ptr [rsp+0D0h+CreateDisposition], rsi; lpOverlapped
0x14000b3ff  mov     r14d, 4D0008h
0x14000b405  mov     qword ptr [rsp+0D0h+ShareAccess], rax; lpBytesReturned
0x14000b40a  xor     r9d, r9d; nInBufferSize
0x14000b40d  mov     [rsp+0D0h+FileAttributes], ebx; nOutBufferSize
0x14000b411  xor     r8d, r8d; lpInBuffer
0x14000b414  mov     edx, r14d; dwIoControlCode
0x14000b417  mov     [rsp+0D0h+AllocationSize], rdi; lpOutBuffer
0x14000b41c  call    cs:__imp_DeviceIoControl
0x14000b422  test    eax, eax
0x14000b424  jnz     short loc_14000B435
0x14000b426  call    cs:__imp_GetLastError
0x14000b42c  mov     ebx, eax
0x14000b42e  cmp     eax, 0EAh
0x14000b433  jnz     short loc_14000B3BE
0x14000b435  movzx   ebx, word ptr [rdi]
0x14000b438  mov     rcx, rdi; Block
0x14000b43b  add     ebx, 4
0x14000b43e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b443  mov     ecx, ebx; Size
0x14000b445  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b44a  mov     rdi, rax
0x14000b44d  test    rax, rax
0x14000b450  jz      short loc_14000B3E8
0x14000b452  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x14000b456  lea     rax, [rbp+57h+BytesReturned]
0x14000b45a  mov     qword ptr [rsp+0D0h+CreateDisposition], rsi; lpOverlapped
0x14000b45f  xor     r9d, r9d; nInBufferSize
0x14000b462  mov     qword ptr [rsp+0D0h+ShareAccess], rax; lpBytesReturned
0x14000b467  xor     r8d, r8d; lpInBuffer
0x14000b46a  mov     [rsp+0D0h+FileAttributes], ebx; nOutBufferSize
0x14000b46e  mov     edx, r14d; dwIoControlCode
0x14000b471  mov     [rsp+0D0h+AllocationSize], rdi; lpOutBuffer
0x14000b476  call    cs:__imp_DeviceIoControl
0x14000b47c  test    eax, eax
0x14000b47e  jnz     short loc_14000B48B
0x14000b480  call    cs:__imp_GetLastError
0x14000b486  jmp     loc_14000B3BC
0x14000b48b  movzx   r14d, word ptr [rdi]
0x14000b48f  add     r14d, 2
0x14000b493  mov     ecx, r14d; Size
0x14000b496  mov     ebx, r14d
0x14000b499  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b49e  mov     rsi, rax
0x14000b4a1  test    rax, rax
0x14000b4a4  jz      loc_14000B3E8
0x14000b4aa  mov     r8d, ebx; Size
0x14000b4ad  xor     edx, edx; Val
0x14000b4af  mov     rcx, rax; void *
0x14000b4b2  call    memset_0
0x14000b4b7  movzx   r9d, word ptr [rdi]; SourceSize
0x14000b4bb  lea     r8, [rdi+2]; Source
0x14000b4bf  mov     edx, ebx; DestinationSize
0x14000b4c1  mov     rcx, rsi; Destination
0x14000b4c4  call    cs:__imp_memcpy_s
0x14000b4ca  test    eax, eax
0x14000b4cc  jnz     short loc_14000B480
0x14000b4ce  xor     ebx, ebx
0x14000b4d0  mov     [r12], rsi
0x14000b4d4  xor     esi, esi
0x14000b4d6  mov     [r15], r14d
0x14000b4d9  mov     rcx, [rbp+57h+FileHandle]; hObject
0x14000b4dd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000b4e1  jz      short loc_14000B4E9
0x14000b4e3  call    cs:__imp_CloseHandle
0x14000b4e9  test    rsi, rsi
0x14000b4ec  jz      short loc_14000B4F6
0x14000b4ee  mov     rcx, rsi; Block
0x14000b4f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b4f6  test    rdi, rdi
0x14000b4f9  jz      short loc_14000B503
0x14000b4fb  mov     rcx, rdi; Block
0x14000b4fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b503  lea     r11, [rsp+0D0h+var_20]
0x14000b50b  mov     eax, ebx
0x14000b50d  mov     rbx, [r11+30h]
0x14000b511  mov     rsi, [r11+48h]
0x14000b515  mov     rsp, r11
0x14000b518  pop     r15
0x14000b51a  pop     r14
0x14000b51c  pop     r12
0x14000b51e  pop     rdi
0x14000b51f  pop     rbp
0x14000b520  retn
```
