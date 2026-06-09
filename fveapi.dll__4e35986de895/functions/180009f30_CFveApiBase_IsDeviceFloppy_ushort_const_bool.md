# CFveApiBase::IsDeviceFloppy(ushort const *,bool *)

- ea: `0x180009f30`
- end: `0x18000a1b4`
- name: `?IsDeviceFloppy@CFveApiBase@@SAJPEBGPEA_N@Z`
- size: `644`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180007f80`
- `0x180009790`

## callees

- `0x180009f30`
- `0x18005e368`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18000a0f7`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000a0f7`
- `ntdll!RtlNtStatusToDosError` at `0x18000a105`
- `ntdll!RtlNtStatusToDosError` at `0x18000a105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f6c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f6c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a09b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a09b`

## pseudocode

```c
__int64 __fastcall CFveApiBase::IsDeviceFloppy(const unsigned __int16 *a1, bool *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  WCHAR *v8; // rdx
  signed int v9; // esi
  __int64 v10; // r9
  HANDLE FileW; // rax
  signed int LastError; // eax
  NTSTATUS v13; // eax
  signed int v14; // eax
  unsigned __int64 v15; // rbx
  __int64 FsInformation; // [rsp+78h] [rbp-250h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+90h] [rbp-238h] BYREF

  v4 = -1;
  FsInformation = 0;
  IoStatusBlock = 0;
  memset_0(FileName, 0, 0x208u);
  if ( a1 && a2 )
  {
    *a2 = 0;
    v6 = 2147483646;
    v7 = 260;
    v8 = FileName;
    v9 = 0;
    v10 = 0;
    while ( v7 )
    {
      if ( !v6 )
        goto LABEL_10;
      v5 = *a1;
      if ( !(_WORD)v5 )
        goto LABEL_10;
      ++a1;
      *v8++ = v5;
      --v7;
      --v6;
      ++v10;
    }
    --v8;
    --v10;
    v9 = -2147024774;
LABEL_10:
    *v8 = 0;
    if ( v9 >= 0 )
    {
      do
        ++v4;
      while ( FileName[v4] );
      if ( v4 && *((_WORD *)&IoStatusBlock.Information + v4 + 3) == 92 )
      {
        v15 = 2 * v4 - 2;
        if ( v15 >= 0x208 )
          _report_rangecheckfailure(v6, v8, v5, v10);
        *(WCHAR *)((char *)FileName + v15) = 0;
      }
      FileW = CreateFileW(FileName, 0x80u, 3u, 0, 3u, 0, 0);
      v4 = (__int64)FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v13 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
        v14 = RtlNtStatusToDosError(v13);
        v9 = v14;
        if ( v14 > 0 )
          v9 = (unsigned __int16)v14 | 0x80070000;
        if ( v9 >= 0 && (FsInformation & 0x400000000LL) != 0 )
          *a2 = 1;
      }
    }
  }
  else
  {
    v9 = -2147467261;
  }
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009f30  mov     [rsp+arg_0], rbx
0x180009f35  mov     [rsp+arg_10], rsi
0x180009f3a  push    rdi
0x180009f3b  push    r14
0x180009f3d  push    r15
0x180009f3f  sub     rsp, 2B0h
0x180009f46  mov     rax, cs:__security_cookie
0x180009f4d  xor     rax, rsp
0x180009f50  mov     [rsp+2C8h+var_28], rax
0x180009f58  mov     r14, rdx
0x180009f5b  mov     rdi, rcx
0x180009f5e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180009f65  mov     [rsp+2C8h+var_270], rbx
0x180009f6a  xor     r15d, r15d
0x180009f6d  mov     [rsp+2C8h+FsInformation], r15
0x180009f72  xorps   xmm0, xmm0
0x180009f75  movups  xmmword ptr [rsp+2C8h+IoStatusBlock], xmm0
0x180009f7d  xor     edx, edx; Val
0x180009f7f  mov     r8d, 208h; Size
0x180009f85  lea     rcx, [rsp+2C8h+FileName]; void *
0x180009f8d  call    memset_0
0x180009f92  nop
0x180009f93  test    rdi, rdi
0x180009f96  jz      loc_18000A163
0x180009f9c  test    r14, r14
0x180009f9f  jz      loc_18000A163
0x180009fa5  mov     [r14], r15b
0x180009fa8  mov     [rsp+2C8h+var_284], r15d
0x180009fad  mov     [rsp+2C8h+var_284], r15d
0x180009fb2  mov     ecx, 7FFFFFFEh
0x180009fb7  mov     [rsp+2C8h+var_258], rcx
0x180009fbc  mov     [rsp+2C8h+var_268], rdi
0x180009fc1  mov     eax, 104h
0x180009fc6  mov     [rsp+2C8h+var_260], rax
0x180009fcb  lea     rdx, [rsp+2C8h+FileName]
0x180009fd3  mov     [rsp+2C8h+var_280], rdx
0x180009fd8  mov     esi, r15d
0x180009fdb  mov     r9d, r15d
0x180009fde  mov     [rsp+2C8h+var_278], r15
0x180009fe3  test    rax, rax
0x180009fe6  jz      short loc_18000A02C
0x180009fe8  test    rcx, rcx
0x180009feb  jz      short loc_18000A027
0x180009fed  movzx   r8d, word ptr [rdi]
0x180009ff1  test    r8w, r8w
0x180009ff5  jz      short loc_18000A027
0x180009ff7  add     rdi, 2
0x180009ffb  mov     [rsp+2C8h+var_268], rdi
0x18000a000  mov     [rdx], r8w
0x18000a004  add     rdx, 2
0x18000a008  mov     [rsp+2C8h+var_280], rdx
0x18000a00d  dec     rax
0x18000a010  mov     [rsp+2C8h+var_260], rax
0x18000a015  dec     rcx
0x18000a018  mov     [rsp+2C8h+var_258], rcx
0x18000a01d  inc     r9
0x18000a020  mov     [rsp+2C8h+var_278], r9
0x18000a025  jmp     short loc_180009FE3
0x18000a027  test    rax, rax
0x18000a02a  jnz     short loc_18000A042
0x18000a02c  sub     rdx, 2
0x18000a030  mov     [rsp+2C8h+var_280], rdx
0x18000a035  dec     r9
0x18000a038  mov     [rsp+2C8h+var_278], r9
0x18000a03d  mov     esi, 8007007Ah
0x18000a042  mov     eax, r15d
0x18000a045  mov     [rdx], ax
0x18000a048  mov     [rsp+2C8h+var_284], esi
0x18000a04c  mov     [rsp+2C8h+var_288], esi
0x18000a050  test    esi, esi
0x18000a052  js      loc_18000A173
0x18000a058  lea     rax, [rsp+2C8h+FileName]
0x18000a060  inc     rbx
0x18000a063  cmp     word ptr [rax+rbx*2], 0
0x18000a068  jnz     short loc_18000A060
0x18000a06a  test    rbx, rbx
0x18000a06d  jnz     loc_18000A135
0x18000a073  mov     [rsp+2C8h+hTemplateFile], r15; hTemplateFile
0x18000a078  mov     [rsp+2C8h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18000a07d  mov     [rsp+2C8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a085  xor     r9d, r9d; lpSecurityAttributes
0x18000a088  mov     edx, 80h; dwDesiredAccess
0x18000a08d  mov     r8d, 3; dwShareMode
0x18000a093  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x18000a09b  call    cs:__imp_CreateFileW
0x18000a0a2  nop     dword ptr [rax+rax+00h]
0x18000a0a7  mov     rbx, rax
0x18000a0aa  mov     [rsp+2C8h+var_270], rax
0x18000a0af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a0b3  jnz     short loc_18000A0D9
0x18000a0b5  call    cs:__imp_GetLastError
0x18000a0bc  nop     dword ptr [rax+rax+00h]
0x18000a0c1  mov     esi, eax
0x18000a0c3  test    eax, eax
0x18000a0c5  jle     short loc_18000A0D0
0x18000a0c7  movzx   esi, ax
0x18000a0ca  or      esi, 80070000h
0x18000a0d0  mov     [rsp+2C8h+var_288], esi
0x18000a0d4  jmp     loc_18000A173
0x18000a0d9  mov     [rsp+2C8h+dwCreationDisposition], 4; FsInformationClass
0x18000a0e1  mov     r9d, 8; Length
0x18000a0e7  lea     r8, [rsp+2C8h+FsInformation]; FsInformation
0x18000a0ec  lea     rdx, [rsp+2C8h+IoStatusBlock]; IoStatusBlock
0x18000a0f4  mov     rcx, rax; FileHandle
0x18000a0f7  call    cs:__imp_NtQueryVolumeInformationFile
0x18000a0fe  nop     dword ptr [rax+rax+00h]
0x18000a103  mov     ecx, eax; Status
0x18000a105  call    cs:__imp_RtlNtStatusToDosError
0x18000a10c  nop     dword ptr [rax+rax+00h]
0x18000a111  mov     esi, eax
0x18000a113  test    eax, eax
0x18000a115  jle     short loc_18000A120
0x18000a117  movzx   esi, ax
0x18000a11a  or      esi, 80070000h
0x18000a120  mov     [rsp+2C8h+var_288], esi
0x18000a124  test    esi, esi
0x18000a126  js      short loc_18000A173
0x18000a128  test    byte ptr [rsp+2C8h+FsInformation+4], 4
0x18000a12d  jz      short loc_18000A173
0x18000a12f  mov     byte ptr [r14], 1
0x18000a133  jmp     short loc_18000A173
0x18000a135  cmp     word ptr [rsp+rbx*2+2C8h+IoStatusBlock.Information+6], 5Ch ; '\'
0x18000a13e  jnz     loc_18000A073
0x18000a144  lea     rbx, ds:0FFFFFFFFFFFFFFFEh[rbx*2]
0x18000a14c  cmp     rbx, 208h
0x18000a153  jnb     short loc_18000A16D
0x18000a155  mov     [rsp+rbx+2C8h+FileName], r15w
0x18000a15e  jmp     loc_18000A073
0x18000a163  mov     esi, 80004003h
0x18000a168  jmp     loc_18000A0D0
0x18000a16d  call    __report_rangecheckfailure
0x18000a173  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a177  jz      short loc_18000A188
0x18000a179  mov     rcx, rbx; hObject
0x18000a17c  call    cs:__imp_CloseHandle
0x18000a183  nop     dword ptr [rax+rax+00h]
0x18000a188  mov     eax, esi
0x18000a18a  mov     rcx, [rsp+2C8h+var_28]
0x18000a192  xor     rcx, rsp; StackCookie
0x18000a195  call    __security_check_cookie
0x18000a19a  lea     r11, [rsp+2C8h+var_18]
0x18000a1a2  mov     rbx, [r11+20h]
0x18000a1a6  mov     rsi, [r11+30h]
0x18000a1aa  mov     rsp, r11
0x18000a1ad  pop     r15
0x18000a1af  pop     r14
0x18000a1b1  pop     rdi
0x18000a1b2  retn
0x18011f6b0  push    rbp
0x18011f6b2  sub     rsp, 40h
0x18011f6b6  mov     rbp, rdx
0x18011f6b9  mov     rcx, [rbp+58h]; hObject
0x18011f6bd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011f6c1  jz      short loc_18011F6D0
0x18011f6c3  call    cs:__imp_CloseHandle
0x18011f6ca  nop     dword ptr [rax+rax+00h]
0x18011f6cf  nop
0x18011f6d0  add     rsp, 40h
0x18011f6d4  pop     rbp
0x18011f6d5  retn
```
