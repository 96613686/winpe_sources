# PuDownloadFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort const *,uchar)

- ea: `0x18019f7e0`
- end: `0x18019fa24`
- name: `?PuDownloadFirmware@@YAHPEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEBGE@Z`
- size: `580`
- prototype: `__int64 __fastcall(HANDLE hDevice, struct _STORAGE_HW_FIRMWARE_INFO *, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800395dc`

## callees

- `0x180006dd4`
- `0x1800298d0`
- `0x18019f7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fa01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fa01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f8a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f9b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f8a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f9b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019f8c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019f8c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019f9ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019f9ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019f998`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019f998`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019f84b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019f84b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18019f95b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18019f95b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18019f86c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18019f86c`

## pseudocode

```c
__int64 __fastcall PuDownloadFirmware(
        HANDLE hDevice,
        struct _STORAGE_HW_FIRMWARE_INFO *a2,
        const unsigned __int16 *a3,
        char a4)
{
  bool v5; // zf
  HANDLE FileW; // rax
  void *v9; // r14
  unsigned int v10; // ebx
  DWORD v11; // ecx
  DWORD v12; // ebp
  HANDLE ProcessHeap; // rax
  union _LARGE_INTEGER *v14; // rax
  union _LARGE_INTEGER *v15; // rdi
  union _LARGE_INTEGER v16; // rcx
  union _LARGE_INTEGER v17; // rcx
  HANDLE v18; // rax
  unsigned int v19; // edx
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-58h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+10h] BYREF

  v5 = (*((_BYTE *)a2 + 8) & 1) == 0;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  if ( v5 || !a2->ImagePayloadAlignment || !a2->ImagePayloadMaxSize )
  {
    SetLastError(0x32u);
    return 0;
  }
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  v10 = GetFileSizeEx(FileW, &FileSize);
  if ( v10 )
  {
    if ( FileSize.QuadPart )
    {
      v12 = a2->ImagePayloadMaxSize - a2->ImagePayloadMaxSize % a2->ImagePayloadAlignment;
      NumberOfBytesRead = v12 + 32;
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
      {
        v14 = (union _LARGE_INTEGER *)HeapAlloc(ProcessHeap, 8u, v12 + 32);
        v15 = v14;
        if ( v14 )
        {
          v14->LowPart = 40;
          v14->HighPart = NumberOfBytesRead;
          v14[2].QuadPart = 0;
          BYTE4(v14[1].QuadPart) = a4;
          if ( a2->FirmwareShared )
            v14[1].LowPart |= 1u;
          v16.QuadPart = 0;
          while ( v16.QuadPart < (unsigned __int64)FileSize.QuadPart )
          {
            if ( (unsigned __int64)v12 >= FileSize.QuadPart - v16.QuadPart )
              v12 = FileSize.LowPart - v16.LowPart;
            v17.QuadPart = v12
                         - (v12 + a2->ImagePayloadAlignment - 1) % a2->ImagePayloadAlignment
                         + a2->ImagePayloadAlignment
                         - 1;
            v15[3] = v17;
            memset_0(&v15[4], 0, v17.LowPart);
            v10 = ReadFile(v9, &v15[4], v12, &NumberOfBytesRead, 0);
            if ( !v10 )
              break;
            v10 = DeviceIoControl(hDevice, 0x2DDC04u, v15, v15->HighPart, 0, 0, &NumberOfBytesRead, 0);
            if ( !v10 )
              break;
            v15[2].QuadPart += v12;
            v16 = v15[2];
          }
          v18 = GetProcessHeap();
          PmHeapFree(v18, v19, v15);
          goto LABEL_22;
        }
      }
      v11 = 8;
    }
    else
    {
      v11 = 50;
    }
    SetLastError(v11);
    v10 = 0;
  }
LABEL_22:
  if ( v9 )
    CloseHandle(v9);
  return v10;
}

```

## disassembly

