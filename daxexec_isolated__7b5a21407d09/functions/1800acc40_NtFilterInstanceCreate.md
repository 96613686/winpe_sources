# NtFilterInstanceCreate

- ea: `0x1800acc40`
- end: `0x1800acf8a`
- name: `NtFilterInstanceCreate`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800ad510`

## callees

- `0x18000b126`
- `0x1800acc40`
- `0x1800ae23c`
- `0x1800ae2f8`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800acca2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800acca2`
- `ntdll!RtlAllocateHeap` at `0x1800ace09`
- `ntdll!RtlAllocateHeap` at `0x1800ace09`
- `ntdll!NtClose` at `0x1800acf30`
- `ntdll!NtClose` at `0x1800c802f`
- `ntdll!NtClose` at `0x1800acf30`
- `ntdll!NtClose` at `0x1800c802f`
- `ntdll!RtlFreeHeap` at `0x1800acf15`
- `ntdll!RtlFreeHeap` at `0x1800acf60`
- `ntdll!RtlFreeHeap` at `0x1800c800f`
- `ntdll!RtlFreeHeap` at `0x1800c805d`
- `ntdll!RtlFreeHeap` at `0x1800acf15`
- `ntdll!RtlFreeHeap` at `0x1800acf60`
- `ntdll!RtlFreeHeap` at `0x1800c800f`
- `ntdll!RtlFreeHeap` at `0x1800c805d`
- `ntdll!NtCreateFile` at `0x1800acd66`
- `ntdll!NtCreateFile` at `0x1800acd66`

## pseudocode

