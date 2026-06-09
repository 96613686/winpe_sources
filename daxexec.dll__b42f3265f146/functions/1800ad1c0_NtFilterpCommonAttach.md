# NtFilterpCommonAttach

- ea: `0x1800ad1c0`
- end: `0x1800ad508`
- name: `NtFilterpCommonAttach`
- size: `840`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, void *FileHandle, __int64, size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800ad510`

## callees

- `0x18000b126`
- `0x1800ad1c0`
- `0x1800ae23c`
- `0x1800ae2f8`
- `0x1800bec44`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ad22d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ad22d`
- `ntdll!RtlAllocateHeap` at `0x1800ad3c2`
- `ntdll!RtlAllocateHeap` at `0x1800ad3c2`
- `ntdll!NtClose` at `0x1800ad4ab`
- `ntdll!NtClose` at `0x1800c8117`
- `ntdll!NtClose` at `0x1800ad4ab`
- `ntdll!NtClose` at `0x1800c8117`
- `ntdll!RtlFreeHeap` at `0x1800ad4ce`
- `ntdll!RtlFreeHeap` at `0x1800ad4f5`
- `ntdll!RtlFreeHeap` at `0x1800c813c`
- `ntdll!RtlFreeHeap` at `0x1800c8163`
- `ntdll!RtlFreeHeap` at `0x1800ad4ce`
- `ntdll!RtlFreeHeap` at `0x1800ad4f5`
- `ntdll!RtlFreeHeap` at `0x1800c813c`
- `ntdll!RtlFreeHeap` at `0x1800c8163`
- `ntdll!NtCreateFile` at `0x1800ad2ee`
- `ntdll!NtCreateFile` at `0x1800ad2ee`

## pseudocode

```c
__int64 __fastcall NtFilterpCommonAttach(
        _WORD *Src,
        _WORD *a2,
        __int64 a3,
        _WORD *a4,
        __int64 FileHandle,
        __int64 a6,
        size_t Size)
{
  unsigned __int16 v10; // si
  _WORD *v11; // rbx
  __int64 v12; // rdi
  unsigned int v13; // edi
  unsigned int v14; // eax
  __int64 v16; // r14
  unsigned __int16 v17; // r14
  unsigned __int16 v18; // di
  __int64 v19; // rsi
  _WORD *Heap; // rax
  __int64 v21; // rcx
  unsigned __int16 v22; // di
  __int64 v23; // [rsp+0h] [rbp-F8h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-D8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-D0h]
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-98h] BYREF
  _WORD *v27; // [rsp+70h] [rbp-88h]
  size_t v28; // [rsp+78h] [rbp-80h]
  size_t v29; // [rsp+80h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-70h] BYREF
  __int64 *v31; // [rsp+B8h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-38h] BYREF
  unsigned int v33; // [rsp+110h] [rbp+18h]

  v31 = &v23;
  v10 = 0;
  v11 = 0;
  v27 = 0;
  v12 = -1;
  FileHandle = -1;
  NtPathName = 0;
  if ( Src && a2 )
  {
    if ( RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &NtPathName, 0, 0) )
    {
      *(&ObjectAttributes.Length + 1) = 0;
      memset(&ObjectAttributes.Attributes + 1, 0, 20);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtPathName;
      IoStatusBlock = 0;
      v14 = NtCreateFile((PHANDLE)&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
      if ( FileHandle == -1 )
      {
        v33 = FilterHResultFromNtStatus(v14);
        local_unwind_0(v31, &loc_1800AD327);
        return v33;
      }
      v16 = -1;
      do
        ++v16;
      while ( Src[v16] );
      v17 = 2 * v16;
      do
        ++v12;
      while ( a2[v12] );
      v18 = 2 * v12;
      if ( a4 )
      {
        v19 = -1;
        do
          ++v19;
        while ( a4[v19] );
        v10 = 2 * v19;
      }
      Size = v17;
      v28 = v18;
      v29 = v10;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v17 + 20 + v18 + (unsigned int)v10);
      v11 = Heap;
      v27 = Heap;
      if ( Heap )
      {
        *Heap = v17;
        Heap[1] = 20;
        memcpy_0(Heap + 10, Src, Size);
        v11[2] = v18;
        v21 = (unsigned __int16)(v17 + 20);
        v11[3] = v21;
        memcpy_0((char *)v11 + v21, a2, v28);
        *((_DWORD *)v11 + 2) = 1;
        v11[6] = v10;
        if ( a4 )
        {
          v22 = v17 + v18 + 20;
          v11[7] = v22;
          memcpy_0((char *)v11 + v22, a4, v29);
        }
        else
        {
          v11[7] = 0;
        }
        *((_DWORD *)v11 + 4) = 0;
        v13 = NtFilterpDeviceIoControl((HANDLE)FileHandle, 0x88010u, (int)AllocationSize, FileAttributes, (__int64)&a6);
      }
      else
      {
        v13 = -2147024882;
      }
    }
    else
    {
      v13 = -2147024893;
    }
  }
  else
  {
    v13 = -2147024809;
  }
  if ( FileHandle != -1 )
    NtClose((HANDLE)FileHandle);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  return v13;
}

```

