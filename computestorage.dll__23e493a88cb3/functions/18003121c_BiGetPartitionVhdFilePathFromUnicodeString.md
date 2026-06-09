# BiGetPartitionVhdFilePathFromUnicodeString

- ea: `0x18003121c`
- end: `0x180031514`
- name: `BiGetPartitionVhdFilePathFromUnicodeString`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800311e4`

## callees

- `0x180003bb5`
- `0x18003121c`
- `0x180031dc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180031376`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180031376`
- `ntdll!ZwDeviceIoControlFile` at `0x18003130e`
- `ntdll!ZwDeviceIoControlFile` at `0x18003130e`
- `ntdll!ZwClose` at `0x1800314f0`
- `ntdll!ZwClose` at `0x1800314f0`
- `ntdll!ZwOpenFile` at `0x180031288`
- `ntdll!ZwOpenFile` at `0x180031288`
- `ntdll!RtlFreeHeap` at `0x18003133e`
- `ntdll!RtlFreeHeap` at `0x180031449`
- `ntdll!RtlFreeHeap` at `0x180031493`
- `ntdll!RtlFreeHeap` at `0x1800314b5`
- `ntdll!RtlFreeHeap` at `0x1800314d8`
- `ntdll!RtlFreeHeap` at `0x18003133e`
- `ntdll!RtlFreeHeap` at `0x180031449`
- `ntdll!RtlFreeHeap` at `0x180031493`
- `ntdll!RtlFreeHeap` at `0x1800314b5`
- `ntdll!RtlFreeHeap` at `0x1800314d8`
- `ntdll!RtlAllocateHeap` at `0x1800312bb`
- `ntdll!RtlAllocateHeap` at `0x1800313fb`
- `ntdll!RtlAllocateHeap` at `0x1800312bb`
- `ntdll!RtlAllocateHeap` at `0x1800313fb`

## pseudocode

