# GetProcessIptTrace

- ea: `0x1800269bc`
- end: `0x180026ab3`
- name: `GetProcessIptTrace`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180013510`

## callees

- `0x180026988`
- `0x1800269bc`
- `0x18002a13c`

## import_xrefs

- `ntdll!NtClose` at `0x180026a85`
- `ntdll!NtClose` at `0x180026a85`
- `ntdll!NtDeviceIoControlFile` at `0x180026a79`
- `ntdll!NtDeviceIoControlFile` at `0x180026a79`
- `ntdll!RtlReleasePrivilege` at `0x180026a93`
- `ntdll!RtlReleasePrivilege` at `0x180026a93`

## pseudocode

```c
NTSTATUS __fastcall GetProcessIptTrace(__int64 a1, void *a2, ULONG a3)
{
  NTSTATUS result; // eax
  bool v7; // bl
  NTSTATUS v8; // edi
  PVOID ReturnedState; // [rsp+50h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-1h] BYREF
  __int128 InputBuffer; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v12; // [rsp+78h] [rbp+1Fh]
  __int128 v13; // [rsp+88h] [rbp+2Fh]
  HANDLE FileHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  ReturnedState = 0;
  InputBuffer = 0;
  v12 = 0;
  v13 = 0;
  IoStatusBlock = 0;
  if ( a3 < 8 )
    return -1073741811;
  result = OpenIptDevice(&FileHandle);
  if ( result >= 0 )
  {
    v7 = AcquireDebugPrivilege(&ReturnedState);
    *(_QWORD *)&InputBuffer = 1;
    LOWORD(v12) = 1;
    DWORD2(InputBuffer) = 2;
    *((_QWORD *)&v12 + 1) = a1;
    v8 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x220006u, &InputBuffer, 0x30u, a2, a3);
    NtClose(FileHandle);
    if ( v7 )
      RtlReleasePrivilege(ReturnedState);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800269bc  mov     [rsp-8+arg_0], rbx
0x1800269c1  mov     [rsp-8+arg_8], rsi
0x1800269c6  push    rbp
0x1800269c7  push    rdi
0x1800269c8  push    r14
0x1800269ca  lea     rbp, [rsp-47h]
0x1800269cf  sub     rsp, 0A0h
0x1800269d6  mov     [rbp+57h+FileHandle], 0
0x1800269de  xorps   xmm0, xmm0
0x1800269e1  mov     [rbp+57h+ReturnedState], 0
0x1800269e9  mov     edi, r8d
0x1800269ec  mov     rsi, rdx
0x1800269ef  mov     r14, rcx
0x1800269f2  movups  [rbp+57h+var_48], xmm0
0x1800269f6  movups  [rbp+57h+var_38], xmm0
0x1800269fa  movups  [rbp+57h+var_28], xmm0
0x1800269fe  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180026a02  cmp     r8d, 8
0x180026a06  jnb     short loc_180026A12
0x180026a08  mov     eax, 0C000000Dh
0x180026a0d  jmp     loc_180026A9B
0x180026a12  lea     rcx, [rbp+57h+FileHandle]
0x180026a16  call    OpenIptDevice
0x180026a1b  test    eax, eax
0x180026a1d  js      short loc_180026A9B
0x180026a1f  lea     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x180026a23  call    AcquireDebugPrivilege
0x180026a28  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180026a2c  mov     bl, al
0x180026a2e  mov     [rsp+0B0h+OutputBufferLength], edi; OutputBufferLength
0x180026a32  mov     eax, 1
0x180026a37  mov     [rsp+0B0h+OutputBuffer], rsi; OutputBuffer
0x180026a3c  xor     r9d, r9d; ApcContext
0x180026a3f  mov     qword ptr [rbp+57h+var_48], rax
0x180026a43  xor     r8d, r8d; ApcRoutine
0x180026a46  mov     word ptr [rbp+57h+var_38], ax
0x180026a4a  xor     edx, edx; Event
0x180026a4c  mov     [rsp+0B0h+InputBufferLength], 30h ; '0'; InputBufferLength
0x180026a54  lea     rax, [rbp+57h+var_48]
0x180026a58  mov     [rsp+0B0h+InputBuffer], rax; InputBuffer
0x180026a5d  lea     rax, [rbp+57h+var_58]
0x180026a61  mov     [rsp+0B0h+IoControlCode], 220006h; IoControlCode
0x180026a69  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x180026a6e  mov     dword ptr [rbp+57h+var_48+8], 2
0x180026a75  mov     qword ptr [rbp+57h+var_38+8], r14
0x180026a79  call    cs:__imp_NtDeviceIoControlFile
0x180026a7f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180026a83  mov     edi, eax
0x180026a85  call    cs:__imp_NtClose
0x180026a8b  test    bl, bl
0x180026a8d  jz      short loc_180026A99
0x180026a8f  mov     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x180026a93  call    cs:__imp_RtlReleasePrivilege
0x180026a99  mov     eax, edi
0x180026a9b  lea     r11, [rsp+0B0h+var_10]
0x180026aa3  mov     rbx, [r11+20h]
0x180026aa7  mov     rsi, [r11+28h]
0x180026aab  mov     rsp, r11
0x180026aae  pop     r14
0x180026ab0  pop     rdi
0x180026ab1  pop     rbp
0x180026ab2  retn
```
