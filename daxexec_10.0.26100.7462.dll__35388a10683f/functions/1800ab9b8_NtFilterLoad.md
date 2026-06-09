# NtFilterLoad

- ea: `0x1800ab9b8`
- end: `0x1800abbf9`
- name: `NtFilterLoad`
- size: `577`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800ac2fc`

## callees

- `0x18000b3c9`
- `0x1800ab9b8`
- `0x1800acd04`
- `0x1800acdc0`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ab9ed`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ab9ed`
- `ntdll!RtlAllocateHeap` at `0x1800abb0f`
- `ntdll!RtlAllocateHeap` at `0x1800abb0f`
- `ntdll!NtClose` at `0x1800abb8e`
- `ntdll!NtClose` at `0x1800c6d26`
- `ntdll!NtClose` at `0x1800abb8e`
- `ntdll!NtClose` at `0x1800c6d26`
- `ntdll!RtlFreeHeap` at `0x1800abbb3`
- `ntdll!RtlFreeHeap` at `0x1800abbda`
- `ntdll!RtlFreeHeap` at `0x1800c6d4d`
- `ntdll!RtlFreeHeap` at `0x1800c6d74`
- `ntdll!RtlFreeHeap` at `0x1800abbb3`
- `ntdll!RtlFreeHeap` at `0x1800abbda`
- `ntdll!RtlFreeHeap` at `0x1800c6d4d`
- `ntdll!RtlFreeHeap` at `0x1800c6d74`
- `ntdll!NtCreateFile` at `0x1800abab5`
- `ntdll!NtCreateFile` at `0x1800abab5`

## pseudocode

```c
__int64 __fastcall NtFilterLoad(_WORD *Src)
{
  _WORD *Heap; // rbx
  unsigned int v3; // eax
  int v4; // eax
  __int64 v5; // rax
  unsigned int v6; // eax
  int AllocationSize; // [rsp+20h] [rbp-B8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-B0h]
  PVOID P; // [rsp+60h] [rbp-78h]
  struct _UNICODE_STRING v11; // [rsp+68h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-50h] BYREF
  __int64 v14; // [rsp+E8h] [rbp+10h] BYREF
  unsigned int v15; // [rsp+F0h] [rbp+18h]
  void *FileHandle; // [rsp+F8h] [rbp+20h] BYREF

  FileHandle = (void *)-1LL;
  Heap = 0;
  P = 0;
  v11 = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v11, 0, 0) )
  {
    LODWORD(v14) = -2147024893;
    goto LABEL_11;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v11;
  IoStatusBlock = 0;
  v3 = NtCreateFile(&FileHandle, 0x120116u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v4 = FilterHResultFromNtStatus(v3);
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( Src[v5] );
    LOWORD(v14) = 2 * v5;
    v15 = (unsigned __int16)(2 * v5) + 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    P = Heap;
    if ( !Heap )
    {
      LODWORD(v14) = -2147024882;
      goto LABEL_11;
    }
    v6 = (unsigned __int16)v14;
    *Heap = v14;
    memcpy_0(Heap + 1, Src, v6);
    v4 = NtFilterpDeviceIoControl(FileHandle, 0x88004u, AllocationSize, FileAttributes, (__int64)&v14);
  }
  LODWORD(v14) = v4;
LABEL_11:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v11.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11.Buffer);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800ab9b8  mov     rax, rsp
0x1800ab9bb  push    rbx
0x1800ab9bc  push    rsi
0x1800ab9bd  push    rdi
0x1800ab9be  sub     rsp, 0C0h
0x1800ab9c5  mov     rdi, rcx
0x1800ab9c8  or      qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x1800ab9cd  xor     esi, esi
0x1800ab9cf  mov     ebx, esi
0x1800ab9d1  mov     [rax-78h], rbx
0x1800ab9d5  xorps   xmm0, xmm0
0x1800ab9d8  movups  xmmword ptr [rax-70h], xmm0
0x1800ab9dc  xor     r9d, r9d; DirectoryInfo
0x1800ab9df  xor     r8d, r8d; NtFileNamePart
0x1800ab9e2  lea     rdx, [rax-70h]; NtPathName
0x1800ab9e6  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1800ab9ed  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ab9f4  nop     dword ptr [rax+rax+00h]
0x1800ab9f9  test    al, al
0x1800ab9fb  jnz     short loc_1800ABA0D
0x1800ab9fd  mov     dword ptr [rsp+0D8h+arg_8], 80070003h
0x1800aba08  jmp     loc_1800ABB80
0x1800aba0d  xor     eax, eax
0x1800aba0f  mov     dword ptr [rsp+0D8h+ObjectAttributes+4], eax
0x1800aba16  xorps   xmm0, xmm0
0x1800aba19  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x1800aba21  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x1800aba29  mov     [rsp+0D8h+ObjectAttributes.SecurityDescriptor], rax
0x1800aba31  mov     dword ptr [rsp+0D8h+ObjectAttributes.SecurityQualityOfService], eax
0x1800aba38  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x1800aba43  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], rsi
0x1800aba4b  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800aba56  lea     rax, [rsp+0D8h+var_70]
0x1800aba5b  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x1800aba63  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aba6c  movups  xmmword ptr [rsp+0D8h+IoStatusBlock], xmm0
0x1800aba71  mov     [rsp+0D8h+EaLength], esi; EaLength
0x1800aba75  mov     [rsp+0D8h+EaBuffer], rsi; EaBuffer
0x1800aba7a  mov     [rsp+0D8h+CreateOptions], esi; CreateOptions
0x1800aba7e  mov     [rsp+0D8h+CreateDisposition], 1; CreateDisposition
0x1800aba86  mov     [rsp+0D8h+ShareAccess], 2; ShareAccess
0x1800aba8e  mov     [rsp+0D8h+FileAttributes], 80h; int
0x1800aba96  mov     [rsp+0D8h+AllocationSize], rsi; int
0x1800aba9b  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x1800abaa0  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x1800abaa8  mov     edx, 120116h; DesiredAccess
0x1800abaad  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x1800abab5  call    cs:__imp_NtCreateFile
0x1800ababc  nop     dword ptr [rax+rax+00h]
0x1800abac1  cmp     [rsp+0D8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800abaca  jnz     short loc_1800ABAD8
0x1800abacc  mov     ecx, eax
0x1800abace  call    FilterHResultFromNtStatus
0x1800abad3  jmp     loc_1800ABB79
0x1800abad8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800abadc  inc     rax
0x1800abadf  cmp     [rdi+rax*2], si
0x1800abae3  jnz     short loc_1800ABADC
0x1800abae5  add     ax, ax
0x1800abae8  mov     word ptr [rsp+0D8h+arg_8], ax
0x1800abaf0  movzx   eax, ax
0x1800abaf3  add     eax, 2
0x1800abaf6  mov     [rsp+0D8h+arg_10], eax
0x1800abafd  mov     r8d, eax; Size
0x1800abb00  mov     rcx, gs:60h
0x1800abb09  xor     edx, edx; Flags
0x1800abb0b  mov     rcx, [rcx+30h]; HeapHandle
0x1800abb0f  call    cs:__imp_RtlAllocateHeap
0x1800abb16  nop     dword ptr [rax+rax+00h]
0x1800abb1b  mov     rbx, rax
0x1800abb1e  mov     [rsp+0D8h+P], rax
0x1800abb23  test    rax, rax
0x1800abb26  jnz     short loc_1800ABB35
0x1800abb28  mov     dword ptr [rsp+0D8h+arg_8], 8007000Eh
0x1800abb33  jmp     short loc_1800ABB80
0x1800abb35  movzx   eax, word ptr [rsp+0D8h+arg_8]
0x1800abb3d  mov     [rbx], ax
0x1800abb40  mov     r8d, eax; Size
0x1800abb43  lea     rcx, [rbx+2]; void *
0x1800abb47  mov     rdx, rdi; Src
0x1800abb4a  call    memcpy_0
0x1800abb4f  lea     rax, [rsp+0D8h+arg_8]
0x1800abb57  mov     qword ptr [rsp+0D8h+ShareAccess], rax; __int64
0x1800abb5c  mov     r9d, [rsp+0D8h+arg_10]
0x1800abb64  mov     r8, rbx
0x1800abb67  mov     edx, 88004h; FsControlCode
0x1800abb6c  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1800abb74  call    NtFilterpDeviceIoControl
0x1800abb79  mov     dword ptr [rsp+0D8h+arg_8], eax
0x1800abb80  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1800abb88  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800abb8c  jz      short loc_1800ABB9A
0x1800abb8e  call    cs:__imp_NtClose
0x1800abb95  nop     dword ptr [rax+rax+00h]
0x1800abb9a  test    rbx, rbx
0x1800abb9d  jz      short loc_1800ABBBF
0x1800abb9f  mov     rcx, gs:60h
0x1800abba8  mov     r8, [rsp+0D8h+P]; P
0x1800abbad  xor     edx, edx; Flags
0x1800abbaf  mov     rcx, [rcx+30h]; HeapHandle
0x1800abbb3  call    cs:__imp_RtlFreeHeap
0x1800abbba  nop     dword ptr [rax+rax+00h]
0x1800abbbf  cmp     [rsp+0D8h+var_68], rsi
0x1800abbc4  jz      short loc_1800ABBE6
0x1800abbc6  mov     rcx, gs:60h
0x1800abbcf  mov     r8, [rsp+0D8h+var_68]; P
0x1800abbd4  xor     edx, edx; Flags
0x1800abbd6  mov     rcx, [rcx+30h]; HeapHandle
0x1800abbda  call    cs:__imp_RtlFreeHeap
0x1800abbe1  nop     dword ptr [rax+rax+00h]
0x1800abbe6  mov     eax, dword ptr [rsp+0D8h+arg_8]
0x1800abbed  add     rsp, 0C0h
0x1800abbf4  pop     rdi
0x1800abbf5  pop     rsi
0x1800abbf6  pop     rbx
0x1800abbf7  retn
0x1800c6d10  push    rbp
0x1800c6d12  sub     rsp, 60h
0x1800c6d16  mov     rbp, rdx
0x1800c6d19  mov     rcx, [rbp+0F8h]; Handle
0x1800c6d20  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c6d24  jz      short loc_1800C6D33
0x1800c6d26  call    cs:__imp_NtClose
0x1800c6d2d  nop     dword ptr [rax+rax+00h]
0x1800c6d32  nop
0x1800c6d33  cmp     qword ptr [rbp+60h], 0
0x1800c6d38  jz      short loc_1800C6D5A
0x1800c6d3a  mov     rcx, gs:60h
0x1800c6d43  mov     r8, [rbp+60h]; P
0x1800c6d47  xor     edx, edx; Flags
0x1800c6d49  mov     rcx, [rcx+30h]; HeapHandle
0x1800c6d4d  call    cs:__imp_RtlFreeHeap
0x1800c6d54  nop     dword ptr [rax+rax+00h]
0x1800c6d59  nop
0x1800c6d5a  cmp     qword ptr [rbp+70h], 0
0x1800c6d5f  jz      short loc_1800C6D81
0x1800c6d61  mov     rcx, gs:60h
0x1800c6d6a  mov     r8, [rbp+70h]; P
0x1800c6d6e  xor     edx, edx; Flags
0x1800c6d70  mov     rcx, [rcx+30h]; HeapHandle
0x1800c6d74  call    cs:__imp_RtlFreeHeap
0x1800c6d7b  nop     dword ptr [rax+rax+00h]
0x1800c6d80  nop
0x1800c6d81  add     rsp, 60h
0x1800c6d85  pop     rbp
0x1800c6d86  retn
```
