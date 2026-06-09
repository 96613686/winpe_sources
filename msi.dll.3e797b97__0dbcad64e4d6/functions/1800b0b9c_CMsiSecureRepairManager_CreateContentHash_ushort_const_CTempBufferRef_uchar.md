# CMsiSecureRepairManager::CreateContentHash(ushort const *,CTempBufferRef<uchar> &)

- ea: `0x1800b0b9c`
- end: `0x1800b12a7`
- name: `?CreateContentHash@CMsiSecureRepairManager@@AEAAPEAVIMsiRecord@@PEBGAEAV?$CTempBufferRef@E@@@Z`
- size: `1803`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b0658`
- `0x180212318`

## callees

- `0x18000c4bc`
- `0x180013d64`
- `0x180014f18`
- `0x180016154`
- `0x180019cc0`
- `0x18001f57c`
- `0x18009ca0c`
- `0x1800b0b9c`
- `0x1800b12b0`
- `0x1800d04fc`
- `0x18013fa30`
- `0x18015d0b8`
- `0x180215434`
- `0x1802651ea`
- `0x180265240`
- `0x1802652d0`
- `0x180266010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800b0f26`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800b0f26`
- `KERNEL32!CloseHandle` at `0x1800b122b`
- `KERNEL32!CloseHandle` at `0x1800b122b`
- `KERNEL32!GetLastError` at `0x1800b0fa2`
- `KERNEL32!GetLastError` at `0x1800b1170`
- `KERNEL32!GetLastError` at `0x1800b0fa2`
- `KERNEL32!GetLastError` at `0x1800b1170`
- `KERNEL32!Sleep` at `0x1800b1119`
- `KERNEL32!Sleep` at `0x1800b1119`
- `KERNEL32!CreateFileW` at `0x1800b0d72`
- `KERNEL32!CreateFileW` at `0x1800b0d72`
- `KERNEL32!ReadFile` at `0x1800b0ddc`
- `KERNEL32!ReadFile` at `0x1800b0ddc`
- `bcrypt!BCryptFinishHash` at `0x1800b0eb1`
- `bcrypt!BCryptFinishHash` at `0x1800b0eb1`
- `bcrypt!BCryptCreateHash` at `0x1800b0dac`
- `bcrypt!BCryptCreateHash` at `0x1800b0dac`
- `bcrypt!BCryptHashData` at `0x1800b0e03`
- `bcrypt!BCryptHashData` at `0x1800b0e03`
- `bcrypt!BCryptGetProperty` at `0x1800b0e7c`
- `bcrypt!BCryptGetProperty` at `0x1800b0e7c`
- `bcrypt!BCryptDestroyHash` at `0x1800b124b`
- `bcrypt!BCryptDestroyHash` at `0x1800b124b`

## string_xrefs

