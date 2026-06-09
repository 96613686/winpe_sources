# TruncateRemoteDatabase

- ea: `0x14000a550`
- end: `0x14000a631`
- name: `TruncateRemoteDatabase`
- size: `225`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b5e8`
- `0x1400119a0`
- `0x1400135a0`

## callees

- `0x140001ae0`
- `0x14000a550`

## import_xrefs

- `ntoskrnl!ZwSetInformationFile` at `0x14000a589`
- `ntoskrnl!ZwSetInformationFile` at `0x14000a5e6`
- `ntoskrnl!ZwSetInformationFile` at `0x14000a589`
- `ntoskrnl!ZwSetInformationFile` at `0x14000a5e6`

## pseudocode

```c
__int64 __fastcall TruncateRemoteDatabase(HANDLE FileHandle, unsigned int a2)
{
  NTSTATUS v3; // edi
  __int64 v4; // r8
  NTSTATUS v6; // ebx
  __int64 v7; // r8
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-18h] BYREF
  __int64 FileInformation; // [rsp+60h] [rbp+18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  FileInformation = a2;
  v10 = a2;
  IoStatusBlock = 0;
  v3 = ZwSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation);
  if ( v3 >= 0 )
  {
    v6 = ZwSetInformationFile(FileHandle, &IoStatusBlock, &v10, 8u, FileAllocationInformation);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x2Bu, v7, v6);
    }
    return (unsigned int)v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x2Au, v4, v3);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x14000a550  mov     [rsp+arg_0], rbx
0x14000a555  push    rdi
0x14000a556  sub     rsp, 40h
0x14000a55a  mov     eax, edx
0x14000a55c  lea     r8, [rsp+48h+FileInformation]; FileInformation
0x14000a561  xorps   xmm0, xmm0
0x14000a564  mov     [rsp+48h+FileInformation], rax
0x14000a569  lea     rdx, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x14000a56e  mov     [rsp+48h+arg_18], rax
0x14000a573  mov     r9d, 8; Length
0x14000a579  mov     [rsp+48h+FileInformationClass], 14h; FileInformationClass
0x14000a581  movups  xmmword ptr [rsp+48h+IoStatusBlock], xmm0
0x14000a586  mov     rbx, rcx
0x14000a589  call    cs:__imp_ZwSetInformationFile
0x14000a590  nop     dword ptr [rax+rax+00h]
0x14000a595  mov     edi, eax
0x14000a597  test    eax, eax
0x14000a599  jns     short loc_14000A5CB
0x14000a59b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5a2  lea     rax, WPP_GLOBAL_Control
0x14000a5a9  cmp     rcx, rax
0x14000a5ac  jz      short loc_14000A5C7
0x14000a5ae  mov     edx, [rcx+2Ch]
0x14000a5b1  test    dl, 1
0x14000a5b4  jz      short loc_14000A5C7
0x14000a5b6  mov     rcx, [rcx+18h]
0x14000a5ba  mov     edx, 2Ah ; '*'
0x14000a5bf  mov     r9d, edi
0x14000a5c2  call    WPP_SF_L
0x14000a5c7  mov     eax, edi
0x14000a5c9  jmp     short loc_14000A625
0x14000a5cb  mov     r9d, 8; Length
0x14000a5d1  mov     [rsp+48h+FileInformationClass], 13h; FileInformationClass
0x14000a5d9  lea     r8, [rsp+48h+arg_18]; FileInformation
0x14000a5de  mov     rcx, rbx; FileHandle
0x14000a5e1  lea     rdx, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x14000a5e6  call    cs:__imp_ZwSetInformationFile
0x14000a5ed  nop     dword ptr [rax+rax+00h]
0x14000a5f2  mov     ebx, eax
0x14000a5f4  test    eax, eax
0x14000a5f6  jns     short loc_14000A623
0x14000a5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5ff  lea     rax, WPP_GLOBAL_Control
0x14000a606  cmp     rcx, rax
0x14000a609  jz      short loc_14000A623
0x14000a60b  mov     eax, [rcx+2Ch]
0x14000a60e  test    al, 1
0x14000a610  jz      short loc_14000A623
0x14000a612  mov     rcx, [rcx+18h]
0x14000a616  mov     edx, 2Bh ; '+'
0x14000a61b  mov     r9d, ebx
0x14000a61e  call    WPP_SF_L
0x14000a623  mov     eax, ebx
0x14000a625  mov     rbx, [rsp+48h+arg_0]
0x14000a62a  add     rsp, 40h
0x14000a62e  pop     rdi
0x14000a62f  retn
```
