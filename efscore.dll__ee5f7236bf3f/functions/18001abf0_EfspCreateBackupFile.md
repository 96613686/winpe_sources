# EfspCreateBackupFile

- ea: `0x18001abf0`
- end: `0x18001b125`
- name: `EfspCreateBackupFile`
- size: `1333`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b61c`
- `0x18001c22c`

## callees

- `0x180004f86`
- `0x18000b8c8`
- `0x1800102f0`
- `0x180010bf0`
- `0x180017510`
- `0x18001abf0`
- `0x18001d290`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0b2`
- `ntdll!NtClose` at `0x18001b109`
- `ntdll!NtClose` at `0x18001b109`
- `ntdll!NtSetInformationThread` at `0x18001af66`
- `ntdll!NtSetInformationThread` at `0x18001af66`
- `ntdll!NtOpenThreadToken` at `0x18001aeb0`
- `ntdll!NtOpenThreadToken` at `0x18001aeb0`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001b0df`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001b0df`
- `ntdll!NtQueryInformationFile` at `0x18001b044`
- `ntdll!NtQueryInformationFile` at `0x18001b044`
- `ntdll!RtlFreeHeap` at `0x18001afa4`
- `ntdll!RtlFreeHeap` at `0x18001afa4`
- `ntdll!NtCreateFile` at `0x18001ae68`
- `ntdll!NtCreateFile` at `0x18001af28`
- `ntdll!NtCreateFile` at `0x18001ae68`
- `ntdll!NtCreateFile` at `0x18001af28`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001add8`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001add8`
- `RPCRT4!RpcRevertToSelf` at `0x18001aede`
- `RPCRT4!RpcRevertToSelf` at `0x18001aede`

## pseudocode

