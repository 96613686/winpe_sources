# CCorSvcMgr::ProcessWorkItems(void)

- ea: `0x180023834`
- end: `0x180023923`
- name: `?ProcessWorkItems@CCorSvcMgr@@AEAAXXZ`
- size: `239`
- prototype: `void __fastcall(CCorSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001eed0`

## callees

- `0x180005df0`
- `0x180006a2c`
- `0x180023834`
- `0x180023924`
- `0x180023bcc`
- `0x18003f280`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180023906`
- `KERNEL32!CloseHandle` at `0x180023906`

## string_xrefs

- `0x180023893`: `ngennicupdatelock.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall CCorSvcMgr::ProcessWorkItems(CCorSvcMgr *this)
{
  char v2; // al
  bool v3; // r8
  __int64 v4; // [rsp+30h] [rbp-58h] BYREF
  void **v5; // [rsp+38h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-48h]
  int v7; // [rsp+48h] [rbp-40h] BYREF
  __int64 v8; // [rsp+50h] [rbp-38h]
  __int64 v9; // [rsp+58h] [rbp-30h]
  BOOL v10; // [rsp+60h] [rbp-28h]
  void **v11; // [rsp+68h] [rbp-20h]
  __int64 v12; // [rsp+70h] [rbp-18h]
  __int64 v13; // [rsp+78h] [rbp-10h]
  void ***v15; // [rsp+98h] [rbp+10h] BYREF
  int *v16; // [rsp+A0h] [rbp+18h]

  v2 = *((_BYTE *)this + 344);
  v15 = &v5;
  hObject = (HANDLE)-1LL;
  v5 = &MachineWideMutexHolder::`vftable';
  if ( !v2 )
  {
    GetRootList(0);
    if ( *v5 == MachineWideMutexHolder::Acquire )
      MachineWideMutexHolder::Acquire((MachineWideMutexHolder *)&v5, L"ngennicupdatelock.dat", 0, 0);
    else
      ((void (__fastcall *)(void ***, const unsigned __int16 *, _QWORD, _QWORD))*v5)(
        &v5,
        L"ngennicupdatelock.dat",
        0,
        0);
  }
  v15 = (void ***)this;
  v7 = 0;
  v8 = 0;
  try
  {
    try
    {
      v16 = &v7;
      CCorSvcMgr::CompilePhase(this);
    }
    catch ( Exception *v4 )
    {
      Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v7);
      v8 = v4;
      throw;
    }
  }
  catch ( ... )
  {
    v12 = 0;
    v11 = &DelegatingException::`vftable';
    v13 = -1;
    v9 = v8;
    v10 = v8 != 0;
    Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v7, 2185, v3);
    while ( WorkQueue::GetJobFromPrimaryList((CCorSvcMgr *)((char *)this + 104)) )
      ;
    v10 = 0;
    throw;
  }
  CCorSvcMgr::ProcessWorkItems_::_2_::Cleanup::_Cleanup(&v15);
  v5 = &FileLockHolder::`vftable';
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
}

```

## disassembly

```asm
0x180023834  mov     r11, rsp
0x180023837  mov     [r11+20h], rbx
0x18002383b  mov     [r11+8], rcx
0x18002383f  push    rsi
0x180023840  sub     rsp, 80h
0x180023847  mov     rbx, rcx
0x18002384a  mov     al, [rcx+158h]
0x180023850  lea     rcx, [r11-50h]
0x180023854  mov     [r11+10h], rcx
0x180023858  lea     rsi, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18002385f  mov     [r11-50h], rsi
0x180023863  or      qword ptr [r11-48h], 0FFFFFFFFFFFFFFFFh
0x180023868  lea     rcx, ??_7MachineWideMutexHolder@@6B@; const MachineWideMutexHolder::`vftable'
0x18002386f  mov     [r11-50h], rcx
0x180023873  test    al, al
0x180023875  jnz     short loc_1800238B2
0x180023877  xor     ecx, ecx; int
0x180023879  call    ?GetRootList@@YAPEAVRootList@@H@Z; GetRootList(int)
0x18002387e  mov     rax, [rsp+88h+var_50]
0x180023883  mov     rax, [rax]
0x180023886  lea     rcx, ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x18002388d  xor     r9d, r9d; int *
0x180023890  xor     r8d, r8d; void *
0x180023893  lea     rdx, aNgennicupdatel; "ngennicupdatelock.dat"
0x18002389a  cmp     rax, rcx
0x18002389d  lea     rcx, [rsp+88h+var_50]; this
0x1800238a2  jnz     short loc_1800238AB
0x1800238a4  call    ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x1800238a9  jmp     short loc_1800238B2
0x1800238ab  call    cs:__guard_dispatch_icall_fptr
0x1800238b1  nop
0x1800238b2  mov     [rsp+88h+arg_8], rbx
0x1800238ba  and     [rsp+88h+var_40], 0
0x1800238bf  and     [rsp+88h+var_38], 0
0x1800238c5  lea     rax, [rsp+88h+var_40]
0x1800238ca  mov     [rsp+88h+arg_10], rax
0x1800238d2  mov     rcx, rbx; this
0x1800238d5  call    ?CompilePhase@CCorSvcMgr@@AEAAXXZ; CCorSvcMgr::CompilePhase(void)
0x1800238da  nop
0x1800238db  lea     rcx, [rsp+88h+arg_8]
0x1800238e3  call    _CCorSvcMgr__ProcessWorkItems____2___Cleanup___Cleanup
0x1800238e8  nop
0x1800238e9  lea     rax, [rsp+88h+var_50]
0x1800238ee  mov     [rsp+88h+arg_0], rax
0x1800238f6  mov     [rsp+88h+var_50], rsi
0x1800238fb  mov     rcx, [rsp+88h+hObject]; hObject
0x180023900  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180023904  jz      short loc_180023912
0x180023906  call    cs:__imp_CloseHandle
0x18002390c  or      [rsp+88h+hObject], 0FFFFFFFFFFFFFFFFh
0x180023912  mov     rbx, [rsp+88h+arg_18]
0x18002391a  add     rsp, 80h
0x180023921  pop     rsi
0x180023922  retn
```
