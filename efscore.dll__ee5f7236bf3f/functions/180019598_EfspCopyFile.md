# EfspCopyFile

- ea: `0x180019598`
- end: `0x1800199a2`
- name: `EfspCopyFile`
- size: `1034`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a01c`

## callees

- `0x180005045`
- `0x18000505d`
- `0x1800102f0`
- `0x180010bf0`
- `0x180017510`
- `0x180019598`
- `0x1800199a8`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019960`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019895`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019895`
- `ntdll!NtSetInformationFile` at `0x1800196d9`
- `ntdll!NtSetInformationFile` at `0x1800196d9`
- `ntdll!NtFsControlFile` at `0x18001982c`
- `ntdll!NtFsControlFile` at `0x18001982c`
- `ntdll!NtCreateFile` at `0x1800197de`
- `ntdll!NtCreateFile` at `0x1800197de`
- `ntdll!RtlNtStatusToDosError` at `0x18001997d`
- `ntdll!RtlNtStatusToDosError` at `0x18001997d`

## pseudocode

```c
__int64 __fastcall EfspCopyFile(unsigned int *a1, void *a2, _QWORD *a3)
{
  unsigned __int64 v4; // rcx
  char *v5; // rsi
  __int64 v6; // rax
  ULONG v7; // r13d
  __int64 i; // r14
  struct _UNICODE_STRING *v9; // rbx
  HANDLE v10; // r10
  __int64 v11; // rcx
  void **v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rax
  NTSTATUS v15; // eax
  NTSTATUS v16; // edi
  __int64 v17; // rax
  bool v18; // zf
  union _LARGE_INTEGER *v19; // rcx
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  DWORD v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v26; // [rsp+60h] [rbp-29h]
  __int64 v27; // [rsp+68h] [rbp-21h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  __int64 FileInformation; // [rsp+F0h] [rbp+67h] BYREF
  HANDLE FileHandle; // [rsp+F8h] [rbp+6Fh]
  _QWORD *v32; // [rsp+100h] [rbp+77h]
  DWORD BytesReturned; // [rsp+108h] [rbp+7Fh] BYREF

  v32 = a3;
  FileHandle = a2;
  v4 = 8LL * *a1;
  IoStatusBlock = 0;
  v5 = (char *)wil::details::heap_allocator::allocate(v4);
  v6 = *a1;
  if ( v5 )
  {
    v7 = 0;
    memset_0(v5, 0, 8 * v6);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *a1 )
      {
LABEL_32:
        *v32 = v5;
        return v7;
      }
      v9 = (struct _UNICODE_STRING *)(*((_QWORD *)a1 + 1) + 16LL * (unsigned int)i);
      if ( v9->Length == 14 && !memcmp_0(v9->Buffer, L"::$DATA", v9->Length) )
      {
        v10 = FileHandle;
        v11 = 8 * i;
        v12 = (void **)&v5[8 * i];
        v27 = 8 * i;
        *v12 = FileHandle;
        v13 = *((_QWORD *)a1 + 2);
        v14 = 24 * i;
        v26 = 24 * i;
        if ( (*(_DWORD *)(24 * i + v13) & 0x200) != 0 )
        {
          v16 = 0;
        }
        else
        {
          FileInformation = 0;
          FileInformation = *(_QWORD *)(v14 + v13 + 8);
          v15 = NtSetInformationFile(v10, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation);
          v16 = v15;
          if ( v15 >= 0 )
            goto LABEL_17;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v15, 10, 8);
          v14 = 24 * i;
          v11 = 8 * i;
        }
        v26 = v14;
        v27 = v11;
        if ( v16 < 0 )
          goto LABEL_24;
      }
      else
      {
        v17 = *((_QWORD *)a1 + 2);
        v26 = 24 * i;
        memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
        v18 = (*(_DWORD *)(24 * i + v17) & 0x200) == 0;
        v19 = (union _LARGE_INTEGER *)(24 * i + 8 + v17);
        ObjectAttributes.ObjectName = v9;
        if ( !v18 )
          v19 = 0;
        ObjectAttributes.RootDirectory = FileHandle;
        v12 = (void **)&v5[8 * i];
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v27 = 8 * i;
        v20 = NtCreateFile(v12, 0xC0110000, &ObjectAttributes, &IoStatusBlock, v19, 0, 4u, 2u, 0x200060u, 0, 0);
        v16 = v20;
        if ( v20 < 0 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v20, 10, 81);
          *v12 = 0;
LABEL_24:
          if ( !*v12 )
            LODWORD(i) = i - 1;
LABEL_26:
          v23 = 0;
          do
          {
            v24 = *(_QWORD *)&v5[8 * v23];
            if ( v24 )
            {
              MarkFileForDelete(v24);
              CloseHandle(*(HANDLE *)&v5[8 * v23]);
            }
            v23 = (unsigned int)(v23 + 1);
          }
          while ( (unsigned int)v23 <= (unsigned int)i );
          EfsFreeHeap(v5);
          v5 = 0;
          if ( v16 < 0 )
            v7 = RtlNtStatusToDosError(v16);
          goto LABEL_32;
        }
        v21 = NtFsControlFile(*v12, 0, 0, 0, &IoStatusBlock, 0x90194u, 0, 0, 0, 0);
        v16 = v21;
        if ( v21 < 0 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 10, 107);
          goto LABEL_24;
        }
      }
LABEL_17:
      BytesReturned = 0;
      LOWORD(FileInformation) = (*(_DWORD *)(*((_QWORD *)a1 + 2) + v26) & 0x800) != 0;
      DeviceIoControl(*v12, 0x9C040u, &FileInformation, 2u, 0, 0, &BytesReturned, 0);
      v22 = EfspCopyStream(*v12, *(HANDLE *)(*((_QWORD *)a1 + 3) + v27), v26 + *((_QWORD *)a1 + 2));
      v7 = v22;
      if ( v22 )
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v22, 10, 140);
      if ( v16 < 0 )
        goto LABEL_24;
      if ( v7 )
        goto LABEL_26;
    }
  }
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 8 * v6, 10, 225);
  v7 = 8;
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 8, 10, 226);
  return v7;
}

```

