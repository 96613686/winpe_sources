# SmbCePnpBindBrowser

- ea: `0x1400946f0`
- end: `0x1400949cc`
- name: `SmbCePnpBindBrowser`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002b9e0`

## callees

- `0x140059f00`
- `0x1400946f0`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x1400947d3`
- `ntoskrnl!IoCreateFile` at `0x1400947d3`
- `ntoskrnl!NtDeviceIoControlFile` at `0x14009494d`
- `ntoskrnl!NtDeviceIoControlFile` at `0x14009494d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094738`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094738`
- `ntoskrnl!ExAllocatePool2` at `0x140094840`
- `ntoskrnl!ExAllocatePool2` at `0x140094840`
- `ntoskrnl!ZwClose` at `0x14009499e`
- `ntoskrnl!ZwClose` at `0x14009499e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400948fb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14009498a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400948fb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14009498a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14009480e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14009480e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094963`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094963`

## pseudocode

```c
__int64 __fastcall SmbCePnpBindBrowser(const void **a1, char a2)
{
  NTSTATUS Status; // ebx
  ULONG v5; // ebp
  _DWORD *Pool2; // rax
  _DWORD *v7; // rsi
  _DWORD *v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rdx
  char *v11; // rcx
  __int64 v12; // rbx
  ULONG v13; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-78h] BYREF
  UNICODE_STRING v16; // [rsp+80h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+18h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v16 = 0;
  RtlInitUnicodeString(&v16, L"\\Device\\LanmanDatagramReceiver");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v16;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = IoCreateFile(
             &FileHandle,
             0x100000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0,
             7u,
             1u,
             0x20u,
             0,
             0,
             CreateFileTypeNone,
             0,
             0);
  if ( Status >= 0 )
  {
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
    {
      ExAcquirePushLockExclusiveEx(&qword_140070FA0, 0);
      v5 = DestinationString.Length + *(unsigned __int16 *)a1 + SmbCeContext.Length + 100;
      Pool2 = (_DWORD *)ExAllocatePool2(64, v5, 1834184788);
      v7 = Pool2;
      if ( Pool2 )
      {
        Pool2[1] = 7;
        Pool2[14] = *(unsigned __int16 *)a1;
        v8 = Pool2 + 15;
        memmove(Pool2 + 15, a1[1], *(unsigned __int16 *)a1);
        v9 = *(unsigned __int16 *)a1;
        v7[2] = 1;
        memmove((char *)v8 + v9, DestinationString.Buffer, DestinationString.Length);
        v10 = (unsigned int)v9 + DestinationString.Length;
        *(_WORD *)((char *)v8 + v10) = 0;
        LODWORD(v9) = v10 + 2;
        v11 = (char *)v8 + (unsigned int)(v10 + 2);
        *((_QWORD *)v7 + 6) = v11;
        *((_WORD *)v7 + 20) = SmbCeContext.Length;
        *((_WORD *)v7 + 21) = SmbCeContext.Length;
        memmove(v11, SmbCeContext.Buffer, SmbCeContext.Length);
        v12 = SmbCeContext.Length + (unsigned int)v9;
        ExReleasePushLockExclusiveEx(&qword_140070FA0, 0);
        v13 = 1245215;
        if ( !a2 )
          v13 = 1245223;
        *(_WORD *)((char *)v8 + v12) = 0;
        Status = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, v13, v7, v5, 0, 0);
        ExFreePoolWithTag(v7, 0x6D537054u);
        if ( Status >= 0 )
          Status = IoStatusBlock.Status;
      }
      else
      {
        ExReleasePushLockExclusiveEx(&qword_140070FA0, 0);
      }
      ZwClose(FileHandle);
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400946f0  mov     r11, rsp
0x1400946f3  push    rbx
0x1400946f4  push    r12
0x1400946f6  push    r14
0x1400946f8  push    r15
0x1400946fa  sub     rsp, 0C8h
0x140094701  xorps   xmm0, xmm0
0x140094704  movzx   r15d, dl
0x140094708  mov     r14, rcx
0x14009470b  lea     rdx, aDeviceLanmanda; "\\Device\\LanmanDatagramReceiver"
0x140094712  movups  xmmword ptr [r11-48h], xmm0
0x140094717  xor     r12d, r12d
0x14009471a  lea     rcx, [r11-68h]; DestinationString
0x14009471e  xor     eax, eax
0x140094720  mov     [r11+18h], r12
0x140094724  movups  xmmword ptr [r11-3Ch], xmm0
0x140094729  movups  xmmword ptr [rsp+0E8h+IoStatusBlock], xmm0
0x14009472e  movups  xmmword ptr [r11-58h], xmm0
0x140094733  movups  xmmword ptr [r11-68h], xmm0
0x140094738  call    cs:__imp_RtlInitUnicodeString
0x14009473f  nop     dword ptr [rax+rax+00h]
0x140094744  mov     [rsp+0E8h+Options], r12d; Options
0x140094749  lea     rax, [rsp+0E8h+var_68]
0x140094751  mov     [rsp+0E8h+InternalParameters], r12; InternalParameters
0x140094756  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x14009475b  mov     [rsp+0E8h+CreateFileType], r12d; CreateFileType
0x140094760  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x140094768  mov     [rsp+0E8h+EaLength], r12d; EaLength
0x14009476d  lea     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x140094775  mov     [rsp+0E8h+EaBuffer], r12; EaBuffer
0x14009477a  xorps   xmm0, xmm0
0x14009477d  mov     [rsp+0E8h+CreateOptions], 20h ; ' '; CreateOptions
0x140094785  mov     edx, 100000h; DesiredAccess
0x14009478a  mov     [rsp+0E8h+Disposition], 1; Disposition
0x140094792  mov     [rsp+0E8h+ShareAccess], 7; ShareAccess
0x14009479a  mov     [rsp+0E8h+FileAttributes], r12d; FileAttributes
0x14009479f  mov     [rsp+0E8h+AllocationSize], r12; AllocationSize
0x1400947a4  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x1400947af  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], r12
0x1400947b7  mov     [rsp+0E8h+ObjectAttributes.Attributes], 240h
0x1400947c2  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rax
0x1400947ca  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400947d3  call    cs:__imp_IoCreateFile
0x1400947da  nop     dword ptr [rax+rax+00h]
0x1400947df  mov     ebx, eax
0x1400947e1  test    eax, eax
0x1400947e3  js      loc_1400949BA
0x1400947e9  mov     ebx, dword ptr [rsp+0E8h+IoStatusBlock]
0x1400947ed  test    ebx, ebx
0x1400947ef  js      loc_1400949BA
0x1400947f5  mov     [rsp+0E8h+arg_0], rbp
0x1400947fd  lea     rcx, qword_140070FA0
0x140094804  xor     edx, edx
0x140094806  mov     [rsp+0E8h+arg_8], rsi
0x14009480e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140094815  nop     dword ptr [rax+rax+00h]
0x14009481a  movzx   ecx, word ptr [r14]
0x14009481e  mov     r8d, 6D537054h
0x140094824  movzx   eax, cs:DestinationString.Length
0x14009482b  movzx   ebp, cs:SmbCeContext.Length
0x140094832  add     ecx, eax
0x140094834  add     ebp, 64h ; 'd'
0x140094837  add     ebp, ecx
0x140094839  mov     ecx, 40h ; '@'
0x14009483e  mov     edx, ebp
0x140094840  call    cs:__imp_ExAllocatePool2
0x140094847  nop     dword ptr [rax+rax+00h]
0x14009484c  mov     rsi, rax
0x14009484f  test    rax, rax
0x140094852  jz      loc_140094981
0x140094858  mov     dword ptr [rax+4], 7
0x14009485f  movzx   ecx, word ptr [r14]
0x140094863  mov     [rax+38h], ecx
0x140094866  movzx   r8d, word ptr [r14]; Size
0x14009486a  mov     rdx, [r14+8]; Src
0x14009486e  mov     [rsp+0E8h+var_28], rdi
0x140094876  lea     rdi, [rax+3Ch]
0x14009487a  mov     rcx, rdi; void *
0x14009487d  call    memmove
0x140094882  movzx   ebx, word ptr [r14]
0x140094886  mov     dword ptr [rsi+8], 1
0x14009488d  movzx   r8d, cs:DestinationString.Length; Size
0x140094895  mov     rdx, cs:DestinationString.Buffer; Src
0x14009489c  lea     rcx, [rdi+rbx]; void *
0x1400948a0  call    memmove
0x1400948a5  movzx   edx, cs:DestinationString.Length
0x1400948ac  add     edx, ebx
0x1400948ae  mov     [rdx+rdi], r12w
0x1400948b3  lea     ebx, [rdx+2]
0x1400948b6  mov     ecx, ebx
0x1400948b8  add     rcx, rdi; void *
0x1400948bb  mov     [rsi+30h], rcx
0x1400948bf  movzx   eax, cs:SmbCeContext.Length
0x1400948c6  mov     [rsi+28h], ax
0x1400948ca  movzx   eax, cs:SmbCeContext.Length
0x1400948d1  mov     [rsi+2Ah], ax
0x1400948d5  movzx   r8d, cs:SmbCeContext.Length; Size
0x1400948dd  mov     rdx, cs:SmbCeContext.Buffer; Src
0x1400948e4  call    memmove
0x1400948e9  movzx   eax, cs:SmbCeContext.Length
0x1400948f0  lea     rcx, qword_140070FA0
0x1400948f7  xor     edx, edx
0x1400948f9  add     ebx, eax
0x1400948fb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140094902  nop     dword ptr [rax+rax+00h]
0x140094907  mov     dword ptr [rsp+0E8h+EaBuffer], r12d; OutputBufferLength
0x14009490c  mov     eax, 13001Fh
0x140094911  mov     qword ptr [rsp+0E8h+CreateOptions], r12; OutputBuffer
0x140094916  mov     ecx, 130027h
0x14009491b  mov     [rsp+0E8h+Disposition], ebp; InputBufferLength
0x14009491f  test    r15b, r15b
0x140094922  mov     qword ptr [rsp+0E8h+ShareAccess], rsi; InputBuffer
0x140094927  cmovz   eax, ecx
0x14009492a  mov     [rbx+rdi], r12w
0x14009492f  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x140094937  xor     r9d, r9d; ApcContext
0x14009493a  mov     [rsp+0E8h+FileAttributes], eax; IoControlCode
0x14009493e  xor     r8d, r8d; ApcRoutine
0x140094941  lea     rax, [rsp+0E8h+IoStatusBlock]
0x140094946  xor     edx, edx; Event
0x140094948  mov     [rsp+0E8h+AllocationSize], rax; IoStatusBlock
0x14009494d  call    cs:__imp_NtDeviceIoControlFile
0x140094954  nop     dword ptr [rax+rax+00h]
0x140094959  mov     edx, 6D537054h; Tag
0x14009495e  mov     rcx, rsi; P
0x140094961  mov     ebx, eax
0x140094963  call    cs:__imp_ExFreePoolWithTag
0x14009496a  nop     dword ptr [rax+rax+00h]
0x14009496f  mov     rdi, [rsp+0E8h+var_28]
0x140094977  test    ebx, ebx
0x140094979  js      short loc_140094996
0x14009497b  mov     ebx, dword ptr [rsp+0E8h+IoStatusBlock]
0x14009497f  jmp     short loc_140094996
0x140094981  xor     edx, edx
0x140094983  lea     rcx, qword_140070FA0
0x14009498a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140094991  nop     dword ptr [rax+rax+00h]
0x140094996  mov     rcx, [rsp+0E8h+FileHandle]; Handle
0x14009499e  call    cs:__imp_ZwClose
0x1400949a5  nop     dword ptr [rax+rax+00h]
0x1400949aa  mov     rsi, [rsp+0E8h+arg_8]
0x1400949b2  mov     rbp, [rsp+0E8h+arg_0]
0x1400949ba  mov     eax, ebx
0x1400949bc  add     rsp, 0C8h
0x1400949c3  pop     r15
0x1400949c5  pop     r14
0x1400949c7  pop     r12
0x1400949c9  pop     rbx
0x1400949ca  retn
```
