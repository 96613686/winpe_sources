# NdisEnumerateInterfaces

- ea: `0x180030ccc`
- end: `0x180030dd3`
- name: `NdisEnumerateInterfaces`
- size: `263`
- prototype: `__int64 __fastcall(char *lpOutBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000fdac`

## callees

- `0x180030ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030db8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030db8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030dc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030d5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030d09`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030d09`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180030d4a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180030d4a`

## pseudocode

```c
__int64 __fastcall NdisEnumerateInterfaces(char *lpOutBuffer)
{
  HANDLE FileW; // rbp
  unsigned int v3; // esi
  DWORD LastError; // edi
  unsigned int i; // r8d
  __int64 v6; // rdx
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF

  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v3 = 0;
    LastError = GetLastError();
  }
  else
  {
    v3 = DeviceIoControl(FileW, 0x170010u, 0, 0, lpOutBuffer, 0x100u, &BytesReturned, 0);
    LastError = GetLastError();
    CloseHandle(FileW);
    if ( v3 || LastError == 234 )
    {
      for ( i = 0;
            i < *(_DWORD *)lpOutBuffer;
            *(_QWORD *)&lpOutBuffer[v6 + 40] = (unsigned __int64)&lpOutBuffer[*(_QWORD *)&lpOutBuffer[v6 + 40]]
                                             & -(__int64)(*(_QWORD *)&lpOutBuffer[v6 + 40] != 0) )
      {
        v6 = 32LL * i;
        *(_QWORD *)&lpOutBuffer[v6 + 24] = (unsigned __int64)&lpOutBuffer[*(_QWORD *)&lpOutBuffer[v6 + 24]]
                                         & -(__int64)(*(_QWORD *)&lpOutBuffer[v6 + 24] != 0);
        ++i;
      }
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x180030ccc  mov     rax, rsp
0x180030ccf  mov     [rax+10h], edx
0x180030cd2  push    rbx
0x180030cd3  push    rbp
0x180030cd4  push    rsi
0x180030cd5  push    rdi
0x180030cd6  sub     rsp, 48h
0x180030cda  mov     qword ptr [rax-38h], 0
0x180030ce2  mov     rbx, rcx
0x180030ce5  mov     dword ptr [rax-40h], 0
0x180030cec  lea     rcx, FileName; "\\\\.\\NDIS"
0x180030cf3  xor     r9d, r9d; lpSecurityAttributes
0x180030cf6  mov     dword ptr [rax-48h], 3
0x180030cfd  xor     r8d, r8d; dwShareMode
0x180030d00  mov     dword ptr [rax+10h], 0
0x180030d07  xor     edx, edx; dwDesiredAccess
0x180030d09  call    cs:__imp_CreateFileW
0x180030d0f  mov     rbp, rax
0x180030d12  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030d16  jz      loc_180030DB6
0x180030d1c  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180030d25  lea     rax, [rsp+68h+BytesReturned]
0x180030d2a  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180030d2f  xor     r9d, r9d; nInBufferSize
0x180030d32  mov     [rsp+68h+nOutBufferSize], 100h; nOutBufferSize
0x180030d3a  xor     r8d, r8d; lpInBuffer
0x180030d3d  mov     edx, 170010h; dwIoControlCode
0x180030d42  mov     [rsp+68h+lpOutBuffer], rbx; lpOutBuffer
0x180030d47  mov     rcx, rbp; hDevice
0x180030d4a  call    cs:__imp_DeviceIoControl
0x180030d50  mov     esi, eax
0x180030d52  call    cs:__imp_GetLastError
0x180030d58  mov     rcx, rbp; hObject
0x180030d5b  mov     edi, eax
0x180030d5d  call    cs:__imp_CloseHandle
0x180030d63  test    esi, esi
0x180030d65  jnz     short loc_180030D6F
0x180030d67  cmp     edi, 0EAh
0x180030d6d  jnz     short loc_180030DC0
0x180030d6f  xor     r8d, r8d
0x180030d72  cmp     [rbx], r8d
0x180030d75  jbe     short loc_180030DC0
0x180030d77  mov     edx, r8d
0x180030d7a  shl     rdx, 5
0x180030d7e  mov     rax, [rdx+rbx+18h]
0x180030d83  lea     rcx, [rax+rbx]
0x180030d87  neg     rax
0x180030d8a  sbb     rax, rax
0x180030d8d  and     rax, rcx
0x180030d90  mov     [rdx+rbx+18h], rax
0x180030d95  mov     rax, [rdx+rbx+28h]
0x180030d9a  lea     rcx, [rax+rbx]
0x180030d9e  neg     rax
0x180030da1  sbb     rax, rax
0x180030da4  inc     r8d
0x180030da7  and     rax, rcx
0x180030daa  mov     [rdx+rbx+28h], rax
0x180030daf  cmp     r8d, [rbx]
0x180030db2  jb      short loc_180030D77
0x180030db4  jmp     short loc_180030DC0
0x180030db6  xor     esi, esi
0x180030db8  call    cs:__imp_GetLastError
0x180030dbe  mov     edi, eax
0x180030dc0  mov     ecx, edi; dwErrCode
0x180030dc2  call    cs:__imp_SetLastError
0x180030dc8  mov     eax, esi
0x180030dca  add     rsp, 48h
0x180030dce  pop     rdi
0x180030dcf  pop     rsi
0x180030dd0  pop     rbp
0x180030dd1  pop     rbx
0x180030dd2  retn
```
