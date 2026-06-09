# CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)

- ea: `0x1801f0578`
- end: `0x1801f09bf`
- name: `?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z`
- size: `1095`
- prototype: `bool __fastcall(CMsiOpExecute *__hidden this, struct IMsiRecord *, struct IMsiRecord *, int, struct IMsiRecord *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1801de0a0`
- `0x1801f0350`
- `0x1801f0578`
- `0x1801fe220`

## callees

- `0x180061334`
- `0x1800620e4`
- `0x18008a388`
- `0x1801e113c`
- `0x1801f0350`
- `0x1801f0578`
- `0x1801f22ac`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!EnumDependentServicesW` at `0x1801f075f`
- `ADVAPI32!EnumDependentServicesW` at `0x1801f07c5`
- `ADVAPI32!EnumDependentServicesW` at `0x1801f075f`
- `ADVAPI32!EnumDependentServicesW` at `0x1801f07c5`
- `ADVAPI32!ControlService` at `0x1801f06d8`
- `ADVAPI32!ControlService` at `0x1801f06d8`
- `ADVAPI32!CloseServiceHandle` at `0x1801f0717`
- `ADVAPI32!CloseServiceHandle` at `0x1801f096a`
- `ADVAPI32!CloseServiceHandle` at `0x1801f0717`
- `ADVAPI32!CloseServiceHandle` at `0x1801f096a`
- `KERNEL32!GetLastError` at `0x1801f069a`
- `KERNEL32!GetLastError` at `0x1801f06f9`
- `KERNEL32!GetLastError` at `0x1801f0765`
- `KERNEL32!GetLastError` at `0x1801f0945`
- `KERNEL32!GetLastError` at `0x1801f09a9`
- `KERNEL32!GetLastError` at `0x1801f069a`
- `KERNEL32!GetLastError` at `0x1801f06f9`
- `KERNEL32!GetLastError` at `0x1801f0765`
- `KERNEL32!GetLastError` at `0x1801f0945`
- `KERNEL32!GetLastError` at `0x1801f09a9`
- `KERNEL32!SetLastError` at `0x1801f094d`
- `KERNEL32!SetLastError` at `0x1801f09b4`
- `KERNEL32!SetLastError` at `0x1801f094d`
- `KERNEL32!SetLastError` at `0x1801f09b4`

## pseudocode

```c
char __fastcall CMsiOpExecute::StopService(
        CMsiOpExecute *this,
        struct IMsiRecord *a2,
        struct IMsiRecord *a3,
        int a4,
        struct IMsiRecord *a5)
{
  __int64 v7; // rax
  struct IMsiRecord *v9; // r13
  const struct IMsiString *v10; // rbx
  bool v11; // zf
  const struct IMsiString *v12; // rcx
  void (__fastcall *v13)(const struct IMsiString *); // rax
  const struct IMsiString *v15; // rdi
  SC_HANDLE ServiceHandle; // r12
  bool i; // r15
  CMsiOpExecute *v18; // rcx
  DWORD LastError; // eax
  int v20; // edx
  struct _ENUM_SERVICE_STATUSW *v21; // r15
  __int64 v22; // rdi
  DWORD v23; // r13d
  __int64 v24; // rax
  struct IMsiRecord *v25; // r15
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD cbBufSize; // [rsp+30h] [rbp-41h] BYREF
  DWORD ServicesReturned; // [rsp+34h] [rbp-3Dh] BYREF
  int v30; // [rsp+38h] [rbp-39h]
  struct IMsiRecord *v31; // [rsp+40h] [rbp-31h]
  struct IMsiRecord *v32; // [rsp+48h] [rbp-29h]
  void *v33; // [rsp+50h] [rbp-21h]
  CMsiOpExecute *v34; // [rsp+58h] [rbp-19h]
  __int64 v35; // [rsp+60h] [rbp-11h]
  _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-9h] BYREF

  v31 = a5;
  v7 = *(_QWORD *)a2;
  v34 = this;
  v32 = a3;
  v9 = a3;
  v10 = (const struct IMsiString *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(v7 + 72))(a2, 2);
  v30 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a2 + 56LL))(a2, 4);
  if ( !a4 )
  {
    v15 = (const struct IMsiString *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a2 + 72LL))(
                                       a2,
                                       1);
    ServiceHandle = GetServiceHandle(v15, v10, 0x2Cu);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( !ServiceHandle )
    {
      v11 = GetLastError() == 1060;
      v12 = v10;
      v13 = *(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v10 + 16LL);
      if ( !v11 )
        goto LABEL_3;
      v13(v10);
      return 1;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    i = 1;
    if ( ControlService(ServiceHandle, 1u, &ServiceStatus) )
    {
      CMsiOpExecute::StartServiceW(v34, a2, v9, 1);
    }
    else
    {
      LastError = GetLastError();
      v18 = (CMsiOpExecute *)(LastError - 1060);
      if ( (unsigned int)v18 <= 0x11 )
      {
        v20 = 131077;
        if ( _bittest(&v20, (unsigned int)v18) )
        {
          CloseServiceHandle(ServiceHandle);
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v10 + 16LL))(v10);
          return 1;
        }
      }
      if ( LastError == 1051 )
      {
        cbBufSize = 0;
        ServicesReturned = 0;
        EnumDependentServicesW(ServiceHandle, 1u, 0, 0, &cbBufSize, &ServicesReturned);
        if ( GetLastError() != 234 || !cbBufSize )
          goto LABEL_27;
        v21 = (struct _ENUM_SERVICE_STATUSW *)operator new(cbBufSize);
        v33 = v21;
        v22 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v31 + 72LL))(v31, 1);
        if ( EnumDependentServicesW(ServiceHandle, 1u, v21, cbBufSize, &cbBufSize, &ServicesReturned) )
        {
          v23 = 0;
          for ( i = 1; v23 < ServicesReturned; ++v23 )
          {
            v24 = *(_QWORD *)a2;
            v35 = 48LL * (int)v23;
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(v24 + 128))(
              a2,
              2,
              *(_QWORD *)((char *)v33 + v35));
            if ( !v30 )
              (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)a2 + 104LL))(a2, 4, 1);
            v25 = v31;
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v31 + 128LL))(
              v31,
              1,
              *(_QWORD *)((char *)v33 + v35 + 8));
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v25 + 128LL))(
              v25,
              2,
              *(_QWORD *)((char *)v33 + v35));
            i = CMsiOpExecute::StopService(v34, a2, v32, 0, v25);
            if ( !i )
              break;
          }
          v9 = v32;
        }
        else
        {
          v27 = GetLastError();
          i = 0;
          SetLastError(v27);
        }
        operator delete(v33);
        (*(void (__fastcall **)(struct IMsiRecord *, __int64, const struct IMsiString *))(*(_QWORD *)a2 + 120LL))(
          a2,
          2,
          v10);
        if ( !v30 )
          (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a2 + 104LL))(a2, 4);
        (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v31 + 120LL))(v31, 1, v22);
        (*(void (__fastcall **)(struct IMsiRecord *, __int64, const struct IMsiString *))(*(_QWORD *)v31 + 120LL))(
          v31,
          2,
          v10);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( i )
        {
LABEL_27:
          i = CMsiOpExecute::StopService(v34, a2, v9, 0, v31);
          if ( !i )
          {
            v26 = GetLastError();
            SetLastError(v26);
          }
        }
      }
    }
    if ( v30 )
      i = CMsiOpExecute::WaitForService(v18, ServiceHandle, 1u);
    CloseServiceHandle(ServiceHandle);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v10 + 16LL))(v10);
    return i;
  }
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, const struct IMsiString *))(*(_QWORD *)v9 + 120LL))(v9, 2, v10);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, 3, 2);
  v11 = (unsigned __int8)CMsiOpExecute::RollbackRecord(this, 77, v9) == 0;
  v12 = v10;
  v13 = *(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v10 + 16LL);
  if ( v11 )
  {
LABEL_3:
    v13(v12);
    return 0;
  }
  v13(v10);
  return 1;
}