## disassembly

```asm
0x1800ad1c0  mov     rax, rsp
0x1800ad1c3  mov     [rax+8], rbx
0x1800ad1c7  mov     [rax+10h], rsi
0x1800ad1cb  mov     [rax+18h], r8d
0x1800ad1cf  push    rdi
0x1800ad1d0  push    r12
0x1800ad1d2  push    r13
0x1800ad1d4  push    r14
0x1800ad1d6  push    r15
0x1800ad1d8  sub     rsp, 0D0h
0x1800ad1df  mov     [rsp+0F8h+var_40], rsp
0x1800ad1e7  mov     r15, r9
0x1800ad1ea  mov     r13, rdx
0x1800ad1ed  mov     r12, rcx
0x1800ad1f0  xor     esi, esi
0x1800ad1f2  mov     ebx, esi
0x1800ad1f4  mov     [rsp+0F8h+var_88], rbx
0x1800ad1f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ad1fd  mov     [rax+28h], rdi
0x1800ad201  xorps   xmm0, xmm0
0x1800ad204  movups  xmmword ptr [rsp+0F8h+NtPathName.Length], xmm0
0x1800ad209  test    rcx, rcx
0x1800ad20c  jz      loc_1800AD498
0x1800ad212  test    rdx, rdx
0x1800ad215  jz      loc_1800AD498
0x1800ad21b  xor     r9d, r9d; DirectoryInfo
0x1800ad21e  xor     r8d, r8d; NtFileNamePart
0x1800ad221  lea     rdx, [rsp+0F8h+NtPathName]; NtPathName
0x1800ad226  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1800ad22d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ad234  nop     dword ptr [rax+rax+00h]
0x1800ad239  test    al, al
0x1800ad23b  jnz     short loc_1800AD247
0x1800ad23d  mov     edi, 80070003h
0x1800ad242  jmp     loc_1800AD49D
0x1800ad247  xor     eax, eax
0x1800ad249  mov     dword ptr [rsp+0F8h+ObjectAttributes+4], eax
0x1800ad250  xorps   xmm0, xmm0
0x1800ad253  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x1800ad25b  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x1800ad263  movups  xmmword ptr [rsp+0F8h+ObjectAttributes+1Ch], xmm0
0x1800ad26b  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x1800ad276  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], rsi
0x1800ad27e  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad289  lea     rax, [rsp+0F8h+NtPathName]
0x1800ad28e  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x1800ad296  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad29f  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x1800ad2a7  mov     [rsp+0F8h+EaLength], esi; EaLength
0x1800ad2ab  mov     [rsp+0F8h+EaBuffer], rsi; EaBuffer
0x1800ad2b0  mov     [rsp+0F8h+CreateOptions], esi; CreateOptions
0x1800ad2b4  mov     [rsp+0F8h+CreateDisposition], 1; CreateDisposition
0x1800ad2bc  mov     [rsp+0F8h+ShareAccess], 3; ShareAccess
0x1800ad2c4  mov     [rsp+0F8h+FileAttributes], 80h; int
0x1800ad2cc  mov     [rsp+0F8h+AllocationSize], rsi; int
0x1800ad2d1  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x1800ad2d9  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x1800ad2e1  mov     edx, 12019Fh; DesiredAccess
0x1800ad2e6  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x1800ad2ee  call    cs:__imp_NtCreateFile
0x1800ad2f5  nop     dword ptr [rax+rax+00h]
0x1800ad2fa  cmp     [rsp+0F8h+FileHandle], rdi
0x1800ad302  jnz     short loc_1800AD34C
0x1800ad304  mov     ecx, eax
0x1800ad306  call    FilterHResultFromNtStatus
0x1800ad30b  mov     [rsp+0F8h+arg_10], eax
0x1800ad312  lea     rdx, loc_1800AD327
0x1800ad319  mov     rcx, [rsp+0F8h+var_40]
0x1800ad321  call    _local_unwind_0
0x1800ad326  nop
0x1800ad327  mov     eax, [rsp+0F8h+arg_10]
0x1800ad32e  lea     r11, [rsp+0F8h+var_28]
0x1800ad336  mov     rbx, [r11+30h]
0x1800ad33a  mov     rsi, [r11+38h]
0x1800ad33e  mov     rsp, r11
0x1800ad341  pop     r15
0x1800ad343  pop     r14
0x1800ad345  pop     r13
0x1800ad347  pop     r12
0x1800ad349  pop     rdi
0x1800ad34a  retn
0x1800ad34c  mov     r14, rdi
0x1800ad34f  inc     r14
0x1800ad352  cmp     [r12+r14*2], si
0x1800ad357  jnz     short loc_1800AD34F
0x1800ad359  add     r14w, r14w
0x1800ad35d  inc     rdi
0x1800ad360  cmp     [r13+rdi*2+0], si
0x1800ad366  jnz     short loc_1800AD35D
0x1800ad368  add     di, di
0x1800ad36b  test    r15, r15
0x1800ad36e  jz      short loc_1800AD383
0x1800ad370  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ad374  xor     eax, eax
0x1800ad376  inc     rsi
0x1800ad379  cmp     [r15+rsi*2], ax
0x1800ad37e  jnz     short loc_1800AD376
0x1800ad380  add     si, si
0x1800ad383  movzx   ecx, r14w
0x1800ad387  mov     [rsp+0F8h+Size], rcx
0x1800ad38f  movzx   edx, di
0x1800ad392  mov     [rsp+0F8h+var_80], rdx
0x1800ad397  movzx   eax, si
0x1800ad39a  mov     [rsp+0F8h+var_78], rax
0x1800ad3a2  add     eax, edx
0x1800ad3a4  add     ecx, 14h
0x1800ad3a7  add     eax, ecx
0x1800ad3a9  mov     [rsp+0F8h+arg_10], eax
0x1800ad3b0  mov     r8d, eax; Size
0x1800ad3b3  mov     rcx, gs:60h
0x1800ad3bc  xor     edx, edx; Flags
0x1800ad3be  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad3c2  call    cs:__imp_RtlAllocateHeap
0x1800ad3c9  nop     dword ptr [rax+rax+00h]
0x1800ad3ce  mov     rbx, rax
0x1800ad3d1  mov     [rsp+0F8h+var_88], rax
0x1800ad3d6  test    rax, rax
0x1800ad3d9  jnz     short loc_1800AD3E7
0x1800ad3db  mov     edi, 8007000Eh
0x1800ad3e0  xor     esi, esi
0x1800ad3e2  jmp     loc_1800AD49D
0x1800ad3e7  mov     [rax], r14w
0x1800ad3eb  mov     eax, 14h
0x1800ad3f0  mov     [rbx+2], ax
0x1800ad3f4  lea     rcx, [rbx+14h]; void *
0x1800ad3f8  mov     r8, [rsp+0F8h+Size]; Size
0x1800ad400  mov     rdx, r12; Src
0x1800ad403  call    memcpy_0
0x1800ad408  mov     [rbx+4], di
0x1800ad40c  mov     r12d, 14h
0x1800ad412  lea     eax, [r12+r14]
0x1800ad416  movzx   ecx, ax
0x1800ad419  mov     [rbx+6], cx
0x1800ad41d  add     rcx, rbx; void *
0x1800ad420  mov     r8, [rsp+0F8h+var_80]; Size
0x1800ad425  mov     rdx, r13; Src
0x1800ad428  call    memcpy_0
0x1800ad42d  mov     dword ptr [rbx+8], 1
0x1800ad434  mov     [rbx+0Ch], si
0x1800ad438  xor     esi, esi
0x1800ad43a  test    r15, r15
0x1800ad43d  jz      short loc_1800AD463
0x1800ad43f  add     di, r14w
0x1800ad443  add     di, r12w
0x1800ad447  movzx   ecx, di
0x1800ad44a  mov     [rbx+0Eh], cx
0x1800ad44e  add     rcx, rbx; void *
0x1800ad451  mov     r8, [rsp+0F8h+var_78]; Size
0x1800ad459  mov     rdx, r15; Src
0x1800ad45c  call    memcpy_0
0x1800ad461  jmp     short loc_1800AD467
0x1800ad463  mov     [rbx+0Eh], si
0x1800ad467  mov     [rbx+10h], esi
0x1800ad46a  lea     rax, [rsp+0F8h+arg_28]
0x1800ad472  mov     qword ptr [rsp+0F8h+ShareAccess], rax; __int64
0x1800ad477  mov     r9d, [rsp+0F8h+arg_10]
0x1800ad47f  mov     r8, rbx
0x1800ad482  mov     edx, 88010h; FsControlCode
0x1800ad487  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x1800ad48f  call    NtFilterpDeviceIoControl
0x1800ad494  mov     edi, eax
0x1800ad496  jmp     short loc_1800AD49D
0x1800ad498  mov     edi, 80070057h
0x1800ad49d  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x1800ad4a5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ad4a9  jz      short loc_1800AD4B7
0x1800ad4ab  call    cs:__imp_NtClose
0x1800ad4b2  nop     dword ptr [rax+rax+00h]
0x1800ad4b7  test    rbx, rbx
0x1800ad4ba  jz      short loc_1800AD4DA
0x1800ad4bc  mov     rcx, gs:60h
0x1800ad4c5  mov     r8, rbx; P
0x1800ad4c8  xor     edx, edx; Flags
0x1800ad4ca  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad4ce  call    cs:__imp_RtlFreeHeap
0x1800ad4d5  nop     dword ptr [rax+rax+00h]
0x1800ad4da  cmp     [rsp+0F8h+NtPathName.Buffer], rsi
0x1800ad4df  jz      short loc_1800AD501
0x1800ad4e1  mov     rcx, gs:60h
0x1800ad4ea  mov     r8, [rsp+0F8h+NtPathName.Buffer]; P
0x1800ad4ef  xor     edx, edx; Flags
0x1800ad4f1  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad4f5  call    cs:__imp_RtlFreeHeap
0x1800ad4fc  nop     dword ptr [rax+rax+00h]
0x1800ad501  mov     eax, edi
0x1800ad503  jmp     loc_1800AD32E
0x1800c8101  push    rbp
0x1800c8103  sub     rsp, 60h
0x1800c8107  mov     rbp, rdx
0x1800c810a  mov     rcx, [rbp+120h]; Handle
0x1800c8111  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c8115  jz      short loc_1800C8124
0x1800c8117  call    cs:__imp_NtClose
0x1800c811e  nop     dword ptr [rax+rax+00h]
0x1800c8123  nop
0x1800c8124  mov     r8, [rbp+70h]; P
0x1800c8128  test    r8, r8
0x1800c812b  jz      short loc_1800C8149
0x1800c812d  mov     rcx, gs:60h
0x1800c8136  xor     edx, edx; Flags
0x1800c8138  mov     rcx, [rcx+30h]; HeapHandle
0x1800c813c  call    cs:__imp_RtlFreeHeap
0x1800c8143  nop     dword ptr [rax+rax+00h]
0x1800c8148  nop
0x1800c8149  cmp     qword ptr [rbp+68h], 0
0x1800c814e  jz      short loc_1800C8170
0x1800c8150  mov     rcx, gs:60h
0x1800c8159  mov     r8, [rbp+68h]; P
0x1800c815d  xor     edx, edx; Flags
0x1800c815f  mov     rcx, [rcx+30h]; HeapHandle
0x1800c8163  call    cs:__imp_RtlFreeHeap
0x1800c816a  nop     dword ptr [rax+rax+00h]
0x1800c816f  nop
0x1800c8170  add     rsp, 60h
0x1800c8174  pop     rbp
0x1800c8175  retn
```
