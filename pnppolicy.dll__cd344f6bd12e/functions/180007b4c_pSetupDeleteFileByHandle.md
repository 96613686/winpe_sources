# pSetupDeleteFileByHandle

- ea: `0x180007b4c`
- end: `0x180007c54`
- name: `pSetupDeleteFileByHandle`
- size: `264`
- prototype: `_BOOL8 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800054d4`

## callees

- `0x180007b4c`
- `0x18000a1a0`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180007bb2`
- `ntdll!NtQueryInformationFile` at `0x180007bb2`
- `ntdll!RtlNtStatusToDosError` at `0x180007c1c`
- `ntdll!RtlNtStatusToDosError` at `0x180007c1c`
- `ntdll!NtSetInformationFile` at `0x180007bf1`
- `ntdll!NtSetInformationFile` at `0x180007c10`
- `ntdll!NtSetInformationFile` at `0x180007bf1`
- `ntdll!NtSetInformationFile` at `0x180007c10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c26`

## pseudocode

```c
_BOOL8 __fastcall pSetupDeleteFileByHandle(HANDLE FileHandle)
{
  ULONG v2; // ebx
  int v3; // eax
  char v5[8]; // [rsp+30h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v8; // [rsp+58h] [rbp-28h]
  __int64 v9; // [rsp+68h] [rbp-18h]

  v5[0] = 1;
  v9 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v8 = 0;
  if ( FileHandle == (HANDLE)-1LL )
  {
    v2 = 87;
  }
  else
  {
    v2 = 0;
    if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation) >= 0
      && (v9 & 1) != 0 )
    {
      v9 = 128;
      FileInformation = 0;
      v8 = 0;
      NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    }
    v3 = NtSetInformationFile(FileHandle, &IoStatusBlock, v5, 1u, FileDispositionInformation);
    if ( v3 < 0 )
      v2 = RtlNtStatusToDosError(v3);
  }
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x180007b4c  mov     [rsp-8+arg_8], rbx
0x180007b51  mov     [rsp-8+arg_10], rdi
0x180007b56  push    rbp
0x180007b57  mov     rbp, rsp
0x180007b5a  sub     rsp, 80h
0x180007b61  mov     rax, cs:__security_cookie
0x180007b68  xor     rax, rsp
0x180007b6b  mov     [rbp+var_10], rax
0x180007b6f  xor     eax, eax
0x180007b71  mov     [rbp+var_50], 1
0x180007b75  mov     [rbp+var_18], rax
0x180007b79  xorps   xmm1, xmm1
0x180007b7c  xorps   xmm0, xmm0
0x180007b7f  mov     rdi, rcx
0x180007b82  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180007b86  movups  [rbp+FileInformation], xmm1
0x180007b8a  movups  [rbp+var_28], xmm1
0x180007b8e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007b92  jnz     short loc_180007B9C
0x180007b94  lea     ebx, [rcx+58h]
0x180007b97  jmp     loc_180007C24
0x180007b9c  xor     ebx, ebx
0x180007b9e  mov     [rsp+80h+FileInformationClass], 4; FileInformationClass
0x180007ba6  lea     r8, [rbp+FileInformation]; FileInformation
0x180007baa  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180007bae  lea     r9d, [rbx+28h]; Length
0x180007bb2  call    cs:__imp_NtQueryInformationFile
0x180007bb8  test    eax, eax
0x180007bba  js      short loc_180007BF7
0x180007bbc  test    byte ptr [rbp+var_18], 1
0x180007bc0  jz      short loc_180007BF7
0x180007bc2  xorps   xmm0, xmm0
0x180007bc5  mov     [rsp+80h+FileInformationClass], 4; FileInformationClass
0x180007bcd  xor     eax, eax
0x180007bcf  lea     r9d, [rbx+28h]; Length
0x180007bd3  mov     [rbp+var_18], rax
0x180007bd7  lea     r8, [rbp+FileInformation]; FileInformation
0x180007bdb  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180007bdf  mov     dword ptr [rbp+var_18], 80h
0x180007be6  mov     rcx, rdi; FileHandle
0x180007be9  movups  [rbp+FileInformation], xmm0
0x180007bed  movups  [rbp+var_28], xmm0
0x180007bf1  call    cs:__imp_NtSetInformationFile
0x180007bf7  mov     r9d, 1; Length
0x180007bfd  mov     [rsp+80h+FileInformationClass], 0Dh; FileInformationClass
0x180007c05  lea     r8, [rbp+var_50]; FileInformation
0x180007c09  mov     rcx, rdi; FileHandle
0x180007c0c  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180007c10  call    cs:__imp_NtSetInformationFile
0x180007c16  test    eax, eax
0x180007c18  jns     short loc_180007C24
0x180007c1a  mov     ecx, eax; Status
0x180007c1c  call    cs:__imp_RtlNtStatusToDosError
0x180007c22  mov     ebx, eax
0x180007c24  mov     ecx, ebx; dwErrCode
0x180007c26  call    cs:__imp_SetLastError
0x180007c2c  xor     eax, eax
0x180007c2e  test    ebx, ebx
0x180007c30  setz    al
0x180007c33  mov     rcx, [rbp+var_10]
0x180007c37  xor     rcx, rsp; StackCookie
0x180007c3a  call    __security_check_cookie
0x180007c3f  lea     r11, [rsp+80h+var_s0]
0x180007c47  mov     rbx, [r11+18h]
0x180007c4b  mov     rdi, [r11+20h]
0x180007c4f  mov     rsp, r11
0x180007c52  pop     rbp
0x180007c53  retn
```
