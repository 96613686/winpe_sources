# NtFilterpCommonAttach

- ea: `0x1800abc00`
- end: `0x1800abf77`
- name: `NtFilterpCommonAttach`
- size: `887`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, __int16, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800abf80`

## callees

- `0x18000b3c9`
- `0x1800abc00`
- `0x1800acd04`
- `0x1800acdc0`
- `0x1800bccec`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800abc6b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800abc6b`
- `ntdll!RtlAllocateHeap` at `0x1800abe0f`
- `ntdll!RtlAllocateHeap` at `0x1800abe0f`
- `ntdll!NtClose` at `0x1800abf0d`
- `ntdll!NtClose` at `0x1800c6da1`
- `ntdll!NtClose` at `0x1800abf0d`
- `ntdll!NtClose` at `0x1800c6da1`
- `ntdll!RtlFreeHeap` at `0x1800abf32`
- `ntdll!RtlFreeHeap` at `0x1800abf5f`
- `ntdll!RtlFreeHeap` at `0x1800c6dc8`
- `ntdll!RtlFreeHeap` at `0x1800c6df5`
- `ntdll!RtlFreeHeap` at `0x1800abf32`
- `ntdll!RtlFreeHeap` at `0x1800abf5f`
- `ntdll!RtlFreeHeap` at `0x1800c6dc8`
- `ntdll!RtlFreeHeap` at `0x1800c6df5`
- `ntdll!NtCreateFile` at `0x1800abd38`
- `ntdll!NtCreateFile` at `0x1800abd38`

## pseudocode

