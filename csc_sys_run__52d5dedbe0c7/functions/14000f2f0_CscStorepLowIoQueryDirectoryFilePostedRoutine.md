# CscStorepLowIoQueryDirectoryFilePostedRoutine

- ea: `0x14000f2f0`
- end: `0x14000f456`
- name: `CscStorepLowIoQueryDirectoryFilePostedRoutine`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000f2f0`
- `0x140029ed0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000f332`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000f332`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000f398`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000f398`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000f343`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000f3a9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000f343`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000f3a9`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoQueryDirectoryFilePostedRoutine(__int64 a1)
{
  _DWORD *v1; // rsi
  BOOLEAN RestartScan; // bp
  struct _UNICODE_STRING *FileName; // r14
  BOOLEAN ReturnSingleEntry; // r15
  FILE_INFORMATION_CLASS FileInformationClass; // r12d
  ULONG Length; // r13d
  void *FileInformation; // rbx
  IRP *TopLevelIrp; // rdi
  unsigned int v9; // ebx
  int Information; // r8d
  int v12; // edx
  char v13; // al
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-58h] BYREF
  HANDLE FileHandle; // [rsp+C0h] [rbp+8h]

  v1 = *(_DWORD **)(a1 + 88);
  RestartScan = *(_BYTE *)(a1 + 80);
  FileName = *(struct _UNICODE_STRING **)(a1 + 72);
  ReturnSingleEntry = *(_BYTE *)(a1 + 64);
  FileInformationClass = *(_DWORD *)(a1 + 60);
  Length = *(_DWORD *)(a1 + 56);
  FileInformation = *(void **)(a1 + 48);
  FileHandle = *(HANDLE *)(a1 + 40);
  HIDWORD(IoStatusBlock.Pointer) = 0;
  TopLevelIrp = IoGetTopLevelIrp();
  IoSetTopLevelIrp(0);
  IoStatusBlock.Status = -1;
  IoStatusBlock.Information = -1;
  v9 = ZwQueryDirectoryFile(
         FileHandle,
         0,
         0,
         0,
         &IoStatusBlock,
         FileInformation,
         Length,
         FileInformationClass,
         ReturnSingleEntry,
         FileName,
         RestartScan);
  IoSetTopLevelIrp(TopLevelIrp);
  if ( (v9 & 0xC0000000) == 0xC0000000 )
  {
    *v1 = 0;
    Information = 0;
  }
  else
  {
    Information = IoStatusBlock.Information;
    *v1 = IoStatusBlock.Information;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v12 = 89;
    v13 = 89;
    if ( !RestartScan )
      v13 = 78;
    if ( !ReturnSingleEntry )
      v12 = 78;
    WPP_SF_qDdcZcDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      Information,
      (_DWORD)FileHandle,
      Length,
      FileInformationClass,
      v12,
      (__int64)FileName,
      v13,
      Information,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x14000f2f0  push    rbx
0x14000f2f2  push    rbp
0x14000f2f3  push    rsi
0x14000f2f4  push    rdi
0x14000f2f5  push    r12
0x14000f2f7  push    r13
0x14000f2f9  push    r14
0x14000f2fb  push    r15
0x14000f2fd  sub     rsp, 78h
0x14000f301  mov     rax, [rcx+28h]
0x14000f305  xorps   xmm0, xmm0
0x14000f308  mov     rsi, [rcx+58h]
0x14000f30c  movzx   ebp, byte ptr [rcx+50h]
0x14000f310  mov     r14, [rcx+48h]
0x14000f314  movzx   r15d, byte ptr [rcx+40h]
0x14000f319  mov     r12d, [rcx+3Ch]
0x14000f31d  mov     r13d, [rcx+38h]
0x14000f321  mov     rbx, [rcx+30h]
0x14000f325  mov     [rsp+0B8h+FileHandle], rax
0x14000f32d  movups  xmmword ptr [rsp+0B8h+var_58], xmm0
0x14000f332  call    cs:__imp_IoGetTopLevelIrp
0x14000f339  nop     dword ptr [rax+rax+00h]
0x14000f33e  xor     ecx, ecx; Irp
0x14000f340  mov     rdi, rax
0x14000f343  call    cs:__imp_IoSetTopLevelIrp
0x14000f34a  nop     dword ptr [rax+rax+00h]
0x14000f34f  mov     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x14000f357  lea     rax, [rsp+0B8h+var_58]
0x14000f35c  mov     [rsp+0B8h+RestartScan], bpl; RestartScan
0x14000f361  xor     r9d, r9d; ApcContext
0x14000f364  mov     [rsp+0B8h+FileName], r14; FileName
0x14000f369  xor     r8d, r8d; ApcRoutine
0x14000f36c  mov     [rsp+0B8h+ReturnSingleEntry], r15b; ReturnSingleEntry
0x14000f371  xor     edx, edx; Event
0x14000f373  mov     [rsp+0B8h+FileInformationClass], r12d; FileInformationClass
0x14000f378  mov     [rsp+0B8h+Length], r13d; Length
0x14000f37d  mov     [rsp+0B8h+FileInformation], rbx; FileInformation
0x14000f382  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x14000f387  mov     dword ptr [rsp+0B8h+var_58], 0FFFFFFFFh
0x14000f38f  mov     [rsp+0B8h+var_58.Information], 0FFFFFFFFFFFFFFFFh
0x14000f398  call    cs:__imp_ZwQueryDirectoryFile
0x14000f39f  nop     dword ptr [rax+rax+00h]
0x14000f3a4  mov     rcx, rdi; Irp
0x14000f3a7  mov     ebx, eax
0x14000f3a9  call    cs:__imp_IoSetTopLevelIrp
0x14000f3b0  nop     dword ptr [rax+rax+00h]
0x14000f3b5  mov     ecx, ebx
0x14000f3b7  and     ecx, 0C0000000h
0x14000f3bd  cmp     ecx, 0C0000000h
0x14000f3c3  jnz     short loc_14000F3FE
0x14000f3c5  mov     dword ptr [rsi], 0
0x14000f3cb  xor     r8d, r8d
0x14000f3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3d5  lea     rax, WPP_GLOBAL_Control
0x14000f3dc  cmp     rcx, rax
0x14000f3df  jz      short loc_14000F3EA
0x14000f3e1  test    dword ptr [rcx+2Ch], 40000h
0x14000f3e8  jnz     short loc_14000F408
0x14000f3ea  mov     eax, ebx
0x14000f3ec  add     rsp, 78h
0x14000f3f0  pop     r15
0x14000f3f2  pop     r14
0x14000f3f4  pop     r13
0x14000f3f6  pop     r12
0x14000f3f8  pop     rdi
0x14000f3f9  pop     rsi
0x14000f3fa  pop     rbp
0x14000f3fb  pop     rbx
0x14000f3fc  retn
0x14000f3fe  mov     r8d, dword ptr [rsp+0B8h+var_58.Information]
0x14000f403  mov     [rsi], r8d
0x14000f406  jmp     short loc_14000F3CE
0x14000f408  mov     rcx, [rcx+18h]
0x14000f40c  mov     edx, 59h ; 'Y'
0x14000f411  mov     dword ptr [rsp+0B8h+RestartScan], ebx
0x14000f415  test    bpl, bpl
0x14000f418  mov     dword ptr [rsp+0B8h+FileName], r8d
0x14000f41d  mov     eax, edx
0x14000f41f  mov     r9d, 4Eh ; 'N'
0x14000f425  cmovz   eax, r9d
0x14000f429  test    r15b, r15b
0x14000f42c  mov     [rsp+0B8h+ReturnSingleEntry], al
0x14000f430  cmovz   edx, r9d
0x14000f434  mov     qword ptr [rsp+0B8h+FileInformationClass], r14
0x14000f439  mov     r9, [rsp+0B8h+FileHandle]
0x14000f441  mov     byte ptr [rsp+0B8h+Length], dl
0x14000f445  mov     dword ptr [rsp+0B8h+FileInformation], r12d
0x14000f44a  mov     dword ptr [rsp+0B8h+IoStatusBlock], r13d
0x14000f44f  call    WPP_SF_qDdcZcDD
0x14000f454  jmp     short loc_14000F3EA
```
