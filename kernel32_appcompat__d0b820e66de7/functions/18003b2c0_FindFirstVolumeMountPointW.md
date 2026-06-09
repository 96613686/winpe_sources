# FindFirstVolumeMountPointW

- ea: `0x18003b2c0`
- end: `0x18003b53e`
- name: `FindFirstVolumeMountPointW`
- size: `638`
- prototype: `HANDLE __stdcall(LPCWSTR lpszRootPathName, LPWSTR lpszVolumeMountPoint, DWORD cchBufferLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180073d40`

## callees

- `0x18000ccf0`
- `0x18003b2c0`
- `0x18003b544`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18003b2fb`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003b2fb`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003b3d9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003b3d9`
- `ntdll!RtlSetLastWin32Error` at `0x18003b4a1`
- `ntdll!RtlSetLastWin32Error` at `0x18003b520`
- `ntdll!RtlSetLastWin32Error` at `0x18003b4a1`
- `ntdll!RtlSetLastWin32Error` at `0x18003b520`
- `ntdll!RtlCopyUnicodeString` at `0x18003b3c5`
- `ntdll!RtlCopyUnicodeString` at `0x18003b3c5`
- `ntdll!RtlInitUnicodeString` at `0x18003b351`
- `ntdll!RtlInitUnicodeString` at `0x18003b351`
- `ntdll!RtlFreeHeap` at `0x18003b43d`
- `ntdll!RtlFreeHeap` at `0x18003b4fb`
- `ntdll!RtlFreeHeap` at `0x18003b43d`
- `ntdll!RtlFreeHeap` at `0x18003b4fb`
- `ntdll!RtlAllocateHeap` at `0x18003b3a0`
- `ntdll!RtlAllocateHeap` at `0x18003b47b`
- `ntdll!RtlAllocateHeap` at `0x18003b3a0`
- `ntdll!RtlAllocateHeap` at `0x18003b47b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b380`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b45a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b380`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b45a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4dd`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18003b331`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18003b331`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b41b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b41b`

## string_xrefs

- `0x18003b346`: `$Extend\$Reparse:$R:$INDEX_ALLOCATION`

## pseudocode

```c
HANDLE __stdcall FindFirstVolumeMountPointW(
        LPCWSTR lpszRootPathName,
        LPWSTR lpszVolumeMountPoint,
        DWORD cchBufferLength)
{
  NTSTATUS inited; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  ULONG *GlobalData; // rax
  ULONG v12; // ecx
  HANDLE FileW; // rsi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  ULONG *v19; // rax
  HANDLE *Heap; // rax
  HANDLE *v21; // rdi
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-18h] BYREF

  DestinationString = 0;
  Source = 0;
  Destination = 0;
  if ( !lpszRootPathName )
    goto LABEL_18;
  inited = RtlInitUnicodeStringEx(&DestinationString, lpszRootPathName);
  if ( inited >= 0 )
  {
    if ( DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92 )
      goto LABEL_17;
    if ( GetDriveTypeW(lpszRootPathName) != 4 )
    {
      RtlInitUnicodeString(&Source, L"$Extend\\$Reparse:$R:$INDEX_ALLOCATION");
      v10 = Source.Length + (unsigned int)DestinationString.Length + 2;
      if ( (unsigned int)v10 <= 0xFFFF )
      {
        Destination.MaximumLength = Source.Length + DestinationString.Length + 2;
        Destination.Length = 0;
        GlobalData = (ULONG *)KernelBaseGetGlobalData(Source.Length, v10, v8, v9);
        Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, Destination.MaximumLength);
        if ( Destination.Buffer )
        {
          RtlCopyUnicodeString(&Destination, &DestinationString);
          RtlAppendUnicodeStringToString(&Destination, &Source);
          Destination.Buffer[(unsigned __int64)Destination.Length >> 1] = 0;
          FileW = CreateFileW(Destination.Buffer, 0x80000000, 1u, 0, 3u, 0x2020000u, 0);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
          if ( FileW != (HANDLE)-1LL )
          {
            v19 = (ULONG *)KernelBaseGetGlobalData(v15, v14, v16, v17);
            Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v19, 0x18u);
            v21 = Heap;
            if ( Heap )
            {
              Heap[1] = 0;
              Heap[2] = 0;
              *Heap = FileW;
              if ( (unsigned int)FindNextVolumeMountPointHelper((__int64)Heap, lpszVolumeMountPoint, cchBufferLength, 1) )
                return v21;
              CloseHandle(*v21);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
            }
            else
            {
              CloseHandle(FileW);
              RtlSetLastWin32Error(8u);
            }
          }
          return (HANDLE)-1LL;
        }
        v12 = 8;
        goto LABEL_19;
      }
LABEL_17:
      v7 = 3221225523LL;
      goto LABEL_4;
    }
LABEL_18:
    v12 = 87;
LABEL_19:
    RtlSetLastWin32Error(v12);
    return (HANDLE)-1LL;
  }
  v7 = (unsigned int)inited;
LABEL_4:
  BaseSetLastNTError(v7);
  return (HANDLE)-1LL;
}

```

