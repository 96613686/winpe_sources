# Kd1394Connection::ReadPhysicalMemory(unsigned __int64,void *,ulong,ulong *)

- ea: `0x1800db1f0`
- end: `0x1800db3f4`
- name: `?ReadPhysicalMemory@Kd1394Connection@@UEAAJ_KPEAXKPEAK@Z`
- size: `516`
- prototype: `int(Kd1394Connection *__hidden this, unsigned __int64, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callees

- `0x1800db1f0`
- `0x1800db3fc`
- `0x1800db578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db2e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db2f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db3c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db2e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db2f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db3c5`
- `api-ms-win-core-misc-l1-1-0!LocalAlloc` at `0x1800db23f`
- `api-ms-win-core-misc-l1-1-0!LocalAlloc` at `0x1800db23f`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db274`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db32b`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db33f`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db274`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db32b`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db33f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800db366`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800db366`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800db39e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800db39e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800db2d2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800db2d2`

## string_xrefs

- `0x1800db21c`: `Symlink must be established\n`

## pseudocode

```c
__int64 __fastcall Kd1394Connection::ReadPhysicalMemory(
        Kd1394Connection *this,
        __int64 a2,
        void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesRead)
{
  bool v5; // zf
  _QWORD *v11; // rdi
  unsigned int v12; // esi
  unsigned int v13; // ebx
  signed int v14; // eax
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+80h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 80) == 0;
  BytesReturned = 0;
  if ( v5 )
  {
    v11 = LocalAlloc(0x40u, 0x20u);
    if ( v11 )
    {
      v12 = Kd1394Connection::SwitchVirtualDebuggerDriverMode((Kd1394Connection *)((char *)this - 16), 1u);
      if ( v12 )
      {
        LocalFree(v11);
        return v12;
      }
      else
      {
        *(_DWORD *)v11 = 3;
        *(_QWORD *)((char *)v11 + 4) = 2;
        v11[2] = a2;
        if ( DeviceIoControl(*((HANDLE *)this + 4), 0x220800u, v11, 0x20u, 0, 0, &BytesReturned, 0) )
        {
          LocalFree(v11);
          if ( ReadFile(*((HANDLE *)this + 4), a3, a4, lpNumberOfBytesRead, (LPOVERLAPPED)((char *)this + 72))
            || GetLastError() == 997
            && GetOverlappedResult(*((HANDLE *)this + 4), (LPOVERLAPPED)((char *)this + 72), lpNumberOfBytesRead, 1) )
          {
            return 0;
          }
          else if ( GetLastError() )
          {
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            return (unsigned int)-2147467259;
          }
        }
        else
        {
          if ( GetLastError() )
          {
            v14 = GetLastError();
            v13 = v14;
            if ( v14 > 0 )
              v13 = (unsigned __int16)v14 | 0x80070000;
          }
          else
          {
            v13 = -2147467259;
          }
          LnkOut(2u, L"Failed to send SetIoParameters 1394 Virtual Driver Request, error 0x%x\n", v13);
          LocalFree(v11);
        }
        return v13;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    LnkOut(2u, L"Symlink must be established\n");
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800db1f0  mov     rax, rsp
0x1800db1f3  push    rbx
0x1800db1f4  push    rbp
0x1800db1f5  push    rsi
0x1800db1f6  push    rdi
0x1800db1f7  push    r14
0x1800db1f9  push    r15
0x1800db1fb  sub     rsp, 48h
0x1800db1ff  cmp     qword ptr [rcx+280h], 0
0x1800db207  mov     r14d, r9d
0x1800db20a  mov     r15, r8
0x1800db20d  mov     dword ptr [rax+8], 0
0x1800db214  mov     rbp, rdx
0x1800db217  mov     rbx, rcx
0x1800db21a  jz      short loc_1800DB237
0x1800db21c  lea     rdx, aSymlinkMustBeE; "Symlink must be established\n"
0x1800db223  mov     ecx, 2; unsigned int
0x1800db228  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1800db22d  mov     eax, 8000FFFFh
0x1800db232  jmp     loc_1800DB3E6
0x1800db237  mov     edx, 20h ; ' '; uBytes
0x1800db23c  lea     ecx, [rdx+20h]; uFlags
0x1800db23f  call    cs:__imp_LocalAlloc
0x1800db246  nop     dword ptr [rax+rax+00h]
0x1800db24b  mov     rdi, rax
0x1800db24e  test    rax, rax
0x1800db251  jnz     short loc_1800DB25D
0x1800db253  mov     eax, 8007000Eh
0x1800db258  jmp     loc_1800DB3E6
0x1800db25d  mov     edx, 1; unsigned int
0x1800db262  lea     rcx, [rbx-10h]; this
0x1800db266  call    ?SwitchVirtualDebuggerDriverMode@Kd1394Connection@@QEAAJK@Z; Kd1394Connection::SwitchVirtualDebuggerDriverMode(ulong)
0x1800db26b  mov     esi, eax
0x1800db26d  test    eax, eax
0x1800db26f  jz      short loc_1800DB287
0x1800db271  mov     rcx, rdi; hMem
0x1800db274  call    cs:__imp_LocalFree
0x1800db27b  nop     dword ptr [rax+rax+00h]
0x1800db280  mov     eax, esi
0x1800db282  jmp     loc_1800DB3E6
0x1800db287  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800db290  lea     rax, [rsp+78h+BytesReturned]
0x1800db298  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x1800db29d  mov     r9d, 20h ; ' '; nInBufferSize
0x1800db2a3  mov     dword ptr [rdi], 3
0x1800db2a9  mov     r8, rdi; lpInBuffer
0x1800db2ac  mov     qword ptr [rdi+4], 2
0x1800db2b4  mov     edx, 220800h; dwIoControlCode
0x1800db2b9  mov     [rdi+10h], rbp
0x1800db2bd  mov     rcx, [rbx+20h]; hDevice
0x1800db2c1  mov     [rsp+78h+nOutBufferSize], 0; nOutBufferSize
0x1800db2c9  mov     [rsp+78h+lpOutBuffer], 0; lpOutBuffer
0x1800db2d2  call    cs:__imp_DeviceIoControl
0x1800db2d9  nop     dword ptr [rax+rax+00h]
0x1800db2de  test    eax, eax
0x1800db2e0  jnz     short loc_1800DB33C
0x1800db2e2  call    cs:__imp_GetLastError
0x1800db2e9  nop     dword ptr [rax+rax+00h]
0x1800db2ee  test    eax, eax
0x1800db2f0  jnz     short loc_1800DB2F9
0x1800db2f2  mov     ebx, 80004005h
0x1800db2f7  jmp     short loc_1800DB314
0x1800db2f9  call    cs:__imp_GetLastError
0x1800db300  nop     dword ptr [rax+rax+00h]
0x1800db305  mov     ebx, eax
0x1800db307  test    eax, eax
0x1800db309  jle     short loc_1800DB314
0x1800db30b  movzx   ebx, ax
0x1800db30e  or      ebx, 80070000h
0x1800db314  mov     r8d, ebx
0x1800db317  lea     rdx, aFailedToSendSe; "Failed to send SetIoParameters 1394 Vir"...
0x1800db31e  mov     ecx, 2; unsigned int
0x1800db323  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1800db328  mov     rcx, rdi; hMem
0x1800db32b  call    cs:__imp_LocalFree
0x1800db332  nop     dword ptr [rax+rax+00h]
0x1800db337  jmp     loc_1800DB3E4
0x1800db33c  mov     rcx, rdi; hMem
0x1800db33f  call    cs:__imp_LocalFree
0x1800db346  nop     dword ptr [rax+rax+00h]
0x1800db34b  mov     r9, [rsp+78h+lpNumberOfBytesRead]; lpNumberOfBytesRead
0x1800db353  lea     rdi, [rbx+48h]
0x1800db357  mov     rcx, [rbx+20h]; hFile
0x1800db35b  mov     r8d, r14d; nNumberOfBytesToRead
0x1800db35e  mov     rdx, r15; lpBuffer
0x1800db361  mov     [rsp+78h+lpOutBuffer], rdi; lpOverlapped
0x1800db366  call    cs:__imp_ReadFile
0x1800db36d  nop     dword ptr [rax+rax+00h]
0x1800db372  test    eax, eax
0x1800db374  jnz     short loc_1800DB3E2
0x1800db376  call    cs:__imp_GetLastError
0x1800db37d  nop     dword ptr [rax+rax+00h]
0x1800db382  cmp     eax, 3E5h
0x1800db387  jnz     short loc_1800DB3AE
0x1800db389  mov     r8, [rsp+78h+lpNumberOfBytesRead]; lpNumberOfBytesTransferred
0x1800db391  mov     r9d, 1; bWait
0x1800db397  mov     rcx, [rbx+20h]; hFile
0x1800db39b  mov     rdx, rdi; lpOverlapped
0x1800db39e  call    cs:__imp_GetOverlappedResult
0x1800db3a5  nop     dword ptr [rax+rax+00h]
0x1800db3aa  test    eax, eax
0x1800db3ac  jnz     short loc_1800DB3E2
0x1800db3ae  call    cs:__imp_GetLastError
0x1800db3b5  nop     dword ptr [rax+rax+00h]
0x1800db3ba  test    eax, eax
0x1800db3bc  jnz     short loc_1800DB3C5
0x1800db3be  mov     ebx, 80004005h
0x1800db3c3  jmp     short loc_1800DB3E4
0x1800db3c5  call    cs:__imp_GetLastError
0x1800db3cc  nop     dword ptr [rax+rax+00h]
0x1800db3d1  mov     ebx, eax
0x1800db3d3  test    eax, eax
0x1800db3d5  jle     short loc_1800DB3E4
0x1800db3d7  movzx   ebx, ax
0x1800db3da  or      ebx, 80070000h
0x1800db3e0  jmp     short loc_1800DB3E4
0x1800db3e2  xor     ebx, ebx
0x1800db3e4  mov     eax, ebx
0x1800db3e6  add     rsp, 48h
0x1800db3ea  pop     r15
0x1800db3ec  pop     r14
0x1800db3ee  pop     rdi
0x1800db3ef  pop     rsi
0x1800db3f0  pop     rbp
0x1800db3f1  pop     rbx
0x1800db3f2  retn
```
