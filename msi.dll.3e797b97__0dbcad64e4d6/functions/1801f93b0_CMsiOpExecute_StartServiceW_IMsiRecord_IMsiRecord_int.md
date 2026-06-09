# CMsiOpExecute::StartServiceW(IMsiRecord &,IMsiRecord &,int)

- ea: `0x1801f93b0`
- end: `0x1801f9609`
- name: `?StartServiceW@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0H@Z`
- size: `601`
- prototype: `bool __fastcall(CMsiOpExecute *__hidden this, struct IMsiRecord *, struct IMsiRecord *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1801f9610`
- `0x180207400`

## callees

- `0x180019cc0`
- `0x180064084`
- `0x1801ea0fc`
- `0x1801eb9bc`
- `0x1801f93b0`
- `0x1801f9610`
- `0x1801fb3b8`
- `0x180266010`

## import_xrefs

- `ADVAPI32!StartServiceW` at `0x1801f94ef`
- `ADVAPI32!StartServiceW` at `0x1801f94ef`
- `ADVAPI32!CloseServiceHandle` at `0x1801f9562`
- `ADVAPI32!CloseServiceHandle` at `0x1801f95ca`
- `ADVAPI32!CloseServiceHandle` at `0x1801f9562`
- `ADVAPI32!CloseServiceHandle` at `0x1801f95ca`
- `KERNEL32!GetLastError` at `0x1801f95a5`
- `KERNEL32!GetLastError` at `0x1801f95a5`
- `KERNEL32!SetLastError` at `0x1801f95e9`
- `KERNEL32!SetLastError` at `0x1801f95e9`
- `KERNEL32!SetErrorMode` at `0x1801f94c1`
- `KERNEL32!SetErrorMode` at `0x1801f94d6`
- `KERNEL32!SetErrorMode` at `0x1801f9529`
- `KERNEL32!SetErrorMode` at `0x1801f95da`
- `KERNEL32!SetErrorMode` at `0x1801f94c1`
- `KERNEL32!SetErrorMode` at `0x1801f94d6`
- `KERNEL32!SetErrorMode` at `0x1801f9529`
- `KERNEL32!SetErrorMode` at `0x1801f95da`

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
0x1801f93b0  mov     [rsp+arg_0], rbx
0x1801f93b5  push    rbp
0x1801f93b6  push    rsi
0x1801f93b7  push    rdi
0x1801f93b8  push    r12
0x1801f93ba  push    r13
0x1801f93bc  push    r14
0x1801f93be  push    r15
0x1801f93c0  sub     rsp, 30h
0x1801f93c4  mov     rax, [rdx]
0x1801f93c7  mov     rsi, rdx
0x1801f93ca  mov     r12, rcx
0x1801f93cd  mov     ebp, 2
0x1801f93d2  mov     edx, ebp
0x1801f93d4  mov     rcx, rsi
0x1801f93d7  mov     edi, r9d
0x1801f93da  mov     r15, r8
0x1801f93dd  mov     rax, [rax+48h]
0x1801f93e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f93e6  mov     rbx, rax
0x1801f93e9  test    edi, edi
0x1801f93eb  jz      short loc_1801F9435
0x1801f93ed  mov     rax, [r15]
0x1801f93f0  mov     r8, rbx
0x1801f93f3  mov     edx, ebp
0x1801f93f5  mov     rcx, r15
0x1801f93f8  mov     rax, [rax+78h]
0x1801f93fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9401  mov     rax, [r15]
0x1801f9404  mov     ebp, 1
0x1801f9409  mov     r8d, ebp
0x1801f940c  mov     rcx, r15
0x1801f940f  mov     rax, [rax+68h]
0x1801f9413  lea     edx, [rbp+2]
0x1801f9416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f941b  mov     r8, r15
0x1801f941e  lea     edx, [rbp+4Ch]
0x1801f9421  mov     rcx, r12
0x1801f9424  call    ?RollbackRecord@CMsiOpExecute@@QEAA_NW4ixoEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::RollbackRecord(ixoEnum,IMsiRecord &)
0x1801f9429  mov     rcx, [rbx]
0x1801f942c  mov     rax, [rcx+10h]
0x1801f9430  jmp     loc_1801F9584
0x1801f9435  mov     rax, [rsi]
0x1801f9438  mov     ebp, 1
0x1801f943d  mov     edx, ebp
0x1801f943f  mov     rcx, rsi
0x1801f9442  mov     rax, [rax+48h]
0x1801f9446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f944b  lea     r8d, [rbp+13h]; unsigned int
0x1801f944f  mov     rdx, rbx; struct IMsiString *
0x1801f9452  mov     rcx, rax; struct IMsiString *
0x1801f9455  mov     rdi, rax
0x1801f9458  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x1801f945d  mov     rcx, [rdi]
0x1801f9460  mov     r14, rax
0x1801f9463  mov     rax, [rcx+10h]
0x1801f9467  mov     rcx, rdi
0x1801f946a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f946f  test    r14, r14
0x1801f9472  jnz     short loc_1801F948A
0x1801f9474  mov     rax, [rbx]
0x1801f9477  mov     rcx, rbx
0x1801f947a  mov     rax, [rax+10h]
0x1801f947e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9483  xor     al, al
0x1801f9485  jmp     loc_1801F958F
0x1801f948a  mov     rax, [rsi]
0x1801f948d  mov     edx, 5
0x1801f9492  mov     rcx, rsi
0x1801f9495  mov     [rsp+68h+dwNumServiceArgs], 0
0x1801f94a0  mov     rax, [rax+48h]
0x1801f94a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f94a9  lea     r8, [rsp+68h+dwNumServiceArgs]; int *
0x1801f94b1  mov     rdx, rax; struct IMsiString *
0x1801f94b4  mov     rdi, rax
0x1801f94b7  call    ?NewArgumentArray@CMsiOpExecute@@IEAAPEAPEAGAEBVIMsiString@@AEAH@Z; CMsiOpExecute::NewArgumentArray(IMsiString const &,int &)
0x1801f94bc  xor     ecx, ecx; uMode
0x1801f94be  mov     r13, rax
0x1801f94c1  call    cs:__imp_SetErrorMode
0x1801f94c8  nop     dword ptr [rax+rax+00h]
0x1801f94cd  mov     ecx, eax
0x1801f94cf  mov     [rsp+68h+uMode], eax
0x1801f94d3  and     ecx, 0FFFFFFFEh; uMode
0x1801f94d6  call    cs:__imp_SetErrorMode
0x1801f94dd  nop     dword ptr [rax+rax+00h]
0x1801f94e2  mov     edx, [rsp+68h+dwNumServiceArgs]; dwNumServiceArgs
0x1801f94e9  mov     r8, r13; lpServiceArgVectors
0x1801f94ec  mov     rcx, r14; hService
0x1801f94ef  call    cs:__imp_StartServiceW
0x1801f94f6  nop     dword ptr [rax+rax+00h]
0x1801f94fb  test    eax, eax
0x1801f94fd  jz      loc_1801F95A5
0x1801f9503  mov     r9d, ebp; int
0x1801f9506  mov     [rsp+68h+var_48], 0; struct IMsiRecord *
0x1801f950f  mov     r8, r15; struct IMsiRecord *
0x1801f9512  mov     rdx, rsi; struct IMsiRecord *
0x1801f9515  mov     rcx, r12; this
0x1801f9518  call    ?StopService@CMsiOpExecute@@IEAA_NAEAVIMsiRecord@@0HPEAV2@@Z; CMsiOpExecute::StopService(IMsiRecord &,IMsiRecord &,int,IMsiRecord *)
0x1801f951d  mov     rcx, r13; void *
0x1801f9520  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f9525  mov     ecx, [rsp+68h+uMode]; uMode
0x1801f9529  call    cs:__imp_SetErrorMode
0x1801f9530  nop     dword ptr [rax+rax+00h]
0x1801f9535  mov     rax, [rsi]
0x1801f9538  mov     r15d, 4
0x1801f953e  mov     edx, r15d
0x1801f9541  mov     rcx, rsi
0x1801f9544  mov     rax, [rax+38h]
0x1801f9548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f954d  test    eax, eax
0x1801f954f  jz      short loc_1801F955F
0x1801f9551  mov     r8d, r15d; unsigned int
0x1801f9554  mov     rdx, r14; struct SC_HANDLE__ *
0x1801f9557  call    ?WaitForService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@K@Z; CMsiOpExecute::WaitForService(SC_HANDLE__ * const,ulong)
0x1801f955c  mov     bpl, al
0x1801f955f  mov     rcx, r14; hSCObject
0x1801f9562  call    cs:__imp_CloseServiceHandle
0x1801f9569  nop     dword ptr [rax+rax+00h]
0x1801f956e  mov     rax, [rdi]
0x1801f9571  mov     rcx, rdi
0x1801f9574  mov     rax, [rax+10h]
0x1801f9578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f957d  mov     rax, [rbx]
0x1801f9580  mov     rax, [rax+10h]
0x1801f9584  mov     rcx, rbx
0x1801f9587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f958c  mov     al, bpl
0x1801f958f  mov     rbx, [rsp+68h+arg_0]
0x1801f9594  add     rsp, 30h
0x1801f9598  pop     r15
0x1801f959a  pop     r14
0x1801f959c  pop     r13
0x1801f959e  pop     r12
0x1801f95a0  pop     rdi
0x1801f95a1  pop     rsi
0x1801f95a2  pop     rbp
0x1801f95a3  retn
0x1801f95a5  call    cs:__imp_GetLastError
0x1801f95ac  nop     dword ptr [rax+rax+00h]
0x1801f95b1  mov     r15d, eax
0x1801f95b4  cmp     eax, 420h
0x1801f95b9  jz      loc_1801F951D
0x1801f95bf  mov     rcx, r13; void *
0x1801f95c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f95c7  mov     rcx, r14; hSCObject
0x1801f95ca  call    cs:__imp_CloseServiceHandle
0x1801f95d1  nop     dword ptr [rax+rax+00h]
0x1801f95d6  mov     ecx, [rsp+68h+uMode]; uMode
0x1801f95da  call    cs:__imp_SetErrorMode
0x1801f95e1  nop     dword ptr [rax+rax+00h]
0x1801f95e6  mov     ecx, r15d; dwErrCode
0x1801f95e9  call    cs:__imp_SetLastError
0x1801f95f0  nop     dword ptr [rax+rax+00h]
0x1801f95f5  mov     rax, [rdi]
0x1801f95f8  mov     rcx, rdi
0x1801f95fb  mov     rax, [rax+10h]
0x1801f95ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9604  jmp     loc_1801F9474
```