```asm
0x18019f7e0  mov     r11, rsp
0x18019f7e3  push    rbx
0x18019f7e4  push    rbp
0x18019f7e5  push    rsi
0x18019f7e6  push    rdi
0x18019f7e7  push    r12
0x18019f7e9  push    r13
0x18019f7eb  push    r14
0x18019f7ed  push    r15
0x18019f7ef  sub     rsp, 58h
0x18019f7f3  xor     r13d, r13d
0x18019f7f6  mov     r15b, r9b
0x18019f7f9  test    byte ptr [rdx+8], 1
0x18019f7fd  mov     rax, r8
0x18019f800  mov     rsi, rdx
0x18019f803  mov     [r11+10h], r13d
0x18019f807  mov     r12, rcx
0x18019f80a  mov     [r11-58h], r13
0x18019f80e  jz      loc_18019F9FC
0x18019f814  cmp     [rdx+10h], r13d
0x18019f818  jz      loc_18019F9FC
0x18019f81e  cmp     [rdx+14h], r13d
0x18019f822  jz      loc_18019F9FC
0x18019f828  mov     [r11-68h], r13
0x18019f82c  lea     r8d, [r13+1]; dwShareMode
0x18019f830  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18019f838  xor     r9d, r9d; lpSecurityAttributes
0x18019f83b  mov     edx, 80000000h; dwDesiredAccess
0x18019f840  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18019f848  mov     rcx, rax; lpFileName
0x18019f84b  call    cs:__imp_CreateFileW
0x18019f852  nop     dword ptr [rax+rax+00h]
0x18019f857  mov     r14, rax
0x18019f85a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019f85e  jz      loc_18019FA0D
0x18019f864  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x18019f869  mov     rcx, rax; hFile
0x18019f86c  call    cs:__imp_GetFileSizeEx
0x18019f873  nop     dword ptr [rax+rax+00h]
0x18019f878  mov     ebx, eax
0x18019f87a  test    eax, eax
0x18019f87c  jz      loc_18019F9E6
0x18019f882  cmp     qword ptr [rsp+98h+FileSize], r13
0x18019f887  jnz     short loc_18019F892
0x18019f889  lea     ecx, [r13+32h]
0x18019f88d  jmp     loc_18019F9D7
0x18019f892  mov     ebp, [rsi+14h]
0x18019f895  xor     edx, edx
0x18019f897  mov     eax, ebp
0x18019f899  div     dword ptr [rsi+10h]
0x18019f89c  sub     ebp, edx
0x18019f89e  lea     edi, [rbp+20h]
0x18019f8a1  mov     [rsp+98h+NumberOfBytesRead], edi
0x18019f8a8  call    cs:__imp_GetProcessHeap
0x18019f8af  nop     dword ptr [rax+rax+00h]
0x18019f8b4  test    rax, rax
0x18019f8b7  jz      loc_18019F9D2
0x18019f8bd  mov     r8d, edi; dwBytes
0x18019f8c0  mov     edx, 8; dwFlags
0x18019f8c5  mov     rcx, rax; hHeap
0x18019f8c8  call    cs:__imp_HeapAlloc
0x18019f8cf  nop     dword ptr [rax+rax+00h]
0x18019f8d4  mov     rdi, rax
0x18019f8d7  test    rax, rax
0x18019f8da  jz      loc_18019F9D2
0x18019f8e0  mov     dword ptr [rax], 28h ; '('
0x18019f8e6  mov     eax, [rsp+98h+NumberOfBytesRead]
0x18019f8ed  mov     [rdi+4], eax
0x18019f8f0  mov     [rdi+10h], r13
0x18019f8f4  mov     [rdi+0Ch], r15b
0x18019f8f8  cmp     [rsi+0Ch], r13b
0x18019f8fc  jz      short loc_18019F902
0x18019f8fe  or      dword ptr [rdi+8], 1
0x18019f902  mov     rcx, r13
0x18019f905  mov     rax, qword ptr [rsp+98h+FileSize]
0x18019f90a  cmp     rcx, rax
0x18019f90d  jnb     loc_18019F9B9
0x18019f913  sub     rax, rcx
0x18019f916  mov     ecx, ebp
0x18019f918  cmp     rcx, rax
0x18019f91b  mov     ecx, [rsi+10h]
0x18019f91e  cmovnb  ebp, eax
0x18019f921  xor     edx, edx
0x18019f923  lea     eax, [rcx-1]
0x18019f926  add     eax, ebp
0x18019f928  div     ecx
0x18019f92a  dec     ecx
0x18019f92c  mov     eax, ebp
0x18019f92e  sub     eax, edx
0x18019f930  xor     edx, edx; Val
0x18019f932  add     ecx, eax
0x18019f934  mov     [rdi+18h], rcx
0x18019f938  mov     r8d, ecx; Size
0x18019f93b  lea     rcx, [rdi+20h]; void *
0x18019f93f  call    memset_0
0x18019f944  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18019f94c  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; lpOverlapped
0x18019f951  mov     r8d, ebp; nNumberOfBytesToRead
0x18019f954  lea     rdx, [rdi+20h]; lpBuffer
0x18019f958  mov     rcx, r14; hFile
0x18019f95b  call    cs:__imp_ReadFile
0x18019f962  nop     dword ptr [rax+rax+00h]
0x18019f967  mov     ebx, eax
0x18019f969  test    eax, eax
0x18019f96b  jz      short loc_18019F9B9
0x18019f96d  mov     r9d, [rdi+4]; nInBufferSize
0x18019f971  lea     rax, [rsp+98h+NumberOfBytesRead]
0x18019f979  mov     [rsp+98h+lpOverlapped], r13; lpOverlapped
0x18019f97e  mov     r8, rdi; lpInBuffer
0x18019f981  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x18019f986  mov     edx, 2DDC04h; dwIoControlCode
0x18019f98b  mov     [rsp+98h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x18019f990  mov     rcx, r12; hDevice
0x18019f993  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; lpOutBuffer
0x18019f998  call    cs:__imp_DeviceIoControl
0x18019f99f  nop     dword ptr [rax+rax+00h]
0x18019f9a4  mov     ebx, eax
0x18019f9a6  test    eax, eax
0x18019f9a8  jz      short loc_18019F9B9
0x18019f9aa  mov     eax, ebp
0x18019f9ac  add     [rdi+10h], rax
0x18019f9b0  mov     rcx, [rdi+10h]
0x18019f9b4  jmp     loc_18019F905
0x18019f9b9  call    cs:__imp_GetProcessHeap
0x18019f9c0  nop     dword ptr [rax+rax+00h]
0x18019f9c5  mov     rcx, rax; void *
0x18019f9c8  mov     r8, rdi; void *
0x18019f9cb  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x18019f9d0  jmp     short loc_18019F9E6
0x18019f9d2  mov     ecx, 8; dwErrCode
0x18019f9d7  call    cs:__imp_SetLastError
0x18019f9de  nop     dword ptr [rax+rax+00h]
0x18019f9e3  mov     ebx, r13d
0x18019f9e6  test    r14, r14
0x18019f9e9  jz      short loc_18019FA10
0x18019f9eb  mov     rcx, r14; hObject
0x18019f9ee  call    cs:__imp_CloseHandle
0x18019f9f5  nop     dword ptr [rax+rax+00h]
0x18019f9fa  jmp     short loc_18019FA10
0x18019f9fc  mov     ecx, 32h ; '2'; dwErrCode
0x18019fa01  call    cs:__imp_SetLastError
0x18019fa08  nop     dword ptr [rax+rax+00h]
0x18019fa0d  mov     ebx, r13d
0x18019fa10  mov     eax, ebx
0x18019fa12  add     rsp, 58h
0x18019fa16  pop     r15
0x18019fa18  pop     r14
0x18019fa1a  pop     r13
0x18019fa1c  pop     r12
0x18019fa1e  pop     rdi
0x18019fa1f  pop     rsi
0x18019fa20  pop     rbp
0x18019fa21  pop     rbx
0x18019fa22  retn
```
