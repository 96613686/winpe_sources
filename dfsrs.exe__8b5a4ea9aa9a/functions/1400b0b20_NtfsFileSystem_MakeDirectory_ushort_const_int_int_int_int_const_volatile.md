# NtfsFileSystem::MakeDirectory(ushort const *,int,int,int,int const volatile &)

- ea: `0x1400b0b20`
- end: `0x1400b0e9a`
- name: `?MakeDirectory@NtfsFileSystem@@UEAAPEAVFrsStatus@@PEBGHHHAEDH@Z`
- size: `890`
- prototype: `struct FrsStatus *(NtfsFileSystem *__hidden this, const unsigned __int16 *, int, int, int, const volatile int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x14000ee94`
- `0x140010680`
- `0x1400255c8`
- `0x1400ae800`
- `0x1400aff78`
- `0x1400b0b20`
- `0x1400b2fd4`
- `0x1400b334c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x1400b0c95`
- `KERNEL32!CreateDirectoryW` at `0x1400b0c95`
- `KERNEL32!GetFileAttributesW` at `0x1400b0ce5`
- `KERNEL32!GetFileAttributesW` at `0x1400b0ce5`
- `KERNEL32!GetLastError` at `0x1400b0bab`
- `KERNEL32!GetLastError` at `0x1400b0ca9`
- `KERNEL32!GetLastError` at `0x1400b0d04`
- `KERNEL32!GetLastError` at `0x1400b0bab`
- `KERNEL32!GetLastError` at `0x1400b0ca9`
- `KERNEL32!GetLastError` at `0x1400b0d04`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0b9d`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0cc3`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0cf6`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0d41`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0e1b`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0b9d`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0cc3`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0cf6`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0d41`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0e1b`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400b0c00`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400b0c2e`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400b0c00`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400b0c2e`
- `ADVAPI32!FreeSid` at `0x1400b0ded`
- `ADVAPI32!FreeSid` at `0x1400b0e06`
- `ADVAPI32!FreeSid` at `0x1400b0ded`
- `ADVAPI32!FreeSid` at `0x1400b0e06`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b0b8d`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b0b8d`

## string_xrefs

