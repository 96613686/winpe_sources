# CMsiPath::FileCanBeOpened(ushort const *,ulong,bool &,ulong &,void * *)

- ea: `0x18006b1f0`
- end: `0x18006b597`
- name: `?FileCanBeOpened@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGKAEA_NAEAKPEAPEAX@Z`
- size: `935`
- prototype: `struct IMsiRecord *(CMsiPath *__hidden this, const unsigned __int16 *, unsigned int, bool *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x180064b4c`
- `0x180064f18`
- `0x18006ab6c`
- `0x18006b1f0`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006b28e`
- `KERNEL32!GetLastError` at `0x18006b327`
- `KERNEL32!GetLastError` at `0x18006b376`
- `KERNEL32!GetLastError` at `0x18006b410`
- `KERNEL32!GetLastError` at `0x18006b472`
- `KERNEL32!GetLastError` at `0x18006b4c5`
- `KERNEL32!GetLastError` at `0x18006b518`
- `KERNEL32!GetLastError` at `0x18006b28e`
- `KERNEL32!GetLastError` at `0x18006b327`
- `KERNEL32!GetLastError` at `0x18006b376`
- `KERNEL32!GetLastError` at `0x18006b410`
- `KERNEL32!GetLastError` at `0x18006b472`
- `KERNEL32!GetLastError` at `0x18006b4c5`
- `KERNEL32!GetLastError` at `0x18006b518`
- `KERNEL32!SetLastError` at `0x18006b525`
- `KERNEL32!SetLastError` at `0x18006b525`
- `KERNEL32!CreateFileW` at `0x18006b3fd`
- `KERNEL32!CreateFileW` at `0x18006b463`
- `KERNEL32!CreateFileW` at `0x18006b4b6`
- `KERNEL32!CreateFileW` at `0x18006b3fd`
- `KERNEL32!CreateFileW` at `0x18006b463`
- `KERNEL32!CreateFileW` at `0x18006b4b6`
- `KERNEL32!GetFileType` at `0x18006b4e4`
- `KERNEL32!GetFileType` at `0x18006b4e4`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::FileCanBeOpened(
        CMsiPath *this,
        const unsigned __int16 *a2,
        DWORD a3,
        bool *a4,
        unsigned int *a5,
        void **a6)
{
  void **v10; // r14
  unsigned int *v11; // rdi
  __int64 (__fastcall *v12)(CMsiPath *, const unsigned __int16 *, void **); // rbx
  __int64 v13; // rbx
  DWORD LastError; // eax
  void *v15; // rcx
  void (*v16)(void); // rax
  int v18; // r15d
  char v19; // al
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  const WCHAR *v24; // rax
  __int64 FileW; // rbx
  DWORD v26; // eax
  const WCHAR *v27; // rax
  const WCHAR *v28; // rax
  bool v29; // al
  __int64 v30; // rdi
  void *v31; // [rsp+80h] [rbp+40h] BYREF
  char v32; // [rsp+98h] [rbp+58h] BYREF

  (*(void (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 576LL))(this);
  v10 = a6;
  if ( a6 )
    *a6 = (void *)-1LL;
  v11 = a5;
  *a4 = 0;
  v31 = &MsiString::s_NullString;
  *v11 = 0;
  v12 = *(__int64 (__fastcall **)(CMsiPath *, const unsigned __int16 *, void **))(*(_QWORD *)this + 136LL);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v31 = &MsiString::s_NullString;
  v13 = v12(this, a2, &v31);
  if ( v13 )
  {
    LastError = GetLastError();
    v15 = v31;
    *v11 = LastError;
    v16 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
LABEL_5:
    v16();
    return (struct IMsiRecord *)v13;
  }
  v18 = a3 & 0x40120116;
  v19 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 544LL))(this);
  CImpersonate::CImpersonate((CImpersonate *)&v32, v19);
  LODWORD(a6) = 0;
  if ( (a3 & 0x40130116) != 0 )
  {
    v20 = *(_QWORD *)this;
    LODWORD(a5) = 0;
    v21 = (*(__int64 (__fastcall **)(CMsiPath *, unsigned int **))(v20 + 520))(this, &a5);
    v13 = v21;
    if ( v21 )
    {
      if ( !v18 )
      {
        *v11 = GetLastError();
        CImpersonate::~CImpersonate((CImpersonate *)&v32);
        v16 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
        goto LABEL_5;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    else if ( ((unsigned __int8)a5 & 1) != 0 )
    {
      v22 = *(_QWORD *)this;
      LODWORD(a6) = 1;
      v23 = (*(__int64 (__fastcall **)(CMsiPath *, __int64))(v22 + 528))(this, 4);
      if ( v23 )
      {
        *v11 = GetLastError();
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_14:
        CImpersonate::~CImpersonate((CImpersonate *)&v32);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
        return 0;
      }
    }
    else
    {
      LODWORD(a6) = 0;
    }
  }
  v24 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
  FileW = (__int64)CreateFileW(v24, a3, 7u, 0, 3u, 0x100000u, 0);
  if ( FileW != -1 )
    goto LABEL_27;
  v26 = GetLastError();
  *v11 = v26;
  if ( !v18 || v26 != 2 )
    goto LABEL_25;
  v27 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
  FileW = (__int64)CreateFileW(v27, a3, 7u, 0, 1u, 0x4100000u, 0);
  if ( FileW == -1 )
    *v11 = GetLastError();
  v26 = *v11;
  if ( *v11 != 31 )
  {
    if ( FileW != -1 )
      goto LABEL_27;
LABEL_25:
    if ( v26 == 32 )
      *a4 = 1;
    goto LABEL_33;
  }
  v28 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
  FileW = (__int64)CreateFileW(v28, a3, 7u, 0, 1u, 0x4100000u, 0);
  if ( FileW == -1 )
  {
    v26 = GetLastError();
    *v11 = v26;
    goto LABEL_25;
  }
LABEL_27:
  v29 = GetFileType((HANDLE)FileW) - 2 > 1;
  *a4 = v29;
  if ( v10 && v29 )
  {
    *v10 = (void *)FileW;
  }
  else
  {
    MsiCloseUnregisteredSysHandle(FileW);
    FileW = -1;
  }
  if ( !*a4 )
  {
    *v11 = GetLastError();
    SetLastError(0x6Eu);
  }
LABEL_33:
  if ( !(_DWORD)a6 )
    goto LABEL_14;
  v30 = (*(__int64 (__fastcall **)(CMsiPath *, __int64, __int64))(*(_QWORD *)this + 528LL))(this, 4, 1);
  if ( !v30 )
    goto LABEL_14;
  if ( FileW != -1 )
    MsiCloseUnregisteredSysHandle(FileW);
  if ( v10 )
    *v10 = (void *)-1LL;
  CImpersonate::~CImpersonate((CImpersonate *)&v32);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
  return (struct IMsiRecord *)v30;
}

```

