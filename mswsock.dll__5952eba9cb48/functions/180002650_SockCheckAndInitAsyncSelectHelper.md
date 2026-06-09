# SockCheckAndInitAsyncSelectHelper

- ea: `0x180002650`
- end: `0x1800028af`
- name: `SockCheckAndInitAsyncSelectHelper`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002240`

## callees

- `0x180002650`
- `0x18000ca20`
- `0x18000db30`
- `0x18001e14c`
- `0x18001ed78`
- `0x18003ae8c`

## import_xrefs

- `ntdll!NtSetInformationObject` at `0x180002886`
- `ntdll!NtSetInformationObject` at `0x180002886`
- `ntdll!NtSetInformationFile` at `0x18000284e`
- `ntdll!NtSetInformationFile` at `0x18000284e`
- `ntdll!NtClose` at `0x1800027f6`
- `ntdll!NtClose` at `0x1800027f6`
- `ntdll!NtCreateFile` at `0x18000273b`
- `ntdll!NtCreateFile` at `0x1800027a3`
- `ntdll!NtCreateFile` at `0x18000273b`
- `ntdll!NtCreateFile` at `0x1800027a3`
- `ntdll!RtlInitUnicodeString` at `0x1800026d6`
- `ntdll!RtlInitUnicodeString` at `0x1800026d6`

## pseudocode

```c
__int64 SockCheckAndInitAsyncSelectHelper()
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // ebx
  NTSTATUS v6; // ebx
  unsigned __int64 v7; // rax
  HANDLE v8; // rax
  NTSTATUS v9; // eax
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
  if ( SockAsyncSelectHelperHandle )
    return 1;
  SockAcquireRwLockExclusive();
  if ( !SockAsyncSelectHelperHandle )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Afd\\AsyncSelectHlp");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 66;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 3u, 0, 0, 0);
    v7 = (unsigned int)(v6 + 1073741810);
    if ( (unsigned int)v7 <= 0x2C )
    {
      v2 = 0x104000000001LL;
      if ( _bittest64(&v2, v7) )
      {
        if ( !(unsigned int)SockDemandStartAfd() )
          v6 = NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 3u, 0, 0, 0);
      }
    }
    if ( v6 < 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 41, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids, (unsigned int)v6);
      goto LABEL_13;
    }
    v8 = SockAsyncQueuePort;
    if ( !SockAsyncQueuePort )
    {
      if ( (int)SockCreateAsyncQueuePort() < 0 )
      {
LABEL_12:
        NtClose(FileHandle);
LABEL_13:
        v5 = 0;
        goto LABEL_21;
      }
      v8 = SockAsyncQueuePort;
    }
    *(_QWORD *)&FileInformation = v8;
    *((_QWORD *)&FileInformation + 1) = SockAsyncSelectCompletion;
    v9 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x10u, FileCompletionInformation);
    if ( v9 >= 0 )
    {
      v5 = 1;
      ObjectInformation = 256;
      NtSetInformationObject(FileHandle, ObjectHandleFlagInformation, &ObjectInformation, 2u);
      v2 = (__int64)FileHandle;
      SockAsyncSelectHelperHandle = FileHandle;
      SockAsyncSelectCalled = 1;
      goto LABEL_21;
    }
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 42, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids, (unsigned int)v9);
    goto LABEL_12;
  }
  v5 = 1;
LABEL_21:
  SockReleaseRwLockExclusive(v2, v1, v3, v4);
  return v5;
}

