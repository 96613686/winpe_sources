# IsThisAVolumeName

- ea: `0x180046ac0`
- end: `0x180046c98`
- name: `IsThisAVolumeName`
- size: `472`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180054f30`

## callees

- `0x18000f920`
- `0x180046ac0`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180046b03`
- `ntdll!RtlInitUnicodeStringEx` at `0x180046b03`
- `ntdll!RtlSetLastWin32Error` at `0x180046b6b`
- `ntdll!RtlSetLastWin32Error` at `0x180046b6b`
- `ntdll!RtlFreeHeap` at `0x180046c71`
- `ntdll!RtlFreeHeap` at `0x180046c71`
- `ntdll!RtlAllocateHeap` at `0x180046b5a`
- `ntdll!RtlAllocateHeap` at `0x180046b5a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180046b3c`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180046b3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046c54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046c54`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046be2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046be2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180046c2c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180046c2c`

## string_xrefs

- `0x180046bc3`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall IsThisAVolumeName(PCWSTR SourceString, bool *a2)
{
  NTSTATUS inited; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 Length; // rdx
  unsigned __int64 v8; // rcx
  ULONG *GlobalData; // rax
  _QWORD *Heap; // rax
  _WORD *v11; // rbx
  void *v12; // rcx
  unsigned int v13; // eax
  HANDLE FileW; // rdi
  unsigned int v15; // edi
  bool v16; // al
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-30h] BYREF
  _OWORD OutBuffer[2]; // [rsp+58h] [rbp-28h] BYREF

  BytesReturned = 0;
  DestinationString = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
  {
    BaseSetLastNTError((unsigned int)inited);
    return 0;
  }
  Length = DestinationString.Length;
  v8 = (unsigned __int64)DestinationString.Length >> 1;
  if ( DestinationString.Buffer[v8 - 1] == 92 )
  {
    LOWORD(Length) = DestinationString.Length - 2;
    DestinationString.Length -= 2;
  }
  GlobalData = (ULONG *)KernelBaseGetGlobalData(v8, Length, v4, v5);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, DestinationString.Length + 24LL);
  v11 = Heap;
  if ( !Heap )
  {
    RtlSetLastWin32Error(8u);
    return 0;
  }
  v12 = Heap + 3;
  *(_OWORD *)Heap = 0;
  Heap[2] = 0;
  *((_DWORD *)Heap + 4) = 24;
  v13 = DestinationString.Length;
  v11[10] = DestinationString.Length;
  memcpy_0(v12, DestinationString.Buffer, v13);
  if ( DestinationString.Length >= 4u && DestinationString.Buffer[1] == 92 )
    *(_WORD *)((char *)v11 + *((unsigned int *)v11 + 4) + 2) = 63;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( FileW == (HANDLE)-1LL )
  {
    v15 = 0;
  }
  else
  {
    if ( DeviceIoControl(FileW, 0x6D0008u, v11, DestinationString.Length + 24, OutBuffer, 0x20u, &BytesReturned, 0) )
      v16 = DWORD1(OutBuffer[0]) != 0;
    else
      v16 = NtCurrentTeb()->LastErrorValue == 234;
    *a2 = v16;
    CloseHandle(FileW);
    v15 = 1;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return v15;
}