## disassembly

```asm
0x18006b1f0  mov     [rsp-38h+arg_8], rbx
0x18006b1f5  push    rbp
0x18006b1f6  push    rsi
0x18006b1f7  push    rdi
0x18006b1f8  push    r12
0x18006b1fa  push    r13
0x18006b1fc  push    r14
0x18006b1fe  push    r15
0x18006b200  mov     rbp, rsp
0x18006b203  sub     rsp, 40h
0x18006b207  mov     rax, [rcx]
0x18006b20a  mov     r12, r9
0x18006b20d  mov     r13d, r8d
0x18006b210  mov     r15, rdx
0x18006b213  mov     rsi, rcx
0x18006b216  mov     rax, [rax+240h]
0x18006b21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b222  mov     r14, [rbp+arg_28]
0x18006b226  test    r14, r14
0x18006b229  jz      short loc_18006B232
0x18006b22b  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18006b232  mov     rdi, [rbp+arg_20]
0x18006b236  lea     rdx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18006b23d  mov     byte ptr [r12], 0
0x18006b242  mov     [rbp+arg_0], rdx
0x18006b246  mov     dword ptr [rdi], 0
0x18006b24c  mov     rax, [rsi]
0x18006b24f  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18006b256  mov     rbx, [rax+88h]
0x18006b25d  mov     rax, [rcx+10h]
0x18006b261  mov     rcx, rdx
0x18006b264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b269  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18006b270  mov     rdx, r15
0x18006b273  mov     [rbp+arg_0], rax
0x18006b277  lea     r8, [rbp+arg_0]
0x18006b27b  mov     rax, rbx
0x18006b27e  mov     rcx, rsi
0x18006b281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b286  mov     rbx, rax
0x18006b289  test    rax, rax
0x18006b28c  jz      short loc_18006B2AE
0x18006b28e  call    cs:__imp_GetLastError
0x18006b294  mov     rcx, [rbp+arg_0]
0x18006b298  mov     [rdi], eax
0x18006b29a  mov     rdx, [rcx]
0x18006b29d  mov     rax, [rdx+10h]
0x18006b2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2a6  mov     rax, rbx
0x18006b2a9  jmp     loc_18006B3A8
0x18006b2ae  mov     rax, [rsi]
0x18006b2b1  mov     r15d, r13d
0x18006b2b4  mov     rcx, rsi
0x18006b2b7  and     r15d, 40120116h
0x18006b2be  mov     rax, [rax+220h]
0x18006b2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2ca  mov     dl, al; bool
0x18006b2cc  lea     rcx, [rbp+arg_18]; this
0x18006b2d0  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x18006b2d5  mov     dword ptr [rbp+arg_28], 0
0x18006b2dc  test    r13d, 40130116h
0x18006b2e3  jz      loc_18006B3C7
0x18006b2e9  mov     rax, [rsi]
0x18006b2ec  lea     rdx, [rbp+arg_20]
0x18006b2f0  mov     rcx, rsi
0x18006b2f3  mov     dword ptr [rbp+arg_20], 0
0x18006b2fa  mov     rax, [rax+208h]
0x18006b301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b306  mov     rbx, rax
0x18006b309  test    rax, rax
0x18006b30c  jz      short loc_18006B348
0x18006b30e  test    r15d, r15d
0x18006b311  jz      short loc_18006B327
0x18006b313  mov     rcx, [rax]
0x18006b316  mov     rax, [rcx+10h]
0x18006b31a  mov     rcx, rbx
0x18006b31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b322  jmp     loc_18006B3C7
0x18006b327  call    cs:__imp_GetLastError
0x18006b32d  lea     rcx, [rbp+arg_18]; this
0x18006b331  mov     [rdi], eax
0x18006b333  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18006b338  mov     rcx, [rbp+arg_0]
0x18006b33c  mov     rax, [rcx]
0x18006b33f  mov     rax, [rax+10h]
0x18006b343  jmp     loc_18006B2A1
0x18006b348  test    byte ptr [rbp+arg_20], 1
0x18006b34c  jz      short loc_18006B3C0
0x18006b34e  mov     rax, [rsi]
0x18006b351  xor     r8d, r8d
0x18006b354  mov     rcx, rsi
0x18006b357  mov     dword ptr [rbp+arg_28], 1
0x18006b35e  mov     rax, [rax+210h]
0x18006b365  lea     edx, [r8+4]
0x18006b369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b36e  mov     rbx, rax
0x18006b371  test    rax, rax
0x18006b374  jz      short loc_18006B3C7
0x18006b376  call    cs:__imp_GetLastError
0x18006b37c  mov     [rdi], eax
0x18006b37e  mov     rcx, [rbx]
0x18006b381  mov     rax, [rcx+10h]
0x18006b385  mov     rcx, rbx
0x18006b388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b38d  lea     rcx, [rbp+arg_18]; this
0x18006b391  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18006b396  mov     rcx, [rbp+arg_0]
0x18006b39a  mov     rax, [rcx]
0x18006b39d  mov     rax, [rax+10h]
0x18006b3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3a6  xor     eax, eax
0x18006b3a8  mov     rbx, [rsp+40h+arg_8]
0x18006b3b0  add     rsp, 40h
0x18006b3b4  pop     r15
0x18006b3b6  pop     r14
0x18006b3b8  pop     r13
0x18006b3ba  pop     r12
0x18006b3bc  pop     rdi
0x18006b3bd  pop     rsi
0x18006b3be  pop     rbp
0x18006b3bf  retn
0x18006b3c0  mov     dword ptr [rbp+arg_28], 0
0x18006b3c7  mov     rcx, [rbp+arg_0]
0x18006b3cb  mov     rax, [rcx]
0x18006b3ce  mov     rax, [rax+50h]
0x18006b3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3d7  xor     r9d, r9d; lpSecurityAttributes
0x18006b3da  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18006b3e3  mov     [rsp+40h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18006b3eb  mov     edx, r13d; dwDesiredAccess
0x18006b3ee  mov     rcx, rax; lpFileName
0x18006b3f1  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x18006b3f9  lea     r8d, [r9+7]; dwShareMode
0x18006b3fd  call    cs:__imp_CreateFileW
0x18006b403  mov     rbx, rax
0x18006b406  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b40a  jnz     loc_18006B4E1
0x18006b410  call    cs:__imp_GetLastError
0x18006b416  mov     [rdi], eax
0x18006b418  test    r15d, r15d
0x18006b41b  jz      loc_18006B4D5
0x18006b421  cmp     eax, 2
0x18006b424  jnz     loc_18006B4D5
0x18006b42a  mov     rcx, [rbp+arg_0]
0x18006b42e  mov     rax, [rcx]
0x18006b431  mov     rax, [rax+50h]
0x18006b435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b43a  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18006b443  lea     r15d, [rbx+8]
0x18006b447  mov     r8d, r15d; dwShareMode
0x18006b44a  mov     [rsp+40h+dwFlagsAndAttributes], 4100000h; dwFlagsAndAttributes
0x18006b452  xor     r9d, r9d; lpSecurityAttributes
0x18006b455  mov     [rsp+40h+dwCreationDisposition], 1; dwCreationDisposition
0x18006b45d  mov     edx, r13d; dwDesiredAccess
0x18006b460  mov     rcx, rax; lpFileName
0x18006b463  call    cs:__imp_CreateFileW
0x18006b469  mov     rbx, rax
0x18006b46c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b470  jnz     short loc_18006B47A
0x18006b472  call    cs:__imp_GetLastError
0x18006b478  mov     [rdi], eax
0x18006b47a  mov     eax, [rdi]
0x18006b47c  cmp     eax, 1Fh
0x18006b47f  jnz     short loc_18006B4CF
0x18006b481  mov     rcx, [rbp+arg_0]
0x18006b485  mov     rax, [rcx]
0x18006b488  mov     rax, [rax+50h]
0x18006b48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b491  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18006b49a  xor     r9d, r9d; lpSecurityAttributes
0x18006b49d  mov     [rsp+40h+dwFlagsAndAttributes], 4100000h; dwFlagsAndAttributes
0x18006b4a5  mov     r8d, r15d; dwShareMode
0x18006b4a8  mov     edx, r13d; dwDesiredAccess
0x18006b4ab  mov     [rsp+40h+dwCreationDisposition], 1; dwCreationDisposition
0x18006b4b3  mov     rcx, rax; lpFileName
0x18006b4b6  call    cs:__imp_CreateFileW
0x18006b4bc  mov     rbx, rax
0x18006b4bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b4c3  jnz     short loc_18006B4E1
0x18006b4c5  call    cs:__imp_GetLastError
0x18006b4cb  mov     [rdi], eax
0x18006b4cd  jmp     short loc_18006B4D5
0x18006b4cf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18006b4d3  jnz     short loc_18006B4E1
0x18006b4d5  cmp     eax, 20h ; ' '
0x18006b4d8  jnz     short loc_18006B52B
0x18006b4da  mov     byte ptr [r12], 1
0x18006b4df  jmp     short loc_18006B52B
0x18006b4e1  mov     rcx, rbx; hFile
0x18006b4e4  call    cs:__imp_GetFileType
0x18006b4ea  add     eax, 0FFFFFFFEh
0x18006b4ed  cmp     eax, 1
0x18006b4f0  setnbe  al
0x18006b4f3  mov     [r12], al
0x18006b4f7  test    r14, r14
0x18006b4fa  jz      short loc_18006B505
0x18006b4fc  test    al, al
0x18006b4fe  jz      short loc_18006B505
0x18006b500  mov     [r14], rbx
0x18006b503  jmp     short loc_18006B511
0x18006b505  mov     rcx, rbx
0x18006b508  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x18006b50d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006b511  cmp     byte ptr [r12], 0
0x18006b516  jnz     short loc_18006B52B
0x18006b518  call    cs:__imp_GetLastError
0x18006b51e  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18006b523  mov     [rdi], eax
0x18006b525  call    cs:__imp_SetLastError
0x18006b52b  cmp     dword ptr [rbp+arg_28], 0
0x18006b52f  jz      loc_18006B38D
0x18006b535  mov     rax, [rsi]
0x18006b538  mov     edx, 4
0x18006b53d  mov     rcx, rsi
0x18006b540  mov     rax, [rax+210h]
0x18006b547  lea     r8d, [rdx-3]
0x18006b54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b550  mov     rdi, rax
0x18006b553  test    rax, rax
0x18006b556  jz      loc_18006B38D
0x18006b55c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18006b560  jz      short loc_18006B56A
0x18006b562  mov     rcx, rbx
0x18006b565  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x18006b56a  test    r14, r14
0x18006b56d  jz      short loc_18006B576
0x18006b56f  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18006b576  lea     rcx, [rbp+arg_18]; this
0x18006b57a  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18006b57f  mov     rcx, [rbp+arg_0]
0x18006b583  mov     rax, [rcx]
0x18006b586  mov     rax, [rax+10h]
0x18006b58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b58f  mov     rax, rdi
0x18006b592  jmp     loc_18006B3A8
```
