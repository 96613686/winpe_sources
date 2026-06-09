# CMsiPath::Writable(Bool &)

- ea: `0x1802182d0`
- end: `0x1802186c1`
- name: `?Writable@CMsiPath@@UEAAPEAVIMsiRecord@@AEAW4Bool@@@Z`
- size: `1009`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, enum Bool *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180025a18`
- `0x180027b54`
- `0x180035a8c`
- `0x180066074`
- `0x180083178`
- `0x1800833ec`
- `0x1800bc708`
- `0x180146548`
- `0x18014e4d4`
- `0x1802182d0`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x1802184d9`
- `KERNEL32!SetFileInformationByHandle` at `0x1802184d9`
- `KERNEL32!GetLastError` at `0x180218435`
- `KERNEL32!GetLastError` at `0x1802184b7`
- `KERNEL32!GetLastError` at `0x1802184e3`
- `KERNEL32!GetLastError` at `0x180218435`
- `KERNEL32!GetLastError` at `0x1802184b7`
- `KERNEL32!GetLastError` at `0x1802184e3`
- `KERNEL32!CreateFileW` at `0x1802183b1`
- `KERNEL32!CreateFileW` at `0x1802184a0`
- `KERNEL32!CreateFileW` at `0x1802183b1`
- `KERNEL32!CreateFileW` at `0x1802184a0`
- `KERNEL32!GetTempFileNameW` at `0x18021842b`
- `KERNEL32!GetTempFileNameW` at `0x18021842b`

## string_xrefs