- `0x1400b0bc8`: `NtfsFileSystem::MakeDirectory`
- `0x1400b0d21`: `NtfsFileSystem::MakeDirectory`
- `0x1400b0d5e`: `NtfsFileSystem::MakeDirectory`
- `0x1400b0e38`: `NtfsFileSystem::MakeDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall NtfsFileSystem::MakeDirectory(
        NtfsFileSystem *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        int a5,
        const volatile int *a6)
{
  __int64 v10; // rdi
  struct FrsStatus *v11; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  const unsigned __int16 *v14; // rdx
  const WCHAR *v15; // rsi
  DWORD v16; // eax
  DWORD v17; // ebx
  __int64 v18; // rcx
  DWORD FileAttributesW; // eax
  NtfsFileSystem *v20; // rcx
  DWORD v21; // ebx
  DWORD v22; // eax
  struct FrsStatus *v23; // rax
  NtfsFileSystem *v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rcx
  int v28; // [rsp+38h] [rbp-39h]
  DWORD v29; // [rsp+40h] [rbp-31h]
  unsigned __int16 *v30; // [rsp+58h] [rbp-19h] BYREF
  PSID pSid; // [rsp+60h] [rbp-11h] BYREF
  PSID v32; // [rsp+68h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-1h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp+7h] BYREF

  v10 = 0;
  v11 = 0;
  SecurityDescriptor = 0;
  v30 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
  if ( a3
    && !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:P(A;CIOI;FA;;;SY)(A;CIOI;FA;;;BA)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v11 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                LastError,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                "NtfsFileSystem::MakeDirectory",
                                1645,
                                CurrentThreadId,
                                0);
  }
  if ( !wcsncmp(a2, L"\\\\?\\", 4u) )
  {
    FrsStringImpl<unsigned short,char>::Set(&v30, a2);
  }
  else
  {
    if ( !wcsncmp(a2, L"\\\\.\\", 4u) )
    {
      FrsStringImpl<unsigned short,char>::Set(&v30, L"\\\\?\\");
      v14 = a2 + 4;
    }
    else
    {
      FrsStringImpl<unsigned short,char>::Set(&v30, L"\\\\?\\");
      v14 = a2;
    }
    FrsStringImpl<unsigned short,char>::Append(&v30, v14);
  }
  if ( v11 )
    goto LABEL_34;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  v15 = v30 + 9;
  if ( !CreateDirectoryW(v30 + 9, &SecurityAttributes) )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 != 183 && v16 != 5 )
    {
      v29 = GetCurrentThreadId();
      v28 = 1704;
LABEL_21:
      v23 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v18,
                                  v17,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                  "NtfsFileSystem::MakeDirectory",
                                  v28,
                                  v29,
                                  0);
      goto LABEL_26;
    }
    FileAttributesW = GetFileAttributesW(v15);
    if ( FileAttributesW == -1 )
    {
      v21 = GetCurrentThreadId();
      v22 = GetLastError();
      v23 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                  v22,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                  "NtfsFileSystem::MakeDirectory",
                                  1681,
                                  v21,
                                  0);
    }
    else
    {
      if ( (FileAttributesW & 0x10) == 0 )
      {
        v29 = GetCurrentThreadId();
        v28 = 1685;
        goto LABEL_21;
      }
      if ( !a3 )
        goto LABEL_35;
      if ( !a4 )
      {
        pSid = 0;
        v32 = 0;
        v11 = NtfsFileSystem::InitializeSids(v20, &pSid, &v32);
        if ( !v11 )
          v11 = NtfsFileSystem::ValidateSecurity(v24, v15, pSid, v32);
        if ( pSid )
        {
          FreeSid(pSid);
          pSid = 0;
        }
        if ( v32 )
        {
          FreeSid(v32);
          v32 = 0;
        }
LABEL_33:
        if ( v11 )
        {
LABEL_34:
          v25 = GetCurrentThreadId();
          v10 = FrsStatusList::PushNewError(
                  v26,
                  *((unsigned int *)v11 + 1),
                  *((unsigned int *)v11 + 2),
                  *(unsigned int *)v11,
                  "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                  "NtfsFileSystem::MakeDirectory",
                  1711,
                  v25,
                  v11);
          goto LABEL_35;
        }
        goto LABEL_35;
      }
      v23 = NtfsFileSystem::SetValidateSecurity(this, v15, SecurityDescriptor, a5, a6);
    }
LABEL_26:
    v11 = v23;
    goto LABEL_33;
  }
LABEL_35:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v30);
  scoped_any<void *,close_fun<void * (*)(void *),&void * LocalFree(void *)>,null_t,0>::~scoped_any<void *,close_fun<void * (*)(void *),&void * LocalFree(void *)>,null_t,0>(&SecurityDescriptor);
  return (struct FrsStatus *)v10;
}

```

## disassembly