```

## disassembly

```asm
0x180002650  mov     [rsp-8+arg_10], rbx
0x180002655  mov     [rsp-8+arg_18], rdi
0x18000265a  push    rbp
0x18000265b  lea     rbp, [rsp-57h]
0x180002660  sub     rsp, 0C0h
0x180002667  xorps   xmm0, xmm0
0x18000266a  xor     edi, edi
0x18000266c  xor     eax, eax
0x18000266e  mov     [rbp+57h+FileHandle], rdi
0x180002672  cmp     cs:SockAsyncSelectHelperHandle, rdi
0x180002679  xorps   xmm1, xmm1
0x18000267c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180002680  mov     [rbp+57h+ObjectInformation], di
0x180002684  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180002688  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000268c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180002690  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180002694  movups  [rbp+57h+FileInformation], xmm1
0x180002698  jz      short loc_1800026B3
0x18000269a  lea     eax, [rdi+1]
0x18000269d  lea     r11, [rsp+0C0h+var_s0]
0x1800026a5  mov     rbx, [r11+20h]
0x1800026a9  mov     rdi, [r11+28h]
0x1800026ad  mov     rsp, r11
0x1800026b0  pop     rbp
0x1800026b1  retn
0x1800026b3  call    SockAcquireRwLockExclusive
0x1800026b8  cmp     cs:SockAsyncSelectHelperHandle, rdi
0x1800026bf  jz      short loc_1800026CB
0x1800026c1  mov     ebx, 1
0x1800026c6  jmp     loc_1800028A3
0x1800026cb  lea     rdx, SourceString; "\\Device\\Afd\\AsyncSelectHlp"
0x1800026d2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800026d6  call    cs:__imp_RtlInitUnicodeString
0x1800026dd  nop     dword ptr [rax+rax+00h]
0x1800026e2  mov     [rsp+0C0h+EaLength], edi; EaLength
0x1800026e6  lea     rax, [rbp+57h+DestinationString]
0x1800026ea  mov     [rsp+0C0h+EaBuffer], rdi; EaBuffer
0x1800026ef  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800026f3  mov     [rsp+0C0h+CreateOptions], edi; CreateOptions
0x1800026f7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800026fb  mov     [rsp+0C0h+CreateDisposition], 3; CreateDisposition
0x180002703  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002707  mov     [rsp+0C0h+ShareAccess], 3; ShareAccess
0x18000270f  xorps   xmm0, xmm0
0x180002712  mov     [rsp+0C0h+FileAttributes], edi; FileAttributes
0x180002716  mov     edx, 0C0100000h; DesiredAccess
0x18000271b  mov     [rsp+0C0h+AllocationSize], rdi; AllocationSize
0x180002720  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180002727  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18000272b  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x180002732  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180002736  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000273b  call    cs:__imp_NtCreateFile
0x180002742  nop     dword ptr [rax+rax+00h]
0x180002747  mov     ebx, eax
0x180002749  add     eax, 3FFFFFF2h
0x18000274e  cmp     eax, 2Ch ; ','
0x180002751  ja      short loc_1800027B1
0x180002753  mov     rcx, 104000000001h
0x18000275d  bt      rcx, rax
0x180002761  jnb     short loc_1800027B1
0x180002763  call    SockDemandStartAfd
0x180002768  test    eax, eax
0x18000276a  jnz     short loc_1800027B1
0x18000276c  mov     [rsp+0C0h+EaLength], edi; EaLength
0x180002770  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180002774  mov     [rsp+0C0h+EaBuffer], rdi; EaBuffer
0x180002779  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000277d  mov     [rsp+0C0h+CreateOptions], edi; CreateOptions
0x180002781  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002785  mov     [rsp+0C0h+CreateDisposition], 3; CreateDisposition
0x18000278d  mov     edx, 0C0100000h; DesiredAccess
0x180002792  mov     [rsp+0C0h+ShareAccess], 3; ShareAccess
0x18000279a  mov     [rsp+0C0h+FileAttributes], edi; FileAttributes
0x18000279e  mov     [rsp+0C0h+AllocationSize], rdi; AllocationSize
0x1800027a3  call    cs:__imp_NtCreateFile
0x1800027aa  nop     dword ptr [rax+rax+00h]
0x1800027af  mov     ebx, eax
0x1800027b1  test    ebx, ebx
0x1800027b3  jns     short loc_180002809
0x1800027b5  test    byte ptr cs:xmmword_180063D60, 2
0x1800027bc  jz      short loc_180002802
0x1800027be  mov     edx, 29h ; ')'
0x1800027c3  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x1800027ca  mov     ecx, 401h
0x1800027cf  mov     r9d, ebx
0x1800027d2  call    WPP_SF_d
0x1800027d7  jmp     short loc_180002802
0x1800027d9  mov     edx, 2Ah ; '*'
0x1800027de  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x1800027e5  mov     ecx, 401h
0x1800027ea  mov     r9d, eax
0x1800027ed  call    WPP_SF_d
0x1800027f2  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800027f6  call    cs:__imp_NtClose
0x1800027fd  nop     dword ptr [rax+rax+00h]
0x180002802  mov     ebx, edi
0x180002804  jmp     loc_1800028A3
0x180002809  mov     rax, cs:SockAsyncQueuePort
0x180002810  test    rax, rax
0x180002813  jnz     short loc_180002825
0x180002815  call    SockCreateAsyncQueuePort
0x18000281a  test    eax, eax
0x18000281c  js      short loc_1800027F2
0x18000281e  mov     rax, cs:SockAsyncQueuePort
0x180002825  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002829  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000282d  mov     qword ptr [rbp+57h+FileInformation], rax
0x180002831  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180002835  lea     rax, SockAsyncSelectCompletion
0x18000283c  mov     dword ptr [rsp+0C0h+AllocationSize], 1Eh; FileInformationClass
0x180002844  mov     r9d, 10h; Length
0x18000284a  mov     qword ptr [rbp+57h+FileInformation+8], rax
0x18000284e  call    cs:__imp_NtSetInformationFile
0x180002855  nop     dword ptr [rax+rax+00h]
0x18000285a  test    eax, eax
0x18000285c  jns     short loc_18000286C
0x18000285e  test    byte ptr cs:xmmword_180063D60, 2
0x180002865  jz      short loc_1800027F2
0x180002867  jmp     loc_1800027D9
0x18000286c  mov     rcx, [rbp+57h+FileHandle]; ObjectHandle
0x180002870  lea     r8, [rbp+57h+ObjectInformation]; ObjectInformation
0x180002874  mov     ebx, 1
0x180002879  mov     [rbp+57h+ObjectInformation], 100h
0x18000287f  lea     r9d, [rbx+1]; Length
0x180002883  lea     edx, [rbx+3]; ObjectInformationClass
0x180002886  call    cs:__imp_NtSetInformationObject
0x18000288d  nop     dword ptr [rax+rax+00h]
0x180002892  mov     rcx, [rbp+57h+FileHandle]
0x180002896  mov     cs:SockAsyncSelectHelperHandle, rcx
0x18000289d  mov     cs:SockAsyncSelectCalled, bl
0x1800028a3  call    SockReleaseRwLockExclusive
0x1800028a8  mov     eax, ebx
0x1800028aa  jmp     loc_18000269D
```