```

## disassembly

```asm
0x1801f0578  mov     [rsp-8+arg_18], rbx
0x1801f057d  push    rbp
0x1801f057e  push    rsi
0x1801f057f  push    rdi
0x1801f0580  push    r12
0x1801f0582  push    r13
0x1801f0584  push    r14
0x1801f0586  push    r15
0x1801f0588  lea     rbp, [rsp-1Fh]
0x1801f058d  sub     rsp, 90h
0x1801f0594  mov     rax, cs:__security_cookie
0x1801f059b  xor     rax, rsp
0x1801f059e  mov     [rbp+4Fh+var_38], rax
0x1801f05a2  mov     rax, [rbp+4Fh+arg_20]
0x1801f05a6  mov     r14, rdx
0x1801f05a9  mov     [rbp+4Fh+var_80], rax
0x1801f05ad  mov     rsi, rcx
0x1801f05b0  mov     rax, [rdx]
0x1801f05b3  mov     r15d, 2
0x1801f05b9  mov     [rbp+4Fh+var_68], rcx
0x1801f05bd  mov     edx, r15d
0x1801f05c0  mov     rcx, r14
0x1801f05c3  mov     [rbp+4Fh+var_78], r8
0x1801f05c7  mov     edi, r9d
0x1801f05ca  mov     r13, r8
0x1801f05cd  mov     rax, [rax+48h]
0x1801f05d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f05d6  mov     rbx, rax
0x1801f05d9  lea     edx, [r15+2]
0x1801f05dd  mov     rax, [r14]
0x1801f05e0  mov     rcx, r14
0x1801f05e3  mov     rax, [rax+38h]
0x1801f05e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f05ec  mov     [rbp+4Fh+var_88], eax
0x1801f05ef  test    edi, edi
0x1801f05f1  jz      short loc_1801F065B
0x1801f05f3  mov     rax, [r13+0]
0x1801f05f7  mov     r8, rbx
0x1801f05fa  mov     edx, r15d
0x1801f05fd  mov     rcx, r13
0x1801f0600  mov     rax, [rax+78h]
0x1801f0604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0609  mov     rax, [r13+0]
0x1801f060d  lea     edx, [r15+1]
0x1801f0611  mov     r8d, r15d
0x1801f0614  mov     rcx, r13
0x1801f0617  mov     rax, [rax+68h]
0x1801f061b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0620  mov     r8, r13
0x1801f0623  lea     edx, [r15+4Bh]
0x1801f0627  mov     rcx, rsi
0x1801f062a  call    ?RollbackRecord@CMsiOpExecute@@QEAA_NW4ixoEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::RollbackRecord(ixoEnum,IMsiRecord &)
0x1801f062f  mov     rcx, [rbx]
0x1801f0632  test    al, al
0x1801f0634  mov     rdx, [rcx+10h]
0x1801f0638  mov     rcx, rbx
0x1801f063b  mov     rax, rdx
0x1801f063e  jnz     short loc_1801F064C
0x1801f0640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0645  xor     al, al
0x1801f0647  jmp     loc_1801F0982
0x1801f064c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0651  mov     eax, 1
0x1801f0656  jmp     loc_1801F0982
0x1801f065b  mov     rax, [r14]
0x1801f065e  mov     esi, 1
0x1801f0663  mov     edx, esi
0x1801f0665  mov     rcx, r14
0x1801f0668  mov     rax, [rax+48h]
0x1801f066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0671  lea     r8d, [rsi+2Bh]; unsigned int
0x1801f0675  mov     rdx, rbx; struct IMsiString *
0x1801f0678  mov     rcx, rax; struct IMsiString *
0x1801f067b  mov     rdi, rax
0x1801f067e  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x1801f0683  mov     rcx, [rdi]
0x1801f0686  mov     r12, rax
0x1801f0689  mov     rax, [rcx+10h]
0x1801f068d  mov     rcx, rdi
0x1801f0690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0695  test    r12, r12
0x1801f0698  jnz     short loc_1801F06C1
0x1801f069a  call    cs:__imp_GetLastError
0x1801f06a0  mov     rcx, [rbx]
0x1801f06a3  cmp     eax, 424h
0x1801f06a8  mov     rdx, [rcx+10h]
0x1801f06ac  mov     rcx, rbx
0x1801f06af  mov     rax, rdx
0x1801f06b2  jnz     short loc_1801F0640
0x1801f06b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f06b9  mov     al, sil
0x1801f06bc  jmp     loc_1801F0982
0x1801f06c1  xorps   xmm0, xmm0
0x1801f06c4  lea     r8, [rbp+4Fh+ServiceStatus]; lpServiceStatus
0x1801f06c8  movups  xmmword ptr [rbp+4Fh+ServiceStatus.dwServiceType], xmm0
0x1801f06cc  mov     edx, esi; dwControl
0x1801f06ce  mov     rcx, r12; hService
0x1801f06d1  movups  xmmword ptr [rbp+4Fh+ServiceStatus.dwWin32ExitCode], xmm0
0x1801f06d5  mov     r15b, sil
0x1801f06d8  call    cs:__imp_ControlService
0x1801f06de  test    eax, eax
0x1801f06e0  jz      short loc_1801F06F9
0x1801f06e2  mov     rcx, [rbp+4Fh+var_68]; this
0x1801f06e6  mov     r9d, esi; int
0x1801f06e9  mov     r8, r13; struct IMsiRecord *
0x1801f06ec  mov     rdx, r14; struct IMsiRecord *
0x1801f06ef  call    ?StartServiceW@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0H@Z; CMsiOpExecute::StartServiceW(IMsiRecord &,IMsiRecord &,int)
0x1801f06f4  jmp     loc_1801F0953
0x1801f06f9  call    cs:__imp_GetLastError
0x1801f06ff  lea     ecx, [rax-424h]
0x1801f0705  cmp     ecx, 11h
0x1801f0708  ja      short loc_1801F0729
0x1801f070a  mov     edx, 20005h
0x1801f070f  bt      edx, ecx
0x1801f0712  jnb     short loc_1801F0729
0x1801f0714  mov     rcx, r12; hSCObject
0x1801f0717  call    cs:__imp_CloseServiceHandle
0x1801f071d  mov     rax, [rbx]
0x1801f0720  mov     rcx, rbx
0x1801f0723  mov     rax, [rax+10h]
0x1801f0727  jmp     short loc_1801F06B4
0x1801f0729  cmp     eax, 41Bh
0x1801f072e  jnz     loc_1801F0953
0x1801f0734  lea     rax, [rbp+4Fh+ServicesReturned]
0x1801f0738  mov     [rbp+4Fh+cbBufSize], 0
0x1801f073f  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x1801f0744  xor     r9d, r9d; cbBufSize
0x1801f0747  lea     rax, [rbp+4Fh+cbBufSize]
0x1801f074b  mov     [rbp+4Fh+ServicesReturned], 0
0x1801f0752  xor     r8d, r8d; lpServices
0x1801f0755  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801f075a  mov     edx, esi; dwServiceState
0x1801f075c  mov     rcx, r12; hService
0x1801f075f  call    cs:__imp_EnumDependentServicesW
0x1801f0765  call    cs:__imp_GetLastError
0x1801f076b  cmp     eax, 0EAh
0x1801f0770  jnz     loc_1801F0923
0x1801f0776  mov     eax, [rbp+4Fh+cbBufSize]
0x1801f0779  test    eax, eax
0x1801f077b  jz      loc_1801F0923
0x1801f0781  mov     ecx, eax; unsigned __int64
0x1801f0783  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801f0788  mov     r8, [rbp+4Fh+var_80]
0x1801f078c  mov     r15, rax
0x1801f078f  mov     [rbp+4Fh+var_70], rax
0x1801f0793  mov     edx, esi
0x1801f0795  mov     rcx, [r8]
0x1801f0798  mov     rax, [rcx+48h]
0x1801f079c  mov     rcx, r8
0x1801f079f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f07a4  mov     r9d, [rbp+4Fh+cbBufSize]; cbBufSize
0x1801f07a8  mov     rdi, rax
0x1801f07ab  lea     rax, [rbp+4Fh+ServicesReturned]
0x1801f07af  mov     r8, r15; lpServices
0x1801f07b2  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x1801f07b7  mov     edx, esi; dwServiceState
0x1801f07b9  lea     rax, [rbp+4Fh+cbBufSize]
0x1801f07bd  mov     rcx, r12; hService
0x1801f07c0  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801f07c5  call    cs:__imp_EnumDependentServicesW
0x1801f07cb  test    eax, eax
0x1801f07cd  jz      loc_1801F09A9
0x1801f07d3  xor     r13d, r13d
0x1801f07d6  mov     r15b, sil
0x1801f07d9  cmp     [rbp+4Fh+ServicesReturned], r13d
0x1801f07dd  jbe     loc_1801F08A2
0x1801f07e3  mov     r8, [rbp+4Fh+var_70]
0x1801f07e7  mov     edx, 2
0x1801f07ec  movsxd  rax, r13d
0x1801f07ef  lea     rcx, [rax+rax*2]
0x1801f07f3  mov     rax, [r14]
0x1801f07f6  shl     rcx, 4
0x1801f07fa  mov     [rbp+4Fh+var_60], rcx
0x1801f07fe  mov     rax, [rax+80h]
0x1801f0805  mov     r8, [rcx+r8]
0x1801f0809  mov     rcx, r14
0x1801f080c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0811  cmp     [rbp+4Fh+var_88], 0
0x1801f0815  jnz     short loc_1801F082E
0x1801f0817  mov     rax, [r14]
0x1801f081a  mov     r8d, esi
0x1801f081d  mov     edx, 4
0x1801f0822  mov     rcx, r14
0x1801f0825  mov     rax, [rax+68h]
0x1801f0829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f082e  mov     r15, [rbp+4Fh+var_80]
0x1801f0832  mov     edx, esi
0x1801f0834  mov     rcx, [rbp+4Fh+var_70]
0x1801f0838  mov     r8, [rbp+4Fh+var_60]
0x1801f083c  mov     rax, [r15]
0x1801f083f  mov     r8, [r8+rcx+8]
0x1801f0844  mov     rcx, r15
0x1801f0847  mov     rax, [rax+80h]
0x1801f084e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0853  mov     rdx, [rbp+4Fh+var_70]
0x1801f0857  mov     rcx, [rbp+4Fh+var_60]
0x1801f085b  mov     rax, [r15]
0x1801f085e  mov     r8, [rcx+rdx]
0x1801f0862  mov     edx, 2
0x1801f0867  mov     rax, [rax+80h]
0x1801f086e  mov     rcx, r15
0x1801f0871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0876  mov     r8, [rbp+4Fh+var_78]; struct IMsiRecord *
0x1801f087a  xor     r9d, r9d; int
0x1801f087d  mov     rcx, [rbp+4Fh+var_68]; this
0x1801f0881  mov     rdx, r14; struct IMsiRecord *
0x1801f0884  mov     [rsp+0C0h+pcbBytesNeeded], r15; struct IMsiRecord *
0x1801f0889  call    ?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z; CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)
0x1801f088e  mov     r15b, al
0x1801f0891  test    al, al
0x1801f0893  jz      short loc_1801F08A2
0x1801f0895  add     r13d, esi
0x1801f0898  cmp     r13d, [rbp+4Fh+ServicesReturned]
0x1801f089c  jb      loc_1801F07E3
0x1801f08a2  mov     r13, [rbp+4Fh+var_78]
0x1801f08a6  mov     rcx, [rbp+4Fh+var_70]; void *
0x1801f08aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f08af  mov     rax, [r14]
0x1801f08b2  mov     r8, rbx
0x1801f08b5  mov     edx, 2
0x1801f08ba  mov     rcx, r14
0x1801f08bd  mov     rax, [rax+78h]
0x1801f08c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f08c6  cmp     [rbp+4Fh+var_88], 0
0x1801f08ca  jnz     short loc_1801F08E2
0x1801f08cc  mov     rax, [r14]
0x1801f08cf  xor     r8d, r8d
0x1801f08d2  mov     rcx, r14
0x1801f08d5  mov     rax, [rax+68h]
0x1801f08d9  lea     edx, [r8+4]
0x1801f08dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f08e2  mov     rcx, [rbp+4Fh+var_80]
0x1801f08e6  mov     r8, rdi
0x1801f08e9  mov     edx, esi
0x1801f08eb  mov     rax, [rcx]
0x1801f08ee  mov     rax, [rax+78h]
0x1801f08f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f08f7  mov     rcx, [rbp+4Fh+var_80]
0x1801f08fb  mov     r8, rbx
0x1801f08fe  mov     edx, 2
0x1801f0903  mov     rax, [rcx]
0x1801f0906  mov     rax, [rax+78h]
0x1801f090a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f090f  mov     rax, [rdi]
0x1801f0912  mov     rcx, rdi
0x1801f0915  mov     rax, [rax+10h]
0x1801f0919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f091e  test    r15b, r15b
0x1801f0921  jz      short loc_1801F0953
0x1801f0923  mov     r8, [rbp+4Fh+var_80]
0x1801f0927  xor     r9d, r9d; int
0x1801f092a  mov     rcx, [rbp+4Fh+var_68]; this
0x1801f092e  mov     rdx, r14; struct IMsiRecord *
0x1801f0931  mov     [rsp+0C0h+pcbBytesNeeded], r8; struct IMsiRecord *
0x1801f0936  mov     r8, r13; struct IMsiRecord *
0x1801f0939  call    ?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z; CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)
0x1801f093e  mov     r15b, al
0x1801f0941  test    al, al
0x1801f0943  jnz     short loc_1801F0953
0x1801f0945  call    cs:__imp_GetLastError
0x1801f094b  mov     ecx, eax; dwErrCode
0x1801f094d  call    cs:__imp_SetLastError
0x1801f0953  cmp     [rbp+4Fh+var_88], 0
0x1801f0957  jz      short loc_1801F0967
0x1801f0959  mov     r8d, esi; unsigned int
0x1801f095c  mov     rdx, r12; struct SC_HANDLE__ *
0x1801f095f  call    ?WaitForService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@K@Z; CMsiOpExecute::WaitForService(SC_HANDLE__ * const,ulong)
0x1801f0964  mov     r15b, al
0x1801f0967  mov     rcx, r12; hSCObject
0x1801f096a  call    cs:__imp_CloseServiceHandle
0x1801f0970  mov     rax, [rbx]
0x1801f0973  mov     rcx, rbx
0x1801f0976  mov     rax, [rax+10h]
0x1801f097a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f097f  mov     al, r15b
0x1801f0982  mov     rcx, [rbp+4Fh+var_38]
0x1801f0986  xor     rcx, rsp; StackCookie
0x1801f0989  call    __security_check_cookie
0x1801f098e  mov     rbx, [rsp+0C0h+arg_18]
0x1801f0996  add     rsp, 90h
0x1801f099d  pop     r15
0x1801f099f  pop     r14
0x1801f09a1  pop     r13
0x1801f09a3  pop     r12
0x1801f09a5  pop     rdi
0x1801f09a6  pop     rsi
0x1801f09a7  pop     rbp
0x1801f09a8  retn
0x1801f09a9  call    cs:__imp_GetLastError
0x1801f09af  mov     ecx, eax; dwErrCode
0x1801f09b1  xor     r15b, r15b
0x1801f09b4  call    cs:__imp_SetLastError
0x1801f09ba  jmp     loc_1801F08A6
```
