# SetVolumeNameForRoot

- ea: `0x18005d758`
- end: `0x18005d997`
- name: `SetVolumeNameForRoot`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180059fb0`

## callees

- `0x18005d758`
- `0x180082751`

## import_xrefs

- `ntdll!toupper` at `0x18005d7de`
- `ntdll!toupper` at `0x18005d7de`
- `ntdll!RtlSetLastWin32Error` at `0x18005d7b1`
- `ntdll!RtlSetLastWin32Error` at `0x18005d7b1`
- `ntdll!RtlInitUnicodeString` at `0x18005d7fd`
- `ntdll!RtlInitUnicodeString` at `0x18005d7fd`
- `ntdll!RtlFreeHeap` at `0x18005d865`
- `ntdll!RtlFreeHeap` at `0x18005d8cb`
- `ntdll!RtlFreeHeap` at `0x18005d97f`
- `ntdll!RtlFreeHeap` at `0x18005d865`
- `ntdll!RtlFreeHeap` at `0x18005d8cb`
- `ntdll!RtlFreeHeap` at `0x18005d97f`
- `ntdll!RtlAllocateHeap` at `0x18005d798`
- `ntdll!RtlAllocateHeap` at `0x18005d83f`
- `ntdll!RtlAllocateHeap` at `0x18005d798`
- `ntdll!RtlAllocateHeap` at `0x18005d83f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005d777`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005d821`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005d777`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005d821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d961`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d961`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d902`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d902`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005d950`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005d950`

## string_xrefs

- `0x18005d8ee`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall SetVolumeNameForRoot(unsigned __int16 *a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  ULONG *GlobalData; // rax
  _OWORD *Heap; // rax
  _OWORD *v8; // rbx
  DWORD v10; // ebp
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  ULONG *v14; // rax
  char *v15; // rax
  unsigned __int16 *v16; // rdi
  size_t Length; // r8
  HANDLE FileW; // rsi
  unsigned int v19; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF

  BytesReturned = 0;
  DestinationString = 0;
  GlobalData = (ULONG *)KernelBaseGetGlobalData(a1, a2, a3, a4);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 0x1Eu);
  v8 = Heap;
  if ( !Heap )
    goto LABEL_2;
  *Heap = *(_OWORD *)L"\\DosDevices\\";
  *((_QWORD *)Heap + 2) = *(_QWORD *)L"ces\\";
  *((_WORD *)Heap + 12) = toupper(*a1);
  *(_DWORD *)((char *)v8 + 26) = 58;
  RtlInitUnicodeString(&DestinationString, a2);
  v10 = (unsigned __int16)(DestinationString.Length - 2) + 36;
  DestinationString.Length -= 2;
  v14 = (ULONG *)KernelBaseGetGlobalData(65534, v11, v12, v13);
  v15 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v14, v10);
  v16 = (unsigned __int16 *)v15;
  if ( !v15 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
LABEL_2:
    RtlSetLastWin32Error(8u);
    return 0;
  }
  *(_DWORD *)v15 = 1835016;
  *((_WORD *)v15 + 2) = 36;
  *((_WORD *)v15 + 3) = DestinationString.Length;
  Length = DestinationString.Length;
  *(_OWORD *)(v15 + 8) = *v8;
  *(_OWORD *)(v15 + 20) = *(_OWORD *)((char *)v8 + 12);
  memcpy_0(v15 + 36, DestinationString.Buffer, Length);
  *(unsigned __int16 *)((char *)v16 + v16[2] + 2) = 63;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( FileW == (HANDLE)-1LL )
  {
    v19 = 0;
  }
  else
  {
    v19 = DeviceIoControl(FileW, 0x6DC000u, v16, v10, 0, 0, &BytesReturned, 0);
    CloseHandle(FileW);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
  return v19;
}

```

## disassembly

