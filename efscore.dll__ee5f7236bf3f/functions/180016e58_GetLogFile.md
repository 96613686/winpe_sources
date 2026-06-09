# GetLogFile

- ea: `0x180016e58`
- end: `0x1800172fd`
- name: `GetLogFile`
- size: `1189`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010740`
- `0x180016080`
- `0x180042508`

## callees

- `0x180004f86`
- `0x1800102f0`
- `0x180010bf0`
- `0x180013ae0`
- `0x180016e58`
- `0x18001d290`
- `0x180063698`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171d8`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001724e`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001724e`
- `ntdll!RtlFreeHeap` at `0x180017131`
- `ntdll!RtlFreeHeap` at `0x1800172d4`
- `ntdll!RtlFreeHeap` at `0x180017131`
- `ntdll!RtlFreeHeap` at `0x1800172d4`
- `ntdll!NtCreateFile` at `0x1800171c0`
- `ntdll!NtCreateFile` at `0x1800171c0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180016f66`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180016f66`
- `ntdll!RtlInitUnicodeString` at `0x180016ec1`
- `ntdll!RtlInitUnicodeString` at `0x180016ecd`
- `ntdll!RtlInitUnicodeString` at `0x180016ec1`
- `ntdll!RtlInitUnicodeString` at `0x180016ecd`

## pseudocode

```c
__int64 __fastcall GetLogFile(const void **a1, DWORD a2)
{
  void *v4; // r14
  unsigned int v5; // edi
  DWORD LastError; // eax
  int v7; // r8d
  WCHAR *p_DaclDefaulted; // rbx
  unsigned __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  WCHAR *v14; // rax
  PWSTR Buffer; // rcx
  __int64 v16; // rdx
  int SystemFullControlSD; // eax
  PVOID v18; // rsi
  char v19; // r15
  LPSECURITY_ATTRIBUTES v20; // r9
  int v21; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  __int64 v24; // [rsp+0h] [rbp-60h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-40h]
  ULONG FileAttributes; // [rsp+28h] [rbp-38h]
  int DaclDefaulted; // [rsp+60h] [rbp+0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp+8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+18h] BYREF
  ACCESS_MASK fDesiredAccess[2]; // [rsp+88h] [rbp+28h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+30h] BYREF
  PACL Dacl; // [rsp+98h] [rbp+38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp+78h] BYREF

  FileHandle = 0;
  *(_QWORD *)fDesiredAccess = 0;
  LOWORD(DaclDefaulted) = 0;
  Dacl = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DestinationString = 0;
  NtPathName = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&NtPathName, 0);
  v4 = wil::details::heap_allocator::allocate(*(unsigned __int16 *)a1 + 2LL);
  if ( !v4 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, *(unsigned __int16 *)a1 + 2, 4, 192);
    v5 = -1073741670;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -1073741670, 4, 193);
    goto LABEL_35;
  }
  memcpy_0(v4, a1[1], *(unsigned __int16 *)a1);
  *((_WORD *)v4 + ((unsigned __int64)*(unsigned __int16 *)a1 >> 1)) = 0;
  LOBYTE(DaclDefaulted) = RtlDosPathNameToNtPathName_U((PCWSTR)v4, &NtPathName, 0, 0);
  if ( (_BYTE)DaclDefaulted )
  {
    p_DaclDefaulted = 0;
    v9 = NtPathName.Length + 78LL;
    if ( v9 > g_ulMaxStackAllocSize || v9 + g_ulAdditionalProbeSize + 8 < v9 || !(unsigned int)VerifyStackAvailable() )
      goto LABEL_40;
    v10 = v9 + 23;
    if ( v9 + 23 <= v9 + 8 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    p_DaclDefaulted = (WCHAR *)&DaclDefaulted;
    if ( &v24 == (__int64 *)-96LL || (DaclDefaulted = 1801679955, (p_DaclDefaulted = (WCHAR *)&NtPathName) == 0) )
    {
LABEL_40:
      if ( v9 + 8 >= v9 )
      {
        v14 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_DaclDefaulted = v14;
        if ( v14 )
        {
          *(_DWORD *)v14 = 1885431112;
          p_DaclDefaulted = v14 + 4;
        }
      }
    }
    DestinationString.Buffer = p_DaclDefaulted;
    if ( !p_DaclDefaulted )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, NtPathName.Length + 78, 4, 216);
      v7 = -1073741670;
      LODWORD(AllocationSize) = 1497;
      v5 = -1073741670;
      goto LABEL_5;
    }
    memcpy_0(p_DaclDefaulted, NtPathName.Buffer, NtPathName.Length - 2LL);
    Buffer = DestinationString.Buffer;
    v16 = NtPathName.Length & 0xFFFE;
    *(_OWORD *)((char *)DestinationString.Buffer + v16 - 2) = *(_OWORD *)L"\\System Volume Information";
    *(_OWORD *)((char *)Buffer + v16 + 14) = *(_OWORD *)L"Volume Information";
    *(_OWORD *)((char *)Buffer + v16 + 30) = *(_OWORD *)L"nformation";
    *(_DWORD *)((char *)Buffer + v16 + 46) = *(_DWORD *)L"on";
    DestinationString.Length = NtPathName.Length + 50;
    DestinationString.MaximumLength = NtPathName.Length + 78;
    DestinationString.Buffer[(unsigned __int64)(unsigned __int16)(NtPathName.Length + 50) >> 1] = 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    NtPathName.Buffer = 0;
    SystemFullControlSD = EfspMakeSystemFullControlSD(fDesiredAccess);
    v18 = *(PVOID *)fDesiredAccess;
    v5 = SystemFullControlSD;
    if ( SystemFullControlSD >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.SecurityDescriptor = *(PVOID *)fDesiredAccess;
      ObjectAttributes.SecurityQualityOfService = 0;
      SystemFullControlSD = NtCreateFile(
                              &FileHandle,
                              0x80u,
                              &ObjectAttributes,
                              &IoStatusBlock,
                              0,
                              0x16u,
                              7u,
                              3u,
                              1u,
                              0,
                              0);
      v5 = SystemFullControlSD;
      if ( SystemFullControlSD >= 0 )
      {
        CloseHandle(FileHandle);
        SystemFullControlSD = (unsigned int)CreateLogFile(
                                              &DestinationString.Length,
                                              (ACCESS_MASK)v18,
                                              a2,
                                              v20,
                                              (ULONG)AllocationSize,
                                              FileAttributes);
        v5 = SystemFullControlSD;
        if ( SystemFullControlSD >= 0 )
        {
LABEL_25:
          if ( v18 )
          {
            DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(
                                       v18,
                                       (PBOOLEAN)&DaclDefaulted + 1,
                                       &Dacl,
                                       (PBOOLEAN)&DaclDefaulted);
            if ( DaclSecurityDescriptor >= 0 )
            {
              if ( BYTE1(DaclDefaulted) )
                EfsFreeHeap(Dacl);
            }
            else
            {
              fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, DaclSecurityDescriptor, 4, 42);
            }
            EfsFreeHeap(v18);
          }
          if ( DestinationString.Buffer && *((_DWORD *)DestinationString.Buffer - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          goto LABEL_34;
        }
        v19 = 33;
      }
      else
      {
        v19 = 16;
      }
    }
    else
    {
      v19 = -7;
    }
    v21 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, SystemFullControlSD, 4, v19);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v21, 4, v19);
    goto LABEL_25;
  }
  LastError = GetLastError();
  fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 4, 202);
  v7 = -1073741772;
  LODWORD(AllocationSize) = 1483;
  v5 = -1073741772;
