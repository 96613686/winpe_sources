# PuDownloadFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort const *,uchar)

- ea: `0x18019aa94`
- end: `0x18019aca3`
- name: `?PuDownloadFirmware@@YAHPEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEBGE@Z`
- size: `527`
- prototype: `__int64 __fastcall(HANDLE hDevice, struct _STORAGE_HW_FIRMWARE_INFO *, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003845c`

## callees

- `0x180006cf4`
- `0x18019aa94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ac69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ac87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ac69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ac87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019ac5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019ac5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ab50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ac49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ab50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ac49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019ab6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019ab6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ac7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ac7a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019ac2e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019ac2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019aaff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019aaff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18019abf7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18019abf7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18019ab1a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18019ab1a`

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
          if ( v18 )
            HeapFree(v18, 0, v15);
          goto LABEL_23;
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
LABEL_23:
  if ( v9 )
    CloseHandle(v9);
  return v10;
}

```

## disassembly

```asm
0x18019aa94  mov     r11, rsp
0x18019aa97  push    rbx
0x18019aa98  push    rbp
0x18019aa99  push    rsi
0x18019aa9a  push    rdi
0x18019aa9b  push    r12
0x18019aa9d  push    r13
0x18019aa9f  push    r14
0x18019aaa1  push    r15
0x18019aaa3  sub     rsp, 58h
0x18019aaa7  xor     r13d, r13d
0x18019aaaa  mov     r15b, r9b
0x18019aaad  test    byte ptr [rdx+8], 1
0x18019aab1  mov     rax, r8
0x18019aab4  mov     rsi, rdx
0x18019aab7  mov     [r11+10h], r13d
0x18019aabb  mov     r12, rcx
0x18019aabe  mov     [r11-58h], r13
0x18019aac2  jz      loc_18019AC82
0x18019aac8  cmp     [rdx+10h], r13d
0x18019aacc  jz      loc_18019AC82
0x18019aad2  cmp     [rdx+14h], r13d
0x18019aad6  jz      loc_18019AC82
0x18019aadc  mov     [r11-68h], r13
0x18019aae0  lea     r8d, [r13+1]; dwShareMode
0x18019aae4  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18019aaec  xor     r9d, r9d; lpSecurityAttributes
0x18019aaef  mov     edx, 80000000h; dwDesiredAccess
0x18019aaf4  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18019aafc  mov     rcx, rax; lpFileName
0x18019aaff  call    cs:__imp_CreateFileW
0x18019ab05  mov     r14, rax
0x18019ab08  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019ab0c  jz      loc_18019AC8D
0x18019ab12  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x18019ab17  mov     rcx, rax; hFile
0x18019ab1a  call    cs:__imp_GetFileSizeEx
0x18019ab20  mov     ebx, eax
0x18019ab22  test    eax, eax
0x18019ab24  jz      loc_18019AC72
0x18019ab2a  cmp     qword ptr [rsp+98h+FileSize], r13
0x18019ab2f  jnz     short loc_18019AB3A
0x18019ab31  lea     ecx, [r13+32h]
0x18019ab35  jmp     loc_18019AC69
0x18019ab3a  mov     ebp, [rsi+14h]
0x18019ab3d  xor     edx, edx
0x18019ab3f  mov     eax, ebp
0x18019ab41  div     dword ptr [rsi+10h]
0x18019ab44  sub     ebp, edx
0x18019ab46  lea     edi, [rbp+20h]
0x18019ab49  mov     [rsp+98h+NumberOfBytesRead], edi
0x18019ab50  call    cs:__imp_GetProcessHeap
0x18019ab56  test    rax, rax
0x18019ab59  jz      loc_18019AC64
0x18019ab5f  mov     r8d, edi; dwBytes
0x18019ab62  mov     edx, 8; dwFlags
0x18019ab67  mov     rcx, rax; hHeap
0x18019ab6a  call    cs:__imp_HeapAlloc
0x18019ab70  mov     rdi, rax
0x18019ab73  test    rax, rax
0x18019ab76  jz      loc_18019AC64
0x18019ab7c  mov     dword ptr [rax], 28h ; '('
0x18019ab82  mov     eax, [rsp+98h+NumberOfBytesRead]
0x18019ab89  mov     [rdi+4], eax
0x18019ab8c  mov     [rdi+10h], r13
0x18019ab90  mov     [rdi+0Ch], r15b
0x18019ab94  cmp     [rsi+0Ch], r13b
0x18019ab98  jz      short loc_18019AB9E
0x18019ab9a  or      dword ptr [rdi+8], 1
0x18019ab9e  mov     rcx, r13
0x18019aba1  mov     rax, qword ptr [rsp+98h+FileSize]
0x18019aba6  cmp     rcx, rax
0x18019aba9  jnb     loc_18019AC49
0x18019abaf  sub     rax, rcx
0x18019abb2  mov     ecx, ebp
0x18019abb4  cmp     rcx, rax
0x18019abb7  mov     ecx, [rsi+10h]
0x18019abba  cmovnb  ebp, eax
0x18019abbd  xor     edx, edx
0x18019abbf  lea     eax, [rcx-1]
0x18019abc2  add     eax, ebp
0x18019abc4  div     ecx
0x18019abc6  dec     ecx
0x18019abc8  mov     eax, ebp
0x18019abca  sub     eax, edx
0x18019abcc  xor     edx, edx; Val
0x18019abce  add     ecx, eax
0x18019abd0  mov     [rdi+18h], rcx
0x18019abd4  mov     r8d, ecx; Size
0x18019abd7  lea     rcx, [rdi+20h]; void *
0x18019abdb  call    memset_0
0x18019abe0  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18019abe8  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; lpOverlapped
0x18019abed  mov     r8d, ebp; nNumberOfBytesToRead
0x18019abf0  lea     rdx, [rdi+20h]; lpBuffer
0x18019abf4  mov     rcx, r14; hFile
0x18019abf7  call    cs:__imp_ReadFile
0x18019abfd  mov     ebx, eax
0x18019abff  test    eax, eax
0x18019ac01  jz      short loc_18019AC49
0x18019ac03  mov     r9d, [rdi+4]; nInBufferSize
0x18019ac07  lea     rax, [rsp+98h+NumberOfBytesRead]
0x18019ac0f  mov     [rsp+98h+lpOverlapped], r13; lpOverlapped
0x18019ac14  mov     r8, rdi; lpInBuffer
0x18019ac17  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x18019ac1c  mov     edx, 2DDC04h; dwIoControlCode
0x18019ac21  mov     [rsp+98h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x18019ac26  mov     rcx, r12; hDevice
0x18019ac29  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; lpOutBuffer
0x18019ac2e  call    cs:__imp_DeviceIoControl
0x18019ac34  mov     ebx, eax
0x18019ac36  test    eax, eax
0x18019ac38  jz      short loc_18019AC49
0x18019ac3a  mov     eax, ebp
0x18019ac3c  add     [rdi+10h], rax
0x18019ac40  mov     rcx, [rdi+10h]
0x18019ac44  jmp     loc_18019ABA1
0x18019ac49  call    cs:__imp_GetProcessHeap
0x18019ac4f  test    rax, rax
0x18019ac52  jz      short loc_18019AC72
0x18019ac54  mov     r8, rdi; lpMem
0x18019ac57  xor     edx, edx; dwFlags
0x18019ac59  mov     rcx, rax; hHeap
0x18019ac5c  call    cs:__imp_HeapFree
0x18019ac62  jmp     short loc_18019AC72
0x18019ac64  mov     ecx, 8; dwErrCode
0x18019ac69  call    cs:__imp_SetLastError
0x18019ac6f  mov     ebx, r13d
0x18019ac72  test    r14, r14
0x18019ac75  jz      short loc_18019AC90
0x18019ac77  mov     rcx, r14; hObject
0x18019ac7a  call    cs:__imp_CloseHandle
0x18019ac80  jmp     short loc_18019AC90
0x18019ac82  mov     ecx, 32h ; '2'; dwErrCode
0x18019ac87  call    cs:__imp_SetLastError
0x18019ac8d  mov     ebx, r13d
0x18019ac90  mov     eax, ebx
0x18019ac92  add     rsp, 58h
0x18019ac96  pop     r15
0x18019ac98  pop     r14
0x18019ac9a  pop     r13
0x18019ac9c  pop     r12
0x18019ac9e  pop     rdi
0x18019ac9f  pop     rsi
0x18019aca0  pop     rbp
0x18019aca1  pop     rbx
0x18019aca2  retn
```
