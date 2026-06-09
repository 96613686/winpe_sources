# NtFilterInstanceCreate

- ea: `0x1800ab670`
- end: `0x1800ab9b2`
- name: `NtFilterInstanceCreate`
- size: `834`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800abf80`

## callees

- `0x18000b3c9`
- `0x1800ab670`
- `0x1800acd04`
- `0x1800acdc0`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ab6cc`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ab6cc`
- `ntdll!RtlAllocateHeap` at `0x1800ab82f`
- `ntdll!RtlAllocateHeap` at `0x1800ab82f`
- `ntdll!NtClose` at `0x1800ab947`
- `ntdll!NtClose` at `0x1800c6cb7`
- `ntdll!NtClose` at `0x1800ab947`
- `ntdll!NtClose` at `0x1800c6cb7`
- `ntdll!RtlFreeHeap` at `0x1800ab928`
- `ntdll!RtlFreeHeap` at `0x1800ab97a`
- `ntdll!RtlFreeHeap` at `0x1800c6c97`
- `ntdll!RtlFreeHeap` at `0x1800c6ce8`
- `ntdll!RtlFreeHeap` at `0x1800ab928`
- `ntdll!RtlFreeHeap` at `0x1800ab97a`
- `ntdll!RtlFreeHeap` at `0x1800c6c97`
- `ntdll!RtlFreeHeap` at `0x1800c6ce8`
- `ntdll!NtCreateFile` at `0x1800ab79a`
- `ntdll!NtCreateFile` at `0x1800ab79a`

## pseudocode

```c
__int64 __fastcall NtFilterInstanceCreate(_WORD *Src, _WORD *a2, _WORD *a3, void **a4)
{
  char *v8; // rdi
  int v9; // ebx
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  unsigned __int16 v13; // dx
  __int64 v14; // rcx
  unsigned __int16 v15; // cx
  __int64 v16; // rax
  unsigned __int16 v17; // ax
  unsigned __int16 v18; // r14
  char *Heap; // rax
  unsigned __int16 *v20; // rbx
  unsigned int v21; // eax
  unsigned __int16 v22; // r14
  unsigned int v23; // eax
  __int64 v24; // rcx
  int AllocationSize; // [rsp+20h] [rbp-E8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-E0h]
  int v28; // [rsp+60h] [rbp-A8h]
  unsigned __int16 v29; // [rsp+64h] [rbp-A4h]
  void *FileHandle; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v31; // [rsp+70h] [rbp-98h]
  _DWORD v32[3]; // [rsp+74h] [rbp-94h] BYREF
  unsigned int v33; // [rsp+80h] [rbp-88h]
  struct _UNICODE_STRING v34; // [rsp+88h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-40h] BYREF

  v8 = 0;
  *(_QWORD *)&v32[1] = 0;
  FileHandle = (void *)-1LL;
  v34 = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v34, 0, 0) )
  {
    v9 = -2147024893;
    v28 = -2147024893;
    goto LABEL_21;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v34;
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
    while ( Src[v12] );
    v13 = 2 * v12;
    v31 = v13;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = 2 * v14;
    LOWORD(v32[0]) = v15;
    if ( a3 )
    {
      v16 = -1;
      do
        ++v16;
      while ( a3[v16] );
      v17 = 2 * v16;
    }
    else
    {
      v17 = 0;
    }
    v29 = v17;
    v18 = v13;
    v33 = v15 + 20 + v13 + v17;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
    v8 = Heap;
    *(_QWORD *)&v32[1] = Heap;
    if ( !Heap )
    {
      v9 = -2147024882;
      v28 = -2147024882;
      goto LABEL_21;
    }
    *((_DWORD *)Heap + 1) = 8;
    v20 = (unsigned __int16 *)(Heap + 8);
    *(_DWORD *)Heap = 1;
    *((_WORD *)Heap + 5) = 12;
    v21 = v31;
    *v20 = v31;
    memcpy_0((char *)v20 + v20[1], Src, v21);
    v22 = v20[1] + v18;
    v20[3] = v22;
    v23 = LOWORD(v32[0]);
    v20[2] = v32[0];
    memcpy_0((char *)v20 + v22, a2, v23);
    if ( a3 )
    {
      v24 = (unsigned __int16)(v20[2] + v20[3]);
      v20[5] = v24;
      v20[4] = v29;
      memcpy_0((char *)v20 + v24, a3, v29);
    }
    else
    {
      *((_DWORD *)v20 + 2) = 0;
    }
    v11 = NtFilterpDeviceIoControl(FileHandle, 0x8400Cu, AllocationSize, FileAttributes, (__int64)v32);
  }
  v28 = v11;
  v9 = v11;
