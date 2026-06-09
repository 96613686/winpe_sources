# CMsiPath::FileCanBeOpened(ushort const *,ulong,bool &,ulong &,void * *)

- ea: `0x18010d980`
- end: `0x18010dd70`
- name: `?FileCanBeOpened@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGKAEA_NAEAKPEAPEAX@Z`
- size: `1008`
- prototype: `struct IMsiRecord *(CMsiPath *__hidden this, const unsigned __int16 *, unsigned int, bool *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x180013d64`
- `0x180014f18`
- `0x18006a558`
- `0x18010d980`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18010da1e`
- `KERNEL32!GetLastError` at `0x18010dabd`
- `KERNEL32!GetLastError` at `0x18010db12`
- `KERNEL32!GetLastError` at `0x18010dbb9`
- `KERNEL32!GetLastError` at `0x18010dc27`
- `KERNEL32!GetLastError` at `0x18010dc86`
- `KERNEL32!GetLastError` at `0x18010dce5`
- `KERNEL32!GetLastError` at `0x18010da1e`
- `KERNEL32!GetLastError` at `0x18010dabd`
- `KERNEL32!GetLastError` at `0x18010db12`
- `KERNEL32!GetLastError` at `0x18010dbb9`
- `KERNEL32!GetLastError` at `0x18010dc27`
- `KERNEL32!GetLastError` at `0x18010dc86`
- `KERNEL32!GetLastError` at `0x18010dce5`
- `KERNEL32!SetLastError` at `0x18010dcf8`
- `KERNEL32!SetLastError` at `0x18010dcf8`
- `KERNEL32!CreateFileW` at `0x18010dba0`
- `KERNEL32!CreateFileW` at `0x18010dc12`
- `KERNEL32!CreateFileW` at `0x18010dc71`
- `KERNEL32!CreateFileW` at `0x18010dba0`
- `KERNEL32!CreateFileW` at `0x18010dc12`
- `KERNEL32!CreateFileW` at `0x18010dc71`
- `KERNEL32!GetFileType` at `0x18010dcab`
- `KERNEL32!GetFileType` at `0x18010dcab`

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
0x18010d980  mov     [rsp-38h+arg_8], rbx
0x18010d985  push    rbp
0x18010d986  push    rsi
0x18010d987  push    rdi
0x18010d988  push    r12
0x18010d98a  push    r13
0x18010d98c  push    r14
0x18010d98e  push    r15
0x18010d990  mov     rbp, rsp
0x18010d993  sub     rsp, 40h
0x18010d997  mov     rax, [rcx]
0x18010d99a  mov     r12, r9
0x18010d99d  mov     r13d, r8d
0x18010d9a0  mov     r15, rdx
0x18010d9a3  mov     rsi, rcx
0x18010d9a6  mov     rax, [rax+240h]
0x18010d9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d9b2  mov     r14, [rbp+arg_28]
0x18010d9b6  test    r14, r14
0x18010d9b9  jz      short loc_18010D9C2
0x18010d9bb  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18010d9c2  mov     rdi, [rbp+arg_20]
0x18010d9c6  lea     rdx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18010d9cd  mov     byte ptr [r12], 0
0x18010d9d2  mov     [rbp+arg_0], rdx
0x18010d9d6  mov     dword ptr [rdi], 0
0x18010d9dc  mov     rax, [rsi]
0x18010d9df  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18010d9e6  mov     rbx, [rax+88h]
0x18010d9ed  mov     rax, [rcx+10h]
0x18010d9f1  mov     rcx, rdx
0x18010d9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d9f9  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18010da00  mov     rdx, r15
0x18010da03  mov     [rbp+arg_0], rax
0x18010da07  lea     r8, [rbp+arg_0]
0x18010da0b  mov     rax, rbx
0x18010da0e  mov     rcx, rsi
0x18010da11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010da16  mov     rbx, rax
0x18010da19  test    rax, rax
0x18010da1c  jz      short loc_18010DA44
0x18010da1e  call    cs:__imp_GetLastError
0x18010da25  nop     dword ptr [rax+rax+00h]
0x18010da2a  mov     rcx, [rbp+arg_0]
0x18010da2e  mov     [rdi], eax
0x18010da30  mov     rdx, [rcx]
0x18010da33  mov     rax, [rdx+10h]
0x18010da37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010da3c  mov     rax, rbx
0x18010da3f  jmp     loc_18010DB4A
0x18010da44  mov     rax, [rsi]
0x18010da47  mov     r15d, r13d
0x18010da4a  mov     rcx, rsi
0x18010da4d  and     r15d, 40120116h
0x18010da54  mov     rax, [rax+220h]
0x18010da5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010da60  mov     dl, al; bool
0x18010da62  lea     rcx, [rbp+arg_18]; this
0x18010da66  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x18010da6b  mov     dword ptr [rbp+arg_28], 0
0x18010da72  test    r13d, 40130116h
0x18010da79  jz      loc_18010DB6A
0x18010da7f  mov     rax, [rsi]
0x18010da82  lea     rdx, [rbp+arg_20]
0x18010da86  mov     rcx, rsi
0x18010da89  mov     dword ptr [rbp+arg_20], 0
0x18010da90  mov     rax, [rax+208h]
0x18010da97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010da9c  mov     rbx, rax
0x18010da9f  test    rax, rax
0x18010daa2  jz      short loc_18010DAE4
0x18010daa4  test    r15d, r15d
0x18010daa7  jz      short loc_18010DABD
0x18010daa9  mov     rcx, [rax]
0x18010daac  mov     rax, [rcx+10h]
0x18010dab0  mov     rcx, rbx
0x18010dab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dab8  jmp     loc_18010DB6A
0x18010dabd  call    cs:__imp_GetLastError
0x18010dac4  nop     dword ptr [rax+rax+00h]
0x18010dac9  lea     rcx, [rbp+arg_18]; this
0x18010dacd  mov     [rdi], eax
0x18010dacf  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18010dad4  mov     rcx, [rbp+arg_0]
0x18010dad8  mov     rax, [rcx]
0x18010dadb  mov     rax, [rax+10h]
0x18010dadf  jmp     loc_18010DA37
0x18010dae4  test    byte ptr [rbp+arg_20], 1
0x18010dae8  jz      short loc_18010DB63
0x18010daea  mov     rax, [rsi]
0x18010daed  xor     r8d, r8d
0x18010daf0  mov     rcx, rsi
0x18010daf3  mov     dword ptr [rbp+arg_28], 1
0x18010dafa  mov     rax, [rax+210h]
0x18010db01  lea     edx, [r8+4]
0x18010db05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010db0a  mov     rbx, rax
0x18010db0d  test    rax, rax
0x18010db10  jz      short loc_18010DB6A
0x18010db12  call    cs:__imp_GetLastError
0x18010db19  nop     dword ptr [rax+rax+00h]
0x18010db1e  mov     [rdi], eax
0x18010db20  mov     rcx, [rbx]
0x18010db23  mov     rax, [rcx+10h]
0x18010db27  mov     rcx, rbx
0x18010db2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010db2f  lea     rcx, [rbp+arg_18]; this
0x18010db33  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18010db38  mov     rcx, [rbp+arg_0]
0x18010db3c  mov     rax, [rcx]
0x18010db3f  mov     rax, [rax+10h]
0x18010db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010db48  xor     eax, eax
0x18010db4a  mov     rbx, [rsp+40h+arg_8]
0x18010db52  add     rsp, 40h
0x18010db56  pop     r15
0x18010db58  pop     r14
0x18010db5a  pop     r13
0x18010db5c  pop     r12
0x18010db5e  pop     rdi
0x18010db5f  pop     rsi
0x18010db60  pop     rbp
0x18010db61  retn
0x18010db63  mov     dword ptr [rbp+arg_28], 0
0x18010db6a  mov     rcx, [rbp+arg_0]
0x18010db6e  mov     rax, [rcx]
0x18010db71  mov     rax, [rax+50h]
0x18010db75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010db7a  xor     r9d, r9d; lpSecurityAttributes
0x18010db7d  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18010db86  mov     [rsp+40h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18010db8e  mov     edx, r13d; dwDesiredAccess
0x18010db91  mov     rcx, rax; lpFileName
0x18010db94  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x18010db9c  lea     r8d, [r9+7]; dwShareMode
0x18010dba0  call    cs:__imp_CreateFileW
0x18010dba7  nop     dword ptr [rax+rax+00h]
0x18010dbac  mov     rbx, rax
0x18010dbaf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010dbb3  jnz     loc_18010DCA8
0x18010dbb9  call    cs:__imp_GetLastError
0x18010dbc0  nop     dword ptr [rax+rax+00h]
0x18010dbc5  mov     [rdi], eax
0x18010dbc7  test    r15d, r15d
0x18010dbca  jz      loc_18010DC9C
0x18010dbd0  cmp     eax, 2
0x18010dbd3  jnz     loc_18010DC9C
0x18010dbd9  mov     rcx, [rbp+arg_0]
0x18010dbdd  mov     rax, [rcx]
0x18010dbe0  mov     rax, [rax+50h]
0x18010dbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dbe9  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18010dbf2  lea     r15d, [rbx+8]
0x18010dbf6  mov     r8d, r15d; dwShareMode
0x18010dbf9  mov     [rsp+40h+dwFlagsAndAttributes], 4100000h; dwFlagsAndAttributes
0x18010dc01  xor     r9d, r9d; lpSecurityAttributes
0x18010dc04  mov     [rsp+40h+dwCreationDisposition], 1; dwCreationDisposition
0x18010dc0c  mov     edx, r13d; dwDesiredAccess
0x18010dc0f  mov     rcx, rax; lpFileName
0x18010dc12  call    cs:__imp_CreateFileW
0x18010dc19  nop     dword ptr [rax+rax+00h]
0x18010dc1e  mov     rbx, rax
0x18010dc21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010dc25  jnz     short loc_18010DC35
0x18010dc27  call    cs:__imp_GetLastError
0x18010dc2e  nop     dword ptr [rax+rax+00h]
0x18010dc33  mov     [rdi], eax
0x18010dc35  mov     eax, [rdi]
0x18010dc37  cmp     eax, 1Fh
0x18010dc3a  jnz     short loc_18010DC96
0x18010dc3c  mov     rcx, [rbp+arg_0]
0x18010dc40  mov     rax, [rcx]
0x18010dc43  mov     rax, [rax+50h]
0x18010dc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dc4c  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18010dc55  xor     r9d, r9d; lpSecurityAttributes
0x18010dc58  mov     [rsp+40h+dwFlagsAndAttributes], 4100000h; dwFlagsAndAttributes
0x18010dc60  mov     r8d, r15d; dwShareMode
0x18010dc63  mov     edx, r13d; dwDesiredAccess
0x18010dc66  mov     [rsp+40h+dwCreationDisposition], 1; dwCreationDisposition
0x18010dc6e  mov     rcx, rax; lpFileName
0x18010dc71  call    cs:__imp_CreateFileW
0x18010dc78  nop     dword ptr [rax+rax+00h]
0x18010dc7d  mov     rbx, rax
0x18010dc80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010dc84  jnz     short loc_18010DCA8
0x18010dc86  call    cs:__imp_GetLastError
0x18010dc8d  nop     dword ptr [rax+rax+00h]
0x18010dc92  mov     [rdi], eax
0x18010dc94  jmp     short loc_18010DC9C
0x18010dc96  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18010dc9a  jnz     short loc_18010DCA8
0x18010dc9c  cmp     eax, 20h ; ' '
0x18010dc9f  jnz     short loc_18010DD04
0x18010dca1  mov     byte ptr [r12], 1
0x18010dca6  jmp     short loc_18010DD04
0x18010dca8  mov     rcx, rbx; hFile
0x18010dcab  call    cs:__imp_GetFileType
0x18010dcb2  nop     dword ptr [rax+rax+00h]
0x18010dcb7  add     eax, 0FFFFFFFEh
0x18010dcba  cmp     eax, 1
0x18010dcbd  setnbe  al
0x18010dcc0  mov     [r12], al
0x18010dcc4  test    r14, r14
0x18010dcc7  jz      short loc_18010DCD2
0x18010dcc9  test    al, al
0x18010dccb  jz      short loc_18010DCD2
0x18010dccd  mov     [r14], rbx
0x18010dcd0  jmp     short loc_18010DCDE
0x18010dcd2  mov     rcx, rbx
0x18010dcd5  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x18010dcda  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18010dcde  cmp     byte ptr [r12], 0
0x18010dce3  jnz     short loc_18010DD04
0x18010dce5  call    cs:__imp_GetLastError
0x18010dcec  nop     dword ptr [rax+rax+00h]
0x18010dcf1  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18010dcf6  mov     [rdi], eax
0x18010dcf8  call    cs:__imp_SetLastError
0x18010dcff  nop     dword ptr [rax+rax+00h]
0x18010dd04  cmp     dword ptr [rbp+arg_28], 0
0x18010dd08  jz      loc_18010DB2F
0x18010dd0e  mov     rax, [rsi]
0x18010dd11  mov     edx, 4
0x18010dd16  mov     rcx, rsi
0x18010dd19  mov     rax, [rax+210h]
0x18010dd20  lea     r8d, [rdx-3]
0x18010dd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dd29  mov     rdi, rax
0x18010dd2c  test    rax, rax
0x18010dd2f  jz      loc_18010DB2F
0x18010dd35  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18010dd39  jz      short loc_18010DD43
0x18010dd3b  mov     rcx, rbx
0x18010dd3e  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x18010dd43  test    r14, r14
0x18010dd46  jz      short loc_18010DD4F
0x18010dd48  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18010dd4f  lea     rcx, [rbp+arg_18]; this
0x18010dd53  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18010dd58  mov     rcx, [rbp+arg_0]
0x18010dd5c  mov     rax, [rcx]
0x18010dd5f  mov     rax, [rax+10h]
0x18010dd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dd68  mov     rax, rdi
0x18010dd6b  jmp     loc_18010DB4A
```
