# MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)

- ea: `0x180028640`
- end: `0x180028827`
- name: `?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z`
- size: `487`
- prototype: `void __fastcall(void *, enum _ATTACH_VIRTUAL_DISK_FLAG, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180014c20`

## callees

- `0x180002690`
- `0x180008a8c`
- `0x18000971c`
- `0x180012818`
- `0x1800136f8`
- `0x180028640`
- `0x18002994c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002877f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002877f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287c0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800286eb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800286eb`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18002873e`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18002873e`

## string_xrefs

- `0x1800287ee`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x180028800`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x180028815`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MountVhd(void *a1, enum _ATTACH_VIRTUAL_DISK_FLAG a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  const char *v5; // r9
  DWORD VirtualDiskPhysicalPath; // eax
  char *FileW; // rbx
  const char *v8; // r9
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  ULONG DiskPathSizeInBytes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+68h] [rbp-98h]
  _DWORD InBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 InBuffer_8; // [rsp+78h] [rbp-88h]
  __int128 v16; // [rsp+80h] [rbp-80h]
  __int128 v17; // [rsp+90h] [rbp-70h]
  __int64 v18; // [rsp+A0h] [rbp-60h]
  WCHAR DiskPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  hDevice = a1;
  v12 = 0;
  v13 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v12, 28);
  InBuffer_8 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  InBuffer[0] = 1;
  InBuffer[1] = a2;
  WORD3(v16) = 4;
  if ( !DeviceIoControl(hDevice, 0x2D191Cu, InBuffer, 0x38u, 0, 0, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      v5);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v12, v3, v4, v5);
  if ( (a2 & 0x40) == 0 )
  {
    *(_QWORD *)&v12 = &hDevice;
    BYTE8(v12) = 1;
    DiskPathSizeInBytes = 520;
    VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(hDevice, &DiskPathSizeInBytes, DiskPath);
    if ( VirtualDiskPhysicalPath )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)VirtualDiskPhysicalPath,
        lpOutBuffer);
    FileW = (char *)CreateFileW(DiskPath, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        v8);
    ForceOnlineHardDisk(FileW);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
}