```asm
0x18005d758  mov     rax, rsp
0x18005d75b  push    rbx
0x18005d75c  push    rbp
0x18005d75d  push    rsi
0x18005d75e  push    rdi
0x18005d75f  sub     rsp, 58h
0x18005d763  xorps   xmm0, xmm0
0x18005d766  mov     dword ptr [rax+18h], 0
0x18005d76d  movups  xmmword ptr [rax-38h], xmm0
0x18005d771  mov     rdi, rdx
0x18005d774  mov     rsi, rcx
0x18005d777  call    cs:__imp_KernelBaseGetGlobalData
0x18005d77e  nop     dword ptr [rax+rax+00h]
0x18005d783  mov     rcx, gs:60h
0x18005d78c  mov     r8d, 1Eh; Size
0x18005d792  mov     edx, [rax]; Flags
0x18005d794  mov     rcx, [rcx+30h]; HeapHandle
0x18005d798  call    cs:__imp_RtlAllocateHeap
0x18005d79f  nop     dword ptr [rax+rax+00h]
0x18005d7a4  mov     rbx, rax
0x18005d7a7  test    rax, rax
0x18005d7aa  jnz     short loc_18005D7C4
0x18005d7ac  mov     ecx, 8; LastError
0x18005d7b1  call    cs:__imp_RtlSetLastWin32Error
0x18005d7b8  nop     dword ptr [rax+rax+00h]
0x18005d7bd  xor     eax, eax
0x18005d7bf  jmp     loc_18005D98D
0x18005d7c4  movups  xmm0, xmmword ptr cs:aDosdevices; "\\DosDevices\\"
0x18005d7cb  movups  xmmword ptr [rax], xmm0
0x18005d7ce  movsd   xmm1, qword ptr cs:aDosdevices+10h; "ces\\"
0x18005d7d6  movsd   qword ptr [rax+10h], xmm1
0x18005d7db  movzx   ecx, word ptr [rsi]; C
0x18005d7de  call    cs:__imp_toupper
0x18005d7e5  nop     dword ptr [rax+rax+00h]
0x18005d7ea  mov     [rbx+18h], ax
0x18005d7ee  mov     rdx, rdi; SourceString
0x18005d7f1  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18005d7f6  mov     dword ptr [rbx+1Ah], 3Ah ; ':'
0x18005d7fd  call    cs:__imp_RtlInitUnicodeString
0x18005d804  nop     dword ptr [rax+rax+00h]
0x18005d809  movzx   eax, [rsp+78h+DestinationString.Length]
0x18005d80e  mov     ecx, 0FFFEh
0x18005d813  add     ax, cx
0x18005d816  movzx   ebp, ax
0x18005d819  add     ebp, 24h ; '$'
0x18005d81c  mov     [rsp+78h+DestinationString.Length], ax
0x18005d821  call    cs:__imp_KernelBaseGetGlobalData
0x18005d828  nop     dword ptr [rax+rax+00h]
0x18005d82d  mov     rcx, gs:60h
0x18005d836  mov     r8d, ebp; Size
0x18005d839  mov     edx, [rax]; Flags
0x18005d83b  mov     rcx, [rcx+30h]; HeapHandle
0x18005d83f  call    cs:__imp_RtlAllocateHeap
0x18005d846  nop     dword ptr [rax+rax+00h]
0x18005d84b  mov     rdi, rax
0x18005d84e  test    rax, rax
0x18005d851  jnz     short loc_18005D876
0x18005d853  mov     rcx, gs:60h
0x18005d85c  mov     r8, rbx; P
0x18005d85f  xor     edx, edx; Flags
0x18005d861  mov     rcx, [rcx+30h]; HeapHandle
0x18005d865  call    cs:__imp_RtlFreeHeap
0x18005d86c  nop     dword ptr [rax+rax+00h]
0x18005d871  jmp     loc_18005D7AC
0x18005d876  mov     dword ptr [rax], 1C0008h
0x18005d87c  lea     rcx, [rdi+24h]; void *
0x18005d880  mov     word ptr [rax+4], 24h ; '$'
0x18005d886  movzx   eax, [rsp+78h+DestinationString.Length]
0x18005d88b  mov     [rdi+6], ax
0x18005d88f  movups  xmm0, xmmword ptr [rbx]
0x18005d892  movzx   r8d, [rsp+78h+DestinationString.Length]; Size
0x18005d898  movups  xmmword ptr [rdi+8], xmm0
0x18005d89c  movups  xmm1, xmmword ptr [rbx+0Ch]
0x18005d8a0  movups  xmmword ptr [rdi+14h], xmm1
0x18005d8a4  mov     rdx, [rsp+78h+DestinationString.Buffer]; Src
0x18005d8a9  call    memcpy_0
0x18005d8ae  movzx   eax, word ptr [rdi+4]
0x18005d8b2  mov     r8, rbx; P
0x18005d8b5  xor     edx, edx; Flags
0x18005d8b7  mov     word ptr [rax+rdi+2], 3Fh ; '?'
0x18005d8be  mov     rcx, gs:60h
0x18005d8c7  mov     rcx, [rcx+30h]; HeapHandle
0x18005d8cb  call    cs:__imp_RtlFreeHeap
0x18005d8d2  nop     dword ptr [rax+rax+00h]
0x18005d8d7  mov     r8d, 3; dwShareMode
0x18005d8dd  mov     [rsp+78h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x18005d8e6  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005d8ee  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x18005d8f5  xor     r9d, r9d; lpSecurityAttributes
0x18005d8f8  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005d8fd  mov     edx, 0C0000000h; dwDesiredAccess
0x18005d902  call    cs:__imp_CreateFileW
0x18005d909  nop     dword ptr [rax+rax+00h]
0x18005d90e  mov     rsi, rax
0x18005d911  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d915  jnz     short loc_18005D91B
0x18005d917  xor     ebx, ebx
0x18005d919  jmp     short loc_18005D96D
0x18005d91b  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18005d924  lea     rax, [rsp+78h+BytesReturned]
0x18005d92c  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18005d931  mov     r9d, ebp; nInBufferSize
0x18005d934  mov     [rsp+78h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18005d93c  mov     r8, rdi; lpInBuffer
0x18005d93f  mov     edx, 6DC000h; dwIoControlCode
0x18005d944  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOutBuffer
0x18005d94d  mov     rcx, rsi; hDevice
0x18005d950  call    cs:__imp_DeviceIoControl
0x18005d957  nop     dword ptr [rax+rax+00h]
0x18005d95c  mov     rcx, rsi; hObject
0x18005d95f  mov     ebx, eax
0x18005d961  call    cs:__imp_CloseHandle
0x18005d968  nop     dword ptr [rax+rax+00h]
0x18005d96d  mov     rcx, gs:60h
0x18005d976  mov     r8, rdi; P
0x18005d979  xor     edx, edx; Flags
0x18005d97b  mov     rcx, [rcx+30h]; HeapHandle
0x18005d97f  call    cs:__imp_RtlFreeHeap
0x18005d986  nop     dword ptr [rax+rax+00h]
0x18005d98b  mov     eax, ebx
0x18005d98d  add     rsp, 58h
0x18005d991  pop     rdi
0x18005d992  pop     rsi
0x18005d993  pop     rbp
0x18005d994  pop     rbx
0x18005d995  retn
```
