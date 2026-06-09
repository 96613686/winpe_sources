# HsmpOpenFileByPath

- ea: `0x14007f1a0`
- end: `0x14007f2e4`
- name: `HsmpOpenFileByPath`
- size: `324`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400430ec`
- `0x14005599c`
- `0x140067b50`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x14005e2d0`
- `0x14007f1a0`

## import_xrefs

- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14007f1cb`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14007f1cb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007f2cc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007f2cc`

## pseudocode

```c
__int64 __fastcall HsmpOpenFileByPath(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        ACCESS_MASK a3,
        __int64 a4,
        ULONG a5,
        __int64 a6,
        void **a7,
        PFILE_OBJECT *a8)
{
  int FileNameInformationUnsafe; // ebx
  __int64 v13; // [rsp+20h] [rbp-68h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-38h] BYREF

  FileNameInformation = 0;
  FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(a2, 0, 0x101u, &FileNameInformation);
  HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
  if ( FileNameInformationUnsafe >= 0 )
  {
    FileNameInformationUnsafe = HsmiOpenFile(
                                  a1,
                                  *(struct _FLT_INSTANCE **)(a1 + 32),
                                  &FileNameInformation->Name,
                                  a3,
                                  v13,
                                  a5,
                                  0,
                                  a7,
                                  a8);
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
        a1,
        FileNameInformationUnsafe);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
      a1,
      a2,
      FileNameInformationUnsafe);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x14007f1a0  push    rbx
0x14007f1a2  push    rbp
0x14007f1a3  push    rsi
0x14007f1a4  push    rdi
0x14007f1a5  sub     rsp, 68h
0x14007f1a9  mov     rsi, rdx
0x14007f1ac  mov     [rsp+88h+FileNameInformation], 0
0x14007f1b5  mov     ebp, r8d
0x14007f1b8  lea     r9, [rsp+88h+FileNameInformation]; FileNameInformation
0x14007f1bd  mov     rdi, rcx
0x14007f1c0  xor     edx, edx; Instance
0x14007f1c2  mov     rcx, rsi; FileObject
0x14007f1c5  mov     r8d, 101h; NameOptions
0x14007f1cb  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14007f1d2  nop     dword ptr [rax+rax+00h]
0x14007f1d7  mov     ecx, eax
0x14007f1d9  mov     ebx, eax
0x14007f1db  call    HsmDbgBreakOnStatus
0x14007f1e0  test    ebx, ebx
0x14007f1e2  jns     short loc_14007F237
0x14007f1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f1eb  lea     rax, WPP_GLOBAL_Control
0x14007f1f2  cmp     rcx, rax
0x14007f1f5  jz      loc_14007F2C2
0x14007f1fb  mov     edx, [rcx+2Ch]
0x14007f1fe  test    dl, 8
0x14007f201  jz      loc_14007F2C2
0x14007f207  cmp     byte ptr [rcx+29h], 2
0x14007f20b  jb      loc_14007F2C2
0x14007f211  mov     rcx, [rcx+18h]
0x14007f215  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14007f21c  mov     edx, 1Dh
0x14007f221  mov     [rsp+88h+var_60], ebx
0x14007f225  mov     r9, rdi
0x14007f228  mov     [rsp+88h+var_68], rsi
0x14007f22d  call    WPP_SF_qqd
0x14007f232  jmp     loc_14007F2C2
0x14007f237  mov     rax, [rsp+88h+arg_38]
0x14007f23f  mov     r9d, ebp
0x14007f242  mov     r8, [rsp+88h+FileNameInformation]
0x14007f247  mov     rcx, rdi
0x14007f24a  mov     rdx, [rdi+20h]
0x14007f24e  add     r8, 8
0x14007f252  mov     [rsp+88h+var_48], rax
0x14007f257  mov     rax, [rsp+88h+arg_30]
0x14007f25f  mov     [rsp+88h+var_50], rax
0x14007f264  mov     eax, [rsp+88h+arg_20]
0x14007f26b  mov     [rsp+88h+var_58], 0
0x14007f270  mov     [rsp+88h+var_60], eax
0x14007f274  call    HsmiOpenFile
0x14007f279  mov     ecx, eax
0x14007f27b  mov     ebx, eax
0x14007f27d  call    HsmDbgBreakOnStatus
0x14007f282  test    ebx, ebx
0x14007f284  jns     short loc_14007F2C2
0x14007f286  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f28d  lea     rax, WPP_GLOBAL_Control
0x14007f294  cmp     rcx, rax
0x14007f297  jz      short loc_14007F2C2
0x14007f299  mov     eax, [rcx+2Ch]
0x14007f29c  test    al, 8
0x14007f29e  jz      short loc_14007F2C2
0x14007f2a0  cmp     byte ptr [rcx+29h], 2
0x14007f2a4  jb      short loc_14007F2C2
0x14007f2a6  mov     rcx, [rcx+18h]
0x14007f2aa  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14007f2b1  mov     edx, 1Eh
0x14007f2b6  mov     dword ptr [rsp+88h+var_68], ebx
0x14007f2ba  mov     r9, rdi
0x14007f2bd  call    WPP_SF_qd
0x14007f2c2  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x14007f2c7  test    rcx, rcx
0x14007f2ca  jz      short loc_14007F2D8
0x14007f2cc  call    cs:__imp_FltReleaseFileNameInformation
0x14007f2d3  nop     dword ptr [rax+rax+00h]
0x14007f2d8  mov     eax, ebx
0x14007f2da  add     rsp, 68h
0x14007f2de  pop     rdi
0x14007f2df  pop     rsi
0x14007f2e0  pop     rbp
0x14007f2e1  pop     rbx
0x14007f2e2  retn
```
