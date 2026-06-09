# CMsiSecureRepairManager::CreateContentHash(ushort const *,CTempBufferRef<uchar> &)

- ea: `0x1800a86cc`
- end: `0x1800a8d97`
- name: `?CreateContentHash@CMsiSecureRepairManager@@AEAAPEAVIMsiRecord@@PEBGAEAV?$CTempBufferRef@E@@@Z`
- size: `1739`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a818c`
- `0x180208f44`

## callees

- `0x180025a18`
- `0x180026ffc`
- `0x18003bccc`
- `0x1800620e4`
- `0x180064b4c`
- `0x180064f18`
- `0x1800a86cc`
- `0x1800a8da0`
- `0x1800c2854`
- `0x18013a830`
- `0x1801575c4`
- `0x18020bbd0`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025ac10`
- `0x18025c010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a8a31`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a8a31`
- `KERNEL32!CloseHandle` at `0x1800a8d31`
- `KERNEL32!CloseHandle` at `0x1800a8d31`
- `KERNEL32!GetLastError` at `0x1800a8aa7`
- `KERNEL32!GetLastError` at `0x1800a8c7c`
- `KERNEL32!GetLastError` at `0x1800a8aa7`
- `KERNEL32!GetLastError` at `0x1800a8c7c`
- `KERNEL32!Sleep` at `0x1800a8c2b`
- `KERNEL32!Sleep` at `0x1800a8c2b`
- `KERNEL32!CreateFileW` at `0x1800a88a1`
- `KERNEL32!CreateFileW` at `0x1800a88a1`
- `KERNEL32!ReadFile` at `0x1800a88ff`
- `KERNEL32!ReadFile` at `0x1800a88ff`
- `bcrypt!BCryptFinishHash` at `0x1800a89c2`
- `bcrypt!BCryptFinishHash` at `0x1800a89c2`
- `bcrypt!BCryptCreateHash` at `0x1800a88d5`
- `bcrypt!BCryptCreateHash` at `0x1800a88d5`
- `bcrypt!BCryptHashData` at `0x1800a8920`
- `bcrypt!BCryptHashData` at `0x1800a8920`
- `bcrypt!BCryptGetProperty` at `0x1800a8993`
- `bcrypt!BCryptGetProperty` at `0x1800a8993`
- `bcrypt!BCryptDestroyHash` at `0x1800a8d4b`
- `bcrypt!BCryptDestroyHash` at `0x1800a8d4b`

## string_xrefs

- `0x1800a8bc5`: `SECREPAIR: Invalid source directory`
- `0x1800a8c52`: `SECREPAIR: Failed to create a hash object. Error:%d`
- `0x1800a8ae7`: `SECREPAIR: Failed to open the file:%s for computing its hash. Error:%d`
- `0x1800a8cb1`: `SECREPAIR: Failed to read the file:%s for computing its hash. Error:%d`
- `0x1800a8951`: `SECREPAIR: Failed to Hash Data Chunk for file:%s. Error:%d`
- `0x1800a8d04`: `SECREPAIR: Failed to get the Hash Length property. Error:%d`
- `0x1800a89f1`: `SECREPAIR: Failed to get the Hash Value for the file:%s. Error:%d`

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
  char v9; // bl
  struct IMsiRecord *Record; // r15
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
  int v24; // r14d
  DWORD v25; // eax
  const unsigned __int16 *v26; // rax
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  char ImpersonationFromPath; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbOutput[4]; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesRead; // [rsp+74h] [rbp-8Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-88h] BYREF
  ULONG pcbResult; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[8]; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+98h] [rbp-68h]
  _BYTE v38[4096]; // [rsp+A0h] [rbp-60h] BYREF

  LODWORD(LastError) = 0;
  NumberOfBytesRead = 0;
  phHash = 0;
  memset_0(v38, 0, sizeof(v38));
  v7 = *(_QWORD *)a1;
  lpBuffer = v38;
  v37 = 4096;
  v30 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v7 + 184LL))(v7, L"SourceDir");
  v8 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
  ImpersonationFromPath = GetImpersonationFromPath(v8);
  v9 = ImpersonationFromPath;
  CImpersonate::CImpersonate((CImpersonate *)v35, ImpersonationFromPath);
  Record = CreateRecord(2u);
  if ( !Record )
  {
    v11 = PostError(2402);
    CImpersonate::~CImpersonate((CImpersonate *)v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v37 > 4096 )
      operator delete(lpBuffer);
    return v11;
  }
  if ( !a2 )
  {
    LODWORD(LastError) = 87;
    goto LABEL_37;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v30 + 56LL))(v30) )
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
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v30 + 200LL))(
          v30,
          4,
          L"\\") )
    MsiString::operator+=(&v30, L"\\");
  (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 144LL))(v30, a2, &v30);
  if ( ImpersonationFromPath )
    ++HIDWORD(qword_1803096FC);
  v13 = 0;
  while ( 1 )
  {
    if ( v13 )
      Sleep(0x1388u);
    v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
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
            v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
            v21 = L"SECREPAIR: Failed to Hash Data Chunk for file:%s. Error:%d";
            goto LABEL_26;
          }
        }
        if ( !v18 )
        {
          LastError = (const unsigned __int16 *)GetLastError();
          if ( g_dmDiagnosticMode )
          {
            v28 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
            DebugString(
              9,
              0,
              0,
              L"SECREPAIR: Failed to read the file:%s for computing its hash. Error:%d",
              v28,
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
            v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
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
    v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
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
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v9 && HIDWORD(qword_1803096FC) )
    --HIDWORD(qword_1803096FC);
  v27 = *(_QWORD *)Record;
  if ( (_DWORD)LastError )
  {
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(v27 + 104))(Record, 1, (unsigned int)LastError);
    CImpersonate::~CImpersonate((CImpersonate *)v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v37 > 4096 )
      operator delete(lpBuffer);
    return Record;
  }
  else
  {
    (*(void (__fastcall **)(struct IMsiRecord *))(v27 + 16))(Record);
    CImpersonate::~CImpersonate((CImpersonate *)v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    CTempBuffer<unsigned char,4096>::~CTempBuffer<unsigned char,4096>(&lpBuffer);
    return 0;
  }
}

```

