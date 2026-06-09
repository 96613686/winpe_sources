# CMSVidWebDVD::Eject(void)

- ea: `0x1800ac2c0`
- end: `0x1800ac455`
- name: `?Eject@CMSVidWebDVD@@UEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(CMSVidWebDVD *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180004640`
- `0x18000bda8`
- `0x1800ac2c0`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800ac358`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800ac358`
- `KERNEL32!DeviceIoControl` at `0x1800ac403`
- `KERNEL32!DeviceIoControl` at `0x1800ac403`
- `KERNEL32!CreateFileW` at `0x1800ac3a6`
- `KERNEL32!CreateFileW` at `0x1800ac3a6`
- `KERNEL32!CloseHandle` at `0x1800ac429`
- `KERNEL32!CloseHandle` at `0x1800ac429`

## pseudocode

```c
__int64 __fastcall CMSVidWebDVD::Eject(CMSVidWebDVD *this)
{
  __int64 v1; // rax
  __int64 result; // rax
  HANDLE FileW; // rax
  void *v5; // rdi
  bool v6; // zf
  DWORD v7; // edx
  unsigned int v8; // ebx
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *FullPath; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Drive[8]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Ext[256]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t Filename[256]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t Dir[256]; // [rsp+680h] [rbp+580h] BYREF

  v1 = *(_QWORD *)this;
  FullPath = 0;
  result = (*(__int64 (__fastcall **)(CMSVidWebDVD *, wchar_t **))(v1 + 560))(this, &FullPath);
  if ( (int)result >= 0 )
  {
    _wsplitpath_s(FullPath, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
    result = StringCchPrintfW(FileName, 0x104u, L"\\\\.\\%s", Drive);
    if ( (int)result >= 0 )
    {
      FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
      v5 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        return 2147549183LL;
      }
      else
      {
        v6 = *((_BYTE *)this + 128) == 1;
        v7 = 2967564;
        BytesReturned = 0;
        if ( !v6 )
          v7 = 2967560;
        if ( DeviceIoControl(FileW, v7, 0, 0, 0, 0, &BytesReturned, 0) )
        {
          *((_BYTE *)this + 128) = *((_BYTE *)this + 128) == 0;
          v8 = 0;
        }
        else
        {
          v8 = -2147467259;
        }
        CloseHandle(v5);
        return v8;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ac2c0  mov     [rsp-8+arg_8], rbx
0x1800ac2c5  mov     [rsp-8+arg_10], rdi
0x1800ac2ca  push    rbp
0x1800ac2cb  lea     rbp, [rsp-790h]
0x1800ac2d3  sub     rsp, 890h
0x1800ac2da  mov     rax, cs:__security_cookie
0x1800ac2e1  xor     rax, rsp
0x1800ac2e4  mov     [rbp+790h+var_10], rax
0x1800ac2eb  mov     rax, [rcx]
0x1800ac2ee  lea     rdx, [rsp+890h+FullPath]
0x1800ac2f3  mov     rbx, rcx
0x1800ac2f6  mov     [rsp+890h+FullPath], 0
0x1800ac2ff  mov     rax, [rax+230h]
0x1800ac306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac30b  test    eax, eax
0x1800ac30d  js      loc_1800AC431
0x1800ac313  mov     ecx, 100h
0x1800ac318  lea     rax, [rbp+790h+var_610]
0x1800ac31f  mov     [rsp+890h+ExtCount], rcx; ExtCount
0x1800ac324  lea     r9, [rbp+790h+Dir]; Dir
0x1800ac32b  mov     [rsp+890h+Ext], rax; Ext
0x1800ac330  lea     rdx, [rsp+890h+Drive]; Drive
0x1800ac335  mov     [rsp+890h+FilenameCount], rcx; FilenameCount
0x1800ac33a  lea     rax, [rbp+790h+var_410]
0x1800ac341  mov     [rsp+890h+Filename], rax; Filename
0x1800ac346  mov     edi, 3
0x1800ac34b  mov     [rsp+890h+DirCount], rcx; DirCount
0x1800ac350  mov     r8d, edi; DriveCount
0x1800ac353  mov     rcx, [rsp+890h+FullPath]; FullPath
0x1800ac358  call    cs:__imp__wsplitpath_s
0x1800ac35e  lea     r9, [rsp+890h+Drive]
0x1800ac363  mov     edx, 104h; unsigned __int64
0x1800ac368  lea     r8, aS_0; "\\\\.\\%s"
0x1800ac36f  lea     rcx, [rsp+890h+FileName]; unsigned __int16 *
0x1800ac374  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ac379  test    eax, eax
0x1800ac37b  js      loc_1800AC431
0x1800ac381  mov     [rsp+890h+FilenameCount], 0; hTemplateFile
0x1800ac38a  lea     rcx, [rsp+890h+FileName]; lpFileName
0x1800ac38f  mov     dword ptr [rsp+890h+Filename], 0; dwFlagsAndAttributes
0x1800ac397  xor     r9d, r9d; lpSecurityAttributes
0x1800ac39a  mov     r8d, edi; dwShareMode
0x1800ac39d  mov     dword ptr [rsp+890h+DirCount], edi; dwCreationDisposition
0x1800ac3a1  mov     edx, 80000000h; dwDesiredAccess
0x1800ac3a6  call    cs:__imp_CreateFileW
0x1800ac3ac  mov     rdi, rax
0x1800ac3af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ac3b3  jnz     short loc_1800AC3BC
0x1800ac3b5  mov     eax, 8000FFFFh
0x1800ac3ba  jmp     short loc_1800AC431
0x1800ac3bc  cmp     byte ptr [rbx+80h], 1
0x1800ac3c3  mov     edx, 2D480Ch
0x1800ac3c8  mov     [rsp+890h+Ext], 0; lpOverlapped
0x1800ac3d1  mov     rcx, rdi; hDevice
0x1800ac3d4  mov     [rsp+890h+BytesReturned], 0
0x1800ac3dc  lea     eax, [rdx-4]
0x1800ac3df  cmovnz  edx, eax; dwIoControlCode
0x1800ac3e2  lea     rax, [rsp+890h+BytesReturned]
0x1800ac3e7  mov     [rsp+890h+FilenameCount], rax; lpBytesReturned
0x1800ac3ec  xor     r9d, r9d; nInBufferSize
0x1800ac3ef  mov     dword ptr [rsp+890h+Filename], 0; nOutBufferSize
0x1800ac3f7  xor     r8d, r8d; lpInBuffer
0x1800ac3fa  mov     [rsp+890h+DirCount], 0; lpOutBuffer
0x1800ac403  call    cs:__imp_DeviceIoControl
0x1800ac409  test    eax, eax
0x1800ac40b  jnz     short loc_1800AC414
0x1800ac40d  mov     ebx, 80004005h
0x1800ac412  jmp     short loc_1800AC426
0x1800ac414  cmp     byte ptr [rbx+80h], 0
0x1800ac41b  setz    al
0x1800ac41e  mov     [rbx+80h], al
0x1800ac424  xor     ebx, ebx
0x1800ac426  mov     rcx, rdi; hObject
0x1800ac429  call    cs:__imp_CloseHandle
0x1800ac42f  mov     eax, ebx
0x1800ac431  mov     rcx, [rbp+790h+var_10]
0x1800ac438  xor     rcx, rsp; StackCookie
0x1800ac43b  call    __security_check_cookie
0x1800ac440  lea     r11, [rsp+890h+var_s0]
0x1800ac448  mov     rbx, [r11+18h]
0x1800ac44c  mov     rdi, [r11+20h]
0x1800ac450  mov     rsp, r11
0x1800ac453  pop     rbp
0x1800ac454  retn
```
