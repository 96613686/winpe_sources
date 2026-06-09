# BaseDllOpenIniFileOnDisk

- ea: `0x180010720`
- end: `0x180010d68`
- name: `BaseDllOpenIniFileOnDisk`
- size: `1608`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001057c`
- `0x18004d650`

## callees

- `0x180010720`
- `0x1800122f0`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180010c7e`
- `ntdll!RtlAppendUnicodeToString` at `0x180010c7e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180010c95`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180010c95`
- `ntdll!NtOpenFile` at `0x180010a23`
- `ntdll!NtOpenFile` at `0x180010a23`
- `ntdll!NtClose` at `0x180010a46`
- `ntdll!NtClose` at `0x180010a46`
- `ntdll!NtQueryInformationFile` at `0x180010b90`
- `ntdll!NtQueryInformationFile` at `0x180010b90`
- `ntdll!RtlFreeUnicodeString` at `0x180010958`
- `ntdll!RtlFreeUnicodeString` at `0x180010958`
- `ntdll!NtCreateFile` at `0x180010b0b`
- `ntdll!NtCreateFile` at `0x180010b0b`
- `ntdll!wcscspn` at `0x180010c1d`
- `ntdll!wcscspn` at `0x180010c1d`
- `ntdll!NtUnlockFile` at `0x180010cc7`
- `ntdll!NtUnlockFile` at `0x180010cf4`
- `ntdll!NtUnlockFile` at `0x180010cc7`
- `ntdll!NtUnlockFile` at `0x180010cf4`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180010935`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180010935`
- `ntdll!NtReadFile` at `0x18001081f`
- `ntdll!NtReadFile` at `0x18001081f`
- `ntdll!NtLockFile` at `0x180010b62`
- `ntdll!NtLockFile` at `0x180010b62`
- `ntdll!RtlCopyUnicodeString` at `0x18001094e`
- `ntdll!RtlCopyUnicodeString` at `0x1800109b6`
- `ntdll!RtlCopyUnicodeString` at `0x180010c6e`
- `ntdll!RtlCopyUnicodeString` at `0x18001094e`
- `ntdll!RtlCopyUnicodeString` at `0x1800109b6`
- `ntdll!RtlCopyUnicodeString` at `0x180010c6e`
- `ntdll!RtlIsTextUnicode` at `0x180010855`
- `ntdll!RtlIsTextUnicode` at `0x180010855`
- `ntdll!NtAllocateVirtualMemory` at `0x1800107da`
- `ntdll!NtAllocateVirtualMemory` at `0x180010bf1`
- `ntdll!NtAllocateVirtualMemory` at `0x1800107da`
- `ntdll!NtAllocateVirtualMemory` at `0x180010bf1`
- `ntdll!RtlFreeHeap` at `0x180010a5e`
- `ntdll!RtlFreeHeap` at `0x180010a5e`
- `ntdll!RtlAllocateHeap` at `0x180010988`
- `ntdll!RtlAllocateHeap` at `0x180010988`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180010911`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18001095e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180010c61`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180010911`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18001095e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180010c61`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800108ee`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800108ee`

## pseudocode

```c
__int64 __fastcall BaseDllOpenIniFileOnDisk(__int64 a1, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v4; // rdi
  UNICODE_STRING *v5; // r14
  const wchar_t **v6; // rbx
  NTSTATUS appended; // edi
  struct _UNICODE_STRING *v9; // rbx
  __int64 v10; // rdx
  PVOID v11; // rcx
  BOOLEAN IsTextUnicode; // al
  __int64 v13; // rcx
  _WORD *v14; // r8
  _WORD *v15; // rdx
  unsigned int v16; // eax
  _WORD *v17; // rcx
  int v18; // eax
  int v19; // eax
  DWORD FullPathNameW; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  _DWORD *v31; // rax
  struct _UNICODE_STRING *Heap; // rax
  void **p_Buffer; // rcx
  NTSTATUS v34; // eax
  HANDLE Buffer; // rcx
  unsigned int v36; // eax
  _DWORD *v37; // rcx
  int v38; // eax
  HANDLE *v39; // r14
  NTSTATUS v40; // eax
  NTSTATUS v41; // eax
  __int64 v42; // rdx
  PVOID *v43; // r15
  bool v44; // cf
  __int64 v45; // rax
  size_t v46; // rax
  __int64 GlobalData; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  INT Flags; // [rsp+100h] [rbp+67h] BYREF
  union _LARGE_INTEGER Length; // [rsp+108h] [rbp+6Fh] BYREF
  union _LARGE_INTEGER v53; // [rsp+110h] [rbp+77h] BYREF
  LPWSTR FilePart; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = *(unsigned __int16 *)(a1 + 40);
  v5 = (UNICODE_STRING *)(a1 + 56);
  v6 = (const wchar_t **)(a1 + 48);
  FilePart = 0;
  v53.QuadPart = 0;
  Length.QuadPart = 0;
  *(_WORD *)(a1 + 56) = 0;
  NtPathName = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( (unsigned int)v4 > 2 )
  {
    if ( (*v6)[1] == 58 )
      goto LABEL_20;
  }
  else if ( !(_WORD)v4 )
  {
    goto LABEL_3;
  }
  v46 = wcscspn(*v6, L"\\/");
  a2 = v4 >> 1;
  if ( v46 == v4 >> 1 )
  {
LABEL_3:
    if ( !gpTermsrvBuildIniFileName || (appended = gpTermsrvBuildIniFileName(v5, a1 + 24), appended < 0) )
    {
      GlobalData = KernelBaseGetGlobalData(a1, a2, a3, a4);
      RtlCopyUnicodeString(v5, (PCUNICODE_STRING)(GlobalData + 8));
      appended = RtlAppendUnicodeToString(v5, L"\\");
      if ( appended >= 0 )
        appended = RtlAppendUnicodeStringToString(v5, (PCUNICODE_STRING)(a1 + 24));
    }
    v9 = 0;
    if ( appended < 0 )
      return (unsigned int)appended;
    goto LABEL_23;
  }
LABEL_20:
  FullPathNameW = GetFullPathNameW(*v6, *(unsigned __int16 *)(a1 + 58) >> 1, *(LPWSTR *)(a1 + 64), &FilePart);
  v25 = *(unsigned __int16 *)(a1 + 58) >> 1;
  if ( FullPathNameW > (unsigned int)v25 )
    return (unsigned int)-1073741789;
  if ( !FullPathNameW )
    return (unsigned int)-1073741823;
  v5->Length = 2 * FullPathNameW;
  v26 = KernelBaseGetGlobalData(v25, v22, v23, v24);
  TermsrvConvertSysRootToUserDir(v5, v26 + 8);
  v9 = 0;
LABEL_23:
  if ( !RtlDosPathNameToNtPathName_U(*(PCWSTR *)(a1 + 64), &NtPathName, (PCWSTR *)&FilePart, 0) )
  {
    appended = -1073741766;
    goto LABEL_66;
  }
  RtlCopyUnicodeString(v5, &NtPathName);
  RtlFreeUnicodeString(&NtPathName);
  v31 = (_DWORD *)KernelBaseGetGlobalData(v28, v27, v29, v30);
  Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(
                                     NtCurrentPeb()->ProcessHeap,
                                     (*v31 + 0x80000) | 8u,
                                     *(unsigned __int16 *)(a1 + 58) + 160LL);
  v9 = Heap;
  if ( Heap )
  {
    Heap[1].Buffer = &Heap[10].Length;
    Heap[1].MaximumLength = *(_WORD *)(a1 + 58);
    RtlCopyUnicodeString(Heap + 1, v5);
    *(_QWORD *)&v9[2].Length = *(_QWORD *)(a1 + 8);
    LOBYTE(v9[3].Length) = *(_BYTE *)(a1 + 4);
    if ( gpTermsrvCORIniFile )
      gpTermsrvCORIniFile(&v9[1]);
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    p_Buffer = (void **)&v9[2].Buffer;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = v9 + 1;
    if ( LOBYTE(v9[3].Length) )
      v34 = NtCreateFile(p_Buffer, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0x60u, 0, 0);
    else
      v34 = NtOpenFile(p_Buffer, 0x80100000, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
    appended = v34;
    if ( v34 < 0 )
      goto LABEL_30;
    LOBYTE(v9[3].MaximumLength) = 0;
    v39 = (HANDLE *)&v9[2].Buffer;
    v53.QuadPart = 0;
    Length.QuadPart = -1;
    v40 = NtLockFile(v9[2].Buffer, 0, 0, 0, &IoStatusBlock, &v53, &Length, LockFileKey, 0, v9[3].Length);
    if ( v40 < 0 )
    {
      appended = 0;
      if ( v40 != -1073741637 )
        appended = v40;
      if ( appended < 0 )
        goto LABEL_30;
    }
    else
    {
      LOBYTE(v9[3].MaximumLength) = 1;
    }
    v41 = NtQueryInformationFile(*v39, &IoStatusBlock, &v9[8].Buffer, 0x18u, FileStandardInformation);
    appended = v41;
    if ( v41 == -2147483643 || v41 >= 0 )
    {
      v42 = *(unsigned int *)&v9[9].Length;
      v43 = (PVOID *)&v9[3].Buffer;
      v44 = HIBYTE(v9[3].Length) != 0;
      *(_DWORD *)(&v9[3].MaximumLength + 1) = v42;
      v45 = v42 + (v44 ? 8LL : 4LL);
      *(_QWORD *)&v9[4].Length = v45;
      v9[4].Buffer = (PWSTR)(v45 + 0x100000);
      appended = NtAllocateVirtualMemory(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   (PVOID *)&v9[3].Buffer,
                   0,
                   (PSIZE_T)&v9[4].Buffer,
                   0x2000u,
                   4u);
      if ( appended >= 0 )
      {
        appended = NtAllocateVirtualMemory(
                     (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                     (PVOID *)&v9[3].Buffer,
                     0,
                     (PSIZE_T)&v9[4].Length,
                     0x1000u,
                     4u);
        if ( appended >= 0 )
        {
          appended = NtReadFile(
                       v9[2].Buffer,
                       0,
                       0,
                       0,
                       &IoStatusBlock,
                       *v43,
                       *(_DWORD *)(&v9[3].MaximumLength + 1),
                       0,
                       &LockFileKey);
          if ( appended >= 0 )
          {
            v10 = *(unsigned int *)(&v9[3].MaximumLength + 1);
            if ( IoStatusBlock.Information == v10 )
            {
              v11 = *v43;
              Flags = -1;
              *(_DWORD *)&v9[5].Length = -1;
              *(_DWORD *)(&v9[5].MaximumLength + 1) = 0;
              IsTextUnicode = RtlIsTextUnicode(v11, v10, &Flags);
              v13 = *(unsigned int *)(&v9[3].MaximumLength + 1);
              v14 = *v43;
              HIBYTE(v9[3].Length) = IsTextUnicode;
              v15 = (_WORD *)((char *)v14 + v13);
              if ( IsTextUnicode )
              {
                if ( v15 <= v14 )
                {
                  v36 = v13;
                }
                else
                {
                  do
                  {
                    --v15;
                    v36 = v13;
                    if ( *v15 == 10 )
                      break;
                    if ( *v15 > 0x20u )
                      break;
                    if ( *v15 == 13 )
                      break;
                    v36 = v13 - 2;
                    *(_DWORD *)(&v9[3].MaximumLength + 1) = v13 - 2;
                    LODWORD(v13) = v13 - 2;
                  }
                  while ( v15 > v14 );
                }
                v37 = (_DWORD *)((char *)v14 + v36);
                if ( v37 <= (_DWORD *)v14 || *((_WORD *)v37 - 1) == 10 )
                  goto LABEL_17;
                *v37 = 655373;
                v38 = *(_DWORD *)(&v9[3].MaximumLength + 1);
                *(_DWORD *)&v9[5].Length = v38;
                v19 = v38 + 4;
              }
              else
              {
                if ( v15 <= v14 )
                {
                  v16 = v13;
                }
                else
                {
                  do
                  {
                    v15 = (_WORD *)((char *)v15 - 1);
                    v16 = v13;
                    if ( *(_BYTE *)v15 == 10 )
                      break;
                    if ( *(_BYTE *)v15 > 0x20u )
                      break;
                    if ( *(_BYTE *)v15 == 13 )
                      break;
                    v16 = v13 - 1;
                    *(_DWORD *)(&v9[3].MaximumLength + 1) = v13 - 1;
                    LODWORD(v13) = v13 - 1;
                  }
                  while ( v15 > v14 );
                }
                v17 = (_WORD *)((char *)v14 + v16);
                if ( v17 <= v14 || *((_BYTE *)v17 - 1) == 10 )
                  goto LABEL_17;
                *v17 = 2573;
                v18 = *(_DWORD *)(&v9[3].MaximumLength + 1);
                *(_DWORD *)&v9[5].Length = v18;
                v19 = v18 + 2;
              }
              *(_DWORD *)(&v9[3].MaximumLength + 1) = v19;
              *(_DWORD *)(&v9[5].MaximumLength + 1) = v19;
LABEL_17:
              *(_QWORD *)(a1 + 16) = v9;
              return (unsigned int)appended;
            }
            appended = -1073741807;
          }
        }
      }
      if ( LOBYTE(v9[3].MaximumLength) )
      {
        v53.QuadPart = 0;
        Length.QuadPart = -1;
        NtUnlockFile(*v39, &IoStatusBlock, &v53, &Length, LockFileKey);
      }
      Buffer = *v39;
LABEL_33:
      NtClose(Buffer);
LABEL_34:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      return (unsigned int)appended;
    }
LABEL_66:
    if ( !v9 )
      return (unsigned int)appended;
LABEL_30:
    if ( LOBYTE(v9[3].MaximumLength) )
    {
      v53.QuadPart = 0;
      Length.QuadPart = -1;
      NtUnlockFile(v9[2].Buffer, &IoStatusBlock, &v53, &Length, LockFileKey);
    }
    Buffer = v9[2].Buffer;
    if ( !Buffer )
      goto LABEL_34;
    goto LABEL_33;
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x180010720  push    rbp
0x180010722  push    rbx
0x180010723  push    rsi
0x180010724  push    rdi
0x180010725  push    r12
0x180010727  push    r13
0x180010729  push    r14
0x18001072b  push    r15
0x18001072d  lea     rbp, [rsp-1Fh]
0x180010732  sub     rsp, 0B8h
0x180010739  movzx   edi, word ptr [rcx+28h]
0x18001073d  lea     r14, [rcx+38h]
0x180010741  xorps   xmm0, xmm0
0x180010744  lea     rbx, [rcx+30h]
0x180010748  xor     r13d, r13d
0x18001074b  xor     eax, eax
0x18001074d  mov     [rbp+57h+FilePart], r13
0x180010751  mov     rsi, rcx
0x180010754  mov     qword ptr [rbp+57h+arg_10], r13
0x180010758  mov     qword ptr [rbp+57h+arg_8], r13
0x18001075c  mov     [r14], r13w
0x180010760  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180010764  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180010768  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18001076c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180010770  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180010774  cmp     edi, 2
0x180010777  ja      loc_1800108CF
0x18001077d  test    di, di
0x180010780  jnz     loc_180010C13
0x180010786  mov     rax, cs:gpTermsrvBuildIniFileName
0x18001078d  test    rax, rax
0x180010790  jz      loc_180010C61
0x180010796  lea     rdx, [rsi+18h]
0x18001079a  mov     rcx, r14
0x18001079d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107a2  mov     edi, eax
0x1800107a4  test    eax, eax
0x1800107a6  js      loc_180010C61
0x1800107ac  mov     rbx, r13
0x1800107af  test    edi, edi
0x1800107b1  jns     loc_180010926
0x1800107b7  jmp     loc_1800108B9
0x1800107bc  mov     [rsp+0F0h+Protect], 4; Protect
0x1800107c4  lea     r9, [rbx+40h]; RegionSize
0x1800107c8  xor     r8d, r8d; ZeroBits
0x1800107cb  mov     [rsp+0F0h+AllocationType], 1000h; AllocationType
0x1800107d3  mov     rdx, r15; BaseAddress
0x1800107d6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800107da  call    cs:__imp_NtAllocateVirtualMemory
0x1800107e0  mov     edi, eax
0x1800107e2  test    eax, eax
0x1800107e4  js      loc_180010C01
0x1800107ea  mov     rcx, [rbx+28h]; FileHandle
0x1800107ee  lea     rax, LockFileKey
0x1800107f5  mov     [rsp+0F0h+Key], rax; Key
0x1800107fa  xor     r9d, r9d; ApcContext
0x1800107fd  mov     eax, [rbx+34h]
0x180010800  xor     r8d, r8d; ApcRoutine
0x180010803  mov     [rsp+0F0h+ByteOffset], r13; ByteOffset
0x180010808  xor     edx, edx; Event
0x18001080a  mov     [rsp+0F0h+Length], eax; Length
0x18001080e  mov     rax, [r15]
0x180010811  mov     qword ptr [rsp+0F0h+Protect], rax; Buffer
0x180010816  lea     rax, [rbp+57h+IoStatusBlock]
0x18001081a  mov     qword ptr [rsp+0F0h+AllocationType], rax; IoStatusBlock
0x18001081f  call    cs:__imp_NtReadFile
0x180010825  mov     edi, eax
0x180010827  test    eax, eax
0x180010829  js      loc_180010C01
0x18001082f  mov     edx, [rbx+34h]; Size
0x180010832  cmp     [rbp+57h+IoStatusBlock.Information], rdx
0x180010836  jnz     loc_180010D50
0x18001083c  mov     rcx, [r15]; Buffer
0x18001083f  lea     r8, [rbp+57h+Flags]; Flags
0x180010843  mov     [rbp+57h+Flags], 0FFFFFFFFh
0x18001084a  mov     dword ptr [rbx+50h], 0FFFFFFFFh
0x180010851  mov     [rbx+54h], r13d
0x180010855  call    cs:__imp_RtlIsTextUnicode
0x18001085b  mov     ecx, [rbx+34h]
0x18001085e  mov     r10d, 0Dh
0x180010864  mov     r8, [r15]
0x180010867  mov     [rbx+31h], al
0x18001086a  lea     r9d, [r10-3]
0x18001086e  lea     rdx, [rcx+r8]
0x180010872  test    al, al
0x180010874  jnz     loc_180010A69
0x18001087a  cmp     rdx, r8
0x18001087d  jbe     loc_180010D5A
0x180010883  dec     rdx
0x180010886  mov     eax, ecx
0x180010888  cmp     [rdx], r9b
0x18001088b  jnz     loc_180010AAB
0x180010891  mov     ecx, eax
0x180010893  add     rcx, r8
0x180010896  cmp     rcx, r8
0x180010899  jbe     short loc_1800108B5
0x18001089b  cmp     [rcx-1], r9b
0x18001089f  jz      short loc_1800108B5
0x1800108a1  mov     word ptr [rcx], 0A0Dh
0x1800108a6  mov     eax, [rbx+34h]
0x1800108a9  mov     [rbx+50h], eax
0x1800108ac  add     eax, 2
0x1800108af  mov     [rbx+34h], eax
0x1800108b2  mov     [rbx+54h], eax
0x1800108b5  mov     [rsi+10h], rbx
0x1800108b9  mov     eax, edi
0x1800108bb  add     rsp, 0B8h
0x1800108c2  pop     r15
0x1800108c4  pop     r14
0x1800108c6  pop     r13
0x1800108c8  pop     r12
0x1800108ca  pop     rdi
0x1800108cb  pop     rsi
0x1800108cc  pop     rbx
0x1800108cd  pop     rbp
0x1800108ce  retn
0x1800108cf  mov     rax, [rbx]
0x1800108d2  cmp     word ptr [rax+2], 3Ah ; ':'
0x1800108d7  jnz     loc_180010C13
0x1800108dd  movzx   edx, word ptr [rsi+3Ah]
0x1800108e1  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x1800108e5  mov     r8, [rsi+40h]; lpBuffer
0x1800108e9  mov     rcx, [rbx]; lpFileName
0x1800108ec  shr     edx, 1; nBufferLength
0x1800108ee  call    cs:__imp_GetFullPathNameW
0x1800108f4  movzx   ecx, word ptr [rsi+3Ah]
0x1800108f8  shr     ecx, 1
0x1800108fa  cmp     eax, ecx
0x1800108fc  ja      loc_180010D25
0x180010902  test    eax, eax
0x180010904  jz      loc_180010D2F
0x18001090a  add     ax, ax
0x18001090d  mov     [r14], ax
0x180010911  call    cs:__imp_KernelBaseGetGlobalData
0x180010917  mov     rcx, r14
0x18001091a  lea     rdx, [rax+8]
0x18001091e  call    TermsrvConvertSysRootToUserDir
0x180010923  mov     rbx, r13
0x180010926  mov     rcx, [rsi+40h]; DosPathName
0x18001092a  lea     r8, [rbp+57h+FilePart]; NtFileNamePart
0x18001092e  xor     r9d, r9d; DirectoryInfo
0x180010931  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180010935  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18001093b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001093f  test    al, al
0x180010941  jz      loc_180010D61
0x180010947  lea     rdx, [rbp+57h+NtPathName]; SourceString
0x18001094b  mov     rcx, r14; DestinationString
0x18001094e  call    cs:__imp_RtlCopyUnicodeString
0x180010954  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x180010958  call    cs:__imp_RtlFreeUnicodeString
0x18001095e  call    cs:__imp_KernelBaseGetGlobalData
0x180010964  mov     rcx, gs:60h
0x18001096d  movzx   r8d, word ptr [rsi+3Ah]
0x180010972  add     r8, 0A0h; Size
0x180010979  mov     edx, [rax]
0x18001097b  mov     rcx, [rcx+30h]; HeapHandle
0x18001097f  add     edx, 80000h
0x180010985  or      edx, 8; Flags
0x180010988  call    cs:__imp_RtlAllocateHeap
0x18001098e  mov     rbx, rax
0x180010991  test    rax, rax
0x180010994  jz      loc_180010D39
0x18001099a  add     rax, 0A0h
0x1800109a0  lea     rdi, [rbx+10h]
0x1800109a4  mov     [rbx+18h], rax
0x1800109a8  mov     rdx, r14; SourceString
0x1800109ab  movzx   eax, word ptr [rsi+3Ah]
0x1800109af  mov     rcx, rdi; DestinationString
0x1800109b2  mov     [rbx+12h], ax
0x1800109b6  call    cs:__imp_RtlCopyUnicodeString
0x1800109bc  mov     rax, [rsi+8]
0x1800109c0  mov     [rbx+20h], rax
0x1800109c4  mov     al, [rsi+4]
0x1800109c7  mov     [rbx+30h], al
0x1800109ca  mov     rax, cs:gpTermsrvCORIniFile
0x1800109d1  test    rax, rax
0x1800109d4  jnz     loc_180010D43
0x1800109da  xorps   xmm0, xmm0
0x1800109dd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800109e4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800109e9  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x1800109ed  lea     rcx, [rbx+28h]; FileHandle
0x1800109f1  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800109f8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800109fc  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180010a00  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010a04  cmp     [rbx+30h], r13b
0x180010a08  jnz     loc_180010AD7
0x180010a0e  mov     [rsp+0F0h+Protect], 60h ; '`'; OpenOptions
0x180010a16  mov     edx, 80100000h; DesiredAccess
0x180010a1b  mov     [rsp+0F0h+AllocationType], 7; ShareAccess
0x180010a23  call    cs:__imp_NtOpenFile
0x180010a29  mov     edi, eax
0x180010a2b  test    eax, eax
0x180010a2d  jns     loc_180010B16
0x180010a33  cmp     [rbx+32h], r13b
0x180010a37  jnz     loc_180010CD2
0x180010a3d  mov     rcx, [rbx+28h]; Handle
0x180010a41  test    rcx, rcx
0x180010a44  jz      short loc_180010A4C
0x180010a46  call    cs:__imp_NtClose
0x180010a4c  mov     rcx, gs:60h
0x180010a55  mov     r8, rbx; P
0x180010a58  xor     edx, edx; Flags
0x180010a5a  mov     rcx, [rcx+30h]; HeapHandle
0x180010a5e  call    cs:__imp_RtlFreeHeap
0x180010a64  jmp     loc_1800108B9
0x180010a69  cmp     rdx, r8
0x180010a6c  jbe     short loc_180010AD3
0x180010a6e  add     rdx, 0FFFFFFFFFFFFFFFEh
0x180010a72  mov     eax, ecx
0x180010a74  cmp     [rdx], r9w
0x180010a78  jnz     loc_180010C37
0x180010a7e  mov     ecx, eax
0x180010a80  add     rcx, r8
0x180010a83  cmp     rcx, r8
0x180010a86  jbe     loc_1800108B5
0x180010a8c  cmp     [rcx-2], r9w
0x180010a91  jz      loc_1800108B5
0x180010a97  mov     dword ptr [rcx], 0A000Dh
0x180010a9d  mov     eax, [rbx+34h]
0x180010aa0  mov     [rbx+50h], eax
0x180010aa3  add     eax, 4
0x180010aa6  jmp     loc_1800108AF
0x180010aab  cmp     byte ptr [rdx], 20h ; ' '
0x180010aae  ja      loc_180010891
0x180010ab4  cmp     [rdx], r10b
0x180010ab7  jz      loc_180010891
0x180010abd  lea     eax, [rcx-1]
0x180010ac0  mov     [rbx+34h], eax
0x180010ac3  mov     ecx, eax
0x180010ac5  cmp     rdx, r8
0x180010ac8  jbe     loc_180010891
0x180010ace  jmp     loc_180010883
0x180010ad3  mov     eax, ecx
0x180010ad5  jmp     short loc_180010A7E
0x180010ad7  mov     [rsp+0F0h+EaLength], r13d; EaLength
0x180010adc  mov     edx, 0C0100000h; DesiredAccess
0x180010ae1  mov     [rsp+0F0h+EaBuffer], r13; EaBuffer
0x180010ae6  mov     dword ptr [rsp+0F0h+Key], 60h ; '`'; CreateOptions
0x180010aee  mov     dword ptr [rsp+0F0h+ByteOffset], 3; CreateDisposition
0x180010af6  mov     [rsp+0F0h+Length], 7; ShareAccess
0x180010afe  mov     [rsp+0F0h+Protect], 80h; FileAttributes
0x180010b06  mov     qword ptr [rsp+0F0h+AllocationType], r13; AllocationSize
0x180010b0b  call    cs:__imp_NtCreateFile
0x180010b11  jmp     loc_180010A29
0x180010b16  mov     [rbx+32h], r13b
0x180010b1a  lea     r14, [rbx+28h]
0x180010b1e  mov     qword ptr [rbp+57h+arg_10], r13
0x180010b22  xor     r9d, r9d; ApcContext
0x180010b25  mov     qword ptr [rbp+57h+arg_8], r15
0x180010b29  xor     r8d, r8d; ApcRoutine
0x180010b2c  mov     al, [rbx+30h]
0x180010b2f  xor     edx, edx; Event
0x180010b31  mov     rcx, [r14]; FileHandle
0x180010b34  mov     byte ptr [rsp+0F0h+EaBuffer], al; ExclusiveLock
0x180010b38  mov     eax, cs:LockFileKey
0x180010b3e  mov     byte ptr [rsp+0F0h+Key], r13b; FailImmediatedly
0x180010b43  mov     dword ptr [rsp+0F0h+ByteOffset], eax; Key
0x180010b47  lea     rax, [rbp+57h+arg_8]
0x180010b4b  mov     qword ptr [rsp+0F0h+Length], rax; Length
0x180010b50  lea     rax, [rbp+57h+arg_10]
0x180010b54  mov     qword ptr [rsp+0F0h+Protect], rax; ByteOffset
0x180010b59  lea     rax, [rbp+57h+IoStatusBlock]
0x180010b5d  mov     qword ptr [rsp+0F0h+AllocationType], rax; IoStatusBlock
0x180010b62  call    cs:__imp_NtLockFile
0x180010b68  test    eax, eax
0x180010b6a  js      loc_180010CFF
0x180010b70  mov     byte ptr [rbx+32h], 1
0x180010b74  mov     rcx, [r14]; FileHandle
0x180010b77  lea     r8, [rbx+88h]; FileInformation
0x180010b7e  mov     r9d, 18h; Length
0x180010b84  mov     [rsp+0F0h+AllocationType], 5; FileInformationClass
0x180010b8c  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180010b90  call    cs:__imp_NtQueryInformationFile
0x180010b96  mov     edi, eax
0x180010b98  cmp     eax, 80000005h
0x180010b9d  jz      short loc_180010BA7
0x180010b9f  test    eax, eax
0x180010ba1  js      loc_180010D17
0x180010ba7  mov     edx, [rbx+90h]
0x180010bad  lea     r9, [rbx+48h]; RegionSize
0x180010bb1  mov     al, [rbx+31h]
0x180010bb4  lea     r15, [rbx+38h]
0x180010bb8  neg     al
0x180010bba  mov     [rbx+34h], edx
0x180010bbd  mov     [rsp+0F0h+Protect], 4; Protect
0x180010bc5  sbb     rcx, rcx
0x180010bc8  mov     [rsp+0F0h+AllocationType], 2000h; AllocationType
0x180010bd0  and     ecx, 4
0x180010bd3  xor     r8d, r8d; ZeroBits
0x180010bd6  lea     rax, [rcx+4]
0x180010bda  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180010bde  add     rax, rdx
0x180010be1  mov     rdx, r15; BaseAddress
0x180010be4  mov     [rbx+40h], rax
0x180010be8  add     rax, 100000h
0x180010bee  mov     [r9], rax
  ... truncated ...
```
