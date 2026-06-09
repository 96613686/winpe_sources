# EfspOverwriteEfsAttr(void *,_EFS_DATA_STREAM_HEADER *)

- ea: `0x180008bd0`
- end: `0x180008d32`
- name: `?EfspOverwriteEfsAttr@@YAKPEAXPEAU_EFS_DATA_STREAM_HEADER@@@Z`
- size: `354`
- prototype: `unsigned int __fastcall(HANDLE FileHandle, struct _EFS_DATA_STREAM_HEADER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009b2c`

## callees

- `0x1800064f4`
- `0x180008bd0`
- `0x18000a688`
- `0x18000a72c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d1e`
- `ntdll!NtFsControlFile` at `0x180008cdd`
- `ntdll!NtFsControlFile` at `0x180008cdd`
- `ntdll!RtlNtStatusToDosError` at `0x180008d08`
- `ntdll!RtlNtStatusToDosError` at `0x180008d08`

## pseudocode

```c
__int64 __fastcall EfspOverwriteEfsAttr(HANDLE FileHandle, struct _EFS_DATA_STREAM_HEADER *a2)
{
  unsigned int BufferSize; // eax
  __int64 v4; // rcx
  ULONG v5; // edi
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v8; // rcx
  void *InputBuffer; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  NTSTATUS v12; // esi
  HANDLE v13; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  _QWORD v16[8]; // [rsp+60h] [rbp+17h] BYREF
  SIZE_T dwBytes; // [rsp+B8h] [rbp+6Fh] BYREF

  v16[1] = a2;
  v16[0] = 3;
  v16[2] = 0;
  LODWORD(dwBytes) = 0;
  IoStatusBlock = 0;
  BufferSize = EfsFsctlGetBufferSize(v16, &dwBytes);
  v5 = BufferSize;
  if ( BufferSize )
  {
    fnEfsLogTrace1(v4, (__int64)EFS_API_ERROR, BufferSize, 11, 91);
  }
  else
  {
    v6 = dwBytes;
    ProcessHeap = GetProcessHeap();
    InputBuffer = HeapAlloc(ProcessHeap, 8u, v6);
    if ( InputBuffer )
    {
      EfsFsctlPrepareData(4, 3, 1, (unsigned int)v16, (__int64)InputBuffer, (__int64)&dwBytes);
      v10 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900D7u, InputBuffer, dwBytes, 0, 0);
      v12 = v10;
      if ( v10 < 0 )
      {
        fnEfsLogTrace1(v11, (__int64)EFS_API_ERROR, v10, 11, 123);
        v5 = RtlNtStatusToDosError(v12);
      }
      v13 = GetProcessHeap();
      HeapFree(v13, 0, InputBuffer);
    }
    else
    {
      fnEfsLogTrace1(v8, (__int64)EFS_ERROR_MEMORY, dwBytes, 11, 96);
      return 8;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180008bd0  push    rbp
0x180008bd2  push    rbx
0x180008bd3  push    rsi
0x180008bd4  push    rdi
0x180008bd5  lea     rbp, [rsp-3Fh]
0x180008bda  sub     rsp, 88h
0x180008be1  mov     rsi, rcx
0x180008be4  mov     [rbp+57h+var_38], rdx
0x180008be8  xorps   xmm0, xmm0
0x180008beb  mov     [rbp+57h+var_40], 3
0x180008bf3  lea     rdx, [rbp+57h+dwBytes]
0x180008bf7  mov     [rbp+57h+var_30], 0
0x180008bff  lea     rcx, [rbp+57h+var_40]
0x180008c03  mov     dword ptr [rbp+57h+dwBytes], 0
0x180008c0a  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180008c0e  call    EfsFsctlGetBufferSize
0x180008c13  mov     edi, eax
0x180008c15  test    eax, eax
0x180008c17  jz      short loc_180008C3B
0x180008c19  mov     r9d, 0Bh
0x180008c1f  mov     dword ptr [rsp+0A0h+IoStatusBlock], 0C5Bh
0x180008c27  mov     r8d, eax
0x180008c2a  lea     rdx, EFS_API_ERROR
0x180008c31  call    fnEfsLogTrace1
0x180008c36  jmp     loc_180008D24
0x180008c3b  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x180008c3e  call    cs:__imp_GetProcessHeap
0x180008c44  mov     r8d, ebx; dwBytes
0x180008c47  mov     edx, 8; dwFlags
0x180008c4c  mov     rcx, rax; hHeap
0x180008c4f  call    cs:__imp_HeapAlloc
0x180008c55  mov     rbx, rax
0x180008c58  test    rax, rax
0x180008c5b  jnz     short loc_180008C81
0x180008c5d  mov     r8d, dword ptr [rbp+57h+dwBytes]
0x180008c61  lea     r9d, [rax+0Bh]
0x180008c65  lea     rdx, EFS_ERROR_MEMORY
0x180008c6c  mov     dword ptr [rsp+0A0h+IoStatusBlock], 0C60h
0x180008c74  call    fnEfsLogTrace1
0x180008c79  lea     edi, [rbx+8]
0x180008c7c  jmp     loc_180008D24
0x180008c81  mov     edx, 3
0x180008c86  lea     rax, [rbp+57h+dwBytes]
0x180008c8a  mov     qword ptr [rsp+0A0h+FsControlCode], rax
0x180008c8f  lea     r9, [rbp+57h+var_40]
0x180008c93  mov     [rsp+0A0h+IoStatusBlock], rbx
0x180008c98  lea     ecx, [rdx+1]
0x180008c9b  lea     r8d, [rdx-2]
0x180008c9f  call    EfsFsctlPrepareData
0x180008ca4  mov     eax, dword ptr [rbp+57h+dwBytes]
0x180008ca7  xor     r9d, r9d; ApcContext
0x180008caa  mov     [rsp+0A0h+OutputBufferLength], 0; OutputBufferLength
0x180008cb2  xor     r8d, r8d; ApcRoutine
0x180008cb5  mov     [rsp+0A0h+OutputBuffer], 0; OutputBuffer
0x180008cbe  xor     edx, edx; Event
0x180008cc0  mov     [rsp+0A0h+InputBufferLength], eax; InputBufferLength
0x180008cc4  mov     rcx, rsi; FileHandle
0x180008cc7  mov     [rsp+0A0h+InputBuffer], rbx; InputBuffer
0x180008ccc  lea     rax, [rbp+57h+var_50]
0x180008cd0  mov     [rsp+0A0h+FsControlCode], 900D7h; FsControlCode
0x180008cd8  mov     [rsp+0A0h+IoStatusBlock], rax; IoStatusBlock
0x180008cdd  call    cs:__imp_NtFsControlFile
0x180008ce3  mov     esi, eax
0x180008ce5  test    eax, eax
0x180008ce7  jns     short loc_180008D10
0x180008ce9  mov     r9d, 0Bh
0x180008cef  mov     dword ptr [rsp+0A0h+IoStatusBlock], 0C7Bh
0x180008cf7  mov     r8d, eax
0x180008cfa  lea     rdx, EFS_API_ERROR
0x180008d01  call    fnEfsLogTrace1
0x180008d06  mov     ecx, esi; Status
0x180008d08  call    cs:__imp_RtlNtStatusToDosError
0x180008d0e  mov     edi, eax
0x180008d10  call    cs:__imp_GetProcessHeap
0x180008d16  mov     r8, rbx; lpMem
0x180008d19  xor     edx, edx; dwFlags
0x180008d1b  mov     rcx, rax; hHeap
0x180008d1e  call    cs:__imp_HeapFree
0x180008d24  mov     eax, edi
0x180008d26  add     rsp, 88h
0x180008d2d  pop     rdi
0x180008d2e  pop     rsi
0x180008d2f  pop     rbx
0x180008d30  pop     rbp
0x180008d31  retn
```