```

## disassembly

```asm
0x180046ac0  mov     [rsp-18h+arg_10], rbx
0x180046ac5  push    rbp
0x180046ac6  push    rsi
0x180046ac7  push    rdi
0x180046ac8  mov     rbp, rsp
0x180046acb  sub     rsp, 80h
0x180046ad2  mov     rax, cs:__security_cookie
0x180046ad9  xor     rax, rsp
0x180046adc  mov     [rbp+var_8], rax
0x180046ae0  xorps   xmm1, xmm1
0x180046ae3  mov     [rbp+BytesReturned], 0
0x180046aea  mov     rsi, rdx
0x180046aed  xorps   xmm0, xmm0
0x180046af0  mov     rdx, rcx; SourceString
0x180046af3  lea     rcx, [rbp+DestinationString]; DestinationString
0x180046af7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180046afb  movups  [rbp+OutBuffer], xmm1
0x180046aff  movups  [rbp+var_18], xmm1
0x180046b03  call    cs:__imp_RtlInitUnicodeStringEx
0x180046b09  test    eax, eax
0x180046b0b  jns     short loc_180046B1B
0x180046b0d  mov     ecx, eax
0x180046b0f  call    BaseSetLastNTError
0x180046b14  xor     eax, eax
0x180046b16  jmp     loc_180046C79
0x180046b1b  movzx   edx, [rbp+DestinationString.Length]
0x180046b1f  mov     rax, [rbp+DestinationString.Buffer]
0x180046b23  mov     ecx, edx
0x180046b25  shr     rcx, 1
0x180046b28  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180046b2e  jnz     short loc_180046B3C
0x180046b30  mov     eax, 0FFFEh
0x180046b35  add     dx, ax
0x180046b38  mov     [rbp+DestinationString.Length], dx
0x180046b3c  call    cs:__imp_KernelBaseGetGlobalData
0x180046b42  mov     rcx, gs:60h
0x180046b4b  movzx   r8d, [rbp+DestinationString.Length]
0x180046b50  add     r8, 18h; Size
0x180046b54  mov     edx, [rax]; Flags
0x180046b56  mov     rcx, [rcx+30h]; HeapHandle
0x180046b5a  call    cs:__imp_RtlAllocateHeap
0x180046b60  mov     rbx, rax
0x180046b63  test    rax, rax
0x180046b66  jnz     short loc_180046B73
0x180046b68  lea     ecx, [rax+8]; LastError
0x180046b6b  call    cs:__imp_RtlSetLastWin32Error
0x180046b71  jmp     short loc_180046B14
0x180046b73  xor     eax, eax
0x180046b75  lea     rcx, [rbx+18h]; void *
0x180046b79  xorps   xmm0, xmm0
0x180046b7c  movups  xmmword ptr [rbx], xmm0
0x180046b7f  mov     [rbx+10h], rax
0x180046b83  mov     dword ptr [rbx+10h], 18h
0x180046b8a  movzx   eax, [rbp+DestinationString.Length]
0x180046b8e  mov     [rbx+14h], ax
0x180046b92  mov     r8d, eax; Size
0x180046b95  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x180046b99  call    memcpy_0
0x180046b9e  cmp     [rbp+DestinationString.Length], 4
0x180046ba3  jb      short loc_180046BBA
0x180046ba5  mov     rax, [rbp+DestinationString.Buffer]
0x180046ba9  cmp     word ptr [rax+2], 5Ch ; '\'
0x180046bae  jnz     short loc_180046BBA
0x180046bb0  mov     eax, [rbx+10h]
0x180046bb3  mov     word ptr [rax+rbx+2], 3Fh ; '?'
0x180046bba  mov     [rsp+80h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180046bc3  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180046bca  mov     r8d, 3; dwShareMode
0x180046bd0  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180046bd8  xor     r9d, r9d; lpSecurityAttributes
0x180046bdb  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x180046be0  xor     edx, edx; dwDesiredAccess
0x180046be2  call    cs:__imp_CreateFileW
0x180046be8  mov     rdi, rax
0x180046beb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046bef  jnz     short loc_180046BF5
0x180046bf1  xor     edi, edi
0x180046bf3  jmp     short loc_180046C5F
0x180046bf5  movzx   r9d, [rbp+DestinationString.Length]
0x180046bfa  lea     rax, [rbp+BytesReturned]
0x180046bfe  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x180046c07  add     r9d, 18h; nInBufferSize
0x180046c0b  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x180046c10  mov     r8, rbx; lpInBuffer
0x180046c13  lea     rax, [rbp+OutBuffer]
0x180046c17  mov     [rsp+80h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180046c1f  mov     edx, 6D0008h; dwIoControlCode
0x180046c24  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; lpOutBuffer
0x180046c29  mov     rcx, rdi; hDevice
0x180046c2c  call    cs:__imp_DeviceIoControl
0x180046c32  test    eax, eax
0x180046c34  jz      short loc_180046C3F
0x180046c36  cmp     dword ptr [rbp+OutBuffer+4], 0
0x180046c3a  setnz   al
0x180046c3d  jmp     short loc_180046C4F
0x180046c3f  mov     eax, gs:68h
0x180046c47  cmp     eax, 0EAh
0x180046c4c  setz    al
0x180046c4f  mov     rcx, rdi; hObject
0x180046c52  mov     [rsi], al
0x180046c54  call    cs:__imp_CloseHandle
0x180046c5a  mov     edi, 1
0x180046c5f  mov     rcx, gs:60h
0x180046c68  mov     r8, rbx; P
0x180046c6b  xor     edx, edx; Flags
0x180046c6d  mov     rcx, [rcx+30h]; HeapHandle
0x180046c71  call    cs:__imp_RtlFreeHeap
0x180046c77  mov     eax, edi
0x180046c79  mov     rcx, [rbp+var_8]
0x180046c7d  xor     rcx, rsp; StackCookie
0x180046c80  call    __security_check_cookie
0x180046c85  mov     rbx, [rsp+80h+arg_10]
0x180046c8d  add     rsp, 80h
0x180046c94  pop     rdi
0x180046c95  pop     rsi
0x180046c96  pop     rbp
0x180046c97  retn
```
