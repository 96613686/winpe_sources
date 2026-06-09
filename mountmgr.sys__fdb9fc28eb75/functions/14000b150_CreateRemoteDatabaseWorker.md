# CreateRemoteDatabaseWorker

- ea: `0x14000b150`
- end: `0x14000b3cd`
- name: `CreateRemoteDatabaseWorker`
- size: `637`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject, _QWORD *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x14000b150`
- `0x14000ba94`

## import_xrefs

- `ntoskrnl!RtlCreateSystemVolumeInformationFolder` at `0x14000b20f`
- `ntoskrnl!RtlCreateSystemVolumeInformationFolder` at `0x14000b20f`
- `ntoskrnl!KeSetEvent` at `0x14000b3b0`
- `ntoskrnl!KeSetEvent` at `0x14000b3b0`
- `ntoskrnl!ExAllocatePool2` at `0x14000b1be`
- `ntoskrnl!ExAllocatePool2` at `0x14000b1be`
- `ntoskrnl!IoCreateFile` at `0x14000b30c`
- `ntoskrnl!IoCreateFile` at `0x14000b30c`
- `ntoskrnl!IoFreeWorkItem` at `0x14000b389`
- `ntoskrnl!IoFreeWorkItem` at `0x14000b389`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b36e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b36e`

## pseudocode

```c
void __fastcall CreateRemoteDatabaseWorker(PDEVICE_OBJECT DeviceObject, _QWORD *Context)
{
  __int64 v2; // r14
  unsigned __int16 *v4; // rsi
  NTSTATUS SystemVolumeInformationFolder; // ebx
  __int64 v6; // r8
  NTSTATUS v7; // eax
  __int64 v8; // r8
  struct _KEVENT *v9; // rcx
  PVOID P[2]; // [rsp+70h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+108h] [rbp+6Fh] BYREF

  v2 = Context[1];
  FileHandle = 0;
  *(_OWORD *)P = 0;
  v4 = (unsigned __int16 *)(v2 + 80);
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  LOWORD(P[0]) = *(_WORD *)(v2 + 80) + word_140007020;
  WORD1(P[0]) = LOWORD(P[0]) + 2;
  P[1] = (PVOID)ExAllocatePool2(258, (unsigned __int16)(LOWORD(P[0]) + 2), 1114926669);
  if ( P[1] )
  {
    SystemVolumeInformationFolder = RtlCreateSystemVolumeInformationFolder((PCUNICODE_STRING)(v2 + 80));
    if ( SystemVolumeInformationFolder >= 0 )
    {
      memmove(P[1], *(const void **)(v2 + 88), *v4);
      memmove((char *)P[1] + *v4, Src, (unsigned __int16)word_140007020);
      *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = IoCreateFile(
             &FileHandle,
             0x12019Fu,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x86u,
             0,
             2u,
             0x60u,
             0,
             0,
             CreateFileTypeNone,
             0,
             0x108u);
      SystemVolumeInformationFolder = v7;
      if ( v7 < 0 )
      {
        if ( v7 == -2147483603 )
          DetectedSymlinkOnRemoteDatabaseFile();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 31, v8, (unsigned int)SystemVolumeInformationFolder);
        }
        FileHandle = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 30, v6, (unsigned int)SystemVolumeInformationFolder);
    }
  }
  else
  {
    SystemVolumeInformationFolder = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29);
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( SystemVolumeInformationFolder >= 0 )
    *(_BYTE *)(v2 + 134) = 1;
  IoFreeWorkItem((PIO_WORKITEM)*Context);
  v9 = (struct _KEVENT *)Context[2];
  Context[4] = FileHandle;
  *Context = 0;
  *((_DWORD *)Context + 6) = SystemVolumeInformationFolder;
  KeSetEvent(v9, 0, 0);
}

```

## disassembly

