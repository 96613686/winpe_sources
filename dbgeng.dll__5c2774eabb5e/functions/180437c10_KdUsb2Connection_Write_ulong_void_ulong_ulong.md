# KdUsb2Connection::Write(ulong,void *,ulong,ulong *)

- ea: `0x180437c10`
- end: `0x180437e0e`
- name: `?Write@KdUsb2Connection@@UEAAJKPEAXKPEAK@Z`
- size: `510`
- prototype: `int(KdUsb2Connection *__hidden this, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800b94c4`
- `0x1800db578`
- `0x1803f6e1c`
- `0x180431fe0`
- `0x180437c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437d43`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x180437cae`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x180437cae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180437d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180437d7a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180437c92`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180437c92`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180437ce5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180437ce5`

## string_xrefs

- `0x180437d92`: `USB: Write error %d\n`
- `0x180437d6b`: `USB: Write error Not Connected, closing\n`
- `0x180437c6c`: `USB: Write opened\n`

## pseudocode

```c
__int64 __fastcall KdUsb2Connection::Write(KdUsb2Connection *this, int a2, void *a3, DWORD a4, unsigned int *a5)
{
  unsigned int v8; // ebx
  void **v9; // rsi
  const unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  DWORD LastError; // ebp
  signed int v15; // eax
  signed int v16; // eax
  KdConnection *v17; // rcx
  unsigned int v18; // eax
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    v8 = -2147024809;
    goto LABEL_33;
  }
  v9 = (void **)((char *)this + 32);
  if ( !*((_QWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 47) < 2u )
      v10 = 0;
    else
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 22);
    v8 = OpenUSB2Channel(v10, v9);
    if ( v8 )
    {
      Sleep(0x1F4u);
      goto LABEL_33;
    }
    LnkOut(1u, L"USB: Write opened\n");
  }
  if ( WriteFile(*v9, a3, a4, &NumberOfBytesWritten, (LPOVERLAPPED)((char *)this + 104)) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError != 997 )
  {
    if ( GetLastError() )
    {
      v16 = GetLastError();
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    if ( LastError == 1167 )
    {
      LnkOut(0x80000000, L"USB: Write error Not Connected, closing\n");
      CloseHandle(*v9);
      *v9 = 0;
    }
    else
    {
      LnkOut(0x80000000, L"USB: Write error %d\n", LastError);
    }
    goto LABEL_25;
  }
  if ( !GetOverlappedResult(*v9, (LPOVERLAPPED)((char *)this + 104), &NumberOfBytesWritten, 1) )
  {
    if ( !GetLastError() )
    {
      v8 = -2147467259;
      goto LABEL_33;
    }
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
LABEL_25:
    if ( v8 )
      goto LABEL_33;
    goto LABEL_26;
  }
LABEL_10:
  v8 = 0;
LABEL_26:
  if ( (*((_BYTE *)this + 56) & 2) != 0 )
  {
    v17 = (KdConnection *)NumberOfBytesWritten;
    if ( NumberOfBytesWritten > a4 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(NumberOfBytesWritten, v11, v12, v13);
      v17 = (KdConnection *)NumberOfBytesWritten;
    }
    v18 = a4;
    if ( (unsigned int)v17 < a4 )
      v18 = (unsigned int)v17;
    KdConnection::OutputIo(v17, L"USB: Wrote %d bytes of %d\n", a3, a4, v18);
  }
  *((_QWORD *)this + 20) += NumberOfBytesWritten;
  *((_BYTE *)this + 8444) = 1;
LABEL_33:
  if ( a5 )
    *a5 = NumberOfBytesWritten;
  return v8;
}

```

## disassembly

