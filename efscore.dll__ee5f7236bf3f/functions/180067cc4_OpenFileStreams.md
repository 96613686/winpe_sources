# OpenFileStreams

- ea: `0x180067cc4`
- end: `0x180068272`
- name: `OpenFileStreams`
- size: `1454`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK DesiredAccess, int, ULONG, __int64, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b61c`
- `0x18001c22c`
- `0x180023984`
- `0x1800640d4`

## callees

- `0x180005045`
- `0x18000505d`
- `0x1800102f0`
- `0x180010bf0`
- `0x180063698`
- `0x180066828`
- `0x1800670c4`
- `0x180067cc4`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `ntdll!NtClose` at `0x180068056`
- `ntdll!NtClose` at `0x180068205`
- `ntdll!NtClose` at `0x180068056`
- `ntdll!NtClose` at `0x180068205`
- `ntdll!NtFlushBuffersFile` at `0x180067fe9`
- `ntdll!NtFlushBuffersFile` at `0x180067fe9`
- `ntdll!NtQueryInformationFile` at `0x18006801e`
- `ntdll!NtQueryInformationFile` at `0x18006801e`
- `ntdll!NtCreateFile` at `0x180067fc1`
- `ntdll!NtCreateFile` at `0x18006809e`
- `ntdll!NtCreateFile` at `0x180067fc1`
- `ntdll!NtCreateFile` at `0x18006809e`

## pseudocode

```c
__int64 __fastcall OpenFileStreams(
        void *a1,
        ULONG a2,
        int a3,
        unsigned int *a4,
        ACCESS_MASK DesiredAccess,
        int a6,
        ULONG CreateOptions,
        struct _FILE_FS_SIZE_INFORMATION *a8,
        __int64 a9)
{
  unsigned int v9; // r14d
  unsigned int *v10; // r13
  unsigned int v11; // r12d
  unsigned int *v12; // rbx
  void *v13; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // rdi
  char *v16; // r15
  unsigned int v17; // eax
  __int64 v18; // rcx
  PHANDLE v19; // r8
  struct _UNICODE_STRING *v20; // rcx
  __int64 v21; // rdx
  PWSTR Buffer; // rax
  NTSTATUS v23; // eax
  unsigned int v24; // esi
  NTSTATUS v25; // eax
  void *v26; // rcx
  NTSTATUS v27; // eax
  int v28; // eax
  NTSTATUS v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rax
  __int64 i; // rsi
  void *v33; // rcx
  unsigned int v35; // [rsp+60h] [rbp-A0h]
  int v37; // [rsp+68h] [rbp-98h]
  LPVOID lpMem[2]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v40[2]; // [rsp+80h] [rbp-80h]
  PHANDLE FileHandle; // [rsp+90h] [rbp-70h]
  void *v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILE_FS_SIZE_INFORMATION *v45; // [rsp+B8h] [rbp-48h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD FileInformation[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v49; // [rsp+118h] [rbp+18h]

  v42 = a1;
  v9 = 0;
  v45 = a8;
  v10 = a4;
  v46 = a9;
  v49 = 0;
  *(_DWORD *)a9 = 0;
  *(_QWORD *)(a9 + 24) = 0;
  *(_QWORD *)(a9 + 8) = 0;
  *(_QWORD *)(a9 + 16) = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v40 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a4 )
  {
    v14 = v40[1];
    v15 = v40[0];
    v16 = (char *)lpMem[1];
    goto LABEL_65;
  }
  v11 = (unsigned int)lpMem[0];
  v12 = a4;
  do
  {
    if ( v12[1] != 34 || memcmp_0(v12 + 6, L":$EfsBackup:$DATA", 0x22u) )
      ++v11;
    if ( !*v12 )
      break;
    v12 = (unsigned int *)((char *)v12 + *v12);
  }
  while ( v12 );
  LODWORD(lpMem[0]) = v11;
  v13 = wil::details::heap_allocator::allocate(8LL * v11);
  v40[1] = v13;
  v14 = v13;
  if ( !v13 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 21, 141);
    v15 = v40[0];
    v9 = 8;
    v16 = (char *)lpMem[1];
    goto LABEL_57;
  }
  memset_0(v13, 0, 8LL * v11);
  lpMem[1] = wil::details::heap_allocator::allocate(16LL * v11);
  v16 = (char *)lpMem[1];
  if ( !lpMem[1] )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 21, 157);
    v15 = v40[0];
    v9 = 8;
    goto LABEL_57;
  }
  v40[0] = wil::details::heap_allocator::allocate(24LL * v11);
  v15 = v40[0];
  if ( !v40[0] )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 21, 166);
    v9 = 8;
    goto LABEL_57;
  }
  v17 = 0;
  v35 = 0;
  while ( 1 )
  {
    IoStatusBlock = 0;
    if ( v10[1] == 34 )
    {
      if ( !memcmp_0(v10 + 6, L":$EfsBackup:$DATA", 0x22u) )
      {
        if ( *v10 )
          v10 = (unsigned int *)((char *)v10 + *v10);
        else
          v10 = 0;
        v17 = v35;
        goto LABEL_42;
      }
      v17 = v35;
    }
    v19 = (PHANDLE)v17;
    v20 = (struct _UNICODE_STRING *)&v16[16 * v17];
    FileHandle = (PHANDLE)v17;
    v21 = 3LL * v17;
    v43 = v21;
    v20->Buffer = (PWSTR)(v10 + 6);
    v20->MaximumLength = *((_WORD *)v10 + 2);
    v20->Length = *((_WORD *)v10 + 2);
    v15[v21 + 1] = *((_QWORD *)v10 + 1);
    v15[v21 + 2] = *((_QWORD *)v10 + 2);
    if ( *v10 )
      v10 = (unsigned int *)((char *)v10 + *v10);
    else
      v10 = 0;
    if ( v20->Length != 14 )
      break;
    Buffer = v20->Buffer;
    if ( *(_QWORD *)Buffer != 0x440024003A003ALL || *((_DWORD *)Buffer + 2) != 5505089 || Buffer[6] != 65 )
      break;
    v14[(_QWORD)v19] = v42;
    v37 = 1;
LABEL_32:
    if ( a3 != 8 )
    {
      v25 = NtFlushBuffersFile((HANDLE)v14[(_QWORD)v19], &IoStatusBlock);
      v24 = v25;
      if ( v25 < 0 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v25, 21, 21);
        goto LABEL_56;
      }
    }
    v26 = (void *)v14[(_QWORD)FileHandle];
    FileHandle = (PHANDLE)&v14[(_QWORD)FileHandle];
    v27 = NtQueryInformationFile(v26, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    v24 = v27;
    if ( v27 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v27, 21, 37);
      goto LABEL_56;
    }
    if ( a3 != 8 || v37 || (DesiredAccess & 1) != 0 )
      goto LABEL_40;
    v28 = v49;
    if ( (v49 & 0x4000) == 0 )
    {
      NtClose(*FileHandle);
      v29 = NtCreateFile(
              FileHandle,
              DesiredAccess | 1,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              a2,
              1u,
              CreateOptions,
              0,
              0);
      v24 = v29;
      if ( v29 < 0 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v29, 21, 69);
        goto LABEL_56;
      }
