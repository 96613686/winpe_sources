# CMsiPath::Writable(Bool &)

- ea: `0x180221e80`
- end: `0x18022229c`
- name: `?Writable@CMsiPath@@UEAAPEAVIMsiRecord@@AEAW4Bool@@@Z`
- size: `1052`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, enum Bool *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180097c78`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800ca378`
- `0x18014ae8c`
- `0x180153e68`
- `0x180221e80`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x1802220a7`
- `KERNEL32!SetFileInformationByHandle` at `0x1802220a7`
- `KERNEL32!GetLastError` at `0x180221ff1`
- `KERNEL32!GetLastError` at `0x18022207f`
- `KERNEL32!GetLastError` at `0x1802220b7`
- `KERNEL32!GetLastError` at `0x180221ff1`
- `KERNEL32!GetLastError` at `0x18022207f`
- `KERNEL32!GetLastError` at `0x1802220b7`
- `KERNEL32!CreateFileW` at `0x180221f61`
- `KERNEL32!CreateFileW` at `0x180222062`
- `KERNEL32!CreateFileW` at `0x180221f61`
- `KERNEL32!CreateFileW` at `0x180222062`
- `KERNEL32!GetTempFileNameW` at `0x180221fe1`
- `KERNEL32!GetTempFileNameW` at `0x180221fe1`

## string_xrefs

- `0x1802220fd`: `Error: Temporary file is already created: %s`

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
0x180221e80  mov     [rsp-8+arg_10], rbx
0x180221e85  push    rbp
0x180221e86  push    rsi
0x180221e87  push    rdi
0x180221e88  push    r12
0x180221e8a  push    r13
0x180221e8c  push    r14
0x180221e8e  push    r15
0x180221e90  lea     rbp, [rsp-1B0h]
0x180221e98  sub     rsp, 2B0h
0x180221e9f  mov     rax, cs:__security_cookie
0x180221ea6  xor     rax, rsp
0x180221ea9  mov     [rbp+1E0h+var_40], rax
0x180221eb0  mov     r13d, 1
0x180221eb6  xor     edi, edi
0x180221eb8  mov     r12, rdx
0x180221ebb  mov     r14, rcx
0x180221ebe  cmp     [rcx+2Ch], r13d
0x180221ec2  jbe     loc_180222266
0x180221ec8  mov     [rdx], edi
0x180221eca  xor     r9d, r9d
0x180221ecd  mov     rax, [rcx]
0x180221ed0  lea     rdx, [rsp+2E0h+var_270]
0x180221ed5  xor     r8d, r8d
0x180221ed8  mov     [rsp+2E0h+var_270], edi
0x180221edc  mov     rax, [rax+0C8h]
0x180221ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221ee8  mov     rsi, rax
0x180221eeb  test    rax, rax
0x180221eee  jnz     loc_180222192
0x180221ef4  mov     rcx, [r14]
0x180221ef7  mov     r15d, edi
0x180221efa  mov     [r14+2Ch], edi
0x180221efe  mov     rax, [rcx+38h]
0x180221f02  mov     rcx, r14
0x180221f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221f0a  mov     r8d, r13d
0x180221f0d  mov     [rsp+2E0h+var_278], rax
0x180221f12  lea     edx, [rdi+4]
0x180221f15  lea     rcx, [rsp+2E0h+var_278]
0x180221f1a  call    ?Remove@MsiString@@QEAA?AW4Bool@@W4iseEnum@@I@Z; MsiString::Remove(iseEnum,uint)
0x180221f1f  cmp     [r14+30h], edi
0x180221f23  jz      short loc_180221F2D
0x180221f25  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180221f2a  mov     r15d, r13d
0x180221f2d  mov     rcx, [rsp+2E0h+var_278]
0x180221f32  mov     rax, [rcx]
0x180221f35  mov     rax, [rax+50h]
0x180221f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221f3e  mov     [rsp+2E0h+hTemplateFile], rdi; hTemplateFile
0x180221f43  xor     r9d, r9d; lpSecurityAttributes
0x180221f46  mov     [rsp+2E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180221f4e  mov     r8d, r13d; dwShareMode
0x180221f51  mov     edx, 80000000h; dwDesiredAccess
0x180221f56  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180221f5e  mov     rcx, rax; lpFileName
0x180221f61  call    cs:__imp_CreateFileW
0x180221f68  nop     dword ptr [rax+rax+00h]
0x180221f6d  mov     [rsp+2E0h+var_268], rax
0x180221f72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180221f76  jz      loc_18022216D
0x180221f7c  test    r15d, r15d
0x180221f7f  jnz     short loc_180221F9F
0x180221f81  mov     rax, [r14]
0x180221f84  mov     rcx, r14
0x180221f87  mov     rax, [rax+248h]
0x180221f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221f93  test    al, al
0x180221f95  jz      short loc_180221F9F
0x180221f97  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180221f9c  mov     r15d, r13d
0x180221f9f  mov     eax, 7FFE0320h
0x180221fa4  mov     rax, [rax]
0x180221fa7  mov     ecx, ds:7FFE0004h
0x180221fae  imul    rcx, rax
0x180221fb2  shr     rcx, 18h
0x180221fb6  movzx   ebx, cx
0x180221fb9  mov     rcx, [rsp+2E0h+var_278]
0x180221fbe  test    ebx, ebx
0x180221fc0  cmovz   ebx, r13d
0x180221fc4  mov     rax, [rcx]
0x180221fc7  mov     rax, [rax+50h]
0x180221fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221fd0  lea     r9, [rbp+1E0h+TempFileName]; lpTempFileName
0x180221fd4  mov     r8d, ebx; uUnique
0x180221fd7  lea     rdx, aCmp; "CMP"
0x180221fde  mov     rcx, rax; lpPathName
0x180221fe1  call    cs:__imp_GetTempFileNameW
0x180221fe8  nop     dword ptr [rax+rax+00h]
0x180221fed  cmp     eax, ebx
0x180221fef  jz      short loc_18022203E
0x180221ff1  call    cs:__imp_GetLastError
0x180221ff8  nop     dword ptr [rax+rax+00h]
0x180221ffd  cmp     eax, 10Bh
0x180222002  jnz     loc_18022216D
0x180222008  mov     rax, [r14]
0x18022200b  mov     rcx, r14
0x18022200e  mov     rax, [rax+38h]
0x180222012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222017  mov     rdx, rax; struct IMsiString *
0x18022201a  mov     ecx, 94Dh; int
0x18022201f  mov     rbx, rax
0x180222022  call    ?PostError@@YAPEAVIMsiRecord@@HAEBVIMsiString@@@Z; PostError(int,IMsiString const &)
0x180222027  mov     rcx, [rbx]
0x18022202a  mov     rsi, rax
0x18022202d  mov     rax, [rcx+10h]
0x180222031  mov     rcx, rbx
0x180222034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222039  jmp     loc_18022216D
0x18022203e  mov     [rsp+2E0h+hTemplateFile], rdi; hTemplateFile
0x180222043  lea     rcx, [rbp+1E0h+TempFileName]; lpFileName
0x180222047  mov     [rsp+2E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18022204f  xor     r9d, r9d; lpSecurityAttributes
0x180222052  xor     r8d, r8d; dwShareMode
0x180222055  mov     [rsp+2E0h+dwCreationDisposition], 4; dwCreationDisposition
0x18022205d  mov     edx, 80010000h; dwDesiredAccess
0x180222062  call    cs:__imp_CreateFileW
0x180222069  nop     dword ptr [rax+rax+00h]
0x18022206e  mov     [rbp+1E0h+var_260], rax
0x180222072  mov     rbx, rax
0x180222075  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180222079  jz      loc_180222164
0x18022207f  call    cs:__imp_GetLastError
0x180222086  nop     dword ptr [rax+rax+00h]
0x18022208b  cmp     eax, 0B7h
0x180222090  jz      short loc_1802220E5
0x180222092  mov     r9d, r13d; dwBufferSize
0x180222095  mov     [rsp+2E0h+FileInformation], r13b
0x18022209a  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x18022209f  mov     edx, 4; FileInformationClass
0x1802220a4  mov     rcx, rbx; hFile
0x1802220a7  call    cs:__imp_SetFileInformationByHandle
0x1802220ae  nop     dword ptr [rax+rax+00h]
0x1802220b3  test    eax, eax
0x1802220b5  jnz     short loc_1802220DB
0x1802220b7  call    cs:__imp_GetLastError
0x1802220be  nop     dword ptr [rax+rax+00h]
0x1802220c3  lea     r8, [rbp+1E0h+TempFileName]; unsigned __int16 *
0x1802220c7  mov     ecx, 919h; int
0x1802220cc  mov     edx, eax; int
0x1802220ce  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1802220d3  mov     rsi, rax
0x1802220d6  jmp     loc_180222164
0x1802220db  mov     [r12], r13d
0x1802220df  mov     [r14+2Ch], r13d
0x1802220e3  jmp     short loc_180222164
0x1802220e5  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1802220eb  jz      short loc_180222133
0x1802220ed  mov     [rsp+2E0h+var_288], rdi; void *
0x1802220f2  lea     rax, aNull; "(NULL)"
0x1802220f9  mov     [rsp+2E0h+var_290], edi; unsigned int
0x1802220fd  lea     r9, aErrorTemporary; "Error: Temporary file is already create"...
0x180222104  mov     [rsp+2E0h+var_298], rax; unsigned __int16 *
0x180222109  xor     edx, edx; unsigned __int16
0x18022210b  mov     [rsp+2E0h+var_2A0], rax; unsigned __int16 *
0x180222110  xor     r8d, r8d; int
0x180222113  mov     [rsp+2E0h+var_2A8], rax; unsigned __int16 *
0x180222118  mov     [rsp+2E0h+hTemplateFile], rax; unsigned __int16 *
0x18022211d  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180222122  lea     ecx, [rdx+9]; int
0x180222125  lea     rax, [rbp+1E0h+TempFileName]
0x180222129  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; unsigned __int16 *
0x18022212e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180222133  mov     rax, [r14]
0x180222136  mov     rcx, r14
0x180222139  mov     rax, [rax+38h]
0x18022213d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222142  mov     rdx, rax; struct IMsiString *
0x180222145  mov     ecx, 910h; int
0x18022214a  mov     rbx, rax
0x18022214d  call    ?PostError@@YAPEAVIMsiRecord@@HAEBVIMsiString@@@Z; PostError(int,IMsiString const &)
0x180222152  mov     rcx, [rbx]
0x180222155  mov     rsi, rax
0x180222158  mov     rax, [rcx+10h]
0x18022215c  mov     rcx, rbx
0x18022215f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222164  lea     rcx, [rbp+1E0h+var_260]; this
0x180222168  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18022216d  lea     rcx, [rsp+2E0h+var_268]; this
0x180222172  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180222177  mov     rcx, [rsp+2E0h+var_278]
0x18022217c  mov     rax, [rcx]
0x18022217f  mov     rax, [rax+10h]
0x180222183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222188  test    r15d, r15d
0x18022218b  jz      short loc_180222192
0x18022218d  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180222192  cmp     [rsp+2E0h+var_270], edi
0x180222196  jz      loc_180222261
0x18022219c  mov     rax, [r14]
0x18022219f  lea     rcx, [rsp+2E0h+var_278]
0x1802221a4  mov     [rsp+2E0h+var_278], rdi
0x1802221a9  mov     rbx, [rax+58h]
0x1802221ad  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1802221b2  mov     rdx, rax
0x1802221b5  mov     rcx, r14
0x1802221b8  mov     rax, rbx
0x1802221bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802221c0  mov     rdx, rax
0x1802221c3  test    rax, rax
0x1802221c6  jz      short loc_1802221DE
0x1802221c8  test    rsi, rsi
0x1802221cb  jz      short loc_1802221D9
0x1802221cd  mov     rcx, [rax]
0x1802221d0  mov     rax, [rcx+10h]
0x1802221d4  mov     rcx, rdx
0x1802221d7  jmp     short loc_18022224D
0x1802221d9  mov     rsi, rdx
0x1802221dc  jmp     short loc_180222257
0x1802221de  cmp     [rsp+2E0h+var_270], edi
0x1802221e2  jz      short loc_180222257
0x1802221e4  mov     rcx, [rsp+2E0h+var_278]
0x1802221e9  mov     rax, [rcx]
0x1802221ec  mov     rax, [rax+1C0h]
0x1802221f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802221f8  test    al, al
0x1802221fa  jnz     short loc_180222257
0x1802221fc  mov     rcx, [rsp+2E0h+var_278]
0x180222201  lea     rdx, [rsp+2E0h+FileInformation]
0x180222206  mov     [rsp+2E0h+FileInformation], dil
0x18022220b  mov     rax, [rcx]
0x18022220e  mov     rax, [rax+0D0h]
0x180222215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022221a  mov     rcx, rax
0x18022221d  test    rax, rax
0x180222220  jnz     short loc_180222241
0x180222222  cmp     [rsp+2E0h+FileInformation], dil
0x180222227  jz      short loc_18022222E
0x180222229  sub     [rsp+2E0h+var_270], r13d
0x18022222e  mov     rcx, [rsp+2E0h+var_278]
0x180222233  mov     rax, [rcx]
0x180222236  mov     rax, [rax+70h]
0x18022223a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022223f  jmp     short loc_1802221DE
0x180222241  test    rsi, rsi
0x180222244  jz      short loc_180222254
0x180222246  mov     rax, [rax]
0x180222249  mov     rax, [rax+10h]
0x18022224d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222252  jmp     short loc_180222257
0x180222254  mov     rsi, rcx
0x180222257  lea     rcx, [rsp+2E0h+var_278]
0x18022225c  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180222261  mov     rax, rsi
0x180222264  jmp     short loc_180222271
0x180222266  cmp     [rcx+2Ch], edi
0x180222269  setnz   dil
0x18022226d  xor     eax, eax
0x18022226f  mov     [rdx], edi
0x180222271  mov     rcx, [rbp+1E0h+var_40]
0x180222278  xor     rcx, rsp; StackCookie
0x18022227b  call    __security_check_cookie
0x180222280  mov     rbx, [rsp+2E0h+arg_10]
0x180222288  add     rsp, 2B0h
0x18022228f  pop     r15
0x180222291  pop     r14
0x180222293  pop     r13
0x180222295  pop     r12
0x180222297  pop     rdi
0x180222298  pop     rsi
0x180222299  pop     rbp
0x18022229a  retn
```
