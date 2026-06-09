# IsThisAVolumeName

- ea: `0x18004a9fc`
- end: `0x18004ac05`
- name: `IsThisAVolumeName`
- size: `521`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180059fb0`

## callees

- `0x18000ccf0`
- `0x18004a9fc`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18004aa3f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004aa3f`
- `ntdll!RtlSetLastWin32Error` at `0x18004aab9`
- `ntdll!RtlSetLastWin32Error` at `0x18004aab9`
- `ntdll!RtlFreeHeap` at `0x18004abd7`
- `ntdll!RtlFreeHeap` at `0x18004abd7`
- `ntdll!RtlAllocateHeap` at `0x18004aaa2`
- `ntdll!RtlAllocateHeap` at `0x18004aaa2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004aa7e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004aa7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004abb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004abb4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ab36`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ab36`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004ab86`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004ab86`

## string_xrefs

- `0x18004ab17`: `\\.\MountPointManager`

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
0x18004a9fc  mov     [rsp-18h+arg_10], rbx
0x18004aa01  push    rbp
0x18004aa02  push    rsi
0x18004aa03  push    rdi
0x18004aa04  mov     rbp, rsp
0x18004aa07  sub     rsp, 80h
0x18004aa0e  mov     rax, cs:__security_cookie
0x18004aa15  xor     rax, rsp
0x18004aa18  mov     [rbp+var_8], rax
0x18004aa1c  xorps   xmm1, xmm1
0x18004aa1f  mov     [rbp+BytesReturned], 0
0x18004aa26  mov     rsi, rdx
0x18004aa29  xorps   xmm0, xmm0
0x18004aa2c  mov     rdx, rcx; SourceString
0x18004aa2f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004aa33  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004aa37  movups  [rbp+OutBuffer], xmm1
0x18004aa3b  movups  [rbp+var_18], xmm1
0x18004aa3f  call    cs:__imp_RtlInitUnicodeStringEx
0x18004aa46  nop     dword ptr [rax+rax+00h]
0x18004aa4b  test    eax, eax
0x18004aa4d  jns     short loc_18004AA5D
0x18004aa4f  mov     ecx, eax
0x18004aa51  call    BaseSetLastNTError
0x18004aa56  xor     eax, eax
0x18004aa58  jmp     loc_18004ABE5
0x18004aa5d  movzx   edx, [rbp+DestinationString.Length]
0x18004aa61  mov     rax, [rbp+DestinationString.Buffer]
0x18004aa65  mov     ecx, edx
0x18004aa67  shr     rcx, 1
0x18004aa6a  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18004aa70  jnz     short loc_18004AA7E
0x18004aa72  mov     eax, 0FFFEh
0x18004aa77  add     dx, ax
0x18004aa7a  mov     [rbp+DestinationString.Length], dx
0x18004aa7e  call    cs:__imp_KernelBaseGetGlobalData
0x18004aa85  nop     dword ptr [rax+rax+00h]
0x18004aa8a  mov     rcx, gs:60h
0x18004aa93  movzx   r8d, [rbp+DestinationString.Length]
0x18004aa98  add     r8, 18h; Size
0x18004aa9c  mov     edx, [rax]; Flags
0x18004aa9e  mov     rcx, [rcx+30h]; HeapHandle
0x18004aaa2  call    cs:__imp_RtlAllocateHeap
0x18004aaa9  nop     dword ptr [rax+rax+00h]
0x18004aaae  mov     rbx, rax
0x18004aab1  test    rax, rax
0x18004aab4  jnz     short loc_18004AAC7
0x18004aab6  lea     ecx, [rax+8]; LastError
0x18004aab9  call    cs:__imp_RtlSetLastWin32Error
0x18004aac0  nop     dword ptr [rax+rax+00h]
0x18004aac5  jmp     short loc_18004AA56
0x18004aac7  xor     eax, eax
0x18004aac9  lea     rcx, [rbx+18h]; void *
0x18004aacd  xorps   xmm0, xmm0
0x18004aad0  movups  xmmword ptr [rbx], xmm0
0x18004aad3  mov     [rbx+10h], rax
0x18004aad7  mov     dword ptr [rbx+10h], 18h
0x18004aade  movzx   eax, [rbp+DestinationString.Length]
0x18004aae2  mov     [rbx+14h], ax
0x18004aae6  mov     r8d, eax; Size
0x18004aae9  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x18004aaed  call    memcpy_0
0x18004aaf2  cmp     [rbp+DestinationString.Length], 4
0x18004aaf7  jb      short loc_18004AB0E
0x18004aaf9  mov     rax, [rbp+DestinationString.Buffer]
0x18004aafd  cmp     word ptr [rax+2], 5Ch ; '\'
0x18004ab02  jnz     short loc_18004AB0E
0x18004ab04  mov     eax, [rbx+10h]
0x18004ab07  mov     word ptr [rax+rbx+2], 3Fh ; '?'
0x18004ab0e  mov     [rsp+80h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x18004ab17  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x18004ab1e  mov     r8d, 3; dwShareMode
0x18004ab24  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004ab2c  xor     r9d, r9d; lpSecurityAttributes
0x18004ab2f  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004ab34  xor     edx, edx; dwDesiredAccess
0x18004ab36  call    cs:__imp_CreateFileW
0x18004ab3d  nop     dword ptr [rax+rax+00h]
0x18004ab42  mov     rdi, rax
0x18004ab45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004ab49  jnz     short loc_18004AB4F
0x18004ab4b  xor     edi, edi
0x18004ab4d  jmp     short loc_18004ABC5
0x18004ab4f  movzx   r9d, [rbp+DestinationString.Length]
0x18004ab54  lea     rax, [rbp+BytesReturned]
0x18004ab58  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18004ab61  add     r9d, 18h; nInBufferSize
0x18004ab65  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18004ab6a  mov     r8, rbx; lpInBuffer
0x18004ab6d  lea     rax, [rbp+OutBuffer]
0x18004ab71  mov     [rsp+80h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x18004ab79  mov     edx, 6D0008h; dwIoControlCode
0x18004ab7e  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; lpOutBuffer
0x18004ab83  mov     rcx, rdi; hDevice
0x18004ab86  call    cs:__imp_DeviceIoControl
0x18004ab8d  nop     dword ptr [rax+rax+00h]
0x18004ab92  test    eax, eax
0x18004ab94  jz      short loc_18004AB9F
0x18004ab96  cmp     dword ptr [rbp+OutBuffer+4], 0
0x18004ab9a  setnz   al
0x18004ab9d  jmp     short loc_18004ABAF
0x18004ab9f  mov     eax, gs:68h
0x18004aba7  cmp     eax, 0EAh
0x18004abac  setz    al
0x18004abaf  mov     rcx, rdi; hObject
0x18004abb2  mov     [rsi], al
0x18004abb4  call    cs:__imp_CloseHandle
0x18004abbb  nop     dword ptr [rax+rax+00h]
0x18004abc0  mov     edi, 1
0x18004abc5  mov     rcx, gs:60h
0x18004abce  mov     r8, rbx; P
0x18004abd1  xor     edx, edx; Flags
0x18004abd3  mov     rcx, [rcx+30h]; HeapHandle
0x18004abd7  call    cs:__imp_RtlFreeHeap
0x18004abde  nop     dword ptr [rax+rax+00h]
0x18004abe3  mov     eax, edi
0x18004abe5  mov     rcx, [rbp+var_8]
0x18004abe9  xor     rcx, rsp; StackCookie
0x18004abec  call    __security_check_cookie
0x18004abf1  mov     rbx, [rsp+80h+arg_10]
0x18004abf9  add     rsp, 80h
0x18004ac00  pop     rdi
0x18004ac01  pop     rsi
0x18004ac02  pop     rbp
0x18004ac03  retn
```