- `0x1800b0fe8`: `SECREPAIR: Failed to open the file:%s for computing its hash. Error:%d`
- `0x1800b10b3`: `SECREPAIR: Invalid source directory`
- `0x1800b0e3a`: `SECREPAIR: Failed to Hash Data Chunk for file:%s. Error:%d`
- `0x1800b1146`: `SECREPAIR: Failed to create a hash object. Error:%d`
- `0x1800b11ab`: `SECREPAIR: Failed to read the file:%s for computing its hash. Error:%d`
- `0x1800b0ee6`: `SECREPAIR: Failed to get the Hash Value for the file:%s. Error:%d`
- `0x1800b11fe`: `SECREPAIR: Failed to get the Hash Length property. Error:%d`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiSecureRepairManager::CreateContentHash(
        CMsiSecureRepairManager *a1,
        __int64 a2,
        PUCHAR *a3)
{
  const unsigned __int16 *LastError; // rdi
  __int64 v7; // rcx
  const WCHAR *v8; // rax
  bool v9; // bl
  struct IMsiRecord *Record; // r14
  struct IMsiRecord *v11; // rbx
  int v13; // ebx
  const WCHAR *v14; // rax
  HANDLE FileW; // rsi
  NTSTATUS v16; // eax
  const unsigned __int16 *Property; // rbx
  BOOL v18; // eax
  NTSTATUS v19; // eax
  const unsigned __int16 *v20; // rax
  const unsigned __int16 *v21; // r9
  NTSTATUS v22; // eax
  __int64 v23; // rbx
  int v24; // r15d
  DWORD v25; // eax
  const unsigned __int16 *v26; // rax
  MsiUIMessageContext *v27; // rcx
  __int64 v28; // rax
  const unsigned __int16 *v29; // rax
  bool ImpersonationFromPath; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbOutput[4]; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesRead; // [rsp+74h] [rbp-8Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-88h] BYREF
  ULONG pcbResult; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[8]; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+98h] [rbp-68h]
  _BYTE v39[4096]; // [rsp+A0h] [rbp-60h] BYREF

  LODWORD(LastError) = 0;
  NumberOfBytesRead = 0;
  phHash = 0;
  memset_0(v39, 0, sizeof(v39));
  v7 = *(_QWORD *)a1;
  lpBuffer = v39;
  v38 = 4096;
  v31 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v7 + 184LL))(v7, L"SourceDir");
  v8 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
  ImpersonationFromPath = GetImpersonationFromPath(v8);
  v9 = ImpersonationFromPath;
  CImpersonate::CImpersonate((CImpersonate *)v36, ImpersonationFromPath);
  Record = CreateRecord(2u);
  if ( !Record )
  {
    v11 = PostError(2402);
    CImpersonate::~CImpersonate((CImpersonate *)v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v38 > 4096 )
      operator delete(lpBuffer);
    return v11;
  }
  if ( !a2 )
  {
    LODWORD(LastError) = 87;
    goto LABEL_37;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v31 + 56LL))(v31) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Invalid source directory",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_37;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v31 + 200LL))(
          v31,
          4,
          L"\\") )
    MsiString::operator+=(&v31, L"\\");
  (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v31 + 144LL))(v31, a2, &v31);
  if ( ImpersonationFromPath )
    ++HIDWORD(qword_1803136AC);
  v13 = 0;
  while ( 1 )
  {
    if ( v13 )
      Sleep(0x1388u);
    v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
    FileW = CreateFileW(v14, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      phHash = 0;
      v16 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
      LODWORD(Property) = v16;
      if ( v16 < 0 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Failed to create a hash object. Error:%d",
            (const unsigned __int16 *)v16,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
      }
      else
      {
        while ( 1 )
        {
          v18 = ReadFile(FileW, lpBuffer, 0x1000u, &NumberOfBytesRead, 0);
          if ( !v18 )
            break;
          if ( !NumberOfBytesRead )
            goto LABEL_22;
          v19 = BCryptHashData(phHash, (PUCHAR)lpBuffer, NumberOfBytesRead, 0);
          Property = (const unsigned __int16 *)v19;
          if ( v19 < 0 )
          {
            if ( !g_dmDiagnosticMode )
              goto LABEL_27;
            v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
            v21 = L"SECREPAIR: Failed to Hash Data Chunk for file:%s. Error:%d";
            goto LABEL_26;
          }
        }
        if ( !v18 )
        {
          LastError = (const unsigned __int16 *)GetLastError();
          if ( g_dmDiagnosticMode )
          {
            v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
            DebugString(
              9,
              0,
              0,
              L"SECREPAIR: Failed to read the file:%s for computing its hash. Error:%d",
              v29,
              LastError,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          goto LABEL_28;
        }
LABEL_22:
        *(_DWORD *)pbOutput = 0;
        pcbResult = 0;
        Property = (const unsigned __int16 *)BCryptGetProperty(
                                               (BCRYPT_HANDLE)0x41,
                                               L"HashDigestLength",
                                               pbOutput,
                                               4u,
                                               &pcbResult,
                                               0);
        if ( (int)Property < 0 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"SECREPAIR: Failed to get the Hash Length property. Error:%d",
              Property,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        else
        {
          CTempBufferRef<unsigned char>::Resize(a3, *(unsigned int *)pbOutput);
          v22 = BCryptFinishHash(phHash, *a3, *(ULONG *)pbOutput, 0);
          Property = (const unsigned __int16 *)v22;
          if ( v22 >= 0 )
            goto LABEL_28;
          if ( g_dmDiagnosticMode )
          {
            v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
            v21 = L"SECREPAIR: Failed to get the Hash Value for the file:%s. Error:%d";
LABEL_26:
            DebugString(9, 0, 0, v21, v20, Property, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
          }
        }
      }
LABEL_27:
      LODWORD(LastError) = RtlNtStatusToDosErrorNoTeb((NTSTATUS)Property);
LABEL_28:
      v23 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 440LL))(*(_QWORD *)a1);
      v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 504LL))(*(_QWORD *)a1);
      if ( !(_DWORD)LastError
        && (*(unsigned int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v23 + 200LL))(v23, 4, a2)
        && v24 == 4 )
      {
        CMsiSecureRepairManager::SetFileToHashHandle(a1, FileW);
      }
      else
      {
        CloseHandle(FileW);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      goto LABEL_36;
    }
    v25 = GetLastError();
    LastError = (const unsigned __int16 *)v25;
    if ( v25 != 32 )
      break;
    if ( ++v13 >= 60 )
      break;
    LODWORD(LastError) = 0;
  }
  if ( g_dmDiagnosticMode )
  {
    v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
    DebugString(
      9,
      0,
      0,
      L"SECREPAIR: Failed to open the file:%s for computing its hash. Error:%d",
      v26,
      LastError,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
LABEL_36:
  v9 = ImpersonationFromPath;
LABEL_37:
  v27 = (MsiUIMessageContext *)phHash;
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v9 )
    MsiUIMessageContext::EnableTimeout(v27);
  v28 = *(_QWORD *)Record;
  if ( (_DWORD)LastError )
  {
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(v28 + 104))(Record, 1, (unsigned int)LastError);
    CImpersonate::~CImpersonate((CImpersonate *)v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v38 > 4096 )
      operator delete(lpBuffer);
    return Record;
  }
  else
  {
    (*(void (__fastcall **)(struct IMsiRecord *))(v28 + 16))(Record);
    CImpersonate::~CImpersonate((CImpersonate *)v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    CTempBuffer<unsigned char,4096>::~CTempBuffer<unsigned char,4096>(&lpBuffer);
    return 0;
  }
}

```

## disassembly

```asm
0x1800b0b9c  mov     [rsp-8+arg_18], rbx
0x1800b0ba1  push    rbp
0x1800b0ba2  push    rsi
0x1800b0ba3  push    rdi
0x1800b0ba4  push    r12
0x1800b0ba6  push    r13
0x1800b0ba8  push    r14
0x1800b0baa  push    r15
0x1800b0bac  lea     rbp, [rsp-0FB0h]
0x1800b0bb4  mov     eax, 10B0h
0x1800b0bb9  call    _alloca_probe
0x1800b0bbe  sub     rsp, rax
0x1800b0bc1  mov     rax, cs:__security_cookie
0x1800b0bc8  xor     rax, rsp
0x1800b0bcb  mov     [rbp+0FE0h+var_40], rax
0x1800b0bd2  mov     r15, r8
0x1800b0bd5  mov     r12, rdx
0x1800b0bd8  mov     r13, rcx
0x1800b0bdb  xor     edi, edi
0x1800b0bdd  xor     edx, edx; Val
0x1800b0bdf  mov     [rsp+10E0h+NumberOfBytesRead], edi
0x1800b0be3  mov     r8d, 1000h; Size
0x1800b0be9  mov     [rsp+10E0h+phHash], rdi
0x1800b0bee  lea     rcx, [rbp+0FE0h+var_1040]; void *
0x1800b0bf2  call    memset_0
0x1800b0bf7  mov     rcx, [r13+0]
0x1800b0bfb  lea     rax, [rbp+0FE0h+var_1040]
0x1800b0bff  mov     [rbp+0FE0h+lpBuffer], rax
0x1800b0c03  lea     rdx, aSourcedir; "SourceDir"
0x1800b0c0a  mov     [rbp+0FE0h+var_1048], 1000h
0x1800b0c11  mov     rax, [rcx]
0x1800b0c14  mov     rax, [rax+0B8h]
0x1800b0c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c20  mov     [rsp+10E0h+var_1078], rax
0x1800b0c25  mov     rcx, [rax]
0x1800b0c28  mov     rdx, [rcx+50h]
0x1800b0c2c  mov     rcx, rax
0x1800b0c2f  mov     rax, rdx
0x1800b0c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c37  mov     rcx, rax; lpFileName
0x1800b0c3a  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x1800b0c3f  mov     dl, al; bool
0x1800b0c41  mov     [rsp+10E0h+var_1080], al
0x1800b0c45  lea     rcx, [rbp+0FE0h+var_1058]; this
0x1800b0c49  mov     bl, al
0x1800b0c4b  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1800b0c50  lea     ecx, [rdi+2]; unsigned int
0x1800b0c53  call    ?CreateRecord@@YAAEAVIMsiRecord@@I@Z; CreateRecord(uint)
0x1800b0c58  mov     r14, rax
0x1800b0c5b  test    rax, rax
0x1800b0c5e  jnz     short loc_1800B0CC5
0x1800b0c60  mov     ecx, 962h; int
0x1800b0c65  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1800b0c6a  lea     rcx, [rbp+0FE0h+var_1058]; this
0x1800b0c6e  mov     rbx, rax
0x1800b0c71  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800b0c76  mov     rdx, [rsp+10E0h+var_1078]
0x1800b0c7b  mov     rcx, [rdx]
0x1800b0c7e  mov     rax, [rcx+10h]
0x1800b0c82  mov     rcx, rdx
0x1800b0c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c8a  cmp     [rbp+0FE0h+var_1048], 1000h
0x1800b0c91  jg      loc_1800B1084
0x1800b0c97  mov     rax, rbx
0x1800b0c9a  mov     rcx, [rbp+0FE0h+var_40]
0x1800b0ca1  xor     rcx, rsp; StackCookie
0x1800b0ca4  call    __security_check_cookie
0x1800b0ca9  mov     rbx, [rsp+10E0h+arg_18]
0x1800b0cb1  add     rsp, 10B0h
0x1800b0cb8  pop     r15
0x1800b0cba  pop     r14
0x1800b0cbc  pop     r13
0x1800b0cbe  pop     r12
0x1800b0cc0  pop     rdi
0x1800b0cc1  pop     rsi
0x1800b0cc2  pop     rbp
0x1800b0cc3  retn
0x1800b0cc5  test    r12, r12
0x1800b0cc8  jz      loc_1800B1092
0x1800b0cce  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0cd3  mov     rax, [rcx]
0x1800b0cd6  mov     rax, [rax+38h]
0x1800b0cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0cdf  test    eax, eax
0x1800b0ce1  jz      loc_1800B1099
0x1800b0ce7  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0cec  lea     r8, asc_18027979C; "\\"
0x1800b0cf3  mov     edx, 4
0x1800b0cf8  mov     rax, [rcx]
0x1800b0cfb  mov     rax, [rax+0C8h]
0x1800b0d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d07  test    eax, eax
0x1800b0d09  jz      loc_1800B10EC
0x1800b0d0f  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0d14  lea     r8, [rsp+10E0h+var_1078]
0x1800b0d19  mov     rdx, r12
0x1800b0d1c  mov     rax, [rcx]
0x1800b0d1f  mov     rax, [rax+90h]
0x1800b0d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d2b  test    bl, bl
0x1800b0d2d  jnz     loc_1800B1102
0x1800b0d33  mov     ebx, edi
0x1800b0d35  test    ebx, ebx
0x1800b0d37  jnz     loc_1800B1114
0x1800b0d3d  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0d42  mov     rax, [rcx]
0x1800b0d45  mov     rax, [rax+50h]
0x1800b0d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d4e  xor     r9d, r9d; lpSecurityAttributes
0x1800b0d51  mov     [rsp+10E0h+hTemplateFile], rdi; hTemplateFile
0x1800b0d56  mov     [rsp+10E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b0d5e  mov     edx, 80000000h; dwDesiredAccess
0x1800b0d63  mov     rcx, rax; lpFileName
0x1800b0d66  mov     [rsp+10E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b0d6e  lea     r8d, [r9+1]; dwShareMode
0x1800b0d72  call    cs:__imp_CreateFileW
0x1800b0d79  nop     dword ptr [rax+rax+00h]
0x1800b0d7e  mov     rsi, rax
0x1800b0d81  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b0d85  jz      loc_1800B0FA2
0x1800b0d8b  xor     r9d, r9d; cbHashObject
0x1800b0d8e  mov     dword ptr [rsp+10E0h+hTemplateFile], edi; dwFlags
0x1800b0d92  mov     [rsp+10E0h+dwFlagsAndAttributes], edi; cbSecret
0x1800b0d96  lea     rdx, [rsp+10E0h+phHash]; phHash
0x1800b0d9b  xor     r8d, r8d; pbHashObject
0x1800b0d9e  mov     [rsp+10E0h+phHash], rdi
0x1800b0da3  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rdi; pbSecret
0x1800b0da8  lea     ecx, [r9+41h]; hAlgorithm
0x1800b0dac  call    cs:__imp_BCryptCreateHash
0x1800b0db3  nop     dword ptr [rax+rax+00h]
0x1800b0db8  movsxd  rbx, eax
0x1800b0dbb  test    eax, eax
0x1800b0dbd  js      loc_1800B112A
0x1800b0dc3  mov     rdx, [rbp+0FE0h+lpBuffer]; lpBuffer
0x1800b0dc7  lea     r9, [rsp+10E0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b0dcc  xor     ebx, ebx
0x1800b0dce  mov     r8d, 1000h; nNumberOfBytesToRead
0x1800b0dd4  mov     rcx, rsi; hFile
0x1800b0dd7  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rbx; lpOverlapped
0x1800b0ddc  call    cs:__imp_ReadFile
0x1800b0de3  nop     dword ptr [rax+rax+00h]
0x1800b0de8  cmp     eax, 1
0x1800b0deb  jnz     short loc_1800B0E4A
0x1800b0ded  mov     r8d, [rsp+10E0h+NumberOfBytesRead]; cbInput
0x1800b0df2  test    r8d, r8d
0x1800b0df5  jz      short loc_1800B0E52
0x1800b0df7  mov     rdx, [rbp+0FE0h+lpBuffer]; pbInput
0x1800b0dfb  xor     r9d, r9d; dwFlags
0x1800b0dfe  mov     rcx, [rsp+10E0h+phHash]; hHash
0x1800b0e03  call    cs:__imp_BCryptHashData
0x1800b0e0a  nop     dword ptr [rax+rax+00h]
0x1800b0e0f  movsxd  rbx, eax
0x1800b0e12  test    eax, eax
0x1800b0e14  jns     short loc_1800B0DC3
0x1800b0e16  xor     edi, edi
0x1800b0e18  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1800b0e1e  jz      loc_1800B0F24
0x1800b0e24  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0e29  mov     rdx, [rcx]
0x1800b0e2c  mov     rax, [rdx+50h]
0x1800b0e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0e35  mov     [rsp+10E0h+var_1088], rdi
0x1800b0e3a  lea     r9, aSecrepairFaile_0; "SECREPAIR: Failed to Hash Data Chunk fo"...
0x1800b0e41  mov     [rsp+10E0h+var_1090], edi
0x1800b0e45  jmp     loc_1800B0EF2
0x1800b0e4a  test    eax, eax
0x1800b0e4c  jz      loc_1800B1170
0x1800b0e52  mov     r9d, 4; cbOutput
0x1800b0e58  mov     [rsp+10E0h+dwFlagsAndAttributes], ebx; dwFlags
0x1800b0e5c  lea     rax, [rbp+0FE0h+pcbResult]
0x1800b0e60  mov     dword ptr [rsp+10E0h+pbOutput], ebx
0x1800b0e64  lea     r8, [rsp+10E0h+pbOutput]; pbOutput
0x1800b0e69  mov     [rbp+0FE0h+pcbResult], ebx
0x1800b0e6c  lea     rdx, pszProperty; "HashDigestLength"
0x1800b0e73  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rax; pcbResult
0x1800b0e78  lea     ecx, [r9+3Dh]; hObject
0x1800b0e7c  call    cs:__imp_BCryptGetProperty
0x1800b0e83  nop     dword ptr [rax+rax+00h]
0x1800b0e88  movsxd  rbx, eax
0x1800b0e8b  xor     eax, eax
0x1800b0e8d  test    ebx, ebx
0x1800b0e8f  js      loc_1800B11E2
0x1800b0e95  mov     edx, dword ptr [rsp+10E0h+pbOutput]
0x1800b0e99  mov     rcx, r15
0x1800b0e9c  call    ?Resize@?$CTempBufferRef@E@@QEAAXH@Z; CTempBufferRef<uchar>::Resize(int)
0x1800b0ea1  mov     r8d, dword ptr [rsp+10E0h+pbOutput]; cbOutput
0x1800b0ea6  xor     r9d, r9d; dwFlags
0x1800b0ea9  mov     rdx, [r15]; pbOutput
0x1800b0eac  mov     rcx, [rsp+10E0h+phHash]; hHash
0x1800b0eb1  call    cs:__imp_BCryptFinishHash
0x1800b0eb8  nop     dword ptr [rax+rax+00h]
0x1800b0ebd  xor     r15d, r15d
0x1800b0ec0  movsxd  rbx, eax
0x1800b0ec3  test    eax, eax
0x1800b0ec5  jns     short loc_1800B0F34
0x1800b0ec7  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1800b0ece  jz      short loc_1800B0F24
0x1800b0ed0  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0ed5  mov     rdx, [rcx]
0x1800b0ed8  mov     rax, [rdx+50h]
0x1800b0edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ee1  mov     [rsp+10E0h+var_1088], r15; void *
0x1800b0ee6  lea     r9, aSecrepairFaile_3; "SECREPAIR: Failed to get the Hash Value"...
0x1800b0eed  mov     [rsp+10E0h+var_1090], r15d; unsigned int
0x1800b0ef2  lea     r8, aNull; "(NULL)"
0x1800b0ef9  mov     [rsp+10E0h+var_1098], r8; unsigned __int16 *
0x1800b0efe  mov     [rsp+10E0h+var_10A0], r8; unsigned __int16 *
0x1800b0f03  mov     [rsp+10E0h+var_10A8], r8; unsigned __int16 *
0x1800b0f08  mov     [rsp+10E0h+hTemplateFile], r8; unsigned __int16 *
0x1800b0f0d  mov     qword ptr [rsp+10E0h+dwFlagsAndAttributes], rbx; unsigned __int16 *
0x1800b0f12  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800b0f17  xor     edx, edx; unsigned __int16
0x1800b0f19  xor     r8d, r8d; int
0x1800b0f1c  lea     ecx, [rdx+9]; int
0x1800b0f1f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800b0f24  mov     ecx, ebx; Status
0x1800b0f26  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800b0f2d  nop     dword ptr [rax+rax+00h]
0x1800b0f32  mov     edi, eax
0x1800b0f34  mov     rcx, [r13+0]
0x1800b0f38  mov     rax, [rcx]
0x1800b0f3b  mov     rax, [rax+1B8h]
0x1800b0f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0f47  mov     rcx, [r13+0]
0x1800b0f4b  mov     rbx, rax
0x1800b0f4e  mov     rax, [rcx]
0x1800b0f51  mov     rax, [rax+1F8h]
0x1800b0f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0f5d  mov     r15d, eax
0x1800b0f60  test    edi, edi
0x1800b0f62  jnz     loc_1800B1228
0x1800b0f68  mov     rcx, [rbx]
0x1800b0f6b  lea     edx, [rdi+4]
0x1800b0f6e  mov     r8, r12
0x1800b0f71  mov     rax, [rcx+0C8h]
0x1800b0f78  mov     rcx, rbx
0x1800b0f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0f80  test    eax, eax
0x1800b0f82  jz      loc_1800B1228
0x1800b0f88  cmp     r15d, 4
0x1800b0f8c  jnz     loc_1800B1228
0x1800b0f92  mov     rdx, rsi; void *
0x1800b0f95  mov     rcx, r13; this
0x1800b0f98  call    ?SetFileToHashHandle@CMsiSecureRepairManager@@AEAAXPEAX@Z; CMsiSecureRepairManager::SetFileToHashHandle(void *)
0x1800b0f9d  jmp     loc_1800B1237
0x1800b0fa2  call    cs:__imp_GetLastError
0x1800b0fa9  nop     dword ptr [rax+rax+00h]
0x1800b0fae  mov     edi, eax
0x1800b0fb0  cmp     eax, 20h ; ' '
0x1800b0fb3  jnz     short loc_1800B0FC0
0x1800b0fb5  inc     ebx
0x1800b0fb7  cmp     ebx, 3Ch ; '<'
0x1800b0fba  jl      loc_1800B110D
0x1800b0fc0  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1800b0fc7  jz      short loc_1800B101C
0x1800b0fc9  mov     rcx, [rsp+10E0h+var_1078]
0x1800b0fce  mov     rax, [rcx]
0x1800b0fd1  mov     rax, [rax+50h]
0x1800b0fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0fda  lea     r8, aNull; "(NULL)"
0x1800b0fe1  xor     edx, edx; unsigned __int16
0x1800b0fe3  mov     [rsp+10E0h+var_1088], rdx; void *
0x1800b0fe8  lea     r9, aSecrepairFaile_9; "SECREPAIR: Failed to open the file:%s f"...
0x1800b0fef  mov     [rsp+10E0h+var_1090], edx; unsigned int
0x1800b0ff3  mov     [rsp+10E0h+var_1098], r8; unsigned __int16 *
0x1800b0ff8  mov     [rsp+10E0h+var_10A0], r8; unsigned __int16 *
0x1800b0ffd  lea     ecx, [rdx+9]; int
0x1800b1000  mov     [rsp+10E0h+var_10A8], r8; unsigned __int16 *
0x1800b1005  mov     [rsp+10E0h+hTemplateFile], r8; unsigned __int16 *
0x1800b100a  xor     r8d, r8d; int
0x1800b100d  mov     qword ptr [rsp+10E0h+dwFlagsAndAttributes], rdi; unsigned __int16 *
0x1800b1012  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800b1017  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800b101c  mov     bl, [rsp+10E0h+var_1080]
0x1800b1020  mov     rcx, [rsp+10E0h+phHash]; this
0x1800b1025  test    rcx, rcx
0x1800b1028  jnz     loc_1800B124B
0x1800b102e  test    bl, bl
0x1800b1030  jnz     loc_1800B125C
0x1800b1036  mov     rax, [r14]
0x1800b1039  mov     rcx, r14
0x1800b103c  test    edi, edi
0x1800b103e  jz      loc_1800B1274
0x1800b1044  mov     rax, [rax+68h]
0x1800b1048  mov     r8d, edi
0x1800b104b  mov     edx, 1
0x1800b1050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1055  lea     rcx, [rbp+0FE0h+var_1058]; this
0x1800b1059  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800b105e  mov     rcx, [rsp+10E0h+var_1078]
0x1800b1063  mov     rax, [rcx]
0x1800b1066  mov     rax, [rax+10h]
0x1800b106a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b106f  cmp     [rbp+0FE0h+var_1048], 1000h
0x1800b1076  jg      loc_1800B1266
0x1800b107c  mov     rax, r14
0x1800b107f  jmp     loc_1800B0C9A
0x1800b1084  mov     rcx, [rbp+0FE0h+lpBuffer]; void *
0x1800b1088  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b108d  jmp     loc_1800B0C97
  ... truncated ...
```