LABEL_21:
  if ( v8 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v32[1]);
    v9 = v28;
  }
  if ( v9 < 0 && FileHandle != (void *)-1LL )
  {
    NtClose(FileHandle);
    FileHandle = (void *)-1LL;
  }
  if ( v34.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v34.Buffer);
    v9 = v28;
  }
  *a4 = FileHandle;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ab670  mov     rax, rsp
0x1800ab673  mov     [rax+8], rbx
0x1800ab677  mov     [rax+10h], rsi
0x1800ab67b  mov     [rax+20h], r9
0x1800ab67f  push    rdi
0x1800ab680  push    r12
0x1800ab682  push    r13
0x1800ab684  push    r14
0x1800ab686  push    r15
0x1800ab688  sub     rsp, 0E0h
0x1800ab68f  mov     r15, r9
0x1800ab692  mov     rsi, r8
0x1800ab695  mov     r13, rdx
0x1800ab698  mov     r12, rcx
0x1800ab69b  xor     r14d, r14d
0x1800ab69e  mov     edi, r14d
0x1800ab6a1  mov     qword ptr [rsp+108h+var_94+4], r14
0x1800ab6a6  mov     [rsp+108h+var_A8], r14d
0x1800ab6ab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ab6af  mov     [rsp+108h+FileHandle], rbx
0x1800ab6b4  xorps   xmm0, xmm0
0x1800ab6b7  movups  xmmword ptr [rax-80h], xmm0
0x1800ab6bb  xor     r9d, r9d; DirectoryInfo
0x1800ab6be  xor     r8d, r8d; NtFileNamePart
0x1800ab6c1  lea     rdx, [rax-80h]; NtPathName
0x1800ab6c5  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1800ab6cc  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ab6d3  nop     dword ptr [rax+rax+00h]
0x1800ab6d8  test    al, al
0x1800ab6da  jnz     short loc_1800AB6EA
0x1800ab6dc  mov     ebx, 80070003h
0x1800ab6e1  mov     [rsp+108h+var_A8], ebx
0x1800ab6e5  jmp     loc_1800AB90F
0x1800ab6ea  xor     eax, eax
0x1800ab6ec  mov     dword ptr [rsp+108h+ObjectAttributes+4], eax
0x1800ab6f3  xorps   xmm0, xmm0
0x1800ab6f6  movups  xmmword ptr [rsp+108h+ObjectAttributes.Length], xmm0
0x1800ab6fe  movups  xmmword ptr [rsp+108h+ObjectAttributes.ObjectName], xmm0
0x1800ab706  mov     [rsp+108h+ObjectAttributes.SecurityDescriptor], rax
0x1800ab70e  mov     dword ptr [rsp+108h+ObjectAttributes.SecurityQualityOfService], eax
0x1800ab715  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x1800ab720  mov     [rsp+108h+ObjectAttributes.RootDirectory], r14
0x1800ab728  mov     [rsp+108h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ab733  lea     rax, [rsp+108h+var_80]
0x1800ab73b  mov     [rsp+108h+ObjectAttributes.ObjectName], rax
0x1800ab743  movdqu  xmmword ptr [rsp+108h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ab74c  movups  xmmword ptr [rsp+108h+IoStatusBlock], xmm0
0x1800ab754  mov     [rsp+108h+EaLength], r14d; EaLength
0x1800ab759  mov     [rsp+108h+EaBuffer], r14; EaBuffer
0x1800ab75e  mov     [rsp+108h+CreateOptions], r14d; CreateOptions
0x1800ab763  mov     [rsp+108h+CreateDisposition], 1; CreateDisposition
0x1800ab76b  mov     [rsp+108h+ShareAccess], 3; ShareAccess
0x1800ab773  mov     [rsp+108h+FileAttributes], 80h; int
0x1800ab77b  mov     [rsp+108h+AllocationSize], r14; int
0x1800ab780  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x1800ab788  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x1800ab790  mov     edx, 12019Fh; DesiredAccess
0x1800ab795  lea     rcx, [rsp+108h+FileHandle]; FileHandle
0x1800ab79a  call    cs:__imp_NtCreateFile
0x1800ab7a1  nop     dword ptr [rax+rax+00h]
0x1800ab7a6  cmp     [rsp+108h+FileHandle], rbx
0x1800ab7ab  jnz     short loc_1800AB7B9
0x1800ab7ad  mov     ecx, eax
0x1800ab7af  call    FilterHResultFromNtStatus
0x1800ab7b4  jmp     loc_1800AB909
0x1800ab7b9  mov     rdx, rbx
0x1800ab7bc  inc     rdx
0x1800ab7bf  cmp     [r12+rdx*2], r14w
0x1800ab7c4  jnz     short loc_1800AB7BC
0x1800ab7c6  add     dx, dx
0x1800ab7c9  mov     [rsp+108h+var_98], dx
0x1800ab7ce  mov     rcx, rbx
0x1800ab7d1  inc     rcx
0x1800ab7d4  cmp     [r13+rcx*2+0], r14w
0x1800ab7da  jnz     short loc_1800AB7D1
0x1800ab7dc  add     cx, cx
0x1800ab7df  mov     word ptr [rsp+108h+var_94], cx
0x1800ab7e4  test    rsi, rsi
0x1800ab7e7  jz      short loc_1800AB7FB
0x1800ab7e9  mov     rax, rbx
0x1800ab7ec  inc     rax
0x1800ab7ef  cmp     [rsi+rax*2], r14w
0x1800ab7f4  jnz     short loc_1800AB7EC
0x1800ab7f6  add     ax, ax
0x1800ab7f9  jmp     short loc_1800AB7FF
0x1800ab7fb  movzx   eax, r14w
0x1800ab7ff  mov     [rsp+108h+var_A4], ax
0x1800ab804  movzx   r14d, dx
0x1800ab808  movzx   edx, ax
0x1800ab80b  movzx   ecx, cx
0x1800ab80e  add     edx, r14d
0x1800ab811  add     ecx, 14h
0x1800ab814  add     edx, ecx
0x1800ab816  mov     [rsp+108h+var_88], edx
0x1800ab81d  mov     r8d, edx; Size
0x1800ab820  mov     rcx, gs:60h
0x1800ab829  xor     edx, edx; Flags
0x1800ab82b  mov     rcx, [rcx+30h]; HeapHandle
0x1800ab82f  call    cs:__imp_RtlAllocateHeap
0x1800ab836  nop     dword ptr [rax+rax+00h]
0x1800ab83b  mov     rdi, rax
0x1800ab83e  mov     qword ptr [rsp+108h+var_94+4], rax
0x1800ab843  test    rax, rax
0x1800ab846  jnz     short loc_1800AB859
0x1800ab848  mov     ebx, 8007000Eh
0x1800ab84d  mov     [rsp+108h+var_A8], ebx
0x1800ab851  xor     r14d, r14d
0x1800ab854  jmp     loc_1800AB90F
0x1800ab859  mov     dword ptr [rax+4], 8
0x1800ab860  lea     rbx, [rax+8]
0x1800ab864  mov     dword ptr [rax], 1
0x1800ab86a  mov     eax, 0Ch
0x1800ab86f  mov     [rbx+2], ax
0x1800ab873  movzx   eax, [rsp+108h+var_98]
0x1800ab878  mov     [rbx], ax
0x1800ab87b  mov     r8d, eax; Size
0x1800ab87e  movzx   ecx, word ptr [rbx+2]
0x1800ab882  add     rcx, rbx; void *
0x1800ab885  mov     rdx, r12; Src
0x1800ab888  call    memcpy_0
0x1800ab88d  add     r14w, [rbx+2]
0x1800ab892  movzx   ecx, r14w
0x1800ab896  mov     [rbx+6], cx
0x1800ab89a  movzx   eax, word ptr [rsp+108h+var_94]
0x1800ab89f  mov     [rbx+4], ax
0x1800ab8a3  mov     r8d, eax; Size
0x1800ab8a6  add     rcx, rbx; void *
0x1800ab8a9  mov     rdx, r13; Src
0x1800ab8ac  call    memcpy_0
0x1800ab8b1  xor     r14d, r14d
0x1800ab8b4  test    rsi, rsi
0x1800ab8b7  jz      short loc_1800AB8E1
0x1800ab8b9  movzx   eax, word ptr [rbx+6]
0x1800ab8bd  add     ax, [rbx+4]
0x1800ab8c1  movzx   ecx, ax
0x1800ab8c4  mov     [rbx+0Ah], cx
0x1800ab8c8  movzx   eax, [rsp+108h+var_A4]
0x1800ab8cd  mov     [rbx+8], ax
0x1800ab8d1  mov     r8d, eax; Size
0x1800ab8d4  add     rcx, rbx; void *
0x1800ab8d7  mov     rdx, rsi; Src
0x1800ab8da  call    memcpy_0
0x1800ab8df  jmp     short loc_1800AB8E5
0x1800ab8e1  mov     [rbx+8], r14d
0x1800ab8e5  lea     rax, [rsp+108h+var_94]
0x1800ab8ea  mov     qword ptr [rsp+108h+ShareAccess], rax; __int64
0x1800ab8ef  mov     r9d, [rsp+108h+var_88]
0x1800ab8f7  mov     r8, rdi
0x1800ab8fa  mov     edx, 8400Ch; FsControlCode
0x1800ab8ff  mov     rcx, [rsp+108h+FileHandle]; Handle
0x1800ab904  call    NtFilterpDeviceIoControl
0x1800ab909  mov     [rsp+108h+var_A8], eax
0x1800ab90d  mov     ebx, eax
0x1800ab90f  test    rdi, rdi
0x1800ab912  jz      short loc_1800AB938
0x1800ab914  mov     rcx, gs:60h
0x1800ab91d  mov     r8, qword ptr [rsp+108h+var_94+4]; P
0x1800ab922  xor     edx, edx; Flags
0x1800ab924  mov     rcx, [rcx+30h]; HeapHandle
0x1800ab928  call    cs:__imp_RtlFreeHeap
0x1800ab92f  nop     dword ptr [rax+rax+00h]
0x1800ab934  mov     ebx, [rsp+108h+var_A8]
0x1800ab938  test    ebx, ebx
0x1800ab93a  jns     short loc_1800AB959
0x1800ab93c  mov     rcx, [rsp+108h+FileHandle]; Handle
0x1800ab941  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ab945  jz      short loc_1800AB959
0x1800ab947  call    cs:__imp_NtClose
0x1800ab94e  nop     dword ptr [rax+rax+00h]
0x1800ab953  or      [rsp+108h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800ab959  cmp     [rsp+108h+var_78], r14
0x1800ab961  jz      short loc_1800AB98A
0x1800ab963  mov     rcx, gs:60h
0x1800ab96c  mov     r8, [rsp+108h+var_78]; P
0x1800ab974  xor     edx, edx; Flags
0x1800ab976  mov     rcx, [rcx+30h]; HeapHandle
0x1800ab97a  call    cs:__imp_RtlFreeHeap
0x1800ab981  nop     dword ptr [rax+rax+00h]
0x1800ab986  mov     ebx, [rsp+108h+var_A8]
0x1800ab98a  mov     rax, [rsp+108h+FileHandle]
0x1800ab98f  mov     [r15], rax
0x1800ab992  mov     eax, ebx
0x1800ab994  lea     r11, [rsp+108h+var_28]
0x1800ab99c  mov     rbx, [r11+30h]
0x1800ab9a0  mov     rsi, [r11+38h]
0x1800ab9a4  mov     rsp, r11
0x1800ab9a7  pop     r15
0x1800ab9a9  pop     r14
0x1800ab9ab  pop     r13
0x1800ab9ad  pop     r12
0x1800ab9af  pop     rdi
0x1800ab9b0  retn
0x1800c6c74  push    rbp
0x1800c6c76  sub     rsp, 60h
0x1800c6c7a  mov     rbp, rdx
0x1800c6c7d  cmp     qword ptr [rbp+78h], 0
0x1800c6c82  jz      short loc_1800C6CA4
0x1800c6c84  mov     rcx, gs:60h
0x1800c6c8d  mov     r8, [rbp+78h]; P
0x1800c6c91  xor     edx, edx; Flags
0x1800c6c93  mov     rcx, [rcx+30h]; HeapHandle
0x1800c6c97  call    cs:__imp_RtlFreeHeap
0x1800c6c9e  nop     dword ptr [rax+rax+00h]
0x1800c6ca3  nop
0x1800c6ca4  test    dword ptr [rbp+60h], 80000000h
0x1800c6cab  jz      short loc_1800C6CC8
0x1800c6cad  mov     rcx, [rbp+68h]; Handle
0x1800c6cb1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c6cb5  jz      short loc_1800C6CC8
0x1800c6cb7  call    cs:__imp_NtClose
0x1800c6cbe  nop     dword ptr [rax+rax+00h]
0x1800c6cc3  or      qword ptr [rbp+68h], 0FFFFFFFFFFFFFFFFh
0x1800c6cc8  cmp     qword ptr [rbp+90h], 0
0x1800c6cd0  jz      short loc_1800C6CF5
0x1800c6cd2  mov     rcx, gs:60h
0x1800c6cdb  mov     r8, [rbp+90h]; P
0x1800c6ce2  xor     edx, edx; Flags
0x1800c6ce4  mov     rcx, [rcx+30h]; HeapHandle
0x1800c6ce8  call    cs:__imp_RtlFreeHeap
0x1800c6cef  nop     dword ptr [rax+rax+00h]
0x1800c6cf4  nop
0x1800c6cf5  mov     rcx, [rbp+128h]
0x1800c6cfc  mov     rax, [rbp+68h]
0x1800c6d00  mov     [rcx], rax
0x1800c6d03  add     rsp, 60h
0x1800c6d07  pop     rbp
0x1800c6d08  retn
```
