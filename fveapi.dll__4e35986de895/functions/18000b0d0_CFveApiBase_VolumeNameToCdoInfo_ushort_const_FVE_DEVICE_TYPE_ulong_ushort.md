# CFveApiBase::VolumeNameToCdoInfo(ushort const *,_FVE_DEVICE_TYPE *,ulong *,ushort * *)

- ea: `0x18000b0d0`
- end: `0x18000b1cb`
- name: `?VolumeNameToCdoInfo@CFveApiBase@@SAJPEBGPEAW4_FVE_DEVICE_TYPE@@PEAKPEAPEAG@Z`
- size: `251`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, enum _FVE_DEVICE_TYPE *, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180007f80`
- `0x18000a650`

## callees

- `0x180005410`
- `0x18000b0d0`
- `0x18000b1e0`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000b117`
- `ntdll!RtlSetThreadErrorMode` at `0x18000b1a1`
- `ntdll!RtlSetThreadErrorMode` at `0x18011f92c`
- `ntdll!RtlSetThreadErrorMode` at `0x18000b117`
- `ntdll!RtlSetThreadErrorMode` at `0x18000b1a1`
- `ntdll!RtlSetThreadErrorMode` at `0x18011f92c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b18f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b18f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f913`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b149`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b149`

## pseudocode

```c
__int64 __fastcall CFveApiBase::VolumeNameToCdoInfo(
        LPCWSTR lpFileName,
        enum _FVE_DEVICE_TYPE *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  __int64 v8; // rdi
  HANDLE FileW; // rax
  unsigned int LastHresultError; // ebx
  ULONG OldMode; // [rsp+48h] [rbp-50h] BYREF

  v8 = -1;
  OldMode = 0;
  RtlSetThreadErrorMode(0x10u, &OldMode);
  if ( lpFileName )
  {
    FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
    v8 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
      LastHresultError = GetLastHresultError();
    else
      LastHresultError = CFveApiBase::VolumeHandleToCdoInfo(FileW, a2, a3, a4);
  }
  else
  {
    LastHresultError = -2147024809;
  }
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  RtlSetThreadErrorMode(OldMode, 0);
  return LastHresultError;
}

```

## disassembly

```asm
0x18000b0d0  push    rbx
0x18000b0d2  push    rsi
0x18000b0d3  push    rdi
0x18000b0d4  push    r12
0x18000b0d6  push    r14
0x18000b0d8  push    r15
0x18000b0da  sub     rsp, 68h
0x18000b0de  mov     rax, cs:__security_cookie
0x18000b0e5  xor     rax, rsp
0x18000b0e8  mov     [rsp+98h+var_48], rax
0x18000b0ed  mov     r15, r9
0x18000b0f0  mov     r14, r8
0x18000b0f3  mov     rsi, rdx
0x18000b0f6  mov     rbx, rcx
0x18000b0f9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b100  mov     [rsp+98h+var_58], rdi
0x18000b105  xor     r12d, r12d
0x18000b108  mov     [rsp+98h+OldMode], r12d
0x18000b10d  lea     rdx, [rsp+98h+OldMode]; OldMode
0x18000b112  mov     ecx, 10h; NewMode
0x18000b117  call    cs:__imp_RtlSetThreadErrorMode
0x18000b11e  nop     dword ptr [rax+rax+00h]
0x18000b123  nop
0x18000b124  test    rbx, rbx
0x18000b127  jz      short loc_18000B181
0x18000b129  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x18000b12e  mov     [rsp+98h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000b133  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18000b13b  xor     r9d, r9d; lpSecurityAttributes
0x18000b13e  xor     edx, edx; dwDesiredAccess
0x18000b140  mov     r8d, 3; dwShareMode
0x18000b146  mov     rcx, rbx; lpFileName
0x18000b149  call    cs:__imp_CreateFileW
0x18000b150  nop     dword ptr [rax+rax+00h]
0x18000b155  mov     rdi, rax
0x18000b158  mov     [rsp+98h+var_58], rax
0x18000b15d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b161  jz      short loc_18000B178
0x18000b163  mov     r9, r15; unsigned __int16 **
0x18000b166  mov     r8, r14; unsigned int *
0x18000b169  mov     rdx, rsi; enum _FVE_DEVICE_TYPE *
0x18000b16c  mov     rcx, rax; hDevice
0x18000b16f  call    ?VolumeHandleToCdoInfo@CFveApiBase@@SAJPEAXPEAW4_FVE_DEVICE_TYPE@@PEAKPEAPEAG@Z; CFveApiBase::VolumeHandleToCdoInfo(void *,_FVE_DEVICE_TYPE *,ulong *,ushort * *)
0x18000b174  mov     ebx, eax
0x18000b176  jmp     short loc_18000B186
0x18000b178  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000b17d  mov     ebx, eax
0x18000b17f  jmp     short loc_18000B186
0x18000b181  mov     ebx, 80070057h
0x18000b186  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b18a  jz      short loc_18000B19B
0x18000b18c  mov     rcx, rdi; hObject
0x18000b18f  call    cs:__imp_CloseHandle
0x18000b196  nop     dword ptr [rax+rax+00h]
0x18000b19b  xor     edx, edx; OldMode
0x18000b19d  mov     ecx, [rsp+98h+OldMode]; NewMode
0x18000b1a1  call    cs:__imp_RtlSetThreadErrorMode
0x18000b1a8  nop     dword ptr [rax+rax+00h]
0x18000b1ad  mov     eax, ebx
0x18000b1af  mov     rcx, [rsp+98h+var_48]
0x18000b1b4  xor     rcx, rsp; StackCookie
0x18000b1b7  call    __security_check_cookie
0x18000b1bc  add     rsp, 68h
0x18000b1c0  pop     r15
0x18000b1c2  pop     r14
0x18000b1c4  pop     r12
0x18000b1c6  pop     rdi
0x18000b1c7  pop     rsi
0x18000b1c8  pop     rbx
0x18000b1c9  retn
0x18011f900  push    rbp
0x18011f902  sub     rsp, 40h
0x18011f906  mov     rbp, rdx
0x18011f909  mov     rcx, [rbp+40h]; hObject
0x18011f90d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011f911  jz      short loc_18011F927
0x18011f913  call    cs:__imp_CloseHandle
0x18011f91a  nop     dword ptr [rax+rax+00h]
0x18011f91f  mov     qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x18011f927  xor     edx, edx; OldMode
0x18011f929  mov     ecx, [rbp+48h]; NewMode
0x18011f92c  call    cs:__imp_RtlSetThreadErrorMode
0x18011f933  nop     dword ptr [rax+rax+00h]
0x18011f938  nop
0x18011f939  add     rsp, 40h
0x18011f93d  pop     rbp
0x18011f93e  retn
```