## disassembly

```asm
0x18003b2c0  push    rbp
0x18003b2c2  push    rbx
0x18003b2c3  push    rsi
0x18003b2c4  push    rdi
0x18003b2c5  push    r14
0x18003b2c7  push    r15
0x18003b2c9  mov     rbp, rsp
0x18003b2cc  sub     rsp, 78h
0x18003b2d0  xorps   xmm0, xmm0
0x18003b2d3  xorps   xmm1, xmm1
0x18003b2d6  mov     r14d, r8d
0x18003b2d9  mov     r15, rdx
0x18003b2dc  mov     rbx, rcx
0x18003b2df  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003b2e3  movups  xmmword ptr [rbp+Source.Length], xmm1
0x18003b2e7  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18003b2eb  test    rcx, rcx
0x18003b2ee  jz      loc_18003B51B
0x18003b2f4  mov     rdx, rcx; SourceString
0x18003b2f7  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003b2fb  call    cs:__imp_RtlInitUnicodeStringEx
0x18003b302  nop     dword ptr [rax+rax+00h]
0x18003b307  test    eax, eax
0x18003b309  jns     short loc_18003B317
0x18003b30b  mov     ecx, eax
0x18003b30d  call    BaseSetLastNTError
0x18003b312  jmp     loc_18003B52C
0x18003b317  movzx   ecx, [rbp+DestinationString.Length]
0x18003b31b  mov     rax, [rbp+DestinationString.Buffer]
0x18003b31f  shr     rcx, 1
0x18003b322  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18003b328  jnz     loc_18003B511
0x18003b32e  mov     rcx, rbx; lpRootPathName
0x18003b331  call    cs:__imp_GetDriveTypeW
0x18003b338  nop     dword ptr [rax+rax+00h]
0x18003b33d  cmp     eax, 4
0x18003b340  jz      loc_18003B51B
0x18003b346  lea     rdx, aExtendReparseR; "$Extend\\$Reparse:$R:$INDEX_ALLOCATION"
0x18003b34d  lea     rcx, [rbp+Source]; DestinationString
0x18003b351  call    cs:__imp_RtlInitUnicodeString
0x18003b358  nop     dword ptr [rax+rax+00h]
0x18003b35d  movzx   edx, [rbp+DestinationString.Length]
0x18003b361  movzx   ecx, [rbp+Source.Length]
0x18003b365  add     edx, 2
0x18003b368  add     edx, ecx
0x18003b36a  cmp     edx, 0FFFFh
0x18003b370  ja      loc_18003B511
0x18003b376  xor     eax, eax
0x18003b378  mov     [rbp+Destination.MaximumLength], dx
0x18003b37c  mov     [rbp+Destination.Length], ax
0x18003b380  call    cs:__imp_KernelBaseGetGlobalData
0x18003b387  nop     dword ptr [rax+rax+00h]
0x18003b38c  mov     rcx, gs:60h
0x18003b395  movzx   r8d, [rbp+Destination.MaximumLength]; Size
0x18003b39a  mov     edx, [rax]; Flags
0x18003b39c  mov     rcx, [rcx+30h]; HeapHandle
0x18003b3a0  call    cs:__imp_RtlAllocateHeap
0x18003b3a7  nop     dword ptr [rax+rax+00h]
0x18003b3ac  mov     [rbp+Destination.Buffer], rax
0x18003b3b0  test    rax, rax
0x18003b3b3  jnz     short loc_18003B3BD
0x18003b3b5  lea     ecx, [rax+8]
0x18003b3b8  jmp     loc_18003B520
0x18003b3bd  lea     rdx, [rbp+DestinationString]; SourceString
0x18003b3c1  lea     rcx, [rbp+Destination]; DestinationString
0x18003b3c5  call    cs:__imp_RtlCopyUnicodeString
0x18003b3cc  nop     dword ptr [rax+rax+00h]
0x18003b3d1  lea     rdx, [rbp+Source]; Source
0x18003b3d5  lea     rcx, [rbp+Destination]; Destination
0x18003b3d9  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003b3e0  nop     dword ptr [rax+rax+00h]
0x18003b3e5  movzx   edx, [rbp+Destination.Length]
0x18003b3e9  xor     ecx, ecx
0x18003b3eb  mov     rax, [rbp+Destination.Buffer]
0x18003b3ef  xor     r9d, r9d; lpSecurityAttributes
0x18003b3f2  mov     [rsp+78h+hTemplateFile], rcx; hTemplateFile
0x18003b3f7  shr     rdx, 1
0x18003b3fa  lea     r8d, [rcx+1]; dwShareMode
0x18003b3fe  mov     [rsp+78h+dwFlagsAndAttributes], 2020000h; dwFlagsAndAttributes
0x18003b406  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18003b40e  mov     [rax+rdx*2], cx
0x18003b412  mov     edx, 80000000h; dwDesiredAccess
0x18003b417  mov     rcx, [rbp+Destination.Buffer]; lpFileName
0x18003b41b  call    cs:__imp_CreateFileW
0x18003b422  nop     dword ptr [rax+rax+00h]
0x18003b427  mov     rcx, gs:60h
0x18003b430  xor     edx, edx; Flags
0x18003b432  mov     r8, [rbp+Destination.Buffer]; P
0x18003b436  mov     rsi, rax
0x18003b439  mov     rcx, [rcx+30h]; HeapHandle
0x18003b43d  call    cs:__imp_RtlFreeHeap
0x18003b444  nop     dword ptr [rax+rax+00h]
0x18003b449  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003b44d  cmp     rsi, rbx
0x18003b450  jnz     short loc_18003B45A
0x18003b452  mov     rax, rbx
0x18003b455  jmp     loc_18003B530
0x18003b45a  call    cs:__imp_KernelBaseGetGlobalData
0x18003b461  nop     dword ptr [rax+rax+00h]
0x18003b466  mov     rcx, gs:60h
0x18003b46f  mov     r8d, 18h; Size
0x18003b475  mov     edx, [rax]; Flags
0x18003b477  mov     rcx, [rcx+30h]; HeapHandle
0x18003b47b  call    cs:__imp_RtlAllocateHeap
0x18003b482  nop     dword ptr [rax+rax+00h]
0x18003b487  mov     rdi, rax
0x18003b48a  test    rax, rax
0x18003b48d  jnz     short loc_18003B4AF
0x18003b48f  mov     rcx, rsi; hObject
0x18003b492  call    cs:__imp_CloseHandle
0x18003b499  nop     dword ptr [rax+rax+00h]
0x18003b49e  lea     ecx, [rdi+8]; LastError
0x18003b4a1  call    cs:__imp_RtlSetLastWin32Error
0x18003b4a8  nop     dword ptr [rax+rax+00h]
0x18003b4ad  jmp     short loc_18003B452
0x18003b4af  mov     qword ptr [rax+8], 0
0x18003b4b7  mov     r9d, 1
0x18003b4bd  mov     qword ptr [rax+10h], 0
0x18003b4c5  mov     r8d, r14d
0x18003b4c8  mov     rdx, r15
0x18003b4cb  mov     [rax], rsi
0x18003b4ce  mov     rcx, rdi
0x18003b4d1  call    FindNextVolumeMountPointHelper
0x18003b4d6  test    eax, eax
0x18003b4d8  jnz     short loc_18003B50C
0x18003b4da  mov     rcx, [rdi]; hObject
0x18003b4dd  call    cs:__imp_CloseHandle
0x18003b4e4  nop     dword ptr [rax+rax+00h]
0x18003b4e9  mov     rcx, gs:60h
0x18003b4f2  mov     r8, rdi; P
0x18003b4f5  xor     edx, edx; Flags
0x18003b4f7  mov     rcx, [rcx+30h]; HeapHandle
0x18003b4fb  call    cs:__imp_RtlFreeHeap
0x18003b502  nop     dword ptr [rax+rax+00h]
0x18003b507  jmp     loc_18003B452
0x18003b50c  mov     rax, rdi
0x18003b50f  jmp     short loc_18003B530
0x18003b511  mov     ecx, 0C0000033h
0x18003b516  jmp     loc_18003B30D
0x18003b51b  mov     ecx, 57h ; 'W'; LastError
0x18003b520  call    cs:__imp_RtlSetLastWin32Error
0x18003b527  nop     dword ptr [rax+rax+00h]
0x18003b52c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b530  add     rsp, 78h
0x18003b534  pop     r15
0x18003b536  pop     r14
0x18003b538  pop     rdi
0x18003b539  pop     rsi
0x18003b53a  pop     rbx
0x18003b53b  pop     rbp
0x18003b53c  retn
```
