# HsmiCldGetSyncRootFileIdByPath

- ea: `0x140057b20`
- end: `0x140057cd1`
- name: `HsmiCldGetSyncRootFileIdByPath`
- size: `433`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140051da0`
- `0x140053800`
- `0x140055428`
- `0x140059090`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x140057b20`
- `0x140057cd8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140057bd7`
- `ntoskrnl!ObfDereferenceObject` at `0x140057bd7`
- `FLTMGR!FltClose` at `0x140057bed`
- `FLTMGR!FltClose` at `0x140057bed`
- `FLTMGR!FltQueryInformationFile` at `0x140057ba5`
- `FLTMGR!FltQueryInformationFile` at `0x140057ba5`

## pseudocode

```c
__int64 __fastcall HsmiCldGetSyncRootFileIdByPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  HANDLE FileHandle[3]; // [rsp+30h] [rbp-18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp+18h] BYREF
  __int64 FileInformation; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  FileHandle[0] = 0;
  FileObject = 0;
  FileInformation = 0;
  v5 = HsmiCldOpenSyncRoot(a1, a2, FileHandle, &FileObject);
  HsmDbgBreakOnStatus(v5);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 45;
LABEL_18:
      WPP_SF_qd(v7->AttachedDevice, v8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1, v5);
    }
LABEL_5:
    if ( FileObject )
      ObfDereferenceObject(FileObject);
    goto LABEL_7;
  }
  if ( FileObject )
  {
    v5 = FltQueryInformationFile(
           *(PFLT_INSTANCE *)(a1 + 32),
           FileObject,
           &FileInformation,
           8u,
           FileInternalInformation,
           0);
    HsmDbgBreakOnStatus(v5);
    if ( v5 >= 0 )
    {
      *a3 = FileInformation;
      goto LABEL_5;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 47;
      goto LABEL_18;
    }
    goto LABEL_5;
  }
  v5 = -1073688813;
  HsmDbgBreakOnStatus(-1073688813);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1, -1073688813);
  }
LABEL_7:
  if ( FileHandle[0] )
    FltClose(FileHandle[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140057b20  mov     rax, rsp
0x140057b23  mov     [rax+8], rbx
0x140057b27  mov     [rax+10h], rsi
0x140057b2b  push    r14
0x140057b2d  sub     rsp, 40h
0x140057b31  mov     r14, r8
0x140057b34  mov     qword ptr [r8], 0
0x140057b3b  lea     r8, [rax-18h]
0x140057b3f  mov     qword ptr [rax-18h], 0
0x140057b47  lea     r9, [rax+18h]
0x140057b4b  mov     qword ptr [rax+18h], 0
0x140057b53  mov     rsi, rcx
0x140057b56  mov     qword ptr [rax+20h], 0
0x140057b5e  call    HsmiCldOpenSyncRoot
0x140057b63  mov     ecx, eax
0x140057b65  mov     ebx, eax
0x140057b67  call    HsmDbgBreakOnStatus
0x140057b6c  test    ebx, ebx
0x140057b6e  js      loc_140057C0D
0x140057b74  cmp     [rsp+48h+FileObject], 0
0x140057b7a  jz      loc_140057C35
0x140057b80  mov     rdx, [rsp+48h+FileObject]; FileObject
0x140057b85  lea     r8, [rsp+48h+FileInformation]; FileInformation
0x140057b8a  mov     rcx, [rsi+20h]; Instance
0x140057b8e  mov     r9d, 8; Length
0x140057b94  mov     [rsp+48h+LengthReturned], 0; LengthReturned
0x140057b9d  mov     [rsp+48h+FileInformationClass], 6; FileInformationClass
0x140057ba5  call    cs:__imp_FltQueryInformationFile
0x140057bac  nop     dword ptr [rax+rax+00h]
0x140057bb1  mov     ecx, eax
0x140057bb3  mov     ebx, eax
0x140057bb5  call    HsmDbgBreakOnStatus
0x140057bba  test    ebx, ebx
0x140057bbc  js      loc_140057CA3
0x140057bc2  mov     rax, [rsp+48h+FileInformation]
0x140057bc7  mov     [r14], rax
0x140057bca  cmp     [rsp+48h+FileObject], 0
0x140057bd0  jz      short loc_140057BE3
0x140057bd2  mov     rcx, [rsp+48h+FileObject]; Object
0x140057bd7  call    cs:__imp_ObfDereferenceObject
0x140057bde  nop     dword ptr [rax+rax+00h]
0x140057be3  mov     rcx, [rsp+48h+FileHandle]; FileHandle
0x140057be8  test    rcx, rcx
0x140057beb  jz      short loc_140057BF9
0x140057bed  call    cs:__imp_FltClose
0x140057bf4  nop     dword ptr [rax+rax+00h]
0x140057bf9  mov     rsi, [rsp+48h+arg_8]
0x140057bfe  mov     eax, ebx
0x140057c00  mov     rbx, [rsp+48h+arg_0]
0x140057c05  add     rsp, 40h
0x140057c09  pop     r14
0x140057c0b  retn
0x140057c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c14  lea     rax, WPP_GLOBAL_Control
0x140057c1b  cmp     rcx, rax
0x140057c1e  jz      short loc_140057BCA
0x140057c20  mov     edx, [rcx+2Ch]
0x140057c23  test    dl, 1
0x140057c26  jz      short loc_140057BCA
0x140057c28  cmp     byte ptr [rcx+29h], 2
0x140057c2c  jb      short loc_140057BCA
0x140057c2e  mov     edx, 2Dh ; '-'
0x140057c33  jmp     short loc_140057C87
0x140057c35  mov     ebx, 0C000CF13h
0x140057c3a  mov     ecx, ebx
0x140057c3c  call    HsmDbgBreakOnStatus
0x140057c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c48  lea     rax, WPP_GLOBAL_Control
0x140057c4f  cmp     rcx, rax
0x140057c52  jz      short loc_140057BE3
0x140057c54  mov     eax, [rcx+2Ch]
0x140057c57  test    al, 1
0x140057c59  jz      short loc_140057BE3
0x140057c5b  cmp     byte ptr [rcx+29h], 3
0x140057c5f  jb      short loc_140057BE3
0x140057c61  mov     rcx, [rcx+18h]
0x140057c65  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057c6c  mov     edx, 2Eh ; '.'
0x140057c71  mov     [rsp+48h+FileInformationClass], ebx
0x140057c75  mov     r9, rsi
0x140057c78  call    WPP_SF_qd
0x140057c7d  jmp     loc_140057BE3
0x140057c82  mov     edx, 2Fh ; '/'
0x140057c87  mov     rcx, [rcx+18h]
0x140057c8b  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057c92  mov     r9, rsi
0x140057c95  mov     [rsp+48h+FileInformationClass], ebx
0x140057c99  call    WPP_SF_qd
0x140057c9e  jmp     loc_140057BCA
0x140057ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x140057caa  lea     rax, WPP_GLOBAL_Control
0x140057cb1  cmp     rcx, rax
0x140057cb4  jz      loc_140057BCA
0x140057cba  mov     eax, [rcx+2Ch]
0x140057cbd  test    al, 1
0x140057cbf  jz      loc_140057BCA
0x140057cc5  cmp     byte ptr [rcx+29h], 2
0x140057cc9  jb      loc_140057BCA
0x140057ccf  jmp     short loc_140057C82
```
