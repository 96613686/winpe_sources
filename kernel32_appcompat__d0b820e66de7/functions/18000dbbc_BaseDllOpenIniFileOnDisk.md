# BaseDllOpenIniFileOnDisk

- ea: `0x18000dbbc`
- end: `0x18000e29b`
- name: `BaseDllOpenIniFileOnDisk`
- size: `1759`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000da14`
- `0x1800532f0`

## callees

- `0x18000dbbc`
- `0x18000f950`
- `0x180084010`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18000e199`
- `ntdll!RtlAppendUnicodeToString` at `0x18000e199`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000e1b6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000e1b6`
- `ntdll!NtOpenFile` at `0x18000df02`
- `ntdll!NtOpenFile` at `0x18000df02`
- `ntdll!NtClose` at `0x18000df2b`
- `ntdll!NtClose` at `0x18000df2b`
- `ntdll!NtQueryInformationFile` at `0x18000e08d`
- `ntdll!NtQueryInformationFile` at `0x18000e08d`
- `ntdll!RtlFreeUnicodeString` at `0x18000de1f`
- `ntdll!RtlFreeUnicodeString` at `0x18000de1f`
- `ntdll!NtCreateFile` at `0x18000dffc`
- `ntdll!NtCreateFile` at `0x18000dffc`
- `ntdll!wcscspn` at `0x18000e126`
- `ntdll!wcscspn` at `0x18000e126`
- `ntdll!NtUnlockFile` at `0x18000e1ee`
- `ntdll!NtUnlockFile` at `0x18000e221`
- `ntdll!NtUnlockFile` at `0x18000e1ee`
- `ntdll!NtUnlockFile` at `0x18000e221`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000ddf0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000ddf0`
- `ntdll!NtReadFile` at `0x18000dcc1`
- `ntdll!NtReadFile` at `0x18000dcc1`
- `ntdll!NtLockFile` at `0x18000e059`
- `ntdll!NtLockFile` at `0x18000e059`
- `ntdll!RtlCopyUnicodeString` at `0x18000de0f`
- `ntdll!RtlCopyUnicodeString` at `0x18000de8f`
- `ntdll!RtlCopyUnicodeString` at `0x18000e183`
- `ntdll!RtlCopyUnicodeString` at `0x18000de0f`
- `ntdll!RtlCopyUnicodeString` at `0x18000de8f`
- `ntdll!RtlCopyUnicodeString` at `0x18000e183`
- `ntdll!RtlIsTextUnicode` at `0x18000dcfd`
- `ntdll!RtlIsTextUnicode` at `0x18000dcfd`
- `ntdll!NtAllocateVirtualMemory` at `0x18000dc76`
- `ntdll!NtAllocateVirtualMemory` at `0x18000e0f4`
- `ntdll!NtAllocateVirtualMemory` at `0x18000dc76`
- `ntdll!NtAllocateVirtualMemory` at `0x18000e0f4`
- `ntdll!RtlFreeHeap` at `0x18000df49`
- `ntdll!RtlFreeHeap` at `0x18000df49`
- `ntdll!RtlAllocateHeap` at `0x18000de5b`
- `ntdll!RtlAllocateHeap` at `0x18000de5b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000ddc6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000de2b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000e170`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000ddc6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000de2b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000e170`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000dd9d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000dd9d`

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
0x18000dbbc  push    rbp
0x18000dbbe  push    rbx
0x18000dbbf  push    rsi
0x18000dbc0  push    rdi
0x18000dbc1  push    r12
0x18000dbc3  push    r13
0x18000dbc5  push    r14
0x18000dbc7  push    r15
0x18000dbc9  lea     rbp, [rsp-1Fh]
0x18000dbce  sub     rsp, 0B8h
0x18000dbd5  movzx   edi, word ptr [rcx+28h]
0x18000dbd9  lea     r14, [rcx+38h]
0x18000dbdd  xorps   xmm0, xmm0
0x18000dbe0  lea     rbx, [rcx+30h]
0x18000dbe4  xor     r13d, r13d
0x18000dbe7  xor     eax, eax
0x18000dbe9  mov     [rbp+57h+FilePart], r13
0x18000dbed  mov     rsi, rcx
0x18000dbf0  mov     qword ptr [rbp+57h+arg_10], r13
0x18000dbf4  mov     qword ptr [rbp+57h+arg_8], r13
0x18000dbf8  mov     [r14], r13w
0x18000dbfc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000dc00  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000dc04  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18000dc08  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000dc0c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000dc10  cmp     edi, 2
0x18000dc13  ja      loc_18000DD7E
0x18000dc19  test    di, di
0x18000dc1c  jnz     loc_18000E11C
0x18000dc22  mov     rax, cs:gpTermsrvBuildIniFileName
0x18000dc29  test    rax, rax
0x18000dc2c  jz      loc_18000E170
0x18000dc32  lea     rdx, [rsi+18h]
0x18000dc36  mov     rcx, r14
0x18000dc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc3e  mov     edi, eax
0x18000dc40  test    eax, eax
0x18000dc42  js      loc_18000E170
0x18000dc48  mov     rbx, r13
0x18000dc4b  test    edi, edi
0x18000dc4d  jns     loc_18000DDE1
0x18000dc53  jmp     loc_18000DD67
0x18000dc58  mov     [rsp+0F0h+Protect], 4; Protect
0x18000dc60  lea     r9, [rbx+40h]; RegionSize
0x18000dc64  xor     r8d, r8d; ZeroBits
0x18000dc67  mov     [rsp+0F0h+AllocationType], 1000h; AllocationType
0x18000dc6f  mov     rdx, r15; BaseAddress
0x18000dc72  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000dc76  call    cs:__imp_NtAllocateVirtualMemory
0x18000dc7d  nop     dword ptr [rax+rax+00h]
0x18000dc82  mov     edi, eax
0x18000dc84  test    eax, eax
0x18000dc86  js      loc_18000E10A
0x18000dc8c  mov     rcx, [rbx+28h]; FileHandle
0x18000dc90  lea     rax, LockFileKey
0x18000dc97  mov     [rsp+0F0h+Key], rax; Key
0x18000dc9c  xor     r9d, r9d; ApcContext
0x18000dc9f  mov     eax, [rbx+34h]
0x18000dca2  xor     r8d, r8d; ApcRoutine
0x18000dca5  mov     [rsp+0F0h+ByteOffset], r13; ByteOffset
0x18000dcaa  xor     edx, edx; Event
0x18000dcac  mov     [rsp+0F0h+Length], eax; Length
0x18000dcb0  mov     rax, [r15]
0x18000dcb3  mov     qword ptr [rsp+0F0h+Protect], rax; Buffer
0x18000dcb8  lea     rax, [rbp+57h+IoStatusBlock]
0x18000dcbc  mov     qword ptr [rsp+0F0h+AllocationType], rax; IoStatusBlock
0x18000dcc1  call    cs:__imp_NtReadFile
0x18000dcc8  nop     dword ptr [rax+rax+00h]
0x18000dccd  mov     edi, eax
0x18000dccf  test    eax, eax
0x18000dcd1  js      loc_18000E10A
0x18000dcd7  mov     edx, [rbx+34h]; Size
0x18000dcda  cmp     [rbp+57h+IoStatusBlock.Information], rdx
0x18000dcde  jnz     loc_18000E283
0x18000dce4  mov     rcx, [r15]; Buffer
0x18000dce7  lea     r8, [rbp+57h+Flags]; Flags
0x18000dceb  mov     [rbp+57h+Flags], 0FFFFFFFFh
0x18000dcf2  mov     dword ptr [rbx+50h], 0FFFFFFFFh
0x18000dcf9  mov     [rbx+54h], r13d
0x18000dcfd  call    cs:__imp_RtlIsTextUnicode
0x18000dd04  nop     dword ptr [rax+rax+00h]
0x18000dd09  mov     ecx, [rbx+34h]
0x18000dd0c  mov     r10d, 0Dh
0x18000dd12  mov     r8, [r15]
0x18000dd15  mov     [rbx+31h], al
0x18000dd18  lea     r9d, [r10-3]
0x18000dd1c  lea     rdx, [rcx+r8]
0x18000dd20  test    al, al
0x18000dd22  jnz     loc_18000DF5A
0x18000dd28  cmp     rdx, r8
0x18000dd2b  jbe     loc_18000E28D
0x18000dd31  dec     rdx
0x18000dd34  mov     eax, ecx
0x18000dd36  cmp     [rdx], r9b
0x18000dd39  jnz     loc_18000DF9C
0x18000dd3f  mov     ecx, eax
0x18000dd41  add     rcx, r8
0x18000dd44  cmp     rcx, r8
0x18000dd47  jbe     short loc_18000DD63
0x18000dd49  cmp     [rcx-1], r9b
0x18000dd4d  jz      short loc_18000DD63
0x18000dd4f  mov     word ptr [rcx], 0A0Dh
0x18000dd54  mov     eax, [rbx+34h]
0x18000dd57  mov     [rbx+50h], eax
0x18000dd5a  add     eax, 2
0x18000dd5d  mov     [rbx+34h], eax
0x18000dd60  mov     [rbx+54h], eax
0x18000dd63  mov     [rsi+10h], rbx
0x18000dd67  mov     eax, edi
0x18000dd69  add     rsp, 0B8h
0x18000dd70  pop     r15
0x18000dd72  pop     r14
0x18000dd74  pop     r13
0x18000dd76  pop     r12
0x18000dd78  pop     rdi
0x18000dd79  pop     rsi
0x18000dd7a  pop     rbx
0x18000dd7b  pop     rbp
0x18000dd7c  retn
0x18000dd7e  mov     rax, [rbx]
0x18000dd81  cmp     word ptr [rax+2], 3Ah ; ':'
0x18000dd86  jnz     loc_18000E11C
0x18000dd8c  movzx   edx, word ptr [rsi+3Ah]
0x18000dd90  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x18000dd94  mov     r8, [rsi+40h]; lpBuffer
0x18000dd98  mov     rcx, [rbx]; lpFileName
0x18000dd9b  shr     edx, 1; nBufferLength
0x18000dd9d  call    cs:__imp_GetFullPathNameW
0x18000dda4  nop     dword ptr [rax+rax+00h]
0x18000dda9  movzx   ecx, word ptr [rsi+3Ah]
0x18000ddad  shr     ecx, 1
0x18000ddaf  cmp     eax, ecx
0x18000ddb1  ja      loc_18000E258
0x18000ddb7  test    eax, eax
0x18000ddb9  jz      loc_18000E262
0x18000ddbf  add     ax, ax
0x18000ddc2  mov     [r14], ax
0x18000ddc6  call    cs:__imp_KernelBaseGetGlobalData
0x18000ddcd  nop     dword ptr [rax+rax+00h]
0x18000ddd2  mov     rcx, r14
0x18000ddd5  lea     rdx, [rax+8]
0x18000ddd9  call    TermsrvConvertSysRootToUserDir
0x18000ddde  mov     rbx, r13
0x18000dde1  mov     rcx, [rsi+40h]; DosPathName
0x18000dde5  lea     r8, [rbp+57h+FilePart]; NtFileNamePart
0x18000dde9  xor     r9d, r9d; DirectoryInfo
0x18000ddec  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18000ddf0  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000ddf7  nop     dword ptr [rax+rax+00h]
0x18000ddfc  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000de00  test    al, al
0x18000de02  jz      loc_18000E294
0x18000de08  lea     rdx, [rbp+57h+NtPathName]; SourceString
0x18000de0c  mov     rcx, r14; DestinationString
0x18000de0f  call    cs:__imp_RtlCopyUnicodeString
0x18000de16  nop     dword ptr [rax+rax+00h]
0x18000de1b  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18000de1f  call    cs:__imp_RtlFreeUnicodeString
0x18000de26  nop     dword ptr [rax+rax+00h]
0x18000de2b  call    cs:__imp_KernelBaseGetGlobalData
0x18000de32  nop     dword ptr [rax+rax+00h]
0x18000de37  mov     rcx, gs:60h
0x18000de40  movzx   r8d, word ptr [rsi+3Ah]
0x18000de45  add     r8, 0A0h; Size
0x18000de4c  mov     edx, [rax]
0x18000de4e  mov     rcx, [rcx+30h]; HeapHandle
0x18000de52  add     edx, 80000h
0x18000de58  or      edx, 8; Flags
0x18000de5b  call    cs:__imp_RtlAllocateHeap
0x18000de62  nop     dword ptr [rax+rax+00h]
0x18000de67  mov     rbx, rax
0x18000de6a  test    rax, rax
0x18000de6d  jz      loc_18000E26C
0x18000de73  add     rax, 0A0h
0x18000de79  lea     rdi, [rbx+10h]
0x18000de7d  mov     [rbx+18h], rax
0x18000de81  mov     rdx, r14; SourceString
0x18000de84  movzx   eax, word ptr [rsi+3Ah]
0x18000de88  mov     rcx, rdi; DestinationString
0x18000de8b  mov     [rbx+12h], ax
0x18000de8f  call    cs:__imp_RtlCopyUnicodeString
0x18000de96  nop     dword ptr [rax+rax+00h]
0x18000de9b  mov     rax, [rsi+8]
0x18000de9f  mov     [rbx+20h], rax
0x18000dea3  mov     al, [rsi+4]
0x18000dea6  mov     [rbx+30h], al
0x18000dea9  mov     rax, cs:gpTermsrvCORIniFile
0x18000deb0  test    rax, rax
0x18000deb3  jnz     loc_18000E276
0x18000deb9  xorps   xmm0, xmm0
0x18000debc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000dec3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000dec8  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18000decc  lea     rcx, [rbx+28h]; FileHandle
0x18000ded0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ded7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000dedb  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x18000dedf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000dee3  cmp     [rbx+30h], r13b
0x18000dee7  jnz     loc_18000DFC8
0x18000deed  mov     [rsp+0F0h+Protect], 60h ; '`'; OpenOptions
0x18000def5  mov     edx, 80100000h; DesiredAccess
0x18000defa  mov     [rsp+0F0h+AllocationType], 7; ShareAccess
0x18000df02  call    cs:__imp_NtOpenFile
0x18000df09  nop     dword ptr [rax+rax+00h]
0x18000df0e  mov     edi, eax
0x18000df10  test    eax, eax
0x18000df12  jns     loc_18000E00D
0x18000df18  cmp     [rbx+32h], r13b
0x18000df1c  jnz     loc_18000E1FF
0x18000df22  mov     rcx, [rbx+28h]; Handle
0x18000df26  test    rcx, rcx
0x18000df29  jz      short loc_18000DF37
0x18000df2b  call    cs:__imp_NtClose
0x18000df32  nop     dword ptr [rax+rax+00h]
0x18000df37  mov     rcx, gs:60h
0x18000df40  mov     r8, rbx; P
0x18000df43  xor     edx, edx; Flags
0x18000df45  mov     rcx, [rcx+30h]; HeapHandle
0x18000df49  call    cs:__imp_RtlFreeHeap
0x18000df50  nop     dword ptr [rax+rax+00h]
0x18000df55  jmp     loc_18000DD67
0x18000df5a  cmp     rdx, r8
0x18000df5d  jbe     short loc_18000DFC4
0x18000df5f  add     rdx, 0FFFFFFFFFFFFFFFEh
0x18000df63  mov     eax, ecx
0x18000df65  cmp     [rdx], r9w
0x18000df69  jnz     loc_18000E146
0x18000df6f  mov     ecx, eax
0x18000df71  add     rcx, r8
0x18000df74  cmp     rcx, r8
0x18000df77  jbe     loc_18000DD63
0x18000df7d  cmp     [rcx-2], r9w
0x18000df82  jz      loc_18000DD63
0x18000df88  mov     dword ptr [rcx], 0A000Dh
0x18000df8e  mov     eax, [rbx+34h]
0x18000df91  mov     [rbx+50h], eax
0x18000df94  add     eax, 4
0x18000df97  jmp     loc_18000DD5D
0x18000df9c  cmp     byte ptr [rdx], 20h ; ' '
0x18000df9f  ja      loc_18000DD3F
0x18000dfa5  cmp     [rdx], r10b
0x18000dfa8  jz      loc_18000DD3F
0x18000dfae  lea     eax, [rcx-1]
0x18000dfb1  mov     [rbx+34h], eax
0x18000dfb4  mov     ecx, eax
0x18000dfb6  cmp     rdx, r8
0x18000dfb9  jbe     loc_18000DD3F
0x18000dfbf  jmp     loc_18000DD31
0x18000dfc4  mov     eax, ecx
0x18000dfc6  jmp     short loc_18000DF6F
0x18000dfc8  mov     [rsp+0F0h+EaLength], r13d; EaLength
0x18000dfcd  mov     edx, 0C0100000h; DesiredAccess
0x18000dfd2  mov     [rsp+0F0h+EaBuffer], r13; EaBuffer
0x18000dfd7  mov     dword ptr [rsp+0F0h+Key], 60h ; '`'; CreateOptions
0x18000dfdf  mov     dword ptr [rsp+0F0h+ByteOffset], 3; CreateDisposition
0x18000dfe7  mov     [rsp+0F0h+Length], 7; ShareAccess
0x18000dfef  mov     [rsp+0F0h+Protect], 80h; FileAttributes
0x18000dff7  mov     qword ptr [rsp+0F0h+AllocationType], r13; AllocationSize
0x18000dffc  call    cs:__imp_NtCreateFile
0x18000e003  nop     dword ptr [rax+rax+00h]
0x18000e008  jmp     loc_18000DF0E
0x18000e00d  mov     [rbx+32h], r13b
0x18000e011  lea     r14, [rbx+28h]
0x18000e015  mov     qword ptr [rbp+57h+arg_10], r13
0x18000e019  xor     r9d, r9d; ApcContext
0x18000e01c  mov     qword ptr [rbp+57h+arg_8], r15
0x18000e020  xor     r8d, r8d; ApcRoutine
0x18000e023  mov     al, [rbx+30h]
0x18000e026  xor     edx, edx; Event
0x18000e028  mov     rcx, [r14]; FileHandle
0x18000e02b  mov     byte ptr [rsp+0F0h+EaBuffer], al; ExclusiveLock
0x18000e02f  mov     eax, cs:LockFileKey
0x18000e035  mov     byte ptr [rsp+0F0h+Key], r13b; FailImmediatedly
0x18000e03a  mov     dword ptr [rsp+0F0h+ByteOffset], eax; Key
0x18000e03e  lea     rax, [rbp+57h+arg_8]
0x18000e042  mov     qword ptr [rsp+0F0h+Length], rax; Length
0x18000e047  lea     rax, [rbp+57h+arg_10]
0x18000e04b  mov     qword ptr [rsp+0F0h+Protect], rax; ByteOffset
0x18000e050  lea     rax, [rbp+57h+IoStatusBlock]
0x18000e054  mov     qword ptr [rsp+0F0h+AllocationType], rax; IoStatusBlock
0x18000e059  call    cs:__imp_NtLockFile
0x18000e060  nop     dword ptr [rax+rax+00h]
0x18000e065  test    eax, eax
0x18000e067  js      loc_18000E232
0x18000e06d  mov     byte ptr [rbx+32h], 1
0x18000e071  mov     rcx, [r14]; FileHandle
0x18000e074  lea     r8, [rbx+88h]; FileInformation
0x18000e07b  mov     r9d, 18h; Length
0x18000e081  mov     [rsp+0F0h+AllocationType], 5; FileInformationClass
0x18000e089  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e08d  call    cs:__imp_NtQueryInformationFile
0x18000e094  nop     dword ptr [rax+rax+00h]
0x18000e099  mov     edi, eax
0x18000e09b  cmp     eax, 80000005h
0x18000e0a0  jz      short loc_18000E0AA
0x18000e0a2  test    eax, eax
0x18000e0a4  js      loc_18000E24A
0x18000e0aa  mov     edx, [rbx+90h]
  ... truncated ...
```