```asm
0x180437c10  push    rbx
0x180437c12  push    rbp
0x180437c13  push    rsi
0x180437c14  push    rdi
0x180437c15  push    r14
0x180437c17  push    r15
0x180437c19  sub     rsp, 38h
0x180437c1d  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180437c25  mov     r14d, r9d
0x180437c28  mov     r15, r8
0x180437c2b  mov     rdi, rcx
0x180437c2e  test    edx, 0FFFFFFFCh
0x180437c34  jz      short loc_180437C40
0x180437c36  mov     ebx, 80070057h
0x180437c3b  jmp     loc_180437DEB
0x180437c40  lea     rsi, [rcx+20h]
0x180437c44  cmp     qword ptr [rsi], 0
0x180437c48  jnz     short loc_180437C7B
0x180437c4a  cmp     dword ptr [rcx+0BCh], 2
0x180437c51  jb      short loc_180437C5C
0x180437c53  mov     rcx, [rcx+0B0h]
0x180437c5a  jmp     short loc_180437C5E
0x180437c5c  xor     ecx, ecx; Src
0x180437c5e  mov     rdx, rsi; void **
0x180437c61  call    ?OpenUSB2Channel@@YAJPEBGPEAPEAX@Z; OpenUSB2Channel(ushort const *,void * *)
0x180437c66  mov     ebx, eax
0x180437c68  test    eax, eax
0x180437c6a  jnz     short loc_180437CA9
0x180437c6c  lea     rdx, aUsbWriteOpened; "USB: Write opened\n"
0x180437c73  lea     ecx, [rax+1]; unsigned int
0x180437c76  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180437c7b  mov     rcx, [rsi]; hFile
0x180437c7e  lea     rbx, [rdi+68h]
0x180437c82  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180437c87  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x180437c8c  mov     r8d, r14d; nNumberOfBytesToWrite
0x180437c8f  mov     rdx, r15; lpBuffer
0x180437c92  call    cs:__imp_WriteFile
0x180437c99  nop     dword ptr [rax+rax+00h]
0x180437c9e  test    eax, eax
0x180437ca0  jz      short loc_180437CBF
0x180437ca2  xor     ebx, ebx
0x180437ca4  jmp     loc_180437DA2
0x180437ca9  mov     ecx, 1F4h; dwMilliseconds
0x180437cae  call    cs:__imp_Sleep
0x180437cb5  nop     dword ptr [rax+rax+00h]
0x180437cba  jmp     loc_180437DEB
0x180437cbf  call    cs:__imp_GetLastError
0x180437cc6  nop     dword ptr [rax+rax+00h]
0x180437ccb  mov     ebp, eax
0x180437ccd  cmp     eax, 3E5h
0x180437cd2  jnz     short loc_180437D2C
0x180437cd4  mov     rcx, [rsi]; hFile
0x180437cd7  lea     r8, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x180437cdc  mov     r9d, 1; bWait
0x180437ce2  mov     rdx, rbx; lpOverlapped
0x180437ce5  call    cs:__imp_GetOverlappedResult
0x180437cec  nop     dword ptr [rax+rax+00h]
0x180437cf1  test    eax, eax
0x180437cf3  jnz     short loc_180437CA2
0x180437cf5  call    cs:__imp_GetLastError
0x180437cfc  nop     dword ptr [rax+rax+00h]
0x180437d01  test    eax, eax
0x180437d03  jnz     short loc_180437D0F
0x180437d05  mov     ebx, 80004005h
0x180437d0a  jmp     loc_180437DEB
0x180437d0f  call    cs:__imp_GetLastError
0x180437d16  nop     dword ptr [rax+rax+00h]
0x180437d1b  mov     ebx, eax
0x180437d1d  test    eax, eax
0x180437d1f  jle     short loc_180437D9E
0x180437d21  movzx   ebx, ax
0x180437d24  or      ebx, 80070000h
0x180437d2a  jmp     short loc_180437D9E
0x180437d2c  call    cs:__imp_GetLastError
0x180437d33  nop     dword ptr [rax+rax+00h]
0x180437d38  test    eax, eax
0x180437d3a  jnz     short loc_180437D43
0x180437d3c  mov     ebx, 80004005h
0x180437d41  jmp     short loc_180437D5E
0x180437d43  call    cs:__imp_GetLastError
0x180437d4a  nop     dword ptr [rax+rax+00h]
0x180437d4f  mov     ebx, eax
0x180437d51  test    eax, eax
0x180437d53  jle     short loc_180437D5E
0x180437d55  movzx   ebx, ax
0x180437d58  or      ebx, 80070000h
0x180437d5e  mov     ecx, 80000000h; unsigned int
0x180437d63  cmp     ebp, 48Fh
0x180437d69  jnz     short loc_180437D8F
0x180437d6b  lea     rdx, aUsbWriteErrorN; "USB: Write error Not Connected, closing"...
0x180437d72  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180437d77  mov     rcx, [rsi]; hObject
0x180437d7a  call    cs:__imp_CloseHandle
0x180437d81  nop     dword ptr [rax+rax+00h]
0x180437d86  mov     qword ptr [rsi], 0
0x180437d8d  jmp     short loc_180437D9E
0x180437d8f  mov     r8d, ebp
0x180437d92  lea     rdx, aUsbWriteErrorD; "USB: Write error %d\n"
0x180437d99  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180437d9e  test    ebx, ebx
0x180437da0  jnz     short loc_180437DEB
0x180437da2  test    byte ptr [rdi+38h], 2
0x180437da6  jz      short loc_180437DD9
0x180437da8  mov     ecx, [rsp+68h+NumberOfBytesWritten]
0x180437dac  cmp     ecx, r14d
0x180437daf  jbe     short loc_180437DBA
0x180437db1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180437db6  mov     ecx, [rsp+68h+NumberOfBytesWritten]; this
0x180437dba  cmp     ecx, r14d
0x180437dbd  lea     rdx, aUsbWroteDBytes; "USB: Wrote %d bytes of %d\n"
0x180437dc4  mov     eax, r14d
0x180437dc7  mov     r9d, r14d; unsigned int
0x180437dca  cmovb   eax, ecx
0x180437dcd  mov     r8, r15; void *
0x180437dd0  mov     dword ptr [rsp+68h+lpOverlapped], eax; unsigned int
0x180437dd4  call    ?OutputIo@KdConnection@@QEAAXPEAGPEAXKK@Z; KdConnection::OutputIo(ushort *,void *,ulong,ulong)
0x180437dd9  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180437ddd  add     [rdi+0A0h], rax
0x180437de4  mov     byte ptr [rdi+20FCh], 1
0x180437deb  mov     rcx, [rsp+68h+arg_20]
0x180437df3  test    rcx, rcx
0x180437df6  jz      short loc_180437DFE
0x180437df8  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180437dfc  mov     [rcx], eax
0x180437dfe  mov     eax, ebx
0x180437e00  add     rsp, 38h
0x180437e04  pop     r15
0x180437e06  pop     r14
0x180437e08  pop     rdi
0x180437e09  pop     rsi
0x180437e0a  pop     rbp
0x180437e0b  pop     rbx
0x180437e0c  retn
```