LABEL_40:
      v28 = v49;
    }
    v18 = v43;
    LODWORD(v15[v43]) = v28;
    v17 = ++v35;
LABEL_42:
    if ( !v10 )
    {
      if ( v17 != v11 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v18);
      if ( (unsigned int)(a3 - 1) <= 1 )
      {
        if ( !v45 )
        {
          v9 = 87;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 21, 90);
          goto LABEL_57;
        }
        v30 = EfspCheckVolumeSpace(v45, (struct _EFS_STREAM_DATA *)lpMem);
        v9 = v30;
        if ( v30 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v30, 21, 97);
          v14 = v40[1];
          v15 = v40[0];
          v16 = (char *)lpMem[1];
          v11 = (unsigned int)lpMem[0];
          goto LABEL_57;
        }
        v14 = v40[1];
        v15 = v40[0];
        v16 = (char *)lpMem[1];
        v11 = (unsigned int)lpMem[0];
      }
      v31 = v46;
      *(_QWORD *)(v46 + 8) = v16;
      v16 = 0;
      *(_QWORD *)(v31 + 24) = v14;
      v14 = 0;
      *(_QWORD *)(v31 + 16) = v15;
      v15 = 0;
      *(_DWORD *)v31 = v11;
      goto LABEL_65;
    }
  }
  ObjectAttributes.RootDirectory = v42;
  ObjectAttributes.ObjectName = v20;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v23 = NtCreateFile(
          (PHANDLE)&v14[(_QWORD)v19],
          DesiredAccess,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          a2,
          1u,
          CreateOptions,
          0,
          0);
  v24 = v23;
  if ( v23 >= 0 )
  {
    v19 = FileHandle;
    v37 = 0;
    goto LABEL_32;
  }
  fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v23, 21, 5);