## disassembly

```asm
0x1800a86cc  mov     [rsp-8+arg_18], rbx
0x1800a86d1  push    rbp
0x1800a86d2  push    rsi
0x1800a86d3  push    rdi
0x1800a86d4  push    r12
0x1800a86d6  push    r13
0x1800a86d8  push    r14
0x1800a86da  push    r15
0x1800a86dc  lea     rbp, [rsp-0FB0h]
0x1800a86e4  mov     eax, 10B0h
0x1800a86e9  call    _alloca_probe
0x1800a86ee  sub     rsp, rax
0x1800a86f1  mov     rax, cs:__security_cookie
0x1800a86f8  xor     rax, rsp
0x1800a86fb  mov     [rbp+0FE0h+var_40], rax
0x1800a8702  mov     r14, r8
0x1800a8705  mov     r12, rdx
0x1800a8708  mov     r13, rcx
0x1800a870b  xor     edi, edi
0x1800a870d  xor     edx, edx; Val
0x1800a870f  mov     [rsp+10E0h+NumberOfBytesRead], edi
0x1800a8713  mov     r8d, 1000h; Size
0x1800a8719  mov     [rsp+10E0h+phHash], rdi
0x1800a871e  lea     rcx, [rbp+0FE0h+var_1040]; void *
0x1800a8722  call    memset_0
0x1800a8727  mov     rcx, [r13+0]
0x1800a872b  lea     rax, [rbp+0FE0h+var_1040]
0x1800a872f  mov     [rbp+0FE0h+lpBuffer], rax
0x1800a8733  lea     rdx, aSourcedir; "SourceDir"
0x1800a873a  mov     [rbp+0FE0h+var_1048], 1000h
0x1800a8741  mov     rax, [rcx]
0x1800a8744  mov     rax, [rax+0B8h]
0x1800a874b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8750  mov     [rsp+10E0h+var_1078], rax
0x1800a8755  mov     rcx, [rax]
0x1800a8758  mov     rdx, [rcx+50h]
0x1800a875c  mov     rcx, rax
0x1800a875f  mov     rax, rdx
0x1800a8762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8767  mov     rcx, rax; lpFileName
0x1800a876a  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x1800a876f  mov     dl, al; bool
0x1800a8771  mov     [rsp+10E0h+var_1080], al
0x1800a8775  lea     rcx, [rbp+0FE0h+var_1058]; this
0x1800a8779  mov     bl, al
0x1800a877b  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1800a8780  lea     ecx, [rdi+2]; unsigned int
0x1800a8783  call    ?CreateRecord@@YAAEAVIMsiRecord@@I@Z; CreateRecord(uint)
0x1800a8788  mov     r15, rax
0x1800a878b  test    rax, rax
0x1800a878e  jnz     short loc_1800A87F4
0x1800a8790  mov     ecx, 962h; int
0x1800a8795  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1800a879a  lea     rcx, [rbp+0FE0h+var_1058]; this
0x1800a879e  mov     rbx, rax
0x1800a87a1  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800a87a6  mov     rdx, [rsp+10E0h+var_1078]
0x1800a87ab  mov     rcx, [rdx]
0x1800a87ae  mov     rax, [rcx+10h]
0x1800a87b2  mov     rcx, rdx
0x1800a87b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a87ba  cmp     [rbp+0FE0h+var_1048], 1000h
0x1800a87c1  jg      loc_1800A8B93
0x1800a87c7  mov     rax, rbx
0x1800a87ca  mov     rcx, [rbp+0FE0h+var_40]
0x1800a87d1  xor     rcx, rsp; StackCookie
0x1800a87d4  call    __security_check_cookie
0x1800a87d9  mov     rbx, [rsp+10E0h+arg_18]
0x1800a87e1  add     rsp, 10B0h
0x1800a87e8  pop     r15
0x1800a87ea  pop     r14
0x1800a87ec  pop     r13
0x1800a87ee  pop     r12
0x1800a87f0  pop     rdi
0x1800a87f1  pop     rsi
0x1800a87f2  pop     rbp
0x1800a87f3  retn
0x1800a87f4  test    r12, r12
0x1800a87f7  jz      loc_1800A8BA1
0x1800a87fd  mov     rcx, [rsp+10E0h+var_1078]
0x1800a8802  mov     rax, [rcx]
0x1800a8805  mov     rax, [rax+38h]
0x1800a8809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a880e  test    eax, eax
0x1800a8810  jz      loc_1800A8BAB
0x1800a8816  mov     rcx, [rsp+10E0h+var_1078]
0x1800a881b  lea     r8, asc_18026F7A4; "\\"
0x1800a8822  mov     edx, 4
0x1800a8827  mov     rax, [rcx]
0x1800a882a  mov     rax, [rax+0C8h]
0x1800a8831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8836  test    eax, eax
0x1800a8838  jz      loc_1800A8BFE
0x1800a883e  mov     rcx, [rsp+10E0h+var_1078]
0x1800a8843  lea     r8, [rsp+10E0h+var_1078]
0x1800a8848  mov     rdx, r12
0x1800a884b  mov     rax, [rcx]
0x1800a884e  mov     rax, [rax+90h]
0x1800a8855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a885a  test    bl, bl
0x1800a885c  jnz     loc_1800A8C14
0x1800a8862  mov     ebx, edi
0x1800a8864  test    ebx, ebx
0x1800a8866  jnz     loc_1800A8C26
0x1800a886c  mov     rcx, [rsp+10E0h+var_1078]
0x1800a8871  mov     rax, [rcx]
0x1800a8874  mov     rax, [rax+50h]
0x1800a8878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a887d  xor     r9d, r9d; lpSecurityAttributes
0x1800a8880  mov     [rsp+10E0h+hTemplateFile], rdi; hTemplateFile
0x1800a8885  mov     [rsp+10E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a888d  mov     edx, 80000000h; dwDesiredAccess
0x1800a8892  mov     rcx, rax; lpFileName
0x1800a8895  mov     [rsp+10E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a889d  lea     r8d, [r9+1]; dwShareMode
0x1800a88a1  call    cs:__imp_CreateFileW
0x1800a88a7  mov     rsi, rax
0x1800a88aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a88ae  jz      loc_1800A8AA7
0x1800a88b4  xor     r9d, r9d; cbHashObject
0x1800a88b7  mov     dword ptr [rsp+10E0h+hTemplateFile], edi; dwFlags
0x1800a88bb  mov     [rsp+10E0h+dwFlagsAndAttributes], edi; cbSecret
0x1800a88bf  lea     rdx, [rsp+10E0h+phHash]; phHash
0x1800a88c4  xor     r8d, r8d; pbHashObject
0x1800a88c7  mov     [rsp+10E0h+phHash], rdi
0x1800a88cc  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rdi; pbSecret
0x1800a88d1  lea     ecx, [r9+41h]; hAlgorithm
0x1800a88d5  call    cs:__imp_BCryptCreateHash
0x1800a88db  movsxd  rbx, eax
0x1800a88de  test    eax, eax
0x1800a88e0  js      loc_1800A8C36
0x1800a88e6  mov     rdx, [rbp+0FE0h+lpBuffer]; lpBuffer
0x1800a88ea  lea     r9, [rsp+10E0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a88ef  xor     ebx, ebx
0x1800a88f1  mov     r8d, 1000h; nNumberOfBytesToRead
0x1800a88f7  mov     rcx, rsi; hFile
0x1800a88fa  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rbx; lpOverlapped
0x1800a88ff  call    cs:__imp_ReadFile
0x1800a8905  cmp     eax, 1
0x1800a8908  jnz     short loc_1800A8961
0x1800a890a  mov     r8d, [rsp+10E0h+NumberOfBytesRead]; cbInput
0x1800a890f  test    r8d, r8d
0x1800a8912  jz      short loc_1800A8969
0x1800a8914  mov     rdx, [rbp+0FE0h+lpBuffer]; pbInput
0x1800a8918  xor     r9d, r9d; dwFlags
0x1800a891b  mov     rcx, [rsp+10E0h+phHash]; hHash
0x1800a8920  call    cs:__imp_BCryptHashData
0x1800a8926  movsxd  rbx, eax
0x1800a8929  test    eax, eax
0x1800a892b  jns     short loc_1800A88E6
0x1800a892d  xor     edi, edi
0x1800a892f  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1800a8935  jz      loc_1800A8A2F
0x1800a893b  mov     rcx, [rsp+10E0h+var_1078]
0x1800a8940  mov     rdx, [rcx]
0x1800a8943  mov     rax, [rdx+50h]
0x1800a8947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a894c  mov     [rsp+10E0h+var_1088], rdi
0x1800a8951  lea     r9, aSecrepairFaile_0; "SECREPAIR: Failed to Hash Data Chunk fo"...
0x1800a8958  mov     [rsp+10E0h+var_1090], edi
0x1800a895c  jmp     loc_1800A89FD
0x1800a8961  test    eax, eax
0x1800a8963  jz      loc_1800A8C7C
0x1800a8969  mov     r9d, 4; cbOutput
0x1800a896f  mov     [rsp+10E0h+dwFlagsAndAttributes], ebx; dwFlags
0x1800a8973  lea     rax, [rbp+0FE0h+pcbResult]
0x1800a8977  mov     dword ptr [rsp+10E0h+pbOutput], ebx
0x1800a897b  lea     r8, [rsp+10E0h+pbOutput]; pbOutput
0x1800a8980  mov     [rbp+0FE0h+pcbResult], ebx
0x1800a8983  lea     rdx, pszProperty; "HashDigestLength"
0x1800a898a  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rax; pcbResult
0x1800a898f  lea     ecx, [r9+3Dh]; hObject
0x1800a8993  call    cs:__imp_BCryptGetProperty
0x1800a8999  movsxd  rbx, eax
0x1800a899c  xor     eax, eax
0x1800a899e  test    ebx, ebx
0x1800a89a0  js      loc_1800A8CE8
0x1800a89a6  mov     edx, dword ptr [rsp+10E0h+pbOutput]
0x1800a89aa  mov     rcx, r14
0x1800a89ad  call    ?Resize@?$CTempBufferRef@E@@QEAAXH@Z; CTempBufferRef<uchar>::Resize(int)
0x1800a89b2  mov     r8d, dword ptr [rsp+10E0h+pbOutput]; cbOutput
0x1800a89b7  xor     r9d, r9d; dwFlags
0x1800a89ba  mov     rdx, [r14]; pbOutput
0x1800a89bd  mov     rcx, [rsp+10E0h+phHash]; hHash
0x1800a89c2  call    cs:__imp_BCryptFinishHash
0x1800a89c8  xor     r14d, r14d
0x1800a89cb  movsxd  rbx, eax
0x1800a89ce  test    eax, eax
0x1800a89d0  jns     short loc_1800A8A39
0x1800a89d2  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1800a89d9  jz      short loc_1800A8A2F
0x1800a89db  mov     rcx, [rsp+10E0h+var_1078]
0x1800a89e0  mov     rdx, [rcx]
0x1800a89e3  mov     rax, [rdx+50h]
0x1800a89e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a89ec  mov     [rsp+10E0h+var_1088], r14; void *
0x1800a89f1  lea     r9, aSecrepairFaile_3; "SECREPAIR: Failed to get the Hash Value"...
0x1800a89f8  mov     [rsp+10E0h+var_1090], r14d; unsigned int
0x1800a89fd  lea     r8, aNull; "(NULL)"
0x1800a8a04  mov     [rsp+10E0h+var_1098], r8; unsigned __int16 *
0x1800a8a09  mov     [rsp+10E0h+var_10A0], r8; unsigned __int16 *
0x1800a8a0e  mov     [rsp+10E0h+var_10A8], r8; unsigned __int16 *
0x1800a8a13  mov     [rsp+10E0h+hTemplateFile], r8; unsigned __int16 *
0x1800a8a18  mov     qword ptr [rsp+10E0h+dwFlagsAndAttributes], rbx; unsigned __int16 *
0x1800a8a1d  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800a8a22  xor     edx, edx; unsigned __int16
0x1800a8a24  xor     r8d, r8d; int
0x1800a8a27  lea     ecx, [rdx+9]; int
0x1800a8a2a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800a8a2f  mov     ecx, ebx; Status
0x1800a8a31  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a8a37  mov     edi, eax
0x1800a8a39  mov     rcx, [r13+0]
0x1800a8a3d  mov     rax, [rcx]
0x1800a8a40  mov     rax, [rax+1B8h]
0x1800a8a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a4c  mov     rcx, [r13+0]
0x1800a8a50  mov     rbx, rax
0x1800a8a53  mov     rax, [rcx]
0x1800a8a56  mov     rax, [rax+1F8h]
0x1800a8a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a62  mov     r14d, eax
0x1800a8a65  test    edi, edi
0x1800a8a67  jnz     loc_1800A8D2E
0x1800a8a6d  mov     rcx, [rbx]
0x1800a8a70  lea     edx, [rdi+4]
0x1800a8a73  mov     r8, r12
0x1800a8a76  mov     rax, [rcx+0C8h]
0x1800a8a7d  mov     rcx, rbx
0x1800a8a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a85  test    eax, eax
0x1800a8a87  jz      loc_1800A8D2E
0x1800a8a8d  cmp     r14d, 4
0x1800a8a91  jnz     loc_1800A8D2E
0x1800a8a97  mov     rdx, rsi; void *
0x1800a8a9a  mov     rcx, r13; this
0x1800a8a9d  call    ?SetFileToHashHandle@CMsiSecureRepairManager@@AEAAXPEAX@Z; CMsiSecureRepairManager::SetFileToHashHandle(void *)
0x1800a8aa2  jmp     loc_1800A8D37
0x1800a8aa7  call    cs:__imp_GetLastError
0x1800a8aad  mov     edi, eax
0x1800a8aaf  cmp     eax, 20h ; ' '
0x1800a8ab2  jnz     short loc_1800A8ABF
0x1800a8ab4  inc     ebx
0x1800a8ab6  cmp     ebx, 3Ch ; '<'
0x1800a8ab9  jl      loc_1800A8C1F
0x1800a8abf  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1800a8ac6  jz      short loc_1800A8B1B
0x1800a8ac8  mov     rcx, [rsp+10E0h+var_1078]
0x1800a8acd  mov     rax, [rcx]
0x1800a8ad0  mov     rax, [rax+50h]
0x1800a8ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8ad9  lea     r8, aNull; "(NULL)"
0x1800a8ae0  xor     edx, edx; unsigned __int16
0x1800a8ae2  mov     [rsp+10E0h+var_1088], rdx; void *
0x1800a8ae7  lea     r9, aSecrepairFaile_9; "SECREPAIR: Failed to open the file:%s f"...
0x1800a8aee  mov     [rsp+10E0h+var_1090], edx; unsigned int
0x1800a8af2  mov     [rsp+10E0h+var_1098], r8; unsigned __int16 *
0x1800a8af7  mov     [rsp+10E0h+var_10A0], r8; unsigned __int16 *
0x1800a8afc  lea     ecx, [rdx+9]; int
0x1800a8aff  mov     [rsp+10E0h+var_10A8], r8; unsigned __int16 *
0x1800a8b04  mov     [rsp+10E0h+hTemplateFile], r8; unsigned __int16 *
0x1800a8b09  xor     r8d, r8d; int
0x1800a8b0c  mov     qword ptr [rsp+10E0h+dwFlagsAndAttributes], rdi; unsigned __int16 *
0x1800a8b11  mov     qword ptr [rsp+10E0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800a8b16  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800a8b1b  mov     bl, [rsp+10E0h+var_1080]
0x1800a8b1f  mov     rcx, [rsp+10E0h+phHash]; hHash
0x1800a8b24  test    rcx, rcx
0x1800a8b27  jnz     loc_1800A8D4B
0x1800a8b2d  test    bl, bl
0x1800a8b2f  jnz     short loc_1800A8B7F
0x1800a8b31  mov     rax, [r15]
0x1800a8b34  mov     rcx, r15
0x1800a8b37  test    edi, edi
0x1800a8b39  jz      loc_1800A8D64
0x1800a8b3f  mov     rax, [rax+68h]
0x1800a8b43  mov     r8d, edi
0x1800a8b46  mov     edx, 1
0x1800a8b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8b50  lea     rcx, [rbp+0FE0h+var_1058]; this
0x1800a8b54  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800a8b59  mov     rcx, [rsp+10E0h+var_1078]
0x1800a8b5e  mov     rax, [rcx]
0x1800a8b61  mov     rax, [rax+10h]
0x1800a8b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8b6a  cmp     [rbp+0FE0h+var_1048], 1000h
0x1800a8b71  jg      loc_1800A8D56
0x1800a8b77  mov     rax, r15
0x1800a8b7a  jmp     loc_1800A87CA
0x1800a8b7f  mov     eax, dword ptr cs:qword_1803096FC+4
0x1800a8b85  test    eax, eax
0x1800a8b87  jz      short loc_1800A8B31
0x1800a8b89  dec     eax
0x1800a8b8b  mov     dword ptr cs:qword_1803096FC+4, eax
0x1800a8b91  jmp     short loc_1800A8B31
0x1800a8b93  mov     rcx, [rbp+0FE0h+lpBuffer]; void *
0x1800a8b97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a8b9c  jmp     loc_1800A87C7
0x1800a8ba1  mov     edi, 57h ; 'W'
0x1800a8ba6  jmp     loc_1800A8B1F
  ... truncated ...
```
