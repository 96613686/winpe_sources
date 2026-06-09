# NtFilterLoad

- ea: `0x1800acf90`
- end: `0x1800ad1b7`
- name: `NtFilterLoad`
- size: `551`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800ad88c`

## callees

- `0x18000b126`
- `0x1800acf90`
- `0x1800ae23c`
- `0x1800ae2f8`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800acfd4`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800acfd4`
- `ntdll!RtlAllocateHeap` at `0x1800ad0de`
- `ntdll!RtlAllocateHeap` at `0x1800ad0de`
- `ntdll!NtClose` at `0x1800ad145`
- `ntdll!NtClose` at `0x1800c809b`
- `ntdll!NtClose` at `0x1800ad145`
- `ntdll!NtClose` at `0x1800c809b`
- `ntdll!RtlFreeHeap` at `0x1800ad168`
- `ntdll!RtlFreeHeap` at `0x1800ad18f`
- `ntdll!RtlFreeHeap` at `0x1800c80c0`
- `ntdll!RtlFreeHeap` at `0x1800c80e7`
- `ntdll!RtlFreeHeap` at `0x1800ad168`
- `ntdll!RtlFreeHeap` at `0x1800ad18f`
- `ntdll!RtlFreeHeap` at `0x1800c80c0`
- `ntdll!RtlFreeHeap` at `0x1800c80e7`
- `ntdll!NtCreateFile` at `0x1800ad091`
- `ntdll!NtCreateFile` at `0x1800ad091`

## pseudocode

```c
__int64 __fastcall NtFilterLoad(_WORD *Src)
{
  void *v2; // rbx
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rax
  size_t v7; // rsi
  _WORD *Heap; // rax
  int AllocationSize; // [rsp+20h] [rbp-B8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-B0h]
  struct _UNICODE_STRING v12; // [rsp+68h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-50h] BYREF
  __int64 v15; // [rsp+E8h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+18h] BYREF

  FileHandle = (void *)-1LL;
  v2 = 0;
  v12 = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v12, 0, 0) )
  {
    v3 = -2147024893;
    goto LABEL_11;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v12;
  IoStatusBlock = 0;
  v4 = NtCreateFile(&FileHandle, 0x120116u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v5 = FilterHResultFromNtStatus(v4);
  }
  else
  {
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
    v7 = (unsigned __int16)(2 * v6);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v7 + 2));
    v2 = Heap;
    if ( !Heap )
    {
      v3 = -2147024882;
      goto LABEL_11;
    }
    *Heap = v7;
    memcpy_0(Heap + 1, Src, v7);
    v5 = NtFilterpDeviceIoControl(FileHandle, 0x88004u, AllocationSize, FileAttributes, (__int64)&v15);
  }
  v3 = v5;
LABEL_11:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v12.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12.Buffer);
  return v3;
}

