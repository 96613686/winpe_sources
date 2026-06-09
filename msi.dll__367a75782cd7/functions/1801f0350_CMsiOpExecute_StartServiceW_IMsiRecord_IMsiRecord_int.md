# CMsiOpExecute::StartServiceW(IMsiRecord &,IMsiRecord &,int)

- ea: `0x1801f0350`
- end: `0x1801f0572`
- name: `?StartServiceW@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0H@Z`
- size: `546`
- prototype: `bool __fastcall(CMsiOpExecute *__hidden this, struct IMsiRecord *, struct IMsiRecord *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1801f0578`
- `0x1801fe220`

## callees

- `0x1800620e4`
- `0x18008a388`
- `0x1801e113c`
- `0x1801e29b8`
- `0x1801f0350`
- `0x1801f0578`
- `0x1801f22ac`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!StartServiceW` at `0x1801f0483`
- `ADVAPI32!StartServiceW` at `0x1801f0483`
- `ADVAPI32!CloseServiceHandle` at `0x1801f04ea`
- `ADVAPI32!CloseServiceHandle` at `0x1801f0545`
- `ADVAPI32!CloseServiceHandle` at `0x1801f04ea`
- `ADVAPI32!CloseServiceHandle` at `0x1801f0545`
- `KERNEL32!GetLastError` at `0x1801f0526`
- `KERNEL32!GetLastError` at `0x1801f0526`
- `KERNEL32!SetLastError` at `0x1801f0558`
- `KERNEL32!SetLastError` at `0x1801f0558`
- `KERNEL32!SetErrorMode` at `0x1801f0461`
- `KERNEL32!SetErrorMode` at `0x1801f0470`
- `KERNEL32!SetErrorMode` at `0x1801f04b7`
- `KERNEL32!SetErrorMode` at `0x1801f054f`
- `KERNEL32!SetErrorMode` at `0x1801f0461`
- `KERNEL32!SetErrorMode` at `0x1801f0470`
- `KERNEL32!SetErrorMode` at `0x1801f04b7`
- `KERNEL32!SetErrorMode` at `0x1801f054f`

## pseudocode

```c
bool __fastcall CMsiOpExecute::StartServiceW(CMsiOpExecute *this, struct IMsiRecord *a2, struct IMsiRecord *a3, int a4)
{
  __int64 v8; // rax
  const struct IMsiString *v9; // rbx
  bool v10; // bp
  const struct IMsiString *v11; // rdi
  SC_HANDLE ServiceHandle; // r14
  __int64 v14; // rax
  const struct IMsiString *v15; // rdi
  CMsiOpExecute *v16; // rcx
  unsigned __int16 **v17; // r13
  CMsiOpExecute *v18; // rcx
  DWORD LastError; // r15d
  UINT uMode; // [rsp+78h] [rbp+10h]
  DWORD dwNumServiceArgs; // [rsp+88h] [rbp+20h] BYREF

  v8 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 2);
  v9 = (const struct IMsiString *)v8;
  if ( !a4 )
  {
    v10 = 1;
    v11 = (const struct IMsiString *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a2 + 72LL))(
                                       a2,
                                       1);
    ServiceHandle = GetServiceHandle(v11, v9, 0x14u);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( !ServiceHandle )
    {
LABEL_4:
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v9 + 16LL))(v9);
      return 0;
    }
    v14 = *(_QWORD *)a2;
    dwNumServiceArgs = 0;
    v15 = (const struct IMsiString *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(v14 + 72))(a2, 5);
    v17 = CMsiOpExecute::NewArgumentArray(v16, v15, (int *)&dwNumServiceArgs);
    uMode = SetErrorMode(0);
    SetErrorMode(uMode & 0xFFFFFFFE);
    if ( StartServiceW(ServiceHandle, dwNumServiceArgs, (LPCWSTR *)v17) )
    {
      CMsiOpExecute::StopService(this, a2, a3, 1, 0);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 1056 )
      {
        operator delete(v17);
        CloseServiceHandle(ServiceHandle);
        SetErrorMode(uMode);
        SetLastError(LastError);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v15 + 16LL))(v15);
        goto LABEL_4;
      }
    }
    operator delete(v17);
    SetErrorMode(uMode);
    if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a2 + 56LL))(a2, 4) )
      v10 = CMsiOpExecute::WaitForService(v18, ServiceHandle, 4u);
    CloseServiceHandle(ServiceHandle);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v15 + 16LL))(v15);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v9 + 16LL))(v9);
    return v10;
  }
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)a3 + 120LL))(a3, 2, v8);
  v10 = 1;
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)a3 + 104LL))(a3, 3, 1);
  CMsiOpExecute::RollbackRecord(this, 77, a3);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v9 + 16LL))(v9);
  return v10;
}

