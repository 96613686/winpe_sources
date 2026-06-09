# SockCheckAndInitAsyncConnectHelper

- ea: `0x180019054`
- end: `0x1800192c9`
- name: `SockCheckAndInitAsyncConnectHelper`
- size: `629`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012c10`
- `0x180027140`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x180019054`
- `0x18001e14c`
- `0x18001ed78`
- `0x18003ae8c`

## import_xrefs

- `ntdll!NtSetInformationObject` at `0x1800191d4`
- `ntdll!NtSetInformationObject` at `0x1800191d4`
- `ntdll!NtSetInformationFile` at `0x1800191a6`
- `ntdll!NtSetInformationFile` at `0x1800191a6`
- `ntdll!NtClose` at `0x180019296`
- `ntdll!NtClose` at `0x180019296`
- `ntdll!NtCreateFile` at `0x180019139`
- `ntdll!NtCreateFile` at `0x180019242`
- `ntdll!NtCreateFile` at `0x180019139`
- `ntdll!NtCreateFile` at `0x180019242`
- `ntdll!RtlInitUnicodeString` at `0x1800190d4`
- `ntdll!RtlInitUnicodeString` at `0x1800190d4`

## pseudocode

```c
__int64 SockCheckAndInitAsyncConnectHelper()
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  NTSTATUS v5; // ebx
  unsigned __int64 v6; // rax
  HANDLE v7; // rax
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  __int128 FileInformation; // [rsp+60h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+27h] BYREF
  __int16 ObjectInformation; // [rsp+D0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+D8h] [rbp+6Fh] BYREF

  FileHandle = 0;
  ObjectInformation = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( SockAsyncConnectHelperHandle )
    return 1;
  SockAcquireRwLockExclusive();
  if ( SockAsyncConnectHelperHandle )
  {
    v9 = 1;
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Afd\\AsyncConnectHlp");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 3u, 0, 0, 0);
  v6 = (unsigned int)(v5 + 1073741810);
  if ( (unsigned int)v6 <= 0x2C )
  {
    v2 = 0x104000000001LL;
    if ( _bittest64(&v2, v6) )
    {
      if ( !(unsigned int)SockDemandStartAfd() )
        v5 = NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 3u, 0, 0, 0);
    }
  }
  if ( v5 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 25, WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids, (unsigned int)v5);
    goto LABEL_17;
  }
  v7 = SockAsyncQueuePort;
  if ( !SockAsyncQueuePort )
  {
    if ( (int)SockCreateAsyncQueuePort() < 0 )
    {
LABEL_17:
      v9 = 0;
      goto LABEL_10;
    }
    v7 = SockAsyncQueuePort;
  }
  *(_QWORD *)&FileInformation = v7;
  *((_QWORD *)&FileInformation + 1) = SockAsyncConnectCompletion;
  v8 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x10u, FileCompletionInformation);
  if ( v8 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 26, WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids, (unsigned int)v8);
    NtClose(FileHandle);
    goto LABEL_17;
  }
  v9 = 1;
  ObjectInformation = 256;
  NtSetInformationObject(FileHandle, ObjectHandleFlagInformation, &ObjectInformation, 2u);
  v2 = (__int64)FileHandle;
  SockAsyncConnectHelperHandle = FileHandle;
LABEL_10:
  SockReleaseRwLockExclusive(v2, v1, v3, v4);
  return v9;
}

```

## disassembly