LABEL_56:
  v9 = EfspMapError(v24, 6000);
  if ( !v9 )
    goto LABEL_65;
LABEL_57:
  if ( v14 )
  {
    for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
    {
      v33 = (void *)v14[i];
      if ( !v33 )
        break;
      if ( v42 != v33 )
        NtClose(v33);
    }
LABEL_65:
    if ( v14 )
      EfsFreeHeap(v14);
  }
  if ( v16 )
    EfsFreeHeap(v16);
  if ( v15 )
    EfsFreeHeap(v15);
  return v9;
}

```

## disassembly

```asm
0x180067cc4  mov     [rsp-8+arg_10], rbx
0x180067cc9  push    rbp
0x180067cca  push    rsi
0x180067ccb  push    rdi
0x180067ccc  push    r12
0x180067cce  push    r13
0x180067cd0  push    r14
0x180067cd2  push    r15
0x180067cd4  lea     rbp, [rsp-30h]
0x180067cd9  sub     rsp, 130h
0x180067ce0  mov     rax, cs:__security_cookie
0x180067ce7  xor     rax, rsp
0x180067cea  mov     [rbp+60h+var_40], rax
0x180067cee  mov     rax, [rbp+60h+arg_40]
0x180067cf5  xorps   xmm0, xmm0
0x180067cf8  xorps   xmm1, xmm1
0x180067cfb  mov     [rbp+60h+var_C8], rcx
0x180067cff  mov     rcx, [rbp+60h+arg_38]
0x180067d06  xor     r14d, r14d
0x180067d09  mov     [rbp+60h+var_A8], rcx
0x180067d0d  mov     r13, r9
0x180067d10  xor     ecx, ecx
0x180067d12  mov     [rsp+160h+var_FC], r8d
0x180067d17  mov     [rsp+160h+var_F4], edx
0x180067d1b  mov     [rbp+60h+var_A0], rax
0x180067d1f  mov     [rbp+60h+var_48], rcx
0x180067d23  mov     [rax], ecx
0x180067d25  mov     [rax+18h], rcx
0x180067d29  mov     [rax+8], rcx
0x180067d2d  mov     [rax+10h], rcx
0x180067d31  movups  xmmword ptr [rsp+160h+lpMem], xmm0
0x180067d36  movups  xmmword ptr [rbp+60h+var_E0], xmm0
0x180067d3a  movups  [rbp+60h+FileInformation], xmm0
0x180067d3e  movups  [rbp+60h+var_58], xmm0
0x180067d42  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm1
0x180067d46  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm1
0x180067d4a  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm1
0x180067d4e  test    r9, r9
0x180067d51  jz      loc_180068214
0x180067d57  mov     r12d, dword ptr [rsp+160h+lpMem]
0x180067d5c  mov     rbx, r9
0x180067d5f  cmp     dword ptr [rbx+4], 22h ; '"'
0x180067d63  jnz     short loc_180067D7F
0x180067d65  lea     rcx, [rbx+18h]; Buf1
0x180067d69  mov     r8d, 22h ; '"'; Size
0x180067d6f  lea     rdx, aEfsbackupData; ":$EfsBackup:$DATA"
0x180067d76  call    memcmp_0
0x180067d7b  test    eax, eax
0x180067d7d  jz      short loc_180067D82
0x180067d7f  inc     r12d
0x180067d82  cmp     [rbx], r14d
0x180067d85  jz      short loc_180067D8E
0x180067d87  mov     eax, [rbx]
0x180067d89  add     rbx, rax
0x180067d8c  jnz     short loc_180067D5F
0x180067d8e  mov     edi, r12d
0x180067d91  mov     dword ptr [rsp+160h+lpMem], r12d
0x180067d96  lea     rsi, ds:0[rdi*8]
0x180067d9e  mov     rcx, rsi; unsigned __int64
0x180067da1  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180067da6  mov     [rbp+60h+var_E0+8], rax
0x180067daa  mov     rbx, rax
0x180067dad  test    rax, rax
0x180067db0  jnz     short loc_180067DE7
0x180067db2  mov     rcx, cs:g_hPublisher
0x180067db9  lea     r9d, [rax+15h]
0x180067dbd  lea     r8d, [rax+8]
0x180067dc1  mov     dword ptr [rsp+160h+AllocationSize], 28Dh
0x180067dc9  lea     rdx, EFS_API_ERROR
0x180067dd0  call    fnEfsLogTrace1
0x180067dd5  mov     rdi, [rbp+60h+var_E0]
0x180067dd9  lea     r14d, [rbx+8]
0x180067ddd  mov     r15, [rsp+160h+lpMem+8]
0x180067de2  jmp     loc_1800681EA
0x180067de7  mov     r8, rsi; Size
0x180067dea  xor     edx, edx; Val
0x180067dec  mov     rcx, rbx; void *
0x180067def  call    memset_0
0x180067df4  mov     rcx, rdi
0x180067df7  shl     rcx, 4; unsigned __int64
0x180067dfb  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180067e00  mov     [rsp+160h+lpMem+8], rax
0x180067e05  mov     r15, rax
0x180067e08  test    rax, rax
0x180067e0b  jnz     short loc_180067E3D
0x180067e0d  mov     rcx, cs:g_hPublisher
0x180067e14  lea     r9d, [rax+15h]
0x180067e18  lea     r8d, [rax+8]
0x180067e1c  mov     dword ptr [rsp+160h+AllocationSize], 29Dh
0x180067e24  lea     rdx, EFS_API_ERROR
0x180067e2b  call    fnEfsLogTrace1
0x180067e30  mov     rdi, [rbp+60h+var_E0]
0x180067e34  lea     r14d, [r15+8]
0x180067e38  jmp     loc_1800681EA
0x180067e3d  lea     rcx, [rdi+rdi*2]
0x180067e41  shl     rcx, 3; unsigned __int64
0x180067e45  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180067e4a  mov     [rbp+60h+var_E0], rax
0x180067e4e  mov     rdi, rax
0x180067e51  test    rax, rax
0x180067e54  jnz     short loc_180067E82
0x180067e56  mov     rcx, cs:g_hPublisher
0x180067e5d  lea     r9d, [rax+15h]
0x180067e61  lea     r8d, [rax+8]
0x180067e65  mov     dword ptr [rsp+160h+AllocationSize], 2A6h
0x180067e6d  lea     rdx, EFS_API_ERROR
0x180067e74  call    fnEfsLogTrace1
0x180067e79  lea     r14d, [rdi+8]
0x180067e7d  jmp     loc_1800681EA
0x180067e82  xor     eax, eax
0x180067e84  mov     [rsp+160h+var_100], eax
0x180067e88  xorps   xmm0, xmm0
0x180067e8b  lea     rsi, [r13+18h]
0x180067e8f  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x180067e93  cmp     dword ptr [r13+4], 22h ; '"'
0x180067e98  jnz     short loc_180067ED2
0x180067e9a  mov     r8d, 22h ; '"'; Size
0x180067ea0  lea     rdx, aEfsbackupData; ":$EfsBackup:$DATA"
0x180067ea7  mov     rcx, rsi; Buf1
0x180067eaa  call    memcmp_0
0x180067eaf  test    eax, eax
0x180067eb1  jnz     short loc_180067ECE
0x180067eb3  cmp     [r13+0], r14d
0x180067eb7  jz      short loc_180067EC2
0x180067eb9  mov     eax, [r13+0]
0x180067ebd  add     r13, rax
0x180067ec0  jmp     short loc_180067EC5
0x180067ec2  xor     r13d, r13d
0x180067ec5  mov     eax, [rsp+160h+var_100]
0x180067ec9  jmp     loc_1800680BF
0x180067ece  mov     eax, [rsp+160h+var_100]
0x180067ed2  mov     r8d, eax
0x180067ed5  mov     ecx, eax
0x180067ed7  shl     rcx, 4
0x180067edb  add     rcx, r15
0x180067ede  mov     [rbp+60h+FileHandle], r8
0x180067ee2  lea     rdx, [r8+r8*2]
0x180067ee6  mov     [rbp+60h+var_C0], rdx
0x180067eea  mov     [rcx+8], rsi
0x180067eee  movzx   eax, word ptr [r13+4]
0x180067ef3  mov     [rcx+2], ax
0x180067ef7  movzx   eax, word ptr [r13+4]
0x180067efc  mov     [rcx], ax
0x180067eff  mov     rax, [r13+8]
0x180067f03  mov     [rdi+rdx*8+8], rax
0x180067f08  mov     rax, [r13+10h]
0x180067f0c  mov     [rdi+rdx*8+10h], rax
0x180067f11  cmp     [r13+0], r14d
0x180067f15  jz      short loc_180067F20
0x180067f17  mov     eax, [r13+0]
0x180067f1b  add     r13, rax
0x180067f1e  jmp     short loc_180067F23
0x180067f20  xor     r13d, r13d
0x180067f23  mov     eax, 0Eh
0x180067f28  cmp     ax, [rcx]
0x180067f2b  jnz     short loc_180067F62
0x180067f2d  mov     rax, [rcx+8]
0x180067f31  mov     rdx, 440024003A003Ah
0x180067f3b  cmp     [rax], rdx
0x180067f3e  jnz     short loc_180067F62
0x180067f40  cmp     dword ptr [rax+8], 540041h
0x180067f47  jnz     short loc_180067F62
0x180067f49  cmp     word ptr [rax+0Ch], 41h ; 'A'
0x180067f4e  jnz     short loc_180067F62
0x180067f50  mov     rax, [rbp+60h+var_C8]
0x180067f54  mov     [rbx+r8*8], rax
0x180067f58  mov     [rsp+160h+var_F8], 1
0x180067f60  jmp     short loc_180067FDA
0x180067f62  mov     rax, [rbp+60h+var_C8]
0x180067f66  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180067f6a  mov     edx, [rbp+60h+DesiredAccess]; DesiredAccess
0x180067f70  xorps   xmm0, xmm0
0x180067f73  mov     [rsp+160h+EaLength], r14d; EaLength
0x180067f78  mov     [rsp+160h+EaBuffer], r14; EaBuffer
0x180067f7d  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x180067f81  mov     eax, [rbp+60h+arg_30]
0x180067f87  mov     [rsp+160h+CreateOptions], eax; CreateOptions
0x180067f8b  mov     eax, [rsp+160h+var_F4]
0x180067f8f  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x180067f97  mov     [rsp+160h+ShareAccess], eax; ShareAccess
0x180067f9b  mov     [rbp+60h+ObjectAttributes.ObjectName], rcx
0x180067f9f  lea     rcx, [rbx+r8*8]; FileHandle
0x180067fa3  mov     [rsp+160h+FileAttributes], r14d; FileAttributes
0x180067fa8  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180067fac  mov     [rsp+160h+AllocationSize], r14; AllocationSize
0x180067fb1  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180067fb8  mov     [rbp+60h+ObjectAttributes.Attributes], r14d
0x180067fbc  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180067fc1  call    cs:__imp_NtCreateFile
0x180067fc7  mov     esi, eax
0x180067fc9  test    eax, eax
0x180067fcb  js      loc_1800681B3
0x180067fd1  mov     r8, [rbp+60h+FileHandle]
0x180067fd5  mov     [rsp+160h+var_F8], r14d
0x180067fda  cmp     [rsp+160h+var_FC], 8
0x180067fdf  jz      short loc_180067FF9
0x180067fe1  mov     rcx, [rbx+r8*8]; FileHandle
0x180067fe5  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180067fe9  call    cs:__imp_NtFlushBuffersFile
0x180067fef  mov     esi, eax
0x180067ff1  test    eax, eax
0x180067ff3  js      loc_180068115
0x180067ff9  mov     rax, [rbp+60h+FileHandle]
0x180067ffd  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x180068001  mov     r9d, 28h ; '('; Length
0x180068007  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x18006800f  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180068013  lea     rax, [rbx+rax*8]
0x180068017  mov     rcx, [rax]; FileHandle
0x18006801a  mov     [rbp+60h+FileHandle], rax
0x18006801e  call    cs:__imp_NtQueryInformationFile
0x180068024  mov     esi, eax
0x180068026  test    eax, eax
0x180068028  js      loc_1800681A9
0x18006802e  cmp     [rsp+160h+var_FC], 8
0x180068033  jnz     short loc_1800680AA
0x180068035  cmp     [rsp+160h+var_F8], r14d
0x18006803a  jnz     short loc_1800680AA
0x18006803c  test    byte ptr [rbp+60h+DesiredAccess], 1
0x180068043  jnz     short loc_1800680AA
0x180068045  mov     rax, [rbp+60h+var_48]
0x180068049  bt      eax, 0Eh
0x18006804d  jb      short loc_1800680AE
0x18006804f  mov     rsi, [rbp+60h+FileHandle]
0x180068053  mov     rcx, [rsi]; Handle
0x180068056  call    cs:__imp_NtClose
0x18006805c  mov     eax, [rbp+60h+arg_30]
0x180068062  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180068066  mov     edx, [rbp+60h+DesiredAccess]
0x18006806c  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180068070  xor     ecx, ecx
0x180068072  or      edx, 1; DesiredAccess
0x180068075  mov     [rsp+160h+EaLength], ecx; EaLength
0x180068079  mov     [rsp+160h+EaBuffer], rcx; EaBuffer
0x18006807e  mov     [rsp+160h+CreateOptions], eax; CreateOptions
0x180068082  mov     eax, [rsp+160h+var_F4]
0x180068086  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x18006808e  mov     [rsp+160h+ShareAccess], eax; ShareAccess
0x180068092  mov     [rsp+160h+FileAttributes], ecx; FileAttributes
0x180068096  mov     [rsp+160h+AllocationSize], rcx; AllocationSize
0x18006809b  mov     rcx, rsi; FileHandle
0x18006809e  call    cs:__imp_NtCreateFile
0x1800680a4  mov     esi, eax
0x1800680a6  test    eax, eax
0x1800680a8  js      short loc_180068122
0x1800680aa  mov     rax, [rbp+60h+var_48]
0x1800680ae  mov     rcx, [rbp+60h+var_C0]
0x1800680b2  mov     [rdi+rcx*8], eax
0x1800680b5  mov     eax, [rsp+160h+var_100]
0x1800680b9  inc     eax
0x1800680bb  mov     [rsp+160h+var_100], eax
0x1800680bf  test    r13, r13
0x1800680c2  jnz     loc_180067E88
0x1800680c8  cmp     eax, r12d
0x1800680cb  jz      short loc_1800680D2
0x1800680cd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Index == LocalData.StreamCount")
0x1800680d2  mov     eax, [rsp+160h+var_FC]
0x1800680d6  dec     eax
0x1800680d8  cmp     eax, 1
0x1800680db  ja      loc_18006818D
0x1800680e1  mov     rax, [rbp+60h+var_A8]
0x1800680e5  test    rax, rax
0x1800680e8  jnz     short loc_18006812F
0x1800680ea  mov     rcx, cs:g_hPublisher
0x1800680f1  lea     r14d, [rax+57h]
0x1800680f5  mov     r8d, r14d
0x1800680f8  mov     dword ptr [rsp+160h+AllocationSize], 35Ah
0x180068100  lea     r9d, [rax+15h]
0x180068104  lea     rdx, EFS_API_ERROR
0x18006810b  call    fnEfsLogTrace1
0x180068110  jmp     loc_1800681EA
0x180068115  mov     dword ptr [rsp+160h+AllocationSize], 315h
0x18006811d  jmp     loc_1800681BB
0x180068122  mov     dword ptr [rsp+160h+AllocationSize], 345h
0x18006812a  jmp     loc_1800681BB
0x18006812f  lea     rdx, [rsp+160h+lpMem]; struct _EFS_STREAM_DATA *
0x180068134  mov     rcx, rax; struct _FILE_FS_SIZE_INFORMATION *
0x180068137  call    ?EfspCheckVolumeSpace@@YAKPEAU_FILE_FS_SIZE_INFORMATION@@PEAU_EFS_STREAM_DATA@@@Z; EfspCheckVolumeSpace(_FILE_FS_SIZE_INFORMATION *,_EFS_STREAM_DATA *)
0x18006813c  mov     r14d, eax
0x18006813f  test    eax, eax
0x180068141  jz      short loc_18006817B
0x180068143  mov     rcx, cs:g_hPublisher
0x18006814a  lea     rdx, EFS_API_ERROR
0x180068151  mov     r9d, 15h
0x180068157  mov     dword ptr [rsp+160h+AllocationSize], 361h
0x18006815f  mov     r8d, eax
0x180068162  call    fnEfsLogTrace1
0x180068167  mov     rbx, [rbp+60h+var_E0+8]
0x18006816b  mov     rdi, [rbp+60h+var_E0]
0x18006816f  mov     r15, [rsp+160h+lpMem+8]
0x180068174  mov     r12d, dword ptr [rsp+160h+lpMem]
0x180068179  jmp     short loc_1800681EA
0x18006817b  mov     rbx, [rbp+60h+var_E0+8]
0x18006817f  mov     rdi, [rbp+60h+var_E0]
0x180068183  mov     r15, [rsp+160h+lpMem+8]
0x180068188  mov     r12d, dword ptr [rsp+160h+lpMem]
0x18006818d  mov     rax, [rbp+60h+var_A0]
0x180068191  mov     [rax+8], r15
0x180068195  xor     r15d, r15d
0x180068198  mov     [rax+18h], rbx
  ... truncated ...
```