```c
__int64 __fastcall NtFilterpCommonAttach(
        _WORD *Src,
        _WORD *a2,
        int a3,
        _WORD *a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int a7)
{
  _WORD *Heap; // rbx
  unsigned int v11; // eax
  __int64 v13; // r8
  unsigned __int16 v14; // r8
  __int64 v15; // rdx
  unsigned __int16 v16; // dx
  __int64 v17; // rax
  unsigned __int16 v18; // ax
  unsigned int v19; // eax
  __int16 v20; // di
  unsigned int v21; // edx
  __int64 v22; // rcx
  __int16 v23; // r14
  unsigned int v24; // eax
  unsigned __int16 v25; // di
  __int64 v26; // [rsp+0h] [rbp-F8h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-D8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-D0h]
  void *FileHandle; // [rsp+60h] [rbp-98h] BYREF
  PVOID P; // [rsp+68h] [rbp-90h]
  __int64 *v31; // [rsp+70h] [rbp-88h]
  struct _UNICODE_STRING v32; // [rsp+78h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-60h] BYREF
  __int64 v35; // [rsp+110h] [rbp+18h] BYREF

  LODWORD(v35) = a3;
  v31 = &v26;
  Heap = 0;
  P = 0;
  FileHandle = (void *)-1LL;
  v32 = 0;
  if ( Src && a2 )
  {
    if ( RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v32, 0, 0) )
    {
      *(&ObjectAttributes.Length + 1) = 0;
      memset(&ObjectAttributes.Attributes + 1, 0, 20);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &v32;
      IoStatusBlock = 0;
      v11 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
      if ( FileHandle == (void *)-1LL )
      {
        LODWORD(v35) = FilterHResultFromNtStatus(v11);
        local_unwind_0(v31, &loc_1800ABD6B);
        return (unsigned int)v35;
      }
      v13 = -1;
      do
        ++v13;
      while ( Src[v13] );
      v14 = 2 * v13;
      a6 = v14;
      v15 = -1;
      do
        ++v15;
      while ( a2[v15] );
      v16 = 2 * v15;
      a5 = v16;
      if ( a4 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a4[v17] );
        v18 = 2 * v17;
      }
      else
      {
        v18 = 0;
      }
      LOWORD(v35) = v18;
      a7 = v14 + 20 + v16 + v18;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a7);
      P = Heap;
      if ( Heap )
      {
        v19 = a6;
        *Heap = a6;
        Heap[1] = 20;
        v20 = v19;
        memcpy_0(Heap + 10, Src, v19);
        v21 = a5;
        Heap[2] = a5;
        v22 = (unsigned __int16)(v20 + 20);
        Heap[3] = v22;
        v23 = v21;
        memcpy_0((char *)Heap + v22, a2, v21);
        *((_DWORD *)Heap + 2) = 1;
        v24 = (unsigned __int16)v35;
        Heap[6] = v35;
        if ( a4 )
        {
          v25 = v23 + v20 + 20;
          Heap[7] = v25;
          memcpy_0((char *)Heap + v25, a4, v24);
        }
        else
        {
          Heap[7] = 0;
        }
        *((_DWORD *)Heap + 4) = 0;
        LODWORD(v35) = NtFilterpDeviceIoControl(
                         FileHandle,
                         0x88010u,
                         (int)AllocationSize,
                         FileAttributes,
                         (__int64)&v35);
      }
      else
      {
        LODWORD(v35) = -2147024882;
      }
    }
    else
    {
      LODWORD(v35) = -2147024893;
    }
  }
  else
  {
    LODWORD(v35) = -2147024809;
  }
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v32.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32.Buffer);
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x1800abc00  mov     rax, rsp
0x1800abc03  mov     [rax+8], rbx
0x1800abc07  mov     [rax+10h], rsi
0x1800abc0b  mov     [rax+18h], r8d
0x1800abc0f  push    rdi
0x1800abc10  push    r12
0x1800abc12  push    r13
0x1800abc14  push    r14
0x1800abc16  push    r15
0x1800abc18  sub     rsp, 0D0h
0x1800abc1f  mov     [rsp+0F8h+var_88], rsp
0x1800abc24  mov     rsi, r9
0x1800abc27  mov     r15, rdx
0x1800abc2a  mov     r14, rcx
0x1800abc2d  xor     r12d, r12d
0x1800abc30  mov     ebx, r12d
0x1800abc33  mov     [rsp+0F8h+P], rbx
0x1800abc38  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800abc3c  mov     [rsp+0F8h+FileHandle], r13
0x1800abc41  xorps   xmm0, xmm0
0x1800abc44  movups  xmmword ptr [rax-80h], xmm0
0x1800abc48  test    rcx, rcx
0x1800abc4b  jz      loc_1800ABEF8
0x1800abc51  test    rdx, rdx
0x1800abc54  jz      loc_1800ABEF8
0x1800abc5a  xor     r9d, r9d; DirectoryInfo
0x1800abc5d  xor     r8d, r8d; NtFileNamePart
0x1800abc60  lea     rdx, [rax-80h]; NtPathName
0x1800abc64  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1800abc6b  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800abc72  nop     dword ptr [rax+rax+00h]
0x1800abc77  test    al, al
0x1800abc79  jnz     short loc_1800ABC8B
0x1800abc7b  mov     dword ptr [rsp+0F8h+arg_10], 80070003h
0x1800abc86  jmp     loc_1800ABF03
0x1800abc8b  xor     eax, eax
0x1800abc8d  mov     dword ptr [rsp+0F8h+ObjectAttributes+4], eax
0x1800abc94  xorps   xmm0, xmm0
0x1800abc97  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x1800abc9f  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x1800abca7  mov     [rsp+0F8h+ObjectAttributes.SecurityDescriptor], rax
0x1800abcaf  mov     dword ptr [rsp+0F8h+ObjectAttributes.SecurityQualityOfService], eax
0x1800abcb6  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x1800abcc1  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], r12
0x1800abcc9  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800abcd4  lea     rax, [rsp+0F8h+var_80]
0x1800abcd9  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x1800abce1  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800abcea  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x1800abcf2  mov     [rsp+0F8h+EaLength], r12d; EaLength
0x1800abcf7  mov     [rsp+0F8h+EaBuffer], r12; EaBuffer
0x1800abcfc  mov     [rsp+0F8h+CreateOptions], r12d; CreateOptions
0x1800abd01  mov     [rsp+0F8h+CreateDisposition], 1; CreateDisposition
0x1800abd09  mov     [rsp+0F8h+ShareAccess], 3; ShareAccess
0x1800abd11  mov     [rsp+0F8h+FileAttributes], 80h; int
0x1800abd19  mov     [rsp+0F8h+AllocationSize], r12; int
0x1800abd1e  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x1800abd26  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x1800abd2e  mov     edx, 12019Fh; DesiredAccess
0x1800abd33  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x1800abd38  call    cs:__imp_NtCreateFile
0x1800abd3f  nop     dword ptr [rax+rax+00h]
0x1800abd44  cmp     [rsp+0F8h+FileHandle], r13
0x1800abd49  jnz     short loc_1800ABD90
0x1800abd4b  mov     ecx, eax
0x1800abd4d  call    FilterHResultFromNtStatus
0x1800abd52  mov     dword ptr [rsp+0F8h+arg_10], eax
0x1800abd59  lea     rdx, loc_1800ABD6B
0x1800abd60  mov     rcx, [rsp+0F8h+var_88]
0x1800abd65  call    _local_unwind_0
0x1800abd6a  nop
0x1800abd6b  mov     eax, dword ptr [rsp+0F8h+arg_10]
0x1800abd72  lea     r11, [rsp+0F8h+var_28]
0x1800abd7a  mov     rbx, [r11+30h]
0x1800abd7e  mov     rsi, [r11+38h]
0x1800abd82  mov     rsp, r11
0x1800abd85  pop     r15
0x1800abd87  pop     r14
0x1800abd89  pop     r13
0x1800abd8b  pop     r12
0x1800abd8d  pop     rdi
0x1800abd8e  retn
0x1800abd90  mov     r8, r13
0x1800abd93  inc     r8
0x1800abd96  cmp     [r14+r8*2], r12w
0x1800abd9b  jnz     short loc_1800ABD93
0x1800abd9d  add     r8w, r8w
0x1800abda1  mov     [rsp+0F8h+arg_28], r8w
0x1800abdaa  mov     rdx, r13
0x1800abdad  inc     rdx
0x1800abdb0  cmp     [r15+rdx*2], r12w
0x1800abdb5  jnz     short loc_1800ABDAD
0x1800abdb7  add     dx, dx
0x1800abdba  mov     [rsp+0F8h+arg_20], dx
0x1800abdc2  test    rsi, rsi
0x1800abdc5  jz      short loc_1800ABDD9
0x1800abdc7  mov     rax, r13
0x1800abdca  inc     rax
0x1800abdcd  cmp     [rsi+rax*2], r12w
0x1800abdd2  jnz     short loc_1800ABDCA
0x1800abdd4  add     ax, ax
0x1800abdd7  jmp     short loc_1800ABDDD
0x1800abdd9  movzx   eax, r12w
0x1800abddd  mov     word ptr [rsp+0F8h+arg_10], ax
0x1800abde5  movzx   ecx, ax
0x1800abde8  movzx   eax, dx
0x1800abdeb  add     ecx, eax
0x1800abded  movzx   eax, r8w
0x1800abdf1  add     eax, 14h
0x1800abdf4  add     ecx, eax
0x1800abdf6  mov     [rsp+0F8h+arg_30], ecx
0x1800abdfd  mov     r8d, ecx; Size
0x1800abe00  mov     rcx, gs:60h
0x1800abe09  xor     edx, edx; Flags
0x1800abe0b  mov     rcx, [rcx+30h]; HeapHandle
0x1800abe0f  call    cs:__imp_RtlAllocateHeap
0x1800abe16  nop     dword ptr [rax+rax+00h]
0x1800abe1b  mov     rbx, rax
0x1800abe1e  mov     [rsp+0F8h+P], rax
0x1800abe23  test    rax, rax
0x1800abe26  jnz     short loc_1800ABE38
0x1800abe28  mov     dword ptr [rsp+0F8h+arg_10], 8007000Eh
0x1800abe33  jmp     loc_1800ABF03
0x1800abe38  movzx   eax, [rsp+0F8h+arg_28]
0x1800abe40  mov     [rbx], ax
0x1800abe43  mov     ecx, 14h
0x1800abe48  mov     [rbx+2], cx
0x1800abe4c  mov     edi, eax
0x1800abe4e  lea     rcx, [rbx+14h]; void *
0x1800abe52  mov     r8d, eax; Size
0x1800abe55  mov     rdx, r14; Src
0x1800abe58  call    memcpy_0
0x1800abe5d  movzx   edx, [rsp+0F8h+arg_20]
0x1800abe65  mov     [rbx+4], dx
0x1800abe69  mov     eax, 14h
0x1800abe6e  add     eax, edi
0x1800abe70  movzx   ecx, ax
0x1800abe73  mov     [rbx+6], cx
0x1800abe77  mov     r14d, edx
0x1800abe7a  add     rcx, rbx; void *
0x1800abe7d  mov     r8d, edx; Size
0x1800abe80  mov     rdx, r15; Src
0x1800abe83  call    memcpy_0
0x1800abe88  mov     dword ptr [rbx+8], 1
0x1800abe8f  movzx   eax, word ptr [rsp+0F8h+arg_10]
0x1800abe97  mov     [rbx+0Ch], ax
0x1800abe9b  test    rsi, rsi
0x1800abe9e  jz      short loc_1800ABEBF
0x1800abea0  add     di, 14h
0x1800abea4  add     di, r14w
0x1800abea8  movzx   ecx, di
0x1800abeab  mov     [rbx+0Eh], cx
0x1800abeaf  mov     r8d, eax; Size
0x1800abeb2  add     rcx, rbx; void *
0x1800abeb5  mov     rdx, rsi; Src
0x1800abeb8  call    memcpy_0
0x1800abebd  jmp     short loc_1800ABEC4
0x1800abebf  mov     [rbx+0Eh], r12w
0x1800abec4  mov     [rbx+10h], r12d
0x1800abec8  lea     rax, [rsp+0F8h+arg_10]
0x1800abed0  mov     qword ptr [rsp+0F8h+ShareAccess], rax; __int64
0x1800abed5  mov     r9d, [rsp+0F8h+arg_30]
0x1800abedd  mov     r8, rbx
0x1800abee0  mov     edx, 88010h; FsControlCode
0x1800abee5  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x1800abeea  call    NtFilterpDeviceIoControl
0x1800abeef  mov     dword ptr [rsp+0F8h+arg_10], eax
0x1800abef6  jmp     short loc_1800ABF03
0x1800abef8  mov     dword ptr [rsp+0F8h+arg_10], 80070057h
0x1800abf03  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x1800abf08  cmp     rcx, r13
0x1800abf0b  jz      short loc_1800ABF19
0x1800abf0d  call    cs:__imp_NtClose
0x1800abf14  nop     dword ptr [rax+rax+00h]
0x1800abf19  test    rbx, rbx
0x1800abf1c  jz      short loc_1800ABF3E
0x1800abf1e  mov     rcx, gs:60h
0x1800abf27  mov     r8, [rsp+0F8h+P]; P
0x1800abf2c  xor     edx, edx; Flags
0x1800abf2e  mov     rcx, [rcx+30h]; HeapHandle
0x1800abf32  call    cs:__imp_RtlFreeHeap
0x1800abf39  nop     dword ptr [rax+rax+00h]
0x1800abf3e  cmp     [rsp+0F8h+var_78], r12
0x1800abf46  jz      short loc_1800ABF6B
0x1800abf48  mov     rcx, gs:60h
0x1800abf51  mov     r8, [rsp+0F8h+var_78]; P
0x1800abf59  xor     edx, edx; Flags
0x1800abf5b  mov     rcx, [rcx+30h]; HeapHandle
0x1800abf5f  call    cs:__imp_RtlFreeHeap
0x1800abf66  nop     dword ptr [rax+rax+00h]
0x1800abf6b  mov     eax, dword ptr [rsp+0F8h+arg_10]
0x1800abf72  jmp     loc_1800ABD72
0x1800c6d8e  push    rbp
0x1800c6d90  sub     rsp, 60h
0x1800c6d94  mov     rbp, rdx
0x1800c6d97  mov     rcx, [rbp+60h]; Handle
0x1800c6d9b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c6d9f  jz      short loc_1800C6DAE
0x1800c6da1  call    cs:__imp_NtClose
0x1800c6da8  nop     dword ptr [rax+rax+00h]
0x1800c6dad  nop
0x1800c6dae  cmp     qword ptr [rbp+68h], 0
0x1800c6db3  jz      short loc_1800C6DD5
0x1800c6db5  mov     rcx, gs:60h
0x1800c6dbe  mov     r8, [rbp+68h]; P
0x1800c6dc2  xor     edx, edx; Flags
0x1800c6dc4  mov     rcx, [rcx+30h]; HeapHandle
0x1800c6dc8  call    cs:__imp_RtlFreeHeap
0x1800c6dcf  nop     dword ptr [rax+rax+00h]
0x1800c6dd4  nop
0x1800c6dd5  cmp     qword ptr [rbp+80h], 0
0x1800c6ddd  jz      short loc_1800C6E02
0x1800c6ddf  mov     rcx, gs:60h
0x1800c6de8  mov     r8, [rbp+80h]; P
0x1800c6def  xor     edx, edx; Flags
0x1800c6df1  mov     rcx, [rcx+30h]; HeapHandle
0x1800c6df5  call    cs:__imp_RtlFreeHeap
0x1800c6dfc  nop     dword ptr [rax+rax+00h]
0x1800c6e01  nop
0x1800c6e02  add     rsp, 60h
0x1800c6e06  pop     rbp
0x1800c6e07  retn
```