```asm
0x180019054  mov     [rsp-8+arg_10], rbx
0x180019059  mov     [rsp-8+arg_18], rdi
0x18001905e  push    rbp
0x18001905f  lea     rbp, [rsp-57h]
0x180019064  sub     rsp, 0C0h
0x18001906b  xorps   xmm0, xmm0
0x18001906e  xor     edi, edi
0x180019070  xor     eax, eax
0x180019072  mov     [rbp+57h+FileHandle], rdi
0x180019076  cmp     cs:SockAsyncConnectHelperHandle, rdi
0x18001907d  xorps   xmm1, xmm1
0x180019080  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180019084  mov     [rbp+57h+ObjectInformation], di
0x180019088  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001908c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180019090  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180019094  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180019098  movups  [rbp+57h+FileInformation], xmm1
0x18001909c  jz      short loc_1800190B7
0x18001909e  lea     eax, [rdi+1]
0x1800190a1  lea     r11, [rsp+0C0h+var_s0]
0x1800190a9  mov     rbx, [r11+20h]
0x1800190ad  mov     rdi, [r11+28h]
0x1800190b1  mov     rsp, r11
0x1800190b4  pop     rbp
0x1800190b5  retn
0x1800190b7  call    SockAcquireRwLockExclusive
0x1800190bc  cmp     cs:SockAsyncConnectHelperHandle, rdi
0x1800190c3  jnz     loc_1800191F7
0x1800190c9  lea     rdx, aDeviceAfdAsync_0; "\\Device\\Afd\\AsyncConnectHlp"
0x1800190d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800190d4  call    cs:__imp_RtlInitUnicodeString
0x1800190db  nop     dword ptr [rax+rax+00h]
0x1800190e0  mov     [rsp+0C0h+EaLength], edi; EaLength
0x1800190e4  lea     rax, [rbp+57h+DestinationString]
0x1800190e8  mov     [rsp+0C0h+EaBuffer], rdi; EaBuffer
0x1800190ed  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800190f1  mov     [rsp+0C0h+CreateOptions], edi; CreateOptions
0x1800190f5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800190f9  mov     [rsp+0C0h+CreateDisposition], 3; CreateDisposition
0x180019101  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180019105  mov     [rsp+0C0h+ShareAccess], 3; ShareAccess
0x18001910d  xorps   xmm0, xmm0
0x180019110  mov     [rsp+0C0h+FileAttributes], edi; FileAttributes
0x180019114  mov     edx, 0C0100000h; DesiredAccess
0x180019119  mov     [rsp+0C0h+AllocationSize], rdi; AllocationSize
0x18001911e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180019125  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180019129  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180019130  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180019134  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180019139  call    cs:__imp_NtCreateFile
0x180019140  nop     dword ptr [rax+rax+00h]
0x180019145  mov     ebx, eax
0x180019147  add     eax, 3FFFFFF2h
0x18001914c  cmp     eax, 2Ch ; ','
0x18001914f  ja      short loc_180019165
0x180019151  mov     rcx, 104000000001h
0x18001915b  bt      rcx, rax
0x18001915f  jb      loc_1800191FE
0x180019165  test    ebx, ebx
0x180019167  js      loc_180019255
0x18001916d  mov     rax, cs:SockAsyncQueuePort
0x180019174  test    rax, rax
0x180019177  jz      loc_1800192A9
0x18001917d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180019181  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180019185  mov     qword ptr [rbp+57h+FileInformation], rax
0x180019189  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001918d  lea     rax, SockAsyncConnectCompletion
0x180019194  mov     dword ptr [rsp+0C0h+AllocationSize], 1Eh; FileInformationClass
0x18001919c  mov     r9d, 10h; Length
0x1800191a2  mov     qword ptr [rbp+57h+FileInformation+8], rax
0x1800191a6  call    cs:__imp_NtSetInformationFile
0x1800191ad  nop     dword ptr [rax+rax+00h]
0x1800191b2  test    eax, eax
0x1800191b4  js      loc_1800192BE
0x1800191ba  mov     rcx, [rbp+57h+FileHandle]; ObjectHandle
0x1800191be  lea     r8, [rbp+57h+ObjectInformation]; ObjectInformation
0x1800191c2  mov     ebx, 1
0x1800191c7  mov     [rbp+57h+ObjectInformation], 100h
0x1800191cd  lea     r9d, [rbx+1]; Length
0x1800191d1  lea     edx, [rbx+3]; ObjectInformationClass
0x1800191d4  call    cs:__imp_NtSetInformationObject
0x1800191db  nop     dword ptr [rax+rax+00h]
0x1800191e0  mov     rcx, [rbp+57h+FileHandle]
0x1800191e4  mov     cs:SockAsyncConnectHelperHandle, rcx
0x1800191eb  call    SockReleaseRwLockExclusive
0x1800191f0  mov     eax, ebx
0x1800191f2  jmp     loc_1800190A1
0x1800191f7  mov     ebx, 1
0x1800191fc  jmp     short loc_1800191EB
0x1800191fe  call    SockDemandStartAfd
0x180019203  test    eax, eax
0x180019205  jnz     loc_180019165
0x18001920b  mov     [rsp+0C0h+EaLength], edi; EaLength
0x18001920f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180019213  mov     [rsp+0C0h+EaBuffer], rdi; EaBuffer
0x180019218  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001921c  mov     [rsp+0C0h+CreateOptions], edi; CreateOptions
0x180019220  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180019224  mov     [rsp+0C0h+CreateDisposition], 3; CreateDisposition
0x18001922c  mov     edx, 0C0100000h; DesiredAccess
0x180019231  mov     [rsp+0C0h+ShareAccess], 3; ShareAccess
0x180019239  mov     [rsp+0C0h+FileAttributes], edi; FileAttributes
0x18001923d  mov     [rsp+0C0h+AllocationSize], rdi; AllocationSize
0x180019242  call    cs:__imp_NtCreateFile
0x180019249  nop     dword ptr [rax+rax+00h]
0x18001924e  mov     ebx, eax
0x180019250  jmp     loc_180019165
0x180019255  test    byte ptr cs:xmmword_180063D60, 2
0x18001925c  jz      short loc_1800192A2
0x18001925e  mov     edx, 19h
0x180019263  lea     r8, WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids
0x18001926a  mov     ecx, 401h
0x18001926f  mov     r9d, ebx
0x180019272  call    WPP_SF_d
0x180019277  jmp     short loc_1800192A2
0x180019279  mov     edx, 1Ah
0x18001927e  lea     r8, WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids
0x180019285  mov     ecx, 401h
0x18001928a  mov     r9d, eax
0x18001928d  call    WPP_SF_d
0x180019292  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180019296  call    cs:__imp_NtClose
0x18001929d  nop     dword ptr [rax+rax+00h]
0x1800192a2  mov     ebx, edi
0x1800192a4  jmp     loc_1800191EB
0x1800192a9  call    SockCreateAsyncQueuePort
0x1800192ae  test    eax, eax
0x1800192b0  js      short loc_1800192A2
0x1800192b2  mov     rax, cs:SockAsyncQueuePort
0x1800192b9  jmp     loc_18001917D
0x1800192be  test    byte ptr cs:xmmword_180063D60, 2
0x1800192c5  jz      short loc_180019292
0x1800192c7  jmp     short loc_180019279
```