```asm
0x14000b150  push    rbp
0x14000b152  push    rbx
0x14000b153  push    rsi
0x14000b154  push    rdi
0x14000b155  push    r13
0x14000b157  push    r14
0x14000b159  lea     rbp, [rsp-2Fh]
0x14000b15e  sub     rsp, 0C8h
0x14000b165  mov     r14, [rdx+8]
0x14000b169  xorps   xmm0, xmm0
0x14000b16c  xor     eax, eax
0x14000b16e  mov     [rbp+57h+FileHandle], 0
0x14000b176  movzx   eax, cs:word_140007020
0x14000b17d  xorps   xmm1, xmm1
0x14000b180  movups  xmmword ptr [rbp+57h+P], xmm0
0x14000b184  mov     rdi, rdx
0x14000b187  lea     rsi, [r14+50h]
0x14000b18b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000b18f  mov     r13d, 2
0x14000b195  mov     ecx, 102h
0x14000b19a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000b19e  mov     r8d, 42746E4Dh
0x14000b1a4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000b1a8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x14000b1ac  add     ax, [rsi]
0x14000b1af  mov     word ptr [rbp+57h+P], ax
0x14000b1b3  add     ax, r13w
0x14000b1b7  movzx   edx, ax
0x14000b1ba  mov     word ptr [rbp+57h+P+2], dx
0x14000b1be  call    cs:__imp_ExAllocatePool2
0x14000b1c5  nop     dword ptr [rax+rax+00h]
0x14000b1ca  mov     [rbp+57h+P+8], rax
0x14000b1ce  test    rax, rax
0x14000b1d1  jnz     short loc_14000B20C
0x14000b1d3  mov     ebx, 0C000009Ah
0x14000b1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b1df  lea     rax, WPP_GLOBAL_Control
0x14000b1e6  cmp     rcx, rax
0x14000b1e9  jz      loc_14000B363
0x14000b1ef  mov     eax, [rcx+2Ch]
0x14000b1f2  test    al, 4
0x14000b1f4  jz      loc_14000B363
0x14000b1fa  mov     rcx, [rcx+18h]
0x14000b1fe  lea     edx, [r13+1Bh]
0x14000b202  call    WPP_SF_
0x14000b207  jmp     loc_14000B363
0x14000b20c  mov     rcx, rsi; VolumeRootPath
0x14000b20f  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x14000b216  nop     dword ptr [rax+rax+00h]
0x14000b21b  mov     ebx, eax
0x14000b21d  test    eax, eax
0x14000b21f  jns     short loc_14000B264
0x14000b221  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b228  lea     rax, WPP_GLOBAL_Control
0x14000b22f  cmp     rcx, rax
0x14000b232  jz      loc_14000B363
0x14000b238  mov     edx, [rcx+2Ch]
0x14000b23b  test    dl, 1
0x14000b23e  jz      loc_14000B363
0x14000b244  cmp     byte ptr [rcx+29h], 1
0x14000b248  jb      loc_14000B363
0x14000b24e  mov     rcx, [rcx+18h]
0x14000b252  mov     edx, 1Eh
0x14000b257  mov     r9d, ebx
0x14000b25a  call    WPP_SF_L
0x14000b25f  jmp     loc_14000B363
0x14000b264  movzx   r8d, word ptr [rsi]; Size
0x14000b268  mov     rdx, [r14+58h]; Src
0x14000b26c  mov     rcx, [rbp+57h+P+8]; void *
0x14000b270  call    memmove
0x14000b275  movzx   ecx, word ptr [rsi]
0x14000b278  add     rcx, [rbp+57h+P+8]; void *
0x14000b27c  movzx   r8d, cs:word_140007020; Size
0x14000b284  mov     rdx, cs:Src; Src
0x14000b28b  call    memmove
0x14000b290  movzx   edx, word ptr [rbp+57h+P]
0x14000b294  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000b298  mov     rax, [rbp+57h+P+8]
0x14000b29c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000b2a0  xor     ecx, ecx
0x14000b2a2  mov     [rsp+0F0h+Options], 108h; Options
0x14000b2aa  mov     [rsp+0F0h+InternalParameters], rcx; InternalParameters
0x14000b2af  xorps   xmm0, xmm0
0x14000b2b2  mov     [rsp+0F0h+CreateFileType], ecx; CreateFileType
0x14000b2b6  mov     [rsp+0F0h+EaLength], ecx; EaLength
0x14000b2ba  mov     [rsp+0F0h+EaBuffer], rcx; EaBuffer
0x14000b2bf  mov     [rsp+0F0h+CreateOptions], 60h ; '`'; CreateOptions
0x14000b2c7  shr     rdx, 1
0x14000b2ca  mov     [rsp+0F0h+Disposition], r13d; Disposition
0x14000b2cf  mov     [rsp+0F0h+ShareAccess], ecx; ShareAccess
0x14000b2d3  mov     [rsp+0F0h+FileAttributes], 86h; FileAttributes
0x14000b2db  mov     [rax+rdx*2], cx
0x14000b2df  lea     rax, [rbp+57h+P]
0x14000b2e3  mov     [rsp+0F0h+AllocationSize], rcx; AllocationSize
0x14000b2e8  mov     edx, 12019Fh; DesiredAccess
0x14000b2ed  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x14000b2f1  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000b2f5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000b2fc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000b303  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000b307  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b30c  call    cs:__imp_IoCreateFile
0x14000b313  nop     dword ptr [rax+rax+00h]
0x14000b318  mov     ebx, eax
0x14000b31a  test    eax, eax
0x14000b31c  jns     short loc_14000B363
0x14000b31e  cmp     eax, 8000002Dh
0x14000b323  jnz     short loc_14000B32A
0x14000b325  call    DetectedSymlinkOnRemoteDatabaseFile
0x14000b32a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b331  lea     rax, WPP_GLOBAL_Control
0x14000b338  cmp     rcx, rax
0x14000b33b  jz      short loc_14000B35B
0x14000b33d  mov     eax, [rcx+2Ch]
0x14000b340  test    al, 1
0x14000b342  jz      short loc_14000B35B
0x14000b344  cmp     byte ptr [rcx+29h], 1
0x14000b348  jb      short loc_14000B35B
0x14000b34a  mov     rcx, [rcx+18h]
0x14000b34e  mov     edx, 1Fh
0x14000b353  mov     r9d, ebx
0x14000b356  call    WPP_SF_L
0x14000b35b  mov     [rbp+57h+FileHandle], 0
0x14000b363  mov     rcx, [rbp+57h+P+8]; P
0x14000b367  test    rcx, rcx
0x14000b36a  jz      short loc_14000B37A
0x14000b36c  xor     edx, edx; Tag
0x14000b36e  call    cs:__imp_ExFreePoolWithTag
0x14000b375  nop     dword ptr [rax+rax+00h]
0x14000b37a  test    ebx, ebx
0x14000b37c  js      short loc_14000B386
0x14000b37e  mov     byte ptr [r14+86h], 1
0x14000b386  mov     rcx, [rdi]; IoWorkItem
0x14000b389  call    cs:__imp_IoFreeWorkItem
0x14000b390  nop     dword ptr [rax+rax+00h]
0x14000b395  mov     rax, [rbp+57h+FileHandle]
0x14000b399  xor     r8d, r8d; Wait
0x14000b39c  mov     rcx, [rdi+10h]; Event
0x14000b3a0  xor     edx, edx; Increment
0x14000b3a2  mov     [rdi+20h], rax
0x14000b3a6  mov     qword ptr [rdi], 0
0x14000b3ad  mov     [rdi+18h], ebx
0x14000b3b0  call    cs:__imp_KeSetEvent
0x14000b3b7  nop     dword ptr [rax+rax+00h]
0x14000b3bc  add     rsp, 0C8h
0x14000b3c3  pop     r14
0x14000b3c5  pop     r13
0x14000b3c7  pop     rdi
0x14000b3c8  pop     rsi
0x14000b3c9  pop     rbx
0x14000b3ca  pop     rbp
0x14000b3cb  retn
```