```c
__int64 __fastcall NtFilterInstanceCreate(_WORD *a1, _WORD *a2, _WORD *a3, void **a4)
{
  void **v4; // rsi
  void *v8; // rdi
  int v9; // ebx
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // r14
  unsigned __int16 v13; // r14
  __int64 v14; // rbx
  __int64 v15; // r15
  unsigned __int16 v16; // r15
  unsigned __int16 v17; // bx
  _WORD *Heap; // rax
  _WORD *v19; // rsi
  unsigned __int16 v20; // r14
  unsigned __int16 v21; // ax
  int AllocationSize; // [rsp+20h] [rbp-F8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-F0h]
  void *FileHandle; // [rsp+68h] [rbp-B0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-A8h] BYREF
  size_t Size; // [rsp+80h] [rbp-98h] BYREF
  _WORD *v28; // [rsp+88h] [rbp-90h]
  size_t v29; // [rsp+90h] [rbp-88h]
  size_t v30; // [rsp+98h] [rbp-80h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-48h] BYREF

  v4 = a4;
  v8 = 0;
  v28 = 0;
  FileHandle = (void *)-1LL;
  NtPathName = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &NtPathName, 0, 0) )
  {
    v9 = -2147024893;
    goto LABEL_20;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  IoStatusBlock = 0;
  v10 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v11 = FilterHResultFromNtStatus(v10);
  }
  else
  {
    v12 = -1;
    do
      ++v12;
    while ( a1[v12] );
    v13 = 2 * v12;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = 2 * v15;
    if ( a3 )
    {
      do
        ++v14;
      while ( a3[v14] );
      v17 = 2 * v14;
    }
    else
    {
      v17 = 0;
    }
    Size = v13;
    v29 = v16;
    v30 = v17;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16 + v17 + (unsigned int)v13 + 20);
    v8 = Heap;
    v28 = Heap;
    if ( !Heap )
    {
      v9 = -2147024882;
      goto LABEL_20;
    }
    *((_DWORD *)Heap + 1) = 8;
    v19 = Heap + 4;
    *(_DWORD *)Heap = 1;
    Heap[5] = 12;
    Heap[4] = v13;
    memcpy_0((char *)Heap + (unsigned __int16)Heap[5] + 8, a1, Size);
    v20 = v19[1] + v13;
    v19[3] = v20;
    v19[2] = v16;
    memcpy_0((char *)v19 + v20, a2, v29);
    if ( a3 )
    {
      v21 = v19[3] + v19[2];
      v19[5] = v21;
      v19[4] = v17;
      memcpy_0((char *)v19 + v21, a3, v30);
    }
    else
    {
      *((_DWORD *)v19 + 2) = 0;
    }
    v11 = NtFilterpDeviceIoControl(FileHandle, 0x8400Cu, AllocationSize, FileAttributes, (__int64)&Size);
    v4 = a4;
  }
  v9 = v11;
LABEL_20:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( v9 < 0 && FileHandle != (void *)-1LL )
  {
    NtClose(FileHandle);
    FileHandle = (void *)-1LL;
  }
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  *v4 = FileHandle;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800acc40  mov     rax, rsp
0x1800acc43  mov     [rax+20h], r9
0x1800acc47  mov     [rax+10h], rdx
0x1800acc4b  mov     [rax+8], rcx
0x1800acc4f  push    rbx
0x1800acc50  push    rsi
0x1800acc51  push    rdi
0x1800acc52  push    r12
0x1800acc54  push    r13
0x1800acc56  push    r14
0x1800acc58  push    r15
0x1800acc5a  sub     rsp, 0E0h
0x1800acc61  mov     rsi, r9
0x1800acc64  mov     r12, r8
0x1800acc67  mov     r13, rdx
0x1800acc6a  mov     rbx, rcx
0x1800acc6d  xor     r15d, r15d
0x1800acc70  mov     edi, r15d
0x1800acc73  mov     [rax-90h], r15
0x1800acc7a  mov     [rsp+118h+var_B8], r15d
0x1800acc7f  mov     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800acc88  xorps   xmm0, xmm0
0x1800acc8b  movups  xmmword ptr [rsp+118h+NtPathName.Length], xmm0
0x1800acc90  xor     r9d, r9d; DirectoryInfo
0x1800acc93  xor     r8d, r8d; NtFileNamePart
0x1800acc96  lea     rdx, [rsp+118h+NtPathName]; NtPathName
0x1800acc9b  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1800acca2  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800acca9  nop     dword ptr [rax+rax+00h]
0x1800accae  test    al, al
0x1800accb0  jnz     short loc_1800ACCC0
0x1800accb2  mov     ebx, 80070003h
0x1800accb7  mov     [rsp+118h+var_B8], ebx
0x1800accbb  jmp     loc_1800ACEFE
0x1800accc0  xor     eax, eax
0x1800accc2  mov     dword ptr [rsp+118h+ObjectAttributes+4], eax
0x1800accc9  xorps   xmm0, xmm0
0x1800acccc  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x1800accd4  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x1800accdc  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x1800acce4  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x1800accef  mov     [rsp+118h+ObjectAttributes.RootDirectory], r15
0x1800accf7  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x1800acd02  lea     rax, [rsp+118h+NtPathName]
0x1800acd07  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x1800acd0f  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800acd18  movups  xmmword ptr [rsp+118h+IoStatusBlock], xmm0
0x1800acd20  mov     [rsp+118h+EaLength], r15d; EaLength
0x1800acd25  mov     [rsp+118h+EaBuffer], r15; EaBuffer
0x1800acd2a  mov     [rsp+118h+CreateOptions], r15d; CreateOptions
0x1800acd2f  mov     [rsp+118h+CreateDisposition], 1; CreateDisposition
0x1800acd37  mov     [rsp+118h+ShareAccess], 3; ShareAccess
0x1800acd3f  mov     [rsp+118h+FileAttributes], 80h; int
0x1800acd47  mov     [rsp+118h+AllocationSize], r15; int
0x1800acd4c  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x1800acd54  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x1800acd5c  mov     edx, 12019Fh; DesiredAccess
0x1800acd61  lea     rcx, [rsp+118h+FileHandle]; FileHandle
0x1800acd66  call    cs:__imp_NtCreateFile
0x1800acd6d  nop     dword ptr [rax+rax+00h]
0x1800acd72  cmp     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800acd78  jnz     short loc_1800ACD8A
0x1800acd7a  mov     ecx, eax
0x1800acd7c  call    FilterHResultFromNtStatus
0x1800acd81  mov     [rsp+118h+var_B8], eax
0x1800acd85  jmp     loc_1800ACEFC
0x1800acd8a  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800acd8e  inc     r14
0x1800acd91  cmp     [rbx+r14*2], r15w
0x1800acd96  jnz     short loc_1800ACD8E
0x1800acd98  add     r14w, r14w
0x1800acd9c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800acda0  mov     r15, rbx
0x1800acda3  xor     eax, eax
0x1800acda5  inc     r15
0x1800acda8  cmp     [r13+r15*2+0], ax
0x1800acdae  jnz     short loc_1800ACDA5
0x1800acdb0  add     r15w, r15w
0x1800acdb4  test    r12, r12
0x1800acdb7  jz      short loc_1800ACDC8
0x1800acdb9  inc     rbx
0x1800acdbc  cmp     [r12+rbx*2], ax
0x1800acdc1  jnz     short loc_1800ACDB9
0x1800acdc3  add     bx, bx
0x1800acdc6  jmp     short loc_1800ACDCB
0x1800acdc8  movzx   ebx, ax
0x1800acdcb  movzx   ecx, r14w
0x1800acdcf  mov     [rsp+118h+Size], rcx
0x1800acdd7  movzx   edx, r15w
0x1800acddb  mov     [rsp+118h+var_88], rdx
0x1800acde3  movzx   eax, bx
0x1800acde6  mov     [rsp+118h+var_80], rax
0x1800acdee  add     eax, edx
0x1800acdf0  lea     r13d, [rcx+14h]
0x1800acdf4  add     r13d, eax
0x1800acdf7  mov     r8d, r13d; Size
0x1800acdfa  mov     rcx, gs:60h
0x1800ace03  xor     edx, edx; Flags
0x1800ace05  mov     rcx, [rcx+30h]; HeapHandle
0x1800ace09  call    cs:__imp_RtlAllocateHeap
0x1800ace10  nop     dword ptr [rax+rax+00h]
0x1800ace15  mov     rdi, rax
0x1800ace18  mov     [rsp+118h+var_90], rax
0x1800ace20  test    rax, rax
0x1800ace23  jnz     short loc_1800ACE36
0x1800ace25  mov     ebx, 8007000Eh
0x1800ace2a  mov     [rsp+118h+var_B8], ebx
0x1800ace2e  xor     r15d, r15d
0x1800ace31  jmp     loc_1800ACEFE
0x1800ace36  mov     dword ptr [rax+4], 8
0x1800ace3d  lea     rsi, [rax+8]
0x1800ace41  mov     dword ptr [rax], 1
0x1800ace47  mov     eax, 0Ch
0x1800ace4c  mov     [rsi+2], ax
0x1800ace50  mov     [rsi], r14w
0x1800ace54  movzx   ecx, word ptr [rsi+2]
0x1800ace58  add     rcx, rsi; void *
0x1800ace5b  mov     r8, [rsp+118h+Size]; Size
0x1800ace63  mov     rdx, [rsp+118h+Src]; Src
0x1800ace6b  call    memcpy_0
0x1800ace70  add     r14w, [rsi+2]
0x1800ace75  movzx   ecx, r14w
0x1800ace79  mov     [rsi+6], cx
0x1800ace7d  mov     [rsi+4], r15w
0x1800ace82  add     rcx, rsi; void *
0x1800ace85  mov     r8, [rsp+118h+var_88]; Size
0x1800ace8d  mov     rdx, [rsp+118h+arg_8]; Src
0x1800ace95  call    memcpy_0
0x1800ace9a  xor     r15d, r15d
0x1800ace9d  test    r12, r12
0x1800acea0  jz      short loc_1800ACECA
0x1800acea2  movzx   eax, word ptr [rsi+4]
0x1800acea6  add     ax, [rsi+6]
0x1800aceaa  movzx   ecx, ax
0x1800acead  mov     [rsi+0Ah], cx
0x1800aceb1  mov     [rsi+8], bx
0x1800aceb5  add     rcx, rsi; void *
0x1800aceb8  mov     r8, [rsp+118h+var_80]; Size
0x1800acec0  mov     rdx, r12; Src
0x1800acec3  call    memcpy_0
0x1800acec8  jmp     short loc_1800ACECE
0x1800aceca  mov     [rsi+8], r15d
0x1800acece  lea     rax, [rsp+118h+Size]
0x1800aced6  mov     qword ptr [rsp+118h+ShareAccess], rax; __int64
0x1800acedb  mov     r9d, r13d
0x1800acede  mov     r8, rdi
0x1800acee1  mov     edx, 8400Ch; FsControlCode
0x1800acee6  mov     rcx, [rsp+118h+FileHandle]; Handle
0x1800aceeb  call    NtFilterpDeviceIoControl
0x1800acef0  mov     [rsp+118h+var_B8], eax
0x1800acef4  mov     rsi, [rsp+118h+arg_18]
0x1800acefc  mov     ebx, eax
0x1800acefe  test    rdi, rdi
0x1800acf01  jz      short loc_1800ACF21
0x1800acf03  mov     rcx, gs:60h
0x1800acf0c  mov     r8, rdi; P
0x1800acf0f  xor     edx, edx; Flags
0x1800acf11  mov     rcx, [rcx+30h]; HeapHandle
0x1800acf15  call    cs:__imp_RtlFreeHeap
0x1800acf1c  nop     dword ptr [rax+rax+00h]
0x1800acf21  test    ebx, ebx
0x1800acf23  jns     short loc_1800ACF45
0x1800acf25  mov     rcx, [rsp+118h+FileHandle]; Handle
0x1800acf2a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800acf2e  jz      short loc_1800ACF45
0x1800acf30  call    cs:__imp_NtClose
0x1800acf37  nop     dword ptr [rax+rax+00h]
0x1800acf3c  mov     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800acf45  cmp     [rsp+118h+NtPathName.Buffer], r15
0x1800acf4a  jz      short loc_1800ACF6C
0x1800acf4c  mov     rcx, gs:60h
0x1800acf55  mov     r8, [rsp+118h+NtPathName.Buffer]; P
0x1800acf5a  xor     edx, edx; Flags
0x1800acf5c  mov     rcx, [rcx+30h]; HeapHandle
0x1800acf60  call    cs:__imp_RtlFreeHeap
0x1800acf67  nop     dword ptr [rax+rax+00h]
0x1800acf6c  mov     rax, [rsp+118h+FileHandle]
0x1800acf71  mov     [rsi], rax
0x1800acf74  mov     eax, ebx
0x1800acf76  add     rsp, 0E0h
0x1800acf7d  pop     r15
0x1800acf7f  pop     r14
0x1800acf81  pop     r13
0x1800acf83  pop     r12
0x1800acf85  pop     rdi
0x1800acf86  pop     rsi
0x1800acf87  pop     rbx
0x1800acf88  retn
0x1800c7feb  push    rbp
0x1800c7fed  sub     rsp, 60h
0x1800c7ff1  mov     rbp, rdx
0x1800c7ff4  mov     r8, [rbp+88h]; P
0x1800c7ffb  test    r8, r8
0x1800c7ffe  jz      short loc_1800C801C
0x1800c8000  mov     rcx, gs:60h
0x1800c8009  xor     edx, edx; Flags
0x1800c800b  mov     rcx, [rcx+30h]; HeapHandle
0x1800c800f  call    cs:__imp_RtlFreeHeap
0x1800c8016  nop     dword ptr [rax+rax+00h]
0x1800c801b  nop
0x1800c801c  test    dword ptr [rbp+60h], 80000000h
0x1800c8023  jz      short loc_1800C8043
0x1800c8025  mov     rcx, [rbp+68h]; Handle
0x1800c8029  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c802d  jz      short loc_1800C8043
0x1800c802f  call    cs:__imp_NtClose
0x1800c8036  nop     dword ptr [rax+rax+00h]
0x1800c803b  mov     qword ptr [rbp+68h], 0FFFFFFFFFFFFFFFFh
0x1800c8043  cmp     qword ptr [rbp+78h], 0
0x1800c8048  jz      short loc_1800C806A
0x1800c804a  mov     rcx, gs:60h
0x1800c8053  mov     r8, [rbp+78h]; P
0x1800c8057  xor     edx, edx; Flags
0x1800c8059  mov     rcx, [rcx+30h]; HeapHandle
0x1800c805d  call    cs:__imp_RtlFreeHeap
0x1800c8064  nop     dword ptr [rax+rax+00h]
0x1800c8069  nop
0x1800c806a  mov     rcx, [rbp+138h]
0x1800c8071  mov     rax, [rbp+68h]
0x1800c8075  mov     [rcx], rax
0x1800c8078  add     rsp, 60h
0x1800c807c  pop     rbp
0x1800c807d  retn
```