```

## disassembly

```asm
0x180028640  mov     [rsp-8+arg_10], rbx
0x180028645  push    rbp
0x180028646  lea     rbp, [rsp-1D0h]
0x18002864e  sub     rsp, 2D0h
0x180028655  mov     rax, cs:__security_cookie
0x18002865c  xor     rax, rsp
0x18002865f  mov     [rbp+1D0h+var_10], rax
0x180028666  mov     ebx, edx
0x180028668  mov     [rsp+2D0h+hDevice], rcx
0x18002866d  xorps   xmm0, xmm0
0x180028670  xor     eax, eax
0x180028672  movups  [rsp+2D0h+var_278], xmm0
0x180028677  mov     [rsp+2D0h+var_268], rax
0x18002867c  lea     edx, [rax+1Ch]; int
0x18002867f  lea     rcx, [rsp+2D0h+var_278]; this
0x180028684  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180028689  nop
0x18002868a  xorps   xmm0, xmm0
0x18002868d  xor     eax, eax
0x18002868f  movups  [rsp+2D0h+InBuffer], xmm0
0x180028694  movups  [rbp+1D0h+var_250], xmm0
0x180028698  movups  [rbp+1D0h+var_240], xmm0
0x18002869c  mov     [rbp+1D0h+var_230], rax
0x1800286a0  mov     dword ptr [rsp+2D0h+InBuffer], 1
0x1800286a8  mov     dword ptr [rsp+2D0h+InBuffer+4], ebx
0x1800286ac  mov     eax, 4
0x1800286b1  mov     word ptr [rbp+1D0h+var_250+6], ax
0x1800286b5  mov     [rsp+2D0h+lpOverlapped], 0; lpOverlapped
0x1800286be  mov     [rsp+2D0h+lpBytesReturned], 0; lpBytesReturned
0x1800286c7  mov     [rsp+2D0h+nOutBufferSize], 0; nOutBufferSize
0x1800286cf  mov     [rsp+2D0h+lpOutBuffer], 0; unsigned int
0x1800286d8  lea     r9d, [rax+34h]; nInBufferSize
0x1800286dc  lea     r8, [rsp+2D0h+InBuffer]; lpInBuffer
0x1800286e1  mov     edx, 2D191Ch; dwIoControlCode
0x1800286e6  mov     rcx, [rsp+2D0h+hDevice]; hDevice
0x1800286eb  call    cs:__imp_DeviceIoControl
0x1800286f2  nop     dword ptr [rax+rax+00h]
0x1800286f7  mov     rcx, [rbp+1D8h]; this
0x1800286fe  test    eax, eax
0x180028700  jz      loc_180028800
0x180028706  lea     rcx, [rsp+2D0h+var_278]; this
0x18002870b  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180028710  test    bl, 40h
0x180028713  jnz     loc_1800287CD
0x180028719  lea     rax, [rsp+2D0h+hDevice]
0x18002871e  mov     qword ptr [rsp+2D0h+var_278], rax
0x180028723  mov     byte ptr [rsp+2D0h+var_278+8], 1
0x180028728  mov     [rsp+2D0h+DiskPathSizeInBytes], 208h
0x180028730  lea     r8, [rbp+1D0h+DiskPath]; DiskPath
0x180028734  lea     rdx, [rsp+2D0h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180028739  mov     rcx, [rsp+2D0h+hDevice]; VirtualDiskHandle
0x18002873e  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180028745  nop     dword ptr [rax+rax+00h]
0x18002874a  mov     rcx, [rbp+1D8h]; this
0x180028751  test    eax, eax
0x180028753  jnz     loc_180028812
0x180028759  mov     [rsp+2D0h+lpBytesReturned], 0; hTemplateFile
0x180028762  mov     [rsp+2D0h+nOutBufferSize], 20000080h; dwFlagsAndAttributes
0x18002876a  lea     r8d, [rax+3]; dwShareMode
0x18002876e  mov     dword ptr [rsp+2D0h+lpOutBuffer], r8d; dwCreationDisposition
0x180028773  xor     r9d, r9d; lpSecurityAttributes
0x180028776  mov     edx, 0C0000000h; dwDesiredAccess
0x18002877b  lea     rcx, [rbp+1D0h+DiskPath]; lpFileName
0x18002877f  call    cs:__imp_CreateFileW
0x180028786  nop     dword ptr [rax+rax+00h]
0x18002878b  mov     rbx, rax
0x18002878e  mov     [rsp+2D0h+var_290], rax
0x180028793  inc     rax
0x180028796  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002879c  setz    al
0x18002879f  mov     rcx, [rbp+1D8h]; this
0x1800287a6  test    al, al
0x1800287a8  jnz     short loc_1800287EE
0x1800287aa  mov     rcx, rbx; void *
0x1800287ad  call    ?ForceOnlineHardDisk@@YAXPEAX@Z; ForceOnlineHardDisk(void *)
0x1800287b2  nop
0x1800287b3  lea     rax, [rbx-1]
0x1800287b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800287bb  ja      short loc_1800287CD
0x1800287bd  mov     rcx, rbx; hObject
0x1800287c0  call    cs:__imp_CloseHandle
0x1800287c7  nop     dword ptr [rax+rax+00h]
0x1800287cc  nop
0x1800287cd  mov     rcx, [rbp+1D0h+var_10]
0x1800287d4  xor     rcx, rsp; StackCookie
0x1800287d7  call    __security_check_cookie
0x1800287dc  mov     rbx, [rsp+2D0h+arg_10]
0x1800287e4  add     rsp, 2D0h
0x1800287eb  pop     rbp
0x1800287ec  retn
0x1800287ee  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800287f5  mov     edx, 147h; void *
0x1800287fa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180028800  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028807  mov     edx, 12Eh; void *
0x18002880c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180028812  mov     r9d, eax; char *
0x180028815  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002881c  mov     edx, 13Ch; void *
0x180028821  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
