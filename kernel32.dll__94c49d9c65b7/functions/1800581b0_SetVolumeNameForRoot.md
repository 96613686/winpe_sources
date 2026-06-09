# SetVolumeNameForRoot

- ea: `0x1800581b0`
- end: `0x1800583a0`
- name: `SetVolumeNameForRoot`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180054f30`

## callees

- `0x1800581b0`
- `0x18007a7d1`

## import_xrefs

- `ntdll!toupper` at `0x180058224`
- `ntdll!toupper` at `0x180058224`
- `ntdll!RtlSetLastWin32Error` at `0x1800581fd`
- `ntdll!RtlSetLastWin32Error` at `0x1800581fd`
- `ntdll!RtlInitUnicodeString` at `0x18005823d`
- `ntdll!RtlInitUnicodeString` at `0x18005823d`
- `ntdll!RtlFreeHeap` at `0x180058293`
- `ntdll!RtlFreeHeap` at `0x1800582f3`
- `ntdll!RtlFreeHeap` at `0x18005838f`
- `ntdll!RtlFreeHeap` at `0x180058293`
- `ntdll!RtlFreeHeap` at `0x1800582f3`
- `ntdll!RtlFreeHeap` at `0x18005838f`
- `ntdll!RtlAllocateHeap` at `0x1800581ea`
- `ntdll!RtlAllocateHeap` at `0x180058273`
- `ntdll!RtlAllocateHeap` at `0x1800581ea`
- `ntdll!RtlAllocateHeap` at `0x180058273`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800581cf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005825b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800581cf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005825b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058377`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180058324`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180058324`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005836c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005836c`

## string_xrefs

- `0x180058310`: `\\.\MountPointManager`

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
0x1800581b0  mov     rax, rsp
0x1800581b3  push    rbx
0x1800581b4  push    rbp
0x1800581b5  push    rsi
0x1800581b6  push    rdi
0x1800581b7  sub     rsp, 58h
0x1800581bb  xorps   xmm0, xmm0
0x1800581be  mov     dword ptr [rax+18h], 0
0x1800581c5  movups  xmmword ptr [rax-38h], xmm0
0x1800581c9  mov     rdi, rdx
0x1800581cc  mov     rsi, rcx
0x1800581cf  call    cs:__imp_KernelBaseGetGlobalData
0x1800581d5  mov     rcx, gs:60h
0x1800581de  mov     r8d, 1Eh; Size
0x1800581e4  mov     edx, [rax]; Flags
0x1800581e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800581ea  call    cs:__imp_RtlAllocateHeap
0x1800581f0  mov     rbx, rax
0x1800581f3  test    rax, rax
0x1800581f6  jnz     short loc_18005820A
0x1800581f8  mov     ecx, 8; LastError
0x1800581fd  call    cs:__imp_RtlSetLastWin32Error
0x180058203  xor     eax, eax
0x180058205  jmp     loc_180058397
0x18005820a  movups  xmm0, xmmword ptr cs:aDosdevices; "\\DosDevices\\"
0x180058211  movups  xmmword ptr [rax], xmm0
0x180058214  movsd   xmm1, qword ptr cs:aDosdevices+10h; "ces\\"
0x18005821c  movsd   qword ptr [rax+10h], xmm1
0x180058221  movzx   ecx, word ptr [rsi]; C
0x180058224  call    cs:__imp_toupper
0x18005822a  mov     [rbx+18h], ax
0x18005822e  mov     rdx, rdi; SourceString
0x180058231  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180058236  mov     dword ptr [rbx+1Ah], 3Ah ; ':'
0x18005823d  call    cs:__imp_RtlInitUnicodeString
0x180058243  movzx   eax, [rsp+78h+DestinationString.Length]
0x180058248  mov     ecx, 0FFFEh
0x18005824d  add     ax, cx
0x180058250  movzx   ebp, ax
0x180058253  add     ebp, 24h ; '$'
0x180058256  mov     [rsp+78h+DestinationString.Length], ax
0x18005825b  call    cs:__imp_KernelBaseGetGlobalData
0x180058261  mov     rcx, gs:60h
0x18005826a  mov     r8d, ebp; Size
0x18005826d  mov     edx, [rax]; Flags
0x18005826f  mov     rcx, [rcx+30h]; HeapHandle
0x180058273  call    cs:__imp_RtlAllocateHeap
0x180058279  mov     rdi, rax
0x18005827c  test    rax, rax
0x18005827f  jnz     short loc_18005829E
0x180058281  mov     rcx, gs:60h
0x18005828a  mov     r8, rbx; P
0x18005828d  xor     edx, edx; Flags
0x18005828f  mov     rcx, [rcx+30h]; HeapHandle
0x180058293  call    cs:__imp_RtlFreeHeap
0x180058299  jmp     loc_1800581F8
0x18005829e  mov     dword ptr [rax], 1C0008h
0x1800582a4  lea     rcx, [rdi+24h]; void *
0x1800582a8  mov     word ptr [rax+4], 24h ; '$'
0x1800582ae  movzx   eax, [rsp+78h+DestinationString.Length]
0x1800582b3  mov     [rdi+6], ax
0x1800582b7  movups  xmm0, xmmword ptr [rbx]
0x1800582ba  movzx   r8d, [rsp+78h+DestinationString.Length]; Size
0x1800582c0  movups  xmmword ptr [rdi+8], xmm0
0x1800582c4  movups  xmm1, xmmword ptr [rbx+0Ch]
0x1800582c8  movups  xmmword ptr [rdi+14h], xmm1
0x1800582cc  mov     rdx, [rsp+78h+DestinationString.Buffer]; Src
0x1800582d1  call    memcpy_0
0x1800582d6  movzx   eax, word ptr [rdi+4]
0x1800582da  mov     r8, rbx; P
0x1800582dd  xor     edx, edx; Flags
0x1800582df  mov     word ptr [rax+rdi+2], 3Fh ; '?'
0x1800582e6  mov     rcx, gs:60h
0x1800582ef  mov     rcx, [rcx+30h]; HeapHandle
0x1800582f3  call    cs:__imp_RtlFreeHeap
0x1800582f9  mov     r8d, 3; dwShareMode
0x1800582ff  mov     [rsp+78h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180058308  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180058310  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180058317  xor     r9d, r9d; lpSecurityAttributes
0x18005831a  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005831f  mov     edx, 0C0000000h; dwDesiredAccess
0x180058324  call    cs:__imp_CreateFileW
0x18005832a  mov     rsi, rax
0x18005832d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180058331  jnz     short loc_180058337
0x180058333  xor     ebx, ebx
0x180058335  jmp     short loc_18005837D
0x180058337  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180058340  lea     rax, [rsp+78h+BytesReturned]
0x180058348  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18005834d  mov     r9d, ebp; nInBufferSize
0x180058350  mov     [rsp+78h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180058358  mov     r8, rdi; lpInBuffer
0x18005835b  mov     edx, 6DC000h; dwIoControlCode
0x180058360  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOutBuffer
0x180058369  mov     rcx, rsi; hDevice
0x18005836c  call    cs:__imp_DeviceIoControl
0x180058372  mov     rcx, rsi; hObject
0x180058375  mov     ebx, eax
0x180058377  call    cs:__imp_CloseHandle
0x18005837d  mov     rcx, gs:60h
0x180058386  mov     r8, rdi; P
0x180058389  xor     edx, edx; Flags
0x18005838b  mov     rcx, [rcx+30h]; HeapHandle
0x18005838f  call    cs:__imp_RtlFreeHeap
0x180058395  mov     eax, ebx
0x180058397  add     rsp, 58h
0x18005839b  pop     rdi
0x18005839c  pop     rsi
0x18005839d  pop     rbp
0x18005839e  pop     rbx
0x18005839f  retn
```