```c
__int64 __fastcall EfspCreateBackupFile(unsigned __int16 *a1, void **a2, void *a3, PCWSTR *a4)
{
  PSECURITY_DESCRIPTOR v7; // r14
  int v8; // ebx
  const void **v9; // rbx
  int v10; // r8d
  __int64 v11; // rcx
  int v12; // r13d
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  int SystemFullControlSD; // eax
  int v16; // eax
  unsigned __int16 *v17; // rax
  unsigned int v18; // r13d
  DWORD LastError; // eax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  int v24; // r8d
  PACL Dacl; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+110h] [rbp+67h] BYREF
  unsigned __int16 *DaclDefaulted; // [rsp+118h] [rbp+6Fh] BYREF
  PVOID FileInformation; // [rsp+120h] [rbp+77h]
  void *TokenHandle; // [rsp+128h] [rbp+7Fh] BYREF

  FileInformation = a3;
  SecurityDescriptor = 0;
  TokenHandle = 0;
  NtPathName = 0;
  *a2 = 0;
  v7 = 0;
  *a4 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( *a1 < 2u )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, -1073741811, 10, 37);
    v8 = -1073741811;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -1073741811, 10, 38);
    goto LABEL_41;
  }
  v9 = (const void **)(a1 + 4);
  v10 = (*a1 >> 1) - 1;
  do
  {
    if ( v10 < 0 )
      break;
    v11 = v10;
    v9 = (const void **)(a1 + 4);
    --v10;
  }
  while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v11) != 92 );
  v12 = v10 + (*((_WORD *)*v9 + v10 + 1) == 92) + 1;
  v13 = (WCHAR *)wil::details::heap_allocator::allocate(2LL * (unsigned int)(v12 + 20));
  *a4 = v13;
  v14 = v13;
  if ( !v13 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 2 * (v12 + 20), 10, 81);
    v8 = -1073741670;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -1073741670, 10, 82);
    goto LABEL_41;
  }
  memcpy_0(v13, *v9, 2LL * v12);
  SystemFullControlSD = EfspMakeSystemFullControlSD(&SecurityDescriptor);
  v8 = SystemFullControlSD;
  if ( SystemFullControlSD < 0 )
  {
    v16 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, SystemFullControlSD, 10, 97);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 10, 97);
    v7 = SecurityDescriptor;
    goto LABEL_41;
  }
  v17 = &v14[v12];
  v18 = 0;
  v7 = SecurityDescriptor;
  DaclDefaulted = v17;
  while ( 1 )
  {
    StringCchPrintfW(v17, 0x14u, L"EFS%d.TMP", v18);
    if ( RtlDosPathNameToNtPathName_U(*a4, &NtPathName, 0, 0) )
      break;
    LastError = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 10, 110);
LABEL_37:
    v17 = DaclDefaulted;
    if ( ++v18 >= 0x186A0 )
      goto LABEL_38;
  }
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.SecurityDescriptor = v7;
  v20 = NtCreateFile(a2, 0xC0110000, &ObjectAttributes, &IoStatusBlock, 0, 6u, 0, 2u, 0x200020u, 0, 0);
  v8 = v20;
  if ( v20 < 0 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v20, 10, 141);
  if ( v8 == -1073741790 )
  {
    v21 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    v8 = v21;
    if ( v21 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 10, 155);
      goto LABEL_25;
    }
    if ( RpcRevertToSelf() )
      goto LABEL_24;
    v22 = NtCreateFile(a2, 0xC0110000, &ObjectAttributes, &IoStatusBlock, 0, 6u, 0, 2u, 0x200020u, 0, 0);
    v8 = v22;
    if ( v22 < 0 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v22, 10, 182);
    if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u) < 0 )
    {
      if ( v8 >= 0 )
      {
        MarkFileForDelete(*a2);
        CloseHandle(*a2);
        *a2 = 0;
      }
LABEL_24:
      v8 = -1073741790;
    }
  }
LABEL_25:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v8 <= -1073741765 )
  {
    if ( v8 == -1073741765
      || v8 == -1073741809
      || v8 == -1073741790
      || v8 == -1073741774
      || v8 == -1073741767
      || v8 == -1073741766 )
    {
      goto LABEL_41;
    }
    goto LABEL_37;
  }
  if ( v8 != -1073741697 && v8 != -1073741566 && v8 != -1073741183 )
  {
    if ( !v8 )
      goto LABEL_39;
    goto LABEL_37;
  }
LABEL_38:
  if ( v8 < 0 )
    goto LABEL_41;
LABEL_39:
  v23 = NtQueryInformationFile(*a2, &IoStatusBlock, FileInformation, 8u, FileInternalInformation);
  v8 = v23;
  if ( v23 < 0 )
  {
    v24 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v23, 10, 249);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v24, 10, 249);
LABEL_41:
    if ( *a4 )
    {
      EfsFreeHeap((LPVOID)*a4);
      *a4 = 0;
    }
    if ( *a2 )
    {
      MarkFileForDelete(*a2);
      CloseHandle(*a2);
      *a2 = 0;
    }
  }
  if ( v7 )
  {
    LOBYTE(SecurityDescriptor) = 0;
    LOBYTE(DaclDefaulted) = 0;
    Dacl = 0;
    if ( RtlGetDaclSecurityDescriptor(v7, (PBOOLEAN)&SecurityDescriptor, &Dacl, (PBOOLEAN)&DaclDefaulted) >= 0
      && (_BYTE)SecurityDescriptor )
    {
      EfsFreeHeap(Dacl);
    }
    EfsFreeHeap(v7);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001abf0  mov     [rsp-8+FileInformation], r8
0x18001abf5  push    rbp
0x18001abf6  push    rbx
0x18001abf7  push    rsi
0x18001abf8  push    rdi
0x18001abf9  push    r12
0x18001abfb  push    r13
0x18001abfd  push    r14
0x18001abff  push    r15
0x18001ac01  lea     rbp, [rsp-1Fh]
0x18001ac06  sub     rsp, 0C8h
0x18001ac0d  xorps   xmm1, xmm1
0x18001ac10  mov     r12, r9
0x18001ac13  xor     r9d, r9d
0x18001ac16  mov     rsi, rdx
0x18001ac19  xorps   xmm0, xmm0
0x18001ac1c  mov     [rbp+57h+SecurityDescriptor], r9
0x18001ac20  mov     rdx, rcx
0x18001ac23  mov     [rbp+57h+TokenHandle], r9
0x18001ac27  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18001ac2b  lea     eax, [r9+2]
0x18001ac2f  mov     [rsi], r9
0x18001ac32  mov     r14d, r9d
0x18001ac35  mov     [r12], r9
0x18001ac39  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001ac3d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18001ac41  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001ac45  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001ac49  cmp     [rcx], ax
0x18001ac4c  jnb     short loc_18001AC8D
0x18001ac4e  mov     rcx, cs:g_hPublisher
0x18001ac55  lea     edi, [rax+8]
0x18001ac58  mov     r13d, 0C000000Dh
0x18001ac5e  mov     dword ptr [rsp+100h+AllocationSize], 1525h
0x18001ac66  mov     r9d, edi
0x18001ac69  lea     rdx, EFS_API_ERROR
0x18001ac70  mov     r8d, r13d
0x18001ac73  call    fnEfsLogTrace1
0x18001ac78  mov     r8d, r13d
0x18001ac7b  mov     dword ptr [rsp+100h+AllocationSize], 1526h
0x18001ac83  mov     ebx, 0C000000Dh
0x18001ac88  jmp     loc_18001B078
0x18001ac8d  movzx   r8d, word ptr [rcx]
0x18001ac91  lea     rbx, [rcx+8]
0x18001ac95  shr     r8d, 1
0x18001ac98  dec     r8d
0x18001ac9b  test    r8d, r8d
0x18001ac9e  js      short loc_18001ACB4
0x18001aca0  movsxd  rcx, r8d
0x18001aca3  lea     rbx, [rdx+8]
0x18001aca7  mov     rax, [rbx]
0x18001acaa  dec     r8d
0x18001acad  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18001acb2  jnz     short loc_18001AC9B
0x18001acb4  mov     rax, [rbx]
0x18001acb7  mov     edx, r9d
0x18001acba  movsxd  rcx, r8d
0x18001acbd  cmp     word ptr [rax+rcx*2+2], 5Ch ; '\'
0x18001acc3  setz    dl
0x18001acc6  lea     r13d, [rdx+1]
0x18001acca  add     r13d, r8d
0x18001accd  lea     r15d, [r13+14h]
0x18001acd1  mov     ecx, r15d
0x18001acd4  add     rcx, rcx; unsigned __int64
0x18001acd7  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18001acdc  mov     [r12], rax
0x18001ace0  mov     rdi, rax
0x18001ace3  test    rax, rax
0x18001ace6  jnz     short loc_18001AD25
0x18001ace8  mov     rcx, cs:g_hPublisher
0x18001acef  lea     edi, [rax+0Ah]
0x18001acf2  mov     r9d, edi
0x18001acf5  mov     dword ptr [rsp+100h+AllocationSize], 1551h
0x18001acfd  lea     r8d, [r15+r15]
0x18001ad01  lea     rdx, EFS_ERROR_MEMORY
0x18001ad08  call    fnEfsLogTrace1
0x18001ad0d  mov     r8d, 0C000009Ah
0x18001ad13  mov     dword ptr [rsp+100h+AllocationSize], 1552h
0x18001ad1b  mov     ebx, 0C000009Ah
0x18001ad20  jmp     loc_18001B078
0x18001ad25  mov     rdx, [rbx]; Src
0x18001ad28  mov     rcx, rdi; void *
0x18001ad2b  movsxd  rax, r13d
0x18001ad2e  lea     r14, [rax+rax]
0x18001ad32  mov     r8, r14; Size
0x18001ad35  call    memcpy_0
0x18001ad3a  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18001ad3e  call    EfspMakeSystemFullControlSD
0x18001ad43  mov     ebx, eax
0x18001ad45  test    eax, eax
0x18001ad47  jns     short loc_18001AD99
0x18001ad49  mov     rcx, cs:g_hPublisher
0x18001ad50  lea     rdx, EFS_API_ERROR
0x18001ad57  mov     edi, 0Ah
0x18001ad5c  mov     r14d, 1561h
0x18001ad62  mov     r9d, edi
0x18001ad65  mov     dword ptr [rsp+100h+AllocationSize], r14d
0x18001ad6a  mov     r8d, eax
0x18001ad6d  call    fnEfsLogTrace1
0x18001ad72  mov     rcx, cs:g_hPublisher
0x18001ad79  lea     rdx, EFS_TRACE_ERROR
0x18001ad80  mov     r9d, edi
0x18001ad83  mov     dword ptr [rsp+100h+AllocationSize], r14d
0x18001ad88  mov     r8d, eax
0x18001ad8b  call    fnEfsLogTrace1
0x18001ad90  mov     r14, [rbp+57h+SecurityDescriptor]
0x18001ad94  jmp     loc_18001B08E
0x18001ad99  lea     rax, [r14+rdi]
0x18001ad9d  xor     r13d, r13d
0x18001ada0  mov     r14, [rbp+57h+SecurityDescriptor]
0x18001ada4  lea     r15, EFS_API_ERROR
0x18001adab  mov     [rbp+57h+DaclDefaulted], rax
0x18001adaf  lea     edi, [r13+0Ah]
0x18001adb3  mov     r9d, r13d
0x18001adb6  lea     r8, aEfsDTmp; "EFS%d.TMP"
0x18001adbd  mov     edx, 14h; unsigned __int64
0x18001adc2  mov     rcx, rax; unsigned __int16 *
0x18001adc5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001adca  mov     rcx, [r12]; DosPathName
0x18001adce  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18001add2  xor     r9d, r9d; DirectoryInfo
0x18001add5  xor     r8d, r8d; NtFileNamePart
0x18001add8  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18001adde  xor     ecx, ecx
0x18001ade0  test    al, al
0x18001ade2  jnz     short loc_18001AE0C
0x18001ade4  call    cs:__imp_GetLastError
0x18001adea  mov     rcx, cs:g_hPublisher
0x18001adf1  mov     r9d, edi
0x18001adf4  mov     r8d, eax
0x18001adf7  mov     dword ptr [rsp+100h+AllocationSize], 156Eh
0x18001adff  mov     rdx, r15
0x18001ae02  call    fnEfsLogTrace1
0x18001ae07  jmp     loc_18001B013
0x18001ae0c  mov     [rsp+100h+EaLength], ecx; EaLength
0x18001ae10  lea     rax, [rbp+57h+NtPathName]
0x18001ae14  mov     [rsp+100h+EaBuffer], rcx; EaBuffer
0x18001ae19  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001ae1d  mov     [rsp+100h+CreateOptions], 200020h; CreateOptions
0x18001ae25  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001ae29  mov     [rsp+100h+CreateDisposition], 2; CreateDisposition
0x18001ae31  mov     edx, 0C0110000h; DesiredAccess
0x18001ae36  mov     [rsp+100h+ShareAccess], ecx; ShareAccess
0x18001ae3a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x18001ae3e  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rcx
0x18001ae42  mov     [rsp+100h+FileAttributes], 6; FileAttributes
0x18001ae4a  mov     [rsp+100h+AllocationSize], rcx; AllocationSize
0x18001ae4f  mov     rcx, rsi; FileHandle
0x18001ae52  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001ae59  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001ae60  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001ae64  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x18001ae68  call    cs:__imp_NtCreateFile
0x18001ae6e  mov     ebx, eax
0x18001ae70  test    eax, eax
0x18001ae72  jns     short loc_18001AE91
0x18001ae74  mov     rcx, cs:g_hPublisher
0x18001ae7b  mov     r9d, edi
0x18001ae7e  mov     r8d, eax
0x18001ae81  mov     dword ptr [rsp+100h+AllocationSize], 158Dh
0x18001ae89  mov     rdx, r15
0x18001ae8c  call    fnEfsLogTrace1
0x18001ae91  cmp     ebx, 0C0000022h
0x18001ae97  jnz     loc_18001AF91
0x18001ae9d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001aea1  mov     r8b, 1; OpenAsSelf
0x18001aea4  mov     edx, 0Ch; DesiredAccess
0x18001aea9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001aeb0  call    cs:__imp_NtOpenThreadToken
0x18001aeb6  mov     ebx, eax
0x18001aeb8  test    eax, eax
0x18001aeba  jns     short loc_18001AEDE
0x18001aebc  mov     rcx, cs:g_hPublisher
0x18001aec3  mov     r9d, edi
0x18001aec6  mov     r8d, eax
0x18001aec9  mov     dword ptr [rsp+100h+AllocationSize], 159Bh
0x18001aed1  mov     rdx, r15
0x18001aed4  call    fnEfsLogTrace1
0x18001aed9  jmp     loc_18001AF91
0x18001aede  call    cs:__imp_RpcRevertToSelf
0x18001aee4  xor     ecx, ecx
0x18001aee6  test    eax, eax
0x18001aee8  jnz     loc_18001AF8C
0x18001aeee  mov     [rsp+100h+EaLength], ecx; EaLength
0x18001aef2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001aef6  mov     [rsp+100h+EaBuffer], rcx; EaBuffer
0x18001aefb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001aeff  mov     [rsp+100h+CreateOptions], 200020h; CreateOptions
0x18001af07  mov     edx, 0C0110000h; DesiredAccess
0x18001af0c  mov     [rsp+100h+CreateDisposition], 2; CreateDisposition
0x18001af14  mov     [rsp+100h+ShareAccess], ecx; ShareAccess
0x18001af18  mov     [rsp+100h+FileAttributes], 6; FileAttributes
0x18001af20  mov     [rsp+100h+AllocationSize], rcx; AllocationSize
0x18001af25  mov     rcx, rsi; FileHandle
0x18001af28  call    cs:__imp_NtCreateFile
0x18001af2e  mov     ebx, eax
0x18001af30  test    eax, eax
0x18001af32  jns     short loc_18001AF51
0x18001af34  mov     rcx, cs:g_hPublisher
0x18001af3b  mov     r9d, edi
0x18001af3e  mov     r8d, eax
0x18001af41  mov     dword ptr [rsp+100h+AllocationSize], 15B6h
0x18001af49  mov     rdx, r15
0x18001af4c  call    fnEfsLogTrace1
0x18001af51  mov     r9d, 8; ThreadInformationLength
0x18001af57  lea     r8, [rbp+57h+TokenHandle]; ThreadInformation
0x18001af5b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001af62  lea     edx, [r9-3]; ThreadInformationClass
0x18001af66  call    cs:__imp_NtSetInformationThread
0x18001af6c  test    eax, eax
0x18001af6e  jns     short loc_18001AF91
0x18001af70  test    ebx, ebx
0x18001af72  js      short loc_18001AF8C
0x18001af74  mov     rcx, [rsi]
0x18001af77  call    MarkFileForDelete
0x18001af7c  mov     rcx, [rsi]; hObject
0x18001af7f  call    cs:__imp_CloseHandle
0x18001af85  mov     qword ptr [rsi], 0
0x18001af8c  mov     ebx, 0C0000022h
0x18001af91  mov     rcx, gs:60h
0x18001af9a  xor     edx, edx; Flags
0x18001af9c  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18001afa0  mov     rcx, [rcx+30h]; HeapHandle
0x18001afa4  call    cs:__imp_RtlFreeHeap
0x18001afaa  mov     eax, 0C000003Bh
0x18001afaf  cmp     ebx, eax
0x18001afb1  jg      short loc_18001AFF7
0x18001afb3  jz      loc_18001B08E
0x18001afb9  cmp     ebx, 0C000000Fh
0x18001afbf  jz      loc_18001B08E
0x18001afc5  cmp     ebx, 0C0000022h
0x18001afcb  jz      loc_18001B08E
0x18001afd1  cmp     ebx, 0C0000032h
0x18001afd7  jz      loc_18001B08E
0x18001afdd  cmp     ebx, 0C0000039h
0x18001afe3  jz      loc_18001B08E
0x18001afe9  cmp     ebx, 0C000003Ah
0x18001afef  jz      loc_18001B08E
0x18001aff5  jmp     short loc_18001B013
0x18001aff7  cmp     ebx, 0C000007Fh
0x18001affd  jz      short loc_18001B027
0x18001afff  cmp     ebx, 0C0000102h
0x18001b005  jz      short loc_18001B027
0x18001b007  cmp     ebx, 0C0000281h
0x18001b00d  jz      short loc_18001B027
0x18001b00f  test    ebx, ebx
0x18001b011  jz      short loc_18001B02B
0x18001b013  mov     rax, [rbp+57h+DaclDefaulted]
0x18001b017  inc     r13d
0x18001b01a  cmp     r13d, 186A0h
0x18001b021  jb      loc_18001ADB3
0x18001b027  test    ebx, ebx
0x18001b029  js      short loc_18001B08E
0x18001b02b  mov     r8, [rbp+57h+FileInformation]; FileInformation
0x18001b02f  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001b033  mov     rcx, [rsi]; FileHandle
0x18001b036  mov     r9d, 8; Length
0x18001b03c  mov     dword ptr [rsp+100h+AllocationSize], 6; FileInformationClass
0x18001b044  call    cs:__imp_NtQueryInformationFile
0x18001b04a  mov     ebx, eax
0x18001b04c  test    eax, eax
0x18001b04e  jns     short loc_18001B0BD
0x18001b050  mov     rcx, cs:g_hPublisher
0x18001b057  mov     r13d, 15F9h
0x18001b05d  mov     r9d, edi
0x18001b060  mov     dword ptr [rsp+100h+AllocationSize], r13d
0x18001b065  mov     r8d, eax
0x18001b068  mov     rdx, r15
0x18001b06b  call    fnEfsLogTrace1
0x18001b070  mov     r8d, eax
0x18001b073  mov     dword ptr [rsp+100h+AllocationSize], r13d
0x18001b078  mov     rcx, cs:g_hPublisher
0x18001b07f  lea     rdx, EFS_TRACE_ERROR
0x18001b086  mov     r9d, edi
0x18001b089  call    fnEfsLogTrace1
0x18001b08e  mov     rcx, [r12]; lpMem
0x18001b092  xor     edi, edi
0x18001b094  test    rcx, rcx
0x18001b097  jz      short loc_18001B0A2
0x18001b099  call    EfsFreeHeap
0x18001b09e  mov     [r12], rdi
0x18001b0a2  mov     rcx, [rsi]
0x18001b0a5  test    rcx, rcx
0x18001b0a8  jz      short loc_18001B0BF
0x18001b0aa  call    MarkFileForDelete
0x18001b0af  mov     rcx, [rsi]; hObject
0x18001b0b2  call    cs:__imp_CloseHandle
0x18001b0b8  mov     [rsi], rdi
0x18001b0bb  jmp     short loc_18001B0BF
0x18001b0bd  xor     edi, edi
0x18001b0bf  test    r14, r14
0x18001b0c2  jz      short loc_18001B100
0x18001b0c4  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18001b0c8  mov     byte ptr [rbp+57h+SecurityDescriptor], dil
0x18001b0cc  lea     r8, [rbp+57h+Dacl]; Dacl
0x18001b0d0  mov     byte ptr [rbp+57h+DaclDefaulted], dil
0x18001b0d4  lea     rdx, [rbp+57h+SecurityDescriptor]; DaclPresent
0x18001b0d8  mov     [rbp+57h+Dacl], rdi
0x18001b0dc  mov     rcx, r14; SecurityDescriptor
0x18001b0df  call    cs:__imp_RtlGetDaclSecurityDescriptor
  ... truncated ...
```
