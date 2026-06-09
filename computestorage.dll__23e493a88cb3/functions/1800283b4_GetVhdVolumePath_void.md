# GetVhdVolumePath(void *)

- ea: `0x1800283b4`
- end: `0x18002863a`
- name: `?GetVhdVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `646`
- prototype: `__int64 __fastcall(void *Src, HANDLE VirtualDiskHandle)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180014e80`

## callees

- `0x180002690`
- `0x180007cb4`
- `0x180008fac`
- `0x180009a38`
- `0x180012818`
- `0x180013cb4`
- `0x18001b920`
- `0x180028358`
- `0x1800283b4`
- `0x18002a118`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800285aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800285aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800285eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800285eb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800284b9`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800284b9`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180028413`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180028413`

## string_xrefs

- `0x18002852c`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x180028628`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WCHAR *__fastcall GetVhdVolumePath(WCHAR *Src, HANDLE VirtualDiskHandle)
{
  WCHAR *v4; // r8
  DWORD VirtualDiskPhysicalPath; // eax
  PWSTR *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  PWSTR *v9; // rcx
  WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  unsigned __int64 v15; // rdx
  PWSTR *v16; // rcx
  const WCHAR *v17; // rcx
  char *FileW; // rbx
  __int64 DiskVolumePath; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  char *v22[4]; // [rsp+58h] [rbp-11h] BYREF
  PWSTR DiskPath[2]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v25; // [rsp+90h] [rbp+27h]
  ULONG DiskPathSizeInBytes; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  std::wstring::wstring(DiskPath, 260);
  DiskPathSizeInBytes = 520;
  v4 = (WCHAR *)DiskPath;
  if ( v25 > 7 )
    v4 = DiskPath[0];
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, v4);
  if ( VirtualDiskPhysicalPath )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)VirtualDiskPhysicalPath,
      dwCreationDisposition);
  v6 = DiskPath;
  if ( v25 > 7 )
    v6 = (PWSTR *)DiskPath[0];
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)v6 + v7) );
  std::wstring::resize(DiskPath);
  v8 = v24;
  v9 = DiskPath;
  if ( v24 >= v25 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(DiskPath);
  }
  else
  {
    ++v24;
    if ( v25 > 7 )
      v9 = (PWSTR *)DiskPath[0];
    *(_DWORD *)((char *)v9 + 2 * v8) = 92;
  }
  std::wstring::wstring(Src, 260);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v10 = Src;
  else
    v10 = *(WCHAR **)Src;
  v11 = (const WCHAR *)DiskPath;
  if ( v25 > 7 )
    v11 = DiskPath[0];
  if ( GetVolumeNameForVolumeMountPointW(v11, v10, 0x104u) )
  {
    if ( *((_QWORD *)Src + 3) <= 7u )
      v12 = Src;
    else
      v12 = *(WCHAR **)Src;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    std::wstring::resize(Src);
    if ( *((_QWORD *)Src + 3) <= 7u )
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)(Src[*((_QWORD *)Src + 2) - 1] != 92),
        (void *)"%ls",
        (const char *)Src);
    else
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)(*(_WORD *)(*(_QWORD *)Src + 2LL * *((_QWORD *)Src + 2) - 2) != 92),
        (void *)"%ls",
        *(const char **)Src);
    --*((_QWORD *)Src + 2);
    if ( *((_QWORD *)Src + 3) <= 7u )
      v14 = Src;
    else
      v14 = *(WCHAR **)Src;
    v14[*((_QWORD *)Src + 2)] = 0;
  }
  else
  {
    v15 = --v24;
    v16 = DiskPath;
    if ( v25 > 7 )
      v16 = (PWSTR *)DiskPath[0];
    *((_WORD *)v16 + v15) = 0;
    v17 = (const WCHAR *)DiskPath;
    if ( v25 > 7 )
      v17 = DiskPath[0];
    FileW = (char *)CreateFileW(v17, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    DiskVolumePath = GetDiskVolumePath((__int64)v22, (__int64)FileW);
    std::wstring::operator=(Src, DiskVolumePath);
    std::wstring::~wstring(v22);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  std::wstring::~wstring((char **)DiskPath);
  return Src;
}

```

## disassembly

```asm
0x1800283b4  mov     [rsp-8+arg_10], rbx
0x1800283b9  push    rbp
0x1800283ba  push    rdi
0x1800283bb  push    r14
0x1800283bd  lea     rbp, [rsp-47h]
0x1800283c2  sub     rsp, 0B0h
0x1800283c9  mov     rax, cs:__security_cookie
0x1800283d0  xor     rax, rsp
0x1800283d3  mov     [rbp+57h+var_20], rax
0x1800283d7  mov     rbx, rdx
0x1800283da  mov     rdi, rcx
0x1800283dd  mov     [rbp+57h+var_78], rcx
0x1800283e1  xor     r14d, r14d
0x1800283e4  mov     [rbp+57h+var_80], r14d
0x1800283e8  mov     edx, 104h
0x1800283ed  lea     rcx, [rbp+57h+DiskPath]
0x1800283f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800283f6  nop
0x1800283f7  mov     [rbp+57h+DiskPathSizeInBytes], 208h
0x1800283fe  lea     r8, [rbp+57h+DiskPath]
0x180028402  cmp     [rbp+57h+var_30], 7
0x180028407  cmova   r8, [rbp+57h+DiskPath]; DiskPath
0x18002840c  lea     rdx, [rbp+57h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180028410  mov     rcx, rbx; VirtualDiskHandle
0x180028413  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18002841a  nop     dword ptr [rax+rax+00h]
0x18002841f  mov     rcx, [rbp+5Fh]; this
0x180028423  test    eax, eax
0x180028425  jnz     loc_180028625
0x18002842b  lea     rax, [rbp+57h+DiskPath]
0x18002842f  cmp     [rbp+57h+var_30], 7
0x180028434  cmova   rax, [rbp+57h+DiskPath]
0x180028439  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002843d  inc     rdx
0x180028440  cmp     [rax+rdx*2], r14w
0x180028445  jnz     short loc_18002843D
0x180028447  lea     rcx, [rbp+57h+DiskPath]; Src
0x18002844b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180028450  mov     rdx, [rbp+57h+var_38]
0x180028454  lea     rcx, [rbp+57h+DiskPath]; Src
0x180028458  mov     ebx, 5Ch ; '\'
0x18002845d  cmp     rdx, [rbp+57h+var_30]
0x180028461  jnb     short loc_18002847A
0x180028463  lea     rax, [rdx+1]
0x180028467  mov     [rbp+57h+var_38], rax
0x18002846b  cmp     [rbp+57h+var_30], 7
0x180028470  cmova   rcx, [rbp+57h+DiskPath]
0x180028475  mov     [rcx+rdx*2], ebx
0x180028478  jmp     short loc_180028482
0x18002847a  mov     r9d, ebx
0x18002847d  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180028482  mov     edx, 104h
0x180028487  mov     rcx, rdi
0x18002848a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18002848f  mov     [rbp+57h+var_80], 1
0x180028496  cmp     qword ptr [rdi+18h], 7
0x18002849b  jbe     short loc_1800284A2
0x18002849d  mov     rdx, [rdi]
0x1800284a0  jmp     short loc_1800284A5
0x1800284a2  mov     rdx, rdi; lpszVolumeName
0x1800284a5  lea     rcx, [rbp+57h+DiskPath]
0x1800284a9  cmp     [rbp+57h+var_30], 7
0x1800284ae  cmova   rcx, [rbp+57h+DiskPath]; lpszVolumeMountPoint
0x1800284b3  mov     r8d, 104h; cchBufferLength
0x1800284b9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800284c0  nop     dword ptr [rax+rax+00h]
0x1800284c5  test    eax, eax
0x1800284c7  jz      loc_18002855E
0x1800284cd  cmp     qword ptr [rdi+18h], 7
0x1800284d2  jbe     short loc_1800284D9
0x1800284d4  mov     rax, [rdi]
0x1800284d7  jmp     short loc_1800284DC
0x1800284d9  mov     rax, rdi
0x1800284dc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800284e0  inc     rdx
0x1800284e3  cmp     [rax+rdx*2], r14w
0x1800284e8  jnz     short loc_1800284E0
0x1800284ea  mov     rcx, rdi; Src
0x1800284ed  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800284f2  cmp     qword ptr [rdi+18h], 7
0x1800284f7  jbe     short loc_180028501
0x1800284f9  mov     rdx, [rdi]
0x1800284fc  mov     rcx, rdx
0x1800284ff  jmp     short loc_180028507
0x180028501  mov     rdx, rdi
0x180028504  mov     rcx, rdi
0x180028507  mov     rax, [rdi+10h]
0x18002850b  cmp     [rcx+rax*2-2], bx
0x180028510  setnz   al
0x180028513  mov     rcx, [rbp+5Fh]; this
0x180028517  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rdx; char *
0x18002851c  lea     rdx, aLs; "%ls"
0x180028523  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; void *
0x180028528  movzx   r9d, al; char *
0x18002852c  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028533  mov     edx, 1C7h; void *
0x180028538  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18002853d  dec     qword ptr [rdi+10h]
0x180028541  mov     rdx, [rdi+10h]
0x180028545  cmp     qword ptr [rdi+18h], 7
0x18002854a  jbe     short loc_180028551
0x18002854c  mov     rcx, [rdi]
0x18002854f  jmp     short loc_180028554
0x180028551  mov     rcx, rdi
0x180028554  mov     [rcx+rdx*2], r14w
0x180028559  jmp     loc_1800285F8
0x18002855e  mov     rdx, [rbp+57h+var_38]
0x180028562  dec     rdx
0x180028565  mov     [rbp+57h+var_38], rdx
0x180028569  lea     rcx, [rbp+57h+DiskPath]
0x18002856d  cmp     [rbp+57h+var_30], 7
0x180028572  cmova   rcx, [rbp+57h+DiskPath]
0x180028577  mov     [rcx+rdx*2], r14w
0x18002857c  lea     rcx, [rbp+57h+DiskPath]
0x180028580  cmp     [rbp+57h+var_30], 7
0x180028585  cmova   rcx, [rbp+57h+DiskPath]; lpFileName
0x18002858a  mov     [rsp+0C0h+hTemplateFile], r14; hTemplateFile
0x18002858f  mov     [rsp+0C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x180028597  mov     r8d, 3; dwShareMode
0x18002859d  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800285a2  xor     r9d, r9d; lpSecurityAttributes
0x1800285a5  mov     edx, 0C0000000h; dwDesiredAccess
0x1800285aa  call    cs:__imp_CreateFileW
0x1800285b1  nop     dword ptr [rax+rax+00h]
0x1800285b6  mov     rbx, rax
0x1800285b9  mov     [rbp+57h+var_70], rax
0x1800285bd  mov     rdx, rax
0x1800285c0  lea     rcx, [rbp+57h+var_68]
0x1800285c4  call    ?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetDiskVolumePath(void *)
0x1800285c9  mov     rdx, rax
0x1800285cc  mov     rcx, rdi
0x1800285cf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800285d4  lea     rcx, [rbp+57h+var_68]
0x1800285d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800285dd  nop
0x1800285de  lea     rcx, [rbx-1]
0x1800285e2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800285e6  ja      short loc_1800285F8
0x1800285e8  mov     rcx, rbx; hObject
0x1800285eb  call    cs:__imp_CloseHandle
0x1800285f2  nop     dword ptr [rax+rax+00h]
0x1800285f7  nop
0x1800285f8  lea     rcx, [rbp+57h+DiskPath]
0x1800285fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028601  mov     rax, rdi
0x180028604  mov     rcx, [rbp+57h+var_20]
0x180028608  xor     rcx, rsp; StackCookie
0x18002860b  call    __security_check_cookie
0x180028610  mov     rbx, [rsp+0C0h+arg_10]
0x180028618  add     rsp, 0B0h
0x18002861f  pop     r14
0x180028621  pop     rdi
0x180028622  pop     rbp
0x180028623  retn
0x180028625  mov     r9d, eax; char *
0x180028628  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002862f  mov     edx, 1BDh; void *
0x180028634  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