```

## disassembly

```asm
0x1801f0350  mov     [rsp+arg_0], rbx
0x1801f0355  push    rbp
0x1801f0356  push    rsi
0x1801f0357  push    rdi
0x1801f0358  push    r12
0x1801f035a  push    r13
0x1801f035c  push    r14
0x1801f035e  push    r15
0x1801f0360  sub     rsp, 30h
0x1801f0364  mov     rax, [rdx]
0x1801f0367  mov     rsi, rdx
0x1801f036a  mov     r12, rcx
0x1801f036d  mov     ebp, 2
0x1801f0372  mov     edx, ebp
0x1801f0374  mov     rcx, rsi
0x1801f0377  mov     edi, r9d
0x1801f037a  mov     r15, r8
0x1801f037d  mov     rax, [rax+48h]
0x1801f0381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0386  mov     rbx, rax
0x1801f0389  test    edi, edi
0x1801f038b  jz      short loc_1801F03D5
0x1801f038d  mov     rax, [r15]
0x1801f0390  mov     r8, rbx
0x1801f0393  mov     edx, ebp
0x1801f0395  mov     rcx, r15
0x1801f0398  mov     rax, [rax+78h]
0x1801f039c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f03a1  mov     rax, [r15]
0x1801f03a4  mov     ebp, 1
0x1801f03a9  mov     r8d, ebp
0x1801f03ac  mov     rcx, r15
0x1801f03af  mov     rax, [rax+68h]
0x1801f03b3  lea     edx, [rbp+2]
0x1801f03b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f03bb  mov     r8, r15
0x1801f03be  lea     edx, [rbp+4Ch]
0x1801f03c1  mov     rcx, r12
0x1801f03c4  call    ?RollbackRecord@CMsiOpExecute@@QEAA_NW4ixoEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::RollbackRecord(ixoEnum,IMsiRecord &)
0x1801f03c9  mov     rcx, [rbx]
0x1801f03cc  mov     rax, [rcx+10h]
0x1801f03d0  jmp     loc_1801F0506
0x1801f03d5  mov     rax, [rsi]
0x1801f03d8  mov     ebp, 1
0x1801f03dd  mov     edx, ebp
0x1801f03df  mov     rcx, rsi
0x1801f03e2  mov     rax, [rax+48h]
0x1801f03e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f03eb  lea     r8d, [rbp+13h]; unsigned int
0x1801f03ef  mov     rdx, rbx; struct IMsiString *
0x1801f03f2  mov     rcx, rax; struct IMsiString *
0x1801f03f5  mov     rdi, rax
0x1801f03f8  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x1801f03fd  mov     rcx, [rdi]
0x1801f0400  mov     r14, rax
0x1801f0403  mov     rax, [rcx+10h]
0x1801f0407  mov     rcx, rdi
0x1801f040a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f040f  test    r14, r14
0x1801f0412  jnz     short loc_1801F042A
0x1801f0414  mov     rax, [rbx]
0x1801f0417  mov     rcx, rbx
0x1801f041a  mov     rax, [rax+10h]
0x1801f041e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0423  xor     al, al
0x1801f0425  jmp     loc_1801F0511
0x1801f042a  mov     rax, [rsi]
0x1801f042d  mov     edx, 5
0x1801f0432  mov     rcx, rsi
0x1801f0435  mov     [rsp+68h+dwNumServiceArgs], 0
0x1801f0440  mov     rax, [rax+48h]
0x1801f0444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0449  lea     r8, [rsp+68h+dwNumServiceArgs]; int *
0x1801f0451  mov     rdx, rax; struct IMsiString *
0x1801f0454  mov     rdi, rax
0x1801f0457  call    ?NewArgumentArray@CMsiOpExecute@@IEAAPEAPEAGAEBVIMsiString@@AEAH@Z; CMsiOpExecute::NewArgumentArray(IMsiString const &,int &)
0x1801f045c  xor     ecx, ecx; uMode
0x1801f045e  mov     r13, rax
0x1801f0461  call    cs:__imp_SetErrorMode
0x1801f0467  mov     ecx, eax
0x1801f0469  mov     [rsp+68h+uMode], eax
0x1801f046d  and     ecx, 0FFFFFFFEh; uMode
0x1801f0470  call    cs:__imp_SetErrorMode
0x1801f0476  mov     edx, [rsp+68h+dwNumServiceArgs]; dwNumServiceArgs
0x1801f047d  mov     r8, r13; lpServiceArgVectors
0x1801f0480  mov     rcx, r14; hService
0x1801f0483  call    cs:__imp_StartServiceW
0x1801f0489  test    eax, eax
0x1801f048b  jz      loc_1801F0526
0x1801f0491  mov     r9d, ebp; int
0x1801f0494  mov     [rsp+68h+var_48], 0; struct IMsiRecord *
0x1801f049d  mov     r8, r15; struct IMsiRecord *
0x1801f04a0  mov     rdx, rsi; struct IMsiRecord *
0x1801f04a3  mov     rcx, r12; this
0x1801f04a6  call    ?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z; CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)
0x1801f04ab  mov     rcx, r13; void *
0x1801f04ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f04b3  mov     ecx, [rsp+68h+uMode]; uMode
0x1801f04b7  call    cs:__imp_SetErrorMode
0x1801f04bd  mov     rax, [rsi]
0x1801f04c0  mov     r15d, 4
0x1801f04c6  mov     edx, r15d
0x1801f04c9  mov     rcx, rsi
0x1801f04cc  mov     rax, [rax+38h]
0x1801f04d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f04d5  test    eax, eax
0x1801f04d7  jz      short loc_1801F04E7
0x1801f04d9  mov     r8d, r15d; unsigned int
0x1801f04dc  mov     rdx, r14; struct SC_HANDLE__ *
0x1801f04df  call    ?WaitForService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@K@Z; CMsiOpExecute::WaitForService(SC_HANDLE__ * const,ulong)
0x1801f04e4  mov     bpl, al
0x1801f04e7  mov     rcx, r14; hSCObject
0x1801f04ea  call    cs:__imp_CloseServiceHandle
0x1801f04f0  mov     rax, [rdi]
0x1801f04f3  mov     rcx, rdi
0x1801f04f6  mov     rax, [rax+10h]
0x1801f04fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f04ff  mov     rax, [rbx]
0x1801f0502  mov     rax, [rax+10h]
0x1801f0506  mov     rcx, rbx
0x1801f0509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f050e  mov     al, bpl
0x1801f0511  mov     rbx, [rsp+68h+arg_0]
0x1801f0516  add     rsp, 30h
0x1801f051a  pop     r15
0x1801f051c  pop     r14
0x1801f051e  pop     r13
0x1801f0520  pop     r12
0x1801f0522  pop     rdi
0x1801f0523  pop     rsi
0x1801f0524  pop     rbp
0x1801f0525  retn
0x1801f0526  call    cs:__imp_GetLastError
0x1801f052c  mov     r15d, eax
0x1801f052f  cmp     eax, 420h
0x1801f0534  jz      loc_1801F04AB
0x1801f053a  mov     rcx, r13; void *
0x1801f053d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f0542  mov     rcx, r14; hSCObject
0x1801f0545  call    cs:__imp_CloseServiceHandle
0x1801f054b  mov     ecx, [rsp+68h+uMode]; uMode
0x1801f054f  call    cs:__imp_SetErrorMode
0x1801f0555  mov     ecx, r15d; dwErrCode
0x1801f0558  call    cs:__imp_SetLastError
0x1801f055e  mov     rax, [rdi]
0x1801f0561  mov     rcx, rdi
0x1801f0564  mov     rax, [rax+10h]
0x1801f0568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f056d  jmp     loc_1801F0414
```
