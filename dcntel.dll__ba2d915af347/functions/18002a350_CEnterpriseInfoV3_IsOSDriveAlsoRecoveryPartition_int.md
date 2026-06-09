# CEnterpriseInfoV3::IsOSDriveAlsoRecoveryPartition(int *)

- ea: `0x18002a350`
- end: `0x18002a46d`
- name: `?IsOSDriveAlsoRecoveryPartition@CEnterpriseInfoV3@@CAJPEAH@Z`
- size: `285`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800258b0`
- `0x1800a7030`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18002a350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a42a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a44c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a44c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a41e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a41e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002a3df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002a3df`

## pseudocode

```c
__int64 __fastcall CEnterpriseInfoV3::IsOSDriveAlsoRecoveryPartition(int *a1)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  WCHAR FileName[32]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-228h] BYREF

  wcscpy(FileName, L"X:\\Recovery\\WindowsRE\\wnre.wim");
  memset_0(Buffer, 0, 0x208u);
  if ( a1 )
  {
    *a1 = 0;
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
      FileName[0] = Buffer[0];
    FileW = CreateFileW(FileName, 1u, 1u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      *a1 = 1;
      v2 = 0;
      CloseHandle(FileW);
    }
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x18002a350  push    rbx
0x18002a352  sub     rsp, 2A0h
0x18002a359  mov     rax, cs:__security_cookie
0x18002a360  xor     rax, rsp
0x18002a363  mov     [rsp+2A8h+var_18], rax
0x18002a36b  movups  xmm0, xmmword ptr cs:aXRecoveryWindo+2; ":\\Recovery\\WindowsRE\\winre.wim"
0x18002a372  mov     rbx, rcx
0x18002a375  mov     eax, 58h ; 'X'
0x18002a37a  movups  xmm1, xmmword ptr cs:aXRecoveryWindo+12h; "ry\\WindowsRE\\winre.wim"
0x18002a381  xor     edx, edx; Val
0x18002a383  mov     r8d, 208h; Size
0x18002a389  movups  [rsp+2A8h+var_266], xmm0
0x18002a38e  lea     rcx, [rsp+2A8h+Buffer]; void *
0x18002a396  mov     [rsp+2A8h+FileName], ax
0x18002a39b  movups  xmm0, xmmword ptr cs:aXRecoveryWindo+22h; "wsRE\\winre.wim"
0x18002a3a2  movups  [rsp+2A8h+var_256], xmm1
0x18002a3a7  movaps  xmm1, xmmword ptr cs:aXRecoveryWindo+30h; "nre.wim"
0x18002a3ae  movups  [rsp+2A8h+var_246], xmm0
0x18002a3b3  movups  [rsp+2A8h+var_246+0Eh], xmm1
0x18002a3b8  call    memset_0
0x18002a3bd  test    rbx, rbx
0x18002a3c0  jnz     short loc_18002A3CC
0x18002a3c2  mov     ebx, 57h ; 'W'
0x18002a3c7  jmp     loc_18002A452
0x18002a3cc  mov     edx, 104h; uSize
0x18002a3d1  mov     dword ptr [rbx], 0
0x18002a3d7  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x18002a3df  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002a3e5  test    eax, eax
0x18002a3e7  jz      short loc_18002A3F6
0x18002a3e9  movzx   eax, [rsp+2A8h+Buffer]
0x18002a3f1  mov     [rsp+2A8h+FileName], ax
0x18002a3f6  xor     r9d, r9d; lpSecurityAttributes
0x18002a3f9  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x18002a402  mov     [rsp+2A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002a40a  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x18002a40f  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18002a417  lea     edx, [r9+1]; dwDesiredAccess
0x18002a41b  mov     r8d, edx; dwShareMode
0x18002a41e  call    cs:__imp_CreateFileW
0x18002a424  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a428  jnz     short loc_18002A441
0x18002a42a  call    cs:__imp_GetLastError
0x18002a430  mov     ebx, eax
0x18002a432  test    eax, eax
0x18002a434  jle     short loc_18002A452
0x18002a436  movzx   ebx, ax
0x18002a439  or      ebx, 80070000h
0x18002a43f  jmp     short loc_18002A452
0x18002a441  mov     dword ptr [rbx], 1
0x18002a447  xor     ebx, ebx
0x18002a449  mov     rcx, rax; hObject
0x18002a44c  call    cs:__imp_CloseHandle
0x18002a452  mov     eax, ebx
0x18002a454  mov     rcx, [rsp+2A8h+var_18]
0x18002a45c  xor     rcx, rsp; StackCookie
0x18002a45f  call    __security_check_cookie
0x18002a464  add     rsp, 2A0h
0x18002a46b  pop     rbx
0x18002a46c  retn
```