```

## disassembly

```asm
0x1800acf90  mov     rax, rsp
0x1800acf93  mov     [rax+8], rbx
0x1800acf97  mov     [rax+20h], rsi
0x1800acf9b  push    rdi
0x1800acf9c  push    r14
0x1800acf9e  push    r15
0x1800acfa0  sub     rsp, 0C0h
0x1800acfa7  mov     rdi, rcx
0x1800acfaa  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800acfb2  xor     r15d, r15d
0x1800acfb5  mov     ebx, r15d
0x1800acfb8  mov     [rax-78h], rbx
0x1800acfbc  xorps   xmm0, xmm0
0x1800acfbf  movups  xmmword ptr [rax-70h], xmm0
0x1800acfc3  xor     r9d, r9d; DirectoryInfo
0x1800acfc6  xor     r8d, r8d; NtFileNamePart
0x1800acfc9  lea     rdx, [rax-70h]; NtPathName
0x1800acfcd  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1800acfd4  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800acfdb  nop     dword ptr [rax+rax+00h]
0x1800acfe0  test    al, al
0x1800acfe2  jnz     short loc_1800ACFEE
0x1800acfe4  mov     edi, 80070003h
0x1800acfe9  jmp     loc_1800AD137
0x1800acfee  xor     eax, eax
0x1800acff0  mov     dword ptr [rsp+0D8h+ObjectAttributes+4], eax
0x1800acff7  xorps   xmm0, xmm0
0x1800acffa  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x1800ad002  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x1800ad00a  movups  xmmword ptr [rsp+0D8h+ObjectAttributes+1Ch], xmm0
0x1800ad012  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x1800ad01d  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], r15
0x1800ad025  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad030  lea     rax, [rsp+0D8h+var_70]
0x1800ad035  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x1800ad03d  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad046  movups  xmmword ptr [rsp+0D8h+IoStatusBlock], xmm0
0x1800ad04b  mov     [rsp+0D8h+EaLength], r15d; EaLength
0x1800ad050  mov     [rsp+0D8h+EaBuffer], r15; EaBuffer
0x1800ad055  mov     [rsp+0D8h+CreateOptions], r15d; CreateOptions
0x1800ad05a  mov     [rsp+0D8h+CreateDisposition], 1; CreateDisposition
0x1800ad062  mov     [rsp+0D8h+ShareAccess], 2; ShareAccess
0x1800ad06a  mov     [rsp+0D8h+FileAttributes], 80h; int
0x1800ad072  mov     [rsp+0D8h+AllocationSize], r15; int
0x1800ad077  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x1800ad07c  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x1800ad084  mov     edx, 120116h; DesiredAccess
0x1800ad089  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x1800ad091  call    cs:__imp_NtCreateFile
0x1800ad098  nop     dword ptr [rax+rax+00h]
0x1800ad09d  cmp     [rsp+0D8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800ad0a6  jnz     short loc_1800AD0B4
0x1800ad0a8  mov     ecx, eax
0x1800ad0aa  call    FilterHResultFromNtStatus
0x1800ad0af  jmp     loc_1800AD135
0x1800ad0b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ad0b8  inc     rax
0x1800ad0bb  cmp     [rdi+rax*2], r15w
0x1800ad0c0  jnz     short loc_1800AD0B8
0x1800ad0c2  add     ax, ax
0x1800ad0c5  movzx   esi, ax
0x1800ad0c8  lea     r14d, [rsi+2]
0x1800ad0cc  mov     r8d, r14d; Size
0x1800ad0cf  mov     rcx, gs:60h
0x1800ad0d8  xor     edx, edx; Flags
0x1800ad0da  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad0de  call    cs:__imp_RtlAllocateHeap
0x1800ad0e5  nop     dword ptr [rax+rax+00h]
0x1800ad0ea  mov     rbx, rax
0x1800ad0ed  mov     [rsp+0D8h+var_78], rax
0x1800ad0f2  test    rax, rax
0x1800ad0f5  jnz     short loc_1800AD0FE
0x1800ad0f7  mov     edi, 8007000Eh
0x1800ad0fc  jmp     short loc_1800AD137
0x1800ad0fe  mov     [rax], si
0x1800ad101  mov     r8, rsi; Size
0x1800ad104  lea     rcx, [rax+2]; void *
0x1800ad108  mov     rdx, rdi; Src
0x1800ad10b  call    memcpy_0
0x1800ad110  lea     rax, [rsp+0D8h+arg_8]
0x1800ad118  mov     qword ptr [rsp+0D8h+ShareAccess], rax; __int64
0x1800ad11d  mov     r9d, r14d
0x1800ad120  mov     r8, rbx
0x1800ad123  mov     edx, 88004h; FsControlCode
0x1800ad128  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1800ad130  call    NtFilterpDeviceIoControl
0x1800ad135  mov     edi, eax
0x1800ad137  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1800ad13f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ad143  jz      short loc_1800AD151
0x1800ad145  call    cs:__imp_NtClose
0x1800ad14c  nop     dword ptr [rax+rax+00h]
0x1800ad151  test    rbx, rbx
0x1800ad154  jz      short loc_1800AD174
0x1800ad156  mov     rcx, gs:60h
0x1800ad15f  mov     r8, rbx; P
0x1800ad162  xor     edx, edx; Flags
0x1800ad164  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad168  call    cs:__imp_RtlFreeHeap
0x1800ad16f  nop     dword ptr [rax+rax+00h]
0x1800ad174  cmp     [rsp+0D8h+P], r15
0x1800ad179  jz      short loc_1800AD19B
0x1800ad17b  mov     rcx, gs:60h
0x1800ad184  mov     r8, [rsp+0D8h+P]; P
0x1800ad189  xor     edx, edx; Flags
0x1800ad18b  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad18f  call    cs:__imp_RtlFreeHeap
0x1800ad196  nop     dword ptr [rax+rax+00h]
0x1800ad19b  mov     eax, edi
0x1800ad19d  lea     r11, [rsp+0D8h+var_18]
0x1800ad1a5  mov     rbx, [r11+20h]
0x1800ad1a9  mov     rsi, [r11+38h]
0x1800ad1ad  mov     rsp, r11
0x1800ad1b0  pop     r15
0x1800ad1b2  pop     r14
0x1800ad1b4  pop     rdi
0x1800ad1b5  retn
0x1800c8085  push    rbp
0x1800c8087  sub     rsp, 60h
0x1800c808b  mov     rbp, rdx
0x1800c808e  mov     rcx, [rbp+0F0h]; Handle
0x1800c8095  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c8099  jz      short loc_1800C80A8
0x1800c809b  call    cs:__imp_NtClose
0x1800c80a2  nop     dword ptr [rax+rax+00h]
0x1800c80a7  nop
0x1800c80a8  mov     r8, [rbp+60h]; P
0x1800c80ac  test    r8, r8
0x1800c80af  jz      short loc_1800C80CD
0x1800c80b1  mov     rcx, gs:60h
0x1800c80ba  xor     edx, edx; Flags
0x1800c80bc  mov     rcx, [rcx+30h]; HeapHandle
0x1800c80c0  call    cs:__imp_RtlFreeHeap
0x1800c80c7  nop     dword ptr [rax+rax+00h]
0x1800c80cc  nop
0x1800c80cd  cmp     qword ptr [rbp+70h], 0
0x1800c80d2  jz      short loc_1800C80F4
0x1800c80d4  mov     rcx, gs:60h
0x1800c80dd  mov     r8, [rbp+70h]; P
0x1800c80e1  xor     edx, edx; Flags
0x1800c80e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800c80e7  call    cs:__imp_RtlFreeHeap
0x1800c80ee  nop     dword ptr [rax+rax+00h]
0x1800c80f3  nop
0x1800c80f4  add     rsp, 60h
0x1800c80f8  pop     rbp
0x1800c80f9  retn
```