## disassembly

```asm
0x180019598  mov     [rsp-8+arg_10], r8
0x18001959d  mov     [rsp-8+FileHandle], rdx
0x1800195a2  push    rbp
0x1800195a3  push    rbx
0x1800195a4  push    rsi
0x1800195a5  push    rdi
0x1800195a6  push    r13
0x1800195a8  push    r14
0x1800195aa  push    r15
0x1800195ac  lea     rbp, [rsp-27h]
0x1800195b1  sub     rsp, 0B0h
0x1800195b8  mov     r15, rcx
0x1800195bb  xorps   xmm0, xmm0
0x1800195be  mov     ecx, [rcx]
0x1800195c0  shl     rcx, 3; unsigned __int64
0x1800195c4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800195c8  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1800195cd  mov     rsi, rax
0x1800195d0  mov     eax, [r15]
0x1800195d3  test    rsi, rsi
0x1800195d6  jnz     short loc_18001962A
0x1800195d8  mov     rcx, cs:g_hPublisher
0x1800195df  lea     r8d, ds:0[rax*8]
0x1800195e7  lea     r9d, [rsi+0Ah]
0x1800195eb  mov     [rsp+0E0h+FileInformationClass], 9E1h
0x1800195f3  lea     rdx, EFS_ERROR_MEMORY
0x1800195fa  call    fnEfsLogTrace1
0x1800195ff  mov     rcx, cs:g_hPublisher
0x180019606  lea     r13d, [rsi+8]
0x18001960a  mov     r8d, r13d
0x18001960d  mov     [rsp+0E0h+FileInformationClass], 9E2h
0x180019615  lea     r9d, [rsi+0Ah]
0x180019619  lea     rdx, EFS_TRACE_ERROR
0x180019620  call    fnEfsLogTrace1
0x180019625  jmp     loc_18001998D
0x18001962a  mov     r8, rax
0x18001962d  xor     edx, edx; Val
0x18001962f  shl     r8, 3; Size
0x180019633  mov     rcx, rsi; void *
0x180019636  xor     r13d, r13d
0x180019639  call    memset_0
0x18001963e  xor     r14d, r14d
0x180019641  cmp     r14d, [r15]
0x180019644  jnb     loc_180019986
0x18001964a  mov     ebx, r14d
0x18001964d  mov     eax, 0Eh
0x180019652  shl     rbx, 4
0x180019656  add     rbx, [r15+8]
0x18001965a  cmp     ax, [rbx]
0x18001965d  jnz     loc_18001972E
0x180019663  movzx   r8d, word ptr [rbx]; Size
0x180019667  lea     rdx, SourceString; "::$DATA"
0x18001966e  mov     rcx, [rbx+8]; Buf1
0x180019672  call    memcmp_0
0x180019677  test    eax, eax
0x180019679  jnz     loc_18001972E
0x18001967f  mov     r10, [rbp+57h+FileHandle]
0x180019683  lea     rcx, ds:0[r14*8]
0x18001968b  lea     rbx, [rsi+rcx]
0x18001968f  mov     [rbp+57h+var_78], rcx
0x180019693  mov     [rbx], r10
0x180019696  lea     rax, [r14+r14*2]
0x18001969a  mov     rdx, [r15+10h]
0x18001969e  shl     rax, 3
0x1800196a2  mov     [rbp+57h+var_80], rax
0x1800196a6  test    dword ptr [rax+rdx], 200h
0x1800196ad  jnz     short loc_180019717
0x1800196af  mov     [rbp+57h+FileInformation], 0
0x1800196b7  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800196bb  mov     rax, [rax+rdx+8]
0x1800196c0  mov     r9d, 8; Length
0x1800196c6  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800196ca  mov     [rbp+57h+FileInformation], rax
0x1800196ce  mov     rcx, r10; FileHandle
0x1800196d1  mov     [rsp+0E0h+FileInformationClass], 14h; FileInformationClass
0x1800196d9  call    cs:__imp_NtSetInformationFile
0x1800196df  mov     edi, eax
0x1800196e1  test    eax, eax
0x1800196e3  jns     loc_18001983C
0x1800196e9  mov     rcx, cs:g_hPublisher
0x1800196f0  lea     rdx, EFS_API_ERROR
0x1800196f7  mov     r9d, 0Ah
0x1800196fd  mov     [rsp+0E0h+FileInformationClass], 0A08h
0x180019705  mov     r8d, eax
0x180019708  call    fnEfsLogTrace1
0x18001970d  mov     rax, [rbp+57h+var_80]
0x180019711  mov     rcx, [rbp+57h+var_78]
0x180019715  jmp     short loc_180019719
0x180019717  xor     edi, edi
0x180019719  mov     [rbp+57h+var_80], rax
0x18001971d  mov     [rbp+57h+var_78], rcx
0x180019721  test    edi, edi
0x180019723  js      loc_180019943
0x180019729  jmp     loc_18001983C
0x18001972e  mov     [rsp+0E0h+EaLength], 0; EaLength
0x180019736  lea     rax, [r14+r14*2]
0x18001973a  lea     rcx, ds:0[rax*8]
0x180019742  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x18001974b  mov     rax, [r15+10h]
0x18001974f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180019753  xorps   xmm0, xmm0
0x180019756  mov     [rbp+57h+var_80], rcx
0x18001975a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001975e  mov     [rsp+0E0h+CreateOptions], 200060h; CreateOptions
0x180019766  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001976a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001976e  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x180019776  mov     edx, 0C0110000h; DesiredAccess
0x18001977b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001977f  test    dword ptr [rcx+rax], 200h
0x180019786  lea     rcx, [rcx+8]
0x18001978a  lea     rcx, [rcx+rax]
0x18001978e  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x180019792  mov     eax, 0
0x180019797  mov     [rsp+0E0h+ShareAccess], 4; ShareAccess
0x18001979f  cmovnz  rcx, rax
0x1800197a3  mov     [rsp+0E0h+FileAttributes], 0; FileAttributes
0x1800197ab  mov     rax, [rbp+57h+FileHandle]
0x1800197af  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800197b3  lea     rax, ds:0[r14*8]
0x1800197bb  lea     rbx, [rax+rsi]
0x1800197bf  mov     qword ptr [rsp+0E0h+FileInformationClass], rcx; AllocationSize
0x1800197c4  mov     rcx, rbx; FileHandle
0x1800197c7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800197ce  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800197d5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800197da  mov     [rbp+57h+var_78], rax
0x1800197de  call    cs:__imp_NtCreateFile
0x1800197e4  mov     edi, eax
0x1800197e6  test    eax, eax
0x1800197e8  js      loc_180019918
0x1800197ee  mov     rcx, [rbx]; FileHandle
0x1800197f1  lea     rax, [rbp+57h+IoStatusBlock]
0x1800197f5  mov     dword ptr [rsp+0E0h+EaBuffer], 0; OutputBufferLength
0x1800197fd  xor     r9d, r9d; ApcContext
0x180019800  mov     qword ptr [rsp+0E0h+CreateOptions], 0; OutputBuffer
0x180019809  xor     r8d, r8d; ApcRoutine
0x18001980c  mov     [rsp+0E0h+CreateDisposition], 0; InputBufferLength
0x180019814  xor     edx, edx; Event
0x180019816  mov     qword ptr [rsp+0E0h+ShareAccess], 0; InputBuffer
0x18001981f  mov     [rsp+0E0h+FileAttributes], 90194h; FsControlCode
0x180019827  mov     qword ptr [rsp+0E0h+FileInformationClass], rax; IoStatusBlock
0x18001982c  call    cs:__imp_NtFsControlFile
0x180019832  mov     edi, eax
0x180019834  test    eax, eax
0x180019836  js      loc_1800198F2
0x18001983c  mov     r13, [rbp+57h+var_80]
0x180019840  xor     eax, eax
0x180019842  mov     word ptr [rbp+57h+FileInformation], ax
0x180019846  mov     [rbp+57h+BytesReturned], eax
0x180019849  mov     rax, [r15+10h]
0x18001984d  test    dword ptr [rax+r13], 800h
0x180019855  jz      short loc_180019860
0x180019857  mov     eax, 1
0x18001985c  mov     word ptr [rbp+57h+FileInformation], ax
0x180019860  mov     rcx, [rbx]; hDevice
0x180019863  lea     rax, [rbp+57h+BytesReturned]
0x180019867  mov     qword ptr [rsp+0E0h+CreateDisposition], 0; lpOverlapped
0x180019870  lea     r8, [rbp+57h+FileInformation]; lpInBuffer
0x180019874  mov     qword ptr [rsp+0E0h+ShareAccess], rax; lpBytesReturned
0x180019879  mov     r9d, 2; nInBufferSize
0x18001987f  mov     [rsp+0E0h+FileAttributes], 0; nOutBufferSize
0x180019887  mov     edx, 9C040h; dwIoControlCode
0x18001988c  mov     qword ptr [rsp+0E0h+FileInformationClass], 0; lpOutBuffer
0x180019895  call    cs:__imp_DeviceIoControl
0x18001989b  mov     rdx, [r15+18h]
0x18001989f  mov     rax, [rbp+57h+var_78]
0x1800198a3  mov     r8, [r15+10h]
0x1800198a7  mov     rcx, [rbx]; hFile
0x1800198aa  add     r8, r13
0x1800198ad  mov     rdx, [rdx+rax]; HANDLE
0x1800198b1  call    EfspCopyStream
0x1800198b6  mov     r13d, eax
0x1800198b9  test    eax, eax
0x1800198bb  jz      short loc_1800198E1
0x1800198bd  mov     rcx, cs:g_hPublisher
0x1800198c4  lea     rdx, EFS_API_ERROR
0x1800198cb  mov     r9d, 0Ah
0x1800198d1  mov     [rsp+0E0h+FileInformationClass], 0A8Ch
0x1800198d9  mov     r8d, eax
0x1800198dc  call    fnEfsLogTrace1
0x1800198e1  test    edi, edi
0x1800198e3  js      short loc_180019943
0x1800198e5  test    r13d, r13d
0x1800198e8  jnz     short loc_18001994C
0x1800198ea  inc     r14d
0x1800198ed  jmp     loc_180019641
0x1800198f2  mov     rcx, cs:g_hPublisher
0x1800198f9  lea     rdx, EFS_API_ERROR
0x180019900  mov     r9d, 0Ah
0x180019906  mov     [rsp+0E0h+FileInformationClass], 0A6Bh
0x18001990e  mov     r8d, eax
0x180019911  call    fnEfsLogTrace1
0x180019916  jmp     short loc_180019943
0x180019918  mov     rcx, cs:g_hPublisher
0x18001991f  lea     rdx, EFS_API_ERROR
0x180019926  mov     r9d, 0Ah
0x18001992c  mov     [rsp+0E0h+FileInformationClass], 0A51h
0x180019934  mov     r8d, eax
0x180019937  call    fnEfsLogTrace1
0x18001993c  mov     qword ptr [rbx], 0
0x180019943  cmp     qword ptr [rbx], 0
0x180019947  jnz     short loc_18001994C
0x180019949  dec     r14d
0x18001994c  xor     ebx, ebx
0x18001994e  mov     rcx, [rsi+rbx*8]
0x180019952  test    rcx, rcx
0x180019955  jz      short loc_180019966
0x180019957  call    MarkFileForDelete
0x18001995c  mov     rcx, [rsi+rbx*8]; hObject
0x180019960  call    cs:__imp_CloseHandle
0x180019966  inc     ebx
0x180019968  cmp     ebx, r14d
0x18001996b  jbe     short loc_18001994E
0x18001996d  mov     rcx, rsi; lpMem
0x180019970  call    EfsFreeHeap
0x180019975  xor     esi, esi
0x180019977  test    edi, edi
0x180019979  jns     short loc_180019986
0x18001997b  mov     ecx, edi; Status
0x18001997d  call    cs:__imp_RtlNtStatusToDosError
0x180019983  mov     r13d, eax
0x180019986  mov     rax, [rbp+57h+arg_10]
0x18001998a  mov     [rax], rsi
0x18001998d  mov     eax, r13d
0x180019990  add     rsp, 0B0h
0x180019997  pop     r15
0x180019999  pop     r14
0x18001999b  pop     r13
0x18001999d  pop     rdi
0x18001999e  pop     rsi
0x18001999f  pop     rbx
0x1800199a0  pop     rbp
0x1800199a1  retn
```
