# CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)

- ea: `0x1801f9610`
- end: `0x1801f9aa3`
- name: `?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z`
- size: `1171`
- prototype: `bool __fastcall(CMsiOpExecute *__hidden this, struct IMsiRecord *, struct IMsiRecord *, int, struct IMsiRecord *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1801e6fa8`
- `0x1801f93b0`
- `0x1801f9610`
- `0x180207400`

## callees

- `0x180018ee0`
- `0x180019cc0`
- `0x180064084`
- `0x1801ea0fc`
- `0x1801f93b0`
- `0x1801f9610`
- `0x1801fb3b8`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!EnumDependentServicesW` at `0x1801f9812`
- `ADVAPI32!EnumDependentServicesW` at `0x1801f9884`
- `ADVAPI32!EnumDependentServicesW` at `0x1801f9812`
- `ADVAPI32!EnumDependentServicesW` at `0x1801f9884`
- `ADVAPI32!ControlService` at `0x1801f9776`
- `ADVAPI32!ControlService` at `0x1801f9776`
- `ADVAPI32!CloseServiceHandle` at `0x1801f97c1`
- `ADVAPI32!CloseServiceHandle` at `0x1801f9a3b`
- `ADVAPI32!CloseServiceHandle` at `0x1801f97c1`
- `ADVAPI32!CloseServiceHandle` at `0x1801f9a3b`
- `KERNEL32!GetLastError` at `0x1801f9732`
- `KERNEL32!GetLastError` at `0x1801f979d`
- `KERNEL32!GetLastError` at `0x1801f981e`
- `KERNEL32!GetLastError` at `0x1801f9a0a`
- `KERNEL32!GetLastError` at `0x1801f9a81`
- `KERNEL32!GetLastError` at `0x1801f9732`
- `KERNEL32!GetLastError` at `0x1801f979d`
- `KERNEL32!GetLastError` at `0x1801f981e`
- `KERNEL32!GetLastError` at `0x1801f9a0a`
- `KERNEL32!GetLastError` at `0x1801f9a81`
- `KERNEL32!SetLastError` at `0x1801f9a18`
- `KERNEL32!SetLastError` at `0x1801f9a92`
- `KERNEL32!SetLastError` at `0x1801f9a18`
- `KERNEL32!SetLastError` at `0x1801f9a92`

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
0x1801f9610  mov     [rsp-8+arg_18], rbx
0x1801f9615  push    rbp
0x1801f9616  push    rsi
0x1801f9617  push    rdi
0x1801f9618  push    r12
0x1801f961a  push    r13
0x1801f961c  push    r14
0x1801f961e  push    r15
0x1801f9620  lea     rbp, [rsp-1Fh]
0x1801f9625  sub     rsp, 90h
0x1801f962c  mov     rax, cs:__security_cookie
0x1801f9633  xor     rax, rsp
0x1801f9636  mov     [rbp+4Fh+var_38], rax
0x1801f963a  mov     rax, [rbp+4Fh+arg_20]
0x1801f963e  mov     r14, rdx
0x1801f9641  mov     [rbp+4Fh+var_80], rax
0x1801f9645  mov     rsi, rcx
0x1801f9648  mov     rax, [rdx]
0x1801f964b  mov     r15d, 2
0x1801f9651  mov     [rbp+4Fh+var_68], rcx
0x1801f9655  mov     edx, r15d
0x1801f9658  mov     rcx, r14
0x1801f965b  mov     [rbp+4Fh+var_78], r8
0x1801f965f  mov     edi, r9d
0x1801f9662  mov     r13, r8
0x1801f9665  mov     rax, [rax+48h]
0x1801f9669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f966e  mov     rbx, rax
0x1801f9671  lea     edx, [r15+2]
0x1801f9675  mov     rax, [r14]
0x1801f9678  mov     rcx, r14
0x1801f967b  mov     rax, [rax+38h]
0x1801f967f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9684  mov     [rbp+4Fh+var_88], eax
0x1801f9687  test    edi, edi
0x1801f9689  jz      short loc_1801F96F3
0x1801f968b  mov     rax, [r13+0]
0x1801f968f  mov     r8, rbx
0x1801f9692  mov     edx, r15d
0x1801f9695  mov     rcx, r13
0x1801f9698  mov     rax, [rax+78h]
0x1801f969c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f96a1  mov     rax, [r13+0]
0x1801f96a5  lea     edx, [r15+1]
0x1801f96a9  mov     r8d, r15d
0x1801f96ac  mov     rcx, r13
0x1801f96af  mov     rax, [rax+68h]
0x1801f96b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f96b8  mov     r8, r13
0x1801f96bb  lea     edx, [r15+4Bh]
0x1801f96bf  mov     rcx, rsi
0x1801f96c2  call    ?RollbackRecord@CMsiOpExecute@@QEAA_NW4ixoEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::RollbackRecord(ixoEnum,IMsiRecord &)
0x1801f96c7  mov     rcx, [rbx]
0x1801f96ca  test    al, al
0x1801f96cc  mov     rdx, [rcx+10h]
0x1801f96d0  mov     rcx, rbx
0x1801f96d3  mov     rax, rdx
0x1801f96d6  jnz     short loc_1801F96E4
0x1801f96d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f96dd  xor     al, al
0x1801f96df  jmp     loc_1801F9A59
0x1801f96e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f96e9  mov     eax, 1
0x1801f96ee  jmp     loc_1801F9A59
0x1801f96f3  mov     rax, [r14]
0x1801f96f6  mov     esi, 1
0x1801f96fb  mov     edx, esi
0x1801f96fd  mov     rcx, r14
0x1801f9700  mov     rax, [rax+48h]
0x1801f9704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9709  lea     r8d, [rsi+2Bh]; unsigned int
0x1801f970d  mov     rdx, rbx; struct IMsiString *
0x1801f9710  mov     rcx, rax; struct IMsiString *
0x1801f9713  mov     rdi, rax
0x1801f9716  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x1801f971b  mov     rcx, [rdi]
0x1801f971e  mov     r12, rax
0x1801f9721  mov     rax, [rcx+10h]
0x1801f9725  mov     rcx, rdi
0x1801f9728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f972d  test    r12, r12
0x1801f9730  jnz     short loc_1801F975F
0x1801f9732  call    cs:__imp_GetLastError
0x1801f9739  nop     dword ptr [rax+rax+00h]
0x1801f973e  mov     rcx, [rbx]
0x1801f9741  cmp     eax, 424h
0x1801f9746  mov     rdx, [rcx+10h]
0x1801f974a  mov     rcx, rbx
0x1801f974d  mov     rax, rdx
0x1801f9750  jnz     short loc_1801F96D8
0x1801f9752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9757  mov     al, sil
0x1801f975a  jmp     loc_1801F9A59
0x1801f975f  xorps   xmm0, xmm0
0x1801f9762  lea     r8, [rbp+4Fh+ServiceStatus]; lpServiceStatus
0x1801f9766  movups  xmmword ptr [rbp+4Fh+ServiceStatus.dwServiceType], xmm0
0x1801f976a  mov     edx, esi; dwControl
0x1801f976c  mov     rcx, r12; hService
0x1801f976f  movups  xmmword ptr [rbp+4Fh+ServiceStatus.dwWin32ExitCode], xmm0
0x1801f9773  mov     r15b, sil
0x1801f9776  call    cs:__imp_ControlService
0x1801f977d  nop     dword ptr [rax+rax+00h]
0x1801f9782  test    eax, eax
0x1801f9784  jz      short loc_1801F979D
0x1801f9786  mov     rcx, [rbp+4Fh+var_68]; this
0x1801f978a  mov     r9d, esi; int
0x1801f978d  mov     r8, r13; struct IMsiRecord *
0x1801f9790  mov     rdx, r14; struct IMsiRecord *
0x1801f9793  call    ?StartServiceW@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0H@Z; CMsiOpExecute::StartServiceW(IMsiRecord &,IMsiRecord &,int)
0x1801f9798  jmp     loc_1801F9A24
0x1801f979d  call    cs:__imp_GetLastError
0x1801f97a4  nop     dword ptr [rax+rax+00h]
0x1801f97a9  lea     ecx, [rax-424h]
0x1801f97af  cmp     ecx, 11h
0x1801f97b2  ja      short loc_1801F97DC
0x1801f97b4  mov     edx, 20005h
0x1801f97b9  bt      edx, ecx
0x1801f97bc  jnb     short loc_1801F97DC
0x1801f97be  mov     rcx, r12; hSCObject
0x1801f97c1  call    cs:__imp_CloseServiceHandle
0x1801f97c8  nop     dword ptr [rax+rax+00h]
0x1801f97cd  mov     rax, [rbx]
0x1801f97d0  mov     rcx, rbx
0x1801f97d3  mov     rax, [rax+10h]
0x1801f97d7  jmp     loc_1801F9752
0x1801f97dc  cmp     eax, 41Bh
0x1801f97e1  jnz     loc_1801F9A24
0x1801f97e7  lea     rax, [rbp+4Fh+ServicesReturned]
0x1801f97eb  mov     [rbp+4Fh+cbBufSize], 0
0x1801f97f2  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x1801f97f7  xor     r9d, r9d; cbBufSize
0x1801f97fa  lea     rax, [rbp+4Fh+cbBufSize]
0x1801f97fe  mov     [rbp+4Fh+ServicesReturned], 0
0x1801f9805  xor     r8d, r8d; lpServices
0x1801f9808  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801f980d  mov     edx, esi; dwServiceState
0x1801f980f  mov     rcx, r12; hService
0x1801f9812  call    cs:__imp_EnumDependentServicesW
0x1801f9819  nop     dword ptr [rax+rax+00h]
0x1801f981e  call    cs:__imp_GetLastError
0x1801f9825  nop     dword ptr [rax+rax+00h]
0x1801f982a  cmp     eax, 0EAh
0x1801f982f  jnz     loc_1801F99E8
0x1801f9835  mov     eax, [rbp+4Fh+cbBufSize]
0x1801f9838  test    eax, eax
0x1801f983a  jz      loc_1801F99E8
0x1801f9840  mov     ecx, eax; unsigned __int64
0x1801f9842  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801f9847  mov     r8, [rbp+4Fh+var_80]
0x1801f984b  mov     r15, rax
0x1801f984e  mov     [rbp+4Fh+var_70], rax
0x1801f9852  mov     edx, esi
0x1801f9854  mov     rcx, [r8]
0x1801f9857  mov     rax, [rcx+48h]
0x1801f985b  mov     rcx, r8
0x1801f985e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9863  mov     r9d, [rbp+4Fh+cbBufSize]; cbBufSize
0x1801f9867  mov     rdi, rax
0x1801f986a  lea     rax, [rbp+4Fh+ServicesReturned]
0x1801f986e  mov     r8, r15; lpServices
0x1801f9871  mov     [rsp+0C0h+lpServicesReturned], rax; lpServicesReturned
0x1801f9876  mov     edx, esi; dwServiceState
0x1801f9878  lea     rax, [rbp+4Fh+cbBufSize]
0x1801f987c  mov     rcx, r12; hService
0x1801f987f  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801f9884  call    cs:__imp_EnumDependentServicesW
0x1801f988b  nop     dword ptr [rax+rax+00h]
0x1801f9890  test    eax, eax
0x1801f9892  jz      loc_1801F9A81
0x1801f9898  xor     r13d, r13d
0x1801f989b  mov     r15b, sil
0x1801f989e  cmp     [rbp+4Fh+ServicesReturned], r13d
0x1801f98a2  jbe     loc_1801F9967
0x1801f98a8  mov     r8, [rbp+4Fh+var_70]
0x1801f98ac  mov     edx, 2
0x1801f98b1  movsxd  rax, r13d
0x1801f98b4  lea     rcx, [rax+rax*2]
0x1801f98b8  mov     rax, [r14]
0x1801f98bb  shl     rcx, 4
0x1801f98bf  mov     [rbp+4Fh+var_60], rcx
0x1801f98c3  mov     rax, [rax+80h]
0x1801f98ca  mov     r8, [rcx+r8]
0x1801f98ce  mov     rcx, r14
0x1801f98d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f98d6  cmp     [rbp+4Fh+var_88], 0
0x1801f98da  jnz     short loc_1801F98F3
0x1801f98dc  mov     rax, [r14]
0x1801f98df  mov     r8d, esi
0x1801f98e2  mov     edx, 4
0x1801f98e7  mov     rcx, r14
0x1801f98ea  mov     rax, [rax+68h]
0x1801f98ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f98f3  mov     r15, [rbp+4Fh+var_80]
0x1801f98f7  mov     edx, esi
0x1801f98f9  mov     rcx, [rbp+4Fh+var_70]
0x1801f98fd  mov     r8, [rbp+4Fh+var_60]
0x1801f9901  mov     rax, [r15]
0x1801f9904  mov     r8, [r8+rcx+8]
0x1801f9909  mov     rcx, r15
0x1801f990c  mov     rax, [rax+80h]
0x1801f9913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9918  mov     rdx, [rbp+4Fh+var_70]
0x1801f991c  mov     rcx, [rbp+4Fh+var_60]
0x1801f9920  mov     rax, [r15]
0x1801f9923  mov     r8, [rcx+rdx]
0x1801f9927  mov     edx, 2
0x1801f992c  mov     rax, [rax+80h]
0x1801f9933  mov     rcx, r15
0x1801f9936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f993b  mov     r8, [rbp+4Fh+var_78]; struct IMsiRecord *
0x1801f993f  xor     r9d, r9d; int
0x1801f9942  mov     rcx, [rbp+4Fh+var_68]; this
0x1801f9946  mov     rdx, r14; struct IMsiRecord *
0x1801f9949  mov     [rsp+0C0h+pcbBytesNeeded], r15; struct IMsiRecord *
0x1801f994e  call    ?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z; CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)
0x1801f9953  mov     r15b, al
0x1801f9956  test    al, al
0x1801f9958  jz      short loc_1801F9967
0x1801f995a  add     r13d, esi
0x1801f995d  cmp     r13d, [rbp+4Fh+ServicesReturned]
0x1801f9961  jb      loc_1801F98A8
0x1801f9967  mov     r13, [rbp+4Fh+var_78]
0x1801f996b  mov     rcx, [rbp+4Fh+var_70]; void *
0x1801f996f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f9974  mov     rax, [r14]
0x1801f9977  mov     r8, rbx
0x1801f997a  mov     edx, 2
0x1801f997f  mov     rcx, r14
0x1801f9982  mov     rax, [rax+78h]
0x1801f9986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f998b  cmp     [rbp+4Fh+var_88], 0
0x1801f998f  jnz     short loc_1801F99A7
0x1801f9991  mov     rax, [r14]
0x1801f9994  xor     r8d, r8d
0x1801f9997  mov     rcx, r14
0x1801f999a  mov     rax, [rax+68h]
0x1801f999e  lea     edx, [r8+4]
0x1801f99a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f99a7  mov     rcx, [rbp+4Fh+var_80]
0x1801f99ab  mov     r8, rdi
0x1801f99ae  mov     edx, esi
0x1801f99b0  mov     rax, [rcx]
0x1801f99b3  mov     rax, [rax+78h]
0x1801f99b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f99bc  mov     rcx, [rbp+4Fh+var_80]
0x1801f99c0  mov     r8, rbx
0x1801f99c3  mov     edx, 2
0x1801f99c8  mov     rax, [rcx]
0x1801f99cb  mov     rax, [rax+78h]
0x1801f99cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f99d4  mov     rax, [rdi]
0x1801f99d7  mov     rcx, rdi
0x1801f99da  mov     rax, [rax+10h]
0x1801f99de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f99e3  test    r15b, r15b
0x1801f99e6  jz      short loc_1801F9A24
0x1801f99e8  mov     r8, [rbp+4Fh+var_80]
0x1801f99ec  xor     r9d, r9d; int
0x1801f99ef  mov     rcx, [rbp+4Fh+var_68]; this
0x1801f99f3  mov     rdx, r14; struct IMsiRecord *
0x1801f99f6  mov     [rsp+0C0h+pcbBytesNeeded], r8; struct IMsiRecord *
0x1801f99fb  mov     r8, r13; struct IMsiRecord *
0x1801f99fe  call    ?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z; CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)
0x1801f9a03  mov     r15b, al
0x1801f9a06  test    al, al
0x1801f9a08  jnz     short loc_1801F9A24
0x1801f9a0a  call    cs:__imp_GetLastError
0x1801f9a11  nop     dword ptr [rax+rax+00h]
0x1801f9a16  mov     ecx, eax; dwErrCode
0x1801f9a18  call    cs:__imp_SetLastError
0x1801f9a1f  nop     dword ptr [rax+rax+00h]
0x1801f9a24  cmp     [rbp+4Fh+var_88], 0
0x1801f9a28  jz      short loc_1801F9A38
0x1801f9a2a  mov     r8d, esi; unsigned int
0x1801f9a2d  mov     rdx, r12; struct SC_HANDLE__ *
0x1801f9a30  call    ?WaitForService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@K@Z; CMsiOpExecute::WaitForService(SC_HANDLE__ * const,ulong)
0x1801f9a35  mov     r15b, al
0x1801f9a38  mov     rcx, r12; hSCObject
0x1801f9a3b  call    cs:__imp_CloseServiceHandle
0x1801f9a42  nop     dword ptr [rax+rax+00h]
0x1801f9a47  mov     rax, [rbx]
0x1801f9a4a  mov     rcx, rbx
0x1801f9a4d  mov     rax, [rax+10h]
0x1801f9a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9a56  mov     al, r15b
0x1801f9a59  mov     rcx, [rbp+4Fh+var_38]
0x1801f9a5d  xor     rcx, rsp; StackCookie
0x1801f9a60  call    __security_check_cookie
0x1801f9a65  mov     rbx, [rsp+0C0h+arg_18]
0x1801f9a6d  add     rsp, 90h
0x1801f9a74  pop     r15
0x1801f9a76  pop     r14
0x1801f9a78  pop     r13
0x1801f9a7a  pop     r12
0x1801f9a7c  pop     rdi
0x1801f9a7d  pop     rsi
0x1801f9a7e  pop     rbp
0x1801f9a7f  retn
0x1801f9a81  call    cs:__imp_GetLastError
0x1801f9a88  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