```asm
0x1400b0b20  mov     rax, rsp
0x1400b0b23  mov     [rax+8], rbx
0x1400b0b27  mov     [rax+10h], rsi
0x1400b0b2b  mov     [rax+18h], rdi
0x1400b0b2f  push    rbp
0x1400b0b30  push    r12
0x1400b0b32  push    r13
0x1400b0b34  push    r14
0x1400b0b36  push    r15
0x1400b0b38  lea     rbp, [rax-4Fh]
0x1400b0b3c  sub     rsp, 90h
0x1400b0b43  mov     r15d, r9d
0x1400b0b46  mov     r14d, r8d
0x1400b0b49  mov     rsi, rdx
0x1400b0b4c  mov     r12, rcx
0x1400b0b4f  xor     edi, edi
0x1400b0b51  mov     ebx, edi
0x1400b0b53  mov     [rbp+47h+SecurityDescriptor], rdi
0x1400b0b57  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400b0b5e  mov     [rbp+47h+var_60], rax
0x1400b0b62  lea     r13d, [rdi+1]
0x1400b0b66  cmp     cs:byte_140315A80, dil
0x1400b0b6d  jnz     short loc_1400B0B77
0x1400b0b6f  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r13d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400b0b77  test    r14d, r14d
0x1400b0b7a  jz      short loc_1400B0BF0
0x1400b0b7c  xor     r9d, r9d; SecurityDescriptorSize
0x1400b0b7f  lea     r8, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x1400b0b83  mov     edx, r13d; StringSDRevision
0x1400b0b86  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:P(A;CIOI;FA;;;SY)(A;CIOI;FA;;"...
0x1400b0b8d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400b0b94  nop     dword ptr [rax+rax+00h]
0x1400b0b99  test    eax, eax
0x1400b0b9b  jnz     short loc_1400B0BF0
0x1400b0b9d  call    cs:__imp_GetCurrentThreadId
0x1400b0ba4  nop     dword ptr [rax+rax+00h]
0x1400b0ba9  mov     ebx, eax
0x1400b0bab  call    cs:__imp_GetLastError
0x1400b0bb2  nop     dword ptr [rax+rax+00h]
0x1400b0bb7  mov     [rsp+0B0h+var_70], rdi
0x1400b0bbc  mov     dword ptr [rsp+0B0h+var_78], ebx
0x1400b0bc0  mov     [rsp+0B0h+var_80], 66Dh
0x1400b0bc8  lea     rcx, aNtfsfilesystem_27; "NtfsFileSystem::MakeDirectory"
0x1400b0bcf  mov     qword ptr [rsp+0B0h+var_88], rcx
0x1400b0bd4  lea     rcx, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b0bdb  mov     [rsp+0B0h+var_90], rcx
0x1400b0be0  mov     r9d, r13d
0x1400b0be3  xor     r8d, r8d
0x1400b0be6  mov     edx, eax
0x1400b0be8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b0bed  mov     rbx, rax
0x1400b0bf0  mov     r8d, 4; MaxCount
0x1400b0bf6  lea     rdx, String2; "\\\\?\\"
0x1400b0bfd  mov     rcx, rsi; String1
0x1400b0c00  call    cs:__imp_wcsncmp
0x1400b0c07  nop     dword ptr [rax+rax+00h]
0x1400b0c0c  test    eax, eax
0x1400b0c0e  jnz     short loc_1400B0C1E
0x1400b0c10  mov     rdx, rsi
0x1400b0c13  lea     rcx, [rbp+47h+var_60]
0x1400b0c17  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400b0c1c  jmp     short loc_1400B0C65
0x1400b0c1e  mov     r8d, 4; MaxCount
0x1400b0c24  lea     rdx, asc_140244CD8; "\\\\.\\"
0x1400b0c2b  mov     rcx, rsi; String1
0x1400b0c2e  call    cs:__imp_wcsncmp
0x1400b0c35  nop     dword ptr [rax+rax+00h]
0x1400b0c3a  lea     rdx, String2; "\\\\?\\"
0x1400b0c41  lea     rcx, [rbp+47h+var_60]
0x1400b0c45  test    eax, eax
0x1400b0c47  jnz     short loc_1400B0C54
0x1400b0c49  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400b0c4e  lea     rdx, [rsi+8]
0x1400b0c52  jmp     short loc_1400B0C5C
0x1400b0c54  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400b0c59  mov     rdx, rsi
0x1400b0c5c  lea     rcx, [rbp+47h+var_60]
0x1400b0c60  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400b0c65  test    rbx, rbx
0x1400b0c68  jnz     loc_1400B0E1B
0x1400b0c6e  mov     qword ptr [rbp+47h+SecurityAttributes.nLength], 18h
0x1400b0c76  mov     qword ptr [rbp+47h+SecurityAttributes.bInheritHandle], 1
0x1400b0c7e  mov     rax, [rbp+47h+SecurityDescriptor]
0x1400b0c82  mov     [rbp+47h+SecurityAttributes.lpSecurityDescriptor], rax
0x1400b0c86  mov     rsi, [rbp+47h+var_60]
0x1400b0c8a  add     rsi, 12h
0x1400b0c8e  lea     rdx, [rbp+47h+SecurityAttributes]; lpSecurityAttributes
0x1400b0c92  mov     rcx, rsi; lpPathName
0x1400b0c95  call    cs:__imp_CreateDirectoryW
0x1400b0c9c  nop     dword ptr [rax+rax+00h]
0x1400b0ca1  test    eax, eax
0x1400b0ca3  jnz     loc_1400B0E62
0x1400b0ca9  call    cs:__imp_GetLastError
0x1400b0cb0  nop     dword ptr [rax+rax+00h]
0x1400b0cb5  mov     ebx, eax
0x1400b0cb7  cmp     eax, 0B7h
0x1400b0cbc  jz      short loc_1400B0CE2
0x1400b0cbe  cmp     eax, 5
0x1400b0cc1  jz      short loc_1400B0CE2
0x1400b0cc3  call    cs:__imp_GetCurrentThreadId
0x1400b0cca  nop     dword ptr [rax+rax+00h]
0x1400b0ccf  mov     [rsp+0B0h+var_70], rdi
0x1400b0cd4  mov     dword ptr [rsp+0B0h+var_78], eax
0x1400b0cd8  mov     [rsp+0B0h+var_80], 6A8h
0x1400b0ce0  jmp     short loc_1400B0D5E
0x1400b0ce2  mov     rcx, rsi; lpFileName
0x1400b0ce5  call    cs:__imp_GetFileAttributesW
0x1400b0cec  nop     dword ptr [rax+rax+00h]
0x1400b0cf1  cmp     eax, 0FFFFFFFFh
0x1400b0cf4  jnz     short loc_1400B0D3D
0x1400b0cf6  call    cs:__imp_GetCurrentThreadId
0x1400b0cfd  nop     dword ptr [rax+rax+00h]
0x1400b0d02  mov     ebx, eax
0x1400b0d04  call    cs:__imp_GetLastError
0x1400b0d0b  nop     dword ptr [rax+rax+00h]
0x1400b0d10  mov     [rsp+0B0h+var_70], rdi
0x1400b0d15  mov     dword ptr [rsp+0B0h+var_78], ebx
0x1400b0d19  mov     [rsp+0B0h+var_80], 691h
0x1400b0d21  lea     rcx, aNtfsfilesystem_27; "NtfsFileSystem::MakeDirectory"
0x1400b0d28  mov     qword ptr [rsp+0B0h+var_88], rcx
0x1400b0d2d  lea     rcx, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b0d34  mov     [rsp+0B0h+var_90], rcx
0x1400b0d39  mov     edx, eax
0x1400b0d3b  jmp     short loc_1400B0D78
0x1400b0d3d  test    al, 10h
0x1400b0d3f  jnz     short loc_1400B0D85
0x1400b0d41  call    cs:__imp_GetCurrentThreadId
0x1400b0d48  nop     dword ptr [rax+rax+00h]
0x1400b0d4d  mov     [rsp+0B0h+var_70], rdi
0x1400b0d52  mov     dword ptr [rsp+0B0h+var_78], eax
0x1400b0d56  mov     [rsp+0B0h+var_80], 695h
0x1400b0d5e  lea     rax, aNtfsfilesystem_27; "NtfsFileSystem::MakeDirectory"
0x1400b0d65  mov     qword ptr [rsp+0B0h+var_88], rax
0x1400b0d6a  lea     rax, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b0d71  mov     [rsp+0B0h+var_90], rax
0x1400b0d76  mov     edx, ebx
0x1400b0d78  xor     r8d, r8d
0x1400b0d7b  mov     r9d, r13d
0x1400b0d7e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b0d83  jmp     short loc_1400B0DAF
0x1400b0d85  test    r14d, r14d
0x1400b0d88  jz      loc_1400B0E62
0x1400b0d8e  test    r15d, r15d
0x1400b0d91  jz      short loc_1400B0DB4
0x1400b0d93  mov     rax, [rbp+47h+arg_28]
0x1400b0d97  mov     [rsp+0B0h+var_90], rax; volatile int *
0x1400b0d9c  mov     r9d, [rbp+47h+arg_20]; int
0x1400b0da0  mov     r8, [rbp+47h+SecurityDescriptor]; void *
0x1400b0da4  mov     rdx, rsi; unsigned __int16 *
0x1400b0da7  mov     rcx, r12; this
0x1400b0daa  call    ?SetValidateSecurity@NtfsFileSystem@@AEAAPEAVFrsStatus@@PEBGPEAXHAEDH@Z; NtfsFileSystem::SetValidateSecurity(ushort const *,void *,int,int const volatile &)
0x1400b0daf  mov     rbx, rax
0x1400b0db2  jmp     short loc_1400B0E16
0x1400b0db4  mov     [rbp+47h+pSid], rdi
0x1400b0db8  mov     [rbp+47h+var_50], rdi
0x1400b0dbc  lea     r8, [rbp+47h+var_50]; void **
0x1400b0dc0  lea     rdx, [rbp+47h+pSid]; void **
0x1400b0dc4  call    ?InitializeSids@NtfsFileSystem@@AEAAPEAVFrsStatus@@AEAPEAX0@Z; NtfsFileSystem::InitializeSids(void * &,void * &)
0x1400b0dc9  mov     rbx, rax
0x1400b0dcc  test    rax, rax
0x1400b0dcf  jnz     short loc_1400B0DE4
0x1400b0dd1  mov     r9, [rbp+47h+var_50]; void *
0x1400b0dd5  mov     r8, [rbp+47h+pSid]; void *
0x1400b0dd9  mov     rdx, rsi; unsigned __int16 *
0x1400b0ddc  call    ?ValidateSecurity@NtfsFileSystem@@AEAAPEAVFrsStatus@@PEBGQEAX1@Z; NtfsFileSystem::ValidateSecurity(ushort const *,void * const,void * const)
0x1400b0de1  mov     rbx, rax
0x1400b0de4  mov     rcx, [rbp+47h+pSid]; pSid
0x1400b0de8  test    rcx, rcx
0x1400b0deb  jz      short loc_1400B0DFD
0x1400b0ded  call    cs:__imp_FreeSid
0x1400b0df4  nop     dword ptr [rax+rax+00h]
0x1400b0df9  mov     [rbp+47h+pSid], rdi
0x1400b0dfd  mov     rcx, [rbp+47h+var_50]; pSid
0x1400b0e01  test    rcx, rcx
0x1400b0e04  jz      short loc_1400B0E16
0x1400b0e06  call    cs:__imp_FreeSid
0x1400b0e0d  nop     dword ptr [rax+rax+00h]
0x1400b0e12  mov     [rbp+47h+var_50], rdi
0x1400b0e16  test    rbx, rbx
0x1400b0e19  jz      short loc_1400B0E62
0x1400b0e1b  call    cs:__imp_GetCurrentThreadId
0x1400b0e22  nop     dword ptr [rax+rax+00h]
0x1400b0e27  mov     [rsp+0B0h+var_70], rbx
0x1400b0e2c  mov     dword ptr [rsp+0B0h+var_78], eax
0x1400b0e30  mov     [rsp+0B0h+var_80], 6AFh
0x1400b0e38  lea     rax, aNtfsfilesystem_27; "NtfsFileSystem::MakeDirectory"
0x1400b0e3f  mov     qword ptr [rsp+0B0h+var_88], rax
0x1400b0e44  lea     rax, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b0e4b  mov     [rsp+0B0h+var_90], rax
0x1400b0e50  mov     r9d, [rbx]
0x1400b0e53  mov     r8d, [rbx+8]
0x1400b0e57  mov     edx, [rbx+4]
0x1400b0e5a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b0e5f  mov     rdi, rax
0x1400b0e62  lea     rcx, [rbp+47h+var_60]
0x1400b0e66  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400b0e6b  nop
0x1400b0e6c  lea     rcx, [rbp+47h+SecurityDescriptor]
0x1400b0e70  call    ??1?$scoped_any@PEAXU?$close_fun@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<void *,close_fun<void * (*)(void *),&LocalFree(void *)>,null_t,0>::~scoped_any<void *,close_fun<void * (*)(void *),&LocalFree(void *)>,null_t,0>(void)
0x1400b0e75  mov     rax, rdi
0x1400b0e78  lea     r11, [rsp+0B0h+var_20]
0x1400b0e80  mov     rbx, [r11+30h]
0x1400b0e84  mov     rsi, [r11+38h]
0x1400b0e88  mov     rdi, [r11+40h]
0x1400b0e8c  mov     rsp, r11
0x1400b0e8f  pop     r15
0x1400b0e91  pop     r14
0x1400b0e93  pop     r13
0x1400b0e95  pop     r12
0x1400b0e97  pop     rbp
0x1400b0e98  retn
```