LABEL_5:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 4, (char)AllocationSize);
LABEL_34:
  EfsFreeHeap(v4);
LABEL_35:
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  return v5;
}

```

## disassembly

```asm
0x180016e58  push    rbp
0x180016e5a  push    rbx
0x180016e5b  push    rsi
0x180016e5c  push    rdi
0x180016e5d  push    r12
0x180016e5f  push    r14
0x180016e61  push    r15
0x180016e63  sub     rsp, 0F0h
0x180016e6a  lea     rbp, [rsp+60h]
0x180016e6f  mov     rax, cs:__security_cookie
0x180016e76  xor     rax, rbp
0x180016e79  mov     [rbp+0C0h+var_38], rax
0x180016e80  xorps   xmm0, xmm0
0x180016e83  xor     r12d, r12d
0x180016e86  mov     r15, rdx
0x180016e89  mov     [rbp+0C0h+FileHandle], r12
0x180016e8d  mov     rbx, rcx
0x180016e90  mov     qword ptr [rbp+0C0h+fDesiredAccess], r12
0x180016e94  xorps   xmm1, xmm1
0x180016e97  mov     [rbp+0C0h+DaclDefaulted], r12b
0x180016e9b  xor     edx, edx; SourceString
0x180016e9d  mov     [rbp+0C0h+DaclPresent], r12b
0x180016ea1  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x180016ea5  mov     [rbp+0C0h+Dacl], r12
0x180016ea9  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x180016ead  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x180016eb1  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016eb5  movups  xmmword ptr [rbp+0C0h+IoStatusBlock], xmm0
0x180016eb9  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x180016ebd  movups  xmmword ptr [rbp+0C0h+NtPathName.Length], xmm0
0x180016ec1  call    cs:__imp_RtlInitUnicodeString
0x180016ec7  xor     edx, edx; SourceString
0x180016ec9  lea     rcx, [rbp+0C0h+NtPathName]; DestinationString
0x180016ecd  call    cs:__imp_RtlInitUnicodeString
0x180016ed3  movzx   ecx, word ptr [rbx]
0x180016ed6  add     rcx, 2; unsigned __int64
0x180016eda  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180016edf  mov     r14, rax
0x180016ee2  movzx   eax, word ptr [rbx]
0x180016ee5  test    r14, r14
0x180016ee8  jnz     short loc_180016F3F
0x180016eea  mov     rcx, cs:g_hPublisher
0x180016ef1  lea     ebx, [r12+4]
0x180016ef6  mov     r9d, ebx
0x180016ef9  mov     dword ptr [rsp+120h+AllocationSize], 5C0h
0x180016f01  lea     r8d, [rax+2]
0x180016f05  lea     rdx, EFS_ERROR_MEMORY
0x180016f0c  call    fnEfsLogTrace1
0x180016f11  mov     rcx, cs:g_hPublisher
0x180016f18  lea     rdx, EFS_TRACE_ERROR
0x180016f1f  mov     r9d, ebx
0x180016f22  mov     dword ptr [rsp+120h+AllocationSize], 5C1h
0x180016f2a  mov     r8d, 0C000009Ah
0x180016f30  mov     edi, 0C000009Ah
0x180016f35  call    fnEfsLogTrace1
0x180016f3a  jmp     loc_1800172BB
0x180016f3f  mov     rdx, [rbx+8]; Src
0x180016f43  mov     r8, rax; Size
0x180016f46  mov     rcx, r14; void *
0x180016f49  call    memcpy_0
0x180016f4e  movzx   ecx, word ptr [rbx]
0x180016f51  lea     rdx, [rbp+0C0h+NtPathName]; NtPathName
0x180016f55  shr     rcx, 1
0x180016f58  xor     r9d, r9d; DirectoryInfo
0x180016f5b  xor     r8d, r8d; NtFileNamePart
0x180016f5e  mov     [r14+rcx*2], r12w
0x180016f63  mov     rcx, r14; DosPathName
0x180016f66  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180016f6c  mov     [rbp+0C0h+DaclDefaulted], al
0x180016f6f  test    al, al
0x180016f71  jnz     short loc_180016FCD
0x180016f73  call    cs:__imp_GetLastError
0x180016f79  mov     rcx, cs:g_hPublisher
0x180016f80  lea     rdx, EFS_API_ERROR
0x180016f87  mov     ebx, 4
0x180016f8c  mov     dword ptr [rsp+120h+AllocationSize], 5CAh
0x180016f94  mov     r9d, ebx
0x180016f97  mov     r8d, eax
0x180016f9a  call    fnEfsLogTrace1
0x180016f9f  mov     r8d, 0C0000034h
0x180016fa5  mov     dword ptr [rsp+120h+AllocationSize], 5CBh
0x180016fad  mov     edi, 0C0000034h
0x180016fb2  mov     rcx, cs:g_hPublisher
0x180016fb9  lea     rdx, EFS_TRACE_ERROR
0x180016fc0  mov     r9d, ebx
0x180016fc3  call    fnEfsLogTrace1
0x180016fc8  jmp     loc_1800172B3
0x180016fcd  movzx   edi, [rbp+0C0h+NtPathName.Length]
0x180016fd1  mov     rbx, r12
0x180016fd4  add     rdi, 4Eh ; 'N'
0x180016fd8  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180016fdf  ja      short loc_180017039
0x180016fe1  mov     rcx, cs:g_ulAdditionalProbeSize
0x180016fe8  add     rcx, 8
0x180016fec  add     rcx, rdi
0x180016fef  cmp     rcx, rdi
0x180016ff2  jb      short loc_180017039
0x180016ff4  call    VerifyStackAvailable
0x180016ff9  test    eax, eax
0x180016ffb  jz      short loc_180017039
0x180016ffd  lea     rax, [rdi+8]
0x180017001  lea     rcx, [rax+0Fh]
0x180017005  cmp     rcx, rax
0x180017008  ja      short loc_180017014
0x18001700a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180017014  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180017018  mov     rax, rcx
0x18001701b  call    _alloca_probe
0x180017020  sub     rsp, rcx
0x180017023  lea     rbx, [rsp+120h+DaclDefaulted]
0x180017028  test    rbx, rbx
0x18001702b  jz      short loc_180017039
0x18001702d  mov     dword ptr [rbx], 6B637453h
0x180017033  add     rbx, 8
0x180017037  jnz     short loc_180017060
0x180017039  lea     rcx, [rdi+8]
0x18001703d  cmp     rcx, rdi
0x180017040  jb      short loc_180017060
0x180017042  mov     rax, cs:g_pfnAllocate
0x180017049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001704e  mov     rbx, rax
0x180017051  test    rax, rax
0x180017054  jz      short loc_180017060
0x180017056  mov     dword ptr [rax], 70616548h
0x18001705c  add     rbx, 8
0x180017060  mov     [rbp+0C0h+DestinationString.Buffer], rbx
0x180017064  test    rbx, rbx
0x180017067  jnz     short loc_1800170AD
0x180017069  movzx   r8d, [rbp+0C0h+NtPathName.Length]
0x18001706e  lea     rdx, EFS_ERROR_MEMORY
0x180017075  mov     rcx, cs:g_hPublisher
0x18001707c  mov     ebx, 4
0x180017081  add     r8d, 4Eh ; 'N'
0x180017085  mov     dword ptr [rsp+120h+AllocationSize], 5D8h
0x18001708d  mov     r9d, ebx
0x180017090  call    fnEfsLogTrace1
0x180017095  mov     r8d, 0C000009Ah
0x18001709b  mov     dword ptr [rsp+120h+AllocationSize], 5D9h
0x1800170a3  mov     edi, 0C000009Ah
0x1800170a8  jmp     loc_180016FB2
0x1800170ad  movzx   r8d, [rbp+0C0h+NtPathName.Length]
0x1800170b2  mov     rcx, rbx; void *
0x1800170b5  mov     rdx, [rbp+0C0h+NtPathName.Buffer]; Src
0x1800170b9  sub     r8, 2; Size
0x1800170bd  call    memcpy_0
0x1800170c2  mov     rcx, [rbp+0C0h+DestinationString.Buffer]
0x1800170c6  movzx   edx, [rbp+0C0h+NtPathName.Length]
0x1800170ca  movups  xmm0, xmmword ptr cs:aSystemVolumeIn_0; "\\System Volume Information"
0x1800170d1  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1800170d5  movups  xmmword ptr [rdx+rcx-2], xmm0
0x1800170da  movups  xmm1, xmmword ptr cs:aSystemVolumeIn_0+10h; "Volume Information"
0x1800170e1  movups  xmmword ptr [rdx+rcx+0Eh], xmm1
0x1800170e6  movups  xmm0, xmmword ptr cs:aSystemVolumeIn_0+20h; "nformation"
0x1800170ed  movups  xmmword ptr [rdx+rcx+1Eh], xmm0
0x1800170f2  mov     eax, dword ptr cs:aSystemVolumeIn_0+30h; "on"
0x1800170f8  mov     [rdx+rcx+2Eh], eax
0x1800170fc  movzx   ecx, [rbp+0C0h+NtPathName.Length]
0x180017100  lea     eax, [rcx+32h]
0x180017103  add     cx, 4Eh ; 'N'
0x180017107  mov     [rbp+0C0h+DestinationString.Length], ax
0x18001710b  mov     [rbp+0C0h+DestinationString.MaximumLength], cx
0x18001710f  movzx   edx, ax
0x180017112  mov     rax, [rbp+0C0h+DestinationString.Buffer]
0x180017116  shr     rdx, 1
0x180017119  mov     [rax+rdx*2], r12w
0x18001711e  xor     edx, edx; Flags
0x180017120  mov     rcx, gs:60h
0x180017129  mov     r8, [rbp+0C0h+NtPathName.Buffer]; P
0x18001712d  mov     rcx, [rcx+30h]; HeapHandle
0x180017131  call    cs:__imp_RtlFreeHeap
0x180017137  lea     rcx, [rbp+0C0h+fDesiredAccess]
0x18001713b  mov     [rbp+0C0h+NtPathName.Buffer], r12
0x18001713f  call    EfspMakeSystemFullControlSD
0x180017144  mov     rsi, qword ptr [rbp+0C0h+fDesiredAccess]
0x180017148  mov     edi, eax
0x18001714a  test    eax, eax
0x18001714c  jns     short loc_18001715E
0x18001714e  mov     r15d, 5F9h
0x180017154  mov     ebx, 4
0x180017159  jmp     loc_1800171FE
0x18001715e  mov     [rsp+120h+EaLength], r12d; EaLength
0x180017163  lea     rax, [rbp+0C0h+DestinationString]
0x180017167  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x18001716c  lea     r9, [rbp+0C0h+IoStatusBlock]; IoStatusBlock
0x180017170  mov     [rsp+120h+CreateOptions], 1; CreateOptions
0x180017178  lea     r8, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x18001717c  mov     [rsp+120h+CreateDisposition], 3; CreateDisposition
0x180017184  lea     rcx, [rbp+0C0h+FileHandle]; FileHandle
0x180017188  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x180017190  mov     edx, 80h; DesiredAccess
0x180017195  mov     [rsp+120h+FileAttributes], 16h; fFlagsAndAttributes
0x18001719d  mov     [rsp+120h+AllocationSize], r12; fCreateDisposition
0x1800171a2  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x1800171a9  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r12
0x1800171ad  mov     [rbp+0C0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800171b4  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rax
0x1800171b8  mov     [rbp+0C0h+ObjectAttributes.SecurityDescriptor], rsi
0x1800171bc  mov     [rbp+0C0h+ObjectAttributes.SecurityQualityOfService], r12
0x1800171c0  call    cs:__imp_NtCreateFile
0x1800171c6  mov     edi, eax
0x1800171c8  test    eax, eax
0x1800171ca  jns     short loc_1800171D4
0x1800171cc  mov     r15d, 610h
0x1800171d2  jmp     short loc_180017154
0x1800171d4  mov     rcx, [rbp+0C0h+FileHandle]; hObject
0x1800171d8  call    cs:__imp_CloseHandle
0x1800171de  mov     r8, r15; dwShareMode
0x1800171e1  lea     rcx, [rbp+0C0h+DestinationString]; pszLogFileName
0x1800171e5  mov     rdx, rsi; fDesiredAccess
0x1800171e8  call    CreateLogFile
0x1800171ed  mov     edi, eax
0x1800171ef  mov     ebx, 4
0x1800171f4  test    eax, eax
0x1800171f6  jns     short loc_18001723A
0x1800171f8  mov     r15d, 621h
0x1800171fe  mov     rcx, cs:g_hPublisher
0x180017205  lea     rdx, EFS_API_ERROR
0x18001720c  mov     r9d, ebx
0x18001720f  mov     dword ptr [rsp+120h+AllocationSize], r15d
0x180017214  mov     r8d, eax
0x180017217  call    fnEfsLogTrace1
0x18001721c  mov     rcx, cs:g_hPublisher
0x180017223  lea     rdx, EFS_TRACE_ERROR
0x18001722a  mov     r9d, ebx
0x18001722d  mov     dword ptr [rsp+120h+AllocationSize], r15d
0x180017232  mov     r8d, eax
0x180017235  call    fnEfsLogTrace1
0x18001723a  test    rsi, rsi
0x18001723d  jz      short loc_180017292
0x18001723f  lea     r9, [rbp+0C0h+DaclDefaulted]; DaclDefaulted
0x180017243  mov     rcx, rsi; SecurityDescriptor
0x180017246  lea     r8, [rbp+0C0h+Dacl]; Dacl
0x18001724a  lea     rdx, [rbp+0C0h+DaclPresent]; DaclPresent
0x18001724e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180017254  test    eax, eax
0x180017256  jns     short loc_18001727B
0x180017258  mov     rcx, cs:g_hPublisher
0x18001725f  lea     rdx, EFS_API_ERROR
0x180017266  mov     r9d, ebx
0x180017269  mov     dword ptr [rsp+120h+AllocationSize], 62Ah
0x180017271  mov     r8d, eax
0x180017274  call    fnEfsLogTrace1
0x180017279  jmp     short loc_18001728A
0x18001727b  cmp     [rbp+0C0h+DaclPresent], r12b
0x18001727f  jz      short loc_18001728A
0x180017281  mov     rcx, [rbp+0C0h+Dacl]; lpMem
0x180017285  call    EfsFreeHeap
0x18001728a  mov     rcx, rsi; lpMem
0x18001728d  call    EfsFreeHeap
0x180017292  mov     rax, [rbp+0C0h+DestinationString.Buffer]
0x180017296  test    rax, rax
0x180017299  jz      short loc_1800172B3
0x18001729b  lea     rcx, [rax-8]
0x18001729f  cmp     dword ptr [rcx], 70616548h
0x1800172a5  jnz     short loc_1800172B3
0x1800172a7  mov     rax, cs:g_pfnFree
0x1800172ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172b3  mov     rcx, r14; lpMem
0x1800172b6  call    EfsFreeHeap
0x1800172bb  cmp     [rbp+0C0h+NtPathName.Buffer], r12
0x1800172bf  jz      short loc_1800172DA
0x1800172c1  mov     rcx, gs:60h
0x1800172ca  xor     edx, edx; Flags
0x1800172cc  mov     r8, [rbp+0C0h+NtPathName.Buffer]; P
0x1800172d0  mov     rcx, [rcx+30h]; HeapHandle
0x1800172d4  call    cs:__imp_RtlFreeHeap
0x1800172da  mov     eax, edi
0x1800172dc  mov     rcx, [rbp+0C0h+var_38]
0x1800172e3  xor     rcx, rbp; StackCookie
0x1800172e6  call    __security_check_cookie
0x1800172eb  lea     rsp, [rbp+90h]
0x1800172f2  pop     r15
0x1800172f4  pop     r14
0x1800172f6  pop     r12
0x1800172f8  pop     rdi
0x1800172f9  pop     rsi
0x1800172fa  pop     rbx
0x1800172fb  pop     rbp
0x1800172fc  retn
```
