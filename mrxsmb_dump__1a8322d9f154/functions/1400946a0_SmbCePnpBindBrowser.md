# SmbCePnpBindBrowser

- ea: `0x1400946a0`
- end: `0x14009497c`
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
- `0x1400946a0`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x140094783`
- `ntoskrnl!IoCreateFile` at `0x140094783`
- `ntoskrnl!NtDeviceIoControlFile` at `0x1400948fd`
- `ntoskrnl!NtDeviceIoControlFile` at `0x1400948fd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400946e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400946e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400947f0`
- `ntoskrnl!ExAllocatePool2` at `0x1400947f0`
- `ntoskrnl!ZwClose` at `0x14009494e`
- `ntoskrnl!ZwClose` at `0x14009494e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400948ab`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14009493a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400948ab`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14009493a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400947be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400947be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094913`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094913`

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
      ExAcquirePushLockExclusiveEx(&qword_140070F80, 0);
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
        ExReleasePushLockExclusiveEx(&qword_140070F80, 0);
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
        ExReleasePushLockExclusiveEx(&qword_140070F80, 0);
      }
      ZwClose(FileHandle);
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400946a0  mov     r11, rsp
0x1400946a3  push    rbx
0x1400946a4  push    r12
0x1400946a6  push    r14
0x1400946a8  push    r15
0x1400946aa  sub     rsp, 0C8h
0x1400946b1  xorps   xmm0, xmm0
0x1400946b4  movzx   r15d, dl
0x1400946b8  mov     r14, rcx
0x1400946bb  lea     rdx, aDeviceLanmanda; "\\Device\\LanmanDatagramReceiver"
0x1400946c2  movups  xmmword ptr [r11-48h], xmm0
0x1400946c7  xor     r12d, r12d
0x1400946ca  lea     rcx, [r11-68h]; DestinationString
0x1400946ce  xor     eax, eax
0x1400946d0  mov     [r11+18h], r12
0x1400946d4  movups  xmmword ptr [r11-3Ch], xmm0
0x1400946d9  movups  xmmword ptr [rsp+0E8h+IoStatusBlock], xmm0
0x1400946de  movups  xmmword ptr [r11-58h], xmm0
0x1400946e3  movups  xmmword ptr [r11-68h], xmm0
0x1400946e8  call    cs:__imp_RtlInitUnicodeString
0x1400946ef  nop     dword ptr [rax+rax+00h]
0x1400946f4  mov     [rsp+0E8h+Options], r12d; Options
0x1400946f9  lea     rax, [rsp+0E8h+var_68]
0x140094701  mov     [rsp+0E8h+InternalParameters], r12; InternalParameters
0x140094706  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x14009470b  mov     [rsp+0E8h+CreateFileType], r12d; CreateFileType
0x140094710  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x140094718  mov     [rsp+0E8h+EaLength], r12d; EaLength
0x14009471d  lea     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x140094725  mov     [rsp+0E8h+EaBuffer], r12; EaBuffer
0x14009472a  xorps   xmm0, xmm0
0x14009472d  mov     [rsp+0E8h+CreateOptions], 20h ; ' '; CreateOptions
0x140094735  mov     edx, 100000h; DesiredAccess
0x14009473a  mov     [rsp+0E8h+Disposition], 1; Disposition
0x140094742  mov     [rsp+0E8h+ShareAccess], 7; ShareAccess
0x14009474a  mov     [rsp+0E8h+FileAttributes], r12d; FileAttributes
0x14009474f  mov     [rsp+0E8h+AllocationSize], r12; AllocationSize
0x140094754  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x14009475f  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], r12
0x140094767  mov     [rsp+0E8h+ObjectAttributes.Attributes], 240h
0x140094772  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rax
0x14009477a  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140094783  call    cs:__imp_IoCreateFile
0x14009478a  nop     dword ptr [rax+rax+00h]
0x14009478f  mov     ebx, eax
0x140094791  test    eax, eax
0x140094793  js      loc_14009496A
0x140094799  mov     ebx, dword ptr [rsp+0E8h+IoStatusBlock]
0x14009479d  test    ebx, ebx
0x14009479f  js      loc_14009496A
0x1400947a5  mov     [rsp+0E8h+arg_0], rbp
0x1400947ad  lea     rcx, qword_140070F80
0x1400947b4  xor     edx, edx
0x1400947b6  mov     [rsp+0E8h+arg_8], rsi
0x1400947be  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400947c5  nop     dword ptr [rax+rax+00h]
0x1400947ca  movzx   ecx, word ptr [r14]
0x1400947ce  mov     r8d, 6D537054h
0x1400947d4  movzx   eax, cs:DestinationString.Length
0x1400947db  movzx   ebp, cs:SmbCeContext.Length
0x1400947e2  add     ecx, eax
0x1400947e4  add     ebp, 64h ; 'd'
0x1400947e7  add     ebp, ecx
0x1400947e9  mov     ecx, 40h ; '@'
0x1400947ee  mov     edx, ebp
0x1400947f0  call    cs:__imp_ExAllocatePool2
0x1400947f7  nop     dword ptr [rax+rax+00h]
0x1400947fc  mov     rsi, rax
0x1400947ff  test    rax, rax
0x140094802  jz      loc_140094931
0x140094808  mov     dword ptr [rax+4], 7
0x14009480f  movzx   ecx, word ptr [r14]
0x140094813  mov     [rax+38h], ecx
0x140094816  movzx   r8d, word ptr [r14]; Size
0x14009481a  mov     rdx, [r14+8]; Src
0x14009481e  mov     [rsp+0E8h+var_28], rdi
0x140094826  lea     rdi, [rax+3Ch]
0x14009482a  mov     rcx, rdi; void *
0x14009482d  call    memmove
0x140094832  movzx   ebx, word ptr [r14]
0x140094836  mov     dword ptr [rsi+8], 1
0x14009483d  movzx   r8d, cs:DestinationString.Length; Size
0x140094845  mov     rdx, cs:DestinationString.Buffer; Src
0x14009484c  lea     rcx, [rdi+rbx]; void *
0x140094850  call    memmove
0x140094855  movzx   edx, cs:DestinationString.Length
0x14009485c  add     edx, ebx
0x14009485e  mov     [rdx+rdi], r12w
0x140094863  lea     ebx, [rdx+2]
0x140094866  mov     ecx, ebx
0x140094868  add     rcx, rdi; void *
0x14009486b  mov     [rsi+30h], rcx
0x14009486f  movzx   eax, cs:SmbCeContext.Length
0x140094876  mov     [rsi+28h], ax
0x14009487a  movzx   eax, cs:SmbCeContext.Length
0x140094881  mov     [rsi+2Ah], ax
0x140094885  movzx   r8d, cs:SmbCeContext.Length; Size
0x14009488d  mov     rdx, cs:SmbCeContext.Buffer; Src
0x140094894  call    memmove
0x140094899  movzx   eax, cs:SmbCeContext.Length
0x1400948a0  lea     rcx, qword_140070F80
0x1400948a7  xor     edx, edx
0x1400948a9  add     ebx, eax
0x1400948ab  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400948b2  nop     dword ptr [rax+rax+00h]
0x1400948b7  mov     dword ptr [rsp+0E8h+EaBuffer], r12d; OutputBufferLength
0x1400948bc  mov     eax, 13001Fh
0x1400948c1  mov     qword ptr [rsp+0E8h+CreateOptions], r12; OutputBuffer
0x1400948c6  mov     ecx, 130027h
0x1400948cb  mov     [rsp+0E8h+Disposition], ebp; InputBufferLength
0x1400948cf  test    r15b, r15b
0x1400948d2  mov     qword ptr [rsp+0E8h+ShareAccess], rsi; InputBuffer
0x1400948d7  cmovz   eax, ecx
0x1400948da  mov     [rbx+rdi], r12w
0x1400948df  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x1400948e7  xor     r9d, r9d; ApcContext
0x1400948ea  mov     [rsp+0E8h+FileAttributes], eax; IoControlCode
0x1400948ee  xor     r8d, r8d; ApcRoutine
0x1400948f1  lea     rax, [rsp+0E8h+IoStatusBlock]
0x1400948f6  xor     edx, edx; Event
0x1400948f8  mov     [rsp+0E8h+AllocationSize], rax; IoStatusBlock
0x1400948fd  call    cs:__imp_NtDeviceIoControlFile
0x140094904  nop     dword ptr [rax+rax+00h]
0x140094909  mov     edx, 6D537054h; Tag
0x14009490e  mov     rcx, rsi; P
0x140094911  mov     ebx, eax
0x140094913  call    cs:__imp_ExFreePoolWithTag
0x14009491a  nop     dword ptr [rax+rax+00h]
0x14009491f  mov     rdi, [rsp+0E8h+var_28]
0x140094927  test    ebx, ebx
0x140094929  js      short loc_140094946
0x14009492b  mov     ebx, dword ptr [rsp+0E8h+IoStatusBlock]
0x14009492f  jmp     short loc_140094946
0x140094931  xor     edx, edx
0x140094933  lea     rcx, qword_140070F80
0x14009493a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140094941  nop     dword ptr [rax+rax+00h]
0x140094946  mov     rcx, [rsp+0E8h+FileHandle]; Handle
0x14009494e  call    cs:__imp_ZwClose
0x140094955  nop     dword ptr [rax+rax+00h]
0x14009495a  mov     rsi, [rsp+0E8h+arg_8]
0x140094962  mov     rbp, [rsp+0E8h+arg_0]
0x14009496a  mov     eax, ebx
0x14009496c  add     rsp, 0C8h
0x140094973  pop     r15
0x140094975  pop     r14
0x140094977  pop     r12
0x140094979  pop     rbx
0x14009497a  retn
```
