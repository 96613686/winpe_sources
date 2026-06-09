# HsmiCldGetSyncRootFileIdByPath

- ea: `0x140057a00`
- end: `0x140057bb1`
- name: `HsmiCldGetSyncRootFileIdByPath`
- size: `433`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140051c80`
- `0x1400536e0`
- `0x140055308`
- `0x140058f70`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x140057a00`
- `0x140057bb8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140057ab7`
- `ntoskrnl!ObfDereferenceObject` at `0x140057ab7`
- `FLTMGR!FltClose` at `0x140057acd`
- `FLTMGR!FltClose` at `0x140057acd`
- `FLTMGR!FltQueryInformationFile` at `0x140057a85`
- `FLTMGR!FltQueryInformationFile` at `0x140057a85`

## pseudocode

```c
__int64 __fastcall HsmiCldGetSyncRootFileIdByPath(__int64 a1, unsigned __int16 *a2, _QWORD *a3)
{
  int v5; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  HANDLE FileHandle; // [rsp+30h] [rbp-18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp+18h] BYREF
  __int64 FileInformation; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  FileHandle = 0;
  FileObject = 0;
  FileInformation = 0;
  v5 = HsmiCldOpenSyncRoot(a1, a2, &FileHandle, &FileObject);
  HsmDbgBreakOnStatus((unsigned int)v5);
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
    HsmDbgBreakOnStatus((unsigned int)v5);
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
  HsmDbgBreakOnStatus(3221278483LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1, -1073688813);
  }
LABEL_7:
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140057a00  mov     rax, rsp
0x140057a03  mov     [rax+8], rbx
0x140057a07  mov     [rax+10h], rsi
0x140057a0b  push    r14
0x140057a0d  sub     rsp, 40h
0x140057a11  mov     r14, r8
0x140057a14  mov     qword ptr [r8], 0
0x140057a1b  lea     r8, [rax-18h]
0x140057a1f  mov     qword ptr [rax-18h], 0
0x140057a27  lea     r9, [rax+18h]
0x140057a2b  mov     qword ptr [rax+18h], 0
0x140057a33  mov     rsi, rcx
0x140057a36  mov     qword ptr [rax+20h], 0
0x140057a3e  call    HsmiCldOpenSyncRoot
0x140057a43  mov     ecx, eax
0x140057a45  mov     ebx, eax
0x140057a47  call    HsmDbgBreakOnStatus
0x140057a4c  test    ebx, ebx
0x140057a4e  js      loc_140057AED
0x140057a54  cmp     [rsp+48h+FileObject], 0
0x140057a5a  jz      loc_140057B15
0x140057a60  mov     rdx, [rsp+48h+FileObject]; FileObject
0x140057a65  lea     r8, [rsp+48h+FileInformation]; FileInformation
0x140057a6a  mov     rcx, [rsi+20h]; Instance
0x140057a6e  mov     r9d, 8; Length
0x140057a74  mov     [rsp+48h+LengthReturned], 0; LengthReturned
0x140057a7d  mov     [rsp+48h+FileInformationClass], 6; FileInformationClass
0x140057a85  call    cs:__imp_FltQueryInformationFile
0x140057a8c  nop     dword ptr [rax+rax+00h]
0x140057a91  mov     ecx, eax
0x140057a93  mov     ebx, eax
0x140057a95  call    HsmDbgBreakOnStatus
0x140057a9a  test    ebx, ebx
0x140057a9c  js      loc_140057B83
0x140057aa2  mov     rax, [rsp+48h+FileInformation]
0x140057aa7  mov     [r14], rax
0x140057aaa  cmp     [rsp+48h+FileObject], 0
0x140057ab0  jz      short loc_140057AC3
0x140057ab2  mov     rcx, [rsp+48h+FileObject]; Object
0x140057ab7  call    cs:__imp_ObfDereferenceObject
0x140057abe  nop     dword ptr [rax+rax+00h]
0x140057ac3  mov     rcx, [rsp+48h+FileHandle]; FileHandle
0x140057ac8  test    rcx, rcx
0x140057acb  jz      short loc_140057AD9
0x140057acd  call    cs:__imp_FltClose
0x140057ad4  nop     dword ptr [rax+rax+00h]
0x140057ad9  mov     rsi, [rsp+48h+arg_8]
0x140057ade  mov     eax, ebx
0x140057ae0  mov     rbx, [rsp+48h+arg_0]
0x140057ae5  add     rsp, 40h
0x140057ae9  pop     r14
0x140057aeb  retn
0x140057aed  mov     rcx, cs:WPP_GLOBAL_Control
0x140057af4  lea     rax, WPP_GLOBAL_Control
0x140057afb  cmp     rcx, rax
0x140057afe  jz      short loc_140057AAA
0x140057b00  mov     edx, [rcx+2Ch]
0x140057b03  test    dl, 1
0x140057b06  jz      short loc_140057AAA
0x140057b08  cmp     byte ptr [rcx+29h], 2
0x140057b0c  jb      short loc_140057AAA
0x140057b0e  mov     edx, 2Dh ; '-'
0x140057b13  jmp     short loc_140057B67
0x140057b15  mov     ebx, 0C000CF13h
0x140057b1a  mov     ecx, ebx
0x140057b1c  call    HsmDbgBreakOnStatus
0x140057b21  mov     rcx, cs:WPP_GLOBAL_Control
0x140057b28  lea     rax, WPP_GLOBAL_Control
0x140057b2f  cmp     rcx, rax
0x140057b32  jz      short loc_140057AC3
0x140057b34  mov     eax, [rcx+2Ch]
0x140057b37  test    al, 1
0x140057b39  jz      short loc_140057AC3
0x140057b3b  cmp     byte ptr [rcx+29h], 3
0x140057b3f  jb      short loc_140057AC3
0x140057b41  mov     rcx, [rcx+18h]
0x140057b45  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057b4c  mov     edx, 2Eh ; '.'
0x140057b51  mov     [rsp+48h+FileInformationClass], ebx
0x140057b55  mov     r9, rsi
0x140057b58  call    WPP_SF_qd
0x140057b5d  jmp     loc_140057AC3
0x140057b62  mov     edx, 2Fh ; '/'
0x140057b67  mov     rcx, [rcx+18h]
0x140057b6b  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057b72  mov     r9, rsi
0x140057b75  mov     [rsp+48h+FileInformationClass], ebx
0x140057b79  call    WPP_SF_qd
0x140057b7e  jmp     loc_140057AAA
0x140057b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140057b8a  lea     rax, WPP_GLOBAL_Control
0x140057b91  cmp     rcx, rax
0x140057b94  jz      loc_140057AAA
0x140057b9a  mov     eax, [rcx+2Ch]
0x140057b9d  test    al, 1
0x140057b9f  jz      loc_140057AAA
0x140057ba5  cmp     byte ptr [rcx+29h], 2
0x140057ba9  jb      loc_140057AAA
0x140057baf  jmp     short loc_140057B62
```