- `0x180218523`: `Error: Temporary file is already created: %s`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::Writable(CMsiPath *this, enum Bool *a2)
{
  int v2; // edi
  __int64 v5; // rax
  struct IMsiRecord *v6; // rsi
  __int64 v7; // rcx
  int v8; // r15d
  const WCHAR *v9; // rax
  UINT v10; // ebx
  const WCHAR *v11; // rax
  const struct IMsiString *v12; // rbx
  HANDLE v13; // rbx
  DWORD LastError; // eax
  const struct IMsiString *v15; // rbx
  bool v16; // cl
  __int64 v17; // rax
  __int64 (__fastcall *v18)(CMsiPath *, __int64); // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  struct IMsiRecord *result; // rax
  char FileInformation[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  HANDLE FileW; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v28[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR TempFileName[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  if ( *((_DWORD *)this + 11) <= 1u )
  {
    LOBYTE(v2) = *((_DWORD *)this + 11) != 0;
    result = 0;
    *(_DWORD *)a2 = v2;
  }
  else
  {
    *(_DWORD *)a2 = 0;
    v5 = *(_QWORD *)this;
    v26 = 0;
    v6 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(CMsiPath *, int *, _QWORD, _QWORD))(v5 + 200))(
                                this,
                                &v26,
                                0,
                                0);
    if ( !v6 )
    {
      v7 = *(_QWORD *)this;
      v8 = 0;
      *((_DWORD *)this + 11) = 0;
      v25 = (*(__int64 (__fastcall **)(CMsiPath *))(v7 + 56))(this);
      MsiString::Remove(&v25, 4, 1);
      if ( *((_DWORD *)this + 12) )
      {
        StartImpersonating();
        v8 = 1;
      }
      v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      FileW = CreateFileW(v9, 0x80000000, 1u, 0, 3u, 0x2200000u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        if ( !v8 && (*(unsigned __int8 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 584LL))(this) )
        {
          StartImpersonating();
          v8 = 1;
        }
        v10 = (unsigned __int16)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24);
        if ( !(unsigned __int16)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24) )
          v10 = 1;
        v11 = (const WCHAR *)(*(__int64 (**)(void))(*(_QWORD *)v25 + 80LL))();
        if ( GetTempFileNameW(v11, L"CMP", v10, TempFileName) == v10 )
        {
          v28[0] = CreateFileW(TempFileName, 0x80010000, 0, 0, 4u, 0x80u, 0);
          v13 = v28[0];
          if ( v28[0] != (HANDLE)-1LL )
          {
            if ( GetLastError() == 183 )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"Error: Temporary file is already created: %s",
                  TempFileName,
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              v15 = (const struct IMsiString *)(*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
              v6 = PostError(2320, v15);
              (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v15 + 16LL))(v15);
            }
            else
            {
              FileInformation[0] = 1;
              if ( SetFileInformationByHandle(v13, FileDispositionInfo, FileInformation, 1u) )
              {
                *(_DWORD *)a2 = 1;
                *((_DWORD *)this + 11) = 1;
              }
              else
              {
                LastError = GetLastError();
                v6 = PostError(2329, LastError, TempFileName);
              }
            }
          }
          CHandle::~CHandle((CHandle *)v28);
        }
        else if ( GetLastError() == 267 )
        {
          v12 = (const struct IMsiString *)(*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
          v6 = PostError(2381, v12);
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      CHandle::~CHandle((CHandle *)&FileW);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v8 )
        StopImpersonating(v16);
    }
    if ( v26 )
    {
      v17 = *(_QWORD *)this;
      v25 = 0;
      v18 = *(__int64 (__fastcall **)(CMsiPath *, __int64))(v17 + 88);
      v19 = CComPointer<IEnumMsiRecord>::operator=(&v25);
      v20 = v18(this, v19);
      v21 = v20;
      if ( v20 )
      {
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        else
          v6 = (struct IMsiRecord *)v20;
      }
      else
      {
        while ( v26 && !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 448LL))(v25, v21) )
        {
          FileInformation[0] = 0;
          v22 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 208LL))(v25, FileInformation);
          if ( v22 )
          {
            if ( v6 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            else
              v6 = (struct IMsiRecord *)v22;
            break;
          }
          if ( FileInformation[0] )
            --v26;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 112LL))(v25);
        }
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v25);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1802182d0  mov     [rsp-8+arg_10], rbx
0x1802182d5  push    rbp
0x1802182d6  push    rsi
0x1802182d7  push    rdi
0x1802182d8  push    r12
0x1802182da  push    r13
0x1802182dc  push    r14
0x1802182de  push    r15
0x1802182e0  lea     rbp, [rsp-1B0h]
0x1802182e8  sub     rsp, 2B0h
0x1802182ef  mov     rax, cs:__security_cookie
0x1802182f6  xor     rax, rsp
0x1802182f9  mov     [rbp+1E0h+var_40], rax
0x180218300  mov     r13d, 1
0x180218306  xor     edi, edi
0x180218308  mov     r12, rdx
0x18021830b  mov     r14, rcx
0x18021830e  cmp     [rcx+2Ch], r13d
0x180218312  jbe     loc_18021868C
0x180218318  mov     [rdx], edi
0x18021831a  xor     r9d, r9d
0x18021831d  mov     rax, [rcx]
0x180218320  lea     rdx, [rsp+2E0h+var_270]
0x180218325  xor     r8d, r8d
0x180218328  mov     [rsp+2E0h+var_270], edi
0x18021832c  mov     rax, [rax+0C8h]
0x180218333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218338  mov     rsi, rax
0x18021833b  test    rax, rax
0x18021833e  jnz     loc_1802185B8
0x180218344  mov     rcx, [r14]
0x180218347  mov     r15d, edi
0x18021834a  mov     [r14+2Ch], edi
0x18021834e  mov     rax, [rcx+38h]
0x180218352  mov     rcx, r14
0x180218355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021835a  mov     r8d, r13d
0x18021835d  mov     [rsp+2E0h+var_278], rax
0x180218362  lea     edx, [rdi+4]
0x180218365  lea     rcx, [rsp+2E0h+var_278]
0x18021836a  call    ?Remove@MsiString@@QEAA?AW4Bool@@W4iseEnum@@I@Z; MsiString::Remove(iseEnum,uint)
0x18021836f  cmp     [r14+30h], edi
0x180218373  jz      short loc_18021837D
0x180218375  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18021837a  mov     r15d, r13d
0x18021837d  mov     rcx, [rsp+2E0h+var_278]
0x180218382  mov     rax, [rcx]
0x180218385  mov     rax, [rax+50h]
0x180218389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021838e  mov     [rsp+2E0h+hTemplateFile], rdi; hTemplateFile
0x180218393  xor     r9d, r9d; lpSecurityAttributes
0x180218396  mov     [rsp+2E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18021839e  mov     r8d, r13d; dwShareMode
0x1802183a1  mov     edx, 80000000h; dwDesiredAccess
0x1802183a6  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1802183ae  mov     rcx, rax; lpFileName
0x1802183b1  call    cs:__imp_CreateFileW
0x1802183b7  mov     [rsp+2E0h+var_268], rax
0x1802183bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802183c0  jz      loc_180218593
0x1802183c6  test    r15d, r15d
0x1802183c9  jnz     short loc_1802183E9
0x1802183cb  mov     rax, [r14]
0x1802183ce  mov     rcx, r14
0x1802183d1  mov     rax, [rax+248h]
0x1802183d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802183dd  test    al, al
0x1802183df  jz      short loc_1802183E9
0x1802183e1  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1802183e6  mov     r15d, r13d
0x1802183e9  mov     eax, 7FFE0320h
0x1802183ee  mov     rax, [rax]
0x1802183f1  mov     ecx, ds:7FFE0004h
0x1802183f8  imul    rcx, rax
0x1802183fc  shr     rcx, 18h
0x180218400  movzx   ebx, cx
0x180218403  mov     rcx, [rsp+2E0h+var_278]
0x180218408  test    ebx, ebx
0x18021840a  cmovz   ebx, r13d
0x18021840e  mov     rax, [rcx]
0x180218411  mov     rax, [rax+50h]
0x180218415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021841a  lea     r9, [rbp+1E0h+TempFileName]; lpTempFileName
0x18021841e  mov     r8d, ebx; uUnique
0x180218421  lea     rdx, aCmp; "CMP"
0x180218428  mov     rcx, rax; lpPathName
0x18021842b  call    cs:__imp_GetTempFileNameW
0x180218431  cmp     eax, ebx
0x180218433  jz      short loc_18021847C
0x180218435  call    cs:__imp_GetLastError
0x18021843b  cmp     eax, 10Bh
0x180218440  jnz     loc_180218593
0x180218446  mov     rax, [r14]
0x180218449  mov     rcx, r14
0x18021844c  mov     rax, [rax+38h]
0x180218450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218455  mov     rdx, rax; struct IMsiString *
0x180218458  mov     ecx, 94Dh; int
0x18021845d  mov     rbx, rax
0x180218460  call    ?PostError@@YAPEAVIMsiRecord@@HAEBVIMsiString@@@Z; PostError(int,IMsiString const &)
0x180218465  mov     rcx, [rbx]
0x180218468  mov     rsi, rax
0x18021846b  mov     rax, [rcx+10h]
0x18021846f  mov     rcx, rbx
0x180218472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218477  jmp     loc_180218593
0x18021847c  mov     [rsp+2E0h+hTemplateFile], rdi; hTemplateFile
0x180218481  lea     rcx, [rbp+1E0h+TempFileName]; lpFileName
0x180218485  mov     [rsp+2E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18021848d  xor     r9d, r9d; lpSecurityAttributes
0x180218490  xor     r8d, r8d; dwShareMode
0x180218493  mov     [rsp+2E0h+dwCreationDisposition], 4; dwCreationDisposition
0x18021849b  mov     edx, 80010000h; dwDesiredAccess
0x1802184a0  call    cs:__imp_CreateFileW
0x1802184a6  mov     [rbp+1E0h+var_260], rax
0x1802184aa  mov     rbx, rax
0x1802184ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802184b1  jz      loc_18021858A
0x1802184b7  call    cs:__imp_GetLastError
0x1802184bd  cmp     eax, 0B7h
0x1802184c2  jz      short loc_18021850B
0x1802184c4  mov     r9d, r13d; dwBufferSize
0x1802184c7  mov     [rsp+2E0h+FileInformation], r13b
0x1802184cc  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x1802184d1  mov     edx, 4; FileInformationClass
0x1802184d6  mov     rcx, rbx; hFile
0x1802184d9  call    cs:__imp_SetFileInformationByHandle
0x1802184df  test    eax, eax
0x1802184e1  jnz     short loc_180218501
0x1802184e3  call    cs:__imp_GetLastError
0x1802184e9  lea     r8, [rbp+1E0h+TempFileName]; unsigned __int16 *
0x1802184ed  mov     ecx, 919h; int
0x1802184f2  mov     edx, eax; int
0x1802184f4  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1802184f9  mov     rsi, rax
0x1802184fc  jmp     loc_18021858A
0x180218501  mov     [r12], r13d
0x180218505  mov     [r14+2Ch], r13d
0x180218509  jmp     short loc_18021858A
0x18021850b  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x180218511  jz      short loc_180218559
0x180218513  mov     [rsp+2E0h+var_288], rdi; void *
0x180218518  lea     rax, aNull; "(NULL)"
0x18021851f  mov     [rsp+2E0h+var_290], edi; unsigned int
0x180218523  lea     r9, aErrorTemporary; "Error: Temporary file is already create"...
0x18021852a  mov     [rsp+2E0h+var_298], rax; unsigned __int16 *
0x18021852f  xor     edx, edx; unsigned __int16
0x180218531  mov     [rsp+2E0h+var_2A0], rax; unsigned __int16 *
0x180218536  xor     r8d, r8d; int
0x180218539  mov     [rsp+2E0h+var_2A8], rax; unsigned __int16 *
0x18021853e  mov     [rsp+2E0h+hTemplateFile], rax; unsigned __int16 *
0x180218543  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180218548  lea     ecx, [rdx+9]; int
0x18021854b  lea     rax, [rbp+1E0h+TempFileName]
0x18021854f  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; unsigned __int16 *
0x180218554  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180218559  mov     rax, [r14]
0x18021855c  mov     rcx, r14
0x18021855f  mov     rax, [rax+38h]
0x180218563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218568  mov     rdx, rax; struct IMsiString *
0x18021856b  mov     ecx, 910h; int
0x180218570  mov     rbx, rax
0x180218573  call    ?PostError@@YAPEAVIMsiRecord@@HAEBVIMsiString@@@Z; PostError(int,IMsiString const &)
0x180218578  mov     rcx, [rbx]
0x18021857b  mov     rsi, rax
0x18021857e  mov     rax, [rcx+10h]
0x180218582  mov     rcx, rbx
0x180218585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021858a  lea     rcx, [rbp+1E0h+var_260]; this
0x18021858e  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180218593  lea     rcx, [rsp+2E0h+var_268]; this
0x180218598  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18021859d  mov     rcx, [rsp+2E0h+var_278]
0x1802185a2  mov     rax, [rcx]
0x1802185a5  mov     rax, [rax+10h]
0x1802185a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802185ae  test    r15d, r15d
0x1802185b1  jz      short loc_1802185B8
0x1802185b3  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1802185b8  cmp     [rsp+2E0h+var_270], edi
0x1802185bc  jz      loc_180218687
0x1802185c2  mov     rax, [r14]
0x1802185c5  lea     rcx, [rsp+2E0h+var_278]
0x1802185ca  mov     [rsp+2E0h+var_278], rdi
0x1802185cf  mov     rbx, [rax+58h]
0x1802185d3  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1802185d8  mov     rdx, rax
0x1802185db  mov     rcx, r14
0x1802185de  mov     rax, rbx
0x1802185e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802185e6  mov     rdx, rax
0x1802185e9  test    rax, rax
0x1802185ec  jz      short loc_180218604
0x1802185ee  test    rsi, rsi
0x1802185f1  jz      short loc_1802185FF
0x1802185f3  mov     rcx, [rax]
0x1802185f6  mov     rax, [rcx+10h]
0x1802185fa  mov     rcx, rdx
0x1802185fd  jmp     short loc_180218673
0x1802185ff  mov     rsi, rdx
0x180218602  jmp     short loc_18021867D
0x180218604  cmp     [rsp+2E0h+var_270], edi
0x180218608  jz      short loc_18021867D
0x18021860a  mov     rcx, [rsp+2E0h+var_278]
0x18021860f  mov     rax, [rcx]
0x180218612  mov     rax, [rax+1C0h]
0x180218619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021861e  test    al, al
0x180218620  jnz     short loc_18021867D
0x180218622  mov     rcx, [rsp+2E0h+var_278]
0x180218627  lea     rdx, [rsp+2E0h+FileInformation]
0x18021862c  mov     [rsp+2E0h+FileInformation], dil
0x180218631  mov     rax, [rcx]
0x180218634  mov     rax, [rax+0D0h]
0x18021863b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218640  mov     rcx, rax
0x180218643  test    rax, rax
0x180218646  jnz     short loc_180218667
0x180218648  cmp     [rsp+2E0h+FileInformation], dil
0x18021864d  jz      short loc_180218654
0x18021864f  sub     [rsp+2E0h+var_270], r13d
0x180218654  mov     rcx, [rsp+2E0h+var_278]
0x180218659  mov     rax, [rcx]
0x18021865c  mov     rax, [rax+70h]
0x180218660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218665  jmp     short loc_180218604
0x180218667  test    rsi, rsi
0x18021866a  jz      short loc_18021867A
0x18021866c  mov     rax, [rax]
0x18021866f  mov     rax, [rax+10h]
0x180218673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218678  jmp     short loc_18021867D
0x18021867a  mov     rsi, rcx
0x18021867d  lea     rcx, [rsp+2E0h+var_278]
0x180218682  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180218687  mov     rax, rsi
0x18021868a  jmp     short loc_180218697
0x18021868c  cmp     [rcx+2Ch], edi
0x18021868f  setnz   dil
0x180218693  xor     eax, eax
0x180218695  mov     [rdx], edi
0x180218697  mov     rcx, [rbp+1E0h+var_40]
0x18021869e  xor     rcx, rsp; StackCookie
0x1802186a1  call    __security_check_cookie
0x1802186a6  mov     rbx, [rsp+2E0h+arg_10]
0x1802186ae  add     rsp, 2B0h
0x1802186b5  pop     r15
0x1802186b7  pop     r14
0x1802186b9  pop     r13
0x1802186bb  pop     r12
0x1802186bd  pop     rdi
0x1802186be  pop     rsi
0x1802186bf  pop     rbp
0x1802186c0  retn
```
