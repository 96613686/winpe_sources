# HsmpOpenFileByPath

- ea: `0x14007f338`
- end: `0x14007f47c`
- name: `HsmpOpenFileByPath`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400431dc`
- `0x140055abc`
- `0x140067c70`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x14005e3f0`
- `0x14007f338`

## import_xrefs

- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14007f363`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14007f363`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007f464`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007f464`

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
  HsmDbgBreakOnStatus(FileNameInformationUnsafe);
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
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
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
0x14007f338  push    rbx
0x14007f33a  push    rbp
0x14007f33b  push    rsi
0x14007f33c  push    rdi
0x14007f33d  sub     rsp, 68h
0x14007f341  mov     rsi, rdx
0x14007f344  mov     [rsp+88h+FileNameInformation], 0
0x14007f34d  mov     ebp, r8d
0x14007f350  lea     r9, [rsp+88h+FileNameInformation]; FileNameInformation
0x14007f355  mov     rdi, rcx
0x14007f358  xor     edx, edx; Instance
0x14007f35a  mov     rcx, rsi; FileObject
0x14007f35d  mov     r8d, 101h; NameOptions
0x14007f363  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14007f36a  nop     dword ptr [rax+rax+00h]
0x14007f36f  mov     ecx, eax
0x14007f371  mov     ebx, eax
0x14007f373  call    HsmDbgBreakOnStatus
0x14007f378  test    ebx, ebx
0x14007f37a  jns     short loc_14007F3CF
0x14007f37c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f383  lea     rax, WPP_GLOBAL_Control
0x14007f38a  cmp     rcx, rax
0x14007f38d  jz      loc_14007F45A
0x14007f393  mov     edx, [rcx+2Ch]
0x14007f396  test    dl, 8
0x14007f399  jz      loc_14007F45A
0x14007f39f  cmp     byte ptr [rcx+29h], 2
0x14007f3a3  jb      loc_14007F45A
0x14007f3a9  mov     rcx, [rcx+18h]
0x14007f3ad  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14007f3b4  mov     edx, 1Dh
0x14007f3b9  mov     [rsp+88h+var_60], ebx
0x14007f3bd  mov     r9, rdi
0x14007f3c0  mov     [rsp+88h+var_68], rsi
0x14007f3c5  call    WPP_SF_qqd
0x14007f3ca  jmp     loc_14007F45A
0x14007f3cf  mov     rax, [rsp+88h+arg_38]
0x14007f3d7  mov     r9d, ebp
0x14007f3da  mov     r8, [rsp+88h+FileNameInformation]
0x14007f3df  mov     rcx, rdi
0x14007f3e2  mov     rdx, [rdi+20h]
0x14007f3e6  add     r8, 8
0x14007f3ea  mov     [rsp+88h+var_48], rax
0x14007f3ef  mov     rax, [rsp+88h+arg_30]
0x14007f3f7  mov     [rsp+88h+var_50], rax
0x14007f3fc  mov     eax, [rsp+88h+arg_20]
0x14007f403  mov     [rsp+88h+var_58], 0
0x14007f408  mov     [rsp+88h+var_60], eax
0x14007f40c  call    HsmiOpenFile
0x14007f411  mov     ecx, eax
0x14007f413  mov     ebx, eax
0x14007f415  call    HsmDbgBreakOnStatus
0x14007f41a  test    ebx, ebx
0x14007f41c  jns     short loc_14007F45A
0x14007f41e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f425  lea     rax, WPP_GLOBAL_Control
0x14007f42c  cmp     rcx, rax
0x14007f42f  jz      short loc_14007F45A
0x14007f431  mov     eax, [rcx+2Ch]
0x14007f434  test    al, 8
0x14007f436  jz      short loc_14007F45A
0x14007f438  cmp     byte ptr [rcx+29h], 2
0x14007f43c  jb      short loc_14007F45A
0x14007f43e  mov     rcx, [rcx+18h]
0x14007f442  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14007f449  mov     edx, 1Eh
0x14007f44e  mov     dword ptr [rsp+88h+var_68], ebx
0x14007f452  mov     r9, rdi
0x14007f455  call    WPP_SF_qd
0x14007f45a  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x14007f45f  test    rcx, rcx
0x14007f462  jz      short loc_14007F470
0x14007f464  call    cs:__imp_FltReleaseFileNameInformation
0x14007f46b  nop     dword ptr [rax+rax+00h]
0x14007f470  mov     eax, ebx
0x14007f472  add     rsp, 68h
0x14007f476  pop     rdi
0x14007f477  pop     rsi
0x14007f478  pop     rbp
0x14007f479  pop     rbx
0x14007f47a  retn
```