```c
ULONG *__fastcall BiGetPartitionVhdFilePathFromUnicodeString(struct _UNICODE_STRING *a1)
{
  char v1; // r12
  ULONG *v2; // rdi
  ULONG OutputBufferLength; // ebx
  int i; // esi
  ULONG *OutputBuffer; // rax
  NTSTATUS v6; // eax
  _WORD *v7; // r14
  wchar_t *v8; // r15
  wchar_t *v9; // r13
  wchar_t *j; // rbx
  wchar_t *v11; // rsi
  NTSTATUS v12; // eax
  __int64 v13; // rax
  size_t v14; // rbx
  __int64 v15; // rax
  wchar_t *Heap; // rax
  _WORD *v17; // rbx
  signed int v18; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  int InputBuffer; // [rsp+E0h] [rbp+67h] BYREF
  size_t Size; // [rsp+E8h] [rbp+6Fh]
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF
  void *Src; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  ObjectAttributes.ObjectName = a1;
  InputBuffer = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  v2 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    OutputBufferLength = 520;
    for ( i = 1; ; i = 2 )
    {
      OutputBuffer = (ULONG *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBufferLength);
      v2 = OutputBuffer;
      if ( !OutputBuffer )
        break;
      InputBuffer = 1;
      v6 = ZwDeviceIoControlFile(
             FileHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x2D5928u,
             &InputBuffer,
             4u,
             OutputBuffer,
             OutputBufferLength);
      if ( v6 != -1073741789 )
      {
        if ( v6 < 0 )
        {
LABEL_28:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          v2 = 0;
          break;
        }
        v7 = 0;
        Src = 0;
        v8 = 0;
        v9 = (wchar_t *)v2;
        for ( j = 0; ; j = v11 )
        {
          v11 = wcsrchr(v9, 0x5Cu);
          if ( j )
            *j = 92;
          if ( !v11 )
            break;
          *v11 = 0;
          v12 = BiTranslateSymbolicLink(v9, (PWSTR *)&Src);
          v7 = Src;
          if ( v12 >= 0 )
          {
            *v11 = 92;
            v13 = -1;
            do
              ++v13;
            while ( v7[v13] );
            v14 = (unsigned int)(2 * v13);
            v15 = -1;
            do
              ++v15;
            while ( v11[v15] );
            LODWORD(Size) = 2 * v15 + 2;
            Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v14 + Size));
            v8 = Heap;
            if ( !Heap )
            {
              v18 = -1073741801;
              goto LABEL_24;
            }
            v1 = 1;
            memcpy_0(Heap, v7, v14);
            v17 = (wchar_t *)((char *)v8 + v14);
            memcpy_0(v17, v11, (unsigned int)Size);
            if ( v9 != (wchar_t *)v2 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            v9 = v8;
            *v17 = 0;
            v11 = v17;
          }
        }
        v18 = v1 == 0 ? 0xC0000001 : 0;
LABEL_24:
        if ( v7 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        if ( v18 >= 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          v2 = (ULONG *)v8;
        }
        break;
      }
      if ( i != 1 )
        goto LABEL_28;
      OutputBufferLength = *v2;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x18003121c  push    rbp
0x18003121e  push    rbx
0x18003121f  push    rsi
0x180031220  push    rdi
0x180031221  push    r12
0x180031223  push    r13
0x180031225  push    r14
0x180031227  push    r15
0x180031229  lea     rbp, [rsp-1Fh]
0x18003122e  sub     rsp, 98h
0x180031235  xor     r12d, r12d
0x180031238  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x18003123c  xorps   xmm0, xmm0
0x18003123f  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x180031247  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003124b  mov     [rbp+57h+arg_0], r12d
0x18003124f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180031253  mov     [rbp+57h+FileHandle], r12
0x180031257  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003125b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18003125f  mov     edx, 0C0100000h; DesiredAccess
0x180031264  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003126c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180031270  mov     edi, r12d
0x180031273  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18003127b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180031280  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x180031288  call    cs:__imp_ZwOpenFile
0x18003128f  nop     dword ptr [rax+rax+00h]
0x180031294  test    eax, eax
0x180031296  js      loc_1800314E7
0x18003129c  lea     r14d, [r12+1]
0x1800312a1  mov     ebx, 208h
0x1800312a6  mov     esi, r14d
0x1800312a9  mov     rcx, gs:60h
0x1800312b2  xor     edx, edx; Flags
0x1800312b4  mov     r8d, ebx; Size
0x1800312b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800312bb  call    cs:__imp_RtlAllocateHeap
0x1800312c2  nop     dword ptr [rax+rax+00h]
0x1800312c7  mov     rdi, rax
0x1800312ca  test    rax, rax
0x1800312cd  jz      loc_1800314E7
0x1800312d3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800312d7  xor     r9d, r9d; ApcContext
0x1800312da  mov     [rsp+0D0h+OutputBufferLength], ebx; OutputBufferLength
0x1800312de  xor     r8d, r8d; ApcRoutine
0x1800312e1  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x1800312e6  xor     edx, edx; Event
0x1800312e8  mov     [rsp+0D0h+InputBufferLength], 4; InputBufferLength
0x1800312f0  lea     rax, [rbp+57h+arg_0]
0x1800312f4  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x1800312f9  lea     rax, [rbp+57h+IoStatusBlock]
0x1800312fd  mov     [rsp+0D0h+OpenOptions], 2D5928h; IoControlCode
0x180031305  mov     qword ptr [rsp+0D0h+ShareAccess], rax; IoStatusBlock
0x18003130a  mov     [rbp+57h+arg_0], r14d
0x18003130e  call    cs:__imp_ZwDeviceIoControlFile
0x180031315  nop     dword ptr [rax+rax+00h]
0x18003131a  cmp     eax, 0C0000023h
0x18003131f  jnz     short loc_180031354
0x180031321  cmp     esi, r14d
0x180031324  jnz     loc_1800314C6
0x18003132a  mov     rcx, gs:60h
0x180031333  mov     r8, rdi; P
0x180031336  mov     ebx, [rdi]
0x180031338  xor     edx, edx; Flags
0x18003133a  mov     rcx, [rcx+30h]; HeapHandle
0x18003133e  call    cs:__imp_RtlFreeHeap
0x180031345  nop     dword ptr [rax+rax+00h]
0x18003134a  mov     esi, 2
0x18003134f  jmp     loc_1800312A9
0x180031354  test    eax, eax
0x180031356  js      loc_1800314C6
0x18003135c  mov     r14, r12
0x18003135f  mov     [rbp+57h+Src], r12
0x180031363  mov     r15, r12
0x180031366  mov     r13, rdi
0x180031369  mov     rbx, r12
0x18003136c  mov     eax, 5Ch ; '\'
0x180031371  mov     rcx, r13; Str
0x180031374  mov     edx, eax; Ch
0x180031376  call    cs:__imp_wcsrchr
0x18003137d  nop     dword ptr [rax+rax+00h]
0x180031382  mov     rsi, rax
0x180031385  xor     eax, eax
0x180031387  test    rbx, rbx
0x18003138a  jz      short loc_180031391
0x18003138c  mov     word ptr [rbx], 5Ch ; '\'
0x180031391  test    rsi, rsi
0x180031394  jz      loc_18003146F
0x18003139a  lea     rdx, [rbp+57h+Src]
0x18003139e  mov     [rsi], ax
0x1800313a1  mov     rcx, r13; SourceString
0x1800313a4  call    BiTranslateSymbolicLink
0x1800313a9  mov     r14, [rbp+57h+Src]
0x1800313ad  test    eax, eax
0x1800313af  js      loc_180031460
0x1800313b5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800313b9  mov     word ptr [rsi], 5Ch ; '\'
0x1800313be  mov     rax, rcx
0x1800313c1  xor     r12d, r12d
0x1800313c4  inc     rax
0x1800313c7  cmp     [r14+rax*2], r12w
0x1800313cc  jnz     short loc_1800313C4
0x1800313ce  lea     ebx, [rax+rax]
0x1800313d1  mov     rax, rcx
0x1800313d4  inc     rax
0x1800313d7  cmp     [rsi+rax*2], r12w
0x1800313dc  jnz     short loc_1800313D4
0x1800313de  mov     rcx, gs:60h
0x1800313e7  lea     eax, ds:2[rax*2]
0x1800313ee  lea     r8d, [rbx+rax]; Size
0x1800313f2  mov     dword ptr [rbp+57h+Size], eax
0x1800313f5  xor     edx, edx; Flags
0x1800313f7  mov     rcx, [rcx+30h]; HeapHandle
0x1800313fb  call    cs:__imp_RtlAllocateHeap
0x180031402  nop     dword ptr [rax+rax+00h]
0x180031407  mov     r15, rax
0x18003140a  test    rax, rax
0x18003140d  jz      short loc_180031468
0x18003140f  mov     r8, rbx; Size
0x180031412  mov     rdx, r14; Src
0x180031415  mov     rcx, rax; void *
0x180031418  mov     r12b, 1
0x18003141b  call    memcpy_0
0x180031420  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180031424  add     rbx, r15
0x180031427  mov     rcx, rbx; void *
0x18003142a  mov     rdx, rsi; Src
0x18003142d  call    memcpy_0
0x180031432  cmp     r13, rdi
0x180031435  jz      short loc_180031455
0x180031437  mov     rcx, gs:60h
0x180031440  mov     r8, r13; P
0x180031443  xor     edx, edx; Flags
0x180031445  mov     rcx, [rcx+30h]; HeapHandle
0x180031449  call    cs:__imp_RtlFreeHeap
0x180031450  nop     dword ptr [rax+rax+00h]
0x180031455  xor     eax, eax
0x180031457  mov     r13, r15
0x18003145a  mov     [rbx], ax
0x18003145d  mov     rsi, rbx
0x180031460  mov     rbx, rsi
0x180031463  jmp     loc_18003136C
0x180031468  mov     ebx, 0C0000017h
0x18003146d  jmp     short loc_18003147C
0x18003146f  neg     r12b
0x180031472  sbb     ebx, ebx
0x180031474  not     ebx
0x180031476  and     ebx, 0C0000001h
0x18003147c  test    r14, r14
0x18003147f  jz      short loc_18003149F
0x180031481  mov     rcx, gs:60h
0x18003148a  mov     r8, r14; P
0x18003148d  xor     edx, edx; Flags
0x18003148f  mov     rcx, [rcx+30h]; HeapHandle
0x180031493  call    cs:__imp_RtlFreeHeap
0x18003149a  nop     dword ptr [rax+rax+00h]
0x18003149f  test    ebx, ebx
0x1800314a1  js      short loc_1800314E7
0x1800314a3  mov     rcx, gs:60h
0x1800314ac  mov     r8, rdi; P
0x1800314af  xor     edx, edx; Flags
0x1800314b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800314b5  call    cs:__imp_RtlFreeHeap
0x1800314bc  nop     dword ptr [rax+rax+00h]
0x1800314c1  mov     rdi, r15
0x1800314c4  jmp     short loc_1800314E7
0x1800314c6  mov     rcx, gs:60h
0x1800314cf  mov     r8, rdi; P
0x1800314d2  xor     edx, edx; Flags
0x1800314d4  mov     rcx, [rcx+30h]; HeapHandle
0x1800314d8  call    cs:__imp_RtlFreeHeap
0x1800314df  nop     dword ptr [rax+rax+00h]
0x1800314e4  mov     rdi, r12
0x1800314e7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800314eb  test    rcx, rcx
0x1800314ee  jz      short loc_1800314FC
0x1800314f0  call    cs:__imp_ZwClose
0x1800314f7  nop     dword ptr [rax+rax+00h]
0x1800314fc  mov     rax, rdi
0x1800314ff  add     rsp, 98h
0x180031506  pop     r15
0x180031508  pop     r14
0x18003150a  pop     r13
0x18003150c  pop     r12
0x18003150e  pop     rdi
0x18003150f  pop     rsi
0x180031510  pop     rbx
0x180031511  pop     rbp
0x180031512  retn
```
